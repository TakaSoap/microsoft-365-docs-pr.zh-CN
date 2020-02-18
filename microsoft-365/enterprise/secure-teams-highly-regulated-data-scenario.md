---
title: 用于高度管控数据的 Teams
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建安全团队来存储最有价值的敏感文件。
ms.openlocfilehash: e2499c6e9061704846f4649ade43f74bd5632e8b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084232"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="099f1-103">用于高度管控数据的 Teams</span><span class="sxs-lookup"><span data-stu-id="099f1-103">Teams for highly regulated data</span></span>

<span data-ttu-id="099f1-104">本文为你提供在 Microsoft Teams 中配置私人团队的建议和步骤，它只允许 Office 365 团队组的成员和所有者访问 Teams 功能 — 例如聊天、会议和文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="099f1-105">除了基于 Office 365 组的专用访问之外，本文还介绍了如何配置基础专用 SharePoint 团队网站，你可以从团队频道的“**文件**”部分进行访问，以获得存储高度管控数据所需的其他安全性。</span><span class="sxs-lookup"><span data-stu-id="099f1-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="099f1-106">在此 SharePoint 团队网站上，可存储和协作处理文件、页面、共享日历、任务、笔记本和列表。</span><span class="sxs-lookup"><span data-stu-id="099f1-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="099f1-107">[此处](teams-sharepoint-online-sites-highly-regulated-data.md)是使用 SharePoint 的类似方案。</span><span class="sxs-lookup"><span data-stu-id="099f1-107">A similar scenario using SharePoint is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="099f1-108">针对高度管控数据的团队的配置元素如下：</span><span class="sxs-lookup"><span data-stu-id="099f1-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="099f1-109">具有相应的 Office 365 组的私人团队，该组具有所有者和成员用户帐户。</span><span class="sxs-lookup"><span data-stu-id="099f1-109">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="099f1-110">基础 SharePoint 团队网站上的其他安全性：</span><span class="sxs-lookup"><span data-stu-id="099f1-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="099f1-111">阻止网站成员向其他人授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="099f1-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="099f1-112">阻止非网站成员请求访问该网站。</span><span class="sxs-lookup"><span data-stu-id="099f1-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="099f1-113">基础 SharePoint 网站的 Office 365 保留标签，作为定义保留策略的默认方法，该标签将自动应用于该网站上的新文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-113">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="099f1-114">数据丢失防护 (DLP) 策略，该策略使用保留标签并阻止用户在组织外部共享或发送文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="099f1-115">Office 365 敏感度标签或高度管控标签的子标签，它已启用加密并且为 Office 365 团队组提供了共同创作权限。</span><span class="sxs-lookup"><span data-stu-id="099f1-115">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="099f1-116">通过 Word、Excel 和 PowerPoint 中的“**敏感度**”菜单栏选项，用户可以为团队的“**文件**”部分中存储的文件应用标签或子标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-116">Users apply the label or sublabel to files stored in **Files** section of the team from the **Sensitivity** menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="099f1-117">下面是使用敏感度标签生成的配置。</span><span class="sxs-lookup"><span data-stu-id="099f1-117">Here is the resulting configuration with a sensitivity label.</span></span>

