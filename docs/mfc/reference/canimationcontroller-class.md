---
title: Класс CAnimationController
ms.date: 03/27/2019
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
ms.openlocfilehash: 489e931c4063e7bf06ace1cb130b9891253c94d4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750175"
---
# <a name="canimationcontroller-class"></a>Класс CAnimationController

Реализует контроллер анимации, который обеспечивает центральный интерфейс для создания анимации и управления ею.

## <a name="syntax"></a>Синтаксис

```
class CAnimationController : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationController::CAnimationController](#canimationcontroller)|Строит контроллер анимации.|
|[CAnimationController:::CAnimationController](#_dtorcanimationcontroller)|Деструктор Вызывается при уничтожении объекта контроллера анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationController::AddAnimationObject](#addanimationobject)|Добавляет объект анимации в группу, которая принадлежит контроллеру анимации.|
|[КанимацияКонтроллер:AddKeyframeToGroup](#addkeyframetogroup)|Добавляет в группу ключевой элемент.|
|[CAnimationController::AnimateGroup](#animategroup)|Подготавливает группу для запуска анимации и дополнительно запланировал ее.|
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Перегружен. Вызывается по системе очистки группы, когда анимация была запланирована.|
|[CAnimationController::CreateKeyframe](#createkeyframe)|Перегружен. Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.|
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Устанавливает или выпускает обработчик для вызова при изменении статуса менеджера анимации.|
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Устанавливает или выпускает обработчик для событий синхронизации и обработчик для обновлений синхронизации.|
|[CAnimationController::EnablePriorityСравнениHandler](#enableprioritycomparisonhandler)|Устанавливает или выпускает обработчик сравнения приоритетов для вызова, чтобы определить, можно ли отменить, заключить, обрезать или сжать запланированную раскадровку.|
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Устанавливает или выпускает обработчик для состояния раскадровки и обновления событий.|
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Перегружен. Находит анимационную группу по раскадровке.|
|[CAnimationController::FindAnimationObject](#findanimationobject)|Находит объект анимации, содержащий заданную переменную анимации.|
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Возвращает клавиатуру, которая определяет начало раскадровки.|
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Предоставляет доступ к инкапсулированному объекту IUIAnimationManager.|
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Обеспечивает доступ к инкапсулированному объекту IUIAnimationTimer.|
|[КанимацияКонтроллер::GetUITransitionFactory](#getuitransitionfactory)|Указатель на интерфейс IUIAnimationTransitionFactory или NULL, если не удалось создать библиотеку перехода.|
|[КанимацияКонтроллер:GetUITransitionLibrary](#getuitransitionlibrary)|Обеспечивает доступ к инкапсулированному объекту IUIAnimationTransitionLibrary.|
|[КанимацияКонтроллер::АнимацияИнПрогресс](#isanimationinprogress)|Сообщает, играет ли хотя бы одна группа анимации.|
|[КанимацияКонтроллер::Действительно](#isvalid)|Сообщает, является ли контроллер анимации допустимом.|
|[CAnimationController::OnanimationIntegerValue](#onanimationintegervaluechanged)|Вызывается инфраструктурой при изменении ажеронесной ценности переменной анимации.|
|[CAnimationController::OnanimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Вызывается в рамках в ответ на событие StatusChanged от менеджера анимации.|
|[КанимацияКонтроллер::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Вызывается инфраструктурой после завершения обновления анимации.|
|[КанимацияКонтроллер::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Вызывается по системе до начала обновления анимации.|
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Вызывается фреймворком, когда частота рендеринга кадров для анимации опускается ниже минимальной желаемой частоты кадров.|
|[КанимацияКонтроллер::АнимацияValueИзменен](#onanimationvaluechanged)|Вызывается инфраструктурой при изменении значения переменной анимации.|
|[КанимацияКонтроллер::OnbeforeAnimationStart](#onbeforeanimationstart)|Вызывается по рамкам прямо перед запланирована анимация.|
|[КанимацияКонтроллер::OnhasPriorityCancel](#onhasprioritycancel)|Вызывается платформой для решения конфликтов планирования.|
|[КанимацияКонтроллер:OnHasPriorityCompress](#onhasprioritycompress)|Вызывается платформой для решения конфликтов планирования.|
|[КанимацияКонтроллер:OnHasPriorityConclude](#onhaspriorityconclude)|Вызывается платформой для решения конфликтов планирования.|
|[КанимацияКонтроллер:OnHasPrioritytrim](#onhasprioritytrim)|Вызывается платформой для решения конфликтов планирования.|
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Вызывается по структуре, когда статус раскадровки изменился.|
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Вызывается по рамкам, когда раскадровка была обновлена.|
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Удаляет все группы анимации из контроллера анимации.|
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Удаляет группу анимации с указанным идентификатором из контроллера анимации.|
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Удалите объект анимации из контроллера анимации.|
|[CAnimationController::RemoveTransitions](#removetransitions)|Удаляет переходы из объектов анимации, принадлежащих к указанной группе.|
|[CAnimationController:ScheduleGroup](#schedulegroup)|Расписание анимации.|
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Устанавливает связь между контроллером анимации и окном.|
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Направляет менеджера анимации на обновление значений всех переменных анимации.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Перегружен. Помощник, который очищает группу.|
|[КанимацияКонтроллер::НаПой](#onafterschedule)|Вызывается по системе, когда анимация для указанной группы только что была запланирована.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Ключевой кадр, представляющий начало раскадровки.|
|[CAnimationController::m_bIsValid](#m_bisvalid)|Уточняется, действителен ли контроллер анимации или нет. Этот участник устанавливается в FALSE, если текущая ОС не поддерживает API анимации Windows.|
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Список групп анимации, которые принадлежат к этому контроллеру анимации.|
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Хранит указатель на объект Animation Manager COM.|
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Хранит указатель на объект Animation Timer COM.|
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Указатель на связанный объект CWnd, который может быть автоматически перерисован при изменении статуса менеджера анимации или событии обновления после. Может иметь значение NULL.|
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Хранит указатель на объект Transition Factory COM.|
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Хранит указатель на объект Transition Library COM.|

## <a name="remarks"></a>Примечания

Класс CAnimationController является ключевым классом, который управляет анимацией. В приложении можно создать один или несколько экземпляров контроллера анимации и, по желанию, подключить экземпляр контроллера анимации к объекту CWnd с помощью CAnimationController::SetRelatedWnd. Это соединение требуется для отправки WM_PAINT сообщений в связанное окно автоматически при изменении статуса менеджера анимации или обновлении временими анимации. Если вы не включите это отношение, необходимо перерисовать окно, которое отображает анимацию вручную. Для этой цели вы можете получить класс от CAnimationController и переопределить OnAnimationManagerStatusChanged и / или OnAnimationTimerPostUpdate и недействительными одного или нескольких окон, когда это необходимо.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationcontrollercanimationcontroller"></a><a name="_dtorcanimationcontroller"></a>CAnimationController:::CAnimationController

Деструктор Вызывается при уничтожении объекта контроллера анимации.

```
virtual ~CAnimationController(void);
```

## <a name="canimationcontrolleraddanimationobject"></a><a name="addanimationobject"></a>CAnimationController::AddAnimationObject

Добавляет объект анимации в группу, которая принадлежит контроллеру анимации.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>Параметры

*pObject*<br/>
Указатель на объект анимации.

### <a name="return-value"></a>Возвращаемое значение

Указатель на существующую или новую группу анимации, где pObject был добавлен, если функция успешно; NULL, если pObject уже добавлен в группу, которая принадлежит другому контроллеру анимации.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы добавить объект анимации в контроллер анимации. Объект будет добавлен в группу в соответствии с GroupID объекта (см. CAnimationBaseObject:: SetID). Контроллер анимации создаст новую группу, если это первый объект, добавленный с указанным GroupID. Объект анимации можно добавить только к одному контроллеру анимации. Если вам нужно добавить объект другому контроллеру, сначала позвоните в RemoveAnimationObject. Если вы вызовете SetID с новым GroupID для объекта, который уже был добавлен в группу, объект будет удален из старой группы и добавлен в другую группу с указанным идентификатором.

## <a name="canimationcontrolleraddkeyframetogroup"></a><a name="addkeyframetogroup"></a>КанимацияКонтроллер:AddKeyframeToGroup

Добавляет в группу ключевой элемент.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет идентификатор группы.

*pKeyframe*<br/>
Указатель на клавиатуру.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если функция удавляется; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Обычно вам не нужно вызывать этот метод, используйте CAnimationController::CreateKeyframe вместо этого, который создает и добавляет созданный ключевой кадр в группу автоматически.

## <a name="canimationcontrolleranimategroup"></a><a name="animategroup"></a>CAnimationController::AnimateGroup

Подготавливает группу для запуска анимации и дополнительно запланировал ее.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Уточняет GroupID.

*bРасписание сейчас*<br/>
Определяет, следует ли запускать анимацию сразу.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если анимация была успешно запланирована и запущена.

### <a name="remarks"></a>Примечания

Этот метод выполняет фактическую работу по созданию раскадровки, добавлению переменных анимации, применению переходов и настройке ключевых кадров. Можно отложить планирование, если вы установите bScheduleNow на FALSE. В этом случае указанная группа будет держать раскадровку, которая была создана для анимации. В этот момент можно настроить события для раскадровки и переменных анимации. Когда вам действительно нужно запустить анимацию вызова CAnimationController::ScheduleGroup.

## <a name="canimationcontrollercanimationcontroller"></a><a name="canimationcontroller"></a>CAnimationController::CAnimationController

Строит контроллер анимации.

```
CAnimationController(void);
```

## <a name="canimationcontrollercleanupgroup"></a><a name="cleanupgroup"></a>CAnimationController::CleanUpGroup

Вызывается по системе очистки группы, когда анимация была запланирована.

```cpp
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Уточняет GroupID.

