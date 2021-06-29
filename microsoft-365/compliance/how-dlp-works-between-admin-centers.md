---
title: DLP 如何与安全与&中心& Exchange中心一起工作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解安全与合规&中的 DLP 如何与 DLP 和邮件流规则 (管理中心) 传输Exchange规则。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177173"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a>DLP 在合规性中心Microsoft 365管理中心Exchange工作

在Microsoft 365中，可以在两个不同的管理中心 (DLP) 策略创建数据丢失防护：
  
- 在 **Microsoft 365** 合规中心 中，可以创建单个 DLP 策略来帮助保护 SharePoint、OneDrive、Exchange、Teams 和现在终结点设备中的内容。 我们建议您在此处创建 DLP 策略。 有关详细信息，请参阅数据丢失 [防护参考](data-loss-prevention-policies.md)。
    
- 在 **Exchange** 管理中心中，您可以创建 DLP 策略以帮助保护仅Exchange。 此策略可以使用Exchange规则 (传输规则) ，因此它具有更多特定于处理电子邮件的选项。 有关详细信息，请参阅管理中心[中的 DLP Exchange DLP。](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
在这些管理中心中创建的 DLP 策略并行工作 - 本主题将介绍如何。
  
![安全与合规中心和管理中心Exchange DLP 页面](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>安全与合规&中的 DLP 如何与管理中心中的 DLP 和Exchange规则一起工作

在安全与合规中心& DLP 策略后，该策略将部署到策略中包含的所有位置。 如果策略包含Exchange Online，则策略会同步到该策略，并且强制执行方式与在管理中心中创建的 DLP 策略Exchange完全相同。 
  
如果在管理中心内创建了 DLP 策略Exchange，这些策略将继续与在安全与合规中心内创建的任何电子邮件策略&一起工作。 但请注意，在管理中心Exchange规则优先。 首先Exchange所有邮件流规则，然后处理来自安全与合规& DLP 规则。
  
这意味着：
  
- 邮件流规则Exchange阻止的邮件不会由安全与合规中心中创建的 DLP &扫描。

- DLP 不会扫描在 DLP 之前Exchange邮件流规则或其他任何筛选器隔离的邮件
    
- 如果 Exchange 邮件流规则修改邮件的方式会导致邮件与安全 & 合规中心中的 DLP 策略匹配（如添加外部用户），则 DLP 规则将检测此情况并根据需要强制执行该策略。
    
另请注意Exchange"停止处理"操作的邮件流规则不会影响安全与合规中心内 DLP &的处理，仍将进行处理。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>安全与合规中心&策略提示Exchange中心

策略提示既可以与在 Exchange 管理中心中创建的 DLP 策略和邮件流规则一起使用，也可以与在安全与合规中心创建的 DLP &一起使用，但不能同时使用。 这是因为这些策略存储在不同位置，但策略提示只能从单个位置绘制。
  
如果在 Exchange 管理中心中配置了策略提示，在 Outlook 网页版 和 Outlook 2013 及更高版本中关闭 Exchange 管理中心中的提示之前，在安全 & 合规中心配置的任何策略提示将不会向用户显示。 这可确保当前Exchange邮件流规则继续工作，直到您选择切换到安全与合规&中心。
  
请注意，虽然策略提示只能从单个位置进行绘制，但始终会发送电子邮件通知，即使您同时在安全与合规中心和 Exchange 管理中心内使用 & DLP 策略。
