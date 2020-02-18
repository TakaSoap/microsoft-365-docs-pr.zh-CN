---
title: 使用保留标签和 DLP 保护团队中的文件
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 摘要：为具有各种信息保护级别的团队中的文件应用保留标签和数据丢失防护 (DLP) 策略。
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083387"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="cab89-103">使用保留标签和 DLP 保护团队中的文件</span><span class="sxs-lookup"><span data-stu-id="cab89-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="cab89-104">使用本文中的步骤针对基线、敏感和高度保密的团队及其基础 SharePoint 网站设计并部署保留标签和数据丢失防护 (DLP) 策略。</span><span class="sxs-lookup"><span data-stu-id="cab89-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="cab89-105">有关这三层保护的详细信息，请参阅[保护 Microsoft Teams 中的文件](secure-files-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cab89-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="cab89-106">工作原理</span><span class="sxs-lookup"><span data-stu-id="cab89-106">How this works</span></span>

1. <span data-ttu-id="cab89-107">创建所需的保留标签并发布这些标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="cab89-108">最多可能需要 12 个小时来发布这些标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="cab89-109">对于所需的基础 SharePoint 网站，将文档库设置编辑为向库中项目应用所需的保留标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="cab89-110">创建 DLP 策略以根据保留标签执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="cab89-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="cab89-111">当用户将文档添加到团队的基础 SharePoint 网站库时，默认情况下该文档将接收分配的保留标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="cab89-112">用户可以根据需要更改标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-112">Users can change the label, if needed.</span></span> <span data-ttu-id="cab89-113">当用户在组织外共享文档时，DLP 将检查是否已分配标签，并在 DLP 策略与标签匹配时执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="cab89-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="cab89-114">DLP 还将查找其他策略匹配，例如，如果配置了此类策略，则使用信用卡号保护文件。</span><span class="sxs-lookup"><span data-stu-id="cab89-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="cab89-115">基础 SharePoint 网站的保留标签</span><span class="sxs-lookup"><span data-stu-id="cab89-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="cab89-116">为基础 SharePoint 网站创建并分配保留标签分为三个阶段。</span><span class="sxs-lookup"><span data-stu-id="cab89-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="cab89-117">阶段 1：确定保留标签名称</span><span class="sxs-lookup"><span data-stu-id="cab89-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="cab89-118">在此阶段，对于应用到基础 SharePoint 网站的四个级别的信息保护，确定保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="cab89-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="cab89-119">下表列出了针对每个级别建议的名称。</span><span class="sxs-lookup"><span data-stu-id="cab89-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="cab89-120">**基础 SharePoint 网站保护级别**</span><span class="sxs-lookup"><span data-stu-id="cab89-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="cab89-121">**标签名称**</span><span class="sxs-lookup"><span data-stu-id="cab89-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cab89-122">基线 - 公用</span><span class="sxs-lookup"><span data-stu-id="cab89-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="cab89-123">内部公用</span><span class="sxs-lookup"><span data-stu-id="cab89-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="cab89-124">基线 - 专用</span><span class="sxs-lookup"><span data-stu-id="cab89-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="cab89-125">Private</span><span class="sxs-lookup"><span data-stu-id="cab89-125">Private</span></span>  <br/> |
|<span data-ttu-id="cab89-126">敏感</span><span class="sxs-lookup"><span data-stu-id="cab89-126">Sensitive</span></span>  <br/> |<span data-ttu-id="cab89-127">敏感</span><span class="sxs-lookup"><span data-stu-id="cab89-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="cab89-128">高度机密</span><span class="sxs-lookup"><span data-stu-id="cab89-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="cab89-129">高度机密</span><span class="sxs-lookup"><span data-stu-id="cab89-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="cab89-130">阶段 2：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="cab89-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="cab89-131">在此阶段中，针对不同的信息保护级别创建并发布确定的标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="cab89-132">使用具有安全管理员或公司管理员角色的帐户登录 [Microsoft 365 合规门户](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="cab89-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="cab89-133">在浏览器的“**主页 - Microsoft 365 合规性**”选项卡中，单击“**分类 > 标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="cab89-134">单击“**保留标签 > 创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="cab89-135">在“**命名标签**”窗格中，键入标签的名称和管理员及用户描述，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="cab89-136">在“**文件计划描述符**”窗格中，根据需要进行填写，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="cab89-137">在“**标签设置**”窗格中，根据需要将“**保留**”设置为“**开**”并配置保留设置。</span><span class="sxs-lookup"><span data-stu-id="cab89-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="cab89-138">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="cab89-139">在“**查看设置**”窗格中，单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="cab89-140">对于其他标签，请单击“创建标签”\*\*\*\*，然后根据需要重复此过程的步骤 3-7。</span><span class="sxs-lookup"><span data-stu-id="cab89-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="cab89-141">发布新标签</span><span class="sxs-lookup"><span data-stu-id="cab89-141">Publish your new labels</span></span>

<span data-ttu-id="cab89-142">接下来，使用这些步骤发布新的保留标签。</span><span class="sxs-lookup"><span data-stu-id="cab89-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="cab89-143">在“**标签**”窗格中，单击“**保留标签**”选项卡，然后单击“**发布标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="cab89-144">在“**选择要发布的标签**”窗格中，单击“**选择要发布的标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="cab89-145">在“**选择标签**”窗格中，单击“**添加**”并选择全部四个标签，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="cab89-146">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="cab89-147">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="cab89-148">在“选择位置”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="cab89-149">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入标签组的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="cab89-150">在“查看设置”\*\*\*\* 窗格中，单击“发布标签”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="cab89-151">步骤 3：将保留标签应用于基础 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="cab89-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="cab89-152">使用这些步骤将保留标签应用于基础 SharePoint 网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="cab89-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="cab89-153">在团队中，单击“文件”，然后单击“在 SharePoint 中打开”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="cab89-154">在浏览器的新“SharePoint 网站”标签页中，单击“文档”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="cab89-155">单击设置图标，然后单击“库设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="cab89-156">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="cab89-157">在“**设置-应用标签**”中，选择相应的保留标签，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="cab89-158">关闭 SharePoint 网站的选项卡。</span><span class="sxs-lookup"><span data-stu-id="cab89-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="cab89-159">重复步骤 1-6，将保留标签分配给其他基础 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="cab89-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="cab89-160">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="cab89-160">Here is your resulting configuration.</span></span>
  
![四种类型的基础 SharePoint 网站的保留标签。](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="cab89-162">基础 SharePoint 网站的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="cab89-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="cab89-163">使用以下步骤配置 DLP 策略，该策略可在用户在组织外共享关于基础 SharePoint 网站的文档时进行通知。</span><span class="sxs-lookup"><span data-stu-id="cab89-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="cab89-164">使用具有安全管理员或公司管理员角色的帐户登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="cab89-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="cab89-165">在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="cab89-166">在“**主页 > 数据丢失防护**”窗格中，单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="cab89-167">在“**从模板开始或创建自定义策略**”窗格中，单击“**自定义**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="cab89-168">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入敏感级别 DLP 策略的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="cab89-169">在“**选择位置**”窗格中，单击“**允许选择特定位置**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="cab89-170">在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="cab89-171">在“**自定义要保护的内容类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="cab89-172">在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="cab89-173">在“**保留标签**”窗格中，单击“**添加**”，选择“**敏感**”标签，然后依次单击“**添加**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="cab89-174">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="cab89-175">在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="cab89-176">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="cab89-177">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="cab89-178">在文本框中，键入或粘贴以下提示之一：</span><span class="sxs-lookup"><span data-stu-id="cab89-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="cab89-p106">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="cab89-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="cab89-p107">高度机密文件已获加密保护。只有 IT 部门向其授予对这些文件的相应权限的外部用户，才能读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="cab89-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="cab89-184">或键入或粘贴自己的策略提示，指示用户如何在组织外共享文件。</span><span class="sxs-lookup"><span data-stu-id="cab89-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="cab89-185">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="cab89-186">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="cab89-187">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="cab89-188">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="cab89-189">以下为敏感团队的配置结果。</span><span class="sxs-lookup"><span data-stu-id="cab89-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![使用敏感保留标签的敏感团队的 DLP 策略](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="cab89-191">接下来，使用以下步骤配置 DLP 策略，该策略可在用户在组织外共享关于基础 SharePoint 网站的文档时阻止用户。</span><span class="sxs-lookup"><span data-stu-id="cab89-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="cab89-192">在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="cab89-193">在“**数据丢失防护**”窗格中，单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="cab89-194">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="cab89-195">在“命名策略”\*\*\*\* 窗格中，在“名称”\*\*\*\* 中键入高度敏感级别 DLP 策略的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="cab89-196">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="cab89-197">在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="cab89-198">在“**自定义要保护的敏感信息类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="cab89-199">在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="cab89-200">在“**保留标签**”窗格中，单击“**添加**”，选择“**高度机密**”标签，然后依次单击“**添加**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="cab89-201">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="cab89-202">在“自定义要保护的敏感信息类型”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="cab89-203">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="cab89-204">在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="cab89-205">在文本框中，键入或粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="cab89-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="cab89-p108">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="cab89-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="cab89-209">或者，键入或粘贴自己的策略提示，指示用户如何在组织外共享文件。</span><span class="sxs-lookup"><span data-stu-id="cab89-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="cab89-210">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cab89-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="cab89-211">在“**如果检测到敏感信息，希望采取什么操作?**”窗格中，在“**共享特定数量的敏感信息时进行检测**”下方单击“**限制访问或加密内容**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cab89-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="cab89-212">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="cab89-213">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cab89-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="cab89-214">以下为高度机密团队的配置结果。</span><span class="sxs-lookup"><span data-stu-id="cab89-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![使用高度保密保留标签的高度机密团队的 DLP 策略](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="cab89-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cab89-216">Next step</span></span>

[<span data-ttu-id="cab89-217">使用灵敏度标签保护团队中的文件</span><span class="sxs-lookup"><span data-stu-id="cab89-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="cab89-218">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cab89-218">See Also</span></span>

[<span data-ttu-id="cab89-219">保护 Microsoft Teams 中的文件</span><span class="sxs-lookup"><span data-stu-id="cab89-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="cab89-220">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="cab89-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


