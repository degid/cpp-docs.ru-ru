---
title: Класс Ккомсафеаррайбаунд
ms.date: 05/06/2019
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: 9adee1e8b6a46c239aaf6a3c404277b34efd00e2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834756"
---
# <a name="ccomsafearraybound-class"></a>Класс Ккомсафеаррайбаунд

Этот класс является оболочкой для структуры [сафеаррайбаунд](/windows/win32/api/oaidl/ns-oaidl-safearraybound) .

## <a name="syntax"></a>Синтаксис

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Функция|Описание|
|-|-|
|[ккомсафеаррайбаунд](#ccomsafearraybound)|Конструктор.|
|[GetCount](#getcount)|Вызовите этот метод, чтобы получить количество элементов.|
|[жетловербаунд](#getlowerbound)|Вызовите этот метод, чтобы вернуть нижнюю границу.|
|[GetUpperBound](#getupperbound)|Вызовите этот метод, чтобы получить верхнюю границу.|
|[сеткаунт](#setcount)|Вызовите этот метод, чтобы задать количество элементов.|
|[сетловербаунд](#setlowerbound)|Вызовите этот метод, чтобы задать нижнюю границу.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#operator_eq)|Задает `CComSafeArrayBound` новое значение.|

## <a name="remarks"></a>Примечания

Этот класс является оболочкой для `SAFEARRAYBOUND` структуры, используемой [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Он предоставляет методы для запросов и установки верхних и нижних границ одного измерения `CComSafeArray` объекта и числа элементов, содержащихся в нем. В многомерном `CComSafeArray` объекте используется массив `CComSafeArrayBound` объектов, по одному для каждого измерения. Поэтому при использовании таких методов, как [NOCOUNT](#getcount), следует помнить, что этот метод не возвращает общее число элементов в многомерном массиве.

**Заголовок:** atlsafe.h

## <a name="requirements"></a>Требования

**Заголовок:** atlsafe.h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a> Ккомсафеаррайбаунд:: Ккомсафеаррайбаунд

Конструктор.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Параметры

*улкаунт*<br/>
Количество элементов в массиве.

*лловербаунд*<br/>
Нижняя граница, с которой пронумерован массив.

### <a name="remarks"></a>Примечания

Если доступ к массиву осуществляется из программы на языке C++, рекомендуется, чтобы нижняя граница была определена как 0. Может быть предпочтительнее использовать другое значение нижней границы, если массив используется с другими языками, например Visual Basic.

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a> Ккомсафеаррайбаунд:: NOCOUNT

Вызовите этот метод, чтобы получить количество элементов.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов.

### <a name="remarks"></a>Примечания

Если связанный `CComSafeArray` объект представляет многомерный массив, этот метод возвратит только общее число элементов в крайнем правом измерении. Чтобы получить общее количество элементов, используйте [CComSafeArray:: NOCOUNT](../../atl/reference/ccomsafearray-class.md#getcount) .

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a> Ккомсафеаррайбаунд:: Жетловербаунд

Вызовите этот метод, чтобы вернуть нижнюю границу.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает нижнюю границу `CComSafeArrayBound` объекта.

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a> Ккомсафеаррайбаунд:: GetUpperBound

Вызовите этот метод, чтобы получить верхнюю границу.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верхнюю границу `CComSafeArrayBound` объекта.

### <a name="remarks"></a>Примечания

Верхняя граница зависит от количества элементов и значения нижней границы. Например, если нижняя граница равна 0, а число элементов равно 10, то верхняя граница будет автоматически установлена в значение 9.

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a> Ккомсафеаррайбаунд::operator=

Задает `CComSafeArrayBound` новое значение.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Параметры

*выход*<br/>
Объект `CComSafeArrayBound`.

*улкаунт*<br/>
Число элементов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `CComSafeArrayBound` объект.

### <a name="remarks"></a>Примечания

`CComSafeArrayBound`Объект может быть назначен с помощью существующего `CComSafeArrayBound` или путем предоставления количества элементов, в противном случае значение нижней границы по умолчанию равно 0.

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a> Ккомсафеаррайбаунд:: Сеткаунт

Вызовите этот метод, чтобы задать количество элементов.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Параметры

*улкаунт*<br/>
Число элементов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в `CComSafeArrayBound` объекте.

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a> Ккомсафеаррайбаунд:: Сетловербаунд

Вызовите этот метод, чтобы задать нижнюю границу.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Параметры

*лловербаунд*<br/>
Нижняя граница.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую нижнюю границу `CComSafeArrayBound` объекта.

### <a name="remarks"></a>Примечания

Если доступ к массиву осуществляется из Visual C++ программы, рекомендуется, чтобы нижняя граница была определена как 0. Может быть предпочтительнее использовать другое значение нижней границы, если массив используется с другими языками, например Visual Basic.

Верхняя граница зависит от количества элементов и значения нижней границы. Например, если нижняя граница равна 0, а число элементов равно 10, то верхняя граница будет автоматически установлена в значение 9.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
