---
title: 创建和应用信息管理策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 了解如何设置信息管理策略来控制信息保留时间并跟踪使用信息的人。
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817991"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="2df0a-103">创建和应用信息管理策略</span><span class="sxs-lookup"><span data-stu-id="2df0a-103">Create and apply information management policies</span></span>

<span data-ttu-id="2df0a-104">信息管理策略使组织能够控制内容的保留时间，审核用户对内容执行哪些操作，以及向文档添加条码或标签。</span><span class="sxs-lookup"><span data-stu-id="2df0a-104">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="2df0a-105">策略可帮助强制执行法律和政府法规或内部业务流程的合规性。</span><span class="sxs-lookup"><span data-stu-id="2df0a-105">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="2df0a-106">作为管理员，您可以设置一个策略来控制如何跟踪文档以及文档的保留时间。</span><span class="sxs-lookup"><span data-stu-id="2df0a-106">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="2df0a-107">可以在网站层次结构中的三个不同位置（从最广泛到最窄）创建信息管理策略：</span><span class="sxs-lookup"><span data-stu-id="2df0a-107">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="2df0a-108">创建一个策略以用于网站集中的多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-108">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="2df0a-109">为网站内容类型创建策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-109">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="2df0a-110">为列表或库创建策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-110">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="2df0a-111">有关详细信息，请参阅 [信息管理策略简介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2df0a-111">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="2df0a-112">为网站集中的多个内容类型创建策略</span><span class="sxs-lookup"><span data-stu-id="2df0a-112">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="2df0a-113"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-113"><a name="__toc261001590"> </a></span></span>

