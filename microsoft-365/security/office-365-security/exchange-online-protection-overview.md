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
description: 了解Exchange Online Protection (EOP) 如何在独立和混合环境中帮助保护本地电子邮件组织。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624715"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 是基于云的筛选服务，可帮助保护组织免受垃圾邮件、恶意软件和其他电子邮件威胁的攻击。 EOP 包含在具有邮箱Microsoft 365的所有Exchange Online中。

本文的其余部分介绍了 EOP 的工作原理。

> [!NOTE]
> EOP 本身还可用于保护内部部署邮箱和混合环境，以保护内部部署Exchange邮箱。 有关详细信息，[请参阅独立](/exchange/standalone-eop/standaonline-eop)Exchange Online Protection。

## <a name="how-eop-works"></a>EOP 如何工作

了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="在垃圾邮件或隔离裁定之前，通过 Connection、Anti-malware、Mailflow Rules-slash-Policy Filtering 和 Content Filtering 从 Internet 或客户反馈传递到 EOP 的电子邮件的图形。":::

- 传入邮件进入 EOP 时，最初会通过连接筛选，这将检查发件人的信誉。 大多数垃圾邮件此时停止，并遭 EOP 拒绝。 有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。

- 然后检查邮件是否有恶意软件。 如果在邮件或附件中发现恶意软件， (邮件) 仅路由到管理员隔离存储。 若要了解有关恶意软件保护的更多信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。

- 邮件将继续通过策略筛选，其中根据自定义邮件流规则（也称为 (模板创建) 强制实施的传输规则）评估邮件。 例如，你可以将规则设置为当收到来自特定发件人的邮件时向管理器发送通知。 此时， (CAL with Services) 也会进行数据丢失防护 (Exchange Enterprise DLP) 。

- 接下来，邮件通过反垃圾邮件筛选，其中邮件会检查垃圾邮件、网络钓鱼或批量电子邮件。 检测到的邮件可以发送到隔离邮箱或用户的"垃圾邮件"文件夹以及其他选项。 有关详细信息，请参阅[配置反垃圾邮件策略和](configure-your-spam-filter-policies.md)[配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

任何成功通过所有这些保护层的邮件将传递给收件人。

有关详细信息，请参阅电子邮件 [保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>内部部署电子邮件组织的 EOP 计划和功能

可用的 EOP 订阅计划包括：

- **独立 EOP：** 注册 EOP 以保护本地电子邮件组织。

- **eOP features in Exchange Online**： Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.

- **Exchange Enterprise CAL with Services：** 如果你有一个本地 Exchange 组织，你已购买其他 Exchange Enterprise CAL with Services 许可证，则 EOP 是所包括服务的一部分。

有关所有 EOP 订阅计划的要求、重要限制以及功能可用性的信息，请参阅Exchange Online Protection[说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

> [!NOTE]
> 如果您拥有包含Microsoft 365或Office 365邮箱的 Exchange Online 订阅，则具有 EOP。 有关在订阅中设置 EOP 安全功能的步骤，以及 Microsoft Defender for Office 365 订阅可为您提供的附加安全性的信息，请参阅[防止威胁](protect-against-threats.md)。 有关用于设置的 EOP 功能的建议设置，可以在[EOP](recommended-settings-for-eop-and-office365.md)和 Microsoft Defender 的推荐设置中Office 365安全。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>为内部部署电子邮件组织设置 EOP

设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。

如果您已购买 EOP，请参阅 [设置 EOP 服务](/exchange/standalone-eop/set-up-your-eop-service)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。

### <a name="eop-datacenters"></a>EOP 数据中心

EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。 例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。 每个数据中心中的服务器代表您接受邮件，从而在您的组织和 Internet 之间提供一个分隔层，从而减少服务器的负载。 通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。

EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：

- 在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。
- 在 Asia-Pacific (APAC) 中，Exchange Online邮箱都位于 APAC 数据中心，并且邮件当前通过 APAC 数据中心路由，用于 EOP 筛选。
- 在美洲，服务分布在以下位置：
  - 南非：Exchange Online邮箱位于巴西和智利的数据中心。 所有邮件均通过本地数据中心进行 EOP 筛选。 隔离邮件存储在租户所在的数据中心中。
  - 加拿大：Exchange Online位于加拿大的数据中心。 所有邮件均通过本地数据中心进行 EOP 筛选。 隔离邮件存储在租户所在的数据中心中。
  - 美国：Exchange Online邮箱位于美国数据中心。 所有邮件均通过本地数据中心进行 EOP 筛选。 隔离邮件存储在租户所在的数据中心中。
- 对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。

## <a name="eop-help-for-admins"></a>EOP 管理员帮助

针对 EOP 管理员的帮助内容包括以下顶级类别：

- 为 Microsoft Defender for Office 365 管理员配置[EOP，第 1](protect-against-threats.md)天：在 Microsoft Defender 的核心为 Office 365 配置 EOP 保护和Office 365。

- [EOP 功能](eop-features.md)：提供 EOP 中提供的功能列表。

- [设置 EOP 服务](/exchange/standalone-eop/set-up-your-eop-service)：提供设置 EOP 服务的步骤，以及指向其他信息的链接。

- [从 Google Postini、Barracuda 垃圾邮件和](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)病毒防火墙或 Cisco IronPort 切换到 EOP：介绍从另一个电子邮件保护产品切换到 EOP 的过程。

- [在独立 EOP 中管理](/exchange/standalone-eop/manage-recipients-in-eop)收件人：介绍如何在独立 EOP 中管理邮件用户和组。

- [EOP](mail-flow-in-eop.md)中的邮件流：介绍如何使用连接器配置自定义邮件流方案，如何管理与服务关联的域，以及如何启用基于目录的边缘阻止 (DBEB) 功能。

- [EOP 和 Microsoft Defender Office 365](recommended-settings-for-eop-and-office365.md)安全建议设置：介绍设置和预配服务后的建议配置设置和注意事项。

- [审核报告中Exchange Online：](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)介绍如何使用审核报告跟踪对服务的配置更改。

- [EOP 中的](anti-spam-and-anti-malware-protection.md)反垃圾邮件和反恶意软件保护：介绍垃圾邮件筛选和恶意软件筛选，并演示如何自定义它们以最好地满足组织的需求。 还介绍了管理员和最终用户可以对隔离邮件执行的任务。

- [reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)： Describes the reports and troubleshooting tools that are available.

- [Exchange](/exchange/exchange-admin-center)[独立 EOP](/exchange/standalone-eop/exchange-admin-center-eop)中的 Exchange Online 管理中心或 Exchange 管理中心 ：介绍如何访问和导航 Exchange 管理中心 (EAC) 管理界面，以便管理相关的 EOP 功能。

- [Exchange Online Protection PowerShell：](/powershell/exchange/exchange-online-protection-powershell)提供有关远程 PowerShell 的信息，通过远程 PowerShell，你可以从命令行管理 EOP 服务。

- [EOP 帮助与支持](help-and-support-for-eop.md) 提供有关获取帮助和技术支持的信息。