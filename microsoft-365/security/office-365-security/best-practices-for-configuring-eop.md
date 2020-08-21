---
title: 配置 EOP 的最佳实践
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 请遵循这些针对独立 Exchange Online Protection (EOP) 最佳做法，以成功达到上述要求，并避免常见的配置错误。
ms.openlocfilehash: eb8e4aff765fbc1ab13c603f32ca0af51f87a4ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827661"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>配置独立 EOP 的最佳实践

请遵循这些针对独立 Exchange Online Protection (EOP) 最佳做法，以成功达到上述要求，并避免常见的配置错误。 参阅本主题的前提是，你已经完成安装过程。 如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。

## <a name="synchronize-recipients"></a>同步收件人

如果你的组织在本地 Active Directory 环境中拥有现有用户帐户，你可以将这些帐户同步到云中的 Azure Active Directory。 建议使用目录同步。 若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>推荐设置

我们为安全管理员自定义其安全设置，以满足其组织的需要。 虽然一般情况下，我们建议在 EOP 和 Office 365 ATP 中有两种安全级别：标准和严格安全级别。 这些设置在 EOP 和 [Office 365 ATP 安全的推荐设置中列出](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="miscellaneousnon-policy-settings"></a>其他/非策略设置

这些设置涵盖一系列不在安全策略的功能。

****

|安全功能名称|Standard|严格|评论|
|---|---|---|---|
|[设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)|是|是||
|[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)|是|是|用于 `action=quarantine` Standard 和 `action=reject` Strict。|
|部署 [报告邮件加载项](enable-the-report-message-add-in.md) 以改进最终用户报告可疑电子邮件|是|是||
|Schedule Malware and Spam Reports|是|是||
|应不允许或监控自动转发到外部域|是|是||
|应启用统一审核|是|是||
|[IMAP 与邮箱的连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|禁用|禁用||
|[与邮箱的 POP 连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|禁用|禁用||
|通过身份验证的 SMTP 提交|禁用|禁用|通过身份验证的客户端 SMTP (使用客户端 SMTP 提交或 SMTP AUTH) ，POP3 和 IMAP4 客户端需要发送电子邮件。|
|EWS 与邮箱的连接|禁用|禁用||
|[PowerShell 连接性](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|禁用|禁用|可用于邮箱用户或邮件用户 ([Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) cmdlet 返回的用户) 。|
|[使用反欺骗智能](learn-about-spoof-intelligence.md)保护将发件人添加到允许列表|是|是||
|[基于目录的边缘阻止 (DBEB) ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|已启用|已启用|域类型 = 权威|
|[为所有管理员帐户设置多重身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|已启用|已启用||
|

## <a name="troubleshooting"></a>故障排除

查看有关使用管理中心中的报告的常见问题和趋势的故障。 使用消息跟踪工具来查找有关邮件的单点数据。 有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。 安全与合规中心内的消息[跟踪中的消息跟踪&工具。](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>向 Microsoft 报告误报和漏报

为了帮助改善面向所有人的服务中的垃圾邮件筛选，您应向 microsoft 报告标记 (为错误) 错误) 的误报和漏报 (电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则 (规则或自定义) 筛选器，满足你的业务需求。

在对生产部署新规则时，首先选择测试模式之一，以查看规则的效果。 如果规则能够按照你预期的方式工作，则将规则模式更改为“**强制**”。

在部署新规则时，考虑添加附加操作“生成事件报告”****，以监视正在运行的规则。

在您的组织同时包含内部部署 Exchange 和 Exchange Online 的混合环境中，考虑您在邮件流规则中使用的条件。 如果希望将规则应用于整个组织，请务必使用本地 Exchange 和 Exchange Online 中均可用的条件。 虽然大多数条件都可在两个环境中使用，但其中一些条件只在一个环境或其他环境中可用。 在 [Exchange Online 中， (邮件流规则) 规则的详细信息](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
