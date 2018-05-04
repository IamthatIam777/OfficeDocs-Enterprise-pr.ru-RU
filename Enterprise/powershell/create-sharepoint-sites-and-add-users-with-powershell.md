---
title: Создание сайтов и добавление пользователей в SharePoint Online с помощью Office 365 PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 'Сводка: Использование PowerShell Office 365 для создания новых сайтов SharePoint Online, а затем добавьте пользователей и групп для этих сайтов.'
ms.openlocfilehash: 0a0438917f6e7010b56703ce0bf73e89e1db0533
ms.sourcegitcommit: 74cdb2534bce376abc9cf4fef85ff039c46ee790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="create-sharepoint-online-sites-and-add-users-with-office-365-powershell"></a><span data-ttu-id="2ab30-103">Создание сайтов и добавление пользователей в SharePoint Online с помощью Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ab30-103">Create SharePoint Online sites and add users with Office 365 PowerShell</span></span>

 <span data-ttu-id="2ab30-104">**Сводка:** Для создания новых сайтов SharePoint Online с помощью Office 365 PowerShell, а затем добавьте пользователей и групп для этих сайтов.</span><span class="sxs-lookup"><span data-stu-id="2ab30-104">**Summary:** Use Office 365 PowerShell to create new SharePoint Online sites, and then add users and groups to those sites.</span></span>

<span data-ttu-id="2ab30-p101">При использовании Office 365 PowerShell для создания сайтов SharePoint Online и добавление пользователей можно быстро и повторно выполнить задачи значительно быстрее, чем в центре администрирования Office 356. Можно также выполнять задачи, которые невозможно выполнить в центре администрирования Office 356.</span><span class="sxs-lookup"><span data-stu-id="2ab30-p101">When you use Office 365 PowerShell to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Office 356 admin center. You can also perform tasks that are not possible to perform in the Office 356 admin center.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="2ab30-107">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="2ab30-107">Before you begin</span></span>

