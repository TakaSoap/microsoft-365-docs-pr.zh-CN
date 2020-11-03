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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解将有助于防止 Exchange Online Protection 中的垃圾邮件的反垃圾邮件设置和筛选器 (EOP) 。
ms.openlocfilehash: 9a11337e5b9eff1f77d5711fb4cda2a13bdaed24
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844400"
---
# <a name="anti-spam-protection-in-eop"></a>EOP 中的反垃圾邮件保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 本主题适用于管理员。 有关最终用户的主题，请参阅 [垃圾邮件筛选器概述](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) ，并 [了解垃圾邮件和网络钓鱼](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)。

在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，电子邮件将自动抵御垃圾邮件 (垃圾邮件) EOP 的垃圾邮件。

Microsoft 的电子邮件安全路线图包括不匹配的跨产品方法。 EOP 在我们的电子邮件平台中应用了反垃圾邮件和反网络钓鱼技术，为用户提供了整个网络中最新的反垃圾邮件和反钓鱼工具和革新。 EOP 的目标是提供全面且可用的电子邮件服务，以帮助用户检测垃圾邮件、诈骗电子邮件威胁（网络钓鱼）和恶意软件，并免受其侵扰。

随着电子邮件的普及，电子邮件滥用的问题也日趋严重。 无人监控的垃圾邮件会阻塞收件箱和网络、影响用户满意度，并阻碍合法电子邮件通信的有效性。 这就是 Microsoft 仍继续致力于反垃圾邮件技术的原因。 简单地说，它从包含和筛选垃圾邮件开始。

> [!TIP]
> 如果您希望基于邮件信封允许或阻止邮件 (例如，发件人的域或邮件) 的源 IP 地址，则以下反垃圾邮件技术将非常有用。 若要根据有效负载允许或阻止邮件 (例如，邮件中的 Url 或附加文件) 中，则应使用 [租户允许/阻止列表门户](tenant-allow-block-list.md)。

## <a name="anti-spam-technologies-in-eop"></a>EOP 中的反垃圾邮件技术

为了帮助减少垃圾邮件，EOP 包括使用专用垃圾邮件筛选技术标识和将垃圾邮件与合法电子邮件分开的垃圾邮件保护。 EOP 垃圾邮件筛选从我们的使用者平台 Outlook.com 的已知垃圾邮件和网络钓鱼威胁和用户反馈中获悉。 垃圾邮件分类程序中正在进行的、来自 EOP 用户的反馈可以帮助确保 EOP 技术经过不断的定型和提高。

EOP 中的反垃圾邮件设置由以下技术组成：

