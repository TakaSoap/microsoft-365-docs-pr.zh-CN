---
title: 推荐的安全文档策略-适用于企业的 Microsoft 365 |Microsoft 文档
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 7e8104e234bd1b724bc62fb1a9b401ab83a2bcb4
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357523"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a><span data-ttu-id="a12b9-103">保护 SharePoint 网站和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="a12b9-103">Policy recommendations for securing SharePoint sites and files</span></span>

<span data-ttu-id="a12b9-104">本文介绍如何实施推荐的标识和设备访问策略来保护 SharePoint 和 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="a12b9-104">This article describes how to implement the recommended identity and device-access policies to protect SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="a12b9-105">本指南建立在 [通用标识和设备访问策略](identity-access-policies.md)之上。</span><span class="sxs-lookup"><span data-stu-id="a12b9-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="a12b9-106">这些建议基于三种不同的安全性和保护层，可根据您的需要进行应用： **比较基准**、 **敏感** 和 **高度管控** 的 SharePoint 文件。</span><span class="sxs-lookup"><span data-stu-id="a12b9-106">These recommendations are based on three different tiers of security and protection for SharePoint files that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="a12b9-107">您可以在 [概述](microsoft-365-policies-configurations.md)中了解有关这些安全层和推荐的客户端操作系统的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a12b9-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in [the overview](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="a12b9-108">除了实现本指南之外，请务必使用适当的保护措施配置 SharePoint 网站，包括为敏感和高度管控的内容设置适当的权限。</span><span class="sxs-lookup"><span data-stu-id="a12b9-108">In addition to implementing this guidance, be sure to configure SharePoint sites with the right amount of protection, including setting appropriate permissions for sensitive and highly-regulated content.</span></span>

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a><span data-ttu-id="a12b9-109">更新常见策略以包括 SharePoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a12b9-109">Updating common policies to include SharePoint and OneDrive for Business</span></span>

<span data-ttu-id="a12b9-110">若要保护 SharePoint 和 OneDrive 中的文件，下图说明了要从通用标识和设备访问策略中更新的策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-110">To protect files in SharePoint and OneDrive, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="a12b9-111">[![用于保护对团队及其依赖服务的访问权限的策略更新的摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span><span class="sxs-lookup"><span data-stu-id="a12b9-111">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)</span></span>