<span data-ttu-id="2ab30-p102">Процедуры, описанные в этом разделе требуется подключение к SharePoint Online. Сведения содержатся в разделе [подключение к SharePoint Online PowerShell](https://docs.microsoft.com/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="2ab30-p102">The procedures in this topic require you to connect to SharePoint Online. For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-office-365-powershell"></a><span data-ttu-id="2ab30-110">Шаг 1. Создание семейств веб-сайтов с помощью Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ab30-110">Step 1: Create new site collections using Office 365 PowerShell</span></span>

<span data-ttu-id="2ab30-p103">Создайте несколько сайтов с помощью Office 365 PowerShell и CSV-файла. Чтобы создать CSV-файл, используйте пример кода и "Блокнот". Для этого необходимо заменить содержимое заполнителей в угловых скобках на данные о сайтах и клиенте. Эта процедура позволяет создать один файл и выполнить одну команду Office 365 PowerShell, которая использует этот файл. Благодаря этому действия можно повторять в разных средах, а также устраняются многие, если не все, ошибки, связанные с вводом длинных команд в командной консоли SharePoint Online. Эта процедура состоит из двух частей. Сначала вы создаете CSV-файл, а затем ссылаетесь на него с помощью Office 365 PowerShell. Содержимое файла будет использоваться для создания сайтов.</span><span class="sxs-lookup"><span data-stu-id="2ab30-p103">Create multiple sites using Office 365 PowerShell and a .csv file that you create using the example code provided and Notepad. For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information. This process allows you to create a single file and run a single Office 365 PowerShell command that uses that file. This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell. There are two parts to this procedure. First you’ll create a .csv file, and then you’ll reference that .csv file using Office 365 PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="2ab30-p104">Командлет Office 365 PowerShell импортирует CSV-файл и передает его в цикл в фигурных скобках, который считывает первую строку файла как заголовки столбцов. Командлет Office 365 PowerShell проходит по остальным записям, создает семейство веб-сайтов для каждой из них и назначает свойства семейства веб-сайтов в соответствии с заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="2ab30-p104">The Office 365 PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers. The Office 365 PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

###<a name="create-a-csv-file"></a><span data-ttu-id="2ab30-119">Создание CSV-файла</span><span class="sxs-lookup"><span data-stu-id="2ab30-119">Create a .csv file</span></span>

1. <span data-ttu-id="2ab30-120">Откройте Блокнот и вставьте в него следующий блок текста:</span><span class="sxs-lookup"><span data-stu-id="2ab30-120">Open Notepad, and paste the following text block into it:</span></span></br>
```
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```</br>Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</br>(You can press Ctrl+H when you use Notepad to bulk replace faster.)</br>
2. Save the file on your desktop as **SiteCollections.csv**.

 > [!TIP]
> Before you use this or any other .csv or Windows PowerShell script file, it is good practice to make sure that there are no extraneous or nonprinting characters. Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters. There should be no extraneous nonprinting characters. For example, there should be no paragraph marks beyond the final one at the end of the file.

### Run the Windows PowerShell command

1. At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</br>
```
<span data-ttu-id="2ab30-121">Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {новые SPOSite-владелец $_. Владелец - StorageQuota $_. StorageQuota-URL-адрес $_. URL-адрес - NoWait - ResourceQuota $_. ResourceQuota-шаблон $_. Шаблон - идентификатор часового пояса $_. Идентификатор часового пояса-Title $_. Имя}</span><span class="sxs-lookup"><span data-stu-id="2ab30-121">Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}</span></span>
```
</br>Where *MyAlias* equals your user alias.</br>
2. Wait for the Windows PowerShell prompt to reappear. It might take a minute or two.</br>
3. At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</br>
```
<span data-ttu-id="2ab30-122">Get-SPOSite-подробные | Format-Table - AutoSize</span><span class="sxs-lookup"><span data-stu-id="2ab30-122">Get-SPOSite -Detailed | Format-Table -AutoSize</span></span>
```</br>
4. Note the new site collections in the list. You should see the following site collections: **contosotest**, **TeamSite01**, **Blog01**, and **Project01**.

That’s it. You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell cmdlet. You’re now ready to create and assign users to these sites.

## Step 2: Add users and groups

Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.

The following procedures assume that you successfully created the site collections contosotest, TeamSite01, Blog01, and Project01.

### Create .csv and .ps1 files

1. Open Notepad, and paste the following text block into it:</br>
```
<span data-ttu-id="2ab30-123">Сайт, группы, PermissionLevels https://tenant.sharepoint.com/sites/contosotest, руководители проекта Contoso, полный доступ https://tenant.sharepoint.com/sites/contosotest, аудиторы Contoso только просмотр https://tenant.sharepoint.com/sites/contosotest, конструкторы Contoso, разработки https://tenant.sharepoint.com/sites/TeamSite01, XT1000 ведущие специалисты, полный доступ https://tenant.sharepoint.com/sites/TeamSite01, консультантов по XT1000 изменить https://tenant.sharepoint.com/sites/Blog01, блог Contoso Конструкторы, разработки https://tenant.sharepoint.com/sites/Blog01, изменить редакторы блогов Contoso https://tenant.sharepoint.com/sites/Project01, Project альфа утверждающих, полный доступ</span><span class="sxs-lookup"><span data-stu-id="2ab30-123">Site,Group,PermissionLevels https://tenant.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control https://tenant.sharepoint.com/sites/contosotest,Contoso Auditors,View Only https://tenant.sharepoint.com/sites/contosotest,Contoso Designers,Design https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control</span></span>
```
</br>Where *tenant* equals your tenant name.</br>
2. Save the file to your desktop as **GroupsAndPermissions.csv**.</br>
3. Open a new instance of Notepad, and paste the following text block into it:</br>
```
<span data-ttu-id="2ab30-124">Руководители проекта Contoso сайта группы, LoginName, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/contosotest Contoso аудиторов, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/contosotest Contoso конструкторов, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/contosotest ведущие сотрудники групп XT1000 username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01 XT1000 консультантов по, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01 конструкторов блог Contoso, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01 редакторы блогов Contoso, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01 Альфа утверждающие проекта, username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01</span><span class="sxs-lookup"><span data-stu-id="2ab30-124">Group,LoginName,Site Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/contosotest Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/contosotest Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/contosotest XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01 XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01 Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01 Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01 Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01</span></span>
```
</br>Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</br>
4. Save the file to your desktop as **Users.csv**.</br>
5. Open a new instance of Notepad, and paste the following text block into it:</br>
```
<span data-ttu-id="2ab30-125">Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {новые SPOSiteGroup-групповой $_. Групповой $ - PermissionLevels_. PermissionLevels-$_веб-сайтов. Import-Csv C:\users\MyAlias\desktop\Users.csv Site} | где {-SPOUser-групповой $_. Групповое — LoginName $_. LoginName-веб-сайтов $_. Сайт}</span><span class="sxs-lookup"><span data-stu-id="2ab30-125">Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site} Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}</span></span>
```
</br>Where MyAlias equals the user name of the user that is currently logged on.</br>
6. Save the file to your desktop as **UsersAndGroups.ps1**. This is a simple Windows PowerShell script.

You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.

### Run UsersAndGroups.ps1 script

1. Return to the SharePoint Online Management Shell.</br>
2. At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</br>
```
<span data-ttu-id="2ab30-126">Командлет Set-ExecutionPolicy сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="2ab30-126">Set-ExecutionPolicy Bypass</span></span>
```</br>
3. At the confirmation prompt, press **Y**.</br>
4. At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</br>
```
<span data-ttu-id="2ab30-127">c:\users\MyAlias\desktop\UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="2ab30-127">c:\users\MyAlias\desktop\UsersAndGroups.ps1</span></span>
```
</br>Where *MyAlias* equals your user name.</br>
5. Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.

## See also

[Connect to SharePoint Online PowerShell](https://docs.microsoft.com/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Manage SharePoint Online site groups Office 365 PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Manage Office 365 with Office 365 PowerShell](manage-office-365-with-office-365-powershell.md)
  
[Getting started with Office 365 PowerShell](getting-started-with-office-365-powershell.md)

