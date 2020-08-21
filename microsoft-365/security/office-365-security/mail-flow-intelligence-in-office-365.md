---
title: 邮件流智能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解使用连接器服务与邮件传递关联的错误代码 (，也称为邮件流智能) 。
ms.openlocfilehash: b345b52f572efca2aca1fde6ba720d733e521cc4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827709"
---
# <a name="mail-flow-intelligence-in-eop"></a>EOP 中的邮件流智能

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，通常可以使用连接器将电子邮件从 EOP 路由到内部部署电子邮件环境。 您还可以使用连接器将来自 Microsoft 365 的邮件路由到合作伙伴组织。 当 Microsoft 365 无法通过连接器传递这些邮件时，它们会在 Microsoft 365 中排队。 Microsoft 365 将继续 24 小时对每封邮件重试传递。 24 小时之后，排队邮件将过期，并且邮件将以未送达报告 (也称为 NDR 或退回邮件未送达邮件类型退回) 。

当邮件无法使用连接器传递时，Microsoft 365 将生成错误。 本主题对最常见的错误及其解决方案进行了描述。 通过连接器发送的无法送达邮件的队列和通知错误集中称为 _邮件流智能_。

## <a name="error-code-450-44312-dns-query-failed"></a>错误代码：450 4.4.312 DNS 查询失败

通常情况下，此错误意味着 Microsoft 365 尝试连接到连接器中指定的智能主机，但查找智能主机的 IP 地址的 DNS 查询失败。 此错误可能是由如下原因造出的：

- 您的域的 DNS 托管服务遇到 (方将保留域服务的权威名称) 。

- 你的域最近已过期，无法检索 MX 记录。

- 您的域的 MX 记录最近已更改，DNS 服务器仍之前已缓存域的 DNS 信息。

### <a name="how-do-i-fix-error-code-450-44312"></a>如何修复错误代码 450 4.4.312？

- 使用您的 DNS 托管服务来识别并修复您的域的问题。

- 如果错误来自合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决该问题。

## <a name="error-code-450-44315-connection-timed-out"></a>错误代码：450 4.4.315 连接超时

通常情况下，Microsoft 365 无法连接到目标电子邮件服务器。 错误详细信息将说明问题。 例如：

- 您的本地电子邮件服务器已关闭。

- 连接器的智能主机设置中存在错误，导致 Microsoft 365 将尝试连接到错误的 IP 地址。

### <a name="how-do-i-fix-error-code-450-44315"></a>如何修复错误代码 450 4.4.315？

- 找出适用于你的方案，并进行必要的更正。 例如，如果邮件流已正常工作，且连接器设置未更改，则需要检查本地电子邮件环境以确定服务器是否关闭，或者你是否已更改了网络基础结构 (（例如，您已更改了 Internet 服务提供商）以使你现在拥有不同的 IP 地址) 。

- 如果错误来自合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决该问题。

## <a name="error-code-450-44316-connection-refused"></a>错误代码：450 4.4.316 连接拒绝

通常情况下，此错误意味着 Microsoft 365 在尝试连接到目标电子邮件服务器时遇到了连接错误。 错误的原因是你的防火墙阻止了来自 Microsoft 365 IP 地址的连接。 如果您已将本地电子邮件系统完全迁移到 Microsoft 365 并关闭本地电子邮件环境，则此错误可能是设计使而值。

### <a name="how-do-i-fix-error-code-450-44316"></a>如何修复错误代码 450 4.4.316？

- 如果您在本地环境中有邮箱，则需要修改防火墙设置以允许从 TCP 端口 25 上的 Microsoft 365 IP 地址连接到本地电子邮件服务器。 有关 Microsoft 365 IP 地址的列表，请参阅 [Microsoft 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

- 如果没有其他邮件应传递到你的本地环境，则在 **警报中单击"修复** "，以便 Microsoft 365 可以立即拒绝具有无效收件人的邮件。 这将降低无效收件人超过组织配额的风险，进而可能会影响正常邮件传递。 或者，你可以按照以下说明手动修复此问题：

  - 在 [EXCHANGE 管理中心 (EAC) ， ](https://docs.microsoft.com/Exchange/exchange-admin-center)禁用或删除将电子邮件从 Microsoft 365 传递到本地电子邮件环境的连接器：

    1. 在 EAC 中，**转到"** \> **邮件流连接器"。**

    2. 选择"发件人" **值** **Office 365** 且 **您的组织的** 电子邮件服务器的"收件人"值 **的连接器，** 并执行以下步骤之一：

       - 通过单击"删除删除" **图标删除** ![ 连接器](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - 通过单击"编辑"图标 **并** ![ 取消 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 其打开来 **禁用连接器**。

  - 将 Microsoft 365 中与本地电子邮件环境相关联的接受域从 **"内部中继"更改为**"**权威"。** 有关说明，请参阅["在 Exchange Online 中管理接受域"。](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **注意**：这些更改通常需要 30 分钟到 1 小时才能生效。 1 小时后，验证您是否不再收到该错误。

- 如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>错误代码：450 4.4.317 无法连接到远程服务器

通常情况下，此错误意味着 Microsoft 365 连接到目标电子邮件服务器，但服务器返回了即时错误，或者不满足连接要求。 错误详细信息将说明问题。 例如：

- 目标电子邮件服务器响应"服务不可用"错误，表示该服务器无法保持与 Microsoft 365 的通信。

- 连接器配置为需要 TLS，但目标电子邮件服务器不支持 TLS。

### <a name="how-do-i-fix-error-code-450-44317"></a>如何修复错误代码 450 4.4.317？

- 验证您的本地电子邮件服务器上的 TLS 设置和证书，以及连接器上的 TLS 设置。

- 如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>错误代码：450 4.4.318 连接已意外关闭

通常情况下，此错误意味着 Microsoft 365 在与本地电子邮件环境进行联操作时遇到难以，因此连接断开。 此错误可能是由如下原因造出的：

- 你的防火墙使用 SMTP 数据包检查规则，这些规则无法正常运行。

- 你的本地电子邮件服务器运行不正常 (例如服务停靠、崩溃或低系统资源) ，这将使服务器超时并关闭与 Microsoft 365 的连接。

- 本地环境和 Microsoft 365 之间存在网络问题。

### <a name="how-do-i-fix-error-code-450-44318"></a>如何修复错误代码 450 4.4.318？

- 找出适用于你的方案，并进行必要的更正。

- 如果此问题是由本地环境和 Microsoft 365 之间的网络问题导致的，请与网络团队联系以解决该问题。

- 如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。

## <a name="error-code-450-47320-certificate-validation-failed"></a>错误代码：450 4.7.320 证书验证失败

通常情况下，此错误意味着 Microsoft 365 在尝试验证目标电子邮件服务器的证书时遇到错误。 错误详细信息将说明错误。 例如：

- 证书过期

- 证书使用者不匹配

- 证书不再有效

### <a name="how-do-i-fix-error-code-450-47320"></a>如何修复错误代码 450 4.7.320？

- 修复连接器上的证书或设置，以便可以传递 Microsoft 365 中的排队邮件。

- 如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。

## <a name="other-error-codes"></a>其他错误代码

Microsoft 365 在将邮件送达本地或合作伙伴电子邮件服务器时遇到困难。 使用 **错误中的** 目标服务器信息检查环境中的问题，或者在配置错误下修改连接器。

如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。
