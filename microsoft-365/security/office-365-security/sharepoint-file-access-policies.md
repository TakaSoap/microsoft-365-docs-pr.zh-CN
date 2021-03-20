---
title: 建议的安全文档策略 - Microsoft 365 企业版|Microsoft Docs
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
ms.openlocfilehash: 4e5f20feae5b5854107e9d0de54ef18d59d51df7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916616"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="f3231-103">用于保护 SharePoint 网站和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="f3231-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="f3231-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="f3231-104">**Applies to**</span></span>
- [<span data-ttu-id="f3231-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f3231-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f3231-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="f3231-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- <span data-ttu-id="f3231-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f3231-107">SharePoint Online</span></span> 


<span data-ttu-id="f3231-108">本文介绍如何实施推荐的标识和设备访问策略来保护 SharePoint 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="f3231-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="f3231-109">本指南基于通用[标识和设备访问策略。](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f3231-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="f3231-110">这些建议基于 SharePoint 文件的三种不同安全和保护层，可基于你的需求粒度应用这些层：**基线**、敏感和 **高度管控**。 </span><span class="sxs-lookup"><span data-stu-id="f3231-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="f3231-111">你可以了解有关这些安全层以及推荐的客户端操作系统（概述中这些建议 [所引用）的更多信息](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="f3231-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="f3231-112">除了实现本指南之外，请确保使用适当保护量配置 SharePoint 网站，包括为敏感和高度管控内容设置适当的权限。</span><span class="sxs-lookup"><span data-stu-id="f3231-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="f3231-113">更新常见策略以包括 SharePoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f3231-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="f3231-114">若要保护 SharePoint 和 OneDrive 中的文件，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="f3231-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="f3231-115">[![用于保护对 Teams 及其从属服务的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="f3231-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

<span data-ttu-id="f3231-116">如果在创建常见策略时包括了 SharePoint，则只需创建新策略。</span><span class="sxs-lookup"><span data-stu-id="f3231-116">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="f3231-117">对于条件访问策略，SharePoint 包括 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="f3231-117">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="f3231-118">新策略通过对指定的 SharePoint 网站应用特定访问要求，对敏感和高度管控内容实施设备保护。</span><span class="sxs-lookup"><span data-stu-id="f3231-118">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="f3231-119">下表列出了查看和更新或新建 SharePoint 所需的策略。</span><span class="sxs-lookup"><span data-stu-id="f3231-119">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="f3231-120">常见策略链接到常见标识和设备访问策略文章中的关联 [配置说明](identity-access-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="f3231-120">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="f3231-121">保护级别</span><span class="sxs-lookup"><span data-stu-id="f3231-121">Protection level</span></span>|<span data-ttu-id="f3231-122">策略</span><span class="sxs-lookup"><span data-stu-id="f3231-122">Policies</span></span>|<span data-ttu-id="f3231-123">更多信息</span><span class="sxs-lookup"><span data-stu-id="f3231-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="f3231-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="f3231-124">**Baseline**</span></span>|[<span data-ttu-id="f3231-125">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="f3231-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="f3231-126">将 SharePoint 包括在云应用程序的分配中。</span><span class="sxs-lookup"><span data-stu-id="f3231-126">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="f3231-127">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="f3231-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="f3231-128">将 SharePoint 包括在云应用程序的分配中。</span><span class="sxs-lookup"><span data-stu-id="f3231-128">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="f3231-129">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="f3231-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="f3231-130">请确保所有推荐的应用都包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="f3231-130">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="f3231-131">请务必为 iOS、Android、Windows (的每个平台更新) 。</span><span class="sxs-lookup"><span data-stu-id="f3231-131">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="f3231-132">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="f3231-132">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="f3231-133">将 SharePoint 包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="f3231-133">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="f3231-134">在 SharePoint 中使用应用强制限制</span><span class="sxs-lookup"><span data-stu-id="f3231-134">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="f3231-135">添加新策略。</span><span class="sxs-lookup"><span data-stu-id="f3231-135">Add this new policy.</span></span> <span data-ttu-id="f3231-136">这将告知 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="f3231-136">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="f3231-137">此策略适用于所有用户，但仅影响对 SharePoint 访问策略中包含的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="f3231-137">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="f3231-138">**敏感**</span><span class="sxs-lookup"><span data-stu-id="f3231-138">**Sensitive**</span></span>|[<span data-ttu-id="f3231-139">登录风险低、中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="f3231-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="f3231-140">将 SharePoint 包括在云应用程序的分配中。</span><span class="sxs-lookup"><span data-stu-id="f3231-140">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="f3231-141">要求兼容电脑 *和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="f3231-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="f3231-142">将 SharePoint 包括在云应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="f3231-142">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="f3231-143">[SharePoint 访问控制策略](#sharepoint-access-control-policies)：允许从非托管设备仅浏览器访问特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-143">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="f3231-144">这将阻止编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="f3231-144">This prevents edit and download of files.</span></span> <span data-ttu-id="f3231-145">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-145">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="f3231-146">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="f3231-146">**Highly regulated**</span></span>|[<span data-ttu-id="f3231-147">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="f3231-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="f3231-148">将 SharePoint 包括在云应用程序的分配中。</span><span class="sxs-lookup"><span data-stu-id="f3231-148">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="f3231-149">[SharePoint 访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止从非托管设备访问特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-149">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="f3231-150">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-150">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="f3231-151">在 SharePoint 中使用应用实施的限制</span><span class="sxs-lookup"><span data-stu-id="f3231-151">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="f3231-152">如果在 SharePoint 中实现访问控制，则必须在 Azure AD 中创建此条件访问策略，以告诉 Azure AD 强制实施在 SharePoint 中配置的策略。</span><span class="sxs-lookup"><span data-stu-id="f3231-152">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="f3231-153">此策略适用于所有用户，但只会在您创建 SharePoint 中的访问控制时影响对使用 PowerShell 指定的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="f3231-153">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="f3231-154">若要配置此策略，请参阅控制非托管设备的访问中的"阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户[的访问"。](/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="f3231-154">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="f3231-155">SharePoint 访问控制策略</span><span class="sxs-lookup"><span data-stu-id="f3231-155">SharePoint access control policies</span></span>

<span data-ttu-id="f3231-156">Microsoft 建议通过设备访问控制使用敏感和高度管控的内容保护 SharePoint 网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="f3231-156">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="f3231-157">为此，可创建一个策略，指定保护级别以及要应用保护的网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-157">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="f3231-158">敏感网站：允许仅浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="f3231-158">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="f3231-159">这将阻止用户编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="f3231-159">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="f3231-160">高度管控网站：阻止从非托管设备访问。</span><span class="sxs-lookup"><span data-stu-id="f3231-160">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="f3231-161">请参阅控制非托管设备的访问中的"阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户[的访问"。](/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="f3231-161">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="f3231-162">这些策略如何协同工作</span><span class="sxs-lookup"><span data-stu-id="f3231-162">How these policies work together</span></span>

<span data-ttu-id="f3231-163">SharePoint 网站权限通常基于访问网站的业务需求，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="f3231-163">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="f3231-164">这些权限由网站所有者管理，并且可以是高度动态的。</span><span class="sxs-lookup"><span data-stu-id="f3231-164">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="f3231-165">使用 SharePoint 设备访问策略可确保保护这些网站，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f3231-165">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="f3231-166">下图提供了 SharePoint 设备访问策略如何保护用户对网站的访问权限的示例。</span><span class="sxs-lookup"><span data-stu-id="f3231-166">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="f3231-167">[![SharePoint 设备访问策略如何保护网站的示例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="f3231-167">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="f3231-168">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="f3231-168">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="f3231-169">为用户分配了基线条件访问策略，但可以使用敏感或高度管控保护访问 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-169">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="f3231-170">如果为访问敏感或高度管控网站而为使用电脑的成员，则只要其电脑合规，就授予他的访问权。</span><span class="sxs-lookup"><span data-stu-id="f3231-170">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="f3231-171">如果作为使用非托管电话（允许基线用户使用）的敏感网站，则他将收到对敏感网站的仅浏览器访问权限，因为为此网站配置了设备访问策略。</span><span class="sxs-lookup"><span data-stu-id="f3231-171">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="f3231-172">如果作为使用非托管电话的会员的一员，则由于为该网站配置了访问策略，因此将阻止他访问。</span><span class="sxs-lookup"><span data-stu-id="f3231-172">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="f3231-173">他只能使用自己托管且合规的电脑访问此网站。</span><span class="sxs-lookup"><span data-stu-id="f3231-173">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="f3231-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f3231-174">Next step</span></span>

![步骤 4：Microsoft 365 云应用策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="f3231-176">为：配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="f3231-176">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="f3231-177">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3231-177">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="f3231-178">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f3231-178">Exchange Online</span></span>](secure-email-recommended-policies.md)