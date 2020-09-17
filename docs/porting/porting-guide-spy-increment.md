---
title: 'Руководство по переносу: Spy++'
ms.date: 10/23/2019
ms.assetid: e558f759-3017-48a7-95a9-b5b779d5e51d
ms.openlocfilehash: 6f63f082d96f33246592b0e7f39b6788417f8a32
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217861"
---
# <a name="porting-guide-spy"></a>Руководство по переносу: Spy++

Этот пример переноса позволяет понять, на что похож типичный проект переноса, какие типы проблем могут возникать, а также содержит ряд общих советов и рекомендаций по решению проблем переноса. Это не является полным руководством по переносу, так как особенности переноса проекта существенно зависят от конкретного кода.

## <a name="spy"></a>Spy++

Spy++ является широко используемым инструментом диагностики графического интерфейса пользователя для рабочего стола Windows, который предоставляет всевозможные сведения об элементах пользовательского интерфейса на рабочем столе Windows. Он отображает полную иерархию окон и предоставляет доступ к метаданным о всех окнах и элементах управления. Данное приложение поставлялось вместе с Visual Studio в течение нескольких лет. Мы нашли старую версию этого приложения, которое в последний раз было скомпилировано в Visua C++ 6.0, и перенесли его в Visual Studio 2015. Интерфейс Visual Studio 2017 или Visual Studio 2019 должен быть практически одинаковым.

Мы считаем данный случай типичным для переноса классических приложений Windows, использующих MFC и API-интерфейс Win32, особенно для старых проектов, которые не обновлялись с каждым выпуском Visual C++ после Visual C++ 6.0.

## <a name="step-1-converting-the-project-file"></a><a name="convert_project_file"></a> Шаг 1. Преобразование файла проекта.

Файл проекта, два старых файла DSW из Visual C++ 6.0, были преобразованы без проблем, которые бы требовали дополнительного внимания. Один проект — это приложение Spy++. Другой проект — SpyHk, написанный на языке C, представляющий собой вспомогательную библиотеку DLL. Более сложные проекты, возможно, не удастся обновить так же легко, как это описано [здесь](../porting/visual-cpp-porting-and-upgrading-guide.md).

После обновления двух проектов наше решение выглядело следующим образом:

