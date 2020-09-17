---
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 6bd731951b440d3d2597d54c9a52d9f8640a5c5f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219831"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Блок, относящийся только к системам Microsoft**

Задает глобальный флаг прерывания.

## <a name="syntax"></a>Синтаксис

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>Примечания

Функция `__svm_stgi` эквивалентна инструкции компьютера `STGI` . Глобальный флаг прерывания определяет, будет ли микропроцессор игнорировать, откладывать или обрабатывать прерывания из-за таких событий, как завершение ввода-вывода, предупреждение о температуре оборудования или исключение отладки.

Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Для получения дополнительных сведений выполните поиск по фразе "ручной том для программиста архитектуры AMD64". Системное программирование "на сайте [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
