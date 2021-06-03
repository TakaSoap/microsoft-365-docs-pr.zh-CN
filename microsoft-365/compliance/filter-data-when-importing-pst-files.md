---
title: 导入 PST 文件时筛选数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: 了解如何在将 PST 文件导入到 Microsoft 365 时，使用 Microsoft 365 导入服务中的智能导入功能筛选Microsoft 365。
ms.openlocfilehash: fc89467e3ea9c0af86ec6b9ef6a9d7d61079e116
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730566"
---
# <a name="filter-data-when-importing-pst-files"></a><span data-ttu-id="6e194-103">导入 PST 文件时筛选数据</span><span class="sxs-lookup"><span data-stu-id="6e194-103">Filter data when importing PST files</span></span>

<span data-ttu-id="6e194-104">使用 Microsoft 365 导入服务中的新智能导入功能筛选 PST 文件中实际导入到目标邮箱的项目。</span><span class="sxs-lookup"><span data-stu-id="6e194-104">Use the new Intelligent Import feature in the Microsoft 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="6e194-105">以下是相应的工作方式：</span><span class="sxs-lookup"><span data-stu-id="6e194-105">Here's how it works:</span></span>
  
- <span data-ttu-id="6e194-106">创建并提交 PST 导入作业后，PST 文件将上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="6e194-106">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
- <span data-ttu-id="6e194-107">Microsoft 365通过标识邮箱项目的年龄以及 PST 文件中包含的不同邮件类型，以安全的方式分析 PST 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="6e194-107">Microsoft 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
  
- <span data-ttu-id="6e194-108">分析完成且数据已准备好导入时，您可以选择按此方式导入 PST 文件内的所有数据，或者通过设置控制导入哪些数据的筛选器来修整导入的数据。</span><span class="sxs-lookup"><span data-stu-id="6e194-108">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="6e194-109">例如，可以选择：</span><span class="sxs-lookup"><span data-stu-id="6e194-109">For example, you can choose to:</span></span>
  
  - <span data-ttu-id="6e194-110">仅导入特定年龄的项目。</span><span class="sxs-lookup"><span data-stu-id="6e194-110">Import only items of a certain age.</span></span>
  
  - <span data-ttu-id="6e194-111">导入所选邮件类型。</span><span class="sxs-lookup"><span data-stu-id="6e194-111">Import selected message types.</span></span>
  
  - <span data-ttu-id="6e194-112">排除特定人员发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="6e194-112">Exclude messages sent or received by specific people.</span></span>
  
- <span data-ttu-id="6e194-113">配置筛选器设置后，Microsoft 365导入作业中指定的目标邮箱中仅导入符合筛选条件的数据。</span><span class="sxs-lookup"><span data-stu-id="6e194-113">After you configure the filter settings, Microsoft 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
  
<span data-ttu-id="6e194-114">下图显示了智能导入过程，并突出显示了您执行的任务和由 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6e194-114">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![智能导入过程中Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a><span data-ttu-id="6e194-116">创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="6e194-116">Create a PST import job</span></span>

