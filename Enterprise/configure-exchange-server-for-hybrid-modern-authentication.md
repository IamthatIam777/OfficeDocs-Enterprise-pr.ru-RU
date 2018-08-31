---
title: Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 3/23/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
description: Гибридные современных проверки подлинности (НЕГО) — это метод управления удостоверениями, который обеспечивает более безопасной проверки подлинности пользователя и авторизации и доступна для гибридного развертывания Exchange server в локальной.
ms.openlocfilehash: 871f03b8e776c694f7378f6905259d21516f7326
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542459"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="233e1-103">Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="233e1-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="233e1-104">Гибридные современных проверки подлинности (НЕГО) — это метод управления удостоверениями, который обеспечивает более безопасной проверки подлинности пользователя и авторизации и доступна для гибридного развертывания Exchange server в локальной.</span><span class="sxs-lookup"><span data-stu-id="233e1-104">Hybrid Modern Authentication (HMA), is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>
  
## <a name="fyi"></a><span data-ttu-id="233e1-105">FYI</span><span class="sxs-lookup"><span data-stu-id="233e1-105">FYI</span></span>

<span data-ttu-id="233e1-106">Прежде чем начать, ли вызов:</span><span class="sxs-lookup"><span data-stu-id="233e1-106">Before we begin, I call:</span></span>
  
- <span data-ttu-id="233e1-107">Современный проверки подлинности гибридной \> НЕГО</span><span class="sxs-lookup"><span data-stu-id="233e1-107">Hybrid Modern Authentication \> HMA</span></span>
    
- <span data-ttu-id="233e1-108">Exchange в локальной \> EXCH</span><span class="sxs-lookup"><span data-stu-id="233e1-108">Exchange on-premises \> EXCH</span></span>
    
- <span data-ttu-id="233e1-109">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="233e1-109">Exchange Online \> EXO</span></span>
    
<span data-ttu-id="233e1-110">Кроме того, *Если графического элемента в этой статье есть объект, который «серым» или «неактивен», что означает, что элемент, приведенные в серый цвет не входит в НЕГО конфигурации* .</span><span class="sxs-lookup"><span data-stu-id="233e1-110">Also,  *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*  .</span></span> 
  
## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="233e1-111">Включение проверки подлинности гибридной современных</span><span class="sxs-lookup"><span data-stu-id="233e1-111">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="233e1-112">Для включения НЕГО означает, что:</span><span class="sxs-lookup"><span data-stu-id="233e1-112">Turning HMA on means:</span></span>
  
1. <span data-ttu-id="233e1-113">Необходимо выполнить проверка готовности, прежде чем приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="233e1-113">Being sure you meet the prereqs before you begin.</span></span>
    
1. <span data-ttu-id="233e1-p101">С момента множество **необходимых компонентов** являются общими для обоих Скайп для бизнеса и Exchange, [Обзор проверки подлинности гибридной современных и необходимые условия для использования с локальной Скайп для серверов Exchange и бизнес](hybrid-modern-auth-overview.md). Это необходимо сделать, прежде чем начать, какие-либо действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="233e1-p101">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md). Do this before you begin any of the steps in this article.</span></span>
    
2. <span data-ttu-id="233e1-116">Добавление локального URL-адреса служб web как имена участников-служб (SPN) в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="233e1-116">Adding on-premises web service URLs as Service Principal Names (SPNs) in Azure AD.</span></span>
    
3. <span data-ttu-id="233e1-117">Проверка всех виртуальных каталогов, включены для НЕГО</span><span class="sxs-lookup"><span data-stu-id="233e1-117">Ensuring all Virtual Directories are enabled for HMA</span></span>
    
4. <span data-ttu-id="233e1-118">Проверка для объекта EvoSTS проверкой подлинности на основе сервера</span><span class="sxs-lookup"><span data-stu-id="233e1-118">Checking for the EvoSTS Auth Server object</span></span>
    
