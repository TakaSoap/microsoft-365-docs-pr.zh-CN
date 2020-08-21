---
title: 垃圾邮件 &apos; 和批量邮件之间有什么差异？
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解垃圾邮件、垃圾邮件 (和批量) 电子邮件和大量电子邮件 (Exchange Online Protection 和 EOP) 中的) 灰色邮件功能 (。
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826725"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP 中的垃圾邮件和批量邮件之间有什么差异？

无论是在 Exchange Online 组织，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中具有邮箱的 Microsoft 365 组织中，客户有时会问："垃圾邮件和批量邮件之间有什么差异？" 本主题说明了此差异，并介绍了可在 EOP 中使用的控件。

- **垃圾邮件是** 一种垃圾邮件，即未经处理并且通常不受 (识别) 。 默认情况下，EOP 根据源电子邮件服务器的信誉拒绝垃圾邮件。 如果邮件通过源 IP 检查，将发送到垃圾邮件筛选。 如果邮件被垃圾邮件筛选分类为垃圾邮件，则默认情况下) 该 (将目标收件人传递到目标收件人并移动到其"垃圾邮件"文件夹。

  - 可以将操作配置为对垃圾邮件筛选顶点执行操作。 有关说明，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

  - 如果你对垃圾邮件筛选标点有所不同，可以通过几种方式向 Microsoft 报告你认为是垃圾邮件或非垃圾邮件的邮件，如"向 Microsoft 报告 [邮件和文件](report-junk-email-messages-to-microsoft.md)"中所述。

- **批量邮件 (** 邮件 _组（亦_ 称为") 邮件"）会更难分类。 垃圾邮件是一种持续性的威胁，而批量电子邮件通常是一次性广告或营销邮件。 有些用户希望批量 (，并且实际上，他们有意注册以接收) ，而其他用户则认为批量电子邮件为垃圾邮件。 例如，某些用户希望从 Contoso Corporation 收到来自 Contoso Corporation 的广告邮件或即将来活动的网络安全会议邀请，而其他用户则将相同的邮件视为垃圾邮件。

  有关如何识别批量电子邮件的更多信息，请参阅 EOP 中的批量 (诉 [) 级别和 BCL) 级别](bulk-complaint-level-values.md)。

## <a name="how-to-manage-bulk-email"></a>如何管理批量邮件

由于将批量电子邮件的混合反应，所有组织都没有通用指导。

反垃圾邮件策略有一个默认的 BCL 阈值，用于将批量电子邮件标识为垃圾邮件。 管理员可以增大或减少阈值。 有关详细信息，请参阅下列主题：

- [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

容易忽视的另一个选项：如果用户对接收批量电子邮件感到有关，但邮件来自通过 EOP 中垃圾邮件筛选的信誉发件人，用户可在批量电子邮件中检查未订阅选项。
