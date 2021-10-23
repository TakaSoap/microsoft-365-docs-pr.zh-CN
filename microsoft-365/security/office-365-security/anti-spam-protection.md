---
title: 反垃圾邮件保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解反垃圾邮件设置和筛选器，这些设置和筛选器有助于在 EOP Exchange Online Protection (中) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d8a004e5eb909399f1340374b80495dcf0b6e9b
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552520"
---
# <a name="anti-spam-protection-in-eop"></a>EOP 中的反垃圾邮件保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> 本主题面向管理员。 有关最终用户主题，请参阅 [垃圾邮件](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) 筛选器概述和 [了解垃圾邮件和网络钓鱼](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)。

在 Microsoft 365 组织中，在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，EOP 会自动保护电子邮件免受垃圾邮件 (垃圾邮件) 攻击。

Microsoft 的电子邮件安全路线图包括不匹配的跨产品方法。 EOP 反垃圾邮件和防钓鱼技术应用于我们的电子邮件平台，以为用户提供整个网络中最新的反垃圾邮件和防钓鱼工具及创新。 EOP 的目标是提供全面且可用的电子邮件服务，以帮助用户检测垃圾邮件、诈骗电子邮件威胁（网络钓鱼）和恶意软件，并免受其侵扰。

随着电子邮件的普及，电子邮件滥用的问题也日趋严重。 无人监控的垃圾邮件会阻塞收件箱和网络、影响用户满意度，并阻碍合法电子邮件通信的有效性。 这就是 Microsoft 仍继续致力于反垃圾邮件技术的原因。 简单地说，它从包含和筛选垃圾邮件开始。

> [!TIP]
> 当您希望允许或阻止基于邮件信封（例如 (发件人的域或邮件发件人的源 IP 地址）的邮件时，以下反垃圾邮件技术) 。 若要允许或阻止基于有效负载 (例如，邮件或附加文件的 URL) ，您应该使用租户允许 [/阻止列表门户](tenant-allow-block-list.md)。

## <a name="anti-spam-technologies-in-eop"></a>EOP 中的反垃圾邮件技术

为了帮助减少垃圾邮件，EOP 包括使用专有垃圾邮件筛选技术识别和分隔垃圾邮件与合法电子邮件的垃圾邮件保护。 EOP 垃圾邮件筛选从我们的消费者平台 Outlook.com 了解已知的垃圾邮件和网络钓鱼威胁以及用户反馈。 垃圾邮件分类程序中正在进行的、来自 EOP 用户的反馈可以帮助确保 EOP 技术经过不断的定型和提高。

EOP 中的反垃圾邮件设置由以下技术决定：

- 连接 **筛选**：在入站电子邮件连接的早期，通过 IP 允许列表、IP 阻止列表和安全列表识别良好和坏的电子邮件源 *服务器 (由* Microsoft) 维护的受信任发件人的动态但不可编辑的列表。 在连接筛选器策略中配置这些设置。 有关详细信息，请[通过配置连接筛选。](configure-the-connection-filter-policy.md)

