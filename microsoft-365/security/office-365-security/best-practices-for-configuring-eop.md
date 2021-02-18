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
description: 请遵循这些针对独立 Exchange Online Protection (EOP) 的最佳实践建议，以便设置成功并避免常见的配置错误。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c64a9592d93ef046ad1c023a49bf378ccf6cf503
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290829"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>配置独立 EOP 的最佳实践

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [独立 Exchange Online Protection](exchange-online-protection-overview.md)

请遵循这些针对独立 Exchange Online Protection (EOP) 的最佳实践建议，以便设置成功并避免常见的配置错误。 参阅本主题的前提是，你已经完成安装过程。 如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。

## <a name="synchronize-recipients"></a>同步收件人

如果组织在本地 Active Directory 环境中具有现有用户帐户，可以将这些帐户同步到云中的 Azure Active Directory。 建议使用目录同步。 若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>推荐设置

我们使安全管理员能够自定义其安全设置，以满足其组织的需要。 尽管一般而言，EOP 和 Microsoft Defender for Office 365 有两个安全级别，我们建议：Standard 和 Strict。 这些设置在 EOP 和 [Microsoft Defender for Office 365 安全推荐设置中列出](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="miscellaneousnon-policy-settings"></a>杂项/非策略设置

这些设置涵盖安全策略之外的一系列功能。

****

|安全功能名称|标准|严格|评论|
|---|---|---|---|
|[设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)|是|是||
|[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)|是|是|用于 `action=quarantine` Standard 和 `action=reject` Strict。|
|部署 [报告邮件外接程序](enable-the-report-message-add-in.md) 或 [报告网络钓鱼外接程序](enable-the-report-phish-add-in.md) ，以改进最终用户对可疑电子邮件的报告|是|是||
|计划恶意软件和垃圾邮件报告|是|是||
|应禁止或监视自动转发到外部域|是|是||
|应启用统一审核|是|是||
|[与邮箱的 IMAP 连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|禁用|禁用||
|[与邮箱的 POP 连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|禁用|禁用||
|经过身份验证的 SMTP 提交|禁用|禁用|POP3 和 IMAP4 (需要经过身份验证的客户端 SMTP 提交（也称为客户端 SMTP 提交或 SMTP AUTH) ）才能发送电子邮件。|
|与邮箱的 EWS 连接|禁用|禁用||
|[PowerShell 连接](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|禁用|禁用|适用于由 [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) cmdlet (返回的用户对象的邮箱用户或) 。|
|使用 [欺骗智能](learn-about-spoof-intelligence.md) 将发件人添加到允许列表|是|是||
|[基于目录的边缘阻止 (DBEB) ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|已启用|已启用|域类型 = 权威|
|[设置所有管理员帐户的多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|已启用|已启用||
|

## <a name="troubleshooting"></a>疑难解答

使用管理中心中的报告解决一般问题和趋势。 使用消息跟踪工具来查找有关邮件的单点数据。 有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。 在安全与合规中心的邮件跟踪中了解有关&[工具。](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>向 Microsoft 报告误报和漏报

为帮助改善服务中针对所有人的垃圾邮件筛选，您应将误报 (报告给标记为错误) 和漏报 (错误电子邮件允许) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则 (也称为传输规则) 或自定义筛选器，以满足业务需求。

在对生产部署新规则时，首先选择测试模式之一，以查看规则的效果。 如果规则能够按照你预期的方式工作，则将规则模式更改为“**强制**”。

在部署新规则时，考虑添加附加操作“生成事件报告”，以监视正在运行的规则。

在组织同时包括本地 Exchange 和 Exchange Online 的混合环境中，请考虑在邮件流规则中使用的条件。 如果希望将规则应用于整个组织，请务必使用本地 Exchange 和 Exchange Online 中可用的条件。 虽然大多数条件在两个环境中都可用，但其中一些条件仅在一个环境中或另一个环境中可用。 有关详细信息，请通过 [邮件流规则 (Exchange Online) 传输规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
