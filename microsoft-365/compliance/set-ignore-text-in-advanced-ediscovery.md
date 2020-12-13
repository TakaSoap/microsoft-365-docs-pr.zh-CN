---
title: 设置"忽略文本"选项以在高级电子数据展示中分析
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 了解如何定义在高级电子数据展示中使用分析和处理模块时忽略特定文本的规则。
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663467"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a><span data-ttu-id="4123b-103">设置"忽略文本"选项以在高级电子数据展示和经典 (分析) </span><span class="sxs-lookup"><span data-stu-id="4123b-103">Set Ignore Text option for Analyze in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="4123b-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="4123b-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="4123b-106">忽略文本功能可应用于以下所有或任一高级电子数据展示模块：分析 (近重复项、电子邮件线程、主题) 和相关性。</span><span class="sxs-lookup"><span data-stu-id="4123b-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="4123b-107">忽略的文本将不会显示在相关性中显示的文件中，并且分析/计算将丢弃忽略的文本。</span><span class="sxs-lookup"><span data-stu-id="4123b-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="4123b-108">如果以前为已经运行的模块定义了"忽略文本"功能，则"忽略文本"设置现在将受到保护，不会进行修改。</span><span class="sxs-lookup"><span data-stu-id="4123b-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="4123b-109">但是，相关性模块的"忽略文本"功能仍可随时更改。</span><span class="sxs-lookup"><span data-stu-id="4123b-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="4123b-110">如何应用忽略文本筛选器</span><span class="sxs-lookup"><span data-stu-id="4123b-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="4123b-111">将按输入的顺序应用多个忽略文本筛选器。</span><span class="sxs-lookup"><span data-stu-id="4123b-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="4123b-112">若要更改应用的顺序，必须删除它们，然后按所需顺序重新输入它们。</span><span class="sxs-lookup"><span data-stu-id="4123b-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="4123b-113">例如，如果文本内容为"DAVE BOB ALICE ALICE ALICE 一文"，则下面是"忽略文本"条目的示例以及这些条目产生的结果：</span><span class="sxs-lookup"><span data-stu-id="4123b-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results these entries produce:</span></span>

