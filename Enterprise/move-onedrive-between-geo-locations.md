---
title: Перемещение сайта OneDrive различных географического расположения
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 4/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
description: Узнайте, как для переноса сайта OneDrive в разных географического расположения.
ms.openlocfilehash: a31f683170fdb83dac90e9d09884c3020d1a47b1
ms.sourcegitcommit: 3f3d2de6c0c5225156cfba01bc980994cd9ae848
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>Перемещение сайта OneDrive различных географического расположения 

С помощью OneDrive переместить географически, можно переместить пользователя OneDrive в разных географического расположения. Перемещение географически OneDrive производится администратору SharePoint Online или глобального администратора Office 365. Прежде чем начать OneDrive, географически перемещение, убедитесь, что для уведомления пользователей, чьи OneDrive перемещается и рекомендуем они закрыть все файлы во время выполнения перемещения. (Если у пользователя есть документ открыт, с помощью клиента Office во время перемещения, затем на перемещение завершение работы необходимые документ будет сохранен в новом расположении). Перемещение можно запланировать на время в будущем, если это необходимо.

Служба OneDrive использует хранилище больших двоичных объектов Azure для хранения содержимого. Хранение больших двоичных объектов, связанных со службой OneDrive пользователя будут перемещены из источника в месте назначения географически в пределах 40 дням назначения OneDrive, доступные для пользователя. Доступ к OneDrive пользователя будут восстановлены сразу же назначения OneDrive доступен.

Во время перемещения географически OneDrive окно (около 2 – 6 часов) OneDrive пользователя имеет значение только для чтения. Пользователь по-прежнему можно получить доступ к их файлы с помощью клиента синхронизации OneDrive или их OneDrive сайта в SharePoint Online. После завершения перемещения географически OneDrive пользователя будет автоматически подключены к их OneDrive в месте назначения географически при переходе в OneDrive запуска приложения для Office 365. Клиент синхронизации автоматически начнется синхронизация из нового расположения.

Процедуры, описанные в этой статье требуется [Модуль Microsoft SharePoint Online PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=35588).

## <a name="moving-a-onedrive-site"></a>Перемещение сайта OneDrive

Для выполнения OneDrive переместить географически, администратор клиента нужно задать расположение предпочитаемое данных пользователя (PDL) соответствующие географического расположения. После задания PDL дождитесь менее 24 часа в качестве обновления PDL для синхронизации в подразделениях географически перед началом работы move географически OneDrive.

Если с помощью географически переместить командлеты, подключения к службе SPO пользователя текущей позиции OneDrive географически, используя следующий синтаксис:

`connect-sposervice -url https://<tenantName>-admin.sharepoint.com`

Например: перемещение OneDrive пользователя «Matt@contosoenergy.onmicrosoft.com» подключиться к центра администрирования SharePoint ЕВРО как OneDrive пользователя находится в ЕВРО географического расположения:

`connect-sposervice -url https://contosoenergyeur-admin.sharepoint.com`

![](media/move-onedrive-between-geo-locations_image1.png)

## <a name="validating-the-environment"></a>Проверка среды

Прежде чем начать перемещение географически OneDrive, рекомендуется проверить среды.

Чтобы обеспечить совместимость все географического расположения, выполните следующую команду:

`Get-SPOGeoMoveCompatibilityStatus -AllLocations 1`

Если OneDrive в разделе удержания по юридическим причинам или дочернего сайта, его нельзя перемещать. Командлет Start-SPOUserAndContentMove совместно с параметром - ValidationOnly для проверки, если OneDrive может быть перемещен:

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

Это возвращает успех, если OneDrive готова к перемещены или ошибкой, если удержания по юридическим причинам или дочернего сайта, который будет препятствовать move. После проверки, что OneDrive готова для перемещения можно начать перемещение.

## <a name="start-a-onedrive-geo-move"></a>Начать перемещение географически OneDrive

Чтобы запустить move, выполните следующую команду:  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

Используя следующие параметры:

-   _UserPrincipalName_ — имя участника-пользователя, чьи OneDrive перемещается.

-   _DestinationDataLocation_ – географического расположения, где OneDrive нужно переместить. Это должен быть такой же, как расположение предпочитаемый данных пользователя.

> [!NOTE]
> Мы рекомендуем running `Get-SPOGeoMoveStateCompatibility` с `ValidationOnly` до инициализации OneDrive перемещение географически.

Например чтобы переместить OneDrive matt@contosoenergy.onmicrosoft.com из ЕВРО Стандартное, выполните следующую команду:

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![](media/move-onedrive-between-geo-locations_image2.png)

Для планирования перемещения географически для последующего, используйте один из следующих параметров:

-   _PreferredMoveBeginDate_ – скорее move начинается с этой указанное время.

-   _PreferredMoveEndDate_ – скорее перемещения закончится в этот указанное время наиболее объем работ по отдельности.

