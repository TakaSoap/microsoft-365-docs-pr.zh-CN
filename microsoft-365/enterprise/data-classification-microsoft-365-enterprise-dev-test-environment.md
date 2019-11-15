---
title: Microsoft 365 企业版测试环境的数据分类
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可在 Microsoft 365 企业版测试环境中的文档上创建和使用 Office 365 保留标签。
ms.openlocfilehash: 1bcd3ab2d8069ad85d48ecf682d3b7d49e7cf739
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639782"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7e686-103">Microsoft 365 企业版测试环境的数据分类</span><span class="sxs-lookup"><span data-stu-id="7e686-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7e686-104">使用本文中的说明，可以在 Microsoft 365 企业版测试环境中使用 Office 365 保留标签配置数据分类。</span><span class="sxs-lookup"><span data-stu-id="7e686-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7e686-106">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="7e686-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7e686-107">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="7e686-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7e686-108">如果只想使用最低要求以轻型方式配置 Office 365 保留标签，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="7e686-108">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7e686-109">如果要在模拟的企业中配置 Office 365 保留标签，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="7e686-109">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e686-110">测试 Office 365 保留标签不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="7e686-110">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7e686-111">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="7e686-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="7e686-112">第2阶段：创建 Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="7e686-112">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="7e686-113">在此阶段中，您将为 SharePoint Online 文档文件夹的不同保留级别创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="7e686-113">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="7e686-114">使用全局管理员帐户登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7e686-114">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="7e686-115">在浏览器的“**主页 - Microsoft 365 合规性**”选项卡中，单击“**分类 > 标签**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-115">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="7e686-116">单击“**保留标签 > 创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-116">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="7e686-117">在“**命名标签**”窗格上的“**命名标签**”中键入“**内部公用**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-117">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="7e686-118">在“**文件计划描述符**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-118">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7e686-119">在“**标签设置**”窗格中，根据需要将“**保留**”设置为“**开**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-119">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7e686-120">在“**查看设置**”窗格中，单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-120">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7e686-121">对具有以下名称的其他标签重复步骤 3-7：</span><span class="sxs-lookup"><span data-stu-id="7e686-121">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="7e686-122">Private</span><span class="sxs-lookup"><span data-stu-id="7e686-122">Private</span></span>
    
  - <span data-ttu-id="7e686-123">敏感</span><span class="sxs-lookup"><span data-stu-id="7e686-123">Sensitive</span></span>
    
  - <span data-ttu-id="7e686-124">高度机密</span><span class="sxs-lookup"><span data-stu-id="7e686-124">Highly Confidential</span></span>
  
9. <span data-ttu-id="7e686-125">在“开始”>“标签”窗格中，单击“发布标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-125">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="7e686-126">在“选择要发布的标签”窗格中，单击“选择要发布的标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-126">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="7e686-127">在“选择标签”窗格中，单击“添加”并选择全部四个标签\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-127">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="7e686-128">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-128">Click **Done**.</span></span>
    
13. <span data-ttu-id="7e686-129">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-129">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="7e686-130">在“**选择位置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-130">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="7e686-131">在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-131">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="7e686-132">在“**查看设置**”窗格中，单击“**发布标签**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-132">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="7e686-133">请注意，发布保留标签可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="7e686-133">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="7e686-134">第3阶段：将 Office 365 保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="7e686-134">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="7e686-135">在此阶段中，您将发现 SharePoint Online 网站的 Documents 文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。</span><span class="sxs-lookup"><span data-stu-id="7e686-135">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="7e686-136">首先，创建一个敏感级别的 SharePoint Online 团队网站：</span><span class="sxs-lookup"><span data-stu-id="7e686-136">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="7e686-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span><span class="sxs-lookup"><span data-stu-id="7e686-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="7e686-138">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-138">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="7e686-139">在浏览器的 "新建**SharePoint** " 选项卡上，单击 "**创建网站**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-139">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="7e686-140">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-140">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="7e686-141">在 "**团队网站名称**" 中，键入**SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="7e686-141">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="7e686-142">在 "**工作组网站说明**" 中，键入 " **SharePoint 网站" 以查找敏感文件**。</span><span class="sxs-lookup"><span data-stu-id="7e686-142">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="7e686-143">在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-143">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7e686-144">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-144">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="7e686-145">接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e686-145">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="7e686-146">在浏览器的 " **SensitiveFiles** " 选项卡中，单击 "**文档**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-146">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="7e686-147">单击设置图标，然后单击“**库设置**”。</span><span class="sxs-lookup"><span data-stu-id="7e686-147">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="7e686-148">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e686-148">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="7e686-149">在 "**设置-应用标签**" 中，选择下拉框中的 "**敏感**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-149">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="7e686-150">接下来，在 SensitiveFiles 网站中创建一个新文档并更改其保留标签。</span><span class="sxs-lookup"><span data-stu-id="7e686-150">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="7e686-151">在 "文档" 文件夹中，单击 "**新建 > Word 文档**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-151">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="7e686-152">在空白文档中键入一些文本。</span><span class="sxs-lookup"><span data-stu-id="7e686-152">Type some text in the blank document.</span></span> <span data-ttu-id="7e686-153">等待文本保存。</span><span class="sxs-lookup"><span data-stu-id="7e686-153">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="7e686-154">在菜单栏中，单击 "**共享文档**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-154">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="7e686-155">单击**文档 .docx**文件名旁边的单词图标。</span><span class="sxs-lookup"><span data-stu-id="7e686-155">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="7e686-156">在右侧窗格中的 "**属性**" 部分，在 "**应用保留标签**" 下，请注意文档已自动应用了**敏感**标签。</span><span class="sxs-lookup"><span data-stu-id="7e686-156">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="7e686-157">单击 "**编辑全部**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-157">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="7e686-158">在 "**文档 .docx** " 窗格中的 "**应用标签**" 下，选择 "**高度机密**" 标签，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="7e686-158">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="7e686-159">请参阅**信息保护**阶段中的[配置环境分类](infoprotect-configure-classification.md)步骤的信息和链接，了解如何在生产环境中部署 Office 365 保留标签。</span><span class="sxs-lookup"><span data-stu-id="7e686-159">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="7e686-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e686-160">Next step</span></span>

<span data-ttu-id="7e686-161">在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="7e686-161">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e686-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e686-162">See also</span></span>

[<span data-ttu-id="7e686-163">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="7e686-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7e686-164">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="7e686-164">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7e686-165">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="7e686-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 