---
title: Поддержка свободной потоковой модели в поставщике
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 50e05b70a782dd343031443540790697e980c994
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209557"
---
# <a name="supporting-free-threading-in-your-provider"></a>Поддержка свободной потоковой модели в поставщике

Все классы поставщиков OLE DB являются потокобезопасными, а записи реестра задаются соответствующим образом. Рекомендуется поддерживать бесплатные потоки, чтобы обеспечить высокий уровень производительности в многопользовательской ситуации. Чтобы обеспечить потокобезопасность поставщика, необходимо убедиться в том, что код заблокирован правильно. Каждый раз при записи или хранении данных необходимо заблокировать доступ с критически важными разделами.

Каждый объект шаблона поставщика OLE DB имеет свой собственный критический раздел. Чтобы упростить блокировку, каждый новый создаваемый класс должен быть классом шаблона, принимающим имя родительского класса в качестве аргумента.

В следующем примере показано, как заблокировать код:

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

Дополнительные сведения о том, как защитить критические разделы с помощью `Lock` и `Unlock`, см. в статье [многопоточность. Использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Убедитесь, что переопределяемые методы (например, `Execute`) являются потокобезопасными.

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
