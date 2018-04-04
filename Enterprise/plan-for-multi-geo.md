---
title: Планирование использования службы OneDrive для бизнеса Multi географически
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 4/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
description: Сведения о OneDrive для различных бизнес-географически, как работает несколькими географически и какие географического расположения, доступны для хранения данных.
ms.openlocfilehash: 22ba0f4ebc3fb3c4e11bc0386a1479fa6a889ad8
ms.sourcegitcommit: 3f3d2de6c0c5225156cfba01bc980994cd9ae848
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="plan-for-onedrive-for-business-multi-geo"></a>Планирование использования службы OneDrive для бизнеса Multi географически

Данное руководство предназначено для администраторов глобальной экономике компаний (MNCs), подготавливающих их SharePoint Online клиента, чтобы развернуть, чтобы дополнительные географических зон в соответствии с присутствия компании в соответствии с требованиями объемом данных.

В конфигурации с несколькими OneDrive-географически клиента Office 365 состоит из центрального расположения (также известной как расположение по умолчанию) и одно или несколько расположений географически вспомогательных. Это одним клиентом, которая распределена среди в нескольких подразделениях географически. Ферма с несколькими OneDrive-географически, данные клиента, включая географического расположения управляется в Azure Active Directory (AAD). 

Вот некоторые ключевые несколькими географически термины помогут вам понять основные понятия конфигурации.

