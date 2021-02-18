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
ms.openlocfilehash: f3a9cc2c3bae32a8fee10e814f96968b864e78a5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290413"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="ca1e2-103">用于保护 SharePoint 网站和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="ca1e2-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="ca1e2-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="ca1e2-104">**Applies to**</span></span>
- [<span data-ttu-id="ca1e2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ca1e2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ca1e2-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="ca1e2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- <span data-ttu-id="ca1e2-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ca1e2-107">SharePoint Online</span></span> 


<span data-ttu-id="ca1e2-108">本文介绍如何实施建议的标识和设备访问策略来保护 SharePoint 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-108">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="ca1e2-109">本指南基于[通用标识和设备访问策略。](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ca1e2-109">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="ca1e2-110">这些建议基于 SharePoint 文件的三个不同安全和保护层，这些层可以基于你的需求粒度应用：**基线**、敏感和 **高度管控**。 </span><span class="sxs-lookup"><span data-stu-id="ca1e2-110">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="ca1e2-111">你可以了解有关这些安全层以及推荐的客户端操作系统（概述中这些建议所引用） [的更多信息](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-111">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="ca1e2-112">除了实施本指南之外，请确保使用适当保护量配置 SharePoint 网站，包括为敏感和高度管控内容设置适当的权限。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-112">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="ca1e2-113">更新常见策略以包括 SharePoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ca1e2-113">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="ca1e2-114">若要保护 SharePoint 和 OneDrive 中的文件，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-114">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="ca1e2-115">[![用于保护对 Teams 及其从属服务的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="ca1e2-115">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="ca1e2-116">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="ca1e2-116">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="ca1e2-117">如果在创建常见策略时包含 SharePoint，则只需创建新策略。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-117">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="ca1e2-118">对于条件访问策略，SharePoint 包括 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-118">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="ca1e2-119">新策略通过向指定的 SharePoint 网站应用特定访问要求，为敏感和高度管控的内容实施设备保护。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-119">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="ca1e2-120">下表列出了查看和更新 SharePoint 或创建新策略所需的策略。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-120">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="ca1e2-121">常见策略链接到通用标识和设备访问策略文章中的 [关联配置](identity-access-policies.md) 说明。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-121">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="ca1e2-122">保护级别</span><span class="sxs-lookup"><span data-stu-id="ca1e2-122">Protection level</span></span>|<span data-ttu-id="ca1e2-123">策略</span><span class="sxs-lookup"><span data-stu-id="ca1e2-123">Policies</span></span>|<span data-ttu-id="ca1e2-124">更多信息</span><span class="sxs-lookup"><span data-stu-id="ca1e2-124">More information</span></span>|
|---|---|---|
|<span data-ttu-id="ca1e2-125">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="ca1e2-125">**Baseline**</span></span>|[<span data-ttu-id="ca1e2-126">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="ca1e2-126">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="ca1e2-127">在分配云应用时包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-127">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="ca1e2-128">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="ca1e2-128">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="ca1e2-129">在分配云应用时包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-129">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="ca1e2-130">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="ca1e2-130">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="ca1e2-131">请确保所有推荐的应用都包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-131">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="ca1e2-132">请务必为 iOS、Android、Windows (的每个平台更新) 。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-132">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="ca1e2-133">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="ca1e2-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="ca1e2-134">将 SharePoint 包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-134">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="ca1e2-135">在 SharePoint 中使用应用强制限制</span><span class="sxs-lookup"><span data-stu-id="ca1e2-135">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="ca1e2-136">添加新策略。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-136">Add this new policy.</span></span> <span data-ttu-id="ca1e2-137">这将告知 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-137">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="ca1e2-138">此策略适用于所有用户，但仅影响对 SharePoint 访问策略中包含的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-138">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="ca1e2-139">**敏感**</span><span class="sxs-lookup"><span data-stu-id="ca1e2-139">**Sensitive**</span></span>|[<span data-ttu-id="ca1e2-140">登录风险低、中或高时需要MFA  </span><span class="sxs-lookup"><span data-stu-id="ca1e2-140">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="ca1e2-141">将 SharePoint 包括在云应用程序的分配中。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-141">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="ca1e2-142">要求兼容电脑 *和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="ca1e2-142">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="ca1e2-143">将 SharePoint 包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-143">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="ca1e2-144">[SharePoint 访问控制策略](#sharepoint-access-control-policies)：允许仅浏览器访问非托管设备中的特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-144">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="ca1e2-145">这将阻止编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-145">This prevents edit and download of files.</span></span> <span data-ttu-id="ca1e2-146">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-146">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="ca1e2-147">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="ca1e2-147">**Highly regulated**</span></span>|[<span data-ttu-id="ca1e2-148">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="ca1e2-148">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="ca1e2-149">在分配云应用时包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-149">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="ca1e2-150">[SharePoint 访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止从非托管设备访问特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-150">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="ca1e2-151">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-151">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="ca1e2-152">在 SharePoint 中使用应用强制限制</span><span class="sxs-lookup"><span data-stu-id="ca1e2-152">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="ca1e2-153">如果在 SharePoint 中实现访问控制，则必须在 Azure AD 中创建此条件访问策略，以告诉 Azure AD 强制执行在 SharePoint 中配置的策略。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-153">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="ca1e2-154">此策略适用于所有用户，但仅影响在 SharePoint 中创建访问控制时对使用 PowerShell 指定的网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-154">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="ca1e2-155">若要配置此策略，请参阅"阻止或限制对非托管设备的控制访问"中的"阻止或限制对特定 SharePoint 网站集或 OneDrive[帐户的访问"。](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="ca1e2-155">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="ca1e2-156">SharePoint 访问控制策略</span><span class="sxs-lookup"><span data-stu-id="ca1e2-156">SharePoint access control policies</span></span>

<span data-ttu-id="ca1e2-157">Microsoft 建议使用设备访问控制保护具有敏感和高度管控内容的 SharePoint 网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-157">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="ca1e2-158">为此，可创建一个策略，指定保护级别和要应用保护的网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-158">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="ca1e2-159">敏感网站：允许仅浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-159">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="ca1e2-160">这将阻止用户编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-160">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="ca1e2-161">高度管控站点：阻止非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-161">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="ca1e2-162">请参阅"阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户的访问"，了解非托管设备的控制 [访问权限](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-162">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="ca1e2-163">这些策略如何协同工作</span><span class="sxs-lookup"><span data-stu-id="ca1e2-163">How these policies work together</span></span>

<span data-ttu-id="ca1e2-164">了解 SharePoint 网站权限通常基于对网站的访问权限的业务需求，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-164">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="ca1e2-165">这些权限由网站所有者管理，并且可以是高度动态的。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-165">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="ca1e2-166">使用 SharePoint 设备访问策略可确保保护这些网站，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-166">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="ca1e2-167">下图举例说明了 SharePoint 设备访问策略如何保护用户对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-167">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="ca1e2-168">[![SharePoint 设备访问策略如何保护网站的示例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="ca1e2-168">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="ca1e2-169">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="ca1e2-169">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="ca1e2-170">尽管为他分配了基线条件访问策略，但可以使用敏感或高度管控的保护来访问 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-170">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="ca1e2-171">如果 <3>访问敏感或高度管控的网站，他就是使用电脑的成员，只要他的电脑合规，就授予他的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-171">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="ca1e2-172">如果他（允许基线用户使用）使用非托管电话访问敏感网站，则由于为此站点配置了设备访问策略，他将收到对敏感网站的仅浏览器访问权限。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-172">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="ca1e2-173">如果 James 访问高度管控的网站，他就是使用非托管电话的成员，则由于为此网站配置了访问策略，他将被阻止。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-173">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="ca1e2-174">他只能使用托管且合规的电脑访问此网站。</span><span class="sxs-lookup"><span data-stu-id="ca1e2-174">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="ca1e2-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ca1e2-175">Next step</span></span>

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="ca1e2-177">配置条件访问策略，用于：</span><span class="sxs-lookup"><span data-stu-id="ca1e2-177">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="ca1e2-178">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca1e2-178">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="ca1e2-179">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ca1e2-179">Exchange Online</span></span>](secure-email-recommended-policies.md)
