---
title: Структура CDaoErrorInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: 8d731c8e8bea1adc850ab3c00c7688b9f8c9b819
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304225"
---
# <a name="cdaoerrorinfo-structure"></a>Структура CDaoErrorInfo

Структура `CDaoErrorInfo` содержит сведения об объекте Error, определенном для объектов доступа к данным (DAO). Версия DAO 3,6 является окончательной и считается устаревшей.

## <a name="syntax"></a>Синтаксис

```
struct CDaoErrorInfo
{
    long m_lErrorCode;
    CString m_strSource;
    CString m_strDescription;
    CString m_strHelpFile;
    long m_lHelpContext;
};
```

#### <a name="parameters"></a>Параметры

*m_lErrorCode*<br/>
Числовой код ошибки DAO. См. раздел "ошибки доступа к обрабатываемым данным" справки DAO.

*m_strSource*<br/>
Имя объекта или приложения, первоначально вызвавшего ошибку. Свойство Source указывает строковое выражение, представляющее объект, изначально создавший ошибку. выражение обычно является именем класса объекта. Дополнительные сведения см. в разделе "свойство источника" справки DAO.

*m_strDescription*<br/>
Описательная строка, связанная с ошибкой. Дополнительные сведения см. в разделе "свойство описания" справки DAO.

*m_strHelpFile*<br/>
Полный путь к файлу справки Microsoft Windows. Дополнительные сведения см. в подразделе «HelpContext, свойства HelpFile» справки DAO.

*m_lHelpContext*<br/>
Идентификатор контекста для раздела в файле справки Microsoft Windows. Дополнительные сведения см. в подразделе «HelpContext, свойства HelpFile» справки DAO.

## <a name="remarks"></a>Примечания

MFC не инкапсулирует объекты ошибок DAO в классе. Вместо этого класс [кдаоексцептион](../../mfc/reference/cdaoexception-class.md) предоставляет интерфейс для доступа к коллекции Errors, содержащейся в объекте DAO `DBEngine`, объекте, который также содержит все рабочие области. Когда операция MFC DAO создает `CDaoException` перехватывается объект, MFC заполняет структуру `CDaoErrorInfo` и сохраняет ее в элементе [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) объекта исключения. (Если вы решили напрямую вызывать DAO, необходимо самостоятельно вызвать функцию-член [жетерроринфо](../../mfc/reference/cdaoexception-class.md#geterrorinfo) объекта исключения, чтобы заполнить `m_pErrorInfo`.)

Дополнительные сведения об обработке ошибок DAO см. в статье [исключения базы данных](../../mfc/exceptions-database-exceptions.md). Дополнительные сведения см. в разделе «объект Error» справки DAO.

Сведения, получаемые функцией-членом [кдаоексцептион:: жетерроринфо](../../mfc/reference/cdaoexception-class.md#geterrorinfo) , хранятся в структуре `CDaoErrorInfo`. Изучите элемент данных [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) из объекта `CDaoException`, который перехватывается обработчиком исключений, или вызовите `GetErrorInfo` из объекта `CDaoException`, созданного явным образом, чтобы проверить ошибки, которые могли произойти во время прямого вызова интерфейсов DAO. `CDaoErrorInfo` также определяет функцию-член `Dump` в отладочных сборках. Для дампа содержимого объекта `CDaoErrorInfo` можно использовать `Dump`.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао.h

## <a name="see-also"></a>См. также:

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoException](../../mfc/reference/cdaoexception-class.md)
