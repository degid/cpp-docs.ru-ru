---
title: "MFC: Использование классов базы данных без документов и представлений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC applications [C++], without views
- documents [C++], applications without
- ODBC applications [C++]
- document/view architecture [C++], in databases
- files [C++], MFC
- database classes [C++], MFC
- CRecordView class, using in database applications
- database applications [C++], without views
- database applications [C++], application wizard options
- application wizards [C++], creating database applications
- ODBC [C++], file support in database applications
- ODBC applications [C++], without documents
- database applications [C++], without documents
- user interface [C++], drawing information
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89c8c1d67a8273b542c088783e4b5121038c9fc2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC. Использование классов базы данных без документов и представлений
Иногда вы не можете использовать архитектуры document/view framework в приложениях базы данных. Содержание раздела:  
  
-   [При необходимости использовать документы](#_core_when_you_don.92.t_need_documents) случаи.  
  
-   [Параметры мастера приложений](#_core_appwizard_options_for_documents_and_views) для поддержки приложений без сериализации и связанных с документом **файл** меню команды, такие как **New**, **откройте**, **Сохранить**, и **сохранение**.  
  
-   [Способы работы с приложением, использующим минимальный документ](#_core_applications_with_minimal_documents).  
  
-   [Способ организации приложения без документов или представлений](#_core_applications_with_no_document).  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a>Если нет необходимости документов  
 Некоторые приложения имеют особое понятие документа. Эти приложения обычно загрузить все или большинство из файла из хранилища в памяти с **Открытие файла** команды. Они записывают обновленный файл обратно в хранилище при **сохранения файла** или **Сохранить как** команды. Пользователю является файлом данных.  
  
 Для некоторых категорий приложений, однако, не требуют документа. Приложения баз данных выполняются как транзакции. Приложение выбирает записи из базы данных и показывает их пользователю, часто одной записи за раз. Пользователю обычно является один текущей записи, который может быть единственным в памяти.  
  
 Если приложение не требует документа для хранения данных, можно избавиться от некоторых или всех архитектуры document/view framework. Сколько можно обойтись зависит от выбранного подхода. Это делается:  
  
-   Используйте минимальный документ, который является местом хранения подключения к источнику данных, но избавиться от обычных функций документа например сериализации. Это полезно в том случае, если необходимо несколько представлений данных и хотите синхронизировать все представления, обновив их все за один раз и т. д.  
  
-   Используйте окно фрейма, в которое можно заносить напрямую, а не с помощью представления. В этом случае опустить документ и сохранять любые данные или подключения к данным в объекте фреймового окна.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a>Параметры мастера приложений для документов и представлений  
 Мастер приложений MFC имеет несколько параметров **Выбор поддержки баз данных**, перечислены в следующей таблице. При использовании мастера приложений MFC для создания приложения, все эти варианты создания приложений с документами и представлениями. Некоторые параметры предоставляют документов и представлений, которые отсутствуют ненужные функции документов. Дополнительные сведения см. в разделе [Поддержка баз данных, мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md).  
  
|Параметр|Просмотр|Document|  
|------------|----------|--------------|  
|**None**|Производное от `CView`.|Не поддерживает базы данных. Этот параметр используется по умолчанию.<br /><br /> При выборе **поддержка архитектуры Document/view** параметр [тип приложения, мастер приложений MFC](../mfc/reference/application-type-mfc-application-wizard.md) будет включать поддержку полного документа, включая сериализации и `New`,  **Откройте**, **Сохранить**, и **Сохранить как** команды **файл** меню. В разделе [приложения для документов](#_core_applications_with_no_document).|  
|**Только файлы заголовков**|Производное от `CView`.|Предоставляет базовый уровень поддержки базы данных для приложения.<br /><br /> Включает в себя Afxdb.h. Добавляет библиотеки, но не создает классы, зависящие от базы данных. Можно создать наборы записей позже и использовать их для проверки и обновления записей.|  
|**Представление базы данных без поддержки файлов**|Производный от`CRecordView`|Предоставляет поддержку документов, но не поддержку сериализации. Документ можно хранить набора записей и координации нескольких представлений; не поддерживает сериализацию или `New`, **откройте**, **Сохранить**, и **Сохранить как** команд. В разделе [приложения с минимальными документами](#_core_applications_with_minimal_documents). При включении представления базы данных необходимо указать источник данных.<br /><br /> Включает файлы заголовков баз данных, библиотек DLL, представление записей и набор записей. (Доступно только для приложений с помощью **поддержка архитектуры Document/view** выбран параметр на [тип приложения, мастер приложений MFC](../mfc/reference/application-type-mfc-application-wizard.md) страницы.)|  
|**Представление базы данных с поддержкой файлов**|Производный от`CRecordView`|Предоставляет полную поддержку документов, включая сериализацию и связанные с документами **файл** команды меню. Приложения баз данных обычно выполняются на основе записей, а не для каждого файла, поэтому не требуется сериализации. Тем не менее может потребоваться специальное использование для сериализации. В разделе [приложения с минимальными документами](#_core_applications_with_minimal_documents). При включении представления базы данных необходимо указать источник данных.<br /><br /> Включает файлы заголовков баз данных, библиотек DLL, представление записей и набор записей. (Доступно только для приложений с помощью **поддержка архитектуры Document/view** выбран параметр на [тип приложения, мастер приложений MFC](../mfc/reference/application-type-mfc-application-wizard.md) страницы.)|  
  
 Описание способа сериализации и альтернативных вариантах использования сериализации см. в разделе [сериализации: vs сериализации. Базы данных ввода вывода](../mfc/serialization-serialization-vs-database-input-output.md).  
  
##  <a name="_core_applications_with_minimal_documents"></a>Приложения с минимальными документами  
 Мастер приложений MFC имеет два параметра, которые поддерживают приложений доступа к данным на основе форм. Каждый из них создает `CRecordView`-производный класс представления и документ. Они отличаются в том, что они пропускают в документе.  
  
###  <a name="_core_a_document_without_file_support"></a>Документ без поддержки файлов  
 Выберите параметр базы данных **представление без поддержки файлов базы данных** при сериализации документа не требуется. Документ выступает следующих целей:  
  
-   Это удобное место для хранения `CRecordset` объекта.  
  
     Такое использование понятием обычного документа: документ хранит данные (или в данном случае набор записей) и представление — представление документа.  
  
-   При наличии в приложении нескольких представлений (например, нескольких представлений записей), документ поддерживает управление представлениями.  
  
     Если представления отображают те же данные, можно использовать `CDocument::UpdateAllViews` функции-члена для координации обновлений ко всем представлениям при изменении любого представления данных.  
  
 Этот параметр обычно используется для простых приложений на основе форм. Мастер приложений поддерживает структуру, удобный для таких приложений автоматически.  
  
###  <a name="_core_a_document_with_file_support"></a>Документ с поддержкой файлов  
 Выберите параметр базы данных **представление с поддержкой файлов базы данных** при наличии альтернативных вариантов использования связанных документов **файл** сериализации документа и команды меню. Для доступа к данным части программы, можно использовать документ таким же образом, как описано в [документ без поддержки файлов](#_core_a_document_without_file_support). Например, возможность сериализации документа, можно использовать для чтения и записи сериализованного документа профиля пользователя, хранящей персональные настройки пользователя или другой полезной информации. Дополнительные идеи см [сериализации: vs сериализации. Базы данных ввода вывода](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Мастер приложений поддерживает этот параметр, но необходимо написать код, который выполняет сериализацию документа. Сериализованные сведения хранятся в элементах данных документа.  
  
##  <a name="_core_applications_with_no_document"></a>Приложения для документов  
 Иногда может потребоваться написать приложение, которое не использует документы и представления. Без документов, хранения данных (таких как `CRecordset` объект) в класс фреймового окна или приложения. Любые дополнительные требования зависят от того, предоставляет ли приложение пользовательский интерфейс.  
  
###  <a name="_core_database_support_with_a_user_interface"></a>Поддержка баз данных с помощью пользовательского интерфейса  
 Если у вас есть пользовательский интерфейс (кроме, например, интерфейса командной строки), приложение взаимодействует непосредственно в клиентской области окна фрейма, а не в представлении. Такое приложение не использует `CRecordView`, `CFormView`, или `CDialog` для основного пользовательского интерфейса, но он обычно используется `CDialog` для обычных диалоговых окон.  
  
###  <a name="_core_writing_applications_without_documents"></a>Написание приложений без документов  
 Поскольку мастер приложений не поддерживает создание приложений без документов, необходимо написать собственный `CWinApp`-производного класса и при необходимости создать `CFrameWnd` или `CMDIFrameWnd` класса. Переопределить `CWinApp::InitInstance` и объявить для объекта приложения:  
  
```  
CYourNameApp theApp;  
```  
  
 Структура по-прежнему предоставляет механизм сопоставления сообщений и многие другие возможности.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a>Поддержка базы данных, отличном от пользовательского интерфейса  
 Некоторые приложения должны пользовательский интерфейс или не только минимальный из них. Например предположим, что вы пишете:  
  
-   Объект промежуточного доступа к данным, вызов другими приложениями (клиентами) для особой обработки данных между приложением и источником данных.  
  
-   Приложение, обрабатывающее данные без участия пользователя, например приложение, которое перемещает данные из одного формата базы данных в другой либо вычисляет и выполняет пакетные обновления.  
  
 Так как документ не является владельцем `CRecordset` объекта, возможно, потребуется сохранить его как вложенный элемент данных в вашей `CWinApp`-производного класса приложения. Следующие варианты.  
  
-   Без обновляемого постоянную `CRecordset` объекта вообще. Можно передать **NULL** в конструкторы класса набор записей. В этом случае платформа создает временный `CDatabase` объекта, используя сведения в наборе записей `GetDefaultConnect` функции-члена. Это наиболее вероятный вариант.  
  
-   Делая `CRecordset` объекта глобальной переменной. Эта переменная должна являться указателем на объект набора записей, создаваемый динамически в вашей `CWinApp::InitInstance` переопределения. Это позволяет избежать предпринимается попытка создать объект до инициализации платформы.  
  
-   С помощью объекта набора записей, как и в контексте документа или представления. Создайте наборы записей в члене функции приложения или фреймового окна объектов.  
  
## <a name="see-also"></a>См. также  
 [MFC-классы баз данных](../data/mfc-database-classes-odbc-and-dao.md)