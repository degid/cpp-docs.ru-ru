---
title: Соглашения о вызове, параметры и тип возвращаемого значения
ms.date: 02/13/2019
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: 8813bab0cb55aa57792d0031433d96eefb095da4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223919"
---
# <a name="calling-conventions-parameters-and-return-type"></a>Соглашения о вызове, параметры и тип возвращаемого значения

Прототип вспомогательной подпрограммы:

```
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>Параметры

*пидд*<br/>
**`const`** Указатель на объект `ImgDelayDescr` , содержащий смещения различных данных, связанных с импортом, отметку времени для данных привязки и набор атрибутов, которые предоставляют дополнительные сведения о содержимом дескриптора. В настоящее время существует только один атрибут, `dlattrRva` который указывает, что адреса в дескрипторе являются относительными виртуальными адресами. Дополнительные сведения см. в объявлениях в *делайимп.h*.

Описание `PCImgDelayDescr` структуры см. в разделе [определения структуры и константы](structure-and-constant-definitions.md).

*ппфниатентри*<br/>
Указатель на слот в таблице адресов импорта с отложенной загрузкой (IAT), который обновлен с адресом импортированной функции. Вспомогательная подпрограммы должна хранить то же значение, которое она возвращает в это расположение.

## <a name="expected-return-values"></a>Ожидаемые возвращаемые значения

Если функция выполнена успешно, она возвращает адрес импортированной функции.

Если функция завершается с ошибкой, она создает исключение и возвращает 0. Возможны три типа исключений.

- Недопустимый параметр. Это исключение создается, если атрибуты в `pidd` указаны некорректно.

- Функции `LoadLibrary` не удалось загрузить указанную библиотеку DLL.

- Ошибка в функции `GetProcAddress`.

Вы отвечаете за обработку этих исключений.

## <a name="remarks"></a>Примечания

Соглашение о вызовах для вспомогательной функции — **`__stdcall`** . Тип возвращаемого значения не важен, поэтому используется ФАРПРОК. Для этой функции используется компоновка C.

Возвращаемое значение вспомогательной подпрограммы загрузки с задержкой должно быть сохранено в переданном указателе на функцию, если только подпрограмма не должна использоваться в качестве обработчика уведомлений. В этом случае за поиск необходимого возвращаемого указателя на функцию отвечает пользовательский код. Затем код преобразователя, создаваемый компоновщиком, принимает это возвращаемое значение в качестве действительной цели импорта и переходит непосредственно к ней.

## <a name="sample"></a>Пример

В приведенном ниже примере показано, как реализовать простейшую функцию-обработчик.

```C
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)
{
    switch (dliNotify) {
        case dliStartProcessing :

            // If you want to return control to the helper, return 0.
            // Otherwise, return a pointer to a FARPROC helper function
            // that will be used instead, thereby bypassing the rest
            // of the helper.

            break;

        case dliNotePreLoadLibrary :

            // If you want to return control to the helper, return 0.
            // Otherwise, return your own HMODULE to be used by the
            // helper instead of having it call LoadLibrary itself.

            break;

        case dliNotePreGetProcAddress :

            // If you want to return control to the helper, return 0.
            // If you choose you may supply your own FARPROC function
            // address and bypass the helper's call to GetProcAddress.

            break;

        case dliFailLoadLib :

            // LoadLibrary failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_MOD_NOT_FOUND) and exit.
            // If you want to handle the failure by loading an alternate
            // DLL (for example), then return the HMODULE for
            // the alternate DLL. The helper will continue execution with
            // this alternate DLL and attempt to find the
            // requested entrypoint via GetProcAddress.

            break;

        case dliFailGetProc :

            // GetProcAddress failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_PROC_NOT_FOUND) and exit.
            // If you choose you may handle the failure by returning
            // an alternate FARPROC function address.

            break;

        case dliNoteEndProcessing :

            // This notification is called after all processing is done.
            // There is no opportunity for modifying the helper's behavior
            // at this point except by longjmp()/throw()/RaiseException.
            // No return value is processed.

            break;

        default :

            return NULL;
    }

    return NULL;
}

/*
and then at global scope somewhere
const PfnDliHook __pfnDliNotifyHook2 = delayHook;
*/
```

## <a name="see-also"></a>См. также статью

[Основные сведения о вспомогательной функции](understanding-the-helper-function.md)
