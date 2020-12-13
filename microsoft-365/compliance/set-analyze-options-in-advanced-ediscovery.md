---
title: 设置高级电子数据展示中的分析选项
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 查看为高级电子数据展示中的分析过程设置选项的步骤，包括近重复项、电子邮件线程和主题。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663497"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="8dd2e-103">设置高级电子数据展示和经典 (分析) </span><span class="sxs-lookup"><span data-stu-id="8dd2e-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="8dd2e-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8dd2e-106">在高级电子数据展示中，在运行分析之前设置分析选项。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="8dd2e-107">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="8dd2e-107">Set Analyze options</span></span>

<span data-ttu-id="8dd2e-108">打开 **"准备 \> 分析** \> **设置"。**</span><span class="sxs-lookup"><span data-stu-id="8dd2e-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="8dd2e-109">将显示以下窗口。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-109">The following window is displayed.</span></span>
  
![设置分析选项](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="8dd2e-111">**近重复项和电子邮件线程** 如果要运行分析，请选中此框。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="8dd2e-112">默认情况下选中此选项。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="8dd2e-113">**文档相似性** 输入近重复阈值或接受默认值 65%。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="8dd2e-114">**主题** 选中此框可处理所有文件并为其分配主题。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-114">**Themes** Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="8dd2e-115">默认情况下，此复选框未选中。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-115">By default, this check box is not selected.</span></span> <span data-ttu-id="8dd2e-116">如果要执行主题处理，请输入以下选项。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="8dd2e-117">**最大主题数** 输入或选择要创建的主题数的值。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-117">**Max number of themes** Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="8dd2e-118">默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8dd2e-119">增加主题数量会影响性能以及主题的一般化能力。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="8dd2e-120">主题数量越高，主题越精细。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="8dd2e-121">例如，如果一组 50 个主题包含主题，如"Basketball、Clipps、Clippers、Lakers";300 个主题可能包含单独的主题："小马"、"Clippers"、"Lakers"。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="8dd2e-122">如果你对主题"Basketball"没有了解，并且对 ECA 使用此功能，则看到主题"Basketball"可能很有用。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="8dd2e-123">但是，如果处理主题过多，你可能永远不会看到单词"Basketball"，并且可能不知道"小球"和"Clippers"是需要审阅的优秀"篮球"主题，而不是启动和用于发的项目。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="8dd2e-124">**建议的主题** 你可以建议主题词来控制主题处理。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="8dd2e-125">高级电子数据展示将侧重于这些建议词语，并尝试基于"主题最大数量"设置创建一个或多个相关主题。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="8dd2e-126">例如，如果建议的单词是"computer"，并且你指定"2"作为"最大主题数"，则高级电子数据展示将尝试生成与单词"computer"相关的两个主题。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="8dd2e-127">例如，这两个主题可能是"计算机软件"和"计算机硬件"。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![添加建议的主题](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="8dd2e-129">若要查看、添加或编辑建议的主题，请单击"修改 **"。**</span><span class="sxs-lookup"><span data-stu-id="8dd2e-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="8dd2e-130">在 **"建议的主题"** 面板中，单击 **"添加** ![ " ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 图标以添加主题。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="8dd2e-131">在 **"添加建议的主题** "面板中，添加用逗号分隔的单词。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="8dd2e-132">在 **"** 主题数量"中，选择一个值以确定高级电子数据展示将尝试为这些字词生成的主题数， (默认值为 1 个主题) 。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="8dd2e-133">单击 **"** 保存"，然后关闭对话。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8dd2e-134">主题总数包括建议主题。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="8dd2e-135">建议主题总数不能超过主题总数。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="8dd2e-136">如果有许多与总主题相关的建议主题，系统将仅检测到几个"新"主题，因为大多数主题将专用于"建议主题"。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="8dd2e-137">**模式** 从下拉列表中，选择" **主题"** 选项：</span><span class="sxs-lookup"><span data-stu-id="8dd2e-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="8dd2e-138">**创建和应用模型**：按一段文件按模型计算主题，然后分发其中的文件。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="8dd2e-139">**创建模型**：从文件段计算主题模型。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="8dd2e-140">划分文件的"应用"过程在另一个时间单独完成。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="8dd2e-141">**应用模型**：此选项仅在之前创建且尚未应用模型时显示。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="8dd2e-142">这将基于主题划分文件。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="8dd2e-143">还可以设置[忽略文本，](set-ignore-text-in-advanced-ediscovery.md)[并设置分析高级设置以](set-analyze-advanced-settings-in-advanced-ediscovery.md)进行分析。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="8dd2e-144">设置这些选项后，单击" **分析"** 以运行。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="8dd2e-145">[显示"查看](view-analyze-results-in-advanced-ediscovery.md) 分析结果"。</span><span class="sxs-lookup"><span data-stu-id="8dd2e-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="8dd2e-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="8dd2e-146">Related topics</span></span>

[<span data-ttu-id="8dd2e-147">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="8dd2e-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8dd2e-148">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="8dd2e-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8dd2e-149">设置忽略文本 </span><span class="sxs-lookup"><span data-stu-id="8dd2e-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8dd2e-150">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="8dd2e-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8dd2e-151">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="8dd2e-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

