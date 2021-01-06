---
title: 配置具有安全隔离的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.openlocfilehash: 03252cad8449ee83cd757fac3ae74db6df68bcfe
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751139"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="fc0e3-103">配置具有安全隔离的团队</span><span class="sxs-lookup"><span data-stu-id="fc0e3-103">Configure a team with security isolation</span></span>

<span data-ttu-id="fc0e3-104">本文向你提供在 Microsoft Teams 中配置私人团队的建议和步骤，并使用唯一敏感标签来加密文件，以使仅团队成员可以对其进行解密。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="fc0e3-105">除了专用访问之外，本文还介绍了如何配置关联 SharePoint 网站，你可以从团队频道的“**文件**”部分进行访问，以获得存储高度管控数据所需的其他安全性。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="fc0e3-106">采用安全隔离的团队的配置元素如下：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-106">The elements of configuration for a team with security isolation are:</span></span>

- <span data-ttu-id="fc0e3-107">私人团队</span><span class="sxs-lookup"><span data-stu-id="fc0e3-107">A private team</span></span>
- <span data-ttu-id="fc0e3-108">关联 SharePoint 团队网站上的其他安全性：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="fc0e3-109">阻止网站成员与他人共享网站。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="fc0e3-110">阻止非网站成员请求访问该网站。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="fc0e3-111">专为此团队提供的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="fc0e3-112">阻止从未托管的设备访问 SharePoint 内容</span><span class="sxs-lookup"><span data-stu-id="fc0e3-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="fc0e3-113">允许或拒绝来宾访问团队，具体取决于需求</span><span class="sxs-lookup"><span data-stu-id="fc0e3-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="fc0e3-114">加密团队所应用的文件</span><span class="sxs-lookup"><span data-stu-id="fc0e3-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc0e3-115">继续执行本文中的步骤之前，确保启用[敏感度标签来保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) before you proceed with the steps in this article.</span></span>

<span data-ttu-id="fc0e3-116">观看此视频以简要了解部署流程。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-116">Watch this video for an overview of the deployment process.</span></span>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="fc0e3-117">有关此方案的两页摘要，请参阅[“采用安全隔离的 Microsoft Teams”文章](../downloads/team-security-isolation-poster.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-117">For a 2-page summary of this scenario, see the [Microsoft Teams with security isolation poster](../downloads/team-security-isolation-poster.pdf).</span></span>

