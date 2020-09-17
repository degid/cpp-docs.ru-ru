---
title: Класс lock
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: b06c293200bc85945e95996db3109c1f5fba8d8a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225622"
---
# <a name="lock-class"></a>Класс lock

Этот класс автоматизирует блокировку для синхронизации доступа к объекту из нескольких потоков.  При создании он получает блокировку, а после ее уничтожения освобождает блокировку.

## <a name="syntax"></a>Синтаксис

```cpp
ref class lock;
```

## <a name="remarks"></a>Примечания

`lock`доступен только для объектов CLR и может использоваться только в коде CLR.

На внутреннем уровне класс Lock использует <xref:System.Threading.Monitor> для синхронизации доступа. Дополнительные сведения см. в указанной статье.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|---------|-----------|
|[lock::lock](#lock)|Создает `lock` объект, при необходимости ожидающий получения блокировки в течение заданного промежутка времени или вообще без него.|
|[Блокировка блокировки:: ~](#tilde-lock)|Разструктура `lock` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|---------|-----------|
|[lock::acquire](#acquire)|Запрашивает блокировку на объект, при необходимости ожидая получения блокировки в течение заданного времени или вообще без него.|
|[lock::is_locked](#is-locked)|Указывает, удерживается ли блокировка.|
|[lock::release](#release)|Снимает блокировку.|
|[lock::try_acquire](#try-acquire)|Получает блокировку объекта, ожидая указанного времени и возвращая **`bool`** для сообщения об успешном приобретении, а не вызывая исключение.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|---------|-----------|
|[логический::operator &nbsp; bool](#operator-bool)|Оператор для использования `lock` в условном выражении.|
|[lock::operator==](#operator-equality)|Оператор равенства.|
|[Lock::operator!=](#operator-inequality)|Оператор неравенства.|

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\lock.h>

Мсклр **пространства имен**

## <a name="locklock"></a><a name="lock"></a>Блокировка:: Lock

Создает `lock` объект, при необходимости ожидающий получения блокировки в течение заданного промежутка времени или вообще без него.

```cpp
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

### <a name="parameters"></a>Параметры

*_object*<br/>
Объект, который необходимо заблокировать.

*_timeout*<br/>
Значение времени ожидания в миллисекундах или в виде <xref:System.TimeSpan> .

### <a name="exceptions"></a>Исключения

Вызывает исключение <xref:System.ApplicationException> , если получение блокировки не происходит до истечения времени ожидания.

### <a name="remarks"></a>Примечания

Первые три формы конструктора пытаются получить блокировку в `_object` течение заданного периода ожидания (или <xref:System.Threading.Timeout.Infinite> Если ни один из них не указан).

Четвертая форма конструктора не получает блокировку `_object` . `lock_later`является членом [перечисления lock_when](../dotnet/lock-when-enum.md). Чтобы получить блокировку в этом случае, используйте [блокировку:: получение](../dotnet/lock-acquire.md) или [блокировку:: try_acquire](../dotnet/lock-try-acquire.md) .

Блокировка будет автоматически освобождена при вызове деструктора.

`_object`не может иметь <xref:System.Threading.ReaderWriterLock> .  Если это так, будет выдаваться ошибка компилятора.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках. Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока. Главный поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять существование каких-либо рабочих потоков. Основное приложение ждет завершения работы до тех пор, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_lock.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locklock"></a><a name="tilde-lock"></a>Блокировка блокировки:: ~

Разструктура `lock` объекта.

```cpp
~lock();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает [блокировку:: Release](../dotnet/lock-release.md).

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока.  Главный поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять существование каких-либо рабочих потоков. Основное приложение ждет завершения работы до тех пор, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_dtor.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockacquire"></a><a name="acquire"></a>Блокировка:: получение

Запрашивает блокировку на объект, при необходимости ожидая получения блокировки в течение заданного времени или вообще без него.

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Параметры

*_timeout*<br/>
Значение времени ожидания в миллисекундах или в виде <xref:System.TimeSpan> .

### <a name="exceptions"></a>Исключения

Вызывает исключение <xref:System.ApplicationException> , если получение блокировки не происходит до истечения времени ожидания.

### <a name="remarks"></a>Примечания

Если значение времени ожидания не указано, то время ожидания по умолчанию — <xref:System.Threading.Timeout.Infinite> .

Если блокировка уже получена, эта функция не выполняет никаких действий.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока. Главный поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять существование каких-либо рабочих потоков. Основное приложение ждет завершения работы до тех пор, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockis_locked"></a><a name="is-locked"></a>Блокировка:: is_locked

Указывает, удерживается ли блокировка.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если блокировка удерживается; **`false`** в противном случае —.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока.  Главный поток приложения использует блокировку того же экземпляра класса, чтобы периодически проверять, существуют ли какие-либо рабочие потоки, и ожидать завершения работы до тех пор, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_is_locked.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l.is_locked()) { // check if we got the lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>логический::operator bool

Оператор для использования `lock` в условном выражении.

```cpp
operator bool();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если блокировка удерживается; **`false`** в противном случае —.

### <a name="remarks"></a>Примечания

Этот оператор фактически преобразует в `_detail_class::_safe_bool` , который является более безопасным, чем, **`bool`** так как он не может быть преобразован в целочисленный тип.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока. Главный поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять существование каких-либо рабочих потоков. Основное приложение ожидает завершения работы, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_op_bool.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l) { // use bool operator to check for lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockrelease"></a><a name="release"></a>Блокировка:: выпуск

Снимает блокировку.

```cpp
void release();
```

### <a name="remarks"></a>Примечания

Если блокировка не удерживается, `release` не выполняет никаких действий.

Вам не нужно вызывать эту функцию явным образом. Когда `lock` объект выходит из области видимости, его деструктор вызывает `release` .

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках. Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока. Главный поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять существование каких-либо рабочих потоков. Основное приложение ждет завершения работы до тех пор, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_release.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locktry_acquire"></a><a name="try-acquire"></a>Блокировка:: try_acquire

Получает блокировку объекта, ожидая указанного времени и возвращая **`bool`** для сообщения об успешном приобретении, а не вызывая исключение.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Параметры

*_timeout*<br/>
Значение времени ожидания в миллисекундах или в виде <xref:System.TimeSpan> .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если блокировка была получена, **`false`** в противном случае.

### <a name="remarks"></a>Примечания

Если блокировка уже получена, эта функция не выполняет никаких действий.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках. Класс использует блокировку самого себя, чтобы обеспечить целостность доступа к его внутренним данным для каждого потока. Главный поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять существование каких-либо рабочих потоков. Основное приложение ждет завершения работы до тех пор, пока все рабочие потоки не завершат свои задачи.

```cpp
// msl_lock_try_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator"></a><a name="operator-equality"></a>Lock::operator==

Оператор равенства.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Объект для сравнения на равенство.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`true`** , если совпадает с `t` объектом блокировки, **`false`** в противном случае — значение.

### <a name="example"></a>Пример

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="lockoperator"></a><a name="operator-inequality"></a>Lock::operator!=

Оператор неравенства.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Объект для сравнения на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **`true`** `t` , если объект отличается от объекта блокировки; **`false`** в противном случае — значение.

### <a name="example"></a>Пример

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```
