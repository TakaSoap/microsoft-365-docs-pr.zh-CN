---
title: 适用于 Microsoft 365 企业版测试环境的数据分类
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可在 Microsoft 365 企业版测试环境中的文档上创建和使用保留标签。
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686402"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b7902-103">适用于 Microsoft 365 企业版测试环境的数据分类</span><span class="sxs-lookup"><span data-stu-id="b7902-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b7902-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="b7902-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b7902-105">使用本文中的说明，可以在 Microsoft 365 企业版测试环境中使用保留标签配置数据分类。</span><span class="sxs-lookup"><span data-stu-id="b7902-105">With the instructions in this article, you configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b7902-107">单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="b7902-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b7902-108">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="b7902-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b7902-109">如果只想使用最低要求以轻型方式配置保留标签，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b7902-109">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b7902-110">如果要在模拟的企业中配置保留标签，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b7902-110">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7902-111">测试保留标签不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="b7902-111">Testing retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b7902-112">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="b7902-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="b7902-113">阶段2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="b7902-113">Phase 2: Create retention labels</span></span>

<span data-ttu-id="b7902-114">在此阶段中，您将为 SharePoint Online 文档文件夹的不同保留级别创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="b7902-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="b7902-115">使用全局管理员帐户登录 [Microsoft 365 安全中心](https://security.microsoft.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="b7902-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="b7902-116">在浏览器的 " **主页-Microsoft 365 安全** " 选项卡中，单击 " **分类 > 保留标签**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="b7902-117">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="b7902-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="b7902-118">在 "**命名标签**" 窗格中，在 "**命名" 标签**中键入**Internal Public** ，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="b7902-119">在 " **文件计划描述符** " 窗格中，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="b7902-120">在 " **标签设置** " 窗格中，根据需要将 " **保留** " 设置为 **"开**"，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b7902-121">在 " **查看设置** " 窗格中，单击 " **创建标签"**。</span><span class="sxs-lookup"><span data-stu-id="b7902-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="b7902-122">对具有以下名称的其他标签重复步骤 3-7：</span><span class="sxs-lookup"><span data-stu-id="b7902-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="b7902-123">Private</span><span class="sxs-lookup"><span data-stu-id="b7902-123">Private</span></span>
    
  - <span data-ttu-id="b7902-124">敏感</span><span class="sxs-lookup"><span data-stu-id="b7902-124">Sensitive</span></span>
    
  - <span data-ttu-id="b7902-125">高度机密</span><span class="sxs-lookup"><span data-stu-id="b7902-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="b7902-126">在 " **保留标签** " 窗格中，单击 " **发布标签**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="b7902-127">在 " **选择要发布的标签** " 窗格中，单击 " **选择要发布的标签**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="b7902-128">在 " **选择标签** " 窗格中，单击 " **添加** "，然后选择全部四个标签。</span><span class="sxs-lookup"><span data-stu-id="b7902-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="b7902-129">单击“**添加**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="b7902-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="b7902-130">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7902-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="b7902-131">在“**选择位置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b7902-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="b7902-132">在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b7902-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="b7902-133">在 " **查看设置** " 窗格中，单击 " **发布标签**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="b7902-134">请注意，发布保留标签可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="b7902-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="b7902-135">第3阶段：将保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="b7902-135">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="b7902-136">在此阶段中，您将发现 SharePoint Online 网站的 Documents 文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。</span><span class="sxs-lookup"><span data-stu-id="b7902-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="b7902-137">首先，创建一个敏感级别的 SharePoint Online 团队网站：</span><span class="sxs-lookup"><span data-stu-id="b7902-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="b7902-138">使用浏览器的专用实例，使用全局管理员帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="b7902-138">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="b7902-139">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7902-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="b7902-140">在浏览器的 "新建 **SharePoint** " 选项卡上，单击 " **创建网站**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="b7902-141">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7902-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="b7902-142">在 " **团队网站名称**" 中，键入 **SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="b7902-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="b7902-143">在 " **工作组网站说明**" 中，键入 " **SharePoint 网站" 以查找敏感文件**。</span><span class="sxs-lookup"><span data-stu-id="b7902-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="b7902-144">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7902-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b7902-145">在 " **要添加哪些用户？"** 窗格中，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="b7902-146">接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b7902-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="b7902-147">在浏览器的 " **SensitiveFiles** " 选项卡中，单击 " **文档**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="b7902-148">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7902-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="b7902-149">在 " **权限和管理**" 下，单击 " **将标签应用于此列表或库中的项目**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="b7902-150">如果未显示此选项，则尚未发布你的保留标签。</span><span class="sxs-lookup"><span data-stu-id="b7902-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="b7902-151">稍后请尝试执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="b7902-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="b7902-152">在 " **设置-应用标签**" 中，选择下拉框中的 " **敏感** "，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="b7902-153">接下来，在 SensitiveFiles 网站中创建一个新文档并更改其保留标签。</span><span class="sxs-lookup"><span data-stu-id="b7902-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="b7902-154">在 "文档" 文件夹中，单击 " **新建 > Word 文档**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="b7902-155">在空白文档中键入一些文本。</span><span class="sxs-lookup"><span data-stu-id="b7902-155">Type some text in the blank document.</span></span> <span data-ttu-id="b7902-156">等待文本保存。</span><span class="sxs-lookup"><span data-stu-id="b7902-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="b7902-157">在菜单栏中，单击 " **共享文档**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="b7902-158">单击 **Document.docx** 文件名旁边的垂直省略号，然后单击 " **详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="b7902-159">在右侧窗格中的 " **属性** " 部分的 " **应用保留标签**" 下，请注意文档是否已自动应用 " **敏感** 保留" 标签。</span><span class="sxs-lookup"><span data-stu-id="b7902-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="b7902-160">单击“编辑全部”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7902-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="b7902-161">在 " **Document.docx** " 窗格中的 " **应用保留标签**" 下，选择 " **高度机密** " 标签，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b7902-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="b7902-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b7902-162">Next step</span></span>

<span data-ttu-id="b7902-163">在您的测试环境中浏览其他 [信息保护](m365-enterprise-test-lab-guides.md#information-protection) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="b7902-163">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7902-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7902-164">See also</span></span>

[<span data-ttu-id="b7902-165">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="b7902-165">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b7902-166">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="b7902-166">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b7902-167">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="b7902-167">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
