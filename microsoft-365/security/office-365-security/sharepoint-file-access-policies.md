---
title: 建议的安全文档策略 - Microsoft 365策略|Microsoft Docs
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203167"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="2f6a0-103">用于保护网站和SharePoint的策略建议</span><span class="sxs-lookup"><span data-stu-id="2f6a0-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="2f6a0-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2f6a0-104">**Applies to**</span></span>
- [<span data-ttu-id="2f6a0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2f6a0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2f6a0-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2f6a0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- <span data-ttu-id="2f6a0-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2f6a0-107">SharePoint Online</span></span> 


<span data-ttu-id="2f6a0-108">本文介绍如何实施推荐的标识和设备访问策略来保护SharePoint OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="2f6a0-109">本指南基于通用[标识和设备访问策略。](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2f6a0-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="2f6a0-110">这些建议基于三种不同的安全和保护层，用于 SharePoint 文件，这些文件可以基于你的需求粒度应用：**基线**、敏感和 **高度管控**。 </span><span class="sxs-lookup"><span data-stu-id="2f6a0-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="2f6a0-111">你可以了解有关这些安全层以及推荐的客户端操作系统（概述中这些建议 [所引用）的更多信息](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="2f6a0-112">除了实现本指南之外，请确保为SharePoint网站配置适当的保护，包括为敏感和高度管控内容设置适当的权限。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="2f6a0-113">更新常见策略以包括SharePoint OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2f6a0-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="2f6a0-114">若要保护SharePoint和设备OneDrive，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="2f6a0-115">[![用于保护对服务及其依赖Teams的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="2f6a0-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

<span data-ttu-id="2f6a0-116">如果在创建SharePoint策略时包括了策略，则只需创建新策略。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-116">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="2f6a0-117">对于条件访问策略，SharePoint包括OneDrive。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-117">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="2f6a0-118">新策略通过对指定的网站应用特定访问要求，为敏感和高度管控SharePoint设备保护。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-118">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="2f6a0-119">下表列出了需要查看和更新的策略，或创建新的SharePoint。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-119">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="2f6a0-120">常见策略链接到常见标识和设备访问策略文章中的关联 [配置说明](identity-access-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-120">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="2f6a0-121">保护级别</span><span class="sxs-lookup"><span data-stu-id="2f6a0-121">Protection level</span></span>|<span data-ttu-id="2f6a0-122">策略</span><span class="sxs-lookup"><span data-stu-id="2f6a0-122">Policies</span></span>|<span data-ttu-id="2f6a0-123">详细信息</span><span class="sxs-lookup"><span data-stu-id="2f6a0-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="2f6a0-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="2f6a0-124">**Baseline**</span></span>|[<span data-ttu-id="2f6a0-125">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="2f6a0-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2f6a0-126">将SharePoint包括在云应用的分配中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-126">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="2f6a0-127">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="2f6a0-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="2f6a0-128">将SharePoint包括在云应用的分配中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-128">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="2f6a0-129">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="2f6a0-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="2f6a0-130">请确保所有推荐的应用都包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-130">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="2f6a0-131">请务必为 iOS、Android、 (的每个平台更新Windows) 。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-131">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="2f6a0-132">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="2f6a0-132">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2f6a0-133">将SharePoint包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-133">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="2f6a0-134">在应用中使用应用强制SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f6a0-134">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="2f6a0-135">添加新策略。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-135">Add this new policy.</span></span> <span data-ttu-id="2f6a0-136">这将Azure Active Directory (Azure AD) 使用 SharePoint 中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-136">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="2f6a0-137">此策略适用于所有用户，但仅影响对访问策略中包含的SharePoint的访问。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-137">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="2f6a0-138">**敏感**</span><span class="sxs-lookup"><span data-stu-id="2f6a0-138">**Sensitive**</span></span>|[<span data-ttu-id="2f6a0-139">登录风险低、中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="2f6a0-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2f6a0-140">将SharePoint包括在云应用的分配中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-140">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="2f6a0-141">要求兼容电脑 *和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="2f6a0-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="2f6a0-142">将SharePoint包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-142">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="2f6a0-143">[SharePoint访问控制策略](#sharepoint-access-control-policies)：允许仅浏览器访问SharePoint非托管设备的特定网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-143">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="2f6a0-144">这将阻止编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-144">This prevents edit and download of files.</span></span> <span data-ttu-id="2f6a0-145">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-145">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="2f6a0-146">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="2f6a0-146">**Highly regulated**</span></span>|[<span data-ttu-id="2f6a0-147">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2f6a0-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2f6a0-148">将SharePoint包括在云应用的分配中。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-148">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="2f6a0-149">[SharePoint访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止从非SharePoint访问特定网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-149">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="2f6a0-150">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-150">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="2f6a0-151">在应用程序中使用应用强制SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f6a0-151">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="2f6a0-152">如果在 SharePoint 中实现访问控制，则必须在 Azure AD 中创建此条件访问策略，以告诉 Azure AD 强制执行在 SharePoint 中配置的策略。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-152">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="2f6a0-153">此策略适用于所有用户，但仅影响在使用 PowerShell 创建访问控件时对使用 PowerShell 指定的SharePoint。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-153">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="2f6a0-154">若要配置此策略，请参阅控制从非托管设备SharePoint或OneDrive访问特定网站集或帐户["。](/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="2f6a0-154">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="2f6a0-155">SharePoint访问控制策略</span><span class="sxs-lookup"><span data-stu-id="2f6a0-155">SharePoint access control policies</span></span>

<span data-ttu-id="2f6a0-156">Microsoft 建议通过设备访问控制SharePoint敏感和高度管控内容保护网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-156">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="2f6a0-157">为此，可创建一个策略，指定保护级别以及要应用保护的网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-157">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="2f6a0-158">敏感网站：允许仅浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-158">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="2f6a0-159">这将阻止用户编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-159">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="2f6a0-160">高度管控网站：阻止从非托管设备访问。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-160">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="2f6a0-161">请参阅控制非托管设备SharePoint OneDrive中的"阻止或限制SharePoint访问特定网站集或帐户["。](/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="2f6a0-161">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="2f6a0-162">这些策略如何协同工作</span><span class="sxs-lookup"><span data-stu-id="2f6a0-162">How these policies work together</span></span>

<span data-ttu-id="2f6a0-163">网站权限通常SharePoint访问网站的业务需求，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-163">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="2f6a0-164">这些权限由网站所有者管理，并且可以是高度动态的。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-164">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="2f6a0-165">使用SharePoint访问策略可确保保护这些站点，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-165">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="2f6a0-166">下图提供了一个示例，SharePoint访问策略如何保护用户对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-166">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="2f6a0-167">[![设备访问SharePoint如何保护网站的示例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="2f6a0-167">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="2f6a0-168">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="2f6a0-168">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="2f6a0-169">为一位用户分配了基线条件访问策略，但可以SharePoint敏感或高度管控保护的网站访问这些网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-169">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="2f6a0-170">如果为访问敏感或高度管控网站而为使用电脑的成员，则只要其电脑合规，就授予他的访问权。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-170">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="2f6a0-171">如果作为使用非托管电话（允许基线用户使用）的敏感网站，则他将收到对敏感网站的仅浏览器访问权限，因为为此网站配置了设备访问策略。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-171">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="2f6a0-172">如果作为使用非托管电话的会员的一员，则由于为该网站配置了访问策略，因此将阻止他访问。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-172">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="2f6a0-173">他只能使用自己托管且合规的电脑访问此网站。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-173">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="2f6a0-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2f6a0-174">Next step</span></span>

![步骤 4：云Microsoft 365策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="2f6a0-176">为：配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="2f6a0-176">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="2f6a0-177">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f6a0-177">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="2f6a0-178">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2f6a0-178">Exchange Online</span></span>](secure-email-recommended-policies.md)