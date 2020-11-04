---
title: 邮件流智能
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解与使用 (连接器（也称为 "邮件流智能) "）相关联的邮件传递相关的错误代码。
ms.openlocfilehash: 461d9bfa91d88b8bbec52d5aad6ec7a2e534bc96
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877797"
---
# <a name="mail-flow-intelligence-in-eop"></a>EOP 中的邮件流智能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 中的邮箱或独立 Exchange Online Protection 的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，通常使用连接器将电子邮件从 EOP 路由到本地电子邮件环境。 您还可以使用连接器将来自 Microsoft 365 的邮件路由到合作伙伴组织。 当 Microsoft 365 无法通过连接器传递这些邮件时，它们将在 Microsoft 365 中排队。 Microsoft 365 将继续为每封邮件重新尝试传递24小时。 24小时后，排队的邮件将会过期，并且邮件将在未送达报告中返回到原始发件人 (也称为 "NDR" 或 "退回邮件") 。

当无法使用连接器传递邮件时，Microsoft 365 将生成错误。 本主题中介绍了最常见的错误及其解决方案。 通过连接器发送的未送达邮件的排队和通知错误称为 " _邮件流智能_ "。

## <a name="error-code-450-44312-dns-query-failed"></a>错误代码： 450 4.4.312 DNS 查询失败

通常情况下，此错误意味着 Microsoft 365 尝试连接到连接器中指定的智能主机，但用于查找智能主机 IP 地址的 DNS 查询失败。 此错误可能的原因是：

- 您的域的 DNS 托管服务 (在为域) 维护权威名称服务器的一方存在问题。

- 你的域最近已过期，因此无法检索 MX 记录。

- 您的域的 MX 记录最近已更改，并且 DNS 服务器仍有以前为您的域缓存的 DNS 信息。

### <a name="how-do-i-fix-error-code-450-44312"></a>如何修复错误代码 450 4.4.312？

- 使用 DNS 托管服务识别和修复您的域的问题。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决此问题。

## <a name="error-code-450-44315-connection-timed-out"></a>错误代码： 450 4.4.315 连接超时

通常情况下，这意味着 Microsoft 365 无法连接到目标电子邮件服务器。 错误详细信息将对问题进行说明。 例如：

- 您的内部部署电子邮件服务器已关闭。

- 连接器的智能主机设置中存在错误，因此 Microsoft 365 将尝试连接到错误的 IP 地址。

### <a name="how-do-i-fix-error-code-450-44315"></a>如何修复错误代码 450 4.4.315？

- 查找适用于您的方案，并进行必要的更正。 例如，如果邮件流已正常工作，且未更改连接器设置，则需要检查本地电子邮件环境以查看服务器是否已关闭，或者是否对网络基础结构进行了任何更改 (例如，更改了 internet 服务提供商，以便您现在具有不同的 IP 地址) 。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决此问题。

## <a name="error-code-450-44316-connection-refused"></a>错误代码： 450 4.4.316 连接被拒绝

通常情况下，此错误意味着 Microsoft 365 在尝试连接到目标电子邮件服务器时遇到连接错误。 此错误可能的原因是防火墙阻止了来自 Microsoft 365 IP 地址的连接。 或者，如果已将本地电子邮件系统完全迁移到 Microsoft 365 并关闭了本地电子邮件环境，则设计可能会发生此错误。

### <a name="how-do-i-fix-error-code-450-44316"></a>如何修复错误代码 450 4.4.316？

- 如果您的本地环境中有邮箱，您需要修改防火墙设置，以允许从 TCP 端口25上的 Microsoft 365 IP 地址连接到您的本地电子邮件服务器。 有关 Microsoft 365 IP 地址的列表，请参阅 [microsoft 365 url 和 IP 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)。

- 如果不应将更多的邮件传递到您的本地环境，请单击警报中的 " **立即修复** " 以便 Microsoft 365 可以立即拒绝收件人无效的邮件。 这将降低组织的配额对无效收件人的配额造成的风险，这可能会影响正常的邮件传递。 或者，您可以使用以下说明手动修复问题：

  - 在 [Exchange 管理中心 (EAC) ](https://docs.microsoft.com/Exchange/exchange-admin-center)中，禁用或删除将来自 Microsoft 365 的电子邮件传递到本地电子邮件环境的连接器：

    1. 在 EAC 中，转到 " **邮件流** \> **连接器** "。

    2. 选择 " **发件人** " 值为 " **Office 365** " 的连接器，然后选择 " **到** " 值 **您组织的电子邮件服务器** ，然后执行以下步骤之一：

       - 通过单击 " **删除** ![ 删除" 图标删除连接器](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - 通过单击 " **编辑** " "编辑" ![ 图标 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 并清除 " **启用** " 来禁用连接器。

  - 将与您的本地电子邮件环境关联的 Microsoft 365 中的接受域从 **内部中继** 更改为 **权威** 。 有关说明，请参阅 [在 Exchange Online 中管理接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

  **注意** ：通常情况下，这些更改需要30分钟到1小时才能生效。 一小时后，验证您是否不再收到该错误。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，则需要联系合作伙伴以解决问题。

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>错误代码： 450 4.4.317 无法连接到远程服务器

通常情况下，此错误意味着 Microsoft 365 连接到目标电子邮件服务器，但服务器响应直接错误，或者不符合连接要求。 错误详细信息将对问题进行说明。 例如：

- 目标电子邮件服务器响应 "服务不可用" 错误，指示服务器无法维护与 Microsoft 365 的通信。

- 连接器配置为需要 TLS，但目标电子邮件服务器不支持 TLS。

### <a name="how-do-i-fix-error-code-450-44317"></a>如何修复错误代码 450 4.4.317？

- 验证本地电子邮件服务器上的 TLS 设置和证书，以及连接器上的 TLS 设置。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，则需要联系合作伙伴以解决问题。

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>错误代码： 450 4.4.318 连接突然关闭

通常情况下，此错误意味着 Microsoft 365 在与您的本地电子邮件环境通信时遇到困难，因此断开连接。 此错误可能的原因是：

- 您的防火墙使用 SMTP 数据包检查规则，这些规则不能正常运行。

- 您的内部部署电子邮件服务器不能正常运行 (例如，服务挂起、崩溃或系统资源不足) ，这会导致服务器超时并关闭与 Microsoft 365 的连接。

- 您的本地环境和 Microsoft 365 之间存在网络问题。

### <a name="how-do-i-fix-error-code-450-44318"></a>如何修复错误代码 450 4.4.318？

- 查找适用于您的方案，并进行必要的更正。

- 如果问题是由于您的本地环境和 Microsoft 365 之间的网络问题导致的，请联系网络团队以解决此问题。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，则需要联系合作伙伴以解决问题。

## <a name="error-code-450-47320-certificate-validation-failed"></a>错误代码： 450 4.7.320 证书验证失败

通常情况下，此错误意味着 Microsoft 365 在尝试验证目标电子邮件服务器的证书时遇到错误。 错误详细信息将对错误进行说明。 例如：

- 证书已过期

- 证书主题不匹配

- 证书已不再有效

### <a name="how-do-i-fix-error-code-450-47320"></a>如何修复错误代码 450 4.7.320？

- 修复了连接器上的证书或设置，以便可以在 Microsoft 365 中传递排队的邮件。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，则需要联系合作伙伴以解决问题。

## <a name="other-error-codes"></a>其他错误代码

Microsoft 365 在将邮件传递到内部部署或合作伙伴电子邮件服务器时遇到困难。 使用错误中的 **目标服务器** 信息来检查环境中的问题，如果存在配置错误，则修改连接器。

如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，则需要联系合作伙伴以解决问题。
