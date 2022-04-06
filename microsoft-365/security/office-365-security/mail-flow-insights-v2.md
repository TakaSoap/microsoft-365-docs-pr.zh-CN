---
title: 邮件流仪表板中的邮件流见解
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解安全与合规中心内邮件流仪表板中提供的见解&报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 176681b5fe780f0aeb4a0c8502b3e919e7ebcadc
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682518"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全与合规中心内的邮件流见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理员可以使用安全与合规中心内的邮件流&发现趋势、见解，并采取措施来解决与组织中邮件流相关的问题。

![安全与合规中心内的邮件&仪表板。](../../media/mail-flow-dashboard-v2.png)

可用的见解包括：

- [自动转发的邮件见解](mfi-auto-forwarded-messages-report.md)

- [修复可能的邮件循环见解](mfi-mail-loop-insight.md)<sup>1</sup>

- [修复慢速邮件流规则见解](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [邮件流地图](mfi-mail-flow-map-report.md)

- [正在转发电子邮件见解的新域](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新用户转发电子邮件见解](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [非接受域报告](mfi-non-accepted-domain-report.md)

- [未送达报告](mfi-non-delivery-report.md)

- [出站和入站邮件流见解](mfi-outbound-and-inbound-mail-flow.md)

- [队列见解](mfi-queue-alerts-and-queues.md)

- [SMTP 身份验证客户端见解和报告](mfi-smtp-auth-clients-report.md)

- [顶级域邮件流状态见解](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 仅在检测到问题后，此见解会出现在邮件流仪表板的"建议你使用"区域中。 否则，你将看不到它。

<sup>2</sup> 此见解不会显示在邮件流仪表板上，但在检测到问题后，会显示在"转发[](view-mail-flow-reports.md#forwarding-report)报告"页上。 否则，你将看不到它。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看邮件流仪表板所需的权限

邮件流仪表板可供以下角色组的成员使用：

- **安全与** 合规中心&管理 (全局管理员) 。

- **[Exchange管理员](/azure/active-directory/roles/permissions-reference#exchange-administrator)** Azure Active Directory。

- **安全与** 合规中心&邮件流管理员。 如果该帐户不是组织管理或管理员Exchange的成员，请考虑以下问题：
  - 用户必须直接登录到安全&合规中心 <https://protection.office.com>。
  - 用户仅对邮件流仪表板具有只读权限。
  - 用户无法访问Microsoft 365 管理中心。

有关权限详细信息，请参阅安全与合规中心& [权限](permissions-in-the-security-and-compliance-center.md) 和向用户授予对安全与合规& [的访问权限](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>在哪里可以找到邮件流仪表板

打开安全&合规中心， <https://protection.office.com>展开" **邮件流**"，然后选择"仪表板 **"**。

若要直接转到邮件流仪表板，请打开 <https://protection.office.com/mailflow/dashboard>。