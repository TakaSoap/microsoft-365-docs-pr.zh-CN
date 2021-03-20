---
title: Exchange Online Protection (EOP) 概述
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 了解 Exchange Online Protection (EOP) 如何在独立和混合环境中帮助保护本地电子邮件组织。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa2925ed5a9a6088fab81a09754b479740411cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910830"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) 是基于云的筛选服务，可帮助保护组织免受垃圾邮件和恶意软件的攻击。 EOP 包含在所有具有 Exchange Online 邮箱的 Microsoft 365 组织中。 但是，EOP 也可在下列本地方案中使用：

- **在独立方案中**：EOP 为本地 Exchange 组织或任何其他本地 SMTP 电子邮件解决方案提供基于云的电子邮件保护。

- **在混合部署** 中：当您混合使用本地邮箱和云邮箱时，EOP 可以配置为保护您的电子邮件环境并控制邮件路由。

在这些情况下，EOP 可以简化电子邮件环境的管理，并减轻维护本地硬件和软件带来的许多负担。

本主题的其余部分介绍了 EOP 在独立和混合环境中的工作方式。

## <a name="how-eop-works"></a>EOP 如何工作

了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="在垃圾邮件或隔离裁定之前，通过 Connection、Anti-malware、Mailflow Rules-slash-Policy Filtering 和 Content Filtering 从 Internet 或客户反馈传递到 EOP 的电子邮件的图形。":::

- 传入邮件进入 EOP 时，最初会通过连接筛选，这将检查发件人的信誉。 大多数垃圾邮件此时停止，并遭 EOP 拒绝。 有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。

- 然后检查邮件是否有恶意软件的迹象。 如果在邮件或附件中发现恶意软件， (邮件) 仅路由到管理员隔离存储。 你可以在此处了解有关配置反恶意软件 [的更多信息](configure-anti-malware-policies.md)。

- 邮件将继续通过策略筛选，其中根据自定义邮件流规则（也称为 (模板创建) 强制实施的传输规则）评估邮件。 例如，你可以将规则设置为当收到来自特定发件人的邮件时向管理器发送通知。 此时， (EXCHANGE Enterprise CAL with Services) 也会进行数据丢失防护 (DLP) 。

- 接下来，邮件将经过内容筛选 (也称为反垃圾邮件) 。 此筛选器确定为垃圾邮件或网络钓鱼的邮件可以发送到隔离区，或者用户的"垃圾邮件"文件夹以及其他选项。 有关详细信息，请参阅[配置反垃圾邮件策略和](configure-your-spam-filter-policies.md)[配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

任何成功通过所有这些保护层的邮件将传递给收件人。

有关详细信息，请参阅电子邮件 [保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>内部部署电子邮件组织的 EOP 计划和功能

可用的 EOP 订阅计划包括：

- **独立 EOP：** 注册 EOP 以保护本地电子邮件组织。

- **Exchange Online 中的 EOP** 功能：任何包含 Exchange Online (或作为 Microsoft 365) 的一部分的订阅都使用 EOP 来保护 Exchange Online 邮箱。

- **Exchange Enterprise CAL with Services：** 如果你有一个本地 Exchange 组织，你已购买其他 Exchange Enterprise CAL with Services 许可证，则 EOP 是所包括服务的一部分。

有关所有 EOP 订阅计划的要求、重要限制以及功能可用性的信息，请参阅 [Exchange Online Protection 服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>为内部部署电子邮件组织设置 EOP

设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。

如果您已购买 EOP，请参阅 [设置 EOP 服务](set-up-your-eop-service.md)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。

### <a name="eop-datacenters"></a>EOP 数据中心

EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。 例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。 每个数据中心中的服务器代表您接受邮件，从而在您的组织和 Internet 之间提供一个分隔层，从而减少服务器的负载。 通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。

EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：

- 在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。

- 在 Asia-Pacific (APAC) 中，所有 Exchange Online 邮箱都位于 APAC 数据中心，并且邮件当前通过 APAC 数据中心进行路由，以用于 EOP 筛选。

- 在美洲，服务分布在以下位置：

  - 南非：Exchange Online 邮箱位于巴西和智利的数据中心。 所有邮件均通过本地数据中心进行 EOP 筛选。 隔离邮件存储在租户所在的数据中心中。

  - 加拿大：Exchange Online 邮箱位于加拿大的数据中心。 所有邮件均通过本地数据中心进行 EOP 筛选。 隔离邮件存储在租户所在的数据中心中。

  - 美国：Exchange Online 邮箱位于美国数据中心。 所有邮件均通过本地数据中心进行 EOP 筛选。 隔离邮件存储在租户所在的数据中心中。

- 对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。

## <a name="eop-help-for-admins"></a>EOP 管理员帮助

针对 EOP 管理员的帮助内容包括以下顶级类别：

- [Configure EOP， Day 1， for Microsoft Defender for Office 365 admins：](protect-against-threats.md)Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.

- [EOP 功能](eop-features.md)：提供 EOP 中提供的功能列表。

- [设置 EOP 服务](set-up-your-eop-service.md)：提供设置 EOP 服务的步骤，以及指向其他信息的链接。

- [从 Google Postini、Barracuda 垃圾邮件和](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)病毒防火墙或 Cisco IronPort 切换到 EOP：介绍从另一个电子邮件保护产品切换到 EOP 的过程。

- [在独立 EOP 中管理](manage-recipients-in-eop.md)收件人：介绍如何在 EOP 中管理邮件用户和组。

- [EOP](mail-flow-in-eop.md)中的邮件流：介绍如何使用连接器配置自定义邮件流方案，如何管理与服务关联的域，以及如何启用基于目录的边缘阻止 (DBEB) 功能。

- [配置 EOP 的](best-practices-for-configuring-eop.md)最佳实践：介绍设置和设置服务后的建议配置设置和注意事项。

- [独立 EOP 中的](auditing-reports-in-eop.md)审核报告 ：介绍如何使用审核报告跟踪对服务的配置更改。

- [EOP 中的](anti-spam-and-anti-malware-protection.md)反垃圾邮件和反恶意软件保护：介绍垃圾邮件筛选和恶意软件筛选，并演示如何自定义它们以最好地满足组织的需求。 还介绍了管理员和最终用户可以对隔离邮件执行的任务。

- [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)：介绍了可用的报告和疑难解答工具。

- [独立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)中的 Exchange 管理中心 ：介绍如何通过 Exchange 管理中心 (EAC) 管理界面访问和导航，以便管理 EOP 服务。

- [Exchange Online Protection PowerShell：](/powershell/exchange/exchange-online-protection-powershell)提供有关远程 PowerShell 的信息，使您可以从命令行管理 EOP 服务。

- [EOP 帮助与支持](help-and-support-for-eop.md) 提供有关获取帮助和技术支持的信息。