---
title: "Поддержка многобайтовой кодировки (MBCS) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
caps.latest.revision: "11"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 19bbcd1030bdc89de2d3e05281786c1d0efa5ad6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>Поддержка многобайтовых кодировок
Многобайтовые кодировки (MBCS) — это более старый подход к поддержке кодировок, подобных японской и китайской, которые не могут быть представлены одним байтом. Для разработки новых приложений следует использовать Юникод для всех текстовых строк, за исключением, возможно, системных строк, которые не видны пользователям. MBCS — это устаревшая технология, которая не рекомендуется для разработки новых приложений.  
  
 Наиболее распространенная реализация многобайтовой кодировки — двухбайтовая кодировка (DBCS). Visual C++ в целом и MFC в частности полностью поддерживают DBCS.  
  
 Примеры см. в файлах исходного кода MFC.  
  
 Для платформ, использующих объемные кодировки, наилучшая альтернатива Юникоду — это MBCS. MFC поддерживает MBCS с помощью интернациализируемых типов данных и функций времени выполнения C. То же следует сделать и в вашем коде.  
  
 В MBCS символы кодируются одним или двумя байтами. В двухбайтовых символах первый или старший байт указывает, что он и следующий байт должны интерпретироваться как один символ. Первый байт относится к диапазону кодов, зарезервированных для использования в качестве старших байтов. То, какие диапазоны байтов могут быть старшими байтами, зависит от используемой кодовой страницы. Например, японская кодовая страница 932 использует в качестве старших байтов диапазон 0x81–0x9F, но корейская кодовая страница 949 использует другой диапазон.  
  
 Учитывайте следующие аспекты при программировании с использованием MBCS.  
  
 Символы MBCS в среде  
 Символы MBCS могут использоваться в таких строках, как имена файлов и каталогов.  
  
 Операции редактирования  
 Операции редактирования в приложениях с MBCS должны работать с символами, а не байтами. Каретка должна быть неразделенным символом, клавиша со стрелкой вправо должна перемещать указатель на один символ вправо и т. д. **Удалить** должна удалить символ; **Отменить** должна вставлять его повторно.  
  
 Обработка строк  
 В приложении, использующем MBCS, обработка строк вызывает особые проблемы. Символы из одного и двух байтов могут быть перемешаны в одной строке. Поэтому необходимо всегда проверять старшие байты.  
  
 Поддержка библиотеки времени выполнения  
 Библиотеки времени выполнения языка C и MFC поддерживают однобайтовые и многобайтовые кодировки, а также Юникод. Однобайтовые строки обрабатываются с помощью `str` семейства функций времени выполнения, строки многобайтовых Кодировок обрабатываются с помощью соответствующих `_mbs` функции, а строки Юникода обрабатываются с помощью соответствующих *wcs* функции. В реализациях функций-членов классов MFC используются переносимые функции времени выполнения, которые в некоторых обстоятельствах сопоставляются с обычным семейством функций `str`, функциями MBSC или функциями Юникода, как описано в разделе "Переносимость MBSC и Юникода".  
  
 Переносимость MBSC и Юникода  
 С помощью файла заголовка Tchar.h можно создавать приложения, работающие с однобайтовыми, многобайтовыми кодировками и Юникодом из одних источников. В файле Tchar.h определяются макросы с префиксом *_tcs* , которые сопоставляются с `str`, `_mbs`, или *wcs* соответствующие функции. Для использования mbsc определите символ **_MBCS**. Для использования Юникода определите символ **_UNICODE**. По умолчанию **_MBCS** определяется для приложений MFC. Дополнительные сведения см. в разделе [универсальные текстовые сопоставления в файле Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
> [!NOTE]
>  Поведение не определено, если указать одновременно **_UNICODE** и **_MBCS**.  
  
 Файлы заголовков Mbctype.h и Mbstring.h определяют функции и макросы MBCS, которые могут понадобиться в некоторых случаях. Например, `_ismbblead` сообщает, является ли указанный байт в строке старшим.  
  
 Для международной переносимости используйте код программы с [Юникода](../text/support-for-unicode.md) или многобайтовую кодировку (MBCS).  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Использование многобайтовой Кодировки в программе](../text/international-enabling.md)  
  
-   [Использование Юникода и многобайтовых Кодировок в программе](../text/internationalization-strategies.md)  
  
-   [Использование многобайтовой Кодировки для создания многоязыковых программ](../text/mbcs-programming-tips.md)  
  
-   [В разделе о программировании с использованием MBCS](../text/mbcs-programming-tips.md)  
  
-   [Дополнительные сведения об универсальных текстовых сопоставлений для обеспечения переносимости байтовый](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>См. также  
 [Текст и строки](../text/text-and-strings-in-visual-cpp.md)   
 [Поддержка многобайтовой кодировки MBCS в Visual C++](../text/mbcs-support-in-visual-cpp.md)