<span data-ttu-id="fc0e3-118">[![“采用安全隔离的 Microsoft Teams”文章](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span><span class="sxs-lookup"><span data-stu-id="fc0e3-118">[![Microsoft Teams with security isolation poster](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span></span>

<span data-ttu-id="fc0e3-119">你还可以下载 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) 或 [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) 格式的海报，并以信件、法律或小报 (11 x 17) 的纸型打印。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-119">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) or [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="fc0e3-120">初始保护</span><span class="sxs-lookup"><span data-stu-id="fc0e3-120">Initial protections</span></span>

<span data-ttu-id="fc0e3-121">为了帮助保护对团队及其基础 SharePoint 网站的访问，请查看以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-121">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="fc0e3-122">标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="fc0e3-122">Identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="fc0e3-123">SharePoint Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="fc0e3-123">SharePoint Online access policies</span></span>](../security/office-365-security/sharepoint-file-access-policies.md)
- [<span data-ttu-id="fc0e3-124">部署具有基线保护的团队</span><span class="sxs-lookup"><span data-stu-id="fc0e3-124">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="fc0e3-125">来宾共享</span><span class="sxs-lookup"><span data-stu-id="fc0e3-125">Guest sharing</span></span>

<span data-ttu-id="fc0e3-126">根据业务性质，可能会也可能不希望为此团队启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-126">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="fc0e3-127">如果确实计划与团队中的组织外部人员进行协作，请启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-127">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="fc0e3-128">有关与来宾安全共享的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-128">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="fc0e3-129">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="fc0e3-129">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="fc0e3-130">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="fc0e3-130">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="fc0e3-131">为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-131">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="fc0e3-132">创建私人团队。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-132">Create a private team</span></span>

<span data-ttu-id="fc0e3-133">由于我们正在专为此团队创建敏感度标签，下一步是创建团队。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-133">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="fc0e3-134">如果有现有团队，可以使用此团队。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-134">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="fc0e3-135">创建机密信息团队</span><span class="sxs-lookup"><span data-stu-id="fc0e3-135">To create a team for sensitive information</span></span>
1. <span data-ttu-id="fc0e3-136">在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-136">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="fc0e3-137">点击“**创建团队**”（第一张卡片，左上角）。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-137">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="fc0e3-138">选择“**从头开始构建团队**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-138">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="fc0e3-139">在“**敏感度**”列表中，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-139">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="fc0e3-140">在“**隐私**”下，单击“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-140">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="fc0e3-141">键入与敏感项目相关的团队的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-141">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="fc0e3-142">例如，**Project Saturn**。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-142">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="fc0e3-143">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-143">Click **Create**.</span></span>
8. <span data-ttu-id="fc0e3-144">将用户添加到团队，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-144">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="fc0e3-145">专用频道设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-145">Private channel settings</span></span>

<span data-ttu-id="fc0e3-146">建议对团队所有者限制创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-146">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="fc0e3-147">限制专用频道创建</span><span class="sxs-lookup"><span data-stu-id="fc0e3-147">To restrict private channel creation</span></span>
1. <span data-ttu-id="fc0e3-148">在团队中，单击“**更多选项**”，然后单击“**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-148">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="fc0e3-149">在“**设置**”选项卡上，展开“**成员权限**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-149">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="fc0e3-150">清除“**允许成员创建专用频道**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-150">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="fc0e3-151">还可以使用“[团队策略](https://docs.microsoft.com/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-151">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="fc0e3-152">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="fc0e3-152">Create a sensitivity label</span></span>

<span data-ttu-id="fc0e3-153">为配置团队进行安全隔离，我们将使用专门为此团队创建的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-153">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="fc0e3-154">此标签用于以团队级别控制来宾共享和阻止访问未托管的设备。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-154">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="fc0e3-155">也可以用于对团队中的单个文件进行分类和加密，以使只有团队所有者和成员才能打开它们。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-155">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="fc0e3-156">如果拥有能够查看机密文件但是不能编辑的内部合作伙伴或利益干系人组，可以将他们添加至具有“仅查看”权限的标签。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-156">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="fc0e3-157">然后可将这些人员添加至具有“读取者”权限的团队 SharePoint 网站，他们对保管文件的网站具有只读访问权限，而不是本身拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-157">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>


<span data-ttu-id="fc0e3-158">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="fc0e3-158">To create a sensitivity label</span></span>
1. <span data-ttu-id="fc0e3-159">打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="fc0e3-160">在“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="fc0e3-161">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="fc0e3-162">为标签命名。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-162">Give the label a name.</span></span> <span data-ttu-id="fc0e3-163">建议使用“**敏感**”，但如果该名称已在使用，则可以选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-163">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="fc0e3-164">添加显示名称和说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-164">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="fc0e3-165">在“**定义此标签页的搜索范围**”中，选择“**文件和电子邮件**”和“**组和站点**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-165">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="fc0e3-166">在“**选择文件和电子邮件的保护设置**”页面中，选择“**加密文件和电子邮件**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-166">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="fc0e3-167">在“**加密页面中**”页面中，选择“**配置加密设置**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-167">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="fc0e3-168">单击“**添加用户或组**”，选择创建的团队，然后单击“**添加**”</span><span class="sxs-lookup"><span data-stu-id="fc0e3-168">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span>
10. <span data-ttu-id="fc0e3-169">单击“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-169">Click **Choose permissions**.</span></span>
11. <span data-ttu-id="fc0e3-170">从下拉列表中选择“**合著者**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-170">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span>
12. <span data-ttu-id="fc0e3-171">如果包括对带有标签的文件有只读权限的用户或组：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-171">If you want to include users or groups with read-only access to files with the label:</span></span>
    1. <span data-ttu-id="fc0e3-172">单击“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-172">Click **Assign permissions**.</span></span>
    1. <span data-ttu-id="fc0e3-173">单击“**添加用户或组**”，选择要添加的用户或组，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-173">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span>
    1. <span data-ttu-id="fc0e3-174">单击“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-174">Click **Choose permissions**.</span></span>
    1. <span data-ttu-id="fc0e3-175">从下拉列表中选择“**查看者**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-175">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span>
13.  <span data-ttu-id="fc0e3-176">单击“**保存**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-176">Click **Save**, and then click **Next**.</span></span>
14. <span data-ttu-id="fc0e3-177">在“*文件和电子邮件自动标记*”页面中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-177">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
15. <span data-ttu-id="fc0e3-178">在“**定义组和站点的防护设置**”页面中，选择“**隐私和外部用户访问设置**”和“**设备权限和外部共享设置**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-178">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
16. <span data-ttu-id="fc0e3-179">在“**定义隐私和外部用户权限设置**”页面中，选择“**隐私**”下的“**私人**”选项。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-179">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
17. <span data-ttu-id="fc0e3-180">如果你想允许来宾访问，选择“**外部用户权限**”下的“**让 Microsoft 365 组所有者添加组织外的人员为来宾**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-180">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
18. <span data-ttu-id="fc0e3-181">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-181">Click **Next**.</span></span>
19. <span data-ttu-id="fc0e3-182">在“**定义外部共享和设备权限设置**”页面中，选择“**从标记的 SharePoint 站点控制外部共享**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-182">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
20. <span data-ttu-id="fc0e3-183">如果当前允许来宾访问，在“**无法共享的内容**”下选择“**新的和当前来宾**”；如果不允许，则选择“**仅组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-183">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
21. <span data-ttu-id="fc0e3-184">在“**未托管的设备的访问**”下，选择“**阻止访问**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-184">Under **Access from unmanaged devices**, choose **Block access**.</span></span>
22. <span data-ttu-id="fc0e3-185">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-185">Click **Next**.</span></span>
23. <span data-ttu-id="fc0e3-186">在“**数据库列自动标记**”页面中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-186">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
24. <span data-ttu-id="fc0e3-187">单击“**创建标签**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-187">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="fc0e3-188">创建标签后，需要将其发布到使用它的用户。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-188">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="fc0e3-189">在这种情况中，我们将标签仅提供给团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-189">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="fc0e3-190">发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="fc0e3-190">To publish a sensitivity label</span></span>
1. <span data-ttu-id="fc0e3-191">在 Microsoft 365 合规中心的“**信息保护**”页面上，选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-191">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="fc0e3-192">单击“**发布标签**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-192">Click **Publish labels**.</span></span>
3. <span data-ttu-id="fc0e3-193">在“**选择要发布的敏感度标签**”页面上，单击“**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-193">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="fc0e3-194">选择创建的标签，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-194">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="fc0e3-195">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-195">Click **Next**.</span></span>
6. <span data-ttu-id="fc0e3-196">在“发布到用户和组”页面上，单击“**选择用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-196">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="fc0e3-197">单击“**添加**”，然后选择创建的团队。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-197">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="fc0e3-198">单击“**添加**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-198">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="fc0e3-199">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-199">Click **Next**.</span></span>
10. <span data-ttu-id="fc0e3-200">在“策略设置”页面上，选中“**用户必须提供理由才可删除标签或设置更低分类标签**”复选框，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-200">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="fc0e3-201">键入策略名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-201">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="fc0e3-202">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-202">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="fc0e3-203">将标签应用于团队</span><span class="sxs-lookup"><span data-stu-id="fc0e3-203">Apply the label to the team</span></span>

<span data-ttu-id="fc0e3-204">标签发布后，必须将其应用于团队，以使来宾共享和托管设备设置生效。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-204">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="fc0e3-205">此操作在 SharePoint 管理中心中进行。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-205">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="fc0e3-206">注意，标签在发布后可能需要一些时间才可用。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-206">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="fc0e3-207">应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="fc0e3-207">To apply the sensitivity label</span></span>
1. <span data-ttu-id="fc0e3-208">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-208">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="fc0e3-209">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-209">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="fc0e3-210">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-210">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="fc0e3-211">在“**策略**”选项卡的“**敏感度**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-211">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="fc0e3-212">选择创建的标签，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-212">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="fc0e3-213">SharePoint 设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-213">SharePoint settings</span></span>

<span data-ttu-id="fc0e3-214">在 SharePoint 中需要执行三个步骤：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-214">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="fc0e3-215">更新 SharePoint 管理中心中网站的来宾共享设置，使其与创建标签时选择的内容一致，并将默认共享链接更新为“*现有访问权限者*”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-215">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="fc0e3-216">自主更新网站中的网站共享设置，防止成员共享文件、文件夹或网站，并关闭访问请求。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-216">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="fc0e3-217">如果将人员或组添加至具有“查看者”权限的标签，可将他们添加至具有“只读”权限的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-217">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="fc0e3-218">SharePoint 来宾设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-218">SharePoint guest settings</span></span>

<span data-ttu-id="fc0e3-219">创建标签时选择的来宾共享设置（仅影响团队成员身份）应与关联的SharePoint 网站的来宾共享设置匹配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-219">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="fc0e3-220">标签设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-220">Label setting</span></span>|<span data-ttu-id="fc0e3-221">SharePoint 网站设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-221">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="fc0e3-222">**允许 Office 365 组所有者将组织外部的人员添加到组** 已选中</span><span class="sxs-lookup"><span data-stu-id="fc0e3-222">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="fc0e3-223">**新来宾和现有来宾**（新团队默认值）</span><span class="sxs-lookup"><span data-stu-id="fc0e3-223">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="fc0e3-224">**允许 Office 365 组所有者将组织外部的人员添加到组** 未选中</span><span class="sxs-lookup"><span data-stu-id="fc0e3-224">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="fc0e3-225">**仅组织内部人员**</span><span class="sxs-lookup"><span data-stu-id="fc0e3-225">**Only people in your organization**</span></span>|

<span data-ttu-id="fc0e3-226">我们还将更新默认共享链接类型，以减少将文件和文件夹意外共享给比预期更多受众的风险。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-226">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="fc0e3-227">更新网站设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-227">To update site settings</span></span>
1. <span data-ttu-id="fc0e3-228">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-228">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="fc0e3-229">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-229">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="fc0e3-230">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-230">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="fc0e3-231">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-231">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="fc0e3-232">如果在创建敏感标签时允许来宾共享，请确保选定“**新来宾和现有来宾**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-232">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="fc0e3-233">如果创建标签时不允许共享，选择“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-233">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="fc0e3-234">在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**具有现有访问权限的人员**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-234">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="fc0e3-235">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-235">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="fc0e3-236">专用频道</span><span class="sxs-lookup"><span data-stu-id="fc0e3-236">Private channels</span></span>

<span data-ttu-id="fc0e3-237">如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-237">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="fc0e3-238">这些网站在 SharePoint 管理中心中不可见，因此必须使用含有以下参数的 [Set-SPOSite ](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet 来更新来宾共享设置：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-238">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="fc0e3-239">`-SharingCapability Disabled` 用于禁用来宾共享（默认启用）</span><span class="sxs-lookup"><span data-stu-id="fc0e3-239">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="fc0e3-240">`-DefaultSharingLinkType Internal` 用于更改“*指定人员*”的默认共享链接</span><span class="sxs-lookup"><span data-stu-id="fc0e3-240">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="fc0e3-241">如果你不打算将专用频道用于你的团队，请考虑在“[团队设置](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc)”中的“**成员权限**”下关闭团队成员创建它们的功能。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-241">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="fc0e3-242">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="fc0e3-242">Site sharing settings</span></span>

<span data-ttu-id="fc0e3-243">为了确保不与非团队成员共享 SharePoint 网站，我们将此类共享限制为所有者。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-243">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="fc0e3-244">我们还将文件和文件夹的共享限制为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-244">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="fc0e3-245">这有助于确保无论何时与团队外部人员共享文件，所有者都会知道。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-245">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="fc0e3-246">配置仅限所有者的网站共享</span><span class="sxs-lookup"><span data-stu-id="fc0e3-246">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="fc0e3-247">在 Teams 中，导航至要更新团队的“**常规**”标签。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-247">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="fc0e3-248">在团队的工具栏中，单击“文件”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-248">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="fc0e3-249">单击省略号，然后单击“在 SharePoint 中打开”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-249">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="fc0e3-250">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-250">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="fc0e3-251">在“网站权限”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-251">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="fc0e3-252">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-252">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="fc0e3-253">自定义网站权限</span><span class="sxs-lookup"><span data-stu-id="fc0e3-253">Custom site permissions</span></span>

<span data-ttu-id="fc0e3-254">如果将具有“查看者”权限的人员添加到敏感度标签，则可以将其添加到具有“读取”权限的 SharePoint 网站中，以便他们可以轻松访问文件。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-254">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="fc0e3-255">将用户添加至网站</span><span class="sxs-lookup"><span data-stu-id="fc0e3-255">To add users to the site</span></span>
1. <span data-ttu-id="fc0e3-256">在网站中单击设置图标，然后单击“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-256">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="fc0e3-257">点击“**邀请其他人**”，然后点击“**仅共享网站**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-257">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="fc0e3-258">键入要邀请的用户和组的名称。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-258">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="fc0e3-259">对于要添加的每个人或组，将其权限从“**编辑**”更改为“**读取**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-259">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="fc0e3-260">选择是否要向他们发送含有网站链接的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-260">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="fc0e3-261">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-261">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="fc0e3-262">附加保护</span><span class="sxs-lookup"><span data-stu-id="fc0e3-262">Additional protections</span></span>

<span data-ttu-id="fc0e3-263">Microsoft 365 提供了其他用于保护内容的方法。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-263">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="fc0e3-264">考虑以下选项是否有助于提高组织的安全性。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-264">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="fc0e3-265">让你的来宾用户同意[使用条款](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-265">Have your guests agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="fc0e3-266">为来宾用户配置“[会话超时策略](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)”。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-266">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="fc0e3-267">创建“[敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)”，并使用“[数据丢失保护](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)”来设置有关访问敏感信息的策略。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-267">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="fc0e3-268">使用 [Azure Active Directory 访问](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)审核，定期审核团队访问权限和成员资格。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-268">Use [Azure Active Directory access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="fc0e3-269">驱动团队成员的用户采用</span><span class="sxs-lookup"><span data-stu-id="fc0e3-269">Drive user adoption for team members</span></span>

<span data-ttu-id="fc0e3-270">随着团队的建立，是时候驱动该团队的采用以及提升它对团队成员的额外安全性。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-270">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="train-your-users"></a><span data-ttu-id="fc0e3-271">培训用户</span><span class="sxs-lookup"><span data-stu-id="fc0e3-271">Train your users</span></span>

<span data-ttu-id="fc0e3-272">团队成员可以访问团队及其所有资源，包括聊天、会议和其他应用。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-272">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="fc0e3-273">使用频道的“**文件**”部分中的文件时，团队成员应为所创建的文件分配敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-273">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="fc0e3-274">当标签应用至文件时，文件被加密。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-274">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="fc0e3-275">团队成员可以打开并进行实时协作。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-275">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="fc0e3-276">如果文件离开网站并转发给恶意用户，则他们必须提供作为团队成员的用户帐户的凭据，这样才能打开文件并查看其内容。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-276">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="fc0e3-277">培训团队成员：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-277">Train your team members:</span></span>

- <span data-ttu-id="fc0e3-278">了解使用新团队访问聊天、会议、文件和 SharePoint 网站的其他资源的重要性以及高度管控数据泄露的后果，例如法律后果、监管罚款、勒索软件或失去竞争优势。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-278">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="fc0e3-279">如何访问团队。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-279">How to access the team.</span></span>
- <span data-ttu-id="fc0e3-280">如何在网站上创建新文件和上传本地存储的新文件。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-280">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="fc0e3-281">如何为团队使用正确的敏感性标签标记文件。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-281">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="fc0e3-282">标签如何保护文件（即使文件泄露到网站外部）。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-282">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="fc0e3-283">此培训应包括实践练习，让团队成员可以体验这些功能及其结果。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-283">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="fc0e3-284">定期审查使用情况并处理团队成员的反馈意见</span><span class="sxs-lookup"><span data-stu-id="fc0e3-284">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="fc0e3-285">在培训后的几周内：</span><span class="sxs-lookup"><span data-stu-id="fc0e3-285">In the weeks after training:</span></span>

- <span data-ttu-id="fc0e3-286">快速处理团队成员的反馈意见并微调相关策略和配置。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-286">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="fc0e3-287">分析团队的使用情况，并将其与预期使用情况进行比较。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-287">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="fc0e3-288">验证是否使用敏感度标签正确标记了高度管控的文件。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-288">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="fc0e3-289">通过查看 SharePoint 中的文件夹并使用“**添加列**”的“**显示/隐藏列**”选项添加“**敏感度**”列，可以查看为哪些文件分配了标签。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-289">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="fc0e3-290">根据需要重新培训用户。</span><span class="sxs-lookup"><span data-stu-id="fc0e3-290">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc0e3-291">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc0e3-291">See also</span></span>

[<span data-ttu-id="fc0e3-292">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="fc0e3-292">Azure AD Privileged Identity Management</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)
