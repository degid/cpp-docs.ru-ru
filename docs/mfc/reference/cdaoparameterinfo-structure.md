---
title: Структура CDaoParameterInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 6d594bbeec34e400eb074c136e3467e78b35c4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368980"
---
# <a name="cdaoparameterinfo-structure"></a>Структура CDaoParameterInfo

Структура `CDaoParameterInfo` содержит информацию об объекте параметра, определяемом для объектов доступа к данным (DAO). DAO 3.6 является окончательной версией, и он считается устаревшим.

## <a name="syntax"></a>Синтаксис

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Уникально называет объект параметра. Для получения дополнительной информации, см.

*m_nType*<br/>
Значение, указывавававание типа данных объекта параметра. Список возможных значений можно узнать m_nType *члена* структуры [CDaoFieldInfo.](../../mfc/reference/cdaofieldinfo-structure.md) Для получения дополнительной информации, см.

*m_varValue*<br/>
Значение параметра, хранящегося в объекте [COleVariant.](../../mfc/reference/colevariant-class.md)

## <a name="remarks"></a>Примечания

Ссылки на Начальную и Вторичную выше указывают, как информация `CDaoQueryDef`возвращается функцией участника [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) в классе.

MFC не инкапсулирует параметры объектов DAO в классе. DAO querydef объектов, `CDaoQueryDef` лежащих в основе объектов MFC хранения параметров в своих параметрах коллекций. Чтобы получить доступ к объектам параметра в объекте [CDao'EryDef,](../../mfc/reference/cdaoquerydef-class.md) позвоните в функцию `GetParameterInfo` члена объекта querydef для конкретного имени параметра или индекса в коллекцию параметров. Вы можете использовать функцию участника [CDao-'''''iryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) в сочетании с `GetParameterInfo` циклом в коллекции параметров.

Информация, полученная в рамках функции участника [CDao''''iryDef::GetParameterInfo,](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) хранится в структуре. `CDaoParameterInfo` Вызов `GetParameterInfo` объекта запроса, в коллекции параметров которого хранится объект параметра.

> [!NOTE]
> Если вы хотите получить или установить только значение параметра, используйте функции члена `CDaoRecordset` [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) и [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) класса.

`CDaoParameterInfo`также определяет `Dump` функцию члена в сборках отладок. Содержимое `CDaoParameterInfo` `Dump` объекта можно использовать.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также раздел

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CДао-КуириДеф](../../mfc/reference/cdaoquerydef-class.md)
