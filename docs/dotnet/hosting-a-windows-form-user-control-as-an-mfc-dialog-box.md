---
title: Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: 7fc2aad1e0a550fb8f22b311518ae9fb16c076a5
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "79544799"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC

MFC предоставляет класс шаблона [квинформсдиалог](../mfc/reference/cwinformsdialog-class.md) , чтобы можно было разместить Windows Forms пользовательский элемент управления (<xref:System.Windows.Forms.UserControl>) в модальном или немодальном диалоговом окне MFC. `CWinFormsDialog` является производным от класса MFC класс [CDialog](../mfc/reference/cdialog-class.md), поэтому диалоговое окно можно запустить как модальное или немодальное.

Процесс, который `CWinFormsDialog` использует для размещения пользовательского элемента управления, аналогичен описанному в разделе [Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md). Однако `CWinFormsDialog` управляет инициализацией и размещением пользовательского элемента управления, чтобы его не нужно было программировать вручную.

Пример приложения, в котором показаны Windows Forms, используемые в MFC, см. в разделе [Интеграция MFC и Windows Forms](https://www.microsoft.com/download/details.aspx?id=2113).

### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC

1. Создайте проект приложения MFC.

   В меню **файл** выберите пункт **создать**, а затем выберите пункт **проект**. В папке **визуальные элементы C++**  выберите **приложение MFC**.

   В поле **имя** введите `MFC03` и измените параметр решения, чтобы добавить его **в решение**. Нажмите кнопку **ОК**.

   В **мастере приложений MFC**примите все значения по умолчанию и нажмите кнопку **Готово**. При этом создается приложение MFC с интерфейсом нескольких документов.

1. Настройте проект.

   В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **MFC03** и выберите пункт **Свойства**. Откроется диалоговое окно **страницы свойств** .

   В диалоговом окне **страницы свойств** в элементе управления дерево **свойств конфигурации** выберите **Общие**, а затем в разделе **проекты по умолчанию** установите **поддержку** общеязыковой среды выполнения в среде CLR **(/CLR)** . Нажмите кнопку **ОК**.

1. Добавьте ссылку на элемент управления .NET.

   В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **MFC03** и выберите **добавить**, **ссылки**. На **странице свойств**щелкните **Добавить новую ссылку**, выберите WindowsControlLibrary1 (на вкладке **проекты** ) и нажмите кнопку **ОК**. В результате будет добавлена ссылка в виде параметра компилятора [/Fu](../build/reference/fu-name-forced-hash-using-file.md) , чтобы программа была скомпилирована. Он также копирует файл WindowsControlLibrary1. dll в каталог проекта `MFC03`, чтобы программа запускалась.

1. Добавьте `#include <afxwinforms.h>` в *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях) в конце существующих инструкций `#include`.

1. Добавьте новый класс, подклассом `CDialog`.

   Щелкните правой кнопкой мыши имя проекта и добавьте класс MFC (с именем Чостфорвинформ), который подклассировать `CDialog`. Так как не требуется ресурс диалогового окна, можно удалить идентификатор ресурса (выберите **представление ресурсов**, разверните папку **диалогового окна** и удалите ресурс `IDD_HOSTFORWINFORM`.  Затем удалите все ссылки на идентификатор в коде.)

1. Замените `CDialog` в файлах Чостфорвинформ.h и Чостфорвинформ. cpp на `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.

1. Вызовите DoModal для класса Чостфорвинформ.

   В MFC03. cpp добавьте `#include "HostForWinForm.h"`.

   Перед оператором Return в определении CMFC03App:: InitInstance добавьте:

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. Постройте и запустите проект.

   В меню **Сборка** выберите **Построить решение**.

   В меню **Отладка** выберите команду **Запуск без отладки**.

   Далее будет добавлен код для отслеживания состояния элемента управления в Windows Forms из приложения MFC.

1. Добавьте обработчик для Онинитдиалог.

   Отображение окна **Свойства** (F4). В **представление классов**выберите чостфорвинформ. В окне **Свойства** выберите переопределения и в строке для онинитдиалог щелкните столбец слева и выберите \< Добавить >. В Чостфорвинформ.h будет добавлена следующая строка:

    ```cpp
    virtual BOOL OnInitDialog();
    ```

1. Определите Онинитдиалог (в Чостфорвинформ. cpp) следующим образом:

    ```cpp
    BOOL CHostForWinForm::OnInitDialog() {
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);
       return TRUE;
    }
    ```

1. Затем добавьте обработчик OnButton1. Добавьте следующие строки в общедоступный раздел класса Чостфорвинформ в Чостфорвинформ.h:

    ```cpp
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );

    BEGIN_DELEGATE_MAP( CHostForWinForm )
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );
    END_DELEGATE_MAP()
    ```

   В Чостфорвинформ. cpp добавьте следующее определение:

    ```cpp
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )
    {
       System::Windows::Forms::MessageBox::Show("test");
    }
    ```

1. Постройте и запустите проект. При нажатии кнопки, которая находится в форме Windows Forms, будет запущен код в приложении MFC.

    Далее вы добавите код для вывода из библиотеки MFC в текстовое поле в форме Windows.

1. В разделе public класса Чостфорвинформ в Чостфорвинформ.h добавьте следующее объявление:

    ```cpp
    CString m_sEditBoxOnWinForm;
    ```

1. В определении DoDataExchange в Чостфорвинформ. cpp добавьте в конец функции следующие три строки:

    ```cpp
    if (pDX->m_bSaveAndValidate)
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);
    else
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);
    ```

1. В определении OnButton1 в Чостфорвинформ. cpp добавьте в конец функции следующие три строки:

    ```cpp
    this->UpdateData(TRUE);
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);
    System::Windows::Forms::MessageBox::Show(z);
    ```

1. Постройте и запустите проект.

## <a name="see-also"></a>См. также:

<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
[с помощью пользовательского элемента управления формы Windows в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)
