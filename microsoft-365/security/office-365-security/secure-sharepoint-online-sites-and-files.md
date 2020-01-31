---
title: 保护 SharePoint Online 网站和文件
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
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
- SPO_Content
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 摘要：用于保护 SharePoint Online 和 Office 365 中文件的配置建议。
ms.openlocfilehash: c175e0e480670f9e5ce00a701704cedf1abeff26
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572348"
---
# <a name="secure-sharepoint-online-sites-and-files"></a><span data-ttu-id="3b89d-103">保护 SharePoint Online 网站和文件</span><span class="sxs-lookup"><span data-stu-id="3b89d-103">Secure SharePoint Online sites and files</span></span>

<span data-ttu-id="3b89d-p101">本文就如何配置 SharePoint Online 团队网站并在平衡安全性与易于协作的同时如何进行文件保护方面提供了相关建议。本文定义了四个不同的配置，首先是具有最开放共享策略的组织内的公共网站。每个额外配置均表示一个有意义的保护设置，但对资源的访问和协作被限定为一组相关用户。以这些建议为出发点，并调整配置以满足组织的需要。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p101">This article provides recommendations for configuring SharePoint Online team sites and file protection that balances security with ease of collaboration. This article defines four different configurations, starting with a public site within your organization with the most open sharing policies. Each additional configuration represents a meaningful step up in protection, but the ability to access and collaborate on resources is reduced to the relevant set of users. Use these recommendations as a starting point and adjust the configurations to meet the needs of your organization.</span></span>

<span data-ttu-id="3b89d-108">本文中的配置符合 Microsoft 针对数据、标识和设备的三层保护的建议：</span><span class="sxs-lookup"><span data-stu-id="3b89d-108">The configurations in this article align with Microsoft's recommendations for three tiers of protection for data, identities, and devices:</span></span>

- <span data-ttu-id="3b89d-109">基线保护</span><span class="sxs-lookup"><span data-stu-id="3b89d-109">Baseline protection</span></span>

- <span data-ttu-id="3b89d-110">敏感保护</span><span class="sxs-lookup"><span data-stu-id="3b89d-110">Sensitive protection</span></span>

- <span data-ttu-id="3b89d-111">高度机密保护</span><span class="sxs-lookup"><span data-stu-id="3b89d-111">Highly confidential protection</span></span>

<span data-ttu-id="3b89d-112">有关这些保护层以及针对每层建议的功能的详细信息，请参阅以下资源。</span><span class="sxs-lookup"><span data-stu-id="3b89d-112">For more information about these tiers and capabilities recommended for each tier, see the following resources.</span></span>

