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
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487728"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0eeee-103">适用于 Microsoft 365 企业版测试环境的数据分类</span><span class="sxs-lookup"><span data-stu-id="0eeee-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0eeee-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="0eeee-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="0eeee-105">本文介绍如何在 Microsoft 365 企业版测试环境中使用保留标签配置数据分类。</span><span class="sxs-lookup"><span data-stu-id="0eeee-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="0eeee-106">对测试环境中的数据进行分类包括三个阶段：</span><span class="sxs-lookup"><span data-stu-id="0eeee-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="0eeee-107">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="0eeee-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="0eeee-108">阶段2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="0eeee-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="0eeee-109">第3阶段：将保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="0eeee-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="0eeee-111">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="0eeee-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0eeee-112">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="0eeee-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0eeee-113">如果只想使用最低要求以轻型方式配置保留标签，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0eeee-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0eeee-114">如果要在模拟的企业中配置保留标签，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0eeee-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0eeee-115">测试保留标签不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="0eeee-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0eeee-116">它作为选项提供，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="0eeee-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="0eeee-117">阶段2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="0eeee-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="0eeee-118">在此阶段，为 SharePoint Online 文档文件夹的不同保留级别创建保留标签：</span><span class="sxs-lookup"><span data-stu-id="0eeee-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="0eeee-119">使用全局管理员帐户登录 [Microsoft 365 安全中心](https://security.microsoft.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="0eeee-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="0eeee-120">从浏览器的 "**主页-Microsoft 365 安全**" 选项卡中，选择 "**分类**  >  **保留标签**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="0eeee-121">选择“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="0eeee-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="0eeee-122">在 "**命名标签**" 窗格中，在 "**命名" 标签**中输入 "**内部公用**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="0eeee-123">在 " **文件计划描述符** " 窗格中，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="0eeee-124">在 " **标签设置** " 窗格中，根据需要将 " **保留** " 设置为 **"开**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="0eeee-125">在 " **查看设置** " 窗格中，选择 **"创建标签"**。</span><span class="sxs-lookup"><span data-stu-id="0eeee-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="0eeee-126">对具有以下名称的其他标签重复步骤 3-7：</span><span class="sxs-lookup"><span data-stu-id="0eeee-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="0eeee-127">Private</span><span class="sxs-lookup"><span data-stu-id="0eeee-127">Private</span></span>
  - <span data-ttu-id="0eeee-128">敏感</span><span class="sxs-lookup"><span data-stu-id="0eeee-128">Sensitive</span></span>
  - <span data-ttu-id="0eeee-129">高度机密</span><span class="sxs-lookup"><span data-stu-id="0eeee-129">Highly Confidential</span></span>
1. <span data-ttu-id="0eeee-130">在 " **保留标签** " 窗格中，选择 " **发布标签**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="0eeee-131">在 " **选择要发布的标签** " 窗格中，选择 " **选择要发布的标签**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="0eeee-132">在 " **选择标签** " 窗格中，选择 " **添加** "，然后选择全部四个标签。</span><span class="sxs-lookup"><span data-stu-id="0eeee-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="0eeee-133">选择 " **添加**"，然后选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="0eeee-134">在 " **选择要发布的标签** " 窗格中，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="0eeee-135">在 " **选择位置** " 窗格中，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="0eeee-136">在 "**命名策略**" 窗格中，在 "**名称**" 中输入**示例组织**，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="0eeee-137">在 " **查看设置** " 窗格中，选择 " **发布标签**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="0eeee-138">发布保留标签可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="0eeee-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="0eeee-139">第3阶段：将保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="0eeee-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="0eeee-140">在此阶段中，您将发现 SharePoint Online 网站的 Documents 文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。</span><span class="sxs-lookup"><span data-stu-id="0eeee-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="0eeee-141">首先，创建一个敏感级别的 SharePoint Online 团队网站：</span><span class="sxs-lookup"><span data-stu-id="0eeee-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="0eeee-142">使用浏览器的专用实例，使用全局管理员帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="0eeee-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="0eeee-143">在磁贴列表中，选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="0eeee-144">在浏览器的 "新建 **SharePoint** " 选项卡上，选择 " **创建网站**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="0eeee-145">在“创建网站”\*\*\*\* 页中，选择“团队网站”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eeee-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="0eeee-146">在 " **团队网站名称** " 框中，输入 **SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="0eeee-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="0eeee-147">在 " **团队网站说明** " 框中，输入 **敏感文件的 SharePoint 网站**。</span><span class="sxs-lookup"><span data-stu-id="0eeee-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="0eeee-148">在 " **隐私设置**" 中，选择 " **仅专用成员可以访问此网站**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="0eeee-149">在 " **要添加哪些用户？"** 窗格中，选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="0eeee-150">接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0eeee-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="0eeee-151">在浏览器的 " **SensitiveFiles** " 选项卡中，选择 " **文档**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="0eeee-152">选择 " **设置** " 图标，然后选择 " **库设置**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="0eeee-153">在 " **权限和管理**" 下，选择 " **将标签应用于此列表或库中的项目**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="0eeee-154">如果未显示此选项，则您的保留标签尚未发布。</span><span class="sxs-lookup"><span data-stu-id="0eeee-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="0eeee-155">稍后请尝试执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="0eeee-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="0eeee-156">在 " **设置-应用标签**" 中，选择下拉框中的 " **敏感** "，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="0eeee-157">接下来，在 SensitiveFiles 网站中创建一个新文档并更改其保留标签。</span><span class="sxs-lookup"><span data-stu-id="0eeee-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="0eeee-158">在 "文档" 文件夹中，选择 "**新建**  >  **Word 文档**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="0eeee-159">在空白文档中输入一些文本。</span><span class="sxs-lookup"><span data-stu-id="0eeee-159">Enter some text in the blank document.</span></span> <span data-ttu-id="0eeee-160">等待文本保存。</span><span class="sxs-lookup"><span data-stu-id="0eeee-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="0eeee-161">在菜单栏上，选择 " **共享文档**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="0eeee-162">在 " **Document.docx** 文件名旁边，选择垂直省略号，然后选择" **详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="0eeee-163">在右侧窗格中的 " **属性** " 部分的 " **应用保留标签**" 下，请注意文档是否已自动应用 " **敏感** 保留" 标签。</span><span class="sxs-lookup"><span data-stu-id="0eeee-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="0eeee-164">单击“编辑全部”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eeee-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="0eeee-165">在 " **Document.docx** " 窗格中的 " **应用保留标签**" 下，选择 " **高度机密** " 标签，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0eeee-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="0eeee-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0eeee-166">Next step</span></span>

<span data-ttu-id="0eeee-167">在您的测试环境中浏览其他 [信息保护](m365-enterprise-test-lab-guides.md#information-protection) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="0eeee-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0eeee-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eeee-168">See also</span></span>

[<span data-ttu-id="0eeee-169">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="0eeee-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0eeee-170">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="0eeee-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0eeee-171">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="0eeee-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
