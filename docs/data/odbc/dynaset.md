---
title: "Динамический набор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b94957d4402eda467dbe5bb20d6522e123f2e34
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dynaset"></a>Динамический набор
В этом разделе описываются динамические подмножества данных и описывает их [доступности](#_core_availability_of_dynasets).  
  
> [!NOTE]
>  Этот раздел относится к классам MFC ODBC, включая [CRecordset](../../mfc/reference/crecordset-class.md). Сведения о динамических подмножеств данных в классах DAO см. в разделе [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md). С помощью DAO можно открывать наборы записей динамического типа.  
  
 Динамический набор — это набор записей с динамическими свойствами. Во время существования объектом набора записей в режиме динамического подмножества (обычно называемый подмножества) поддерживается синхронизация с источником данных следующим образом. В многопользовательской среде другие пользователи могут изменить или удаления записей, которые динамического набора и добавить записи в таблицу, которую представляет динамического набора. Записи, приложения, добавляет или удаляет из набора записей, отражаются в динамического набора. Записи, которые другие пользователи добавляют в таблицу не быть отражено динамического набора, пока вновь динамический набор путем вызова его **Requery** функции-члена. Когда другие пользователи удаляют записи, код MFC пропускает эти удаления в наборе записей. Изменения существующих записей других пользователей, отражаются в динамического набора, сразу перейдите к измененной записи.  
  
 Аналогичным образом изменения, вносимые в динамический набор записей, отражаются в динамическом множестве данных используется другими пользователями. Записей, добавляемых не отражаются в динамическом множестве данных других пользователей, пока они requery их динамических подмножеств данных. Удаляемые вами записи помечаются как «удалено» в наборах записей других пользователей. Если имеется несколько подключений к одной базе данных (несколько `CDatabase` объектов), связанные с этими подключениями наборы записей с таким же статусом как наборы записей других пользователей.  
  
 Динамические подмножества наиболее полезны, когда данные должны быть динамическими, как, к примеру, в системе бронирования авиабилетов.  
  
> [!NOTE]
>  Чтобы использовать динамические подмножества данных, необходимо иметь драйвер ODBC для источника данных, который поддерживает динамические подмножества данных и библиотеку курсоров ODBC не должна быть загружена. Дополнительные сведения см. в разделе [доступность динамических подмножеств данных](#_core_availability_of_dynasets).  
  
 Чтобы указать, что набор записей является динамическим подмножеством, передайте **CRecordset::dynaset** как первый параметр для **откройте** функцию-член объекта набора записей.  
  
> [!NOTE]
>  Для обновляемых динамических подмножеств драйвер ODBC должен поддерживать инструкции позиционированного обновления или **:: SQLSetPos** функции ODBC API. Если оба поддерживаются, MFC использует **:: SQLSetPos** для повышения эффективности.  
  
##  <a name="_core_availability_of_dynasets"></a>Доступность динамических подмножеств данных  
 Классы баз данных MFC поддерживает динамические подмножества данных, если удовлетворяются следующие требования:  
  
-   Библиотека курсоров ODBC библиотеки DLL не должны использовать для этого источника данных.  
  
     При использовании библиотеки курсоров, он скрывает некоторую функциональность базового драйвера ODBC, необходимую для поддержки динамических подмножеств данных. Если вы хотите использовать динамические подмножества данных (и драйвер ODBC имеет функциональность, необходимую для поддержки динамических подмножеств, как описывается ниже в этом разделе), можно заставить MFC не загружает библиотеку курсоров при создании `CDatabase` объекта. Дополнительные сведения см. в разделе [ODBC](../../data/odbc/odbc-basics.md) и [OpenEx](../../mfc/reference/cdatabase-class.md#openex) или [откройте](../../mfc/reference/cdatabase-class.md#open) функции-члена класса `CDatabase`.  
  
     В терминологии ODBC подмножества и моментальные снимки называются курсоров. Курсор — это механизм, используемый для отслеживания его позиции в наборе записей.  
  
-   Драйвер ODBC для источника данных должен поддерживать управляемые набором ключей курсоры.  
  
     Управляемые набором ключей курсоры управления данными из таблицы путем получения и сохранения набора ключей. Ключи используются для получения текущих данных из таблицы, когда пользователь перемещается к определенной записи. Чтобы определить, является ли ваш драйвер поддерживает этот, вызовите **:: SQLGetInfo** функции API-интерфейса ODBC с **SQL_SCROLL_OPTIONS** параметра.  
  
     Если вы попытаетесь открыть подмножества без поддержки набора ключей, вы получаете `CDBException` с значение кода возврата **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**.  
  
-   Драйвер ODBC для источника данных должен поддерживать расширенную выборку.  
  
     Расширенная выборка — возможность назад, а также вперед по результирующим записям SQL-запроса. Чтобы определить, является ли драйвер поддерживает эту возможность, вызовите **:: SQLGetFunctions** функции API-интерфейса ODBC с **SQL_API_SQLEXTENDEDFETCH** параметра.  
  
 Если требуется использовать обновляемые динамические подмножества (или моментальные снимки по этой причине), драйвер ODBC должен также поддерживать **:: SQLSetPos** функции API-интерфейса ODBC или позиционированные обновления. **:: SQLSetPos** функция позволяет MFC обновить источник данных без отправки инструкций SQL. Данная поддержка доступна, MFC использует вместо внесения изменений, использующих SQL. Чтобы определить, поддерживает ли драйвер **:: SQLSetPos**, вызовите **:: SQLGetInfo** с **SQL_POS_OPERATIONS** параметра.  
  
 Позиционированные обновления используют синтаксис SQL (в форме **WHERE CURRENT OF** \<cursorname >) для указания конкретной строки в таблице в источнике данных. Чтобы определить, поддерживает ли драйвер позиционированные обновления, вызовите **:: SQLGetInfo** с **SQL_POSITIONED_STATEMENTS** параметра.  
  
 Как правило динамические подмножества данных MFC (но не наборы записей последовательного доступа) требуют драйвера ODBC с помощью интерфейса API ODBC уровня 2. Если драйвер для источника данных соответствует набор API уровня 1, можно по-прежнему использовать обновляемые и только для чтения моментальные снимки и наборы последовательного доступа, но не динамических подмножеств данных. Тем не менее драйвер уровня 1 может поддерживать динамические подмножества данных, если он поддерживает расширенную выборку и курсоры. Дополнительные сведения об уровнях совместимости ODBC см. в разделе [ODBC](../../data/odbc/odbc-basics.md).  
  
> [!NOTE]
>  Если вы хотите использовать моментальные снимки и динамические подмножества данных, необходимо основываться на двух разных `CDatabase` объектов (подключения).  
  
 В отличие от моментальных снимков, которые используют промежуточное хранилище, поддерживаемое библиотекой курсоров ODBC, динамические подмножества извлекают запись непосредственно из источника данных как можно скорее при прокрутке к ней. Благодаря этому записи, отличающегося от выбранного динамическим синхронизированы с источником данных.  
  
 Список драйверов ODBC, поставляемых в этой версии Visual C++ и сведения о приобретении дополнительных драйверов см. в разделе [список драйверов ODBC](../../data/odbc/odbc-driver-list.md).  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)