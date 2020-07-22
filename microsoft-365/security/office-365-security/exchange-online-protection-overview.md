---
title: Exchange Online Protection （EOP）概述
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 了解 Exchange Online Protection （EOP）如何帮助保护您的内部部署电子邮件组织在独立和混合环境中。
ms.openlocfilehash: 37b38df9e94bee93202be02c01a220afa9470b8a
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204799"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概述

Exchange Online Protection （EOP）是基于云的筛选服务，可帮助组织抵御垃圾邮件和恶意软件。 EOP 包含在具有 Exchange Online 邮箱的所有 Microsoft 365 组织中。

但是，在以下本地方案中也可以使用 EOP：

- **在独立方案中**： EOP 为您的内部部署 Exchange 组织或任何其他内部部署 SMTP 电子邮件解决方案提供基于云的电子邮件保护。

- **在混合部署中**：在混合使用内部部署和云邮箱时，可以将 EOP 配置为保护您的电子邮件环境并控制邮件路由。

在这些方案中，EOP 可简化电子邮件环境的管理，并缓解维护内部部署硬件和软件带来的许多负担。

本主题的其余部分将介绍 EOP 在独立和混合环境中的工作方式。

## <a name="how-eop-works"></a>EOP 如何工作

了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：

![电子邮件流程图](../../media/emailprocessingineop1.png)

- 传入邮件最初通过连接筛选，它会检查发件人的信誉并检查邮件中是否存在恶意软件。 大多数垃圾邮件在这时就会被 EOP 阻止并删除。 有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。

- 邮件将继续通过策略筛选，其中将根据您从模板创建或实施的自定义邮件流规则（也称为传输规则）对邮件进行评估。 例如，你可以将规则设置为当收到来自特定发件人的邮件时向管理器发送通知。 数据丢失防护（DLP）检查在此点也会发生（Exchange Enterprise CAL with Services）。

- 接下来，邮件通过反垃圾邮件筛选（也称为内容筛选）传递。 确定为垃圾邮件的邮件可以发送到用户的 "垃圾邮件" 文件夹或 "隔离"，以及其他选项。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 在邮件成功传递所有这些保护层后，会将其传递给收件人。

有关详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="eop-datacenters"></a>EOP 数据中心

EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。 例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。 每个数据中心中的服务器代表您接受邮件，提供组织和 internet 之间的一层隔离，从而减少服务器上的负载。 通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。

EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：

- 在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。

- 在亚太地区（APAC）中，所有 Exchange Online 邮箱均位于 APAC 数据中心中，并且邮件当前通过 APAC 数据中心路由以进行 EOP 筛选。

- 在美洲，服务分布在以下位置：

  - 南美洲： Exchange Online 邮箱位于巴西和智利的数据中心。 所有邮件通过本地数据中心路由，以进行 EOP 筛选。 隔离的邮件存储在租户所在的数据中心中。

  - 加拿大： Exchange Online 邮箱位于加拿大的数据中心。 所有邮件通过本地数据中心路由，以进行 EOP 筛选。 隔离的邮件存储在租户所在的数据中心中。

  - 美国： Exchange Online 邮箱位于美国数据中心。 所有邮件通过本地数据中心路由，以进行 EOP 筛选。 隔离的邮件存储在租户所在的数据中心中。

- 对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>适用于内部部署电子邮件组织的 EOP 计划和功能

可用的 EOP 订阅计划包括：

- **EOP 独立**：在 EOP 中注册以保护您的内部部署电子邮件组织。

- **Exchange online 中的 EOP 功能**：包括 exchange online 的任何订阅（独立的或作为 Microsoft 365 的一部分）使用 EOP 来保护 Exchange Online 邮箱。

- **Exchange ENTERPRISE cal With services**：如果您有一个内部部署 exchange 组织，并且您已使用这些服务许可证购买了其他 Exchange 企业版 cal，则 EOP 是所包含服务的一部分。

有关跨所有 EOP 订阅计划的要求、重要限制和功能可用性的信息，请参阅[Exchange Online Protection 服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>为内部部署电子邮件组织设置 EOP

设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。

如果您已购买 EOP，请参阅 [设置 EOP 服务](set-up-your-eop-service.md)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。

## <a name="eop-help-for-admins"></a>管理员的 EOP 帮助

针对 EOP 管理员的帮助内容包括以下顶级类别：

- [Exchange Online Protection 概述](exchange-online-protection-overview.md)：介绍 EOP 如何工作，并提供其他信息的链接。

- [EOP 功能](eop-features.md)：提供 EOP 中可用的功能列表。

- [设置 EOP 服务](set-up-your-eop-service.md)：提供有关设置 EOP 服务的步骤，以及指向其他信息的链接。

- [从 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort 切换到 EOP](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)：介绍了从其他电子邮件保护产品切换到 EOP 的过程。

- [在独立 EOP 中管理收件人](manage-recipients-in-eop.md)：介绍如何在 EOP 中管理邮件用户和组。

- [EOP 中的邮件流](mail-flow-in-eop.md)：介绍如何使用连接器配置自定义邮件流方案、如何管理与服务关联的域以及如何启用基于目录的边缘阻止（DBEB）功能。

- [配置 EOP 的最佳实践](best-practices-for-configuring-eop.md)：介绍了在设置和设置服务后建议的配置设置和注意事项。

- [独立 EOP 中的审核报告](auditing-reports-in-eop.md)：介绍如何使用审核报告跟踪对服务的配置更改。

- [EOP 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)：介绍垃圾邮件筛选和恶意软件筛选，并演示如何对它们进行自定义以最大限度地满足组织的需求。 还介绍了管理员和最终用户可以对隔离邮件执行的任务。

- [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)：介绍了可用的报告和故障排除工具。

- [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)：介绍如何通过 exchange 管理中心（EAC）管理界面访问和导航，以管理您的 EOP 服务。

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)：提供有关远程 PowerShell 的信息，该信息允许您从命令行管理 EOP 服务。

- [EOP 帮助与支持](help-and-support-for-eop.md) 提供有关获取帮助和技术支持的信息。
