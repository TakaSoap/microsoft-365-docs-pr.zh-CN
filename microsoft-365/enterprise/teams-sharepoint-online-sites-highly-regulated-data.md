---
title: 针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 创建安全的 SharePoint Online 团队网站或 Microsoft Teams 团队以存储最有价值和最敏感的数字资产。
ms.openlocfilehash: d80be334f692f905ec70ae43f851d2b73801f4a0
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553321"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="f37ed-103">针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="f37ed-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="f37ed-104">*此方案适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="f37ed-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="f37ed-p101">Microsoft 365 企业版包含一整套基于云的服务，使用户可以创建、存储和保护高度管控的数据。这包括符合以下条件的数据：</span><span class="sxs-lookup"><span data-stu-id="f37ed-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="f37ed-107">受地区法规约束。</span><span class="sxs-lookup"><span data-stu-id="f37ed-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="f37ed-108">组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。</span><span class="sxs-lookup"><span data-stu-id="f37ed-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="f37ed-109">满足此业务需求的 Microsoft 365 企业版基于云的解决方案要求用户执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f37ed-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="f37ed-110">在 SharePoint Online 团队网站或 Microsoft Teams 团队的“文件”\*\*\*\* 选项卡中存储数字资产（文档、幻灯片组、电子表格等）。</span><span class="sxs-lookup"><span data-stu-id="f37ed-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="f37ed-111">锁定网站或团队以防止：</span><span class="sxs-lookup"><span data-stu-id="f37ed-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="f37ed-112">通过组成员身份仅访问特定用户帐户组之外的所有用户帐户，其中包括可以访问 SharePoint Online 团队网站以及拥有权限级别的用户帐户以及可以管理它的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f37ed-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="f37ed-113">网站成员向其他用户授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="f37ed-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="f37ed-114">非网站成员请求访问网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="f37ed-115">为 SharePoint Online 网站或团队配置 Office 365 保留标签，将此作为在站点或团队中的文档上定义保留策略的默认方式。</span><span class="sxs-lookup"><span data-stu-id="f37ed-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="f37ed-116">阻止用户向组织外发送文件。</span><span class="sxs-lookup"><span data-stu-id="f37ed-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="f37ed-117">加密网站或团队中最敏感的数字资产。</span><span class="sxs-lookup"><span data-stu-id="f37ed-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="f37ed-118">添加对最敏感的数字资产的权限，这样，即使它们在网站外共享，打开资产仍需要具有权限的用户帐户的有效凭据。</span><span class="sxs-lookup"><span data-stu-id="f37ed-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="f37ed-119">下表将此解决方案的要求映射到 Microsoft 365 企业版的功能。</span><span class="sxs-lookup"><span data-stu-id="f37ed-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="f37ed-120">**要求**</span><span class="sxs-lookup"><span data-stu-id="f37ed-120">**Requirement**</span></span> | <span data-ttu-id="f37ed-121">**Microsoft 365 企业版 功能**</span><span class="sxs-lookup"><span data-stu-id="f37ed-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="f37ed-122">存储数字资产</span><span class="sxs-lookup"><span data-stu-id="f37ed-122">Store digital assets</span></span> | <span data-ttu-id="f37ed-123">SharePoint Online 团队网站和 Office 365 团队</span><span class="sxs-lookup"><span data-stu-id="f37ed-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="f37ed-124">锁定网站</span><span class="sxs-lookup"><span data-stu-id="f37ed-124">Lock down the site</span></span> | <span data-ttu-id="f37ed-125">Azure AD 组和 SharePoint Online 团队网站权限</span><span class="sxs-lookup"><span data-stu-id="f37ed-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="f37ed-126">标记网站的数字资产</span><span class="sxs-lookup"><span data-stu-id="f37ed-126">Label the digital assets of the site</span></span> | <span data-ttu-id="f37ed-127">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="f37ed-128">阻止向组织外发送文件的用户</span><span class="sxs-lookup"><span data-stu-id="f37ed-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="f37ed-129">Office 365 中的数据丢失防护 (DLP) 策略</span><span class="sxs-lookup"><span data-stu-id="f37ed-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="f37ed-130">加密网站的所有数字资产</span><span class="sxs-lookup"><span data-stu-id="f37ed-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="f37ed-131">企业移动性 + 安全性 (EMS) 中的 Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="f37ed-132">向网站的数字资产添加权限</span><span class="sxs-lookup"><span data-stu-id="f37ed-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="f37ed-133">EMS 中的 Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="f37ed-134">此解决方案要求已经部署：</span><span class="sxs-lookup"><span data-stu-id="f37ed-134">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="f37ed-135">[标识](identity-infrastructure.md)以及基础架构的[信息保护](infoprotect-infrastructure.md)阶段的步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="f37ed-135">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="f37ed-136">对于 SharePoint Online 团队网站中的高度管控数据：[SharePoint Online](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="f37ed-136">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="f37ed-137">对于 Microsoft Teams 团队中的高度管控数据：[Microsoft Teams](teams-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="f37ed-137">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="f37ed-138">以下各阶段将指导你完成针对高度管控数据的 SharePoint Online 网站和团队的设计、配置和驱动采用。</span><span class="sxs-lookup"><span data-stu-id="f37ed-138">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="f37ed-139">若要了解 Contoso Corporation（虚构但具代表性的跨国组织）如何为其研究团队设计 SharePoint Online 网站，请参阅此[示例配置](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="f37ed-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

