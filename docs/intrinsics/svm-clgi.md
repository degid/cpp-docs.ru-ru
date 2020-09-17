---
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: 740c76e5dcc8f94b9257272624a6ad3c1f9726c1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219967"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Блок, относящийся только к системам Microsoft**

Очищает глобальный флаг прерывания.

## <a name="syntax"></a>Синтаксис

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>Примечания

Функция `__svm_clgi` эквивалентна инструкции компьютера `CLGI` . Глобальный флаг прерывания определяет, будет ли микропроцессор игнорировать, откладывать или обрабатывать прерывания из-за таких событий, как завершение ввода-вывода, предупреждение о температуре оборудования или исключение отладки.

Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Для получения дополнительных сведений выполните поиск по фразе "ручной том для программиста архитектуры AMD64". Системное программирование "на сайте [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
