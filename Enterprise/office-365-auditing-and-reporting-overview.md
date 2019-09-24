---
title: Аудит и создание отчетов в облачных службах Майкрософт
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
description: Обзор функций аудита и создания отчетов в Office 365, Microsoft 365 и гарантиях обслуживания.
ms.openlocfilehash: 7f569786903ce00815fa7c28226cbbd181eaeb58
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067782"
---
# <a name="auditing-and-reporting-in-microsoft-cloud-services"></a><span data-ttu-id="fc174-103">Аудит и создание отчетов в облачных службах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fc174-103">Auditing and Reporting in Microsoft Cloud Services</span></span>

## <a name="introduction"></a><span data-ttu-id="fc174-104">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="fc174-104">Introduction</span></span>

<span data-ttu-id="fc174-105">Облачные службы Майкрософт включают несколько функций аудита и создания отчетов, которые можно использовать для отслеживания действий пользователей и администраторов в своих клиентах, в том числе изменения, внесенные в параметры конфигурации клиента Exchange Online и SharePoint Online, а также изменения, внесенные пользователями в документы и другие элементы.</span><span class="sxs-lookup"><span data-stu-id="fc174-105">Microsoft cloud services include several auditing and reporting features you can use to track user and administrative activity within their tenant, Examples include changes made to Exchange Online and SharePoint Online tenant configuration settings, and changes made by users to documents and other items.</span></span> <span data-ttu-id="fc174-106">Вы можете использовать сведения аудита и отчеты, доступные в облачных службах Майкрософт, для более эффективного управления пользовательскими возможностями, устранения рисков и соблюдения обязательств по обеспечению соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fc174-106">You can use audit information and reports available in Microsoft cloud services to more effectively manage user experience, mitigate risks, and fulfill compliance obligations.</span></span>

## <a name="security--compliance-centers"></a><span data-ttu-id="fc174-107">Центры безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fc174-107">Security & Compliance Centers</span></span>

