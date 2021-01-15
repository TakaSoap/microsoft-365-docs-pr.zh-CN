---
title: 评估 Microsoft Defender for Office 365
description: 评估模式下的 Defender for Office 365 创建适用于 Office 365 电子邮件策略的 Defender，用于记录裁定（如恶意软件）但不对邮件执行任何操作。
keywords: 评估 Office 365， Microsoft Defender for Office 365， office 365 评估， 试用 office 365， Microsoft Defender， ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8f105215b23ec49318c133714e758e2a2a9c1df
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870917"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>评估 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 评估为公共预览版。 提供此预览版本时没有服务级别协议。 某些功能可能不受支持，或者可能具有受限功能。

执行全面的安全产品评估可帮助你做出有关升级和购买的明智决定。 它有助于试用安全产品的功能，以评估它如何有助于安全运营团队完成日常任务。

[Microsoft Defender for Office 365](office-365-atp.md)评估体验旨在消除设备和环境配置的复杂性，以便你可以专注于评估安全解决方案的功能。 它仅适用于电子邮件保护，不应用于 SharePoint、Office 客户端或 Teams。

如果还没有支持 Microsoft Defender for Office 365 的许可证，可以开始为期 [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 天的免费评估，并测试 Office 365 安全与合规中心&功能 https://protection.office.com/homepage) (。 您将享受快速设置，并在必要时轻松关闭它。

## <a name="how-the-evaluation-works"></a>评估的工作原理

评估模式下的 Defender for Office 365 创建 Office 365 电子邮件策略的 Defender，用于记录裁定（如恶意软件）但不对邮件执行任何操作。 无需更改 MX 记录配置。

使用评估 [模式，将](atp-safe-attachments.md)代表你 [](atp-safe-links.md)设置安全附件、 [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)安全链接和防钓鱼模拟策略。 所有 Defender for Office 365 策略均在后台非强制模式下创建，并且对不可见。

作为设置的一部分，评估模式还配置 [连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 它通过保留 IP 地址和发件人信息来改进筛选准确度，否则当邮件通过 Office 365 的 Defender (ESG) 电子邮件安全网关时，这些邮件会丢失。 增强的筛选功能还可提高 Exchange Online Protection (EOP) 反垃圾邮件和防钓鱼策略的筛选准确度。

为了最大限度地减少对一些不受支持的方案的潜在生产影响，您可以通过创建传输规则将垃圾邮件可信度 (SCL) 设置为 -1 来绕过所有 EOP 筛选。  [有关详细信息，请参阅使用 EAC 创建设置邮件 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)的邮件流   规则。

设置评估模式后，你每天将更新一个报告，其中最多包含 90 天的数据，用于量化实施策略时可能阻止的邮件 (例如删除、发送到垃圾邮件、隔离邮件) 。 针对所有 Defender for Office 365 和 EOP 检测生成报告。 它们根据检测技术聚合 (例如，模拟) ，并可以按时间范围进行筛选。 此外，还可以按需创建邮件报告以创建自定义透视表，或者使用威胁资源管理器深入探究邮件。

借助简化的设置体验，你可以专注于：

- 运行评估
- 获取详细报告
- 分析报告的操作
- 显示评估结果

## <a name="before-you-begin"></a>开始之前

### <a name="licensing"></a>许可

若要访问评估，你将需要满足许可要求。 以下任一许可证都可用：

- Microsoft Defender for Office 365 计划 1
- Microsoft Defender for Office 365 计划 2
- Microsoft 365 E5、Microsoft 365 E5 安全
- Office 365 E5

如果你没有这些许可证之一，则需要获取试用许可证。

#### <a name="trial"></a>试用

若要获取适用于 Office 365 的 Microsoft Defender 的试用许可证，你需要具有帐单管理员 **角色** 或 **全局管理员角色**。 向具有全局管理员角色的某人请求权限。 [了解订阅和许可证](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

获得适当角色后，建议的路径是，通过进入"帐单 > 购买服务"，在 Microsoft 365 管理中心获取适用于 Office 365 (计划 2) 的 Microsoft Defender 试用许可证。 试用版包含 25 个许可证的 30 天免费试用版。 [获取 Microsoft Defender for Office 365 (计划 2) 。 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

你将有一个 30 天的窗口，该窗口的评估用于监视并报告高级威胁。 如果需要完整的 Defender for Office 365 功能，还可以选择购买付费订阅。

### <a name="roles"></a>角色

在评估模式下设置适用于 Office 365 的 Defender 时，需要 Exchange Online 角色。

- [了解 Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [了解如何分配管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

需要以下角色：

|任务|Role|
|---|---|
|获取免费试用版或购买 Microsoft Defender for Office 365 (计划 2) |计费管理员角色或全局管理员角色|
|创建评估策略|远程域和接受域角色;安全管理员角色|
|编辑评估策略|远程域和接受域角色;安全管理员角色|
|删除评估策略|远程域和接受域角色;安全管理员角色 |
|查看评估报告|安全管理员角色或安全读者角色|
|


### <a name="enhanced-filtering"></a>增强的筛选

Exchange Online Protection 策略（如批量和垃圾邮件保护）将保持不变。 邮件传递也保持不变。 但是，该评估将对连接器启用增强的筛选功能，这将影响邮件流和 Exchange Online Protection 策略，除非绕过。

连接器的增强筛选将允许租户使用反欺骗保护。 如果使用电子邮件安全网关 (ESG) 未启用连接器的增强筛选，则不支持反欺骗。

### <a name="urls"></a>URL

URL 将在邮件流期间触发。 如果不希望触发特定 URL，请适当地管理允许的 URL 列表。 有关详细信息 [，请参阅"管理租户允许/阻止列表"](tenant-allow-block-list.md) 中的 URL。

电子邮件正文中的 URL 链接不会换行，以减少客户影响。

### <a name="email-routing"></a>电子邮件路由

准备设置电子邮件当前路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。 如果只是使用 Exchange Online Protection，则没有连接器。 [了解邮件流和电子邮件路由](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

支持的电子邮件路由方案包括：

- **第三方合作伙伴和/或** 本地服务提供商：要评估的入站连接器使用第三方提供商和/或正在使用本地电子邮件安全解决方案。
- **Microsoft Exchange Online保护**：要评估的租户使用 Office 365 进行电子邮件安全保护，邮件 Exchange (MX) 记录指向 Microsoft。

### <a name="email-security-gateway"></a>电子邮件安全网关

如果使用第三方电子邮件安全网关 (ESG) ，则需要知道提供商的名称。 如果你使用的是 ESG 本地或非受支持的供应商，你需要知道设备的公用 IP 地址 () 地址。

受支持的第三方合作伙伴包括：

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- 斯拉多斯
- Symantec
- Trend Micro

### <a name="scoping"></a>界定访问权限

您将能够将评估范围确定为入站连接器。 如果未配置连接器，则评估范围将允许管理员从租户中任何用户收集数据，以评估 Defender for Office 365。

## <a name="get-started-with-the-evaluation"></a>评估入门

在 Office 365 安全与合规中心内查找 Microsoft Defender for Office 365 &设置卡 (https://protection.office.com/homepage) 访问点：

- 威胁管理>仪表板
- 威胁管理>策略
- 报表>仪表板

## <a name="setting-up-the-evaluation"></a>设置评估

启动评估的设置流后，您将获得两个路由选项。 根据组织的邮件路由设置和评估需求，您可以选择是使用第三方和/或本地服务提供商，还是仅使用Microsoft Exchange Online。

- 如果使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。 提供其他与连接器相关的详细信息。

- Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.

查看你的设置并在必要时编辑它们。 然后，选择 **"创建评估"。** 应收到确认消息，指示设置已完成。

Microsoft Defender for Office 365 评估报告每天生成一次。 可能需要最多 24 小时才能填充数据。

### <a name="exchange-rules-optional"></a>Exchange 规则 (可选) 

如果您具有现有网关，您可能需要绕过筛选，因为它将激活连接器的增强筛选并更改传入发件人 IP 地址。 若要绕过，请导航到 Exchange 管理中心，并创建 SCL -1 策略 (如果您还没有 SCL -1) 。 有关规则组件及其工作方式的详细信息，请参阅 Exchange Online (传输规则) 规则。

## <a name="evaluate-capabilities"></a>评估功能

生成评估报告后，查看组织中电子邮件和协作工作区中标识了多少高级威胁链接、高级威胁附件和潜在模拟。

试用版过期后，您可以在 90 天内继续访问报告。 但是，它不会收集更多信息。 如果你想要在试用到期后继续使用适用于 Office 365 的 Microsoft Defender，请确保为 [Microsoft Defender for Office 365 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) (计划 2) 。

你可以 **转到"设置** "以随时更新路由或关闭评估。 但是，如果你决定在关闭评估后继续评估，则需要再次完成相同的设置过程。

## <a name="provide-feedback"></a>提供反馈

你的反馈可帮助我们更好地保护你的环境免受高级攻击。 分享产品功能和评估结果的体验和印象。

选择 **"提供** 反馈"，告诉我们您的想法。
