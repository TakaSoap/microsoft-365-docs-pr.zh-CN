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
description: 了解如何在本地配置Exchange Server使用混合新式验证 (HMA) ，以为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cb6d25a346ac48c9875a26f385cb733f1ff051f
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259447"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="292fb-103">如何配置本地 Exchange Server 以使用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="292fb-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="292fb-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="292fb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="292fb-105">混合新式 (HMA) 是一种标识管理方法，可提供更安全的用户身份验证和授权，并且可用于 Exchange 服务器本地混合部署。</span><span class="sxs-lookup"><span data-stu-id="292fb-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="292fb-106">FYI</span><span class="sxs-lookup"><span data-stu-id="292fb-106">FYI</span></span>

<span data-ttu-id="292fb-107">在开始之前，我调用：</span><span class="sxs-lookup"><span data-stu-id="292fb-107">Before we begin, I call:</span></span>

- <span data-ttu-id="292fb-108">混合新式验证 \> HMA</span><span class="sxs-lookup"><span data-stu-id="292fb-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="292fb-109">Exchange本地 \> EXCH</span><span class="sxs-lookup"><span data-stu-id="292fb-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="292fb-110">\>Exchange OnlineEXO</span><span class="sxs-lookup"><span data-stu-id="292fb-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="292fb-111">此外，如果本文中的图形有一个"灰显"或"灰显"的对象，则意味着以灰色显示的元素不包含在 *HMA 特定的配置中*。</span><span class="sxs-lookup"><span data-stu-id="292fb-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="292fb-112">启用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="292fb-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="292fb-113">打开 HMA 意味着：</span><span class="sxs-lookup"><span data-stu-id="292fb-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="292fb-114">确保在开始之前满足预先要求。</span><span class="sxs-lookup"><span data-stu-id="292fb-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="292fb-115">由于 **许多先决条件** 对 Skype for Business 和 Exchange 都很常见，因此混合新式验证概述以及将混合新式验证与本地 Skype for Business 和 Exchange [服务器一同使用的先决条件](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="292fb-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="292fb-116">在开始执行本文中的任一步骤之前，先执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="292fb-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="292fb-117">将本地 Web 服务 URL 添加为 Azure AD (**SNS**) 服务主体名称。</span><span class="sxs-lookup"><span data-stu-id="292fb-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="292fb-118">如果 EXCH 与多个租户混合使用，必须将这些本地 Web 服务 URL 添加为与 EXCH 混合的所有租户的 Azure AD 中的 SNS。</span><span class="sxs-lookup"><span data-stu-id="292fb-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="292fb-119">确保为 HMA 启用所有虚拟目录</span><span class="sxs-lookup"><span data-stu-id="292fb-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="292fb-120">检查 EvoSTS Auth Server 对象</span><span class="sxs-lookup"><span data-stu-id="292fb-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="292fb-121">在 EXCH 中启用 HMA。</span><span class="sxs-lookup"><span data-stu-id="292fb-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="292fb-122">你的版本是否Office MA？</span><span class="sxs-lookup"><span data-stu-id="292fb-122">Does your version of Office support MA?</span></span> <span data-ttu-id="292fb-123">请参阅[新式验证如何适用于 Office 2013 和 Office 2016 客户端应用](modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="292fb-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="292fb-124">确保满足所有先决条件</span><span class="sxs-lookup"><span data-stu-id="292fb-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="292fb-125">由于许多先决条件对于 Skype for Business 和 Exchange 都很常见，请查看混合新式验证概述和用于本地 Skype for Business 和 Exchange[服务器的先决条件](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="292fb-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="292fb-126">在开始  *执行本文*  中的任一步骤之前，先执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="292fb-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="292fb-127">Outlook Web App Exchange控制面板不能用于混合新式验证。</span><span class="sxs-lookup"><span data-stu-id="292fb-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="292fb-128">将本地 Web 服务 URL 添加为 Azure AD 中的 SNS</span><span class="sxs-lookup"><span data-stu-id="292fb-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="292fb-129">运行将本地 Web 服务 URL 分配为 Azure AD SNS 的命令。</span><span class="sxs-lookup"><span data-stu-id="292fb-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="292fb-130">SNS 在身份验证和授权期间由客户端计算机和设备使用。</span><span class="sxs-lookup"><span data-stu-id="292fb-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="292fb-131">所有可用于从本地连接到 Azure Active Directory (Azure AD) 的 URL 都必须在 Azure AD (这包括内部和外部命名空间) 。</span><span class="sxs-lookup"><span data-stu-id="292fb-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="292fb-132">首先，收集需要在 AAD 中添加的所有 URL。</span><span class="sxs-lookup"><span data-stu-id="292fb-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="292fb-133">在本地运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="292fb-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="292fb-134">确保连接到的 URL 客户端在 AAD 中列为 HTTPS 服务主体名称。</span><span class="sxs-lookup"><span data-stu-id="292fb-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="292fb-135">如果 EXCH 与多个租户混合，这些 HTTPS S PIN 应添加到与 EXCH 混合的所有租户的 AAD 中。</span><span class="sxs-lookup"><span data-stu-id="292fb-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="292fb-136">首先，使用这些 [说明连接到](connect-to-microsoft-365-powershell.md)AAD。</span><span class="sxs-lookup"><span data-stu-id="292fb-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="292fb-137">您需要使用此页中的 _连接-MsolService_ 选项才能使用下面的命令。</span><span class="sxs-lookup"><span data-stu-id="292fb-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="292fb-138">对于Exchange URL，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="292fb-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="292fb-139">记下 (和屏幕截图，用于稍后比较) 此命令的输出，该命令应包含 https://  *autodiscover.yourdomain.com*  和 https://  *mail.yourdomain.com* URL，但主要包括以 000000002-0000-0ff1-ce00-0000000000000/ 开头的 SPA。</span><span class="sxs-lookup"><span data-stu-id="292fb-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="292fb-140">如果本地 https:// URL 缺失，我们将需要向此列表添加这些特定记录。</span><span class="sxs-lookup"><span data-stu-id="292fb-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="292fb-141">如果在此列表中看不到内部和外部 MAPI/HTTP、EWS、ActiveSync、OAB 和自动发现记录，则必须使用下面的命令添加这些记录 (示例 URL 为''和''，但需要将示例 URL 替换为自己的 `mail.corp.contoso.com` `owa.contoso.com`) ： </span><span class="sxs-lookup"><span data-stu-id="292fb-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="292fb-142">再次运行步骤 2 中的 Get-MsolServicePrincipal 命令并查看输出，以验证是否添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="292fb-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="292fb-143">将之前的列表/屏幕截图与新的 SNS 列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="292fb-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="292fb-144">您还可以为记录拍摄新列表的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="292fb-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="292fb-145">如果成功，你将在列表中看到两个新的 URL。</span><span class="sxs-lookup"><span data-stu-id="292fb-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="292fb-146">以我们的示例为例，SNS 列表现在将包括特定的 URL 和  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="292fb-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="292fb-147">验证虚拟目录是否正确配置</span><span class="sxs-lookup"><span data-stu-id="292fb-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="292fb-148">现在验证 OAuth 是否Exchange所有虚拟目录Outlook运行以下命令来使用：</span><span class="sxs-lookup"><span data-stu-id="292fb-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="292fb-149">检查输出以确保在每个 VDirs 上启用 **OAuth，** 它的外观将如下所示 (需要查看的关键内容是"OAuth") ：</span><span class="sxs-lookup"><span data-stu-id="292fb-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="292fb-150">如果任何服务器和四个虚拟目录中的任意一个中缺少 OAuth，则需要使用相关命令添加 OAuth，然后才能继续 (Set-MapiVirtualDirectory、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory 和[](/powershell/module/exchange/set-mapivirtualdirectory)[](/powershell/module/exchange/set-webservicesvirtualdirectory)[Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)) 。 [](/powershell/module/exchange/set-oabvirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="292fb-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="292fb-151">确认 EvoSTS 身份验证服务器对象存在</span><span class="sxs-lookup"><span data-stu-id="292fb-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="292fb-152">返回到本地命令行管理Exchange最后一个命令。</span><span class="sxs-lookup"><span data-stu-id="292fb-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="292fb-153">现在，您可以验证您的本地是否具有 evoSTS 身份验证提供程序的条目：</span><span class="sxs-lookup"><span data-stu-id="292fb-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

<span data-ttu-id="292fb-154">输出应显示名称 EvoSts 的 AuthServer，并且"已启用"状态应为 True。</span><span class="sxs-lookup"><span data-stu-id="292fb-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="292fb-155">如果未看到此内容，应下载并运行最新版本的混合配置向导。</span><span class="sxs-lookup"><span data-stu-id="292fb-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="292fb-156">如果 EXCH 与多个租户混合，则输出应为与 EXCH 混合的每个租户显示一个名称 EvoSts - {GUID} 的 AuthServer，对于所有这些 AuthServer 对象，"已启用"状态应为 True。</span><span class="sxs-lookup"><span data-stu-id="292fb-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="292fb-157">**重要** 如果在环境中运行 Exchange 2010，将不会创建 EvoSTS 身份验证提供程序。</span><span class="sxs-lookup"><span data-stu-id="292fb-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="292fb-158">启用 HMA</span><span class="sxs-lookup"><span data-stu-id="292fb-158">Enable HMA</span></span>

<span data-ttu-id="292fb-159">在本地命令行管理程序Exchange以下命令：</span><span class="sxs-lookup"><span data-stu-id="292fb-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="292fb-160">如果 EXCH 版本为 Exchange 2016 (CU18 或更高版本) 或 Exchange 2019 (CU7 或更高版本) 且混合配置为在 2020 年 9 月之后下载 HCW，请在本地 Exchange 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="292fb-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="292fb-161">如果 EXCH 与多个租户混合，则 EXCH 中将存在多个 AuthServer 对象，其中域对应于每个租户。</span><span class="sxs-lookup"><span data-stu-id="292fb-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="292fb-162">**对于其中任何** 一个 AuthServer 对象， (**IsDefaultAuthorizationEndpoint cmdlet) IsDefaultAuthorizationEndpoint** 标记应设置为 true。</span><span class="sxs-lookup"><span data-stu-id="292fb-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="292fb-163">无法针对所有 Authserver 对象将此标志设置为 true，并且将启用 HMA，即使其中一个 AuthServer 对象的 **IsDefaultAuthorizationEndpoint** 标志设置为 true 也是如此。</span><span class="sxs-lookup"><span data-stu-id="292fb-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="292fb-164">验证</span><span class="sxs-lookup"><span data-stu-id="292fb-164">Verify</span></span>

<span data-ttu-id="292fb-165">启用 HMA 后，客户端的下一次登录将使用新的身份验证流。</span><span class="sxs-lookup"><span data-stu-id="292fb-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="292fb-166">请注意，仅打开 HMA 不会触发任何客户端的重新身份验证。</span><span class="sxs-lookup"><span data-stu-id="292fb-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="292fb-167">客户端基于其拥有身份验证令牌和/或证书的生存期重新进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="292fb-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="292fb-168">在右键单击 Outlook 客户端图标的同时，还应按住 Ctrl 键 (在 Windows 通知任务栏中) 然后单击"连接状态"。</span><span class="sxs-lookup"><span data-stu-id="292fb-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="292fb-169">针对"Bearer"类型的"Authn"（表示 OAuth 中使用的 bearer 令牌）查找客户端的 SMTP \* 地址。</span><span class="sxs-lookup"><span data-stu-id="292fb-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="292fb-170">需要配置Skype for Business HMA？</span><span class="sxs-lookup"><span data-stu-id="292fb-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="292fb-171">你将需要两篇文章：一篇文章列出支持的拓扑，[](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)另一篇文章演示如何[执行配置](configure-skype-for-business-for-hybrid-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="292fb-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="292fb-172">将混合新式验证用于 Outlook for iOS 和 Outlook for Android</span><span class="sxs-lookup"><span data-stu-id="292fb-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="292fb-173">如果您是使用 TCP 443 Exchange本地客户，请绕过以下 IP 地址范围的流量处理：</span><span class="sxs-lookup"><span data-stu-id="292fb-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="292fb-174">适用于 iOS 和 Android 的 Outlook 应用旨在作为在移动设备上体验 Microsoft 365 或 Office 365 的最佳方法，通过使用 Microsoft 服务 来帮助查找、计划和确定日常工作和工作的优先级。</span><span class="sxs-lookup"><span data-stu-id="292fb-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="292fb-175">有关详细信息，请参阅使用适用于[iOS](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019)和 Android Outlook混合新式验证。</span><span class="sxs-lookup"><span data-stu-id="292fb-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="292fb-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="292fb-176">Related topics</span></span>

[<span data-ttu-id="292fb-177">从专用/ITAR Office 365 vNext 的新式验证配置要求</span><span class="sxs-lookup"><span data-stu-id="292fb-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
