---
title: Прагма const_seg
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
ms.openlocfilehash: 04467df1205bd6d4c70687422572aef898d46f68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231628"
---
# <a name="const_seg-pragma"></a>Прагма const_seg

Указывает раздел (сегмент), в котором переменные [const](../cpp/const-cpp.md) хранятся в файле объекта (obj).

## <a name="syntax"></a>Синтаксис

> **#pragma const_seg (** ["*имя раздела*" [ **,** "*раздел-класс*"]] **)**\
> **#pragma const_seg (** { **Push**  |  **POP** } [ **,** *идентификатор* ] [ **,** "*section-name*" [ **,** "*section-Class*"]] **)**

### <a name="parameters"></a>Параметры

**распространение**\
Используемых Помещает запись во внутренний стек компилятора. **Принудительная отправка** может иметь *идентификатор* и *имя раздела*.

**Рор**\
Используемых Удаляет запись из верхнего внутреннего стека компилятора. **POP** может иметь *идентификатор* и *имя раздела*. С помощью *идентификатора*можно открыть несколько записей, используя только одну команду **POP** . Имя *раздела* преобразуется в имя активного раздела const после точки подключения.

*identifier*\
Используемых При использовании с **Push**назначает имя записи во внутреннем стеке компилятора. При использовании с **POP**директива выводит записи из внутреннего стека до тех пор, пока *идентификатор* не будет удален. Если *идентификатор* не найден во внутреннем стеке, ничего не извлекается.

"*раздел-имя*" \
Используемых Имя раздела. При использовании с **POP**стек извлекается, а *имя раздела* становится активным именем раздела const.

"*класс-раздел*" \
Используемых Игнорируется, но входит в совместимость с версиями Microsoft C++, предшествующими версии 2,0.

## <a name="remarks"></a>Примечания

*Раздел* в объектном файле — это именованный блок данных, который загружается в память как единое целое. *Раздел const* — это раздел, содержащий постоянные данные. В этой статье термины *сегмент* и *раздел* имеют одинаковое значение.

Директива pragma **const_seg** указывает компилятору разместить все элементы постоянных данных из записи преобразования в раздел const с именем *section-name*. По умолчанию в объектном файле для **`const`** переменных используется раздел `.rdata` . Некоторые **`const`** переменные, такие как скалярные, автоматически встроены в поток кода. Встроенный код не отображается в `.rdata` . Директива pragma **const_seg** без параметра *name раздела* сбрасывает имя раздела для последующих **`const`** элементов данных до `.rdata` .

При определении объекта, для которого требуется динамическая инициализация `const_seg` , результат является неопределенным поведением.

Список имен, которые не следует использовать для создания раздела, см. в разделе [/section](../build/reference/section-specify-section-attributes.md).

Можно также указать разделы для инициализированных данных ([data_seg](../preprocessor/data-seg.md)), неинициализированные данные ([bss_seg](../preprocessor/bss-seg.md)) и функции ([code_seg](../preprocessor/code-seg.md)).

Для просмотра объектных файлов можно использовать приложение [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) . Версии DUMPBIN для каждой поддерживаемой целевой архитектуры входят в состав Visual Studio.

## <a name="example"></a>Пример

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="see-also"></a>См. также раздел

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