- <span data-ttu-id="6e194-117">本主题中的步骤假定你已使用网络上载或驱动器寄送在 Office 365 导入服务中创建 PST 导入作业。</span><span class="sxs-lookup"><span data-stu-id="6e194-117">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="6e194-118">有关分步说明，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="6e194-118">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="6e194-119">使用网络上载将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="6e194-119">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="6e194-120">使用驱动器传送将 PST 文件导入 Office 365</span><span class="sxs-lookup"><span data-stu-id="6e194-120">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="6e194-121">使用网络上载创建导入作业后，安全 & 合规中心的"导入"页上的导入作业的状态将设置为"正在分析"，这意味着 Microsoft 365正在分析您上载的 PST 文件的数据。</span><span class="sxs-lookup"><span data-stu-id="6e194-121">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Microsoft 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="6e194-122">单击 **"** ![ 刷新 ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 刷新"以更新导入作业的状态。</span><span class="sxs-lookup"><span data-stu-id="6e194-122">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="6e194-123">对于驱动器寄送导入作业，Microsoft 数据中心工作人员Microsoft 365硬盘驱动器，将 PST 文件上载到组织的 Azure 存储区域后，系统将会分析数据。</span><span class="sxs-lookup"><span data-stu-id="6e194-123">For drive shipping import jobs, the data will be analyzed by Microsoft 365 after Microsoft datacenter personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="6e194-124">筛选导入到邮箱的数据</span><span class="sxs-lookup"><span data-stu-id="6e194-124">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="6e194-125">创建 PST 导入作业后，请按照以下步骤筛选数据，然后再将数据导入Office 365。</span><span class="sxs-lookup"><span data-stu-id="6e194-125">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="6e194-126">转到 <https://compliance.microsoft.com>，然后使用你组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="6e194-126">Go to <https://compliance.microsoft.com> and sign in using the credentials for an administrator account in your organization.</span></span>
    