<span data-ttu-id="fc174-108">Центр [соответствия требованиям & безопасности Office 365](https://protection.office.com), [центр безопасности Майкрософт 365](https://security.microsoft.com)и [центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com) — это односторонние порталы для защиты данных в Организации, а также много аудита и отчетов функции.</span><span class="sxs-lookup"><span data-stu-id="fc174-108">The [Office 365 Security & Compliance Center](https://protection.office.com), the [Microsoft 365 Security Center](https://security.microsoft.com), and the [Microsoft 365 Compliance Center](https://compliance.microsoft.com) are one-stop portals for protecting data in your organization, and they include many auditing and reporting features.</span></span> <span data-ttu-id="fc174-109">Эти центры помогают обеспечить защиту данных или требования соответствия требованиям, а также выполнять аудит действий пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="fc174-109">These centers help you with your data protection or compliance needs and audit user and administrator activity.</span></span> <span data-ttu-id="fc174-110">Вы можете получить доступ к этим центрам с помощью учетной записи администратора подписки.</span><span class="sxs-lookup"><span data-stu-id="fc174-110">You can access these centers using your subscription admin account.</span></span>

<span data-ttu-id="fc174-111">В этих центрах есть области навигации для доступа к нескольким функциям:</span><span class="sxs-lookup"><span data-stu-id="fc174-111">These centers include navigation panes for access to several features:</span></span>

- <span data-ttu-id="fc174-112">**Оповещения:** Позволяет управлять оповещениями, просматривать оповещения, связанные с безопасностью, а также управлять расширенными оповещениями с помощью [Office 365 Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="fc174-112">**Alerts:** Enables you to manage alerts, view security-related alerts, and manage advanced alerts using [Office 365 Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>
- <span data-ttu-id="fc174-113">**Разрешения:** Позволяет [назначать разрешения](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76) , такие как администратор соответствия требованиям, диспетчер обнаружения электронных данных и другие пользователи в вашей организации, чтобы они могли выполнять задачи в этих центрах.</span><span class="sxs-lookup"><span data-stu-id="fc174-113">**Permissions:** Enables you to [assign permissions](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76) such as Compliance Administrator, eDiscovery Manager, and others to people in your organization so they can perform tasks in these centers.</span></span> <span data-ttu-id="fc174-114">Разрешения для большинства функций назначаются в каждом центре, но другие разрешения необходимо настроить с помощью центра администрирования Exchange и центра администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc174-114">You assign permissions for most features in each center, but other permissions must be configured using the Exchange admin center and SharePoint admin center.</span></span>
- <span data-ttu-id="fc174-115">**Управление угрозами:** Позволяет создавать и применять политики управления устройствами с помощью [управления мобильными устройствами Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), чтобы настроить политики защиты от [потери данных](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e) для Организации, настроить фильтрацию электронной почты, защиту от вредоносных программ, DomainKeys identified mail идентифицированных Mail (DKIM), безопасные вложения, безопасные ссылки и приложения OAuth.</span><span class="sxs-lookup"><span data-stu-id="fc174-115">**Threat management:** Enables you to create and apply device management policies using [Office 365 Mobile Device Management](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), to set up [Data Loss Prevention](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP) policies for your organization, to configure email filtering, anti-malware, DomainKeys Identified Mail (DKIM), safe attachments, safe links, and OAuth apps.</span></span>
- <span data-ttu-id="fc174-116">**Управление данными:** Позволяет [импортировать данные электронной почты или SharePoint из других систем в Office 365](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [настроить архивные почтовые ящики](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)и настроить [политики хранения](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c) для электронной почты и другого контента в Организации.</span><span class="sxs-lookup"><span data-stu-id="fc174-116">**Data governance:** Enables you to [import email or SharePoint data from other systems into Office 365](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [configure archive mailboxes](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce), and set [retention policies](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c) for email and other content within your organization.</span></span>
- <span data-ttu-id="fc174-117">**Поиск & расследования:** Предоставляет средства [поиска контента](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [журнала аудита](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), карантина и [обнаружения электронных](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) данных на месте для быстрого перехода к активности через почтовые ящики Exchange Online, группы и общедоступные папки, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="fc174-117">**Search & investigation:** Provides [content search](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [audit log](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), quarantine, and [eDiscovery case management](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) tools to quickly drill into activity across Exchange Online mailboxes, groups and public folders, SharePoint Online, and OneDrive for Business.</span></span>
- <span data-ttu-id="fc174-118">**Отчеты:** Позволяет быстро получать доступ к [отчетам](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) для SharePoint Online, OneDrive для бизнеса, Exchange Online и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fc174-118">**Reports:** Enables you to quickly access [reports](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) for SharePoint Online, OneDrive for Business, Exchange Online, and Azure AD.</span></span>
- <span data-ttu-id="fc174-119">**Гарантия обслуживания:** Сведения о том, как корпорация Майкрософт обеспечивает безопасность, конфиденциальность и соответствие требованиям с глобальными стандартами для Office 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune и других облачных служб.</span><span class="sxs-lookup"><span data-stu-id="fc174-119">**Service assurance:** Provides information about how Microsoft maintains security, privacy, and compliance with global standards for Office 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune, and other cloud services.</span></span> <span data-ttu-id="fc174-120">Также включает доступ к сторонним ISO, SOC и другим отчетам аудита, а также аудиту элементов управления, в которых содержатся сведения о различных элементах управления, проверенных и проверенных сторонними аудиториями Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc174-120">Also includes access to third-party ISO, SOC, and other audit reports, as well as Audited Controls, which provides details about the various controls that have been tested and verified by third-party auditors of Office 365.</span></span>

## <a name="service-assurance"></a><span data-ttu-id="fc174-121">Гарантия обслуживания</span><span class="sxs-lookup"><span data-stu-id="fc174-121">Service Assurance</span></span>

<span data-ttu-id="fc174-122">Многие организации в регулируемых отраслях подчиняются значительным требованиям к соответствиям.</span><span class="sxs-lookup"><span data-stu-id="fc174-122">Many organizations in regulated industries are subject to extensive compliance requirements.</span></span> <span data-ttu-id="fc174-123">Для выполнения собственных оценок риска пользователям часто требуются подробные сведения о том, как Office 365 обеспечивает безопасность и конфиденциальность данных.</span><span class="sxs-lookup"><span data-stu-id="fc174-123">To perform their own risk assessments, customers often need in-depth information about how Office 365 maintains the security and privacy of their data.</span></span> <span data-ttu-id="fc174-124">Корпорация Майкрософт стремится обеспечить безопасность и конфиденциальность данных клиентов в облачных службах и получить доверие клиентов, предоставляя прозрачное представление его операций и простой доступ к независимым отчетам и оценкам соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fc174-124">Microsoft is committed to the security and privacy of customer data in its cloud services and to earning customer trust by providing a transparent view of its operations, and easy access to independent compliance reports and assessments.</span></span>

<span data-ttu-id="fc174-125">Гарантия обслуживания обеспечивает прозрачность операций и сведения о том, как корпорация Майкрософт обеспечивает безопасность, конфиденциальность и соответствие данных клиентов в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc174-125">Service Assurance provides transparency of operations and information about how Microsoft maintains the security, privacy, and compliance of customer data in Office 365.</span></span> <span data-ttu-id="fc174-126">Он включает отчеты об аудите сторонних поставщиков и библиотеку технических документов, вопросов и ответов, а также другие материалы по Office 365, такие как шифрование данных, устойчивость данных, Управление инцидентами безопасности и многое другое.</span><span class="sxs-lookup"><span data-stu-id="fc174-126">It includes third-party audit reports along with a library of white papers, FAQs, and other materials on Office 365 topics such as data encryption, data resiliency, security incident management and more.</span></span> <span data-ttu-id="fc174-127">Клиенты могут использовать эту информацию для выполнения собственных оценок нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="fc174-127">Customers can use this information to perform their own regulatory risk assessments.</span></span> <span data-ttu-id="fc174-128">Руководители соответствия требованиям могут назначить роль "пользователь службы контроля доступа", чтобы предоставить пользователям доступ к службе "гарантия".</span><span class="sxs-lookup"><span data-stu-id="fc174-128">Compliance officers can assign the "Service Assurance User" role to give users access to Service Assurance.</span></span> <span data-ttu-id="fc174-129">Администратор клиента может также предоставлять внешних пользователей, например независимых аудиторов, с доступом к сведениям в панели мониторинга служб Службы [Microsoft Cloud Service Portal](http://aka.ms/STP) (STP).</span><span class="sxs-lookup"><span data-stu-id="fc174-129">The tenant administrator can also provide external users, such as independent auditors, with access to information in the Service Assurance dashboard through the [Microsoft Cloud Service Trust Portal](http://aka.ms/STP) (STP).</span></span> <span data-ttu-id="fc174-130">Для получения дополнительных сведений о доступе к STP посетите страницу [Начало работы с порталом доверия службы для подписок на Office 365 для бизнеса, Azure и Dynamics CRM Online](http://aka.ms/STPHelp).</span><span class="sxs-lookup"><span data-stu-id="fc174-130">For details on how to access the STP, visit [Get started with the Service Trust Portal for Office 365 for business, Azure, and Dynamics CRM Online subscriptions](http://aka.ms/STPHelp).</span></span>

## <a name="onedrive-for-business-admin-center"></a><span data-ttu-id="fc174-131">Центр администрирования OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fc174-131">OneDrive for Business Admin Center</span></span>

<span data-ttu-id="fc174-132">Центр администрирования Microsoft OneDrive помогает быстро и легко управлять параметрами OneDrive для бизнеса в Организации в одном месте.</span><span class="sxs-lookup"><span data-stu-id="fc174-132">The Microsoft OneDrive admin center helps you quickly and easily manage your organization's OneDrive for Business settings in one place.</span></span> <span data-ttu-id="fc174-133">Для использования центра администрирования OneDrive требуется доступ к onedrive.com.</span><span class="sxs-lookup"><span data-stu-id="fc174-133">To use the OneDrive admin center, access to onedrive.com is required.</span></span> <span data-ttu-id="fc174-134">Кроме того, необходимо быть глобальным администратором организации или настраиваемым администратором с ролью администратора SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc174-134">You must also be a global admin for your organization or a custom admin with the SharePoint administrator role.</span></span> <span data-ttu-id="fc174-135">Доступ к центру администрирования OneDrive для бизнеса по [https://admin.onedrive.com](https://admin.onedrive.com/)адресу.</span><span class="sxs-lookup"><span data-stu-id="fc174-135">Access the OneDrive for Business admin center at [https://admin.onedrive.com](https://admin.onedrive.com/).</span></span>

<span data-ttu-id="fc174-136">Основные функции включают область соответствия требованиям, которая предоставляет администраторам ссылки на соответствующий центр управления для ключевых сценариев, таких как поиск в журнале аудита, работа с DLP, хранение, обнаружение электронных данных и оповещения.</span><span class="sxs-lookup"><span data-stu-id="fc174-136">Key features include a Compliance area that provides administrators with links to the appropriate management center for key scenarios like searching the audit log, working with DLP, retention, eDiscovery, and alerting.</span></span>

## <a name="related-links"></a><span data-ttu-id="fc174-137">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="fc174-137">Related Links</span></span>

- [<span data-ttu-id="fc174-138">Функции обнаружения электронных данных и поиска</span><span class="sxs-lookup"><span data-stu-id="fc174-138">eDiscovery and Search Features</span></span>](office-365-ediscovery-and-search-features.md)
- [<span data-ttu-id="fc174-139">Функции создания отчетов в Office 365</span><span class="sxs-lookup"><span data-stu-id="fc174-139">Office 365 Reporting Features</span></span>](office-365-reporting-features.md)
- [<span data-ttu-id="fc174-140">API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="fc174-140">Office 365 Management Activity API</span></span>](office-365-management-activity-api.md)
- [<span data-ttu-id="fc174-141">Перенос почтовых ящиков Office 365</span><span class="sxs-lookup"><span data-stu-id="fc174-141">Office 365 Mailbox Migrations</span></span>](office-365-mailbox-migrations.md)
- [<span data-ttu-id="fc174-142">Внутренняя регистрация для инженеров Office 365</span><span class="sxs-lookup"><span data-stu-id="fc174-142">Internal Logging for Office 365 Engineering</span></span>](office-365-internal-logging.md)