---
title: 邮件流仪表板中的邮件流见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解安全与合规中心的邮件流仪表板中提供的见解&报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7432eca577fb264126b9fc8f10bdd83de32711cf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289671"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全与合规中心内的邮件流见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

管理员可以使用安全与合规&中的邮件流仪表板发现趋势、见解，并采取措施修复与组织中邮件流相关的问题。

![安全与合规中心内的邮件&仪表板](../../media/mail-flow-dashboard-v2.png)

可用的见解包括：

- [自动转发的邮件见解](mfi-auto-forwarded-messages-report.md)

- [修复可能的邮件循环见解](mfi-mail-loop-insight.md)<sup>1</sup>

- [修复较慢的邮件流规则见解](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [邮件流地图](mfi-mail-flow-map-report.md)

- [正在转发电子邮件见解的新域](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [转发电子邮件见解](mfi-new-users-forwarding-email.md)<sup>2</sup>的新用户

- [非接受域报告](mfi-non-accepted-domain-report.md)

- [未送达报告](mfi-non-delivery-report.md)

- [出站和入站邮件流见解](mfi-outbound-and-inbound-mail-flow.md)

- [队列见解](mfi-queue-alerts-and-queues.md)

- [SMTP 身份验证客户端见解和报告](mfi-smtp-auth-clients-report.md)

- [顶级域邮件流状态见解](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup>仅在检测到问题后，此见解才出现在邮件流仪表板的"建议你"区域中。 否则，你将看不到它。

<sup>2</sup>此见解不会显示在邮件流仪表板上，但在检测到问题后会显示在"[](view-mail-flow-reports.md#forwarding-report)转发报告"页上。 否则，你将看不到它。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看邮件流仪表板所需的权限

邮件流仪表板可供以下角色组的成员使用：

- **安全与** 合规中心&管理 (全局管理员) 。

- **[Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** Active Directory 中的 Exchange 管理员。

- **安全与** 合规中心&邮件流管理员。 如果该帐户不是组织管理或 Exchange 管理员角色组的成员，请考虑以下问题：
  - 用户必须直接登录到安全&合规中心 <https://protection.office.com> 。
  - 用户仅对邮件流仪表板具有只读权限。
  - 用户无法访问 Microsoft 365 管理中心。

有关权限详细信息，请参阅安全与合规[](permissions-in-the-security-and-compliance-center.md)&中的权限，并授予用户对安全与合规&[的访问权限](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>在哪里可以找到邮件流仪表板

打开安全& <https://protection.office.com> 合规中心，展开 **"邮件流**"，然后选择"**仪表板"。**

若要直接转到邮件流仪表板，请打开 <https://protection.office.com/mailflow/dashboard> 。
