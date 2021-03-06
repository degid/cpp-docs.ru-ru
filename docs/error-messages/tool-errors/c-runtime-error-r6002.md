---
title: Ошибка времени выполнения C R6002
ms.date: 11/04/2016
f1_keywords:
- R6002
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
ms.openlocfilehash: b2e617b6f7841f1aa7e6fd2f6962c0e117fab6c8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197422"
---
# <a name="c-runtime-error-r6002"></a>Ошибка времени выполнения C R6002

поддержка с плавающей запятой не загружена

Необходимая библиотека с плавающей запятой не связана.

> [!NOTE]
> Если при запуске приложения возникло это сообщение об ошибке, работа приложения была завершена из-за внутренней проблемы. Существует несколько возможных причин возникновения этой ошибки, но часто это вызвано дефектом в коде приложения или попыткой запустить приложение, которое не было создано для конкретного процессора компьютера.
>
> Для устранения этой ошибки попробуйте выполнить следующие действия:
>
> - Используйте страницу **приложения и компоненты** или **программы и компоненты** на **панели управления** , чтобы восстановить или переустановить программу.
> - Проверьте **Центр обновления Windows** на **панели управления** для обновлений программного обеспечения.
> - Проверьте наличие обновленной версии приложения. Если проблема не исчезнет, обратитесь к поставщику приложения.

**Сведения для программистов**

Эта ошибка может возникать в приложении, если библиотека с плавающей запятой не связана. Проверьте одну из следующих причин:

- Строка формата для функции `printf_s` или `scanf_s` содержит спецификацию формата с плавающей запятой, а программа не содержит значений или переменных с плавающей запятой. Чтобы устранить эту проблему, используйте аргумент с плавающей запятой в соответствии со спецификацией формата с плавающей запятой или выполните назначение с плавающей запятой в любом месте программы. Это приводит к загрузке поддержки с плавающей запятой.

- Компилятор уменьшает размер программы, загружая поддержку операций с плавающей запятой только при необходимости. Компилятор не может обнаруживать операции с плавающей запятой или спецификации формата с плавающей запятой в строках формата, поэтому не загружает необходимые подпрограммы с плавающей запятой. Чтобы устранить эту проблему, используйте спецификацию формата с плавающей запятой и укажите аргумент с плавающей запятой или выполните назначение с плавающей запятой в любом месте программы. Это приводит к загрузке поддержки с плавающей запятой.

- В программе на разных языках библиотека C была указана до библиотеки FORTRAN при ее связывании. Повторно свяжите и укажите последнюю библиотеку C.