2. <span data-ttu-id="6e194-127">在 Microsoft 365 合规中心的侧左窗格中，单击“**信息治理**”\>“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="6e194-127">In the left pane of the Microsoft 365 compliance center, click **Information governance** \> **Import**.</span></span>
    
    <span data-ttu-id="6e194-128">组织的导入作业列在"导入"**选项卡** 上。The **Analysis completed** value in the **Status** column indicates the import jobs that have been analysis by Microsoft 365 and are ready for you to import.</span><span class="sxs-lookup"><span data-stu-id="6e194-128">The import jobs for your organization are listed on the **Import** tab. The **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Microsoft 365 and are ready for you to import.</span></span>
    
    ![分析完成状态Microsoft 365 PST 文件中已分析数据](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="6e194-130">选择要完成的导入作业，然后单击"导入 **到Office 365"。**</span><span class="sxs-lookup"><span data-stu-id="6e194-130">Select the import job that you want to complete and click **Import to Office 365**.</span></span>
  
    <span data-ttu-id="6e194-131">系统将显示一个浮出页面，其中包含有关 PST 文件的信息和有关导入作业的其他信息。</span><span class="sxs-lookup"><span data-stu-id="6e194-131">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>

4. <span data-ttu-id="6e194-132">单击 **导入以Office 365。**</span><span class="sxs-lookup"><span data-stu-id="6e194-132">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="6e194-133">系统将显示“**筛选数据**”页面。</span><span class="sxs-lookup"><span data-stu-id="6e194-133">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="6e194-134">它包含有关导入作业的 PST 文件中数据的数据见解，包括有关数据年龄的信息。</span><span class="sxs-lookup"><span data-stu-id="6e194-134">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    !["筛选数据"页显示导入作业的 PST 文件的数据见解](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="6e194-136">根据是否要剪裁导入到数据Microsoft 365，在"是否要筛选数据 **？"** 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6e194-136">Based on whether or not you want to trim the data that's imported to Microsoft 365, under **Do you want to filter your data?**, do one of the following:</span></span>
  
    <span data-ttu-id="6e194-137">a.</span><span class="sxs-lookup"><span data-stu-id="6e194-137">a.</span></span> <span data-ttu-id="6e194-138">单击 **"是，我希望在导入** 之前进行筛选以修整导入的数据"，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="6e194-138">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
  
    <span data-ttu-id="6e194-139">"**将数据导入Office 365"** 页将显示，并包含来自所执行分析Microsoft 365数据见解。</span><span class="sxs-lookup"><span data-stu-id="6e194-139">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Microsoft 365 performed.</span></span> 
  
    ![Microsoft 365 PST 文件分析中显示详细的数据见解](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="6e194-141">此页面上的图形显示将导入的数据量。</span><span class="sxs-lookup"><span data-stu-id="6e194-141">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="6e194-142">有关在 PST 文件中找到的每封邮件类型的信息将显示在图中。</span><span class="sxs-lookup"><span data-stu-id="6e194-142">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="6e194-143">您可以将光标悬停在每个栏上，以显示有关该消息类型的特定信息。</span><span class="sxs-lookup"><span data-stu-id="6e194-143">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="6e194-144">根据 PST 文件分析，还有一个包含不同年龄值的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6e194-144">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="6e194-145">当你在下拉列表中选择一个年龄时，图形将更新以显示所选年龄将导入多少数据。</span><span class="sxs-lookup"><span data-stu-id="6e194-145">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
  
    <span data-ttu-id="6e194-146">b.</span><span class="sxs-lookup"><span data-stu-id="6e194-146">b.</span></span> <span data-ttu-id="6e194-147">若要配置添加筛选器以减少导入的数据量，请单击"更多筛选 **选项"。**</span><span class="sxs-lookup"><span data-stu-id="6e194-147">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
  
    ![配置"更多选项"页上的筛选器以修整导入的数据](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="6e194-149">可以配置以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="6e194-149">You can configure these filters:</span></span>
  
      - <span data-ttu-id="6e194-150">**Age** - 选择一个年数，以便仅导入比指定年龄更新的项目。</span><span class="sxs-lookup"><span data-stu-id="6e194-150">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="6e194-151">请参阅 [详细信息部分](#more-information)，了解有关如何确定Microsoft 365年龄筛选器的年龄 **存储桶的说明**。</span><span class="sxs-lookup"><span data-stu-id="6e194-151">See the [More information](#more-information) section for a description about how Microsoft 365 determines the age buckets for the **Age** filter.</span></span> 
  
      - <span data-ttu-id="6e194-152">**类型** - 此部分显示在导入作业的 PST 文件中找到的所有邮件类型。</span><span class="sxs-lookup"><span data-stu-id="6e194-152">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="6e194-153">可以取消选中要排除的邮件类型旁边的框。</span><span class="sxs-lookup"><span data-stu-id="6e194-153">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="6e194-154">不能排除其他邮件类型。</span><span class="sxs-lookup"><span data-stu-id="6e194-154">You can't exclude the Other message type.</span></span> <span data-ttu-id="6e194-155">有关 [其他类别](#more-information) 中包含的邮箱项目列表，请参阅详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="6e194-155">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span>
  
      - <span data-ttu-id="6e194-156">**用户** - 可以排除特定人员发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="6e194-156">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="6e194-157">若要排除出现在"发件人："字段、"收件人："字段或邮件的"抄送："字段中的用户，请单击该 **收件人类型** 旁边的"排除用户"。</span><span class="sxs-lookup"><span data-stu-id="6e194-157">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="6e194-158">键入 (SMTP 地址) 电子邮件地址，单击"添加新图标"以将其添加到该收件人类型的已排除用户列表中，然后单击"保存"以保存已排除用户 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 的列表。</span><span class="sxs-lookup"><span data-stu-id="6e194-158">Type the email address (SMTP address) of the person, click **Add**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
  
        > [!NOTE]
        > <span data-ttu-id="6e194-159">Microsoft 365显示通过设置人员筛选器获得 **的数据** 见解。</span><span class="sxs-lookup"><span data-stu-id="6e194-159">Microsoft 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="6e194-160">但是，如果设置此筛选器以排除特定人员发送或接收的邮件，则在实际导入过程中将排除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="6e194-160">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="6e194-161">c.</span><span class="sxs-lookup"><span data-stu-id="6e194-161">c.</span></span> <span data-ttu-id="6e194-162">单击 **"** 更多筛选 **选项** "飞出页面中的"应用"以保存筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="6e194-162">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
  
    <span data-ttu-id="6e194-163">"将数据导入到Office 365"页上的数据见解将基于筛选器设置进行更新，包括将基于筛选器设置导入的数据总量。</span><span class="sxs-lookup"><span data-stu-id="6e194-163">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="6e194-164">还会显示筛选器设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="6e194-164">A summary of the filter settings is also shown.</span></span> <span data-ttu-id="6e194-165">可以单击 **筛选器** 旁边的"编辑"以在必要时更改设置。</span><span class="sxs-lookup"><span data-stu-id="6e194-165">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
  
    ![数据见解将基于筛选器设置进行更新](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="6e194-167">d.</span><span class="sxs-lookup"><span data-stu-id="6e194-167">d.</span></span> <span data-ttu-id="6e194-168">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6e194-168">Click **Next**.</span></span>
  
    <span data-ttu-id="6e194-169">将显示一个状态页，其中显示筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="6e194-169">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="6e194-170">同样，您可以编辑任何筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="6e194-170">Again, you can edit any of the filter settings.</span></span>
  
    <span data-ttu-id="6e194-171">e.</span><span class="sxs-lookup"><span data-stu-id="6e194-171">e.</span></span> <span data-ttu-id="6e194-172">单击 **"导入数据** "开始导入。</span><span class="sxs-lookup"><span data-stu-id="6e194-172">Click **Import data** to start the import.</span></span> <span data-ttu-id="6e194-173">将显示将导入的数据总量。</span><span class="sxs-lookup"><span data-stu-id="6e194-173">The total amount of data that will be imported is displayed.</span></span> 
  
    <span data-ttu-id="6e194-174">或</span><span class="sxs-lookup"><span data-stu-id="6e194-174">Or</span></span>
  
    <span data-ttu-id="6e194-175">a.</span><span class="sxs-lookup"><span data-stu-id="6e194-175">a.</span></span> <span data-ttu-id="6e194-176">单击 **"否，我希望导入所有内容** 以将 PST 文件内的所有数据导入Office 365，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="6e194-176">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
  
    <span data-ttu-id="6e194-177">b.</span><span class="sxs-lookup"><span data-stu-id="6e194-177">b.</span></span> <span data-ttu-id="6e194-178">在"**将数据导入Office 365** 页上，单击 **"导入数据**"以开始导入。</span><span class="sxs-lookup"><span data-stu-id="6e194-178">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="6e194-179">将显示将导入的数据总量。</span><span class="sxs-lookup"><span data-stu-id="6e194-179">The total amount of data that will be imported is displayed.</span></span> 
  
6. <span data-ttu-id="6e194-180">在"导入 **"选项卡** 上，单击" **刷新刷新** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) "。</span><span class="sxs-lookup"><span data-stu-id="6e194-180">On the **Import** tab, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="6e194-181">导入作业的状态显示在"状态 **"** 列中。</span><span class="sxs-lookup"><span data-stu-id="6e194-181">The status for the import job is displayed in the **Status** column.</span></span>
  
7. <span data-ttu-id="6e194-182">单击导入作业可显示更详细的信息，例如每个 PST 文件的状态和配置的筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="6e194-182">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

## <a name="more-information"></a><span data-ttu-id="6e194-183">更多信息</span><span class="sxs-lookup"><span data-stu-id="6e194-183">More information</span></span>

- <span data-ttu-id="6e194-184">如何Microsoft 365年龄筛选器的增量？</span><span class="sxs-lookup"><span data-stu-id="6e194-184">How does Microsoft 365 determine the increments for the age filter?</span></span> <span data-ttu-id="6e194-185">当Microsoft 365 PST 文件时，它会查看每个项目的已发送或已接收时间戳 (如果某个项目同时具有已发送和已接收时间戳，则选择) 。</span><span class="sxs-lookup"><span data-stu-id="6e194-185">When Microsoft 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="6e194-186">然后Microsoft 365该时间戳的年值，并将其与当前日期进行比较以确定项目的年龄。</span><span class="sxs-lookup"><span data-stu-id="6e194-186">Then Microsoft 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="6e194-187">然后，这些年龄将用作"年龄"筛选器的下拉列表 **中的** 值。</span><span class="sxs-lookup"><span data-stu-id="6e194-187">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="6e194-188">例如，如果 PST 文件包含来自 2016、2015 和 2014 的邮件，则 **Age** 筛选器中的值为 **1 年\*\*\*\*、2** 年和 **3 年**。</span><span class="sxs-lookup"><span data-stu-id="6e194-188">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
  
- <span data-ttu-id="6e194-189">下表列出了"更多选项"飞出页面 (请参阅上一过程中的步骤5b中"类型"筛选器中的"其他"类别中包含) 。 </span><span class="sxs-lookup"><span data-stu-id="6e194-189">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="6e194-190">目前，在将 PST 导入到"其他"类别中时，无法排除Office 365。</span><span class="sxs-lookup"><span data-stu-id="6e194-190">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
  
    |<span data-ttu-id="6e194-191">**邮件类标识符**</span><span class="sxs-lookup"><span data-stu-id="6e194-191">**Message class ID**</span></span>|<span data-ttu-id="6e194-192">**使用此邮件类的邮箱项目**</span><span class="sxs-lookup"><span data-stu-id="6e194-192">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6e194-193">IPM。活动</span><span class="sxs-lookup"><span data-stu-id="6e194-193">IPM.Activity</span></span>  <br/> |<span data-ttu-id="6e194-194">“日记”条目</span><span class="sxs-lookup"><span data-stu-id="6e194-194">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="6e194-195">IPM.Document</span><span class="sxs-lookup"><span data-stu-id="6e194-195">IPM.Document</span></span>  <br/> |<span data-ttu-id="6e194-196">未附加到 (电子邮件的文档和) </span><span class="sxs-lookup"><span data-stu-id="6e194-196">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="6e194-197">IPM。文件</span><span class="sxs-lookup"><span data-stu-id="6e194-197">IPM.File</span></span>  <br/> |<span data-ttu-id="6e194-198"> (与IPM.Doc一) </span><span class="sxs-lookup"><span data-stu-id="6e194-198">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="6e194-199">IPM。Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="6e194-199">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="6e194-200">由 Internet 邮件连接发送的报告，Exchange Server Internet 的网关</span><span class="sxs-lookup"><span data-stu-id="6e194-200">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="6e194-201">IPM。Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="6e194-201">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="6e194-202">传真邮件</span><span class="sxs-lookup"><span data-stu-id="6e194-202">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="6e194-203">IPM。Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="6e194-203">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="6e194-204">外出自动修复邮件</span><span class="sxs-lookup"><span data-stu-id="6e194-204">Out-of-office autoreply messages</span></span>  <br/> |
    |<span data-ttu-id="6e194-205">IPM。Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="6e194-205">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="6e194-206">收件箱规则发送的答复</span><span class="sxs-lookup"><span data-stu-id="6e194-206">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="6e194-207">IPM。OLE。类</span><span class="sxs-lookup"><span data-stu-id="6e194-207">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="6e194-208">定期系列的例外</span><span class="sxs-lookup"><span data-stu-id="6e194-208">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="6e194-209">IPM。Recall.Report</span><span class="sxs-lookup"><span data-stu-id="6e194-209">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="6e194-210">邮件撤回报告</span><span class="sxs-lookup"><span data-stu-id="6e194-210">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="6e194-211">IPM。远程</span><span class="sxs-lookup"><span data-stu-id="6e194-211">IPM.Remote</span></span>  <br/> |<span data-ttu-id="6e194-212">远程邮件</span><span class="sxs-lookup"><span data-stu-id="6e194-212">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="6e194-213">IPM。报告</span><span class="sxs-lookup"><span data-stu-id="6e194-213">IPM.Report</span></span>  <br/> |<span data-ttu-id="6e194-214">项目状态报告</span><span class="sxs-lookup"><span data-stu-id="6e194-214">Item status reports</span></span>  <br/> |
