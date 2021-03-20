---
title: 如何配置本地 Skype for Business 以使用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 了解如何配置本地 Skype for Business 以使用混合新式验证 (HMA) ，以为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3177bafb6eff27053dca61ec576666cae4a97bb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911146"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="c7055-103">如何配置本地 Skype for Business 以使用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="c7055-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="c7055-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="c7055-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c7055-105">新式验证是一种标识管理方法，可提供更安全的用户身份验证和授权，可用于 Skype for Business 服务器本地和 Exchange 服务器本地，以及拆分域 Skype for Business 混合。</span><span class="sxs-lookup"><span data-stu-id="c7055-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="c7055-106">**重要** 您是否想了解有关 MA (新式验证) 以及为什么可能更希望在你的公司或组织中使用它？</span><span class="sxs-lookup"><span data-stu-id="c7055-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="c7055-107">请查看 [本文档](hybrid-modern-auth-overview.md) ，了解概述。</span><span class="sxs-lookup"><span data-stu-id="c7055-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="c7055-108">如果你需要了解 MA 支持哪些 Skype for Business 拓扑，请在此处进行记录！</span><span class="sxs-lookup"><span data-stu-id="c7055-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="c7055-109">**在开始之前，** 我使用以下术语：</span><span class="sxs-lookup"><span data-stu-id="c7055-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="c7055-110">MA (新式验证) </span><span class="sxs-lookup"><span data-stu-id="c7055-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="c7055-111">混合新式验证 (HMA) </span><span class="sxs-lookup"><span data-stu-id="c7055-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="c7055-112">Exchange 内部部署 (EXCH) </span><span class="sxs-lookup"><span data-stu-id="c7055-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="c7055-113">Exchange Online (EXO) </span><span class="sxs-lookup"><span data-stu-id="c7055-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="c7055-114">本地 Skype for Business (SFB) </span><span class="sxs-lookup"><span data-stu-id="c7055-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="c7055-115">Skype for Business Online (SFBO) </span><span class="sxs-lookup"><span data-stu-id="c7055-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="c7055-116">此外，如果本文中的图形具有灰显或灰显的对象，则意味着以灰色显示的元素不包含在 MA 特定的配置中。</span><span class="sxs-lookup"><span data-stu-id="c7055-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="c7055-117">阅读摘要</span><span class="sxs-lookup"><span data-stu-id="c7055-117">Read the summary</span></span>

