---
title: Предупреждение компилятора (уровень 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: d94347df17bac01334cfd85c2bd9f6c8a98b5fc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174600"
---
# <a name="compiler-warning-level-1-c4951"></a>Предупреждение компилятора (уровень 1) C4951

> "*функция*" была изменена после сбора данных профиля, данные профиля функции не используются

Функция была изменена во входном модуле при компоновке с параметром [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), поэтому данные профиля сейчас недопустимы. Входной модуль был повторно скомпилирован после компоновки с параметром **/LTCG:PGINSTRUMENT** и содержит функцию (*функция*) с другим потоком управления по сравнению с тем, что был в модуле во время компоновки с параметром **/LTCG:PGINSTRUMENT** .

Это предупреждение носит информационный характер. Чтобы устранить его, выполните компоновку с параметром **/LTCG:PGINSTRUMENT**, повторите все тестовые запуски и выполните компоновку с параметром **/LTCG:PGOPTIMIZE**.

Вместо этого предупреждения будет ошибка, если использовался параметр **/LTCG:PGOPTIMIZE** .
