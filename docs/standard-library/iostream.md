---
title: '&lt;iostream&gt;'
ms.date: 09/20/2017
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
ms.openlocfilehash: 5805d441b4fc2fc2927b57f4d94ba8b8ccecb22a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845475"
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;

Объявляет объекты, управляющие чтением из стандартных потоков и записью в них. Это, как правило, единственный заголовок, необходимый для ввода и вывода из программы на C++.

## <a name="syntax"></a>Синтаксис

```cpp
#include <iostream>
```

> [!NOTE]
> \<iostream>Библиотека использует `#include <ios>` операторы,, `#include <streambuf>` `#include <istream>` и `#include <ostream>` .

## <a name="remarks"></a>Примечания

Объекты можно разделить на две группы:

- [cIn](#cin), [cout](#cout), [cerr](#cerr)и [clog](#clog) являются ориентированными на байты и выполняют обычную передачу данных по времени.

- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr) и [wclog](#wclog) — для двухбайтовых значений, они выполняют преобразования в двухбайтовые символы и из двухбайтовых символов, управление которыми осуществляется внутри программы.

После выполнения определенных операций с потоком, например со стандартным входом, нельзя выполнять операции с разными ориентациями в одном потоке. Таким образом, программа не может взаимодействовать как с [cIn](#cin) , так и с [wcin](#wcin), например.

Все объекты, объявленные в этом заголовке, совместно используют свойство довольно необычная — вы можете предположить, что они созданы до любых статических объектов, которые вы определяете, в записи преобразования, которая включает \<iostream> . Точно так же можно предположить, что эти объекты не уничтожаются до деструкторов для любых таких статических объектов, которые вы определяете. (Однако выходные потоки сбрасываются во время завершения программы.) Таким образом, можно безопасно считывать или записывать в стандартные потоки перед запуском программы и после завершения программы.

Однако эта гарантия не является универсальной. Статический конструктор может вызвать функцию в другой записи преобразования. Вызываемая функция не может предположить, что объекты, объявленные в этом заголовке, были созданы с учетом неопределенного порядка, в котором единицы преобразования участвуют в статической конструкции. Для использования этих объектов в таком контексте нужно сначала создать объект класса [ios_base::Init](../standard-library/ios-base-class.md#init).

### <a name="global-stream-objects"></a>Глобальные объекты потоков

|Имя|Описание|
|-|-|
|[cerr](#cerr)|Указывает глобальный поток `cerr`.|
|[CIN](#cin)|Указывает глобальный поток `cin`.|
|[clog](#clog)|Указывает глобальный поток `clog`.|
|[cout](#cout)|Указывает глобальный поток `cout`.|
|[wcerr](#wcerr)|Указывает глобальный поток `wcerr`.|
|[wcin](#wcin)|Указывает глобальный поток `wcin`.|
|[wclog](#wclog)|Указывает глобальный поток `wclog`.|
|[wcout](#wcout)|Указывает глобальный поток `wcout`.|

### <a name="cerr"></a><a name="cerr"></a> cerr

Объект `cerr` управляет выводом в буфер потока, связанный с объектом `stderr` , объявленный в \<cstdio> .

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой без буферизации в стандартный вывод ошибок в виде байтового потока. После создания объекта выражение `cerr.`[флаги](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) отлично от нуля, и `cerr.tie() == &cout`.

#### <a name="example"></a>Пример

```cpp
// iostream_cerr.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void TestWide( )
{
   int i = 0;
   wcout << L"Enter a number: ";
   wcin >> i;
   wcerr << L"test for wcerr" << endl;
   wclog << L"test for wclog" << endl;
}

int main( )
{
   int i = 0;
   cout << "Enter a number: ";
   cin >> i;
   cerr << "test for cerr" << endl;
   clog << "test for clog" << endl;
   TestWide( );
}
```

### <a name="cin"></a><a name="cin"></a> CIN

Указывает глобальный поток `cin`.

```cpp
extern istream cin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [istream](../standard-library/istream-typedefs.md#istream).

#### <a name="remarks"></a>Примечания

Объект контролирует получение данных из стандартного ввода, как потока байтов. После создания объекта вызов `cin.`[tie](../standard-library/basic-ios-class.md#tie) возвращает `&`[cout](#cout).

#### <a name="example"></a>Пример

В этом примере `cin` устанавливает бит сбоя в потоке, если он поступает между нечисловыми символами. Программа очищает бит сбоя и удаляет из потока недопустимый символ, чтобы продолжить.

```cpp
// iostream_cin.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
   int x;
   cout << "enter choice:";
   cin >> x;
   while (x < 1 || x > 4)
   {
      cout << "Invalid choice, try again:";
      cin >> x;
      // not a numeric character, probably
      // clear the failure and pull off the non-numeric character
      if (cin.fail())
      {
         cin.clear();
         char c;
         cin >> c;
      }
   }
}
```

```Output
2
```

### <a name="clog"></a><a name="clog"></a> clog

Указывает глобальный поток `clog`.

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой с буферизацей в стандартный вывод ошибок в виде байтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `clog`.

### <a name="cout"></a><a name="cout"></a> cout

Указывает глобальный поток `cout`.

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [ostream](../standard-library/ostream-typedefs.md#ostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой в стандартный вывод в виде байтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `cout`.

### <a name="wcerr"></a><a name="wcerr"></a> вцерр

Указывает глобальный поток `wcerr`.

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой без буферизации в стандартный вывод ошибок в виде двухбайтового потока. После создания объекта выражение `wcerr.`[флаги](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) отлично от нуля.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcerr`.

### <a name="wcin"></a><a name="wcin"></a> wcin

Указывает глобальный поток `wcin`.

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wistream](../standard-library/istream-typedefs.md#wistream).

#### <a name="remarks"></a>Примечания

Этот объект управляет извлечением из стандартного ввода в виде двухбайтового потока. После создания объекта вызов `wcin.`[tie](../standard-library/basic-ios-class.md#tie) возвращает `&`[wcout](#wcout).

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcin`.

### <a name="wclog"></a><a name="wclog"></a> вклог

Указывает глобальный поток `wclog`.

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой с буферизацей в стандартный вывод ошибок в виде двухбайтового потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wclog`.

### <a name="wcout"></a><a name="wcout"></a> wcout

Указывает глобальный поток `wcout`.

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>Возвращаемое значение

Объект [wostream](../standard-library/ostream-typedefs.md#wostream).

#### <a name="remarks"></a>Примечания

Этот объект управляет вставкой в стандартный вывод в качестве широкого потока.

#### <a name="example"></a>Пример

См. [cerr](#cerr) с примером использования `wcout`.

Экземпляры `CString`в операторе `wcout` необходимо привести к `const wchar_t*`, как показано в следующем примере.

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

Дополнительные сведения см. в разделе [Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md).

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
