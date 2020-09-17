---
title: Фабрики классов и прослушивание
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: 939d7156a9bd7bf0778d2ab4a40acb2afe10cf6e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845930"
---
# <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание

Для создания экземпляра элемента управления OLE приложение-контейнер вызывает функцию-член фабрики класса элемента управления. Поскольку элемент управления является фактическим объектом OLE, фабрика класса отвечает за создание экземпляров элемента управления. Каждый класс элементов управления OLE должен иметь фабрику класса.

Еще одна важная особенность элементов управления OLE — возможность принудительного применения лицензии. Контролвизард позволяет включить лицензирование во время создания проекта элемента управления. Дополнительные сведения о лицензировании элементов управления см. в статье [элементы управления ActiveX: лицензирование элемента управления ActiveX](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).

В следующей таблице перечислены несколько макросов и функций, используемых для объявления и реализации фабрики класса элемента управления, а также для лицензирования вашего элемента управления.

### <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание

|Макрос или функция|Описание|
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Объявляет фабрику класса для элемента управления OLE или страницы свойств.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Реализует функцию элемента управления `GetClassID` и объявляет экземпляр фабрики класса.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|Начинает объявление любых функций лицензирования.|
|[END_OLEFACTORY](#end_olefactory)|Завершает объявление любых функций лицензирования.|
|[AfxVerifyLicFile](#afxverifylicfile)|Проверяет, лицензирован ли элемент управления для использования на определенном компьютере.|

## <a name="declare_olecreate_ex"></a><a name="declare_olecreate_ex"></a> DECLARE_OLECREATE_EX

Объявляет фабрику класса и функцию- `GetClassID` член класса Control.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления.

### <a name="remarks"></a>Примечания

Используйте этот макрос в файле заголовка класса Control для элемента управления, который не поддерживает лицензирование.

Обратите внимание, что этот макрос выполняет ту же цель, что и следующий пример кода:

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="implement_olecreate_ex"></a><a name="implement_olecreate_ex"></a> IMPLEMENT_OLECREATE_EX

Реализует фабрику класса элемента управления и функцию [member в](../../mfc/reference/colecontrol-class.md#getclassid) классе элемента управления.

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса страницы свойств элемента управления.

*external_name*<br/>
Имя объекта, доступное приложениям.

*l, W1, W2, B1, B2, B3, B4, B5, B6, B7, B8*<br/>
Компоненты CLSID класса. Дополнительные сведения об этих параметрах см. в примечаниях для [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate).

### <a name="remarks"></a>Примечания

Этот макрос должен присутствовать в файле реализации для любого класса элементов управления, который использует макрос DECLARE_OLECREATE_EX или макросы BEGIN_OLEFACTORY и END_OLEFACTORY. Внешнее имя — это идентификатор элемента управления OLE, который предоставляется другим приложениям. Контейнеры используют это имя для запроса объекта этого класса элемента управления.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="begin_olefactory"></a><a name="begin_olefactory"></a> BEGIN_OLEFACTORY

Начинает объявление фабрики класса в файле заголовка класса элемента управления.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Указывает имя класса элемента управления, для которого задана фабрика класса.

### <a name="remarks"></a>Примечания

Объявления функций лицензирования фабрики класса должны начинаться сразу же после BEGIN_OLEFACTORY.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="end_olefactory"></a><a name="end_olefactory"></a> END_OLEFACTORY

Завершает объявление фабрики класса элемента управления.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, для которого задана фабрика классов.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxverifylicfile"></a><a name="afxverifylicfile"></a> афксверифиликфиле

Вызовите эту функцию, чтобы убедиться, что файл лицензии с именем `pszLicFileName` является допустимым для элемента управления OLE.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Обработчик экземпляра библиотеки DLL, связанной с лицензированным элементом управления.

*псзликфиленаме*<br/>
Указывает на строку символов, завершающуюся нулем, содержащую имя файла лицензии.

*псзликфилеконтентс*<br/>
Указывает на последовательность байтов, которая должна соответствовать последовательности, найденной в начале файла лицензии.

*кч*<br/>
Число символов в *псзликфилеконтентс*.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если файл лицензии существует и начинается с последовательности символов в *псзликфилеконтентс*; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если *Кч* имеет значение-1, эта функция использует:

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