>[!Note]
><span data-ttu-id="f37ed-p102">高度管控数据的团队要求首先为高度管控数据创建一个 SharePoint Online 团队网站。然后，创建一个使用 SharePoint Online 团队网站的 Office 365 组的新团队。有关详细信息，请参阅第 2 阶段的步骤 4。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>
>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="f37ed-143">身份识别和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="f37ed-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="f37ed-144">若要保护对团队或 SharePoint Online 网站的访问，请确保已配置[身份识别和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint Online 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f37ed-144">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="f37ed-145">第 1 阶段：设计</span><span class="sxs-lookup"><span data-stu-id="f37ed-145">Phase 1: Design</span></span>

<span data-ttu-id="f37ed-p103">若要针对高度管控数据创建 SharePoint Online 网站或团队，必须首先确定其用途。例如，制造业组织的研发部门需要 SharePoint Online 网站来存储现有产品的当前设计规范，以及需要一个用于协作研发新产品的位置。只允许研发部门的成员和选定的管理人员访问该网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="f37ed-149">该目的将推动基本配置项的确定，例如：</span><span class="sxs-lookup"><span data-stu-id="f37ed-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="f37ed-150">SharePoint Online 权限集和 SharePoint 组的集合</span><span class="sxs-lookup"><span data-stu-id="f37ed-150">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="f37ed-151">访问组、Azure AD 安全组及其要添加到 SharePoint 组的成员的集合</span><span class="sxs-lookup"><span data-stu-id="f37ed-151">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="f37ed-152">要分配到网站的 Office 365 保留标签以及标签的 DLP 策略集合</span><span class="sxs-lookup"><span data-stu-id="f37ed-152">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="f37ed-153">用户应用到网站中存储的高度敏感数据资产的 Azure 信息保护子标签的设置</span><span class="sxs-lookup"><span data-stu-id="f37ed-153">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="f37ed-154">确定后，使用这些设置在第 2 阶段中配置网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-154">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="f37ed-155">步骤 1：独立 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="f37ed-155">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="f37ed-p104">SharePoint Online 团队网站的锁定版本称为独立网站。与私有团队网站的默认设置不同，独立网站配置为阻止：</span><span class="sxs-lookup"><span data-stu-id="f37ed-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="f37ed-158">访问非指定组成员。</span><span class="sxs-lookup"><span data-stu-id="f37ed-158">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="f37ed-159">请求访问权限。</span><span class="sxs-lookup"><span data-stu-id="f37ed-159">The requesting of access.</span></span>
- <span data-ttu-id="f37ed-160">未经授权向指定组的当前成员授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="f37ed-160">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="f37ed-161">访问组成员管理网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-161">Administration of the site by access group members.</span></span>

