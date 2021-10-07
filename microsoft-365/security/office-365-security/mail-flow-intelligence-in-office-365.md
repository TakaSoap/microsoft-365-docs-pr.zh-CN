---
title: 邮件流智能
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解使用连接器（也称为"邮件流智能" (）与邮件传递关联的错误) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84029f2f3387913b810c6886a2ac546e587aaca7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169487"
---
# <a name="mail-flow-intelligence-in-eop"></a>EOP 中的邮件流智能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱位于 Exchange Online 或独立 Exchange Online Protection (EOP) 组织（没有 Exchange Online 邮箱）中，通常使用连接器将电子邮件从 EOP 路由到本地电子邮件环境。 您还可以使用连接器将邮件从 Microsoft 365路由到合作伙伴组织。 当Microsoft 365无法通过连接器传递这些邮件时，这些邮件将排入队列Microsoft 365。 Microsoft 365 24 小时内继续重试每封邮件的传递。 24 小时后，排队的邮件将过期，并且该邮件将在未送达报告（也称为 NDR 或退回邮件 (中返回到原始发件人) 。

Microsoft 365连接器无法传递邮件时，将生成错误。 本文介绍了最常见的错误及其解决方案。 通过连接器发送的未送达邮件的排队和通知错误统称为"邮件 _流智能"。_

## <a name="error-code-450-44312-dns-query-failed"></a>错误代码：450 4.4.312 DNS 查询失败

通常，此错误Microsoft 365尝试连接到连接器中指定的智能主机，但查找智能主机 IP 地址的 DNS 查询失败。 导致此错误的可能原因包括：

- 您的域的 DNS 托管服务存在 (维护您的域服务器的权威名称服务器的一) 。

- 您的域最近已过期，因此无法检索 MX 记录。

- 您的域的 MX 记录最近已更改，并且 DNS 服务器以前仍缓存了您的域的 DNS 信息。

### <a name="how-do-i-fix-error-code-450-44312"></a>如何修复错误代码 450 4.4.312？

- 使用 DNS 托管服务识别和修复域问题。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) 联系你的合作伙伴来修复此问题。

## <a name="error-code-450-44315-connection-timed-out"></a>错误代码：450 4.4.315 连接时间已过

通常，这意味着Microsoft 365无法连接到目标电子邮件服务器。 错误详细信息将解释此问题。 例如：

- 您的本地电子邮件服务器已关闭。

- 连接器的智能主机设置出错，Microsoft 365尝试连接到错误的 IP 地址。

### <a name="how-do-i-fix-error-code-450-44315"></a>如何修复错误代码 450 4.4.315？

- 了解适用于你的方案，并进行必要的更正。 例如，如果邮件流一直运行正常，并且尚未更改连接器设置，则需要检查本地电子邮件环境以查看服务器是否关闭，或者是否对网络基础结构进行了任何更改 (例如，您更改了 Internet 服务提供商，因此现在您具有不同的 IP 地址) 。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) 联系你的合作伙伴来修复此问题。

## <a name="error-code-450-44316-connection-refused"></a>错误代码：450 4.4.316 连接被拒绝

通常，此错误意味着Microsoft 365尝试连接到目标电子邮件服务器时遇到连接错误。 导致此错误的一个可能原因是防火墙阻止了与 IP Microsoft 365连接。 或者，如果已完全将本地电子邮件系统迁移到本地电子邮件系统并关闭本地电子邮件环境，Microsoft 365错误。

### <a name="how-do-i-fix-error-code-450-44316"></a>如何修复错误代码 450 4.4.316？

- 如果您的内部部署环境中有邮箱，则需要修改防火墙设置以允许从 TCP 端口 25 上的 Microsoft 365 IP 地址连接到内部部署电子邮件服务器。 有关 IP 地址Microsoft 365，请参阅Microsoft 365 URL 和[IP 地址范围](../../enterprise/urls-and-ip-address-ranges.md)。

- 如果不应将更多邮件传递到本地环境，请单击警报中的"立即修复"，Microsoft 365立即拒绝具有无效收件人的邮件。 这将降低超出组织对无效收件人的配额的风险，这可能会影响正常邮件传递。 或者，可以使用以下说明手动修复该问题：

  - 在 Exchange 管理中心[ (EAC) ](/Exchange/exchange-admin-center)中，禁用或删除将电子邮件从 Microsoft 365 发送到本地电子邮件环境的连接器：

    1. 在 EAC 中，转到"**邮件流** \> **""连接器"。**

    2. Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps：
       - 通过单击"删除 **""删除"** ![ 图标删除连接器。](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - 通过单击"编辑编辑 **"图标禁用** ![ 连接器。](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 并清除 **打开**。

  - 将与本地电子邮件Microsoft 365中的接受域从"内部中继"更改为 **"权威"。**  有关说明，请参阅[管理 Exchange Online 中的接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

  **注意**：通常，这些更改需要 30 分钟到 1 小时才能生效。 一小时后，请确认您不再收到该错误。

- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>错误代码：450 4.4.317 无法连接到远程服务器

通常，此错误意味着Microsoft 365已连接到目标电子邮件服务器，但服务器立即响应错误，或不符合连接要求。 错误详细信息将解释此问题。 例如：

- 目标电子邮件服务器响应了"服务不可用"错误，指示服务器无法与 Microsoft 365。
- 连接器配置为需要 TLS，但目标电子邮件服务器不支持 TLS。

### <a name="how-do-i-fix-error-code-450-44317"></a>如何修复错误代码 450 4.4.317？

- 验证本地电子邮件服务器的 TLS 设置和证书，以及连接器上的 TLS 设置。
- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>错误代码：450 4.4.318 连接突然关闭

通常，此错误意味着Microsoft 365本地电子邮件环境通信时遇到困难，因此连接已中断。 导致此错误的可能原因包括：

- 防火墙使用 SMTP 数据包检查规则，这些规则无法正常工作。
- 您的本地电子邮件服务器无法正常运行 (例如服务挂起、崩溃或系统资源不足) ，从而导致服务器出现问题并关闭与 Microsoft 365 的连接。
- 本地环境和本地环境之间存在网络Microsoft 365。

### <a name="how-do-i-fix-error-code-450-44318"></a>如何修复错误代码 450 4.4.318？

- 了解适用于你的方案，并进行必要的更正。
- 如果问题由本地环境和本地环境之间的网络Microsoft 365，请与网络团队联系以解决问题。
- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。

## <a name="error-code-450-47320-certificate-validation-failed"></a>错误代码：450 4.7.320 证书验证失败

通常，此错误意味着Microsoft 365验证目标电子邮件服务器的证书时遇到错误。 错误详细信息将解释此错误。 例如：

- 证书已过期
- 证书主题不匹配
- 证书不再有效

### <a name="how-do-i-fix-error-code-450-47320"></a>如何修复错误代码 450 4.7.320？

- 修复连接器上的证书或设置，以便可以传递Microsoft 365排队的邮件。
- 如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。

## <a name="other-error-codes"></a>其他错误代码

Microsoft 365无法将邮件发送到本地或合作伙伴电子邮件服务器。 使用 **错误中** 的目标服务器信息检查环境中的问题，或者修改连接器（如果存在配置错误）。

如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。
