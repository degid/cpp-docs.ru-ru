---
title: Инициализация и прекращение работы ядра базы данных DAO
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 0a70dd396a87315a96224edccf13250a2927cd99
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837597"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

DAO используется с базами данных Access и поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей. При использовании объектов MFC DAO необходимо сначала инициализировать ядро СУБД DAO, а затем завершить работу, прежде чем приложение или библиотека DLL завершит работу. Две функции, `AfxDaoInit` и `AfxDaoTerm` , выполняют эти задачи.

### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

|Имя|Описание|
|-|-|
|[AfxDaoInit](#afxdaoinit)|Инициализирует ядро базы данных DAO.|
|[AfxDaoTerm](#afxdaoterm)|Завершает работу компонента базы данных DAO.|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a> афксдаоинит

Эта функция инициализирует ядро базы данных DAO.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Примечания

В большинстве случаев вызывать не нужно, `AfxDaoInit` так как приложение автоматически вызывает его при необходимости.

Связанные сведения и пример вызова `AfxDaoInit` см. в [техническом примечании 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a> афксдаотерм

Эта функция завершает работу компонента базы данных DAO.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Примечания

Как правило, эта функция должна вызываться только в обычной библиотеке DLL MFC. приложение будет автоматически вызываться `AfxDaoTerm` при необходимости.

В обычных библиотеках DLL MFC вызовите метод `AfxDaoTerm` перед `ExitInstance` функцией, но после уничтожения всех объектов MFC DAO.

Связанные сведения см. в [техническом примечании 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
