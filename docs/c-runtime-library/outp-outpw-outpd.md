---
title: ыходной, аутпв, _outp, _outpw, _outpd
description: Описание устаревших и удаленных функций ыходной, аутпв, _outp, _outpw и _outpd библиотеки времени выполнения Microsoft C (CRT).
ms.date: 12/09/2019
api_name:
- _outpd
- _outp
- _outpw
- outp
- outpw
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _outpw
- _outpd
- _outp
- outp
- outpw
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: c66710fe31b5a657a4976bea7f0aa52aac3e3825
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837090"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>ыходной, аутпв, _outp, _outpw, _outpd

Выходные данные, в порте, байт ( `outp` , `_outp` ), слово ( `outpw` , `_outpw` ) или двойное слово ( `_outpd` ).

> [!IMPORTANT]
> Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT.
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```cpp
int _outp(
   unsigned short port,
   int data_byte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short data_word
);
unsigned long _outpd(
   unsigned short port,
   unsigned long data_word
);
```

### <a name="parameters"></a>Параметры

*порту*\
Номер порта.

*data_byte, data_word*\
Выходные значения.

## <a name="return-value"></a>Возвращаемое значение

Функции возвращают выходные данные. Ошибки не возвращаются.

## <a name="remarks"></a>Примечания

Функции `_outp`, `_outpw`и `_outpd` пишут байт, слово и двойное слово, соответственно, на указанный порт вывода. Аргумент *Port* может быть любым целым числом без знака в диапазоне от 0 до 65 535. *data_byte* может быть любым целым числом в диапазоне 0-255. *data_word* может быть любым значением в диапазоне целого числа, короткого целого числа без знака и длинного целого числа без знака соответственно.

Поскольку эти функции записываются непосредственно в порт ввода-вывода, они не могут использоваться в коде Windows пользовательского режима.

Сведения об использовании портов ввода-вывода в операционной системе Windows см. в разделе [последовательная связь](/previous-versions/ff802693(v=msdn.10)).

`outp`Имена и `outpw` являются устаревшими, нерекомендуемыми именами для `_outp` `_outpw` функций и. Дополнительные сведения см. в разделе [имена функций POSIX](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также раздел

[Ввод-вывод в консоль и порт](../c-runtime-library/console-and-port-i-o.md)\
[`inp`, `inpw`, `_inp`, `_inpw`, `_inpd`](../c-runtime-library/inp-inpw-inpd.md)
