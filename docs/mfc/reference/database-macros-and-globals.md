---
title: Макросы и глобальные объекты баз данных
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 0dc53bce8b43677e7fe0aa1787d1adcc16a560c4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837531"
---
# <a name="database-macros-and-globals"></a>Макросы и глобальные объекты баз данных

Указанные ниже макросы и глобальные приложения применимы к приложениям баз данных на основе ODBC. Они не используются в приложениях на основе DAO.

До MFC 4,2 макросы `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` дают асинхронным операциям возможность получить время для других процессов. Начиная с MFC 4,2, реализация этих макросов изменилась, так как классы ODBC MFC используют только синхронные операции. Макрос `AFX_ODBC_CALL` был впервые добавлен в MFC 4,2.

### <a name="database-macros"></a>Макросы базы данных

|Имя|Описание|
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Вызывает функцию API ODBC, которая возвращает `SQL_STILL_EXECUTING` . `AFX_ODBC_CALL` будет вызывать функцию повторно, пока она не вернет значение `SQL_STILL_EXECUTING` .|
|[AFX_SQL_ASYNC](#afx_sql_async)|Вызывает `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Вызывает функцию API ODBC, которая не возвращает `SQL_STILL_EXECUTING` .|

### <a name="database-globals"></a>Глобальные базы данных

|Имя|Описание|
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|Добавляет поддержку базы данных для обычной библиотеки DLL MFC, которая динамически связана с MFC.|
|[AfxGetHENV](#afxgethenv)|Извлекает маркер среды ODBC, используемой в настоящий момент библиотекой MFC. Этот обработчик можно использовать в прямых вызовах ODBC.|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a> афксдбинитмодуле

Для поддержки базы данных MFC (или DAO) из обычной библиотеки DLL MFC, которая динамически связана с MFC, добавьте вызов этой функции в функции обычной библиотеки DLL MFC `CWinApp::InitInstance` для инициализации библиотеки DLL базы данных MFC.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Примечания

Убедитесь, что этот вызов происходит до любого вызова базового класса или любого добавленного кода, который обращается к библиотеке DLL базы данных MFC. Библиотека DLL базы данных MFC является библиотекой DLL расширения MFC. чтобы библиотека DLL расширения MFC была подключена к `CDynLinkLibrary` цепочке, она должна создать `CDynLinkLibrary` объект в контексте каждого модуля, который будет его использовать. `AfxDbInitModule` создает `CDynLinkLibrary` объект в контексте обычной библиотеки DLL MFC, чтобы он был подключен в `CDynLinkLibrary` цепочке объектов обычной библиотеки DLL MFC.

### <a name="requirements"></a>Требования

**Заголовок:**\<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a> AFX_ODBC_CALL

Используйте этот макрос для вызова любой функции API ODBC, которая может возвращать `SQL_STILL_EXECUTING` .

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Параметры

*склфунк*<br/>
Функция API ODBC. Дополнительные сведения о функциях API ODBC см. в Windows SDK.

### <a name="remarks"></a>Примечания

`AFX_ODBC_CALL` многократно вызывает функцию, пока она больше не возвращает значение `SQL_STILL_EXECUTING` .

Перед вызовом `AFX_ODBC_CALL` необходимо объявить переменную `nRetCode` типа реткоде.

Обратите внимание, что классы ODBC MFC теперь используют только синхронную обработку. Для выполнения асинхронной операции необходимо вызвать функцию API ODBC `SQLSetConnectOption` . Дополнительные сведения см. в разделе "асинхронное выполнение функций в Windows SDK".

### <a name="example"></a>Пример

В этом примере используется `AFX_ODBC_CALL` для вызова `SQLColumns` функции ODBC API, которая возвращает список столбцов в таблице с именем `strTableName` . Обратите внимание на объявление `nRetCode` и использование элементов данных набора записей для передачи параметров в функцию. Пример также иллюстрирует проверку результатов вызова с помощью `Check` функции-члена класса `CRecordset` . Переменная `prs` является указателем на `CRecordset` объект, объявленный в других местах.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** афксдб.h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a> AFX_SQL_ASYNC

Реализация этого макроса изменена в MFC 4,2.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Параметры

*Вытягивание*<br/>
Указатель на `CRecordset` объект или `CDatabase` объект. Начиная с MFC 4,2, значение этого параметра игнорируется.

*склфунк*<br/>
Функция API ODBC. Дополнительные сведения о функциях API ODBC см. в Windows SDK.

### <a name="remarks"></a>Примечания

`AFX_SQL_ASYNC` просто вызывает макрос [AFX_ODBC_CALL](#afx_odbc_call) и игнорирует параметр *вытягивание* . В версиях MFC до 4,2 использовался `AFX_SQL_ASYNC` для вызова функций API ODBC, которые могут возвращать `SQL_STILL_EXECUTING` . Если функция API ODBC возвращала `SQL_STILL_EXECUTING` , `AFX_SQL_ASYNC` вызовите `prs->OnWaitForDataSource` .

> [!NOTE]
> Классы ODBC MFC теперь используют только синхронную обработку. Для выполнения асинхронной операции необходимо вызвать функцию API ODBC `SQLSetConnectOption` . Дополнительные сведения см. в разделе "асинхронное выполнение функций в Windows SDK".

### <a name="requirements"></a>Требования

  **Заголовок** афксдб.h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a> AFX_SQL_SYNC

`AFX_SQL_SYNC`Макрос просто вызывает функцию `SQLFunc` .

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Параметры

*склфунк*<br/>
Функция API ODBC. Дополнительные сведения об этих функциях см. в Windows SDK.

### <a name="remarks"></a>Примечания

Используйте этот макрос для вызова функций ODBC API, которые не будут возвращать `SQL_STILL_EXECUTING` .

Перед вызовом `AFX_SQL_SYNC` необходимо объявить переменную `nRetCode` типа реткоде. Можно проверить значение `nRetCode` после вызова макроса.

Обратите внимание, что реализация `AFX_SQL_SYNC` изменена в MFC 4,2. Поскольку проверка состояния сервера больше не требуется, `AFX_SQL_SYNC` просто присваивает значение `nRetCode` . Например, вместо выполнения вызова

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

можно просто сделать назначение

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** афксдб.h

## <a name="afxgethenv"></a><a name="afxgethenv"></a> афксжесенв

Возвращенный обработчик можно использовать в прямых вызовах ODBC, но не следует закрывать этот обработчик или предполагается, что он остается действительным и доступным после уничтожения всех существующих `CDatabase` или `CRecordset` производных объектов.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик для среды ODBC, используемой в настоящий момент библиотекой MFC. Может иметь значение, `SQL_HENV_NULL` Если объекты [CDatabase](../../mfc/reference/cdatabase-class.md) отсутствуют, а объекты [CRecordset](../../mfc/reference/crecordset-class.md) не используются.

### <a name="requirements"></a>Требования

  **Заголовок** афксдб.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
