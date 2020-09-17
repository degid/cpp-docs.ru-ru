---
title: Необработанные указатели (C++)
description: Использование необработанных указателей в C++
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- ':::no-loc(void):::'
- ':::no-loc(nullptr):::'
- ':::no-loc(const):::'
- ':::no-loc(char):::'
- ':::no-loc(new):::'
- ':::no-loc(delete):::'
ms.openlocfilehash: 53679559888191fe7f2aad7cb5a70d607974ae96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233656"
---
# <a name="raw-pointers-c"></a>Необработанные указатели (C++)

*Указатель* — это тип переменной. Он сохраняет адрес объекта в памяти и используется для доступа к этому объекту. *Необработанный указатель* — это указатель, время существования которого не управляется инкапсулированным объектом, например [интеллектуальным указателем](smart-pointers-modern-cpp.md). Необработанному указателю может быть присвоен адрес другой переменной, не являющейся указателем, или ему может быть присвоено значение [:::no-loc(nullptr):::](:::no-loc(nullptr):::.md) . Указатель, которому не присвоено значение, содержит случайные данные.

Указатель может также быть *разыменован* для получения значения объекта, на который он указывает. *Оператор доступа к членам* предоставляет доступ к членам объекта.

```cpp
    int* p = :::no-loc(nullptr):::; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

Указатель может указывать на типизированный объект или на **`:::no-loc(void):::`** . Когда программа выделяет объект в [куче](https://wikipedia.org/wiki/Heap) в памяти, он получает адрес этого объекта в виде указателя. Такие указатели называются *указателями-владельцами*. Для явного освобождения выделенного в куче объекта, когда он больше не нужен, необходимо использовать указатель-владелец (или его копию). Сбой освобождения памяти приводит к *утечке памяти*и отображению этого расположения памяти, недоступного для любой другой программы на компьютере. Память, выделенная с помощью **`:::no-loc(new):::`** , должна быть освобождена с помощью **`:::no-loc(delete):::`** ( ** :::no-loc(delete)::: \[ **или). Дополнительные сведения см. в разделе [ :::no-loc(new)::: :::no-loc(delete)::: операторы и](:::no-loc(new):::-and-:::no-loc(delete):::-operators.md).

```cpp
    MyClass* mc = :::no-loc(new)::: MyClass(); // allocate object on the heap
    mc->print(); // access class member
    :::no-loc(delete)::: mc; // :::no-loc(delete)::: object (please don't forget!)
```

Указатель (если он не объявлен как **`:::no-loc(const):::`** ) можно увеличить или уменьшить до точки в другом месте в памяти. Эта операция называется *арифметикой указателя*. Он используется в программировании в стиле C для итерации элементов в массивах или других структурах данных. **`:::no-loc(const):::`** Невозможно создать указатель для указания на другое место в памяти, и в этом смысле похоже на [ссылку](references-cpp.md). Дополнительные сведения см. в разделе [ :::no-loc(const)::: и временные указатели](:::no-loc(const):::-and-volatile-pointers.md).

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    :::no-loc(const)::: :::no-loc(char):::* str = "Hello world";

    :::no-loc(const)::: int c = 1;
    :::no-loc(const)::: int* p:::no-loc(const)::: = &c; // declare a non-:::no-loc(const)::: pointer to :::no-loc(const)::: int
    :::no-loc(const)::: int c2 = 2;
    p:::no-loc(const)::: = &c2;  // OK p:::no-loc(const)::: itself isn't :::no-loc(const):::
    :::no-loc(const)::: int* :::no-loc(const)::: p:::no-loc(const):::2 = &c;
    // p:::no-loc(const):::2 = &c2; // Error! p:::no-loc(const):::2 is :::no-loc(const):::.
```

В 64-разрядных операционных системах указатель имеет размер 64 бит. Размер указателя системы определяет, сколько памяти она может иметь. Все копии точки указателя на одно и то же место в памяти. Указатели (вместе со ссылками) широко используются в C++ для передачи больших объектов в функции и из них. Это связано с тем, что часто более эффективно копировать адрес объекта, чем копировать весь объект. При определении функции укажите параметры-указатели, как **`:::no-loc(const):::`** если бы вы не предполагали, что функция не изменит объект. Как правило, **`:::no-loc(const):::`** ссылки являются предпочтительным способом передачи объектов в функции, если только значение объекта не может быть **`:::no-loc(nullptr):::`** .