|<span data-ttu-id="4123b-114">**忽略文本条目**</span><span class="sxs-lookup"><span data-stu-id="4123b-114">**Ignore Text entries**</span></span> <br/> |<span data-ttu-id="4123b-115">**结果**</span><span class="sxs-lookup"><span data-stu-id="4123b-115">**Results**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="4123b-116">"ALICE"、"BOB</span><span class="sxs-lookup"><span data-stu-id="4123b-116">"ALICE", "BOB CAROL"</span></span>  <br/> |<span data-ttu-id="4123b-117">"DAVE 一文"</span><span class="sxs-lookup"><span data-stu-id="4123b-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="4123b-118">"ALICE"、"BOB ALICE ALICE"</span><span class="sxs-lookup"><span data-stu-id="4123b-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |<span data-ttu-id="4123b-119">"DAVE BOB 一级 2013</span><span class="sxs-lookup"><span data-stu-id="4123b-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="4123b-120">第二个"忽略文本"条目未实现，因为在应用了第一个"忽略文本"后找不到该字符串。</span><span class="sxs-lookup"><span data-stu-id="4123b-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="4123b-121">定义忽略文本时使用正则表达式</span><span class="sxs-lookup"><span data-stu-id="4123b-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="4123b-122">正则表达式支持在定义忽略文本时使用。</span><span class="sxs-lookup"><span data-stu-id="4123b-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="4123b-123">以下是正则表达式语法和用法的示例：</span><span class="sxs-lookup"><span data-stu-id="4123b-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="4123b-124">若要删除 (忽略) 从 Begin 到行末尾的文本：</span><span class="sxs-lookup"><span data-stu-id="4123b-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="4123b-125">其中"Begin"是行中此字符串的初始匹配项。</span><span class="sxs-lookup"><span data-stu-id="4123b-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="4123b-126">例如，对于以下文本：</span><span class="sxs-lookup"><span data-stu-id="4123b-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="4123b-127">**"这是第一句和第一行**</span><span class="sxs-lookup"><span data-stu-id="4123b-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="4123b-128">**这是第二句和第二行"**</span><span class="sxs-lookup"><span data-stu-id="4123b-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="4123b-129">正则表达式第一 (。 \*) $ 将导致：</span><span class="sxs-lookup"><span data-stu-id="4123b-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="4123b-130">**"This is**</span><span class="sxs-lookup"><span data-stu-id="4123b-130">**"This is**</span></span>
    
    <span data-ttu-id="4123b-131">**这是第二句和第二行"**</span><span class="sxs-lookup"><span data-stu-id="4123b-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="4123b-132">若要删除自动插入到电子邮件线索末尾的免责声明和法律声明，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4123b-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="4123b-133">其中，"Begin"和"End"是环绕文本段落的开头和结尾的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="4123b-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="4123b-134">例如，以下正则表达式将删除在电子邮件线程中"开始"和"结束"字符串之间的免责声明和法律声明：</span><span class="sxs-lookup"><span data-stu-id="4123b-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="4123b-135">**此邮件包含机密信息 (。|\s) \* 如果需要验证，请请求硬拷贝版本**</span><span class="sxs-lookup"><span data-stu-id="4123b-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="4123b-136">若要删除包含 (字符的免责声明) ：</span><span class="sxs-lookup"><span data-stu-id="4123b-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="4123b-137">例如，对于以下文本 (x's) ：</span><span class="sxs-lookup"><span data-stu-id="4123b-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="4123b-138">**/\*\ 此消息包含机密信息。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="4123b-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="4123b-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="4123b-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="4123b-140">\**xxxx xxxx 如果需要验证，请请求硬复制版本。/\*\**</span><span class="sxs-lookup"><span data-stu-id="4123b-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="4123b-141">用于删除上述免责声明的正则表达式应为：</span><span class="sxs-lookup"><span data-stu-id="4123b-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="4123b-142">**\/\\*\\此邮件包含机密信息 \. (。|\s) \* 如果需要验证，请请求硬拷贝版本 \.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="4123b-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="4123b-143">正则表达式规则：</span><span class="sxs-lookup"><span data-stu-id="4123b-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="4123b-144">除空格之外，不是字母表中的任何字符都必须 () 、"_"和"-"前面必须有" \" 。</span><span class="sxs-lookup"><span data-stu-id="4123b-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="4123b-145">常规 eExpression 字段的长度可以不受限制。</span><span class="sxs-lookup"><span data-stu-id="4123b-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="4123b-146">有关正则表达式的说明和详细语法，请参阅： [正则表达式语言 - 快速参考](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4123b-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="4123b-147">定义忽略文本规则</span><span class="sxs-lookup"><span data-stu-id="4123b-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="4123b-148">在 **"管理 \> 分析 \> 分析选项** "选项卡的"忽略 **文本** "部分，单击 **+** 图标以添加规则。</span><span class="sxs-lookup"><span data-stu-id="4123b-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="4123b-149">在 **"添加忽略文本** "对话框中的 **"** 名称"字段中，键入"忽略文本"规则的名称。</span><span class="sxs-lookup"><span data-stu-id="4123b-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![添加忽略的文本](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="4123b-151">在 **文本框** 中，键入要忽略的文本。</span><span class="sxs-lookup"><span data-stu-id="4123b-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="4123b-152">文本字段允许无限数量的字符。</span><span class="sxs-lookup"><span data-stu-id="4123b-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4123b-153">如上面的窗口所示，单击 **灯以** 查看忽略文本规则的常见语法准则。</span><span class="sxs-lookup"><span data-stu-id="4123b-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="4123b-154">如果需要 **，请** 选中"区分大小写"复选框。</span><span class="sxs-lookup"><span data-stu-id="4123b-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="4123b-155">在 **"应用于"** 列表中，选择要应用定义的高级电子数据展示模块。</span><span class="sxs-lookup"><span data-stu-id="4123b-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="4123b-156">如果希望对示例文本运行测试，请在"输入"文本框中键入示例文本，然后单击"**测试"。**</span><span class="sxs-lookup"><span data-stu-id="4123b-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="4123b-157">结果显示在"输出 **"** 文本框中。</span><span class="sxs-lookup"><span data-stu-id="4123b-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="4123b-158">单击 **"确定** "保存"忽略文本"规则。</span><span class="sxs-lookup"><span data-stu-id="4123b-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="4123b-159">将显示定义的"忽略文本"规则。</span><span class="sxs-lookup"><span data-stu-id="4123b-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![设置被忽略的文本名称](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="4123b-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4123b-161">See also</span></span>

[<span data-ttu-id="4123b-162">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="4123b-162">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4123b-163">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="4123b-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4123b-164">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="4123b-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4123b-165">设置 分析高级设置</span><span class="sxs-lookup"><span data-stu-id="4123b-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4123b-166">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="4123b-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

