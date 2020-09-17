---
title: Класс sequenced_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: 5647f20b560828016231a9bbd38977c51211e6bb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444916"
---
# <a name="sequenced_policy-class"></a>Класс sequenced_policy

Используется в качестве уникального типа для устранения неоднозначности при перегрузке параллельного алгоритма и требует, чтобы выполнение параллельного алгоритма не было параллельным.

## <a name="syntax"></a>Синтаксис

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Примечания

При выполнении параллельного алгоритма с политикой `execution::sequenced_policy`, если вызов функции доступа к элементу завершается с помощью неперехваченного исключения, вызываемый `terminate()` должен быть вызван.