[<span data-ttu-id="a12b9-112">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="a12b9-112">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

<span data-ttu-id="a12b9-113">如果您在创建通用策略时包含 SharePoint，则只需创建新策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-113">If you included SharePoint when you created the common policies, you only need to create the new policies.</span></span> <span data-ttu-id="a12b9-114">对于条件访问策略，SharePoint 包括 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a12b9-114">For Conditional Access policies, SharePoint includes OneDrive.</span></span>

<span data-ttu-id="a12b9-115">新策略通过将特定访问要求应用于您指定的 SharePoint 网站来实现敏感和高度管控内容的设备保护。</span><span class="sxs-lookup"><span data-stu-id="a12b9-115">The new policies implement device protection for sensitive and highly-regulated content by applying specific access requirements to SharePoint sites that you specify.</span></span>

<span data-ttu-id="a12b9-116">下表列出了查看和更新或新建 SharePoint 时所需的策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-116">The following table lists the policies you either need to review and update or create new for SharePoint.</span></span> <span data-ttu-id="a12b9-117">常见策略链接到 [常见标识和设备访问策略](identity-access-policies.md) 文章中相关的配置说明。</span><span class="sxs-lookup"><span data-stu-id="a12b9-117">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="a12b9-118">保护级别</span><span class="sxs-lookup"><span data-stu-id="a12b9-118">Protection level</span></span>|<span data-ttu-id="a12b9-119">策略</span><span class="sxs-lookup"><span data-stu-id="a12b9-119">Policies</span></span>|<span data-ttu-id="a12b9-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="a12b9-120">More information</span></span>|
|---|---|---|
|<span data-ttu-id="a12b9-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="a12b9-121">**Baseline**</span></span>|[<span data-ttu-id="a12b9-122">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a12b9-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a12b9-123">在云应用的分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a12b9-123">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="a12b9-124">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="a12b9-124">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="a12b9-125">在云应用的分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a12b9-125">Include SharePoint in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="a12b9-126">应用应用数据保护策略</span><span class="sxs-lookup"><span data-stu-id="a12b9-126">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="a12b9-127">请确保所有建议的应用均包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="a12b9-127">Be sure all recommended apps are included in the list of apps.</span></span> <span data-ttu-id="a12b9-128">请务必为每个平台 (iOS、Android、Windows) 更新策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-128">Be sure to update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="a12b9-129">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="a12b9-129">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a12b9-130">在云应用列表中加入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a12b9-130">Include SharePoint in list of cloud apps.</span></span>|
||[<span data-ttu-id="a12b9-131">在 SharePoint 中使用应用强制实施限制</span><span class="sxs-lookup"><span data-stu-id="a12b9-131">Use app enforced restrictions in SharePoint</span></span>](#use-app-enforced-restrictions-in-sharepoint)|<span data-ttu-id="a12b9-132">添加此新策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-132">Add this new policy.</span></span> <span data-ttu-id="a12b9-133">这将告知 Azure Active Directory (Azure AD) 以使用 SharePoint 中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="a12b9-133">This tells Azure Active Directory (Azure AD) to use the settings specified in SharePoint.</span></span> <span data-ttu-id="a12b9-134">此策略适用于所有用户，但仅影响对 SharePoint 访问策略中包括的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="a12b9-134">This policy applies to all users, but only affects access to sites included in SharePoint access policies.</span></span>|
|<span data-ttu-id="a12b9-135">**敏感**</span><span class="sxs-lookup"><span data-stu-id="a12b9-135">**Sensitive**</span></span>|[<span data-ttu-id="a12b9-136">当登录风险为 *低*、*中* 或 *高* 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a12b9-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a12b9-137">在云应用的工作分配中加入 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a12b9-137">Include SharePoint in the assignments of cloud apps.</span></span>|
||[<span data-ttu-id="a12b9-138">需要符合要求 *的 pc 和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="a12b9-138">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="a12b9-139">将 SharePoint 包括在云应用列表中。</span><span class="sxs-lookup"><span data-stu-id="a12b9-139">Include SharePoint in the list of cloud apps.</span></span>|
||<span data-ttu-id="a12b9-140">[SharePoint 访问控制策略](#sharepoint-access-control-policies)：允许从非托管设备对特定 SharePoint 网站进行仅浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="a12b9-140">[SharePoint access control policy](#sharepoint-access-control-policies): Allow browser-only access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="a12b9-141">这将阻止文件的编辑和下载。</span><span class="sxs-lookup"><span data-stu-id="a12b9-141">This prevents edit and download of files.</span></span> <span data-ttu-id="a12b9-142">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="a12b9-142">Use PowerShell to specify sites.</span></span>|
|<span data-ttu-id="a12b9-143">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="a12b9-143">**Highly regulated**</span></span>|[<span data-ttu-id="a12b9-144">*始终* 要求进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a12b9-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a12b9-145">在云应用的分配中包括 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a12b9-145">Include SharePoint in the assignment of cloud apps.</span></span>|
||<span data-ttu-id="a12b9-146">[SharePoint 访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止来自非托管设备的对特定 SharePoint 网站的访问。</span><span class="sxs-lookup"><span data-stu-id="a12b9-146">[SharePoint access control policy](#use-app-enforced-restrictions-in-sharepoint): Block access to specific SharePoint sites from unmanaged devices.</span></span>|<span data-ttu-id="a12b9-147">使用 PowerShell 指定网站。</span><span class="sxs-lookup"><span data-stu-id="a12b9-147">Use PowerShell to specify sites.</span></span>|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a><span data-ttu-id="a12b9-148">在 SharePoint 中使用应用程序强制性限制</span><span class="sxs-lookup"><span data-stu-id="a12b9-148">Use app-enforced restrictions in SharePoint</span></span>

<span data-ttu-id="a12b9-149">如果在 SharePoint 中实现访问控制，则必须在 Azure AD 中创建此条件访问策略，以通知 Azure AD 强制实施您在 SharePoint 中配置的策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-149">If you implement access controls in SharePoint, you must create this Conditional Access policy in Azure AD to tell Azure AD to enforce the policies you configure in SharePoint.</span></span> <span data-ttu-id="a12b9-150">此策略适用于所有用户，但仅影响在 SharePoint 中创建访问控制时使用 PowerShell 指定的网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a12b9-150">This policy applies to all users, but only affects access to the sites you specify using PowerShell when you create the access controls in SharePoint.</span></span>

<span data-ttu-id="a12b9-151">若要配置此策略，请参阅 [控制来自非托管设备的访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)中的 "阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户的访问权限"。</span><span class="sxs-lookup"><span data-stu-id="a12b9-151">To configure this policy see "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="sharepoint-access-control-policies"></a><span data-ttu-id="a12b9-152">SharePoint 访问控制策略</span><span class="sxs-lookup"><span data-stu-id="a12b9-152">SharePoint access control policies</span></span>

<span data-ttu-id="a12b9-153">Microsoft 建议使用设备访问控制保护 SharePoint 网站中的内容与敏感和高度管控的内容。</span><span class="sxs-lookup"><span data-stu-id="a12b9-153">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="a12b9-154">为此，请创建指定保护级别的策略和要向其应用保护的网站。</span><span class="sxs-lookup"><span data-stu-id="a12b9-154">You do this by creating a policy that specifies the level of protection and the sites to apply the protection to.</span></span>

- <span data-ttu-id="a12b9-155">敏感网站：允许仅浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="a12b9-155">Sensitive sites: Allow browser-only access.</span></span> <span data-ttu-id="a12b9-156">这将阻止用户编辑和下载文件。</span><span class="sxs-lookup"><span data-stu-id="a12b9-156">This prevents users from editing and downloading files.</span></span>
- <span data-ttu-id="a12b9-157">高度管控的网站：阻止来自非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="a12b9-157">Highly regulated sites: Block access from unmanaged devices.</span></span>

<span data-ttu-id="a12b9-158">请参阅 [控制来自非托管设备的访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)中的 "阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户的访问"。</span><span class="sxs-lookup"><span data-stu-id="a12b9-158">See "Block or limit access to specific SharePoint site collections or OneDrive accounts" in [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

## <a name="how-these-policies-work-together"></a><span data-ttu-id="a12b9-159">这些策略如何协同工作</span><span class="sxs-lookup"><span data-stu-id="a12b9-159">How these policies work together</span></span>

<span data-ttu-id="a12b9-160">了解 SharePoint 网站权限通常基于访问网站的业务需求，了解这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="a12b9-160">It's important to understand that SharePoint site permissions are typically based on business need for access to sites.</span></span> <span data-ttu-id="a12b9-161">这些权限由网站所有者管理，并且可以是高度动态的。</span><span class="sxs-lookup"><span data-stu-id="a12b9-161">These permissions are managed by site owners and can be highly dynamic.</span></span> <span data-ttu-id="a12b9-162">使用 SharePoint 设备访问策略可确保对这些网站的保护，而不管是否将用户分配到与比较基准、敏感或高度管控保护相关联的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a12b9-162">Using SharePoint device access policies ensures protection to these sites, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="a12b9-163">下图提供了 SharePoint 设备访问策略如何保护对用户网站的访问的示例。</span><span class="sxs-lookup"><span data-stu-id="a12b9-163">The following illustration provides an example of how SharePoint device access policies protect access to sites for a user.</span></span>

<span data-ttu-id="a12b9-164">[![SharePoint 设备访问策略如何保护网站的示例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span><span class="sxs-lookup"><span data-stu-id="a12b9-164">[![Example of how SharePoint device access policies protect sites](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)</span></span>

[<span data-ttu-id="a12b9-165">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="a12b9-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

<span data-ttu-id="a12b9-166">James 具有已分配的基准条件访问策略，但可以向他授予对具有敏感保护或高度管控保护的 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a12b9-166">James has baseline Conditional Access policies assigned, but he can be given access to SharePoint sites with sensitive or highly-regulated protection.</span></span>

- <span data-ttu-id="a12b9-167">如果 James 访问敏感或高度管控的站点，他是使用他的电脑的成员，那么只要他的 PC 符合要求，就会向其授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="a12b9-167">If James accesses a sensitive or highly-regulated site he is a member of using his PC, his access is granted as long as his PC is compliant.</span></span>
- <span data-ttu-id="a12b9-168">如果 James 访问敏感站点，他是使用他的非托管电话的成员，这对于基准用户是允许的，他将收到对敏感网站的仅浏览器访问权限，这是由于为此网站配置的设备访问策略。</span><span class="sxs-lookup"><span data-stu-id="a12b9-168">If James accesses a sensitive site he is a member of using his unmanaged phone, which is allowed for baseline users, he will receive browser-only access to the sensitive site due to the device access policy configured for this site.</span></span>
- <span data-ttu-id="a12b9-169">如果 James 访问高度管控的网站，他是使用其非托管手机的成员，则会由于为此网站配置的访问策略而被阻止。</span><span class="sxs-lookup"><span data-stu-id="a12b9-169">If James accesses a highly regulated site he is a member of using his unmanaged phone, he will be blocked due to the access policy configured for this site.</span></span> <span data-ttu-id="a12b9-170">他只能使用其受管理且合规的电脑来访问此网站。</span><span class="sxs-lookup"><span data-stu-id="a12b9-170">He can only access this site using his managed and compliant PC.</span></span>

## <a name="next-step"></a><span data-ttu-id="a12b9-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a12b9-171">Next step</span></span>

![步骤4： Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="a12b9-173">为以下项配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="a12b9-173">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="a12b9-174">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a12b9-174">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="a12b9-175">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a12b9-175">Exchange Online</span></span>](secure-email-recommended-policies.md)
