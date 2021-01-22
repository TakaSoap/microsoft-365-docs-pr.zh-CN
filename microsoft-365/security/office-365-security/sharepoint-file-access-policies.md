---
title: 建议的安全文档策略 - Microsoft 365 企业版|Microsoft Docs
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: a3485896cae5e41808cfd16a77d484a35c768a6d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931766"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="5faed-103">保护 SharePoint 网站和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="5faed-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="5faed-104">本文介绍如何实施推荐的标识和设备访问策略来保护 SharePoint 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="5faed-104">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="5faed-105">本指南基于通用 [标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5faed-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="5faed-106">这些建议基于 SharePoint 文件的三个不同安全和保护层，这些层可以基于你的需求粒度应用：**基线**、敏感和 **高度管控**。 </span><span class="sxs-lookup"><span data-stu-id="5faed-106">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="5faed-107">你可以了解有关这些安全层以及推荐的客户端操作系统（概述中这些建议所引用） [的更多信息](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="5faed-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="5faed-108">除了实施本指南之外，请确保使用适当保护量配置 SharePoint 网站，包括为敏感和高度管控内容设置适当的权限。</span><span class="sxs-lookup"><span data-stu-id="5faed-108">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="5faed-109">更新常见策略以包括 SharePoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="5faed-109">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="5faed-110">若要保护 SharePoint 和 OneDrive 中的文件，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-110">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="5faed-111">[![用于保护对 Teams 及其从属服务的访问权限的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="5faed-111">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="5faed-112">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="5faed-112">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="5faed-113">如果在创建常见策略时包含 SharePoint，则只需创建新策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-113">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="5faed-114">对于条件访问策略，SharePoint 包括 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="5faed-114">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="5faed-115">新策略通过向指定的 SharePoint 网站应用特定的访问要求，为敏感和高度管控内容实现设备保护。</span><span class="sxs-lookup"><span data-stu-id="5faed-115">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="5faed-116">下表列出了查看和更新 SharePoint 或创建新策略所需的策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-116">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="5faed-117">常见策略链接到通用标识和设备访问策略文章中的 [关联配置](identity-access-policies.md) 说明。</span><span class="sxs-lookup"><span data-stu-id="5faed-117">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="5faed-118">保护级别</span><span class="sxs-lookup"><span data-stu-id="5faed-118">Protection level</span></span>|<span data-ttu-id="5faed-119">策略</span><span class="sxs-lookup"><span data-stu-id="5faed-119">Policies</span></span>|<span data-ttu-id="5faed-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="5faed-120">More information</span></span>|
|---|---|---|
|<span data-ttu-id="5faed-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="5faed-121">**Baseline**</span></span>|[<span data-ttu-id="5faed-122">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="5faed-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="5faed-123">在云应用分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="5faed-123">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="5faed-124">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="5faed-124">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="5faed-125">在云应用分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="5faed-125">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="5faed-126">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="5faed-126">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="5faed-127">请确保所有推荐的应用都包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="5faed-127">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="5faed-128">请务必为 iOS、Android、Windows) 的每个平台更新 (策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-128">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="5faed-129">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="5faed-129">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="5faed-130">将 SharePoint 包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="5faed-130">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="5faed-131">在 SharePoint 中使用应用强制限制</span><span class="sxs-lookup"><span data-stu-id="5faed-131">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="5faed-132">添加新策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-132">Add this new policy.</span></span> <span data-ttu-id="5faed-133">这将告知 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="5faed-133">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="5faed-134">此策略适用于所有用户，但仅影响对 SharePoint 访问策略中包含的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="5faed-134">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="5faed-135">**敏感**</span><span class="sxs-lookup"><span data-stu-id="5faed-135">**Sensitive**</span></span>|[<span data-ttu-id="5faed-136">当登录风险较低、中等或高时需要MFA </span><span class="sxs-lookup"><span data-stu-id="5faed-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="5faed-137">在云应用分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="5faed-137">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="5faed-138">要求 *兼容电脑和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="5faed-138">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="5faed-139">将 SharePoint 包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="5faed-139">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="5faed-140">[SharePoint 访问控制策略](#sharepoint-access-control-policies)：允许仅浏览器访问非托管设备中的特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-140">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="5faed-141">这将阻止编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="5faed-141">This prevents edit and download of files.</span></span> <span data-ttu-id="5faed-142">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-142">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="5faed-143">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="5faed-143">**Highly regulated**</span></span>|[<span data-ttu-id="5faed-144">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="5faed-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="5faed-145">在云应用分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="5faed-145">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="5faed-146">[SharePoint 访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止从非托管设备访问特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-146">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="5faed-147">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-147">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="5faed-148">在 SharePoint 中使用应用强制限制</span><span class="sxs-lookup"><span data-stu-id="5faed-148">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="5faed-149">如果在 SharePoint 中实现访问控制，则必须在 Azure AD 中创建此条件访问策略，以告诉 Azure AD 强制实施在 SharePoint 中配置的策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-149">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="5faed-150">此策略适用于所有用户，但仅在 SharePoint 中创建访问控制时影响对使用 PowerShell 指定的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="5faed-150">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="5faed-151">若要配置此策略，请参阅"阻止或限制对非托管设备的控制访问"中的"阻止或限制对特定 SharePoint 网站集或 OneDrive[帐户的访问"。](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="5faed-151">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="5faed-152">SharePoint 访问控制策略</span><span class="sxs-lookup"><span data-stu-id="5faed-152">SharePoint access control policies</span></span>

<span data-ttu-id="5faed-153">Microsoft 建议使用设备访问控制保护具有敏感和高度管控内容的 SharePoint 网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="5faed-153">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="5faed-154">为此，请创建一个策略，指定保护级别和要应用保护的网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-154">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="5faed-155">敏感网站：允许仅浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="5faed-155">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="5faed-156">这将阻止用户编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="5faed-156">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="5faed-157">高度管控网站：阻止来自非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="5faed-157">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="5faed-158">请参阅"阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户的访问"中的"控制非[托管设备的访问"。](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)</span><span class="sxs-lookup"><span data-stu-id="5faed-158">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="5faed-159">这些策略如何协同工作</span><span class="sxs-lookup"><span data-stu-id="5faed-159">How these policies work together</span></span>

<span data-ttu-id="5faed-160">了解 SharePoint 网站权限通常基于访问网站的业务需求，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="5faed-160">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="5faed-161">这些权限由网站所有者管理，并且可以是高度动态的。</span><span class="sxs-lookup"><span data-stu-id="5faed-161">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="5faed-162">使用 SharePoint 设备访问策略可确保保护这些网站，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="5faed-162">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="5faed-163">下图提供了 SharePoint 设备访问策略如何保护用户访问网站的示例。</span><span class="sxs-lookup"><span data-stu-id="5faed-163">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="5faed-164">[![SharePoint 设备访问策略如何保护网站的示例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="5faed-164">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="5faed-165">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="5faed-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="5faed-166">尽管为他分配了基准条件访问策略，但可以使用敏感或高度管控保护来访问 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-166">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="5faed-167">如果他访问的敏感或高度管控网站是使用电脑的成员，则只要其电脑合规，就授予其访问权限。</span><span class="sxs-lookup"><span data-stu-id="5faed-167">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="5faed-168">如果他访问的敏感网站是使用其非托管电话的成员（允许基线用户使用）的，则由于为此站点配置了设备访问策略，他将收到对敏感网站的仅浏览器访问权限。</span><span class="sxs-lookup"><span data-stu-id="5faed-168">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="5faed-169">如果 James 访问高度管控的网站，而他也是使用非托管电话的成员，则他将被阻止，因为此站点配置了访问策略。</span><span class="sxs-lookup"><span data-stu-id="5faed-169">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="5faed-170">他只能使用自己托管且合规的电脑访问此网站。</span><span class="sxs-lookup"><span data-stu-id="5faed-170">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="5faed-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5faed-171">Next step</span></span>

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="5faed-173">为：</span><span class="sxs-lookup"><span data-stu-id="5faed-173">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="5faed-174">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5faed-174">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="5faed-175">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5faed-175">Exchange Online</span></span>](secure-email-recommended-policies.md)
