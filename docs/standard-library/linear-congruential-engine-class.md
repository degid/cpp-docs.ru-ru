---
title: Класс linear_congruential_engine
ms.date: 11/04/2016
f1_keywords:
- random/std::linear_congruential_engine
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
ms.openlocfilehash: 8701570787275e853543e723f6461b8ad460f96f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845449"
---
# <a name="linear_congruential_engine-class"></a>Класс linear_congruential_engine

Создает случайную последовательность, используя линейный конгруэнтный алгоритм.

## <a name="syntax"></a>Синтаксис

```cpp
class linear_congruential_engine{
   public:  // types
   typedef UIntType result_type;
   // engine characteristics
   static constexpr result_type multiplier = a;
   static constexpr result_type increment = c;
   static constexpr result_type modulus = m;
   static constexpr result_type min() { return c == 0u  1u: 0u; }
   static constexpr result_type max() { return m - 1u; }
   static constexpr result_type default_seed = 1u;
   // constructors and seeding functions
   explicit linear_congruential_engine(result_type s = default_seed);
   template <class Sseq>
   explicit linear_congruential_engine(Sseq& q);
   void seed(result_type s = default_seed);
   template <class Sseq>
   void seed(Sseq& q);
   // generating functions
   result_type operator()();
   void discard(unsigned long long z);
   };
```

### <a name="parameters"></a>Параметры

*уинттипе*\
Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random>](../standard-library/random.md) .

*Конкретного*\
**Множитель**. **Предварительные условия **: см. раздел "Примечания".

*Ц*\
**Шаг приращения**. **Предварительные условия **: см. раздел "Примечания".

*Пн*\
**Модуль**. **Предварительные условия **: см. раздел "Примечания".

## <a name="members"></a>Элементы

`linear_congruential_engine::linear_congruential_engine`
`linear_congruential_engine::discard`\
`linear_congruential_engine::max`\
`linear_congruential_engine::min`\
`linear_congruential_engine::operator()`\
`linear_congruential_engine::seed`

`default_seed` — это член-константа, определенный как `1u` и используемый как значение по умолчанию для параметра `linear_congruential_engine::seed` и конструктор с одним значением.

Дополнительные сведения о членах подсистемы см [\<random>](../standard-library/random.md) . в разделе.

## <a name="remarks"></a>Примечания

`linear_congruential_engine`Шаблон класса является простейшим механизмом генератора, но не самым быстрым или самым высоким качеством. Улучшением этого механизма является [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Ни один из этих механизмов не обеспечивает такую же скорость и качество результатов, как [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Этот модуль создает значения определяемого пользователем целочисленного типа без знака с помощью отношения повторения ( *period*) `x(i) = (A * x(i-1) + C) mod M` .

Если значение *M* равно нулю, то для операции с этим модульным значением используется `numeric_limits<result_type>::max() + 1` . Последним возвращается состояние механизма или начальное значение, если функция `operator()` не вызывалась.

Если *M* не равен нулю, значения аргументов шаблона *A* и *C* должны быть меньше *M*.

Хотя можно создать генератор на основе этого механизма напрямую, также можно использовать одно из этих предварительно заданных определений типов.

`minstd_rand0`: Минимальный стандартный механизм 1988 (Льюис, Гудман и Миллер, 1969).

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: Обновленный минимальный стандартный механизм `minstd_rand0` (Парк, Миллер и Стокмайер, 1993).

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

Подробные сведения о линейном конгруэнтном алгоритме см. в статье Википедии [Линейный конгруэнтный генератор](https://go.microsoft.com/fwlink/p/?linkid=402446).

## <a name="requirements"></a>Требования

**Заголовок:**\<random>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[\<random>](../standard-library/random.md)
