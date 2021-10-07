---
title: 评估 Microsoft Defender for Office 365
description: 评估Office 365 Defender for Office 365创建 Defender，用于记录裁定（如恶意软件）但不对邮件执行任何操作的电子邮件策略。
keywords: 评估 Office 365， Microsoft Defender for Office 365， office 365 评估， 试用 office 365， Microsoft Defender， Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6baa78512b102bae74a242e243c2e4ac023aa4f2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60149572"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>评估 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365评估在公共预览版中。 提供此预览版本时没有服务级别协议。 某些功能可能不受支持，也可能具有受限功能。

执行全面的安全产品评估可帮助你做出有关升级和购买的明智决定。 它有助于试用安全产品的功能，以评估它如何有助于安全运营团队完成日常任务。

[Microsoft Defender for Office 365](defender-for-office-365.md)评估体验旨在消除设备和环境配置的复杂性，以便你可以专注于评估 Microsoft Defender for Office 365。 使用评估模式，可以评估发送到Exchange Online的所有邮件，而无需将 MX 记录指向 Microsoft。 此功能仅适用于电子邮件保护，Office Word、SharePoint 或 Teams。

如果你还没有支持 Microsoft Defender for Office 365 的许可证，可以开始为期[30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)天的免费评估，并测试 Microsoft 365 Defender 门户中的功能 <https://security.microsoft.com> 。 你可以轻松完成快速设置，并在必要时轻松将其关闭。

> [!NOTE]
> 如果你正在 Microsoft 365 Defender 门户 () 中，可以在此处启动 Defender for Office 365 评估：其他部分中的电子邮件 & 协作策略 & 规则威胁策略评估 <https://security.microsoft.com>  \>  \>  \> 模式。

## <a name="how-the-evaluation-works"></a>评估的工作原理

评估Office 365 Defender for Office 365创建 Defender，用于记录裁定（如恶意软件）但不对邮件执行任何操作的电子邮件策略。 无需更改 MX 记录配置。

使用评估模式 [保险箱，保险箱](safe-attachments.md)代表您设置基于 [](safe-links.md)附件、保险箱链接和基于邮箱 [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)智能的模拟策略。 所有 Defender for Office 365 策略均在后台的非强制模式下创建，并且不可见。

