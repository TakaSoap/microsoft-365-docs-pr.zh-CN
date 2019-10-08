---
title: 用于高度管控数据的 SharePoint 网站
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 创建安全的 SharePoint 团队网站来存储最有价值和敏感的文件。
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403173"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="7ac8e-103">用于高度管控数据的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="7ac8e-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="7ac8e-104">*此方案适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="7ac8e-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7ac8e-p101">Microsoft 365 企业版包含一整套基于云的服务，使用户可以创建、存储和保护文件中存储的高度管控数据。这包括符合以下条件的数据：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="7ac8e-107">受地区法规约束。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="7ac8e-108">组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="7ac8e-109">满足此业务需求的 Microsoft 365 企业版基于云的方案要求用户执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="7ac8e-110">在 SharePoint 团队网站中存储文件（文档、幻灯片和电子表格等）。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="7ac8e-111">锁定网站以防止：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="7ac8e-112">对不是网站 Office 365 组成员的用户进行访问。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="7ac8e-113">网站成员向其他用户授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="7ac8e-114">非网站成员请求访问网站。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="7ac8e-115">为 SharePoint 网站配置 Office 365 保留标签，作为阻止用户将文件发送到组织外部的默认方法。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="7ac8e-116">使用随文件一起传输的加密信息对网站中最敏感的文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="7ac8e-117">添加对最敏感的文件的权限，这样，即使它们在网站外共享，打开文件仍需要具有权限的用户帐户提供有效凭据。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="7ac8e-118">下表将此方案的要求映射到 Microsoft 365 企业版的功能。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="7ac8e-119">**要求**</span><span class="sxs-lookup"><span data-stu-id="7ac8e-119">**Requirement**</span></span> | <span data-ttu-id="7ac8e-120">**Microsoft 365 企业版 功能**</span><span class="sxs-lookup"><span data-stu-id="7ac8e-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="7ac8e-121">存储文件</span><span class="sxs-lookup"><span data-stu-id="7ac8e-121">Store files online</span></span> | <span data-ttu-id="7ac8e-122">SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="7ac8e-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="7ac8e-123">锁定网站</span><span class="sxs-lookup"><span data-stu-id="7ac8e-123">Lock down the site</span></span> | <span data-ttu-id="7ac8e-124">Azure Active Directory (Azure AD) 组和 SharePoint Online 团队网站权限</span><span class="sxs-lookup"><span data-stu-id="7ac8e-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="7ac8e-125">标记网站中的文件</span><span class="sxs-lookup"><span data-stu-id="7ac8e-125">Label the digital assets of the site</span></span> | <span data-ttu-id="7ac8e-126">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="7ac8e-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="7ac8e-127">阻止向组织外发送文件的用户</span><span class="sxs-lookup"><span data-stu-id="7ac8e-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="7ac8e-128">Office 365 中的数据丢失防护 (DLP) 策略</span><span class="sxs-lookup"><span data-stu-id="7ac8e-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="7ac8e-129">加密网站中的所有文件</span><span class="sxs-lookup"><span data-stu-id="7ac8e-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="7ac8e-130">Office 365 灵敏度子标签</span><span class="sxs-lookup"><span data-stu-id="7ac8e-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="7ac8e-131">添加网站文件的权限</span><span class="sxs-lookup"><span data-stu-id="7ac8e-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="7ac8e-132">Office 365 灵敏度子标签</span><span class="sxs-lookup"><span data-stu-id="7ac8e-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="7ac8e-133">以下是用于安全 SharePoint 网站的配置。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-133">Here is the configuration for a SharePoint Online site.</span></span>

