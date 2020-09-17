---
title: Класс Кпропексчанже
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 09fb1bd34f3b5eadb78d8f9081450c042fe22f9e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226871"
---
# <a name="cpropexchange-class"></a>Класс Кпропексчанже

Поддерживает реализацию сохранения элементов управления OLE.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кпропексчанже:: Ексчанжеблобпроп](#exchangeblobprop)|Обменивается данными со свойством большого двоичного объекта (BLOB).|
|[Кпропексчанже:: Ексчанжефонтпроп](#exchangefontprop)|Меняет местами свойство Font.|
|[Кпропексчанже:: Ексчанжеперсистентпроп](#exchangepersistentprop)|Обменивает свойство между элементом управления и файлом.|
|[Кпропексчанже:: Ексчанжепроп](#exchangeprop)|Обменивается свойствами любого встроенного типа.|
|[Кпропексчанже:: Ексчанжеверсион](#exchangeversion)|Меняет местами номер версии элемента управления OLE.|
|[Кпропексчанже::/версия](#getversion)|Возвращает номер версии элемента управления OLE.|
|[Кпропексчанже:: в асинхронном режиме](#isasynchronous)|Определяет, выполняются ли обмены свойствами асинхронно.|
|[Кпропексчанже:: Load](#isloading)|Указывает, загружаются ли свойства в элемент управления или сохраняются из него.|

## <a name="remarks"></a>Примечания

`CPropExchange`не имеет базового класса.

Устанавливает контекст и направление обмена свойствами.

Сохраняемость — это обмен сведениями о состоянии элемента управления, обычно представляемых его свойствами, между самим элементом управления и средним.

Платформа конструирует объект, производный от `CPropExchange` , когда он уведомляется о том, что свойства элемента управления OLE должны быть загружены из постоянного хранилища или сохранены в него.

Платформа передает указатель на этот `CPropExchange` объект в функцию элемента управления `DoPropExchange` . Если для создания начальных файлов для элемента управления использовался мастер, `DoPropExchange` вызывается функция элемента управления `COleControl::DoPropExchange` . Версия базового класса обменивается свойствами запасов элемента управления. Вы изменяете версию производного класса на свойства Exchange, добавленные в элемент управления.

`CPropExchange`может использоваться для сериализации свойств элемента управления или инициализации свойств элемента управления при загрузке или создании элемента управления. `ExchangeProp`Функции- `ExchangeFontProp` члены и могут `CPropExchange` сохранять свойства и загружать их с разных носителей.

Дополнительные сведения об использовании см `CPropExchange` . в статье [элементы управления ActiveX в MFC: страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPropExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="cpropexchangeexchangeblobprop"></a><a name="exchangeblobprop"></a>Кпропексчанже:: Ексчанжеблобпроп

Сериализует свойство, в котором хранятся данные большого двоичного объекта (BLOB).

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>Параметры

*псзпропнаме*<br/>
Имя свойства, для которого выполняется обмен.

*фблоб*<br/>
Указатель на переменную, указывающую на место хранения свойства (переменная обычно является членом класса).

*хблобдефаулт*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Exchange завершился успешно; 0 в случае неудачи.

### <a name="remarks"></a>Примечания

Значение свойства считывается или записывается в, при необходимости, на переменную, на которую ссылается *фблоб*. Если указан параметр *хблобдефаулт* , он будет использоваться как значение свойства по умолчанию. Это значение используется, если по какой-либо причине происходит сбой сериализации элемента управления.

Функции `CArchivePropExchange::ExchangeBlobProp` , `CResetPropExchange::ExchangeBlobProp` и `CPropsetPropExchange::ExchangeBlobProp` переопределяют эту чисто виртуальную функцию.

## <a name="cpropexchangeexchangefontprop"></a><a name="exchangefontprop"></a>Кпропексчанже:: Ексчанжефонтпроп

Меняет местами свойство Font между носителем хранилища и элементом управления.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>Параметры

*псзпропнаме*<br/>
Имя свойства, для которого выполняется обмен.

*шрифтов*<br/>
Ссылка на объект [кфонсолдер](../../mfc/reference/cfontholder-class.md) , содержащий свойство Font.

*пфонтдеск*<br/>
Указатель на структуру [фонтдеск](/windows/win32/api/olectl/ns-olectl-fontdesc) , содержащую значения для инициализации состояния по умолчанию для свойства Font, если *пфонтдиспамбиент* имеет значение null.

*пфонтдиспамбиент*<br/>
Указатель на `IFontDisp` интерфейс шрифта, используемый для инициализации состояния по умолчанию для свойства Font.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Exchange завершился успешно; 0 в случае неудачи.

### <a name="remarks"></a>Примечания

Если свойство Font загружается с носителя на элемент управления, характеристики шрифта извлекаются с носителя, а `CFontHolder` объект, на который ссылается *Font* , инициализируется с ними. Если свойство Font хранится, характеристики в объекте Font записываются на носитель.

Функции `CArchivePropExchange::ExchangeFontProp` , `CResetPropExchange::ExchangeFontProp` и `CPropsetPropExchange::ExchangeFontProp` переопределяют эту чисто виртуальную функцию.

## <a name="cpropexchangeexchangepersistentprop"></a><a name="exchangepersistentprop"></a>Кпропексчанже:: Ексчанжеперсистентпроп

Обменивает свойство между элементом управления и файлом.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>Параметры

*псзпропнаме*<br/>
Имя свойства, для которого выполняется обмен.

*ппунк*<br/>
Указатель на переменную, содержащую указатель на `IUnknown` интерфейс свойства (эта переменная обычно является членом класса).

*IID*<br/>
Идентификатор интерфейса для свойства, которое будет использоваться элементом управления.

*пункдефаулт*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Exchange завершился успешно; 0 в случае неудачи.

### <a name="remarks"></a>Примечания

Если свойство загружается из файла в элемент управления, свойство создается и инициализируется из файла. Если свойство сохраняется, его значение записывается в файл.

Функции `CArchivePropExchange::ExchangePersistentProp` , `CResetPropExchange::ExchangePersistentProp` и `CPropsetPropExchange::ExchangePersistentProp` переопределяют эту чисто виртуальную функцию.

## <a name="cpropexchangeexchangeprop"></a><a name="exchangeprop"></a>Кпропексчанже:: Ексчанжепроп

Меняет местами свойство между носителем хранилища и элементом управления.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>Параметры

*псзпропнаме*<br/>
Имя свойства, для которого выполняется обмен.

*втпроп*<br/>
Символ, указывающий тип свойства, для которого выполняется обмен. Возможны следующие значения:

|Символ|Тип свойства|
|------------|-------------------|
|VT_I2|**`short`**|
|VT_I4|**`long`**|
|VT_BOOL.|**ЛОГИЧЕСКОМ**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**`float`**|
|VT_R8|**`double`**|

*пвпроп*<br/>
Указатель на значение свойства.

*пвдефаулт*<br/>
Указатель на значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если Exchange завершился успешно; 0 в случае неудачи.

### <a name="remarks"></a>Примечания

Если свойство загружается с носителя на элемент управления, значение свойства извлекается из среднего значения и сохраняется в объекте, на который указывает *пвпроп*. Если свойство хранится на носителе, значение объекта, на которое указывает *пвпроп* , записывается на носитель.

Функции `CArchivePropExchange::ExchangeProp` , `CResetPropExchange::ExchangeProp` и `CPropsetPropExchange::ExchangeProp` переопределяют эту чисто виртуальную функцию.

## <a name="cpropexchangeexchangeversion"></a><a name="exchangeversion"></a>Кпропексчанже:: Ексчанжеверсион

Вызывается платформой для управления сохраняемостью номера версии.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Параметры

*двверсионлоадед*<br/>
Ссылка на переменную, в которой будут храниться номера версий постоянных данных, подходящих для загрузки.

*двверсиондефаулт*<br/>
Номер текущей версии элемента управления.

*бконверт*<br/>
Указывает, следует ли преобразовывать постоянные данные в текущую версию или же они должны оставаться в той же версии, которая была загружена.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция прошла удачно; 0 в противном случае.

## <a name="cpropexchangegetversion"></a><a name="getversion"></a>Кпропексчанже::/версия

Вызовите эту функцию, чтобы получить номер версии элемента управления.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Возвращаемое значение

Номер версии элемента управления.

## <a name="cpropexchangeisasynchronous"></a><a name="isasynchronous"></a>Кпропексчанже:: в асинхронном режиме

Определяет, выполняются ли обмены свойствами асинхронно.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если свойства обмениваются асинхронно, в противном случае — значение FALSE.

## <a name="cpropexchangeisloading"></a><a name="isloading"></a>Кпропексчанже:: Load

Вызовите эту функцию, чтобы определить, загружаются ли свойства в элемент управления или сохраняются из него.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если свойства загружаются; в противном случае — 0.

## <a name="see-also"></a>См. также статью

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
