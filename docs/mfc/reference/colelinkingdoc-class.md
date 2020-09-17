---
title: Класс COleLinkingDoc
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: 1fad986b7e7304075cacb0b5ced9feeb8af4664f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753851"
---
# <a name="colelinkingdoc-class"></a>Класс COleLinkingDoc

Базовый класс для документов OLE-контейнера, которые поддерживают связывание со встроенными элементами, которые их содержат.

## <a name="syntax"></a>Синтаксис

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Формирует объект `COleLinkingDoc`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeLinkingDoc:Регистрация](#register)|Регистрирует документ с помощью системы DOL СИСТЕМы OLE.|
|[ColeLinkingDoc::Revoke](#revoke)|Отменяет регистрацию документа.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[ColeLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Находит указанный встроенный элемент.|
|[ColeLinkingDoc::OngetLinkedItem](#ongetlinkeditem)|Находит указанный связанный элемент.|

## <a name="remarks"></a>Примечания

Контейнерное приложение, поддерживающее ссылку на встроенные элементы, называется "контейнер ссылки". Пример приложения [OCLIENT](../../overview/visual-cpp-samples.md) является примером контейнера ссылки.

Когда источник связанного элемента является встроенным элементом в другом документе, этот документ должен быть загружен для редактирования встроенного элемента. По этой причине контейнер ссылок должен быть запущен другим контейнерным приложением, когда пользователь хочет отсечь источник связанного элемента. Ваше приложение также должно использовать класс [COleTemplateServer,](../../mfc/reference/coletemplateserver-class.md) чтобы создавать документы при программном запуске.

Чтобы сделать контейнер ссылкой, вывемите класс документов из `COleLinkingDoc` вместо [COleDocument.](../../mfc/reference/coledocument-class.md) Как и в любом другом контейнере OLE, необходимо разработать свой класс для хранения нативных данных приложения, а также встроенных или связанных элементов. Кроме того, необходимо разработать структуры данных для хранения ваших родных данных. Если вы `CDocItem`определяете класс, полученный в результате использования родных данных приложения, можно использовать интерфейс, определяемый `COleDocument` для хранения ваших родных данных, а также данных OLE.

Чтобы ваше приложение было запущено программно другим контейнером, объявите `COleTemplateServer` объект в `CWinApp`качестве члена класса вашего приложения:

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

В `InitInstance` функции элемента класса «производный» `CWinApp`создайте шаблон документа и укажите класс `COleLinkingDoc`«производный» в качестве класса документа:

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

Подключите `COleTemplateServer` объект к шаблонам документов, позвонив в функцию `ConnectTemplate` члена `COleTemplateServer::RegisterAll`объекта, и зарегистрируйте все объекты класса с помощью системы OLE, позвонив:

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

Для определения `CWinApp`и `InitInstance` функции класса, полученного из образца, см. H и OCLIENT. CPP в образце MFC [OCLIENT](../../overview/visual-cpp-samples.md).

Для получения дополнительной `COleLinkingDoc`информации об использовании, см. [статьи Контейнеры: Реализация контейнеров](../../mfc/containers-implementing-a-container.md) и [контейнеров: Расширенные возможности](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a>ColeLinkingDoc::COleLinkingDoc

Строит объект `COleLinkingDoc` без начала связи с DLL системы OLE.

```
COleLinkingDoc();
```

### <a name="remarks"></a>Примечания

Вы должны `Register` позвонить в функцию участника, чтобы сообщить OLE, что документ открыт.

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a>ColeLinkingDoc::OnFindEmbeddedItem

Вызывается в рамках, чтобы определить, содержит ли документ встроенный элемент OLE с указанным именем.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Параметры

*lpszItemName*<br/>
Указатель на имя запрошенного элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на указанный элемент; NULL, если элемент не найден.

### <a name="remarks"></a>Примечания

Реализация по умолчанию выполняет список встроенных элементов для элемента с указанным именем (сравнение имен является конфиденциальным случаем). Переопределить эту функцию, если у вас есть свой собственный метод хранения или именования встроенных элементов OLE.

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a>ColeLinkingDoc::OngetLinkedItem

Вызывается в рамках, чтобы проверить, содержит ли документ связанный элемент сервера с указанным именем.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Параметры

*lpszItemName*<br/>
Указатель на имя запрошенного элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на указанный элемент; NULL, если элемент не найден.

### <a name="remarks"></a>Примечания

Реализация `COleLinkingDoc` по умолчанию всегда возвращает NULL. Эта функция переиздана в `COleServerDoc` производном классе для поиска списка элементов сервера OLE для связанного элемента с указанным именем (сравнение имен является чувствительным к случаю). Переизбь эту функцию, если вы реализовали свой собственный метод хранения или извлечения связанных элементов сервера.

## <a name="colelinkingdocregister"></a><a name="register"></a>ColeLinkingDoc:Регистрация

Сообщает системе OL, что документ открыт.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*pFactory*<br/>
Указатель на заводской объект OLE (может быть NULL).

*lpszPathName*<br/>
Указатель на полностью квалифицированный путь контейнерного документа.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если документ успешно зарегистрирован; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию при создании или открытии названного файла для регистрации документа с помощью DLL системы OLE. Нет необходимости вызывать эту функцию, если документ представляет собой встроенный элемент.

Если вы `COleTemplateServer` используете в `Register` вашем приложении, называется `OnNewDocument` `OnOpenDocument`для `OnSaveDocument`вас `COleLinkingDoc`'с реализацией , и .

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a>ColeLinkingDoc::Revoke

Сообщает системе OL DLL, что документ больше не открыт.

```cpp
void Revoke();
```

### <a name="remarks"></a>Примечания

Позвоните в эту функцию, чтобы аннулировать регистрацию документа с системой OL DLL.

Вы должны вызвать эту функцию при закрытии названного файла, но обычно вам не нужно вызывать ее напрямую. `Revoke`называется для `COleLinkingDoc`вас 'с `OnCloseDocument` `OnNewDocument`реализацией , , `OnOpenDocument`и `OnSaveDocument`.

## <a name="see-also"></a>См. также раздел

[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
