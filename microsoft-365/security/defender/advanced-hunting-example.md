---
title: Microsoft Defender for Office 365 高级搜寻Office 365
description: 使用高级搜寻开始搜索电子邮件威胁
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 04e4fd2267cc3774e9a816539f0de044ae988dfb
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221180"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 高级搜寻Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

想要开始使用高级搜索搜索电子邮件威胁？ 请尝试使用以下命令：

[Microsoft Defender for Office 365文章](/microsoft-365/security/office-365-security/defender-for-office-365)的[“入门”](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)部分具有如下所示的逻辑早期配置块：

1. 使用名称中的"Anti"配置所有内容。
   - 反恶意软件
   - 防网络钓鱼
   - 反垃圾邮件
2. 设置名称中保险箱"值的所有内容。
   - 安全链接
   - 安全附件
3. 保护工作负载（例如 SharePoint Online、OneDrive 和 Teams) 。
4. 使用零时差自动清除进行保护。

以及一 [链接](../office-365-security/protect-against-threats.md) 一起跳入，在"第 1 天"进行配置。

**入门** 最后一步是通过 **0 小时自动清除清除**（也称为 ZAP）保护用户。 了解你为 ZAP 提供可疑或恶意邮件、发送后成功这一操作是否非常重要。

快速导航到执行查询语言以搜索问题是聚合这两个安全中心的一个优势。 安全团队可以通过在此处执行下一步（在搜寻高级搜寻 [](https://security.microsoft.com/advanced-hunting)下）监视 ZAP \> **错过事件**。

1. 在"高级搜寻"页上，单击"查询 **"。**
1. 将下面的查询复制到查询窗口中。
1. 选择 **运行查询**。

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/ah-query-example-new.png" alt-text="&quot;高级搜寻&quot; (在&quot;搜寻) &quot;下，其中&quot;查询&quot;在查询面板顶部处于选中状态，并运行 Kusto 查询以捕获过去 7 天内的 ZAP 操作。" lightbox="../../media/ah-query-example-new.png":::

来自此查询的数据将在查询自身下方的结果面板中显示。 结果包括可自定义结果集内的信息，如"DeviceName"、"AccountDisplayName"和"<3>pTime"。 也可以为记录导出结果。 如果您再次需要查询，请选择 **保存** > **“另存为”**，然后将查询添加到查询，共享或社区查询列表中。

## <a name="related-information"></a>相关信息
- [高级搜寻最佳做法](advanced-hunting-best-practices.md)
- [概述 - 高级搜寻](advanced-hunting-overview.md)
