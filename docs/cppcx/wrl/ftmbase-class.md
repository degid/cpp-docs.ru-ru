---
title: FtmBase - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: b28b7ee0038e4f828f43fcc3f0d49a2d9e092315
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844045"
---
# <a name="ftmbase-class"></a>FtmBase - класс

Представляет свободнопоточный объект маршаллера.

## <a name="syntax"></a>Синтаксис

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [класс RuntimeClass](runtimeclass-class.md).

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

| name                         | Описание                                        |
| ---------------------------- | -------------------------------------------------- |
| [Метод FtmBase:: метод FtmBase](#ftmbase) | Инициализирует новый экземпляр класса `FtmBase`. |

### <a name="public-methods"></a>Открытые методы

| name                                                               | Описание                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Метод FtmBase:: CreateGlobalInterfaceTable](#createglobalinterfacetable) | Создает таблицу глобальных интерфейсов (GIT).                                                                                                                              |
| [Метод FtmBase::D Исконнектобжект](#disconnectobject)                     | Принудительно выпускают все внешние соединения с объектом. Сервер объекта вызывает реализацию этого метода объекта перед завершением работы.                |
| [Метод FtmBase:: GetMarshalSizeMax](#getmarshalsizemax)                   | Возвращает верхнюю границу числа байтов, необходимых для маршалирования указанного указателя интерфейса для указанного объекта.                                                |
| [Метод FtmBase:: Жетунмаршалкласс](#getunmarshalclass)                   | Возвращает идентификатор CLSID, используемый COM для размещения библиотеки DLL, содержащей код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL, чтобы создать неинициализированный экземпляр прокси-сервера. |
| [Метод FtmBase:: MarshalInterface](#marshalinterface)                     | Выполняет запись в поток данных, необходимых для инициализации прокси-объекта в некоторых клиентских процессах.                                                                          |
| [Метод FtmBase:: ReleaseMarshalData](#releasemarshaldata)                 | Уничтожает упакованный пакет данных.                                                                                                                                    |
| [Метод FtmBase:: Унмаршалинтерфаце](#unmarshalinterface)                 | Инициализирует вновь созданный прокси-сервер и возвращает указатель интерфейса на этот прокси-сервер.                                                                                    |

### <a name="public-data-members"></a>Открытые члены данных

| Имя                                | Описание                                       |
| ----------------------------------- | ------------------------------------------------- |
| [Метод FtmBase:: marshaller_](#marshaller) | Содержит ссылку на свободный потоковый маршалером. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FtmBase`

## <a name="requirements"></a>Требования

**Заголовок:** FTM.h

**Пространство имен:** Microsoft::WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a> Метод FtmBase:: CreateGlobalInterfaceTable

Создает таблицу глобальных интерфейсов (GIT).

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Параметры

*git*<br/>
По завершении этой операции указатель на глобальную таблицу интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. на веб-сайте [`IGlobalInterfaceTable`](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable).

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a> Метод FtmBase::D Исконнектобжект

Принудительно выпускают все внешние соединения с объектом. Сервер объекта вызывает реализацию этого метода объекта перед завершением работы.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Параметры

*двресервед*<br/>
Зарезервировано для будущего использования; должно иметь значение нуль.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a> Метод FtmBase:: метод FtmBase

Инициализирует новый экземпляр класса `FtmBase`.

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a> Метод FtmBase:: GetMarshalSizeMax

Возвращает верхнюю границу числа байтов, необходимых для маршалирования указанного указателя интерфейса для указанного объекта.

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса, который необходимо маршалировать.

*PV*<br/>
Указатель интерфейса для маршалирования; может иметь значение NULL.

*двдестконтекст*<br/>
Контекст назначения, в котором заданный интерфейс должен быть размаршалирован.

Укажите одно или несколько значений перечисления МШКТКС.

В настоящее время распаковка может выполняться либо в другом апартаменте текущего процесса (MSHCTX_INPROC), либо в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*пвдестконтекст*<br/>
Зарезервировано для будущего использования; должен иметь значение NULL.

*мшлфлагс*<br/>
Флаг, указывающий, следует ли передавать данные для упаковки обратно в клиентский процесс — типичный вариант — или записывается в глобальную таблицу, где они могут быть извлечены несколькими клиентами. Укажите одно или несколько значений перечисления МШЛФЛАГС.

*псизе*<br/>
По завершении этой операции указатель на верхнюю границу объема данных, записываемых в поток маршалирования.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_FAIL или E_NOINTERFACE.

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a> Метод FtmBase:: Жетунмаршалкласс

Возвращает идентификатор CLSID, используемый COM для размещения библиотеки DLL, содержащей код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL, чтобы создать неинициализированный экземпляр прокси-сервера.

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса, который необходимо маршалировать.

*PV*<br/>
Указатель на интерфейс для маршалирования; может иметь значение NULL, если вызывающий объект не имеет указателя на нужный интерфейс.

*двдестконтекст*<br/>
Контекст назначения, в котором заданный интерфейс должен быть размаршалирован.

Укажите одно или несколько значений перечисления МШКТКС.

Распаковка может выполняться либо в другом апартаменте текущего процесса (MSHCTX_INPROC), либо в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*пвдестконтекст*<br/>
Зарезервировано для будущего использования; должен иметь значение NULL.

*мшлфлагс*<br/>
По завершении этой операции указатель на идентификатор CLSID, который будет использоваться для создания прокси-сервера в процессе клиента.

*pCid*

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае S_FALSE.

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a> Метод FtmBase:: MarshalInterface

Выполняет запись в поток данных, необходимых для инициализации прокси-объекта в некоторых клиентских процессах.

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>Параметры

*пстм*<br/>
Указатель на поток, используемый во время маршалирования.

*riid*<br/>
Ссылка на идентификатор интерфейса, который необходимо маршалировать. Он должен быть производным от интерфейса `IUnknown` .

*PV*<br/>
Указатель на указатель интерфейса для маршалирования; может иметь значение NULL, если вызывающий объект не имеет указателя на нужный интерфейс.

*двдестконтекст*<br/>
Контекст назначения, в котором заданный интерфейс должен быть размаршалирован.

Укажите одно или несколько значений перечисления МШКТКС.

Распаковка может выполняться в другом апартаменте текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*пвдестконтекст*<br/>
Зарезервировано для будущего использования; должно иметь значение нуль.

*мшлфлагс*<br/>
Указывает, должны ли данные, подлежащий упаковке, передаваться обратно в клиентский процесс — типичный вариант — или записывается в глобальную таблицу, где они могут быть извлечены несколькими клиентами.

### <a name="return-value"></a>Возвращаемое значение

S_OK успешно маршалирован указатель на интерфейс.

E_NOINTERFACE указанный интерфейс не поддерживается.

STG_E_MEDIUMFULL поток заполнен.

E_FAIL выполнить операцию не удалось.

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a> Метод FtmBase:: marshaller_

Содержит ссылку на свободный потоковый маршалером.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a> Метод FtmBase:: ReleaseMarshalData

Уничтожает упакованный пакет данных.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Параметры

*пстм*<br/>
Указатель на поток, содержащий пакет данных для уничтожения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a> Метод FtmBase:: Унмаршалинтерфаце

Инициализирует вновь созданный прокси-сервер и возвращает указатель интерфейса на этот прокси-сервер.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Параметры

*пстм*<br/>
Указатель на поток, из которого следует распаковать указатель интерфейса.

*riid*<br/>
Ссылка на идентификатор интерфейса, который необходимо распаковать.

*ппв*<br/>
По завершении этой операции адрес переменной указателя, получающей указатель интерфейса, запрошенный в *riid*. Если эта операция прошла успешно, **ППВ* содержит запрошенный указатель интерфейса для расупакованного интерфейса.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае E_NOINTERFACE или E_FAIL.
