---
title: 配置 EOP 的最佳实践
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 请遵循这些适用于独立 EOP Exchange Online Protection (的最佳实践) 以便成功设置并避免常见的配置错误。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94586d409d6d8b53ba68c22b6b4f62d2b72266db
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599467"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>配置独立 EOP 的最佳实践

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [Exchange Online Protection独立](exchange-online-protection-overview.md)

请遵循这些适用于独立 EOP Exchange Online Protection (的最佳实践) 以便成功设置并避免常见的配置错误。 参阅本主题的前提是，你已经完成安装过程。 如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。

## <a name="synchronize-recipients"></a>同步收件人

如果组织在本地 Active Directory 环境中具有现有用户帐户，可以将这些帐户同步Azure Active Directory云中。 建议使用目录同步。 若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>推荐设置

我们使安全管理员能够自定义其安全设置，以满足其组织的需求。 尽管一般而言，EOP 和 Microsoft Defender for Office 365安全级别是标准级别和严格级别。 这些设置在[EOP](recommended-settings-for-eop-and-office365.md)和 Microsoft Defender 的推荐设置中Office 365安全。

### <a name="miscellaneousnon-policy-settings"></a>杂项/非策略设置

这些设置涵盖安全策略之外的一系列功能。

<br>

****

|安全功能名称|标准|Strict|评论|
|---|---|---|---|
|[设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)|是|是||
|[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)|是|是|用于 `action=quarantine` Standard 和 `action=reject` Strict。|
|部署[报告邮件外接程序或](enable-the-report-message-add-in.md)[报告网络钓鱼外接程序](enable-the-report-phish-add-in.md)以改进最终用户对可疑电子邮件的报告|是|是||
|计划恶意软件和垃圾邮件报告|是|是||
|应禁止或监视自动转发到外部域|是|是||
|应启用统一审核|是|是||
|[与邮箱的 IMAP 连接](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|已禁用|已禁用||
|[与邮箱的 POP 连接](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|已禁用|已禁用||
|经过身份验证的 SMTP 提交|已禁用|已禁用|生成和发送电子邮件 (POP3 和 IMAP4 客户端以及应用程序和设备需要经过身份验证 (客户端 SMTP 提交或 SMTP AUTH) 。 <p> 有关全局或选择性地启用和禁用 SMTP AUTH 的说明，请参阅在 Exchange Online 中启用或禁用[经过身份验证的客户端 SMTP Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)|
|与邮箱的 EWS 连接|已禁用|已禁用|Outlook使用 Exchange Web 服务进行忙/闲设置、外出设置和日历共享。 如果无法全局禁用 EWS，则有以下选项： <ul><li>如果你 [的客户端](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 支持新式身份验证和新式身份验证，请使用身份验证策略 (EWS) 。</li><li>使用 [客户端访问规则](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 将 EWS 限制为特定用户或源 IP 地址。</li><li>控制全局或每个用户对特定应用程序的 EWS 访问。 有关说明，请参阅[控制对 Exchange 中的 EWS 的访问](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)。</li></ul> <p> 报告[邮件外接程序和](enable-the-report-message-add-in.md)"报告网络钓鱼外接程序[](enable-the-report-phish-add-in.md)"默认在支持的环境中使用 REST，但如果 REST 不可用，将回退到 EWS。 使用 REST 的受支持环境包括：<ul><li>Exchange Online</li><li>Exchange 2019 或 Exchange 2016</li><li>Current Outlook for Windows from a Microsoft 365 subscription or one-time purchase Outlook 2019.</li><li>当前Outlook for Mac 2016 Microsoft 365或更高版本的订阅或一Outlook for Mac购买。</li><li>Outlook for iOS 和 Android</li><li>Outlook 网页版</li></ul>|
|[PowerShell 连接](/powershell/exchange/disable-access-to-exchange-online-powershell)|已禁用|已禁用|适用于由 [Get-User](/powershell/module/exchange/get-user) cmdlet (返回的用户对象的邮箱用户或邮件) 。|
|使用 [欺骗智能](learn-about-spoof-intelligence.md) 将发件人添加到允许列表|是|是||
|[基于目录的边缘阻止 (DBEB) ](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|已启用|已启用|域类型 = 权威|
|[设置所有管理员帐户的多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|已启用|已启用||
|

## <a name="troubleshooting"></a>疑难解答

使用管理中心中的报告解决一般问题和趋势。 使用消息跟踪工具来查找有关邮件的单点数据。 有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。 若要详细了解邮件跟踪工具，请通过安全与合规中心[&跟踪。](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>向 Microsoft 报告误报和漏报

若要帮助改善服务中对所有人的垃圾邮件筛选，应报告误报 (标记为错误) 的误报 (错误电子邮件允许) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则 (也称为传输规则) 筛选器或自定义筛选器以满足您的业务需求。

在对生产部署新规则时，首先选择测试模式之一，以查看规则的效果。 如果规则能够按照你预期的方式工作，则将规则模式更改为“**强制**”。

在部署新规则时，考虑添加附加操作“生成事件报告”，以监视正在运行的规则。

在贵组织同时包括本地 Exchange 和 Exchange Online 混合环境中，请考虑在邮件流规则中使用的条件。 如果希望将规则应用于整个组织，请务必使用本地部署和 Exchange Online 中可用的Exchange条件。 虽然大多数条件在两个环境中都可用，但有些条件仅在一个环境中可用。 有关详细信息，请通过[邮件流规则 (传输规则) 中Exchange Online。](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)