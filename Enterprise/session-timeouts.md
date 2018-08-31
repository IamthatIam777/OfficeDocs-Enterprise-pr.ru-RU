---
title: Время ожидания сеанса для Office 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
description: Время ожидания сеанса используются сбалансировать прав и специальных возможностей в клиентских приложениях Office 365.
ms.openlocfilehash: dda13f280149c969354ae1f0eac336f1d8ed23e7
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542429"
---
# <a name="session-timeouts-for-office-365"></a><span data-ttu-id="9e170-103">Время ожидания сеанса для Office 365</span><span class="sxs-lookup"><span data-stu-id="9e170-103">Session timeouts for Office 365</span></span>

<span data-ttu-id="9e170-104">Время жизни сеанса являются важной частью проверки подлинности для Office 365 и являются важным компонентом балансировки безопасности и количество отправок пользователю предлагается ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="9e170-104">Session lifetimes are an important part of authentication for Office 365 and are an important component in balancing security and the number of times users are prompted for their credentials.</span></span>
  
## <a name="session-times-for-office-365-services"></a><span data-ttu-id="9e170-105">Продолжительность сеанса для службы Office 365</span><span class="sxs-lookup"><span data-stu-id="9e170-105">Session times for Office 365 services</span></span>

<span data-ttu-id="9e170-p101">После проверки подлинности пользователей в любом Office 365 веб-приложений и мобильных приложений, устанавливается сеанс. На протяжении сеанса пользователям не нужно выполнять проверку подлинности повторно. Срок действия сеансов можно при пользователей неактивными, при закрытии браузера или tab или истечения срока действия их маркера проверки подлинности по другим причинам, например, когда выполнен сброс пароля. Службы Office 365 имеют время ожидания сеанса различных в соответствии с обычной работы каждой службы.</span><span class="sxs-lookup"><span data-stu-id="9e170-p101">When users authenticate in any of the Office 365 web apps or mobile apps, a session is established. For the duration of the session, users won't need to re-authenticate. Sessions can expire when users are inactive, when they close the browser or tab, or when their authentication token expires for other reasons such as when their password has been reset. The Office 365 services have different session timeouts to correspond with the typical use of each service.</span></span>
  
<span data-ttu-id="9e170-110">В следующей таблице приведены времени жизни сеанса для службы Office 365:</span><span class="sxs-lookup"><span data-stu-id="9e170-110">The following table lists the session lifetimes for Office 365 services:</span></span>
  