5. <span data-ttu-id="233e1-119">Включение НЕГО в курс</span><span class="sxs-lookup"><span data-stu-id="233e1-119">Enabling HMA in EXCH.</span></span>
    
 <span data-ttu-id="233e1-p102">**Примечание** Поддерживает ли агент Управления вашей версии Office? В разделе [того, как современные выполняется проверка подлинности для Office 2013 и Office 2016 клиентских приложений](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="233e1-p102">**Note** Does your version of Office support MA? See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>
  
## <a name="make-sure-you-meet-all-the-pre-reqs"></a><span data-ttu-id="233e1-122">Убедитесь, что выполнены все предварительные условия</span><span class="sxs-lookup"><span data-stu-id="233e1-122">Make sure you meet all the pre-reqs</span></span>

<span data-ttu-id="233e1-p103">Поскольку множество необходимых компонентов являются общими для обоих Скайп для бизнеса и Exchange, просмотрите [Обзор проверки подлинности гибридной современных и необходимые условия для использования с Скайп локальных серверов Exchange и бизнес](hybrid-modern-auth-overview.md). Сделать этот *перед* началом работы какие-либо действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="233e1-p103">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md). Do this  *before*  you begin any of the steps in this article.</span></span> 
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="233e1-125">Добавление локального веб-службы URL-адреса как имена участников-служб в Azure AD</span><span class="sxs-lookup"><span data-stu-id="233e1-125">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="233e1-p104">Запуск команды, которые присвоить локального веб-службы URL-адреса, как имена участников-служб Azure AD. имена участников-служб используются с клиентских компьютеров и устройств во время проверки подлинности и авторизации. Все URL-адреса, которые могут использоваться для подключения через локальную для Azure Active Directory (AAD) должны быть зарегистрированы в AAD (включая внутренних и внешних пространств имен).</span><span class="sxs-lookup"><span data-stu-id="233e1-p104">Run the commands that assign your on-premises web service URLs as Azure AD SPNs. SPNs are used by client machines and devices during authentication and authorization. All the URLs that might be used to connect from on-premises to Azure Active Directory (AAD) must be registered in AAD (this includes both internal and external namespaces).</span></span>
  
<span data-ttu-id="233e1-p105">Во-первых необходимо Соберите все URL-адреса, которые необходимо добавить в AAD. Выполните следующие команды в локальной:</span><span class="sxs-lookup"><span data-stu-id="233e1-p105">First, gather all the URLs that you need to add in AAD. Run these commands on-premises:</span></span>
  
- <span data-ttu-id="233e1-131">Get-MapiVirtualDirectory | Сервер FL\*URL-адрес\*</span><span class="sxs-lookup"><span data-stu-id="233e1-131">Get-MapiVirtualDirectory | FL server,\*url\*</span></span>
    
- <span data-ttu-id="233e1-132">Get-WebServicesVirtualDirectory | Сервер FL\*URL-адрес\*</span><span class="sxs-lookup"><span data-stu-id="233e1-132">Get-WebServicesVirtualDirectory | FL server,\*url\*</span></span>
    
- <span data-ttu-id="233e1-133">**Get-ActiveSyncVirtualDirectory | Сервер FL\*URL-адрес\***</span><span class="sxs-lookup"><span data-stu-id="233e1-133">**Get-ActiveSyncVirtualDirectory | FL server,\*url\***</span></span>
    
- <span data-ttu-id="233e1-134">Get-OABVirtualDirectory | Сервер FL\*URL-адрес\*</span><span class="sxs-lookup"><span data-stu-id="233e1-134">Get-OABVirtualDirectory | FL server,\*url\*</span></span>
    
<span data-ttu-id="233e1-135">Проверьте URL-адреса, клиенты могут подключаться к присутствовала HTTPS имена участников-служб в AAD.</span><span class="sxs-lookup"><span data-stu-id="233e1-135">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>
  
