---
title: Класс CMultiDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: af950d188c4e02a38a39ed3c672f0f8c4161bee8
ms.sourcegitcommit: 8fd49f8ac20457710ceb5403ca46fc73cb3f95f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85737482"
---
# <a name="cmultidoctemplate-class"></a>Класс CMultiDocTemplate

Определяет шаблон документа, реализующий многодокументный интерфейс (MDI).

## <a name="syntax"></a>Синтаксис

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>Участники

Функции элементов для этого класса являются виртуальными. Документацию см. в разделе [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) и [от CCmdTarget](../../mfc/reference/ccmdtarget-class.md) .

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кмултидоктемплате:: Кмултидоктемплате](#cmultidoctemplate)|Формирует объект `CMultiDocTemplate`.|

## <a name="remarks"></a>Примечания

Приложение MDI использует главное окно фрейма в качестве рабочей области, в которой пользователь может открыть ноль или несколько окон фрейма документа, каждый из которых отображает документ. Более подробное описание интерфейса MDI см. в разделе *рекомендации по интерфейсу Windows для разработки программного обеспечения*.

В шаблоне документа определяются отношения между тремя типами классов:

- Класс документа, производный от [CDocument](../../mfc/reference/cdocument-class.md).

- Класс представления, который отображает данные из указанного выше класса документа. Этот класс можно наследовать от [CView](../../mfc/reference/cview-class.md),, `CScrollView` `CFormView` или `CEditView` . (Можно также использовать `CEditView` напрямую.)

- Класс окна фрейма, который содержит представление. Для шаблона документа MDI можно наследовать этот класс от `CMDIChildWnd` или, если вам не нужно настраивать поведение окон фрейма документа, вы можете использовать [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) напрямую, не создавая собственный класс.

Приложение MDI может поддерживать несколько типов документов, и документы разных типов могут быть открыты одновременно. Приложение имеет один шаблон документа для каждого поддерживаемого типа документа. Например, если приложение MDI поддерживает как электронные таблицы, так и текстовые документы, то приложение имеет два `CMultiDocTemplate` объекта.

Приложение использует шаблоны документов, когда пользователь создает новый документ. Если приложение поддерживает несколько типов документов, платформа получает имена поддерживаемых типов документов из шаблонов документов и отображает их в списке в диалоговом окне Создать файл. После выбора пользователем типа документа приложение создает объект класса документа, объект окна фрейма и объект представления и присоединяет их друг к другу.

Вам не нужно вызывать никакие функции члена, `CMultiDocTemplate` кроме конструктора. Платформа обрабатывает `CMultiDocTemplate` объекты внутренним образом.

Дополнительные сведения о см `CMultiDocTemplate` . в разделе [шаблоны документов и процесс создания документа/представления](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>Кмултидоктемплате:: Кмултидоктемплате

Формирует объект `CMultiDocTemplate`.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Параметры

*нидресаурце*<br/>
Указывает идентификатор ресурсов, используемых с типом документа. Это может быть меню, значок, таблица сочетаний клавиш и строковые ресурсы.

Строковый ресурс состоит из до семи подстрок, разделенных символом "\n" (символ "\n" необходим в качестве заполнителя, если подстрока не включена; Однако замыкающие символы "\n" не требуются); эти подстроки описывают тип документа. Сведения о подстроках см. в разделе [CDocTemplate:: жетдокстринг](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Строка начинается с символа "\n", поскольку первая подстрока не используется для приложений MDI и поэтому не включается. Эту строку можно изменить с помощью редактора строк. вся строка отображается в виде одной записи в редакторе строк, а не в виде семи отдельных записей.

Дополнительные сведения об этих типах ресурсов см. в разделе [редакторы ресурсов](../../windows/resource-editors.md).

*пдоккласс*<br/>
Указывает на `CRuntimeClass` объект класса Document. Этот класс является производным от класса, `CDocument` который определяется для представления документов.

*пфрамекласс*<br/>
Указывает на `CRuntimeClass` объект класса фреймового окна. Этот класс может быть `CMDIChildWnd` производным от класса или, `CMDIChildWnd` Если требуется поведение по умолчанию для окон фрейма документа.

*пвиевкласс*<br/>
Указывает на `CRuntimeClass` объект класса представления. Этот класс является производным от класса, `CView` который определяется для вывода документов.

### <a name="remarks"></a>Примечания

Динамически выделяйте один `CMultiDocTemplate` объект для каждого типа документа, поддерживаемого приложением, и передайте каждое из них в `CWinApp::AddDocTemplate` `InitInstance` функцию члена класса приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

Ниже приведен второй пример.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>См. также

[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)
