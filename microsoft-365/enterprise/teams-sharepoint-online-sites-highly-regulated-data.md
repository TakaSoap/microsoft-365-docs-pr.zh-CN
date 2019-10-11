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
ms.openlocfilehash: ece6547ba596fe53c4f3b3f6bfbaa6570a724c6a
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437822"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="67133-103">用于高度管控数据的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="67133-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="67133-104">*此方案适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="67133-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="67133-p101">Microsoft 365 企业版包含一整套基于云的服务，使用户可以创建、存储、保护和管理文件中存储的高度管控数据。这包括符合以下条件的数据：</span><span class="sxs-lookup"><span data-stu-id="67133-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="67133-107">受地区法规约束。</span><span class="sxs-lookup"><span data-stu-id="67133-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="67133-108">组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。</span><span class="sxs-lookup"><span data-stu-id="67133-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="67133-109">一个使用 Microsoft Teams 的类似方案正在开发中。</span><span class="sxs-lookup"><span data-stu-id="67133-109">A similar scenario using Microsoft Teams is in development.</span></span>
>

<span data-ttu-id="67133-110">满足此业务需求的 Microsoft 365 企业版基于云的方案要求用户执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67133-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="67133-111">在 SharePoint 团队网站中存储文件（文档、幻灯片和电子表格等）。</span><span class="sxs-lookup"><span data-stu-id="67133-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="67133-112">锁定网站以防止：</span><span class="sxs-lookup"><span data-stu-id="67133-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="67133-113">对不是网站 Office 365 组成员的用户进行访问。</span><span class="sxs-lookup"><span data-stu-id="67133-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="67133-114">网站成员向其他用户授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="67133-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="67133-115">非网站成员请求访问网站。</span><span class="sxs-lookup"><span data-stu-id="67133-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="67133-116">为 SharePoint 网站配置 Office 365 保留标签，作为阻止用户将文件发送到组织外部的默认方法。</span><span class="sxs-lookup"><span data-stu-id="67133-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="67133-117">使用随文件一起传输的加密信息对网站中最敏感的文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="67133-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="67133-118">添加对最敏感的文件的权限，这样，即使它们在网站外共享，打开文件仍需要具有权限的用户帐户提供有效凭据。</span><span class="sxs-lookup"><span data-stu-id="67133-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="67133-119">下表将此方案的要求映射到 Microsoft 365 企业版的功能。</span><span class="sxs-lookup"><span data-stu-id="67133-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="67133-120">**要求**</span><span class="sxs-lookup"><span data-stu-id="67133-120">**Requirement**</span></span> | <span data-ttu-id="67133-121">**Microsoft 365 企业版 功能**</span><span class="sxs-lookup"><span data-stu-id="67133-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="67133-122">存储文件</span><span class="sxs-lookup"><span data-stu-id="67133-122">Store files</span></span> | <span data-ttu-id="67133-123">SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="67133-123">SharePoint team sites</span></span> |
| <span data-ttu-id="67133-124">锁定网站</span><span class="sxs-lookup"><span data-stu-id="67133-124">Lock down the site</span></span> | <span data-ttu-id="67133-125">Azure Active Directory (Azure AD) 组和 SharePoint Online 团队网站权限</span><span class="sxs-lookup"><span data-stu-id="67133-125">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="67133-126">标记网站中的文件</span><span class="sxs-lookup"><span data-stu-id="67133-126">Label the files of the site</span></span> | <span data-ttu-id="67133-127">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="67133-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="67133-128">阻止向组织外发送文件的用户</span><span class="sxs-lookup"><span data-stu-id="67133-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="67133-129">Office 365 中的数据丢失防护 (DLP) 策略</span><span class="sxs-lookup"><span data-stu-id="67133-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="67133-130">加密网站中的所有文件</span><span class="sxs-lookup"><span data-stu-id="67133-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="67133-131">Office 365 灵敏度子标签</span><span class="sxs-lookup"><span data-stu-id="67133-131">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="67133-132">添加网站文件的权限</span><span class="sxs-lookup"><span data-stu-id="67133-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="67133-133">Office 365 灵敏度子标签</span><span class="sxs-lookup"><span data-stu-id="67133-133">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="67133-134">以下是用于安全 SharePoint 网站的配置。</span><span class="sxs-lookup"><span data-stu-id="67133-134">Here is the configuration for a secure SharePoint site.</span></span>