作为设置的一部分，评估模式还配置 [连接器的增强筛选](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 它通过保留 IP 地址和发件人信息来提高筛选准确度，否则当邮件通过 Defender for Office 365 前面的电子邮件安全网关 (ESG) 时，这些信息会丢失。 增强的连接器筛选功能还提高了 EOP 现有Exchange Online Protection () 反垃圾邮件和防钓鱼策略的筛选准确度。

增强的连接器筛选可提高筛选准确度，但如果在 Defender for Office 365 前面有 ESG，并且当前未绕过 EOP 筛选，则某些邮件可能会改变可传递性。 影响仅限于 EOP 策略;在Office 365中设置的 Defender for Office 365 策略是在非强制模式下创建的。 为了最大限度地减少潜在的生产影响，您可以通过创建邮件流规则 (也称为传输规则) 来绕过所有 EOP 筛选，将邮件的垃圾邮件可信度 (SCL) 设置为 -1。 有关详细信息[，请参阅](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)使用邮件流规则 (邮件) SCL Exchange Online   SCL 级别。

设置评估模式后，你每天将更新一个报告，其中最多包含 90 天的数据，用于量化实施策略时可能阻止的邮件 (例如，删除、发送到垃圾邮件、隔离) 。 针对所有 Defender 生成针对 Office 365 和 EOP 检测的报告。 它们根据检测技术聚合 (例如，模拟) 并可以按时间范围进行筛选。 此外，还可以按需创建邮件报告，以使用资源管理器创建自定义透视表或深入探究邮件。

借助简化的设置体验，你可以专注于：

- 运行评估
- 获取详细报告
- 分析要操作的报告
- 显示评估结果

## <a name="before-you-begin"></a>准备工作

### <a name="licensing"></a>授权

若要访问评估，你将需要满足许可要求。 以下任一许可证都可用：

- Microsoft Defender for Office 365 计划 1
- Microsoft Defender for Office 365 计划 2
- Microsoft 365 E5、Microsoft 365 E5 安全性
- Office 365 E5

如果你没有这些许可证之一，则需要获取试用许可证。

#### <a name="trial"></a>试用

若要获取 Microsoft Defender for Office 365试用版许可证，你需要具有帐单管理员 **角色或****全局管理员角色**。 向具有全局管理员角色的人请求权限。 [了解订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)

获得适当角色后，建议的路径是，通过进入"帐单">"购买服务"，在 Microsoft 365 管理中心 中获取适用于 Office 365 (计划 2) 的 Microsoft Defender 试用许可证。 试用版包含 25 个许可证的 30 天免费试用版。 [获取 Microsoft Defender for Office 365 (计划 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)试用版。

你将有一个 30 天窗口，其评估用于监视并报告高级威胁。 如果你想要完整的 Defender for Office 365功能，还可以选择购买付费订阅。

### <a name="roles"></a>角色

**Exchange Online评估模式下** 设置 Defender Office 365需要角色。 分配Microsoft 365或安全管理员角色不起作用。

- [了解 Exchange Online](/exchange/permissions-exo/permissions-exo)
- [了解如何分配管理员角色](../../admin/add-users/assign-admin-roles.md)

需要以下角色：

|任务|角色 (角色Exchange Online) |
|---|---|
|获取免费试用版或购买 Microsoft Defender for Office 365 (计划 2) |帐单管理员角色或全局管理员角色|
|创建评估策略|远程域和接受域角色;安全管理员角色|
|编辑评估策略|远程域和接受域角色;安全管理员角色|
|删除评估策略|远程域和接受域角色;安全管理员角色 |
|查看评估报告|安全管理员角色或安全读取者角色|
|

### <a name="enhanced-filtering"></a>增强的筛选

你的Exchange Online Protection策略（如批量和垃圾邮件保护）将保持不变。 但是，该评估将对连接器启用增强的筛选功能，这可能会影响邮件流Exchange Online Protection策略，除非绕过。

连接器的增强筛选允许租户使用反欺骗保护。 如果使用电子邮件安全网关或 ESG (，) 连接器的增强筛选功能，则不支持反欺骗。

### <a name="urls"></a>URL

URL 将在邮件流期间触发。 如果不希望触发特定 URL，请适当地管理允许的 URL 列表。 有关详细信息 [，请参阅管理租户允许/](tenant-allow-block-list.md) 阻止列表。

电子邮件正文中的 URL 链接不会换行，以减少客户影响。

### <a name="email-routing"></a>电子邮件路由

准备设置电子邮件当前路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。 如果您只是使用 Exchange Online Protection，则没有连接器。 [了解邮件流和电子邮件路由](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

支持的电子邮件路由方案包括：

- **第三方合作伙伴和/** 或本地服务提供商：要评估的入站连接器使用第三方提供商和/或你正在使用用于本地电子邮件安全的解决方案。
- **Microsoft Exchange Online保护**：要评估的租户使用 Office 365 用于电子邮件安全，而邮件Exchange (MX) 记录指向 Microsoft。

### <a name="email-security-gateway"></a>电子邮件安全网关

如果使用 ESG (第三方电子邮件安全) ，则需要知道提供商的名称。 如果你使用的是本地或不支持的 ESG 供应商，你需要知道设备的公用 IP 地址 () 地址。

受支持的第三方合作伙伴包括：

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- S一os
- Symantec
- Trend Micro

### <a name="scoping"></a>界定访问权限

你将能够将评估范围确定为入站连接器。 如果未配置连接器，则评估范围将允许管理员从租户中任何用户收集数据，以评估 Defender Office 365。

## <a name="get-started-with-the-evaluation"></a>评估入门

从以下三个Office 365访问点在 Microsoft 365 Defender 门户 () Microsoft Defender <https://security.microsoft.com>) 评估设置卡：

- **终结点** \>**漏洞管理** \>**仪表板** <https://security.microsoft.com/tvm_dashboard> () 
- **电子邮件&协作** \>**策略&规则** \>**威胁策略 ()** <https://security.microsoft.com/threatpolicy>
- **报告** \>**电子邮件&协作** \>**电子邮件&协作报告 ()** <https://security.microsoft.com/emailandcollabreport>

## <a name="setting-up-the-evaluation"></a>设置评估

启动评估设置流后，您将获得两个路由选项。 根据组织的邮件路由设置和评估需求，您可以选择是使用第三方和/或本地服务提供商，还是仅 Microsoft Exchange Online。

- 如果你使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。 提供其他与连接器相关的详细信息。

- 如果Microsoft Exchange Online MX 记录指向 Microsoft，并且你有一个邮箱，请选择"Exchange Online"。

查看设置并在必要时编辑它们。 然后，选择创建 **评估**。 应该会收到一条确认消息，指示设置已完成。

你的 Microsoft Defender for Office 365评估报告每天生成一次。 可能需要 24 小时才能填充数据。

### <a name="exchange-mail-flow-rules-optional"></a>Exchange邮件流规则 (可选) 

如果已有网关，启用评估模式将激活连接器的增强筛选。 此功能通过更改传入发件人 IP 地址提高筛选准确度。 此功能可能会更改筛选裁定，如果您未绕过Exchange Online Protection，则可能会更改某些邮件的可传递性。 在这种情况下，您可能需要暂时绕过筛选来分析影响。 若要绕过筛选，请打开 Exchange 管理中心 (EAC) ，并创建一个邮件流规则，将邮件的 SCL (如果还没有邮件流 <https://admin.exchange.microsoft.com>) 。 有关说明，请参阅[使用邮件流规则将](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)垃圾邮件可信度设置为 (中的) 中的 SCL Exchange Online。

## <a name="evaluate-capabilities"></a>评估功能

生成评估报告后，查看组织中电子邮件和协作工作区中标识了多少高级威胁链接、高级威胁附件和潜在模拟。

试用版过期后，可以在 90 天内继续访问报告。 但是，它不会收集更多信息。 如果你希望在你的试用版过期后继续使用 Microsoft Defender for Office 365，请确保你购买了[Microsoft Defender for Office 365 (计划 2](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)的付费) 。

你可以转到 **"设置"** 以随时更新路由或关闭评估。 但是，如果你决定在关闭评估后继续评估，则需要再次完成相同的设置过程。

## <a name="provide-feedback"></a>提供反馈

你的反馈可帮助我们更好地保护你的环境免受高级攻击。 分享产品功能和评估结果的体验和印象。

选择 **"提供** 反馈"，告诉我们您的想法。