*pGroup*<br/>
Указатель на анимацию группы для очистки.

### <a name="remarks"></a>Примечания

Этот метод удаляет все переходы и ключевые кадры из указанной группы, поскольку они не актуальны после запланированного анимации.

## <a name="canimationcontrollercreatekeyframe"></a><a name="createkeyframe"></a>CAnimationController::CreateKeyframe

Создает опорный кадр, зависящий от перехода, и добавляет его в указанную группу.

```
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseTransition* pTransition);

CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Задает идентификатор группы, для которой создается опорный кадр.

*pTransition*<br/>
Указатель на переход. Опорный кадр будет вставлен в раскадровку после этого перехода.

*pKeyframe*<br/>
Указатель на базовый опорный кадр для данного опорного кадра.

*Смещение*<br/>
Смещение в секундах от базового опорного кадра, заданного параметром pKeyframe.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный опорный кадр, если функция выполнена успешно.

### <a name="remarks"></a>Примечания

Возвращенный указатель можно сохранить и основывать другие опорные кадры на только что созданном опорном кадре (см. вторую перегрузку). Можно начинать переходы на опорных кадрах — см. раздел, посвященный CBaseTransition::SetKeyframes. Удалять созданные таким образом опорные кадры не нужно, так как они автоматически удаляются группами анимации. При создании опорных кадров на основе других опорных кадров и переходов будьте внимательны и избегайте циклических ссылок.

## <a name="canimationcontrollerenableanimationmanagerevent"></a><a name="enableanimationmanagerevent"></a>CAnimationController::EnableAnimationManagerEvent

Устанавливает или выпускает обработчик для вызова при изменении статуса менеджера анимации.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Определяет, устанавливать или выпускать обработчик.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если обработчик был успешно установлен или выпущен.

### <a name="remarks"></a>Примечания

При установке (включено) Windows Animation вызывает OnAnimationManagerStatusChanged при изменении статуса менеджера анимации.

## <a name="canimationcontrollerenableanimationtimereventhandler"></a><a name="enableanimationtimereventhandler"></a>CAnimationController::EnableAnimationTimerEventHandler

Устанавливает или выпускает обработчик для событий синхронизации и обработчик для обновлений синхронизации.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Определяет, устанавливать или выпускать обработчики.

*idleBehavior*<br/>
Определяет поведение простоя для обработчика обновления таймера.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если обработчики были успешно установлены или освобождены; FALSE, если этот метод вызывается во второй раз, не выпуская обработчиков во-первых, или если любая другая ошибка происходит.

### <a name="remarks"></a>Примечания

При установке (включено) API анимации Windows вызывает OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate, OnRenderingTooSlow методы. Необходимо включить таймеры анимации, чтобы позволить Windows Animation API обновлять раскадровки. В противном случае вам нужно будет позвонить CAnimationController::UpdateAnimationManager, чтобы направить менеджеру анимации на обновление значений всех переменных анимации.

## <a name="canimationcontrollerenableprioritycomparisonhandler"></a><a name="enableprioritycomparisonhandler"></a>CAnimationController::EnablePriorityСравнениHandler

Устанавливает или выпускает обработчик сравнения приоритетов для вызова, чтобы определить, можно ли отменить, заключить, обрезать или сжать запланированную раскадровку.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>Параметры

*dwHandlerType*<br/>
Сочетание UI_ANIMATION_PHT_ флагов (см. замечания), в котором оговаривается, какие обработчики установить или выпустить.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если обработчик был успешно установлен или выпущен.

### <a name="remarks"></a>Примечания

Когда обработчик установлен (включен) Windows Animation вызывает следующие виртуальные методы в зависимости от dwHandlerType: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler может быть сочетание следующих флагов: UI_ANIMATION_PHT_NONE - выпустить все обработчики UI_ANIMATION_PHT_CANCEL - установить Отмена обработчик сравнения UI_ANIMATION_PHT_CONCLUDE - набор Заключить сравнение обработчик UI_ANIMATION_PHT_COMPRESS - установить Обработка сравнения сжатия UI_ANIMATION_PHT_TRIM - установить Обработка сравнения Trim UI_ANIMATION_PHT_CANCEL_REMOVE - удалить Отменить сравнение обработчик UI_ANIMATION_PHT_CONCLUDE_REMOVE - удалить Сравнение обработчик UI_ANIMATION_PHT_COMPRESS_REMOVE - удалить обработчик сравнения сжатия UI_ANIMATION_PHT_TRIM_REMOVE - удалить обработчик сравнения обрезки

## <a name="canimationcontrollerenablestoryboardeventhandler"></a><a name="enablestoryboardeventhandler"></a>CAnimationController::EnableStoryboardEventHandler

Устанавливает или выпускает обработчик для состояния раскадровки и обновления событий.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет идентификатор группы.

*bEnable*<br/>
Определяет, устанавливать или выпускать обработчик.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если обработчик был успешно установлен или выпущен; FALSE, если указанная группа анимации теперь найдена или анимация для указанной группы не была инициирована, а ее внутренний раскадровка null.

### <a name="remarks"></a>Примечания

При установке обработчика (включен) Windows Animation API вызывает OnStoryboardStatusChanges и OnStoryboardUpdated виртуальные методы. Обработчик должен быть установлен после CAnimationController::Animate был вызван для указанной группы анимации, потому что он создает инкапсулированный объект IUIAnimationStoryboard.

## <a name="canimationcontrollerfindanimationgroup"></a><a name="findanimationgroup"></a>CAnimationController::FindAnimationGroup

Находит анимационную группу по идентификатору группы.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет GroupID.

*pStoryboard*<br/>
Указатель на раскадровку.

### <a name="return-value"></a>Возвращаемое значение

Указатель на группу анимации или NULL, если группа с указанным идентификатором не найдена.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы найти группу анимации во время выполнения. Группа создается и добавляется во внутренний список групп анимации, когда первый объект анимации с определенным GroupID добавляется в контроллер анимации.

## <a name="canimationcontrollerfindanimationobject"></a><a name="findanimationobject"></a>CAnimationController::FindAnimationObject

Находит объект анимации, содержащий заданную переменную анимации.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>Параметры

*pПеременный*<br/>
Указатель на переменную анимации.

*ppObject*<br/>
Выходные данные. Содержит указатель на объект анимации или NULL.

*ppGroup*<br/>
Выходные данные. Содержит указатель для группы анимации, которая удерживает объект анимации, или NULL.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если объект был найден; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вызывается от обработчиков событий, когда требуется найти объект анимации из входящих переменных анимации.

## <a name="canimationcontrollergkeyframestoryboardstart"></a><a name="g_keyframestoryboardstart"></a>CAnimationController::gkeyframeStoryboardStart

Ключевой кадр, представляющий начало раскадровки.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

## <a name="canimationcontrollergetkeyframestoryboardstart"></a><a name="getkeyframestoryboardstart"></a>CAnimationController::GetKeyframeStoryboardStart

Возвращает клавиатуру, которая определяет начало раскадровки.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый ключевой элемент, который определяет начало раскадровки.

### <a name="remarks"></a>Примечания

Получите этот ключевой кадр для базирования любых других ключевых кадров или переходов в момент начала раскадровки.

## <a name="canimationcontrollergetuianimationmanager"></a><a name="getuianimationmanager"></a>CAnimationController::GetUIAnimationManager

Предоставляет доступ к инкапсулированному объекту IUIAnimationManager.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUIAnimationManager или NULL, если создание менеджера анимации не удалось.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает NULL и после этого все последующие вызовы на CAnimationController::IsValid возврата FALSE. Возможно, вам потребуется доступ к IUIAnimationManager для того, чтобы назвать его методы интерфейса, которые не обернуты контроллером анимации.

## <a name="canimationcontrollergetuianimationtimer"></a><a name="getuianimationtimer"></a>CAnimationController::GetUIAnimationTimer

Обеспечивает доступ к инкапсулированному объекту IUIAnimationTimer.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUIAnimationTimer или NULL, если создание анимационного таймер не удалось.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает NULL и после этого все последующие вызовы на CAnimationController::IsValid возврата FALSE.

## <a name="canimationcontrollergetuitransitionfactory"></a><a name="getuitransitionfactory"></a>КанимацияКонтроллер::GetUITransitionFactory

Указатель на интерфейс IUIAnimationTransitionFactory или NULL, если не удалось создать библиотеку перехода.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на IUIAnimationTransitionFactory или NULL, если создание переходного завода не удалось.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает NULL и после этого все последующие вызовы на CAnimationController::IsValid возврата FALSE.

## <a name="canimationcontrollergetuitransitionlibrary"></a><a name="getuitransitionlibrary"></a>КанимацияКонтроллер:GetUITransitionLibrary

Обеспечивает доступ к инкапсулированному объекту IUIAnimationTransitionLibrary.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUIAnimationTransitionLibrary или NULL, если не удалось создать библиотеку перехода.

### <a name="remarks"></a>Примечания

Если текущая ОС не поддерживает API анимации Windows, этот метод возвращает NULL и после этого все последующие вызовы на CAnimationController::IsValid возврата FALSE.

## <a name="canimationcontrollerisanimationinprogress"></a><a name="isanimationinprogress"></a>КанимацияКонтроллер::АнимацияИнПрогресс

Сообщает, играет ли хотя бы одна группа анимации.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если есть анимация в процессе для этого контроллера анимации; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Проверяет состояние менеджера анимации и возвращает TRUE, если статус UI_ANIMATION_MANAGER_BUSY.

## <a name="canimationcontrollerisvalid"></a><a name="isvalid"></a>КанимацияКонтроллер::Действительно

Сообщает, является ли контроллер анимации допустимом.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если контроллер анимации действителен; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает FALSE только в том случае, если Windows Animation API не поддерживается на текущей ОС и создание менеджера анимации не удалось, потому что он не зарегистрирован. Вы должны позвонить GetUIAnimationManager по крайней мере один раз после инициализации библиотек COM, чтобы вызвать установку этого флага.

## <a name="canimationcontrollerm_bisvalid"></a><a name="m_bisvalid"></a>CAnimationController::m_bIsValid

Уточняется, действителен ли контроллер анимации или нет. Этот участник устанавливается в FALSE, если текущая ОС не поддерживает API анимации Windows.

```
BOOL m_bIsValid;
```

## <a name="canimationcontrollerm_lstanimationgroups"></a><a name="m_lstanimationgroups"></a>CAnimationController::m_lstAnimationGroups

Список групп анимации, которые принадлежат к этому контроллеру анимации.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

## <a name="canimationcontrollerm_panimationmanager"></a><a name="m_panimationmanager"></a>CAnimationController::m_pAnimationManager

Хранит указатель на объект Animation Manager COM.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

## <a name="canimationcontrollerm_panimationtimer"></a><a name="m_panimationtimer"></a>CAnimationController::m_pAnimationTimer

Хранит указатель на объект Animation Timer COM.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

## <a name="canimationcontrollerm_prelatedwnd"></a><a name="m_prelatedwnd"></a>CAnimationController::m_pRelatedWnd

Указатель на связанный объект CWnd, который может быть автоматически перерисован при изменении статуса менеджера анимации или событии обновления после. Может иметь значение NULL.

```
CWnd* m_pRelatedWnd;
```

## <a name="canimationcontrollerm_ptransitionfactory"></a><a name="m_ptransitionfactory"></a>CAnimationController::m_pTransitionFactory

Хранит указатель на объект Transition Factory COM.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

## <a name="canimationcontrollerm_ptransitionlibrary"></a><a name="m_ptransitionlibrary"></a>CAnimationController::m_pTransitionLibrary

Хранит указатель на объект Transition Library COM.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

## <a name="canimationcontrolleronafterschedule"></a><a name="onafterschedule"></a>КанимацияКонтроллер::НаПой

Вызывается по системе, когда анимация для указанной группы только что была запланирована.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Указатель на анимационную группу, которая была запланирована.

### <a name="remarks"></a>Примечания

Реализация по умолчанию удаляет ключевые кадры из указанной группы и переходы из переменных анимации, принадлежащих к указанной группе. Может быть переопределен в производном классе, чтобы предпринять любые дополнительные действия по графику анимации.

## <a name="canimationcontrolleronanimationintegervaluechanged"></a><a name="onanimationintegervaluechanged"></a>CAnimationController::OnanimationIntegerValue

Вызывается инфраструктурой при изменении ажеронесной ценности переменной анимации.

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Указатель на группу анимации, в которой содержится объект анимации, значение которого изменилось.

*pObject*<br/>
Указатель на объект анимации, содержащий переменную анимации, значение которой изменилось.

*Переменной*<br/>
Указатель на переменную анимации.

*newValue*<br/>
Определяет новое значение.

*prevValue*<br/>
Определяет предыдущее значение.

### <a name="remarks"></a>Примечания

Этот метод называется, если включить переменные события анимации с EnableIntegerValueChangedEvent призвал к определенной переменной анимации или объект анимации. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

## <a name="canimationcontrolleronanimationmanagerstatuschanged"></a><a name="onanimationmanagerstatuschanged"></a>CAnimationController::OnanimationManagerStatusChanged

Вызывается в рамках в ответ на событие StatusChanged от менеджера анимации.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Параметры

*newStatus*<br/>
Новый статус менеджера анимации.

*предыдущийСтатус*<br/>
Предыдущий статус менеджера анимации.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы позволяете событиям менеджера анимации с помощью EnableAnimationManagerEvent. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Реализация по умолчанию обновляет связанное окно, если оно было установлено SetRelatedWnd.

## <a name="canimationcontrolleronanimationtimerpostupdate"></a><a name="onanimationtimerpostupdate"></a>КанимацияКонтроллер::OnAnimationTimerPostUpdate

Вызывается инфраструктурой после завершения обновления анимации.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включите обработчики событий таймер с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

## <a name="canimationcontrolleronanimationtimerpreupdate"></a><a name="onanimationtimerpreupdate"></a>КанимацияКонтроллер::OnAnimationTimerPreUpdate

Вызывается по системе до начала обновления анимации.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включите обработчики событий таймер с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

## <a name="canimationcontrolleronanimationtimerrenderingtooslow"></a><a name="onanimationtimerrenderingtooslow"></a>CAnimationController::OnAnimationTimerRenderingTooSlow

Вызывается фреймворком, когда частота рендеринга кадров для анимации опускается ниже минимальной желаемой частоты кадров.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>Параметры

*Fps*<br/>
Текущая частота кадров в кадрах в секунду.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включите обработчики событий таймер с помощью EnableAnimationTimerEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Минимальная желаемая частота кадров указана по телефону IUIAnimationTimer::SetFrameRateThreshold.

## <a name="canimationcontrolleronanimationvaluechanged"></a><a name="onanimationvaluechanged"></a>КанимацияКонтроллер::АнимацияValueИзменен

Вызывается инфраструктурой при изменении значения переменной анимации.

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Указатель на группу анимации, в которой содержится объект анимации, значение которого изменилось.

*pObject*<br/>
Указатель на объект анимации, содержащий переменную анимации, значение которой изменилось.

*Переменной*<br/>
Указатель на переменную анимации.

*newValue*<br/>
Определяет новое значение.

*prevValue*<br/>
Определяет предыдущее значение.

### <a name="remarks"></a>Примечания

Этот метод называется, если включить переменные события анимации с EnableValueChangedEvent, который требует сяочную переменную анимации или объект анимации. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

## <a name="canimationcontrolleronbeforeanimationstart"></a><a name="onbeforeanimationstart"></a>КанимацияКонтроллер::OnbeforeAnimationStart

Вызывается по рамкам прямо перед запланирована анимация.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Указатель на анимационную группу, анимация которой вот-вот начнется.

### <a name="remarks"></a>Примечания

Этот вызов направляется в связанный CWnd и может быть переопределен в производном классе для выполнения любых дополнительных действий до начала анимации для указанной группы.

## <a name="canimationcontrolleronhasprioritycancel"></a><a name="onhasprioritycancel"></a>КанимацияКонтроллер::OnhasPriorityCancel

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*pGroupScheduled*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*pGroupNew*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*priorityEffect*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_CANCEL. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Прочитайте документацию API Windows Animation для получения дополнительной информации об [управлении конфликтами.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronhasprioritycompress"></a><a name="onhasprioritycompress"></a>КанимацияКонтроллер:OnHasPriorityCompress

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*pGroupScheduled*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*pGroupNew*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*priorityEffect*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_COMPRESS. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Прочитайте документацию API Windows Animation для получения дополнительной информации об [управлении конфликтами.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronhaspriorityconclude"></a><a name="onhaspriorityconclude"></a>КанимацияКонтроллер:OnHasPriorityConclude

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*pGroupScheduled*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*pGroupNew*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*priorityEffect*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_CONCLUDE. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Прочитайте документацию API Windows Animation для получения дополнительной информации об [управлении конфликтами.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronhasprioritytrim"></a><a name="onhasprioritytrim"></a>КанимацияКонтроллер:OnHasPrioritytrim

Вызывается платформой для решения конфликтов планирования.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Параметры

*pGroupScheduled*<br/>
Группа, в которую входит текущая запланированная раскадровка.

*pGroupNew*<br/>
Группа, в которую входит новая раскадровка, находящаяся в состоянии конфликта с запланированной раскадровкой, входящей в группу pGroupScheduled.

*priorityEffect*<br/>
Возможное действие на группу pGroupNew, если приоритет группы pGroupScheduled выше.

### <a name="return-value"></a>Возвращаемое значение

Должно возвращаться значение TRUE, если приоритет принадлежит раскадровке, входящей в группу pGroupNew. Должно возвращаться значение FALSE, если приоритет принадлежит раскадровке, входящей в группу pGroupScheduled.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если задействовать события сравнения приоритета с помощью метода CAnimationController::EnablePriorityComparisonHandler и указать UI_ANIMATION_PHT_TRIM. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе. Прочитайте документацию API Windows Animation для получения дополнительной информации об [управлении конфликтами.](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)

## <a name="canimationcontrolleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>CAnimationController::OnStoryboardStatusChanged

Вызывается по структуре, когда статус раскадровки изменился.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Указатель на анимационную группу, владеющую раскадровкой, статус которой изменился.

*newStatus*<br/>
Определяет новый статус.

*предыдущийСтатус*<br/>
Определяет предыдущий статус.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включите события раскадровки с помощью CAnimationController::EnableStoryboardEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

## <a name="canimationcontrolleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>CAnimationController::OnStoryboardUpdated

Вызывается по рамкам, когда раскадровка была обновлена.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Указатель на группу, которая владеет раскадровкой.

### <a name="remarks"></a>Примечания

Этот метод вызывается, если вы включите события раскадровки с помощью CAnimationController::EnableStoryboardEventHandler. Для выполнения действий, характерных для конкретного приложения, его можно переопределить в производном классе.

## <a name="canimationcontrollerremoveallanimationgroups"></a><a name="removeallanimationgroups"></a>CAnimationController::RemoveAllAnimationGroups

Удаляет все группы анимации из контроллера анимации.

```cpp
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>Примечания

