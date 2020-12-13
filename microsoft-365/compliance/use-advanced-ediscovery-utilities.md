---
title: 使用高级电子数据展示实用工具
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 了解高级电子数据展示中的实用工具，包括案例日志、清除数据、处理错误、修改相关性和透明度分析。
ms.openlocfilehash: 745b81609d73ec88525c3348cc4d582c7d5d7b30
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663291"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a><span data-ttu-id="3ab7a-103">使用高级电子数据展示（经典）实用工具</span><span class="sxs-lookup"><span data-stu-id="3ab7a-103">Use Advanced eDiscovery (classic) utilities</span></span>

> [!NOTE]
> <span data-ttu-id="3ab7a-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="3ab7a-106">在高级电子数据展示中显示和可用的实用程序取决于上下文和用户角色。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="3ab7a-107">案例日志</span><span class="sxs-lookup"><span data-stu-id="3ab7a-107">Case log</span></span>

<span data-ttu-id="3ab7a-108">案例日志提供了应用程序处理活动的详细列表，可用于跟踪、疑难解答和解决错误和警告。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="3ab7a-109">日志可以在主机或服务器上本地生成和存储，也可以直接发送到电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="3ab7a-110">也可以日志文件客户端的计算机下载该证书。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="3ab7a-111">客户端下载选项可能会根据配置和用户角色启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="3ab7a-112">在菜单栏中，单击 **Cogwheel** 图标。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="3ab7a-113">在 **"设置和实用程序 \> 实用程序"** 选项卡中，**选择"案例日志 \> 设置"。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="3ab7a-114">选择 **日志级别** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ab7a-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="3ab7a-115">**标准**：包括基本日志数据。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="3ab7a-116">此选项通常是监视所必需的，除非另有建议，否则应使用此选项。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="3ab7a-117">**最小**：用于非常大的情况，并且仅返回最新数据。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="3ab7a-118">单击 **"运行案例日志"。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-118">Click **Run Case log**.</span></span> <span data-ttu-id="3ab7a-119">将生成日志并显示路径。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="3ab7a-120">当前和最后一个任务的任务进度信息显示在任务状态窗格中。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="3ab7a-121">清除数据</span><span class="sxs-lookup"><span data-stu-id="3ab7a-121">Clear data</span></span>

<span data-ttu-id="3ab7a-122">如果需要删除或重新初始化案例数据，则必须初始化数据库实例。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="3ab7a-123">Clear 数据实用程序从案例数据库、文本文件、案例文件夹和累积结果中删除所有指定的条目。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="3ab7a-124">该函数只能由管理员执行。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3ab7a-125">此操作不可反转，并且将清除专家执行的所有相关性标记和分析。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="3ab7a-126">如有必要，保存数据备份。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="3ab7a-127">请谨慎使用此选项。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-127">Use this option with extreme care.</span></span> <span data-ttu-id="3ab7a-128">删除标记和排名文件可能会影响相关性结果。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="3ab7a-129">在菜单栏中，单击 **Cogwheel** 图标。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="3ab7a-130">在 **"设置和实用程序 \> 实用程序"** 选项卡中，选择 **"清除数据 \> 设置"。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="3ab7a-131">为要初始化的信息选择一个选项：</span><span class="sxs-lookup"><span data-stu-id="3ab7a-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="3ab7a-132">**相关性**：删除相关性中完成的所有工作，包括负载定义和要加载的文件关联。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="3ab7a-133">它将删除所有示例和标记。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="3ab7a-134">**近重复项和电子邮件线程**：删除近重复项和电子邮件线程的所有分析信息。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="3ab7a-135">**主题**：删除与主题相关的数据。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="3ab7a-136">**导出历史记录**：删除导出批处理的历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="3ab7a-137">单击 **"清除数据"。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-137">Click **Clear data**.</span></span> <span data-ttu-id="3ab7a-138">将清除案例数据。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-138">The case data is cleared.</span></span> <span data-ttu-id="3ab7a-139">当前和最后一个任务的任务进度信息显示在 **任务状态窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="3ab7a-140">修改相关性</span><span class="sxs-lookup"><span data-stu-id="3ab7a-140">Modify Relevance</span></span>

<span data-ttu-id="3ab7a-141">本节介绍如何跳过或回滚相关性示例。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="3ab7a-142">在菜单栏中，单击 **Cogwheel** 图标。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="3ab7a-143">在 **"设置和实用程序 \> 实用程序"** 选项卡中，选择 **"修改相关性"。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="3ab7a-144">从选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="3ab7a-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="3ab7a-145">**跳过当前示例 - 对于当前** 用户： This will tag， as **Skip**， all untagged files in the open case sample of the user running the utility.</span><span class="sxs-lookup"><span data-stu-id="3ab7a-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="3ab7a-146">不会对标记为 Skip 的文件执行相关性 **处理**。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="3ab7a-147">**跳过当前示例 - 所有打开的示例**：这会将所有用户的所有打开示例中的所有未标记文件标记为 **Skip。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="3ab7a-148">如果用户当前正在标记示例，则不建议使用此选项。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="3ab7a-149">**回滚最后一个示例**：将回滚上一个完成的相关性培训示例，而不管该示例是在"计算"过程之前还是之后。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="3ab7a-150">不允许回滚捕获示例。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="3ab7a-151">单击 **"执行** "运行。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="3ab7a-152">透明度分析</span><span class="sxs-lookup"><span data-stu-id="3ab7a-152">Transparency analysis</span></span>

<span data-ttu-id="3ab7a-153">透明度分析实用工具可详细查看文件及其分配的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="3ab7a-154">该报告可以用作一种有效性检查，或比较由人工审阅者定义的文件与高级电子数据展示分配的相关性。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="3ab7a-155">除了相关性分数之外，高级电子数据展示还计算并分配考虑关键字上下文的关键字权重。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="3ab7a-156">根据上下文和位置，可以给文件中相同的单词分配不同的权重。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="3ab7a-157">每个关键字都使用从黄色到深橙色以及不同的灰色底纹的颜色强度比例进行标记。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="3ab7a-158">颜色编码用于直观地指示字词对相关性分数的相对正或负贡献。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="3ab7a-159">在多问题案例场景中，可以针对每个问题生成透明度分析报告。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="3ab7a-160">在菜单栏中，单击 **Cogwheel** 图标。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="3ab7a-161">在 **"设置和实用程序 \> 实用程序"** 选项卡中，选择 **"透明度分析设置 \> "。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="3ab7a-162">在\*\* 文件 ID \*\*中，输入要处理的文件的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="3ab7a-163">在 **"问题** "列表中，选择相关问题。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="3ab7a-164">单击 **"透明度分析"。**</span><span class="sxs-lookup"><span data-stu-id="3ab7a-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="3ab7a-165">完成后，将显示文件的透明度分析报告，其中显示标记的关键字颜色与总体相关性分数的关联情况。</span><span class="sxs-lookup"><span data-stu-id="3ab7a-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3ab7a-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ab7a-166">See also</span></span>

[<span data-ttu-id="3ab7a-167">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="3ab7a-167">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3ab7a-168">定义案例和租户设置</span><span class="sxs-lookup"><span data-stu-id="3ab7a-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

