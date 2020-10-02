---
title: 配置具有安全隔离的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 了解如何创建具有唯一敏感度标签的团队来保证安全。
ms.openlocfilehash: 544f62e4765388f90874c15504e6656820111ed4
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326491"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="28cf7-103">配置具有安全隔离的团队</span><span class="sxs-lookup"><span data-stu-id="28cf7-103">Configure a team with security isolation</span></span>

<span data-ttu-id="28cf7-104">本文向你提供在 Microsoft Teams 中配置私人团队的建议和步骤，并使用唯一敏感标签来加密文件，以使仅团队成员可以对其进行解密。</span><span class="sxs-lookup"><span data-stu-id="28cf7-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="28cf7-105">除了专用访问之外，本文还介绍了如何配置关联 SharePoint 网站，你可以从团队频道的“**文件**”部分进行访问，以获得存储高度管控数据所需的其他安全性。</span><span class="sxs-lookup"><span data-stu-id="28cf7-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="28cf7-106">采用安全隔离的团队的配置元素如下：</span><span class="sxs-lookup"><span data-stu-id="28cf7-106">The elements of configuration for a team with security isolation are:</span></span>

- <span data-ttu-id="28cf7-107">私人团队</span><span class="sxs-lookup"><span data-stu-id="28cf7-107">A private team</span></span>
- <span data-ttu-id="28cf7-108">关联 SharePoint 团队网站上的其他安全性：</span><span class="sxs-lookup"><span data-stu-id="28cf7-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="28cf7-109">阻止网站成员与他人共享网站。</span><span class="sxs-lookup"><span data-stu-id="28cf7-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="28cf7-110">阻止非网站成员请求访问该网站。</span><span class="sxs-lookup"><span data-stu-id="28cf7-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="28cf7-111">专为此团队提供的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="28cf7-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="28cf7-112">阻止从未托管的设备访问 SharePoint 内容</span><span class="sxs-lookup"><span data-stu-id="28cf7-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="28cf7-113">允许或拒绝来宾访问团队，具体取决于需求</span><span class="sxs-lookup"><span data-stu-id="28cf7-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="28cf7-114">加密团队所应用的文件</span><span class="sxs-lookup"><span data-stu-id="28cf7-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28cf7-115">继续执行本文中的步骤之前，确保启用[敏感度标签来保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="28cf7-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) before you proceed with the steps in this article.</span></span>

<a name="poster"></a> <span data-ttu-id="28cf7-116">有关此方案的两页摘要，请参阅[“采用安全隔离的 Microsoft Teams”文章](../downloads/team-security-isolation-poster.pdf)。</span><span class="sxs-lookup"><span data-stu-id="28cf7-116">For a 2-page summary of this scenario, see the [Microsoft Teams with security isolation poster](../downloads/team-security-isolation-poster.pdf).</span></span>

<span data-ttu-id="28cf7-117">[![“采用安全隔离的 Microsoft Teams”文章](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span><span class="sxs-lookup"><span data-stu-id="28cf7-117">[![Microsoft Teams with security isolation poster](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span></span>

<span data-ttu-id="28cf7-118">你还可以下载 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) 格式的海报，并以信件、法律或小报 (11 x 17) 的纸型打印。</span><span class="sxs-lookup"><span data-stu-id="28cf7-118">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="28cf7-119">初始保护</span><span class="sxs-lookup"><span data-stu-id="28cf7-119">Initial protections</span></span>

<span data-ttu-id="28cf7-120">为了帮助保护对团队及其基础 SharePoint 网站的访问，请查看以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="28cf7-120">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="28cf7-121">标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="28cf7-121">Identity and device access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)
- [<span data-ttu-id="28cf7-122">SharePoint Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="28cf7-122">SharePoint Online access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)
- [<span data-ttu-id="28cf7-123">部署具有基线保护的团队</span><span class="sxs-lookup"><span data-stu-id="28cf7-123">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="28cf7-124">来宾共享</span><span class="sxs-lookup"><span data-stu-id="28cf7-124">Guest sharing</span></span>

<span data-ttu-id="28cf7-125">根据业务性质，可能会也可能不希望为此团队启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="28cf7-125">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="28cf7-126">如果确实计划与团队中的组织外部人员进行协作，请启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="28cf7-126">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="28cf7-127">有关与来宾安全共享的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="28cf7-127">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="28cf7-128">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="28cf7-128">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="28cf7-129">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="28cf7-129">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="28cf7-130">为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。</span><span class="sxs-lookup"><span data-stu-id="28cf7-130">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="28cf7-131">创建私人团队。</span><span class="sxs-lookup"><span data-stu-id="28cf7-131">Create a private team</span></span>

<span data-ttu-id="28cf7-132">由于我们正在专为此团队创建敏感度标签，下一步是创建团队。</span><span class="sxs-lookup"><span data-stu-id="28cf7-132">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="28cf7-133">如果有现有团队，可以使用此团队。</span><span class="sxs-lookup"><span data-stu-id="28cf7-133">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="28cf7-134">创建机密信息团队</span><span class="sxs-lookup"><span data-stu-id="28cf7-134">To create a team for sensitive information</span></span>
1. <span data-ttu-id="28cf7-135">在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-135">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="28cf7-136">点击“**创建团队**”（第一张卡片，左上角）。</span><span class="sxs-lookup"><span data-stu-id="28cf7-136">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="28cf7-137">选择“**从头开始构建团队**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-137">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="28cf7-138">在“**敏感度**”列表中，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="28cf7-138">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="28cf7-139">在“**隐私**”下，单击“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-139">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="28cf7-140">键入与敏感项目相关的团队的名称。</span><span class="sxs-lookup"><span data-stu-id="28cf7-140">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="28cf7-141">例如，**Project Saturn**。</span><span class="sxs-lookup"><span data-stu-id="28cf7-141">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="28cf7-142">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-142">Click **Create**.</span></span>
8. <span data-ttu-id="28cf7-143">将用户添加到团队，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-143">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="28cf7-144">专用频道设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-144">Private channel settings</span></span>

<span data-ttu-id="28cf7-145">建议对团队所有者限制创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="28cf7-145">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="28cf7-146">限制专用频道创建</span><span class="sxs-lookup"><span data-stu-id="28cf7-146">To restrict private channel creation</span></span>
1. <span data-ttu-id="28cf7-147">在团队中，单击“**更多选项**”，然后单击“**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-147">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="28cf7-148">在“**设置**”选项卡上，展开“**成员权限**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-148">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="28cf7-149">清除“**允许成员创建专用频道**”复选框。</span><span class="sxs-lookup"><span data-stu-id="28cf7-149">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="28cf7-150">还可以使用“[团队策略](https://docs.microsoft.com/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="28cf7-150">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="28cf7-151">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="28cf7-151">Create a sensitivity label</span></span>

<span data-ttu-id="28cf7-152">为配置团队进行安全隔离，我们将使用专门为此团队创建的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="28cf7-152">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="28cf7-153">此标签用于以团队级别控制来宾共享和阻止访问未托管的设备。</span><span class="sxs-lookup"><span data-stu-id="28cf7-153">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="28cf7-154">也可以用于对团队中的单个文件进行分类和加密，以使只有团队所有者和成员才能打开它们。</span><span class="sxs-lookup"><span data-stu-id="28cf7-154">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="28cf7-155">如果拥有能够查看机密文件但是不能编辑的内部合作伙伴或利益干系人组，可以将他们添加至具有“仅查看”权限的标签。</span><span class="sxs-lookup"><span data-stu-id="28cf7-155">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="28cf7-156">然后可将这些人员添加至具有“读取者”权限的团队 SharePoint 网站，他们对保管文件的网站具有只读访问权限，而不是本身拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="28cf7-156">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>

<span data-ttu-id="28cf7-157">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="28cf7-157">To create a sensitivity label</span></span>
1. <span data-ttu-id="28cf7-158">打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="28cf7-158">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="28cf7-159">在“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-159">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="28cf7-160">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-160">Click **Create a label**.</span></span>
4. <span data-ttu-id="28cf7-161">键入与团队名称类似的标签名称。</span><span class="sxs-lookup"><span data-stu-id="28cf7-161">Type a name for the label that is similar to your team name.</span></span> <span data-ttu-id="28cf7-162">例如，**高度敏感 - Project Saturn**。</span><span class="sxs-lookup"><span data-stu-id="28cf7-162">For example, **Highly sensitive - Project Saturn**.</span></span>
5. <span data-ttu-id="28cf7-163">添加工具提示，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-163">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="28cf7-164">在“**加密**”页面上的“**加密**”下拉列表中，选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="28cf7-165">添加团队权限：</span><span class="sxs-lookup"><span data-stu-id="28cf7-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="28cf7-166">a.</span><span class="sxs-lookup"><span data-stu-id="28cf7-166">a.</span></span> <span data-ttu-id="28cf7-167">单击“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="28cf7-168">b.</span><span class="sxs-lookup"><span data-stu-id="28cf7-168">b.</span></span> <span data-ttu-id="28cf7-169">单击“**添加用户或组**”，选择创建的团队，然后单击“**添加**”</span><span class="sxs-lookup"><span data-stu-id="28cf7-169">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span><br>
  <span data-ttu-id="28cf7-170">c.</span><span class="sxs-lookup"><span data-stu-id="28cf7-170">c.</span></span> <span data-ttu-id="28cf7-171">单击“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="28cf7-172">d.</span><span class="sxs-lookup"><span data-stu-id="28cf7-172">d.</span></span> <span data-ttu-id="28cf7-173">从下拉列表中选择“**合著者**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="28cf7-174">如果包括对带有标签的文件有只读权限的用户或组：</span><span class="sxs-lookup"><span data-stu-id="28cf7-174">If you want to include users or groups with read-only access to files with the label:</span></span><br>
  <span data-ttu-id="28cf7-175">a.</span><span class="sxs-lookup"><span data-stu-id="28cf7-175">a.</span></span> <span data-ttu-id="28cf7-176">单击“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-176">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="28cf7-177">b.</span><span class="sxs-lookup"><span data-stu-id="28cf7-177">b.</span></span> <span data-ttu-id="28cf7-178">单击“**添加用户或组**”，选择要添加的用户或组，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-178">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span><br>
  <span data-ttu-id="28cf7-179">c.</span><span class="sxs-lookup"><span data-stu-id="28cf7-179">c.</span></span> <span data-ttu-id="28cf7-180">单击“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-180">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="28cf7-181">d.</span><span class="sxs-lookup"><span data-stu-id="28cf7-181">d.</span></span> <span data-ttu-id="28cf7-182">从下拉列表中选择“**查看者**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-182">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span><br>
  <span data-ttu-id="28cf7-183">e.</span><span class="sxs-lookup"><span data-stu-id="28cf7-183">e.</span></span> <span data-ttu-id="28cf7-184">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cf7-184">Click **Save**.</span></span>
9. <span data-ttu-id="28cf7-185">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="28cf7-185">Click **Next**.</span></span>
10. <span data-ttu-id="28cf7-186">如果希望自动向使用此标签分类的文件添加页眉、页脚或水印，请在“**内容标记**”页面上启用内容标记。</span><span class="sxs-lookup"><span data-stu-id="28cf7-186">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
11. <span data-ttu-id="28cf7-187">在“**网站和组设置**”页面上，将“**网站和组设置**”设置为“**开启**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-187">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
12. <span data-ttu-id="28cf7-188">在“**Office 365 与组连接的团队网站的隐私**”下拉菜单中，选择“**专用 - 只有成员才能访问网站**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-188">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
13. <span data-ttu-id="28cf7-189">如果想要允许来宾访问，请选择“**允许 Office 365 组所有者将组织外部的人员添加到组**”复选框。</span><span class="sxs-lookup"><span data-stu-id="28cf7-189">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
14. <span data-ttu-id="28cf7-190">在“**未托管的设备**”下，选择“**阻止访问**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-190">Under **Unmanaged devices**, choose **Block access**.</span></span>
15. <span data-ttu-id="28cf7-191">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-191">Click **Next**.</span></span>
16. <span data-ttu-id="28cf7-192">在“**Office 应用程序自动标记**”页面上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-192">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
17. <span data-ttu-id="28cf7-193">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-193">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="28cf7-194">创建标签后，需要将其发布到使用它的用户。</span><span class="sxs-lookup"><span data-stu-id="28cf7-194">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="28cf7-195">在这种情况中，我们将标签仅提供给团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="28cf7-195">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="28cf7-196">发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="28cf7-196">To publish a sensitivity label</span></span>
1. <span data-ttu-id="28cf7-197">在 Microsoft 365 合规中心的“**信息保护**”页面上，选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="28cf7-197">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="28cf7-198">单击“**发布标签**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-198">Click **Publish labels**.</span></span>
3. <span data-ttu-id="28cf7-199">在“**选择要发布的敏感度标签**”页面上，单击“**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-199">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="28cf7-200">选择创建的标签，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-200">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="28cf7-201">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-201">Click **Next**.</span></span>
6. <span data-ttu-id="28cf7-202">在“发布到用户和组”页面上，单击“**选择用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-202">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="28cf7-203">单击“**添加**”，然后选择创建的团队。</span><span class="sxs-lookup"><span data-stu-id="28cf7-203">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="28cf7-204">单击“**添加**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-204">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="28cf7-205">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-205">Click **Next**.</span></span>
10. <span data-ttu-id="28cf7-206">在“策略设置”页面上，选中“**用户必须提供理由才可删除标签或设置更低分类标签**”复选框，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-206">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="28cf7-207">键入策略名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-207">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="28cf7-208">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-208">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="28cf7-209">将标签应用于团队</span><span class="sxs-lookup"><span data-stu-id="28cf7-209">Apply the label to the team</span></span>

<span data-ttu-id="28cf7-210">标签发布后，必须将其应用于团队，以使来宾共享和托管设备设置生效。</span><span class="sxs-lookup"><span data-stu-id="28cf7-210">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="28cf7-211">此操作在 SharePoint 管理中心中进行。</span><span class="sxs-lookup"><span data-stu-id="28cf7-211">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="28cf7-212">注意，标签在发布后可能需要一些时间才可用。</span><span class="sxs-lookup"><span data-stu-id="28cf7-212">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="28cf7-213">应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="28cf7-213">To apply the sensitivity label</span></span>
1. <span data-ttu-id="28cf7-214">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="28cf7-214">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="28cf7-215">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-215">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="28cf7-216">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="28cf7-216">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="28cf7-217">在“**策略**”选项卡的“**敏感度**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-217">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="28cf7-218">选择创建的标签，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-218">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="28cf7-219">SharePoint 设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-219">SharePoint settings</span></span>

<span data-ttu-id="28cf7-220">在 SharePoint 中需要执行三个步骤：</span><span class="sxs-lookup"><span data-stu-id="28cf7-220">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="28cf7-221">更新 SharePoint 管理中心中网站的来宾共享设置，使其与创建标签时选择的内容一致，并将默认共享链接更新为“*现有访问权限者*”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-221">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="28cf7-222">自主更新网站中的网站共享设置，防止成员共享文件、文件夹或网站，并关闭访问请求。</span><span class="sxs-lookup"><span data-stu-id="28cf7-222">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="28cf7-223">如果将人员或组添加至具有“查看者”权限的标签，可将他们添加至具有“只读”权限的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="28cf7-223">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="28cf7-224">SharePoint 来宾设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-224">SharePoint guest settings</span></span>

<span data-ttu-id="28cf7-225">创建标签时选择的来宾共享设置（仅影响团队成员身份）应与关联的SharePoint 网站的来宾共享设置匹配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="28cf7-225">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="28cf7-226">标签设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-226">Label setting</span></span>|<span data-ttu-id="28cf7-227">SharePoint 网站设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-227">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="28cf7-228">**允许 Office 365 组所有者将组织外部的人员添加到组**已选中</span><span class="sxs-lookup"><span data-stu-id="28cf7-228">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="28cf7-229">**新来宾和现有来宾**（新团队默认值）</span><span class="sxs-lookup"><span data-stu-id="28cf7-229">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="28cf7-230">**允许 Office 365 组所有者将组织外部的人员添加到组**未选中</span><span class="sxs-lookup"><span data-stu-id="28cf7-230">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="28cf7-231">**仅组织内部人员**</span><span class="sxs-lookup"><span data-stu-id="28cf7-231">**Only people in your organization**</span></span>|

<span data-ttu-id="28cf7-232">我们还将更新默认共享链接类型，以减少将文件和文件夹意外共享给比预期更多受众的风险。</span><span class="sxs-lookup"><span data-stu-id="28cf7-232">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="28cf7-233">更新网站设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-233">To update site settings</span></span>
1. <span data-ttu-id="28cf7-234">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="28cf7-234">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="28cf7-235">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-235">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="28cf7-236">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="28cf7-236">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="28cf7-237">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-237">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="28cf7-238">如果在创建敏感标签时允许来宾共享，请确保选定“**新来宾和现有来宾**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-238">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="28cf7-239">如果创建标签时不允许共享，选择“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-239">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="28cf7-240">在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**具有现有访问权限的人员**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-240">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="28cf7-241">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-241">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="28cf7-242">专用频道</span><span class="sxs-lookup"><span data-stu-id="28cf7-242">Private channels</span></span>

<span data-ttu-id="28cf7-243">如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="28cf7-243">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="28cf7-244">这些网站在 SharePoint 管理中心中不可见，因此必须使用含有以下参数的 [Set-SPOSite ](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet 来更新来宾共享设置：</span><span class="sxs-lookup"><span data-stu-id="28cf7-244">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="28cf7-245">`-SharingCapability Disabled` 用于禁用来宾共享（默认启用）</span><span class="sxs-lookup"><span data-stu-id="28cf7-245">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="28cf7-246">`-DefaultSharingLinkType Internal` 用于更改“*指定人员*”的默认共享链接</span><span class="sxs-lookup"><span data-stu-id="28cf7-246">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="28cf7-247">如果你不打算将专用频道用于你的团队，请考虑在“[团队设置](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc)”中的“**成员权限**”下关闭团队成员创建它们的功能。</span><span class="sxs-lookup"><span data-stu-id="28cf7-247">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="28cf7-248">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="28cf7-248">Site sharing settings</span></span>

<span data-ttu-id="28cf7-249">为了确保不与非团队成员共享 SharePoint 网站，我们将此类共享限制为所有者。</span><span class="sxs-lookup"><span data-stu-id="28cf7-249">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="28cf7-250">我们还将文件和文件夹的共享限制为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="28cf7-250">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="28cf7-251">这有助于确保无论何时与团队外部人员共享文件，所有者都会知道。</span><span class="sxs-lookup"><span data-stu-id="28cf7-251">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="28cf7-252">配置仅限所有者的网站共享</span><span class="sxs-lookup"><span data-stu-id="28cf7-252">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="28cf7-253">在 Teams 中，导航至要更新团队的“**常规**”标签。</span><span class="sxs-lookup"><span data-stu-id="28cf7-253">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="28cf7-254">在团队的工具栏中，单击“文件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cf7-254">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="28cf7-255">单击省略号，然后单击“在 SharePoint 中打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cf7-255">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="28cf7-256">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28cf7-256">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="28cf7-257">在“网站权限”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-257">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="28cf7-258">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-258">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="28cf7-259">自定义网站权限</span><span class="sxs-lookup"><span data-stu-id="28cf7-259">Custom site permissions</span></span>

<span data-ttu-id="28cf7-260">如果将具有“查看者”权限的人员添加到敏感度标签，则可以将其添加到具有“读取”权限的 SharePoint 网站中，以便他们可以轻松访问文件。</span><span class="sxs-lookup"><span data-stu-id="28cf7-260">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="28cf7-261">将用户添加至网站</span><span class="sxs-lookup"><span data-stu-id="28cf7-261">To add users to the site</span></span>
1. <span data-ttu-id="28cf7-262">在网站中单击设置图标，然后单击“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-262">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="28cf7-263">点击“**邀请其他人**”，然后点击“**仅共享网站**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-263">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="28cf7-264">键入要邀请的用户和组的名称。</span><span class="sxs-lookup"><span data-stu-id="28cf7-264">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="28cf7-265">对于要添加的每个人或组，将其权限从“**编辑**”更改为“**读取**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-265">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="28cf7-266">选择是否要向他们发送含有网站链接的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="28cf7-266">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="28cf7-267">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-267">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="28cf7-268">附加保护</span><span class="sxs-lookup"><span data-stu-id="28cf7-268">Additional protections</span></span>

<span data-ttu-id="28cf7-269">Microsoft 365 提供了其他用于保护内容的方法。</span><span class="sxs-lookup"><span data-stu-id="28cf7-269">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="28cf7-270">考虑以下选项是否有助于提高组织的安全性。</span><span class="sxs-lookup"><span data-stu-id="28cf7-270">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="28cf7-271">让来宾用户同意[使用条款](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)。</span><span class="sxs-lookup"><span data-stu-id="28cf7-271">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="28cf7-272">为来宾用户配置“[会话超时策略](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)”。</span><span class="sxs-lookup"><span data-stu-id="28cf7-272">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="28cf7-273">创建“[敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)”，并使用“[数据丢失保护](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)”来设置有关访问敏感信息的策略。</span><span class="sxs-lookup"><span data-stu-id="28cf7-273">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="28cf7-274">使用 [Azure Active Directory 访问](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)审核，定期审核团队访问权限和成员资格。</span><span class="sxs-lookup"><span data-stu-id="28cf7-274">Use [Azure Active Directory access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="28cf7-275">驱动团队成员的用户采用</span><span class="sxs-lookup"><span data-stu-id="28cf7-275">Drive user adoption for team members</span></span>

<span data-ttu-id="28cf7-276">随着团队的建立，是时候驱动该团队的采用以及提升它对团队成员的额外安全性。</span><span class="sxs-lookup"><span data-stu-id="28cf7-276">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="train-your-users"></a><span data-ttu-id="28cf7-277">培训用户</span><span class="sxs-lookup"><span data-stu-id="28cf7-277">Train your users</span></span>

<span data-ttu-id="28cf7-278">团队成员可以访问团队及其所有资源，包括聊天、会议和其他应用。</span><span class="sxs-lookup"><span data-stu-id="28cf7-278">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="28cf7-279">使用频道的“**文件**”部分中的文件时，团队成员应为所创建的文件分配敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="28cf7-279">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="28cf7-280">当标签应用至文件时，文件被加密。</span><span class="sxs-lookup"><span data-stu-id="28cf7-280">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="28cf7-281">团队成员可以打开并进行实时协作。</span><span class="sxs-lookup"><span data-stu-id="28cf7-281">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="28cf7-282">如果文件离开网站并转发给恶意用户，则他们必须提供作为团队成员的用户帐户的凭据，这样才能打开文件并查看其内容。</span><span class="sxs-lookup"><span data-stu-id="28cf7-282">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="28cf7-283">培训团队成员：</span><span class="sxs-lookup"><span data-stu-id="28cf7-283">Train your team members:</span></span>

- <span data-ttu-id="28cf7-284">了解使用新团队访问聊天、会议、文件和 SharePoint 网站的其他资源的重要性以及高度管控数据泄露的后果，例如法律后果、监管罚款、勒索软件或失去竞争优势。</span><span class="sxs-lookup"><span data-stu-id="28cf7-284">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="28cf7-285">如何访问团队。</span><span class="sxs-lookup"><span data-stu-id="28cf7-285">How to access the team.</span></span>
- <span data-ttu-id="28cf7-286">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="28cf7-286">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="28cf7-287">如何为团队使用正确的敏感性标签标记文件。</span><span class="sxs-lookup"><span data-stu-id="28cf7-287">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="28cf7-288">标签如何保护文件（即使文件泄露到网站外部）。</span><span class="sxs-lookup"><span data-stu-id="28cf7-288">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="28cf7-289">此培训应包括实践练习，让团队成员可以体验这些功能及其结果。</span><span class="sxs-lookup"><span data-stu-id="28cf7-289">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="28cf7-290">定期审查使用情况并处理团队成员的反馈意见</span><span class="sxs-lookup"><span data-stu-id="28cf7-290">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="28cf7-291">在培训后的几周内：</span><span class="sxs-lookup"><span data-stu-id="28cf7-291">In the weeks after training:</span></span>

- <span data-ttu-id="28cf7-292">快速处理团队成员的反馈意见并微调相关策略和配置。</span><span class="sxs-lookup"><span data-stu-id="28cf7-292">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="28cf7-293">分析团队的使用情况，并将其与预期使用情况进行比较。</span><span class="sxs-lookup"><span data-stu-id="28cf7-293">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="28cf7-294">验证是否使用敏感度标签正确标记了高度管控的文件。</span><span class="sxs-lookup"><span data-stu-id="28cf7-294">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="28cf7-295">通过查看 SharePoint 中的文件夹并使用“**添加列**”的“**显示/隐藏列**”选项添加“**敏感度**”列，可以查看为哪些文件分配了标签。</span><span class="sxs-lookup"><span data-stu-id="28cf7-295">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="28cf7-296">根据需要重新培训用户。</span><span class="sxs-lookup"><span data-stu-id="28cf7-296">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="28cf7-297">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28cf7-297">See also</span></span>

[<span data-ttu-id="28cf7-298">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="28cf7-298">Azure AD Privileged Identity Management</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)