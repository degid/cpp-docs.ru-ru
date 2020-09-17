---
title: Служебные функции HTTP библиотеки ATL
ms.date: 11/04/2016
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
ms.openlocfilehash: d2e30f940ded0bf355000cd42ff46a67662b54f5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833989"
---
# <a name="atl-http-utility-functions"></a>Служебные функции HTTP библиотеки ATL

Эти функции поддерживают обработку URL-адресов.

|Функция|Описание|
|-|-|
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Каноникализес URL-адрес, который включает преобразование недопустимых символов и пробелов в управляющие последовательности.|
|[AtlCombineUrl](#atlcombineurl)|Объединяет базовый URL-адрес и относительный URL-адрес в один канонический URL-адрес.|
|[AtlEscapeUrl](#atlescapeurl)|Преобразует все ненадежные символы в escape-последовательности.|
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Возвращает номер порта по умолчанию, связанный с определенным протоколом или схемой Интернета.|
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Определяет, является ли символ защищенным для использования в URL-адресе.|
|[AtlUnescapeUrl](#atlunescapeurl)|Преобразует экранированные символы обратно в исходные значения.|
|[RGBToHtml](#rgbtohtml)|Преобразует значение [COLORREF](/windows/win32/gdi/colorref) в HTML-текст, соответствующий значению цвета.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

## <a name="atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a> атлканоникализеурл

Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности.

```cpp
inline BOOL AtlCanonicalizeUrl(
   LPCTSTR szUrl,
   LPTSTR szCanonicalized,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*сзурл*<br/>
URL-адрес для канонизации.

*сзканоникализед*<br/>
Выделенный вызывающим объектом буфер для получения канонического URL-адреса.

*пдвмаксленгс*<br/>
Указатель на переменную, которая содержит длину в символах *сзканоникализед*. Если функция завершается с ошибкой, переменная получает число символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая пробел для завершающего нуль-символа.

*dwFlags*<br/>
ATL_URL флаги, управляющие поведением этой функции.

- ATL_URL_BROWSER_MODE не кодирует и не декодировать символы после "#" или "?" и не удаляет конечные пробелы после "?". Если это значение не указано, то весь URL-адрес кодируется, а конечные пробелы удаляются.

- ATL_URL_DECODE преобразует все последовательности% XX в символы, включая escape-последовательности, перед синтаксическим анализом URL.

- ATL_URL_ENCODE_PERCENT кодирует все обнаруженные знаки процента. По умолчанию знаки процента не кодируются.

- ATL_URL_ENCODE_SPACES_ONLY кодирует только пробелы.

- ATL_URL_ESCAPE преобразует все escape-последовательности (% XX) в соответствующие символы.

- ATL_URL_NO_ENCODE не преобразует ненадежные символы в escape-последовательности.

- ATL_URL_NO_META не удаляет в URL-адресе метаданные (например, "." и "..").

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Ведет себя как текущая версия [интернетканоникализеурл](/windows/win32/api/wininet/nf-wininet-internetcanonicalizeurlw) , но не требует установки WinInet или Internet Explorer.

## <a name="atlcombineurl"></a><a name="atlcombineurl"></a> атлкомбинеурл

Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес.

```cpp
inline BOOL AtlCombineUrl(
   LPCTSTR szBaseUrl,
   LPCTSTR szRelativeUrl,
   LPTSTR szBuffer,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*сзбасеурл*<br/>
Базовый URL.

*сзрелативеурл*<br/>
URL-адрес относительно базового URL-адреса.

*сзбуффер*<br/>
Выделенный вызывающим объектом буфер для получения канонического URL-адреса.

*пдвмаксленгс*<br/>
Указатель на переменную, которая содержит длину в символах *сзбуффер*. Если функция завершается с ошибкой, переменная получает число символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая пробел для завершающего нуль-символа.

*dwFlags*<br/>
Флаги, управляющие поведением этой функции. См. [атлканоникализеурл](#atlcanonicalizeurl).

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Ведет себя как текущая версия [интернеткомбинеурл](/windows/win32/api/wininet/nf-wininet-internetcombineurlw) , но не требует установки WinInet или Internet Explorer.

## <a name="atlescapeurl"></a><a name="atlescapeurl"></a> атлескапеурл

Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности.

```cpp
inline BOOL AtlEscapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();

inline BOOL AtlEscapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*лпсзстрингин*<br/>
URL-адрес для преобразования.

*лпсзстрингаут*<br/>
Выделенный вызывающим объектом буфер, в который будет записан Преобразованный URL-адрес.

*пдвстрлен*<br/>
Указатель на переменную типа DWORD. Если функция завершается с ошибкой, *пдвстрлен* получает количество символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая пробел для завершающего нуль-символа. При использовании версии этого метода для расширенных символов *пдвстрлен* получает необходимое количество символов, а не число байтов.

*двмаксленгс*<br/>
Размер буфера *лпсзстрингаут*.

*dwFlags*<br/>
ATL_URL флаги, управляющие поведением этой функции. Возможные значения см. в разделе [атлканоникализеурл](#atlcanonicalizeurl) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

## <a name="atlgetdefaulturlport"></a><a name="atlgetdefaulturlport"></a> атлжетдефаултурлпорт

Вызывайте эту функцию для получения номера порта по умолчанию, связанного с определенным интернет-протоколом или схемой.

```cpp
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();
```

### <a name="parameters"></a>Параметры

*m_nScheme*<br/>
Значение [ATL_URL_SCHEME](atl-url-scheme-enum.md) , идентифицирующее схему, для которой требуется получить номер порта.

### <a name="return-value"></a>Возвращаемое значение

[ATL_URL_PORT](atl-typedefs.md#atl_url_port) , связанная с указанной схемой, или ATL_URL_INVALID_PORT_NUMBER, если схема не распознана.

## <a name="atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a> атлисунсафеурлчар

Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.

```cpp
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();
```

### <a name="parameters"></a>Параметры

*чин*<br/>
Символ, проверяемый на безопасность.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если входной символ является ненадежным, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Символы, которые не должны использоваться в URL-адресах, можно проверить с помощью этой функции и преобразовать с помощью [атлканоникализеурл](#atlcanonicalizeurl).

## <a name="atlunescapeurl"></a><a name="atlunescapeurl"></a> атлунескапеурл

Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения.

```cpp
inline BOOL AtlUnescapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();

inline BOOL AtlUnescapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();
```

### <a name="parameters"></a>Параметры

*лпсзстрингин*<br/>
URL-адрес для преобразования.

*лпсзстрингаут*<br/>
Выделенный вызывающим объектом буфер, в который будет записан Преобразованный URL-адрес.

*пдвстрлен*<br/>
Указатель на переменную типа DWORD. Если функция завершается с ошибкой, переменная получает число символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая пробел для завершающего нуль-символа.

*двмаксленгс*<br/>
Размер буфера *лпсзстрингаут*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Отменяет процесс преобразования, примененный функцией [атлескапеурл](#atlescapeurl).

## <a name="rgbtohtml"></a><a name="rgbtohtml"></a> ргбтохтмл

Преобразует значение [COLORREF](/windows/win32/gdi/colorref) в HTML-текст, соответствующий значению цвета.

```cpp
bool inline RGBToHtml(
   COLORREF color,
   LPTSTR pbOut,
   long nBuffer);
```

### <a name="parameters"></a>Параметры

*color*<br/>
Значение цвета RGB.

*пбаут*<br/>
Выделенный вызывающим объектом буфер для получения текста для значения цвета HTML. В буфере должно быть по крайней мере 8 символов, включая пробел для нулевого символа конца строки).

*нбуффер*<br/>
Размер (в байтах) буфера (включая пробел для символа завершения null).

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Значение цвета HTML — это знак решетки, за которым следует 6-значное шестнадцатеричное значение, использующее 2 цифры для каждого красного, зеленого и синего компонентов цвета (например, #FFFFFF является белым).

## <a name="systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a> системтиметохттпдате

Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.

```cpp
inline void SystemTimeToHttpDate(
   const SYSTEMTIME& st,
   CStringA& strTime);
```

### <a name="parameters"></a>Параметры

*день*<br/>
Системное время для получения в виде строки формата HTTP.

*стртиме*<br/>
Ссылка на строковую переменную для получения даты и времени HTTP, как определено в RFC 2616 ( [https://www.ietf.org/rfc/rfc2616.txt](https://www.ietf.org/rfc/rfc2616.txt) ) и rfc 1123 ( [https://www.ietf.org/rfc/rfc1123.txt](https://www.ietf.org/rfc/rfc1123.txt) ).

## <a name="see-also"></a>См. также раздел

[Концепции](../active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl-com-desktop-components.md)<br/>
[интернетканоникализеурл](/windows/win32/api/wininet/nf-wininet-internetcanonicalizeurlw)
