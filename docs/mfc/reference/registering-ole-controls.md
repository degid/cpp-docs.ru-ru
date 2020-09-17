---
title: Регистрация элементов управления OLE
ms.date: 11/04/2016
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 5468f3d4b730cc0b81a6ab814d495b061d292f20
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843577"
---
# <a name="registering-ole-controls"></a>Регистрация элементов управления OLE

Элементы управления OLE, как и другие объекты OLE-сервера, могут обращаться к другим приложениям, поддерживающим технологию OLE. Это достигается путем регистрации библиотеки типов и класса элемента управления.

Следующие функции позволяют добавлять и удалять класс элемента управления, страницы свойств и библиотеку типов в базе данных регистрации Windows:

### <a name="registering-ole-controls"></a>Регистрация элементов управления OLE

|Имя|Описание|
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Добавляет класс элемента управления в базу данных регистрации.|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Добавляет страницу свойств элемента управления в базу данных регистрации.|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Добавляет библиотеку типов элемента управления в базу данных регистрации.|
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Удаляет из базы данных регистрации класс элемента управления или класс страницы свойств.|
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Удаляет библиотеку типов элемента управления из базы данных регистрации.|

`AfxOleRegisterTypeLib` обычно вызывается в реализации библиотеки DLL элемента управления `DllRegisterServer` . Аналогичным образом `AfxOleUnregisterTypeLib` метод вызывается методом `DllUnregisterServer` . `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass` и `AfxOleUnregisterClass` обычно вызываются `UpdateRegistry` функцией-членом фабрики класса элемента управления или страницы свойств.

## <a name="afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a> афксолерегистерконтролкласс

Регистрирует класс элемента управления в базе данных регистрации Windows.

```
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,
    REFCLSID clsid,
    LPCTSTR pszProgID,
    UINT idTypeName,
    UINT idBitmap,
    int nRegFlags,
    DWORD dwMiscStatus,
    REFGUID tlid,
    WORD wVerMajor,
    WORD wVerMinor);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Обработчик экземпляра модуля, связанного с классом элемента управления.

*этому*<br/>
Уникальный идентификатор класса элемента управления.

*псзпрогид*<br/>
Уникальный идентификатор программы элемента управления.

*идтипенаме*<br/>
Идентификатор ресурса строки, содержащей имя типа, читаемое пользователем для элемента управления.

*идбитмап*<br/>
Идентификатор ресурса точечного рисунка, используемого для представления элемента управления OLE в панели инструментов или палитре.

*нрегфлагс*<br/>
Содержит один или несколько следующих флагов:

- `afxRegInsertable` Разрешает отображение элемента управления в диалоговом окне «Вставка объекта» для объектов OLE.

- `afxRegApartmentThreading` Задает для потоковой модели в реестре значение ThreadingModel = апартамент.

- `afxRegFreeThreading` Задает для потоковой модели в реестре значение ThreadingModel = Free.

   Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` задать ThreadingModel = оба. Дополнительные сведения о регистрации модели потоков см. в разделе [InprocServer32](/windows/win32/com/inprocserver32) в Windows SDK.

> [!NOTE]
> В версиях MFC до MFC 4,2 **`int`** параметр *нрегфлагс* был параметром bool, *бинсертабле*, который позволял или не допускал вставку элемента управления из диалогового окна «Вставка объекта».

*двмискстатус*<br/>
Содержит один или несколько следующих флагов состояния (описание флагов см. в разделе Перечисление ОЛЕМИСК в Windows SDK):

- OLEMISC_RECOMPOSEONRESIZE

- OLEMISC_ONLYICONIC

- OLEMISC_INSERTNOTREPLACE

- OLEMISC_STATIC

- OLEMISC_CANTLINKINSIDE

- OLEMISC_CANLINKBYOLE1

- OLEMISC_ISLINKOBJECT

- OLEMISC_INSIDEOUT

- OLEMISC_ACTIVATEWHENVISIBLE

- OLEMISC_RENDERINGISDEVICEINDEPENDENT

- OLEMISC_INVISIBLEATRUNTIME

- OLEMISC_ALWAYSRUN

- OLEMISC_ACTSLIKEBUTTON

- OLEMISC_ACTSLIKELABEL

- OLEMISC_NOUIACTIVATE

- OLEMISC_ALIGNABLE

- OLEMISC_IMEMODE

- OLEMISC_SIMPLEFRAME

- OLEMISC_SETCLIENTSITEFIRST

