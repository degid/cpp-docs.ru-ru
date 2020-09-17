---
title: Макросы и функции для управления библиотеками DLL
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: e4170ba95775fd3380837673a76a8adafc8ad011
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837187"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Макросы и функции для управления библиотеками DLL

|Имя|Описание|
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Экспортирует классы.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Защита экспортированной функции в библиотеке DLL.|
|[AfxOleInitModule](#afxoleinitmodule)|Обеспечивает поддержку OLE из обычной библиотеки DLL MFC, которая динамически связана с MFC.|
|[AfxNetInitModule](#afxnetinitmodule)|Предоставляет поддержку сокетов MFC из обычной библиотеки DLL MFC, которая динамически связана с MFC.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Возвращает текущее состояние флага состояния каждого модуля.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Задает состояние модуля перед инициализацией и (или) восстановление предыдущего состояния модуля после очистки.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|Инициализирует библиотеку DLL.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|Установите флаг состояния каждого модуля, который влияет на поведение WinSxS в MFC.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|Позволяет MFC очищать библиотеку DLL расширения MFC, когда каждый процесс отключается от библиотеки DLL.|

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a> AFX_EXT_CLASS

[Библиотеки DLL расширения MFC](../../build/extension-dlls.md) используют макрос AFX_EXT_CLASS для экспорта классов; исполняемые файлы, которые связываются с библиотекой DLL расширения MFC, используют макрос для импорта классов.

### <a name="remarks"></a>Примечания

С помощью макроса AFX_EXT_CLASS те же файлы заголовков, которые используются для сборки библиотеки DLL расширения MFC, можно использовать с исполняемыми файлами, которые связываются с библиотекой DLL.

В файле заголовка для библиотеки DLL добавьте ключевое слово AFX_EXT_CLASS в объявление класса следующим образом:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Дополнительные сведения см. в разделе [Экспорт и импорт с помощью AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md).

### <a name="requirements"></a>Требования

**Заголовок:** AFXV_DLL.h

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a> AFX_MANAGE_STATE

Вызовите этот макрос, чтобы защитить экспортированную функцию в библиотеке DLL.

### <a name="syntax"></a>Синтаксис

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Параметры

*пмодулестате*<br/>
Указатель на `AFX_MODULE_STATE` структуру.

### <a name="remarks"></a>Примечания

При вызове этого макроса *пмодулестате* является эффективным состоянием модуля для оставшейся части немедленно содержащей его области. При выходе из этой области предыдущее действующее состояние модуля будет автоматически восстановлено.
`AFX_MODULE_STATE`Структура содержит глобальные данные для модуля, то есть часть состояния модуля, которая помещается или извлекается.

По умолчанию MFC использует для загрузки шаблона ресурса обработчик ресурсов основного приложения. Если в библиотеке DLL есть экспортированная функция, например, которая запускает диалоговое окно в библиотеке DLL, этот шаблон фактически хранится в модуле DLL. Необходимо переключить состояние модуля, чтобы использовать правильный маркер. Это можно сделать, добавив следующий код в начало функции:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Это меняет местами текущее состояние модуля на состояние, возвращенное из [афксжетстатикмодулестате](#afxgetstaticmodulestate) , до конца текущей области.

Дополнительные сведения о состояниях модулей и MFC см. в разделе "Управление данными о состоянии модулей MFC" статьи [Создание новых документов, окон и представлений](../creating-new-documents-windows-and-views.md) и [техническое примечание 58](../tn058-mfc-module-state-implementation.md).

> [!NOTE]
> Когда MFC создает контекст активации для сборки, он использует [афксвининит](application-information-and-management.md#afxwininit) для создания контекста и `AFX_MANAGE_STATE` его активации и деактивации. Обратите внимание, что `AFX_MANAGE_STATE` включено для статических библиотек MFC, а также библиотек DLL MFC, чтобы код MFC можно было выполнять в правильном контексте активации, выбранном в библиотеке DLL пользователя. Дополнительные сведения см. [в разделе Поддержка контекстов активации в состоянии модуля MFC](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxstat_.h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> афксолеинитмодуле

Для поддержки OLE из обычной библиотеки DLL MFC, которая динамически связана с MFC, вызовите эту функцию в функции обычной библиотеки DLL MFC, `CWinApp::InitInstance` чтобы инициализировать БИБЛИОТЕКУ MFC OLE DLL.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Примечания

MFC OLE DLL — это библиотека DLL расширения MFC. чтобы библиотека DLL расширения MFC была подключена к `CDynLinkLibrary` цепочке, она должна создать `CDynLinkLibrary` объект в контексте каждого модуля, который будет его использовать. `AfxOleInitModule` создает `CDynLinkLibrary` объект в контексте обычной библиотеки DLL MFC, чтобы он был подключен в `CDynLinkLibrary` цепочке объектов обычной библиотеки DLL MFC.

Если вы создаете элемент управления OLE и используете `COleControlModule` , не следует вызывать, `AfxOleInitModule` поскольку функция- `InitInstance` член для `COleControlModule` вызовов `AfxOleInitModule` .

### <a name="requirements"></a>Требования

**Заголовок**: \<afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a> афкснетинитмодуле

Для поддержки сокетов MFC из обычной библиотеки DLL MFC, которая динамически связана с MFC, добавьте вызов этой функции в функции обычной библиотеки DLL MFC `CWinApp::InitInstance` для инициализации DLL-библиотеки MFC.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Примечания

Библиотека DLL MFC Sockets является библиотекой DLL расширения MFC. чтобы библиотека DLL расширения MFC была подключена к `CDynLinkLibrary` цепочке, она должна создать `CDynLinkLibrary` объект в контексте каждого модуля, который будет его использовать. `AfxNetInitModule` создает `CDynLinkLibrary` объект в контексте обычной библиотеки DLL MFC, чтобы он был подключен в `CDynLinkLibrary` цепочке объектов обычной библиотеки DLL MFC.

### <a name="requirements"></a>Требования

**Заголовок:**\<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a> афксжетамбиентакткткс

Эта функция используется для получения текущего состояния флага состояния каждого модуля, что влияет на поведение WinSxS в MFC.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение флага состояния модуля.

### <a name="remarks"></a>Примечания

Если установлен флаг (по умолчанию) и поток входит в модуль MFC (см. [AFX_MANAGE_STATE](#afx_manage_state)), то активируется контекст модуля.

Если флаг не установлен, то контекст модуля не активируется при входе.

Контекст модуля определяется из его манифеста, который обычно внедряется в ресурсы модуля.

### <a name="requirements"></a>Требования

**Заголовок:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a> афксжетстатикмодулестате

Вызывайте эту функцию, чтобы задать состояние модуля перед инициализацией и (или) восстановить предыдущее состояние модуля после очистки.

### <a name="syntax"></a>Синтаксис

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `AFX_MODULE_STATE` структуру.

### <a name="remarks"></a>Примечания

`AFX_MODULE_STATE`Структура содержит глобальные данные для модуля, то есть часть состояния модуля, которая помещается или извлекается.

По умолчанию MFC использует для загрузки шаблона ресурса обработчик ресурсов основного приложения. Если в библиотеке DLL есть экспортированная функция, например, которая запускает диалоговое окно в библиотеке DLL, этот шаблон фактически хранится в модуле DLL. Необходимо переключить состояние модуля, чтобы использовать правильный маркер. Это можно сделать, добавив следующий код в начало функции:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Это меняет местами текущее состояние модуля на состояние, возвращенное `AfxGetStaticModuleState` до конца текущей области.

Дополнительные сведения о состояниях модулей и MFC см. в разделе "Управление данными о состоянии модулей MFC" статьи [Создание новых документов, окон и представлений](../creating-new-documents-windows-and-views.md) и [техническое примечание 58](../tn058-mfc-module-state-implementation.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

Вызовите эту функцию в библиотеке DLL расширения MFC `DllMain` для инициализации библиотеки DLL.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Параметры

*state*<br/>
Ссылка на структуру [структуры AFX_EXTENSION_MODULE](afx-extension-module-structure.md) , которая будет содержать состояние модуля DLL расширения MFC после инициализации. Состояние включает копию объектов класса среды выполнения, которые были инициализированы библиотекой DLL расширения MFC как часть обычной конструкции статического объекта, выполняемой перед `DllMain` входом.

*хмодуле*<br/>
Маркер модуля DLL расширения MFC.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если библиотека DLL расширения MFC успешно инициализирована; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Пример:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule` создает копию ХМОДУЛЕ библиотеки DLL и записывает классы среды выполнения (структуры) библиотеки DLL, а `CRuntimeClass` также фабрики объектов ( `COleObjectFactory` объекты) для дальнейшего использования при `CDynLinkLibrary` создании объекта.
Библиотеки DLL расширения MFC должны выполнять два действия в своей `DllMain` функции:

- Вызовите [афксинитекстенсионмодуле](#afxinitextensionmodule) и проверьте возвращаемое значение.

- Создайте `CDynLinkLibrary` объект, если библиотека DLL будет экспортировать объекты [структуры крунтимекласс](cruntimeclass-structure.md) или имеет собственные пользовательские ресурсы.

Можно вызвать `AfxTermExtensionModule` для очистки библиотеки DLL расширения MFC, когда каждый процесс отсоединяется от библиотеки DLL расширения MFC (которая происходит при завершении процесса или при выгрузке библиотеки DLL в результате `AfxFreeLibrary` вызова).

### <a name="requirements"></a>Требования

**Заголовок:** AFXDLL_.h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a> афкссетамбиентакткткс

Эта функция используется для установки флага состояния каждого модуля, который влияет на поведение WinSxS в MFC.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Параметры

*Управляемое bSet*<br/>
Новое значение флага состояния модуля.

### <a name="remarks"></a>Примечания

Если установлен флаг (по умолчанию) и поток входит в модуль MFC (см. [AFX_MANAGE_STATE](#afx_manage_state)), то активируется контекст модуля.
Если флаг не установлен, то контекст модуля не активируется при входе.
Контекст модуля определяется из его манифеста, который обычно внедряется в ресурсы модуля.

### <a name="example"></a>Пример

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a> афкстермекстенсионмодуле

Вызывайте эту функцию, чтобы разрешить MFC очищать библиотеку DLL расширения MFC, когда каждый процесс отключается от библиотеки DLL (что происходит при завершении процесса или при выгрузке библиотеки DLL в результате `AfxFreeLibrary` вызова).

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>Параметры

*state*<br/>
Ссылка на структуру [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) , которая содержит состояние модуля DLL расширения MFC.

*Шара*<br/>
Если значение — TRUE, очистите все модули DLL расширения MFC. В противном случае очистите только текущий модуль DLL.

### <a name="remarks"></a>Примечания

`AfxTermExtensionModule` удалит все локальные хранилища, подключенные к модулю, и удалит все записи из кэша схемы сообщений. Пример:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

Если приложение загружает и освобождает библиотеки DLL расширения MFC динамически, обязательно вызовите `AfxTermExtensionModule` . Так как большинство библиотек DLL расширения MFC не загружаются динамически (обычно они связаны с помощью библиотек импорта), вызов метода `AfxTermExtensionModule` обычно не требуется.

Библиотеки DLL расширения MFC должны вызывать [афксинитекстенсионмодуле](#afxinitextensionmodule) в `DllMain` . Если библиотека DLL будет экспортировать объекты [крунтимекласс](cruntimeclass-structure.md) или имеет собственные пользовательские ресурсы, необходимо также создать `CDynLinkLibrary` объект в `DllMain` .

### <a name="requirements"></a>Требования

**Заголовок:** AFXDLL_.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[Управление данными состояния модулей MFC](../managing-the-state-data-of-mfc-modules.md)<br/>
