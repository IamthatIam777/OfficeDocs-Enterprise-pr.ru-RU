---
title: URL-адреса и диапазоны IP-адресов Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/13/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: Сводка. Для Office 365 требуется подключение к Интернету. Указанные ниже конечные точки должны быть доступны для клиентов, использующих планы Office 365, в том числе входящих в облако сообщества государственных учреждений (GCC).
hideEdit: true
ms.openlocfilehash: 2e6f5afd097aa85c09847b58fd3166961116b773
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542612"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="7806b-104">URL-адреса и диапазоны IP-адресов Office 365</span><span class="sxs-lookup"><span data-stu-id="7806b-104">Office 365 URLs and IP address ranges</span></span>

 <span data-ttu-id="7806b-p102">**Сводка.** Для Office 365 требуется подключение к Интернету. Указанные ниже конечные точки должны быть доступны для клиентов, использующих планы Office 365, в том числе входящих в облако сообщества государственных учреждений (GCC).</span><span class="sxs-lookup"><span data-stu-id="7806b-p102">**Summary:** Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7806b-p103">Корпорация Майкрософт разрабатывает веб-службу на базе REST для записей IP-адресов и полных доменных имен на этой странице. Эта новая служба поможет настраивать и обновлять устройства периметра сети, такие как брандмауэры и прокси-серверы. Вы можете скачать список конечных точек, текущую версию списка или сведения об определенных изменениях. Со временем эта служба заменит XML-документ, связанный с этой страницей. Сведения о новой службе см. в разделе [Веб-служба](managing-office-365-endpoints.md#webservice).</span><span class="sxs-lookup"><span data-stu-id="7806b-p103">Microsoft is developing a REST-based web service for the IP address and FQDN entries on this page. This new service will help you configure and update network perimeter devices such as firewalls and proxy servers. You can download the list of endpoints, the current version of the list, or specific changes. This service will eventually replace the XML document linked from this page. To try out this new service, go to [Web service](managing-office-365-endpoints.md#webservice).</span></span> 
  
