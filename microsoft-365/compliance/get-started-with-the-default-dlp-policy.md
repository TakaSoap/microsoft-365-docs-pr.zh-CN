---
title: 开始使用默认 DLP 策略
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用此报告在 DLP 策略中优化组织 (数据丢失) 防护。
ms.openlocfilehash: 0e63648f78fd5adf2b0a354fa1a26abae4561ba8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200481"
---
# <a name="get-started-with-the-default-dlp-policy"></a>开始使用默认 DLP 策略

在通过 DLP 策略创建第一 (数据丢失防护) ，DLP 会使用默认策略帮助保护敏感信息。 此默认策略及其建议 (如下所示) 当包含信用卡号的电子邮件或文档与组织外部人员共享时通知您，以帮助保护敏感内容的安全。 你将在安全与合规中心 **主页** 上看到 &amp; 此建议。 
  
您可以使用此小组件快速查看共享敏感信息的共享时间及内容，然后只需单击一次或两次即可优化默认 DLP 策略。 您还可以随时编辑默认 DLP 策略，因为它可完全自定义。 请注意，如果一开始看不到建议，请尝试在"建议你"部分底部单击 **"+更多**"。 
  
![名为"进一步保护共享内容"的小部件。](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>查看报告并优化默认 DLP 策略

当小组件显示用户与组织外部人员共享敏感信息时，选择底部的"优化 **DLP** 策略"。 
  
详细报告显示过去 30 天内共享包含信用卡号的内容的时间和数量。 请注意，规则匹配最多可能需要 48 小时才能显示在小部件中。
  
为了帮助保护敏感信息，默认 DLP 策略：
  
- 检测何时将Exchange、SharePoint和OneDrive信用卡号的内容与组织外部人员共享。
    
- 显示策略提示，当用户尝试与组织外部人员共享此敏感信息时，会向用户发送电子邮件通知。 有关这些选项的详细信息，请参阅发送电子邮件 [通知和显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)。
    
- 生成详细的活动报告，以便你可以跟踪与组织外部人员共享内容的人以及他们何时共享内容等内容。 您可以使用 DLP [](view-the-dlp-reports.md)报告和审核日志 [数据](search-the-audit-log-in-security-and-compliance.md) (**活动**  =  **DLP**) 查看此信息。
    
若要快速优化默认 DLP 策略，可以选择具有：
  
- 当用户与组织外部人员共享此敏感信息时，向您发送事件报告电子邮件。
    
- 将其他用户添加到电子邮件事件报告。
    
- 阻止访问包含敏感信息的内容，但允许用户替代和共享或发送（如果需要）。
    
有关事件报告或限制访问权的信息，请参阅 [数据丢失防护参考](data-loss-prevention-policies.md)。
  
如果您想稍后更改这些选项，您随时都可以编辑默认 DLP 策略 ，请参阅下一节。
  
![设置"进一步保护共享内容"的小部件。](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>编辑默认 DLP 策略

此策略名为 **"默认 DLP 策略**"，显示在安全与合规中心的"策略"页上的"数据丢失 &amp; 防护"下。 
  
此策略完全可自定义，与从头开始创建的任何 DLP 策略相同。 您还可以关闭或删除策略，以便用户不再收到策略提示或电子邮件通知。
  
![名为"默认 DLP 策略"的 DLP 策略。](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>小组件何时显示和不显示

名为"**进一步保护共享内容"的** 小部件显示在安全与合规中心主页的"推荐使用 &amp; "部分。 
  
此小组件仅在：
  
- 安全与合规中心或管理中心内没有数据丢失 &amp; Exchange策略。 此小组件旨在帮助您开始使用 DLP，因此如果您已经拥有 DLP 策略，它不会出现。
    
- 在过去 30 天内，包含至少一张信用卡的内容已与组织外部的某人共享。
    
请注意，规则匹配可能需要 48 小时才能对小组件可用，因此在检测到外部共享的敏感信息后，可能需要最多两天时间才能显示建议。
  
最后，使用小部件优化默认 DLP 策略后，小部件将从主页 **中** 消失。 
  

