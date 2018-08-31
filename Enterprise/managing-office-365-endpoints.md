---
title: Управление конечных точках Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 7/18/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365_Setup
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Некоторые сети предназначены для ограничения доступа к Интернету, чтобы убедиться, что компьютеры в сети, как они могут получить доступ к Office 365, администраторов сети и прокси-сервер должен управлять список полных доменных имен, URL-адреса, а IP-адресов, будут включены в список конечных точках Office 365. Эти потребности для добавления правила прокси-сервера или брандмауэра и PAC файлы для обеспечения сетевых запросов дают возможность связи с Office 365.
ms.openlocfilehash: 0396174719adc7794a1d6bb4b1f950bfe4603996
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542436"
---
# <a name="managing-office-365-endpoints"></a><span data-ttu-id="519b8-104">Управление конечных точках Office 365</span><span class="sxs-lookup"><span data-stu-id="519b8-104">Managing Office 365 endpoints</span></span>

## <a name="office-365-network-connectivity"></a><span data-ttu-id="519b8-105">Подключение к сети Office 365</span><span class="sxs-lookup"><span data-stu-id="519b8-105">Office 365 network connectivity</span></span>

 <span data-ttu-id="519b8-p102">Подключение к Office 365 состоят из большой поток запросов надежной сети, выполняющие лучше всего, когда они состоят через выходной небольшой задержкой, рядом с пользователем. Некоторые подключения к Office 365, могут воспользоваться преимуществами оптимизации подключение.</span><span class="sxs-lookup"><span data-stu-id="519b8-p102">Connections to Office 365 consist of high volume, trusted network requests that perform best when they're made over a low-latency egress that is near the user. Some Office 365 connections can benefit from optimizing the connection.</span></span> 
  
1. <span data-ttu-id="519b8-108">Убедитесь, брандмауэр разрешить списки разрешенных для подключения к конечным точкам Office 365.</span><span class="sxs-lookup"><span data-stu-id="519b8-108">Ensure your firewall allow lists allow for connectivity to Office 365 endpoints.</span></span>
    
2. <span data-ttu-id="519b8-109">Используйте инфраструктуры прокси-сервера, чтобы разрешить подключение к Интернету для подстановочные знаки и отменить публикацию назначения.</span><span class="sxs-lookup"><span data-stu-id="519b8-109">Use your proxy infrastructure to allow Internet connectivity to wildcard and unpublished destinations.</span></span>
    
3. <span data-ttu-id="519b8-110">Ведение конфигурация оптимальную пограничной сети.</span><span class="sxs-lookup"><span data-stu-id="519b8-110">Maintain an optimal perimeter network configuration.</span></span>
    