<span data-ttu-id="7806b-112">*Office 365 по всему миру (+ GCC)* | [Office 365, предоставляемый 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](office-365-germany-endpoints.md) | [Office 365 для DoD государственных организаций США](office-365-u-s-government-dod-endpoints.md)  | [Office 365 для GCC High государственных организаций США](office-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="7806b-112">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](office-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](office-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](office-365-u-s-government-gcc-high-endpoints.md) |</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="7806b-113">**Последнее обновление:** 01.08.2018 — ![RSS](media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Подписка на журнал изменений](https://go.microsoft.com/fwlink/p/?linkid=236301)</span><span class="sxs-lookup"><span data-stu-id="7806b-113">**Last updated:** 8/1/2018 - ![RSS](media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://go.microsoft.com/fwlink/p/?linkid=236301)</span></span> <br/> |<span data-ttu-id="7806b-114">**Скачать:** все обязательные и необязательные назначения в одном списке [в формате XML](https://go.microsoft.com/fwlink/?LinkId=533185).</span><span class="sxs-lookup"><span data-stu-id="7806b-114">**Download:** all required and optional destinations in one [XML formatted](https://go.microsoft.com/fwlink/?LinkId=533185) list.</span></span>  <br/> | <span data-ttu-id="7806b-115">**Используйте:** наши [PAC-файлы](managing-office-365-endpoints.md#pacfiles) прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="7806b-115">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |
   
 <span data-ttu-id="7806b-p104">Сначала ознакомьтесь со статьей [Управление конечными точками Office 365](managing-office-365-endpoints.md) с рекомендациями по управлению сетевым подключением с использованием этих данных. В начале каждого месяца данные конечных точек обновляются новыми IP-адресами и URL-адресами, публикуемыми за 30 дней до их активации. Это позволяет пользователям, не имеющим автоматических обновлений, завершить свои процессы до того, как новое подключение станет обязательным. Конечные точки также могут обновляться в течение месяца, если это требуется для решения проблем, выявленных службой поддержки, инцидентов безопасности или в связи с другими экстренными рабочими требованиями. Данные, представленные ниже на этой странице, получены из веб-служб на базе REST. Если вы используете сценарий или сетевое устройство для доступа к этим данным, сразу переходите к разделу [Веб-служба](managing-office-365-endpoints.md#webservice).</span><span class="sxs-lookup"><span data-stu-id="7806b-p104">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you are using a script or a network device to access this data, you should go to the [Web service](managing-office-365-endpoints.md#webservice) directly.</span></span>

<span data-ttu-id="7806b-p105">Ниже в данных конечной точки перечислены требования к подключениям с компьютера пользователя к Office 365. Они не включают сетевые подключения от корпорации Майкрософт к сети клиентов, которые иногда называются гибридными или входящими сетевыми подключениями.</span><span class="sxs-lookup"><span data-stu-id="7806b-p105">Endpoint data below lists requirements for connectivity from a user’s machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.</span></span>

<span data-ttu-id="7806b-p106">Конечные точки сгруппированы в четыре области обслуживания. Первые три области обслуживания можно независимо выбирать для подключения. Четвертая область обслуживания — это общая зависимость (называемая Microsoft 365 Common and Office Online), которая всегда должна обеспечиваться сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="7806b-p106">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office Online) and must always have network connectivity.</span></span>

<span data-ttu-id="7806b-127">Показанные столбцы с данными:</span><span class="sxs-lookup"><span data-stu-id="7806b-127">Data columns shown are:</span></span>

- <span data-ttu-id="7806b-p107">**Идентификатор**. Код строки, также известный как набор конечной точки. Этот идентификатор совпадает с возвращаемым веб-службой для набора конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7806b-p107">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="7806b-p108">**Категория**. Показывает, присвоена ли набору конечной точки категория "Optimize" (Оптимизация), "Allow" (Разрешение) или "Default" (По умолчанию). С этими категориями и инструкцией по их управлению можно ознакомиться на странице [http://aka.ms/pnc](http://aka.ms/pnc). В этом столбце также указано, какие наборы конечной точки необходимы для обеспечения сетевого подключения. Для наборов конечной точки, не требующихся для сетевого подключения, в этом поле указываются примечания о том, что при блокировании этого набора конечной точки функции будут отсутствовать. При исключении всей области обслуживания наборы конечной точки, перечисленные как обязательные, не требуют подключения.</span><span class="sxs-lookup"><span data-stu-id="7806b-p108">**Category**: Shows whether the endpoint set is categorized as “Optimize”, “Allow”, or “Default”. You can read about these categories and guidance for management of them at [http://aka.ms/pnc](http://aka.ms/pnc). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="7806b-p109">**ER**. Значение **Да**, если набор конечной точки поддерживается в Azure ExpressRoute с префиксами маршрутизации Office 365. Сообщество BGP, которое включает указанные префиксы маршрутизации, соответствует области службы в списке. Если значение ER соответствует **Нет**, это означает, что ExpressRoute не поддерживается для этого набора конечной точки. Тем не менее, не нужно считать, что для набора конечной точки со значением ER равным **Нет** отсутствуют объявленные маршруты.</span><span class="sxs-lookup"><span data-stu-id="7806b-p109">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="7806b-p110">**Адреса**. Перечисляет полные доменные имена или подстановочные доменные имена, а также диапазоны IP-адресов для набора конечной точки. Обратите внимание, что диапазон IP-адресов представлен в формате CIDR и может содержать несколько отдельных IP-адресов в указанной сети.</span><span class="sxs-lookup"><span data-stu-id="7806b-p110">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="7806b-p111">**Порты**. Перечисляет порты TCP или UDP, которые объединяются с адресами для создания конечной точки сети. Можно заметить дублирование в диапазонах IP-адресов при перечислении разных портов.</span><span class="sxs-lookup"><span data-stu-id="7806b-p111">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](./includes/office-365-worldwide-endpoints.md)]

## <a name="related-topics"></a><span data-ttu-id="7806b-143">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7806b-143">Related Topics</span></span>

[<span data-ttu-id="7806b-144">Управление конечными точками Office 365</span><span class="sxs-lookup"><span data-stu-id="7806b-144">Office 365 Germany endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="7806b-145">Устранение неполадок с подключением к Office 365</span><span class="sxs-lookup"><span data-stu-id="7806b-145">Office 365 connectivity limits</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[<span data-ttu-id="7806b-146">Подключение клиентских компьютеров</span><span class="sxs-lookup"><span data-stu-id="7806b-146">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="7806b-147">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="7806b-147">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="7806b-148">Диапазоны IP-адресов центра обработки данных Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="7806b-148">Microsoft Azure Datacenter IP Ranges</span></span>](https://www.microsoft.com/download/details.aspx?id=41653)
  
[<span data-ttu-id="7806b-149">Пространство публичных IP-адресов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7806b-149">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)
