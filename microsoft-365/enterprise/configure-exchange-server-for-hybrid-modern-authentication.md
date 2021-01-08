---
title: 如何配置本地 Exchange Server 以使用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 了解如何在本地配置 Exchange Server 以使用混合新式验证 (HMA) ，为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780280"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="f849d-103">如何配置本地 Exchange Server 以使用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="f849d-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="f849d-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="f849d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f849d-105">混合新式 (HMA) 是一种标识管理方法，可提供更安全的用户身份验证和授权，并且可用于 Exchange 服务器本地混合部署。</span><span class="sxs-lookup"><span data-stu-id="f849d-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="f849d-106">FYI</span><span class="sxs-lookup"><span data-stu-id="f849d-106">FYI</span></span>

<span data-ttu-id="f849d-107">在开始之前，我调用：</span><span class="sxs-lookup"><span data-stu-id="f849d-107">Before we begin, I call:</span></span>

- <span data-ttu-id="f849d-108">混合新式验证 \> HMA</span><span class="sxs-lookup"><span data-stu-id="f849d-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="f849d-109">Exchange 本地 \> EXCH</span><span class="sxs-lookup"><span data-stu-id="f849d-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="f849d-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="f849d-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="f849d-111">此外，如果本文中的图形有一个"灰显"或"灰显"的对象，则意味着以灰色显示的元素不包含在 *HMA 特定的配置中*。</span><span class="sxs-lookup"><span data-stu-id="f849d-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="f849d-112">启用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="f849d-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="f849d-113">打开 HMA 意味着：</span><span class="sxs-lookup"><span data-stu-id="f849d-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="f849d-114">确保在开始之前满足预先要求。</span><span class="sxs-lookup"><span data-stu-id="f849d-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="f849d-115">由于 **Skype** for Business 和 Exchange 都常见许多先决条件，混合新式验证概述以及将混合新式验证与本地 [Skype for Business](hybrid-modern-auth-overview.md)和 Exchange 服务器一同使用的先决条件。</span><span class="sxs-lookup"><span data-stu-id="f849d-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="f849d-116">在开始本文中的任一步骤之前，应执行上述操作。</span><span class="sxs-lookup"><span data-stu-id="f849d-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="f849d-117">将本地 Web 服务 URL 添加为 Azure AD (**SSP**) 服务主体名称。</span><span class="sxs-lookup"><span data-stu-id="f849d-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="f849d-118">确保为 HMA 启用所有虚拟目录</span><span class="sxs-lookup"><span data-stu-id="f849d-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="f849d-119">检查 EvoSTS Auth Server 对象</span><span class="sxs-lookup"><span data-stu-id="f849d-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="f849d-120">在 EXCH 中启用 HMA。</span><span class="sxs-lookup"><span data-stu-id="f849d-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="f849d-121">**注意** Office 版本是否支持 MA？</span><span class="sxs-lookup"><span data-stu-id="f849d-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="f849d-122">请参阅 [新式验证如何适用于 Office 2013 和 Office 2016 客户端应用](modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="f849d-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="f849d-123">确保满足所有先决条件</span><span class="sxs-lookup"><span data-stu-id="f849d-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="f849d-124">由于 Skype for Business 和 Exchange 都常见许多先决条件，请查看混合新式验证概述以及将混合新式验证与本地 [Skype for Business](hybrid-modern-auth-overview.md)和 Exchange 服务器一同使用的先决条件。</span><span class="sxs-lookup"><span data-stu-id="f849d-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="f849d-125">在开始  *本文中的*  任一步骤之前，应执行上述操作。</span><span class="sxs-lookup"><span data-stu-id="f849d-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="f849d-126">在 Azure AD 中添加本地 Web 服务 URL 作为 SNS</span><span class="sxs-lookup"><span data-stu-id="f849d-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="f849d-127">运行将本地 Web 服务 URL 分配为 Azure AD SNS 的命令。</span><span class="sxs-lookup"><span data-stu-id="f849d-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="f849d-128">SNS 在身份验证和授权期间由客户端计算机和设备使用。</span><span class="sxs-lookup"><span data-stu-id="f849d-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="f849d-129">可能用于从本地连接到 Azure Active Directory (Azure AD) 的所有 URL 都必须在 Azure AD (这包括内部和外部命名空间) 。</span><span class="sxs-lookup"><span data-stu-id="f849d-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="f849d-130">首先，收集需要在 AAD 中添加的所有 URL。</span><span class="sxs-lookup"><span data-stu-id="f849d-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="f849d-131">在本地运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f849d-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="f849d-132">确保 URL 客户端可能连接到的 URL 在 AAD 中列为 HTTPS 服务主体名称。</span><span class="sxs-lookup"><span data-stu-id="f849d-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="f849d-133">首先，使用这些 [说明连接到](connect-to-microsoft-365-powershell.md)AAD。</span><span class="sxs-lookup"><span data-stu-id="f849d-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="f849d-134">**注意** 您需要使用此页面中的 _Connect-MsolService_ 选项才能使用下面的命令。</span><span class="sxs-lookup"><span data-stu-id="f849d-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="f849d-135">对于与 Exchange 相关的 URL，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f849d-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="f849d-136">记下 (和屏幕截图，用于稍后比较) 此命令的输出，该命令应包含 https://  *autodiscover.yourdomain.com*  和 https://  *mail.yourdomain.com* URL，但主要包括以 000000002-0000-0ff1-ce00-0000000000000/开头的 SSP。</span><span class="sxs-lookup"><span data-stu-id="f849d-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="f849d-137">如果本地https:// URL 缺失，我们需要将这些特定记录添加到此列表。</span><span class="sxs-lookup"><span data-stu-id="f849d-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="f849d-138">如果在此列表中看不到内部和外部 MAPI/HTTP、EWS、ActiveSync、OAB 和自动发现记录，则必须使用下面的命令添加它们 (示例 URL 为 `mail.corp.contoso.com` ""和 `owa.contoso.com` ""，但需要将示例 URL 替换为您自己的) ：</span><span class="sxs-lookup"><span data-stu-id="f849d-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="f849d-139">通过再次运行步骤 2 中的 Get-MsolServicePrincipal 命令并查看输出，验证是否添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="f849d-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="f849d-140">将之前的列表/屏幕截图与新的 SNS 列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="f849d-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="f849d-141">您还可以为记录拍摄新列表的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="f849d-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="f849d-142">如果成功，你将在列表中看到两个新 URL。</span><span class="sxs-lookup"><span data-stu-id="f849d-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="f849d-143">以我们的示例为例，SNS 列表现在将包括特定的 URL 和  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="f849d-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="f849d-144">验证虚拟目录是否正确配置</span><span class="sxs-lookup"><span data-stu-id="f849d-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="f849d-145">现在，通过运行以下命令，验证 Outlook 可能使用的所有虚拟目录的 Exchange 中是否正确启用了 OAuth：</span><span class="sxs-lookup"><span data-stu-id="f849d-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="f849d-146">检查输出以确保在这些 VDirs 中每个 VDirs 上都启用了 **OAuth，** 它看起来如下所示 (关键内容是"OAuth") ：</span><span class="sxs-lookup"><span data-stu-id="f849d-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="f849d-147">如果任何服务器和四个虚拟目录中的任一虚拟目录中缺少 OAuth，则需要在继续 (Set-MapiVirtualDirectory、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory 和[](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory)[](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory)[Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)) 之前，使用相关命令添加 OAuth。 [](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="f849d-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="f849d-148">确认 EvoSTS 身份验证服务器对象存在</span><span class="sxs-lookup"><span data-stu-id="f849d-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="f849d-149">返回最后一个命令的本地 Exchange 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="f849d-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="f849d-150">现在，您可以验证您的本地是否具有 evoSTS 身份验证提供程序的条目：</span><span class="sxs-lookup"><span data-stu-id="f849d-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="f849d-151">输出应显示名称 EvoSts 的 AuthServer，并且"已启用"状态应为 True。</span><span class="sxs-lookup"><span data-stu-id="f849d-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="f849d-152">如果未看到此内容，应下载并运行最新版本的混合配置向导。</span><span class="sxs-lookup"><span data-stu-id="f849d-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="f849d-153">**重要** 如果在环境中运行 Exchange 2010，将不会创建 EvoSTS 身份验证提供程序。</span><span class="sxs-lookup"><span data-stu-id="f849d-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="f849d-154">启用 HMA</span><span class="sxs-lookup"><span data-stu-id="f849d-154">Enable HMA</span></span>

