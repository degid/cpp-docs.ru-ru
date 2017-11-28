---
title: "Классы и структуры ссылки (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
caps.latest.revision: 42
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 42
---
# Классы и структуры ссылки (C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) поддерживает определяемые пользователем *классы ссылок* и *структуры ссылок*, а также определяемые пользователем *классы значений* и *структуры значений*. Эти структуры данных являются основными контейнерами, с помощью которых [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] поддерживает систему типов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Их содержимое передается в метаданные в соответствии с определенными правилами, что позволяет передавать их между компонентами [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] и приложениями [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], написанными на C\+\+ и других языках.  
  
 Класс ссылки и структура ссылки имеют следующие основные особенности:  
  
-   они должны объявляться в пространстве имен, в области пространства имен, и в этом пространстве имен они могут иметь режим доступа public \(открытый\) или private \(закрытый\). Только открытые типы формируют метаданные; Определения вложенных открытых классов не допускаются, в том числе определения вложенных открытых классов [enum](../cppcx/enums-c-cx.md). Дополнительные сведения см. в разделе [Пространства имен и видимость типов](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
-   Он может содержать в качестве членов [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], включая классы ссылок, классы значений, структуры ссылок, структуры значений и структуры, допускающие значение NULL. Он также может содержать скалярные типы, такие как float64, bool и т. д. Он также может содержать стандартные типы C\+\+, например `std::vector`, или пользовательский класс при условии, что они не являются открытыми. Конструкции [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] могут иметь доступность `public`, `protected`, `internal`, `private` или `protected private`. Все члены `public` или `protected` передаются в метаданные. Стандартные типы C\+\+ должны иметь доступность `private`, `internal` или `protected private`, что не позволит им быть переданным в метаданные.  
  
-   они могут реализовывать один или несколько *классов интерфейсов* или *структур интерфейсов*;  
  
-   они могут наследовать одному базовому классу, а на сами базовые классы налагаются дополнительные ограничения. Наследование в иерархиях открытых классов ссылок имеет больше ограничений, чем наследование закрытых классов ссылок;  
  
-   они не могут объявляться как универсальные. Если они имеют закрытый доступ, они могут быть шаблонами;  
  
-   Их время жизни управляется автоматическим подсчетом ссылок.  
  
## Объявление  
 В следующем фрагменте кода объявляется класс ссылки `Person`. Обратите внимание, что в закрытых членах используется стандартный тип C\+\+ `std::map`, а в открытом интерфейсе используется интерфейс [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IMapView`. Также обратите внимание, что в конце объявлений ссылочных типов используется оператор "^".  
  
 [!code-cpp[cx_classes#03](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#03)]  
  
## Реализация  
 В этом примере кода демонстрируется реализация класса ссылки `Person`.  
  
 [!code-cpp[cx_classes#04](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#04)]  
  
## Использование  
 В следующем примере кода показано, как клиентский код использует класс ссылки `Person`.  
  
 [!code-cpp[cx_classes#05](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#05)]  
  
 Также можно также объявить локальную переменную класса ссылки с помощью семантики стека. Поведение такого объекта аналогично поведению стековой переменной, несмотря на то что память все же выделяется динамически. Важное отличие заключается в том, что нельзя присвоить отслеживаемую ссылку \(%\) переменной, объявленной с использованием семантики стека: таким образом гарантируется, что счетчик ссылок уменьшается до нуля, когда выполняется выход из функции. В этом примере показаны базовый класс ссылки `Uri` и функция, в которой он используется с семантикой стека:  
  
 [!code-cpp[cx_classes#06](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#06)]  
  
## Управление памятью  
 Класс ссылки размещается в динамической памяти с помощью ключевого слова `ref new`.  
  
 [!code-cpp[cx_classes#01](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#01)]  
  
 Оператор дескриптора объекта ^ \(называемый "крышкой"\) по сути является интеллектуальным указателем C\+\+. Память, на которую он указывает, автоматически освобождается, когда последний дескриптор оказывается вне области или ему явно задается значение `nullptr`.  
  
 По определению класс ссылки имеет семантику ссылки. Когда вы присваиваете значение переменной класса ссылки, копируется не сам объект, а его дескриптор. В следующем примере после операции присваивания оба объекта `myClass` и `myClass2` указывают на одно и то же расположение в памяти.  
  
 [!code-cpp[cx_classes#02](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#02)]  
  
 Когда создается экземпляр класса ссылки C\+\+\/CX, его память перед вызовом конструктора инициализируется нулями, поэтому такая инициализация для отдельных членов, включая свойства, не требуется. Если класс C\+\+\/CX является производным от класса библиотеки C\+\+ для среды выполнения Windows \(WRL\), инициализация нулями осуществляется только для области производного класса C\+\+\/CX.  
  
## Члены  
 Класс ссылки может содержать функции\-члены `public`, `protected` и `private`; только члены `public` и `protected` передаются в метаданные. Вложенные классы и классы ссылок разрешены, однако они не могут быть `public`. Открытые поля не допускаются; открытые члены данных должны объявляться как свойства. Закрытые и защищенные внутренние данные\-члены могут быть полями. По умолчанию в классе ссылки доступность всех членов равна `private`.  
  
 Структура ссылки аналогична классу ссылки за тем исключением, что ее члены по умолчанию имеют доступность `public`.  
  
 Класс ссылки или структура ссылки `public` передаются в метаданные, но для использования из других приложений [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] и компонентов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] они должны иметь по крайней мере по одному открытому или защищенному конструктору. Класс ссылки, являющийся открытым и имеющий открытый конструктор, необходимо также объявлять как `sealed`, чтобы предотвратить его дальнейшее изменение через двоичный интерфейс приложений \(ABI\).  
  
 Открытые члены не могут объявляться как константное выражение, потому что система типов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] не поддерживает const. Можно использовать статическое свойство для объявления открытого члена данных с постоянным значением.  
  
 При определении открытого класса или структуры ссылок компилятор применяет необходимые атрибуты к классу и сохраняет эти сведения в файле WinMD приложения. Однако при определении открытого незапечатанного класса необходимо вручную применить атрибут `Windows::Foundation::Metadata::WebHostHidden`, чтобы класс не был видимым для приложений [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], написанных на языке JavaScript.  
  
 Класс ссылки может содержать стандартные типы C\+\+, включая типы `const`, в любых членах `private`, `internal` или `protected private`.  
  
 Открытые классы ссылки, имеющие параметры\-типы, не допускаются. Определяемые пользователем универсальные классы ссылок не допускаются. Класс ссылки с атрибутами private, internal или protected private может быть шаблоном.  
  
## Деструкторы  
 В [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] вызов `delete` в общем деструкторе вызывает деструктор независимо от счетчика ссылок объекта. Это позволяет определить деструктор, который будет выполнять пользовательскую очистку ресурсов, не относящихся к RAII, детерминированным образом. Однако даже в этом случае сам объект не удаляется из памяти. Память для объекта освобождается, только когда число ссылок достигает нуля.  
  
 Если деструктор класса не является общим, он вызывается только в случае, когда число ссылок достигает нуля. При вызове `delete` для объекта, который имеет закрытый деструктор, компилятор выдает предупреждение C4493 о том, что выражение delete не приводит ни каким результатам, поскольку для \<имя\_типа\> не установлен режим доступа public.  
  
 Деструкторы классов ссылок можно объявлять только следующим образом:  
  
-   открытый и виртуальный \(допускается только для запечатанных и незапечатанных типов\);  
  
-   защищенный закрытый и невиртуальный \(допускается только для незапечатанных типов\);  
  
-   закрытый и невиртуальный \(допускается только для запечатанных типов\).  
  
 Никакие другие сочетания режимов доступа, виртуальности и запечатанности не допускаются.  Если деструктор явно не объявлен, компилятор создает открытый виртуальный деструктор, если у базового класса типа или любого из его членов имеется открытый деструктор. В противном случае компилятор создает защищенный закрытый невиртуальный деструктор для незапечатанных типов и закрытый невиртуальный деструктор для запечатанных типов.  
  
 При попытке обращения к членам класса, для которого уже запускался деструктор, поведение будет неопределенным; это наиболее вероятная причина сбоя программы. При вызове `delete t` для типа, у которого нет открытого деструктора, ничего не происходит. При вызове `delete this` для типа или базового класса, не имеющих деструктора `private` или `protected private` в иерархии типов, также ничего не происходит.  
  
 При объявлении открытого деструктора компилятор создает код таким образом, чтобы класс ссылки реализовывал интерфейс `Platform::IDisposable`, а деструктор реализовывал метод `Dispose`.`Platform::IDisposable` является проекцией [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] элемента `Windows::Foundation::IClosable`. Никогда не следует явным образом реализовывать эти интерфейсы.  
  
## Наследование  
 Platform::Object является универсальным базовым классом для всех классов ссылок. Все классы ссылок неявно преобразуются в Platform::Object и могут переопределять [Object::ToString](../cppcx/object-tostring-method-c-cx.md). Однако модель наследования [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] не подразумевается использовать как общую модель наследования; в C\+\+ и CX это означает, что определенный пользователем открытый класс ссылок не может использоваться в качестве базового класса.  
  
 При создании пользовательского элемента управления XAML можно использовать в качестве базового класса `Windows::UI::Xaml::DependencyObject`, если объект участвует в системе свойств зависимостей.  
  
 После определения незапечатанного класса `MyBase`, который наследует классу `DependencyObject`, другие открытые или закрытые классы ссылок в компоненте или приложении могут наследовать этому классу `MyBase`. Наследование в открытых классах ссылок должно использоваться только для поддержки переопределений виртуальных методов, полиморфной идентичности и инкапсуляции.  
  
 Закрытый базовый класс ссылки не требуется для наследования от существующего незапечатанного класса. Если требуется, чтобы иерархия объектов моделировала собственную структуру программы или обеспечивала повторное использование кода, используйте закрытые или внутренние классы ссылок, а лучше стандартные классы C\+\+. Доступ к функциональности закрытой иерархии объектов можно реализовать с помощью оболочки открытого запечатанного класса ссылки.  
  
 Класс ссылки, имеющий открытый или защищенный конструктор, в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] необходимо объявлять как запечатанный. Это ограничение означает, что классы, написанные на других языках, таких как C\# или Visual Basic, не могут наследовать от типов, объявленных в компоненте [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], написанном на [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)].  
  
 Ниже приведены основные правила наследования в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]:  
  
-   классы ссылок могут напрямую наследовать не более чем от одного базового класса, но могут реализовывать любое количество интерфейсов;  
  
-   если у класса имеется открытый конструктор, он должен объявляться как запечатанный, чтобы запретить его дальнейшее наследование;  
  
-   можно создавать открытые незапечатанные базовые классы, которые имеют внутренние или защищенные закрытые конструкторы, при условии что базовый класс является производным \(прямо или косвенно\) от существующего незапечатанного базового класса, такого как `Windows::UI::Xaml::DependencyObject`. Наследование определяемых пользователем классов ссылок между файлами WinMD не поддерживается; однако класс ссылки может наследовать от интерфейса, определенного в другом файле WinMD. Производные классы для определяемого пользователем базового класса ссылки можно создавать только в пределах одного компонента [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] или приложения [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)];  
  
-   для классов ссылок поддерживается только открытое наследование.  
  
     [!code-cpp[cx_classes#08](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#08)]  
  
 В следующем примере показано, как предоставлять доступ к открытому классу ссылки, производному от других классов ссылки в иерархии наследования.  
  
 [!code-cpp[cx_classes#09](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#09)]  
  
## См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Классы и структуры значений](../cppcx/value-classes-and-structs-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)