Все группы будут удалены, их указатель, если они хранятся на уровне приложения, должны быть признаны недействительными. Если CAnimationGroup::m_bAutodestroyAnimationObjects для удаленной группы является правдой, все объекты анимации, принадлежащие к этой группе, будут удалены; в противном случае их ссылки на контроллер родительской анимации будут установлены на NULL, и они могут быть добавлены к другому контроллеру.

## <a name="canimationcontrollerremoveanimationgroup"></a><a name="removeanimationgroup"></a>CAnimationController::RemoveAnimationGroup

Удаляет группу анимации с указанным идентификатором из контроллера анимации.

```cpp
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет идентификатор группы анимации.

### <a name="remarks"></a>Примечания

Этот метод удаляет группу анимации из внутреннего списка групп и удаляет ее, поэтому, если вы сохранили указатель для этой группы анимации, она должна быть признана недействительной. Если CAnimationGroup::m_bAutodestroyAnimationObjects является правдой, все объекты анимации, которые принадлежат к этой группе, будут удалены; в противном случае их ссылки на контроллер родительской анимации будут установлены на NULL, и они могут быть добавлены к другому контроллеру.

## <a name="canimationcontrollerremoveanimationobject"></a><a name="removeanimationobject"></a>CAnimationController::RemoveAnimationObject

Удалите объект анимации из контроллера анимации.

```cpp
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>Параметры

