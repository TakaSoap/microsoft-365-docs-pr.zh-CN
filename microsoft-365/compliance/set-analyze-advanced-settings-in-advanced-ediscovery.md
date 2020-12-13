---
title: 设置"分析高级电子数据展示"中的高级设置
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 了解如何为高级电子数据展示中的分析过程配置高级设置，包括近重复项、电子邮件线程和主题。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac1300eb26338691722d9ccd15269ccf7f964f58
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663487"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="7e90c-103">设置"分析高级电子数据展示"中的高级设置</span><span class="sxs-lookup"><span data-stu-id="7e90c-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="7e90c-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="7e90c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7e90c-106">高级电子数据展示提供分析模块设置的默认高级参数。</span><span class="sxs-lookup"><span data-stu-id="7e90c-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="7e90c-107">以下过程介绍可指定的设置。</span><span class="sxs-lookup"><span data-stu-id="7e90c-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="7e90c-108">在 **"准备 \> 分析 \> 安装程序** "选项卡中 **， (** 页面底部的"高级设置") 。</span><span class="sxs-lookup"><span data-stu-id="7e90c-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="7e90c-109">将显示以下面板。</span><span class="sxs-lookup"><span data-stu-id="7e90c-109">The following panel is displayed.</span></span> 
    
    ![设置分析高级设置](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="7e90c-111">在 **"近重复项"和"电子邮件线程"** 参数中，如有必要，选择以下值：</span><span class="sxs-lookup"><span data-stu-id="7e90c-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="7e90c-112">**最少字** 数：单词的最小数目，低于此数字时不提交文件进行近重复分析。</span><span class="sxs-lookup"><span data-stu-id="7e90c-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="7e90c-113">**最大字** 数：最大字数，超过此数目时不提交文件进行近重复分析。</span><span class="sxs-lookup"><span data-stu-id="7e90c-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="7e90c-114">**电子邮件相似** 性：两封电子邮件的相似性最低级别。</span><span class="sxs-lookup"><span data-stu-id="7e90c-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="7e90c-115">值始终等于或大于文档相似性。</span><span class="sxs-lookup"><span data-stu-id="7e90c-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="7e90c-116">默认值为 90%。</span><span class="sxs-lookup"><span data-stu-id="7e90c-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="7e90c-117">在 **"主题"参数** 中，选中"在主题分析中包括数字"复选框以在"分析"期间处理主题时包括数字。</span><span class="sxs-lookup"><span data-stu-id="7e90c-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="7e90c-118">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7e90c-118">Click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="7e90c-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e90c-119">Related topics</span></span>

[<span data-ttu-id="7e90c-120">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="7e90c-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7e90c-121">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="7e90c-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e90c-122">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="7e90c-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e90c-123">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="7e90c-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7e90c-124">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="7e90c-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

