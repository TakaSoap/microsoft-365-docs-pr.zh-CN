---
title: 配置 EOP 的最佳实践
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 请遵循这些有关独立 Exchange Online Protection (EOP) 的最佳实践建议，以便自己设置成功并避免常见配置错误。
ms.openlocfilehash: b734fe87b82c243531944bbd9cf53d22d5b42f53
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414030"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>配置独立 EOP 的最佳实践

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


请遵循这些有关独立 Exchange Online Protection (EOP) 的最佳实践建议，以便自己设置成功并避免常见配置错误。 参阅本主题的前提是，你已经完成安装过程。 如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。

## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。

## <a name="synchronize-recipients"></a>同步收件人

如果您的组织在本地 Active Directory 环境中有现有的用户帐户，则可以将这些帐户同步到云中的 Azure Active Directory。 建议使用目录同步。 若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。

## <a name="recommended-settings"></a>推荐设置

我们为安全管理员自定义安全设置以满足其组织的需求。 尽管作为一般规则，我们建议的 EOP 和 Office 365 ATP 中有两个安全级别：标准和严格。 这些设置在 [EOP 和 Office 365 ATP security 的推荐设置](recommended-settings-for-eop-and-office365-atp.md)中列出。

### <a name="miscellaneousnon-policy-settings"></a>杂项/非策略设置

这些设置涵盖了安全策略之外的一系列功能。

****

|安全功能名称|标准|全|评论|
|---|---|---|---|
|[设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)|是|是||
|[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)|是|是|对 `action=quarantine` 标准和 `action=reject` 进行严格使用。|
|部署 [报告邮件加载项](enable-the-report-message-add-in.md) 以改进对可疑电子邮件的最终用户报告|是|是||
|安排恶意软件和垃圾邮件报告|是|是||
|自动转发到外部域应为 "允许" 或 "受监视"|是|是||
|应启用统一审核|是|是||
|[IMAP 到邮箱的连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disabled|Disabled||
|[到邮箱的 POP 连接](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disabled|Disabled||
|已通过身份验证的 SMTP 提交|Disabled|Disabled|已通过身份验证的客户端 SMTP 提交 (POP3 和 IMAP4 客户端在发送电子邮件时，也称为客户端 SMTP 提交或 SMTP 身份验证) 。|
|到邮箱的 EWS 连接|Disabled|Disabled||
|[PowerShell 连接](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Disabled|Disabled|适用于邮箱用户或邮件用户 (由) [用户](https://docs.microsoft.com/powershell/module/exchange/get-user) cmdlet 返回的用户对象。|
|使用 [欺骗智能](learn-about-spoof-intelligence.md) 将发件人添加到允许列表中|是|是||
|[基于目录的边缘阻止 (DBEB) ](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|已启用|已启用|域类型 = 权威|
|[为所有管理员帐户设置多重身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|已启用|已启用||
|

## <a name="troubleshooting"></a>疑难解答

使用管理中心中的报告解决一般问题和趋势。 使用消息跟踪工具来查找有关邮件的单点数据。 有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。 有关详细信息，请参阅 [安全性 & 合规性中心中的邮件跟踪中](message-trace-scc.md)的邮件跟踪工具。

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>向 Microsoft 报告误报和假否定

若要帮助提高每个人的服务中的垃圾邮件筛选功能，应报告误报 (电子邮件被标记为错误的) 和漏报 (错误的电子邮件) Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则 (也称为传输规则) 或自定义筛选器来满足您的业务需求。

在对生产部署新规则时，首先选择测试模式之一，以查看规则的效果。 如果规则能够按照你预期的方式工作，则将规则模式更改为“**强制**”。

在部署新规则时，考虑添加附加操作“生成事件报告”****，以监视正在运行的规则。

在组织同时包括本地 Exchange 和 Exchange Online 的混合环境中，请考虑在邮件流规则中使用的条件。 如果要将规则应用于整个组织，请务必使用内部部署 Exchange 和 Exchange Online 中提供的条件。 虽然大多数条件在这两个环境中都可用，但只有一个环境或另一个环境中提供了一些。 有关详细信息，请参阅 [邮件流规则 (传输规则) Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
