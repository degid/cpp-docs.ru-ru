---
title: Класс CLongBinary
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: 1ce1daba90f3a1dad4b9627082d63f1b3405eab4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370140"
---
# <a name="clongbinary-class"></a>Класс CLongBinary

Упрощает работу с очень большими объектами двоичных данных (BLOB-объектами) в базе данных.

## <a name="syntax"></a>Синтаксис

```
class CLongBinary : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CLongBinary::CLongBinary](#clongbinary)|Формирует объект `CLongBinary`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Содержит фактический размер байтов объекта данных, `m_hData`в котором хранится ручка.|
|[CLongBinary::m_hData](#m_hdata)|Содержит ручку Windows HGLOBAL к объекту фактического изображения.|

## <a name="remarks"></a>Примечания

Например, поле записи в таблице S'L может содержать битную карту, представляющую изображение. Объект `CLongBinary` хранит такой объект и отслеживает его размер.

> [!NOTE]
> В общем, лучше использовать [CByteArray](../../mfc/reference/cbytearray-class.md) в сочетании с [DFX_Binary](record-field-exchange-functions.md#dfx_binary) функции. Вы все `CLongBinary`еще можете `CByteArray` использовать, но в целом обеспечивает больше функциональности под Win32, `CByteArray`так как больше нет ограничения размера, встречающихся с 16-битным . Этот совет относится к программированию с объектами доступа к данным (DAO), а также open Database Connectivity (ODBC).

Чтобы использовать `CLongBinary` объект, объявите полевой `CLongBinary` член данных типа в классе записей. Этот участник будет встроенным членом класса recordset и будет построен, когда будет построен рекорд. После `CLongBinary` построения объекта механизм обмена полями записи (RFX) загружает объект данных с поля в текущем источнике на источнике данных и сохраняет его обратно в запись при обновлении записи. RFX запрашивает источник данных для размера двоичного крупного объекта, `CLongBinary` выделяет `m_hData` хранилище для него `HGLOBAL` (через член `m_hData`данных объекта) и хранит ручку к данным в. RFX также хранит фактический размер объекта `m_dwDataLength` данных в члене данных. Работайте с данными `m_hData`в объекте с помощью тех же методов, которые `HGLOBAL` обычно используются для управления данными, хранящимися в ручке Windows.

Когда вы уничтожаете `CLongBinary` свой рекорд, встроенный объект также разрушается, а его деструктор разлагает ручку `HGLOBAL` данных.

Для получения дополнительной информации о `CLongBinary`крупных объектах и использовании , см. статьи [Recordset (ODBC)](../../data/odbc/recordset-odbc.md) и [Recordset: Работа с большими элементами данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb_.h

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a>CLongBinary::CLongBinary

Формирует объект `CLongBinary`.

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength

Хранит фактический размер байтов данных, хранящихся в ручке HGLOBAL в `m_hData`.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Примечания

Этот размер может быть меньше, чем размер блока памяти, выделенного для данных. Позвоните в функцию Win32 [GLobalSize,](/windows/win32/api/winbase/nf-winbase-globalsize) чтобы получить выделенный размер.

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a>CLongBinary::m_hData

Хранит ручку Windows HGLOBAL для фактических двоичных данных больших объектов.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
