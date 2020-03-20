---
title: Использование наборов правил для задания выполняемых правил C++
ms.date: 04/28/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.native
ms.openlocfilehash: 5cf0f88c6937f4c1609a29fd618af0fdadad4437
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2020
ms.locfileid: "79467123"
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>Использование наборов правил для указания C++ правил для выполнения

В Visual Studio можно создать и изменить набор настраиваемых *правил* для удовлетворения конкретных потребностей проекта, связанных с анализом кода. Наборы правил по умолчанию хранятся в `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`.

**Visual Studio 2017 версии 15,7 и более поздних версий:** Пользовательские наборы правил можно создавать с помощью любого текстового редактора и применять их в сборках из командной строки независимо от используемой системы сборки. Дополнительные сведения см. в разделе [/Analyze: RuleSet](/cpp/build/reference/analyze-code-analysis).

Чтобы создать настраиваемый C++ набор правил в Visual Studio, в интегрированнойC++ среде разработки Visual Studio должен быть открыт проект C/. Затем вы открываете стандартный набор правил в редакторе набора правил, а затем добавляете или удаляете определенные правила и при необходимости изменяете действие, которое происходит, когда анализ кода определит, что правило нарушено.

Чтобы создать новый настраиваемый набор правил, сохраните его с новым именем файла. Настраиваемый набор правил автоматически назначается проекту.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Создание настраиваемого правила на основе одного существующего набора правил

1. В обозреватель решений откройте контекстное меню проекта и выберите пункт **Свойства**.

1. На вкладке **Свойства** выберите **анализ кода**.

1. В раскрывающемся списке **набор правил** выполните одно из следующих действий.

   - Выберите набор правил, который требуется настроить.

     \- или -

   - Выберите **\<обзор... >** , чтобы указать существующий набор правил, отсутствующий в списке.

1. Нажмите кнопку **Открыть** , чтобы отобразить правила в редакторе набора правил.

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Изменение набора правил в редакторе набора правил

- Чтобы изменить отображаемое имя набора правил, в меню **вид** выберите пункт **окно свойств**. Введите отображаемое имя в поле **имя** . Обратите внимание, что отображаемое имя может отличаться от имени файла.

- Чтобы добавить все правила группы в настраиваемый набор правил, установите флажок для группы. Чтобы удалить все правила группы, снимите флажок.

- Чтобы добавить определенное правило в набор настраиваемых правил, установите флажок для этого правила. Чтобы удалить правило из набора правил, снимите флажок.

- Чтобы изменить действие, выполняемое при нарушении правила анализа кода, выберите поле **действия** для правила и выберите одно из следующих значений:

     **Предупреждение** — выдает предупреждение.

     **Ошибка** -выдает ошибку.

     **Info** — создает сообщение.

     **Нет** — отключает правило. Это действие аналогично удалению правила из набора правил.

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Группирование, фильтрация или изменение полей в редакторе набора правил с помощью панели инструментов редактора набора правил

- Чтобы развернуть правила во всех группах, выберите **Развернуть все**.

- Чтобы свернуть правила во всех группах, выберите **Свернуть все**.

- Чтобы изменить поле, по которому группируются правила, выберите поле в списке **Группировать по** . Чтобы отобразить правила без группировки, выберите **\<None >** .

- Чтобы добавить или удалить поля в столбцах правил, выберите **Параметры столбцов**.

- Чтобы скрыть правила, которые не применяются к текущему решению, выберите **Скрыть правила, которые не применяются к текущему решению**.

- Чтобы переключиться между отображением и скрытием правил, которым назначено действие ошибка, выберите **Показать правила, которые могут формировать ошибки анализа кода**.

- Чтобы переключиться между отображением и скрытием правил, которым назначено действие предупреждение, выберите **Показать правила, которые могут формировать предупреждения анализа кода**.

- Чтобы переключиться между отображением и скрытием правил, которым назначено действие **нет** , выберите **Показать правила, которые не включены**.

- Чтобы добавить или удалить наборы правил Майкрософт по умолчанию для текущего набора правил, выберите **Добавить или удалить дочерние наборы правил**.

## <a name="to-create-a-rule-set-in-a-text-editor"></a>Создание набора правил в текстовом редакторе

Вы можете создать настраиваемый набор правил в текстовом редакторе, сохранить его в любом расположении с расширением `.ruleset` и применить в с параметром компилятора [/Analyze: RuleSet](/cpp/build/reference/analyze-code-analysis) .

В следующем примере показан базовый файл набора правил, который можно использовать в качестве отправной точки:

::: moniker range="<=vs-2017"

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end

::: moniker range=">=vs-2019"

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="16.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end