*тлид*<br/>
Уникальный идентификатор класса элемента управления.

*ввермажор*<br/>
Основной номер версии класса элемента управления.

*вверминор*<br/>
Дополнительный номер версии класса элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если класс элемента управления был зарегистрирован; в противном случае — 0.

### <a name="remarks"></a>Примечания

Это позволяет использовать элемент управления в контейнерах, поддерживающих технологию OLE-управления. `AfxOleRegisterControlClass` обновляет реестр, используя имя и расположение элемента управления в системе, а также задает модель потоков, которую элемент управления поддерживает в реестре. Дополнительные сведения см. в [техническом примечании 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «потоковая модель потоков в элементах управления OLE» и [о процессах и потоках](/windows/win32/ProcThread/about-processes-and-threads) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

В приведенном выше примере показано, как `AfxOleRegisterControlClass` вызывается с флагом для inserted и флагом для модели подразделения ORed вместе для создания шестого параметра:

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

Элемент управления будет отображаться в диалоговом окне Вставка объекта для включенных контейнеров и будет поддерживать модель подразделений. Элементы управления, учитывающие модель подразделений, должны обеспечивать защиту данных статического класса с помощью блокировок, поэтому, когда элемент управления в одном апартаменте получает доступ к статическим данным, он не отключается планировщиком до его завершения, а другой экземпляр того же класса начинает использовать одни и те же статические данные. Любой доступ к статическим данным будет окружен кодом критической секции.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a> афксолерегистерпропертипажекласс

Регистрирует класс страницы свойств в базе данных регистрации Windows.

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Обработчик экземпляра модуля, связанного с классом страницы свойств.

*этому*<br/>
Уникальный идентификатор класса страницы свойств.

*идтипенаме*<br/>
Идентификатор ресурса строки, которая содержит понятное пользователю имя для страницы свойств.

*нрегфлагс*<br/>
Может содержать флаг:

- `afxRegApartmentThreading` Задает для потоковой модели в реестре значение ThreadingModel = апартамент.

> [!NOTE]
> В версиях MFC, предшествовавших версии MFC 4,2, **`int`** параметр *нрегфлагс* недоступен. Обратите внимание, что `afxRegInsertable` флаг не является допустимым параметром для страниц свойств и вызовет утверждение в MFC, если оно задано

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если класс элемента управления был зарегистрирован; в противном случае — 0.

### <a name="remarks"></a>Примечания

Это позволяет использовать страницу свойств в контейнерах, поддерживающих технологию OLE-управления. `AfxOleRegisterPropertyPageClass` обновляет реестр, используя имя страницы свойств и ее расположение в системе, а также задает модель потоков, которую элемент управления поддерживает в реестре. Дополнительные сведения см. в [техническом примечании 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «потоковая модель потоков в элементах управления OLE» и [о процессах и потоках](/windows/win32/ProcThread/about-processes-and-threads) в Windows SDK.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a> афксолерегистертипелиб

Регистрирует библиотеку типов в базе данных регистрации Windows и позволяет использовать библиотеку типов в других контейнерах, поддерживающих управление OLE.

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Обработчик экземпляра приложения, связанного с библиотекой типов.

*тлид*<br/>
Уникальный идентификатор библиотеки типов.

*pszFileName*<br/>
Указывает на необязательное имя файла локализованной библиотеки типов (. TLB) для элемента управления.

*псзелпдир*<br/>
Имя каталога, в котором можно найти файл справки для библиотеки типов. Если значение равно NULL, файл справки считается в том же каталоге, что и сама библиотека типов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если библиотека типов была зарегистрирована; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция обновляет реестр, используя имя библиотеки типов и ее расположение в системе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** афксдисп.h

## <a name="afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a> афксолеунрегистеркласс

Удаляет запись класса элемента управления или страницы свойств из базы данных регистрации Windows.

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>Параметры

*Этому*<br/>
Уникальный идентификатор класса элемента управления или страницы свойств.

*псзпрогид*<br/>
Уникальный идентификатор программы для элемента управления или страницы свойств.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если регистрация класса элемента управления или страницы свойств была успешно отменена; в противном случае — 0.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a> афксолеунрегистертипелиб

Вызовите эту функцию, чтобы удалить запись типа "Библиотека типов" из базы данных регистрации Windows.

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>Параметры

*тлид*<br/>
Уникальный идентификатор библиотеки типов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если регистрация библиотеки типов была успешно отменена; в противном случае — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** афксдисп.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
