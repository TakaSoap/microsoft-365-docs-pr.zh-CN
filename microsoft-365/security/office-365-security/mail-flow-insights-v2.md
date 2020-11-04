---
title: 邮件流仪表板中的邮件流见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中提供的见解和报告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d252b9d898d4ee5a0df854a871f821c2b02bb482
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877773"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全与合规中心内的邮件流见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


管理员可以使用安全 & 合规性中心中的邮件流仪表板来发现趋势、见解，并采取措施解决与组织中的邮件流相关的问题。

![安全 & 合规性中心中的邮件流仪表板](../../media/mail-flow-dashboard-v2.png)

可用的见解包括：

- [自动转发的邮件见解](mfi-auto-forwarded-messages-report.md)

- [修复可能的邮件循环见解](mfi-mail-loop-insight.md)<sup>1</sup>

- [修复慢速邮件流规则真知灼见](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [邮件流地图](mfi-mail-flow-map-report.md)

- [转发的新域电子邮件洞察力](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新用户转发电子邮件真知灼见](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [非接受域报告](mfi-non-accepted-domain-report.md)

- [未送达报告](mfi-non-delivery-report.md)

- [出站和入站邮件流见解](mfi-outbound-and-inbound-mail-flow.md)

- [队列见解](mfi-queue-alerts-and-queues.md)

- [SMTP 身份验证客户端见解和报告](mfi-smtp-auth-clients-report.md)

- [顶级域邮件流状态见解](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 只有在检测到问题之后，才会在 "邮件流" 仪表板的 " **建议** " 区域中显示此见解。 否则，您将看不到它。

<sup>2</sup> 此真知灼见不会出现在邮件流仪表板上，但在检测到问题后，在 " [转发报告](view-mail-flow-reports.md#forwarding-report) " 页面上可见。 否则，您将看不到它。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看邮件流仪表板所需的权限

邮件流仪表板可用于以下角色组的成员：

- 安全 & 合规中心 (全局管理员) 中的 " **组织管理** "。

- Azure Active Directory 中的 **[Exchange 管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** 。

- Security & 合规性中心中的 **邮件流管理员** ：如果此角色组的成员不是全局管理员或 Exchange 管理员角色组的成员，则请注意以下问题和要求：

  - 用户必须直接在中直接登录到安全 & 合规性中心 <https://protection.office.com> 。
  - 用户将只具有对邮件流仪表板的只读权限。
  - 用户将无法访问 Microsoft 365 管理中心。

有关安全性 & 合规性中心中的权限的详细信息，请参阅 [security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md) 和 [授予用户对安全 & 合规性中心的访问](grant-access-to-the-security-and-compliance-center.md)权限。

## <a name="where-to-find-the-mail-flow-dashboard"></a>在何处查找邮件流仪表板

在中打开 "安全 & 合规中心" <https://protection.office.com> ，展开 " **邮件流** "，然后选择 " **仪表板** "。

若要直接转到 "邮件流" 仪表板，请打开 <https://protection.office.com/mailflow/dashboard> 。
