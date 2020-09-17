---
title: Класс CSingleDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 5a014b35a6cd2d12367e190e4d6dd689e28eae66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318345"
---
# <a name="csingledoctemplate-class"></a>Класс CSingleDocTemplate

Определяет шаблон документа, реализующий интерфейс одного документа (SDI).

## <a name="syntax"></a>Синтаксис

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Формирует объект `CSingleDocTemplate`.|

## <a name="remarks"></a>Примечания

Приложение SDI использует окно основной кадр для отображения документа; одновременно может быть открыт только один документ.

Шаблон документа определяет взаимосвязь между тремя типами классов:

- Класс документов, который `CDocument`вы получаете из .

- Класс представления, отображаемый данными из класса документов, перечисленных выше. Вы можете получить `CView`этот `CScrollView` `CFormView`класс `CEditView`из , , или . (Вы также `CEditView` можете использовать непосредственно.)

- Класс окна кадра, который содержит представление. Для шаблона документа SDI можно извлечь `CFrameWnd`этот класс из; если вам не нужно настраивать поведение окна основного кадра, вы можете использовать `CFrameWnd` непосредственно без создания собственного класса.

Приложение SDI обычно поддерживает один тип документа, `CSingleDocTemplate` поэтому оно имеет только один объект. Открыт одновременно только один документ.

Вам не нужно вызывать какие-либо `CSingleDocTemplate` функции члена, кроме конструктора. Фрейм `CSingleDocTemplate` обрабатывает объекты внутренне.

Для получения дополнительной `CSingleDocTemplate`информации об использовании [см.](../../mfc/document-templates-and-the-document-view-creation-process.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a>CSingleDocTemplate::CSingleDocTemplate

Формирует объект `CSingleDocTemplate`.

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Упогоняет идентификатор ресурсов, используемых с типом документа. Это может включать меню, значок, таблицу акселератора и строковые ресурсы.

Ресурс строки состоит из семи подстроек, разделенных символом 'n' (символ 'n' необходим в качестве заполнителя, если подстрока не включена; однако, задние символы 'n' не являются необходимыми); эти подстроки описывают тип документа. Для получения информации о подстроках [см. CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот ресурс строки находится в файле ресурса приложения. Пример:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

Эту строку можно отредконить с помощью строки редактора; вся строка отображается как одна запись в строке редактора, а не как семь отдельных записей.

Для получения дополнительной информации об [String Editor](../../windows/string-editor.md)этих типах ресурсов см.

*pDocClass*<br/>
Указывает на `CRuntimeClass` объект класса документов. Этот класс `CDocument`— это класс, который вы определяете для представления документов.

*pFrameClass*<br/>
Указывает на `CRuntimeClass` объект класса окна кадра. Этот класс может `CFrameWnd`быть -производным `CFrameWnd` классом, или он может быть сам, если вы хотите поведение по умолчанию для окна основного кадра.

*pViewClass*<br/>
Указывает на `CRuntimeClass` объект класса представления. Этот класс `CView`является классом, который вы определяете для отображения документов.

### <a name="remarks"></a>Примечания

Динамически выделите `CSingleDocTemplate` объект `CWinApp::AddDocTemplate` и `InitInstance` передайте его от функции члена класса приложений.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Класс CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)