|<span data-ttu-id="9e170-111">**Служба Office 365**</span><span class="sxs-lookup"><span data-stu-id="9e170-111">**Office 365 service**</span></span>|<span data-ttu-id="9e170-112">**Время ожидания сеанса**</span><span class="sxs-lookup"><span data-stu-id="9e170-112">**Session timeout**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e170-113">Центр администрирования Office 365</span><span class="sxs-lookup"><span data-stu-id="9e170-113">Office 365 Admin center</span></span>  <br/> |<span data-ttu-id="9e170-114">Будет предложено ввести учетные данные по центру администрирования каждые 8 часов.</span><span class="sxs-lookup"><span data-stu-id="9e170-114">You are asked to provide credentials for the admin center every 8 hours.</span></span>  <br/> |
|<span data-ttu-id="9e170-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9e170-115">SharePoint Online</span></span>  <br/> |<span data-ttu-id="9e170-p102">5 дней простоя в течение пользователей выбирает **оставаться в системе**. Если пользователь получает доступ к SharePoint Online еще раз после выполнения из предыдущих входа в 24 или более часов, значения времени ожидания сбрасывается до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="9e170-p102">5 days of inactivity as long as the users chooses **Keep me signed in**. If the user accesses SharePoint Online again after 24 or more hours have passed from the previous sign-in, the timeout value is reset to 5 days.  </span></span><br/> |
|<span data-ttu-id="9e170-118">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="9e170-118">Outlook Web App</span></span>  <br/> |<span data-ttu-id="9e170-119">6 часов.</span><span class="sxs-lookup"><span data-stu-id="9e170-119">6 hours.</span></span>  <br/> <span data-ttu-id="9e170-120">Это значение можно изменить с помощью параметра _ActivityBasedAuthenticationTimeoutInterval_ в командлет [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) .</span><span class="sxs-lookup"><span data-stu-id="9e170-120">You can change this value by using the  _ActivityBasedAuthenticationTimeoutInterval_ parameter in the [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) cmdlet.</span></span>  <br/> |
|<span data-ttu-id="9e170-121">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9e170-121">Azure Active Directory</span></span>  <br/> <span data-ttu-id="9e170-122">(Используется клиентами Office 2013 Windows с поддержкой современных проверки подлинности)</span><span class="sxs-lookup"><span data-stu-id="9e170-122">(Used by Office 2013 Windows clients with modern authentication enabled)</span></span>  <br/> | <span data-ttu-id="9e170-p103">Современный проверки подлинности использует маркеры доступа и обновление маркеров для предоставления доступа пользователей к ресурсам Office 365 с помощью Azure Active Directory. Маркер доступа JSON Web маркер предоставляются после успешной проверки подлинности и действительны в течение часа. Кроме того, обеспечивается маркер обновления с значительно больше времени жизни. По истечении маркеры доступа клиентов Office использовать маркер допустимый обновления для получения новый маркер доступа. В этом exchange завершается успешно, если допустима Начальная проверка подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e170-p103">Modern authentication uses access tokens and refresh tokens to grant user access to Office 365 resources using Azure Active Directory. An access token is a JSON Web Token provided after a successful authentication and is valid for 1 hour. A refresh token with a longer lifetime is also provided. When access tokens expire, Office clients use a valid refresh token to obtain a new access token. This exchange succeeds if the user's initial authentication is still valid.</span></span>  <br/>  <span data-ttu-id="9e170-128">Маркеры обновления действительны в течение 90 дней, и с непрерывной работы может быть допустимым, пока не отозваны.</span><span class="sxs-lookup"><span data-stu-id="9e170-128">Refresh tokens are valid for 90 days, and with continuous use, they can be valid until revoked.</span></span>  <br/>  <span data-ttu-id="9e170-129">Обновление маркеров может стать недействительным несколькими событиями, например:</span><span class="sxs-lookup"><span data-stu-id="9e170-129">Refresh tokens can be invalidated by several events such as :</span></span>  <br/>  <span data-ttu-id="9e170-130">Пароль пользователя был изменен с момента выпуска маркера обновления.</span><span class="sxs-lookup"><span data-stu-id="9e170-130">User's password has changed since the refresh token was issued.</span></span>  <br/>  <span data-ttu-id="9e170-131">Администратор может применить политики условного доступа, которые ограничить доступ к ресурс, который пользователь пытается получить доступ к.</span><span class="sxs-lookup"><span data-stu-id="9e170-131">An administrator can apply conditional access policies which restrict access to the resource the user is trying to access.</span></span>  <br/> |
|<span data-ttu-id="9e170-132">SharePoint и OneDrive мобильных приложений для Android, iOS и Windows 10</span><span class="sxs-lookup"><span data-stu-id="9e170-132">SharePoint and OneDrive mobile apps for Android, iOS, and Windows 10</span></span>  <br/> |<span data-ttu-id="9e170-p104">По умолчанию времени жизни маркера доступа — 1 час. Max неактивных время маркер обновления по умолчанию — 90 дней.</span><span class="sxs-lookup"><span data-stu-id="9e170-p104">The default lifetime for the access token is 1 hour. The default max inactive time of the refresh token is 90 days.  </span></span><br/> [<span data-ttu-id="9e170-135">Дополнительные сведения о маркеры и способы настройки времени жизни маркера</span><span class="sxs-lookup"><span data-stu-id="9e170-135">Learn more about tokens and how to configure token lifetimes</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> <span data-ttu-id="9e170-136">Чтобы отозвать обновление маркеров, вы может сбросить пароль пользователя Office 365</span><span class="sxs-lookup"><span data-stu-id="9e170-136">To revoke the refresh token, you can reset the user's Office 365 password</span></span>  <br/> |
|<span data-ttu-id="9e170-137">Yammer с входа в Office 365</span><span class="sxs-lookup"><span data-stu-id="9e170-137">Yammer with Office 365 Sign-In</span></span>  <br/> |<span data-ttu-id="9e170-p105">Время жизни браузера. Если пользователи закройте окно браузера и доступ к сети Yammer в новом окне, Yammer будет повторно выполнять проверку подлинности их с помощью Office 365. Если пользователи используют сторонних браузерах, файлы cookie для кэша, они не требуется повторное проверки подлинности, когда они снова откройте браузер.</span><span class="sxs-lookup"><span data-stu-id="9e170-p105">Lifetime of the browser. If users close the browser and access Yammer in a new browser, Yammer will re-authenticate them with Office 365. If users use third-party browsers that cache cookies, they may not need to re-authenticate when they reopen the browser.  </span></span><br/> <span data-ttu-id="9e170-141">> [!NOTE]> Это допустимо только для сетей, использующих Office 365 входа в сети Yammer.</span><span class="sxs-lookup"><span data-stu-id="9e170-141">> [!NOTE]> This is valid only for networks using Office 365 Sign-In for Yammer.</span></span>           |
   
