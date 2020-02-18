---
title: 保护 Microsoft Teams 中的文件
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 摘要：用于保护 Microsoft Teams 中文件的配置建议。
ms.openlocfilehash: 82c55affc8384c04e0595f82d21c7e3532b5cb0e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088122"
---
# <a name="secure-files-in-microsoft-teams"></a><span data-ttu-id="e27fa-103">保护 Microsoft Teams 中的文件</span><span class="sxs-lookup"><span data-stu-id="e27fa-103">Secure files in Microsoft Teams</span></span>

<span data-ttu-id="e27fa-104">本文为如何在 Microsoft Teams 中配置团队及其基础 SharePoint 网站以实现通过轻松协作权衡安全性的文件保护提供了相关建议。</span><span class="sxs-lookup"><span data-stu-id="e27fa-104">This article provides recommendations for configuring teams in Microsoft Teams and their underlying SharePoint sites for file protection that balances security with ease of collaboration.</span></span> <span data-ttu-id="e27fa-105">本文定义了四个不同的配置，首先介绍的是具有最开放的共享策略的组织内的公共网站。</span><span class="sxs-lookup"><span data-stu-id="e27fa-105">This article defines four different configurations, starting with a public site within your organization with the most open sharing policies.</span></span> <span data-ttu-id="e27fa-106">每个额外配置均表示有意义的保护设置，但对 Teams 中存储的文件的访问和协作限定为一组相关团队成员。</span><span class="sxs-lookup"><span data-stu-id="e27fa-106">Each additional configuration represents a meaningful step up in protection, but the ability to access and collaborate on files stored within Teams is reduced to the relevant set of team members.</span></span> <span data-ttu-id="e27fa-107">使用这些建议作为起点并调整配置，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="e27fa-107">Use these recommendations as a starting point and adjust the configurations to meet the needs of your organization.</span></span>

<span data-ttu-id="e27fa-108">本文中的配置符合 Microsoft 针对数据、标识和设备的三层保护的建议：</span><span class="sxs-lookup"><span data-stu-id="e27fa-108">The configurations in this article align with Microsoft's recommendations for three tiers of protection for data, identities, and devices:</span></span>

- <span data-ttu-id="e27fa-109">基线保护</span><span class="sxs-lookup"><span data-stu-id="e27fa-109">Baseline protection</span></span>

- <span data-ttu-id="e27fa-110">敏感保护</span><span class="sxs-lookup"><span data-stu-id="e27fa-110">Sensitive protection</span></span>

- <span data-ttu-id="e27fa-111">高度机密保护</span><span class="sxs-lookup"><span data-stu-id="e27fa-111">Highly confidential protection</span></span>

<span data-ttu-id="e27fa-112">有关这些保护层以及针对每层建议的功能的详细信息，请参阅以下资源。</span><span class="sxs-lookup"><span data-stu-id="e27fa-112">For more information about these tiers and capabilities recommended for each tier, see the following resources.</span></span>

