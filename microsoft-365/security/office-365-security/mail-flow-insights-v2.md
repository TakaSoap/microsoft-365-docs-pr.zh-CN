---
title: 邮件流仪表板中的邮件流见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解安全与合规中心的邮件流仪表板中可用的见&报告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e9449553d008bc383ae6f2b6098f9598cad43c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826561"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全与合规中心内的邮件流见解

管理员可使用安全 & 合规中心的邮件流仪表板，发现趋势、见解并采取措施解决与其组织中邮件流相关的问题。

![安全与合规中心&的邮件流仪表板](../../media/mail-flow-dashboard-v2.png)

可以见解为：

- [自动转发的邮件见解](mfi-auto-forwarded-messages-report.md)

- [修复可能的邮件循环见解](mfi-mail-loop-insight.md)<sup>1</sup>

- [修复邮件流规则缓慢的见解](mfi-slow-mail-flow-rules-insight.md)<sup>1 问题</sup>

- [邮件流地图](mfi-mail-flow-map-report.md)

- [转发电子邮件见](mfi-new-domains-being-forwarded-email.md)解 2 的新<sup>域</sup>

- [新用户转发电子邮件见解](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [非接受域报告](mfi-non-accepted-domain-report.md)

- [未送达报告](mfi-non-delivery-report.md)

- [出站和入站邮件流见解](mfi-outbound-and-inbound-mail-flow.md)

- [队列见解](mfi-queue-alerts-and-queues.md)

- [SMTP 身份验证客户端见解和报告](mfi-smtp-auth-clients-report.md)

- [顶级域邮件流状态见解](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 仅当检测到此问题后 **，"只要您是在** 邮件流"仪表板的区域中，"建议"就会出现此见解。 否则，您将看不到它。

<sup>2</sup> 此见解不显示在邮件流仪表板中，但在检测到问题后 [会在"转发报告](view-mail-flow-reports.md#forwarding-report) "页面上显示该见解。 否则，您将看不到它。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看邮件流仪表板所需的权限

邮件流仪表板对以下路由组的成员可用：

- **安全与** 合规中心内的组织&管理 (管理员审核日志) 。

- **[Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** AD 中的 Exchange 管理员。

- **安全与** 合规中心 &中的邮件流管理员：如果此角色组的成员不是全局管理员或 Exchange 管理员角色组的成员，请注意下列问题和要求：

  - 用户必须直接登录安全&合规中心 <https://protection.office.com> 。
  - 用户仅对邮件流仪表板具有只读权限。
  - 用户无法访问 Microsoft 365 管理中心。

若要详细了解安全与&合规中心中的权限，请参阅 [安全&合规中心中的"](permissions-in-the-security-and-compliance-center.md) 权限" [并向用户授予对安全与&合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>在哪里查找邮件流仪表板

打开"安全&中心， <https://protection.office.com> 展开"**邮件流"，** 然后选择"仪表板 **"。**

若要直接转到邮件流仪表板，请打开 <https://protection.office.com/mailflow/dashboard> 。
