---
title: Microsoft 365 企业版测试环境的数据分类
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
description: 使用此测试实验室指南创建和使用 Microsoft 365 企业版测试环境中文档的保留标签。
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919184"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="88e56-103">Microsoft 365 企业版测试环境的数据分类</span><span class="sxs-lookup"><span data-stu-id="88e56-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="88e56-104">*此测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="88e56-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="88e56-105">本文介绍如何在 Microsoft 365 企业版测试环境中使用保留标签配置数据分类。</span><span class="sxs-lookup"><span data-stu-id="88e56-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="88e56-106">对测试环境中的数据进行分类分为三个阶段：</span><span class="sxs-lookup"><span data-stu-id="88e56-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="88e56-107">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="88e56-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="88e56-108">阶段 2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="88e56-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="88e56-109">阶段 3：将保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="88e56-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="88e56-111">有关 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观地图，请转到 [Microsoft 365 企业版测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="88e56-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="88e56-112">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="88e56-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="88e56-113">如果你只想按最低要求以轻型方式配置保留标签，请按照轻型基本配置 [中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="88e56-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="88e56-114">如果要在模拟的企业中配置保留标签，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="88e56-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="88e56-115">测试保留标签不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 同步。</span><span class="sxs-lookup"><span data-stu-id="88e56-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="88e56-116">它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="88e56-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="88e56-117">阶段 2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="88e56-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="88e56-118">在此阶段，为 SharePoint Online 文档文件夹的不同保留级别创建保留标签：</span><span class="sxs-lookup"><span data-stu-id="88e56-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="88e56-119">使用全局管理员帐户登录到 [Microsoft 365](https://security.microsoft.com/homepage) 安全中心。</span><span class="sxs-lookup"><span data-stu-id="88e56-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="88e56-120">在浏览器 **的"主页 - Microsoft 365** 安全"选项卡中，选择"**分类**  >  **保留标签"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="88e56-121">选择“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="88e56-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="88e56-122">在"**命名标签"窗格中\*\*\*\*，在"** 命名标签"中 **输入**"内部公用"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="88e56-123">在"**文件计划描述符"窗格中**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="88e56-124">在"**标签设置"** 窗格中，根据需要将 **"保留**"设置为 **"打开**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="88e56-125">在"**查看设置"窗格中**，选择 **"创建标签"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="88e56-126">对具有以下名称的其他标签重复步骤 3-7：</span><span class="sxs-lookup"><span data-stu-id="88e56-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="88e56-127">Private</span><span class="sxs-lookup"><span data-stu-id="88e56-127">Private</span></span>
  - <span data-ttu-id="88e56-128">敏感</span><span class="sxs-lookup"><span data-stu-id="88e56-128">Sensitive</span></span>
  - <span data-ttu-id="88e56-129">高度机密</span><span class="sxs-lookup"><span data-stu-id="88e56-129">Highly Confidential</span></span>
1. <span data-ttu-id="88e56-130">在"**保留标签"窗格中**，选择"**发布标签"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="88e56-131">在"**选择要发布的标签"窗格中**，**选择"选择要发布的标签"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="88e56-132">在" **选择标签"** 窗格中，选择 **"添加"** 并选择所有四个标签。</span><span class="sxs-lookup"><span data-stu-id="88e56-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="88e56-133">选择 **"添加**"，然后选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="88e56-134">在"**选择要发布的标签"窗格中，** 选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="88e56-135">在"**选择位置"窗格中**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="88e56-136">在"**命名策略"窗格中**，在"名称"**中输入"\*\*\*\*示例组织**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="88e56-137">在"**查看设置"窗格中**，选择"**发布标签"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="88e56-138">可能需要几分钟才能发布保留标签。</span><span class="sxs-lookup"><span data-stu-id="88e56-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="88e56-139">阶段 3：将保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="88e56-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="88e56-140">在此阶段，您将发现 SharePoint Online 网站的"文档"文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。</span><span class="sxs-lookup"><span data-stu-id="88e56-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="88e56-141">首先，创建敏感级别的 SharePoint Online 团队网站：</span><span class="sxs-lookup"><span data-stu-id="88e56-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="88e56-142">使用浏览器的专用实例，使用全局管理员帐户登录 [Microsoft 365](https://admin.microsoft.com) 管理中心。</span><span class="sxs-lookup"><span data-stu-id="88e56-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="88e56-143">在磁贴列表中，选择 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="88e56-144">在浏览器的新 **"SharePoint"** 选项卡上，选择"**创建网站"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="88e56-145">在“创建网站”页中，选择“团队网站”。</span><span class="sxs-lookup"><span data-stu-id="88e56-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="88e56-146">在" **团队网站名称"** 框中，输入 **SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="88e56-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="88e56-147">在" **团队网站说明"** 框中，输入 **敏感文件的 SharePoint 网站**。</span><span class="sxs-lookup"><span data-stu-id="88e56-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="88e56-148">在 **"隐私设置**"**中，选择"专用 - 只有成员可以访问此网站**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="88e56-149">在"**要添加谁？"窗格中，** 选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="88e56-150">接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="88e56-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="88e56-151">在浏览器 **的"SensitiveFiles"** 选项卡中，选择"文档 **"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="88e56-152">选择"**设置"** 图标，然后选择"库 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="88e56-153">在 **"权限和管理"下**，**选择"将标签应用于此列表或库中的项目"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="88e56-154">如果未显示此选项，则尚未发布保留标签。</span><span class="sxs-lookup"><span data-stu-id="88e56-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="88e56-155">稍后尝试执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="88e56-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="88e56-156">在 **"设置-应用标签**"**中，** 选择下拉框中的"敏感"，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="88e56-157">接下来，在 SensitiveFiles 网站中创建新文档并更改其保留标签。</span><span class="sxs-lookup"><span data-stu-id="88e56-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="88e56-158">在"文档"文件夹中，选择"**新建**  >  **Word 文档"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="88e56-159">在空白文档中输入一些文本。</span><span class="sxs-lookup"><span data-stu-id="88e56-159">Enter some text in the blank document.</span></span> <span data-ttu-id="88e56-160">等待保存文本。</span><span class="sxs-lookup"><span data-stu-id="88e56-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="88e56-161">在菜单栏上，选择"**共享文档"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="88e56-162">在文件 **Document.docx** 旁边，选择垂直省略号， **然后选择详细信息**。</span><span class="sxs-lookup"><span data-stu-id="88e56-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="88e56-163">在右窗格的"属性"**部分，** 在"应用保留标签"下，请注意，文档已自动应用"**敏感**"保留标签。</span><span class="sxs-lookup"><span data-stu-id="88e56-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="88e56-164">单击 **编辑全部**。</span><span class="sxs-lookup"><span data-stu-id="88e56-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="88e56-165">在 **"Document.docx"** 窗格中的"**应用保留** 标签"下，选择"**高度机密**"标签，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="88e56-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="88e56-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="88e56-166">Next step</span></span>

<span data-ttu-id="88e56-167">探索 [测试环境中](m365-enterprise-test-lab-guides.md#information-protection) 的其他信息保护特性和功能。</span><span class="sxs-lookup"><span data-stu-id="88e56-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="88e56-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88e56-168">See also</span></span>

[<span data-ttu-id="88e56-169">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="88e56-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="88e56-170">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="88e56-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="88e56-171">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="88e56-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)