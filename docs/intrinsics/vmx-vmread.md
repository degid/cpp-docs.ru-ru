---
title: __vmx_vmread
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 409835ac29d6f2e839de62291cc5b142166a465c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219432"
---
# <a name="__vmx_vmread"></a>__vmx_vmread

**Блок, относящийся только к системам Microsoft**

Считывает указанное поле из текущей структуры управления виртуальной машины (VMCS) и помещает его в указанное расположение.

## <a name="syntax"></a>Синтаксис

```C
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

### <a name="parameters"></a>Параметры

*Полями*\
окне Поле VMCS для чтения.

*FieldValue*\
окне Указатель на место хранения значения, считанного из поля VMCS, указанного `Field` параметром.

## <a name="return-value"></a>Возвращаемое значение

|Значение|Смысл|
|-----------|-------------|
|0|Операция успешно выполнена.|
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|
|2|Сбой операции без сведений о состоянии.|

## <a name="remarks"></a>Примечания

Функция `__vmx_vmread` эквивалентна инструкции компьютера `VMREAD` . Значением `Field` параметра является индекс поля в кодировке, описанный в документации Intel. Для получения дополнительной информации выполните поиск приложения C из раздела "Техническая спецификация виртуализации Intel для архитектуры IA-32" на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmread`|X64|

**Заголовочный файл** \<> Intrin.h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
