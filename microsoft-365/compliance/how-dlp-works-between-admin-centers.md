---
title: DLP 如何与 Exchange 管理&安全&中心一起工作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
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
description: 了解安全与合规&中的 DLP 如何与 DLP 和邮件流规则 (Exchange 管理) 传输规则一起运行。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905934"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>DLP 在安全与合规中心和 Exchange 管理中心中之间的工作原理

在 Office 365 中，可以在两个不同的管理中心 (DLP) 策略创建数据丢失防护：
  
- 在安全 **&** 合规中心，你可以创建单个 DLP 策略来帮助保护 SharePoint、OneDrive、Exchange 和现在 Microsoft Teams 中的内容。 如果可能，我们建议你在此处创建 DLP 策略。 有关详细信息，请参阅[安全与合规中心& DLP。](data-loss-prevention-policies.md)
    
- 在 **Exchange 管理中心** 中，您可以创建 DLP 策略来帮助保护 Exchange 中的内容。 此策略可以使用 Exchange 邮件流规则 (也称为传输规则) ，因此它具有更多特定于处理电子邮件的选项。 有关详细信息，请参阅[Exchange 管理中心中的 DLP。](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
在这些管理中心中创建的 DLP 策略并行工作 - 本主题将介绍如何。
  
![安全与合规中心和 Exchange 管理中心中的 DLP 页面](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>安全与合规中心& DLP 如何与 Exchange 管理中心中的 DLP 和邮件流规则一起工作

在安全与合规中心& DLP 策略后，该策略将部署到策略中包含的所有位置。 如果策略包含 Exchange Online，则策略会同步到 Exchange Online，并且强制执行方式与在 Exchange 管理中心创建的 DLP 策略完全相同。 
  
如果在 Exchange 管理中心创建了 DLP 策略，这些策略将继续与在安全与合规中心内创建的任何电子邮件策略&一起工作。 但请注意，在 Exchange 管理中心中创建的规则优先。 首先处理所有 Exchange 邮件流规则，然后处理来自安全与合规& DLP 规则。
  
这意味着：
  
- Exchange 邮件流规则阻止的邮件将不会由安全与合规中心中创建的 DLP &扫描。
    
- 如果 Exchange 邮件流规则修改邮件的方式导致邮件与安全 & 合规中心中的 DLP 策略匹配（如添加外部用户）则 DLP 规则将检测此情况并根据需要强制执行该策略。
    
另请注意，使用"停止处理"操作的 Exchange 邮件流规则不会影响安全与合规中心内 DLP &处理，仍将进行处理。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>安全与合规&与 Exchange 管理中心中的策略提示

策略提示既可以与在 Exchange 管理中心创建的 DLP 策略和邮件流规则一起使用，也可以与在安全与合规中心创建的 DLP &一起使用，但不能同时使用。 这是因为这些策略存储在不同位置，但策略提示只能从单个位置绘制。
  
如果在 Exchange 管理中心中配置了策略提示，那么在安全 & 合规中心内配置的任何策略提示在 Outlook 网页版和 Outlook 2013 及更高版本中不会向用户显示，直到你在 Exchange 管理中心关闭这些提示。 这可确保当前 Exchange 邮件流规则继续工作，直到您选择切换到安全与合规&中心。
  
请注意，虽然策略提示只能从单个位置进行绘制，但始终会发送电子邮件通知，即使您同时在安全与合规中心和 Exchange 管理中心& DLP 策略。