- [<span data-ttu-id="3b89d-113">Office 365 的标识和设备保护</span><span class="sxs-lookup"><span data-stu-id="3b89d-113">Identity and Device Protection for Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [<span data-ttu-id="3b89d-114">Office 365 中的文件保护解决方案</span><span class="sxs-lookup"><span data-stu-id="3b89d-114">File Protection Solutions in Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="capability-overview"></a><span data-ttu-id="3b89d-115">功能概述</span><span class="sxs-lookup"><span data-stu-id="3b89d-115">Capability overview</span></span>

<span data-ttu-id="3b89d-116">针对各种 Microsoft 365 功能的 SharePoint Online 团队网站绘制的建议。</span><span class="sxs-lookup"><span data-stu-id="3b89d-116">Recommendations for SharePoint Online team sites draw on a variety of Microsoft 365 capabilities.</span></span> <span data-ttu-id="3b89d-117">下图显示了针对四个 SharePoint Online 团队网站的建议配置。</span><span class="sxs-lookup"><span data-stu-id="3b89d-117">The following illustration shows the recommended configurations for four SharePoint Online team sites.</span></span>

![适用于 SharePoint 网站的推荐配置](../media/SharePoint-site-configurations.png)

<span data-ttu-id="3b89d-119">如图所示：</span><span class="sxs-lookup"><span data-stu-id="3b89d-119">As illustrated:</span></span>

- <span data-ttu-id="3b89d-p103">基线保护包含针对 SharePoint Online 团队网站的两个选项 - 公共网站和专用网站。 组织中的任何人均可发现和访问公共网站。 只有网站成员可以发现和访问专用网站。 这两个网站配置均允许组外共享。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p103">Baseline protection includes two options for SharePoint Online team sites — a public site and private site. Public sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the site. Both of these site configurations allow for sharing outside the group.</span></span>

- <span data-ttu-id="3b89d-124">敏感保护和高度机密的保护的网站是专用网站，只有特定组的成员才具有相关访问权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-124">Sites for sensitive and highly confidential protection are private sites with access limited only to members of specific groups.</span></span>

- <span data-ttu-id="3b89d-125">[保留标签](../../compliance/labels.md)提供了一种对网站内的文件进行分类的方法。</span><span class="sxs-lookup"><span data-stu-id="3b89d-125">[Retention labels](../../compliance/labels.md) provide a way to classify files within the sites.</span></span> <span data-ttu-id="3b89d-126">每个 SharePoint Online 团队网站均被配置为使用网站的默认保留标签自动标记文档库中的文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-126">Each of the SharePoint Online team sites are configured to automatically label files in document libraries with a default retention label for the site.</span></span> <span data-ttu-id="3b89d-127">与四个网站配置相对应，此示例中的标签分别为内部公开、专用、敏感和高度机密。</span><span class="sxs-lookup"><span data-stu-id="3b89d-127">Corresponding to the four site configurations, the labels in this example are Internal Public, Private, Sensitive, and Highly Confidential.</span></span> <span data-ttu-id="3b89d-128">用户可以更改标签，但此配置可确保所有文件均接收默认的标签。</span><span class="sxs-lookup"><span data-stu-id="3b89d-128">Users can change the labels, but this configuration ensures all files receive a default label.</span></span>

- <span data-ttu-id="3b89d-129">为敏感和高度机密保留标签配置[数据丢失防护](../../compliance/data-loss-prevention-policies.md) (DLP) 策略，在其试图向组织外部发送这些类型的文件时警告或阻止用户。</span><span class="sxs-lookup"><span data-stu-id="3b89d-129">[Data loss prevention](../../compliance/data-loss-prevention-policies.md) (DLP) policies are configured for the Sensitive and Highly Confidential retention labels to either warn or prevent users when they attempt to send these types of files outside the organization.</span></span>

- <span data-ttu-id="3b89d-130">如果方案需要，可以使用[敏感度标签](../../compliance/sensitivity-labels.md)来通过加密和权限来保护高度机密文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-130">If needed for your scenario, you can use [sensitivity labels](../../compliance/sensitivity-labels.md) to protect highly confidential files with encryption and permissions.</span></span> <span data-ttu-id="3b89d-131">对于 Azure 信息保护客户，你可以在 Microsoft 365 合规中心内使用 Azure 信息保护标签。如果你选择执行其他配置或高级配置，这些标签便会与 Azure 门户同步。</span><span class="sxs-lookup"><span data-stu-id="3b89d-131">For Azure Information Protection customers, you can use your Azure Information Protection labels in the Microsoft 365 compliance center, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration.</span></span> <span data-ttu-id="3b89d-132">Azure 信息保护标签和 Office 365 敏感度标签彼此完全相互兼容。</span><span class="sxs-lookup"><span data-stu-id="3b89d-132">Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.</span></span> <span data-ttu-id="3b89d-133">也就是说，例如，如果内容已有 Azure 信息保护标签，无需重新对此内容进行分类或标记。</span><span class="sxs-lookup"><span data-stu-id="3b89d-133">This means, for example, if you have content labeled by Azure Information Protection, you won't need to reclassify or relabel your content.</span></span> <span data-ttu-id="3b89d-134">并非所有客户都需要这一级别的保护。</span><span class="sxs-lookup"><span data-stu-id="3b89d-134">Not all customers need this level of protection.</span></span>

## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="3b89d-135">SharePoint Online 和 OneDrive for Business 的租户范围内设置</span><span class="sxs-lookup"><span data-stu-id="3b89d-135">Tenant-wide settings for SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="3b89d-p106">SharePoint Online 和 OneDrive for Business 包括影响所有网站和用户的租户范围内设置。 其中一些设置也可在网站级别进行调整，使其更具有（而不是更不具有）限制性。 本部分讨论影响安全性和协作的租户范围内设置。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p106">SharePoint Online and OneDrive for Business include tenant-wide settings that affect all sites and users. Some of these settings can also be adjusted at the site level to be more restrictive (but not less). This section discusses tenant-wide settings that affect security and collaboration.</span></span>

### <a name="sharing"></a><span data-ttu-id="3b89d-139">共享</span><span class="sxs-lookup"><span data-stu-id="3b89d-139">Sharing</span></span>

<span data-ttu-id="3b89d-140">对于此解决方案，建议使用以下租户范围内设置：</span><span class="sxs-lookup"><span data-stu-id="3b89d-140">For this solution, we recommend the following tenant-wide settings:</span></span>

- <span data-ttu-id="3b89d-141">保留允许所有与所有帐户类型共享（包括匿名共享）的默认共享策略。</span><span class="sxs-lookup"><span data-stu-id="3b89d-141">Keep the default sharing policy that allows all sharing with all account types, including anonymous sharing.</span></span>

- <span data-ttu-id="3b89d-142">如果需要，请将匿名链接设置为过期。</span><span class="sxs-lookup"><span data-stu-id="3b89d-142">Set anonymous links to expire, if desired.</span></span>

- <span data-ttu-id="3b89d-p107">将共享的默认链接类型更改为“内部”。 这有助于防止数据意外泄露到组织外部。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p107">Change the default link type for sharing to Internal. This helps prevent accidental data leakage outside your organization.</span></span>

<span data-ttu-id="3b89d-p108">虽然允许外部共享可能看起来有悖常理，但相较于通过电子邮件发送文件，此方法可更好地控制文件共享。 SharePoint Online 和 Outlook 彼此协作，提供安全的文件协作。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p108">While it might seem counterintuitive to allow external sharing, this approach provides more control over file sharing compared to sending files in email. SharePoint Online and Outlook work together to provide secure collaboration on files.</span></span>

- <span data-ttu-id="3b89d-147">默认情况下，Outlook 共享文件链接，而不是通过电子邮件发送文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-147">By default, Outlook shares a link to a file instead of sending the file in email.</span></span>

- <span data-ttu-id="3b89d-148">SharePoint Online 和 OneDrive for Business 可轻松实现与组织内外部的参与者共享文件链接</span><span class="sxs-lookup"><span data-stu-id="3b89d-148">SharePoint Online and OneDrive for Business make it easy to share links to files with contributors who are both inside and outside your organization</span></span>

<span data-ttu-id="3b89d-p109">用户还可进行控制，帮助管理外部共享。 例如，你能够：</span><span class="sxs-lookup"><span data-stu-id="3b89d-p109">You also have controls to help govern external sharing. For example, you can:</span></span>

- <span data-ttu-id="3b89d-151">禁用匿名来宾链接。</span><span class="sxs-lookup"><span data-stu-id="3b89d-151">Disable an anonymous guest link.</span></span>

- <span data-ttu-id="3b89d-152">撤销用户对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-152">Revoke user access to a site.</span></span>

- <span data-ttu-id="3b89d-153">查看谁有权访问特定网站或文档。</span><span class="sxs-lookup"><span data-stu-id="3b89d-153">See who has access to a specific site or document.</span></span>

- <span data-ttu-id="3b89d-154">将匿名共享链接设置为过期（租户设置）。</span><span class="sxs-lookup"><span data-stu-id="3b89d-154">Set anonymous sharing links to expire (tenant setting).</span></span>

- <span data-ttu-id="3b89d-155">限制可与之共享的组织外部用户（租户设置）。</span><span class="sxs-lookup"><span data-stu-id="3b89d-155">Limit who can share outside your organization (tenant setting).</span></span>

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a><span data-ttu-id="3b89d-156">配合使用外部共享与数据丢失预防 (DLP)</span><span class="sxs-lookup"><span data-stu-id="3b89d-156">Use external sharing together with data loss prevention (DLP)</span></span>

<span data-ttu-id="3b89d-p110">如果不允许外部共享，则有业务需求的用户需要寻找备用工具和方法。Microsoft 建议结合使用外部共享和 DLP 策略来保护敏感和高度机密的文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p110">If you don't allow external sharing, users with a business need will find alternate tools and methods. Microsoft recommends you combine external sharing with DLP policies to protect sensitive and highly confidential files.</span></span>

### <a name="device-access-settings"></a><span data-ttu-id="3b89d-159">设备访问设置</span><span class="sxs-lookup"><span data-stu-id="3b89d-159">Device access settings</span></span>

<span data-ttu-id="3b89d-160">SharePoint Online 和 OneDrive for Business 的设备访问设置可确定是否已将访问权限限制为仅限浏览器（不能下载文件）或访问被阻止。</span><span class="sxs-lookup"><span data-stu-id="3b89d-160">Device access settings for SharePoint Online and OneDrive for Business let you determine whether access is limited to browser only (files can't be downloaded) or if access is blocked.</span></span> <span data-ttu-id="3b89d-161">有关详细信息，请参阅[控制非托管设备的访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-161">For more information, see [Control access from unmanaged devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).</span></span>

<span data-ttu-id="3b89d-162">若要在 Azure Active Directory 中使用具有推荐条件访问策略的设备访问设置，请参阅[用于保护 SharePoint 网站和文件的策略建议](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-162">To use device access settings with recommended conditional access policies in Azure Active Directory, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="3b89d-163">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3b89d-163">OneDrive for Business</span></span>

<span data-ttu-id="3b89d-p112">访问这些设置，确定是否要更改 OneDrive for Business 网站的默认设置。目前，共享和设备访问设置与 SharePoint Online 管理中心重复，并适用于这两个环境。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p112">Visit these settings to decide if you want to change the default settings for OneDrive for Business sites. Currently, the sharing and device access settings are duplicated from the SharePoint Online admin center and apply to both environments.</span></span>

## <a name="sharepoint-team-site-configuration"></a><span data-ttu-id="3b89d-166">SharePoint 团队网站配置</span><span class="sxs-lookup"><span data-stu-id="3b89d-166">SharePoint team site configuration</span></span>

<span data-ttu-id="3b89d-p113">下表总结了本文前面所述的每个团队网站的配置。使用这些配置作为起点建议并调整网站类型和配置，以满足组织的需求。不是每个组织都需要每种类型的网站。只有少许组织需要高度机密的保护。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p113">The following table summarizes the configuration for each of the team sites described earlier in this article. Use these configurations as starting point recommendations and adjust the site types and configurations to meet the needs of your organization. Not every organization needs every type of site. Only a small number of organizations require highly confidential protection.</span></span>

||||||
|:-----|:-----|:-----|:-----|:-----|
||<span data-ttu-id="3b89d-171">**基线保护 #1**</span><span class="sxs-lookup"><span data-stu-id="3b89d-171">**Baseline protection #1**</span></span>|<span data-ttu-id="3b89d-172">**基线保护 #2**</span><span class="sxs-lookup"><span data-stu-id="3b89d-172">**Baseline protection #2**</span></span>|<span data-ttu-id="3b89d-173">**敏感保护**</span><span class="sxs-lookup"><span data-stu-id="3b89d-173">**Sensitive protection**</span></span>|<span data-ttu-id="3b89d-174">**高度机密**</span><span class="sxs-lookup"><span data-stu-id="3b89d-174">**Highly confidential**</span></span>|
|<span data-ttu-id="3b89d-175">描述</span><span class="sxs-lookup"><span data-stu-id="3b89d-175">Description</span></span>|<span data-ttu-id="3b89d-176">组织内的开放式发现和协作。</span><span class="sxs-lookup"><span data-stu-id="3b89d-176">Open discovery and collaboration within the organization.</span></span>|<span data-ttu-id="3b89d-177">允许在组外部共享的专用网站和组。</span><span class="sxs-lookup"><span data-stu-id="3b89d-177">Private site and group with sharing allowed outside the group.</span></span>|<span data-ttu-id="3b89d-p114">仅允许网站成员进行共享的专用网站。DLP 在用户试图向组织外发送文件时警告用户。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p114">Private site with sharing allowed only to members of the site. DLP warns users when attempting to send files outside the organization.</span></span>|<span data-ttu-id="3b89d-180">具有敏感标签的专用网站和文件加密及权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-180">Private site and file encryption and permissions with sensitivity labels.</span></span> <span data-ttu-id="3b89d-181">DLP 阻止用户向组织外发送文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-181">DLP prevents users from sending files outside the organization.</span></span>|
|<span data-ttu-id="3b89d-182">专用或公用团队网站</span><span class="sxs-lookup"><span data-stu-id="3b89d-182">Private or public team site</span></span>|<span data-ttu-id="3b89d-183">公用</span><span class="sxs-lookup"><span data-stu-id="3b89d-183">Public</span></span>|<span data-ttu-id="3b89d-184">Private</span><span class="sxs-lookup"><span data-stu-id="3b89d-184">Private</span></span>|<span data-ttu-id="3b89d-185">Private</span><span class="sxs-lookup"><span data-stu-id="3b89d-185">Private</span></span>|<span data-ttu-id="3b89d-186">Private</span><span class="sxs-lookup"><span data-stu-id="3b89d-186">Private</span></span>|
|<span data-ttu-id="3b89d-187">谁可以访问？</span><span class="sxs-lookup"><span data-stu-id="3b89d-187">Who has access?</span></span>|<span data-ttu-id="3b89d-188">组织中的任何人，包括 B2B 用户和来宾用户。</span><span class="sxs-lookup"><span data-stu-id="3b89d-188">Everybody in the organization, including B2B users and guest users.</span></span>|<span data-ttu-id="3b89d-p116">仅限网站成员。其他人可以请求访问。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p116">Members of the site only. Others can request access.</span></span>|<span data-ttu-id="3b89d-p117">仅限网站成员。其他人可以请求访问。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p117">Members of the site only. Others can request access.</span></span>|<span data-ttu-id="3b89d-p118">仅限成员。其他人无法请求访问。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p118">Members only. Others cannot request access.</span></span>|
|<span data-ttu-id="3b89d-195">网站级共享控制</span><span class="sxs-lookup"><span data-stu-id="3b89d-195">Site-level sharing controls</span></span>|<span data-ttu-id="3b89d-p119">允许与任何人共享。默认设置。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p119">Sharing allowed with anybody. Default settings.</span></span>|<span data-ttu-id="3b89d-p120">允许与任何人共享。默认设置。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p120">Sharing allowed with anybody. Default settings.</span></span>|<span data-ttu-id="3b89d-200">成员无法共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-200">Members cannot share access to the site.</span></span> <br/> <span data-ttu-id="3b89d-201">非成员可以请求访问该网站，但需要由网站管理员对这些请求进行寻址。</span><span class="sxs-lookup"><span data-stu-id="3b89d-201">Non-members can request access to the site, but these requests need to be addressed by a site administrator.</span></span>|<span data-ttu-id="3b89d-202">成员无法共享对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-202">Members cannot share access to the site.</span></span> <br/> <span data-ttu-id="3b89d-203">非成员无法请求访问网站或内容。</span><span class="sxs-lookup"><span data-stu-id="3b89d-203">Non-members cannot request access to the site or contents.</span></span>|
|<span data-ttu-id="3b89d-204">网站级别的设备访问控制</span><span class="sxs-lookup"><span data-stu-id="3b89d-204">Site-level device access controls</span></span>|<span data-ttu-id="3b89d-205">无任何额外控制。</span><span class="sxs-lookup"><span data-stu-id="3b89d-205">No additional controls.</span></span>|<span data-ttu-id="3b89d-206">无任何额外控制。</span><span class="sxs-lookup"><span data-stu-id="3b89d-206">No additional controls.</span></span>|<span data-ttu-id="3b89d-p121">防止用户将文件下载到不符合或未加入域的设备。使所有其他设备仅限浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p121">Prevents users from downloading files to non-compliant or non-domain joined devices. This allows browser-only access from all other devices.</span></span>|<span data-ttu-id="3b89d-209">阻止将文件下载到不符合或未加入域的设备。</span><span class="sxs-lookup"><span data-stu-id="3b89d-209">Block downloading of files to non-compliant or non-domain joined devices.</span></span>|
|<span data-ttu-id="3b89d-210">保留标签</span><span class="sxs-lookup"><span data-stu-id="3b89d-210">Retention labels</span></span>|<span data-ttu-id="3b89d-211">内部公用</span><span class="sxs-lookup"><span data-stu-id="3b89d-211">Internal Public</span></span>|<span data-ttu-id="3b89d-212">Private</span><span class="sxs-lookup"><span data-stu-id="3b89d-212">Private</span></span>|<span data-ttu-id="3b89d-213">敏感</span><span class="sxs-lookup"><span data-stu-id="3b89d-213">Sensitive</span></span>|<span data-ttu-id="3b89d-214">高度机密</span><span class="sxs-lookup"><span data-stu-id="3b89d-214">Highly Confidential</span></span>|
|<span data-ttu-id="3b89d-215">DLP 策略</span><span class="sxs-lookup"><span data-stu-id="3b89d-215">DLP policies</span></span>|||<span data-ttu-id="3b89d-216">在用户向组织外发送标记为“敏感”的文件时进行警告。</span><span class="sxs-lookup"><span data-stu-id="3b89d-216">Warn users when sending files that are labeled as Sensitive outside the organization.</span></span> <br/> <span data-ttu-id="3b89d-217">要阻止外部共享敏感数据类型，如信用卡号或其他个人数据，可以针对这些数据类型（包括所配置的自定义数据类型）配置其他 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="3b89d-217">To block external sharing of sensitive data types, such as credit card numbers or other personal data, you can configure additional DLP policies for these data types (including custom data types you configure).</span></span>|<span data-ttu-id="3b89d-p122">阻止用户向组织外发送标记为“高度机密”的文件。允许用户通过提供他们与之共享的对象等理由来替代此行为。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p122">Block users from sending files that are labeled as highly confidential outside organization. Allow users to override this by providing justification, including who they are sharing the file with.</span></span>|
|<span data-ttu-id="3b89d-220">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="3b89d-220">Sensitivity labels</span></span>||||<span data-ttu-id="3b89d-221">使用敏感度标签自动加密和授予文件权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-221">Use sensitivity labels to automatically encrypt and grant permissions to files.</span></span> <span data-ttu-id="3b89d-222">此保护将始终伴随文件，以防其泄露。</span><span class="sxs-lookup"><span data-stu-id="3b89d-222">This protection travels with the files in case they are leaked.</span></span> <br/> <span data-ttu-id="3b89d-223">Office 365 无法读取使用敏感度标签加密的文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-223">Office 365 cannot read files encrypted with sensitivity labels.</span></span> <span data-ttu-id="3b89d-224">此外，DLP 策略只适用于元数据（包括标签），但并不适用于这些文件的内容（如文件内的信用卡号）。</span><span class="sxs-lookup"><span data-stu-id="3b89d-224">Additionally, DLP policies can only work with the metadata (including labels) but not the contents of these files (such as credit card numbers within files).</span></span>|

<span data-ttu-id="3b89d-225">有关如何部署此解决方案中四种不同类型的 SharePoint Online 团队网站的步骤，请参阅[部署具有三层保护的 SharePoint Online 网站](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-225">For the steps to deploy the four different types of SharePoint Online team sites in this solution, see [Deploy SharePoint Online sites for three tiers of protection](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md).</span></span>

## <a name="office-365-retention-labels"></a><span data-ttu-id="3b89d-226">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="3b89d-226">Office 365 retention labels</span></span>

<span data-ttu-id="3b89d-227">对于具有敏感和高度机密数据的环境，建议使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="3b89d-227">Using retention labels is recommended for environments with sensitive and highly confidential data.</span></span> <span data-ttu-id="3b89d-228">在配置和发布保留标签后：</span><span class="sxs-lookup"><span data-stu-id="3b89d-228">After you configure and publish retention labels:</span></span>

- <span data-ttu-id="3b89d-229">可以将默认标签应用于 SharePoint Online 团队网站中的文档库，以便该库中的所有文档都能获取默认标签。</span><span class="sxs-lookup"><span data-stu-id="3b89d-229">You can apply a default label to a document library in a SharePoint Online team site, so that all documents in that library get the default label.</span></span>

- <span data-ttu-id="3b89d-230">只要标签与特定条件匹配，就可以将其自动应用到内容。</span><span class="sxs-lookup"><span data-stu-id="3b89d-230">You can apply labels to content automatically if it matches specific conditions.</span></span>

- <span data-ttu-id="3b89d-231">你可以应用基于保留标签的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="3b89d-231">You can apply DLP policies that are based on retention labels.</span></span>

- <span data-ttu-id="3b89d-p126">组织中的用户可手动将标签应用于 Outlook 网页版、Outlook 2010 及更高版本、OneDrive for Business、SharePoint Online 以及 Office 365 组。用户通常都很了解他们处理的内容类型，以便可以对其进行分类并应用相应的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p126">People in your organization can apply a label manually to content in Outlook on the web, Outlook 2010 and later, OneDrive for Business, SharePoint Online, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate DLP policy applied.</span></span>

![适用于 SharePoint 网站的推荐配置](../media/7fed0126-ab4a-4480-922c-681970642339.png)

<span data-ttu-id="3b89d-235">如图所示，此解决方案包括创建以下保留标签：</span><span class="sxs-lookup"><span data-stu-id="3b89d-235">As illustrated, this solution includes creating the following retention labels:</span></span>

- <span data-ttu-id="3b89d-236">高度机密</span><span class="sxs-lookup"><span data-stu-id="3b89d-236">Highly Confidential</span></span>

- <span data-ttu-id="3b89d-237">敏感</span><span class="sxs-lookup"><span data-stu-id="3b89d-237">Sensitive</span></span>

- <span data-ttu-id="3b89d-238">Private</span><span class="sxs-lookup"><span data-stu-id="3b89d-238">Private</span></span>

- <span data-ttu-id="3b89d-239">内部公用</span><span class="sxs-lookup"><span data-stu-id="3b89d-239">Internal Public</span></span>

<span data-ttu-id="3b89d-p127">这些标签均映射到本文前述插图和图表中建议的网站。本解决方案建议配置 DLP 策略，以帮助防止泄露标记为“敏感”和“高度机密”的文件。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p127">These labels are mapped to the recommended sites in the illustrations and charts earlier in this article. This solution recommends configuring DLP policies to help prevent the leakage of files labeled as Sensitive and Highly Confidential.</span></span>

<span data-ttu-id="3b89d-242">有关在此解决方案中配置保留标签和 DLP 策略的步骤，请参阅[使用保留标签和 DLP 保护 SharePoint Online文件](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-242">For the steps to configure retention labels and DLP policies in this solution, see [Protect SharePoint Online files with retention labels and DLP](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md).</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="3b89d-243">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="3b89d-243">Sensitivity labels</span></span>

<span data-ttu-id="3b89d-244">如果你的安全方案需要保护，则可以使用敏感度标签应用与文件如影随形的保护。</span><span class="sxs-lookup"><span data-stu-id="3b89d-244">If warranted for your security scenario, you can use sensitivity labels to apply protections that follow the files wherever they go.</span></span> <span data-ttu-id="3b89d-245">Microsoft 365 合规中心内的敏感度标签与 Azure 信息保护标签是相同的。</span><span class="sxs-lookup"><span data-stu-id="3b89d-245">Sensitivity labels in the Microsoft 365 compliance center and Azure Information Protection labels are the same.</span></span> <span data-ttu-id="3b89d-246">对于此解决方案，建议使用敏感度标签或高度机密敏感度标签的子标签来加密需要最高级别安全性保护的文件并授予相应权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-246">For this solution, we recommend you use a sensitivity label or a sub-label of the Highly Confidential sensitivity label to encrypt and grant permissions to files that need to be protected with the highest level of security.</span></span>

<span data-ttu-id="3b89d-247">请注意，将敏感度标签加密应用于 Office 365 中存储的文件时，该服务无法处理这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="3b89d-247">Be aware that when sensitivity label encryption is applied to files stored in Office 365, the service cannot process the contents of these files.</span></span> <span data-ttu-id="3b89d-248">共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。</span><span class="sxs-lookup"><span data-stu-id="3b89d-248">Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work.</span></span> <span data-ttu-id="3b89d-249">DLP 策略只适用于元数据（包括保留标签），但并不适用于这些文件的内容（如文件内的信用卡号）。</span><span class="sxs-lookup"><span data-stu-id="3b89d-249">DLP policies can only work with the metadata (including retention labels) but not the contents of these files (such as credit card numbers within files).</span></span>

<span data-ttu-id="3b89d-250">有关详细信息，请参阅[敏感度标签概述](../../compliance/sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-250">For more information, see [Overview of sensitivity labels](../../compliance/sensitivity-labels.md).</span></span>

### <a name="adding-permissions-for-external-users"></a><span data-ttu-id="3b89d-251">为外部用户添加权限</span><span class="sxs-lookup"><span data-stu-id="3b89d-251">Adding permissions for external users</span></span>

<span data-ttu-id="3b89d-252">可通过两种方式授予使用敏感度标签进行保护的文件的外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-252">There are two ways you can grant external users access to files protected with a sensitivity label.</span></span> <span data-ttu-id="3b89d-253">在这两种情况下，外部用户均须具有 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="3b89d-253">In both these cases, external users must have an Azure AD account.</span></span> <span data-ttu-id="3b89d-254">如果外部用户不是使用 Azure AD 的组织的成员，他们可以通过使用此注册页面以个人身份获得 Azure AD 帐户：[https://aka.ms/aip-signup](https://aka.ms/aip-signup)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-254">If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this sign-up page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

- <span data-ttu-id="3b89d-255">将外部用户添加到用于配置标签保护的 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="3b89d-255">Add external users to an Azure AD group that is used to configure protection for a label</span></span>

  <span data-ttu-id="3b89d-p131">你需要先将该帐户作为 B2B 用户添加到目录中。[通过 Azure 权限管理缓存组成员资格](https://docs.microsoft.com/information-protection/plan-design/prepare)可能需要几个小时的时间。使用此方法，可将权限授予使用标签保护的所有现有文件（甚至在将用户添加到 Azure AD 组之前受保护的文件）。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p131">You'll need to first add the account as a B2B user in your directory. It can take a couple of hours for [group membership caching by Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare). With this method, permissions are granted to all existing files protected with the label (even files protected before a user is added to the Azure AD group).</span></span>

- <span data-ttu-id="3b89d-259">将外部用户直接添加到标签保护</span><span class="sxs-lookup"><span data-stu-id="3b89d-259">Add external users directly to the label protection</span></span>

  <span data-ttu-id="3b89d-p132">你可以添加组织（例如 Fabrikam.com）、Azure AD 组（如组织内的财务组）中的所有用户或单个用户。例如，可以将监管机构的外部团队添加到标签保护中。使用此方法，可仅向在外部实体添加到保护后使用标签进行保护的文件授予权限。</span><span class="sxs-lookup"><span data-stu-id="3b89d-p132">You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or an individual user. For example, you can add an external team of regulators to the protection for a label. With this method, permissions are granted only to files protected with the label after the external entity is added to the protection.</span></span>

### <a name="deploying-and-using-a-sensitivity-label"></a><span data-ttu-id="3b89d-263">部署和使用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="3b89d-263">Deploying and using a sensitivity label</span></span>

<span data-ttu-id="3b89d-264">有关在此解决方案中配置敏感度标签的步骤，请参阅[使用敏感度标签保护 SharePoint Online 文件](../../compliance/protect-sharepoint-online-files-with-sensitivity-label.md)。</span><span class="sxs-lookup"><span data-stu-id="3b89d-264">For the steps to configure a sensitivity label in this solution, see [Protect SharePoint Online files with a sensitivity label](../../compliance/protect-sharepoint-online-files-with-sensitivity-label.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="3b89d-265">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b89d-265">Next step</span></span>

<span data-ttu-id="3b89d-266">通过[在开发/测试环境中保护 SharePoint Online 网站](secure-sharepoint-online-sites-in-a-dev-test-environment.md)将此项作为概念证明进行构建。</span><span class="sxs-lookup"><span data-stu-id="3b89d-266">Build this out as a proof-of-concept with [Secure SharePoint Online sites in a dev/test environment](secure-sharepoint-online-sites-in-a-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b89d-267">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b89d-267">See Also</span></span>

[<span data-ttu-id="3b89d-268">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="3b89d-268">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="3b89d-269">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="3b89d-269">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
