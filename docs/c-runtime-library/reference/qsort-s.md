---
title: qsort_s
ms.date: 4/2/2020
api_name:
- qsort_s
- _o_qsort_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- qsort_s
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
ms.openlocfilehash: 934801531804345a8cede6ed1ac4abb06bae45b4
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913277"
---
# <a name="qsort_s"></a>qsort_s

Выполняет быструю сортировку. Версия функции [qsort](qsort.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Параметры

*base*<br/>
Начало целевого массива.

*number*<br/>
Размер массива в элементах.

*width*<br/>
Размер элементов в байтах.

*равенств*<br/>
Функция сравнения. Первым аргументом является указатель *контекста* . Второй аргумент — это указатель на *ключ* для поиска. Третий аргумент — это указатель на элемент массива, который будет сравниваться с *ключом*.

*context*<br/>
Указатель на контекст, который может быть любым объектом, к которому должна обращаться подпрограммы *сравнения* .

## <a name="remarks"></a>Примечания

Функция **qsort_s** реализует алгоритм быстрой сортировки для сортировки массива *числовых* элементов, каждый из которых имеет *ширину* в байтах. *Основание* аргумента — это указатель на базовую часть массива, который необходимо отсортировать. **qsort_s** перезаписывает этот массив отсортированными элементами. Аргумент *Compare* — это указатель на предоставляемую пользователем подпрограммы, которая сравнивает два элемента массива и возвращает значение, указывающее их связь. **qsort_s** вызывает подпрограммы *сравнения* один или несколько раз во время сортировки, передавая указатели на два элемента массива при каждом вызове:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Подпрограмма должна сравнивать элементы, а затем возвращать одно из следующих значений:

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|**elem1** меньше **elem2**|
|0|**elem1** эквивалентно **elem2**|
|> 0|**elem1** больше **elem2**|

Массив сортируется по возрастанию, как определено функцией сравнения. Для сортировки массива по убыванию измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.

Если функции передаются недопустимые параметры, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **, а** параметру переводит значение **еинвал**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|ключ|base;|compare|num|width|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**ЗАКАНЧИВАЮЩ**|any|any|any|any|**еинвал**|
|any|**ЗАКАНЧИВАЮЩ**|any|!= 0|any|**еинвал**|
|any|any|any|any|<= 0|**еинвал**|
|any|any|**ЗАКАНЧИВАЮЩ**|any|any|**еинвал**|

**qsort_s** имеет то же поведение, что и **qsort** , но имеет параметр *контекста* **и устанавливает значение**переводится. Передавая параметр *контекста* , функции сравнения могут использовать указатель на объект для доступа к функциональности объекта или другую информацию, недоступную через указатель элемента. Добавление параметра *контекста* делает **qsort_s** более безопасным, так как *контекст* может использоваться, чтобы избежать ошибок повторного входа, появившихся с помощью статических переменных, чтобы предоставить доступ к общей информации функции *сравнения* .

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

**Библиотеки:** все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется использование параметра *context* в функции **qsort_s** . Параметр *контекста* упрощает выполнение поточно-ориентированных сортировок. Вместо использования статических переменных, которые должны быть синхронизированы для обеспечения потокобезопасности, передайте другой параметр *контекста* в каждой сортировке. В этом примере в качестве параметра *контекста* используется объект языкового стандарта.

```cpp
// crt_qsort_s.cpp
// compile with: /EHsc /MT
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S in that codepage and \x00a4
// is the n tilde.

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.850"
#define SPANISH_LOCALE "Spanish_Spain.850"
#define ENGLISH_LOCALE "English_US.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S and \x001f for the n tilde.
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.1252"
#define SPANISH_LOCALE "Spanish_Spain.1252"
#define ENGLISH_LOCALE "English_US.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making sort_array vulnerable to thread
// conflicts.

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char s1[256];
    char s2[256];
    strcpy_s(s1, 256, *(char**)str1);
    strcpy_s(s2, 256, *(char**)str2);
    _strlwr_s( s1, sizeof(s1) );
    _strlwr_s( s2, sizeof(s2) );

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(s1,
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);

}

void sort_array(char *array[], int num, locale &loc)
{
    qsort_s(array, num, sizeof(char*), compare, &loc);
}

void print_array(char *a[], int c)
{
   for (int i = 0; i < c; i++)
      printf("%s ", a[i]);
   printf("\n");

}

void sort_german(void * Dummy)
{
   sort_array(array1, 6, locale(GERMAN_LOCALE));
}

void sort_spanish(void * Dummy)
{
   sort_array(array2, 3, locale(SPANISH_LOCALE));
}

void sort_english(void * Dummy)
{
   sort_array(array3, 3, locale(ENGLISH_LOCALE));
}

int main( )
{
   int i;
   HANDLE threads[3];

   printf("Unsorted input:\n");
   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);

   // Create several threads that perform sorts in different
   // languages at the same time.

   threads[0] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_german , 0, NULL));
   threads[1] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_spanish, 0, NULL));
   threads[2] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_english, 0, NULL));

   for (i = 0; i < 3; i++)
   {
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
      {
         printf("Error creating threads.\n");
         exit(1);
      }
   }

   // Wait until all threads have terminated.
   WaitForMultipleObjects(3, threads, true, INFINITE);

   printf("Sorted output: \n");

   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);
}
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
