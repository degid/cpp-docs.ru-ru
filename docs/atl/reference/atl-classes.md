---
title: Классы и структуры ATL | Документация Майкрософт
ms.date: 05/03/2018
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
ms.openlocfilehash: 2bf13700ada3284b8a32718d21971e89e30e5b76
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498053"
---
# <a name="atl-classes-and-structs"></a>Классы и структуры библиотеки ATL

Библиотека активных шаблонов (ATL) включает следующие классы и структуры. Чтобы найти конкретный класс по категории, см. раздел [Общие сведения о классе ATL](../../atl/atl-class-overview.md).

|Класс или структура|Описание|Заголовочный файл|
|-----------|-----------------|-----------------|
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|Содержит сведения, используемые для подготовки к просмотру различных целевых объектов, таких как принтер, метафайл или элемент управления ActiveX.|атлктл.h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|Содержит данные экземпляра класса в коде окна в ATL.|atlbase.h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|Используется любым проектом, использующим ATL.|atlbase.h|
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|Используется кодом, связанным с COM, в ATL.| atlbase.h|
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|Содержит сведения о типе, используемые для описания метода или свойства в DISP-интерфейсе.|атлком.h|
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|Содержит данные, используемые каждым модулем ATL.|atlbase.h|
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|Используется в коде окон в ATL.|atlbase.h|
|[CA2AEX](../../atl/reference/ca2aex-class.md)|Этот класс используется макросами преобразования строк CA2TEX и CT2AEX, а также typedef CA2A.|атлконв.h|
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|Этот класс используется макросами преобразования строк CA2CTEX и CT2CAEX, а также typedef CA2CA.|атлконв.h|
|[CA2WEX](../../atl/reference/ca2wex-class.md)|Этот класс используется макросами преобразования строк CA2TEX, CA2CTEX, CT2WEX и CT2CWEX и typedef CA2W.|атлконв.h|
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|Этот класс является оболочкой для маркера доступа.|атлсекурити.h|
|[какл](../../atl/reference/cacl-class.md)|Этот класс является оберткой для структуры ACL (списка управления доступом).|атлсекурити.h|
|[кадапт](../../atl/reference/cadapt-class.md)|Этот шаблон используется для создания оболочек классов, переопределяющих оператор взятия адреса, чтобы он возвращал нечто, отличное от адреса объекта.|atlcomcli.h|
|[CAtlArray](../../atl/reference/catlarray-class.md)|Этот класс реализует объект Array.|атлколл.h|
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|Этот класс реализует COM-сервер модели подразделения в пуле потоков.|atlbase.h|
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|Этот класс предоставляет методы для реализации COM-сервера с контейнерами в пуле потоков.|atlbase.h|
|[катлбасемодуле](../../atl/reference/catlbasemodule-class.md)|Этот класс создается в каждом проекте ATL.|атлкоре.h|
|[катлкоммодуле](../../atl/reference/catlcommodule-class.md)|Этот класс реализует модуль COM-сервера.|atlbase.h|
|[катлдебугинтерфацесмодуле](../../atl/reference/catldebuginterfacesmodule-class.md)|Этот класс обеспечивает поддержку для интерфейсов отладки.|atlbase.h|
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|Этот класс представляет модуль для библиотеки DLL.|atlbase.h|
|[катлексцептион](../../atl/reference/catlexception-class.md)|Этот класс определяет исключение ATL.|атлексцепт.h|
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|Этот класс представляет модуль для приложения.|atlbase.h|
|[катлфиле](../../atl/reference/catlfile-class.md)|Этот класс предоставляет тонкую оболочку для API-интерфейса обработки файлов Windows.|атлфиле.h|
|[катлфилемаппинг](../../atl/reference/catlfilemapping-class.md)|Этот класс представляет размещенный в памяти файл, добавляя оператор приведения к методам [катлфилемаппингбасе](../../atl/reference/catlfilemappingbase-class.md).|атлфиле.h|
|[катлфилемаппингбасе](../../atl/reference/catlfilemappingbase-class.md)|Этот класс представляет размещенный в памяти файл.|атлфиле.h|
|[катллист](../../atl/reference/catllist-class.md)|Этот класс предоставляет методы для создания объекта списка и управления им.|атлколл.h|
|[CAtlMap](../../atl/reference/catlmap-class.md)|Этот класс предоставляет методы для создания объекта Map и управления им.|атлколл.h|
|[катлмодуле](../../atl/reference/catlmodule-class.md)|Этот класс предоставляет методы, используемые несколькими классами модуля ATL.|atlbase.h|
|[катлмодулет](../../atl/reference/catlmodulet-class.md)|Этот класс реализует модуль ATL.|atlbase.h|
|[катлпревиевктрлимпл](../../atl/reference/catlpreviewctrlimpl-class.md)|Этот класс является реализацией библиотеки ATL окна, размещенной в главном окне, предоставляемом оболочкой для расширенного просмотра.|атлпревиевктрлимпл.h|
|[Функция CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|Этот класс реализует службу.|atlbase.h|
|[катлтемпорарифиле](../../atl/reference/catltemporaryfile-class.md)|Этот класс предоставляет методы для создания и использования временного файла.|атлфиле.h|
|[катлтрансактионманажер](../../atl/reference/catltransactionmanager-class.md)|Этот класс предоставляет оболочку для функций диспетчера транзакций ядра (KTM).|атлтрансактионманажер.h|
|[катлвинмодуле](../../atl/reference/catlwinmodule-class.md)|Этот класс обеспечивает поддержку для компонентов окна ATL.|atlbase.h|
|[каутоптр](../../atl/reference/cautoptr-class.md)|Этот класс представляет объект интеллектуального указателя.|atlbase.h|
|[каутоптраррай](../../atl/reference/cautoptrarray-class.md)|Этот класс предоставляет методы, полезные при построении массива смарт-указателей.|atlbase.h|
|[каутоптрелементтраитс](../../atl/reference/cautoptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов, полезные при создании коллекций смарт-указателей.|атлколл.h|
|[каутоптрлист](../../atl/reference/cautoptrlist-class.md)|Этот класс предоставляет методы, полезные при создании списка смарт-указателей.|атлколл.h|
|[каутовекторптр](../../atl/reference/cautovectorptr-class.md)|Этот класс представляет объект интеллектуального указателя, используя операторы создания и удаления Vector.|atlbase.h|
|[каутовекторптрелементтраитс](../../atl/reference/cautovectorptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов, полезные при создании коллекций смарт-указателей с помощью операторов Vector New и DELETE.|атлколл.h|
|[каксдиалогимпл](../../atl/reference/caxdialogimpl-class.md)|Этот класс реализует диалоговое окно (модальное или немодальное), в котором размещены элементы управления ActiveX.|atlwin.h|
|[каксвиндов](../../atl/reference/caxwindow-class.md)|Этот класс предоставляет методы для управления окном, в котором размещается элемент ActiveX.|atlwin.h|
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|Этот класс предоставляет методы для управления окном, в котором размещается элемент управления ActiveX, а также поддерживает размещение лицензированных элементов управления ActiveX.|atlwin.h|
|[кбиндстатускаллбакк](../../atl/reference/cbindstatuscallback-class.md)|Этот класс реализует интерфейс `IBindStatusCallback` .|атлктл.h|
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|Этот класс реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного объекта.|атлком.h|
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|Этот класс предоставляет методы для управления памятью с помощью подпрограмм COM-памяти.|atlbase.h|
|[ккомапартмент](../../atl/reference/ccomapartment-class.md)|Этот класс обеспечивает поддержку управления апартаментом в модуле EXE в пуле потоков.|atlbase.h|
|[ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md)|Этот класс предоставляет методы для получения и освобождения владения объектом критической секции.|атлкоре.h|
|[ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md)|Начиная с ATL 7,0, `CComAutoThreadModule` является устаревшим: Дополнительные сведения см. в разделе [модули ATL](../../atl/atl-module-classes.md) .|atlbase.h|
|[CComBSTR](../../atl/reference/ccombstr-class.md)|Этот класс является оболочкой для BSTRs.|atlbase.h|
|[ккомкачедтеароффобжект](../../atl/reference/ccomcachedtearoffobject-class.md)|Этот класс реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для интерфейса разрыва.|атлком.h|
|[ккомклассфактори](../../atl/reference/ccomclassfactory-class.md)|Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) .|атлком.h|
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|Этот класс реализует интерфейс [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) .|атлком.h|
|[ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md)|Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) и позволяет создавать объекты в нескольких подразделениях.|атлком.h|
|[ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md)|Этот класс является производным от [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md) и использует [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) для создания одного объекта.|атлком.h|
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|Этот класс предоставляет методы для создания экземпляров класса и получения его свойств.|атлком.h|
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|Этот класс предоставляет методы, необходимые для реализации составного элемента управления.|атлктл.h|
|[ккомконтаинедобжект](../../atl/reference/ccomcontainedobject-class.md)|Этот класс реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , делегируя его объекту `IUnknown`Owner.|атлком.h|
|[ккомконтрол](../../atl/reference/ccomcontrol-class.md)|Этот класс предоставляет методы для создания элементов управления ATL и управления ими.|атлктл.h|
|[ккомконтролбасе](../../atl/reference/ccomcontrolbase-class.md)|Этот класс предоставляет методы для создания элементов управления ATL и управления ими.|атлктл.h|
|[ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)|Этот класс предоставляет методы для получения и освобождения владения объектом критической секции.|атлкоре.h|
|[ккомкритсеклокк](../../atl/reference/ccomcritseclock-class.md)|Этот класс предоставляет методы для блокировки и разблокировки объекта критической секции.|atlbase.h|
|[ккомкурренци](../../atl/reference/ccomcurrency-class.md)|Этот класс содержит методы и операторы для создания объекта CURRENCY и управления им.|атлкур.h|
|[ккомдинамикункаррай](../../atl/reference/ccomdynamicunkarray-class.md)|Этот класс хранит массив `IUnknown` указателей.|атлком.h|
|[ккоменум](../../atl/reference/ccomenum-class.md)|Этот класс определяет объект перечислителя COM, основанный на массиве.|атлком.h|
|[ккоменумимпл](../../atl/reference/ccomenumimpl-class.md)|Этот класс предоставляет реализацию для интерфейса перечислителя COM, в котором перечисляемые элементы хранятся в массиве.|атлком.h|
|[ккоменумонстл](../../atl/reference/ccomenumonstl-class.md)|Этот класс определяет объект перечислителя COM на основе коллекции C++ стандартной библиотеки.|атлком.h|
|[ккомфакекритикалсектион](../../atl/reference/ccomfakecriticalsection-class.md)|Этот класс предоставляет те же методы, что и [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критическую секцию.|атлкоре.h|
|[ккомгитптр](../../atl/reference/ccomgitptr-class.md)|Этот класс предоставляет методы для работы с указателями интерфейса и глобальной таблицей интерфейса (GIT).|atlbase.h|
|[CComHeap](../../atl/reference/ccomheap-class.md)|Этот класс реализует [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения памяти com.|Атлкоммем.h|
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|Класс интеллектуального указателя для управления указателями кучи.|atlbase.h|
|[CComModule](../../atl/reference/ccommodule-class.md)|Начиная с ATL 7,0, `CComModule` является устаревшим: Дополнительные сведения см. в разделе [модули ATL](../../atl/atl-module-classes.md) .|atlbase.h|
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|Этот класс предоставляет потокобезопасные методы для увеличения и уменьшения значения переменной.|atlbase.h|
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|Этот класс предоставляет потокобезопасные методы для увеличения и уменьшения значения переменной без блокировки критической секции или разблокировки.|atlbase.h|
|[CComObject](../../atl/reference/ccomobject-class.md)|Этот класс реализует `IUnknown` для неагрегированного объекта.|атлком.h|
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|Этот класс управляет счетчиком ссылок для модуля, содержащего ваш `Base` объект.|атлком.h|
|[ккомобжектнолокк](../../atl/reference/ccomobjectnolock-class.md)|Этот класс реализует `IUnknown` для неагрегированного объекта, но не увеличивает счетчик блокировок модуля в конструкторе.|атлком.h|
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|Это определение типа [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) преобразованный в потоковой модели сервера по умолчанию.|атлком.h|
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|Этот класс предоставляет методы для обработки управления счетчиком ссылок на объекты как для неагрегированных, так и для агрегированных объектов.|атлком.h|
|[ккомобжектстакк](../../atl/reference/ccomobjectstack-class.md)|Этот класс создает временный COM-объект и предоставляет его с реализацией `IUnknown`скелетообразных.|атлком.h|
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|Этот класс реализует `IUnknown` для агрегированного или неагрегированного объекта.|атлком.h|
|[CComPtr](../../atl/reference/ccomptr-class.md)|Класс интеллектуального указателя для управления указателями на интерфейс COM.|atlcomcli.h|
|[ккомптрбасе](../../atl/reference/ccomptrbase-class.md)|Этот класс предоставляет базу для классов интеллектуальных указателей, использующих подпрограммы памяти на основе COM.|atlcomcli.h|
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|Класс интеллектуального указателя для управления указателями на интерфейс COM.|atlcomcli.h|
|[ккомкиптрелементтраитс](../../atl/reference/ccomqiptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов, полезные при создании коллекций указателей на COM-интерфейсах.|атлколл.h|
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|Этот класс является оболочкой для `SAFEARRAY Data Type` структуры.|атлсафе.h|
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|Этот класс является оболочкой для `SAFEARRAYBOUND` структуры.|атлсафе.h|
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|Этот класс управляет выбором потоков для класса [ккомаутосреадмодуле](../../atl/reference/ccomautothreadmodule-class.md).|atlbase.h|
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|Этот класс предоставляет методы для увеличения и уменьшения значения переменной.|atlbase.h|
|[ккомтеароффобжект](../../atl/reference/ccomtearoffobject-class.md)|Этот класс реализует интерфейс разрыва.|атлком.h|
|[ккомункаррай](../../atl/reference/ccomunkarray-class.md)|Этот класс хранит `IUnknown` указатели и предназначен для использования в качестве параметра для класса шаблона [иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md) .|атлком.h|
|[CComVariant](../../atl/reference/ccomvariant-class.md)|Этот класс служит оболочкой для типа VARIANT, предоставляя член, указывающий тип хранимых данных.|atlcomcli.h|
|[кконтаинедвиндовт](../../atl/reference/ccontainedwindowt-class.md)|Этот класс реализует окно, содержащееся в другом объекте.|atlwin.h|
|[ккрталлокатор](../../atl/reference/ccrtallocator-class.md)|Этот класс предоставляет методы для управления памятью с помощью подпрограмм памяти CRT.|атлкоре.h|
|[ккрсеап](../../atl/reference/ccrtheap-class.md)|Этот класс реализует [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md) с помощью функций кучи CRT.|атлмем.h|
|[CDacl](../../atl/reference/cdacl-class.md)|Этот класс является оболочкой для структуры DACL (список управления доступом на уровне пользователей).|атлсекурити.h|
|[Класс CDebugReportHook](../../atl/reference/cdebugreporthook-class.md)|Этот класс используется для отправки отладочных отчетов в именованный канал.|файлов atlutil.h|
|[кдефаултчартраитс](../../atl/reference/cdefaultchartraits-class.md)|Этот класс предоставляет две статические функции для преобразования символов между прописными и строчными буквами.|атлколл.h|
|[кдефаулткомпаретраитс](../../atl/reference/cdefaultcomparetraits-class.md)|Этот класс предоставляет функции сравнения элементов по умолчанию.|атлколл.h|
|[кдефаултелементтраитс](../../atl/reference/cdefaultelementtraits-class.md)|Этот класс предоставляет методы и функции по умолчанию для класса коллекции.|атлколл.h|
|[кдефаулсаштраитс](../../atl/reference/cdefaulthashtraits-class.md)|Этот класс предоставляет статическую функцию для вычисления хэш-значений.|атлколл.h|
|[CDialogImpl](../../atl/reference/cdialogimpl-class.md)|Этот класс предоставляет методы для создания модального или немодального диалогового окна.|atlwin.h|
|[кдинамикчаин](../../atl/reference/cdynamicchain-class.md)|Этот класс предоставляет методы, поддерживающие динамическую цепочку сопоставлений сообщений.|atlwin.h|
|[целементтраитс](../../atl/reference/celementtraits-class.md)|Этот класс используется классами коллекций для предоставления методов и функций для операций перемещения, копирования, сравнения и хэширования.|атлколл.h|
|[целементтраитсбасе](../../atl/reference/celementtraitsbase-class.md)|Этот класс предоставляет методы копирования и перемещения по умолчанию для класса коллекции.|атлколл.h|
|[кфирепропнотифевент](../../atl/reference/cfirepropnotifyevent-class.md)|Этот класс предоставляет методы для уведомления приемника контейнера об изменениях свойств элемента управления.|атлктл.h|
|[CCRTHeap](../../atl/reference/cglobalheap-class.md)|Этот класс реализует [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md) с помощью глобальных функций кучи Win32.|атлмем.h|
|[чандле](../../atl/reference/chandle-class.md)|Этот класс предоставляет методы для создания и использования объекта Handle.|atlbase.h|
|[чеапптр](../../atl/reference/cheapptr-class.md)|Класс интеллектуального указателя для управления указателями кучи.|атлкоре.h|
|[чеапптрбасе](../../atl/reference/cheapptrbase-class.md)|Этот класс образует базу для нескольких классов указателей смарт-кучи.|атлкоре.h|
|[Класс CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов, которые полезны при создании коллекций указателей кучи.|атлколл.h|
|[чеапптрлист](../../atl/reference/cheapptrlist-class.md)|Этот класс предоставляет методы, полезные при построении списка указателей на кучу.|атлколл.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Обеспечивает улучшенную поддержку точечных рисунков, включая возможность загрузки и сохранения изображений в форматах JPEG, GIF, BMP и PNG.|атлимаже.h|
|[Цинтерфацеаррай](../../atl/reference/cinterfacearray-class.md)|Этот класс предоставляет методы, полезные при построении массива указателей на COM-интерфейс.|атлколл.h|
|[Цинтерфацелист](../../atl/reference/cinterfacelist-class.md)|Этот класс предоставляет методы, полезные при создании списка указателей на COM-интерфейс.|атлколл.h|
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|Этот класс реализует [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md) с помощью функций локальной кучи Win32.|атлмем.h|
|[кмессажемап](../../atl/reference/cmessagemap-class.md)|Этот класс разрешает доступ к сопоставлению сообщений объекта другим объектом.|atlwin.h|
|[Класс CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их в рабочий объект, который создается и уничтожается при каждом запросе.|файлов atlutil.h|
|[Класс CNoWorkerThread](../../atl/reference/cnoworkerthread-class.md)|Используйте этот класс в качестве аргумента для `MonitorClass` классов кэша параметра шаблона, если требуется отключить динамическое обслуживание кэша.|файлов atlutil.h|
|[Класс CPathT](../../atl/reference/cpatht-class.md)|Этот класс представляет путь.|atlpath.h|
|[кпримитивилементтраитс](../../atl/reference/cprimitiveelementtraits-class.md)|Этот класс предоставляет методы и функции по умолчанию для класса коллекции, состоящего из примитивных типов данных.|атлколл.h|
|[кприватеобжектсекуритидеск](../../atl/reference/cprivateobjectsecuritydesc-class.md)|Этот класс представляет объект дескриптора безопасности закрытого объекта.|атлсекурити.h|
|[крбмап](../../atl/reference/crbmap-class.md)|Этот класс представляет структуру сопоставления с помощью двоичного дерева из красного черного.|атлколл.h|
|[крбмултимап](../../atl/reference/crbmultimap-class.md)|Этот класс представляет структуру сопоставления, которая позволяет связать каждый ключ с более чем одним значением с помощью двоичного дерева из красного черного.|атлколл.h|
|[крбтри](../../atl/reference/crbtree-class.md)|Этот класс предоставляет методы для создания и использования дерева с красным и черным цветами.|атлколл.h|
|[Сбой CRegKey](../../atl/reference/cregkey-class.md)|Этот класс предоставляет методы для управления записями в системном реестре.|atlbase.h|
|[кртсреадтраитс](../../atl/reference/crtthreadtraits-class.md)|Этот класс предоставляет функцию создания для потока CRT. Используйте этот класс, если поток будет использовать функции CRT.|atlbase.h|
|[ксакл](../../atl/reference/csacl-class.md)|Этот класс является оболочкой для структуры SACL (системный доступ к списку управления).|атлсекурити.h|
|[ксекуритяттрибутес](../../atl/reference/csecurityattributes-class.md)|Этот класс является тонкой оболочкой для `SECURITY_ATTRIBUTES` структуры.|атлсекурити.h|
|[ксекуритидеск](../../atl/reference/csecuritydesc-class.md)|Этот класс является оболочкой для `SECURITY_DESCRIPTOR` структуры.|атлсекурити.h|
|[CSid](../../atl/reference/csid-class.md)|Этот класс является оболочкой для `SID` структуры идентификатора безопасности.|атлсекурити.h|
|[ксимплеаррай](../../atl/reference/csimplearray-class.md)|Этот класс предоставляет методы для управления простым массивом.|атлсимпколл.h|
|[ксимплеаррайекуалхелпер](../../atl/reference/csimplearrayequalhelper-class.md)|Этот класс является вспомогательным классом для класса [ксимплеаррай](../../atl/reference/csimplearray-class.md) .|атлсимпколл.h|
|[ксимплеаррайекуалхелперфалсе](../../atl/reference/csimplearrayequalhelperfalse-class.md)|Этот класс является вспомогательным классом для класса [ксимплеаррай](../../atl/reference/csimplearray-class.md) .|атлсимпколл.h|
|[ксимпледиалог](../../atl/reference/csimpledialog-class.md)|Этот класс реализует базовое модальное диалоговое окно.|atlwin.h|
|[ксимплемап](../../atl/reference/csimplemap-class.md)|Этот класс обеспечивает поддержку простого массива сопоставления.|атлсимпколл.h|
|[ксимплемапекуалхелпер](../../atl/reference/csimplemapequalhelper-class.md)|Этот класс является вспомогательным классом для класса [ксимплемап](../../atl/reference/csimplemap-class.md) .|атлсимпколл.h|
|[ксимплемапекуалхелперфалсе](../../atl/reference/csimplemapequalhelperfalse-class.md)|Этот класс является вспомогательным классом для класса [ксимплемап](../../atl/reference/csimplemap-class.md) .|атлсимпколл.h|
|[кснапинитемимпл](../../atl/reference/csnapinitemimpl-class.md)|Этот класс предоставляет методы для реализации объекта узла оснастки.|атлснап.h|
|[кснапинпропертипажеимпл](../../atl/reference/csnapinpropertypageimpl-class.md)|Этот класс предоставляет методы для реализации объекта страницы свойств оснастки.|атлснап.h|
|[кстоккпропимпл](../../atl/reference/cstockpropimpl-class.md)|Этот класс предоставляет методы для поддержки значений стандартных свойств.|атлктл.h|
|[кстринжелементтраитс](../../atl/reference/cstringelementtraits-class.md)|Этот класс предоставляет статические функции, используемые классами `CString` коллекций, в которых хранятся объекты.|CStringT.h|
|[кстринжелементтраитси](../../atl/reference/cstringelementtraitsi-class.md)|Этот класс предоставляет статические функции, связанные со строками, хранящимися в объектах класса коллекции. Он аналогичен [кстринжелементтраитс](../../atl/reference/cstringelementtraits-class.md), но выполняет сравнения без учета регистра.|атлколл.h|
|[кстрингрефелементтраитс](../../atl/reference/cstringrefelementtraits-class.md)|Этот класс предоставляет статические функции, связанные со строками, хранящимися в объектах класса коллекции. Строковые объекты обрабатываются как ссылки.|атлколл.h|
|[Класс CThreadPool](../../atl/reference/cthreadpool-class.md)|Этот класс предоставляет пул рабочих потоков, которые обрабатывают очередь рабочих элементов.|файлов atlutil.h|
|[ктокенграупс](../../atl/reference/ctokengroups-class.md)|Этот класс является оболочкой для `TOKEN_GROUPS` структуры.|атлсекурити.h|
|[ктокенпривилежес](../../atl/reference/ctokenprivileges-class.md)|Этот класс является оболочкой для `TOKEN_PRIVILEGES` структуры.|атлсекурити.h|
|[Класс CUrl](../../atl/reference/curl-class.md)|Этот класс представляет URL-адрес. Он позволяет управлять каждым элементом URL-адреса независимо от того, выполняется ли синтаксический анализ существующей строки URL-адреса или создание строки с нуля.|файлов atlutil.h|
|[CW2AEX](../../atl/reference/cw2aex-class.md)|Этот класс используется макросами преобразования строк CT2AEX, CW2TEX, CW2CTEX и CT2CAEX и typedef CW2A.|атлконв.h|
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|Этот класс используется макросами преобразования строк CW2CTEX и CT2CWEX, а также typedef CW2CW.|атлконв.h|
|[CW2WEX](../../atl/reference/cw2wex-class.md)|Этот класс используется макросами преобразования строк CW2TEX и CT2WEX, а также typedef CW2W.|атлконв.h|
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|Этот класс реализует [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.|атлмем.h|
|[CWindow](../../atl/reference/cwindow-class.md)|Этот класс предоставляет методы для управления окном.|atlwin.h|
|[квиндовимпл](../../atl/reference/cwindowimpl-class.md)|Этот класс предоставляет методы для создания или подкласса окна.|atlwin.h|
|[квинтраитс](../../atl/reference/cwintraits-class.md)|Этот класс предоставляет метод для стандартизации стилей, используемых при создании объекта Window.|atlwin.h|
|[квинтраитсор](../../atl/reference/cwintraitsor-class.md)|Этот класс предоставляет метод для стандартизации стилей, используемых при создании объекта Window.|atlwin.h|
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|Этот класс предоставляет методы для регистрации сведений для класса окна.|atlwin.h|
|[Класс CWorkerThread](../../atl/reference/cworkerthread-class.md)|Этот класс создает рабочий поток или использует существующий, ожидает один или несколько дескрипторов объектов ядра и выполняет указанную клиентскую функцию, когда один из дескрипторов получает сигнал.|файлов atlutil.h|
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|Этот класс представляет интерфейс для `CreateInstance` метода.|atlbase.h|
|[иатлмеммгр](../../atl/reference/iatlmemmgr-class.md)|Этот класс представляет интерфейс для диспетчера памяти.|атлмем.h|
|[иаксвинамбиентдиспатч](../../atl/reference/iaxwinambientdispatch-interface.md)|Этот интерфейс предоставляет методы для указания характеристик размещенного элемента управления или контейнера.|atlbase.h, описана.h|
|[иаксвинамбиентдиспатчекс](../../atl/reference/iaxwinambientdispatchex-interface.md)|Этот интерфейс реализует дополнительные свойства окружения для размещенного элемента управления.|atlbase.h, описана.h|
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|Этот интерфейс предоставляет методы для манипулирования элементом управления и его ведущим объектом.|atlbase.h, описана.h|
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|Этот интерфейс предоставляет методы для манипулирования лицензированным элементом управления и его ведущим объектом.|atlbase.h, описана.h|
|[иколлектиононстлимпл](../../atl/reference/icollectiononstlimpl-class.md)|Этот класс предоставляет методы, используемые классом коллекции.|атлком.h|
|[иконнектионпоинтконтаинеримпл](../../atl/reference/iconnectionpointcontainerimpl-class.md)|Этот класс реализует контейнер точек соединения для управления коллекцией объектов [иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md) .|атлком.h|
|[иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md)|Этот класс реализует точку соединения.|атлком.h|
|[идатаобжектимпл](../../atl/reference/idataobjectimpl-class.md)|Этот класс предоставляет методы для поддержки универсальных Передача данных и управления соединениями.|атлктл.h|
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|Этот класс предоставляет реализацию по умолчанию для `IDispatch` части сдвоенного интерфейса.|атлком.h|
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|Этот класс предоставляет реализации `IDispatch` методов.|атлком.h|
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|Этот класс предоставляет реализации `IDispatch` методов без получения сведений о типе из библиотеки типов.|атлком.h|
|[идочостуихандлердиспатч](../../atl/reference/idochostuihandlerdispatch-interface.md)|Интерфейс для механизма анализа и подготовки отчетов в формате HTML (Майкрософт).|atlbase.h, описана.h|
|[иенумонстлимпл](../../atl/reference/ienumonstlimpl-class.md)|Этот класс определяет интерфейс перечислителя на основе коллекции C++ стандартной библиотеки.|атлком.h|
|[иобжектсафетимпл](../../atl/reference/iobjectsafetyimpl-class.md)|Этот класс предоставляет реализацию `IObjectSafety` интерфейса по умолчанию, позволяющую клиенту получать и устанавливать уровни безопасности объекта.|атлктл.h|
|[иобжектвисситеимпл](../../atl/reference/iobjectwithsiteimpl-class.md)|Этот класс предоставляет методы, позволяющие объекту взаимодействовать с его сайтом.|атлком.h|
|[иолеконтролимпл](../../atl/reference/iolecontrolimpl-class.md)|Этот класс предоставляет реализацию `IOleControl` интерфейса по умолчанию и реализует. `IUnknown`|атлктл.h|
|[иолеинплацеактивеобжектимпл](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|Этот класс предоставляет методы для облегчения взаимодействия между элементом управления на месте и его контейнером.|атлктл.h|
|[иолеинплацеобжектвиндовлессимпл](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|Этот класс реализует `IUnknown` и предоставляет методы, позволяющие безоконному управлению принимать сообщения окон и принимать участие в операциях перетаскивания.|атлктл.h|
|[иолеобжектимпл](../../atl/reference/ioleobjectimpl-class.md)|Этот класс реализует `IUnknown` и является основным интерфейсом, через который контейнер взаимодействует с элементом управления.|атлктл.h|
|[иперпропертибровсингимпл](../../atl/reference/iperpropertybrowsingimpl-class.md)|Этот класс реализует `IUnknown` и позволяет клиенту обращаться к данным на страницах свойств объекта.|атлктл.h|
|[иперсистпропертибагимпл](../../atl/reference/ipersistpropertybagimpl-class.md)|Этот класс реализует `IUnknown` и позволяет объекту сохранять свои свойства в контейнере свойств, предоставляемом клиентом.|атлком.h|
|[иперсистсторажеимпл](../../atl/reference/ipersiststorageimpl-class.md)|Этот класс реализует интерфейс [иперсистстораже](/windows/win32/api/objidl/nn-objidl-ipersiststorage) .|атлком.h|
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|Этот класс реализует `IUnknown` интерфейс [иперсистстреаминит](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) и предоставляет реализацию по умолчанию.|атлком.h|
|[ипоинтеринактивеимпл](../../atl/reference/ipointerinactiveimpl-class.md)|Этот класс реализует `IUnknown` методы интерфейса [интерфейс IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) и.|атлктл.h|
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|Этот класс предоставляет интерфейс [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) в качестве исходящего интерфейса для подключаемого объекта.|атлктл.h|
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|Этот класс реализует `IUnknown` и наследует реализацию [ипропертипажеимпл](../../atl/reference/ipropertypageimpl-class.md)по умолчанию.|атлктл.h|
|[ипропертипажеимпл](../../atl/reference/ipropertypageimpl-class.md)|Этот класс реализует `IUnknown` интерфейс [ипропертипаже](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) и предоставляет реализацию по умолчанию.|атлктл.h|
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|Этот класс предоставляет реализацию методов [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) и [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) по умолчанию.|атлком.h|
|[икуиккактиватеимпл](../../atl/reference/iquickactivateimpl-class.md)|Этот класс сочетает инициализацию элементов управления контейнера с одним вызовом.|атлктл.h|
|[ируннаблеобжектимпл](../../atl/reference/irunnableobjectimpl-class.md)|Этот класс реализует `IUnknown` интерфейс [ируннаблеобжект](/windows/win32/api/objidl/nn-objidl-irunnableobject) и предоставляет реализацию по умолчанию.|атлктл.h|
|[исервицепровидеримпл](../../atl/reference/iserviceproviderimpl-class.md)|Этот класс предоставляет реализацию `IServiceProvider` интерфейса по умолчанию.|атлком.h|
|[испеЦифипропертипажесимпл](../../atl/reference/ispecifypropertypagesimpl-class.md)|Этот класс реализует `IUnknown` интерфейс [испеЦифипропертипажес](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) и предоставляет реализацию по умолчанию.|атлком.h|
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|Этот класс предоставляет реализацию `ISupportErrorInfo Interface` интерфейса по умолчанию и может использоваться, когда только один интерфейс создает ошибки для объекта.|атлком.h|
|[Интерфейс IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)|Этот интерфейс предоставляет методы для настройки пула потоков.|файлов atlutil.h|
|[ивиевобжектексимпл](../../atl/reference/iviewobjecteximpl-class.md)|Этот класс реализует `IUnknown` и предоставляет реализации по умолчанию интерфейсов [ивиевобжект](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)и [ивиевобжектекс](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) .|атлктл.h|
|[Интерфейс IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient`— Это интерфейс, реализуемый клиентами класса [кворкерсреад](../../atl/reference/cworkerthread-class.md) .|файлов atlutil.h|
|[_U_MENUorID](../../atl/reference/u-menuorid-class.md)|Этот класс предоставляет оболочки для `CreateWindow` и. `CreateWindowEx`|atlwin.h|
|[_U_RECT](../../atl/reference/u-rect-class.md)|Этот класс адаптера Argument позволяет `RECT` передавать указатели или ссылки в функцию, которая реализуется в терминах указателей.|atlwin.h|
|[_U_STRINGorID](../../atl/reference/u-stringorid-class.md)|Этот класс адаптера Argument позволяет передавать в функцию имена ресурсов (Лпктстрс) или идентификаторы ресурсов (UINT), не требуя от вызывающего объекта преобразования идентификатора в строку с помощью макроса МАКЕИНТРЕСАУРЦЕ.|atlwin.h|
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|Этот класс предоставляет функцию создания для потока Windows. Используйте этот класс, если поток не будет использовать функции CRT.|atlbase.h|

## <a name="see-also"></a>См. также

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Функции](../../atl/reference/atl-functions.md)<br/>
[Глобальные переменные](../../atl/reference/atl-global-variables.md)<br/>
[Typedefs](../../atl/reference/atl-typedefs.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