- **连接筛选** ：在入站电子邮件连接的早期，通过 Ip 允许列表、Ip 阻止列表和 *安全列表* 在 Microsoft) 维护的受信任发件人列表的动态但不可编辑的电子邮件源服务器上识别出良好和错误的电子邮件源服务器 (。 您可以在连接筛选器策略中配置这些设置。 有关详细信息，请参阅 [配置连接筛选](configure-the-connection-filter-policy.md)。

  > [!NOTE]
  > 欺骗智能使用连接筛选来创建要哄骗电子邮件域的发件人的允许名单和阻止名单。 有关详细信息，请参阅 [在 Microsoft 365 中了解有关欺骗情报的详细](learn-about-spoof-intelligence.md)信息。

- **垃圾邮件筛选 (内容筛选)** ： EOP 使用垃圾邮件筛选 verdicts **垃圾** 邮件、 **高可信度垃圾邮件** 、 **批量电子邮件** 、 **网络钓鱼电子** 邮件和 **高可信度的网络钓鱼电子** 邮件对邮件进行分类。 您可以根据这些 verdicts 配置要采取的操作，并且可以为已隔离而不是传递的邮件配置最终用户通知选项。 有关详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

  > [!NOTE]
  > 默认情况下，垃圾邮件筛选配置为将标记为 "垃圾邮件" 的邮件发送到收件人的 "垃圾邮件" 文件夹。 但是，在 EOP 保护本地 Exchange 邮箱的混合环境中，您需要配置两个邮件流规则 (也称为传输规则) 在内部部署 Exchange 组织中，以识别添加到邮件中的 EOP 垃圾邮件头。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

- **出站垃圾邮件筛选** ： EOP 还会进行检查以确保您的用户不会在出站邮件内容中或超过出站邮件限制发送垃圾邮件。 有关详细信息，请参阅 [在 Microsoft 365 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

- **欺骗情报** ：有关详细信息，请参阅 [了解 Microsoft 365 中有关欺骗情报的详细](learn-about-spoof-intelligence.md)信息。

## <a name="manage-errors-in-spam-filtering"></a>管理垃圾邮件筛选中的错误

可以将良好的邮件标识为垃圾邮件 (也称为误报) ，或者可以将垃圾邮件传递到收件箱。 您可以使用以下部分中的建议查看已发生的情况，并帮助防止将来发生此问题。

以下是适用于任一方案的一些最佳做法：

- 始终将 misclassified 邮件提交给 Microsoft。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

- **检查反垃圾邮件邮件头** ：这些值将告诉你为什么邮件被标记为垃圾邮件，或者为什么它跳过垃圾邮件筛选。 有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

- **将 MX 记录指向 Microsoft 365** ：为了使 EOP 能够提供最佳保护，我们始终建议您先将电子邮件传递到 microsoft 365。 有关说明，请参阅 [在 Microsoft 365 的任意 DNS 托管提供程序中创建 dns 记录](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

  如果 MX 记录指向某个其他位置 (例如，第三方反垃圾邮件解决方案或设备) ，则 EOP 很难提供准确的垃圾邮件筛选。 在这种情况下，您需要为连接器配置增强的筛选 (也称为 " _跳过列表_ ") 。 有关说明，请参阅 [增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **使用电子邮件身份验证** ：如果你拥有电子邮件域，则可以使用 DNS 帮助确保来自该域中的发件人的邮件是合法邮件。 若要帮助防止垃圾邮件和 EOP 中不需要的欺骗，请使用以下所有电子邮件身份验证方法：

  - **SPF** ：发件人策略框架验证邮件的源 IP 地址是否针对发送域的所有者。 若要快速了解 SPF 并使其快速配置，请参阅 [设置 spf 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 若要更深入地了解 Microsoft 365 如何使用 SPF，或要了解故障排除或非标准部署（如混合部署），请从 [Microsoft 365 如何使用发件人策略框架 (SPF) 以防欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)入手。

  - **DKIM** ：域密钥已识别邮件将数字签名添加到从您的域发送的邮件的邮件头。 有关信息，请参阅 [使用 DKIM 在 Microsoft 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。

  - **DMARC** ：基于域的邮件身份验证、报告和一致性可帮助目标电子邮件系统确定如何处理未通过 SPF 或 DKIM 检查的邮件，并为您的电子邮件合作伙伴提供另一个信任级别。 有关详细信息，请参阅 [使用 DMARC 验证 Microsoft 365 中的电子邮件](use-dmarc-to-validate-email.md)。

- **验证批量电子邮件设置** ：在反垃圾邮件策略中配置的批量兼容级别 (BCL) 阈值将确定是否将批量电子邮件 (（也称为 " _灰色邮件_ ) " 标记为 "垃圾邮件"）。 默认情况下启用的仅限 PowerShell 的设置 _MarkAsSpamBulkMail_ 也对结果有贡献。 有关详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>阻止将垃圾邮件传递到收件箱

- **验证您的组织设置** ：查看允许邮件跳过垃圾邮件筛选的设置 (例如，如果您将自己的域添加到反垃圾邮件策略中的 "允许的域" 列表中) 。 有关我们推荐的设置，请参阅 [EOP 和 Microsoft Defender For Office 365 security](recommended-settings-for-eop-and-office365-atp.md) 和 [Create safe sender Lists](create-safe-sender-lists-in-office-365.md)中的推荐设置。

- **验证是否已在用户邮箱中启用垃圾邮件规则** ：默认情况下已启用，但如果已禁用，则标记为 "垃圾邮件" 的邮件不能移到 "垃圾邮件" 文件夹中。 有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

- **使用可用的阻止发件人列表** ：有关信息，请参阅 [创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。

- **从批量电子邮件中取消订阅** 如果该邮件是用户在 (新闻稿、产品通知等 ) 并包含来自著名来源的取消订阅的内容，请考虑让他们只是取消订阅。

- **独立 EOP：在内部部署 exchange 中创建邮件流规则对于 EOP 垃圾邮件筛选 verdicts** ：在 EOP 保护本地 exchange 邮箱的独立 EOP 环境中，您需要配置邮件流规则 (也称为传输规则) 在本地 exchange 中，以翻译 EOP 垃圾邮件筛选判定，以便垃圾邮件规则可以将邮件移动到 "垃圾邮件" 文件夹。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

### <a name="prevent-good-email-from-being-identified-as-spam"></a>防止将正常的电子邮件标识为垃圾邮件

下面是您可以采取的一些步骤来帮助防止误报：

- **验证用户的 Outlook 垃圾邮件筛选器设置** ：

  - **验证 Outlook 垃圾邮件筛选器是否已禁用** ：当 Outlook 垃圾邮件筛选器设置为默认值 **无自动筛选** 时，outlook 不会尝试将 massages 归类为垃圾邮件。  如果设置为 " **低** " 或 " **高** "，Outlook 垃圾邮件筛选器将使用其自己的 SmartScreen 筛选器技术来识别垃圾邮件文件夹，并将垃圾邮件移至 "垃圾邮件" 文件夹，这样您就可以得到误报。 请注意，Microsoft 已停止在11月2016的 Exchange 和 Outlook 中为 SmartScreen 筛选器生成垃圾邮件定义更新。 现有的 SmartScreen 垃圾邮件定义保留不变，但其有效性可能会随着时间的推移而下降。

  - **验证 Outlook 的 "仅安全列表" 设置是否已禁用** ：如果启用此设置，则仅将来自用户安全发件人列表或安全收件人列表中发件人的邮件传递到收件箱;来自其他人的电子邮件将自动移至 "垃圾邮件" 文件夹。

  有关这些设置的详细信息，请参阅 [在 Microsoft 365 中的 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

- **使用可用的安全发件人列表** ：有关信息，请参阅 [创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

- **验证用户是否在发送和接收限制内** ，如 Exchange Online 服务说明中的 [接收和发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 中所述。

- **独立 EOP：使用目录同步** ：如果使用独立的 EOP 来帮助保护本地 Exchange 组织，则应使用目录同步将用户设置与该服务同步。 执行此操作可确保 EOP 沿用用户安全发件人列表。 有关详细信息，请参阅“[使用目录同步管理邮件用户](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)”。

## <a name="anti-spam-legislation"></a>反垃圾邮件法规

在 Microsoft，我们认为新技术开发和自我管理需要有效的政府政策和法律体系的支持。 全球垃圾邮件的激增促使许多立法机构规范商业电子邮件。 目前，许多国家/地区都采用了抵制垃圾邮件法。 美国已针对垃圾邮件的管理制定了相应的联邦法律，同时各个州也制定了相关的法律，这种互补措施有助于减少垃圾邮件，同时确保合法的电子商务能够正常开展。 CAN-SPAM Act（反垃圾邮件法）为抵制欺诈和欺骗性电子邮件提供了更有力的法律武器。
