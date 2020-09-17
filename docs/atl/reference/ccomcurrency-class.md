---
title: Класс Ккомкурренци
ms.date: 11/04/2016
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
ms.openlocfilehash: 2b3c260f250fdb198c8317355628fa2fe62c44eb
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470788"
---
# <a name="ccomcurrency-class"></a>Класс CComCurrency

`CComCurrency` содержит методы и операторы для создания объекта CURRENCY и управления им.

## <a name="syntax"></a>Синтаксис

```
class CComCurrency
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::CComCurrency](#ccomcurrency)|Конструктор объекта `CComCurrency`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Возвращает адрес элемента данных `m_currency`.|
|[CComCurrency::GetFraction](#getfraction)|Вызовите этот метод для возврата дробной части объекта `CComCurrency`.|
|[CComCurrency::GetInteger](#getinteger)|Вызовите этот метод для возврата целой части объекта `CComCurrency`.|
|[CComCurrency::Round](#round)|Вызовите этот метод для округления объекта `CComCurrency` до ближайшего целого значения.|
|[CComCurrency::SetFraction](#setfraction)|Вызовите этот метод для установки дробной части объекта `CComCurrency`.|
|[CComCurrency::SetInteger](#setinteger)|Вызовите этот метод для установки целой части объекта `CComCurrency`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::operator-](#operator_-)|Этот оператор используется для вычитания объекта `CComCurrency`.|
|[CComCurrency::operator!=](#operator_neq)|Проверяет неравенство двух объектов `CComCurrency`.|
|[CComCurrency::operator*](#operator_star)|Этот оператор используется для умножения объекта `CComCurrency`.|
|[CComCurrency::operator*=](#operator_star_eq)|Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator/](#operator_div)|Этот оператор используется для деления объекта `CComCurrency`.|
|[CComCurrency::operator/=](#operator_div_eq)|Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator+](#operator_add)|Этот оператор используется для сложения объекта `CComCurrency`.|
|[CComCurrency::operator+=](#operator_add_eq)|Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator<](#operator_lt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.|
|[CComCurrency::operator<=](#operator_lt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.|
|[CComCurrency::operator=](#operator_eq)|Этот оператор присваивает объекту `CComCurrency` новое значение.|
|[CComCurrency::operator-=](#operator_-_eq)|Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator==](#operator_eq_eq)|Этот оператор сравнивает два объекта `CComCurrency` на равенство.|
|[CComCurrency::operator>](#operator_gt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.|
|[CComCurrency::operator>=](#operator_gt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.|
|[CComCurrency:: оператор CURRENCY](#operator_currency)|Приводит объект CURRENCY.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|Переменная CURRENCY, созданная экземпляром класса.|

## <a name="remarks"></a>Комментарии

`CComCurrency` — это оболочка для типа данных CURRENCY. CURRENCY реализуется как целое 8-байтное значение в дополнительном коде, умноженное на 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данныхCURRENCY крайне полезен для денежных расчетов или расчетов с фиксированной запятой, когда важна точность.

`CComCurrency`Обертка реализует операции арифметического, присваивания и сравнения для этого типа с фиксированной запятой. Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.

Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой. Дробная часть хранится в системе как целое значение от —9 999 (CY_MIN_FRACTION) до +9 999 (CY_MAX_FRACTION). Метод [ккомкурренци::-дробь](#getfraction) возвращает значение, масштабированное с коэффициентом 10000 (CY_SCALE).

При указании целочисленных и дробных компонентов `CComCurrency` объекта Помните, что дробный компонент является числом в диапазоне от 0 до 9999. Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой. Хотя две последние цифры не отображаются, их необходимо учитывать.

|Значение|Возможные значения CComCurrency|
|-----------|---------------------------------------|
|$10.50|CComCurrency(10,5000) *или* CComCurrency(10.50)|
|$10.05|CComCurrency(10,500) *или* CComCurrency(10.05)|

Значения CY_MIN_FRACTION, CY_MAX_FRACTION и  CY_SCALE определены в файле atlcur.h.

## <a name="requirements"></a>Требования

**Заголовок:** атлкур.h

## <a name="ccomcurrencyccomcurrency"></a><a name="ccomcurrency"></a>CComCurrency:: CComCurrency

Конструктор.

```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);
CComCurrency(USHORT usSrc);
CComCurrency(CHAR cSrc);
CComCurrency(DOUBLE dSrc);
CComCurrency(FLOAT fSrc);
CComCurrency(LONG lSrc);
CComCurrency(SHORT sSrc);
CComCurrency(BYTE bSrc);
CComCurrency(LONGLONG nInteger, SHORT nFraction);
explicit CComCurrency(LPDISPATCH pDispSrc);
explicit CComCurrency(const VARIANT& varSrc);
explicit CComCurrency(LPCWSTR szSrc);
explicit CComCurrency(LPCSTR szSrc);
```

### <a name="parameters"></a>Параметры

*курсрк*<br/>
Существующий объект `CComCurrency`.

*цисрк*<br/>
Переменная типа CURRENCY.

*бсрк*, *дсрк*, *ФСРК*, *лсрк*, *ССРК*, *улсрк, уссрк*<br/>
Начальное значение, присваиваемое переменной члена `m_currency` .

*ксрк*<br/>
Символ, содержащий начальное значение, присвоенное переменной-члену `m_currency` .

*нинтежер*, *нфрактион*<br/>
Целочисленные и дробные компоненты начального денежного значения. Дополнительные сведения см. в обзоре [ккомкурренци](../../atl/reference/ccomcurrency-class.md) .

*пдиспсрк*<br/>
`IDispatch`Указатель.

*varSrc*<br/>
Переменная типа VARIANT. Языковой стандарт текущего потока используется для выполнения преобразования.

*сзсрк*<br/>
Строка в Юникоде или ANSI, содержащая начальное значение. Языковой стандарт текущего потока используется для выполнения преобразования.

### <a name="remarks"></a>Комментарии

Конструктор задает начальное значение [ккомкурренци:: m_currency](#m_currency)и принимает широкий диапазон типов данных, включая целые числа, строки, числа с плавающей запятой, переменные валюты и другие `CComCurrency` объекты. Если значение не указано, присваивается значение `m_currency` 0.

В случае ошибки, например переполнения, конструкторы не имеют пустого вызова спецификации исключения (**Throw ()**) `AtlThrow` со значением HRESULT, описывающим ошибку.

При использовании значений с плавающей запятой или двойной точности для присваивания значения Обратите внимание, что `CComCurrency(10.50)` эквивалентно `CComCurrency(10,5000)` и Not `CComCurrency(10,50)` .

## <a name="ccomcurrencygetcurrencyptr"></a><a name="getcurrencyptr"></a>CComCurrency:: Жеткурренциптр

Возвращает адрес элемента данных `m_currency`.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес `m_currency` элемента данных

## <a name="ccomcurrencygetfraction"></a><a name="getfraction"></a>CComCurrency:: дробь

Вызовите этот метод, чтобы вернуть дробный компонент `CComCurrency` объекта.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дробный компонент `m_currency` элемента данных.

### <a name="remarks"></a>Комментарии

Компонент дробной части представляет собой 4-значное целочисленное значение в диапазоне от-9999 (CY_MIN_FRACTION) до + 9999 (CY_MAX_FRACTION). `GetFraction`Возвращает это значение, масштабированное на 10000 (CY_SCALE). Значения CY_MIN_FRACTION, CY_MAX_FRACTION и CY_SCALE определены в атлкур.h.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

## <a name="ccomcurrencygetinteger"></a><a name="getinteger"></a>CComCurrency:: integer

Вызовите этот метод, чтобы получить целочисленный компонент `CComCurrency` объекта.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает целочисленный компонент `m_currency` элемента данных.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

## <a name="ccomcurrencym_currency"></a><a name="m_currency"></a>CComCurrency:: m_currency

Элемент данных валюты.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Комментарии

Этот элемент содержит валюту, к которой обращаются и которыми манипулируют методы этого класса.

## <a name="ccomcurrencyoperator--"></a><a name="operator_-"></a>CComCurrency::operator-

Этот оператор используется для вычитания объекта `CComCurrency`.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат вычитания. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_neq"></a>CComCurrency::operator!=

Этот оператор сравнивает два объекта на неравенство.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Сравниваемый объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если сравниваемый элемент не равен `CComCurrency` объекту; в противном случае — значение false.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star"></a>CComCurrency::operator*

Этот оператор используется для умножения объекта `CComCurrency`.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Коэффициент.

*выравнивани*<br/>
`CComCurrency`Объект, используемый в качестве множителя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат умножения. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star_eq"></a>CComCurrency::operator\*=

Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Коэффициент.

*выравнивани*<br/>
`CComCurrency`Объект, используемый в качестве множителя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div"></a>CComCurrency::operator/

Этот оператор используется для деления объекта `CComCurrency`.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат деления. Если делитель равен 0, произойдет сбой Assert.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div_eq"></a>CComCurrency::operator/=

Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. Если делитель равен 0, произойдет сбой Assert.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add"></a>CComCurrency::operator+

Этот оператор используется для сложения объекта `CComCurrency`.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
`CComCurrency`Объект, добавляемый в исходный объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат сложения. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add_eq"></a>CComCurrency::operator+=

Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt"></a>CComCurrency::operator&lt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше второго, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt_eq"></a>CComCurrency::operator&lt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше или равен второму, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq"></a>CComCurrency::operator=

Этот оператор присваивает объекту `CComCurrency` новое значение.

```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```

### <a name="parameters"></a>Параметры

*курсрк*<br/>
Объект `CComCurrency`.

*цисрк*<br/>
Переменная типа CURRENCY.

*ССРК*, *ФСРК*, *лсрк*, *бсрк*, *уссрк*, *дсрк*, *КСРК*, *улсрк*, *дсрк*<br/>
Числовое значение, присваиваемое `CComCurrency` объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

## <a name="ccomcurrencyoperator--"></a><a name="operator_-_eq"></a>CComCurrency::operator-=

Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq_eq"></a>CComCurrency::operator==

Этот оператор сравнивает два объекта `CComCurrency` на равенство.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`, подлежащий сравнению.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны (то есть `m_currency` элементы данных, как целые, так и дробные, в обоих объектах имеют одинаковое значение), в противном случае — значение false.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt"></a>CComCurrency::operator&gt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше второго, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt_eq"></a>CComCurrency::operator&gt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*выравнивани*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше или равен второму, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

