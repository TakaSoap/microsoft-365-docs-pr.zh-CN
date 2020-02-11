---
title: 配置 EOP 和 Office 365 ATP 的最佳实践
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。
ms.openlocfilehash: b4b1f02e3b034b7e89d605a2164b6add3f20dae5
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887299"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>配置 EOP 和 Office 365 ATP 的最佳实践

请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。 参阅本主题的前提是，你已经完成安装过程。 如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。

## <a name="synchronize-recipients"></a>同步收件人

如果您的组织在本地 Active Directory 环境中有现有的用户帐户，则可以将这些帐户同步到云中的 Azure Active Directory。 建议使用目录同步。 若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>推荐设置

我们为安全管理员自定义安全设置以满足其组织的需求。 尽管作为一般规则，我们建议的 EOP 和 Office 365 ATP 中有两个安全级别：标准和严格。 这些设置在[EOP 和 Office 365 ATP security 的推荐设置](recommended-settings-for-eop-and-office365-atp.md)中列出。

### <a name="miscellaneousnon-policy-settings"></a>杂项/非策略设置

这些设置涵盖了安全策略之外的一系列功能。

|安全功能名称|标准|全|评论|
|---------|---------|---------|---------|
|[在 Office 365 中设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)|是|是||
|[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)|是|是|对 Standard 使用 action = 隔离，对 Strict 执行 action = 拒绝。|
|部署报告邮件加载项以改进最终用户报告可疑电子邮件的情况|是|是||
|安排恶意软件和垃圾邮件报告|是|是||
|自动转发到外部域应为 "允许" 或 "受监视"|是|是||
|应启用统一审核|是|是||
|[IMAP 到邮箱的连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disabled|Disabled||
|[到邮箱的 POP 连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disabled|Disabled||
|对邮箱的 SMTP 已验证的提交|Disabled|Disabled||
|到邮箱的 EWS 连接|Disabled|Disabled||
|[PowerShell 连接](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Disabled|Disabled|适用于邮箱用户或邮件用户（由[获取用户](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)cmdlet 返回的用户对象）。|
|尽可能使用欺骗智能白名单发件人|是|是||
|基于目录的边缘阻止（DBEB）|已启用|已启用|域类型 = 权威|
|[为所有管理员帐户设置多重身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|已启用|已启用||

## <a name="troubleshooting"></a>故障排除

使用管理中心中的报告解决一般问题和趋势。 使用消息跟踪工具来查找有关邮件的单点数据。 有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。 有关详细信息，请参阅[安全性 & 合规性中心中的邮件跟踪中](message-trace-scc.md)的邮件跟踪工具。

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>向 Microsoft 报告误报和假负整数

管理员应通过我们的管理员提交门户将漏报（垃圾邮件）和误报（非垃圾邮件）提交给 Microsoft。 可以提交电子邮件、文件和 Url，以帮助管理员确定我们为什么传递或未将邮件传递给最终用户。 有关详细信息，请参阅[如何将可疑垃圾邮件、网络钓鱼、url 和文件提交到 Microsoft For Office 365 扫描](admin-submission.md)。

最终用户还可以直接将漏报（垃圾邮件）和误报（非垃圾邮件）报告给 Microsoft，以便在 verdicts 时对其进行不同意的分析。 有关详细信息，请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则或自定义筛选器以满足您的业务需求。

在对生产部署新规则时，首先选择测试模式之一，以查看规则的效果。 如果规则能够按照你预期的方式工作，则将规则模式更改为“**强制**”。

在部署新规则时，考虑添加附加操作“生成事件报告”****，以监视正在运行的规则。

在组织同时包括本地 Exchange 和 Office 365 的混合环境中，请考虑在邮件流规则中使用的条件。 如果要将规则应用于整个组织，请务必使用内部部署 Exchange 和 Office 365 中提供的条件。 虽然大多数条件在这两个环境中都可用，但只有一个环境或另一个环境中提供了一些。 有关详细信息，请参阅[Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