![Решение&#43;&#43; Spy](../porting/media/spyxxsolution.PNG "Решение&#43;&#43; Spy")

У нас есть два проекта — один с большим количеством файлов C++ и другой, представляющий собой библиотеку DLL, которая написана на языке C.

## <a name="step-2-header-file-problems"></a><a name="header_file_problems"></a> Шаг 2. Проблемы с файлами заголовков

При построении нового преобразованного проекта первая проблема, с которой часто можно столкнуться, заключается в том, что не найдены файлы заголовков, используемые в проекте.

Одним из файлов, которые не удалось найти в Spy++, был файл verstamp.h. Благодаря поиску в Интернете мы решили, что это произошло из-за DAO SDK, устаревшей технологии данных. Мы хотели узнать, какие символы использовались из этого файла заголовка, чтобы выяснить, что этот файл действительно нужен или что эти символы определены в другом месте, поэтому мы закомментировали объявление файла заголовка и повторно выполнили компиляцию. Оказалось, что имеется лишь один символ, который нужен, а именно VER_FILEFLAGSMASK.

```Output
1>C:\Program Files (x86)\Windows Kits\8.1\Include\shared\common.ver(212): error RC2104: undefined keyword or key name: VER_FILEFLAGSMASK
```

Самым простым способом поиска символа в доступных включаемых файлах является применение операции **поиска в файлах** (**CTRL**+**SHIFT**+**F**) и указание **каталогов включаемых файлов Visual C++**. Мы нашли данный символ в файле ntverp.h. Мы заменили включаемый файл verstamp.h на файл ntverp.h, и эта ошибка исчезла.

## <a name="step-3-linker-outputfile-setting"></a><a name="linker_output_settings"></a>Шаг 3. Параметр OutputFile компоновщика

Иногда старые проекты содержат файлы, расположенные в нестандартных папках, что может вызывать проблемы после обновления. В этом случае нужно добавить `$(SolutionDir)` в путь поиска **включаемых файлов** в свойствах проекта, чтобы убедиться, что Visual Studio может найти некоторые файлы заголовков в этих расположениях, а не в одной из папок проекта.

MSBuild сообщает, что свойство **Link.OutputFile** не совпадает со значениями **TargetPath** и **TargetName**, выдавая MSB8012.

```Output
warning MSB8012: TargetPath(...\spyxx\spyxxhk\.\..\Debug\SpyxxHk.dll) does not match the Linker's OutputFile property value (...\spyxx\Debug\SpyHk55.dll). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).warning MSB8012: TargetName(SpyxxHk) does not match the Linker's OutputFile property value (SpyHk55). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).
```

**Link.OutputFile** — это выходной файл сборки (например, EXE, DLL). Обычно он создается на основе `$(TargetDir)$(TargetName)$(TargetExt)`, что задает путь, имя файла и расширение. Это распространенная ошибка при миграции проектов из старого инструмента сборки Visual C++ (vcbuild.exe) в новый инструмент сборки (MSBuild.exe). Так как в Visual Studio 2010 применяется другой инструмент сборки, эта проблема может происходить при каждой миграции проекта из версии до 2010 в версию 2010 или более позднюю. Основная проблема заключается в том, что мастер миграции проектов не обновляет значение **Link. выходной_файл** , так как не всегда можно определить, какое значение должно быть основано на других параметрах проекта. Поэтому его обычно приходится устанавливать вручную. Дополнительные сведения см. в [публикации](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/) в блоге Visual C++.

В этом случае для свойства **Link.OutputFile** в преобразованном проекте было установлено значение Debug\Spyxx.exe и \Release\Spyxx.exe для проекта Spy ++ в зависимости от конфигурации. Лучше всего просто заменить эти жестко запрограммированные значения на `$(TargetDir)$(TargetName)$(TargetExt)` для **всех конфигураций**. Если это не поможет, можно выполнить настройку из этого раздела или изменить свойства в разделе **Общие** , где заданы эти значения (свойства являются **выходным каталогом**, **целевым именем**и **целевым расширением**). Помните, что если просматриваемое вами свойство использует макросы, то в раскрывающемся списке можно нажать **Изменить**, чтобы открыть диалоговое окно, где будет отображаться последняя строка со сделанными подстановками макросов. Для просмотра всех доступных макросов и их текущих значений нажмите кнопку **Макросы**.

## <a name="step-4-updating-the-target-windows-version"></a><a name="updating_winver"></a>Шаг 4. Обновление целевой версии Windows

Следующая ошибка указывает, что версия WINVER больше не поддерживается в MFC. Версия WINVER для Windows XP — 0x0501.

```Output
C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxv_w32.h(40): fatal error C1189: #error:  MFC does not support WINVER less than 0x0501.  Please change the definition of WINVER in your project properties or precompiled header.
```

Корпорация Майкрософт больше не поддерживает Windows XP, поэтому, хотя эту ОС можно использовать в качестве целевой в Visual Studio, рекомендуем вам постепенно отказываться от ее поддержки в своих приложениях и просить своих клиентов переходить на новые версии Windows.

Для устранения ошибки определите WINVER путем обновления **свойств проекта** — укажите здесь самую раннюю версию Windows, на которую вы хотите в настоящее время ориентироваться. Таблицу значений для различных версий Windows см. [здесь](/windows/win32/WinProg/using-the-windows-headers).

Файл *stdafx.h* содержал некоторые из этих определений макросов.

```cpp
#define WINVER       0x0500  // these defines are set so that we get the
#define _WIN32_WINNT 0x0500  // maximum set of message/flag definitions,
#define _WIN32_IE    0x0400  // from both winuser.h and commctrl.h.
```

Для WINVER мы установим Windows 7. Если вы используете макрос для Windows 7 (_WIN32_WINNT_WIN7), а не само значение (0x0601), проще прочитать код позже.

```cpp
#define WINVER _WINNT_WIN32_WIN7 // Minimum targeted Windows version is Windows 7
```

## <a name="step-5-linker-errors"></a><a name="linker_errors"></a>Шаг 5. Ошибки компоновщика

Благодаря этим изменениям проект SpyHk (DLL) выполняет сборку, но создает ошибку компоновщика.

```Output
LINK : warning LNK4216: Exported entry point _DLLEntryPoint@12
```

Точка входа для библиотеки DLL не должна экспортироваться. Точка входа должна вызываться загрузчиком только при первой загрузке библиотеки DLL в память, поэтому ее не должно быть в таблице экспорта, предназначенной для других вызывающих объектов. Нам просто нужно убедиться, что к ней не **`__declspec(dllexport)`** присоединена директива. В файле spyxxhk.c ее необходимо удалить в двух местах: в объявлении и определении `DLLEntryPoint`. Смысла использовать эту директиву никогда не было, но предыдущие версии компоновщика и компилятора не отмечали ее как проблему. Более новые версии компоновщика выдают предупреждение.

```cpp
// deleted __declspec(dllexport)
BOOL WINAPI DLLEntryPoint(HINSTANCE hinstDLL,DWORD fdwReason, LPVOID lpvReserved);
```

Теперь проект C DLL (SpyHK.dll) выполняет процесс сборки и компоновки без ошибок.

## <a name="step-6-more-outdated-header-files"></a><a name="outdated_header_files"></a>Шаг 6. Более устаревшие файлы заголовков

Теперь мы приступаем к работе с основным проектом исполняемого файла — Spyxx.

Несколько других включаемых файлов (ctl3d.h и penwin.h) найти не удалось. Хотя может быть полезно выполнить поиск в Интернете, чтобы попытаться определить, что включало заголовок, иногда информация не полезна. Мы обнаружили, что файл ctl3d.h входил в состав Exchange Development Kit и обеспечивал поддержку определенного стиля элементов управления в Windows 95, а penwin.h относится к технологии вычислений с использованием перьевого указателя (устаревшего API). В этом случае мы просто закомментируем строку `#include` и займемся неопределенными символами, как мы сделали с файлом verstamp.h. Все, что относится к технологиям 3D Controls или к компьютерам с перьевым вводом, было удалено из проекта.

В случае проекта с большим количеством ошибок компиляции, которые вы постепенно устраняете, нереально найти все случаи использования устаревшего API сразу после удаления директивы `#include`. Мы не обнаружили все сразу, а лишь через некоторое время выявили ошибку, которая заключается в том, что символ WM_DLGBORDER не был определен. Фактически это один из многочисленных неопределенных символов, которые содержатся в файле ctl3d.h. Определив, что данный символ относится к устаревшему API, мы удалили все ссылки на него в коде.

## <a name="step-7-updating-old-iostreams-code"></a><a name="updating_iostreams_code"></a>Шаг 7. Обновление старого кода iostream

Следующая ошибка чаще всего происходит со старым кодом C++, который использует потоки iostream.

```Output
mstream.h(40): fatal error C1083: Cannot open include file: 'iostream.h': No such file or directory
```

Проблема заключается в том, что старая библиотека iostream была удалена и заменена. Старые iostream необходимо заменить на новые стандарты.

```cpp
#include <iostream.h>
#include <strstrea.h>
#include <iomanip.h>
```

Обновления включают в себя:

```cpp
#include <iostream>
#include <sstream>
#include <iomanip>
```

Из-за этого изменения возникают проблемы с `ostrstream`, который больше не используется. Соответствующая замена — ostringstream. Мы пытаемся добавить **`typedef`** для, `ostrstream` чтобы избежать слишком большого изменения кода, по крайней мере в начале.

```cpp
typedef std::basic_ostringstream<TCHAR> ostrstream;
```

В настоящее время проект строится с использованием многобайтовой кодировки, поэтому **`char`** является соответствующим символьным типом данных. Однако, чтобы упростить обновление кода в кодировке UTF-16 Unicode, мы обновляем его до `TCHAR` , который разрешается в **`char`** или в **`wchar_t`** зависимости от того, задано ли для свойства **Кодировка** в параметрах проекта значение MBCS или Unicode.

Необходимо обновить несколько фрагментов кода.  Мы заменили базовый класс `ios` на `ios_base` , и мы заменили ostream basic_ostream \<T> . Мы добавляем два дополнительных typedef и компилируем данный раздел.

```cpp
typedef std::basic_ostream<TCHAR> ostream;
typedef ios_base ios;
```

Использование этих typedef представляет собой просто временное решение. Чтобы получить постоянное решение, следует обновить каждую ссылку на переименованный или устаревший API.

Ниже приведена следующая ошибка.

```Output
error C2039: 'freeze': is not a member of 'std::basic_stringbuf<char,std::char_traits<char>,std::allocator<char>>'
```

Следующая проблема заключается в том, что `basic_stringbuf` у вас нет `freeze` метода. Метод `freeze` используется для предотвращения утечки памяти в старом `ostream`. Он не нужен, пока мы используем новый `ostringstream` . Мы можем удалить вызов `freeze`.

```cpp
//rdbuf()->freeze(0);
```

Следующие две ошибки произошли в соседних строках. Первый сообщает об использовании `ends` , который является `iostream` манипулятором ввода-вывода старой библиотеки, добавляющим в строку символ конца null. Во второй из этих ошибок объясняется, что выходные данные `str` метода не могут быть назначены указателю, не являющемуся константой.

```cpp
// Null terminate the string in the buffer and
// get a pointer to it.
//
*this << ends;
LPSTR psz = str();
```

```Output
2>mstream.cpp(167): error C2065: 'ends': undeclared identifier2>mstream.cpp(168): error C2440: 'initializing': cannot convert from 'std::basic_string<char,std::char_traits<char>,std::allocator<char>>' to 'LPSTR'
```

Благодаря применению новой библиотеки потоков `ends` не нужен, так как строка всегда имеет знак завершения NULL, поэтому ее можно удалить. Во второй причине проблема заключается в том, что теперь `str()` не возвращает указатель на массив символов для строки. он возвращает `std::string` тип. Для устранения второй проблемы следует изменить тип на `LPCSTR` и использовать метод `c_str()` для запроса указателя.

```cpp
//*this << ends;
LPCTSTR psz = str().c_str();
```

В этом коде произошла ошибка, которая озадачила нас на некоторое время.

```cpp
MOUT << _T(" chUser:'") << chUser
<< _T("' (") << (INT)(UCHAR)chUser << _T(')');
```

Макрос MOUT разрешается в `*g_pmout`, который является объектом типа `mstream`. Класс `mstream` является производным от класса стандартной выходной строки, `std::basic_ostream<TCHAR>`. Однако при наличии \_T вокруг строкового литерала, который мы поместили в процессе подготовки к преобразованию в Юникод, разрешение перегрузки **оператора <<** завершается сбоем со следующим сообщением об ошибке:

```Output
1>winmsgs.cpp(4612): error C2666: 'mstream::operator <<': 2 overloads have similar conversions
1>  c:\source\spyxx\spyxx\mstream.h(120): note: could be 'mstream &mstream::operator <<(ios &(__cdecl *)(ios &))'
1>  c:\source\spyxx\spyxx\mstream.h(118): note: or       'mstream &mstream::operator <<(ostream &(__cdecl *)(ostream &))'
1>  c:\source\spyxx\spyxx\mstream.h(116): note: or       'mstream &mstream::operator <<(ostrstream &(__cdecl *)(ostrstream &))'
1>  c:\source\spyxx\spyxx\mstream.h(114): note: or       'mstream &mstream::operator <<(mstream &(__cdecl *)(mstream &))'
1>  c:\source\spyxx\spyxx\mstream.h(109): note: or       'mstream &mstream::operator <<(LPTSTR)'
1>  c:\source\spyxx\spyxx\mstream.h(104): note: or       'mstream &mstream::operator <<(TCHAR)'
1>  c:\source\spyxx\spyxx\mstream.h(102): note: or       'mstream &mstream::operator <<(DWORD)'
1>  c:\source\spyxx\spyxx\mstream.h(101): note: or       'mstream &mstream::operator <<(WORD)'
1>  c:\source\spyxx\spyxx\mstream.h(100): note: or       'mstream &mstream::operator <<(BYTE)'
1>  c:\source\spyxx\spyxx\mstream.h(95): note: or       'mstream &mstream::operator <<(long)'
1>  c:\source\spyxx\spyxx\mstream.h(90): note: or       'mstream &mstream::operator <<(unsigned int)'
1>  c:\source\spyxx\spyxx\mstream.h(85): note: or       'mstream &mstream::operator <<(int)'
1>  c:\source\spyxx\spyxx\mstream.h(83): note: or       'mstream &mstream::operator <<(HWND)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1132): note: or       'CDumpContext &operator <<(CDumpContext &,COleSafeArray &)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1044): note: or       'CArchive &operator <<(CArchive &,ATL::COleDateTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1042): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::COleDateTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1037): note: or       'CArchive &operator <<(CArchive &,ATL::COleDateTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1035): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::COleDateTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1030): note: or       'CArchive &operator <<(CArchive &,COleCurrency)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1028): note: or       'CDumpContext &operator <<(CDumpContext &,COleCurrency)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(955): note: or       'CArchive &operator <<(CArchive &,ATL::CComBSTR)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(951): note: or       'CArchive &operator <<(CArchive &,COleVariant)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(949): note: or       'CDumpContext &operator <<(CDumpContext &,COleVariant)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(248): note: or       'CArchive &operator <<(CArchive &,const RECT &)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(247): note: or       'CArchive &operator <<(CArchive &,POINT)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(246): note: or       'CArchive &operator <<(CArchive &,SIZE)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(242): note: or       'CDumpContext &operator <<(CDumpContext &,const RECT &)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(241): note: or       'CDumpContext &operator <<(CDumpContext &,POINT)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(240): note: or       'CDumpContext &operator <<(CDumpContext &,SIZE)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1639): note: or       'CArchive &operator <<(CArchive &,const CObject *)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1425): note: or       'CArchive &operator <<(CArchive &,ATL::CTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1423): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::CTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1418): note: or       'CArchive &operator <<(CArchive &,ATL::CTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1416): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::CTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(694): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,const char *)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(741): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(866): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,const _Elem *)'
1>          with
1>          [
1>              _Elem=wchar_t
1>          ]
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(983): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>,wchar_t[10]>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &&,const _Ty (&))'
1>          with
1>          [
1>              _Ty=wchar_t [10]
1>          ]
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(1021): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,const std::error_code &)'
1>  winmsgs.cpp(4612): note: while trying to match the argument list '(CMsgStream, const wchar_t [10])'
```

Так много определений **оператора <<** приводит к тому, что такая ошибка может иметь угрожающий вид. После более внимательного анализа доступных перегрузок можно увидеть, что большинство из них являются нерелевантными. Благодаря более глубокому анализу определения класса `mstream` мы обнаружили следующую функцию, которая, как нам кажется, должна вызываться в этом случае.

```cpp
mstream& operator<<(LPTSTR psz)
{
  return (mstream&)ostrstream::operator<<(psz);
}
```

Причина, по которой она не вызывается, заключается в том, что строковый литерал имеет тип `const wchar_t[10]`, как видно из последней строки в этом длинном сообщении об ошибке, поэтому преобразование в указатель, отличный от const, не выполняется автоматически. Однако этот оператор не должен изменять входной параметр, поэтому более подходящим типом параметра является `LPCTSTR` (`const char*` при компиляции как MBCS и `const wchar_t*` — как Юникод), а не `LPTSTR` (`char*` при компиляции как MBCS и `wchar_t*` — как Юникод). Если внести данное изменение, ошибка будет устранена.

Этот тип преобразования был разрешен в более старом и менее строгом компиляторе, но для более поздних изменений, обеспечивающих совместимость, требуется более правильный код.

## <a name="step-8-the-compilers-more-strict-conversions"></a><a name="stricter_conversions"></a>Шаг 8. Более строгие преобразования компилятора

Мы также получаем много примерно следующих ошибок:

```Output
error C2440: 'static_cast': cannot convert from 'UINT (__thiscall CHotLinkCtrl::* )(CPoint)' to 'LRESULT (__thiscall CWnd::* )(CPoint)'
```

Ошибка произошла в схеме сообщений, которая является просто макросом:

```cpp
BEGIN_MESSAGE_MAP(CFindToolIcon, CWnd)
// other messages omitted...
ON_WM_NCHITTEST() // Error occurs on this line.
END_MESSAGE_MAP()
```

Если посмотреть на определение этого макроса, мы увидим, что он ссылается на функцию `OnNcHitTest`.

```cpp
#define ON_WM_NCHITTEST() \
{ WM_NCHITTEST, 0, 0, 0, AfxSig_l_p, \
(AFX_PMSG)(AFX_PMSGW) \
(static_cast< LRESULT (AFX_MSG_CALL CWnd::*)(CPoint) > (&ThisClass :: OnNcHitTest)) },
```

Проблема связана с несоответствием в указателе на типы функций-членов. Проблема не заключается в преобразовании `CHotLinkCtrl` типа класса в в `CWnd` качестве типа класса, так как это допустимое преобразование производного на базовое. Проблема является типом возвращаемого значения: UINT и LRESULT. LRESULT разрешается в LONG_PTR, который является 64- или 32-разрядным указателем в зависимости от целевого двоичного типа, поэтому UINT не выполняет преобразование в этот тип. Такая ситуация при обновлении кода, написанного до 2005 г., является довольно редкой, так как тип возвращаемого значения многих методов схемы сообщений изменился с UINT на LRESULT в Visual Studio 2005 в рамках изменений для обеспечения совместимости с 64-разрядной версией. В следующем коде мы изменяем тип возвращаемого значения с UINT на LRESULT:

```cpp
afx_msg UINT OnNcHitTest(CPoint point);
```

После изменения получается следующий код:

```cpp
afx_msg LRESULT OnNcHitTest(CPoint point);
```

Поскольку существует около десяти вхождений этой функции в разных классах, производных от CWnd, полезно использовать **команду Перейти к определению** (клавиатура: **F12**) и **Перейти к объявлению** (сочетание клавиш: **CTRL** + **F12**), если курсор находится в функции редактора, чтобы найти их и перейти к ним из окна инструментов **Поиск символа** . Обычно функция **Перейти к определению** является более полезной при поиске. **Перейти к объявлению** позволяет искать объявления, отличные от объявления определяющего класса, например объявления дружественного класса или ссылки вперед.

## <a name="step-9-mfc-changes"></a><a name="mfc_changes"></a>Шаг 9. Изменения в MFC

Следующая ошибка также связана с типом измененного объявления и также возникает в макросе.

```Output
error C2440: 'static_cast': cannot convert from 'void (__thiscall CFindWindowDlg::* )(BOOL,HTASK)' to 'void (__thiscall CWnd::* )(BOOL,DWORD)'
```

Проблема заключается в том, что второй параметр `CWnd::OnActivateApp` изменен с HTASK на DWORD. Это изменение было сделано в выпуске 2002 г. для Visual Studio, Visual Studio .NET.

```cpp
afx_msg void OnActivateApp(BOOL bActive, HTASK hTask);
```

Нам нужно обновить объявления OnActivateApp в производных классах следующим образом:

```cpp
afx_msg void OnActivateApp(BOOL bActive, DWORD dwThreadId);
```

Теперь мы можем скомпилировать проект. Но у нас есть несколько предупреждений для проработки, а также имеются вспомогательные части обновления, например преобразование из MBCS в Юникод или повышение безопасности с помощью функций Secure CRT.

## <a name="step-10-addressing-compiler-warnings"></a><a name="compiler_warnings"></a>Шаг 10. Обработка предупреждений компилятора

Чтобы получить полный список предупреждений, выполните задачу **Перестроить все** в решении вместо обычного построения, чтобы убедиться, что все ранее скомпилированные части будут перекомпилированы, так как отчеты с предупреждениями будут поступать только из текущей компиляции. Другой вопрос заключается в том, следует ли оставить текущий уровень предупреждений или использовать более высокий уровень предупреждений.  При переносе большого объема кода, особенно старого кода, более удобным вариантом может оказаться применение более высокого уровня предупреждений.  Также можно начать с уровня предупреждений по умолчанию, а затем повысить уровень, чтобы получать все предупреждения. При использовании `/Wall` вы получаете некоторые предупреждения в системных файлах заголовков, поэтому многие пользователи применяют `/W4` для получения большинства предупреждений для своего кода вместо получения предупреждений для системных файлов заголовков. Если требуется, чтобы предупреждения отображались как ошибки, добавьте параметр `/WX`. Эти параметры находятся в разделе **C/C++** диалогового окна **Свойства проекта** .

Один из методов в классе `CSpyApp` выдает предупреждение о функции, которая больше не поддерживается.

```cpp
void SetDialogBkColor() {CWinApp::SetDialogBkColor(::GetSysColor(COLOR_BTNFACE));}
```

Предупреждение выглядит следующим образом.

```Output
warning C4996: 'CWinApp::SetDialogBkColor': CWinApp::SetDialogBkColor is no longer supported. Instead, handle WM_CTLCOLORDLG in your dialog
```

Сообщение WM_CTLCOLORDLG уже было обработано в коде Spy++, поэтому нужно было просто удалить все ссылки на `SetDialogBkColor`, который больше не требуется.

Для устранения следующего предупреждения нужно было просто закомментировать имя переменной. Мы получили следующее предупреждение:

```Output
warning C4456: declaration of 'lpszBuffer' hides previous local declaration
```

Код, создающий данное предупреждение, содержит макрос.

```cpp
DECODEPARM(CB_GETLBTEXT)
{
  P2WPOUT();

  P2LPOUTPTRSTR;
  P2IFDATA()
  {
    PARM(lpszBuffer, PPACK_STRINGORD, ED2);

    INDENT();

    P2IFISORD(lpszBuffer)
    {
      P2OUTORD(lpszBuffer);
    }
    else
    {
      PARM(lpszBuffer, LPTSTR, ED2);
      P2OUTS(lpszBuffer);
    }
  }
}
```

Активное применение макросов, как в этом коде, может усложнить работу с самим кодом. В этом случае макросы содержат объявления переменных. Макрос PARM определяется следующим образом:

```cpp
#define PARM(var, type, src)type var = (type)src
```

Поэтому переменная `lpszBuffer` объявляется в одной и той же функции два раза. Если бы в коде макросы не использовались, то такую ошибку исправить было бы очень просто (нужно просто удалить второе объявление типа). Однако у нас другая ситуация, и мы вынуждены решить, нужно ли переписать код макроса как обычный код (что является трудоемкой задачей, сопряженной с ошибками) или отключить предупреждение.

В этом случае мы решили отключить предупреждение. Это можно сделать путем добавления директивы pragma следующим образом:

```cpp
#pragma warning(disable : 4456)
```

При отключении предупреждения может потребоваться ограничить эффект отключения только в том коде, который создает предупреждение, чтобы избежать подавления предупреждения в тех случаях, когда оно может предоставлять полезные сведения. Мы добавляем код для восстановления предупреждения сразу после строки, которая выдает предупреждение. Но так как это предупреждение возникает в макросе, следует использовать ключевое слово **__pragma**, которое работает в макросах (`#pragma` в макросах не работает).

```cpp
#define PARM(var, type, src)__pragma(warning(disable : 4456))  \
type var = (type)src \
__pragma(warning(default : 4456))
```

Следующее предупреждение требует внесения некоторых изменений в код. Win32 API `GetVersion` (и `GetVersionEx`) является устаревшим.

```Output
warning C4996: 'GetVersion': was declared deprecated
```

Следующий код показывает, как получить версию.

```cpp
// check Windows version and set m_bIsWindows9x/m_bIsWindows4x/m_bIsWindows5x flags accordingly.
DWORD dwWindowsVersion = GetVersion();
```

Далее следует объемный код, который проверяет значение dwWindowsVersion, чтобы определить, работаем ли мы в Windows 95, а также версию Windows NT. Так как все это уже устарело, мы удаляем код и работаем со всеми ссылками на эти переменные.

Дополнительные сведения см. в статье [Operating system version changes in Windows 8.1 and Windows Server 2012 R2](/windows/win32/w8cookbook/operating-system-version-changes-in-windows-8-1) (Изменения версии операционной системы в Windows 8.1 и Windows Server 2012 R2).

Существуют методы в классе `CSpyApp`, которые запрашивают версию операционной системы: `IsWindows9x`, `IsWindows4x` и `IsWindows5x`. Для начала предположим, что все версии Windows, которые мы собираемся поддерживать (Windows 7 и более поздние версии) «близки» к Windows NT 5 с точки зрения технологий, используемых этим старым приложением. Применение данных методов было связано с ограничениями старых операционных систем. Поэтому мы изменили эти методы для возврата значения TRUE для `IsWindows5x` и значения FALSE для других.

```cpp
BOOL IsWindows9x() {/*return(m_bIsWindows9x);*/ return FALSE;  }
BOOL IsWindows4x() {/*return(m_bIsWindows4x);*/ return FALSE;  }
BOOL IsWindows5x() {/*return(m_bIsWindows5x);*/ return TRUE;  }
```

В коде осталось лишь несколько мест, где внутренние переменные использовались напрямую. Так как мы удалили эти переменные, мы получили несколько сообщений об ошибках, которые нужно обработать явным образом.

```Output
error C2065: 'm_bIsWindows9x': undeclared identifier
```

```cpp
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)
{
  pCmdUI->Enable(m_bIsWindows9x || hToolhelp32 != NULL);
}
```

Мы могли заменить это на вызов метода или просто передать значение TRUE и удалить старый особый случай для Windows 9x.

```cpp
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)
{
  pCmdUI->Enable(TRUE /*!m_bIsWindows9x || hToolhelp32 != NULL*/);
}
```

Окончательное предупреждение на уровне по умолчанию (3) относится к битовому полю.

```Output
treectl.cpp(1656): warning C4463: overflow; assigning 1 to bit-field that can only hold values from -1 to 0
```

Код, который запускает это предупреждение, выглядит следующим образом.

```cpp
m_bStdMouse = TRUE;
```

Объявление `m_bStdMouse` указывает, что это битовое поле.

```cpp
class CTreeListBox : public CListBox
{
  DECLARE_DYNCREATE(CTreeListBox)

  CTreeListBox();

  private:
  int ItemFromPoint(const CPoint& point);

  class CTreeCtl* m_pTree;
  BOOL m_bGotMouseDown : 1;
  BOOL m_bDeferedDeselection : 1;
  BOOL m_bStdMouse : 1;
```

Этот код был написан до того, как в Visual C++ начал поддерживаться встроенный тип bool. В таком коде BOOL был **`typedef`** для **`int`** . Тип **`int`** является **`signed`** типом, а битовое представление **`signed int`** — использовать первый бит в качестве бита знака, поэтому битовое выражение типа int может интерпретироваться как представляющее 0 или-1, возможно, не то, что было задумано.

Если посмотреть на данный код, нельзя понять, для чего используются эти битовые поля. Предполагалось ли сохранить небольшой размер объекта или же где-то применяется двоичный макет объекта? Мы изменили их на обычные элементы BOOL, так как не видели причин использовать битовое поле. Применение битовых полей для сохранения небольшого размера объекта не обязательно будет работать. Это зависит от того, как компилятор размещает тип.

Может возникнуть вопрос, будет ли полезны стандартный тип по **`bool`** всему всего. Многие старые шаблоны кода, такие как тип BOOL, были разработаны для решения проблем, которые позднее были решены в стандартном языке C++, поэтому переход от BOOL к **`bool`** встроенному типу является лишь одним из примеров такого изменения, которое следует выполнить после того, как вы получите код, изначально выполняющийся в новой версии.

После рассмотрения всех предупреждений, которые появляются на уровне по умолчанию (уровень 3), перейдем на уровень 4 и рассмотрим несколько дополнительных предупреждений. Первое такое предупреждение имеет следующий вид:

```Output
warning C4100: 'nTab': unreferenced formal parameter
```

Код, который создал это предупреждение, имел следующий вид.

```cpp
virtual void OnSelectTab(int nTab) {};
```

Код кажется достаточно безопасным, но так как нам требуется чистая компиляция с заданными параметрами `/W4` и `/WX`, мы просто закомментируем имя переменной, оставив ее для удобочитаемости.

```cpp
virtual void OnSelectTab(int /*nTab*/) {};
```

Другие предупреждения, которые мы получили, полезны для обычной очистки кода. Существует несколько неявных преобразований из **`int`** или **`unsigned int`** в Word (это typedef для **`unsigned short`** ). Они могут вызывать потерю данных. В таких случаях мы добавили приведение в WORD.

Другое предупреждение на уровне 4, полученное для этого кода:

```Output
warning C4211: nonstandard extension used: redefined extern to static
```

Проблема возникает при первой объявлении переменной **`extern`** , затем объявленной позднее **`static`** . Значения этих двух спецификаторов класса хранения являются взаимоисключающими, но это допускается как расширение Microsoft. Если требуется, чтобы код был переносимым в другие компиляторы, или его необходимо компилировать с параметром `/Za` (для совместимости с ANSI), нужно изменить объявления так, чтобы они соответствовали спецификаторам классов хранения.

## <a name="step-11-porting-from-mbcs-to-unicode"></a><a name="porting_to_unicode"></a>Шаг 11. Перенос из MBCS в Юникод

Обратите внимание, что в мире Windows, когда мы говорим Юникод, обычно это означает UTF-16. В других операционных системах, например в Linux, применяется UTF-8, а в Windows обычно нет. MBCS-версия MFC была признана нерекомендуемой в Visual Studio 2013 и 2015, однако не является таковой в Visual Studio 2017. При использовании Visual Studio 2013 или 2015 перед фактическим переносом кода MBCS в Юникод UTF-16 может потребоваться временное устранение предупреждений о нежелательности применения MBCS, чтобы выполнить другую работу или отложить перенос на более удобное время. В текущем коде применяется MBCS, и для продолжения работы с ним нужно установить версию ANSI/MBCS для MFC. Достаточно крупная библиотека MFC не входит в вариант установки Visual Studio по умолчанию **Разработка классических приложений на C++**, поэтому ее нужно выбрать в разделе дополнительных компонентов в установщике. См. статью [MFC MBCS DLL Add-on](../mfc/mfc-mbcs-dll-add-on.md) (Надстройка DLL MBCS MFC). После загрузки этого и перезапуска Visual Studio можно компилировать и связываться с версией многобайтовой версии MFC, но чтобы избавиться от предупреждений многобайтовой кодировки при использовании Visual Studio 2013 или 2015, следует также добавить NO_WARN_MBCS_MFC_DEPRECATION в список предопределенных макросов в разделе **препроцессора** в свойствах проекта или в начале файла заголовка *stdafx.h* или другого файла заголовков.

Теперь мы получили несколько сообщений об ошибках компоновщика.

```Output
fatal error LNK1181: cannot open input file 'mfc42d.lib'
```

Сообщение LNK1181 появляется потому, что устаревшая версия статической библиотеки для mfc включена во входные данные компоновщика. Это не требуется, так как мы можем динамически связать MFC, поэтому нам нужно просто удалить все статические библиотеки MFC из свойства **input** в разделе **компоновщика** свойств проекта. В этом проекте также используется параметр `/NODEFAULTLIB`, который вместо этого перечисляет все зависимости библиотеки.

```
msvcrtd.lib;msvcirtd.lib;kernel32.lib;user32.lib;gdi32.lib;advapi32.lib;Debug\SpyHk55.lib;%(AdditionalDependencies)
```

Теперь давайте фактически обновим старый код MBCS в Юникод. Так как это приложение Windows тесно связано с платформой рабочего стола Windows, мы будет переносить его в Юникод UTF-16, используемый в Windows. При написании кроссплатформенного кода или переноса приложения Windows на другую платформу может потребоваться рассмотреть задачу переноса в UTF-8, которая широко применяется в других операционных системах.

При переносе в Юникод UTF-16 необходимо решить, сохранить ли возможность компиляции в MBCS или нет.  Если требуется поддерживать многобайтовую кодировку, следует использовать макрос TCHAR в качестве символьного типа, который разрешается в **`char`** или **`wchar_t`** , в зависимости от того, определен ли параметр \_ MBCS или \_ Unicode во время компиляции. Переключение на TCHAR и версии TCHAR различных интерфейсов API вместо **`wchar_t`** и связанных с ним API означает, что вы можете вернуться к МНОГОбайтовой версии кода, просто определив \_ макрос MBCS, а не \_ Unicode. В дополнение к TCHAR существует несколько версий TCHAR, например широко используемые определения typedef, макросы и функции. Например, LPCTSTR вместо LPCSTR и т. д. В диалоговом окне свойств проекта в разделе **Свойства конфигурации** в подразделе **Общие** установите для свойства **Кодировка** вместо значения **Использовать набор символов MBCS** значение **Использовать набор символов Юникода**. Этот параметр влияет на то, какой макрос предварительно определен во время компиляции. Существуют два макроса: UNICODE и \_UNICODE. Свойство проекта влияет на них единообразно. В заголовках Windows используется Юникод там, где заголовки Visual C++, например MFC, используют \_UNICODE. Но, если один макрос определен, второй будет определен всегда.

Дополнительные сведения о переносе из MBCS в Юникод UTF-16 с помощью TCHAR см. в [руководстве](/previous-versions/cc194801(v=msdn.10)). Мы выбрали следующий путь. Сначала для свойства **Кодировка** мы установили значение **Использовать набор символов Юникода** и повторно построили проект.

В некоторых частях кода уже использовался TCHAR, очевидно с учетом поддержки в будущем Юникода. В других частях он не использовался. Мы искали экземпляры CHAR, которые являются **`typedef`** для **`char`** , и заменили большинство из них на TCHAR. Кроме того, выполнили поиск `sizeof(CHAR)`. Каждый раз, когда мы заменяли CHAR на TCHAR, нам обычно было нужно изменять на `sizeof(TCHAR)`, так как он часто использовался для определения количества символов в строке. Использование здесь неправильного типа не будет вызывать ошибку компилятора, поэтому данный случай рекомендуется рассмотреть более подробно.

Ошибки такого типа довольно часто происходят сразу после переключения на Юникод.

```Output
error C2664: 'int wsprintfW(LPWSTR,LPCWSTR,...)': cannot convert argument 1 from 'CHAR [16]' to 'LPWSTR'
```

Ниже приведен пример кода, который создает это:

```cpp
wsprintf(szTmp, "%d.%2.2d.%4.4d", rmj, rmm, rup);
```

Мы поместили \_T вокруг строкового литерала, чтобы устранить ошибку.

```cpp
wsprintf(szTmp, _T("%d.%2.2d.%4.4d"), rmj, rmm, rup);
```

\_Макрос T оказывает результат компиляции строкового литерала в виде **`char`** строки или **`wchar_t`** строки в зависимости от параметра MBCS или Unicode. Чтобы заменить все строки с \_T в Visual Studio, откройте окно **Быстрая замена** (сочетание клавиш **CTRL**+**F**) или **Заменить в файлах** (сочетание клавиш **CTRL**+**SHIFT**+**H**), а затем установите флажок **Использовать регулярные выражения**. Введите `((\".*?\")|('.+?'))` как искомый текст и `_T($1)` как текст для замены. Если вокруг некоторых строк макрос \_T уже имеется, эта процедура добавит его снова. В коде также могут быть случаи, где вы не хотите использовать \_T. Например, если используется `#include`, то лучше всего использовать **Заменить следующий**, а не **Заменить все**.

В заголовках Windows фактически определена функция [wsprintf](/windows/win32/api/winuser/nf-winuser-wsprintfw), но в документации ее использовать не рекомендуется, так как она может вызвать переполнение буфера. Для буфера `szTmp` размер не задан, поэтому функция не может проверить, сможет ли буфер вместить все данные, подлежащие записи в него. В следующем разделе описывается перенос в Secure CRT, в котором мы будем устранять другие подобные проблемы. Мы завершили процедуру путем замены функции на [_stprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md).

Еще одна распространенная ошибка, которую можно увидеть при преобразовании в Юникод, — это.

```Output
error C2440: '=': cannot convert from 'char *' to 'TCHAR *'
```

Код, создающий данное сообщение об ошибке, выглядит следующим образом:

```cpp
pParentNode->m_szText = new char[strTitle.GetLength() + 1];
_tcscpy(pParentNode->m_szText, strTitle);
```

Хотя `_tcscpy` используется функция, которая является функцией TCHAR strcpy для копирования строки, буфер, который был выделен, был **`char`** буфером. Его легко изменить на TCHAR.

```cpp
pParentNode->m_szText = new TCHAR[strTitle.GetLength() + 1];
_tcscpy(pParentNode->m_szText, strTitle);
```

Аналогичным образом при появлении сообщения об ошибке компилятора мы изменили LPSTR (Long Pointer to STRing — длинный указатель на строку) и LPCSTR (Long Pointer to Constant STRing — длинный указатель на константную строку) на LPTSTR (Long Pointer to TCHAR STRing — длинный указатель на строку TCHAR) и LPCTSTR (Long Pointer to Constant TCHAR STRing — длинный указатель на константную строку TCHAR) соответственно. Мы решили не выполнять такую замену с помощью функции глобального поиска и замены, так как каждую ситуацию было нужно анализировать по отдельности. В некоторых случаях **`char`** требуется версия, например при обработке определенных сообщений Windows, использующих структуры Windows с суффиксом **A** . В Windows API суффикс **A** означает ASCII или ANSI (и также применяется к многобайтовой кодировке), а суффикс **W** означает широкие символы или Юникод UTF-16. Этот шаблон именования используется в заголовках Windows, но мы также применяли его в коде Spy++, когда нам было нужно добавить версию Юникода для функции, который уже была определен только в версии MBCS.

В некоторых случаях нам пришлось заменить тип для использования версии, которая корректно разрешается (например, WNDCLASS вместо WNDCLASSA).

Во многих случаях нам было необходимо использовать универсальную версию (макрос) API-интерфейса Win32, например `GetClassName` (вместо `GetClassNameA`). В операторе переключения обработчика сообщений некоторые сообщения относятся к кодировке MBCS или Юникоду. в таких случаях нам пришлось изменить код для явного вызова версии MBCS, так как мы заменили универсальные именованные **функции на функции** , специфичные для и **w** , и добавили макрос для универсального имени, которое разрешается в правильное имя **A** или **w** в зависимости от того, определен ли Юникод.  Во многих частях кода, когда мы переключаемся на определение \_ Юникода, теперь выбрана версия W, даже если требуется **A** версия.

В нескольких частях кода потребовалось выполнить специальные действия. Использовать `WideCharToMultiByte` или `MultiByteToWideChar` нужно с осторожностью. Ниже приведен пример применения `WideCharToMultiByte`.

```cpp
BOOL C3dDialogTemplate::GetFont(CString& strFace, WORD& nFontSize)
{
  ASSERT(m_hTemplate != NULL);

  DLGTEMPLATE* pTemplate = (DLGTEMPLATE*)GlobalLock(m_hTemplate);
  if ((pTemplate->style & DS_SETFONT) == 0)
  {
    GlobalUnlock(m_hTemplate);
    return FALSE;
  }

  BYTE* pb = GetFontSizeField(pTemplate);
  nFontSize = *(WORD*)pb;
  pb += sizeof (WORD);
  WideCharToMultiByte(CP_ACP, 0, (LPCWSTR)pb, -1,
  strFace.GetBufferSetLength(LF_FACESIZE), LF_FACESIZE, NULL, NULL);
  strFace.ReleaseBuffer();
  GlobalUnlock(m_hTemplate);
  return TRUE;
}
```

Для решения этой проблемы следовало понять, что причиной таких действий была необходимость копирования широкой строки символов, представляющей имя шрифта во внутреннем буфере строки `CString`, `strFace`. Это потребовало создания немного другого кода для многобайтовых строк `CString` как для строк `CString` с расширенными символами, поэтому в данном случае мы добавили `#ifdef`.

```cpp
#ifdef _MBCS
WideCharToMultiByte(CP_ACP, 0, (LPCWSTR)pb, -1,
strFace.GetBufferSetLength(LF_FACESIZE), LF_FACESIZE, NULL, NULL);
strFace.ReleaseBuffer();
#else
wcscpy(strFace.GetBufferSetLength(LF_FACESIZE), (LPCWSTR)pb);
strFace.ReleaseBuffer();
#endif
```

Разумеется, вместо `wcscpy` мы должны были использовать более безопасную версию `wcscpy_s`. Эта задача рассматривается в следующем разделе.

В качестве проверки нашей работы необходимо **сбросить кодировку, чтобы она** **использовала многобайтовую** кодировку, и убедиться, что код по-прежнему КОМПИЛИРУЕТся с использованием MBCS и Unicode. Следует отметить, что после внесения всех этих изменений для перекомпилированного приложения нужно было выполнить полное тестирование.

В нашей работе с данным решением Spy++ среднестатистический разработчик C++ потратил бы около двух рабочих дней на преобразование кода в Юникод. Причем сюда не входит время на повторное тестирование.

## <a name="step-12-porting-to-use-the-secure-crt"></a><a name="porting_to_secure_crt"></a>Шаг 12. Перенос для использования Secure CRT

Перенос кода для использования безопасных версий (версии с суффиксом **_s** ) для функций CRT является следующим. В этом случае общая стратегия заключается в замене функции на **_s** версии, а затем, как правило, добавьте необходимые дополнительные параметры размера буфера. В большинстве случаев сделать это несложно, так как размер известен. В других случаях, когда размер не будет немедленно доступен, необходимо добавить дополнительные параметры в функцию, которая использует функцию CRT, или, возможно, проверить использование буфера назначения и узнать, какие ограничения имеют соответствующие размеры.

Visual C++ позволяет упростить процесс создания безопасного кода без добавления большого количества параметров размера, что достигается благодаря применению перегрузок шаблонов. Так как такие перегрузки являются шаблонами, они доступны только при компиляции как C++, а не как C. Spyxxhk — это проект C, поэтому данный прием для него работать не будет.  А Spyxx — нет, поэтому описанный прием можно применить. Прием заключается в добавлении подобной строки там, где будет выполняться компиляция — в любом файле проекта, например в файле stdafx.h:

```cpp
#define _CRT_SECURE_TEMPLATE_OVERLOADS 1
```

Когда вы определяете, что каждый раз, когда буфер является массивом, а не необработанным указателем, его размер определяется из типа массива и используется в качестве параметра размера, и вам не нужно его указывать. Это позволяет уменьшить степень сложности при переработке кода. По-прежнему необходимо заменить имя функции на **_s** версии, но часто это можно сделать с помощью операции поиска и замены.

Возвращаемые значения некоторых функций изменяются. Например `_itoa_s` (и `_itow_s` и макрос `_itot_s`) возвращает код ошибки (`errno_t`), а не строку. Поэтому в таких случаях следует переместить вызов в `_itoa_s` на отдельную строку и заменить его на идентификатор буфера.

Некоторые из распространенных случаев: для `memcpy` при переключении на `memcpy_s` мы часто добавляли размер структуры, в которую выполняется копирование. Аналогичным образом, для большинства строк и буферов размер массива или буфера легко определить с помощью объявления буфера или путем поиска места, в котором изначально располагался буфер. В некоторых ситуациях необходимо определить, насколько велик доступ к буферу, и если эта информация недоступна в области функции, которую вы изменяете, то ее следует добавить в качестве дополнительного параметра, и вызывающий код должен быть изменен для предоставления информации.

При использовании этих методов на преобразование кода с целью использования безопасных функций CRT ушло примерно полдня. Если вы не будете использовать перегрузки шаблонов, а будете добавлять параметры размера вручную, возможно, вам потребуется в два или три раза больше времени.

## <a name="step-13-zcforscope--is-deprecated"></a><a name="deprecated_forscope"></a>Шаг 13. /Zc:forScope использовать не рекомендуется.

Начиная с Visual C++ 6.0 компилятор соответствует текущему стандарту, который ограничивает область переменных, объявленных в цикле, самой областью цикла. Параметр компилятора [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) (**Принудительное обеспечение соответствия для области цикла** в свойствах проекта) контролирует, сообщается ли о данной ситуации как об ошибке или нет. Мы обновили наш код для обеспечения соответствия и добавили объявления сразу за пределами цикла. Во избежание внесения изменений в код этот параметр можно изменить в разделе **Язык** свойств проекта C++ на `No (/Zc:forScope-)`. Однако имейте в виду, что `/Zc:forScope-` может быть удален в будущих версиях Visual C++, поэтому в конечном итоге код будет необходимо изменить, чтобы он соответствовал стандарту.

Эти проблемы относительно несложно устранить, но, в зависимости от вашего кода, может потребоваться внесение изменений в большой объем кода. Ниже рассмотрена типичная проблема.

```cpp
int CPerfTextDataBase::NumStrings(LPCTSTR mszStrings) const
{
  for (int n = 0; mszStrings[0] != 0; n++)
  mszStrings = _tcschr(mszStrings, 0) + 1;
  return(n);
}
```

Этот код создает ошибку:

```Output
'n': undeclared identifier
```

Ошибка возникает, так как компилятор не принял параметр компилятора, разрешивший код, который больше не соответствует стандарту C++. В соответствии со стандартом объявление переменной в цикле ограничивает свою область только пределами цикла, поэтому для использования счетчика цикла вне цикла обычно требуется, чтобы объявление счетчика также было бы перенесено за пределы цикла, как показано в следующем измененном коде:

```cpp
int CPerfTextDataBase::NumStrings(LPCTSTR mszStrings) const
{
  int n;
  for (n = 0; mszStrings[0] != 0; n++)
  mszStrings = _tcschr(mszStrings, 0) + 1;
  return(n);
}
```

## <a name="summary"></a>Итоги

Процедура переноса Spy++ из исходного кода Visual C++ 6.0 в последний компилятор заняла около 20 часов всего процесса кодирования, который продолжался примерно одну неделю. Мы выполнили обновление непосредственно через восемь версий продукта, с Visual Studio 6.0 до Visual Studio 2015. Теперь это рекомендуемый подход для всех обновлений в больших и маленьких проектах.

## <a name="see-also"></a>См. также раздел

[Перенос и обновление: примеры и конкретные случаи](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Previous case study: COM Spy](../porting/porting-guide-com-spy.md) (Предыдущий пример: COM Spy)
