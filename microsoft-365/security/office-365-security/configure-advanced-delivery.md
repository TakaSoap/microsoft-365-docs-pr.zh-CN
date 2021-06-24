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
description: 管理员可以了解如何使用 Exchange Online Protection (EOP) 中的高级传递策略识别不应在特定的支持方案中筛选的邮件 (第三方网络钓鱼模拟以及传递到安全操作 (SecOps) 邮箱的邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 819f78883aa75fbbdded2e47c1bb85945f080233
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108399"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文介绍的功能在预览版中，并非对所有人都可用，并且可能会更改。

若要在默认情况下保证[](secure-by-default.md)组织安全，Exchange Online Protection (EOP) 不允许对标识为恶意软件或高可信度网络钓鱼的邮件进行安全列表或筛选绕过。 但是，有一些特定方案需要传递未筛选的邮件。 例如：

- **第三方网络钓鱼模拟**：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。
- **SecOps (安全**) ：安全团队用于收集和分析未筛选邮件的专用邮箱 (无论邮件好还是坏) 。

在邮件 _中，可以使用_ Microsoft 365策略来阻止筛选这些特定方案中的邮件。  <sup>\*</sup>高级传递策略可确保这些方案中的邮件获得以下结果：

- EOP 和 Microsoft Defender 中的筛选器Office 365这些邮件不执行任何操作。<sup>\*</sup>
- [零时差清除 (对 ](zero-hour-auto-purge.md)) 和网络钓鱼的 ZAP 邮件不执行任何操作。<sup>\*</sup>
- [对于这些方案](alerts.md) ，不会触发默认系统警报。
- [AIR 和 Defender for Office 365](office-365-air.md)将忽略这些消息。
- 专用于第三方网络钓鱼模拟：
  - [管理员提交](admin-submission.md) 生成自动响应，指出邮件是网络钓鱼模拟活动的一部分，不是真正的威胁。 不会触发警报和 AIR。
  - [保险箱 Defender for Office 365](safe-links.md)中的链接不会阻止或触发这些邮件中专门标识的 URL。
  - [保险箱 Defender for Office 365](safe-attachments.md)中的附件不会触发这些邮件中的附件。

<sup>\*</sup> 无法绕过恶意软件筛选或恶意软件的 ZAP。

由高级传递策略标识的邮件不是安全威胁，因此邮件标记为系统替代。 管理员可以在下列体验中筛选和分析这些系统替代：

- [Defender for Office 365 计划 2 中的威胁资源管理器/实时检测](threat-explorer.md)
- 威胁[资源管理器/实时](mdo-email-entity-page.md)检测中的电子邮件实体页面
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Defender for Endpoint 中的高级搜寻](../defender-endpoint/advanced-hunting-overview.md)
- [市场活动视图](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到高级传递 **页面，** 请打开 <https://security.microsoft.com/advanceddelivery> 。

- 您需获得权限，然后才能执行本文中的过程：
  - 若要在高级传递策略中创建、修改或删除配置的设置，您需要是 Microsoft 365 Defender 门户中安全管理员角色组的成员以及 **Exchange Online** 中的组织管理角色 **组的成员**。   
  - 若要对高级传递策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。

  有关详细信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)和 Exchange Online 中[的权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > 将用户添加到相应的 Azure Active Directory 角色会为用户提供在 Microsoft 365 Defender _门户中_ 所需的权限，以及用户对 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>使用 Microsoft 365 Defender门户在高级传递策略中配置 SecOps 邮箱

1. In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** threat \> **policies** page \> **Rules** section \> **Advanced delivery**.

2. 在" **高级传递"** 页上，确认 **"SecOps** 邮箱"选项卡已选中，然后执行下列步骤之一：
   - 单击 ![ "编辑"图标 ](../../media/m365-cc-sc-edit-icon.png) **"编辑"。**
   - 如果没有配置网络钓鱼模拟，请单击"添加 **"。**

3. 在打开的"编辑 **SecOps** 邮箱"飞出控件上，通过执行以下步骤之一输入要指定为 SecOps 邮箱的现有 Exchange Online 邮箱：
   - 在框中单击，让邮箱列表解析，然后选择邮箱。
   - 单击框中开始键入邮箱 (名称、显示名称、别名、电子邮件地址、帐户名等 ) 的标识符，然后从结果中选择 (显示名称) 邮箱标识符。

     根据需要重复执行此步骤（次数不限）。 不允许通讯组。

     若要删除现有值，请单击值旁边的 ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

4. 完成时，请单击“保存”。

您配置的 SecOps 邮箱条目显示在 **SecOps** 邮箱选项卡上。若要进行更改，请单击选项卡 ![ 上的" ](../../media/m365-cc-sc-edit-icon.png) 编辑"图标"编辑"。

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>使用Microsoft 365 Defender门户在高级传递策略中配置第三方网络钓鱼模拟

1. In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** threat \> **policies** page \> **Rules** section \> **Advanced delivery**.

2. 在" **高级传递"** 页上，选择" **网络钓鱼模拟** "选项卡，然后执行下列步骤之一：
   - 单击 ![ "编辑"图标 ](../../media/m365-cc-sc-edit-icon.png) **"编辑"。**
   - 如果没有配置网络钓鱼模拟，请单击"添加 **"。**

3. 在打开 **的"编辑第三方网络钓鱼** 模拟"飞出控件上，配置以下设置：

   - 发送域：展开此设置并输入至少一个电子邮件地址域 (例如，contoso.com) 方法是单击该框，输入值，然后按 Enter 或选择显示在框下方的值。 根据需要重复执行此步骤（次数不限）。 您最多可以添加 10 个条目。
   - **发送 IP：** 展开此设置，并输入至少一个有效的 IPv4 地址，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。 根据需要重复执行此步骤（次数不限）。 您最多可以添加 10 个条目。 有效值为：
     - 单个 IP：例如，192.168.1.1。
     - IP 范围：例如，192.168.0.1-192.168.0.254。
     - CIDR IP：例如，192.168.0.1/25。
   - 要允许的模拟 URL：展开此设置，并选择输入属于网络钓鱼模拟活动的一部分的特定 URL，这些 URL 不应被阻止或触发，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。 您最多可以添加 10 个条目。

   若要删除现有值，请单击值旁边的 ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

4. 完成后，请执行下列步骤之一：
   - **第一次**：单击 **"添加"，** 然后单击"关闭 **"。**
   - **编辑现有**：单击"**保存"，** 然后单击"关闭 **"。**

您配置的第三方网络钓鱼模拟条目显示在"网络钓鱼模拟 **"选项卡上**。若要进行更改，请单击选项卡 ![ 上的" ](../../media/m365-cc-sc-edit-icon.png) 编辑"图标"编辑"。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>需要筛选旁路的其他方案

除了高级传递策略可以帮助你的两种方案之外，还有其他一些方案可能需要绕过筛选：

- **第三方筛选器**：如果你的域的 MX记录没有指向Office 365 (邮件将路由到其他位置) ，默认情况下，安全 [](secure-by-default.md)*不可用*。

  若要绕过 Microsoft 筛选已由第三方筛选评估的邮件，请使用邮件流规则 (传输规则) 。 有关详细信息，请参阅使用[邮件流规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- 正在审查 **的** 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在分析的某些邮件，以报告被 [](admin-submission.md)错误地标记为对 Microsoft (误报错误的已知) 。 与所有替代一样， **_我们强烈建议这些_** 允许是临时的。