<span data-ttu-id="f849d-155">在本地 Exchange 命令行管理程序 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f849d-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="f849d-156">验证</span><span class="sxs-lookup"><span data-stu-id="f849d-156">Verify</span></span>

<span data-ttu-id="f849d-157">启用 HMA 后，客户端的下一个登录名将使用新的身份验证流。</span><span class="sxs-lookup"><span data-stu-id="f849d-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="f849d-158">请注意，仅打开 HMA 不会触发任何客户端的重新身份验证。</span><span class="sxs-lookup"><span data-stu-id="f849d-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="f849d-159">客户端根据其拥有身份验证令牌和/或证书的生存期重新进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f849d-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="f849d-160">在右键单击 Outlook 客户端图标的同时，还应按住 Ctrl 键 (Windows 通知任务栏) 然后单击"连接状态"。</span><span class="sxs-lookup"><span data-stu-id="f849d-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="f849d-161">针对"Bearer"类型的"Authn"类型查找客户端的 SMTP 地址，该类型表示 OAuth 中使用的记 \* 名令牌。</span><span class="sxs-lookup"><span data-stu-id="f849d-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="f849d-162">**注意** 需要配置具有 HMA 的 Skype for Business？</span><span class="sxs-lookup"><span data-stu-id="f849d-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="f849d-163">你将需要两篇文章：一 [篇文章列出支持的](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)拓扑，另一篇文章演示如何 [执行配置](configure-skype-for-business-for-hybrid-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="f849d-163">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="f849d-164">将混合新式验证用于 Outlook for iOS 和 Outlook for Android</span><span class="sxs-lookup"><span data-stu-id="f849d-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="f849d-165">如果您是使用 TCP 443 上的 Exchange 服务器本地客户，请绕过以下 IP 范围的流量处理：</span><span class="sxs-lookup"><span data-stu-id="f849d-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="f849d-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="f849d-166">Related topics</span></span>

[<span data-ttu-id="f849d-167">从 Office 365 专用/ITAR 转换到 vNext 的新式验证配置要求</span><span class="sxs-lookup"><span data-stu-id="f849d-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