- **垃圾邮件筛选 (** 内容筛选) ：EOP 使用垃圾邮件筛选裁定 **垃圾邮件**、高可信度垃圾邮件、批量电子邮件、网络钓鱼电子邮件和高可信度网络钓鱼电子邮件对邮件进行分类。  您可以配置基于这些裁定要采取的操作，您可以为隔离而不是传递的邮件配置最终用户通知选项，以及可以使用隔离策略配置允许用户对隔离邮件执行哪些 [操作](quarantine-policies.md)。 有关详细信息，请参阅在 Microsoft 365[中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

  > [!NOTE]
  > 默认情况下，垃圾邮件筛选配置为将标记为垃圾邮件的邮件发送到收件人的"垃圾邮件"文件夹。 但是，在 EOP 保护内部部署 Exchange 邮箱的混合环境中，您需要在本地 Exchange 组织中配置两个邮件流规则 (也称为传输规则) ，以识别添加到邮件中的 EOP 垃圾邮件头。 有关详细信息，请参阅[在混合环境中将 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。

- **出站垃圾邮件筛选**：EOP 还会进行检查以确保您的用户不会发送出站邮件内容或超出出站邮件限制的垃圾邮件。 有关详细信息，请参阅 Configure [outbound spam filtering in Microsoft 365](configure-the-outbound-spam-policy.md)。

- **欺骗智能**：有关详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。

## <a name="manage-errors-in-spam-filtering"></a>管理垃圾邮件筛选中的错误

良好的邮件可以标识为垃圾邮件 (也称为误报) ，或者垃圾邮件可以传递到收件箱 (也称为漏报) 。 您可以使用以下各节中的建议来了解发生了什么，并帮助防止在将来发生。

下面是适用于这两种方案的一些最佳实践：

- 始终向 Microsoft 报告错误分类的邮件。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- **检查反垃圾邮件邮件头**：这些值将告诉您邮件被标记为垃圾邮件的原因，或邮件跳过垃圾邮件筛选的原因。 有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

- **将 MX** 记录指向Microsoft 365：为了让 EOP 提供最佳保护，我们始终建议您先将电子邮件传递到 Microsoft 365 服务器。 有关说明，请参阅[在任何 DNS 托管提供商上](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)为 Microsoft 365。

  如果 MX 记录指向其他位置 (例如，第三方反垃圾邮件解决方案或) ，EOP 就很难提供准确的垃圾邮件筛选。 在此方案中，您需要为连接器配置增强筛选 (也称为 _跳过列表_) 。 有关说明，请参阅[增强的连接器筛选Exchange Online。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **使用电子邮件身份验证**：如果你拥有电子邮件域，可以使用 DNS 帮助确保来自该域中发件人的邮件是合法的。 为了帮助防止 EOP 中的垃圾邮件和不需要的欺骗，请使用以下所有电子邮件身份验证方法：

  - **SPF：** 发件人策略框架针对发送域的所有者验证邮件的源 IP 地址。 有关 SPF 的快速介绍和快速配置，请参阅设置 [SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 若要更深入地了解 Microsoft 365 如何使用 SPF，或要了解故障排除或非标准部署（如混合部署），请从 [Microsoft 365 如何使用发件人策略框架 (SPF) 以防欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)入手。

  - **DKIM：** 域密钥识别邮件将数字签名添加到从你的域发送的邮件的邮件头。 有关信息，请参阅[使用 DKIM 验证从](use-dkim-to-validate-outbound-email.md)自定义域发送的出站Microsoft 365。

  - **DMARC：** 基于域的邮件身份验证、报告和一致性可帮助目标电子邮件系统确定对未通过 SPF 或 DKIM 检查的邮件执行哪些操作，并提供了另一个信任级别的电子邮件合作伙伴。 有关详细信息，请参阅使用[DMARC 验证电子邮件Microsoft 365。](use-dmarc-to-validate-email.md)

- 验证批量电子邮件设置：在反垃圾邮件策略中配置的批量投诉级别 (BCL) 阈值确定是否将批量电子邮件 (也称为灰色邮件) 标记为垃圾邮件。  默认情况下，启用的仅 PowerShell 设置 _MarkAsSpamBulkMail_ 也会对结果产生影响。 有关详细信息，请参阅在 Microsoft 365[中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>阻止将垃圾邮件发送到收件箱

- **验证你的** 组织设置：注意允许邮件跳过垃圾邮件筛选的设置 (例如，如果你将自己的域添加到反垃圾邮件策略策略中的允许域列表中) 。 有关我们建议的设置，请参阅[EOP](recommended-settings-for-eop-and-office365.md)和 Microsoft Defender 的安全Office 365推荐设置和[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

- **使用可用的阻止发件人列表**：有关信息，请参阅 [创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。

- **取消订阅批量电子邮件** 如果邮件是用户注册的 (新闻稿、产品公告等 ) 并且包含来自信誉良好的源的取消订阅链接，请考虑要求他们直接取消订阅。

- 独立 **EOP：** 在本地 Exchange 中为 EOP 垃圾邮件筛选裁定创建邮件流规则：在 EOP 保护本地 Exchange 邮箱的混合环境中，您需要在本地 Exchange 中配置邮件流规则 (也称为传输规则) 。 这些邮件流规则转换 EOP 垃圾邮件筛选裁定，以便邮箱中的垃圾邮件规则可以将邮件移动到"垃圾邮件"文件夹。 有关详细信息，请参阅[在混合环境中将 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。

### <a name="prevent-good-email-from-being-identified-as-spam"></a>防止将良好的电子邮件标识为垃圾邮件

以下是可以帮助防止误报的一些步骤：

- **验证用户是否Outlook垃圾邮件筛选器设置**：

  - 验证 **Outlook** 垃圾邮件筛选器是否被禁用：当 Outlook 垃圾邮件筛选器设置为默认值"无自动筛选"时，Outlook不会尝试将邮件分类为垃圾邮件。  当垃圾邮件筛选器设置为"低"或"高"时，Outlook垃圾邮件筛选器使用自己的 SmartScreen 筛选器技术来标识垃圾邮件，并移动垃圾邮件文件夹，以便您可以获得误报。 请注意，Microsoft 在 2016 年 11 月停止为 Exchange Outlook SmartScreen 筛选器生成垃圾邮件定义更新。 现有的 SmartScreen 垃圾邮件定义已就位，但其有效性可能会随着时间的推移而降低。

  - **验证是否Outlook"保险箱列表**"设置已禁用：启用此设置后，仅来自用户的 保险箱 发件人列表或 保险箱 收件人列表中的发件人的邮件传递到收件箱;来自其他人的电子邮件会自动移动到"垃圾邮件"文件夹。

  有关这些设置详细信息，请参阅在邮箱Exchange Online[配置垃圾邮件Microsoft 365。](configure-junk-email-settings-on-exo-mailboxes.md)

- **使用可用的安全发件人列表**：有关信息，请参阅 [创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

- **验证用户是否位于发送和接收限制范围内**，如接收和发送 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)Exchange Online说明中所述。

- **独立 EOP：使用目录同步**：如果使用独立 EOP 帮助保护本地 Exchange 组织，则应该使用目录同步将用户设置与服务同步。 执行此操作可确保 EOP 沿用用户安全发件人列表。 有关详细信息，请参阅“[使用目录同步管理邮件用户](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)”。

## <a name="anti-spam-legislation"></a>反垃圾邮件法规

在 Microsoft，我们认为新技术开发和自我管理需要有效的政府政策和法律体系的支持。 全球垃圾邮件的激增促使许多立法机构规范商业电子邮件。 现在，多个国家/地区都制定反垃圾邮件法律。 美国已针对垃圾邮件的管理制定了相应的联邦法律，同时各个州也制定了相关的法律，这种互补措施有助于减少垃圾邮件，同时确保合法的电子商务能够正常开展。 CAN-SPAM Act（反垃圾邮件法）为抵制欺诈和欺骗性电子邮件提供了更有力的法律武器。
