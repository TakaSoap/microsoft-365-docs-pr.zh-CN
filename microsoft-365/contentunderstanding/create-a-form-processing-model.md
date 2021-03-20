---
title: 创建表单处理模型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 在 Microsoft SharePoint Syntex 中创建表单处理模型。
ms.openlocfilehash: d71273e416bf7922627e44d9423eaa8903411689
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905842"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="cbf1f-103">在 Microsoft SharePoint Syntex 中创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="cbf1f-104">使用[AI Builder](/ai-builder/overview) - Microsoft PowerApps 中的一项功能 - SharePoint Syntex 用户可以直接从 SharePoint 文档库中创建[表单处理模型](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-104">Using [AI Builder](/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="cbf1f-105">创建表单处理模型涉及以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbf1f-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="cbf1f-106">步骤 1：创建表单处理模型以创建内容类型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="cbf1f-107">步骤 2：添加和分析示例文件</span><span class="sxs-lookup"><span data-stu-id="cbf1f-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="cbf1f-108">步骤 3：选择表单字段</span><span class="sxs-lookup"><span data-stu-id="cbf1f-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="cbf1f-109">步骤 4：培训并测试你的模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="cbf1f-110">步骤 5：发布模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="cbf1f-111">步骤 6：使用模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="cbf1f-112">要求</span><span class="sxs-lookup"><span data-stu-id="cbf1f-112">Requirements</span></span>

<span data-ttu-id="cbf1f-113">只能在启用了表单处理的 SharePoint 文档库中创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="cbf1f-114">如果已启用表单处理，你可以在文档库中的“**自动化**”菜单下看到 “**AI Buidler**” “**创建表单处理模型**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="cbf1f-115">如果需要在文档库中启用处理，则必须联系你的 SharePoint 管理员。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![创建 AI Builder 模型](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="cbf1f-117">步骤 1：创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="cbf1f-118">创建表单处理模型的第一步是将其命名并创建新内容类型的定义，以及为其创建新的文档库视图。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="cbf1f-119">在文档库中，选择 “**自动化**”菜单，选择 “**AI Builder**”，然后选择“**创建表单处理模型**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![创建模型](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="cbf1f-121">在“**新的表单处理模型**”窗格中，在“**名称**”字段中，键入模型的名称（例如，“*采购订单*”）。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![新的表单处理模型](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="cbf1f-123">创建表单处理模型时，将创建新的 SharePoint 内容类型。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="cbf1f-124">SharePoint 内容类型表示具有共同特征的文档类别，并共享该特定内容的列或元数据属性的集合。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="cbf1f-125">可通过“[内容类型库]()”管理 SharePoint 内容类型。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="cbf1f-126">如果想要将此模型映射到 SharePoint 内容类型库中的现有内容类型以使用其架构，请选择“**高级设置**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="cbf1f-127">你的模型将在文档库中为提取的数据创建一个新视图。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="cbf1f-128">如果不希望其成为默认视图，请取消选择“**将视图设置为默认**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="cbf1f-129">选择 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="cbf1f-130">步骤 2：添加和分析文档</span><span class="sxs-lookup"><span data-stu-id="cbf1f-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="cbf1f-131">创建新的表单处理模型后，浏览器将打开一个新的 PowerApps AI Builder 表单处理模型页面。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="cbf1f-132">在此页面上，你可以添加和分析示例文档。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="cbf1f-133">查找要使用的示例文件时，请参阅[表单处理模型输入文档要求和优化提示](/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="cbf1f-135">选择“**添加文档**”，开始添加已分析的示例文档，以确定可提取的指名值对。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="cbf1f-136">然后，你可以选择“**从本地存储上传**”、“**SharePoint**”，或“**Azure Blob 存储**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="cbf1f-137">至少需要使用五个文件进行培训。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="cbf1f-138">添加文件后，选择“**分析**”，检查所有文件的任何常见信息。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="cbf1f-139">此操作可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-139">This may take several minutes to complete.</span></span></br> 
 
    ![分析文件](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="cbf1f-141">分析文件后，在“**选择想要保存的表单域**”页面上，选择该文件以查看检测到的字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![选择表单字段](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="cbf1f-143">步骤 3：选择表单字段</span><span class="sxs-lookup"><span data-stu-id="cbf1f-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="cbf1f-144">为字段而分析文档后，你现在可以看到找到的字段，并确定要保存的字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="cbf1f-145">保存的字段在模型的文档库视图中显示为列，并显示从每个文档中提取的值。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="cbf1f-146">下一页将显示其中一个示例文件，并突出显示系统自动检测到的所有常见字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![选择字段页](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="cbf1f-148">选择要保存的字段，然后选中该复选框以确认选择。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="cbf1f-149">例如，在“采购订单”模型 中，选择选中“*日期*”、“*PO*” 和 “*总数*”字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="cbf1f-150">请注意，如果选择的话，你也也可以选择重命名字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![选择 PO#](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="cbf1f-152">如果分析未检测到字段，你仍然可以选择添加。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="cbf1f-153">突出显示要提取的信息，然后在名称框中键入所需名称。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="cbf1f-154">然后选中复选框。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-154">Then select the check box.</span></span> <span data-ttu-id="cbf1f-155">请注意，你需要在其余示例文件中确认未检测到的字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="cbf1f-156">选择要保存的字段后，单击“**确认字段**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![选择字段后确认字段](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="cbf1f-158">在“**选择想要保存的表单字段**”页面，它将显示所选的字段数量。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="cbf1f-159">选择 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="cbf1f-160">步骤 4：培训并测试你的模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="cbf1f-161">选择想要保存的字段后，“**模型摘要**”页可用于培训并测试模型。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="cbf1f-162">在“**模型摘要**”页面上，已保存的字段将显示在“**选定字段**”部分。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="cbf1f-163">选择“**培训**”以开始对示例文件进行培训。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="cbf1f-164">请注意，这可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-164">Note that this may take a few minutes to complete.</span></span></br>

     ![选择字段培训](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="cbf1f-166">当你看到“已完成培训”的通知时，请选择“**转到详细信息页面**。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="cbf1f-167">在“**模型详细信息**”页面上，可选择“**快速测试**”来测试模型的工作方式。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="cbf1f-168">这使你可以将文件拖放到页面上，查看是否检测到字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![确认字段](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="cbf1f-170">当你看到“已完成培训”的通知时，请选择“**转到详细信息页面**。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="cbf1f-171">在“**模型详细信息**”页面上，选择“**快速测试**”来测试模型的工作方式。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="cbf1f-172">这使你可以将文件拖放到页面上，查看是否检测到字段。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="cbf1f-173">步骤 5：发布模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="cbf1f-174">如果你对模型的结果感到满意，请选择“**发布**”，使其可供使用。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="cbf1f-175">发布模型后，选择“**使用模型**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="cbf1f-176">这将创建一个可在 SharePoint 文档库中运行的 PowerAutomate 流，它还可以提取已在模型中标识的字段，然后选择“**创建流**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="cbf1f-177">完成后，你将看到一条消息，“**已成功创建流**”。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="cbf1f-178">步骤 6：使用模型</span><span class="sxs-lookup"><span data-stu-id="cbf1f-178">Step 6: Use your model</span></span>

<span data-ttu-id="cbf1f-179">发布模型并创建 PowerAutomate 流后，可在 SharePoint 文档库中使用模型。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="cbf1f-180">发布模型后，选择“**转到 SharePoint**”，以便转到文档库。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="cbf1f-181">在文档库模型视图中，注意看，所选字段现在已显示为列。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![已应用文档库模型](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="cbf1f-183">注意看，**文档** 旁的信息链接提示了表单处理模型已应用于此文档库。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![信息按钮](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="cbf1f-185">将文件上传到文档库。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-185">Upload files to your document library.</span></span> <span data-ttu-id="cbf1f-186">任何被模型识别为其内容类型的文件都会在视图中列出文件，并且在列中显示提取的数据。</span><span class="sxs-lookup"><span data-stu-id="cbf1f-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![完成](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="cbf1f-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbf1f-188">See Also</span></span>
  
[<span data-ttu-id="cbf1f-189">Power Automate 文档</span><span class="sxs-lookup"><span data-stu-id="cbf1f-189">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="cbf1f-190">培训：使用 AI Builder 改善业务绩效</span><span class="sxs-lookup"><span data-stu-id="cbf1f-190">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)