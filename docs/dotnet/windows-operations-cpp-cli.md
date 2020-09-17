---
title: Операции Windows (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows [C++], Windows-specific tasks
- .NET Framework [C++], Windows operations
- Visual C++, Windows operations
- Windows operations [C++]
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
- Visual C++, user interactive state
- user interactive state
- Visual C++, reading from Windows Registry
- registry, reading
- performance counters
- performance counters, reading Windows performance counters
- performance monitoring, Windows performance counters
- performance, counters
- counters, reading Windows performance counters
- performance
- performance monitoring
- text, retrieving from Clipboard
- Clipboard, retrieving text
- current user names
- user names, retrieving
- UserName string
- .NET Framework, version
- Version property, retrieving .NET Framework version
- computer name, retrieving
- machine name, retrieving
- computer name
- Windows [C++], version
- Windows [C++], retrieving version using Visual C++
- time, elapsed since startup
- counters, elapsed time
- startup, time elapsed since
- tick counts
- startup
- text, storing in Clipboard
- Clipboard, storing text
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: b9a75cb4-0589-4d5b-92cb-5e8be42b4ac0
ms.openlocfilehash: 99fce804ad30e01bdbaa99b1636a5238ff535f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371774"
---
# <a name="windows-operations-ccli"></a>Операции Windows (C++/CLI)

Демонстрирует различные задачи, связанные с Windows, с помощью Windows SDK.

Ниже приведены следующие темы, демонстрирующие различные операции Windows, выполняемые с помощью Windows SDK с использованием визуального СЗ.

## <a name="determine-if-shutdown-has-started"></a><a name="determine_shutdown"></a>Определить, запущено ли завершение работы

Следующий пример кода показывает, как определить, прекращается ли приложение или рамочная .NET в настоящее время. Это полезно для доступа к статическим элементам в рамочном режиме .NET, поскольку во время завершения работы эти конструкции завершаются системой и не могут быть надежно использованы. Проверив свойство <xref:System.Environment.HasShutdownStarted%2A> во-первых, вы можете избежать потенциальных сбоев, не доступ к этим элементам.

### <a name="example"></a>Пример

```cpp
// check_shutdown.cpp
// compile with: /clr
using namespace System;
int main()
{
   if (Environment::HasShutdownStarted)
      Console::WriteLine("Shutting down.");
   else
      Console::WriteLine("Not shutting down.");
   return 0;
}
```

## <a name="determine-the-user-interactive-state"></a><a name="determine_user"></a>Определение интерактивного состояния пользователя

Следующий пример кода показывает, как определить, выполняется ли код в интерактивном пользовательском контексте. Если <xref:System.Environment.UserInteractive%2A> это неверно, то код работает как процесс службы или внутри веб-приложения, и в этом случае вы не должны пытаться взаимодействовать с пользователем.

### <a name="example"></a>Пример

```cpp
// user_interactive.cpp
// compile with: /clr
using namespace System;

int main()
{
   if ( Environment::UserInteractive )
      Console::WriteLine("User interactive");
   else
      Console::WriteLine("Noninteractive");
   return 0;
}
```

## <a name="read-data-from-the-windows-registry"></a><a name="read_registry"></a>Чтение данных из реестра Windows

В следующем примере <xref:Microsoft.Win32.Registry.CurrentUser> кода используется ключ для чтения данных из реестра Windows. Сначала подключи перечисляются с помощью <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> метода, а затем подключка <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> идентификационных данных открывается с помощью метода. Как и корневые клавиши, каждая подключка представлена классом. <xref:Microsoft.Win32.RegistryKey> Наконец, <xref:Microsoft.Win32.RegistryKey> новый объект используется для перечисления пар ключей/значений.

### <a name="example"></a>Пример

```cpp
// registry_read.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main( )
{
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );

   Console::WriteLine("Subkeys within CurrentUser root key:");
   for (int i=0; i<key->Length; i++)
   {
      Console::WriteLine("   {0}", key[i]);
   }

   Console::WriteLine("Opening subkey 'Identities'...");
   RegistryKey^ rk = nullptr;
   rk = Registry::CurrentUser->OpenSubKey("Identities");
   if (rk==nullptr)
   {
      Console::WriteLine("Registry key not found - aborting");
      return -1;
   }

   Console::WriteLine("Key/value pairs within 'Identities' key:");
   array<String^>^ name = rk->GetValueNames( );
   for (int i=0; i<name->Length; i++)
   {
      String^ value = rk->GetValue(name[i])->ToString();
      Console::WriteLine("   {0} = {1}", name[i], value);
   }

   return 0;
}
```

### <a name="remarks"></a>Примечания

Класс <xref:Microsoft.Win32.Registry> является всего лишь контейнером <xref:Microsoft.Win32.RegistryKey>для статических экземпляров . Каждый экземпляр представляет собой корневой узлы реестра. Экземпляры, <xref:Microsoft.Win32.Registry.ClassesRoot> <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, <xref:Microsoft.Win32.Registry.Users>и .

Помимо статики, объекты в <xref:Microsoft.Win32.Registry> классе читаются только для чтения. Кроме того, экземпляры <xref:Microsoft.Win32.RegistryKey> класса, созданные для доступа к содержимому объектов реестра, также читаются. Например, как переопределить это поведение, [см.](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)

Есть два дополнительных <xref:Microsoft.Win32.Registry> объекта <xref:Microsoft.Win32.Registry.DynData> в <xref:Microsoft.Win32.Registry.PerformanceData>классе: и . Оба экземпляра являются <xref:Microsoft.Win32.RegistryKey> экземплярами класса. Объект <xref:Microsoft.Win32.Registry.DynData> содержит динамическую информацию реестра, которая поддерживается только в Windows 98 и Windows Me. Объект <xref:Microsoft.Win32.Registry.PerformanceData> может использоваться для доступа к информации о счетчике производительности для приложений, которые используют систему мониторинга производительности Windows. Узел <xref:Microsoft.Win32.Registry.PerformanceData> представляет информацию, которая на самом деле не хранится в реестре и поэтому не может быть просмотрена с помощью Regedit.exe.

## <a name="read-windows-performance-counters"></a><a name="read_performance"></a>Читать счетчики производительности Windows

Некоторые приложения и подсистемы Windows предоставляют данные о производительности через систему производительности Windows. Эти счетчики могут быть <xref:System.Diagnostics.PerformanceCounterCategory> доступны <xref:System.Diagnostics.PerformanceCounter> с помощью и <xref:System.Diagnostics?displayProperty=fullName> классов, которые находятся в пространстве имен.

В следующем примере кода эти классы используются для извлечения и отображения счетчика, обновляемого Windows, чтобы указать процент времени, в течение которого процессор занят.

> [!NOTE]
> В этом примере требуются права администратора для работы в Windows Vista.

### <a name="example"></a>Пример

```cpp
// processor_timer.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Diagnostics;
using namespace System::Timers;

ref struct TimerObject
{
public:
   static String^ m_instanceName;
   static PerformanceCounter^ m_theCounter;

public:
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)
   {
      try
      {
         Console::WriteLine("CPU time used: {0,6} ",
          m_theCounter->NextValue( ).ToString("f"));
      }
      catch(Exception^ e)
      {
         if (dynamic_cast<InvalidOperationException^>(e))
         {
            Console::WriteLine("Instance '{0}' does not exist",
                  m_instanceName);
            return;
         }
         else
         {
            Console::WriteLine("Unknown exception... ('q' to quit)");
            return;
         }
      }
   }
};

int main()
{
   String^ objectName = "Processor";
   String^ counterName = "% Processor Time";
   String^ instanceName = "_Total";

   try
   {
      if ( !PerformanceCounterCategory::Exists(objectName) )
      {
         Console::WriteLine("Object {0} does not exist", objectName);
         return -1;
      }
   }
   catch (UnauthorizedAccessException ^ex)
   {
      Console::WriteLine("You are not authorized to access this information.");
      Console::Write("If you are using Windows Vista, run the application with ");
      Console::WriteLine("administrative privileges.");
      Console::WriteLine(ex->Message);
      return -1;
   }

   if ( !PerformanceCounterCategory::CounterExists(
          counterName, objectName) )
   {
      Console::WriteLine("Counter {0} does not exist", counterName);
      return -1;
   }

   TimerObject::m_instanceName = instanceName;
   TimerObject::m_theCounter = gcnew PerformanceCounter(
          objectName, counterName, instanceName);

   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);
   aTimer->Interval = 1000;
   aTimer->Enabled = true;
   aTimer->AutoReset = true;

   Console::WriteLine("reporting CPU usage for the next 10 seconds");
   Thread::Sleep(10000);
   return 0;
}
```

## <a name="retrieve-text-from-the-clipboard"></a><a name="retrieve_text"></a>Извлекать текст из буфера обмена

В следующем примере <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> кода функция члена используется <xref:System.Windows.Forms.IDataObject> для возврата указателя в интерфейс. Этот интерфейс может быть запрошен для формата данных и использован для получения фактических данных.

### <a name="example"></a>Пример

```cpp
// read_clipboard.cpp
// compile with: /clr
#using <system.dll>
#using <system.Drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main( )
{
   IDataObject^ data = Clipboard::GetDataObject( );

   if (data)
   {
      if (data->GetDataPresent(DataFormats::Text))
      {
         String^ text = static_cast<String^>
           (data->GetData(DataFormats::Text));
         Console::WriteLine(text);
      }
      else
         Console::WriteLine("Nontext data is in the Clipboard.");
   }
   else
   {
      Console::WriteLine("No data was found in the Clipboard.");
   }

   return 0;
}
```

## <a name="retrieve-the-current-username"></a><a name="retrieve_current"></a>Retrieve текущее имя пользователя

Следующий пример кода демонстрирует поиск текущего имени пользователя (имя пользователя, вскакиваемого в Windows). Имя хранится в <xref:System.Environment.UserName%2A> строке, которая <xref:System.Environment> определяется в пространстве имен.

### <a name="example"></a>Пример

```cpp
// username.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);
   return 0;
}
```

## <a name="retrieve-the-net-framework-version"></a><a name="retrieve_dotnet"></a>Извлекай рамочную версию .NET

Следующий пример кода показывает, как определить версию установленной <xref:System.Environment.Version%2A> в настоящее время рамочной программы .NET с свойством, который является указателем на <xref:System.Version> объект, содержащий информацию о версии.

### <a name="example"></a>Пример

```cpp
// dotnet_ver.cpp
// compile with: /clr
using namespace System;
int main()
{
   Version^ version = Environment::Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write(".NET Framework version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
            build, major, minor, revision);
   }
   return 0;
}
```

## <a name="retrieve-the-local-machine-name"></a><a name="retrieve_local"></a>Получить название локальной машины

Следующий пример кода демонстрирует поиск локального имени машины (имя компьютера, как он появляется в сети). Вы можете достичь этого, получив <xref:System.Environment.MachineName%2A> строку, <xref:System.Environment> которая определяется в пространстве имен.

### <a name="example"></a>Пример

```cpp
// machine_name.cpp
// compile with: /clr
using namespace System;

int main()
{
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);
   return 0;
}
```

## <a name="retrieve-the-windows-version"></a><a name="retrieve_version"></a>Извлечения версии для Windows

Следующий пример кода показывает, как получить информацию о платформе и версии текущей операционной системы. Эта информация хранится в свойстве <xref:System.Environment.OSVersion%2A?displayProperty=fullName> и состоит из перечисления, которое <xref:System.Environment.Version%2A> описывает версию Windows в широком смысле и объект, который содержит точную сборку операционной системы.

### <a name="example"></a>Пример

```cpp
// os_ver.cpp
// compile with: /clr
using namespace System;

int main()
{
   OperatingSystem^ osv = Environment::OSVersion;
   PlatformID id = osv->Platform;
   Console::Write("Operating system: ");

   if (id == PlatformID::Win32NT)
      Console::WriteLine("Win32NT");
   else if (id == PlatformID::Win32S)
      Console::WriteLine("Win32S");
   else if (id == PlatformID::Win32Windows)
      Console::WriteLine("Win32Windows");
   else
      Console::WriteLine("WinCE");

   Version^ version = osv->Version;
   if (version)
   {
      int build = version->Build;
      int major = version->Major;
      int minor = version->Minor;
      int revision = Environment::Version->Revision;
      Console::Write("OS Version: ");
      Console::WriteLine("{0}.{1}.{2}.{3}",
                   build, major, minor, revision);
   }

   return 0;
}
```

## <a name="retrieve-time-elapsed-since-startup"></a><a name="retrieve_time"></a>Время получения, прошедшее с момента запуска

Следующий пример кода показывает, как определить количество тиков, или количество миллисекунд, которые прошли с момента запуска Windows. Это значение хранится <xref:System.Environment.TickCount%2A?displayProperty=fullName> в члене и, поскольку оно является 32-битным значением, сбрасывается до нуля примерно каждые 24,9 дня.

### <a name="example"></a>Пример

```cpp
// startup_time.cpp
// compile with: /clr
using namespace System;

int main( )
{
   Int32 tc = Environment::TickCount;
   Int32 seconds = tc / 1000;
   Int32 minutes = seconds / 60;
   float hours = static_cast<float>(minutes) / 60;
   float days = hours / 24;

   Console::WriteLine("Milliseconds since startup: {0}", tc);
   Console::WriteLine("Seconds since startup: {0}", seconds);
   Console::WriteLine("Minutes since startup: {0}", minutes);
   Console::WriteLine("Hours since startup: {0}", hours);
   Console::WriteLine("Days since startup: {0}", days);

   return 0;
}
```

## <a name="store-text-in-the-clipboard"></a><a name="store_text"></a>Храните текст в буфере обмена

В следующем примере <xref:System.Windows.Forms.Clipboard> кода объект, определенный <xref:System.Windows.Forms> в пространстве имен, для хранения строки. Этот объект предоставляет две <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>функции члена: и . Данные хранятся в Clipboard, отправляя любой объект, полученный из <xref:System.Object> <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.

### <a name="example"></a>Пример

```cpp
// store_clipboard.cpp
// compile with: /clr
#using <System.dll>
#using <System.Drawing.dll>
#using <System.Windows.Forms.dll>

using namespace System;
using namespace System::Windows::Forms;

[STAThread] int main()
{
   String^ str = "This text is copied into the Clipboard.";

   // Use 'true' as the second argument if
   // the data is to remain in the clipboard
   // after the program terminates.
   Clipboard::SetDataObject(str, true);

   Console::WriteLine("Added text to the Clipboard.");

   return 0;
}
```

## <a name="write-data-to-the-windows-registry"></a><a name="write_data"></a>Запись данных в реестр Windows

В следующем примере <xref:Microsoft.Win32.Registry.CurrentUser> кода используется ключ для создания <xref:Microsoft.Win32.RegistryKey> допустимого экземпляра класса, соответствующего ключу **Программного обеспечения.** Затем <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> метод используется для создания нового ключа и добавления к парам ключей/значений.

### <a name="example"></a>Пример

```cpp
// registry_write.cpp
// compile with: /clr
using namespace System;
using namespace Microsoft::Win32;

int main()
{
   // The second OpenSubKey argument indicates that
   // the subkey should be writable.
   RegistryKey^ rk;
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);
   if (!rk)
   {
      Console::WriteLine("Failed to open CurrentUser/Software key");
      return -1;
   }

   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");
   if (!nk)
   {
      Console::WriteLine("Failed to create 'NewRegKey'");
      return -1;
   }

   String^ newValue = "NewValue";
   try
   {
      nk->SetValue("NewKey", newValue);
      nk->SetValue("NewKey2", 44);
   }
   catch (Exception^)
   {
      Console::WriteLine("Failed to set new values in 'NewRegKey'");
      return -1;
   }

   Console::WriteLine("New key created.");
   Console::Write("Use REGEDIT.EXE to verify ");
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");
   return 0;
}
```

### <a name="remarks"></a>Примечания

Вы можете использовать рамочку .NET <xref:Microsoft.Win32.Registry> <xref:Microsoft.Win32.RegistryKey> для доступа к реестру <xref:Microsoft.Win32> с классами и классами, которые определяются в пространстве имен. Класс **реестра** — это контейнер для <xref:Microsoft.Win32.RegistryKey> статических экземпляров класса. Каждый экземпляр представляет собой корневой узлы реестра. Экземпляры, <xref:Microsoft.Win32.Registry.ClassesRoot> <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, <xref:Microsoft.Win32.Registry.Users>и .

## <a name="related-sections"></a>Связанные разделы

<xref:System.Environment>

## <a name="see-also"></a>См. также раздел

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
