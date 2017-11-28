---
title: "Инициализация скалярных типов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1a580a62c8ee8588386ceb92e10a8593881f6e28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="initializing-scalar-types"></a>Инициализация скалярных типов
При инициализации скалярных типов значение *assignment-expression* присваивается переменной. Применяются правила преобразования для присваивания. (См. сведения о правилах преобразования в статье [Преобразования типов (C)](../c-language/type-conversions-c.md).)  
  
## <a name="syntax"></a>Синтаксис  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt**;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list*  **,**  *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* Для инициализации скалярных переменных \*/  
  
 *initializer*:  
 *assignment-expression*  
  
 Можно инициализировать переменные любого типа при условии соблюдения следующих правил.  
  
-   Переменные, объявленные на уровне области файлов, можно инициализировать. Если явно не инициализировать переменную на внешнем уровне, она инициализируется значением 0 по умолчанию.  
  
-   Константное выражение можно использовать для инициализации любой глобальной переменной, объявленной со статическим **static** описателем класса хранения (*storage-class-specifier*). Переменные, объявленные как **static**, инициализируются после начала исполнения программы. Если явно не инициализировать глобальную переменную, объявленную как **static**, она инициализируется значением 0 по умолчанию, и каждому элементу типа "указатель" присваивается указатель NULL.  
  
-   Переменные, объявленные с описателем класса хранения **auto** или **register**, инициализируются каждый раз при передаче контроля исполнения блоку, в котором они объявлены. Если исключить инициализатор из объявления переменной **auto** или **register**, начальное значение переменной будет неопределенным. Для автоматических значений и значений регистра инициализатор не обязательно должен являться константой; он может быть любым выражением, включая ранее определенные значения (даже вызовами функции).  
  
-   Начальные значения для внешних объявлений переменных и для всех переменных **static** (как внешних, так и внутренних) должны представлять собой константные выражения. (Дополнительные сведения см. в разделе [Постоянные выражения в C](../c-language/c-constant-expressions.md).) Так как адрес объявленной внешне или статической переменной является константным, его можно использовать для инициализации объявленной внутренне переменной указателя **static**. Однако адрес переменной **auto** невозможно использовать как статический инициализатор, так как он может быть разным для каждого исполнения блока. Для инициализации переменных **auto** и **register** можно использовать константные или переменные значения.  
  
-   Если объявление идентификатора имеет область видимости блока и идентификатор имеет внешнюю компоновку, объявление не может иметь инициализацию.  
  
## <a name="examples"></a>Примеры  
 Инициализация иллюстрируется следующими примерами.  
  
```  
int x = 10;   
```  
  
 Целочисленная переменная `x` инициализируется с константным выражением `10`.  
  
```  
register int *px = 0;  
```  
  
 Указатель `px` инициализируется значением 0, создавая указатель null.  
  
```  
const int c = (3 * 1024);  
```  
  
 В этом примере константное выражение `(3 * 1024)` используется для инициализации `c` с константным значением, которое невозможно изменить из-за ключевого слова **const**.  
  
```  
int *b = &x;  
```  
  
 Этот оператор инициализирует указатель `b` адресом другой переменной, `x`.  
  
```  
int *const a = &z;  
```  
  
 Указатель `a` инициализируется с адресом переменной с именем `z`. Но так как он определен как **const**, переменную `a` можно только инициализировать, но не изменить. Она всегда указывает на одно и то же расположение.  
  
```  
int GLOBAL ;  
  
int function( void )  
{  
    int LOCAL ;  
    static int *lp = &LOCAL;   /* Illegal initialization */  
    static int *gp = &GLOBAL;  /* Legal initialization   */  
    register int *rp = &LOCAL; /* Legal initialization   */  
}  
```  
  
 Глобальная переменная `GLOBAL` объявляется на внешнем уровне и поэтому имеет глобальное время существования. Локальная переменная `LOCAL` относится к классу хранения **auto**, и ей присваивается адрес только во время исполнения функции, в которой она объявлена. Поэтому инициализировать **статическую** переменную указателя `lp` с адресом `LOCAL` невозможно. **Статическую** переменную указателя `gp` можно инициализировать с адресом `GLOBAL`, так как этот адрес остается неизменным. Аналогично, `*rp` можно инициализировать, поскольку `rp` — это локальная переменная и может иметь неконстантный инициализатор. Всякий раз при входе в блок `LOCAL` имеет новый адрес, который затем присваивается `rp`.  
  
## <a name="see-also"></a>См. также  
 [Инициализация](../c-language/initialization.md)