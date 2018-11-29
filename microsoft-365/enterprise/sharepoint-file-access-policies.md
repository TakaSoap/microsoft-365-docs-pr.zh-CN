---
title: 建议的安全文档策略 - Microsoft 365 企业版 | Microsoft Docs
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 2f5658146df3da7cc28c907b33e5035a84628fc5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865684"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="fd373-103">用于保护 SharePoint 网站和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="fd373-103">Policy recommendations for securing SharePoint Sites and files</span></span>
<span data-ttu-id="fd373-p101">本文介绍如何实现建议的标识和设备访问策略以保护 SharePoint Online 和 OneDrive for Business。本指南基于[常见标识和访问策略的设备](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fd373-p101">This article describes how to implement the recommended identity and device access policies to protect SharePoint Online and OneDrive for Business. This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span> 


<span data-ttu-id="fd373-p102">这些建议基于三个不同级别的安全和保护可以应用的 SharePoint 文件 （英文） 根据您的需求的粒度：**基线**、**敏感**和**高度管控**。您可以了解有关这些安全层及推荐客户端的操作系统，通过这些建议[概述](microsoft-365-policies-configurations.md)中引用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd373-p102">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**. You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="fd373-p103">在所实现本指南，请确保使用适量的保护，其中包括确保敏感和高管控内容为适当的权限配置 SharePoint 网站。创建站点的比较基准，敏感和高管控保护的详细信息，请参阅[安全 SharePoint Online 网站和文件](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。</span><span class="sxs-lookup"><span data-stu-id="fd373-p103">In addtion to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including ensuring permissions for sensitive and highly regulated content are appropriate. For more information on creating sites for baseline, sensitive, and highly regulated protection, see [Secure SharePoint Online sites and files](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</span></span> 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="fd373-110">更新常见的策略，以包含 SharePoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="fd373-110">Updating common policies to include SharePoint and OneDrive for Business</span></span>
<span data-ttu-id="fd373-p104">下图演示了用来保护中 SharePoint Online 和 OneDrive for Business 的文件的建议策略的组。表示哪些策略将更新或新创建的以添加对 SharePoint Online 和 OneDrive for Business 的保护。</span><span class="sxs-lookup"><span data-stu-id="fd373-p104">The following diagram illustrates the set of recommended policies for protecting files in SharePoint Online and OneDrive for Business. It indicates which policies will be updated or newly created to add protection for SharePoint Online and OneDrive for Business.</span></span>

![SharePoint Online 和 OneDrive 策略的摘要。](../images/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="fd373-p105">如果您包括 SharePoint Online 中创建的常用策略时，您只需创建新的 polcies。配置条件访问规则，SharePoint Online 中包括的 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="fd373-p105">If you included SharePoint Online when you created the common policies, you only need to create the new polcies. When configuring conditional access rules, SharePoint Online includes OneDrive for Business.</span></span>

<span data-ttu-id="fd373-116">新增的策略通过应用到您指定的 SharePoint 网站的特定访问要求实现设备保护敏感和高管控的内容。</span><span class="sxs-lookup"><span data-stu-id="fd373-116">The new policies implement device protection for sensitive and highly regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span> 

 <span data-ttu-id="fd373-p106">下表列出您也需要查看和更新或创建新的 SharePoint Online 的策略。常见策略链接到[常见 identity 和设备访问策略](identity-access-policies.md)一文 （即将推出的链接） 中的关联的配置说明。</span><span class="sxs-lookup"><span data-stu-id="fd373-p106">The following table lists the policies you either need to review and update or create new for SharePoint Online. The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article (links coming soon).</span></span>


|<span data-ttu-id="fd373-119">保护级别</span><span class="sxs-lookup"><span data-stu-id="fd373-119">Protection level</span></span>|<span data-ttu-id="fd373-120">Policies</span><span class="sxs-lookup"><span data-stu-id="fd373-120">Policies</span></span>|<span data-ttu-id="fd373-121">更多信息</span><span class="sxs-lookup"><span data-stu-id="fd373-121">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="fd373-122">**基线**</span><span class="sxs-lookup"><span data-stu-id="fd373-122">**Baseline**</span></span>|[<span data-ttu-id="fd373-123">*中等*或*高*风险登录时需要 MFA</span><span class="sxs-lookup"><span data-stu-id="fd373-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="fd373-124">包括 SharePoint Online 中的云应用程序的分配。</span><span class="sxs-lookup"><span data-stu-id="fd373-124">Include SharePoint Online in the assignments of cloud apps.</span></span>|
|        |[<span data-ttu-id="fd373-125">阻止客户端不支持现代身份验证</span><span class="sxs-lookup"><span data-stu-id="fd373-125">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="fd373-126">包括 SharePoint Online 中的云应用程序的分配。</span><span class="sxs-lookup"><span data-stu-id="fd373-126">Include SharePoint Online in the assignments of cloud apps.</span></span>|
|        |[<span data-ttu-id="fd373-127">定义应用程序保护策略</span><span class="sxs-lookup"><span data-stu-id="fd373-127">Define app protection policies</span></span>](identity-access-policies.md#define-app-protection-policies)|<span data-ttu-id="fd373-p107">确保所有建议的应用程序都包含在应用程序的列表。请务必更新为每个平台 (iOS，Android、 Windows) 策略。</span><span class="sxs-lookup"><span data-stu-id="fd373-p107">Be sure all recommended apps are included in the list of apps. Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="fd373-130">需要符合标准的 Pc</span><span class="sxs-lookup"><span data-stu-id="fd373-130">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="fd373-131">在列表中的云应用程序包括 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="fd373-131">Include SharePoint Online in list of cloud apps.</span></span>|
|        |[<span data-ttu-id="fd373-132">在 SharePoint Online 中使用应用程序强制实施限制</span><span class="sxs-lookup"><span data-stu-id="fd373-132">Use app enforced restrictions in SharePoint Online</span></span>](#use-app-enforced-restrictions-in-sharepoint-online)|<span data-ttu-id="fd373-p108">添加此新策略。这会告诉 Azure AD 以使用 SharePoint Online 中指定的设置。此规则应用于所有用户，但只影响对 SharePoint Online 访问策略中包括的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="fd373-p108">Add this new policy. This tells Azure AD to use the settings specified in SharePoint Online. This rule applies to all users but only affects access to sites included in SharePoint Online access policies.</span></span>
|<span data-ttu-id="fd373-136">**敏感**</span><span class="sxs-lookup"><span data-stu-id="fd373-136">**Sensitive**</span></span>|[<span data-ttu-id="fd373-137">*低*、*中*或*高*风险登录时需要 MFA</span><span class="sxs-lookup"><span data-stu-id="fd373-137">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="fd373-138">包括 SharePoint Online 中的云应用程序的分配。</span><span class="sxs-lookup"><span data-stu-id="fd373-138">Include SharePoint Online in the assignments of cloud apps.</span></span>|
|         |[<span data-ttu-id="fd373-139">需要符合标准的 Pc*和*移动设备</span><span class="sxs-lookup"><span data-stu-id="fd373-139">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="fd373-140">包括的云应用程序列表中的 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="fd373-140">Include SharePoint Online in the list of cloud apps.</span></span>|
||<span data-ttu-id="fd373-141">[SharePoint Online 访问控制策略](#sharepoint-online-access-control-policies)： 允许从非托管设备仅浏览器访问特定的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="fd373-141">[SharePoint Online access control policy](#sharepoint-online-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices</span></span>|<span data-ttu-id="fd373-p109">这样可以防止编辑和下载文件。要指定站点的用户 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fd373-p109">This prevents edit and download of files. User PowerShell to specify sites.</span></span>|
|<span data-ttu-id="fd373-144">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="fd373-144">**Highly regulated**</span></span>|[<span data-ttu-id="fd373-145">*始终*requrie MFA</span><span class="sxs-lookup"><span data-stu-id="fd373-145">*Always* requrie MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="fd373-146">包括 SharePoint Online 中的云应用程序的分配。</span><span class="sxs-lookup"><span data-stu-id="fd373-146">Include SharePoint Online in the assignments of cloud apps.</span></span> |
||<span data-ttu-id="fd373-147">[SharePoint Online 访问控制策略](#use-app-enforced-restrictions-in-sharepoint-online)： 从非托管设备阻止到特定的 SharePoint 网站的访问</span><span class="sxs-lookup"><span data-stu-id="fd373-147">[SharePoint Online access control policy](#use-app-enforced-restrictions-in-sharepoint-online): Block access to specific SharePoint sites from unmanaged devices</span></span>|<span data-ttu-id="fd373-148">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="fd373-148">Use PowerShell to specify sites.</span></span>|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a><span data-ttu-id="fd373-149">在 SharePoint Online 中使用应用程序强制实施限制</span><span class="sxs-lookup"><span data-stu-id="fd373-149">Use app enforced restrictions in SharePoint Online</span></span>
<span data-ttu-id="fd373-p110">如果在 SharePoint Online 中实现访问控制，您必须在 Azure AD 以告知 Azure AD 实施 SharePoint Online 中配置的策略创建该条件访问策略。此规则应用于所有用户，但只影响对使用 PowerShell 在 SharePoint Online 中创建的访问控制时指定网站的访问。</span><span class="sxs-lookup"><span data-stu-id="fd373-p110">If you implement access controls in SharePoint Online, you must create this conditional access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint Online. This rule applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint Online.</span></span>

<span data-ttu-id="fd373-152">本文中配置此策略，请参阅 《 到特定的 SharePoint 网站集或 OneDrive 帐户的阻止或限制访问":[控件从非托管的设备的访问](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。</span><span class="sxs-lookup"><span data-stu-id="fd373-152">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in this article: [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).</span></span>


## <a name="sharepoint-online-access-control-policies"></a><span data-ttu-id="fd373-153">SharePoint Online 访问控制策略</span><span class="sxs-lookup"><span data-stu-id="fd373-153">SharePoint Online access control policies</span></span>
<span data-ttu-id="fd373-p111">Microsoft 建议您保护敏感和高管控与设备访问控件的内容与 SharePoint 网站中的内容。通过创建指定的保护和网站应用到保护级别的策略来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="fd373-p111">Microsoft recommends you protect content in SharePoint sites with sensitive and highly regulated content with device access controls. You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span> 
- <span data-ttu-id="fd373-p112">敏感网站 — 允许仅浏览器访问权限。这样可以防止用户编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="fd373-p112">Sensitive sites — Allow browser-only access. This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="fd373-158">高度管控网站 — 阻止访问从非托管设备。</span><span class="sxs-lookup"><span data-stu-id="fd373-158">Highly regulated sites — Block access from unmanaged devices.</span></span>

<span data-ttu-id="fd373-159">请参阅本文中的"阻止或限制访问特定的 SharePoint 网站集或 OneDrive 帐户":[控件从非托管的设备的访问](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。</span><span class="sxs-lookup"><span data-stu-id="fd373-159">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in this article: [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) .</span></span> 

## <a name="how-these-policies-work-together"></a><span data-ttu-id="fd373-160">这些策略如何协同工作</span><span class="sxs-lookup"><span data-stu-id="fd373-160">How these policies work together</span></span>
<span data-ttu-id="fd373-p113">务必要了解 SharePoint 网站权限通常基于业务需要对网站的访问。这些权限由网站所有者管理，可以是高度动态。使用设备访问策略可确保对这些网站，而不管是否将用户分配到 Azure AD 组保护的 SharePoint 相关联比较基准敏感，或者高度管控保护。</span><span class="sxs-lookup"><span data-stu-id="fd373-p113">It's important to understand that SharePoint site permissions are typically based on business need for access to sites. These permissions are managed by site owners and can be highly dynamic. Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span> 

<span data-ttu-id="fd373-164">下图提供了一种 SharePoint 设备访问策略如何保护对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="fd373-164">The following illustration provides an example of how SharePoint device access policies protect access to sites.</span></span>

![SharePoint 设备访问策略如何保护网站](../images/SharePoint-rules-scenario.png)

<span data-ttu-id="fd373-166">在此图中：</span><span class="sxs-lookup"><span data-stu-id="fd373-166">In the illustration:</span></span>
- <span data-ttu-id="fd373-167">James 被分配给与比较基准保护关联的条件的访问策略，但他可以授予对访问敏感或高度管控保护与关联的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="fd373-167">James is assigned to conditional access policies associated with baseline protection, but he can be given access to SharePoint sites associated with sensitive or highly regulated protection.</span></span> 
- <span data-ttu-id="fd373-168">如果 James 访问敏感或高度管控网站他是使用其 PC 的成员，只要其 PC 符合授予其访问。</span><span class="sxs-lookup"><span data-stu-id="fd373-168">If James accesses a sensitive or highly regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="fd373-169">如果 James 访问敏感网站他是成员的使用其非托管的电话，允许对基线用户，则他将收到由于为此站点配置的设备访问策略敏感的网站的浏览器只读访问。</span><span class="sxs-lookup"><span data-stu-id="fd373-169">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span> 
- <span data-ttu-id="fd373-p114">如果 James 访问高度管控的网站他是使用其非托管的电话的成员，则他将被阻止由于为此站点配置的访问策略。他只能访问此网站使用他的管理和合规性 PC。</span><span class="sxs-lookup"><span data-stu-id="fd373-p114">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site. He can only access this site using his managed and compliant PC.</span></span>


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a><span data-ttu-id="fd373-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fd373-172">Next steps</span></span>
[<span data-ttu-id="fd373-173">保护 SharePoint Online 网站和文件</span><span class="sxs-lookup"><span data-stu-id="fd373-173">Secure SharePoint Online sites and files</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