![用于高度管控数据场景的 SharePoint 网站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="7ac8e-135">此方案要求已经部署：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="7ac8e-136">[标识](identity-infrastructure.md)以及基础架构的[信息保护](infoprotect-infrastructure.md)阶段的步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="7ac8e-137">[SharePoint](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-137">SharePoint</span></span>

<span data-ttu-id="7ac8e-138">以下各阶段将指导你完成用于高度管控数据的 SharePoint 网站的设计、配置和驱动采用。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="7ac8e-139">若要了解 Contoso Corporation（虚构但具代表性的跨国组织）如何为其研究团队设计 SharePoint 网站，请参阅此[示例配置](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="7ac8e-140">标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="7ac8e-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="7ac8e-141">若要保护对 SharePoint 网站的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="7ac8e-142">第 1 阶段：设计</span><span class="sxs-lookup"><span data-stu-id="7ac8e-142">Phase 1: Design</span></span>

<span data-ttu-id="7ac8e-143">若要创建用于高度管控数据的 SharePoint 网站，必须首先确定其用途。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="7ac8e-144">例如，制造组织的研发部需要一个 SharePoint 网站来存储现有产品的当前设计规范，并需要一个协作处理新产品的位置。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="7ac8e-145">仅允许研发部和选定的管理人员访问该网站。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="7ac8e-146">该目的将推动基本配置项的确定，例如：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="7ac8e-147">要分配给网站“文档”部分的 Office 365 保留标签以及该标签的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="7ac8e-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="7ac8e-148">由用户应用于网站中存储的高度敏感文件的 Office 365 敏感度子标签的设置</span><span class="sxs-lookup"><span data-stu-id="7ac8e-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="7ac8e-149">确定后，使用这些设置在第 2 阶段中配置网站。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="7ac8e-150">步骤 1：Office 365 保留标签和 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="7ac8e-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="7ac8e-151">应用于 SharePoint 团队网站的“文档”部分时，Office 365 保留标签提供对存储在网站上的所有文件进行分类的默认方法。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="7ac8e-152">对于用于高度管控数据的 SharePoint 网站，需要确定要使用的 Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="7ac8e-153">有关 Office 365 标签的设计注意事项，请参阅 [Office 365 分类和标签](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="7ac8e-p103">为保护敏感信息并防止意外或故意泄露，可以使用 DLP 策略。有关详细信息，请参阅此[概述](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="7ac8e-156">对于 SharePoint 网站，必须为分配给网站的 Office 365 保留标签配置 DLP 策略，在用户尝试与外部用户共享文件时进行阻止。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="7ac8e-157">步骤 2：Office 365 灵敏度子标签</span><span class="sxs-lookup"><span data-stu-id="7ac8e-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="7ac8e-158">若要对最敏感的文件提供加密和一组权限，用户必须应用 Office 365 敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="7ac8e-159">子标签存在于现有标签下。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="7ac8e-160">例如，可在“高度管控”标签下创建“研发部”子标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="7ac8e-161">对于用于高度管控数据的 SharePoint 网站，需要配置权限，以便只有网站成员可以打开和更改已附加子标签的文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="7ac8e-162">已应用子标签的设置会随文件一起移动。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="7ac8e-163">即使文件泄露到网站外，也只有拥有权限并经过身份验证的用户帐户才可以将其打开。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="7ac8e-164">设计结果</span><span class="sxs-lookup"><span data-stu-id="7ac8e-164">Design results</span></span>

<span data-ttu-id="7ac8e-165">已确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-165">You have determined the following:</span></span>

- <span data-ttu-id="7ac8e-166">适当的 Office 365 保留标签以及与标签关联的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="7ac8e-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="7ac8e-167">包含加密和权限的 Office 365 敏感度子标签设置</span><span class="sxs-lookup"><span data-stu-id="7ac8e-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="7ac8e-168">第 2 阶段：配置</span><span class="sxs-lookup"><span data-stu-id="7ac8e-168">Phase 2: Configure</span></span>

<span data-ttu-id="7ac8e-169">此阶段将使用并实施第 1 阶段中确定的设置，为高度管控的数据创建 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="7ac8e-170">步骤 1：创建专用 SharePoint 团队网站，使其包含相应 Office 365 组的所有者和成员</span><span class="sxs-lookup"><span data-stu-id="7ac8e-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="7ac8e-171">请遵循[这些说明]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8)创建专用的 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="7ac8e-172">步骤 2：配置 SharePoint 团队网站的其他权限设置</span><span class="sxs-lookup"><span data-stu-id="7ac8e-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="7ac8e-173">在 SharePoint 网站中配置以下权限设置。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="7ac8e-174">在工具栏中，依次单击设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="7ac8e-175">在“网站权限”窗格中，单击“高级权限设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="7ac8e-176">在浏览器的新“权限”标签页中，单击“访问请求设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="7ac8e-177">在“**访问请求设置**”对话框中，取消选中“**允许成员共享网站以及个别文件和文件夹**”和“**允许访问请求**”（以便取消选中全部三个复选框），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-177">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="7ac8e-178">使用这些设置可以禁止网站用户组成员与其他成员共享网站以及非成员访问网站。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="7ac8e-179">步骤 3：为网站配置 Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="7ac8e-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="7ac8e-180">按照[使用 Office 365 标签和 DLP 保护 SharePoint 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的说明执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="7ac8e-181">创建并发布高度管控数据的保留标签（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="7ac8e-182">为网站配置步骤 1 中创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="7ac8e-183">为高度管控数据创建 DLP 策略以使用步骤 2 中创建的保留标签并阻止用户将文件发送到组织外部</span><span class="sxs-lookup"><span data-stu-id="7ac8e-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="7ac8e-184">步骤 4：为网站创建 Office 365 敏感度子标签</span><span class="sxs-lookup"><span data-stu-id="7ac8e-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="7ac8e-185">与可由任何人应用于任何文件的高度管控数据敏感度标签不同，安全网站需要其自己的子标签，使分配了子标签的文件：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="7ac8e-186">启用加密，并且加密信息将与文件一起移动。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="7ac8e-187">包含自定义权限，以便只有网站用户组的成员能打开文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="7ac8e-188">若要以这种方式为网站中存储的文件实现更高的安全级别，必须配置一个新的敏感度标签，作为高度管控文件的常规标签的子标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="7ac8e-189">只有网站的用户组成员才能在高度管控标签的子标签列表中看到该子标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="7ac8e-190">请按照[此处](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)的说明，使用以下设置来配置用于高度管控文件的标签的子标签：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="7ac8e-191">子标签的名称包含网站的名称，以便在将子标签分配给文件时实现轻松关联。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="7ac8e-192">启用加密。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-192">Encryption is enabled.</span></span>
- <span data-ttu-id="7ac8e-193">网站用户组具有共同创作权限。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="7ac8e-194">配置结果</span><span class="sxs-lookup"><span data-stu-id="7ac8e-194">Configuration results</span></span>

<span data-ttu-id="7ac8e-195">已配置了以下内容：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-195">You have configured the following:</span></span>

- <span data-ttu-id="7ac8e-196">SharePoint 网站上具有更严格的权限设置</span><span class="sxs-lookup"><span data-stu-id="7ac8e-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="7ac8e-197">将 Office 365 保留标签分配给 SharePoint 网站的“文档”部分</span><span class="sxs-lookup"><span data-stu-id="7ac8e-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="7ac8e-198">Office 365 保留标签的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="7ac8e-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="7ac8e-199">可由用户应用于网站中存储的最敏感文件的 Office 365 敏感度子标签，用于对文件加密并仅允许团队网站用户组中的成员进行“共同创作”访问</span><span class="sxs-lookup"><span data-stu-id="7ac8e-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="7ac8e-200">下面是配置结果。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-200">Here is the resulting configuration.</span></span>

![用于高度管控数据场景的 SharePoint 网站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="7ac8e-202">下面是对网站中存储的文件应用了敏感度子标签的用户示例。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![用于高度管控数据场景的 SharePoint 网站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="7ac8e-204">第 3 阶段：驱动用户采用</span><span class="sxs-lookup"><span data-stu-id="7ac8e-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="7ac8e-205">用于高度管控数据的 SharePoint 网站对这些数据进行保护的前提是该网站一直用于存储和访问敏感文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="7ac8e-206">此阶段依赖于用户改变其习惯和喜好，因此是最困难的阶段。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="7ac8e-207">例如，习惯于在 USB 驱动器或基于云的个人存储解决方案中存储敏感文件的员工现在必须将这些文件专门存储在用于高度管控数据的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="7ac8e-208">步骤 1：培训用户</span><span class="sxs-lookup"><span data-stu-id="7ac8e-208">Step 1: Train your users</span></span>

<span data-ttu-id="7ac8e-209">完成配置后，对作为网站访问组成员的一组用户培训以下内容：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="7ac8e-210">有关使用新网站保护重要文件的重要性以及高度管控数据泄露的后果，例如法律后果、监管罚款、勒索软件或失去竞争优势。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="7ac8e-211">如何访问网站及其文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="7ac8e-212">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="7ac8e-213">DLP 策略如何阻止它们在外部共享文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="7ac8e-214">如何使用网站的子标签来标记最敏感的文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="7ac8e-215">子标签如何保护文件（即使文件泄露到网站外部）。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="7ac8e-216">此培训应包括实践练习，让用户可以体验这些操作及其结果。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="7ac8e-217">步骤 2：定期审查使用情况和文件</span><span class="sxs-lookup"><span data-stu-id="7ac8e-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="7ac8e-218">在培训后的几周内，SharePoint 网站的 SharePoint 管理员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ac8e-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="7ac8e-219">分析网站的使用情况，并将其与预期使用情况进行比较。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="7ac8e-220">验证是否使用敏感度子标签正确标记了高度敏感的文件。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="7ac8e-221">根据需要重新培训用户。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="7ac8e-222">用户采用结果</span><span class="sxs-lookup"><span data-stu-id="7ac8e-222">User adoption results</span></span>

<span data-ttu-id="7ac8e-223">高度管控的文件专门存储在用于高度管控数据的 SharePoint 网站上，并且最敏感的文件应用了网站的敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="7ac8e-224">Contoso Corporation 如何部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="7ac8e-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7ac8e-225">Contoso Corporation 是一家虚构但具代表性的全球大型制企业，总部设在法国巴黎。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="7ac8e-226">了解 Contoso 如何设计、配置并推动其在巴黎、莫斯科、纽约、北京和班加罗尔的研究团队采用[安全的 SharePoint 网站](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac8e-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="7ac8e-227">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ac8e-227">See also</span></span>

[<span data-ttu-id="7ac8e-228">部署指南</span><span class="sxs-lookup"><span data-stu-id="7ac8e-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7ac8e-229">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="7ac8e-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

