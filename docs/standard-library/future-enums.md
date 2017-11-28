---
title: "Перечисления &lt;future&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 835abafde46858bd108dfa648a246345bd254eaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltfuturegt-enums"></a>Перечисления &lt;future&gt;
||||  
|-|-|-|  
|[future_errc](#future_errc)|[future_status](#future_status)|[Запуск](#launch)|  
  
##  <a name="future_errc"></a>  Перечисление future_errc  
 Предоставляет символические имена для всех ошибок, о которых сообщает класс [future_error](../standard-library/future-error-class.md).  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="future_status"></a>  Перечисление future_status  
 Предоставляет символические имена по причинам, которые может возвращать привязанная по времени функция wait.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="launch"></a>  Перечисление launch  
 Представляет тип битовой маски, который описывает возможные режимы для функции-шаблона [async](../standard-library/future-functions.md#async).  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>См. также  
 [\<future>](../standard-library/future.md)


