---
title: Azure ExpressRoute для Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Сведения об использовании Azure ExpressRoute в Office 365 и планирование реализации проекта сети, который требуется, если выполняется развертывание Azure ExpressRoute для использования с Office 365.
ms.openlocfilehash: 5a82576b541e27c70bca490ff8dfe887ee879c83
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542342"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute для Office 365

Сведения об использовании Azure ExpressRoute в Office 365 и планирование реализации проекта сети, который требуется, если выполняется развертывание Azure ExpressRoute для использования с Office 365. Инфраструктура и платформы служб, работающих в Azure часто выиграют, устраняя рекомендации по архитектуре и производительности сети. В таких случаях рекомендуется ExpressRoute для Azure. Программное обеспечение, как службы и услуги, как Office 365 и Dynamics 365 построенных доступ к безопасности и надежности через Интернет. Соответственно только рекомендуется ExpressRoute для этих приложений в определенных сценариях. Могут читать о безопасности и производительности Интернета и когда может потребоваться Azure ExpressRoute для Office 365 в статье [сетевое подключение к Office 365](network-connectivity.md).

> [!NOTE]
> Запуск 31 июля 2017, можно включить Microsoft Peering непосредственно из консоли администрирования Azure или с помощью PowerShell. После включения Peering Майкрософт, можно создать фильтры маршрутов для получения определенного объявления маршрутов протокола BGP. Необходимо разрешение на создание фильтров для Office 365 и можно создавать фильтры приложений (ранее известных как CRM Online) Dynamics 365 сотрудничества с клиентами в любое время. В группу учетную запись Майкрософт обсудим процесс для получения авторизации для создания фильтров маршрута Office 365. Несанкционированная подписок для создания фильтров маршрутов для Office 365 получите [сообщение об ошибке](https://support.microsoft.com/kb/3181709)

Теперь можно добавить прямое сетевое подключение к Office 365 для выбранного Office 365 сетевого трафика. Azure ExpressRoute предоставляет прямое подключение прогнозируемой производительности и поставляется с соглашения об уровне ОБСЛУЖИВАНИЯ 99,95% времени работы сетевых компонентов Microsoft. Будет по-прежнему требуется подключение к Интернету для служб, которые не поддерживаются через Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Планирование Azure ExpressRoute для Office 365

В дополнение к Интернет-соединение можно перенаправлять подмножество их Office 365 сетевого трафика через прямое соединение, в котором представлены предсказуемость и времени в 99,95% соглашения об уровне ОБСЛУЖИВАНИЯ, работы сетевых компонентов Microsoft. Azure ExpressRoute предоставляет этот выделенный сетевое подключение к Office 365 и прочие облачные службы Майкрософт.

Независимо от того, есть ли у существующего MPLS глобальной сети можно добавить ExpressRoute в архитектуру сети одним из трех способов; поддерживаемые облачных exchange совместное расположение поставщика, поставщика подключения точка-точка Ethernet, или через поставщика подключения MPLS. В разделе какой [поставщиков, доступные в вашем регионе](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Прямое подключение ExpressRoute позволит подключения к приложениям, описанные в [включены службы что Office 365?](azure-expressroute.md#BKMK_WhatDoIGet) ниже. Сетевой трафик для других приложений и служб будет продолжать проходят через Интернет.

Рассмотрите возможность на следующей схеме высокого уровня сети, где отображаются типичного клиента Office 365, подключение к центров данных корпорации Майкрософт в Интернете для доступа ко всем приложениям Microsoft Office 365, Центр обновления Windows и TechNet. Клиенты используют следующий сетевой путь независимо от того, является ли они подключаются из локальной сети или подключение к Интернету независимо.

![Подключение к сети Office 365](media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Теперь рассмотрим Обновленная схема, которая описывается на Office 365 клиента, который использует ExpressRoute и Интернета для подключения к Office 365. Обратите внимание на то, что некоторые подключений, таких как узлы общедоступного DNS-сервера и сети доставки содержимого по-прежнему требуется общедоступных подключение к Интернету. Также Обратите внимание на то клиента пользователей, которые не находятся в их ExpressRoute подключенных построения выполняется подключение через Интернет.

![Подключения к Office 365 с помощью ExpressRoute](media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Нужны дополнительные сведения? Узнайте, как [управлять вашего сетевого трафика с ExpressRoute Azure для Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) и узнайте, как [настроить ExpressRoute Azure для Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). Мы также записанные [ExpressRoute Azure для обучающие курсы по Office 365](https://channel9.msdn.com/series/aer) 10 частей, посвященных Channel 9, чтобы объяснить понятиями более подробно.

([Azure ExpressRoute для Office 365](azure-expressroute.md#BKMK_HOME))

## <a name="what-office-365-services-are-included"></a>Включены какие службы Office 365?
<a name="BKMK_WhatDoIGet"> </a>

В следующей таблице приведены служб Office 365, которые поддерживаются через ExpressRoute. Обратитесь к [статье конечных точках Office 365](https://aka.ms/o365endpoints) понять, какие сети запросов для этих приложений требуется подключение к Интернету.

|**Включенных**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Углубимся<sup>1</sup> <br/> |
|Скайп для бизнеса сети<sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive для бизнеса<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Портал и общих<sup>1</sup> <br/> Azure Active Directory<sup>1</sup> <br/> AAD подключение<sup>1</sup> <br/> Office Online<sup>1</sup> <br/> |

<sup>1</sup> Каждый из этих приложений имеет требования подключения к Интернет через ExpressRoute не поддерживается, обратитесь к [статье конечных точках Office 365](https://aka.ms/o365endpoints) для получения дополнительных сведений.

Службы, которые не входят в состав ExpressRoute для Office 365, загружаемые файлы для Office 365 ProPlus клиента, учетное поставщика удостоверений в локальной и службы Office 365 (обслуживается 21 Vianet) в Китае.

([Azure ExpressRoute для Office 365](azure-expressroute.md#BKMK_HOME))

## <a name="implementing-expressroute-for-office-365"></a>Реализация ExpressRoute для Office 365

Реализация ExpressRoute, необходимо задействовать владельцев сети и приложений и требует тщательного планирования для определения нового [Сетевая архитектура маршрутизации](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), требования к пропускной способности, где будет безопасности, реализованных, высокая доступность и так далее. Чтобы реализовать ExpressRoute, вам потребуется:

1. Полного понимания необходимо ExpressRoute должна удовлетворять при планировании подключения к Office 365. Узнайте, какие приложения будут использовать Интернет или ExpressRoute и полностью планирование мощность сети, безопасность и высокой доступности должен в контексте с помощью ExpressRoute и Интернета для Office 365 трафика.

2. Определение авторами расположения для Интернета и трафика ExpressRoute<sup>1</sup>и исходящего трафика.

3. Определите емкость в Интернете и ExpressRoute подключений.

4. Составить план на месте для реализации безопасности и других элементов управления стандартной пограничной<sup>1</sup>.

5. Иметь допустимая учетная запись Microsoft Azure для подписки на ExpressRoute.

6. Выберите модель подключения к и [утвержденных поставщика](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Следует помнить, клиенты можно выбрать несколько моделей подключения к или партнеров и партнеров не совпадает с поставщиком существующих сетевых.

7. Проверка развертывания перед направляют трафик на ExpressRoute.

8. При необходимости [реализации качества обслуживания](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) и оценка региональных расширения.

<sup>1</sup> Рекомендации по важным производительности. Здесь решения кардинально могут влиять на задержку, которая крайне важна для приложений, таких как Скайп для бизнеса.

Дополнительные ссылки используйте наш [маршрутизации руководство](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) в дополнение к [документации ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

Чтобы приобрести ExpressRoute для Office 365, вам потребуются для работы с одного или нескольких [утвержденных поставщиков](https://azure.microsoft.com/documentation/articles/expressroute-locations/) для подготовки требуемого числа и размера цепи с подпиской ExpressRoute Premium. Существует никаких дополнительных лицензий на покупку из Office 365.

Ниже приводится краткое связь, которую можно использовать для возврата:[https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Подготовиться к переходу на регистрации для [ExpressRoute для Office 365](https://aka.ms/ert)?

([Azure ExpressRoute для Office 365](azure-expressroute.md#BKMK_HOME))

## <a name="related-topics"></a>Статьи по теме
<a name="BKMK_End"> </a>

[Сетевое подключение к Office 365](network-connectivity.md)

[Управление подключением ExpressRoute для Office 365](managing-expressroute-for-connectivity.md)

[Маршрутизация с помощью ExpressRoute для Office 365](routing-with-expressroute.md)

[Планирование сети при использовании ExpressRoute для Office 365](network-planning-with-expressroute.md)

[Реализация ExpressRoute для Office 365](implementing-expressroute.md)

[Использование протокола BGP сообществ в ExpressRoute для Office 365 сценариев (Предварительная версия)](bgp-communities-in-expressroute.md)

[Качество мультимедиа и производительность подключения к сети в Скайп для бизнеса в Интернете](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Настройка производительности Office 365 с помощью базовых показателей и журнала производительности](performance-tuning-using-baselines-and-history.md)

[План устранения проблем с производительностью Office 365](performance-troubleshooting-plan.md)

[URL-адреса и диапазоны IP-адресов для Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Office 365 сети и настройка производительности](network-planning-and-performance.md)