- [<span data-ttu-id="e27fa-113">Office 365 的标识和设备保护</span><span class="sxs-lookup"><span data-stu-id="e27fa-113">Identity and Device Protection for Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [<span data-ttu-id="e27fa-114">Office 365 中的文件保护解决方案</span><span class="sxs-lookup"><span data-stu-id="e27fa-114">File Protection Solutions in Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="capability-overview"></a><span data-ttu-id="e27fa-115">功能概述</span><span class="sxs-lookup"><span data-stu-id="e27fa-115">Capability overview</span></span>

<span data-ttu-id="e27fa-116">针对各种 Microsoft 365 功能的受保护团队网站绘制的建议。</span><span class="sxs-lookup"><span data-stu-id="e27fa-116">Recommendations for secured teams draw on a variety of Microsoft 365 capabilities.</span></span> <span data-ttu-id="e27fa-117">下图显示了建议配置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-117">The following illustration shows the recommended configurations.</span></span>

![适用于团队的推荐配置](../../media/secure-team-configurations.png)

<span data-ttu-id="e27fa-119">如图所示：</span><span class="sxs-lookup"><span data-stu-id="e27fa-119">As illustrated:</span></span>

- <span data-ttu-id="e27fa-120">基线保护同时包括公共团队和私人团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-120">Baseline protection includes a public team and private team.</span></span> <span data-ttu-id="e27fa-121">组织中的任何人均可发现和访问公共团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-121">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="e27fa-122">只有团队成员可以发现和访问私人团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-122">Private teams can only be discovered and accessed by members of the team.</span></span> <span data-ttu-id="e27fa-123">这两种配置均允许共享基础 SharePoint 网站（这些网站上的文件存储在团队组之外）。</span><span class="sxs-lookup"><span data-stu-id="e27fa-123">Both of these configurations allow for sharing of the underlying SharePoint site on which files are stored outside the team group.</span></span>

- <span data-ttu-id="e27fa-124">有关敏感和高度机密保护的团队是私人团队，在这些团队中，对基础网站的共享和访问请求受到限制。</span><span class="sxs-lookup"><span data-stu-id="e27fa-124">Teams for sensitive and highly confidential protection are private teams in which sharing and the requesting of access for the underlying site is limited.</span></span>

- <span data-ttu-id="e27fa-125">[保留标签](../../compliance/labels.md)提供了一种对基础 SharePoint 网站内的文件进行分类的方法。</span><span class="sxs-lookup"><span data-stu-id="e27fa-125">[Retention labels](../../compliance/labels.md) provide a way to classify files within the underlying SharePoint sites.</span></span> <span data-ttu-id="e27fa-126">每个基础 SharePoint 网站均被配置为使用默认保留标签自动标记文档库中的文件。</span><span class="sxs-lookup"><span data-stu-id="e27fa-126">Each of the underlying SharePoint sites are configured to automatically label files in document libraries with a default retention label.</span></span> <span data-ttu-id="e27fa-127">与四个团队配置相对应，此示例中的标签分别为内部公开、私人、敏感和高度机密。</span><span class="sxs-lookup"><span data-stu-id="e27fa-127">Corresponding to the four team configurations, the labels in this example are Internal Public, Private, Sensitive, and Highly Confidential.</span></span> <span data-ttu-id="e27fa-128">用户可以更改单个文件中的标签，但此配置可确保所有文件均接收默认的标签。</span><span class="sxs-lookup"><span data-stu-id="e27fa-128">Users can change the labels on the individual files, but this configuration ensures all files receive a default label.</span></span>

- <span data-ttu-id="e27fa-129">为敏感和高度机密保留标签配置[数据丢失防护](../../compliance/data-loss-prevention-policies.md) (DLP) 策略，在其试图向组织外部发送这些类型的文件时警告或阻止用户。</span><span class="sxs-lookup"><span data-stu-id="e27fa-129">[Data loss prevention](../../compliance/data-loss-prevention-policies.md) (DLP) policies are configured for the Sensitive and Highly Confidential retention labels to either warn or prevent users when they attempt to send these types of files outside the organization.</span></span>

- <span data-ttu-id="e27fa-130">如果方案需要，可以使用[敏感度标签](../../compliance/sensitivity-labels.md)来通过加密和权限来保护高度机密文件。</span><span class="sxs-lookup"><span data-stu-id="e27fa-130">If needed for your scenario, you can use [sensitivity labels](../../compliance/sensitivity-labels.md) to protect highly confidential files with encryption and permissions.</span></span> <span data-ttu-id="e27fa-131">对于 Azure 信息保护客户，你可以在 Microsoft 365 合规中心内使用 Azure 信息保护标签。如果你选择执行其他配置或高级配置，这些标签便会与 Azure 门户同步。</span><span class="sxs-lookup"><span data-stu-id="e27fa-131">For Azure Information Protection customers, you can use your Azure Information Protection labels in the Microsoft 365 compliance center, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration.</span></span> <span data-ttu-id="e27fa-132">Azure 信息保护标签和 Office 365 敏感度标签彼此完全相互兼容。</span><span class="sxs-lookup"><span data-stu-id="e27fa-132">Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.</span></span> <span data-ttu-id="e27fa-133">也就是说，例如，如果内容已有 Azure 信息保护标签，无需重新对此内容进行分类或标记。</span><span class="sxs-lookup"><span data-stu-id="e27fa-133">This means, for example, if you have content labeled by Azure Information Protection, you won't need to reclassify or relabel your content.</span></span> <span data-ttu-id="e27fa-134">并非所有客户都需要这一级别的保护。</span><span class="sxs-lookup"><span data-stu-id="e27fa-134">Not all customers need this level of protection.</span></span>

## <a name="organization-wide-settings-for-sharepoint-and-onedrive"></a><span data-ttu-id="e27fa-135">SharePoint 和 OneDrive 的全组织设置</span><span class="sxs-lookup"><span data-stu-id="e27fa-135">Organization-wide settings for SharePoint and OneDrive</span></span>

<span data-ttu-id="e27fa-136">SharePoint 和 OneDrive 包括影响所有网站和用户的组织范围内设置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-136">SharePoint and OneDrive include organization-wide settings that affect all sites and users.</span></span> <span data-ttu-id="e27fa-137">其中一些设置也可在网站级别进行调整，使其更具有（而不是更不具有）限制性。</span><span class="sxs-lookup"><span data-stu-id="e27fa-137">Some of these settings can also be adjusted at the site level to be more restrictive (but not less).</span></span> <span data-ttu-id="e27fa-138">本部分讨论影响安全性和协作的租户范围内设置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-138">This section discusses tenant-wide settings that affect security and collaboration.</span></span>

### <a name="sharing"></a><span data-ttu-id="e27fa-139">共享</span><span class="sxs-lookup"><span data-stu-id="e27fa-139">Sharing</span></span>

<span data-ttu-id="e27fa-140">对于此解决方案，建议使用以下组织范围内设置：</span><span class="sxs-lookup"><span data-stu-id="e27fa-140">For this solution, we recommend the following organization-wide settings:</span></span>

- <span data-ttu-id="e27fa-141">保留允许所有与所有帐户类型共享（包括匿名共享）的默认共享策略。</span><span class="sxs-lookup"><span data-stu-id="e27fa-141">Keep the default sharing policy that allows all sharing with all account types, including anonymous sharing.</span></span>

- <span data-ttu-id="e27fa-142">如果需要，请将匿名链接设置为过期。</span><span class="sxs-lookup"><span data-stu-id="e27fa-142">Set anonymous links to expire, if desired.</span></span>

- <span data-ttu-id="e27fa-p107">将共享的默认链接类型更改为“内部”。 这有助于防止数据意外泄露到组织外部。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p107">Change the default link type for sharing to Internal. This helps prevent accidental data leakage outside your organization.</span></span>

<span data-ttu-id="e27fa-145">虽然允许外部共享可能看起来有悖常理，但相较于通过电子邮件发送文件，此方法可更好地控制文件共享。</span><span class="sxs-lookup"><span data-stu-id="e27fa-145">While it might seem counterintuitive to allow external sharing, this approach provides more control over file sharing compared to sending files in email.</span></span> <span data-ttu-id="e27fa-146">SharePoint 和 Outlook 彼此协作，提供安全的文件协作。</span><span class="sxs-lookup"><span data-stu-id="e27fa-146">SharePoint and Outlook work together to provide secure collaboration on files.</span></span>

- <span data-ttu-id="e27fa-147">默认情况下，Outlook 共享文件链接，而不是通过电子邮件发送文件。</span><span class="sxs-lookup"><span data-stu-id="e27fa-147">By default, Outlook shares a link to a file instead of sending the file in email.</span></span>

- <span data-ttu-id="e27fa-148">SharePoint 和 OneDrive 可轻松实现与组织内外部的参与者共享文件链接</span><span class="sxs-lookup"><span data-stu-id="e27fa-148">SharePoint and OneDrive make it easy to share links to files with contributors who are both inside and outside your organization</span></span>

<span data-ttu-id="e27fa-p109">用户还可进行控制，帮助管理外部共享。 例如，你能够：</span><span class="sxs-lookup"><span data-stu-id="e27fa-p109">You also have controls to help govern external sharing. For example, you can:</span></span>

- <span data-ttu-id="e27fa-151">禁用匿名来宾链接。</span><span class="sxs-lookup"><span data-stu-id="e27fa-151">Disable an anonymous guest link.</span></span>

- <span data-ttu-id="e27fa-152">撤销用户对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e27fa-152">Revoke user access to a site.</span></span>

- <span data-ttu-id="e27fa-153">查看谁有权访问特定网站或文档。</span><span class="sxs-lookup"><span data-stu-id="e27fa-153">See who has access to a specific site or document.</span></span>

- <span data-ttu-id="e27fa-154">将匿名共享链接设置为过期（租户设置）。</span><span class="sxs-lookup"><span data-stu-id="e27fa-154">Set anonymous sharing links to expire (tenant setting).</span></span>

- <span data-ttu-id="e27fa-155">限制可与之共享的组织外部用户（租户设置）。</span><span class="sxs-lookup"><span data-stu-id="e27fa-155">Limit who can share outside your organization (tenant setting).</span></span>

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a><span data-ttu-id="e27fa-156">配合使用外部共享与数据丢失预防 (DLP)</span><span class="sxs-lookup"><span data-stu-id="e27fa-156">Use external sharing together with data loss prevention (DLP)</span></span>

<span data-ttu-id="e27fa-p110">如果不允许外部共享，则有业务需求的用户需要寻找备用工具和方法。Microsoft 建议结合使用外部共享和 DLP 策略来保护敏感和高度机密的文件。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p110">If you don't allow external sharing, users with a business need will find alternate tools and methods. Microsoft recommends you combine external sharing with DLP policies to protect sensitive and highly confidential files.</span></span>

### <a name="device-access-settings"></a><span data-ttu-id="e27fa-159">设备访问设置</span><span class="sxs-lookup"><span data-stu-id="e27fa-159">Device access settings</span></span>

<span data-ttu-id="e27fa-160">SharePoint 和 OneDrive 的设备访问设置可确定是否已将访问权限限制为仅限浏览器（不能下载文件）或访问被阻止。</span><span class="sxs-lookup"><span data-stu-id="e27fa-160">Device access settings for SharePoint and OneDrive let you determine whether access is limited to browser only (files can't be downloaded) or if access is blocked.</span></span> <span data-ttu-id="e27fa-161">有关详细信息，请参阅[控制非托管设备的访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="e27fa-161">For more information, see [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

<span data-ttu-id="e27fa-162">若要在 Azure Active Directory 中使用具有推荐条件访问策略的设备访问设置，请参阅[用于保护 SharePoint 网站和文件的策略建议](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="e27fa-162">To use device access settings with recommended conditional access policies in Azure Active Directory, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

<span data-ttu-id="e27fa-163">访问这些设置，确定是否要更改 OneDrive 网站的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-163">Visit these settings to decide if you want to change the default settings for OneDrive sites.</span></span> <span data-ttu-id="e27fa-164">目前，共享和设备访问设置与 SharePoint 管理中心重复，并适用于这两个环境。</span><span class="sxs-lookup"><span data-stu-id="e27fa-164">Currently, the sharing and device access settings are duplicated from the SharePoint admin center and apply to both environments.</span></span>

## <a name="team-and-sharepoint-site-configuration"></a><span data-ttu-id="e27fa-165">团队和 SharePoint 网站配置</span><span class="sxs-lookup"><span data-stu-id="e27fa-165">Team and SharePoint site configuration</span></span>

<span data-ttu-id="e27fa-166">下表总结了本文前面所述的每个团队及其基础 SharePoint 网站的配置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-166">The following table summarizes the configuration for each of the teams and their underlying SharePoint site described earlier in this article.</span></span> <span data-ttu-id="e27fa-167">使用这些配置作为起点建议并调整网站类型和配置，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="e27fa-167">Use these configurations as starting point recommendations and adjust the site types and configurations to meet the needs of your organization.</span></span> <span data-ttu-id="e27fa-168">不是每个组织都需要每种类型的团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-168">Not every organization needs every type of team.</span></span> <span data-ttu-id="e27fa-169">只有少许组织需要具有高度机密保护的团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-169">Only a small number of organizations require teams with highly confidential protection.</span></span>

||||||
|:-----|:-----|:-----|:-----|:-----|
||<span data-ttu-id="e27fa-170">**基线保护 #1**</span><span class="sxs-lookup"><span data-stu-id="e27fa-170">**Baseline protection #1**</span></span>|<span data-ttu-id="e27fa-171">**基线保护 #2**</span><span class="sxs-lookup"><span data-stu-id="e27fa-171">**Baseline protection #2**</span></span>|<span data-ttu-id="e27fa-172">**敏感保护**</span><span class="sxs-lookup"><span data-stu-id="e27fa-172">**Sensitive protection**</span></span>|<span data-ttu-id="e27fa-173">**高度机密**</span><span class="sxs-lookup"><span data-stu-id="e27fa-173">**Highly confidential**</span></span>|
|<span data-ttu-id="e27fa-174">Description</span><span class="sxs-lookup"><span data-stu-id="e27fa-174">Description</span></span>|<span data-ttu-id="e27fa-175">在组织内公开发现和协作的公共团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-175">Public team with open discovery and collaboration within the organization.</span></span>|<span data-ttu-id="e27fa-176">在组外允许共享基础 SharePoint 网站的私人团队。</span><span class="sxs-lookup"><span data-stu-id="e27fa-176">Private team with sharing of the underlying SharePoint site allowed outside the group.</span></span>|<span data-ttu-id="e27fa-177">私人团队，但仅允许网站成员共享基础 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="e27fa-177">Private team, but sharing of the underlying SharePoint site is only allowed to members of the site.</span></span> <span data-ttu-id="e27fa-178">DLP 在用户试图向组织外发送文件时警告用户。</span><span class="sxs-lookup"><span data-stu-id="e27fa-178">DLP warns users when attempting to send files outside the organization.</span></span>|<span data-ttu-id="e27fa-179">私人团队，其中包含文件加密的敏感标签和浏览文件的权限。</span><span class="sxs-lookup"><span data-stu-id="e27fa-179">Private team with sensitivity labels for file encryption and permissions that travel with the file.</span></span> <span data-ttu-id="e27fa-180">DLP 阻止用户向组织外发送文件。</span><span class="sxs-lookup"><span data-stu-id="e27fa-180">DLP prevents users from sending files outside the organization.</span></span>|
|<span data-ttu-id="e27fa-181">专用或公用团队网站</span><span class="sxs-lookup"><span data-stu-id="e27fa-181">Private or public team site</span></span>|<span data-ttu-id="e27fa-182">公用</span><span class="sxs-lookup"><span data-stu-id="e27fa-182">Public</span></span>|<span data-ttu-id="e27fa-183">Private</span><span class="sxs-lookup"><span data-stu-id="e27fa-183">Private</span></span>|<span data-ttu-id="e27fa-184">Private</span><span class="sxs-lookup"><span data-stu-id="e27fa-184">Private</span></span>|<span data-ttu-id="e27fa-185">Private</span><span class="sxs-lookup"><span data-stu-id="e27fa-185">Private</span></span>|
|<span data-ttu-id="e27fa-186">谁可以访问？</span><span class="sxs-lookup"><span data-stu-id="e27fa-186">Who has access?</span></span>|<span data-ttu-id="e27fa-187">组织中的每个人（包括 B2B 用户）。</span><span class="sxs-lookup"><span data-stu-id="e27fa-187">Everybody in the organization, including B2B users.</span></span>|<span data-ttu-id="e27fa-188">仅限网站成员。</span><span class="sxs-lookup"><span data-stu-id="e27fa-188">Members of the site only.</span></span> <span data-ttu-id="e27fa-189">其他人可以请求访问。</span><span class="sxs-lookup"><span data-stu-id="e27fa-189">Others can request access.</span></span>|<span data-ttu-id="e27fa-190">仅限团队成员。</span><span class="sxs-lookup"><span data-stu-id="e27fa-190">Members of the team only.</span></span> <span data-ttu-id="e27fa-191">其他人可以请求访问团队所有者批准的基础网站。</span><span class="sxs-lookup"><span data-stu-id="e27fa-191">Others can request access to the underlying site, which is approved by a team owner.</span></span>|<span data-ttu-id="e27fa-192">仅限成员。</span><span class="sxs-lookup"><span data-stu-id="e27fa-192">Members only.</span></span> <span data-ttu-id="e27fa-193">其他人无法请求访问基础网站。</span><span class="sxs-lookup"><span data-stu-id="e27fa-193">Others cannot request access to the underlying site.</span></span>|
|<span data-ttu-id="e27fa-194">网站级共享控制</span><span class="sxs-lookup"><span data-stu-id="e27fa-194">Site-level sharing controls</span></span>|<span data-ttu-id="e27fa-p119">允许与任何人共享。默认设置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p119">Sharing allowed with anybody. Default settings.</span></span>|<span data-ttu-id="e27fa-p120">允许与任何人共享。默认设置。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p120">Sharing allowed with anybody. Default settings.</span></span>|<span data-ttu-id="e27fa-199">成员无法共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e27fa-199">Members cannot share access to the site.</span></span> <br/> <span data-ttu-id="e27fa-200">非成员可请求访问网站，但需要由团队的组所有者来处理这些请求。</span><span class="sxs-lookup"><span data-stu-id="e27fa-200">Non-members can request access to the site, but these requests need to be addressed by a group owner for the team.</span></span>|<span data-ttu-id="e27fa-201">成员无法共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e27fa-201">Members cannot share access to the site.</span></span> <br/> <span data-ttu-id="e27fa-202">非成员无法请求访问网站或其内容。</span><span class="sxs-lookup"><span data-stu-id="e27fa-202">Non-members cannot request access to the site or its contents.</span></span>|
|<span data-ttu-id="e27fa-203">网站级别的设备访问控制</span><span class="sxs-lookup"><span data-stu-id="e27fa-203">Site-level device access controls</span></span>|<span data-ttu-id="e27fa-204">无任何额外控制。</span><span class="sxs-lookup"><span data-stu-id="e27fa-204">No additional controls.</span></span>|<span data-ttu-id="e27fa-205">无任何额外控制。</span><span class="sxs-lookup"><span data-stu-id="e27fa-205">No additional controls.</span></span>|<span data-ttu-id="e27fa-p121">防止用户将文件下载到不符合或未加入域的设备。使所有其他设备仅限浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p121">Prevents users from downloading files to non-compliant or non-domain joined devices. This allows browser-only access from all other devices.</span></span>|<span data-ttu-id="e27fa-208">阻止将文件下载到不符合或未加入域的设备。</span><span class="sxs-lookup"><span data-stu-id="e27fa-208">Block downloading of files to non-compliant or non-domain joined devices.</span></span>|
|<span data-ttu-id="e27fa-209">保留标签</span><span class="sxs-lookup"><span data-stu-id="e27fa-209">Retention labels</span></span>|<span data-ttu-id="e27fa-210">内部公用</span><span class="sxs-lookup"><span data-stu-id="e27fa-210">Internal Public</span></span>|<span data-ttu-id="e27fa-211">Private</span><span class="sxs-lookup"><span data-stu-id="e27fa-211">Private</span></span>|<span data-ttu-id="e27fa-212">敏感</span><span class="sxs-lookup"><span data-stu-id="e27fa-212">Sensitive</span></span>|<span data-ttu-id="e27fa-213">高度机密</span><span class="sxs-lookup"><span data-stu-id="e27fa-213">Highly Confidential</span></span>|
|<span data-ttu-id="e27fa-214">DLP 策略</span><span class="sxs-lookup"><span data-stu-id="e27fa-214">DLP policies</span></span>|||<span data-ttu-id="e27fa-215">在用户向组织外发送标记为“敏感”的文件时进行警告。</span><span class="sxs-lookup"><span data-stu-id="e27fa-215">Warn users when sending files that are labeled as Sensitive outside the organization.</span></span> <br/> <span data-ttu-id="e27fa-216">要阻止外部共享敏感数据类型，如信用卡号或其他个人数据，可以针对这些数据类型（包括所配置的自定义数据类型）配置其他 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e27fa-216">To block external sharing of sensitive data types, such as credit card numbers or other personal data, you can configure additional DLP policies for these data types (including custom data types you configure).</span></span>|<span data-ttu-id="e27fa-p122">阻止用户向组织外发送标记为“高度机密”的文件。允许用户通过提供他们与之共享的对象等理由来替代此行为。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p122">Block users from sending files that are labeled as highly confidential outside organization. Allow users to override this by providing justification, including who they are sharing the file with.</span></span>|
|<span data-ttu-id="e27fa-219">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="e27fa-219">Sensitivity labels</span></span>||||<span data-ttu-id="e27fa-220">使用敏感度标签加密文件和授予对文件的权限。</span><span class="sxs-lookup"><span data-stu-id="e27fa-220">Use sensitivity labels to encrypt and grant permissions to files.</span></span> <span data-ttu-id="e27fa-221">此保护一直伴随文件，以防它们从基础 SharePoint 网站泄漏。</span><span class="sxs-lookup"><span data-stu-id="e27fa-221">This protection travels with the files in case they are leaked from the underlying SharePoint site.</span></span>|

<span data-ttu-id="e27fa-222">有关在此解决方案中部署四种不同团队的步骤，请参阅[部署团队以实现文件的三层保护](deploy-teams-three-tiers.md)。</span><span class="sxs-lookup"><span data-stu-id="e27fa-222">For the steps to deploy the four different types of teams in this solution, see [Deploy teams for three tiers of protection for files](deploy-teams-three-tiers.md).</span></span>

## <a name="office-365-retention-labels"></a><span data-ttu-id="e27fa-223">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="e27fa-223">Office 365 retention labels</span></span>

<span data-ttu-id="e27fa-224">对于具有敏感数据的环境，建议使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e27fa-224">Using retention labels is recommended for environments with sensitive data.</span></span> <span data-ttu-id="e27fa-225">在配置和发布保留标签后：</span><span class="sxs-lookup"><span data-stu-id="e27fa-225">After you configure and publish retention labels:</span></span>

- <span data-ttu-id="e27fa-226">可将默认标签应用于团队的基础 SharePoint 网站中的文档库，以便团队“文件”\*\*\*\* 部分中的所有文档都获取默认标签。</span><span class="sxs-lookup"><span data-stu-id="e27fa-226">You can apply a default label to a document library in the underlying SharePoint site for a team, so that all documents in the **Files** section of the team get the default label.</span></span>

- <span data-ttu-id="e27fa-227">只要标签与特定条件匹配，就可以将其自动应用到内容。</span><span class="sxs-lookup"><span data-stu-id="e27fa-227">You can apply labels to content automatically if it matches specific conditions.</span></span>

- <span data-ttu-id="e27fa-228">你可以应用基于保留标签的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e27fa-228">You can apply DLP policies that are based on retention labels.</span></span>

- <span data-ttu-id="e27fa-229">组织中的人员可以将标签手动应用于 Outlook 网页版、Outlook 2010 及更高版本、OneDrive、SharePoint 和 Office 365 组中的内容。</span><span class="sxs-lookup"><span data-stu-id="e27fa-229">People in your organization can apply a label manually to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Office 365 groups.</span></span> <span data-ttu-id="e27fa-230">用户通常知道他们正在使用的内容类型，以便对其进行分类并应用适当的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e27fa-230">Users often know best what type of content they're working with, so they can classify it and have the appropriate DLP policy applied.</span></span>

<span data-ttu-id="e27fa-231">如图所示，此解决方案包括创建以下保留标签：</span><span class="sxs-lookup"><span data-stu-id="e27fa-231">As illustrated, this solution includes creating the following retention labels:</span></span>

- <span data-ttu-id="e27fa-232">高度机密</span><span class="sxs-lookup"><span data-stu-id="e27fa-232">Highly Confidential</span></span>

- <span data-ttu-id="e27fa-233">敏感</span><span class="sxs-lookup"><span data-stu-id="e27fa-233">Sensitive</span></span>

- <span data-ttu-id="e27fa-234">Private</span><span class="sxs-lookup"><span data-stu-id="e27fa-234">Private</span></span>

- <span data-ttu-id="e27fa-235">内部公用</span><span class="sxs-lookup"><span data-stu-id="e27fa-235">Internal Public</span></span>

<span data-ttu-id="e27fa-p126">这些标签均映射到本文前述插图和图表中建议的网站。本解决方案建议配置 DLP 策略，以帮助防止泄露标记为“敏感”和“高度机密”的文件。</span><span class="sxs-lookup"><span data-stu-id="e27fa-p126">These labels are mapped to the recommended sites in the illustrations and charts earlier in this article. This solution recommends configuring DLP policies to help prevent the leakage of files labeled as Sensitive and Highly Confidential.</span></span>

<span data-ttu-id="e27fa-238">有关在此解决方案中配置保留标签和 DLP 策略的步骤，请参阅[通过保留标签和 DLP 保护团队中的文件](deploy-teams-retention-DLP.md)。</span><span class="sxs-lookup"><span data-stu-id="e27fa-238">For the steps to configure retention labels and DLP policies in this solution, see [Protect files in teams with retention labels and DLP](deploy-teams-retention-DLP.md).</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="e27fa-239">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="e27fa-239">Sensitivity labels</span></span>

<span data-ttu-id="e27fa-240">如果你的安全方案需要保护，则可以使用敏感度标签应用与文件如影随形的保护。</span><span class="sxs-lookup"><span data-stu-id="e27fa-240">If warranted for your security scenario, you can use sensitivity labels to apply protections that follow the files wherever they go.</span></span> <span data-ttu-id="e27fa-241">Microsoft 365 合规中心内的敏感度标签与 Azure 信息保护标签是相同的。</span><span class="sxs-lookup"><span data-stu-id="e27fa-241">Sensitivity labels in the Microsoft 365 compliance center and Azure Information Protection labels are the same.</span></span> <span data-ttu-id="e27fa-242">对于此解决方案，建议使用灵敏度标签或子标签来加密需要最高安全性级别保护的文件，并授予对这些文件的权限。</span><span class="sxs-lookup"><span data-stu-id="e27fa-242">For this solution, we recommend you use a sensitivity label or sublabel to encrypt and grant permissions to files that need to be protected with the highest level of security.</span></span>

<span data-ttu-id="e27fa-243">有关详细信息，请参阅[敏感度标签概述](../../compliance/sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="e27fa-243">For more information, see [Overview of sensitivity labels](../../compliance/sensitivity-labels.md).</span></span>

<span data-ttu-id="e27fa-244">有关在此解决方案中配置灵敏度标签的步骤，请参阅[使用灵敏度标签保护团队中的文件](deploy-teams-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="e27fa-244">For the steps to configure sensitivity labels in this solution, see [Protect files in teams with sensitivity labels](deploy-teams-sensitivity-labels.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e27fa-245">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e27fa-245">See also</span></span>

[<span data-ttu-id="e27fa-246">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="e27fa-246">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
