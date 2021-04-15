---
title: 配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理员可以了解如何使用 Exchange Online Protection (EOP) 中的高级传递策略来确定不应在特定的支持方案中筛选的邮件 (第三方网络钓鱼模拟以及传递到安全操作 (SecOps) 邮箱的邮件。
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760425"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文介绍的功能在预览版中，并非对所有人都可用，并且可能会更改。

我们希望在默认情况下保证组织的安全[](secure-by-default.md)，因此 Exchange Online Protection (EOP) 不允许对导致恶意软件或高可信度钓鱼裁定的邮件进行安全列表或筛选绕过。 但是，我们知道有一些需要传递未筛选邮件的特定方案。 例如：

- **第三方网络钓鱼模拟**：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。
- **SecOps (安全**) ：安全团队用于收集和分析未筛选邮件的专用邮箱 (无论邮件好还是坏) 。

在 Microsoft  365 中，可以使用高级传递策略来阻止筛选这些特定方案中的邮件 <sup>\*</sup> 。 高级传递策略可确保不筛选这些方案中的邮件：

- EOP 和 Microsoft Defender for Office 365 中的筛选器不针对这些邮件执行任何操作。<sup>\*</sup>
- [零时差清除 (垃圾邮件 ](zero-hour-auto-purge.md)) 对此类邮件不执行任何操作。<sup>\*</sup>
- [这些方案不会](alerts.md) 触发默认系统警报。
- [适用于 Office 365 的 Defender](office-365-air.md) 中的 AIR 和群集将忽略这些消息。
- 专用于第三方网络钓鱼模拟：
  - [管理员提交](admin-submission.md) 会生成自动响应，指出邮件是网络钓鱼模拟活动的一部分，不是真正的威胁。 不会触发警报和 AIR。
  - [Defender for Office 365](safe-links.md) 中的安全链接不会阻止或触发这些邮件中专门标识的 URL。
  - [适用于 Office 365 的 Defender](safe-attachments.md) 中的安全附件不会触发这些邮件中的附件。

<sup>\*</sup> 无法绕过恶意软件筛选或恶意软件的 ZAP。

由高级传递策略标识的邮件不是安全威胁，因此邮件标记为系统替代。 管理员可以在下列体验中筛选和分析这些系统替代：

- [适用于 Office 365 计划 2 的 Defender 中的威胁资源管理器/实时检测](threat-explorer.md)
- 威胁[资源管理器/实时](mdo-email-entity-page.md)检测中的电子邮件实体页面
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Defender for Endpoint 中的高级搜寻](../defender-endpoint/advanced-hunting-overview.md)
- [市场活动视图](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到高级传递 **页面，** 请打开 <https://protection.office.com/advanceddelivery> 。

- 您需获得权限，然后才能执行本文中的过程：
  - 若要在高级传递策略中创建、修改或删除配置的设置，您需要是安全 **&** 合规中心中安全管理员角色组的成员和 **Exchange Online** 中的组织管理角色组的成员。   
  - 若要对高级传递策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。

  有关详细信息，请参阅安全 [与合规](permissions-in-the-security-and-compliance-center.md) 中心&和 [Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo)。

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>使用安全&中心在高级传递策略中配置第三方网络钓鱼模拟

1. 在安全与&中心，转到"**威胁管理** 策略高级 \>  \> **传递"。**

2. 在"**高级传递"** 页上，选择"**网络钓鱼模拟**"选项卡，然后单击"编辑 **"。**

3. 在 **打开的第三方网络钓鱼** 模拟飞出上，配置以下设置：

   - **发送域**：至少需要一个电子邮件地址 (，例如 contoso.com) 。 您最多可以添加 10 个条目。
   - **发送 IP：** 至少需要一个有效的 IPv4 地址。 您最多可以添加 10 个条目。 有效值为：
     - 单个 IP：例如，192.168.1.1。
     - IP 范围：例如，192.168.0.1-192.168.0.254。
     - CIDR IP：例如，192.168.0.1/25。
   - **要允许的** 模拟 URL：（可选）输入属于网络钓鱼模拟活动的特定 URL，不应被阻止或触发。 您最多可以添加 10 个条目。

4. 完成后，单击"保存 **"。**

您配置的第三方网络钓鱼模拟条目显示在"网络钓鱼模拟 **"选项卡上** 。若要进行更改，请单击选项卡 **上的** "编辑"。

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>使用安全&中心在高级传递策略中配置 SecOps 邮箱

1. 在安全与&中心，转到"**威胁管理策略**"" \>  \> **高级传递"。**

2. 在"**高级传递"** 页上，选择 **"SecOps 邮箱"** 选项卡，然后单击"编辑 **"。**

3. 在打开 **的 SecOps** 邮箱飞出区中，输入要指定为 SecOps 邮箱的现有 Exchange Online 邮箱的电子邮件地址。 不允许通讯组。

4. 完成后，单击“**保存**”。

您配置的 SecOps 邮箱条目显示在 **SecOps** 邮箱选项卡上。若要进行更改，请单击选项卡 **上的** "编辑"。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>需要筛选旁路的其他方案

除了高级传递策略可以帮助你的两种方案之外，还有其他一些方案可能需要绕过筛选：

- 第三方筛选器：如果域的 MX 记录未指向 Office 365， (邮件将路由到其他位置) ，默认情况下，安全不可用。 [](secure-by-default.md)

  若要绕过 Microsoft 筛选已由第三方筛选评估的邮件，请使用邮件流规则 (也称为传输规则) ，请参阅使用邮件流规则设置邮件[中的 SCL。](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- 正在审查 **的** 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在分析的某些邮件，以报告被 [](admin-submission.md)错误地标记为对 Microsoft (误报错误的已知) 。 与所有替代一样，我们强烈建议这些允许是临时的。
