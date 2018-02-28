---
title: "По умолчанию печать | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5001026f1e5fe9e1fed86a49b0565b09ddd6b555
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-default-printing-is-done"></a>Печать по умолчанию
В этой статье объясняется по умолчанию процесс печати в Windows с точки зрения платформы MFC.  
  
 В приложениях MFC класс представления содержит функцию-член с именем `OnDraw` , содержащий весь код отрисовки. `OnDraw`принимает указатель на [CDC](../mfc/reference/cdc-class.md) объект в качестве параметра. Что `CDC` представляет объект контекста устройства для получения изображений, полученных при `OnDraw`. При получении окно отображения документа [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) сообщений, платформа вызывает `OnDraw` и передает его на контекст устройства для экрана ( [CPaintDC](../mfc/reference/cpaintdc-class.md) объекта, чтобы указать точно). Соответственно `OnDraw`выходные файлы остаются на экране.  
  
 В программировании для Windows отправку выходные данные на принтер очень похожа на отправку вывода на экран. Это так, как аппаратно независимых интерфейс графических устройств Windows (GDI). Можно использовать те же функции GDI для отображения на экране или для печати при помощи контекста соответствующего устройства. Если `CDC` объекта, `OnDraw` получает представляет принтер, `OnDraw`выходных переходит на принтер.  
  
 Это объясняет, как приложения MFC можно выполнять простой печать без дополнительных усилий со стороны пользователя. Платформа отвечает за отображение диалогового окна «Печать» и создание на контекст устройства принтера. При выборе команды «Печать» из меню «файл», представление передает этот контекст устройства для `OnDraw`, который рисует документа на принтере.  
  
 Однако существуют значительные различия печати и отображения на экране. При печати, необходимо разделить на отдельные страницы и отображения их, по одному, а не любые отображал отображается в окне документа. Как следствие необходимо иметь в виду размер бумаги (если он является буквой размер, допустимый размер или конверта). Вы можете выполнять печать в разные ориентации, например горизонтальной или вертикальной. Библиотеки классов Microsoft Foundation невозможно предсказать, как приложение будет обрабатывать эти проблемы, поэтому он обеспечивает протокол можно добавить эти возможности.  
  
 Что протокол описан в статье [Многостраничные документы](../mfc/multipage-documents.md).  
  
## <a name="see-also"></a>См. также  
 [Печать](../mfc/printing.md)