[Указатели на функции](#pointers_to_functions) позволяют передавать функции другим функциям и использоваться для обратных вызовов в программировании в стиле C. В современных C++ для этой цели используются [лямбда-выражения](lambda-expressions-in-cpp.md) .

## <a name="initialization-and-member-access"></a>Доступ к инициализации и членам

В следующем примере показано, как объявить, инициализировать и использовать необработанный указатель. Он инициализируется с помощью **`:::no-loc(new):::`** , чтобы указать объект, выделенный в куче, который необходимо явным образом **`:::no-loc(delete):::`** . В примере также показано несколько опасностей, связанных с необработанными указателями. (Помните, что этот пример — программирование в стиле C, а не современные C++!)

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
:::no-loc(void)::: func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
:::no-loc(void)::: func_B(MyClass mc)
{
    // mc here is a regular object, not a pointer.
    // Use the "." operator to access members.
    // This statement modifies only the local copy of mc.
    mc.num = 21;
    std::cout << "Local copy of mc:";
    mc.print(); // "Erika, 21"
}


int main()
{
    // Use the * operator to declare a pointer type
    // Use :::no-loc(new)::: to allocate and initialize memory
    MyClass* pmc = :::no-loc(new)::: MyClass{ 108, "Nick" };

    // Prints the memory address. Usually not what you want.
    std::cout << pmc << std::endl;

    // Copy the pointed-to object by dereferencing the pointer
    // to access the contents of the memory location.
    // mc is a separate object, allocated here on the stack
    MyClass mc = *pmc;

    // Declare a pointer that points to mc using the addressof operator
    MyClass* pcopy = &mc;

    // Use the -> operator to access the object's public members
    pmc->print(); // "Nick, 108"

    // Copy the pointer. Now pmc and pmc2 point to same object!
    MyClass* pmc2 = pmc;

    // Use copied pointer to modify the original object
    pmc2->name = "Erika";
    pmc->print(); // "Erika, 108"
    pmc2->print(); // "Erika, 108"

    // Pass the pointer to a function.
    func_A(pmc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*pmc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    :::no-loc(delete):::(pmc); // don't forget to give memory back to operating system!
   // :::no-loc(delete):::(pmc2); //crash! memory location was already :::no-loc(delete):::d
}
```

## <a name="pointer-arithmetic-and-arrays"></a>Арифметические и массивные указатели

Указатели и массивы тесно связаны друг с друга. Когда массив передается в функцию по значению, он передается в качестве указателя на первый элемент. В следующем примере показаны следующие важные свойства указателей и массивов.

- **`sizeof`** оператор возвращает общий размер массива в байтах
- чтобы определить количество элементов, разделите общее число байтов на размер одного элемента.
- когда массив передается в функцию, он *декайс* к типу указателя
- **`sizeof`** оператор, применяемый к указателю, возвращает размер указателя, 4 байта на x86 или 8 байт в x64

```cpp
#include <iostream>

:::no-loc(void)::: func(int arr[], int length)
{
    // returns pointer size. not useful here.
    size_t test = sizeof(arr);

    for(int i = 0; i < length; ++i)
    {
        std::cout << arr[i] << " ";
    }
}

int main()
{

    int i[5]{ 1,2,3,4,5 };
    // sizeof(i) = total bytes
    int j = sizeof(i) / sizeof(i[0]);
    func(i,j);
}
```

Некоторые арифметические операции можно использовать для :::no-loc(const)::: неуказателей, чтобы они указывали на другое место в памяти. Указатели увеличиваются и уменьшаются с помощью **++** **+=** операторов, **-=** и **--** . Этот метод можно использовать в массивах и особенно полезен в буферах нетипизированных данных. Значение увеличивается на величину **:::no-loc(void):::\*** **`:::no-loc(char):::`** (1 байт). Типизированный указатель увеличивается по размеру типа, на который он указывает.

В следующем примере показано, как можно использовать арифметические действия с указателями для доступа к отдельным пикселям точечного рисунка в Windows. Обратите внимание на **`:::no-loc(new):::`** использование **`:::no-loc(delete):::`** операторов и и разыменование оператора.

```cpp
#include <Windows.h>
#include <fstream>

using namespace std;

int main()
{

    BITMAPINFOHEADER header;
    header.biHeight = 100; // Multiple of 4 for simplicity.
    header.biWidth = 100;
    header.biBitCount = 24;
    header.biPlanes = 1;
    header.biCompression = BI_RGB;
    header.biSize = sizeof(BITMAPINFOHEADER);

    :::no-loc(const):::expr int bufferSize = 30000;
    unsigned :::no-loc(char):::* buffer = :::no-loc(new)::: unsigned :::no-loc(char):::[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned :::no-loc(char):::* begin = &buffer[0];
    unsigned :::no-loc(char):::* end = &buffer[0] + bufferSize;
    unsigned :::no-loc(char):::* p = begin;
    :::no-loc(const):::expr int pixelWidth = 3;
    :::no-loc(const):::expr int borderWidth = 2;

    while (p < end)
    {
            // Is top or bottom edge?
        if ((p < begin + header.biWidth * pixelWidth * borderWidth)
            || (p > end - header.biWidth * pixelWidth * borderWidth)
            // Is left or right edge?
            || (p - begin) % (header.biWidth * pixelWidth) < (borderWidth * pixelWidth)
            || (p - begin) % (header.biWidth * pixelWidth) > ((header.biWidth - borderWidth) * pixelWidth))
        {
            *p = 0x0; // Black
        }
        else
        {
            *p = 0xC3; // Gray
        }
        p++; // Increment one byte sizeof(unsigned :::no-loc(char):::).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<:::no-loc(char):::*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(&header), sizeof(header));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(begin), bufferSize);

    :::no-loc(delete):::[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="no-locvoid-pointers"></a>:::no-loc(void):::* указатели

Указатель на **`:::no-loc(void):::`** просто указывает на расположение необработанной памяти. Иногда необходимо использовать **:::no-loc(void):::\*** указатели, например при передаче между кодом C++ и функциями C.

Если типизированный указатель приводится к :::no-loc(void)::: указателю, содержимое области памяти не изменяется. Однако сведения о типе теряются, поэтому нельзя выполнять операции увеличения или уменьшения. Место в памяти может быть приведено к типу, например, от `MyClass*` до **`:::no-loc(void):::*`** и обратно в `MyClass*` . Такие операции по сути подвержены ошибкам и нуждаются в отличных от них ошибках :::no-loc(void)::: . Современный C++ не рекомендует использовать :::no-loc(void)::: указатели практически во всех обстоятельствах.

```cpp

//func.c
:::no-loc(void)::: func(:::no-loc(void):::* data, int length)
{
    :::no-loc(char):::* c = (:::no-loc(char):::*)(data);

    // fill in the buffer with data
    for (int i = 0; i < length; ++i)
    {
        *c = 0x41;
        ++c;
    }
}

// main.cpp
#include <iostream>

extern "C"
{
    :::no-loc(void)::: func(:::no-loc(void):::* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = :::no-loc(new)::: MyClass{10, "Marian"};
    :::no-loc(void):::* p = static_cast<:::no-loc(void):::*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator :::no-loc(new)::: to allocate untyped memory block
    :::no-loc(void):::* p:::no-loc(void)::: = operator :::no-loc(new):::(1000);
    :::no-loc(char):::* p:::no-loc(char)::: = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::);
    for(:::no-loc(char):::* c = p:::no-loc(char):::; c < p:::no-loc(char)::: + 1000; ++c)
    {
        *c = 0x00;
    }
    func(p:::no-loc(void):::, 1000);
    :::no-loc(char)::: ch = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::)[0];
    std::cout << ch << std::endl; // 'A'
    operator :::no-loc(delete):::(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>Указатели на функции

В программировании в стиле C указатели функций используются в основном для передачи функций другим функциям. Этот метод позволяет вызывающему объекту настраивать поведение функции, не изменяя ее. В современных C++ [лямбда-выражения](lambda-expressions-in-cpp.md) обеспечивают те же возможности, что и более строгая типизация, и другие преимущества.

Объявление указателя на функцию указывает сигнатуру, которую должна иметь функция, на которую должен быть указан объект.

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
:::no-loc(void)::: (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

В следующем примере показана функция `combine` , которая принимает в качестве параметра любую функцию, которая принимает `std::string` и возвращает `std::string` . В зависимости от функции, которая передается `combine` , она либо добавляет строку в начале, либо добавляет ее.

```cpp
#include <iostream>
#include <string>

using namespace std;

string base {"hello world"};

string append(string s)
{
    return base.append(" ").append(s);
}

string prepend(string s)
{
    return s.append(" ").append(base);
}

string combine(string s, string(*g)(string a))
{
    return (*g)(s);
}

int main()
{
    cout << combine("from MSVC", append) << "\n";
    cout << combine("Good morning and", prepend) << "\n";
}
```

## <a name="see-also"></a>См. также статью

[Интеллектуальные указатели](smart-pointers-modern-cpp.md) 
 [Оператор косвенного обращения: *](indirection-operator-star.md)<br/>
[Оператор address-of: &](address-of-operator-amp.md)</br>
[Добро пожаловать в C++](welcome-back-to-cpp-modern-cpp.md)