## <a name="ccomcurrencyoperator-currency"></a><a name="operator_currency"></a>CComCurrency:: оператор CURRENCY

Эти операторы используются для приведения `CComCurrency` объекта к типу данных Currency.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на объект CURRENCY.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

## <a name="ccomcurrencyround"></a><a name="round"></a>CComCurrency:: Round

Вызовите этот метод, чтобы округлить валюту до указанного числа десятичных разрядов.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Параметры

*ндеЦималс*<br/>
Число знаков, до которого `m_currency` будет округляться значение в диапазоне от 0 до 4.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

## <a name="ccomcurrencysetfraction"></a><a name="setfraction"></a>CComCurrency:: Сетфрактион

Вызовите этот метод для установки дробной части объекта `CComCurrency`.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Параметры

*нфрактион*<br/>
Значение, присваиваемое дробному компоненту `m_currency` элемента данных. Знак дробного компонента должен быть таким же, как и у целочисленного компонента, а значение должно находиться в диапазоне от-9999 (CY_MIN_FRACTION) до + 9999 (CY_MAX_FRACTION).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

## <a name="ccomcurrencysetinteger"></a><a name="setinteger"></a>CComCurrency:: Сетинтежер

Вызовите этот метод для установки целой части объекта `CComCurrency`.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Параметры

*нинтежер*<br/>
Значение, присваиваемое целочисленному компоненту `m_currency` элемента данных. Знак целочисленного компонента должен соответствовать знаку существующего дробного компонента.

*нинтежер* должен находиться в диапазоне CY_MIN_INTEGER для CY_MAX_INTEGER включительно. Эти значения определены в атлкур.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>См. также

[Класс COleCurrency](../../mfc/reference/colecurrency-class.md)<br/>
[ДЕНЕЖНАЯ ЕДИНИЦА](/windows/win32/api/wtypes/ns-wtypes-cy-r1)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