![用于高度管控数据场景的 SharePoint 网站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="67133-136">此方案要求已经部署：</span><span class="sxs-lookup"><span data-stu-id="67133-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="67133-137">[标识](identity-infrastructure.md)以及基础架构的[信息保护](infoprotect-infrastructure.md)阶段的步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="67133-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="67133-138">[SharePoint](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="67133-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="67133-139">以下各阶段将指导你完成用于高度管控数据的 SharePoint 网站的设计、配置和驱动采用。</span><span class="sxs-lookup"><span data-stu-id="67133-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<span data-ttu-id="67133-140">若要了解 Contoso Corporation（虚构但具代表性的跨国组织）如何为其研究团队设计 SharePoint 网站，请参阅此[示例配置](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="67133-140">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="67133-141">标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="67133-141">Identity and device access prerequisites</span></span>

<span data-ttu-id="67133-142">若要保护对 SharePoint 网站的访问，请确保已配置[标识和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="67133-142">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="67133-143">第 1 阶段：设计</span><span class="sxs-lookup"><span data-stu-id="67133-143">Phase 1: Design</span></span>

<span data-ttu-id="67133-144">若要创建用于高度管控数据的 SharePoint 网站，必须首先确定其用途。</span><span class="sxs-lookup"><span data-stu-id="67133-144">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="67133-145">例如，制造组织的研发部需要一个 SharePoint 网站来存储现有产品的当前设计规范，并需要一个协作处理新产品的位置。</span><span class="sxs-lookup"><span data-stu-id="67133-145">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="67133-146">仅允许研发部和选定的管理人员访问该网站。</span><span class="sxs-lookup"><span data-stu-id="67133-146">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="67133-147">该目的将推动基本配置项的确定，例如：</span><span class="sxs-lookup"><span data-stu-id="67133-147">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="67133-148">要分配给网站“文档”部分的 Office 365 保留标签以及该标签的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="67133-148">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="67133-149">由用户应用于网站中存储的高度敏感文件的 Office 365 敏感度子标签的设置</span><span class="sxs-lookup"><span data-stu-id="67133-149">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="67133-150">确定后，使用这些设置在第 2 阶段中配置网站。</span><span class="sxs-lookup"><span data-stu-id="67133-150">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="67133-151">步骤 1：Office 365 保留标签和 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="67133-151">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="67133-152">应用于 SharePoint 团队网站的“文档”部分时，Office 365 保留标签提供对存储在网站上的所有文件进行分类的默认方法。</span><span class="sxs-lookup"><span data-stu-id="67133-152">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="67133-153">对于用于高度管控数据的 SharePoint 网站，需要确定要使用的 Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="67133-153">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="67133-154">有关 Office 365 标签的设计注意事项，请参阅 [Office 365 分类和标签](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="67133-154">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="67133-p103">为保护敏感信息并防止意外或故意泄露，可以使用 DLP 策略。有关详细信息，请参阅此[概述](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。</span><span class="sxs-lookup"><span data-stu-id="67133-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="67133-157">对于 SharePoint 网站，必须为分配给网站的 Office 365 保留标签配置 DLP 策略，在用户尝试与外部用户共享文件时进行阻止。</span><span class="sxs-lookup"><span data-stu-id="67133-157">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="67133-158">步骤 2：Office 365 灵敏度子标签</span><span class="sxs-lookup"><span data-stu-id="67133-158">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="67133-159">若要对最敏感的文件提供加密和一组权限，用户必须应用 Office 365 敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="67133-159">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="67133-160">子标签存在于现有标签下。</span><span class="sxs-lookup"><span data-stu-id="67133-160">A sublabel exists under an existing label.</span></span> <span data-ttu-id="67133-161">例如，可在“高度管控”标签下创建“研发部”子标签。</span><span class="sxs-lookup"><span data-stu-id="67133-161">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="67133-162">对于用于高度管控数据的 SharePoint 网站，需要配置权限，以便只有网站成员可以打开和更改已附加子标签的文件。</span><span class="sxs-lookup"><span data-stu-id="67133-162">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="67133-163">已应用子标签的设置会随文件一起移动。</span><span class="sxs-lookup"><span data-stu-id="67133-163">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="67133-164">即使文件泄露到网站外，也只有拥有权限并经过身份验证的用户帐户才可以将其打开。</span><span class="sxs-lookup"><span data-stu-id="67133-164">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="67133-165">设计结果</span><span class="sxs-lookup"><span data-stu-id="67133-165">Design results</span></span>

<span data-ttu-id="67133-166">已确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="67133-166">You have determined the following:</span></span>

- <span data-ttu-id="67133-167">适当的 Office 365 保留标签以及与标签关联的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="67133-167">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="67133-168">包含加密和权限的 Office 365 敏感度子标签设置</span><span class="sxs-lookup"><span data-stu-id="67133-168">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="67133-169">第 2 阶段：配置</span><span class="sxs-lookup"><span data-stu-id="67133-169">Phase 2: Configure</span></span>

<span data-ttu-id="67133-170">此阶段将使用并实施第 1 阶段中确定的设置，为高度管控的数据创建 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="67133-170">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="67133-171">步骤 1：创建专用 SharePoint 团队网站，使其包含相应 Office 365 组的所有者和成员</span><span class="sxs-lookup"><span data-stu-id="67133-171">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="67133-172">请遵循[这些说明]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8)创建专用的 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="67133-172">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="67133-173">步骤 2：配置 SharePoint 团队网站的其他权限设置</span><span class="sxs-lookup"><span data-stu-id="67133-173">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="67133-174">在 SharePoint 网站中配置以下权限设置。</span><span class="sxs-lookup"><span data-stu-id="67133-174">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="67133-175">在工具栏中，依次单击设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67133-175">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="67133-176">在“网站权限”窗格中，单击“高级权限设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67133-176">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="67133-177">在浏览器的新“权限”标签页中，单击“访问请求设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67133-177">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="67133-178">在“**访问请求设置**”对话框中，取消选中“**允许成员共享网站以及个别文件和文件夹**”和“**允许访问请求**”（以便取消选中全部三个复选框），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="67133-178">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="67133-179">使用这些设置可以禁止网站用户组成员与其他成员共享网站以及非成员访问网站。</span><span class="sxs-lookup"><span data-stu-id="67133-179">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="67133-180">步骤 3：为网站配置 Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="67133-180">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="67133-181">按照[使用 Office 365 标签和 DLP 保护 SharePoint 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的说明执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67133-181">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="67133-182">创建并发布高度管控数据的保留标签（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="67133-182">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="67133-183">为网站配置步骤 1 中创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="67133-183">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="67133-184">为高度管控数据创建 DLP 策略以使用步骤 2 中创建的保留标签并阻止用户将文件发送到组织外部</span><span class="sxs-lookup"><span data-stu-id="67133-184">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="67133-185">步骤 4：为网站创建 Office 365 敏感度子标签</span><span class="sxs-lookup"><span data-stu-id="67133-185">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="67133-186">与可由任何人应用于任何文件的高度管控数据敏感度标签不同，安全网站需要其自己的子标签，使分配了子标签的文件：</span><span class="sxs-lookup"><span data-stu-id="67133-186">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="67133-187">启用加密，并且加密信息将与文件一起移动。</span><span class="sxs-lookup"><span data-stu-id="67133-187">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="67133-188">包含自定义权限，以便只有网站用户组的成员能打开文件。</span><span class="sxs-lookup"><span data-stu-id="67133-188">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="67133-189">若要以这种方式为网站中存储的文件实现更高的安全级别，必须配置一个新的敏感度标签，作为高度管控文件的常规标签的子标签。</span><span class="sxs-lookup"><span data-stu-id="67133-189">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="67133-190">只有网站的用户组成员才能在高度管控标签的子标签列表中看到该子标签。</span><span class="sxs-lookup"><span data-stu-id="67133-190">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="67133-191">请按照[此处](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)的说明，使用以下设置来配置用于高度管控文件的标签的子标签：</span><span class="sxs-lookup"><span data-stu-id="67133-191">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="67133-192">子标签的名称包含网站的名称，以便在将子标签分配给文件时实现轻松关联。</span><span class="sxs-lookup"><span data-stu-id="67133-192">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="67133-193">启用加密。</span><span class="sxs-lookup"><span data-stu-id="67133-193">Encryption is enabled.</span></span>
- <span data-ttu-id="67133-194">网站用户组具有共同创作权限。</span><span class="sxs-lookup"><span data-stu-id="67133-194">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="67133-195">配置结果</span><span class="sxs-lookup"><span data-stu-id="67133-195">Configuration results</span></span>

<span data-ttu-id="67133-196">已配置了以下内容：</span><span class="sxs-lookup"><span data-stu-id="67133-196">You have configured the following:</span></span>

- <span data-ttu-id="67133-197">SharePoint 网站上具有更严格的权限设置</span><span class="sxs-lookup"><span data-stu-id="67133-197">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="67133-198">将 Office 365 保留标签分配给 SharePoint 网站的“文档”部分</span><span class="sxs-lookup"><span data-stu-id="67133-198">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="67133-199">Office 365 保留标签的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="67133-199">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="67133-200">可由用户应用于网站中存储的最敏感文件的 Office 365 敏感度子标签，用于对文件加密并仅允许团队网站用户组中的成员进行“共同创作”访问</span><span class="sxs-lookup"><span data-stu-id="67133-200">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="67133-201">下面是配置结果。</span><span class="sxs-lookup"><span data-stu-id="67133-201">Here is the resulting configuration.</span></span>

![用于高度管控数据场景的 SharePoint 网站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="67133-203">下面是对网站中存储的文件应用了敏感度子标签的用户示例。</span><span class="sxs-lookup"><span data-stu-id="67133-203">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![用于高度管控数据场景的 SharePoint 网站](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="67133-205">第 3 阶段：驱动用户采用</span><span class="sxs-lookup"><span data-stu-id="67133-205">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="67133-206">用于高度管控数据的 SharePoint 网站对这些数据进行保护的前提是该网站一直用于存储和访问敏感文件。</span><span class="sxs-lookup"><span data-stu-id="67133-206">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="67133-207">此阶段依赖于用户改变其习惯和喜好，因此是最困难的阶段。</span><span class="sxs-lookup"><span data-stu-id="67133-207">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="67133-208">例如，习惯于在 USB 驱动器或基于云的个人存储解决方案中存储敏感文件的员工现在必须将这些文件专门存储在用于高度管控数据的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="67133-208">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="67133-209">步骤 1：培训用户</span><span class="sxs-lookup"><span data-stu-id="67133-209">Step 1: Train your users</span></span>

<span data-ttu-id="67133-210">完成配置后，对作为网站访问组成员的一组用户培训以下内容：</span><span class="sxs-lookup"><span data-stu-id="67133-210">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="67133-211">有关使用新网站保护重要文件的重要性以及高度管控数据泄露的后果，例如法律后果、监管罚款、勒索软件或失去竞争优势。</span><span class="sxs-lookup"><span data-stu-id="67133-211">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="67133-212">如何访问网站及其文件。</span><span class="sxs-lookup"><span data-stu-id="67133-212">How to access the site and its files.</span></span>
- <span data-ttu-id="67133-213">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="67133-213">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="67133-214">DLP 策略如何阻止它们在外部共享文件。</span><span class="sxs-lookup"><span data-stu-id="67133-214">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="67133-215">如何使用网站的子标签来标记最敏感的文件。</span><span class="sxs-lookup"><span data-stu-id="67133-215">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="67133-216">子标签如何保护文件（即使文件泄露到网站外部）。</span><span class="sxs-lookup"><span data-stu-id="67133-216">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="67133-217">此培训应包括实践练习，让用户可以体验这些操作及其结果。</span><span class="sxs-lookup"><span data-stu-id="67133-217">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="67133-218">步骤 2：定期审查使用情况和文件</span><span class="sxs-lookup"><span data-stu-id="67133-218">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="67133-219">在培训后的几周内，SharePoint 网站的 SharePoint 管理员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67133-219">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="67133-220">分析网站的使用情况，并将其与预期使用情况进行比较。</span><span class="sxs-lookup"><span data-stu-id="67133-220">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="67133-221">验证是否使用敏感度子标签正确标记了高度敏感的文件。</span><span class="sxs-lookup"><span data-stu-id="67133-221">Verify that highly sensitive files have been properly labeled with the sensitivity sublabel.</span></span>

<span data-ttu-id="67133-222">根据需要重新培训用户。</span><span class="sxs-lookup"><span data-stu-id="67133-222">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="67133-223">用户采用结果</span><span class="sxs-lookup"><span data-stu-id="67133-223">User adoption results</span></span>

<span data-ttu-id="67133-224">高度管控的文件专门存储在用于高度管控数据的 SharePoint 网站上，并且最敏感的文件应用了网站的敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="67133-224">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="67133-225">Contoso Corporation 如何部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="67133-225">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="67133-226">Contoso Corporation 是一家虚构但具代表性的全球大型制企业，总部设在法国巴黎。</span><span class="sxs-lookup"><span data-stu-id="67133-226">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="67133-227">了解 Contoso 如何设计、配置并推动其在巴黎、莫斯科、纽约、北京和班加罗尔的研究团队采用[安全的 SharePoint 网站](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。</span><span class="sxs-lookup"><span data-stu-id="67133-227">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="67133-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67133-228">See also</span></span>

[<span data-ttu-id="67133-229">部署指南</span><span class="sxs-lookup"><span data-stu-id="67133-229">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="67133-230">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="67133-230">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

