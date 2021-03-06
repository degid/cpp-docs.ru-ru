---
title: /SECTION (указание атрибутов секции)
ms.date: 12/29/2017
f1_keywords:
- /section
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.openlocfilehash: 0a52e9c9dcd53b01f17dc36825732b34771c75bb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492629"
---
# <a name="section-specify-section-attributes"></a>/SECTION (указание атрибутов секции)

> **/Section:** _имя_, [[ **!** ] {**Декпрсв**}] [ **, Выровняйте =** _число_]

## <a name="remarks"></a>Примечания

Параметр **/section** изменяет атрибуты раздела, переопределяя атрибуты, заданные при компиляции OBJ-файла раздела.

*Раздел* в переносимом исполняемом файле (PE) является именованным непрерывным блоком памяти, который содержит код или данные. Некоторые разделы содержат код или данные, которые программа объявила и использует напрямую, а другие разделы данных создаются компоновщиком и диспетчером библиотек (lib. exe) и содержат сведения, необходимые для операционной системы. Дополнительные сведения см. в разделе [Формат PE](/windows/win32/Debug/pe-format).

Укажите двоеточие (:) и *имя*раздела. *Имя* чувствительно к регистру.

Не используйте следующие имена, так как они конфликтуют со стандартными именами. Например,. sdata используется на платформах RISC:

- . Arch

- . BSS

- . Data

- . едата

- . иДата

- . pdata

- . rdata

- . reloc

- . rsrc

- . SBSS

- . sdata

- . срдата

- . текст

- . XData

Укажите один или несколько атрибутов для раздела. Символы атрибутов, перечисленные ниже, не учитывают регистр. Необходимо указать все атрибуты, которые должен иметь раздел. Пропущенный символ атрибута приводит к отключению бита атрибута. Если R, W или E не задано, существующее состояние чтения, записи или исполняемого файла остается неизменным.

Чтобы инвертировать атрибут, перед его символом следует указать восклицательный знак (!). В этой таблице показаны значения атрибутов.

|Знак|Атрибут|Значение|
|---------------|---------------|-------------|
|E|Выполнение|Раздел является исполняемым|
|R|Чтение|Разрешает операции чтения с данными|
|W|Write|Разрешает операции записи в данные|
|S|Shared|Разделяет раздел на все процессы, которые загружают образ.|
|D|Отклонено|Помечает раздел как отброшенный|
|K|Кэшируемые|Помечает раздел как некэшированный|
|С|Выгружаемой|Помечает раздел как нестраничный|

K и P обычно используются в тех ситуациях, когда соответствующие им флаги разделов используются в отрицательном смысле. Если указать один из них в разделе. Text с помощью параметра **/Section:. Text, K** , то при запуске [dumpbin](dumpbin-options.md) с параметром [/headers](headers.md) различия в разделах не различаются. раздел уже был неявно кэширован. Чтобы удалить значение по умолчанию, укажите параметр **/Section:. Text,! K** вместо этого. DUMPBIN отображает характеристики раздела, включая "не кэшировано".

Возможно, раздел PE-файла, в котором нет набора E, R или W, является недопустимым.

Аргумент **Выровнять =** _Number_ позволяет указать значение выравнивания для определенного раздела. Аргумент _Number_ находится в байтах и должен быть степенью числа 2. Дополнительные сведения см. в разделе [/align](align-section-alignment.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойства**командной строки** **компоновщика** >  **свойств** > конфигурации.

1. Введите параметр в поле **Дополнительные параметры** . Нажмите кнопку **ОК** или **Применить** , чтобы применить изменение.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
