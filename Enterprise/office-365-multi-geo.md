---
title: Office 365 с поддержкой нескольких регионов
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
ms.collection: Strat_SP_gtc
localization_priority: Priority
description: Расширьте свою географию присутствия Office 365 с помощью поддержки нескольких регионов в Office 365.
ms.openlocfilehash: e216f61806ea5d648519ac7217acf7dbaddd1419
ms.sourcegitcommit: 8ba20f1b1839630a199585da0c83aaebd1ceb9fc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934082"
---
# <a name="office-365-multi-geo"></a>Office 365 с поддержкой нескольких регионов

Поддержка нескольких регионов в Office 365 позволяет организации развивать бизнес в нескольких географических регионах или странах, используя существующий клиент Office 365. Обратитесь в отдел по работе с клиентами Майкрософт, чтобы зарегистрировать свою международную компанию для работы с несколькими регионами в Office 365.
  
Поддержка нескольких регионов в Office 365 позволяет подготавливать и хранить неактивные данные в выбранных вами регионах, а также предоставлять современные возможности для работы всем сотрудникам.

#### <a name="video-introducing-office-365-multi-geo"></a>Видео: знакомство с Office 365 с поддержкой нескольких регионов

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1Yk6B?autoplay=false]

В среде с поддержкой нескольких регионов клиент Office 365 состоит из центрального расположения (где изначально подготавливается подписка на Office 365) и одного или нескольких периферийных расположений. В клиенте с несколькими регионами информация о регионах, группах и пользователях обрабатывается в Azure Active Directory (AAD). Так как информация клиента обрабатывается централизованно и синхронизируется с каждым регионом, общий доступ и возможности в компании носят глобальный характер.

![Снимок экрана: карта нескольких регионов в Центре администрирования SharePoint](media/multi-geo-world-map.png)

Обратите внимание, что функция поддержки нескольких регионов в Office 365 изначально не предназначена для повышения производительности. Она предназначена для соблюдения требований по расположению данных. Сведения о повышении производительности для Office 365 см. в статье [Планирование сети и настройка производительности для Office 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) или обратитесь к группе поддержки.

## <a name="terminology"></a>Терминология

Ниже указаны основные термины, используемые при описании Office 365 с поддержкой нескольких регионов:

- **Центральное расположение** — географическое расположение, в котором изначально подготовлен клиент.
- **Администратор геообъекта** — администратор, который может управлять одним или несколькими периферийными расположениями.
- **Код региона** — код из трех букв для определенного географического расположения.
- **Географическое расположение** — регион, который можно использовать в клиенте с поддержкой нескольких регионов для размещения данных, включая почтовые ящики Exchange, а также сайты OneDrive и SharePoint.
- **Предпочтительное расположение данных (PDL)** — свойство пользователя, устанавливаемое администратором, которое указывает географическое расположение, где следует подготовить почтовый ящик Exchange и хранилище OneDrive пользователей. PDL также определяет, где подготовлены сайты SharePoint, созданные пользователем.
- **Периферийное расположение** — географическое расположение, где учитывающие регион рабочие нагрузки Office 365 (SharePoint, OneDrive и Exchange) включены в клиенте с поддержкой нескольких регионов.
- **Клиент** — представление организации в Office 365, которое имеет, как правило, один или несколько связанных с ним доменов (например, contoso.com).

## <a name="office-365-multi-geo-availability"></a>Доступность поддержки нескольких регионов в Office 365

В настоящее время поддержка нескольких регионов в Office 365 доступна в таких странах и регионах:

[!INCLUDE [Office 365 Multi-Geo locations](includes/office-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Начало работы

Чтобы приступить к работе с несколькими регионами, следуйте указанным ниже инструкциям.

1. Совместно с группой специалистов, занимающихся учетными записями, добавьте план обслуживания _с поддержкой нескольких регионов в Office 365_. Они помогут вам добавить необходимое количество лицензий.

   Прежде чем вы сможете начать работу в Office 365 с поддержкой нескольких регионов корпорации Майкрософт потребуется настроить ваш клиент Exchange Online для поддержки нескольких регионов. Этот разовый процесс настройки запускается после заказа плана обслуживания с *функциями поддержки нескольких регионов в Office 365* и появления лицензий в вашем клиенте. Вы получите уведомления в [Центре сообщений Office 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) после присвоения лицензий с поддержкой нескольких регионов и затем сможете начать настройку и использование функций поддержки нескольких регионов в Office 365.

2. См. статью [Планирование среды с поддержкой нескольких регионов](plan-for-multi-geo.md).

3. Узнайте об [администрировании среды с поддержкой нескольких регионов](administering-a-multi-geo-environment.md) и о том, [как пользователи взаимодействуют со средой](multi-geo-user-experience.md).

4. Когда вы будете готовы настроить Office 365 с поддержкой нескольких регионов, [настройте свой клиент для поддержки нескольких регионов](multi-geo-tenant-configuration.md).

5. [Настройка поиска](configure-search-for-multi-geo.md).

## <a name="see-also"></a>См. также

[Aka.ms/GoMultiGeo ](https://Aka.ms/GoMultiGeo)

[Поддержка нескольких регионов в OneDrive и SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365.md)

[Поддержка нескольких регионов в Exchange Online](multi-geo-capabilities-in-exchange-online.md)