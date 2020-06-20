---
title: 导入 PST 文件时筛选数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: 了解如何在将 PST 文件导入到 Office 365 时使用 Office 365 导入服务中的智能导入功能筛选数据。
ms.openlocfilehash: d511c1277104a27076116fafcb4b71bc851baaca
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817721"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="ce494-103">导入 PST 文件时筛选数据</span><span class="sxs-lookup"><span data-stu-id="ce494-103">Filter data when importing PST files</span></span>

<span data-ttu-id="ce494-104">使用 Office 365 导入服务中的新智能导入功能可筛选实际导入到目标邮箱的 PST 文件中的项目。</span><span class="sxs-lookup"><span data-stu-id="ce494-104">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="ce494-105">以下是相应的工作方式：</span><span class="sxs-lookup"><span data-stu-id="ce494-105">Here's how it works:</span></span>
  
- <span data-ttu-id="ce494-106">在创建并提交 PST 导入作业之后，PST 文件将上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="ce494-106">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="ce494-107">Microsoft 365 通过识别邮箱项目的期限和 PST 文件中包含的不同邮件类型，以安全和安全的方式分析 PST 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="ce494-107">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="ce494-108">分析完成并准备导入数据后，您可以选择按如下方式导入 PST 文件中的所有数据，或通过设置筛选器来裁剪导入的数据，以控制导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ce494-108">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="ce494-109">例如，您可以选择执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ce494-109">For example, you can choose to:</span></span>
    
  - <span data-ttu-id="ce494-110">仅导入特定期限的项目。</span><span class="sxs-lookup"><span data-stu-id="ce494-110">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="ce494-111">导入所选的邮件类型。</span><span class="sxs-lookup"><span data-stu-id="ce494-111">Import selected message types.</span></span>
    
  - <span data-ttu-id="ce494-112">排除特定人员发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="ce494-112">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="ce494-113">配置筛选器设置后，Microsoft 365 仅将满足筛选条件的数据导入到导入作业中指定的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="ce494-113">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="ce494-114">下图显示了智能导入过程，并突出显示了您执行的任务以及 Office 365 执行的任务。</span><span class="sxs-lookup"><span data-stu-id="ce494-114">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 中的智能导入过程](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a><span data-ttu-id="ce494-116">创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="ce494-116">Create a PST import job</span></span>

- <span data-ttu-id="ce494-117">本主题中的步骤假定您已使用网络上传或驱动器传送在 Office 365 导入服务中创建了 PST 导入作业。</span><span class="sxs-lookup"><span data-stu-id="ce494-117">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="ce494-118">有关分步说明，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="ce494-118">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="ce494-119">使用网络上载将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ce494-119">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="ce494-120">使用驱动器传送将 PST 文件导入 Office 365</span><span class="sxs-lookup"><span data-stu-id="ce494-120">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="ce494-121">在使用网络上载创建导入作业之后，安全 & 合规中心中的 "导入" 页上的导入作业的状态设置为 "**正在进行分析**"，这意味着 Microsoft 365 正在分析您上载的 PST 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="ce494-121">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="ce494-122">单击 "**刷新** ![ 刷新" ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 以更新导入作业的状态。</span><span class="sxs-lookup"><span data-stu-id="ce494-122">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="ce494-123">对于驱动器运输导入作业，microsoft 365 在 Microsoft 数据中心人员收到您的硬盘并将 PST 文件上传到您的组织的 Azure 存储区域后，数据将由 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="ce494-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="ce494-124">筛选导入到邮箱的数据</span><span class="sxs-lookup"><span data-stu-id="ce494-124">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="ce494-125">创建 PST 导入作业后，请按照以下步骤在将数据导入到 Office 365 之前对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ce494-125">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="ce494-126">转到 [https://protection.office.com/](https://protection.office.com/)，然后使用你组织中的管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="ce494-126">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your organization.</span></span> 
    
2. <span data-ttu-id="ce494-127">单击 "**信息调控** \> **导入**" " \> **导入 PST 文件**"。</span><span class="sxs-lookup"><span data-stu-id="ce494-127">Click **Information governance** \> **Import** \> **Import PST files**.</span></span>
    
    <span data-ttu-id="ce494-128">您的组织的导入作业列在 "**导入 PST 文件**" 页上。</span><span class="sxs-lookup"><span data-stu-id="ce494-128">The import jobs for your organization are listed on the **Import PST files** page.</span></span> <span data-ttu-id="ce494-129">请注意，"**状态**" 列中的 "**分析完成**" 值指示已由 Microsoft 365 分析并可供您导入的导入作业。</span><span class="sxs-lookup"><span data-stu-id="ce494-129">Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span> 
    
    ![分析完成状态指示 Microsoft 365 已分析 PST 文件中的数据](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="ce494-131">对于要完成的导入作业，单击 "已**准备好导入到 Office 365** "。</span><span class="sxs-lookup"><span data-stu-id="ce494-131">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="ce494-132">系统将显示一个浮出页面，其中包含有关 PST 文件的信息和有关导入作业的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ce494-132">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="ce494-133">单击 "**导入到 Office 365**"。</span><span class="sxs-lookup"><span data-stu-id="ce494-133">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="ce494-134">系统将显示“**筛选数据**”页面。</span><span class="sxs-lookup"><span data-stu-id="ce494-134">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="ce494-135">它包含有关导入作业的 PST 文件中的数据的数据见解，包括有关数据期限的信息。</span><span class="sxs-lookup"><span data-stu-id="ce494-135">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    !["筛选数据" 页面显示导入作业的 PST 文件的数据见解](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="ce494-137">根据是否要修整导入到 Microsoft 365 的数据，在 "**是否要筛选数据？**" 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ce494-137">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="ce494-138">a.</span><span class="sxs-lookup"><span data-stu-id="ce494-138">a.</span></span> <span data-ttu-id="ce494-139">单击 **"是，我想在导入之前对其进行筛选**" 以修整您导入的数据，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ce494-139">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="ce494-140">"将**数据导入到 Office 365 页面**" 页面将显示，其中包含来自 Microsoft 365 执行的分析的详细数据见解。</span><span class="sxs-lookup"><span data-stu-id="ce494-140">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
    
    ![Microsoft 365 显示来自其 PST 文件分析的详细数据见解](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="ce494-142">此页面上的图显示了将导入的数据量。</span><span class="sxs-lookup"><span data-stu-id="ce494-142">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="ce494-143">有关在 PST 文件中找到的每种邮件类型的信息将显示在图形中。</span><span class="sxs-lookup"><span data-stu-id="ce494-143">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="ce494-144">您可以将光标悬停在每个条上，以显示有关该邮件类型的特定信息。</span><span class="sxs-lookup"><span data-stu-id="ce494-144">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="ce494-145">还有一个下拉列表，其中包含不同的年龄值，基于 PST 文件的分析。</span><span class="sxs-lookup"><span data-stu-id="ce494-145">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="ce494-146">当您在下拉列表中选择某个年龄时，会更新图形以显示所选年龄将导入的数据量。</span><span class="sxs-lookup"><span data-stu-id="ce494-146">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="ce494-147">b.</span><span class="sxs-lookup"><span data-stu-id="ce494-147">b.</span></span> <span data-ttu-id="ce494-148">若要配置添加筛选器以减少导入的数据量，请单击 "**更多筛选选项**"。</span><span class="sxs-lookup"><span data-stu-id="ce494-148">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![配置 "更多选项" 页上的筛选器以裁切导入的数据](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="ce494-150">您可以配置以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="ce494-150">You can configure these filters:</span></span>
    
      - <span data-ttu-id="ce494-151">**年龄**-选择年龄，以便只导入比指定年龄更高的项目。</span><span class="sxs-lookup"><span data-stu-id="ce494-151">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="ce494-152">有关 Microsoft 365 如何确定**年龄**筛选器的年龄桶的说明，请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="ce494-152">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="ce494-153">**类型**-此部分显示在导入作业的 PST 文件中找到的所有邮件类型。</span><span class="sxs-lookup"><span data-stu-id="ce494-153">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="ce494-154">您可以取消选中要排除的邮件类型旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="ce494-154">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="ce494-155">请注意，不能排除其他邮件类型。</span><span class="sxs-lookup"><span data-stu-id="ce494-155">Note that you can't exclude the Other message type.</span></span> <span data-ttu-id="ce494-156">有关其他类别中包含的邮箱项目列表，请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="ce494-156">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="ce494-157">**用户**-您可以排除特定人员发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="ce494-157">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="ce494-158">若要排除出现在 "发件人：" 字段、"收件人：" 字段或邮件的 "抄送：" 字段中的人员，请单击该收件人类型旁边的 "**排除用户**"。</span><span class="sxs-lookup"><span data-stu-id="ce494-158">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="ce494-159">键入人员的电子邮件地址（SMTP 地址），单击 "**添加** ![ 新图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) " 以将其添加到该收件人类型的 "已排除的用户" 列表中，然后单击 "**保存**" 以保存排除的用户列表。</span><span class="sxs-lookup"><span data-stu-id="ce494-159">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="ce494-160">Microsoft 365 不显示通过设置**人员**筛选器得到的数据见解。</span><span class="sxs-lookup"><span data-stu-id="ce494-160">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="ce494-161">但是，如果您设置此筛选器以排除特定人员发送或接收的邮件，则在实际导入过程中将排除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="ce494-161">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="ce494-162">c.</span><span class="sxs-lookup"><span data-stu-id="ce494-162">c.</span></span> <span data-ttu-id="ce494-163">单击 "**更多筛选选项**" 飞出页面中的 "**应用**" 以保存筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="ce494-163">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="ce494-164">"将**数据导入到 Office 365** " 页面将根据您的筛选器设置进行更新，其中包括将根据筛选器设置导入的总数据量。</span><span class="sxs-lookup"><span data-stu-id="ce494-164">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="ce494-165">请注意，还会显示筛选器设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="ce494-165">Note that a summary of the filter settings is also shown.</span></span> <span data-ttu-id="ce494-166">您可以单击筛选器旁边的 "**编辑**" 以更改设置（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="ce494-166">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![数据洞察力根据您的筛选器设置进行更新](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="ce494-168">d.</span><span class="sxs-lookup"><span data-stu-id="ce494-168">d.</span></span> <span data-ttu-id="ce494-169">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ce494-169">Click **Next**.</span></span>
    
    <span data-ttu-id="ce494-170">将显示 "状态" 页，其中显示了筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="ce494-170">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="ce494-171">同样，您可以编辑任何筛选设置。</span><span class="sxs-lookup"><span data-stu-id="ce494-171">Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="ce494-172">e.</span><span class="sxs-lookup"><span data-stu-id="ce494-172">e.</span></span> <span data-ttu-id="ce494-173">单击 "**导入数据**" 以启动导入。</span><span class="sxs-lookup"><span data-stu-id="ce494-173">Click **Import data** to start the import .</span></span> <span data-ttu-id="ce494-174">请注意，将显示将导入的总数据量。</span><span class="sxs-lookup"><span data-stu-id="ce494-174">Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="ce494-175">或</span><span class="sxs-lookup"><span data-stu-id="ce494-175">Or</span></span>
    
    <span data-ttu-id="ce494-176">a.</span><span class="sxs-lookup"><span data-stu-id="ce494-176">a.</span></span> <span data-ttu-id="ce494-177">单击 "**否，我想要导**入所有文件以将 PST 文件中的所有数据导入 Office 365"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ce494-177">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="ce494-178">b.</span><span class="sxs-lookup"><span data-stu-id="ce494-178">b.</span></span> <span data-ttu-id="ce494-179">在 "将**数据导入到 Office 365** " 页上，单击 "**导入数据**" 以启动导入。</span><span class="sxs-lookup"><span data-stu-id="ce494-179">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="ce494-180">请注意，将显示将导入的总数据量。</span><span class="sxs-lookup"><span data-stu-id="ce494-180">Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="ce494-181">在 "**导入 PST 文件**" 页上，单击 "**刷新** ![ 刷新" ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 。</span><span class="sxs-lookup"><span data-stu-id="ce494-181">On the **Import PST files** page, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="ce494-182">导入作业的状态将显示在 "**状态**" 列中。</span><span class="sxs-lookup"><span data-stu-id="ce494-182">The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="ce494-183">单击 "导入作业" 以显示更多详细信息，如每个 PST 文件的状态和您配置的筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="ce494-183">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="ce494-184">更多信息</span><span class="sxs-lookup"><span data-stu-id="ce494-184">More information</span></span>

- <span data-ttu-id="ce494-185">Microsoft 365 如何确定年龄筛选器的增量？</span><span class="sxs-lookup"><span data-stu-id="ce494-185">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="ce494-186">当 Microsoft 365 分析 PST 文件时，它会查看每个项目的已发送或接收时间戳（如果某个项目同时具有已发送和已接收的时间戳，则选择了最早的日期）。</span><span class="sxs-lookup"><span data-stu-id="ce494-186">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="ce494-187">然后，Microsoft 365 查看该时间戳的年份值，并将其与当前日期进行比较以确定项目的年龄。</span><span class="sxs-lookup"><span data-stu-id="ce494-187">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="ce494-188">然后，将这些年龄用作**年龄**筛选器的下拉列表中的值。</span><span class="sxs-lookup"><span data-stu-id="ce494-188">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="ce494-189">例如，如果 PST 文件包含来自2016、2015和2014的邮件，则**年龄**筛选器中的值将为**1 年**、 **2 年**和**3 年**。</span><span class="sxs-lookup"><span data-stu-id="ce494-189">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="ce494-190">下表列出了 "**更多选项**" 飞出页面（请参阅上一过程中的步骤5b）**的 "** **其他**" 类别中包含的邮件类型。</span><span class="sxs-lookup"><span data-stu-id="ce494-190">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="ce494-191">当前，在将 Pst 导入到 Office 365 时，不能排除 "其他" 类别中的项目。</span><span class="sxs-lookup"><span data-stu-id="ce494-191">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="ce494-192">**邮件类标识符**</span><span class="sxs-lookup"><span data-stu-id="ce494-192">**Message class ID**</span></span>|<span data-ttu-id="ce494-193">**使用此邮件类别的邮箱项目**</span><span class="sxs-lookup"><span data-stu-id="ce494-193">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ce494-194">IPM.NOTE.活动</span><span class="sxs-lookup"><span data-stu-id="ce494-194">IPM.Activity</span></span>  <br/> |<span data-ttu-id="ce494-195">“日记”条目</span><span class="sxs-lookup"><span data-stu-id="ce494-195">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="ce494-196">IPM.Document</span><span class="sxs-lookup"><span data-stu-id="ce494-196">IPM.Document</span></span>  <br/> |<span data-ttu-id="ce494-197">文档和文件（未附加到电子邮件）</span><span class="sxs-lookup"><span data-stu-id="ce494-197">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="ce494-198">IPM.NOTE.文本文件</span><span class="sxs-lookup"><span data-stu-id="ce494-198">IPM.File</span></span>  <br/> |<span data-ttu-id="ce494-199">（与 IPM.Document）相同</span><span class="sxs-lookup"><span data-stu-id="ce494-199">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="ce494-200">IPM.NOTE.注意： IMC. 通知</span><span class="sxs-lookup"><span data-stu-id="ce494-200">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="ce494-201">由 Internet 邮件连接发送的报告，即 Exchange Server 到 Internet 的网关</span><span class="sxs-lookup"><span data-stu-id="ce494-201">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="ce494-202">IPM.NOTE.注意： Microsoft. Fax</span><span class="sxs-lookup"><span data-stu-id="ce494-202">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="ce494-203">传真邮件</span><span class="sxs-lookup"><span data-stu-id="ce494-203">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="ce494-204">IPM.NOTE.注意： "Rules。</span><span class="sxs-lookup"><span data-stu-id="ce494-204">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="ce494-205">外出自动答复邮件</span><span class="sxs-lookup"><span data-stu-id="ce494-205">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="ce494-206">IPM.NOTE.注意： ReplyTemplate</span><span class="sxs-lookup"><span data-stu-id="ce494-206">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="ce494-207">收件箱规则发送的答复</span><span class="sxs-lookup"><span data-stu-id="ce494-207">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="ce494-208">IPM.NOTE.OLE.静态类</span><span class="sxs-lookup"><span data-stu-id="ce494-208">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="ce494-209">定期系列的例外</span><span class="sxs-lookup"><span data-stu-id="ce494-209">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="ce494-210">IPM.NOTE.撤回。报告</span><span class="sxs-lookup"><span data-stu-id="ce494-210">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="ce494-211">邮件撤回报告</span><span class="sxs-lookup"><span data-stu-id="ce494-211">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="ce494-212">IPM.NOTE.远端</span><span class="sxs-lookup"><span data-stu-id="ce494-212">IPM.Remote</span></span>  <br/> |<span data-ttu-id="ce494-213">远程邮件</span><span class="sxs-lookup"><span data-stu-id="ce494-213">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="ce494-214">IPM.NOTE.完工</span><span class="sxs-lookup"><span data-stu-id="ce494-214">IPM.Report</span></span>  <br/> |<span data-ttu-id="ce494-215">项目状态报告</span><span class="sxs-lookup"><span data-stu-id="ce494-215">Item status reports</span></span>  <br/> |
