---
title: code_seg (__declspec)
ms.date: 11/04/2016
f1_keywords:
- code_seg_cpp
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
ms.openlocfilehash: 22703e92b1a127378c965ce12bcc4e5475b3e452
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180840"
---
# <a name="code_seg-__declspec"></a>code_seg (__declspec)

**Блок, относящийся только к системам Microsoft**

Атрибут объявления **code_seg** именует фрагмент текста исполняемого файла в OBJ-файле, в котором будут храниться объектный код для функций-членов функции или класса.

## <a name="syntax"></a>Синтаксис

```
__declspec(code_seg("segname")) declarator
```

## <a name="remarks"></a>Примечания

Атрибут `__declspec(code_seg(...))` позволяет помещать код в различные именованные сегменты, которые можно выгружать или блокировать в памяти по отдельности. Можно использовать этот атрибут для управления размещением шаблонов с созданными экземплярами и кода, созданного компилятором.

*Сегмент* — это именованный блок данных в OBJ-файле, который загружается в память как единое целое. *Сегмент текста* — это сегмент, содержащий исполняемый код. Термин *раздел* часто используется с сегментом.

Объектный код, создаваемый при определении `declarator`, помещается в сегмент текста, указанный `segname`, а это узкий строковый литерал. Имя `segname` не обязательно указывать [в директиве pragma, прежде](../preprocessor/section.md) чем его можно будет использовать в объявлении. По умолчанию если значение `code_seg` не указано, объектный код помещается в сегмент с именем .text. Атрибут **code_seg** переопределяет любую существующую директиву [#pragma code_seg](../preprocessor/code-seg.md) . Атрибут **code_seg** , применяемый к функции-члену, переопределяет любой атрибут **code_seg** , примененный к включающему классу.

Если сущность имеет атрибут **code_seg** , все объявления и определения одной и той же сущности должны иметь одинаковые **code_seg** атрибуты. Если базовый класс имеет атрибут **code_seg** , то производные классы должны иметь один и тот же атрибут.

Когда к функции-члену применяется атрибут **code_seg** , объектный код для этой функции помещается в указанный сегмент текста. Если этот атрибут применяется к классу, все функции-члены класса и вложенные классы, включая созданные компилятором специальные функции члены, помещаются в указанный сегмент. Локально определенные классы, например классы, определенные в теле функции-члена, не наследуют атрибут **code_seg** включающей области.

При применении атрибута **code_seg** к классу шаблона или функции шаблона все неявные специализации шаблона помещаются в указанный сегмент. Явные или частичные специализации не наследуют атрибут **code_seg** из основного шаблона. Вы можете указать тот же или другой атрибут **code_seg** в специализации. Атрибут **code_seg** нельзя применить к явному созданию экземпляра шаблона.

По умолчанию созданный компилятором, такой как специальная функция-член, помещается в сегмент .text. Директива `#pragma code_seg` не переопределяет это значение по умолчанию. Используйте атрибут **code_seg** в классе, шаблоне класса или шаблоне функции, чтобы управлять размещением кода, сгенерированного компилятором.

Лямбда-выражения наследуют **code_seg** атрибуты из их включающей области. Чтобы указать сегмент для лямбда-выражения, примените атрибут **code_seg** после предложения объявления параметра и перед любыми переменными или спецификациями исключений, а также любыми конечными спецификациями возвращаемого типа и телом лямбда-выражения. Дополнительные сведения см. в разделе [синтаксис лямбда-выражений](../cpp/lambda-expression-syntax.md). В этом примере определяется лямбда-выражение в сегменте с именем PagedMem:

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

Будьте внимательны при помещении определенных функций-членов, особенно виртуальных функций-членов, в разные сегменты. При определении виртуальной функции в производном классе, находящемся в выгруженном сегменте, когда метод базового класса находится в невыгруженном в сегменте, другие методы базового класса или пользовательский код могут предположить, что вызов виртуального метода не активирует ошибку выгрузки.

## <a name="example"></a>Пример

В этом примере показано, как атрибут **code_seg** управляет размещением сегментов при использовании неявной и явной специализации шаблона:

```cpp
// code_seg.cpp
// Compile: cl /EHsc /W4 code_seg.cpp

// Base template places object code in Segment_1 segment
template<class T>
class __declspec(code_seg("Segment_1")) Example
{
public:
   virtual void VirtualMemberFunction(T /*arg*/) {}
};

// bool specialization places code in default .text segment
template<>
class Example<bool>
{
public:
   virtual void VirtualMemberFunction(bool /*arg*/) {}
};

// int specialization places code in Segment_2 segment
template<>
class __declspec(code_seg("Segment_2")) Example<int>
{
public:
   virtual void VirtualMemberFunction(int /*arg*/) {}
};

// Compiler warns and ignores __declspec(code_seg("Segment_3"))
// in this explicit specialization
__declspec(code_seg("Segment_3")) Example<short>; // C4071

int main()
{
   // implicit double specialization uses base template's
   // __declspec(code_seg("Segment_1")) to place object code
   Example<double> doubleExample{};
   doubleExample.VirtualMemberFunction(3.14L);

   // bool specialization places object code in default .text segment
   Example<bool> boolExample{};
   boolExample.VirtualMemberFunction(true);

   // int specialization uses __declspec(code_seg("Segment_2"))
   // to place object code
   Example<int> intExample{};
   intExample.VirtualMemberFunction(42);
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