![安全团队方案配置](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="099f1-119">要快速概览，请观看此简短视频。</span><span class="sxs-lookup"><span data-stu-id="099f1-119">For a quick overview, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="099f1-120">有关这种情况的 1 页摘要，请参阅[针对高度管控数据海报的 Teams](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)。</span><span class="sxs-lookup"><span data-stu-id="099f1-120">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="099f1-121">[![针对高度管控数据海报的 Teams](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="099f1-121">[![Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="099f1-122">还可以下载 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) 或 [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) 格式的海报，并按 letter、legal 或 tabloid (11 x 17) 大小的纸张打印。</span><span class="sxs-lookup"><span data-stu-id="099f1-122">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="099f1-123">阶段 1：为高度管控数据配置团队</span><span class="sxs-lookup"><span data-stu-id="099f1-123">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="099f1-124">端到端配置包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="099f1-124">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="099f1-125">配置标识和设备访问。</span><span class="sxs-lookup"><span data-stu-id="099f1-125">Configure identity and device access.</span></span>
2. <span data-ttu-id="099f1-126">创建私人团队。</span><span class="sxs-lookup"><span data-stu-id="099f1-126">Create a private team.</span></span>
3. <span data-ttu-id="099f1-127">配置基础 SharePoint 网站的其他安全性。</span><span class="sxs-lookup"><span data-stu-id="099f1-127">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="099f1-128">创建保留标签和 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="099f1-128">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="099f1-129">创建标签或高度管控标签的子标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-129">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="099f1-130">步骤 1：配置标识和设备访问</span><span class="sxs-lookup"><span data-stu-id="099f1-130">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="099f1-131">若要保护对团队及其基础 SharePoint 网站的访问，请确保已配置[标识和设备访问策略](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)以及建议的 [SharePoint Online 访问策略](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="099f1-131">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="099f1-132">步骤 2：创建私人团队</span><span class="sxs-lookup"><span data-stu-id="099f1-132">Step 2: Create a private team</span></span>

<span data-ttu-id="099f1-133">请按照[这些说明](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)创建私人团队。</span><span class="sxs-lookup"><span data-stu-id="099f1-133">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="099f1-134">创建私人团队时，以下是默认权限：</span><span class="sxs-lookup"><span data-stu-id="099f1-134">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="099f1-135">Office 365 团队组（团队组）具有组所有者和组成员</span><span class="sxs-lookup"><span data-stu-id="099f1-135">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="099f1-136">对于基础 SharePoint 团队网站（团队网站）：</span><span class="sxs-lookup"><span data-stu-id="099f1-136">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="099f1-137">已为团队组所有者配置网站集管理员</span><span class="sxs-lookup"><span data-stu-id="099f1-137">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="099f1-138">对于团队网站：</span><span class="sxs-lookup"><span data-stu-id="099f1-138">For the Team Site:</span></span> 
    - <span data-ttu-id="099f1-139">具有“完全控制”权限级别的团队网站所有者 SharePoint 组已设置为团队组所有者</span><span class="sxs-lookup"><span data-stu-id="099f1-139">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="099f1-140">具有“编辑”权限级别的团队网站成员 SharePoint 组已设置为团队组成员</span><span class="sxs-lookup"><span data-stu-id="099f1-140">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="099f1-141">具有“读取”权限级别的团队网站访问者 SharePoint 组没有任何组或用户帐户</span><span class="sxs-lookup"><span data-stu-id="099f1-141">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="099f1-142">下面是团队网站的默认权限。</span><span class="sxs-lookup"><span data-stu-id="099f1-142">Here are the default permissions for the Team Site.</span></span>

![团队网站的默认权限](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="099f1-144">如果查看“编辑”权限级别的\<团队名称 > 所有者 SharePoint 组，则不会显示\<团队名称 > 所有者。</span><span class="sxs-lookup"><span data-stu-id="099f1-144">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="099f1-145">生成的权限允许：</span><span class="sxs-lookup"><span data-stu-id="099f1-145">The resulting permissions allow:</span></span>

- <span data-ttu-id="099f1-146">团队组所有者管理网站，并对网站内容拥有完全控制权。</span><span class="sxs-lookup"><span data-stu-id="099f1-146">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="099f1-147">团队组成员在网站上创建和编辑文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-147">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="099f1-148">权限维护与团队成员和所有者维护相同。</span><span class="sxs-lookup"><span data-stu-id="099f1-148">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="099f1-149">下面是到目前为止生成的配置。</span><span class="sxs-lookup"><span data-stu-id="099f1-149">Here’s the resulting configuration so far.</span></span>

![安全团队方案配置的步骤 2](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="099f1-151">步骤 3：配置基础 SharePoint 网站的其他安全性</span><span class="sxs-lookup"><span data-stu-id="099f1-151">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="099f1-152">对于团队网站，请配置以下权限设置。</span><span class="sxs-lookup"><span data-stu-id="099f1-152">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="099f1-153">在工具栏中，依次单击设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="099f1-153">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="099f1-154">在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="099f1-154">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="099f1-155">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。</span><span class="sxs-lookup"><span data-stu-id="099f1-155">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="099f1-156">关闭“**允许访问请求**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="099f1-156">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="099f1-157">使用这些设置，可以禁止团队组成员与其他成员共享团队网站以及非成员请求访问团队网站。</span><span class="sxs-lookup"><span data-stu-id="099f1-157">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="099f1-158">下面是到目前为止生成的配置。</span><span class="sxs-lookup"><span data-stu-id="099f1-158">Here’s the resulting configuration so far.</span></span>

![安全团队方案配置的步骤 3](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="099f1-160">步骤 4：创建保留标签和 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="099f1-160">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="099f1-161">按照[这些说明](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="099f1-161">Use [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) to:</span></span>

1. <span data-ttu-id="099f1-162">创建并发布高度管控数据的保留标签（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="099f1-162">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="099f1-163">为团队网站配置步骤 1 中创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-163">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="099f1-164">为高度管控数据创建 DLP 策略以使用步骤 2 中创建的保留标签并阻止用户将文件发送到组织外部。</span><span class="sxs-lookup"><span data-stu-id="099f1-164">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="099f1-165">你还可以基于 [DLP 策略模板](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates)，根据其他要求（例如健康和金融行业的法规要求）来配置策略。</span><span class="sxs-lookup"><span data-stu-id="099f1-165">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="099f1-166">下面是到目前为止生成的配置。</span><span class="sxs-lookup"><span data-stu-id="099f1-166">Here’s the resulting configuration so far.</span></span>

![安全团队方案配置的步骤 4](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a><span data-ttu-id="099f1-168">步骤 5：创建敏感度标签或高度管控敏感度标签的子标签</span><span class="sxs-lookup"><span data-stu-id="099f1-168">Step 5: Create a sensitivity label or a sublabel of the highly regulated sensitivity label</span></span>

<span data-ttu-id="099f1-169">与可由任何人应用于任何文件的高度管控数据敏感度标签不同，安全团队需要其自己的标签或子标签，以使分配的文件：</span><span class="sxs-lookup"><span data-stu-id="099f1-169">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="099f1-170">启用加密，并且加密信息将与文件一起移动。</span><span class="sxs-lookup"><span data-stu-id="099f1-170">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="099f1-171">包含自定义权限，以便只有团队组的成员能打开文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-171">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="099f1-172">若要以这种方式为团队网站中存储的文件实现更高的安全级别，必须配置一个新的敏感度标签，以用作其自身标签，或作为高度管控文件的常规标签的子标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-172">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="099f1-173">只有团队组成员才能在其标签列表中看到它。</span><span class="sxs-lookup"><span data-stu-id="099f1-173">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="099f1-174">如果需要将少量标签应用于全局和各个私人团队，请使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-174">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="099f1-175">如果你拥有大量标签，或者希望在高度管控标签下整理私人团队的标签，请使用敏感度子标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-175">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="099f1-176">[按照这些说明](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)，使用以下设置配置单独的标签或子标签：</span><span class="sxs-lookup"><span data-stu-id="099f1-176">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="099f1-177">标签名称包含团队名称</span><span class="sxs-lookup"><span data-stu-id="099f1-177">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="099f1-178">启用加密</span><span class="sxs-lookup"><span data-stu-id="099f1-178">Encryption is enabled</span></span>
- <span data-ttu-id="099f1-179">团队组具有共同创作权限</span><span class="sxs-lookup"><span data-stu-id="099f1-179">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="099f1-180">下面是使用新标签生成的配置。</span><span class="sxs-lookup"><span data-stu-id="099f1-180">Here’s the resulting configuration with the new label.</span></span>

![安全团队方案配置的步骤 5](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="099f1-182">下面是敏感度标签与团队组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="099f1-182">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![团队组与标签权限之间的关系](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="099f1-184">如果为用户定义的权限配置敏感度标签或子标签或具有到期日期，则无法从 Teams 或 SharePoint 中打开文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-184">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="099f1-185">必须使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="099f1-185">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="099f1-186">自定义权限</span><span class="sxs-lookup"><span data-stu-id="099f1-186">Custom permissions</span></span>

<span data-ttu-id="099f1-187">你还可以为团队网站配置自定义 SharePoint 网站权限，并根据需要配置其相应的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-187">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="099f1-188">下面是两个示例。</span><span class="sxs-lookup"><span data-stu-id="099f1-188">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="099f1-189">示例 1：委派 SharePoint 网站管理</span><span class="sxs-lookup"><span data-stu-id="099f1-189">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="099f1-190">如果团队所有者没有 SharePoint 管理经验，或者希望委派团队网站的管理，则他们可以将 SharePoint 管理员的用户帐户添加到团队所有者列表中。</span><span class="sxs-lookup"><span data-stu-id="099f1-190">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="099f1-191">但是，SharePoint 管理员可以完全访问团队及其所有资源，并且可以打开应用了敏感度标签的文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-191">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="099f1-192">为了防止过度授予特权，请在网站的高级权限设置中将 SharePoint 管理员的用户帐户添加到团队网站所有者 SharePoint 组中。</span><span class="sxs-lookup"><span data-stu-id="099f1-192">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="099f1-193">SharePoint 管理员可以管理网站，但是将无法访问团队及其任何资源，也无法打开分配了敏感度标签的文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-193">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="099f1-194">示例 2：允许仅查看带标签的文件</span><span class="sxs-lookup"><span data-stu-id="099f1-194">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="099f1-195">如果某些员工只需要查看团队网站中带标签的文件内容，可将其个人用户帐户添加到：</span><span class="sxs-lookup"><span data-stu-id="099f1-195">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="099f1-196">\<团队名称 > 访问者 SharePoint 组，默认情况下它具有“读取”权限级别。</span><span class="sxs-lookup"><span data-stu-id="099f1-196">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="099f1-197">具有查看者权限的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-197">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="099f1-198">下面是标签上生成的权限。</span><span class="sxs-lookup"><span data-stu-id="099f1-198">Here are the resulting permissions on the label.</span></span>

![用于查看带标签的文件的自定义权限示例](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="099f1-200">网站访问者将能够直接访问团队网站，并查看已应用子标签的文件内容。</span><span class="sxs-lookup"><span data-stu-id="099f1-200">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="099f1-201">但是，由于它们不是团队组的成员，因此不能访问团队或其任何资源。</span><span class="sxs-lookup"><span data-stu-id="099f1-201">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="099f1-202">阶段 2：驱动团队成员的用户采用</span><span class="sxs-lookup"><span data-stu-id="099f1-202">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="099f1-203">随着团队的建立，是时候驱动该团队的采用以及提升它对团队成员的额外安全性。</span><span class="sxs-lookup"><span data-stu-id="099f1-203">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="099f1-204">步骤 1：培训用户</span><span class="sxs-lookup"><span data-stu-id="099f1-204">Step 1: Train your users</span></span>

<span data-ttu-id="099f1-205">团队组成员可以访问团队及其所有资源，包括聊天、会议和其他应用。</span><span class="sxs-lookup"><span data-stu-id="099f1-205">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="099f1-206">使用频道的“**文件**”部分中的文件时，团队组成员必须将敏感度标签或子标签分配给为安全团队创建的文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-206">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="099f1-207">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="099f1-207">Here’s an example.</span></span>

![将标签应用于安全团队中的文件的示例](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="099f1-209">将标签应用于受保护的文件时。</span><span class="sxs-lookup"><span data-stu-id="099f1-209">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="099f1-210">团队组成员可以在 Teams 中打开它并进行实时协作。</span><span class="sxs-lookup"><span data-stu-id="099f1-210">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="099f1-211">它已加密，并且包含为团队组成员提供的共同创作权限集。</span><span class="sxs-lookup"><span data-stu-id="099f1-211">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="099f1-212">如果文件离开网站并转发给恶意用户，则他们必须提供作为团队组成员的用户帐户的凭据，这样才能打开文件并查看其内容。</span><span class="sxs-lookup"><span data-stu-id="099f1-212">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="099f1-213">培训团队成员：</span><span class="sxs-lookup"><span data-stu-id="099f1-213">Train your team members:</span></span>

- <span data-ttu-id="099f1-214">了解使用新团队访问聊天、会议、文件和团队网站的其他资源的重要性以及高度管控数据泄露的后果，例如法律后果、监管罚款、勒索软件或失去竞争优势。</span><span class="sxs-lookup"><span data-stu-id="099f1-214">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="099f1-215">如何访问团队。</span><span class="sxs-lookup"><span data-stu-id="099f1-215">How to access the team.</span></span>
- <span data-ttu-id="099f1-216">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-216">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="099f1-217">DLP 策略如何阻止它们在外部共享文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-217">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="099f1-218">如何使用团队的自定义标签或子标签来标记文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-218">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="099f1-219">标签或子标签如何保护文件（即使文件泄露到网站外部）。</span><span class="sxs-lookup"><span data-stu-id="099f1-219">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="099f1-220">此培训应包括实践练习，让团队成员可以体验这些功能及其结果。</span><span class="sxs-lookup"><span data-stu-id="099f1-220">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="099f1-221">步骤 2：定期审查使用情况并处理团队成员的反馈意见</span><span class="sxs-lookup"><span data-stu-id="099f1-221">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="099f1-222">在培训后的几周内：</span><span class="sxs-lookup"><span data-stu-id="099f1-222">In the weeks after training:</span></span>

- <span data-ttu-id="099f1-223">快速处理团队成员的反馈意见并微调相关策略和配置。</span><span class="sxs-lookup"><span data-stu-id="099f1-223">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="099f1-224">分析团队的使用情况，并将其与预期使用情况进行比较。</span><span class="sxs-lookup"><span data-stu-id="099f1-224">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="099f1-225">验证是否使用自定义敏感度标签或子标签正确标记了高度管控的文件。</span><span class="sxs-lookup"><span data-stu-id="099f1-225">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="099f1-226">通过查看 SharePoint 中的文件夹并使用“**添加列**”的“**显示/隐藏列**”选项添加“**敏感度**”列，可以查看为哪些文件分配了标签。</span><span class="sxs-lookup"><span data-stu-id="099f1-226">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="099f1-227">根据需要重新培训用户。</span><span class="sxs-lookup"><span data-stu-id="099f1-227">Retrain your users as needed.</span></span>

## <a name="demonstrate-this-in-a-test-environment"></a><span data-ttu-id="099f1-228">在测试环境中演示这种情况</span><span class="sxs-lookup"><span data-stu-id="099f1-228">Demonstrate this in a test environment</span></span>

<span data-ttu-id="099f1-229">若要构建自己的测试环境以测试团队的敏感和高度机密文件，请参阅[这些说明](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment)。</span><span class="sxs-lookup"><span data-stu-id="099f1-229">To build out your own test environment to test teams for sensitive and highly confidential files, see [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span></span> 

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a><span data-ttu-id="099f1-231">Contoso Corporation 如何对最高机密项目使用安全团队</span><span class="sxs-lookup"><span data-stu-id="099f1-231">How the Contoso Corporation used a secure team for a top-secret project</span></span>

<span data-ttu-id="099f1-232">Contoso Corporation 是一家虚构但具代表性的全球大型制造企业。</span><span class="sxs-lookup"><span data-stu-id="099f1-232">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="099f1-233">了解 Contoso 如何配置并推动对最高机密项目采用[安全团队](contoso-team-for-top-secret-project.md)，从而开发一组新的产品和服务并推向市场。</span><span class="sxs-lookup"><span data-stu-id="099f1-233">See how Contoso configured and drove the adoption of a [secure team](contoso-team-for-top-secret-project.md) for a top secret project to develop and bring to market a new set of products and services.</span></span> 

## <a name="see-also"></a><span data-ttu-id="099f1-234">另请参阅</span><span class="sxs-lookup"><span data-stu-id="099f1-234">See also</span></span>

[<span data-ttu-id="099f1-235">用于高度管控数据的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="099f1-235">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="099f1-236">Microsoft 365 企业版工作负载和方案</span><span class="sxs-lookup"><span data-stu-id="099f1-236">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="099f1-237">[Microsoft 365 工作效率库](https://aka.ms/productivitylibrary) https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="099f1-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="099f1-238">部署指南</span><span class="sxs-lookup"><span data-stu-id="099f1-238">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