1. <span data-ttu-id="233e1-136">Во-первых подключение к AAD с [этим инструкциям](https://docs.microsoft.com/en-us/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="233e1-136">First, connect to AAD with [these instructions](https://docs.microsoft.com/en-us/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>
    
2. <span data-ttu-id="233e1-137">Для обмена связанные URL-адреса, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="233e1-137">For your Exchange related URLs, type the following command:</span></span>
    
- <span data-ttu-id="233e1-138">Get-MsolServicePrincipal - AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | Выберите - ExpandProperty ServicePrincipalNames</span><span class="sxs-lookup"><span data-stu-id="233e1-138">Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames</span></span>
    
<span data-ttu-id="233e1-p106">Принимать сообщения с (и снимок экрана для дальнейшего сравнения) выходных данных, эта команда, должен включать https:// * службы автообнаружения. .com *имя_домена* * и URL-адрес https:// *mail.yourdomain.com* , но в основном состоят из имен участников-служб, начинающихся с 00000002-0000-0ff1-ce00-000000000000 /. При наличии https:// URL-адресов из своей локальной, которые не указаны необходимо добавить записи, определенные в этот список.</span><span class="sxs-lookup"><span data-stu-id="233e1-p106">Take note of (and screenshot for later comparison) the output of this command, which should include an https:// *autodiscover. *yourdomain*  .com *  and https://  *mail.yourdomain.com*  URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/. If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span> 
  
3. <span data-ttu-id="233e1-142">Если своих внутренних и внешних MAPI/HTTP, веб-служб Exchange, ActiveSync, автономной адресной книги и автоматического обнаружения записей в этом списке не отображается, необходимо добавить их с помощью приведенной ниже команды (примере используются URL-адреса "`mail.corp.contoso.com`«и»`owa.contoso.com`", но было **Заменить примеры URL-адресов с помощью собственного** ) :</span><span class="sxs-lookup"><span data-stu-id="233e1-142">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span> </br>
```
- $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000   
- $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
- $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
- $x.ServicePrincipalnames.Add("https://eas.contoso.com/")
- Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
 
4. <span data-ttu-id="233e1-p107">Убедитесь, что были добавлены новые записи, выполнив команду Get-MsolServicePrincipal на шаге 2 еще раз и просмотр выходных данных. Сравните список / снимок экрана с перед новый список имен участников-служб (можно также снимок экрана нового списка для записи). Если вы было выполнено успешно, вы увидите две новые URL-адресов в списке. Переход в нашем примере список имен участников-служб будут включать конкретные URL-адреса `https://mail.corp.contoso.com` и `https://owa.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="233e1-p107">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output. Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records). If you were successful, you will see the two new URLs in the list. Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span> 
  
## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="233e1-147">Убедитесь, что правильно настроить виртуальные каталоги</span><span class="sxs-lookup"><span data-stu-id="233e1-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="233e1-148">Теперь проверьте OAuth должным образом включены в Exchange на всех виртуальных каталогов Outlook может использовать, выполнив следующие команды:</span><span class="sxs-lookup"><span data-stu-id="233e1-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```
Get-MapiVirtualDirectory | FL server,\*url\*,\*auth\* 
Get-WebServicesVirtualDirectory | FL server,\*url\*,\*oauth\*
Get-OABVirtualDirectory | FL server,\*url\*,\*oauth\*
Get-AutoDiscoverVirtualDirectory | FL server,\*oauth\*
```

<span data-ttu-id="233e1-149">Проверка выходные данные в убедитесь в том, **OAuth** включен на каждом из этих VDirs, он будет выглядеть примерно следующим образом (и всего рассмотрение является «OAuth»);</span><span class="sxs-lookup"><span data-stu-id="233e1-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth');</span></span> 
  
 <span data-ttu-id="233e1-150">**[PS] C:\Windows\system32\>Get-MapiVirtualDirectory | сервер fl\*URL-адрес\*,\*проверки подлинности\***</span><span class="sxs-lookup"><span data-stu-id="233e1-150">**[PS] C:\Windows\system32\>Get-MapiVirtualDirectory | fl server,\*url\*,\*auth\***</span></span>
  
 <span data-ttu-id="233e1-151">**Сервер: EX1**</span><span class="sxs-lookup"><span data-stu-id="233e1-151">**Server : EX1**</span></span>
  
 <span data-ttu-id="233e1-152">**InternalUrl:`https://mail.contoso.com/mapi`**</span><span class="sxs-lookup"><span data-stu-id="233e1-152">**InternalUrl : `https://mail.contoso.com/mapi`**</span></span>
  
 <span data-ttu-id="233e1-153">**ExternalUrl:`https://mail.contoso.com/mapi`**</span><span class="sxs-lookup"><span data-stu-id="233e1-153">**ExternalUrl : `https://mail.contoso.com/mapi`**</span></span>
  
 <span data-ttu-id="233e1-154">**IISAuthenticationMethods: {Ntlm, OAuth, согласование}**</span><span class="sxs-lookup"><span data-stu-id="233e1-154">**IISAuthenticationMethods : {Ntlm, OAuth, Negotiate}**</span></span>
  
 <span data-ttu-id="233e1-155">**InternalAuthenticationMethods: {Ntlm, OAuth, согласование}**</span><span class="sxs-lookup"><span data-stu-id="233e1-155">**InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}**</span></span>
  
 <span data-ttu-id="233e1-156">**ExternalAuthenticationMethods: {Ntlm, OAuth, согласование}**</span><span class="sxs-lookup"><span data-stu-id="233e1-156">**ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}**</span></span>
  