*pObject*<br/>
Указатель на объект анимации.

*bNoУдалить*<br/>
Если этот параметр является истинным, объект не будет удален при удалении.

### <a name="remarks"></a>Примечания

Удаляет объект анимации из контроллера анимации и группы анимации. Вызовите эту функцию, если определенный объект больше не должен быть анимирован, или если вам нужно переместить объект на другой контроллер анимации. В последнем случае bNoDelete должен быть правдой.

## <a name="canimationcontrollerremovetransitions"></a><a name="removetransitions"></a>CAnimationController::RemoveTransitions

Удаляет переходы из объектов анимации, принадлежащих к указанной группе.

```cpp
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет идентификатор группы.

### <a name="remarks"></a>Примечания

Группа петли над своими объектами анимации и вызывает ClearTransitions (FALSE) для каждого объекта анимации. Этот метод вызывается инфраструктурой после запланированного анимации.

## <a name="canimationcontrollerschedulegroup"></a><a name="schedulegroup"></a>CAnimationController:ScheduleGroup

Расписание анимации.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет идентификатор группы анимации в расписании.

*time*<br/>
Определяет время для расписания.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если анимация была запланирована успешно. FALSE, если раскадровка не была создана, или происходит другая ошибка.

### <a name="remarks"></a>Примечания

Вы должны позвонить в AnimateGroup с параметром bScheduleNow, установленным на FALSE prior ScheduleGroup. Вы можете указать желаемое время анимации, полученное от IUIAnimationTimer::GetTime. Если параметр времени 0,0, анимация запланирована на текущее время.

## <a name="canimationcontrollersetrelatedwnd"></a><a name="setrelatedwnd"></a>CAnimationController::SetRelatedWnd

Устанавливает связь между контроллером анимации и окном.

```cpp
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на объект окна для установки.

### <a name="remarks"></a>Примечания

Если настроен связанный объект CWnd, контроллер анимации может автоматически обновлять его (отправить WM_PAINT сообщение), когда изменился статус менеджера анимации или произошло событие обновления таймера.

## <a name="canimationcontrollerupdateanimationmanager"></a><a name="updateanimationmanager"></a>CAnimationController::UpdateAnimationManager

Направляет менеджера анимации на обновление значений всех переменных анимации.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>Примечания

Вызов этого метода продвигает менеджера анимации к текущему времени, изменяя статусы раскадровок по мере необходимости и обновляя любые переменные анимации для соответствующих интерполированных значений. Внутренне этот метод вызывает IUIAnimationTimer::GetTime (timeNow) и IUIAnimationManager::Update (timeNow). Переопределить этот метод в производном классе, чтобы настроить это поведение.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
