---
title: Класс CFixedStringT
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: fe096185f6f0b71ad45757cd0b75ab13c41e5f5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317830"
---
# <a name="cfixedstringt-class"></a>Класс CFixedStringT

Этот класс представляет собой объект строки с фиксированным буфером символов.

## <a name="syntax"></a>Синтаксис

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Параметры

*StringType*<br/>
Используется в качестве базового класса для объекта `CStringT`фиксированной строки и может быть любым типом. Некоторые примеры включают, `CString` `CStringA`, и `CStringW`.

*t_nChars*<br/>
Количество символов, хранящихся в буфере.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFixedStringt::CfixedStringt](#cfixedstringt)|Конструктор для объекта строки.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CFixedStringT::оператор](#operator_eq)|Присваивает объекту `CFixedStringT` новое значение.|

## <a name="remarks"></a>Примечания

Этот класс является примером пользовательского `CStringT`класса строки на основе . Хотя эти два класса схожи отличаются по своему осуществлению. Основные различия `CFixedStringT` `CStringT` между и являются:

- Первоначальный буфер символов выделяется как часть объекта и имеет размер *t_nChars.* Это позволяет `CFixedString` объекту занимать смежный кусок памяти для целей производительности. Однако, если содержимое `CFixedStringT` объекта вырастает за пределы *t_nChars,* буфер распределяется динамически.

- Буфер символов `CFixedStringT` для объекта всегда одинаковой длины *(t_nChars).* Для `CStringT` объектов нет ограничений по размеру буфера.

- Для менеджера `CFixedStringT` памяти настраивается таким образом, что не допускается совместное использование объекта [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) между двумя или более `CFixedStringT` объектами. `CStringT`объекты не имеют этого ограничения.

Для получения дополнительной информации `CFixedStringT` о настройке и управлении памятью для объектов строки в целом, см. [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>Требования

**Заголовок:** cstringt.h

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a>CFixedStringt::CfixedStringt

Формирует объект `CFixedStringT`.

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>Параметры

*pszSrc*<br/>
Нулевая строка, которая будет `CFixedStringT` скопирована в этот объект.

*strSrc*<br/>
Существующий `CFixedStringT` объект, который должен `CFixedStringT` быть скопирован в этот объект.

*pStringMgr*<br/>
Указатель на менеджер памяти `CFixedStringT` объекта. Для получения `IAtlStringMgr` дополнительной информации `CFixedStringT`и управления памятью для, см. [Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Примечания

Поскольку конструкторы копируют входные данные в новое выделенное хранилище, следует знать, что могут возникнуть исключения из памяти. Некоторые из этих конструкторов выступают в качестве функций преобразования.

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a>CFixedStringT::оператор

Репарализует существующий `CFixedStringT` объект с новыми данными.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>Параметры

*pszSrc*<br/>
Нулевая строка, которая будет `CFixedStringT` скопирована в этот объект.

*strSrc*<br/>
Существующий, `CFixedStringT` который будет `CFixedStringT` скопирован в этот объект.

### <a name="remarks"></a>Примечания

Вы должны знать, что исключения памяти могут возникать всякий раз, когда `CFixedStringT` вы используете оператора назначения, потому что новое хранилище часто выделяется для удержания полученного объекта.

## <a name="see-also"></a>См. также раздел

[Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
