---
title: Microsoft 365 企业版的数据分类测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南创建和使用 Office 365 标签对 Microsoft 365 企业版测试环境中的文档。
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866013"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="75c56-103">Microsoft 365 企业版的数据分类测试环境</span><span class="sxs-lookup"><span data-stu-id="75c56-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="75c56-104">使用本文中的说明，您可以配置 Microsoft 365 企业版在测试环境中使用 Office 365 标签的数据分类。</span><span class="sxs-lookup"><span data-stu-id="75c56-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="75c56-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="75c56-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="75c56-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="75c56-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="75c56-108">如果您只想要配置轻型方式的最低硬件要求与 Office 365 标签，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="75c56-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="75c56-109">如果您想要配置模拟企业中的 Office 365 标签，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="75c56-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="75c56-p101">测试 Office 365 标签不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="75c56-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="75c56-112">第 2 阶段：创建 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="75c56-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="75c56-113">在此阶段中，您将创建为 SharePoint Online 文档文件夹的安全的不同级别的标签。</span><span class="sxs-lookup"><span data-stu-id="75c56-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="75c56-p102">如果需要使用专用的 Internet 浏览器实例，并登录到 Office 365 门户使用全局管理员帐户。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="75c56-p102">If needed, use a private instance of your Internet browser and sign in to the Office 365 portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="75c56-116">在“Microsoft Office 主页”\*\*\*\* 标签页中，单击“管理员”磁贴\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="75c56-117">在浏览器的新“Office 管理中心”\*\*\*\* 标签页中，单击“管理中心”>“安全&amp;合规性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="75c56-118">在浏览器的新“主页 -安全&amp;合规性”\*\*\*\* 标签页中，单击“分类”>“标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="75c56-119">在“**开始”>“标签**”窗格中，单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="75c56-120">在“**命名标签**”窗格中，键入“**内部公用**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="75c56-121">在“**标签设置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="75c56-122">在“查看设置”\*\*\*\* 窗格中，单击“创建此标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="75c56-123">对以下标签重复步骤 5-8：</span><span class="sxs-lookup"><span data-stu-id="75c56-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="75c56-124">Private</span><span class="sxs-lookup"><span data-stu-id="75c56-124">Private</span></span>
    
  - <span data-ttu-id="75c56-125">敏感</span><span class="sxs-lookup"><span data-stu-id="75c56-125">Sensitive</span></span>
    
  - <span data-ttu-id="75c56-126">高度机密</span><span class="sxs-lookup"><span data-stu-id="75c56-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="75c56-127">在“开始”>“标签”窗格中，单击“发布标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="75c56-128">在“选择要发布的标签”窗格中，单击“选择要发布的标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="75c56-129">在“选择标签”窗格中，单击“添加”并选择全部四个标签\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="75c56-130">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="75c56-131">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="75c56-132">在“**选择位置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="75c56-133">在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="75c56-134">在“**查看设置**”窗格中，单击“**发布标签**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="75c56-135">请注意，可能需要几分钟，要发布的标签。</span><span class="sxs-lookup"><span data-stu-id="75c56-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="75c56-136">第 3 阶段： 将 Office 365 标签应用于文档</span><span class="sxs-lookup"><span data-stu-id="75c56-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="75c56-137">在此阶段中，可以发现的 SharePoint Online 网站的文档文件夹中的文件的默认标签行为和手动更改文档的标签。</span><span class="sxs-lookup"><span data-stu-id="75c56-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="75c56-138">首先，创建敏感级别 SharePoint Online 团队网站：</span><span class="sxs-lookup"><span data-stu-id="75c56-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="75c56-p103">使用本地计算机上的浏览器，并使用全局管理员帐户登录 Office 365 门户。如需帮助，请参阅[如何登录 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="75c56-p103">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="75c56-141">在磁贴列表中，单击“**SharePoint**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="75c56-142">在新**SharePoint**选项卡在浏览器中，单击**创建网站**。</span><span class="sxs-lookup"><span data-stu-id="75c56-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="75c56-143">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="75c56-144">在**工作组网站名称**框中，键入**SensitiveFiles**。</span><span class="sxs-lookup"><span data-stu-id="75c56-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="75c56-145">在**团队网站说明**框中，键入**敏感文件的 SharePoint 网站**。</span><span class="sxs-lookup"><span data-stu-id="75c56-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="75c56-146">在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="75c56-147">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="75c56-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="75c56-148">接下来，配置敏感标签 SensitiveFiles 工作组网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="75c56-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="75c56-149">在浏览器的**SensitiveFiles**选项卡上，单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="75c56-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="75c56-150">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="75c56-151">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75c56-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="75c56-152">在**设置应用标签**，在下拉列表框中，选择**敏感**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="75c56-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="75c56-153">接下来，SensitiveFiles 网站中创建一个新文档，并更改其标签。</span><span class="sxs-lookup"><span data-stu-id="75c56-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="75c56-154">在文档文件夹中，单击**新建 > Word 文档**。</span><span class="sxs-lookup"><span data-stu-id="75c56-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="75c56-p104">空白文档中键入一些文本。等待要保存的文本。</span><span class="sxs-lookup"><span data-stu-id="75c56-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="75c56-157">在菜单栏中，单击**共享文档**。</span><span class="sxs-lookup"><span data-stu-id="75c56-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="75c56-158">单击**Document.docx**文件名旁边的 Word 图标。</span><span class="sxs-lookup"><span data-stu-id="75c56-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="75c56-159">在右侧窗格中，在**属性**部分下**应用标签**，请注意文档已自动应用**敏感**标签。</span><span class="sxs-lookup"><span data-stu-id="75c56-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="75c56-160">单击**编辑所有**。</span><span class="sxs-lookup"><span data-stu-id="75c56-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="75c56-161">在**Document.docx**窗格中的**应用标签**、 下，选择的**高度机密**标签，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="75c56-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="75c56-162">有关信息和生产环境中的 Office 365 标签的链接的**信息保护**阶段，请参阅[针对您的环境配置分类](data-classification-microsoft-365-enterprise-dev-test-environment.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="75c56-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="75c56-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="75c56-163">Next step</span></span>

<span data-ttu-id="75c56-164">浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="75c56-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="75c56-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75c56-165">See also</span></span>

[<span data-ttu-id="75c56-166">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="75c56-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="75c56-167">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="75c56-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="75c56-168">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="75c56-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 