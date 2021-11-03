---
title: 隔离的电子邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在包含潜在危险或不需要Exchange Online Protection (EOP) 隔离邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58097b5dba60c1ea085ea6e78c878982abe24021
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703617"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>EOP 和 Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365邮箱位于 Exchange Online 或独立 Exchange Online Protection (EOP) Exchange Online) 组织中，可以使用隔离来保留潜在危险或不需要的邮件。

如果发现任何附件包含 *恶意软件，反* 恶意软件策略将自动隔离邮件。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

默认情况下，反垃圾邮件策略隔离网络钓鱼和高可信度网络钓鱼邮件，将垃圾邮件、高可信度垃圾邮件和批量电子邮件发送到用户的"垃圾邮件"文件夹。 但是，您还可以创建和自定义反垃圾邮件策略以隔离垃圾邮件、高可信度垃圾邮件和批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

用户和管理员可以使用隔离邮件：

- _隔离_ 策略根据隔离邮件的原因来定义允许或不对隔离邮件执行哪些操作 (支持的功能) 。 默认隔离策略强制实施历史功能，如下所述。 管理员可以创建和应用自定义隔离策略，这些策略为用户定义限制性较低或限制更严格的功能，还可以打开隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

- 管理员可以为所有用户使用所有类型的隔离邮件。 默认情况下，只有管理员才能处理被隔离为恶意软件、高可信度网络钓鱼或由于邮件流规则（也称为传输规则 (邮件) ）。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)。

- 默认情况下，用户可以处理作为收件人且被隔离为垃圾邮件、批量电子邮件或网络钓鱼邮件的隔离邮件 (高可信度钓鱼邮件) 。 有关详细信息，请参阅在 [EOP](find-and-release-quarantined-messages-as-a-user.md)中以用户模式查找并释放隔离邮件。

  若要阻止用户管理其自己的隔离网络钓鱼邮件，管理员可以分配一个隔离策略，拒绝从反垃圾邮件策略中的网络钓鱼电子邮件筛选裁定访问隔离邮件。  有关详细信息，请参阅在反[垃圾邮件策略](quarantine-policies.md#anti-spam-policies)"隔离策略"中分配[隔离策略](quarantine-policies.md)。

- 管理员和用户可以在隔离中向 Microsoft 报告误报。

- 隔离邮件在过期之前在隔离中的时间因邮件被隔离的原因而异。 下表介绍了隔离邮件的功能及其相应的保留期：

  <br>

  ****

  |隔离原因：|默认保留期|可自定义？|备注|
  |---|:---:|:---:|---|
  |由反垃圾邮件策略隔离的邮件：垃圾邮件、高可信度垃圾邮件、网络钓鱼、高可信度网络钓鱼或批量邮件。|30 天|是|可以在反 (中) 此值配置较低的值。 有关详细信息，请参阅配置反垃圾邮件策略中的将垃圾邮件保留隔离的这 (_QuarantineRetentionPeriod_) [设置。](configure-your-spam-filter-policies.md)|
  |由反网络钓鱼策略隔离的邮件：EOP 中的欺骗智能;Defender for Office 365 中的用户模拟、域模拟或Office 365。|30 天|是|此保留期也由反垃圾邮件策略中的"将垃圾邮件保留隔离 (_QuarantineRetentionPeriod_) **设置控制**。 使用的保留期是定义收件人的第一个匹配反垃圾邮件策略的值。|
  |由反恶意软件策略隔离的邮件 (恶意软件) 。|15 天|否||
  |在 Defender 中保险箱附件策略隔离的邮件Office 365 (恶意软件) 。|15 天|否||
  |邮件流规则隔离的邮件：操作是 **"** 将邮件发送到托管隔离邮箱" (_隔离_) 。|30 天|否||
  |附件隔离的文件保险箱附件SharePoint、OneDrive Microsoft Teams (恶意软件) 。|15 天|否||
  |

  当邮件从隔离区过期时，你无法恢复它。

有关隔离功能详细信息，请参阅隔离 [常见问题](quarantine-faq.yml)解答。
