---
title: Журнал транзакций Office 365 IdFix
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
ms.assetid: d58b7d45-7947-4193-9456-82ba76f42d89
description: Пример и описание соглашение об именовании и уровень журнала по умолчанию в журнал транзакций Office 365 IdFix.
ms.openlocfilehash: 016318c7e771ec6c5f90336e11c5dd011144d12e
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542456"
---
# <a name="office-365-idfix-transaction-log"></a><span data-ttu-id="1f19a-103">Журнал транзакций Office 365 IdFix</span><span class="sxs-lookup"><span data-stu-id="1f19a-103">Office 365 IdFix transaction log</span></span>

<span data-ttu-id="1f19a-104">Пример и описание соглашение об именовании и уровень журнала по умолчанию в журнал транзакций Office 365 IdFix.</span><span class="sxs-lookup"><span data-stu-id="1f19a-104">Provides an example and describes the naming convention and default log level of the Office 365 IdFix transaction log.</span></span>
  
## <a name="idfix-transaction-log-location"></a><span data-ttu-id="1f19a-105">Расположение журнала транзакций IdFix</span><span class="sxs-lookup"><span data-stu-id="1f19a-105">IdFix transaction log location</span></span>

<span data-ttu-id="1f19a-p101">Средство Office 365 IdFix создает новый журнал транзакций каждый раз, нажмите кнопку **Применить** в IdFix и применить изменения к лесу Active Directory. Журнал транзакций сохраняются в ту же папку, где установлен IdFix. По умолчанию эта папка не C:\Deployment Tools\IDFix. Имя файла журнала транзакций используется формат штамп даты и времени, например, Verbose 6-1-2018 6 17 22 PM указывает файл, который был создан на 1 июня 2018 на 6:17:22 PM. подробный уровень ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="1f19a-p101">The Office 365 IdFix tool creates a new transaction log each time you click **Apply** in IdFix and apply changes to the Active Directory forest. The transaction log is saved in the same folder where you installed IdFix. By default, this folder is C:\Deployment Tools\IDFix. The transaction log file name uses a date and time stamp format, for example, Verbose 6-1-2018 6-17-22 PM indicates a file that was generated at June 1, 2018 at 6:17:22 PM. Verbose indicates the logging level.</span></span> 
  
## <a name="idfix-transaction-log-logging-level"></a><span data-ttu-id="1f19a-111">Уровень ведения журнала транзакций IdFix</span><span class="sxs-lookup"><span data-stu-id="1f19a-111">IdFix transaction log logging level</span></span>

<span data-ttu-id="1f19a-p102">Слово "verbose" в имени журнала транзакций указывает уровень ведения журнала. В данном случае записывается максимальное количество информации. Данный уровень ведения журнала является уровнем по умолчанию. В текущий момент уровень ведения журнала не изменятся.</span><span class="sxs-lookup"><span data-stu-id="1f19a-p102">The word verbose in the transaction log file name indicates the level of logging in the file. Verbose means that the maximum amount of information is captured in the log. This is the default logging level. At this time, you cannot change the logging level.</span></span>
  
## <a name="idfix-transaction-log-format"></a><span data-ttu-id="1f19a-116">Расположение журнала транзакций IdFix</span><span class="sxs-lookup"><span data-stu-id="1f19a-116">IdFix transaction log format</span></span>

<span data-ttu-id="1f19a-117">IdFix записывает результаты каждого действия **UPDATE** в журнал транзакций, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1f19a-117">IdFix writes the results of each **UPDATE** action to a transaction log as shown in the following example:</span></span>
  
```
5/22/2018 6:36:44 AM Initialized - IdFix version 1.07 - Multi-Tenant
5/22/2018 6:36:47 AM Query AD
5/22/2018 6:36:47 AM FOREST:e2k10.com SERVER:dc1.e2k10.com FILTER:(|(objectCategory=Person)(objectCategory=Group))
5/22/2018 6:36:47 AM Please wait while the LDAP Connection is established.
5/22/2018 6:36:49 AM Query Count: 140  Error Count: 29  Duplicate Check Count: 191
5/22/2018 6:36:49 AM Elapsed Time: AD Query - 00:00:02.3890432
5/22/2018 6:36:49 AM Write split files
5/22/2018 6:36:49 AM Merge split files
5/22/2018 6:36:49 AM Count duplicates
5/22/2018 6:36:49 AM Write filtered duplicate objects
5/22/2018 6:36:49 AM Read filtered duplicate objects
5/22/2018 6:36:49 AM Read error file
5/22/2018 6:36:49 AM Elapsed Time: Duplicate Checks - 00:00:00.0780785
5/22/2018 6:36:49 AM Populating DataGrid
5/22/2018 6:36:50 AM Elapsed Time: Populate DataGridView - 00:00:00.0780785
5/22/2018 6:36:50 AM Query Count: 140  Error Count: 53
5/22/2018 6:37:34 AM Apply Pending
5/22/2018 6:37:34 AM Update: [CN=user000001,OU=e2k10OU1,DC=e2k10,DC=com][user][mailnickname][character][user?^|000001][user000001][EDIT]
5/22/2018 6:37:34 AM Update: [CN=user000008,OU=e2k10OU1,DC=e2k10,DC=com][user][targetAddress][duplicate][smtp:user000008@customer.com][][REMOVE]
5/22/2018 6:37:34 AM COMPLETE
5/22/2018 6:37:40 AM Loading Updates
5/22/2018 6:37:40 AM Action Selection
5/22/2018 6:37:57 AM Apply Pending
5/22/2018 6:37:57 AM Update: [CN=user000001,OU=e2k10OU1,DC=e2k10,DC=com][user][mailnickname][character][user?^|000001][user000001][UNDO]
5/22/2018 6:37:57 AM Update: [CN=user000008,OU=e2k10OU1,DC=e2k10,DC=com][user][targetAddress][duplicate][smtp:user000008@customer.com][][UNDO]
5/22/2018 6:37:57 AM COMPLETE

```