4. <span data-ttu-id="519b8-111">[Убедитесь, что они будут наиболее подключения](https://aka.ms/o365perfprinciples).</span><span class="sxs-lookup"><span data-stu-id="519b8-111">[Ensure you're getting the best connectivity](https://aka.ms/o365perfprinciples).</span></span>
    
5. <span data-ttu-id="519b8-112">Чтение [Сетевого подключения к Office 365 принципы](office-365-network-connectivity-principles.md) понять принципы подключения для безопасного управления Office 365 трафика и начало обеспечить максимально высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="519b8-112">Read [Office 365 Network Connectivity Principles](office-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> 
    
![Подключение к Office 365 через брандмауэров и прокси-серверов.](media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)
  
## <a name="update-your-firewalls-outbound-allow-lists"></a><span data-ttu-id="519b8-114">Обновление брандмауэра исходящих списков</span><span class="sxs-lookup"><span data-stu-id="519b8-114">Update your firewall's outbound allow lists</span></span>

<span data-ttu-id="519b8-p103">Можно оптимизировать сети, отправив все доверенных Office 365 сетевые запросы непосредственно через брандмауэр, обход всех проверку уровня дополнительных пакетов или обработки. Это уменьшает снижения производительности из задержку и уменьшает требований к мощности демилитаризованной зоны. Выбрать, какие сетевые запросы на доверие проще всего использовать наш готовые файлы PAC на вкладке **прокси-серверы** выше.</span><span class="sxs-lookup"><span data-stu-id="519b8-p103">You can optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet level inspection or processing. This reduces slow performance from latency and reduces your perimeter capacity requirements. The easiest way to choose which network requests to trust is to use our pre-built PAC files on the **Proxies** tab above.</span></span> 
  
<span data-ttu-id="519b8-p104">Если исходящий трафик блоки вашего брандмауэра, может потребоваться обеспечить соблюдение IP-адресов и полных доменных имен указано, что **требуется** в [XML-файл](https://go.microsoft.com/fwlink/?LinkId=533185) включены в список разрешений. Распознавать все службы требуют использования служб, сторонних производителей. Мы не предоставляют IP-адреса для этих сторонних производителей службы, такие как поставщиков поставщиков сети доставки содержимого, DNS и так далее. Для полной функциональности Office 365 необходимо сделать доступными все назначения по Office 365 запросу независимо от того, объем сведений, мы публикации о назначении.</span><span class="sxs-lookup"><span data-stu-id="519b8-p104">If your firewall blocks outbound traffic, you'll want to ensure all of the IP and FQDNs listed as **Required** in this [XML file](https://go.microsoft.com/fwlink/?LinkId=533185) are on the allow list. Recognize all services require the use of some 3rd party services. We don't provide IP addresses for these 3rd party services such as certificate providers, Content Delivery Networks, DNS providers, and so on. For full Office 365 functionality, you must be able to reach all destinations requested by Office 365 regardless of how much information we publish about the destination.</span></span> 
  
<span data-ttu-id="519b8-122">Множество назначений опубликовано IP-адрес или не представлены в виде домена подстановочные знаки без определенного полного доменного имени, для использования этой функции необходимо иметь возможность устранения сетевые запросы текущий IP-адрес был запрошен и отправки сетевой запрос через Интернет.</span><span class="sxs-lookup"><span data-stu-id="519b8-122">Many destinations do not have an IP address published or are listed as a wildcard domain with no specific fully qualified domain name, to use this functionality you must be able to resolve these network requests to the current IP address being requested and send the network request over the Internet.</span></span>
  
<span data-ttu-id="519b8-p105">Автоматизация процесса с помощью брандмауэра, который выполняет синтаксический анализ XML-файла от вашего имени и обновляет правил автоматически на основе служб или компонентов, которые предполагается маршрутизировать непосредственно через брандмауэр. Можно также использовать средство [Диапазон Azure](https://azurerange.azurewebsites.net/) , которая создала сообщества и анализ XML-код для вас с параметры экспорта для конфигурации списка Cisco XE маршрута или списка управления Доступом, обычный текст или CSV.</span><span class="sxs-lookup"><span data-stu-id="519b8-p105">Automate your process by using a firewall that parses the XML file on your behalf and updates your rules automatically based on the services or features you plan to route directly through your firewall. You can also use the [Azure Range](https://azurerange.azurewebsites.net/) tool that has been built by the community and parses the XML for you with export options for Cisco XE Route or ACL list configuration, plain text, or CSV.</span></span> 
  
<span data-ttu-id="519b8-125">Больше описание назначения сети доступен на веб- [сайт ссылку](urls-and-ip-address-ranges.md) также в наш [RSS-канал на основе журнала изменений](https://go.microsoft.com/fwlink/p/?linkid=236301) , можно подписаться на изменения.</span><span class="sxs-lookup"><span data-stu-id="519b8-125">A longer explanation of the network destinations is available on our [reference site](urls-and-ip-address-ranges.md) as well through our [RSS based change log](https://go.microsoft.com/fwlink/p/?linkid=236301) so you can subscribe to changes.</span></span> 
  
<span data-ttu-id="519b8-126"><a name="pacfiles"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-126"></span></span>
## <a name="configure-outbound-paths-with-pac-files"></a><span data-ttu-id="519b8-127">Настройка исходящего пути с помощью PAC-файлов</span><span class="sxs-lookup"><span data-stu-id="519b8-127">Configure outbound paths with PAC files</span></span>

<span data-ttu-id="519b8-p106">Используйте PAC или WPAD файлов для управления сетевых запросов, которые связаны с Office 365, но не предоставляются IP-адреса. Типичные сетевые запросы, отправляемые через прокси-сервер или периметра устройство требует дополнительных задержки. Во время проверки подлинности прокси-сервера приводит к наибольшим налогах, другие службы, включая репутации подстановки и попытки проверки пакетов может привести к низкого уровня пользовательского интерфейса. Кроме того эти устройства сети периметра должны достаточную емкость для обработки всех запросов сети. Мы рекомендуем обход прокси-сервера или проверка на наличие инфраструктуры для прямой запрос сети Office 365.</span><span class="sxs-lookup"><span data-stu-id="519b8-p106">Use PAC or WPAD files to manage network requests that are associated with Office 365 but don't have an IP address provided. Typical network requests that are sent through a proxy or perimeter device incur additional latency. While proxy authentication incurs the largest tax, other services such as reputation lookup and attempts to inspect packets can cause a poor user experience. Additionally, these perimeter network devices need enough capacity to process all of the network requests. We recommend bypassing your proxy or inspection infrastructure for direct Office 365 network requests.</span></span>
  
<span data-ttu-id="519b8-p107">Используйте один из наших файлов PAC качестве отправной точки для определения какие сетевого трафика будут отправляться на прокси-сервер и которого будут отправляться брандмауэр. Если вы не знакомы с PAC или WPAD файлов, прочитайте этой записи о [файлах развертывание PAC](https://blogs.technet.microsoft.com/undocumentedfeatures/2016/04/06/deploying-the-office-365-proxy-pac-to-manage-your-users/) из одного из наших консультанты Office 365. Вы наверняка хотели бы просмотрите их в качестве отправной точки и изменить в соответствии с вашей средой.</span><span class="sxs-lookup"><span data-stu-id="519b8-p107">Use one of our PAC files as a starting place to determine what network traffic will be sent to a proxy and which will be sent to a firewall. If you're new to PAC or WPAD files, read this post about [deploying PAC files](https://blogs.technet.microsoft.com/undocumentedfeatures/2016/04/06/deploying-the-office-365-proxy-pac-to-manage-your-users/) from one of our Office 365 consultants. You'll want to review these as a starting place and edit to suit your environment.</span></span> 
  
 <span data-ttu-id="519b8-136">**Обновлено 7/10/2018 PAC файлов**.</span><span class="sxs-lookup"><span data-stu-id="519b8-136">**PAC files updated 7/10/2018**.</span></span> 
  
### <a name="1---pac-file-separates-required-internet-fqdns-from-known-office-365-fqdn"></a><span data-ttu-id="519b8-137">#1 - файл PAC: разделяет требуется Internet полные доменные имена из полного доменного ИМЕНИ для известных Office 365.</span><span class="sxs-lookup"><span data-stu-id="519b8-137">#1 - PAC file: Separates required Internet FQDNs from known Office 365 FQDN.</span></span>

<span data-ttu-id="519b8-p108">Первый пример представляет демонстрационный наших рекомендуемый подход к управлению конечных точек через Интернет только. Обходит прокси-сервера для Office 365 назначения, где будет опубликована IP-адрес и отправляет запросы на оставшихся сетевой прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="519b8-p108">The first example is a demonstration of our recommended approach to managing endpoints over the Internet only. Bypasses the proxy for Office 365 destinations where the IP address is published and sends remaining network requests to the proxy.</span></span>
  
<span data-ttu-id="519b8-140">Фрагмент кода:</span><span class="sxs-lookup"><span data-stu-id="519b8-140">Code snippet:</span></span>
  
```
// JavaScript source code
//July 2018 - Updates go live 1st August2018
//This PAC file contains all FQDNs needed for all services and splits the traffic between those which Microsoft can provide IPs for (so can be sent through a managed firewall with conditional access if desired) and those which IPs cannot be provided for, so need to go to an unrestricted proxy or egress. 
//Due to the use of wildcards, some extra logic is provided to send traffic to the proxy before a 'direct' wildcard is hit.
//Includes Core ProPlus URLs but not Office Mobile/IPAD/IOS/ANDROID fqdns from https://support.office.com/en-gb/article/Network-requests-in-Office-365-ProPlus-eb73fcd1-ca88-4d02-a74b-2dd3a9f3364d
//Every Effort is made to ensure 100% accuracy but this PAC should be used as an example and cross-checked with your needs and the Office 365 URL &amp; IP page
//Intended only for Worldwide Office 365 instances, which the vast majority of customers will be using
function FindProxyForURL(url, host)
{
    // Define proxy server
    var proxyserver = "PROXY 10.10.10.10:8080";
    var proxyserver2 = "PROXY 10.10.10.11:8080";
    // Make host lowercase
    var lhost = host.toLowerCase();
    host = lhost;
    //Catch explicit FQDNs which need the proxy but are covered under wildcarded FQDNs which have IPs. This has to be done first before the wildcard is hit
    if ((shExpMatch(host, "quicktips.skypeforbusiness.com"))    
        || (shExpMatch(host, "*.um.outlook.com"))
        || (shExpMatch(host, "r3.res.office365.com"))
        || (shExpMatch(host, "r3.res.outlook.com"))
        || (shExpMatch(host, "r4.res.office365.com"))
        || (shExpMatch(host, "xsi.outlook.com"))
        || (shExpMatch(host, "r1.res.office365.com")))
    {
        return proxyserver;
    }
        //Send FQDNs which Microsoft provide IPs for direct, so they can be sent via a firewall
    else if ((isPlainHostName(host))
    || (shExpMatch(host, "*.aria.microsoft.com"))    
    || (shExpMatch(host, "*.dc.trouter.io"))
    || (shExpMatch(host, "*.lync.com"))
    || (shExpMatch(host, "*.manage.office.com"))
    || (shExpMatch(host, "*.office365.com"))
    || (shExpMatch(host, "*.onenote.com"))
    || (shExpMatch(host, "*.outlook.com"))
    || (shExpMatch(host, "*.outlook.office.com"))
    || (shExpMatch(host, "*.portal.cloudappsecurity.com"))
    || (shExpMatch(host, "*.protection.office.com"))
    || (shExpMatch(host, "*.sharepoint.com"))
    || (shExpMatch(host, "*.skype.com"))
    || (shExpMatch(host, "*.skypeforbusiness.com"))
    || (shExpMatch(host, "*.svc.ms"))
    || (shExpMatch(host, "*.teams.microsoft.com"))
    || (shExpMatch(host, "*.yammer.com"))
    || (shExpMatch(host, "*.yammerusercontent.com"))    
    || (shExpMatch(host, "*broadcast.officeapps.live.com"))
    || (shExpMatch(host, "*excel.officeapps.live.com"))
    || (shExpMatch(host, "*onenote.officeapps.live.com"))
    || (shExpMatch(host, "*powerpoint.officeapps.live.com"))
    || (shExpMatch(host, "*view.officeapps.live.com"))
    || (shExpMatch(host, "*visio.officeapps.live.com"))
    || (shExpMatch(host, "*word-edit.officeapps.live.com"))
    || (shExpMatch(host, "*word-view.officeapps.live.com"))
    || (shExpMatch(host, "admin.microsoft.com"))    
    || (shExpMatch(host, "account.office.net"))
    || (shExpMatch(host, "adminwebservice.microsoftonline.com"))
    || (shExpMatch(host, "agent.office.net"))
    || (shExpMatch(host, "api.login.microsoftonline.com"))
    || (shExpMatch(host, "api.passwordreset.microsoftonline.com"))
    || (shExpMatch(host, "apc.delve.office.com"))
    || (shExpMatch(host, "aus.delve.office.com"))
    || (shExpMatch(host, "autologon.microsoftazuread-sso.com"))  
    || (shExpMatch(host, "becws.microsoftonline.com"))
    || (shExpMatch(host, "browser.pipe.aria.microsoft.com"))  
    || (shExpMatch(host, "can.delve.office.com"))
    || (shExpMatch(host, "ccs.login.microsoftonline.com"))
    || (shExpMatch(host, "ccs-sdf.login.microsoftonline.com"))
    || (shExpMatch(host, "clientconfig.microsoftonline-p.net"))
    || (shExpMatch(host, "clientlog.portal.office.com"))
    || (shExpMatch(host, "companymanager.microsoftonline.com"))
    || (shExpMatch(host, "cus-000.tasks.osi.office.net"))
    || (shExpMatch(host, "delve.office.com"))
    || (shExpMatch(host, "device.login.microsoftonline.com"))    
    || (shExpMatch(host, "ea-000.tasks.osi.office.net"))
    || (shExpMatch(host, "eur.delve.office.com"))
    || (shExpMatch(host, "eus-zzz.tasks.osi.office.net"))
    || (shExpMatch(host, "gbr.delve.office.com"))    
    || (shExpMatch(host, "hip.microsoftonline-p.net"))
    || (shExpMatch(host, "hipservice.microsoftonline.com"))
    || (shExpMatch(host, "home.office.com"))
    || (shExpMatch(host, "ind.delve.office.com"))
    || (shExpMatch(host, "jpn.delve.office.com"))
    || (shExpMatch(host, "kor.delve.office.com"))
    || (shExpMatch(host, "lam.delve.office.com"))
    || (shExpMatch(host, "login.microsoft.com"))
    || (shExpMatch(host, "login.microsoftonline.com"))
    || (shExpMatch(host, "login.microsoftonline-p.com"))
    || (shExpMatch(host, "login.windows.net"))
    || (shExpMatch(host, "logincert.microsoftonline.com"))
    || (shExpMatch(host, "loginex.microsoftonline.com"))
    || (shExpMatch(host, "login-us.microsoftonline.com"))     
    || (shExpMatch(host, "manage.office.com"))
    || (shExpMatch(host, "mobile.pipe.aria.microsoft.com"))
    || (shExpMatch(host, "nam.delve.office.com"))
    || (shExpMatch(host, "neu-000.tasks.osi.office.net"))
    || (shExpMatch(host, "nexus.microsoftonline-p.com"))
    || (shExpMatch(host, "nexus.officeapps.live.com"))
    || (shExpMatch(host, "nexusrules.officeapps.live.com"))
    || (shExpMatch(host, "office.live.com"))
    || (shExpMatch(host, "officeapps.live.com"))
    || (shExpMatch(host, "passwordreset.microsoftonline.com"))
    || (shExpMatch(host, "portal.microsoftonline.com"))
    || (shExpMatch(host, "portal.office.com"))
    || (shExpMatch(host, "protection.office.com"))
    || (shExpMatch(host, "provisioningapi.microsoftonline.com"))
    || (shExpMatch(host, "scsinstrument-ss-us.trafficmanager.net"))   
    || (shExpMatch(host, "scsquery-ss-asia.trafficmanager.net")) 
    || (shExpMatch(host, "scsquery-ss-eu.trafficmanager.net")) 
    || (shExpMatch(host, "scsquery-ss-us.trafficmanager.net"))
    || (shExpMatch(host, "sea-000.tasks.osi.office.net"))    
    || (shExpMatch(host, "stamp2.login.microsoftonline.com"))
    || (shExpMatch(host, "suite.office.net"))    
    || (shExpMatch(host, "tasks.office.com"))
    || (shExpMatch(host, "teams.microsoft.com"))
    || (shExpMatch(host, "testconnectivity.microsoft.com"))
    || (shExpMatch(host, "webshell.suite.office.com"))
    || (shExpMatch(host, "weu-000.tasks.osi.office.net"))
    || (shExpMatch(host, "wus-000.tasks.osi.office.net"))
    || (shExpMatch(host, "www.office.com")))
      
    {
        return "DIRECT";
    }
    else
        // Send all unknown IP traffic to Proxy for unrestricted access. This section is not necessary if you have a catchall for all other traffic to go to an unfiltered proxy. 
        //However the fqdns required, but for which we dont have IPs for, are listed here incase you need an explicit list.
   if          ((shExpMatch(host, "*.aadrm.com"))
        || (shExpMatch(host, "*.adhybridhealth.azure.com")) 
        || (shExpMatch(host, "*.adl.windows.com"))   
        || (shExpMatch(host, "*.api.microsoftstream.com"))      
        || (shExpMatch(host, "*.assets-yammer.com"))   
        || (shExpMatch(host, "*.azureedge.net"))            
        || (shExpMatch(host, "*.azurerms.com"))
        || (shExpMatch(host, "*.cloudapp.net"))
        || (shExpMatch(host, "*.entrust.net")) 
        || (shExpMatch(host, "*.geotrust.com"))   
        || (shExpMatch(host, "*.helpshift.com"))   
        || (shExpMatch(host, "*.hockeyapp.net"))    
        || (shExpMatch(host, "*.localytics.com"))    
        || (shExpMatch(host, "*.log.optimizely.com"))    
        || (shExpMatch(host, "*.microsoft.com"))
        || (shExpMatch(host, "*.microsoftonline.com"))
        || (shExpMatch(host, "*.microsoftonline-p.com"))
        || (shExpMatch(host, "*.microsoftonline-p.net"))
        || (shExpMatch(host, "*.msecnd.net"))
        || (shExpMatch(host, "*.msedge.net"))      
        || (shExpMatch(host, "*.msocdn.com")) 
        || (shExpMatch(host, "*.mstea.ms"))    
        || (shExpMatch(host, "*.notification.api.microsoftstream.com")) 
        || (shExpMatch(host, "*.o365weve.com"))     
        || (shExpMatch(host, "*.office.com"))   
        || (shExpMatch(host, "*.office.net"))
        || (shExpMatch(host, "*.omniroot.com"))
        || (shExpMatch(host, "*.onmicrosoft.com"))
        || (shExpMatch(host, "*.phonefactor.net"))
        || (shExpMatch(host, "*.public-trust.com"))
        || (shExpMatch(host, "*.search.production.apac.trafficmanager.net"))
        || (shExpMatch(host, "*.search.production.emea.trafficmanager.net"))
        || (shExpMatch(host, "*.search.production.us.trafficmanager.net"))
        || (shExpMatch(host, "*.secure.skypeassets.com"))  
        || (shExpMatch(host, "*.sfbassets.com"))
        || (shExpMatch(host, "*.sharepointonline.com"))
        || (shExpMatch(host, "*.sway.com"))
        || (shExpMatch(host, "*.symcb.com"))
        || (shExpMatch(host, "*.teams.microsoft.com"))  
        || (shExpMatch(host, "*.tenor.com"))  
        || (shExpMatch(host, "*.symcd.com"))     
        || (shExpMatch(host, "*.users.storage.live.com"))
        || (shExpMatch(host, "*.verisign.com"))
        || (shExpMatch(host, "*.verisign.net"))
        || (shExpMatch(host, "*.windows.net"))
        || (shExpMatch(host, "*cdn.onenote.net"))
        || (shExpMatch(host, "account.activedirectory.windowsazure.com"))
        || (shExpMatch(host, "ad.atdmt.com"))
        || (shExpMatch(host, "admin.onedrive.com"))
        || (shExpMatch(host, "ajax.aspnetcdn.com"))
        || (shExpMatch(host, "aka.ms"))
        || (shExpMatch(host, "amp.azure.net"))
        || (shExpMatch(host, "api.microsoftstream.com"))
        || (shExpMatch(host, "apis.live.net"))  
        || (shExpMatch(host, "apps.identrust.com"))  
        || (shExpMatch(host, "assets.onestore.ms"))
        || (shExpMatch(host, "auth.gfx.ms"))
        || (shExpMatch(host, "cacerts.digicert.com"))        
        || (shExpMatch(host, "cdn.odc.officeapps.live.com"))  
        || (shExpMatch(host, "cdn.onenote.net"))
        || (shExpMatch(host, "cdn.optimizely.com")) 
        || (shExpMatch(host, "cert.int-x3.letsencrypt.org"))
        || (shExpMatch(host, "client.hip.live.com"))
        || (shExpMatch(host, "connect.facebook.net"))        
        || (shExpMatch(host, "crl.globalsign.com"))
        || (shExpMatch(host, "crl.globalsign.net"))
        || (shExpMatch(host, "crl.identrust.com"))    
        || (shExpMatch(host, "crl3.digicert.com"))  
        || (shExpMatch(host, "crl4.digicert.com"))
        || (shExpMatch(host, "cus-odc.officeapps.live.com"))              
        || (shExpMatch(host, "cus-roaming.officeapps.live.com"))
        || (shExpMatch(host, "dc.services.visualstudio.com"))
        || (shExpMatch(host, "domains.live.com"))
        || (shExpMatch(host, "ea-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "ea-roaming.officeapps.live.com"))          
        || (shExpMatch(host, "ecn.dev.virtualearth.net "))   
        || (shExpMatch(host, "eus2-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "eus2-roaming.officeapps.live.com"))             
        || (shExpMatch(host, "eus-odc.officeapps.live.com"))         
        || (shExpMatch(host, "eus-www.sway-cdn.com"))
        || (shExpMatch(host, "eus-www.sway-extensions.com"))        
        || (shExpMatch(host, "firstpartyapps.oaspapps.com"))
        || (shExpMatch(host, "g.live.com"))
        || (shExpMatch(host, "groupsapi2-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "groupsapi3-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "groupsapi4-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "groupsapi-prod.outlookgroups.ms"))   
        || (shExpMatch(host, "isrg.trustid.ocsp.identrust.com"))   
        || (shExpMatch(host, "liverdcxstorage.blob.core.windowsazure.com"))
        || (shExpMatch(host, "management.azure.com"))        
        || (shExpMatch(host, "mem.gfx.ms"))
        || (shExpMatch(host, "mrodevicemgr.officeapps.live.com"))      
        || (shExpMatch(host, "ncus-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "ncus-roaming.officeapps.live.com"))                
        || (shExpMatch(host, "neu-000.ocws.officeapps.live.com")) 
        || (shExpMatch(host, "neu-odc.officeapps.live.com"))         
        || (shExpMatch(host, "neu-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "nexus.officeapps.live.com"))
        || (shExpMatch(host, "nexusrules.officeapps.live.com"))
        || (shExpMatch(host, "nps.onyx.azure.net"))
        || (shExpMatch(host, "ocsa.officeapps.live.com"))
        || (shExpMatch(host, "ocsp.digicert.com"))
        || (shExpMatch(host, "ocspx.digicert.com"))
        || (shExpMatch(host, "ocsp.globalsign.com"))
        || (shExpMatch(host, "ocsp.int-x3.letsencrypt.org"))
        || (shExpMatch(host, "ocsp.msocsp.com"))       
        || (shExpMatch(host, "ocsp2.globalsign.com"))
        || (shExpMatch(host, "ocsredir.officeapps.live.com"))
        || (shExpMatch(host, "ocws.officeapps.live.com"))
        || (shExpMatch(host, "odc.officeapps.live.com"))  
        || (shExpMatch(host, "officecdn.microsoft.com.edgekey.net"))            
        || (shExpMatch(host, "officecdn.microsoft.com.edgesuite.net"))              
        || (shExpMatch(host, "ols.officeapps.live.com"))  
        || (shExpMatch(host, "oneclient.sfx.ms"))
        || (shExpMatch(host, "outlook.uservoice.com"))
        || (shExpMatch(host, "platform.linkedin.com"))
        || (shExpMatch(host, "policykeyservice.dc.ad.msft.net"))
        || (shExpMatch(host, "prod.firstpartyapps.oaspapps.com.akadns.net")) 
        || (shExpMatch(host, "r1.res.office365.com"))
        || (shExpMatch(host, "r3.res.office365.com"))
        || (shExpMatch(host, "r4.res.office365.com"))
        || (shExpMatch(host, "s.ytimg.com"))
        || (shExpMatch(host, "scus-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "scus-odc.officeapps.live.com"))         
        || (shExpMatch(host, "scus-roaming.officeapps.live.com"))                 
        || (shExpMatch(host, "sea-odc.officeapps.live.com"))         
        || (shExpMatch(host, "sea-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "secure.globalsign.com"))
        || (shExpMatch(host, "site-cdn.onenote.net"))
        || (shExpMatch(host, "skydrive.wns.windows.com"))
        || (shExpMatch(host, "skypemaprdsitus.trafficmanager.net"))   
        || (shExpMatch(host, "spoprod-a.akamaihd.net"))  
        || (shExpMatch(host, "ssw.live.com"))
        || (shExpMatch(host, "staffhub.ms"))
        || (shExpMatch(host, "staffhub.uservoice.com"))
        || (shExpMatch(host, "storage.live.com"))
        || (shExpMatch(host, "sway.com")) 
        || (shExpMatch(host, "teams.microsoft.com"))              
        || (shExpMatch(host, "telemetry.remoteapp.windowsazure.com"))         
        || (shExpMatch(host, "telemetryservice.firstpartyapps.oaspapps.com"))    
        || (shExpMatch(host, "web.microsoftstream.com"))         
        || (shExpMatch(host, "weu-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "weu-odc.officeapps.live.com"))         
        || (shExpMatch(host, "weu-roaming.officeapps.live.com"))
        || (shExpMatch(host, "wu.client.hip.live.com"))
        || (shExpMatch(host, "wus-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "wus-firstpartyapps.oaspapps.com"))  
        || (shExpMatch(host, "wus-odc.officeapps.live.com"))         
        || (shExpMatch(host, "wus-roaming.officeapps.live.com"))
        || (shExpMatch(host, "wus-www.sway-cdn.com"))
        || (shExpMatch(host, "wus-www.sway-extensions.com"))   
        || (shExpMatch(host, "www.digicert.com"))
        || (shExpMatch(host, "www.google-analytics.com"))
        || (shExpMatch(host, "www.onedrive.com"))
        || (shExpMatch(host, "www.remoteapp.windowsazure.com"))
        || (shExpMatch(host, "www.youtube.com"))
        || (shExpMatch(host, "xsi.outlook.com")))
        
    {
        return proxyserver;
    }
    //Catchall for all other traffic to another proxy 
else return proxyserver;
}

```

### <a name="2---pac-file-connect-to-office-365-over-the-internet-and-expressroute"></a><span data-ttu-id="519b8-141">#2 - файл PAC: подключение к Office 365 через Интернет и ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="519b8-141">#2 - PAC file: Connect to Office 365 over the Internet and ExpressRoute</span></span>
<span data-ttu-id="519b8-142"><a name="bkmk_inet-aer"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-142"></span></span>

<span data-ttu-id="519b8-p109">Во втором примере — это Демонстрация наших рекомендуемый подход для управления подключениями, когда ExpressRoute и Интернет цепи доступны. Отправляет ExpressRoute объявление места назначения цепи ExpressRoute и Интернет только объявленных назначения для прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="519b8-p109">The second example is a demonstration of our recommended approach to managing connections when ExpressRoute and Internet circuits are available. Sends ExpressRoute advertised destinations to the ExpressRoute circuit and Internet only advertised destinations to the proxy.</span></span>
  
<span data-ttu-id="519b8-145">Фрагмент кода:</span><span class="sxs-lookup"><span data-stu-id="519b8-145">Code snippet:</span></span>
  
```
// JavaScript source code
//July 2018 Update
// Consolidated FQDNs of URLS which are reachable via Microsoft peering over ExpressRoute. All other traffic sent to a proxy in this example. 
//Every Effort is made to ensure 100% accuracy but this PAC should be used as an example and cross-checked with your traffic flow needs and the Office 365 URL &amp; IP page. 
//Intended only for Worldwide Office 365 instances, which the vast majority of customers will be using
//PAC presumes all Office 365 BGP communities/route filters are allowed.
function FindProxyForURL(url, host)
{
    // Define proxy server
    var proxyserver = "PROXY 10.10.10.10:8080";
    // Make host lowercase
    var lhost = host.toLowerCase();
    host = lhost;
    //SUB-FQDNs of ExpressRoutable wildcards which need to be explicitly sent to the proxy at the top of the PAC because they arent ER routable
    if ((shExpMatch(host, "xsi.outlook.com"))
        || (shExpMatch(host, "r3.res.outlook.com"))
        || (shExpMatch(host, "quicktips.skypeforbusiness.com"))
        || (shExpMatch(host, "*.um.outlook.com")))                  
    {
        return proxyserver;
    }
        //EXPRESS ROUTE DIRECT
    else if ((isPlainHostName(host))  
            || (shExpMatch(host, "*.aria.microsoft.com"))             
            || (shExpMatch(host, "*.dc.trouter.io"))
            || (shExpMatch(host, "*.lync.com"))
            || (shExpMatch(host, "*.manage.office.com"))
            || (shExpMatch(host, "*.outlook.com"))
            || (shExpMatch(host, "*.outlook.office.com"))
            || (shExpMatch(host, "*.portal.cloudappsecurity.com"))
            || (shExpMatch(host, "*.protection.office.com"))
            || (shExpMatch(host, "*.protection.outlook.com"))
            || (shExpMatch(host, "*.sharepoint.com")) 
            || (shExpMatch(host, "*.skype.com")) 
            || (shExpMatch(host, "*.skypeforbusiness.com")) 
            || (shExpMatch(host, "*.svc.ms"))   
            || (shExpMatch(host, "*.teams.microsoft.com"))  
            || (shExpMatch(host, "*broadcast.officeapps.live.com"))
            || (shExpMatch(host, "*excel.officeapps.live.com"))
            || (shExpMatch(host, "*onenote.officeapps.live.com"))
            || (shExpMatch(host, "*powerpoint.officeapps.live.com"))
            || (shExpMatch(host, "*view.officeapps.live.com"))                                 
            || (shExpMatch(host, "*visio.officeapps.live.com"))
            || (shExpMatch(host, "*word-edit.officeapps.live.com"))
            || (shExpMatch(host, "*word-view.officeapps.live.com"))
            || (shExpMatch(host, "account.office.net"))
            || (shExpMatch(host, "adminwebservice.microsoftonline.com"))
            || (shExpMatch(host, "agent.office.net"))  
            || (shExpMatch(host, "apc.delve.office.com"))
            || (shExpMatch(host, "api.login.microsoftonline.com"))
            || (shExpMatch(host, "api.passwordreset.microsoftonline.com"))
            || (shExpMatch(host, "aus.delve.office.com"))
            || (shExpMatch(host, "autologon.microsoftazuread-sso.com")) 
            || (shExpMatch(host, "becws.microsoftonline.com"))
            || (shExpMatch(host, "browser.pipe.aria.microsoft.com"))  
            || (shExpMatch(host, "can.delve.office.com")) 
            || (shExpMatch(host, "ccs.login.microsoftonline.com"))  
            || (shExpMatch(host, "ccs-sdf.login.microsoftonline.com"))
            || (shExpMatch(host, "clientconfig.microsoftonline-p.net"))
            || (shExpMatch(host, "companymanager.microsoftonline.com"))
            || (shExpMatch(host, "delve.office.com"))
            || (shExpMatch(host, "device.login.microsoftonline.com"))
            || (shExpMatch(host, "domains.live.com")) 
            || (shExpMatch(host, "eur.delve.office.com"))
            || (shExpMatch(host, "gbr.delve.office.com"))
            || (shExpMatch(host, "hip.microsoftonline-p.net"))
            || (shExpMatch(host, "hipservice.microsoftonline.com"))
            || (shExpMatch(host, "home.office.com"))
            || (shExpMatch(host, "ind.delve.office.com"))
            || (shExpMatch(host, "jpn.delve.office.com"))
            || (shExpMatch(host, "kor.delve.office.com"))
            || (shExpMatch(host, "lam.delve.office.com"))
            || (shExpMatch(host, "login.microsoft.com"))
            || (shExpMatch(host, "login.microsoftonline.com"))
            || (shExpMatch(host, "login.microsoftonline-p.net"))
            || (shExpMatch(host, "login.windows.net"))
            || (shExpMatch(host, "logincert.microsoftonline.com"))
            || (shExpMatch(host, "loginex.microsoftonline.com"))
            || (shExpMatch(host, "login-us.microsoftonline.com"))
            || (shExpMatch(host, "manage.office.com"))
            || (shExpMatch(host, "mobile.pipe.aria.microsoft.com"))
            || (shExpMatch(host, "nam.delve.office.com"))
            || (shExpMatch(host, "nexus.microsoftonline-p.net"))
            || (shExpMatch(host, "office.live.com")) 
            || (shExpMatch(host, "officeapps.live.com")) 
            || (shExpMatch(host, "outlook.office365.com")) 
            || (shExpMatch(host, "passwordreset.microsoftonline.com"))
            || (shExpMatch(host, "portal.office.com"))
            || (shExpMatch(host, "protection.office.com"))
            || (shExpMatch(host, "provisioningapi.microsoftonline.com"))
            || (shExpMatch(host, "scsinstrument-ss-us.trafficmanager.net")) 
            || (shExpMatch(host, "scsquery-ss-asia.trafficmanager.net"))
            || (shExpMatch(host, "scsquery-ss-eu.trafficmanager.net")) 
            || (shExpMatch(host, "scsquery-ss-us.trafficmanager.net"))  
            || (shExpMatch(host, "signup.microsoft.com"))
            || (shExpMatch(host, "smtp.office365.com"))  
            || (shExpMatch(host, "stamp2.login.microsoftonline.com"))
            || (shExpMatch(host, "suite.office.net")) 
            || (shExpMatch(host, "teams.microsoft.com")) 
            || (shExpMatch(host, "webshell.suite.office.com")) 
            || (shExpMatch(host, "www.office.com")))             
       
    {
        return "DIRECT";
    }
        //Catchall for all other traffic to proxy
    else
    {
        return proxyserver;
    }
}

```

### <a name="3---pac-file-manage-all-office-365-destinations-collectively"></a><span data-ttu-id="519b8-146">#3 - файл PAC: управление Собирательно все назначения Office 365</span><span class="sxs-lookup"><span data-stu-id="519b8-146">#3 - PAC file: Manage all Office 365 destinations collectively</span></span>
<span data-ttu-id="519b8-147"><a name="bkmk_inet-direct"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-147"></span></span>

<span data-ttu-id="519b8-p110">Третий пример демонстрирует отправку всех сетевых запросов, связанные с Office 365 в одну целевую. Это обычно используется для обхода все проверки запросов сети Office 365 и предоставляет вам формат, где все опубликованные конечных точек входящих в список в формате PAC для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="519b8-p110">The third example demonstrates sending all network requests associated with Office 365 to a single destination. This is commonly used to bypass all inspection of Office 365 network requests and offers you a format where all published endpoints are in list in the PAC format to use for your customization.</span></span>
  
<span data-ttu-id="519b8-150">Фрагмент кода:</span><span class="sxs-lookup"><span data-stu-id="519b8-150">Code snippet:</span></span>
  
```
// JavaScript source code
//July 2018 Update new URLS go live 1st August 2018 -
//Consolidated FQDNs required to access Office 365 - All services including optional components covered and elements covered under wildcards removed. 
//Some repeated domains have been consoliodated into unpublished wildcards in order to keep the file as small as possible.
//Includes Core ProPlus URLs but not Office Mobile/IPAD/IOS/ANDROID fqdns from https://support.office.com/en-gb/article/Network-requests-in-Office-365-ProPlus-eb73fcd1-ca88-4d02-a74b-2dd3a9f3364d
//Every Effort is made to ensure 100% accuracy but this PAC should be used as an example and cross-checked with your needs and the Office 365 URL &amp; IP page
//Intended only for Worldwide Office 365 instances, which the vast majority of customers will be using
function FindProxyForURL(url, host)
{
    // Define proxy server
    var proxyserver = "PROXY 10.10.10.10:8080";
    // Make host lowercase
    var lhost = host.toLowerCase();
    host = lhost;
   if  ((shExpMatch(host, "*.aadrm.com"))
        || (shExpMatch(host, "*.adhybridhealth.azure.com"))
        || (shExpMatch(host, "*.adl.windows.com"))
        || (shExpMatch(host, "*.api.microsoftstream.com"))  
        || (shExpMatch(host, "*.assets-yammer.com"))
        || (shExpMatch(host, "autologon.microsoftazuread-sso.com"))  
        || (shExpMatch(host, "*.azureedge.net"))   
        || (shExpMatch(host, "*.azurerms.com"))
        || (shExpMatch(host, "*.cloudapp.net")) 
        || (shExpMatch(host, "*.dc.trouter.io"))
        || (shExpMatch(host, "*.entrust.net")) 
        || (shExpMatch(host, "*.geotrust.com"))
        || (shExpMatch(host, "*.helpshift.com"))
        || (shExpMatch(host, "*.hockeyapp.net"))       
        || (shExpMatch(host, "*.localytics.com"))
        || (shExpMatch(host, "*.log.optimizely.com"))     
        || (shExpMatch(host, "*.lync.com"))
        || (shExpMatch(host, "*.microsoft.com"))
        || (shExpMatch(host, "*.microsoftonline.com"))
        || (shExpMatch(host, "*.microsoftonline-p.com"))
        || (shExpMatch(host, "*.microsoftonline-p.net"))
        || (shExpMatch(host, "*.msecnd.net"))
        || (shExpMatch(host, "*.msedge.net"))
        || (shExpMatch(host, "*.msocdn.com"))
        || (shExpMatch(host, "*.mstea.ms"))
        || (shExpMatch(host, "*.o365weve.com"))
        || (shExpMatch(host, "*.office.com"))
        || (shExpMatch(host, "*.office.net"))
        || (shExpMatch(host, "*.office365.com"))
        || (shExpMatch(host, "*.omniroot.com"))
        || (shExpMatch(host, "*.onenote.com"))
        || (shExpMatch(host, "*.onmicrosoft.com"))
        || (shExpMatch(host, "*.outlook.com"))
        || (shExpMatch(host, "*.phonefactor.net")) 
        || (shExpMatch(host, "*.portal.cloudappsecurity.com"))
        || (shExpMatch(host, "*.public-trust.com"))
        || (shExpMatch(host, "*.search.production.apac.trafficmanager.net"))
        || (shExpMatch(host, "*.search.production.emea.trafficmanager.net"))
        || (shExpMatch(host, "*.search.production.us.trafficmanager.net"))
        || (shExpMatch(host, "*.secure.skypeassets.com"))
        || (shExpMatch(host, "*.sfbassets.com"))  
        || (shExpMatch(host, "*.sharepoint.com"))
        || (shExpMatch(host, "*.sharepointonline.com"))
        || (shExpMatch(host, "*.skype.com"))
        || (shExpMatch(host, "*.skypeforbusiness.com"))
        || (shExpMatch(host, "*.svc.ms")) 
        || (shExpMatch(host, "*.sway.com"))
        || (shExpMatch(host, "*.symcb.com"))
        || (shExpMatch(host, "*.symcd.com"))
        || (shExpMatch(host, "*.tenor.com"))
        || (shExpMatch(host, "*.users.storage.live.com"))
        || (shExpMatch(host, "*.verisign.com"))
        || (shExpMatch(host, "*.verisign.net"))
        || (shExpMatch(host, "*.windows.net"))
        || (shExpMatch(host, "*.yammer.com"))
        || (shExpMatch(host, "*.yammerusercontent.com"))         
        || (shExpMatch(host, "*broadcast.officeapps.live.com"))
        || (shExpMatch(host, "*cdn.onenote.net"))
        || (shExpMatch(host, "*excel.officeapps.live.com"))
        || (shExpMatch(host, "*onenote.officeapps.live.com"))
        || (shExpMatch(host, "*powerpoint.officeapps.live.com"))
        || (shExpMatch(host, "*view.officeapps.live.com"))
        || (shExpMatch(host, "*visio.officeapps.live.com"))
        || (shExpMatch(host, "*word-edit.officeapps.live.com"))
        || (shExpMatch(host, "*word-view.officeapps.live.com"))    
        || (shExpMatch(host, "account.activedirectory.windowsazure.com"))
        || (shExpMatch(host, "ad.atdmt.com"))
        || (shExpMatch(host, "admin.onedrive.com"))
        || (shExpMatch(host, "ajax.aspnetcdn.com"))
        || (shExpMatch(host, "aka.ms"))
        || (shExpMatch(host, "amp.azure.net"))
        || (shExpMatch(host, "api.microsoftstream.com"))
        || (shExpMatch(host, "apis.live.net"))
        || (shExpMatch(host, "apps.identrust.com")) 
        || (shExpMatch(host, "assets.onestore.ms"))
        || (shExpMatch(host, "auth.gfx.ms"))
        || (shExpMatch(host, "cacerts.digicert.com"))    
        || (shExpMatch(host, "cdn.odc.officeapps.live.com"))  
        || (shExpMatch(host, "cdn.onenote.net"))
        || (shExpMatch(host, "cdn.optimizely.com"))
        || (shExpMatch(host, "cert.int-x3.letsencrypt.org"))
        || (shExpMatch(host, "client.hip.live.com"))     
        || (shExpMatch(host, "connect.facebook.net"))
        || (shExpMatch(host, "crl.globalsign.com"))
        || (shExpMatch(host, "crl.globalsign.net"))
        || (shExpMatch(host, "crl.identrust.com"))    
        || (shExpMatch(host, "crl3.digicert.com"))  
        || (shExpMatch(host, "crl4.digicert.com"))
        || (shExpMatch(host, "cus-odc.officeapps.live.com"))              
        || (shExpMatch(host, "cus-roaming.officeapps.live.com"))      
        || (shExpMatch(host, "dc.services.visualstudio.com"))
        || (shExpMatch(host, "domains.live.com"))
        || (shExpMatch(host, "ea-000.ocws.officeapps.live.com")) 
        || (shExpMatch(host, "ea-roaming.officeapps.live.com"))           
        || (shExpMatch(host, "ecn.dev.virtualearth.net"))
        || (shExpMatch(host, "eus2-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "eus2-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "eus-odc.officeapps.live.com"))              
        || (shExpMatch(host, "eus-www.sway-cdn.com"))
        || (shExpMatch(host, "eus-www.sway-extensions.com"))
        || (shExpMatch(host, "firstpartyapps.oaspapps.com"))
        || (shExpMatch(host, "g.live.com"))
        || (shExpMatch(host, "groupsapi2-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "groupsapi3-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "groupsapi4-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "groupsapi-prod.outlookgroups.ms"))  
        || (shExpMatch(host, "isrg.trustid.ocsp.identrust.com"))
        || (shExpMatch(host, "liverdcxstorage.blob.core.windowsazure.com"))
        || (shExpMatch(host, "management.azure.com"))
        || (shExpMatch(host, "mem.gfx.ms"))
        || (shExpMatch(host, "mrodevicemgr.officeapps.live.com"))               
        || (shExpMatch(host, "ncus-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "ncus-roaming.officeapps.live.com"))                 
        || (shExpMatch(host, "neu-000.ocws.officeapps.live.com")) 
        || (shExpMatch(host, "neu-odc.officeapps.live.com"))              
        || (shExpMatch(host, "neu-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "nexus.officeapps.live.com"))
        || (shExpMatch(host, "nexusrules.officeapps.live.com"))
        || (shExpMatch(host, "nps.onyx.azure.net"))   
        || (shExpMatch(host, "ocsa.officeapps.live.com"))
        || (shExpMatch(host, "ocsp.digicert.com"))
        || (shExpMatch(host, "ocsp.globalsign.com"))
        || (shExpMatch(host, "ocsp.int-x3.letsencrypt.org"))
        || (shExpMatch(host, "ocsp.msocsp.com"))     
        || (shExpMatch(host, "ocsp2.globalsign.com")) 
        || (shExpMatch(host, "ocspx.digicert.com"))
        || (shExpMatch(host, "ocsredir.officeapps.live.com"))
        || (shExpMatch(host, "ocws.officeapps.live.com"))
        || (shExpMatch(host, "odc.officeapps.live.com"))  
        || (shExpMatch(host, "office.live.com"))
        || (shExpMatch(host, "officeapps.live.com"))
        || (shExpMatch(host, "officecdn.microsoft.com.edgekey.net"))              
        || (shExpMatch(host, "officecdn.microsoft.com.edgesuite.net"))
        || (shExpMatch(host, "ols.officeapps.live.com"))  
        || (shExpMatch(host, "oneclient.sfx.ms"))
        || (shExpMatch(host, "outlook.uservoice.com"))
        || (shExpMatch(host, "platform.linkedin.com"))
        || (shExpMatch(host, "policykeyservice.dc.ad.msft.net"))
        || (shExpMatch(host, "prod.firstpartyapps.oaspapps.com.akadns.net"))
        || (shExpMatch(host, "s.ytimg.com"))
        || (shExpMatch(host, "s0.assets-yammer.com"))  
        || (shExpMatch(host, "scsinstrument-ss-us.trafficmanager.net")) 
        || (shExpMatch(host, "scsquery-ss-asia.trafficmanager.net"))
        || (shExpMatch(host, "scsquery-ss-eu.trafficmanager.net")) 
        || (shExpMatch(host, "scsquery-ss-us.trafficmanager.net")) 
        || (shExpMatch(host, "scus-000.ocws.officeapps.live.com"))
        || (shExpMatch(host, "scus-odc.officeapps.live.com"))         
        || (shExpMatch(host, "scus-roaming.officeapps.live.com"))                 
        || (shExpMatch(host, "sea-odc.officeapps.live.com"))              
        || (shExpMatch(host, "sea-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "secure.globalsign.com"))
        || (shExpMatch(host, "site-cdn.onenote.net"))
        || (shExpMatch(host, "skydrive.wns.windows.com"))
        || (shExpMatch(host, "skypemaprdsitus.trafficmanager.net"))
        || (shExpMatch(host, "spoprod-a.akamaihd.net"))
        || (shExpMatch(host, "ssw.live.com"))
        || (shExpMatch(host, "staffhub.ms"))
        || (shExpMatch(host, "staffhub.uservoice.com"))    
        || (shExpMatch(host, "storage.live.com"))
        || (shExpMatch(host, "telemetry.remoteapp.windowsazure.com"))
        || (shExpMatch(host, "telemetryservice.firstpartyapps.oaspapps.com"))
        || (shExpMatch(host, "web.microsoftstream.com"))   
        || (shExpMatch(host, "weu-000.ocws.officeapps.live.com")) 
        || (shExpMatch(host, "weu-odc.officeapps.live.com"))              
        || (shExpMatch(host, "weu-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "wu.client.hip.live.com"))
        || (shExpMatch(host, "wus-000.ocws.officeapps.live.com"))  
        || (shExpMatch(host, "wus-firstpartyapps.oaspapps.com"))  
        || (shExpMatch(host, "wus-odc.officeapps.live.com"))              
        || (shExpMatch(host, "wus-roaming.officeapps.live.com"))              
        || (shExpMatch(host, "wus-www.sway-cdn.com"))
        || (shExpMatch(host, "wus-www.sway-extensions.com"))        
        || (shExpMatch(host, "www.digicert.com"))
        || (shExpMatch(host, "www.google-analytics.com"))
        || (shExpMatch(host, "www.onedrive.com"))
        || (shExpMatch(host, "www.remoteapp.windowsazure.com"))
        || (shExpMatch(host, "www.youtube.com")))
    {
        return proxyserver;
    }
        //Catchall for all other traffic to another proxy
    else return "PROXY 10.10.10.11:8080";
}

```

### <a name="use-custom-scripts-or-manually-create-your-own-pac-files"></a><span data-ttu-id="519b8-151">Использовать пользовательские сценарии или вручную создать PAC файлов</span><span class="sxs-lookup"><span data-stu-id="519b8-151">Use custom scripts or manually create your own PAC files</span></span>
<span data-ttu-id="519b8-152"><a name="pacfiles_manual"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-152"></span></span>

<span data-ttu-id="519b8-p111">Вот некоторые дополнительные средства сообщества, если вы создали что-то необходимости совместно использовать оставлять Примечание в комментариях. Ни одна из сообщества, инструменты, описанные в этой статье приведены официально поддерживается или поддерживается корпорацией Майкрософт и содержащиеся в этой статье для вашего удобства.</span><span class="sxs-lookup"><span data-stu-id="519b8-p111">Here's a few more tools from the community, if you've built something you'd like to share leave a note in the comments. None of the community tools referenced in this article are officially supported or maintained by Microsoft and are provided here for your convenience.</span></span>
  
- <span data-ttu-id="519b8-p112">Это средство наиболее старых сообщества созданный для управления процессом, средства, создавать, должна быть членом сообщества Office 365. Здесь приводится ссылка на [загрузку](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7).</span><span class="sxs-lookup"><span data-stu-id="519b8-p112">This is the oldest community generated tool to help manage the process, a tool built by a member of the Office 365 community. Here is link to [download](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7).</span></span>
    
- <span data-ttu-id="519b8-157">Эксперимент с помощью правил брандмауэра экспортируемый: [API Microsoft Cloud IP-адресов](https://mscloudips.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="519b8-157">Proof of Concept with exportable firewall rules: [Microsoft Cloud IP API](https://mscloudips.azurewebsites.net/).</span></span>
    
- <span data-ttu-id="519b8-158">Из Praktyk ИТ: [Преобразование RSS-канал](https://gallery.technet.microsoft.com/Convert-the-RSS-channel-5efe18b7) и [преобразования XML](https://gallery.technet.microsoft.com/Convert-the-O365IPAddresses-9890d896).</span><span class="sxs-lookup"><span data-stu-id="519b8-158">From IT Praktyk: [RSS conversion](https://gallery.technet.microsoft.com/Convert-the-RSS-channel-5efe18b7) and [XML conversion](https://gallery.technet.microsoft.com/Convert-the-O365IPAddresses-9890d896).</span></span>
    
- <span data-ttu-id="519b8-159">Из Питер Abele: [Загрузка](https://gallery.technet.microsoft.com/How-to-create-an-up-to-b1fc33f3).</span><span class="sxs-lookup"><span data-stu-id="519b8-159">From Peter Abele: [Download](https://gallery.technet.microsoft.com/How-to-create-an-up-to-b1fc33f3).</span></span>
    
- <span data-ttu-id="519b8-p113">Использование анализа сети для определения, который сети запросами должен обойти инфраструктуры прокси-сервера. Наиболее распространенные полных доменных имен, используемый для обхода прокси-серверы клиента включают следующие из-за объема сетевого трафика отправленных и полученных из этих конечных точек.</span><span class="sxs-lookup"><span data-stu-id="519b8-p113">Use your network analysis to determine which network requests should bypass your proxy infrastructure. The most common FQDNs used to bypass customer proxies include the following due to the volume of network traffic sent and received from these endpoints.</span></span>
    
  ```
  outlook.office365.com
  outlook.office.com
  <tenant-name>.sharepoint.com
  <tenant-name>-my.sharepoint.com
  <tenant-name>-<app>.sharepoint.com
  *.Lync.com
  
  ```

- <span data-ttu-id="519b8-162">Убедитесь, что все сетевые запросы передаются непосредственно в брандмауэре иметь соответствующую запись в брандмауэре разрешить список, чтобы разрешить запрос привлечения.</span><span class="sxs-lookup"><span data-stu-id="519b8-162">Ensure any network requests being sent to your firewall directly have a corresponding entry in the firewall allow list to allow the request to go through.</span></span>
    
## <a name="perimeter-network-integration"></a><span data-ttu-id="519b8-163">Интеграция сети периметра</span><span class="sxs-lookup"><span data-stu-id="519b8-163">Perimeter network integration</span></span>
<span data-ttu-id="519b8-164"><a name="BKMK_Perimeter"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-164"></span></span>

<span data-ttu-id="519b8-165">Вы знаете корпорации Майкрософт территориально-распределенной сети — это один из наибольшее магистралей в мире?</span><span class="sxs-lookup"><span data-stu-id="519b8-165">Did you know Microsoft's WAN is one of the largest backbones in the world?</span></span>
  
<span data-ttu-id="519b8-p114">Он имеет значение true, это большой сети это приводит к Office 365 и другие облачным службам работать независимо от того, где в условиях, которые. Сети состоит из высокой пропускной способностью, минимизировать задержки, способный ссылки после сбоя тысячи километров маршрут в конфиденциальном режиме собственные темный оптоволоконной и несколькими терабит подключений между узлами центров обработки данных и пограничного сервера, все, чтобы упростить использование облачным службам.</span><span class="sxs-lookup"><span data-stu-id="519b8-p114">It's true, this massive network is what makes Office 365 and our other cloud services work regardless of where in the world you are. Our network consists of high bandwidth, low latency, fail-over capable links with thousands of route miles of privately owned dark fiber, and multi-Terabit connections between datacenters and edge nodes, all to make it easier to use our cloud services.</span></span>
  
<span data-ttu-id="519b8-p115">С помощью сети следующим образом, которое устройствах вашей организации, для подключения к сети, как можно скорее. С более чем 2500 авторами связи поставщика услуг Интернета глобально и 70 точек присутствия, начало из локальной сети для нас должны быть полностью. Он не может снизить потратить несколько минут, убедившись, что авторами отношения поставщика услуг Интернета — оптимальный, [Вот несколько примеров](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__) из хороший и не так хорошо авторами наличии номера телефонов для сети.</span><span class="sxs-lookup"><span data-stu-id="519b8-p115">With a network like this, you want your organization's devices to connect to our network as soon as possible. With over 2500 ISP peering relationships globally and 70 points of presence, getting from your network to ours should be seamless. It can't hurt to spend a few minutes making sure your ISP's peering relationship is the most optimal, [here's a few examples](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__) of good and not so good peering hand-offs to our network.</span></span> 
  
<span data-ttu-id="519b8-p116">Можно вручную или автоматически настраивает устройства в сети для оптимальной обработки запросов сети приложения Office 365, в зависимости от используемого оборудования. Какие изменения конфигурации, необходимо сделать для оптимального обработки трафика сети Office 365 будут зависеть от среды. Office 365 сетевых запросов может использовать преимущества конфигурации сети, которые позволяют следующее:</span><span class="sxs-lookup"><span data-stu-id="519b8-p116">You can manually or automatically configure the devices on your network to optimally handle Office 365 application network requests, depending on your equipment. What configuration changes you need to make to optimally handle Office 365 network traffic will depend on your environment. Office 365 network requests may benefit from network configurations that allow the following:</span></span>
  
- <span data-ttu-id="519b8-174">Приоритет над меньше важных сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="519b8-174">Priority over less critical network traffic.</span></span>
    
- <span data-ttu-id="519b8-p117">Маршрутизация локального исходящего трафика во избежание ретрансляторы медленных глобальной сети ссылок, используя минимизировать задержки доступны в сети Microsoft при. [Здесь приводится подробное обсуждение](https://blogs.technet.microsoft.com/onthewire/2017/05/03/office-365-connectivity-guidance-part-2/) на основании сотрудничества с клиентами.</span><span class="sxs-lookup"><span data-stu-id="519b8-p117">Routing to a local egress to avoid backhauling over a slow WAN link while taking advantage of the low latency available on the Microsoft network. [Here's a good discussion](https://blogs.technet.microsoft.com/onthewire/2017/05/03/office-365-connectivity-guidance-part-2/) based on customer engagements.</span></span> 
    
- <span data-ttu-id="519b8-177">С использованием службы DNS рядом с локального исходящего трафика для обеспечения сетевой запрос увольняется из локального исходящего трафика поступает в ближайшее место авторами Microsoft.</span><span class="sxs-lookup"><span data-stu-id="519b8-177">Using DNS near a local egress to ensure the network request that leaves the local egress arrives at the nearest Microsoft peering location.</span></span>
    
- <span data-ttu-id="519b8-178">Исключения из проверки глубокой сетевых пакетов или других обработки в соответствии с требованиями задержку в масштабе связано со значительными затратами сетевых пакетов.</span><span class="sxs-lookup"><span data-stu-id="519b8-178">Exclusion from deep packet inspection or other intensive network packet processing to meet latency requirements at scale.</span></span>
    
<span data-ttu-id="519b8-p118">Современный сетевых устройств включают возможности, которые иначе, чем универсальный ненадежные Интернет-трафик управления запросами сети для доверенных приложений, такие как Office 365. С помощью новых альбомная глобальная сеть SD решения такие различие трафика и путь выбора также могут быть выполнены с сведения о изменение состояния сети, например моменту времени доступности, задержка или производительности различных путей подключения к между пользователем и в облаке.</span><span class="sxs-lookup"><span data-stu-id="519b8-p118">Modern network devices include capabilities to manage network requests for trusted applications such as Office 365 differently than generic, untrusted Internet traffic. With the emerging landscape of SD-WAN solutions, such differentiation of traffic and path selection can also be performed with awareness of the changing state of the network, such as point in time availability, latency or performance of various connectivity paths between the user and the cloud.</span></span>
  
<span data-ttu-id="519b8-181">Иллюстрация [сети и планирования для Office 365 миграции](network-and-migration-planning.md), [производительность, устранение неполадок план для Office 365](performance-troubleshooting-plan.md)и [Контрольный список планирования развертывания для Office 365](deployment-planning-checklist.md) для Дополнительные рекомендации по планированию реализации конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="519b8-181">See [Network and migration planning for Office 365](network-and-migration-planning.md), [Performance troubleshooting plan for Office 365](performance-troubleshooting-plan.md), and [Deployment planning checklist for Office 365](deployment-planning-checklist.md) for additional guidance on planning your network configuration.</span></span> 
  
### <a name="to-implement-this-scenario"></a><span data-ttu-id="519b8-182">Для реализации этого сценария:</span><span class="sxs-lookup"><span data-stu-id="519b8-182">To implement this scenario:</span></span>

<span data-ttu-id="519b8-p119">Обратитесь к поставщику сети решения или службы, если они могут использовать URL-адреса Office 365 и определения IP-адресов из XML для облегчения локального (к пользователю), low дополнительную нагрузку сети выходной для трафика Office 365, управлять его приоритета относительно других приложений и настройка сетевой путь для подключения к Office 365 в сети Microsoft в зависимости от того, изменения в сети. Некоторые решения автоматизации определения URL-адреса Office 365 и XMLs IP-адресов в их стеки и загрузки.</span><span class="sxs-lookup"><span data-stu-id="519b8-p119">Check with your network solution or service provider if they can use Office 365 URL and IP definitions from XML to facilitate local (to the user), low overhead network egress for Office 365 traffic, manage its priority relative to other applications and adjust the network path for Office 365 connections into Microsoft network depending on changing network conditions. Some solutions download and automate Office 365 URL and IP XMLs definition in their stacks.</span></span>
  
<span data-ttu-id="519b8-185">Всегда убедитесь, что реализованное решение имеет необходимые степень устойчивости, соответствующие географического дублирования сетевой путь для трафика Office 365 и обеспечивает изменения в Office 365 URL-адреса и IP-адреса, становятся публикации.</span><span class="sxs-lookup"><span data-stu-id="519b8-185">Always ensure that the implemented solution has necessary degree of resiliency, appropriate geo-redundancy of the network path for Office 365 traffic and accommodates changes to Office 365 URLs and IPs as they become published.</span></span>
  
## <a name="web-service"></a><span data-ttu-id="519b8-186">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="519b8-186">Web service</span></span>
<span data-ttu-id="519b8-187"><a name="webservice"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-187"></span></span>

<span data-ttu-id="519b8-p120">Чтобы помочь определить и различать Office 365 сетевого трафика новой веб-службы публикует конечных точках Office 365, упрощая оценить, настроить и будьте в курсе последних изменений. В этом новой веб-службы (теперь в предварительной версии), заменит списки конечных точек в статье [Office 365 URL-адреса и диапазоны IP-адресов](urls-and-ip-address-ranges.md) , наряду с RSS-канал и XML версий этих данных. Будут использоваться на 2 октября 2018 планируются эти формат данных конечной точки.</span><span class="sxs-lookup"><span data-stu-id="519b8-p120">To help you better identify and differentiate Office 365 network traffic, a new web service publishes Office 365 endpoints, making it easier for you to evaluate, configure, and stay up to date with changes. This new web service (now in preview), will eventually replace the lists of endpoints in the [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) article, along with the RSS and XML versions of that data. These format of endpoint data are planned to be phased out on October 2, 2018.</span></span> 
  
<span data-ttu-id="519b8-191">Как клиента или поставщика устройства сети периметра можно построить для нового на основе REST веб-службы для Office 365 IP-адрес и полное доменное имя записи.</span><span class="sxs-lookup"><span data-stu-id="519b8-191">As a customer or a network perimeter device vendor, you can build against the new REST-based web service for the Office 365 IP address and FQDN entries.</span></span>
  
- <span data-ttu-id="519b8-192">Последнюю версию диапазонов адресов URL-адреса Office 365 и IP-адресов, используйте [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="519b8-192">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
    
- <span data-ttu-id="519b8-193">Данные на странице диапазонов IP-адресов адрес для брандмауэров и прокси-серверов и URL-адреса Office 365, используйте [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="519b8-193">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
    
- <span data-ttu-id="519b8-194">Чтобы получить последние изменения, воспользуйтесь [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="519b8-194">To get the latest changes, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
    
<span data-ttu-id="519b8-195">Как клиента можно использовать веб-службы:</span><span class="sxs-lookup"><span data-stu-id="519b8-195">As a customer, you can use this web service to:</span></span> 
  
- <span data-ttu-id="519b8-196">Обновление сценариев PowerShell для получения данных конечной точки Office 365 и изменять форматирование для сетевых устройств.</span><span class="sxs-lookup"><span data-stu-id="519b8-196">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
    
- <span data-ttu-id="519b8-197">Эти сведения можно используйте для обновления файлов PAC разворачивать на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="519b8-197">Use this information to update PAC files deployed to client computers.</span></span>
    
<span data-ttu-id="519b8-198">Как поставщик устройства сети периметра можно использовать веб-службы:</span><span class="sxs-lookup"><span data-stu-id="519b8-198">As a network perimeter device vendor, you can use this web service to:</span></span> 
  
- <span data-ttu-id="519b8-199">Создание и тестирование программного обеспечения устройства можно загрузить в список для автоматической настройки.</span><span class="sxs-lookup"><span data-stu-id="519b8-199">Create and test device software to download the list for automated configuration.</span></span> 
    
- <span data-ttu-id="519b8-200">Проверьте наличие текущей версии.</span><span class="sxs-lookup"><span data-stu-id="519b8-200">Check for the current version.</span></span>
    
- <span data-ttu-id="519b8-201">Получение текущих изменений.</span><span class="sxs-lookup"><span data-stu-id="519b8-201">Get the current changes.</span></span>
    
<span data-ttu-id="519b8-202">Предварительный просмотр данной веб-службы, который может изменяться со временем, пока эта служба обычно доступна в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="519b8-202">The following sections describe the preview of this web service, which might change over time until the service is generally available.</span></span> 
  
<span data-ttu-id="519b8-203">Данные на веб-службы в актуальном состоянии и мы не планируется дополнительные изменения URL-адреса служб web или возвращаемых схему данных перед выпуском общедоступность данной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="519b8-203">The data on the web service is up to date and we are not planning to make further changes to the web service URLs or returned data schema before the general availability release of this web service.</span></span>
  
<span data-ttu-id="519b8-204">Для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="519b8-204">For additional information, see:</span></span>
  
- [<span data-ttu-id="519b8-205">Публикация в блоге объявлений на форуме, посвященном Office 365 Tech сообщества</span><span class="sxs-lookup"><span data-stu-id="519b8-205">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
    
- [<span data-ttu-id="519b8-206">Форум сообщества Office 365 Технический вопросы об использовании веб-служб</span><span class="sxs-lookup"><span data-stu-id="519b8-206">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
    
### <a name="common-parameters"></a><span data-ttu-id="519b8-207">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="519b8-207">Common parameters</span></span>

<span data-ttu-id="519b8-208">Эти параметры являются общими для всех методов веб-службы:</span><span class="sxs-lookup"><span data-stu-id="519b8-208">These parameters are common across all the web service methods:</span></span>
  
- <span data-ttu-id="519b8-p121">формат **= CSV | JSON** -строковый параметр запроса. По умолчанию имеет формат возвращаемые данные JSON. Включите этот дополнительный параметр для возвращения данных в формат с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="519b8-p121">**format=CSV | JSON** - Query string parameter. By default, the returned data format is JSON. Include this optional parameter to return the data in comma-separated values (CSV) format.</span></span> 
    
- <span data-ttu-id="519b8-p122">**ClientRequestId** - параметр строки запроса. Требуется идентификатор GUID, создать для клиентского сеанса связи. Необходимо создать идентификатор GUID для каждого клиентского компьютера, который вызывает веб-службы. Не используйте идентификаторы GUID, показано в следующих примерах, так как они могут быть заблокированы веб-службы в будущем. Идентификатор GUID имеет формат xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx, где x — это шестнадцатеричный номер. Чтобы создать GUID, используйте команду PowerShell [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) .</span><span class="sxs-lookup"><span data-stu-id="519b8-p122">**ClientRequestId** - Query string parameter. A required GUID that you generate for client session association. You should generate a GUID for each client machine that calls the web service. Do not use the GUIDs shown in the following examples because they may be blocked by the web service in the future. GUID format is xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx, where x represents a hexadecimal number. To generate a GUID, use the [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell command.</span></span> 
    
### <a name="version-web-method"></a><span data-ttu-id="519b8-218">Версии веб-метод</span><span class="sxs-lookup"><span data-stu-id="519b8-218">Version web method</span></span>

<span data-ttu-id="519b8-p123">Обновлений Microsoft Office 365 IP-адрес и полное доменное имя записи в конце каждого месяца и иногда из цикла для действующие или поддержки требований. Данные для каждого опубликованного экземпляра назначается номер версии. Версии веб-метода позволяет проверяют наличие последней версии для каждого экземпляра службы Office 365. Мы рекомендуем проверка версии ежедневно, или наиболее, каждый час.</span><span class="sxs-lookup"><span data-stu-id="519b8-p123">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month and occasionally out of cycle for operational or support requirements. The data for each published instance is assigned a version number. The version web method lets you poll for the latest version for each Office 365 service instance. We recommend you check the version daily, or at the most, hourly.</span></span>
  
<span data-ttu-id="519b8-223">Существует один параметр для веб-метода версии:</span><span class="sxs-lookup"><span data-stu-id="519b8-223">There is one parameter for the version web method:</span></span>
  
- <span data-ttu-id="519b8-p124">**AllVersions = true** -строковый параметр запроса. По умолчанию возвращается последняя версия. Включите этот дополнительный параметр, чтобы запросить все опубликованные версии.</span><span class="sxs-lookup"><span data-stu-id="519b8-p124">**AllVersions=true** - Query string parameter. By default, the version returned is the latest. Include this optional parameter to request all published versions.</span></span> 
    
- <span data-ttu-id="519b8-p125">**Экземпляр** - параметр маршрута. Этот дополнительный параметр экземпляр для возврата версии для. Если этот параметр опущен, будут возвращены все экземпляры. Допустимый экземпляры: по всему миру, Китай, Германия, USGovDoD, USGovGCCHigh</span><span class="sxs-lookup"><span data-stu-id="519b8-p125">**Instance** - Route parameter. This optional parameter specifies the instance to return the version for. If omitted, all instances are returned. Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh</span></span> 
    
<span data-ttu-id="519b8-p126">Результат веб-метода версия может быть одной записи или массив записей. Элементы каждой записи являются:</span><span class="sxs-lookup"><span data-stu-id="519b8-p126">The result from the version web method may be a single record or an array of records. The elements of each record are:</span></span>
  
- <span data-ttu-id="519b8-233">экземпляр - краткое имя экземпляра службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="519b8-233">instance - The short name of the Office 365 service instance.</span></span>
    
- <span data-ttu-id="519b8-234">узнать последние новости - последней версии для конечных точек данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="519b8-234">latest - The latest version for endpoints of the specified instance.</span></span>
    
- <span data-ttu-id="519b8-p127">версий — список всех предыдущих версий для указанного экземпляра. Этот элемент необходим, только если параметр AllVersions имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="519b8-p127">versions - A list of all previous versions for the specified instance. This element is only included if the AllVersions parameter is true.</span></span>
   
#### <a name="examples"></a><span data-ttu-id="519b8-237">Примеры</span><span class="sxs-lookup"><span data-stu-id="519b8-237">Examples:</span></span>
  
<span data-ttu-id="519b8-238">В примере 1 запроса URI: ** <span>https:</span>//endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-238">Example 1 request URI: **<span>https:</span>//endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p128">Этот URI возвращает последней версии каждый экземпляр службы Office 365. Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="519b8-p128">This URI returns the latest version of each Office 365 service instance. Example result:</span></span>
  
```
[
 {
  "instance": "Worldwide", 
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD", 
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
] 
```

> [!IMPORTANT]
> <span data-ttu-id="519b8-p129">Идентификатор GUID для параметра ClientRequestID в таких URI являются только пример. Чтобы повторить в Интернете службы коды URI в работе, создать собственный идентификатор GUID. Идентификаторы GUID, показано в следующих примерах блокируется веб-службы в будущем.</span><span class="sxs-lookup"><span data-stu-id="519b8-p129">The GUID for the ClientRequestID parameter in these URIs are only an example. To try the web service URIs out, generate your own GUID. The GUIDs shown in these examples may be blocked by the web service in the future.</span></span> 
  
<span data-ttu-id="519b8-244">В примере 2 запроса URI: ** <span>https:</span>//endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-244">Example 2 request URI: **<span>https:</span>//endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p130">Этот URI возвращает последнюю версию указанного экземпляра службы Office 365. Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="519b8-p130">This URI returns the latest version of the specified Office 365 service instance. Example result:</span></span>
  
```
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="519b8-247">В примере 3 запроса URI: ** <span>https:</span>//endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId = b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-247">Example 3 request URI: **<span>https:</span>//endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p131">Этот URI показаны выходные данные в формате CSV. Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="519b8-p131">This URI shows output in CSV format. Example result:</span></span>
  
```
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="519b8-250">Пример 4 запроса URI: ** <span>https:</span>//endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId = b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-250">Example 4 request URI: **<span>https:</span>//endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p132">Этот URI показаны все предыдущие версии, которые не были опубликованы для экземпляра по всему миру службы Office 365. Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="519b8-p132">This URI shows all prior versions that have been published for the Office 365 worldwide service instance. Example result:</span></span>
  
```
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

### <a name="endpoints-web-method"></a><span data-ttu-id="519b8-253">Конечные точки веб-метод</span><span class="sxs-lookup"><span data-stu-id="519b8-253">Endpoints web method</span></span>

<span data-ttu-id="519b8-p133">Конечные точки веб-метода возвращает все записи для диапазонов IP-адресов и URL-адреса, которые будут включены в службе Office 365. Используются параметры для веб-метода конечных точек.</span><span class="sxs-lookup"><span data-stu-id="519b8-p133">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service. Parameters for the endpoints web method are:</span></span>
  
- <span data-ttu-id="519b8-p134">**ServiceAreas** - параметр строки запроса. Разделенный запятыми список областей обслуживания. Допустимые элементы являются Common, Exchange, SharePoint, Скайп. Так как общие элементы области службы все необходимые компоненты для всех других областях службы, веб-службы всегда включать их. Если этот параметр не указан, возвращаются все области службы.</span><span class="sxs-lookup"><span data-stu-id="519b8-p134">**ServiceAreas** - Query string parameter. A comma-separated list of service areas. Valid items are Common,Exchange,SharePoint,Skype. Because Common service area items are a prerequisite for all other service areas, the web service will always include them. If you do not include this parameter, all service areas are returned.</span></span> 
    
- <span data-ttu-id="519b8-p135">**TenantName** - параметр строки запроса. Имя клиента Office 365. Веб-службы принимает предоставленное имя и вставляет его в части URL-адреса, включая имя клиента. Если не указано имя клиента, эти компоненты URL-адреса имеют подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="519b8-p135">**TenantName** - Query string parameter. Your Office 365 tenant name. The web service takes your provided name and inserts it in parts of URLs that include the tenant name. If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span> 
    
- <span data-ttu-id="519b8-p136">**NoIPv6** - параметр строки запроса. Установите для значение true, чтобы исключить IPv6-адреса в выходных данных, к примеру, в сети не используется IPv6.</span><span class="sxs-lookup"><span data-stu-id="519b8-p136">**NoIPv6** - Query string parameter. Set this to true to exclude IPv6 addresses from the output, for example, if you don't use IPv6 in your network.</span></span> 
    
- <span data-ttu-id="519b8-p137">**Экземпляр** - параметр маршрута. Это обязательный параметр экземпляр для конечных точек для возврата. Допустимый экземпляры: по всему миру, Китай, Германия, USGovDoD, USGovGCCHigh.</span><span class="sxs-lookup"><span data-stu-id="519b8-p137">**Instance** - Route parameter. This required parameter specifies the instance to return the endpoints for. Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span> 
    
<span data-ttu-id="519b8-p138">Результат из конечных точек веб-метода представляет собой массив из записей, каждая запись представляет набор конечной точки. Элементы для каждой записи являются:</span><span class="sxs-lookup"><span data-stu-id="519b8-p138">The result from the endpoints web method is an array of records with each record representing an endpoint set. The elements for each record are:</span></span>
  
- <span data-ttu-id="519b8-272">ID - установить постоянные идентификатор конечной точки.</span><span class="sxs-lookup"><span data-stu-id="519b8-272">id - The immutable id number of the endpoint set.</span></span>
    
- <span data-ttu-id="519b8-273">serviceArea - области службы, к которой применяется частью: общий, Exchange, SharePoint или Скайп.</span><span class="sxs-lookup"><span data-stu-id="519b8-273">serviceArea - The service area that this is part of: Common, Exchange, SharePoint, or Skype.</span></span>
    
- <span data-ttu-id="519b8-p139">URL-адреса — задайте URL-адресов для конечной точки. Массив JSON DNS-записей. Опускается, если не указано.</span><span class="sxs-lookup"><span data-stu-id="519b8-p139">urls - URLs for the endpoint set. A JSON array of DNS records. Omitted if blank.</span></span>
    
- <span data-ttu-id="519b8-p140">tcpPorts - задайте TCP-порты для конечной точки. Все элементы порты форматируются как разделенный запятыми список порты или диапазоны портов, разделенных символом дефис (-). Порты применяются к всех IP-адресов и все URL-адреса, в том, что установка конечной точки для этой категории. Опускается, если не указано.</span><span class="sxs-lookup"><span data-stu-id="519b8-p140">tcpPorts - TCP ports for the endpoint set. All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-). Ports apply to all IP addresses and all URLs in that endpoint set for that category. Omitted if blank.</span></span>
    
- <span data-ttu-id="519b8-p141">udpPorts - UDP-порты для IP-адресов устранения диапазонов в этот набор конечной точки. Опускается, если не указано.</span><span class="sxs-lookup"><span data-stu-id="519b8-p141">udpPorts - UDP ports for the IP address ranges in this endpoint set. Omitted if blank.</span></span>
    
- <span data-ttu-id="519b8-p142">IP-адреса - диапазоны IP-адресов, связанных с этой конечной точки, установить, как связанного с перечисленных порты TCP или UDP-ПОРТ. Опускается, если не указано.</span><span class="sxs-lookup"><span data-stu-id="519b8-p142">ips - The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports. Omitted if blank.</span></span>
    
- <span data-ttu-id="519b8-p143">категории - Настройка категории подключения для конечной точки. Допустимыми значениями являются оптимизировать, разрешить и по умолчанию. Обязательно.</span><span class="sxs-lookup"><span data-stu-id="519b8-p143">category - The connectivity category for the endpoint set. Valid values are Optimize, Allow, and Default. Required.</span></span>
    
- <span data-ttu-id="519b8-288">expressRoute - значение True или False, если этого набора конечных точек перенаправляется на ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="519b8-288">expressRoute - True or False if this endpoint set is routed over ExpressRoute.</span></span>
    
- <span data-ttu-id="519b8-p144">обязательно — имеет значение True, если требуется иметь подключения к Office 365 для поддержки этого набора конечных точек. Указывается, если значение false.</span><span class="sxs-lookup"><span data-stu-id="519b8-p144">required - True if this endpoint set is required to have connectivity for Office 365 to be supported. Omitted if false.</span></span>
    
- <span data-ttu-id="519b8-p145">Примечания - необязательный конечных точек в этом текстовом описываются функциональные возможности Office 365, которая будет отсутствовать, если IP-адресов или URL-адреса в эту конечную точку set не были доступны на уровне сети. Опускается, если не указано.</span><span class="sxs-lookup"><span data-stu-id="519b8-p145">notes - For optional endpoints, this text describes Office 365 functionality that will be missing if IP addresses or URLs in this endpoint set cannot be accessed at the network layer. Omitted if blank.</span></span>
    
#### <a name="examples"></a><span data-ttu-id="519b8-293">Примеры</span><span class="sxs-lookup"><span data-stu-id="519b8-293">Examples:</span></span>
  
<span data-ttu-id="519b8-294">В примере 1 запроса URI: ** <span>https:</span>//endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-294">Example 1 request URI: **<span>https:</span>//endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p146">Этот URI получает все конечные точки для экземпляра по всему миру Office 365 для всех рабочих нагрузок. Пример результатов отображение фрагмент выходных данных:</span><span class="sxs-lookup"><span data-stu-id="519b8-p146">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads. Example result showing an excerpt of the output:</span></span>
  
```
[ 
 { 
  "id": 1, 
  "serviceArea": "Exchange", 
  "serviceAreaDisplayName": "Exchange Online", 
  "urls": 
   [ 
    "*.protection.outlook.com" 
   ], 
  "ips": 
   [ 
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32" 
   ], 
  "tcpPorts": "443", 
  "expressRoute": true, 
  "category": "Allow" 
 }, 
 { 
  "id": 2, 
  "serviceArea": "Exchange", 
  "serviceAreaDisplayName": "Exchange Online", 
  "urls": 
   [ 
    "*.mail.protection.outlook.com" 
   ],
...
```

<span data-ttu-id="519b8-297">Задает дополнительные конечной точки не включаются в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="519b8-297">Additional endpoint sets are not included in this example.</span></span>
  
<span data-ttu-id="519b8-298">В примере 2 запроса URI: ** <span>https:</span>//endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId = b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-298">Example 2 request URI: **<span>https:</span>//endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-299">Этот пример получает конечных точек для экземпляра по всему миру Office 365 для Exchange Online и только зависимости.</span><span class="sxs-lookup"><span data-stu-id="519b8-299">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>
  
<span data-ttu-id="519b8-300">Выходные данные, например 2 аналогичен в примере 1, за исключением того, что результаты не будут содержать конечных точек для SharePoint Online или Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="519b8-300">The output for example 2 is similar to example 1 except that the results will not include endpoints for SharePoint Online or Skype for Business Online.</span></span>
  
### <a name="changes-web-method"></a><span data-ttu-id="519b8-301">Изменения веб-метода</span><span class="sxs-lookup"><span data-stu-id="519b8-301">Changes web method</span></span>

<span data-ttu-id="519b8-p147">Изменения веб-метода возвращает самыми последними обновлениями, которые не были опубликованы. Обычно это изменения предыдущего месяца диапазоны IP-адресов и URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="519b8-p147">The changes web method returns the most recent updates that have been published. This is typically the previous month's changes to IP address ranges and URLs.</span></span>
  
> [!NOTE]
> <span data-ttu-id="519b8-304">Данные из изменений API точное в области предварительного просмотра и будет использоваться для разработки и тестирования только.</span><span class="sxs-lookup"><span data-stu-id="519b8-304">Data from the changes API is accurate in the preview and should be used for development and testing only.</span></span> 
  
<span data-ttu-id="519b8-305">Параметр для веб-метода изменения является:</span><span class="sxs-lookup"><span data-stu-id="519b8-305">The parameter for the changes web method is:</span></span>
  
- <span data-ttu-id="519b8-p148">**Версия** - параметр маршрута требуется URL-адрес. Версия, которая реализована в настоящее время, и вы хотите просмотреть изменения, начиная с этой версии. YYYYMMDDNN имеет формат.</span><span class="sxs-lookup"><span data-stu-id="519b8-p148">**Version** - Required URL route parameter. The version that you have currently implemented, and you want to see the changes since that version. The format is YYYYMMDDNN.</span></span> 
    
<span data-ttu-id="519b8-p149">Результат изменений веб-метода представляет собой массив записей для каждой записи, представляющее внести изменения в определенной версии конечных точек. Элементы для каждой записи являются:</span><span class="sxs-lookup"><span data-stu-id="519b8-p149">The result from the changes web method is an array of records with each record representing a change in a specific version of the endpoints. The elements for each record are:</span></span>
  
- <span data-ttu-id="519b8-311">ID — постоянные идентификатор записи изменений.</span><span class="sxs-lookup"><span data-stu-id="519b8-311">id - The immutable id of the change record.</span></span>
    
- <span data-ttu-id="519b8-p150">endpointSetId - идентификатор конечной точки задания записи, необходимо изменить. Обязательно.</span><span class="sxs-lookup"><span data-stu-id="519b8-p150">endpointSetId - The ID of the endpoint set record that is changed. Required.</span></span>
    
- <span data-ttu-id="519b8-314">ликвидации - это может быть либо изменения, добавления или удаления и описываются изменения были для записи набора конечных точек.</span><span class="sxs-lookup"><span data-stu-id="519b8-314">disposition - This can be either of change, add, or remove and describes what the change did to the endpoint set record.</span></span>
    
- <span data-ttu-id="519b8-p151">версия - версия групповому, в которой была введена изменения. Номера версий имеют формат YYYYMMDDNN, где NN — число натуральный увеличивается при наличии нескольких версий, необходимые для публикации на один день.</span><span class="sxs-lookup"><span data-stu-id="519b8-p151">version - The version of the published endpoint set in which the change was introduced. Version numbers are of the format YYYYMMDDNN, where NN is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
    
- <span data-ttu-id="519b8-p152">предыдущие - подструктуре, о ранее заданные значения измененных элементов для конечной точки необходимо задать. Это не будут включены для наборов только что добавленный конечной точки. Включает в себя tcpPorts, udpPorts, ExpressRoute, требуется категория, заметки.</span><span class="sxs-lookup"><span data-stu-id="519b8-p152">previous - A substructure detailing previous values of changed elements on the endpoint set. This will not be included for newly added endpoint sets. Includes tcpPorts, udpPorts, ExpressRoute, category, required, notes.</span></span>
    
- <span data-ttu-id="519b8-p153">текущий - подструктуре, о обновленные значения элементов изменения на endpoinset. Включает в себя tcpPorts, udpPorts, ExpressRoute, требуется категория, заметки.</span><span class="sxs-lookup"><span data-stu-id="519b8-p153">current - A substructure detailing updated values of changes elements on the endpoinset. Includes tcpPorts, udpPorts, ExpressRoute, category, required, notes.</span></span>
    
- <span data-ttu-id="519b8-p154">Add - коллекции множества sub структуры, о элементов для добавления к конечной точки. Указывается, если нет без дополнения.</span><span class="sxs-lookup"><span data-stu-id="519b8-p154">add - A sub structure detailing items to be added to endpoint set collections. Omitted if there are no additions.</span></span>
    
  - <span data-ttu-id="519b8-324">effectiveDate - определяет данные, когда дополнения будут оставаться активными в службе.</span><span class="sxs-lookup"><span data-stu-id="519b8-324">effectiveDate - Defines the data when the additions will be live in the service.</span></span>
    
  - <span data-ttu-id="519b8-325">IP-адреса - элементов будет добавлена в массив IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="519b8-325">ips - Items to be added to the ips array.</span></span>
    
  - <span data-ttu-id="519b8-326">URL-адреса элементов будет добавлена в массив URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="519b8-326">urls- Items to be added to the urls array.</span></span>
    
- <span data-ttu-id="519b8-p155">Удаление - подструктуре, о элементов для удаления из набора конечных точек. Указывается, если нет без удаления.</span><span class="sxs-lookup"><span data-stu-id="519b8-p155">remove - A substructure detailing items to be removed from the endpoint set. Omitted if there are no removals.</span></span>
    
  - <span data-ttu-id="519b8-329">IP-адреса - элементов для удаления из массива IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="519b8-329">ips - Items to be removed from the ips array.</span></span>
    
  - <span data-ttu-id="519b8-330">URL-адреса элементов для удаления из массива URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="519b8-330">urls- Items to be removed from the urls array.</span></span>
    
 <span data-ttu-id="519b8-331">**Примеры:**</span><span class="sxs-lookup"><span data-stu-id="519b8-331">**Examples:**</span></span>
  
<span data-ttu-id="519b8-332">В примере 1 запроса URI: ** <span>https:</span>//endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-332">Example 1 request URI: **<span>https:</span>//endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p156">Это запрашивает все предыдущие изменения на экземпляр по всему миру службы Office 365. Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="519b8-p156">This requests all previous changes to the Office 365 worldwide service instance. Example result:</span></span>
  
```
[ 
 { 
  "id": 424, 
  "endpointSetId": 32, 
  "disposition": "Change", 
  "version": "2018062700", 
  "remove": 
   { 
    "urls": 
     [ 
      "*.api.skype.com", "skypegraph.skype.com" 
     ] 
   } 
 }, 
 { 
  "id": 426, 
  "endpointSetId": 31, 
  "disposition": "Change", 
  "version": "2018062700", 
  "add": 
   { 
    "effectiveDate": "20180609", 
    "ips": 
     [ 
      "51.140.203.190/32" 
     ]
   },
  "remove": 
   { 
    "ips": 
     [
...

```

<span data-ttu-id="519b8-335">В примере 2 запроса URI: ** <span>https:</span>//endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span><span class="sxs-lookup"><span data-stu-id="519b8-335">Example 2 request URI: **<span>https:</span>//endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7**</span></span>
  
<span data-ttu-id="519b8-p157">Это запрашивает изменения с момента указанной версии по всему миру Office 365 экземпляру. В этом случае указанную версию является последней. Пример результатов:</span><span class="sxs-lookup"><span data-stu-id="519b8-p157">This requests changes since the specified version to the Office 365 Worldwide instance. In this case, the version specified is the latest. Example result:</span></span>
  
```
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]

```

### <a name="example-powershell-script"></a><span data-ttu-id="519b8-339">Пример скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="519b8-339">Example PowerShell Script</span></span>

<span data-ttu-id="519b8-p158">Вот сценарий PowerShell, который можно запустить, чтобы увидеть, если имеется действия, которые необходимо предпринять для обновленных данных. Этот сценарий проверяет номер версии по всему миру Office 365 конечных точек экземпляра. При наличии изменений, загружаемые файлы конечные точки и фильтры для конечных точек категории «Разрешить» и «Оптимизировать». Также использует уникальный ClientRequestId через несколько вызовов и сохраняет последней версии, обнаруженных в временный файл. Этот скрипт должны вызывать один раз в час на наличие новой версии.</span><span class="sxs-lookup"><span data-stu-id="519b8-p158">Here is a PowerShell script that you can run to see if there are actions you need to take for updated data. This script checks the version number for the Office 365 Worldwide instance endpoints. When there is a change, it downloads the endpoints and filters for the "Allow" and "Optimize" category endpoints. It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file. You should call this script once an hour to check for a version update.</span></span>
  
```
# webservice root URL
$ws = "https://endpoints.office.com"
# path where client ID and latest version number will be stored
$datapath = $Env:TEMP + "\endpoints_clientid_latestversion.txt"
# fetch client ID and version if data file exists; otherwise create new file
if (Test-Path $datapath) {
    $content = Get-Content $datapath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
}
else {
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $datapath
}
# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    
    # write the new version number to the data file
    @($clientRequestId, $version.latest) | Out-File $datapath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    $flatIps = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings have dots while IPv6 strings have colons
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        
        $ipCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ipCustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ipCustomObjects
    }
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIps.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    # TODO Call Send-MailMessage with new endpoints data
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date"
}
```

### <a name="example-python-script"></a><span data-ttu-id="519b8-345">Пример сценария Python</span><span class="sxs-lookup"><span data-stu-id="519b8-345">Example Python Script</span></span>

<span data-ttu-id="519b8-p159">Вот скрипта Python с Python 3.6.3 на 10 Windows, который можно запустить для просмотра, если имеется действия, которые необходимо предпринять для обновленных данных. Этот сценарий проверяет номер версии по всему миру Office 365 конечных точек экземпляра. При наличии изменений, загружаемые файлы конечные точки и фильтры для конечных точек категории «Разрешить» и «Оптимизировать». Также использует уникальный ClientRequestId через несколько вызовов и сохраняет последней версии, обнаруженных в временный файл. Этот скрипт должны вызывать один раз в час на наличие новой версии.</span><span class="sxs-lookup"><span data-stu-id="519b8-p159">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data. This script checks the version number for the Office 365 Worldwide instance endpoints. When there is a change, it downloads the endpoints and filters for the "Allow" and "Optimize" category endpoints. It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file. You should call this script once an hour to check for a version update.</span></span>
  
```
import json
import os
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = os.environ['TEMP'] + '\endpoints_clientid_latestversion.txt'
# fetch client ID and version if data exists; otherwise create new file
if os.path.exists(datapath):
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))
    
    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

### <a name="web-service-interface-versioning"></a><span data-ttu-id="519b8-351">Веб-службы интерфейса управления версиями</span><span class="sxs-lookup"><span data-stu-id="519b8-351">Web Service interface versioning</span></span>

<span data-ttu-id="519b8-p160">Обновление параметров и результаты для этих методов веб-службы может потребоваться в будущем. После публикации версии общей доступности этих веб-служб, корпорация Майкрософт прилагает разумные усилия для уведомления материалам обновлений для веб-службы. Когда корпорация Майкрософт считает, что обновление потребует изменений для клиентов, использующих веб-службы, корпорация Майкрософт будет сохранена в предыдущей версии (обратно в одной версии) веб-службы, доступные для по крайней мере двенадцать (12) месяцев после выпуска новой версии. Пользователи, которые не обновлять в это время не удается получить доступ к веб-службы и к ее методам. Пользователи должны убедиться, что клиенты веб-службы, продолжать работать без ошибок, если выполняются следующие изменения к подписи, интерфейс службы web:</span><span class="sxs-lookup"><span data-stu-id="519b8-p160">Updates to the parameters or results for these web service methods may be required in the future. After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service. When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least twelve (12) months after the release of the new version. Customers who do not upgrade during that time may be unable to access the web service and its methods. Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>
  
- <span data-ttu-id="519b8-357">Добавление нового необязательный параметр существующего веб-метод, который не должен быть предоставлено старых клиентов и не влиять на результат получает старого клиента.</span><span class="sxs-lookup"><span data-stu-id="519b8-357">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
    
- <span data-ttu-id="519b8-358">Добавление нового именованного атрибута в одном из элементов REST ответа или дополнительных столбцов в ответ CSV.</span><span class="sxs-lookup"><span data-stu-id="519b8-358">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
    
- <span data-ttu-id="519b8-359">Добавление нового веб-метод с новое имя, которое не вызывается старых клиентов.</span><span class="sxs-lookup"><span data-stu-id="519b8-359">Adding a new web method with a new name that is not called by the older clients.</span></span>
    
## <a name="faq"></a><span data-ttu-id="519b8-360">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="519b8-360">FAQ</span></span>

<span data-ttu-id="519b8-361">Администратор часто задаваемые вопросы о подключения:</span><span class="sxs-lookup"><span data-stu-id="519b8-361">Frequently-asked administrator questions about connectivity:</span></span>
  
### <a name="how-do-i-submit-a-question"></a><span data-ttu-id="519b8-362">Как отправить вопрос?</span><span class="sxs-lookup"><span data-stu-id="519b8-362">How do I submit a question?</span></span>

<span data-ttu-id="519b8-p161">Щелкните ссылку внизу для указания, если статья была полезной или нет и отправьте его любые дополнительные вопросы. Мы отслеживать свои отзывы и предложения и обновление с наиболее часто задаваемые вопросы по.</span><span class="sxs-lookup"><span data-stu-id="519b8-p161">Click the link at the bottom to indicate if the article was helpful or not and submit any additional questions. We monitor the feedback and update the questions here with the most frequently asked.</span></span>
  
### <a name="when-is-the-xml-file-updated"></a><span data-ttu-id="519b8-365">При обновлении XML-файла</span><span class="sxs-lookup"><span data-stu-id="519b8-365">When is the XML file updated?</span></span>

<span data-ttu-id="519b8-p162">При объявили об изменении новые конечные точки, имеется обычно буфера 30 + день перед их эффективны и сетевые запросы почта направляется им. Этот буфер является для обеспечения клиентов и партнеров предоставлена возможность обновлять свои системы. Полное доменное имя и IP-адрес префикс добавления и удаления обрабатываются в XML-файла в то же время, как оповещения, что означает, что новый полное доменное имя будет находиться в XML-файле 30 дней до использования. Поскольку мы прекращения отправки сетевых запросов конечных точек, которые мы удаляется до объявление о их удаления при удалении конечной точки из XML в то же время, как объявление его уже не используется.</span><span class="sxs-lookup"><span data-stu-id="519b8-p162">When new endpoints are announced, there is usually a 30+ day buffer before they are effective and network requests begin going to them. This buffer is to ensure customers and partners have an opportunity to update their systems. FQDN and IP prefix additions and removals are processed in the XML file at the same time as the announcement, meaning a new FQDN will be in the XML file 30 days before use. Since we stop sending network requests to endpoints we're removing prior to announcing their removal, when we remove the endpoint from the XML at the same time as the announcement it is already unused.</span></span>
  
### <a name="how-can-i-be-notified-of-changes"></a><span data-ttu-id="519b8-370">Как можно ли получать уведомления об изменениях?</span><span class="sxs-lookup"><span data-stu-id="519b8-370">How can I be notified of changes?</span></span>
<span data-ttu-id="519b8-371"><a name="bkmk_changes"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-371"></span></span>

<span data-ttu-id="519b8-p163">Конечные точки Office 365 публикуются в конце каждого месяца с уведомление о 30 дней. Иногда изменений внесено не будет более чем один раз в месяц или с более короткий срок, уведомление о периодов. При добавлении конечную точку, дата, перечисленные в [RSS-канал](https://go.microsoft.com/fwlink/p/?linkid=236301) — это дата, после которого будут отправляться сетевых запросов к конечной точке. Если вы не знакомы с RSS-канал, вот как для [подписки с помощью Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) , или вы может [иметь RSS-канал, обновления, отправлять вам по электронной почте](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span><span class="sxs-lookup"><span data-stu-id="519b8-p163">Office 365 endpoints are published at the end of each month with 30 days notice. Occasionally changes will occur more than once a month or with shorter notice periods. When an endpoint is added, the effective date listed in the [RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) is the date after which network requests will be sent to the endpoint. If you're new to RSS, here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>
  
### <a name="how-do-i-read-the-rss-change-log"></a><span data-ttu-id="519b8-376">Как читать, RSS-канал журнала изменений?</span><span class="sxs-lookup"><span data-stu-id="519b8-376">How do I read the RSS change log?</span></span>
<span data-ttu-id="519b8-377"><a name="bkmk_changes"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-377"></span></span>

<span data-ttu-id="519b8-p164">После подписаться на RSS-канал, который может выполнять синтаксический анализ сведения самостоятельно или с использованием скрипта. В следующей таблице описываются формат RSS-канал o облегчают.</span><span class="sxs-lookup"><span data-stu-id="519b8-p164">After you subscribe to the RSS feed, you can parse the information yourself or with a script. The following table describes the format of the RSS feed o make it easier.</span></span>
  
|<span data-ttu-id="519b8-380">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="519b8-380">**Section**</span></span>|<span data-ttu-id="519b8-381">**Часть 1**</span><span class="sxs-lookup"><span data-stu-id="519b8-381">**Part 1**</span></span>|<span data-ttu-id="519b8-382">**Часть 2**</span><span class="sxs-lookup"><span data-stu-id="519b8-382">**Part 2**</span></span>|<span data-ttu-id="519b8-383">**Часть 3**</span><span class="sxs-lookup"><span data-stu-id="519b8-383">**Part 3**</span></span>|<span data-ttu-id="519b8-384">**Часть 4**</span><span class="sxs-lookup"><span data-stu-id="519b8-384">**Part 4**</span></span>|<span data-ttu-id="519b8-385">**Часть 5**</span><span class="sxs-lookup"><span data-stu-id="519b8-385">**Part 5**</span></span>|<span data-ttu-id="519b8-386">**Часть 6**</span><span class="sxs-lookup"><span data-stu-id="519b8-386">**Part 6**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="519b8-387">**Описание**</span><span class="sxs-lookup"><span data-stu-id="519b8-387">**Description**</span></span> <br/> |<span data-ttu-id="519b8-388">Количество</span><span class="sxs-lookup"><span data-stu-id="519b8-388">Count</span></span>  <br/> |<span data-ttu-id="519b8-389">Дата, после которого может предполагать сети запросы на отправку в конечную точку.</span><span class="sxs-lookup"><span data-stu-id="519b8-389">Date after which you can expect network requests to be sent to the endpoint.</span></span>  <br/> |<span data-ttu-id="519b8-390">Базовая описание компонента или служба, которая требует конечной точки.</span><span class="sxs-lookup"><span data-stu-id="519b8-390">Basic description of the feature or service that requires the endpoint.</span></span>  <br/> |<span data-ttu-id="519b8-391">Можно ли подключиться к этой конечной точки на канал ExpressRoute в дополнение к Интернету?</span><span class="sxs-lookup"><span data-stu-id="519b8-391">Can you connect to this endpoint on an ExpressRoute Circuit in addition to the internet?</span></span>  <br/> |<span data-ttu-id="519b8-392">**Да** — возможность подключения к этой конечной точки в Интернете и ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="519b8-392">**Yes** - you can connect to this endpoint on both the internet and ExpressRoute.</span></span>  <br/> <span data-ttu-id="519b8-393">**Нет** — только можно подключить к этой конечной точки в Интернете.</span><span class="sxs-lookup"><span data-stu-id="519b8-393">**No** - you can only connect to this endpoint on the internet.</span></span>  <br/> |<span data-ttu-id="519b8-394">Полное доменное имя или IP-адреса диапазона, добавления или удаления назначения.</span><span class="sxs-lookup"><span data-stu-id="519b8-394">The destination FQDN or IP range being added or removed.</span></span>  <br/> |
|<span data-ttu-id="519b8-395">**Пример**</span><span class="sxs-lookup"><span data-stu-id="519b8-395">**Example**</span></span> <br/> |<span data-ttu-id="519b8-396">1 /</span><span class="sxs-lookup"><span data-stu-id="519b8-396">1/</span></span>  <br/> |<span data-ttu-id="519b8-397">[Эффективных xx/xx/xxx.</span><span class="sxs-lookup"><span data-stu-id="519b8-397">[Effective xx/xx/xxx.</span></span>  <br/> |<span data-ttu-id="519b8-398">Обязательный: \<описание\>.</span><span class="sxs-lookup"><span data-stu-id="519b8-398">Required: \<description\>.</span></span>  <br/> |<span data-ttu-id="519b8-399">ExpressRoute:</span><span class="sxs-lookup"><span data-stu-id="519b8-399">ExpressRoute:</span></span>  <br/> |<span data-ttu-id="519b8-400">\<Да/Нет\>.</span><span class="sxs-lookup"><span data-stu-id="519b8-400">\<Yes/No\>.</span></span>  <br/> |<span data-ttu-id="519b8-401">\<Полное доменное имя или IP-адрес\>],</span><span class="sxs-lookup"><span data-stu-id="519b8-401">\<FQDN/IP\>],</span></span>  <br/> |
   
<span data-ttu-id="519b8-402">Несколько других замечания, любая операция имеет набору разделителей:</span><span class="sxs-lookup"><span data-stu-id="519b8-402">A couple other things to note, every entry has a common set of delimiters:</span></span>
  
- <span data-ttu-id="519b8-403">**/**-После count</span><span class="sxs-lookup"><span data-stu-id="519b8-403">**/** - after the count</span></span> 
    
- <span data-ttu-id="519b8-404">**[** - для указания запись для подсчета</span><span class="sxs-lookup"><span data-stu-id="519b8-404">**[** - to indicate the entry for the count</span></span> 
    
- <span data-ttu-id="519b8-p165">**.** -используется между каждой несовпадающих раздел записи</span><span class="sxs-lookup"><span data-stu-id="519b8-p165">**.** - used in between each distinct section of the entry</span></span> 
    
- <span data-ttu-id="519b8-407">**],** -, чтобы указать окончание одной операции</span><span class="sxs-lookup"><span data-stu-id="519b8-407">**],** - to indicate the end of a single entry</span></span> 
    
- <span data-ttu-id="519b8-p166">**].** -Чтобы указать окончание всех записей</span><span class="sxs-lookup"><span data-stu-id="519b8-p166">**].** - To indicate the end of all the entries</span></span> 
    
### <a name="how-do-i-determine-the-location-of-my-tenant"></a><span data-ttu-id="519b8-410">Как определить расположение личных клиента?</span><span class="sxs-lookup"><span data-stu-id="519b8-410">How do I determine the location of my tenant?</span></span>

 <span data-ttu-id="519b8-411">**Расположение клиента** лучше всего определяется с помощью нашего [сопоставление центра обработки данных](https://o365datacentermap.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="519b8-411">**Tenant location** is best determined using our [datacenter map](https://o365datacentermap.azurewebsites.net/).</span></span>
  
### <a name="am-i-peering-appropriately-with-microsoft"></a><span data-ttu-id="519b8-412">У меня авторами надлежащим образом с корпорацией Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="519b8-412">Am I peering appropriately with Microsoft?</span></span>

 <span data-ttu-id="519b8-413">**Расположения Peering** описаны более подробно в [авторами с корпорацией Майкрософт](https://www.microsoft.com/peering).</span><span class="sxs-lookup"><span data-stu-id="519b8-413">**Peering locations** are described in more detail in [peering with Microsoft](https://www.microsoft.com/peering).</span></span>
  
<span data-ttu-id="519b8-p167">С более чем 2500 авторами связи поставщика услуг Интернета глобально и 70 точек присутствия, начало из локальной сети для нас должны быть полностью. Он не может снизить потратить несколько минут, убедившись, что авторами отношения поставщика услуг Интернета — оптимальный, [Вот несколько примеров](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__) из хороший и не так хорошо авторами наличии номера телефонов для сети.</span><span class="sxs-lookup"><span data-stu-id="519b8-p167">With over 2500 ISP peering relationships globally and 70 points of presence, getting from your network to ours should be seamless. It can't hurt to spend a few minutes making sure your ISP's peering relationship is the most optimal, [here's a few examples](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__) of good and not so good peering hand-offs to our network.</span></span> 
  
### <a name="how-do-i-determine-which-ip-addresses-to-accept-over-expressroute"></a><span data-ttu-id="519b8-416">Как определить, какую IP-адресов, чтобы принять через ExpressRoute?</span><span class="sxs-lookup"><span data-stu-id="519b8-416">How do I determine which IP addresses to accept over ExpressRoute?</span></span>

 <span data-ttu-id="519b8-417">**Маршруты принятия ExpressRoute** определяются конкретных Office 365 [протокола BGP сообществ](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099)и [диапазоны IP-адресов корпорации Майкрософт](https://www.microsoft.com/download/details.aspx?id=53602) .</span><span class="sxs-lookup"><span data-stu-id="519b8-417">**Accepted ExpressRoute routes** are defined by [Microsoft's IP ranges](https://www.microsoft.com/download/details.aspx?id=53602) and the specific Office 365 [BGP communities](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099).</span></span>
  
### <a name="how-do-i-determine-which-endpoints-i-need"></a><span data-ttu-id="519b8-418">Как определить, какие конечные точки, требуются?</span><span class="sxs-lookup"><span data-stu-id="519b8-418">How do I determine which endpoints I need?</span></span>

<span data-ttu-id="519b8-p168">Мы регулярно добавить новые функции и службы в набор Office 365 расширятся, создавая подключения к альбомная. Если вы подписаны на E3 или E5 SKU, простой способ подумайте, список конечных точек — требуются все из них для получения полной функциональности для набора. Если вы не подписаны на любой из этих продуктов разницы минимальной в зависимости от конечных точек.</span><span class="sxs-lookup"><span data-stu-id="519b8-p168">We regularly add new features and services to the Office 365 suite, expanding the connectivity landscape. If you're subscribed to the E3 or E5 SKU, the simple way to think about the list of endpoints is that you need all of them to get full functionality for the suite. If you aren't subscribed to either of these SKUs the difference is minimal in terms of the number of endpoints.</span></span>
  
<span data-ttu-id="519b8-422">Чтение [Сетевого подключения к Office 365 принципы](office-365-network-connectivity-principles.md) Чтобы получить дополнительные сведения о категории конечной точки Office 365 и понять принципы подключения для безопасного управления Office 365 трафика и начало обеспечить максимально высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="519b8-422">Read [Office 365 Network Connectivity Principles](office-365-network-connectivity-principles.md) to get more information on Office 365 endpoint categories, and to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> 
  
<span data-ttu-id="519b8-p169">На следующем рисунке видно пример из части таблицы полное доменное имя в разделе Office в Интернете. Строки упорядочены по компонентам и различия в службе подключения к. Первые две строки указывают Office Online полагается на конечных точек помеченные требуется в Office 365 проверки подлинности и удостоверения и портала и общих разделов. Это характерно для службы в Office 365 полагаться на следующих общих служб. Третьей строки указывает на клиентских компьютерах должны быть смогут получать \*. officeapps.live.com для использования Office Online и четвертой строки указывает компьютеров также должны для связи с \*. cdn.office.net для использования Office Online.</span><span class="sxs-lookup"><span data-stu-id="519b8-p169">In the image below, you can see an example from a portion of the FQDN table in the Office Online section. The rows are organized by feature and differences in connectivity. The first two rows indicate Office Online relies on the endpoints marked Required in the Office 365 Authentication and Identity and portal and shared sections. This is typical for a service within Office 365 to rely on these shared services. The third row indicates client computers must be able to reach \*.officeapps.live.com to use Office Online and the fourth row indicates computers must also be able to reach \*.cdn.office.net to use Office Online.</span></span>
  
<span data-ttu-id="519b8-428">Несмотря на то, что в строке три и четыре необходимы для использования Office Online, они разделены указывает, что назначения разных:</span><span class="sxs-lookup"><span data-stu-id="519b8-428">Even though both row three and four are required to use Office Online, they've been separated to indicate the destination is different:</span></span>
  
1. <span data-ttu-id="519b8-429">\*. officeapps.live.com не представляет CDN, запросы значение для этого пространства имен будет перейти непосредственно в центре обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="519b8-429">\*.officeapps.live.com does not represent a CDN, meaning requests to this namespace will go directly to a Microsoft datacenter.</span></span>
    
2. <span data-ttu-id="519b8-430">\*. officeapps.live.com доступен на ExpressRoute каналов, с помощью Microsoft Peering.</span><span class="sxs-lookup"><span data-stu-id="519b8-430">\*.officeapps.live.com is accessible on ExpressRoute circuits using Microsoft Peering.</span></span>
    
3. <span data-ttu-id="519b8-431">IP-адреса, связанные с Office Online и \*. officeapps.live.com можно найти, выполнив эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="519b8-431">The IP addresses associated with Office Online and \*.officeapps.live.com can be found by following this link.</span></span>
    
4. <span data-ttu-id="519b8-432">\*. cdn.office.net представляет CDN, размещенного в Akamai, запросы значение для этого пространства имен будут поступать на Akamai центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="519b8-432">\*.cdn.office.net represents a CDN hosted by Akamai, meaning requests to this namespace will go to an Akamai datacenter.</span></span>
    
5. <span data-ttu-id="519b8-433">\*. cdn.office.net недоступен на ExpressRoute каналов.</span><span class="sxs-lookup"><span data-stu-id="519b8-433">\*.cdn.office.net is not accessible on ExpressRoute circuits.</span></span>
    
6. <span data-ttu-id="519b8-434">IP-адреса, связанные с Office Online и \*. cdn.office.net недоступны.</span><span class="sxs-lookup"><span data-stu-id="519b8-434">The IP addresses associated with Office Online and \*.cdn.office.net are not available.</span></span>
    
![Снимок экрана на странице конечных точек](media/42b487f3-24f3-48fe-9885-f97aae3194f3.png)
  
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a><span data-ttu-id="519b8-436">Я вижу сетевых запросов для IP-адресов не на опубликованные списка, необходимо предоставить доступ к ним?</span><span class="sxs-lookup"><span data-stu-id="519b8-436">I see network requests to IP addresses not on the published list, do I need to provide access to them?</span></span>
<span data-ttu-id="519b8-437"><a name="bkmk_MissingIP"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-437"></span></span>

<span data-ttu-id="519b8-p170">Корпорация Майкрософт предоставлять только IP-адресов для серверов Microsoft Office 365, которые следует направлять непосредственно в Интернете или ExpressRoute. Это не полный список всех IP-адресов, которые вы увидите сетевых запросов для. Вы увидите сетевые запросы корпорации Майкрософт и сторонних производителей собственные, отменить публикацию, IP-адресов. Эти IP-адреса динамически создаются или управляемых, чтобы не позволяет своевременно уведомление при изменении ими. Если брандмауэр не может разрешить доступ на основании полные доменные имена для сетевые запросы, используйте файл PAC или WPAD для управления запросами.</span><span class="sxs-lookup"><span data-stu-id="519b8-p170">We only provide IP addresses for the Office 365 servers you should route directly to over the Internet or ExpressRoute. This isn't a comprehensive list of all IP addresses you'll see network requests for. You'll see network requests to Microsoft and third-party owned, unpublished, IP addresses. These IP addresses are dynamically generated or managed in a way that prevents timely notice when they change. If your firewall can't allow access based on the FQDNs for these network requests, use a PAC or WPAD file to manage the requests.</span></span>
  
<span data-ttu-id="519b8-443">Отображаются IP-адрес, связанный с Office 365, который вы хотите больше узнать о?</span><span class="sxs-lookup"><span data-stu-id="519b8-443">See an IP associated with Office 365 that you want more information on?</span></span>
  
1. <span data-ttu-id="519b8-444">Установите флажок, если IP-адрес включен в больший диапазон опубликованные с помощью [CIDR калькулятор](http://jodies.de/ipcalc).</span><span class="sxs-lookup"><span data-stu-id="519b8-444">Check if the IP address is included in a larger published range using a [CIDR calculator](http://jodies.de/ipcalc).</span></span>
    
2. <span data-ttu-id="519b8-p171">В разделе Если партнер несет ответственность за IP-адресов с помощью [запросов whois](https://dnsquery.org/). Если он установлен Microsoft владельцем, возможно внутренних партнера.</span><span class="sxs-lookup"><span data-stu-id="519b8-p171">See if a partner owns the IP with a [whois query](https://dnsquery.org/). If it's Microsoft owned, it may be an internal partner.</span></span>
    
3. <span data-ttu-id="519b8-p172">Проверьте сертификат, в браузере подключиться к адрес IP-адресов с помощью *HTTPS://\<IP-адрес\> * , проверьте доменов, перечисленных в сертификате, чтобы понять, какие домены связаны с IP-адрес. Если будет Microsoft, владельцем которого IP-адрес, а не на список Office 365 IP-адресов, значит, вероятно, IP-адрес связан с CDN Майкрософт например *MSOCDN.NET* или другой домен Microsoft без публикуемые сведения IP-адресов. Если в домене в сертификате — это один где мы утверждению IP-адрес, сообщите нам.</span><span class="sxs-lookup"><span data-stu-id="519b8-p172">Check the certificate, in a browser connect to the IP address using  *HTTPS://\<IP_ADDRESS\>*  , check the domains listed on the certificate to understand what domains are associated with the IP address. If it's a Microsoft owned IP address and not on the list of Office 365 IP addresses, it's likely the IP address is associated with a Microsoft CDN such as  *MSOCDN.NET*  or another Microsoft domain without published IP information. If you do find the domain on the certificate is one where we claim to list the IP address, please let us know.</span></span> 
    
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a><span data-ttu-id="519b8-450">Почему отображаются имена, например nsatc.net или akadns.net в доменных имен Microsoft?</span><span class="sxs-lookup"><span data-stu-id="519b8-450">Why do I see names such as nsatc.net or akadns.net in the Microsoft domain names?</span></span>
<span data-ttu-id="519b8-451"><a name="bkmk_akamai"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-451"></span></span>

<span data-ttu-id="519b8-p173">Office 365 и другие службы Microsoft используют несколько служб сторонних производителей, например Akamai и MarkMonitor для улучшения работы в Office 365. Оставьте предоставляет оптимального возможности изменения этих служб в будущем. При этом, мы часто публикация записи CNAME, которая указывает третьей стороне собственные домена, записи или IP-адрес. Домены сторонних производителей могут размещаться контент, такой как CDN, или они могут размещаться службы, такие как служба управления географических трафика. При появлении подключений эти третьим лицам, они в виде перенаправления или ссылок, не начального запроса от клиента. Некоторые клиенты должны убедиться эту форму ссылок и перенаправление разрешено передавать без явного добавления используют длинный список возможных служб сторонних производителей полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="519b8-p173">Office 365 and other Microsoft services use several third-party services such as Akamai and MarkMonitor to improve your Office 365 experience. To keep giving you the best experience possible, we may change these services in the future. In doing so, we often publish the CNAME record which points to a third party owned domain, A record, or IP address. Third party domains may host content, such as a CDN, or they may host a service, such as a geographical traffic management service. When you see connections to these third parties, they're in the form of a redirect or referral, not an initial request from the client. Some customers need to ensure this form of referral and redirection is allowed to pass without explicitly adding the long list of potential FQDNs third party services may use.</span></span>
  
<span data-ttu-id="519b8-p174">Список служб, может быть изменен в любое время. Ниже перечислены некоторые из служб, используемых в настоящее время:</span><span class="sxs-lookup"><span data-stu-id="519b8-p174">The list of services is subject to change at any time. Some of the services currently in use include:</span></span>
  
<span data-ttu-id="519b8-p175">[MarkMonitor](https://www.markmonitor.com/) используется при появлении запросов, которые включают \* \*. nsatc.net\* . Эта служба предоставляет защиты имя домена и мониторинга для защиты от вредоносного поведения.</span><span class="sxs-lookup"><span data-stu-id="519b8-p175">[MarkMonitor](https://www.markmonitor.com/) is in use when you see requests that include  *\*.nsatc.net*  . This service provides domain name protection and monitoring to protect against malicious behavior.</span></span> 
  
<span data-ttu-id="519b8-p176">[ExactTarget](https://www.marketingcloud.com/) используется при появлении запросов к \* \*. exacttarget.com\* . Эта служба предоставляет электронной почты ссылку Управление и мониторинг от вредоносного поведения.</span><span class="sxs-lookup"><span data-stu-id="519b8-p176">[ExactTarget](https://www.marketingcloud.com/) is in use when you see requests to  *\*.exacttarget.com*  . This service provides email link management and monitoring against malicious behavior.</span></span> 
  
<span data-ttu-id="519b8-p177">При появлении запросы, включающие один из следующих полных доменных имен [Akamai](https://www.akamai.com/) не используется. Данная служба предлагает географически DNS и служб сети доставки содержимого.</span><span class="sxs-lookup"><span data-stu-id="519b8-p177">[Akamai](https://www.akamai.com/) is in use when you see requests that include one of the following FQDNs. This service offers geo-DNS and content delivery network services.</span></span> 
  
```
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net

```

### <a name="what-are-the-three-types-of-office-365-endpoints"></a><span data-ttu-id="519b8-466">Какие существуют три типа конечных точках Office 365?</span><span class="sxs-lookup"><span data-stu-id="519b8-466">What are the three types of Office 365 endpoints?</span></span>
<span data-ttu-id="519b8-467"><a name="bkmk_akamai"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-467"></span></span>

- <span data-ttu-id="519b8-p178">Подключитесь к службам сторонних производителей для получения базовой служб Интернета, например DNS-запросы и получения содержимого CDN. Можно также подключиться к службам сторонних производителей для интеграции, такие как включение видеороликов YouTube записных книжек OneNote.</span><span class="sxs-lookup"><span data-stu-id="519b8-p178">You connect to third-party services to retrieve basic internet services such as DNS lookups and CDN content retrieval. You also connect to third-party services for integrations such as incorporating YouTube videos in your OneNote notebooks.</span></span>
    
- <span data-ttu-id="519b8-p179">Подключитесь к дополнительного служб, размещенных и запустите корпорацией Майкрософт, таких как узлы пограничного сервера, которые позволяют сети запрос на ввод корпорации Майкрософт глобальной сети на ближайших веб-сайта на своем компьютере. Как третьего наибольшего сети как это повышает эффективность подключения. Можно также подключиться к службам Microsoft Azure такими как службы Azure мультимедиа, которые используются по-разному служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="519b8-p179">You connect to secondary services hosted and run by Microsoft such as edge nodes that enable your network request to enter Microsoft's global network at the closest internet location to your computer. As the third largest network on the planet, this improves your connectivity experience. You also connect to Microsoft Azure services such as Azure Media Services which are used by a variety of Office 365 services.</span></span>
    
- <span data-ttu-id="519b8-p180">Подключитесь к основным службам Office 365 например сервере почтовых ящиков Exchange Online или Скайп для Business Online server, где находятся уникальное и конфиденциальные данные. Можно подключиться к основным службам Office 365 с полное доменное имя или IP-адрес и использовать internet или ExpressRoute цепей. Только можно подключить к сторонних производителей и дополнительных служб, с помощью полных доменных имен в Интернете цепи.</span><span class="sxs-lookup"><span data-stu-id="519b8-p180">You connect to primary Office 365 services such as the Exchange Online mailbox server or the Skype for Business Online server where your unique and proprietary data lives. You can connect to the primary Office 365 services by FQDN or IP address and use internet or ExpressRoute circuits. You can only connect to the third party and secondary services using FQDNs on an internet circuit.</span></span>
    
<span data-ttu-id="519b8-p181">На следующей схеме показана различия между областями эти службы. На этой диаграмме локальной сети клиента в нижнем левом имеет несколько сетевых устройств для помощи в управлении подключение к сети. Конфигурации следующим образом являются общими для предприятий. Если вашей сети только брандмауэра между клиентскими компьютерами и Интернетом, а также поддерживаются, а вы наверняка хотели бы убедиться, что брандмауэр поддерживает полные доменные имена и подстановочные знаки в список правил allow.</span><span class="sxs-lookup"><span data-stu-id="519b8-p181">The following diagram shows the differences between these service areas. In this diagram, the customer on-premises network in the lower left has multiple network devices to assist in managing network connectivity. Configurations like this one are common for enterprise customers. If your network only has a firewall between your client computers and the internet, that's supported as well, and you'll want to ensure your firewall can support FQDNs and wildcards in the allow list rules.</span></span>
  
<span data-ttu-id="519b8-480">Чтение [Сетевого подключения к Office 365 принципы](office-365-network-connectivity-principles.md) Чтобы получить дополнительные сведения о категории конечной точки Office 365 и понять принципы подключения для безопасного управления Office 365 трафика и начало обеспечить максимально высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="519b8-480">Read [Office 365 Network Connectivity Principles](office-365-network-connectivity-principles.md) to get more information on Office 365 endpoint categories, and to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> 
  
![Отображает три различных типа конечных точек сети при использовании Office 365](media/6582bcfa-11ba-4ac2-9b69-14bef0437670.png)
  
### <a name="i-cant-or-dont-want-to-use-any-third-party-service"></a><span data-ttu-id="519b8-482">Не удается или не хотите использовать любой службы сторонних производителей</span><span class="sxs-lookup"><span data-stu-id="519b8-482">I can't or don't want to use any third-party service</span></span>
<span data-ttu-id="519b8-483"><a name="bkmk_thirdparty"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-483"></span></span>

<span data-ttu-id="519b8-p182">Office 365 — это набор служб, созданных в функции через Интернет, надежность и доступность использованием основаны на многих стандартных Интернет-служб, доступных. Например стандартный служб Интернета, например DNS, списки отзыва Сертификатов и CDN должен быть доступен, как они должны быть доступны для использования большинство современных Интернет-служб с помощью Office 365.</span><span class="sxs-lookup"><span data-stu-id="519b8-p182">Office 365 is a suite of services built to function over the internet, the reliability and availability promises are based on many standard internet services being available. For example, standard internet services such as DNS, CRL, and CDNs must be reachable to use Office 365 just as they must be reachable to use most modern internet services.</span></span>
  
<span data-ttu-id="519b8-p183">Помимо этих основных служб Интернета существуют службы сторонних производителей, которые используются только для интеграции функций. Например с помощью Giphy.com внутри групп Майкрософт позволяет пользователям легко включать рисунки в формате GIF внутри групп. Аналогично YouTube и Flickr являются служб сторонних производителей, которые используются для интегрируют видео и изображений в клиентах Office из Интернета. Хотя они необходимы для интеграции, они помечаются как необязательные в статье конечных точках Office 365, это значит, что основные функциональные возможности службы будет продолжать работать, если конечная точка не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="519b8-p183">In addition to these basic internet services, there are third-party services that are only used to integrate functionality. For example, using Giphy.com within Microsoft Teams allows customers to seamlessly include Gifs within Teams. Similarly, YouTube and Flickr are third-party services that are used to seamlessly integrate video and images into Office clients from the internet. While these are needed for integration, they're marked as optional in the Office 365 endpoints article which means core functionality of the service will continue to function if the endpoint isn't accessible.</span></span>
  
<span data-ttu-id="519b8-490">Если выполняется попытка использовать Office 365 и уже знают, что третья сторона службы недоступны можно [Разрешить все полные доменные имена, помеченные обязательный или необязательный в этой статье через прокси-сервера и брандмауэра](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="519b8-490">If you're attempting to use Office 365 and are finding third party services aren't accessible you'll want to [ensure all FQDNs marked required or optional in this article are allowed through the proxy and firewall](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="i-cant-or-dont-want-to-use-any-secondary-services"></a><span data-ttu-id="519b8-491">Не удается или не хотите использовать какие-либо дополнительных службы</span><span class="sxs-lookup"><span data-stu-id="519b8-491">I can't or don't want to use any secondary services</span></span>
<span data-ttu-id="519b8-492"><a name="bkmk_secondary"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-492"></span></span>

<span data-ttu-id="519b8-p184">Дополнительный службы, службы Майкрософт, которые не попадают в элемент управления Office 365. Это пограничной сети, носитель служб Azure и сети доставки содержимого Azure. Они необходимы для использования Office 365 и должен быть доступен.</span><span class="sxs-lookup"><span data-stu-id="519b8-p184">Secondary services are Microsoft services that don't fall within Office 365 control. These are things like the edge network, Azure Media Services, and Azure Content Delivery Networks. These are all required to use Office 365 and must be reachable.</span></span>
  
<span data-ttu-id="519b8-496">Если выполняется попытка использовать Office 365 и уже знают, что третья сторона службы недоступны можно [Разрешить все полные доменные имена, помеченные обязательный или необязательный в этой статье через прокси-сервера и брандмауэра](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="519b8-496">If you're attempting to use Office 365 and are finding third party services aren't accessible you'll want to [ensure all FQDNs marked required or optional in this article are allowed through the proxy and firewall](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a><span data-ttu-id="519b8-497">Как запретить доступ к службам потребителей корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="519b8-497">How do I block access to Microsoft's consumer services?</span></span>
<span data-ttu-id="519b8-498"><a name="bkmk_consumer"> </a></span><span class="sxs-lookup"><span data-stu-id="519b8-498"></span></span>

<span data-ttu-id="519b8-p185">Ограничение доступа к наших услуг потребитель должно выполняться на собственный риск, только надежный способ блокировки потребитель службы для ограничения доступа к *login.live.com* полное доменное имя. В этом поле полное доменное имя используется широкий набор служб, включая не потребитель службы, такие как MSDN, TechNet и другими пользователями. Ограничение доступа к этой полное доменное имя может привести к необходимости также включать исключения для сетевых запросов, связанные с этими службами.</span><span class="sxs-lookup"><span data-stu-id="519b8-p185">Restricting access to our consumer services should be done at your own risk, the only reliable way to block consumer services is to restrict access to the  *login.live.com*  FQDN. This FQDN is used by a broad set of services including non-consumer services such as MSDN, TechNet, and others. Restricting access to this FQDN may result in the need to also include exceptions to the rule for network requests associated with these services.</span></span> 
  
<span data-ttu-id="519b8-502">Имейте в виду, что блокирующая доступ к службам потребитель Microsoft сам по себе он не предотвратить возможность другого пользователя в сети на exfiltrate сведения, с помощью клиента Office 365 или другие службы.</span><span class="sxs-lookup"><span data-stu-id="519b8-502">Keep in mind that blocking access to the Microsoft consumer services alone won't prevent the ability for someone on your network to exfiltrate information using an Office 365 tenant or other service.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="519b8-503">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="519b8-503">Related Topics</span></span>

[<span data-ttu-id="519b8-504">Диапазоны IP-адресов центра обработки данных Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="519b8-504">Microsoft Azure Datacenter IP Ranges</span></span>](https://www.microsoft.com/download/details.aspx?id=41653)
  
[<span data-ttu-id="519b8-505">Microsoft общедоступный IP-адрес пространства</span><span class="sxs-lookup"><span data-stu-id="519b8-505">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)
  
[<span data-ttu-id="519b8-506">Требования к инфраструктуре сети для Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="519b8-506">Network infrastructure requirements for Microsoft Intune</span></span>](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[<span data-ttu-id="519b8-507">Power BI и ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="519b8-507">Power BI and ExpressRoute</span></span>](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[<span data-ttu-id="519b8-508">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="519b8-508">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)
  
[<span data-ttu-id="519b8-509">Управление подключением ExpressRoute для Office 365</span><span class="sxs-lookup"><span data-stu-id="519b8-509">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)
  
[<span data-ttu-id="519b8-510">Принципы сетевого подключения к Office 365</span><span class="sxs-lookup"><span data-stu-id="519b8-510">Office 365 Network Connectivity Principles</span></span>](office-365-network-connectivity-principles.md)
  
