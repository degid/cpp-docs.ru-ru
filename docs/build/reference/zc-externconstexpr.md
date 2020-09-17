---
title: /Zc:externConstexpr (включение внешних переменных constexpr)
ms.date: 02/28/2018
f1_keywords:
- /Zc:externConstexpr
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
ms.openlocfilehash: 7546ab6d81137a2abb053cd18f0d5d74913c3b00
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211909"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>`/Zc:externConstexpr`(Включить внешние переменные constexpr)

**`/Zc:externConstexpr`** Параметр компилятора указывает компилятору на соответствие стандарту C++ и разрешать внешнюю компоновку для **`constexpr`** переменных. По умолчанию Visual Studio всегда предоставляет **`constexpr`** переменную внутреннюю компоновку, даже если указано **`extern`** ключевое слово.

## <a name="syntax"></a>Синтаксис

> **`/Zc:externConstexpr`**[**`-`**]

## <a name="remarks"></a>Примечания

**`/Zc:externConstexpr`** Параметр компилятора заставляет компилятор применить внешнюю компоновку к переменным, объявленным с помощью `extern constexpr` . В более ранних версиях Visual Studio и по умолчанию или при **`/Zc:externConstexpr-`** указании Visual Studio применяет внутреннюю компоновку к **`constexpr`** переменным, даже если **`extern`** используется ключевое слово. **`/Zc:externConstexpr`** Параметр доступен начиная с Visual Studio 2017 с обновлением 15,6. и по умолчанию отключен. [`/permissive-`](permissive-standards-conformance.md)Параметр не включается **`/Zc:externConstexpr`** .

Если файл заголовка содержит объявленную переменную `extern constexpr` , он должен быть помечен [`__declspec(selectany)`](../../cpp/selectany.md) для слияния повторяющихся объявлений в один экземпляр в связанном двоичном файле. В противном случае при нарушениях правила с одним определением могут возникнуть ошибки компоновщика, например LNK2005.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Добавьте **`/Zc:externConstexpr`** или **`/Zc:externConstexpr-`** в область **Дополнительные параметры:** панель.

## <a name="see-also"></a>См. также раздел

[`/Zc`Соответствия](zc-conformance.md)<br/>
[`auto`This](../../cpp/auto-keyword.md)
