---
title: 查看数据丢失防护报告
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 使用 Office 365 中的 DLP 报告查看 DLP 策略匹配、覆盖或误报的数量，并查看它们是否随着时间的推移呈上升或下降趋势。
ms.openlocfilehash: eb281f4d912a9e21716d7f9859564a02f9c23401
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423825"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>查看数据丢失防护报告

在 DLP (策略) 数据丢失防护后，您需要验证它们是否正常工作，并帮助您保持合规性。 使用安全合规中心中的 DLP 报告 &amp; ，可以快速查看：
  
- **DLP 策略匹配** 此报告显示随着时间的推移 DLP 策略匹配项的计数。 可以按日期、位置、策略或操作筛选报告。 可以使用此报告： 
    
  - 在测试模式下运行 DLP 策略时，请调整或优化这些策略。 您可以查看与内容匹配的特定规则。
    
  - 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
  - 发现违反组织的 DLP 策略的业务流程。
    
  - 通过查看要应用于内容的操作，了解 DLP 策略的任何业务影响。
    
  - 通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。
    
  - 查看顶级用户列表，并重复组织中参与事件的用户。
    
  - 查看组织中最热门敏感信息类型的列表。
    
- **DLP 事件** 此报告还显示一段时间的策略匹配，如策略匹配报告。 但是，策略匹配报告在规则级别显示匹配项;例如，如果电子邮件匹配三个不同的规则，则策略匹配报告将显示三个不同的行项目。 相比之下，事件报告在项目级别显示匹配项;例如，如果电子邮件匹配三个不同的规则，则事件报告将显示该内容的单个行项。 
    
  由于报告计数的聚合方式不同，因此策略匹配报告更适用于使用特定规则标识匹配项并微调 DLP 策略。 事件报告更适用于标识 DLP 策略存在问题的特定内容部分。
    
- **DLP 误报和替代** 如果您的 DLP 策略允许用户替代它或报告误报，则此报告显示随着时间的推移此类实例的计数。 可以按日期、位置或策略筛选报告。 可以使用此报告： 
    
  - 通过查看哪些策略导致大量误报来调整或优化 DLP 策略。
    
  - 查看用户在通过覆盖策略解析策略提示时提交的理由。
    
  - 通过导致大量用户替代发现 DLP 策略与有效业务流程冲突的地方。
    
所有 DLP 报告都可以显示最近四个月时间段的数据。 最新数据最多可能需要 24 小时才能显示在报告中。
  
您可以在安全合规中心报告仪表板 &amp; \> **中查找** \> **这些报告**。
  
![DLP 策略匹配报告](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>查看用户提交的替代理由

如果 DLP 策略允许用户替代它，可以使用误报和覆盖报告查看策略提示中用户提交的文本。
  
![DLP 误报和替代报告详细信息的"理由"字段](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>对见解和建议采取措施

报告可以显示见解和建议，可在其中单击红色警告图标查看有关潜在问题的详细信息，并采取可能的补救措施。
  
![单击见解图标以查看详细信息和要采取的操作](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>DLP 报告的权限

若要在安全与合规&查看 DLP 报告，您必须获得以下权限：

- **Exchange 管理** 中心中的安全读者角色。 默认情况下，此角色分配给 Exchange 管理中心中的"组织管理和安全读者"角色组。

- **安全与合规中心** 中的"仅查看 DLP 合规性&角色。 默认情况下，此角色分配给安全与合规中心中的合规性管理员、组织管理、安全管理员&角色组。

- **Exchange 管理中心中的** "仅查看收件人"角色。 默认情况下，此角色分配给 Exchange 管理中心View-Only合规性管理、组织管理和组织管理角色组。

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>查找 DLP 报表的 cmdlet

若要使用安全 &amp; 合规中心的大多数 cmdlet，你需要执行以下操作：
  
1. [使用远程 &amp; PowerShell 连接到安全合规中心](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. 使用以下任一 [安全 &amp; 合规中心 cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
但是，DLP 报告需要从 Office 365（包括 Exchange Online）提取数据。 因此，DLP 报告 cmdlet 在 Exchange Online Powershell 中可用，而不是在安全 &amp; 合规中心 Powershell 中提供。 因此，若要使用适用于 DLP 报告的 cmdlet，你需要执行以下操作：
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. 对 DLP 报告使用以下任意 cmdlet：
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