<span data-ttu-id="f37ed-162">除非由网站的 SharePoint 管理员操作，否则包含高度管控资产的 SharePoint Online 团队网站的安全性不会改变。</span><span class="sxs-lookup"><span data-stu-id="f37ed-162">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="f37ed-163">请参阅[设计独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)，详细了解如何确定权限级别、SharePoint 组、访问组和组成员的集合。</span><span class="sxs-lookup"><span data-stu-id="f37ed-163">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="f37ed-164">步骤 2：Office 365 保留标签和 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f37ed-164">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="f37ed-165">应用于 SharePoint Online 团队网站时，Office 365 保留标签提供对存储在网站上的所有数字资产进行分类的默认方法。</span><span class="sxs-lookup"><span data-stu-id="f37ed-165">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="f37ed-166">对于针对高度管控数据的 SharePoint Online，需要确定要使用的 Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="f37ed-166">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="f37ed-167">有关 Office 365 标签的设计注意事项，请参阅 [Office 365 分类和标签](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="f37ed-167">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="f37ed-p105">为保护敏感信息并防止意外或故意泄露，可以使用 DLP 策略。有关详细信息，请参阅此[概述](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="f37ed-170">对于针对高度管控数据的 SharePoint Online 网站，必须为分配给网站的 Office 365 保留标签配置 DLP 策略，在用户尝试与外部用户共享数字资产时进行阻止。</span><span class="sxs-lookup"><span data-stu-id="f37ed-170">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="f37ed-171">步骤 3：Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-171">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="f37ed-p106">若要为最敏感的数字资产提供加密和一组权限，用户必须使用 Azure 信息保护客户端来应用 Azure 信息保护标签。若要为针对高度管控数据的 SharePoint Online 网站使用 Azure 信息保护标签，必须在范围策略中配置 Azure 信息保护子标签。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="f37ed-p107">子标签位于现有标签下。例如，可以在“高度机密”标签下创建一个“研发”子标签。范围策略是仅适用于用户子集的策略。对于针对高度管控数据的 SharePoint Online 网站，该范围是作为网站访问组的成员的用户集。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="f37ed-p108">应用的子标签的设置随资产一起移动。即使在网站外部下载和共享，也只有具有权限的经过身份验证的用户帐户才能打开它。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="f37ed-180">设计结果</span><span class="sxs-lookup"><span data-stu-id="f37ed-180">Design results</span></span>

<span data-ttu-id="f37ed-181">已确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="f37ed-181">You have determined the following:</span></span>

- <span data-ttu-id="f37ed-182">SharePoint 组集及权限级别</span><span class="sxs-lookup"><span data-stu-id="f37ed-182">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="f37ed-183">每个权限级别的访问组及其成员集</span><span class="sxs-lookup"><span data-stu-id="f37ed-183">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="f37ed-184">与标签关联的相应的 Office 365 保留标签和 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f37ed-184">The appropriate Office 365 label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="f37ed-185">包含加密和权限的 Azure 信息保护子标签设置</span><span class="sxs-lookup"><span data-stu-id="f37ed-185">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="f37ed-186">第 2 阶段：配置</span><span class="sxs-lookup"><span data-stu-id="f37ed-186">Phase 2: Configure</span></span>

