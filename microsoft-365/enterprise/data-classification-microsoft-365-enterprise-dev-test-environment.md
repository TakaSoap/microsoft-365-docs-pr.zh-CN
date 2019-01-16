---
title: Microsoft 365 企业版的数据分类测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南创建和使用 Office 365 标签对 Microsoft 365 企业版测试环境中的文档。
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866013"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5fa8f-103">Microsoft 365 企业版的数据分类测试环境</span><span class="sxs-lookup"><span data-stu-id="5fa8f-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5fa8f-104">使用本文中的说明，您可以配置 Microsoft 365 企业版在测试环境中使用 Office 365 保留标签的数据分类。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5fa8f-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5fa8f-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="5fa8f-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5fa8f-108">如果您只想要配置轻型方式的最低硬件要求与 Office 365 标签，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5fa8f-109">如果您想要配置模拟企业中的 Office 365 标签，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fa8f-p101">测试 Office 365 标签不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="5fa8f-112">第 2 阶段：创建 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="5fa8f-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="5fa8f-113">在此阶段中，您将创建为 SharePoint Online 文档文件夹的保留的不同级别的标签。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-113">In this phase, you create the labels for the different levels of retention for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="5fa8f-p102">如果需要使用专用的 Internet 浏览器实例，并登录到您的全局管理员帐户的 Office 门户。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5fa8f-116">在“**Microsoft Office 主页**”标签页中，单击“**管理**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="5fa8f-117">在浏览器的新“Office 管理中心”\*\*\*\* 标签页中，单击“管理中心”>“安全&amp;合规性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="5fa8f-p103">从新**主页-安全&amp;合规性**选项卡上的浏览器中，单击**分类 > 标签**。从**主页 > 标签**窗格中，单击**保留**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-p103">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**. From the **Home > Labels** pane, click the **Retention** tab.</span></span>
    
5. <span data-ttu-id="5fa8f-120">单击**创建标签**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-120">Click **Create a label**.</span></span>
    
6. <span data-ttu-id="5fa8f-121">在“**命名标签**”窗格中，键入“**内部公用**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-121">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5fa8f-122">在“**标签设置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-122">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="5fa8f-123">在“查看设置”\*\*\*\* 窗格中，单击“创建此标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-123">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="5fa8f-124">对以下标签重复步骤 5-8：</span><span class="sxs-lookup"><span data-stu-id="5fa8f-124">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="5fa8f-125">Private</span><span class="sxs-lookup"><span data-stu-id="5fa8f-125">Private</span></span>
    
  - <span data-ttu-id="5fa8f-126">敏感</span><span class="sxs-lookup"><span data-stu-id="5fa8f-126">Sensitive</span></span>
    
  - <span data-ttu-id="5fa8f-127">高度机密</span><span class="sxs-lookup"><span data-stu-id="5fa8f-127">Highly Confidential</span></span>
    
10. <span data-ttu-id="5fa8f-128">在“开始”>“标签”窗格中，单击“发布标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-128">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="5fa8f-129">在“选择要发布的标签”窗格中，单击“选择要发布的标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-129">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="5fa8f-130">在“选择标签”窗格中，单击“添加”并选择全部四个标签\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-130">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="5fa8f-131">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-131">Click **Done**.</span></span>
    
14. <span data-ttu-id="5fa8f-132">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-132">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="5fa8f-133">在“**选择位置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-133">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="5fa8f-134">在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-134">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="5fa8f-135">在“**查看设置**”窗格中，单击“**发布标签**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-135">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="5fa8f-136">请注意，可能需要几分钟，要发布的标签。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-136">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="5fa8f-137">第 3 阶段： 将 Office 365 保留标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="5fa8f-137">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="5fa8f-138">在此阶段中，可以发现的 SharePoint Online 网站的文档文件夹中的文件的默认标签行为和手动更改文档的标签。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-138">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="5fa8f-139">首先，创建敏感级别 SharePoint Online 团队网站：</span><span class="sxs-lookup"><span data-stu-id="5fa8f-139">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="5fa8f-p104">在本地计算机上使用浏览器中，登录到 Office 门户使用全局管理员帐户。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-p104">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5fa8f-142">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-142">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="5fa8f-143">在新**SharePoint**选项卡在浏览器中，单击**创建网站**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-143">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="5fa8f-144">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-144">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="5fa8f-145">在**工作组网站名称**框中，键入**SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-145">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="5fa8f-146">在**团队网站说明**框中，键入**敏感文件的 SharePoint 网站**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-146">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="5fa8f-147">在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-147">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5fa8f-148">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-148">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="5fa8f-149">接下来，配置敏感标签 SensitiveFiles 工作组网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-149">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="5fa8f-150">在浏览器的**SensitiveFiles**选项卡上，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-150">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="5fa8f-151">单击设置图标，然后单击“**库设置**”。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-151">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="5fa8f-152">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-152">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="5fa8f-153">在**设置应用标签**，在下拉列表框中，选择**敏感**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-153">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="5fa8f-154">接下来，SensitiveFiles 网站中创建一个新文档，并更改其标签。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-154">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="5fa8f-155">在文档文件夹中，单击**新建 > Word 文档**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-155">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="5fa8f-p105">空白文档中键入一些文本。等待要保存的文本。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-p105">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="5fa8f-158">在菜单栏中，单击**共享文档**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-158">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="5fa8f-159">单击**Document.docx**文件名旁边的 Word 图标。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-159">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="5fa8f-160">在右侧窗格中，在**属性**部分下**应用保留标签**，请注意文档已自动应用**敏感**标签。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-160">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="5fa8f-161">单击**编辑所有**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-161">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="5fa8f-162">在**Document.docx**窗格中的**应用标签**、 下，选择的**高度机密**标签，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-162">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="5fa8f-163">有关信息和生产环境中的 Office 365 保留标签的链接的**信息保护**阶段，请参阅[针对您的环境配置分类](infoprotect-configure-classification.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-163">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="5fa8f-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5fa8f-164">Next step</span></span>

<span data-ttu-id="5fa8f-165">浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="5fa8f-165">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fa8f-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa8f-166">See also</span></span>

[<span data-ttu-id="5fa8f-167">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="5fa8f-167">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5fa8f-168">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="5fa8f-168">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5fa8f-169">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="5fa8f-169">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 