<span data-ttu-id="233e1-157">Если отсутствует OAuth с любого сервера и любой из четырех виртуальных каталогов необходимо добавить его с помощью нужных команд перед тем как перейти.</span><span class="sxs-lookup"><span data-stu-id="233e1-157">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding.</span></span>
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="233e1-158">Убедитесь, что отображается объект EvoSTS проверкой подлинности на основе сервера</span><span class="sxs-lookup"><span data-stu-id="233e1-158">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="233e1-p108">Вернуться к локальной Командная консоль Exchange для этой команды последнего. Теперь можно проверить, что локальную имеется запись evoSTS поставщика проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="233e1-p108">Return to the on-premises Exchange Management Shell for this last command. Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>
  
`Get-AuthServer | where {$_.Name -eq "EvoSts"}`
    
<span data-ttu-id="233e1-p109">Выходные данные должны быть показаны AuthServer EvoSts имя и состояние «Включено» должно быть значение True. Если это не отображается, следует Загрузите и запустите последнюю версию мастера гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="233e1-p109">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True. If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>
  
 <span data-ttu-id="233e1-163">**Важные** Если вы используете Exchange 2010 в вашей среде, не создается поставщик проверки подлинности EvoSTS.</span><span class="sxs-lookup"><span data-stu-id="233e1-163">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span> 
  
## <a name="enable-hma"></a><span data-ttu-id="233e1-164">Включите в НЕГО</span><span class="sxs-lookup"><span data-stu-id="233e1-164">Enable HMA</span></span>

<span data-ttu-id="233e1-165">Выполните следующую команду в командной консоли Exchange, в локальной:</span><span class="sxs-lookup"><span data-stu-id="233e1-165">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```
    
## <a name="verify"></a><span data-ttu-id="233e1-166">"Проверить"</span><span class="sxs-lookup"><span data-stu-id="233e1-166">Verify</span></span>

<span data-ttu-id="233e1-p110">После включения НЕГО клиента следующем входе в систему будет использовать новый поток проверки подлинности. Обратите внимание на то, что только что включение НЕГО не запустит повторная проверка подлинности для любого клиента. Клиенты повторно пройти проверку подлинности на основе времени жизни проверкой подлинности на основе маркеров и/или сертификаты у них.</span><span class="sxs-lookup"><span data-stu-id="233e1-p110">Once you enable HMA, a client's next login will use the new auth flow. Note that just turning on HMA won't trigger a re-authentication for any client. The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="233e1-p111">Также следует удерживайте нажатой клавишу CTRL, в то же время, щелкните значок правой кнопкой мыши для клиентов Outlook (а также в области уведомлений Windows) и нажмите кнопку «Состояние подключения». Найдите SMTP-адрес клиента с типом «Определения» "носителя\*", который представляет маркер носителя, используемый в OAuth.</span><span class="sxs-lookup"><span data-stu-id="233e1-p111">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'. Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
 <span data-ttu-id="233e1-p112">**Примечание** Необходимо настроить Скайп для бизнеса с НЕГО? Вам потребуются две статьи:, в котором приведены [Поддерживаемые топологии](https://technet.microsoft.com/en-us/library/mt803262.aspx)и показано, [как для выполнения конфигурации](configure-skype-for-business-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="233e1-p112">**Note** Need to configure Skype for Business with HMA? You'll need two articles: One that lists [supported topologies](https://technet.microsoft.com/en-us/library/mt803262.aspx), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="233e1-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="233e1-174">Related topics</span></span>

[<span data-ttu-id="233e1-175">Обзор проверки подлинности на современном гибридной среды и необходимые условия для использования его с Скайп локальных серверов Exchange и бизнес-</span><span class="sxs-lookup"><span data-stu-id="233e1-175">Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers</span></span>](hybrid-modern-auth-overview.md) 
  
