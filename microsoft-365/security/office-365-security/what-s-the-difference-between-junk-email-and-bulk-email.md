---
title: '&apos;垃圾邮件和批量电子邮件之间有什么区别？'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 eOP (中的垃圾邮件) 垃圾邮件 (灰色) Exchange Online Protection (邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8a896ac3360ccf799dbe34c7e298f76140ee6d5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154298"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP 中的垃圾邮件和批量电子邮件之间有什么区别？

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，客户有时会问："垃圾邮件和批量邮件之间有什么区别？" 本主题介绍区别，并介绍 EOP 中可用的控件。

- **垃圾邮件是** 垃圾邮件，如果标识正确，垃圾邮件是未经请求 (不必要的) 。 默认情况下，EOP 根据源电子邮件服务器的信誉拒绝垃圾邮件。 如果邮件通过源 IP 检查，则发送到垃圾邮件筛选。 如果通过垃圾邮件筛选将邮件分类为垃圾邮件，则默认情况下 (邮件) 目标收件人并移动到其"垃圾邮件"文件夹。

  - 您可以配置对垃圾邮件筛选裁定采取的操作。 有关说明，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

  - 如果您对垃圾邮件筛选裁定不一致，您可以通过多种方式向 Microsoft 报告视为垃圾邮件或非垃圾邮件的邮件，如向 Microsoft 报告邮件和文件 [中所述](report-junk-email-messages-to-microsoft.md)。

- **群发** (也称为 _灰色_ 邮件) ，更难分类。 垃圾邮件是一种持续的威胁，而批量电子邮件通常是一次广告或营销邮件。 一些用户希望批量电子邮件 (实际上，他们特意注册以接收这些) ，而其他用户则认为批量电子邮件是垃圾邮件。 例如，一些用户希望接收来自 Contoso Corporation 的广告消息或邀请参加即将召开的网络安全会议，而其他用户则认为这些相同的邮件是垃圾邮件。

  有关如何识别批量电子邮件详细信息，请参阅批量投诉级别 [ (BCL) EOP](bulk-complaint-level-values.md)。

## <a name="how-to-manage-bulk-email"></a>如何管理批量邮件

由于对批量电子邮件的混合反应，没有适用于每个组织的通用指南。

反垃圾邮件策略具有一个默认 BCL 阈值，用于将批量电子邮件标识为垃圾邮件。 管理员可以增加或减小阈值。 有关详细信息，请参阅下列主题：

- [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

另一个易于忽略的选项：如果用户抱怨接收批量电子邮件，但邮件来自通过 EOP 中的垃圾邮件筛选的声誉良好的发件人，请让用户检查批量电子邮件中的取消订阅选项。