<span data-ttu-id="f37ed-187">在此阶段中，将执行第 1 阶段中确定的设置并实现这些设置，以针对高度管控的数据创建 SharePoint Online 网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-187">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="f37ed-188">步骤 1：创建和配置独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="f37ed-188">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="f37ed-189">使用[部署独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)中的说明执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f37ed-189">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="f37ed-190">为网站中使用的每个 SharePoint 权限级别创建并填充访问组。</span><span class="sxs-lookup"><span data-stu-id="f37ed-190">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="f37ed-191">创建并配置独立的团队网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-191">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a><span data-ttu-id="f37ed-192">步骤 2：针对 Office 365 保留标签 DLP 策略配置网站</span><span class="sxs-lookup"><span data-stu-id="f37ed-192">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="f37ed-193">按照[使用 Office 365 标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的说明执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f37ed-193">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="f37ed-194">识别或创建 Office 365 保留标签，然后将其应用到独立的 SharePoint Online 网站。</span><span class="sxs-lookup"><span data-stu-id="f37ed-194">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="f37ed-195">创建并配置 DLP 策略，用于在用户尝试于组织外部的 SharePoint Online 网站上共享数字资产时阻止用户。</span><span class="sxs-lookup"><span data-stu-id="f37ed-195">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="f37ed-196">步骤 3：创建网站的 Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-196">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="f37ed-197">按照[使用 Azure 信息保护来保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)中的说明执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f37ed-197">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="f37ed-198">在范围策略中创建并配置 Azure 信息保护子标签。</span><span class="sxs-lookup"><span data-stu-id="f37ed-198">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="f37ed-199">将 Azure 信息保护客户端部署到用户计算机。</span><span class="sxs-lookup"><span data-stu-id="f37ed-199">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="f37ed-200">步骤 4（可选）：针对高度管控数据创建团队</span><span class="sxs-lookup"><span data-stu-id="f37ed-200">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="f37ed-p109">如果需要针对高度管控数据的团队，可以首先针对高度管控数据创建一个 SharePoint Online。创建初始私有 SharePoint Online 团队网站时，需要指定一个 Office 365 组名。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="f37ed-203">完全配置了针对高度管控数据的 SharePoint Online 网站后，使用以下步骤将其转换为针对高度管控数据的团队：</span><span class="sxs-lookup"><span data-stu-id="f37ed-203">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="f37ed-204">登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f37ed-204">Sign in to Office 365.</span></span>
2. <span data-ttu-id="f37ed-205">在“Microsoft Office 主页”\*\*\*\* 选项卡上，单击“Teams”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f37ed-205">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="f37ed-206">从“Microsoft Teams”\*\*\*\* 选项卡上的“加入或创建团队”\*\*\*\* 窗格中，单击“创建团队”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f37ed-206">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="f37ed-207">在“创建团队”\*\*\*\* 窗格中，单击“从现有 Office 365 组创建团队”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f37ed-207">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="f37ed-208">在 Office 365 组的列表中，选择针对高度管控数据的 SharePoint Online 网站对应的 Office 365 组的名称，然后单击“选择团队”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f37ed-208">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="f37ed-p110">新团队的“文件”\*\*\*\* 选项卡列出了相应的 SharePoint Online 网站“文档”\*\*\*\* 区域的“常规”\*\*\*\* 文件夹的内容。若要查看团队的 SharePoint Online 网站的其余资源，请单击省略号，然后单击“在 SharePoint 中打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="f37ed-211">配置结果</span><span class="sxs-lookup"><span data-stu-id="f37ed-211">Configuration results</span></span>

<span data-ttu-id="f37ed-212">已配置了以下内容：</span><span class="sxs-lookup"><span data-stu-id="f37ed-212">You have configured the following:</span></span>