## <a name="cancel-a-onedrive-geo-move"></a>Отменить перемещение географически OneDrive 

Можно остановить переместить географически OneDrive пользователя, предоставляемые move не выполняется или завершено с помощью командлета:

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

Где _UserPrincipalName_ — это имя участника-пользователя, которого OneDrive переместить почтовые требуется остановить.

## <a name="determining-current-status"></a>Определение текущего состояния

Можно проверить состояние OneDrive, географически перемещение и выход географически, установлено подключение с помощью командлета Get-SPOUserAndContentMoveState.

На перемещение состояния, описаны в следующей таблице.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Status</strong></th>
<th align="left"><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">Перемещение не запущена.</td>
</tr>
<tr class="even">
<td align="left">InProgress (<em>n</em>/4)</td>
<td align="left">Перемещение находится в стадии разработки в одном из следующих состояний: проверки (1/4), резервное копирование (2/4), восстановить (3 и 4) очистки (4/4).</td>
</tr>
<tr class="odd">
<td align="left">Success (Успешно)</td>
<td align="left">Перемещение успешно завершена.</td>
</tr>
<tr class="even">
<td align="left">Failed</td>
<td align="left">Не удалось переместить.</td>
</tr>
</tbody>
</table>

Чтобы найти состояния перемещения определенного пользователя, используйте параметр UserPrincipalName:

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

Чтобы найти состояние всех перемещений в данные группы или из расположения географически, вы подключены к, используйте параметр MoveState с одним из следующих значений: NotStarted, InProgress, успех, не удалось выполнить, все.

`Get-SPOUserAndContentMoveState -MoveState <value>`

Также можно добавить `-Verbose` параметр более подробное описание перемещения состояния.

## <a name="user-experience"></a>Удобство пользователя

Пользователи OneDrive следует заметить мешая при перемещении их OneDrive для разных географического расположения. Помимо краткое состояние только для чтения во время перемещения существующие связи и разрешения будет продолжать работать неправильно после завершения перемещения.

### <a name="onedrive-for-business"></a>OneDrive для бизнеса

В процессе перемещения пользователя OneDrive имеет значение только для чтения. После завершения перемещения пользователь перенаправляется на их OneDrive в новом расположении географически, когда они переходят в OneDrive запуска приложения для Office 365 или веб-браузера.

### <a name="permissions-on-onedrive-content"></a>Разрешения на OneDrive содержимого

Пользователи с разрешениями на OneDrive содержимого будет иметь доступ к содержимому во время перемещения и после завершения.

### <a name="onedrive-sync-client"></a>Клиент синхронизации OneDrive 

Клиента синхронизации OneDrive автоматически определяет и легко перенести синхронизации в новом расположении OneDrive после завершения перемещения географически OneDrive. Пользователь не требуется входить в систему и выполнения других действий.

Если пользователь обновляет файл в процессе перемещения географически OneDrive, клиент синхронизации уведомим им, что имеются ожидающие передачи файлов во время перемещения.

### <a name="sharing-links"></a>Совместное использование ссылок 

После географически OneDrive перемещение завершения, существующей общей ссылки для файлов, которые были перемещены автоматически перенаправляются на новое расположение географически.

### <a name="onenote-experience"></a>Возможности OneNote 

Клиент OneNote win32 и UWP (универсальные) приложение будет автоматическое определение и эффективно синхронизировать записные книжки к новому местоположению OneDrive после завершения перемещения географически OneDrive. Пользователь не требуется входить в систему и выполнения других действий. Индикатор доступны только для пользователя — синхронизации записную книжку не будут выполнены при перемещении географически OneDrive находится в стадии разработки. Этот интерфейс доступна в следующих версиях клиента OneNote:

-   Win32 OneNote – версии 16.0.8326.2096 (и более поздних версий)

-   UWP OneNote – версии 16.0.8431.1006 (и более поздних версий)

-   Приложение OneNote Mobile – версии 16.0.8431.1011 (и более поздних версий)

### <a name="teams-app"></a>Приложение группы

После географически OneDrive перемещение завершения, пользователи получат доступ к их файлы OneDrive на app. групп Кроме того, совместно с помощью чата группы из их OneDrive до перемещения географически файлы будут работать после завершения перемещения.

### <a name="onedrive-for-business-mobile-app-ios"></a>OneDrive для мобильного бизнес-приложения (операций ввода-вывода) 

После географически OneDrive перемещение завершения, пользователь должен выйти из системы и повторного входа на iOS мобильного приложения для синхронизации в новом расположении OneDrive.

### <a name="existing-followed-groups-and-sites"></a>Существующие за групп и веб-узлы

Число сайтов и группы будут отображаться в пользователя OneDrive для бизнеса независимо от их географического расположения. Сайты и группы, находящиеся в другом месте географически будет открыт в отдельной вкладке.