<span data-ttu-id="2df0a-114">为了确保信息策略应用于网站集中特定类型的所有文档，请考虑在网站集级别创建策略，然后将该策略应用于内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-114">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="2df0a-115">这些称为网站集策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-115">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="2df0a-116">在网站集主页上 \> **，设置SharePoint** ![ 2016 设置按钮。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="2df0a-116">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="2df0a-117">\>“**网站设置**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-117">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="2df0a-118">在连接到SharePoint的网站中，单击"设置"，**再** 单击"网站内容"，然后单击"网站 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-118">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="2df0a-119">在"网站设置页上的"网站 **集管理** \> **内容类型策略模板"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-119">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
!["网站集"页上的"内容类型策略设置链接](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="2df0a-121">在"策略"页上， \> **创建**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-121">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="2df0a-122">输入策略的名称和说明，然后编写一个简短的策略声明，向用户解释策略用于什么。</span><span class="sxs-lookup"><span data-stu-id="2df0a-122">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="2df0a-123">请参阅下一部分，了解如何为网站内容类型创建策略，了解如何设置要与策略关联的功能。</span><span class="sxs-lookup"><span data-stu-id="2df0a-123">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="2df0a-124">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-124">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="2df0a-125">为网站内容类型创建策略</span><span class="sxs-lookup"><span data-stu-id="2df0a-125">Create a policy for a site content type</span></span>
<span data-ttu-id="2df0a-126"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-126"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="2df0a-127">将信息管理策略添加到内容类型后，可轻松将策略功能与多个列表或库关联。</span><span class="sxs-lookup"><span data-stu-id="2df0a-127">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="2df0a-128">可以选择将现有信息管理策略添加到内容类型，也可以创建特定于单个内容类型的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-128">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="2df0a-129">您还可以将信息管理策略添加到特定于列表的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-129">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="2df0a-130">这只能将策略应用于正在使用内容类型的列表中的项目。</span><span class="sxs-lookup"><span data-stu-id="2df0a-130">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="2df0a-131">在网站集主页上 \> **，设置SharePoint** ![ 2016 设置按钮。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="2df0a-131">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="2df0a-132">\>“**网站设置**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-132">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="2df0a-133">在连接到SharePoint的网站中，单击"设置"，**再** 单击"网站内容"，然后单击"网站 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-133">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="2df0a-134">在"网站设置页上的"**网站设计器库** \> **网站内容类型"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-134">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
!["网站类型"页上的"网站设置链接](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="2df0a-136">在"网站内容类型设置页上，选择要添加策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-136">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="2df0a-137">在"网站内容类型"页上的"设置 \> **信息管理策略设置"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-137">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="2df0a-138">在"编辑策略"页上，输入策略的名称和说明，然后编写简要说明，向用户解释策略用于哪些内容。</span><span class="sxs-lookup"><span data-stu-id="2df0a-138">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="2df0a-139">In the next sections， select the individual policy features that you want to add to your information management policy.</span><span class="sxs-lookup"><span data-stu-id="2df0a-139">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![内容策略的类型](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="2df0a-141">若要指定受此策略影响的文档和项目的保留期，请选择"启用保留"，然后指定保留期以及您希望在项目过期时发生的操作。 </span><span class="sxs-lookup"><span data-stu-id="2df0a-141">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="2df0a-142">指定保留期</span><span class="sxs-lookup"><span data-stu-id="2df0a-142">To specify a retention period</span></span>
    
||||||<span data-ttu-id="2df0a-143">**1.**</span><span class="sxs-lookup"><span data-stu-id="2df0a-143">**1.**</span></span>|<span data-ttu-id="2df0a-144">\*\*Choose \*\*Add a retention stage for records...\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2df0a-144">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="2df0a-145">2.</span><span class="sxs-lookup"><span data-stu-id="2df0a-145">2.</span></span>  <br/> | <span data-ttu-id="2df0a-146">选择保留期选项以指定文档或项目设置为过期的时间。</span><span class="sxs-lookup"><span data-stu-id="2df0a-146">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="2df0a-147">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2df0a-147">Do one of the following:</span></span>  <br/>  <span data-ttu-id="2df0a-148">若要基于日期属性设置到期日期，请在"事件 此阶段基于项目的日期属性"下，选择文档或项目操作 (例如，"已创建或修改) "以及此操作后的时间增量 (例如，您希望项目过期的天数、月数或年 \> 数) 。</span><span class="sxs-lookup"><span data-stu-id="2df0a-148">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="2df0a-149">若要使用自定义保留公式确定过期时间，请选择"按 **此服务器上安装的自定义保留公式设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-149">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="2df0a-150">> [!NOTE]>此选项仅在管理员已设置自定义公式时可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-150">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="2df0a-151">3.</span><span class="sxs-lookup"><span data-stu-id="2df0a-151">3.</span></span>  <br/> |<span data-ttu-id="2df0a-152">" **启动工作流"** 选项仅在为已具有与其关联的工作流的列表、库或内容类型定义策略时可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-152">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="2df0a-153">然后，您可以选择工作流。</span><span class="sxs-lookup"><span data-stu-id="2df0a-153">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-154">4.</span><span class="sxs-lookup"><span data-stu-id="2df0a-154">4.</span></span>  <br/> |<span data-ttu-id="2df0a-155">在" **定期"** 部分中，选择 **"重复此阶段的操作..."。** 并输入希望操作重复出现多久。</span><span class="sxs-lookup"><span data-stu-id="2df0a-155">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="2df0a-156">> [!NOTE]>此选项仅在所选操作可以重复时可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-156">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="2df0a-157">例如，不能为"永久删除"**操作设置定期。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-157">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="2df0a-158">5.</span><span class="sxs-lookup"><span data-stu-id="2df0a-158">5.</span></span>  <br/> |<span data-ttu-id="2df0a-159">选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-159">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="2df0a-160">若要对受此策略限制的文档和项目启用审核，请选择"启用审核"，然后指定要审核的事件。</span><span class="sxs-lookup"><span data-stu-id="2df0a-160">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="2df0a-161">启用审核</span><span class="sxs-lookup"><span data-stu-id="2df0a-161">To enable auditing</span></span>
    
||||||<span data-ttu-id="2df0a-162">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2df0a-162">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="2df0a-163">在"编辑策略"页上的 **"审核** 启用审核\*\*"下，选中要保留审核跟踪的事件旁边的 **\>** 复选框。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2df0a-163">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="2df0a-164">**2.**</span><span class="sxs-lookup"><span data-stu-id="2df0a-164">**2.**</span></span> <br/> |<span data-ttu-id="2df0a-165">**若要提示用户将这些条码插入文档**，请选择"提示用户先插入条码，然后再 **保存或打印"。** </span><span class="sxs-lookup"><span data-stu-id="2df0a-165">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="2df0a-166">**3.**</span><span class="sxs-lookup"><span data-stu-id="2df0a-166">**3.**</span></span> <br/> |<span data-ttu-id="2df0a-167">**选择\*\*\*\*"** 确定"\*\*将审核功能应用于策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-167">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="2df0a-168">利用审核策略功能，组织可以创建和分析文档的审核跟踪，以及任务列表、问题列表、讨论组和日历等列表项。</span><span class="sxs-lookup"><span data-stu-id="2df0a-168">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="2df0a-169">此策略功能可提供用于记录事件的审核日志，例如内容被查看、编辑或删除的时间。</span><span class="sxs-lookup"><span data-stu-id="2df0a-169">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="2df0a-170">在将审核作为信息管理策略的一部分启用时，管理员可以查看基于 Microsoft Excel 并汇总当前使用情况的策略使用率报告中的审核数据。</span><span class="sxs-lookup"><span data-stu-id="2df0a-170">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="2df0a-171">管理员可以使用这些报告来确定信息在组织内的使用率。</span><span class="sxs-lookup"><span data-stu-id="2df0a-171">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="2df0a-172">这些报告还可帮助组织验证和记录其法规合规性或调查潜在问题。</span><span class="sxs-lookup"><span data-stu-id="2df0a-172">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="2df0a-173">审核日志可记录以下信息：事件名称、事件的日期和时间以及执行操作的用户的系统名称。</span><span class="sxs-lookup"><span data-stu-id="2df0a-173">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="2df0a-174">当条码作为策略的一部分启用时，它们将被添加到文档属性中，并显示在应用条码的文档的标题区域中。</span><span class="sxs-lookup"><span data-stu-id="2df0a-174">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="2df0a-175">与标签一样，还可以从文档中手动删除条码。</span><span class="sxs-lookup"><span data-stu-id="2df0a-175">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="2df0a-176">您可以指定在打印或保存项目时是否提示用户包括条码，或者是否应当使用 2010 年发布程序中的"插入"选项卡手动插入Office条码。</span><span class="sxs-lookup"><span data-stu-id="2df0a-176">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="2df0a-177">启用条码</span><span class="sxs-lookup"><span data-stu-id="2df0a-177">To enable barcodes</span></span>
    
||||||<span data-ttu-id="2df0a-178">1.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2df0a-178">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="2df0a-179">**在"编辑策略"页上的"**条码\*\* \> **启用条码"下**。\*\*</span><span class="sxs-lookup"><span data-stu-id="2df0a-179">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="2df0a-180">**2.**</span><span class="sxs-lookup"><span data-stu-id="2df0a-180">**2.**</span></span> <br/> |<span data-ttu-id="2df0a-181">若要提示用户将这些条码插入文档，请选择"提示用户先插入条码，然后再 **保存或打印"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-181">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-182">**3.**</span><span class="sxs-lookup"><span data-stu-id="2df0a-182">**3.**</span></span> <br/> |<span data-ttu-id="2df0a-183">选择 **"** 确定"将条码功能应用于策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-183">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="2df0a-184">条码策略生成 Code 39 标准条形码。</span><span class="sxs-lookup"><span data-stu-id="2df0a-184">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="2df0a-185">每个条形码图像均包括表示条码值的条形码符号下方的文本。</span><span class="sxs-lookup"><span data-stu-id="2df0a-185">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="2df0a-186">这使条形码数据即使在扫描硬件不可用时也可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-186">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="2df0a-187">用户可以在搜索框中手动键入条码，以查找网站上的项目。</span><span class="sxs-lookup"><span data-stu-id="2df0a-187">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="2df0a-188">若要要求受此策略影响的文档具有标签，请选择"启用标签"，然后指定要用于标签的设置。</span><span class="sxs-lookup"><span data-stu-id="2df0a-188">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="2df0a-189">启用标签</span><span class="sxs-lookup"><span data-stu-id="2df0a-189">To enable labels</span></span>
    
||||||<span data-ttu-id="2df0a-190">**1.**</span><span class="sxs-lookup"><span data-stu-id="2df0a-190">**1.**</span></span>|<span data-ttu-id="2df0a-191">\*\*若要要求用户向文档添加标签，请选择"提示用户在保存或打印 **前插入标签"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-191">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="2df0a-192">> [!NOTE]>如果希望标签是可选的，请不要选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="2df0a-192">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="2df0a-193">2.</span><span class="sxs-lookup"><span data-stu-id="2df0a-193">2.</span></span>  <br/> |<span data-ttu-id="2df0a-194">若要锁定标签，以便插入标签后不能更改标签，请选择"添加标签后禁止 **更改标签"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-194">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="2df0a-195">此设置可阻止在将标签插入客户端应用程序（如 Word、Excel 或 PowerPoint）中的项后更新标签文本。</span><span class="sxs-lookup"><span data-stu-id="2df0a-195">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="2df0a-196">如果您想要在更新该文档或项的属性时更新标签，请不要选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="2df0a-196">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-197">3.</span><span class="sxs-lookup"><span data-stu-id="2df0a-197">3.</span></span>  <br/> |<span data-ttu-id="2df0a-198">在"标签格式"框中，输入要显示的标签的文本。</span><span class="sxs-lookup"><span data-stu-id="2df0a-198">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="2df0a-199">标签可包含最多 10 列引用，每个列引用最多 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="2df0a-199">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="2df0a-200">若要为标签创建格式，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2df0a-200">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="2df0a-201">按希望列的显示顺序键入要包括在标签中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="2df0a-201">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="2df0a-202">将列名称放在大括号 () ，如"编辑策略"页上 {} 的示例所示。</span><span class="sxs-lookup"><span data-stu-id="2df0a-202">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="2df0a-203">键入单词以标识方括号之外的列，如"编辑策略"页上的示例所示。</span><span class="sxs-lookup"><span data-stu-id="2df0a-203">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-204">4.</span><span class="sxs-lookup"><span data-stu-id="2df0a-204">4.</span></span>  <br/> |<span data-ttu-id="2df0a-205">若要添加换行符 **，\n** 换行符出现位置。</span><span class="sxs-lookup"><span data-stu-id="2df0a-205">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-206">5.</span><span class="sxs-lookup"><span data-stu-id="2df0a-206">5.</span></span>  <br/> |<span data-ttu-id="2df0a-207">选择您想要的字号和样式，并指定标签位于文档中的左侧、中间还是右侧。</span><span class="sxs-lookup"><span data-stu-id="2df0a-207">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="2df0a-208">选择可以在用户计算机上使用的字体和样式。</span><span class="sxs-lookup"><span data-stu-id="2df0a-208">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="2df0a-209">字体的大小将影响可以在标签上显示的文本的多少。</span><span class="sxs-lookup"><span data-stu-id="2df0a-209">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-210">6.</span><span class="sxs-lookup"><span data-stu-id="2df0a-210">6.</span></span>  <br/> |<span data-ttu-id="2df0a-211">输入标签的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="2df0a-211">Enter the height and width of the label.</span></span> <span data-ttu-id="2df0a-212">标签高度介于 0.25 英寸到 20 英寸之间，标签宽度介于 0.25 英寸到 20 英寸之间。</span><span class="sxs-lookup"><span data-stu-id="2df0a-212">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="2df0a-213">标签文本始终在标签图像内垂直居中。</span><span class="sxs-lookup"><span data-stu-id="2df0a-213">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="2df0a-214">7.</span><span class="sxs-lookup"><span data-stu-id="2df0a-214">7.</span></span>  <br/> |<span data-ttu-id="2df0a-215">选择 **"刷新** "预览标签内容。</span><span class="sxs-lookup"><span data-stu-id="2df0a-215">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="2df0a-216">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-216">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="2df0a-217">为列表、库或文件夹创建策略（基于位置的保留策略）</span><span class="sxs-lookup"><span data-stu-id="2df0a-217">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="2df0a-218"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-218"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="2df0a-219">可以定义仅适用于特定列表、库或文件夹的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-219">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="2df0a-220">但是，如果这样创建保留策略，将无法在其他列表、库、文件夹或网站上重复使用此策略，也无法将网站集策略应用于基于位置的策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-220">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="2df0a-221">如果要将单个保留策略应用于单个位置中所有类型的内容，则最可能希望使用基于位置的保留。</span><span class="sxs-lookup"><span data-stu-id="2df0a-221">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="2df0a-222">在大多数情况下，您需要验证是否针对所有内容类型指定了保留策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-222">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="2df0a-223">每个子文件夹都继承其父级的保留策略，除非你选择中断继承，在子级别定义新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-223">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="2df0a-224">如果要定义除保留列表或库外的信息管理策略，则需要为与该列表或库关联的每个列表内容类型定义信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-224">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="2df0a-225">如果您决定随时从列表或库的内容类型切换到基于位置的策略，则仅保留策略将用作基于位置的策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-225">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="2df0a-226">所有其他管理策略 (审核、条码和条形码) 将继承自关联的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-226">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="2df0a-227">可通过停用"基于库和文件夹的保留"功能为网站集禁用基于位置的策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-227">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="2df0a-228">这使网站集管理员能够确保其内容类型策略不会由列表管理员的基于位置的策略覆盖。</span><span class="sxs-lookup"><span data-stu-id="2df0a-228">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="2df0a-229">至少需要"管理列表"权限才能更改列表或库的信息管理策略设置。</span><span class="sxs-lookup"><span data-stu-id="2df0a-229">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="2df0a-230">导航到要指定信息管理策略的列表或库。</span><span class="sxs-lookup"><span data-stu-id="2df0a-230">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="2df0a-231">在功能区上，选择 **"库**"或"**列表**" \> **选项卡"库设置** 或 **"列表设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-231">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="2df0a-232">在 SharePoint Online 中，**单击**"设置"，然后单击"**列表设置"** 或"库 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-232">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="2df0a-233">在 **"权限和管理** \> **信息管理策略设置"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-233">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![文档库的设置页上的信息管理策略链接](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="2df0a-235">在"信息管理策略设置页上，确保将列表或库的保留源设置为"库和文件夹"。</span><span class="sxs-lookup"><span data-stu-id="2df0a-235">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="2df0a-236">如果 **内容类型** 显示为源，请单击"**更改源**"，然后单击"库 **和文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-236">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="2df0a-237">请注意，内容类型保留策略将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-237">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="2df0a-238">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-238">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="2df0a-239">在"编辑策略"页上的"基于 **库的保留计划**"下，输入所创建策略的简要说明。</span><span class="sxs-lookup"><span data-stu-id="2df0a-239">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="2df0a-240">选择 **"添加保留阶段..."。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-240">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="2df0a-241">请注意，在"记录"下，可以通过选择"定义记录的不同保留阶段"选项来为记录定义不同的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-241">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="2df0a-242">在"阶段属性"对话框中，选择保留期选项以指定文档或项目何时过期。</span><span class="sxs-lookup"><span data-stu-id="2df0a-242">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="2df0a-243">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2df0a-243">Do one of the following:</span></span>
    
  - <span data-ttu-id="2df0a-244">若要基于日期属性设置到期日期，请在"事件 此阶段基于项目的日期属性"下，选择文档或项目操作 (例如，"已创建或修改) "以及此操作后的时间增量 (例如，您希望项目过期的天数、月数或年 \> 数) 。</span><span class="sxs-lookup"><span data-stu-id="2df0a-244">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="2df0a-245">若要使用自定义保留公式确定过期时间，请选择"按 **此服务器上安装的自定义保留公式设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-245">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="2df0a-246">此选项仅在管理员已设置自定义公式时可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-246">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="2df0a-247">在 **"操作**"下，指定您希望在文档或项目过期时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2df0a-247">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="2df0a-248">若要允许对文档或项目执行特定操作 (如删除) ，请从列表中选择一个操作。</span><span class="sxs-lookup"><span data-stu-id="2df0a-248">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="2df0a-249">" **启动工作流"** 选项仅在为已具有与其关联的工作流的列表、库或内容类型定义策略时可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-249">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="2df0a-250">然后，您可以选择工作流。</span><span class="sxs-lookup"><span data-stu-id="2df0a-250">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="2df0a-251">在 **"定期**"下 **，选择"重复此阶段的操作..."。** 并输入希望操作重复出现多久。</span><span class="sxs-lookup"><span data-stu-id="2df0a-251">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="2df0a-252">此选项仅在所选操作可以重复时可用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-252">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="2df0a-253">例如，不能为"永久删除"**操作设置定期。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-253">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="2df0a-254">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-254">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="2df0a-255">将网站集策略应用于内容类型</span><span class="sxs-lookup"><span data-stu-id="2df0a-255">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="2df0a-256"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-256"><a name="__apply_a_site"> </a></span></span>

<span data-ttu-id="2df0a-257">如果已针对您的网站创建了信息管理策略作为网站集策略，您可以将其中一个策略应用于内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-257">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="2df0a-258">通过执行此操作，您可以将同一策略应用于网站集中不共享同一父内容类型的多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-258">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="2df0a-259">如果要将策略应用于网站集中的多个内容类型，并且配置了 Managed Metadata Service，可以使用内容类型发布将信息管理策略发布到多个网站集。</span><span class="sxs-lookup"><span data-stu-id="2df0a-259">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="2df0a-260">有关详细信息， [请参阅跨网站集应用](#apply-a-policy-across-site-collections) 策略一节。</span><span class="sxs-lookup"><span data-stu-id="2df0a-260">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="2df0a-261">导航到包含要应用策略的内容类型的列表或库。</span><span class="sxs-lookup"><span data-stu-id="2df0a-261">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="2df0a-262">在功能区上，选择 **"库**"或"**列表**" \> **选项卡"库设置** 或 **"列表设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-262">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="2df0a-263">在 SharePoint Online 中，**单击**"设置"，然后单击"**列表设置"** 或"库 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-263">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="2df0a-264">在 **"权限和管理** \> **信息管理策略设置"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-264">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![文档库的设置页上的信息管理策略链接](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="2df0a-266">验证策略源是否设置为"**内容** 类型"，在"内容类型策略"下，选择要应用策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-266">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="2df0a-267">在 **"指定策略** \> **使用网站集策略"** 下，从列表中选择要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-267">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="2df0a-268">如果 **"使用网站集策略** "选项不可用，则没有为网站集定义任何网站集策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-268">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="2df0a-269">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2df0a-269">Choose **OK**.</span></span>
    
     <span data-ttu-id="2df0a-270">如果您处理的列表或库支持管理多个内容类型，您可以在"内容类型"下选择要指定信息管理策略的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-270">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="2df0a-271">这将直接进入上述步骤 5。</span><span class="sxs-lookup"><span data-stu-id="2df0a-271">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="2df0a-272">跨网站集应用策略</span><span class="sxs-lookup"><span data-stu-id="2df0a-272">Apply a policy across site collections</span></span>
<span data-ttu-id="2df0a-273"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-273"><a name="__toc260646789"> </a></span></span>

<span data-ttu-id="2df0a-274">通过使用 Managed Metadata Service 应用程序设置内容类型发布，跨网站集共享内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-274">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="2df0a-275">内容类型发布可帮助您跨网站一致地管理内容和元数据，因为可以集中创建和更新内容类型，并且可以将更新发布到多个订阅网站集或 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2df0a-275">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="2df0a-276">从现有策略创建模板以跨网站集使用</span><span class="sxs-lookup"><span data-stu-id="2df0a-276">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="2df0a-277"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-277"><a name="__toc262125409"> </a></span></span>

<span data-ttu-id="2df0a-278">您可以定义信息管理策略，然后根据策略创建模板，以根据需要在多个网站集之间使用。</span><span class="sxs-lookup"><span data-stu-id="2df0a-278">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="2df0a-279">如果希望备份信息策略，可以使用此方法，也可以用作使用内容类型发布跨网站集应用一个策略的替代方法。</span><span class="sxs-lookup"><span data-stu-id="2df0a-279">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="2df0a-280">通过从一个网站集导出策略，然后将该策略导入到保存的位置或另一个网站集，可以创建策略的模板或备份。</span><span class="sxs-lookup"><span data-stu-id="2df0a-280">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="2df0a-281">如果使用导出/导入功能作为创建一组策略模板的方法，请记住策略模板文件中存在唯一.xml标识符。</span><span class="sxs-lookup"><span data-stu-id="2df0a-281">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="2df0a-282">因此，如果不更改此唯一标识符，将无法多次将策略导入站点。</span><span class="sxs-lookup"><span data-stu-id="2df0a-282">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="2df0a-283">导出策略</span><span class="sxs-lookup"><span data-stu-id="2df0a-283">Export a policy</span></span>
<span data-ttu-id="2df0a-284"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-284"><a name="__toc260646790"> </a></span></span>

1. <span data-ttu-id="2df0a-285">在网站集主页上，选择"设置"设置"小齿轮"，以 ![ 设置"网站 ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-285">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="2df0a-286">在连接到SharePoint的网站中，单击"设置"，**再** 单击"网站内容"，然后单击"网站 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-286">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="2df0a-287">在"网站设置页上的"网站 **集管理** \> **内容类型策略模板"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-287">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
!["网站集"页上的"内容类型策略设置链接](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="2df0a-289">选择要导出的策略滚动到底部 \> "导出 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-289">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="2df0a-290">在提示保存或打开文件时，选择"保存"，然后选择文件保存到的位置。 </span><span class="sxs-lookup"><span data-stu-id="2df0a-290">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="2df0a-291">请务必选择一个可供导入策略的网站集使用的位置。</span><span class="sxs-lookup"><span data-stu-id="2df0a-291">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="2df0a-292">当显示"下载完成"对话框时，选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-292">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="2df0a-293">将策略导入到其他网站集</span><span class="sxs-lookup"><span data-stu-id="2df0a-293">Import a policy to a different site collection</span></span>
<span data-ttu-id="2df0a-294"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0a-294"><a name="__toc260646791"> </a></span></span>

<span data-ttu-id="2df0a-295">导入信息管理策略使您能够在任何给定网站集中的网站或列表级别将信息管理策略应用于多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-295">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="2df0a-296">这样做的好处有两个方面：无需重新定义和应用每个内容类型的策略，并且只需在一个地方更改策略，就可以更轻松地管理策略修改。</span><span class="sxs-lookup"><span data-stu-id="2df0a-296">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="2df0a-297">在要应用策略的网站集的主页上，选择"设置 小设置齿轮"，以 ![ 设置"站点 ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> 设置"。</span><span class="sxs-lookup"><span data-stu-id="2df0a-297">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="2df0a-298">在连接到SharePoint的网站中，单击"设置"，**再** 单击"网站内容"，然后单击"网站 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-298">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="2df0a-299">在"网站设置页上的"网站 **集管理** \> **内容类型策略模板"下**。</span><span class="sxs-lookup"><span data-stu-id="2df0a-299">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="2df0a-300">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span><span class="sxs-lookup"><span data-stu-id="2df0a-300">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="2df0a-301">选择已保存策略的 XML 文件"打开 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="2df0a-301">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="2df0a-302">在"导入网站集策略"页上 \> **，导入** 以将策略添加到网站集。</span><span class="sxs-lookup"><span data-stu-id="2df0a-302">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="2df0a-303">现在可以将导入的策略应用于站点或列表级别的一个或多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-303">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="2df0a-304">信息管理策略使组织能够控制内容的保留时间，审核用户对内容执行哪些操作，以及向文档添加条码或标签。</span><span class="sxs-lookup"><span data-stu-id="2df0a-304">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="2df0a-305">策略可帮助强制执行法律和政府法规或内部业务流程的合规性。</span><span class="sxs-lookup"><span data-stu-id="2df0a-305">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="2df0a-306">作为管理员，您可以设置一个策略来控制如何跟踪文档以及文档的保留时间。</span><span class="sxs-lookup"><span data-stu-id="2df0a-306">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="2df0a-307">可以在网站层次结构中的三个不同位置（从最广泛到最窄）创建信息管理策略：</span><span class="sxs-lookup"><span data-stu-id="2df0a-307">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="2df0a-308">创建一个策略以用于网站集中的多个内容类型。</span><span class="sxs-lookup"><span data-stu-id="2df0a-308">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="2df0a-309">为网站内容类型创建策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-309">Create a policy for a site content type.</span></span>
- <span data-ttu-id="2df0a-310">为列表或库创建策略。</span><span class="sxs-lookup"><span data-stu-id="2df0a-310">Create a policy for a list or library.</span></span>

<span data-ttu-id="2df0a-311">有关详细信息，请参阅 [信息管理策略简介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2df0a-311">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

