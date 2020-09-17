---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: 456e84cfba40a4219f44fe1549272621f79d09a2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213246"
---
# <a name="safebuffers"></a>safebuffers

**Блок, относящийся только к системам Microsoft**

Указывает компилятору не вставлять проверки безопасности на переполнение буфера для функции.

## <a name="syntax"></a>Синтаксис

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Примечания

Параметр компилятора **/GS** заставляет компилятор проверить переполнение буфера, вставив проверки безопасности в стек. Типы структур данных, подходящих для проверок безопасности, описаны в параметре [/GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md). Дополнительные сведения об обнаружении переполнения буфера см. [в разделе функции безопасности в компилятором MSVC](https://devblogs.microsoft.com/cppblog/security-features-in-microsoft-visual-c/).

Экспертная проверка кода вручную или внешний анализ могут показать, что функция безопасна с точки зрения переполнения буфера. В этом случае можно отключить проверку безопасности для функции, применив к **`__declspec(safebuffers)`** объявлению функции ключевое слово.

> [!CAUTION]
> Проверки безопасности буфера — это важное средство обеспечения безопасности, которое практически не сказывается производительности. Поэтому отключать их не рекомендуется, кроме тех редких случаев, когда производительность функции исключительно важна, а сама функция заведомо безопасна.

## <a name="inline-functions"></a>Встраиваемые функции

*Основная функция* может использовать ключевое слово [встраивания](inline-functions-cpp.md) для вставки копии *вторичной функции*. Если **`__declspec(safebuffers)`** ключевое слово применяется к функции, Обнаружение переполнения буфера для этой функции подавляется. Однако встраивание влияет на **`__declspec(safebuffers)`** ключевое слово следующим образом.

Предположим, что для обеих функций указан параметр компилятора **/GS** , но основная функция указывает **`__declspec(safebuffers)`** ключевое слово. Структуры данных в дополнительной функции делают ее законным объектом для проверок безопасности, поэтому такие проверки в ней не отключаются. В данном случае:

- Укажите ключевое слово [__forceinline](inline-functions-cpp.md) во вторичной функции, чтобы заставить компилятор подставляемую функцию независимо от оптимизации компилятора.

- Так как вторичная функция подходит для проверок безопасности, проверки безопасности также применяются к основной функции, даже если она указывает **`__declspec(safebuffers)`** ключевое слово.

## <a name="example"></a>Пример

В следующем коде показано, как использовать **`__declspec(safebuffers)`** ключевое слово.

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