- <span data-ttu-id="f37ed-213">SharePoint Online 独立网站</span><span class="sxs-lookup"><span data-stu-id="f37ed-213">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="f37ed-214">分配给 SharePoint Online 独立网站的 Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-214">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="f37ed-215">Office 365 保留标签的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f37ed-215">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="f37ed-216">用户可以应用到加密资产和强制执行权限的网站中存储的最敏感数字资产的范围策略的 Azure 信息保护子标签</span><span class="sxs-lookup"><span data-stu-id="f37ed-216">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="f37ed-217">基于 SharePoint Online 网站的针对高度管控数据的团队（如果需要）</span><span class="sxs-lookup"><span data-stu-id="f37ed-217">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="f37ed-218">第 3 阶段：驱动用户采用</span><span class="sxs-lookup"><span data-stu-id="f37ed-218">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="f37ed-p111">针对高度管控数据的 SharePoint Online 网站或团队只有在始终用于存储和访问敏感数字资产的情况下才能保护该数据。这是最困难的一个阶段，因为它依赖于用户改变他们的方式。</span><span class="sxs-lookup"><span data-stu-id="f37ed-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="f37ed-221">例如，用于在 USB 驱动器或基于云的个人存储解决方案上存储敏感文件的管理人员现在必须将它们专门存储在针对高度管控数据的 SharePoint Online 网站或团队中。</span><span class="sxs-lookup"><span data-stu-id="f37ed-221">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="f37ed-222">步骤 1：培训用户</span><span class="sxs-lookup"><span data-stu-id="f37ed-222">Step 1: Train your users</span></span>

<span data-ttu-id="f37ed-223">完成配置后，对作为网站访问组成员的一组用户培训以下内容：</span><span class="sxs-lookup"><span data-stu-id="f37ed-223">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="f37ed-224">有关使用新网站或团队保护重要资产的重要性以及高度管控数据泄露的后果，例如法律后果、管制罚款、勒索软件或失去竞争优势。</span><span class="sxs-lookup"><span data-stu-id="f37ed-224">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="f37ed-225">如何访问网站及其资产。</span><span class="sxs-lookup"><span data-stu-id="f37ed-225">How to access the site and its assets.</span></span>
- <span data-ttu-id="f37ed-226">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="f37ed-226">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="f37ed-227">DLP 策略如何阻止它们在外部共享文件。</span><span class="sxs-lookup"><span data-stu-id="f37ed-227">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="f37ed-228">如何使用 Azure 信息保护客户端对最敏感的数字资产标记已配置的子标签。</span><span class="sxs-lookup"><span data-stu-id="f37ed-228">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="f37ed-229">如果资产从网站或团队中泄露，Azure 信息保护子标签如何保护资产。</span><span class="sxs-lookup"><span data-stu-id="f37ed-229">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="f37ed-230">此培训应包括实践练习，让用户可以体验这些操作及其结果。</span><span class="sxs-lookup"><span data-stu-id="f37ed-230">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="f37ed-231">步骤 2：定期审查使用情况和文件</span><span class="sxs-lookup"><span data-stu-id="f37ed-231">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="f37ed-232">在培训后的几周内，SharePoint Online 网站或团队的 SharePoint 管理员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f37ed-232">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="f37ed-233">分析网站或团队的使用情况，并将其与预期使用情况进行比较。</span><span class="sxs-lookup"><span data-stu-id="f37ed-233">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="f37ed-234">验证是否使用 Azure 信息保护子标签正确标记了高度敏感的文件。</span><span class="sxs-lookup"><span data-stu-id="f37ed-234">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="f37ed-235">根据需要重新培训用户。</span><span class="sxs-lookup"><span data-stu-id="f37ed-235">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="f37ed-236">用户采用结果</span><span class="sxs-lookup"><span data-stu-id="f37ed-236">User adoption results</span></span>

<span data-ttu-id="f37ed-237">敏感数字资产专门存储在针对高度管控数据的 SharePoint Online 网站或团队中，并且已对最敏感的资产应用了已配置的 Azure 信息保护子标签。</span><span class="sxs-lookup"><span data-stu-id="f37ed-237">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f37ed-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f37ed-238">See also</span></span>

[<span data-ttu-id="f37ed-239">部署指南</span><span class="sxs-lookup"><span data-stu-id="f37ed-239">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f37ed-240">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f37ed-240">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f37ed-241">保护开发/测试环境中的 SharePoint Online 网站安全</span><span class="sxs-lookup"><span data-stu-id="f37ed-241">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
