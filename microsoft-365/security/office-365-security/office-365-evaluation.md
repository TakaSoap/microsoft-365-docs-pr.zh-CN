---
title: 评估 Microsoft Defender for Office 365
description: 评估模式下的 Office 365 的 defender 为 Office 365 电子邮件策略创建了用于记录 verdicts 的 Defender，如恶意软件，但不对邮件执行操作。
keywords: 评估 Office 365、Microsoft Defender for Office 365、Office 365 评估、试用 Office 365、Microsoft Defender、ATP
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
ms.openlocfilehash: b5b095a1d75ead0f963a71d816e7d879b7cd3697
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614794"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>评估 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 评估 Microsoft Defender for Office 365 将很快处于公共预览版中。 提供此预览版本时没有服务级别协议。 某些功能可能不受支持或可能具有受约束的功能。

进行全面的安全产品评估有助于向您提供有关升级和购买的有根据的决策。 它有助于试用安全产品的功能，以评估如何帮助安全操作团队在日常任务中进行评估。

[Microsoft Defender For Office 365](office-365-atp.md)评估体验旨在消除设备和环境配置的复杂性，这样您就可以专注于评估安全解决方案的功能。 它仅适用于电子邮件保护，而不适用于 SharePoint、Office 客户端或团队。

如果你还没有支持 Microsoft Defender for Office 365 的许可证，你可以开始 [30 天免费评估](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) ，并在 Office 365 安全性 & 合规性中心 (中测试功能 https://protection.office.com/homepage) 。 你将喜欢快速设置，如果需要，你可以轻松地将其关闭。

## <a name="how-the-evaluation-works"></a>评估的工作方式

评估模式下的 Office 365 的 defender 为 Office 365 电子邮件策略创建了用于记录 verdicts 的 Defender，如恶意软件，但不对邮件执行操作。 您无需更改 MX 记录配置。

使用评估模式时，将代表你设置 [安全附件](atp-safe-attachments.md)、 [安全链接](atp-safe-links.md)和 [反钓鱼网络模拟策略](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。 所有适用于 Office 365 的 Defender 策略都是在后台非强制模式下创建的，对你不可见。

在设置过程中，评估模式还会为 [连接器配置增强的筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 它通过保留 IP 地址和发件人信息来提高筛选准确性，当邮件通过电子邮件安全网关 (ESG) 在 Office 365 的前端中时，这些信息将会丢失。 这还提高了 Exchange Online Protection (EOP) 反垃圾邮件和反网络钓鱼策略的筛选准确性。

若要最大限度地减少对某些不受支持的方案的潜在生产影响，可以通过创建传输规则来将垃圾邮件可信度 (SCL) 设置为-1，从而绕过所有 EOP 筛选。 有关详细信息，请参阅 [使用 EAC 创建邮件流规则，以设置邮件的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   。

在设置评估模式时，将每日更新一次，最长可达90天的数据量化量化邮件已被阻止的邮件已被阻止，并已实施了策略 (例如，删除、发送到垃圾邮件、隔离) 。 为所有 Defender for Office 365 和 EOP 检测生成报告。 它们按检测技术进行聚合 (例如，模拟) 并可按时间范围进行筛选。 此外，还可以按需创建邮件报告，以使用威胁资源管理器创建自定义透视或深入研究邮件。

使用简化的设置体验，您可以重点关注：

- 运行评估
- 获取详细报告
- 分析报告的操作
- 展示评估结果

## <a name="before-you-begin"></a>准备工作

### <a name="licensing"></a>许可

若要访问评估版，你需要满足许可要求。 以下任何许可证都将生效：

- Microsoft Defender for Office 365 计划1
- Microsoft Defender for Office 365 计划2
- Microsoft 365 E5，Microsoft 365 E5 安全
- Office 365 E5

如果你没有这些许可证中的任何一个，则需要获取试用许可证。

#### <a name="trial"></a>试用

若要获取 Microsoft Defender for Office 365 试用版许可证，您需要具有 " **记帐管理员" 角色** 或 " **全局管理员" 角色**。 向具有全局管理员角色的用户请求权限。 [了解订阅和许可证](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

拥有适当的角色后，推荐的路径是获取 Microsoft 365 管理中心内的 Microsoft Defender for Office 365 的试用许可证，方法是转到帐单 > 购买服务 (计划 2) 。 试用版包括30天免费试用版，25个许可证。 [获取 Microsoft Defender For Office 365 (Plan 2) 试用版 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

你将有一个为期30天的窗口，评估版将对高级威胁进行监控和报告。 如果你想要使用完整的 Defender for Office 365 功能，你也可以选择购买付费订阅。

### <a name="roles"></a>角色

Exchange Online 角色是在评估模式下设置适用于 Office 365 的 Defender 所必需的。 以下角色是必需的：

|任务|Role|
|---|---|
|获取免费试用版或购买 Microsoft Defender for Office 365 (Plan 2) |帐单管理员角色或全局管理员角色|
|创建评估策略|远程和接受域角色;安全管理员角色|
|编辑评估策略|远程和接受域角色;安全管理员角色|
|删除评估策略|远程和接受域角色;安全管理员角色 |
|查看评估报告|安全管理员角色或安全读者角色|
|

### <a name="enhanced-filtering"></a>增强的筛选

您的 Exchange Online Protection 策略（如批量和垃圾邮件保护）将保持不变。 邮件传递也将保持不变。 但是，此评估会对连接器启用增强型筛选，这将影响您的邮件流和 Exchange Online Protection 策略，除非被绕过。

连接器的增强型筛选功能将允许租户使用反欺骗保护。 如果使用的是电子邮件安全网关 (ESG) 而无需启用对连接器的增强筛选，则不支持反欺骗。

### <a name="urls"></a>URL

在邮件流过程中，将触发 Url。 如果不想让特定 Url 触发，请相应地管理允许的 Url 列表。 有关详细信息，请参阅 [管理租户允许/阻止列表中的 url](tenant-allow-block-list.md) 。

电子邮件正文中的 URL 链接不会换行，以减少客户影响。

### <a name="email-routing"></a>电子邮件路由

您需要准备设置您的电子邮件当前的路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。 如果只使用 Exchange Online Protection，则不会有连接器。 [了解有关邮件流和电子邮件路由的信息](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

支持的电子邮件路由方案包括：

- **第三方合作伙伴和/或本地服务提供商**：要评估的入站连接器使用第三方提供程序，或使用的是本地电子邮件安全解决方案的解决方案。
- **仅 Microsoft Exchange Online Protection**：要评估的租户使用 Office 365 for email Security 和 Mail EXCHANGE (MX) 记录指向 Microsoft。

### <a name="email-security-gateway"></a>电子邮件安全网关

如果使用的是第三方电子邮件安全网关 (ESG) ，则需要知道提供商的名称。 如果您使用的是 ESG 内部部署或不受支持的供应商，您需要知道这些设备 (es) 的公用 IP 地址。

支持的第三方合作伙伴包括：

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- 趋势微

### <a name="scoping"></a>界定访问权限

您将能够将评估范围限定为入站连接器。 如果未配置任何连接器，则评估范围将允许管理员从租户中的任何用户收集数据，以评估 Office 365 的 Defender。

## <a name="get-started-with-the-evaluation"></a>评估入门

在 Office 365 安全性 & 合规性中心 (https://protection.office.com/homepage) 从三个接入点中查找 Microsoft Defender For office 365 评估设置卡：

- > 仪表板的威胁管理
- 威胁管理 > 策略
- 报表 > 仪表板

## <a name="setting-up-the-evaluation"></a>设置评估

启动评估的设置流程后，您将获得两个路由选项。 根据组织的邮件路由设置和评估需求，您可以选择使用的是第三方和/或本地服务提供商还是仅使用 Microsoft Exchange Online。

- 如果使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。 提供其他与连接器有关的详细信息。

- 如果 MX 记录指向 Microsoft 并拥有 Exchange Online 邮箱，请选择 "Microsoft Exchange Online"。

查看您的设置并根据需要进行编辑。 然后，选择 " **创建评估**"。 您应该会收到一条确认消息，指示您的设置已完成。

Microsoft Defender for Office 365 评估报告每天生成一次。 可能需要长达24小时才能填充数据。

### <a name="exchange-rules-optional"></a>Exchange 规则 (可选) 

如果您有一个现有的网关，则可能需要绕过筛选，因为它将激活连接器的增强筛选并更改传入发件人的 IP 地址。 若要绕过，请导航到 Exchange 管理中心并创建 SCL-1 (的策略（如果尚没有) ）。 有关规则组件及其工作方式的详细信息，请参阅 Mail flow rules (transport rules) in Exchange Online。

## <a name="evaluate-capabilities"></a>评估功能

生成评估报告后，请参阅组织中的电子邮件和协作工作区中确定了多少高级威胁链接、高级威胁附件和潜在 impersonations。

试用期到期后，你可以继续访问90天的报告。 但是，它不会收集任何详细信息。 如果你想要在试用期过期后继续使用 Microsoft Defender for Office 365，请确保 [购买付费订阅 For Microsoft defender For office 365 (Plan 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

你可以转到 " **设置** " 以更新你的路由或在任何时候关闭评估。 但是，如果决定在关闭后继续进行评估，则需要再次执行相同的设置过程。

## <a name="provide-feedback"></a>提供反馈

你的反馈有助于我们更好地保护你的环境免受高级攻击。 分享产品功能和评估结果的体验和印象。

选择 " **提供反馈** "，让我们知道你的想法。