-   **Клиент** – представление организации в облако Office 365, который обычно имеет один или несколько доменов, связанных с ним (например, http://contoso.sharepoint.com). 

-   **Географического расположения** – географического расположения, где размещены данные вашего клиента. Географическая ферма с несколькими клиентами охватывать несколько местоположений географически, к примеру, Северной Америки и Европы.

-   **Допускается данных расположения (ADL)** — географически расположения, для которых настроен вашего клиента для размещения данных OneDrive и SharePoint.

-   **Предпочтительная расположение данных (PDL)** — географически расположение, где хранятся данные OneDrive отдельного пользователя. Это может иметь значение администратором, на какие-либо из расположений данных разрешены, настроенных для клиента. Обратите внимание, что при изменении PDL для пользователя, который уже связан сайт OneDrive их OneDrive данные не перемещаются в новое местоположение географически автоматически. Для получения дополнительных сведений в разделе [Перемещение библиотеки OneDrive для разных географического расположения](move-onedrive-between-geo-locations.md) .

Включение несколькими географически требует четырех основных шагов:

1.  Работа с коллегами учетной записи для добавления план обслуживания _Несколькими географически возможности в Office 365_ .

2.  Выберите на желаемую вспомогательные географически местоположений и добавить их к клиенту.

3.  Задайте расположение предпочитаемый данных пользователей к месту географически необходимые вспомогательные. При подготовке нового сайта OneDrive для пользователя, он может их PDL.

4.  Перенос существующих сайтов OneDrive пользователей из дома в их расположение предпочитаемый данных при необходимости.

В разделе [Настройка OneDrive для бизнеса Multi-географически](multi-geo-tenant-configuration.md) для получения дополнительных сведений на каждый из этих шагов.

> [!IMPORTANT]
> Обратите внимание, что ферма с несколькими географически компонентов Office 365 не предназначены для оптимизации производительности случаях они предназначенные для удовлетворения требований к данным местонахождения. Сведения об оптимизации производительности для Office 365 [Планирование сети](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) и настройка производительности для Office 365 или обратитесь в группу поддержки.

Можно настроить любые из следующих расположений быть расположения географически вспомогательных, где вы можете размещать файлы OneDrive. Во время планирования для различных географически, для создания списка расположений, которые вы хотите добавить в клиент Office 365. Мы рекомендуем начиная с одним или двумя вспомогательных расположения и затем постепенно расширятся, создавая дополнительные географического расположения, при необходимости.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Расположение</strong></th>
<th align="left"><strong>Код</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Азиатско-Тихоокеанский регион</td>
<td align="left">APC</td>
</tr>
<tr class="even">
<td align="left">Европа / Средний Восток и Африка</td>
<td align="left">ЕВРО</td>
</tr>
<tr class="odd">
<td align="left">Северная Америка</td>
<td align="left">ИМ</td>
</tr>
<tr class="even">
<td align="left">Австралия</td>
<td align="left">СТАНДАРТНОЕ</td>
</tr>
<tr class="odd">
<td align="left">Канада</td>
<td align="left">МОЖНО</td>
</tr>
<tr class="odd">
<td align="left">Япония</td>
<td align="left">ЯПОНСКИЙ</td>
</tr>
<tr class="even">
<td align="left">Корея</td>
<td align="left">КОРЕЙСКИЙ</td>
</tr>
<tr class="odd">
<td align="left">Соединенное Королевство</td>
<td align="left">GBR</td>
</tr>
</tbody>
</table>

Скоро:
  
- Франция
- Индия

При настройке несколькими географически проведите возможность консолидации локальной инфраструктуре во время миграции на Office 365. Например при наличии локальной фермы в Сингапур и Малайзия нажмите их можно объединить в расположение вспомогательных APC условии, что требования к местонахождения данных позволяют делать это.

## <a name="best-practices"></a>Советы и рекомендации

Рекомендуется создать тестового пользователя в Office 365 для начального тестирования. Мы рассмотрим некоторые этапы тестирования и проверки с этим пользователем прежде чем перейти к встроенным конечных пользователей в функцию OneDrive несколькими-географически.

После выполнения тестирования с помощью тестового пользователя выберите пилотную – возможно из ИТ-отдел компании – к первым должен использовать OneDrive в новый географического расположения. Для первой группы выберите пользователей, которые еще не имеют OneDrive. Рекомендуется не более пяти пользователей в эту группу начальной и постепенно разверните трудозатрат пакетной выгрузка данных.

Каждый пользователь должен иметь *расположение предпочитаемый данных* (PDL), чтобы Office 365 можно определить, в какой географически расположение для подготовки их OneDrive. Расположение пользователя предпочтительный данных должно соответствовать одному из к расположениям выбранного вспомогательных или центрального расположения. В поле PDL не является обязательным, рекомендуется задать PDL для всех пользователей. Рабочие нагрузки пользователя, не PDL будет выполнена подготовка в центрального расположения, на основе логики несколькими географически.   

Создание списка пользователей и включают в себя их имя участника-пользователя (UPN) и расположение кода для размещения соответствующих предпочитаемый данных. Со включают тестового пользователя и начальные пилотной группы. В этом списке потребуются процедуры настройки.

Если пользователи синхронизируются из Active Directory (AD) в локальной системе для Azure Active Directory (AAD), необходимо задать расположение предпочитаемый данных для синхронизированных пользователей с помощью Azure Active Directory подключение. Расположение предпочитаемый данных для синхронизированных пользователей с помощью Windows Azure AD PowerShell нельзя настроить напрямую. Рассматривается процесс настройки PDL в AD и синхронизировать его в [Azure Active Directory подключение синхронизации: Настройка предпочитаемого данных расположения для ресурсов Office 365](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

Администрирования клиента несколькими географически может отличаться от клиента несколькими географически, как многие из параметров SharePoint и OneDrive и службы, несколькими географически принять во внимание. Рекомендуется проверить [Администрирование среды ферма с несколькими географически](administering-a-multi-geo-environment.md) перед началом работы с конфигурацией.

Ознакомьтесь с [пользовательским интерфейсом в среде multgeo](multi-geo-user-experience.md) для получения дополнительных сведений о конечных пользователей в среде с несколькими географически.

Чтобы перед началом настройки OneDrive для бизнеса Multi-географически, обратитесь к разделу [Настройка OneDrive для бизнеса Multi-географически](multi-geo-tenant-configuration.md).

После выполнения настройки, не забудьте [перенос пользователей библиотеки OneDrive](move-onedrive-between-geo-locations.md) , чтобы получить от их расположения предпочитаемый данных пользователей.