<span data-ttu-id="c7055-118">此摘要将流程分解为在执行过程中可能丢失的步骤，并且适合使用整体检查表来跟踪您在此进程中的运行位置。</span><span class="sxs-lookup"><span data-stu-id="c7055-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="c7055-119">首先，请确保满足所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="c7055-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="c7055-120">由于 **许多先决条件** 对 Skype for Business 和 Exchange 都很常见，请参阅有关预重新检查表 [的概述文章](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c7055-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c7055-121">在开始  *执行本文*  中的任一步骤之前，先执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c7055-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="c7055-122">在文件或 OneNote 中收集你需要的 HMA 特定信息。</span><span class="sxs-lookup"><span data-stu-id="c7055-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="c7055-123">如果 EXO 身份验证尚未 (，请打开 EXO 身份验证) 。</span><span class="sxs-lookup"><span data-stu-id="c7055-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="c7055-124">如果 SFBO 证书尚未 (，请为 SFBO 启用新式) 。</span><span class="sxs-lookup"><span data-stu-id="c7055-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="c7055-125">为 Exchange 本地启用混合新式验证。</span><span class="sxs-lookup"><span data-stu-id="c7055-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="c7055-126">在本地为 Skype for Business 启用混合新式验证。</span><span class="sxs-lookup"><span data-stu-id="c7055-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="c7055-127">这些步骤为 SFB、SFBO、EXCH 和 EXO 启用 MA，即可以参与 SFB 和 SFBO (包括 EXCH/EXO) 的 HMA 配置的所有产品。</span><span class="sxs-lookup"><span data-stu-id="c7055-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="c7055-128">换句话说，如果用户在混合 (EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB) 的任何部分创建邮箱，则已完成的产品将如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7055-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![混合 6 Skype for Business HMA 拓扑在所有四个可能的位置均具有 MA。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="c7055-130">如你所见，有四个不同的位置可以打开 MA！</span><span class="sxs-lookup"><span data-stu-id="c7055-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="c7055-131">为了获得最佳用户体验，我们建议你在这四个位置都打开 MA。</span><span class="sxs-lookup"><span data-stu-id="c7055-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="c7055-132">如果无法在所有这些位置打开 MA，请调整步骤，以便仅在环境所需的位置打开 MA。</span><span class="sxs-lookup"><span data-stu-id="c7055-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="c7055-133">有关支持的 [拓扑，请参阅适用于具有 MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) 的 Skype for Business 的可支持性主题。</span><span class="sxs-lookup"><span data-stu-id="c7055-133">See the [Supportability topic for Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) for supported topologies.</span></span>
  
 <span data-ttu-id="c7055-134">**重要** 在开始之前，仔细检查是否满足所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="c7055-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="c7055-135">你将在混合新式验证概述 [和先决条件中找到该信息](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c7055-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="c7055-136">收集你需要的所有 HMA 特定信息</span><span class="sxs-lookup"><span data-stu-id="c7055-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="c7055-137">在仔细检查是否满足使用新式验证 (请参阅上述[](hybrid-modern-auth-overview.md)) 说明后，应创建一个文件来保存在以下步骤中配置 HMA 时需要的信息。</span><span class="sxs-lookup"><span data-stu-id="c7055-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="c7055-138">本文中使用的示例：</span><span class="sxs-lookup"><span data-stu-id="c7055-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="c7055-139">**SIP/SMTP 域**</span><span class="sxs-lookup"><span data-stu-id="c7055-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="c7055-140">例如，</span><span class="sxs-lookup"><span data-stu-id="c7055-140">Ex.</span></span> <span data-ttu-id="c7055-141">contoso.com (Office 365) </span><span class="sxs-lookup"><span data-stu-id="c7055-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="c7055-142">**租户 ID**</span><span class="sxs-lookup"><span data-stu-id="c7055-142">**Tenant ID**</span></span>

  - <span data-ttu-id="c7055-143">表示 Office 365 租户的 GUID (登录时 contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="c7055-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="c7055-144">**SFB 2015 CU5 Web 服务 URL**</span><span class="sxs-lookup"><span data-stu-id="c7055-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="c7055-145">您需要为部署的所有 SfB 2015 池提供内部和外部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="c7055-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="c7055-146">若要获取这些证书，请从 Skype for Business 命令行管理程序 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c7055-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="c7055-147">例如，</span><span class="sxs-lookup"><span data-stu-id="c7055-147">Ex.</span></span> <span data-ttu-id="c7055-148">内部： https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7055-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="c7055-149">例如，</span><span class="sxs-lookup"><span data-stu-id="c7055-149">Ex.</span></span> <span data-ttu-id="c7055-150">外部： https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7055-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="c7055-151">如果使用的是 Standard Edition Server，内部 URL 将为空。</span><span class="sxs-lookup"><span data-stu-id="c7055-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="c7055-152">在这种情况下，将池 fqdn 用于内部 URL。</span><span class="sxs-lookup"><span data-stu-id="c7055-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="c7055-153">启用 EXO 的新式验证</span><span class="sxs-lookup"><span data-stu-id="c7055-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="c7055-154">请按照以下说明操作 [：Exchange Online：如何为租户启用新式验证。](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="c7055-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="c7055-155">为 SFBO 启用新式验证</span><span class="sxs-lookup"><span data-stu-id="c7055-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="c7055-156">请按照以下说明操作 [：Skype for Business Online：为租户启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c7055-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="c7055-157">为 Exchange 本地启用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="c7055-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="c7055-158">请按照以下说明操作 [：如何配置Exchange Server内部部署，以使用混合新式验证](configure-exchange-server-for-hybrid-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="c7055-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="c7055-159">打开 Skype for Business 本地混合新式验证</span><span class="sxs-lookup"><span data-stu-id="c7055-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="c7055-160">将本地 Web 服务 URL 添加为 Azure Active Directory 中的 SNS</span><span class="sxs-lookup"><span data-stu-id="c7055-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="c7055-161">现在，你需要运行命令，将之前收集 (URL) SFBO 中的服务主体。</span><span class="sxs-lookup"><span data-stu-id="c7055-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="c7055-162">**注意** 服务主体名称 (SNS) 标识 Web 服务，并将其与安全主体 (（如帐户名或组) ）关联，以便该服务可以代表授权用户操作。</span><span class="sxs-lookup"><span data-stu-id="c7055-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="c7055-163">对服务器进行身份验证的客户端使用 SNS 中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="c7055-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="c7055-164">首先，按照以下说明 (Azure AD) Azure Active [Directory。](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="c7055-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="c7055-165">在本地运行此命令，获取 SFB Web 服务 URL 的列表。</span><span class="sxs-lookup"><span data-stu-id="c7055-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="c7055-166">请注意，AppPrincipalId 以 开头 `00000004` 。</span><span class="sxs-lookup"><span data-stu-id="c7055-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="c7055-167">这对应于 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="c7055-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="c7055-168">记下命令 (和屏幕截图，以) 此命令的输出，此命令将包含 SE 和 WS URL，但主要包括以 开头的 `00000004-0000-0ff1-ce00-000000000000/` SNS。</span><span class="sxs-lookup"><span data-stu-id="c7055-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="c7055-169">例如， **如果** 缺少内部部署中的内部或外部 SFB URL (，我们将需要将那些特定记录 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) 添加到此列表。</span><span class="sxs-lookup"><span data-stu-id="c7055-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="c7055-170">请务必将下面的示例  *URL 替换为* "添加"命令中的实际 URL！</span><span class="sxs-lookup"><span data-stu-id="c7055-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="c7055-171">再次运行步骤 2 中的 **Get-MsolServicePrincipal** 命令并查看输出，以验证是否添加了新记录。</span><span class="sxs-lookup"><span data-stu-id="c7055-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="c7055-172">将之前的列表或屏幕截图与新的 SNS 列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="c7055-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="c7055-173">您还可以为记录的新列表屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="c7055-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="c7055-174">如果成功，你将在列表中看到两个新的 URL。</span><span class="sxs-lookup"><span data-stu-id="c7055-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="c7055-175">以我们的示例为例，SNS 列表现在将包括特定的 URL 和 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ 。</span><span class="sxs-lookup"><span data-stu-id="c7055-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="c7055-176">创建 EvoSTS 身份验证服务器对象</span><span class="sxs-lookup"><span data-stu-id="c7055-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="c7055-177">在 Skype for Business 命令行管理程序 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c7055-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="c7055-178">启用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="c7055-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="c7055-179">这是实际上打开 MA 的步骤。</span><span class="sxs-lookup"><span data-stu-id="c7055-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="c7055-180">可以提前运行上述所有步骤，而无需更改客户端身份验证流。</span><span class="sxs-lookup"><span data-stu-id="c7055-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="c7055-181">准备好更改身份验证流后，在 Skype for Business 命令行管理程序 中运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c7055-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="c7055-182">验证</span><span class="sxs-lookup"><span data-stu-id="c7055-182">Verify</span></span>

<span data-ttu-id="c7055-183">启用 HMA 后，客户端的下一次登录将使用新的身份验证流。</span><span class="sxs-lookup"><span data-stu-id="c7055-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="c7055-184">请注意，仅打开 HMA 不会触发任何客户端的重新身份验证。</span><span class="sxs-lookup"><span data-stu-id="c7055-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="c7055-185">客户端基于其拥有身份验证令牌和/或证书的生存期重新进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c7055-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="c7055-186">若要测试 HMA 在启用后是否正常工作，请注销测试 SFB Windows 客户端，并确保单击"删除我的凭据"。</span><span class="sxs-lookup"><span data-stu-id="c7055-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="c7055-187">再次登录。</span><span class="sxs-lookup"><span data-stu-id="c7055-187">Sign in again.</span></span> <span data-ttu-id="c7055-188">客户端现在应该使用新式身份验证流，并且你的登录名现在将包括 Office **365** 提示输入"工作或学校"帐户，在客户端联系服务器并登录之前，将会看到此提示。</span><span class="sxs-lookup"><span data-stu-id="c7055-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="c7055-189">还应检查 Skype for Business 客户端的"配置信息"，查看"OAuth 颁发机构"。</span><span class="sxs-lookup"><span data-stu-id="c7055-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="c7055-190">若要在客户端计算机上执行此操作，请按住 Ctrl 键，同时右键单击 Windows 通知托盘中的 Skype for Business 图标。</span><span class="sxs-lookup"><span data-stu-id="c7055-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="c7055-191">在 **出现的菜单中** 单击"配置信息"。</span><span class="sxs-lookup"><span data-stu-id="c7055-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="c7055-192">在桌面上出现的"Skype for Business 配置信息"窗口中，查找以下内容：</span><span class="sxs-lookup"><span data-stu-id="c7055-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![使用新式验证的 Skype for Business 客户端的配置信息显示 的 Lync 和 EWS OAUTH 颁发机构 https://login.windows.net/common/oauth2/authorize URL。](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="c7055-194">在右键单击 Outlook 客户端图标的同时，还应按住 Ctrl 键 (在 Windows 通知托盘中单击) "连接状态"。</span><span class="sxs-lookup"><span data-stu-id="c7055-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="c7055-195">针对表示 OAuth 中使用的 bearer 令牌的 AuthN 类型查找客户端的 SMTP \* 地址。</span><span class="sxs-lookup"><span data-stu-id="c7055-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c7055-196">相关文章</span><span class="sxs-lookup"><span data-stu-id="c7055-196">Related articles</span></span>

<span data-ttu-id="c7055-197">[链接回新式验证概述](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c7055-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="c7055-198">是否需要了解如何为 Skype for Business 客户端 (ADAL) 新式验证？</span><span class="sxs-lookup"><span data-stu-id="c7055-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="c7055-199">我们在此处有 [步骤](./hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c7055-199">We've got steps [here](./hybrid-modern-auth-overview.md).</span></span>