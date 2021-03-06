---
title: COM+ 1.0, мастер компонентов ATL COM+ 1.0
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: 83b7beafe537f6b271b254d16505b515a41acf27
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496694"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, мастер компонентов ATL COM+ 1.0

::: moniker range="vs-2019"

Этот мастер недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=vs-2017"

На этой странице мастера компонентов COM+ 1.0 библиотеки ATL можно задать тип интерфейса и дополнительные поддерживаемые интерфейсы.

Дополнительные сведения о проектах ATL и COM-классах библиотеки ATL см. в разделе [COM-компоненты ATL для настольных приложений](../../atl/atl-com-desktop-components.md).

- **Interface**

   Указывает тип интерфейса, который поддерживается объектом. По умолчанию объект поддерживает двойной интерфейс.

   |Параметр|Описание|
   |------------|-----------------|
   |**Двойной**|Указывает, что объект поддерживает двойной интерфейс (его виртуальная таблица содержит настраиваемые функции интерфейса и методы позднего связывания `IDispatch`). Обеспечивает доступ к объекту как COM-клиентам, так и контроллерам автоматизации.|
   |**Пользовательский**|Указывает, что объект поддерживает настраиваемый интерфейс (его виртуальная таблица содержит настраиваемые функции интерфейса). Настраиваемый интерфейс может работать быстрее двойного, особенно в случае межпроцессного взаимодействия.<br /><br /> - **Совместимый с автоматизацией**. Добавляет поддержку автоматизации для настраиваемого интерфейса. Для проектов с атрибутами задает атрибут **oleautomation** в коклассе.|

- **Поддержка очередей**

   Указывает, что клиент может вызывать этот компонент асинхронно с использованием очередей сообщений. Добавляет макрос компонента с атрибутами custom(TLBATTR_QUEUEABLE, 0) в H-файл (проекты с атрибутами) или в IDL-файл (проекты без атрибутов).

- **Поддержка**

   Указывает дополнительный способ поддержки для обработки ошибок и управления объектом.

   |Параметр|Описание|
   |------------|-----------------|
   |**ISupportErrorInfo**|Создает поддержку для интерфейса [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md), который позволяет объекту возвращать в клиент сведения об ошибке.|
   |**IObjectControl**|Предоставляет объекту доступ к трем методам интерфейса [IObjectControl](/windows/win32/api/comsvcs/nn-comsvcs-iobjectcontrol): [Activate](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-activate), [CanBePooled](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled) и [Deactivate](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate).|
   |**IObjectConstruct**|Создает поддержку интерфейса [IObjectConstruct](/windows/win32/api/comsvcs/nn-comsvcs-iobjectconstruct), который управляет передачей параметров из других методов и объектов.|

- **Транзакция**

   Указывает, что объект поддерживает транзакции. Включает файл mtxattr.h в IDL-файл (проекты без атрибутов).

   |Параметр|Описание|
   |------------|-----------------|
   |**Поддерживается**|Указывает, что объект никогда не выступает в качестве корневого объекта потока транзакций. Для этого добавляет макрос компонента с атрибутами custom(TLBATTR_TRANS_SUPPORTED,0) в H-файл (проекты с атрибутами) или в IDL-файл (проекты без атрибутов).|
   |**Обязательное**|Указывает, что объект в некоторых случаях может выступать в качестве корневого объекта потока транзакций. Для этого добавляет макрос компонента с атрибутами custom(TLBATTR_TRANS_REQUIRED,0) в H-файл (проекты с атрибутами) или в IDL-файл (проекты без атрибутов).|
   |**Не поддерживается**|Указывает, что объект не поддерживает транзакции. Добавляет макрос компонента с атрибутами custom(TLBATTR_TRANS_NOTSUPP,0) в H-файл (проекты с атрибутами) или в IDL-файл (проекты без атрибутов).|
   |**Требуется новая**|Указывает, что объект всегда выступает в качестве корневого объекта потока транзакций. Для этого добавляет макрос компонента с атрибутами custom(TLBATTR_TRANS_REQNEW,0) в H-файл (проекты с атрибутами) или в IDL-файл (проекты без атрибутов).|

::: moniker-end

## <a name="see-also"></a>См. также

[Мастер компонентов ATL COM+ 1.0](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[Компонент COM+ 1.0 библиотеки ATL](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
