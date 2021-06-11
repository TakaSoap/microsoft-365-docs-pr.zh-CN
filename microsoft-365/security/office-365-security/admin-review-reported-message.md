---
title: 管理员审阅报告邮件
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 了解如何查看报告的消息，并为用户提供反馈。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893724"
---
# <a name="admin-review-for-reported-messages"></a>管理员审阅报告邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> 本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。 本文档仅供评估和探索之用。

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365邮箱Exchange Online Microsoft Defender for Office 365 的组织中，管理员现在可以在查看报告的邮件后将模板邮件发送回最终用户。 这可以根据管理员裁定针对你的组织进行自定义。

此功能旨在为用户提供反馈，但不更改系统中邮件裁定。 为了帮助 Microsoft 更新和改进其筛选器，你将需要使用管理员提交 提交[邮件进行分析。](admin-submission.md)

只有在邮件被报告为误报或漏报时，你才能标记和通知 [用户审阅结果](report-false-positives-and-false-negatives.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 在 打开Microsoft 365 Defender 门户 <https://security.microsoft.com/> 。 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission> 。

- 若要修改用户提交的配置，你需要是以下角色组之一的成员：
  - 组织管理或安全管理员在[Microsoft 365 Defender 门户中](permissions-microsoft-365-security-center.md)。
  - 中的组织[Exchange Online。](/Exchange/permissions-exo/permissions-exo#role-groups)

- 你还需要访问 PowerShell Exchange Online权限。 如果您尝试使用的帐户无法访问 Exchange Online PowerShell，您将收到错误消息，指出"在域中指定 *电子邮件地址"。* 有关启用或禁用对 PowerShell Exchange Online，请参阅下列主题：
  - [启用或禁用对 Exchange Online PowerShell 的访问](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [客户端访问规则Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>配置用于通知用户的消息

1. In the Microsoft 365 Defender portal， go to **Email & collaboration Policies** & \> **rules** Threat \> **policies** \> **Others** section User \> **reported message settings**.

2. 在"用户提交"页面上，如果要指定发件人 显示名称，请选中"管理员审阅结果的电子邮件通知"部分下的"指定要用作发件人的 **Office 365** 电子邮件地址"框，然后输入想要使用的名称。 这是将在电子邮件中显示的电子邮件地址Outlook以及答复将转到的电子邮件地址。

3. 如果要自定义任何模板，请单击"**自定义电子邮件通知"。** 在此飞出中，你只能自定义以下内容：
    - 网络钓鱼
    - 垃圾邮件
    - 未发现威胁
    - 意识培训
    - 页脚

4. 完成时，请单击“保存”。 若要清除这些值，请单击" **用户提交** "页面上的"放弃"。
