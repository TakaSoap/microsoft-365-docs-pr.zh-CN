---
title: 开始使用默认 DLP 策略
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用此报告来优化 DLP 策略中组织 (数据丢失) 防护。
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114080"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="34496-103">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="34496-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="34496-104">在通过 DLP 策略创建第一 (数据丢失防护) ，DLP 会使用默认策略帮助保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="34496-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="34496-105">此默认策略及其建议 (如下所示) 当包含信用卡号的电子邮件或文档与组织外部人员共享时通知您，以帮助保护敏感内容的安全。</span><span class="sxs-lookup"><span data-stu-id="34496-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="34496-106">你将在安全与合规中心 **主页** 上看到 &amp; 此建议。</span><span class="sxs-lookup"><span data-stu-id="34496-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="34496-107">您可以使用此小组件快速查看共享敏感信息的共享时间及内容，然后只需单击一次或两次即可优化默认 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="34496-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="34496-108">您还可以随时编辑默认 DLP 策略，因为它可完全自定义。</span><span class="sxs-lookup"><span data-stu-id="34496-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="34496-109">请注意，如果一开始看不到建议，请尝试在"建议你"部分底部单击 **"+更多**"。</span><span class="sxs-lookup"><span data-stu-id="34496-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![名为"进一步保护共享内容"的小部件](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="34496-111">查看报告并优化默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="34496-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="34496-112">当小组件显示用户与组织外部人员共享敏感信息时，选择底部的"优化 **DLP** 策略"。</span><span class="sxs-lookup"><span data-stu-id="34496-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="34496-113">详细报告显示过去 30 天内共享包含信用卡号的内容的时间和数量。</span><span class="sxs-lookup"><span data-stu-id="34496-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="34496-114">请注意，规则匹配最多可能需要 48 小时才能显示在小部件中。</span><span class="sxs-lookup"><span data-stu-id="34496-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="34496-115">为了帮助保护敏感信息，默认 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="34496-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="34496-116">检测何时与组织外部人员共享包含至少一个信用卡号的 Exchange、SharePoint 和 OneDrive 中的内容。</span><span class="sxs-lookup"><span data-stu-id="34496-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="34496-117">显示策略提示，当用户尝试与组织外部人员共享此敏感信息时，会向用户发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="34496-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="34496-118">有关这些选项的详细信息，请参阅发送电子邮件 [通知和显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="34496-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="34496-119">生成详细的活动报告，以便你可以跟踪与组织外部人员共享内容的人以及他们何时共享内容等内容。</span><span class="sxs-lookup"><span data-stu-id="34496-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="34496-120">您可以使用 DLP [](view-the-dlp-reports.md)报告和审核日志 [数据](search-the-audit-log-in-security-and-compliance.md) (**活动**  =  **DLP**) 查看此信息。</span><span class="sxs-lookup"><span data-stu-id="34496-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="34496-121">若要快速优化默认 DLP 策略，可以选择具有：</span><span class="sxs-lookup"><span data-stu-id="34496-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="34496-122">当用户与组织外部人员共享此敏感信息时，向您发送事件报告电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34496-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="34496-123">将其他用户添加到电子邮件事件报告。</span><span class="sxs-lookup"><span data-stu-id="34496-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="34496-124">阻止访问包含敏感信息的内容，但允许用户替代和共享或发送（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="34496-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="34496-125">有关事件报告或限制访问权的信息，请参阅 [数据丢失防护参考](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="34496-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="34496-126">如果您想稍后更改这些选项，您随时都可以编辑默认 DLP 策略，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="34496-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![名为"进一步保护共享内容"的小部件的设置](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="34496-128">编辑默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="34496-128">Edit the default DLP policy</span></span>

<span data-ttu-id="34496-129">此策略名为 **"默认 DLP 策略**"，显示在安全与合规中心的"策略"页上的"数据丢失 &amp; 防护"下。</span><span class="sxs-lookup"><span data-stu-id="34496-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="34496-130">此策略完全可自定义，与从头开始创建的任何 DLP 策略相同。</span><span class="sxs-lookup"><span data-stu-id="34496-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="34496-131">您还可以关闭或删除策略，以便用户不再收到策略提示或电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="34496-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名为"默认 DLP 策略"的 DLP 策略](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="34496-133">小组件何时显示和不显示</span><span class="sxs-lookup"><span data-stu-id="34496-133">When the widget does and does not appear</span></span>

<span data-ttu-id="34496-134">名为"**进一步保护共享内容"的** 小部件显示在安全与合规中心主页的"推荐使用 &amp; "部分。</span><span class="sxs-lookup"><span data-stu-id="34496-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="34496-135">此小组件仅在：</span><span class="sxs-lookup"><span data-stu-id="34496-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="34496-136">安全与合规中心或 Exchange 管理中心 &amp; 中没有任何数据丢失防护策略。</span><span class="sxs-lookup"><span data-stu-id="34496-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="34496-137">此小组件旨在帮助您开始使用 DLP，因此如果您已经拥有 DLP 策略，它不会出现。</span><span class="sxs-lookup"><span data-stu-id="34496-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="34496-138">在过去 30 天内，包含至少一张信用卡的内容已与组织外部的某人共享。</span><span class="sxs-lookup"><span data-stu-id="34496-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="34496-139">请注意，规则匹配可能需要 48 小时才能对小组件可用，因此在检测到外部共享的敏感信息后，可能需要最多两天时间才能显示建议。</span><span class="sxs-lookup"><span data-stu-id="34496-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="34496-140">最后，使用小部件优化默认 DLP 策略后，小部件将从主页 **中** 消失。</span><span class="sxs-lookup"><span data-stu-id="34496-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

