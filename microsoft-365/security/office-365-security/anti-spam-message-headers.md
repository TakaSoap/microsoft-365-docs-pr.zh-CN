---
title: 反垃圾邮件邮件头
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解 Exchange Online Protection (EOP) 向邮件添加的标题字段。这些标题字段提供了有关此邮件和其处理方式的信息。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b82826cf650caffa08c0c7435ea4cabf5a19742
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208981"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Microsoft 365 中的反垃圾邮件标题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在所有 Microsoft 365 组织中，Exchange Online Protection (EOP) 会扫描所有传入邮件中的垃圾邮件、恶意软件和其他威胁。 这些扫描的结果将添加到消息中的以下标头字段中：

- **X-Forefront-Antispam-Report**：包含有关消息及其处理方式的信息。

- **X-Microsoft-Antispam**：包含有关批量邮件和网络钓鱼的其他信息。

- **Authentication-results**：包含有关 SPF、DKIM 和 DMARC（电子邮件身份验证）结果的信息。

本文介绍了这些标头字段中的可用功能。

要了解如何查看各种电子邮件客户端中的电子邮件头，请参阅[ Outlook 中查看 Internet 邮件头](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。

> [!TIP]
> 你可以将邮件头的内容复制并粘贴到[邮件头分析器](https://mha.azurewebsites.net/)工具中。 此工具可帮助分析标头，并将其放入更可靠的格式中。

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 邮件标头字段

获得邮件头信息后，找到 **X-Forefront-Antispam-Report** 标头。 此标头中将有多个字段和值对，以分号 (;) 分隔。 例如：

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

下表介绍了各个字段和值。

> [!NOTE]
> **X-Forefront-Antispam-Report** 标头包含许多不同的字段和值。 表中未描述的字段专供 Microsoft 反垃圾邮件团队用于进行诊断。

****

|字段|描述|
|---|---|
|`ARC`|`ARC` 协议具有以下字段： <ul><li>`AAR`：记录 DMARC 中 **Authentication-results** 标头的内容。</li><li>`AMS`：包括邮件的加密签名。</li><li>`AS`：包括邮件标头的加密签名。此字段包含名为 `"cv="` 的链验证的标记，其中包括值为 **none**、**pass** 或 **fail** 的链验证结果。</li></ul>|
|`CAT:`|应用于邮件的保护策略类别： <ul><li>`BULK`：大量邮件</li><li>`DIMP`：域模拟</li><li>`GIMP`：[基于邮箱智能的模拟](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>`HPHSH` 或 `HPHISH`：高可信度钓鱼</li><li>`HSPM`：高可信度垃圾邮件</li><li>`MALW`：恶意软件</li><li>`PHSH`：网络钓鱼</li><li>`SPM`：垃圾邮件</li><li>`SPOOF`：欺骗</li><li>`UIMP`：用户模拟</li><li>`AMP`：反恶意软件</li><li>`SAP`：安全附件</li><li>`OSPM`：出站垃圾邮件</li></ul> <p> 入站邮件可能受到多种形式保护方法和多次检测扫描的标记。 策略的优先级不同，优先级最高的策略第一个应用。 有关详细信息，请参阅[在电子邮件上运行多种保护方法和多次检测扫描时应用什么策略](how-policies-and-protections-are-combined.md)。|
|`CIP:[IP address]`|连接 IP 地址。 可以在 IP 允许列表或 IP 阻止列表中使用此 IP 地址。 有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。|
|`CTRY`|由连接 IP 地址确定的源国家/地区，可能与原始发送 IP 地址不同。|
|`H:[helostring]`|连接电子邮件服务器的 HELO 或 EHLO 字符串。|
|`IPV:CAL`|邮件跳过了垃圾邮件筛选，因为源 IP 地址在 IP 允许列表中。有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。|
|`IPV:NLI`|该 IP 地址没有出现在任何 IP 信誉列表中。|
|`LANG`|邮件的编写语言，由国家/地区代码指定（例如，俄语的代码为 ru_RU）。|
|`PTR:[ReverseDNS]`|源 IP 地址的 PTR 记录（亦称为反向 DNS 查找）。|
|`SCL`|邮件的垃圾邮件可信度 (SCL)。 值越高，邮件是垃圾邮件的可能性就越大。 有关详细信息，请参阅[垃圾邮件可信度 (SCL)](spam-confidence-levels.md)。|
|`SFTY`|邮件被标识为“网络钓鱼”，还将使用下述值之一进行标记： <ul><li>9.19：域模拟。 发送域正在尝试[模拟受保护的域](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 将向邮件添加域模拟安全提示（如果已启用）。</li><li>9.20：用户模拟。 发送用户试图模拟收件人组织中的用户，或 Microsoft Defender for Office 365 中的[反钓鱼策略中指定的受保护用户](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 将向邮件添加用户模拟安全提示（如果已启用）。</li></ul>|
|`SFV:BLK`|邮件跳过了筛选，但被阻止，因为邮件是从用户的“阻止的发件人”列表中的地址发送的。 <p> 若要详细了解管理员如何管理用户的“阻止的发件人”列表，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。|
|`SFV:NSPM`|邮件被垃圾邮件筛选标记为非垃圾邮件，并发送到目标收件人。|
|`SFV:SFE`|邮件跳过了筛选，且被允许，因为邮件是从用户的“安全发件人”列表中的地址发送的。 <p> 若要详细了解管理员如何管理用户的“安全发件人”列表，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。|
|`SFV:SKA`|邮件跳过了垃圾邮件筛选，并被发送到收件箱，因为发件人在反垃圾邮件策略中“允许的发件人”列表或“允许的域”列表中。有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|`SFV:SKB`|邮件被标记为垃圾邮件，因为邮件与反垃圾邮件策略中“阻止的发件人”列表或“阻止的域”列表中的发件人匹配。有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|`SFV:SKI`|与 SFV:SKN 类似，区别在于邮件因其他原因（例如，邮件是租户内的组织内电子邮件）而跳过垃圾邮件筛选。|
|`SFV:SKN`|邮件在垃圾邮件筛选处理前标记为非垃圾邮件，例如，邮件流规则将邮件标记为 SCL-1 或 **不使用垃圾邮件筛选**。|
|`SFV:SKQ`|从隔离区释放邮件，并将其发送给目标收件人。|
|`SFV:SKS`|邮件在垃圾邮件筛选处理前标记为垃圾邮件，例如，邮件流规则将邮件标记为 SCL 5 至 9。|
|`SFV:SPM`|邮件被垃圾邮件筛选标记为垃圾邮件。|
|`SRV:BULK`|邮件被垃圾邮件筛选和批量投诉级别 (BCL) 阈值标识为大量电子邮件。 如果 _MarkAsSpamBulkMail_ 参数为 `On`（默认处于启用状态），大量电子邮件被标记为高可信度垃圾邮件 (SCL 9)。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。|
|`X-CustomSpam: [ASFOption]`|邮件与高级垃圾邮件筛选 (ASF) 设置匹配。 若要查看每个 ASF 设置的 X 标头值，请参阅[高级垃圾邮件筛选 (ASF) 设置](advanced-spam-filtering-asf-options.md)。|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 邮件标头字段

下表描述了“**X-Microsoft-Antispam**”邮件头中的有用字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。

****

|字段|描述|
|---|---|
|`BCL`|邮件的批量投诉级别 (BCL)。 BCL 越高，大量邮件产生投诉的可能性就越大（因此更有可能是垃圾邮件）。 有关详细信息，请参阅[批量投诉级别 (BCL)](bulk-complaint-level-values.md)。|
|

## <a name="authentication-results-message-header"></a>“Authentication-results”邮件头

对 SPF、DKIM 和 DMARC 的电子邮件身份验证检查的结果记录（标记）在入站邮件的 **Authentication-results** 邮件头中。

下表描述了每种电子邮件身份验证检查类型添加到 **Authentication-Results** 标头中的文本：

- SPF 使用以下语法：

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  例如：

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM 使用以下语法：

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  例如：

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC 使用以下语法：

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  例如：

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Authentication-results 邮件头字段

下表描述了每个电子邮件身份验证检查的字段和可能的值。

****

|字段|说明|
|---|---|
|`action`|指示垃圾邮件筛选器基于 DMARC 检查结果执行的操作。例如： <ul><li>**oreject** 或 **o.reject**：代表覆盖拒绝。在这种情况下，Microsoft 365 将在收到来自 DMARC TXT 记录的策略为 p=reject 的域的邮件，且该邮件未通过 DMARC 检查时使用此操作。Microsoft 365 将该邮件标记为垃圾邮件，而不是删除或拒绝该邮件。有关这样配置 Microsoft 365 的原因的详细信息，请参阅 [Microsoft 365 如何处理未通过 DMARC 检查的入站电子邮件](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc)。  </li><li>**pct.quarantine**：指示未通过 DMARC 的邮件将按少于 100% 的比例以任意方式传递。这表示邮件未通过 DMARC 且已将策略设置为隔离，但 pct 字段未设置为 100% 且系统根据每个特定域的策略随机决定不执行 DMARC 操作。</li><li>**pct.reject**：指示未通过 DMARC 的邮件将按少于 100% 的比例以任意方式传递。这表示邮件未通过 DMARC 且已将策略设置为拒绝，但 pct 字段未设置为 100% 且系统根据每个特定域的策略随机决定不执行 DMARC 操作。</li><li>**permerror**：DMARC 评估过程中出现的永久性错误，例如，在 DNS 中遇到格式不正确的 DMARC TXT 记录。尝试重新发送此邮件不太可能产生不同的结果。你反而可能需要联系域的所有者，以解决该问题。</li><li>**temperror**：DMARC 评估期间出现的临时错误。你可以请求发件人稍后重新发送邮件，以正确处理电子邮件。</li></ul>|
|`compauth`|复合身份验证结果。由 Microsoft 365 用于合并多种类型的身份验证，例如 SPF、DKIM、DMARC 或邮件的任何其他部分，以确定是否对消息进行了身份验证。使用 From: domain 作为评估的基础。|
|`dkim`|说明邮件的 DKIM 检查结果。可能的值包括： <ul><li>**pass**：表示通过了邮件的 DKIM 检查。</li><li>**fail (reason)**：指示邮件未通过 DMARC 检查及其原因。例如，如果邮件未签名或签名未经验证。</li><li>**none**：指示邮件未签名。这可能表示或不表示域存在 DKIM 记录或 DKIM 记录未生成结果，仅表示该邮件未签名。</li></ul>|
|`dmarc`|说明邮件的 DMARC 检查结果。可能的值包括： <ul><li>**pass**：表示通过了邮件的 DMARC 检查。</li><li>**fail**：表示未通过邮件的 DMARC 检查。</li><li>**bestguesspass**：表示域没有 DMARC TXT 记录；如果存在该记录，就会通过邮件的 DMARC 检查。</li><li>**none**：指示没有 DMARC TXT 记录用于 DNS 中的发送域。|
|`header.d`|DKIM 签名中标识的域（如有）。这指的是针对公钥查询的域。|
|`header.from`|电子邮件头中 `5322.From` 地址（亦称为“发件人地址”或“P2 发件人”）的域。收件人可在邮件客户端中看到发件人地址。|
|`reason`|复合身份验证通过或失败的原因。 该值是一个 3 位数的代码。 例如： <ul><li>**000**: 邮件未通过显式身份验证 (`compauth=fail`)。例如，邮件未通过 DMARC 验证，采取的操作是隔离或拒绝。</li><li>**001**: 邮件未通过隐式身份验证 (`compauth=fail`)。这意味着发送域未发布电子邮件身份验证记录，或者如果已发布，则意味着它们具有较弱的失败策略 (SPF 软失败或中性，DMARC 策略为 `p=none`)。</li><li>**002**: 组织为发件人/域对设置了明确禁止发送欺骗性电子邮件的策略。此设置由管理员手动设置。</li><li>**010**：邮件未通过 DMARC 验证，并采取了拒绝或隔离操作，而且发送域是组织的接受域之一（这是自我欺骗或组织内欺骗的一部分）之一。</li><li>**1xx** 或 **7xx**：邮件通过了身份验证 (`compauth=pass`)。 最后两位数是 Microsoft 365 使用的内部代码。</li><li>**2xx**：邮件“软”通过隐式身份验证 (`compauth=softpass`)。 最后两位数是 Microsoft 365 使用的内部代码。</li><li>**3xx**：未针对复合身份验证检查邮件 (`compauth=none`)。</li><li>**4xx** 或 **9xx**：邮件规避了复合身份验证 (`compauth=none`)。 最后两位数是 Microsoft 365 使用的内部代码。</li><li>**6xx**：邮件未通过隐式电子邮件身份验证，并采取了拒绝或隔离操作，而且发送域是组织的接受域之一（它是自我欺骗或组织内欺骗的一部分）之一。</li></ul>|
|`smtp.mailfrom`|`5321.MailFrom` 地址（亦称为“MAIL FROM 地址”、“P1 发件人”或“信封发件人”）的域。 这是用于未送达报告（亦称为“NDR”或“退回邮件”）的电子邮件地址。|
|`spf`|说明邮件的 SPF 检查结果。可能的值包括： <ul><li>`pass (IP address)`：邮件通过 SPF 检查，且其中包括发件人的 IP 地址。已授权客户端代表发件人的域发送或中继电子邮件。  </li><li>`fail (IP address)`：邮件未通过 SPF 检查，且其中包括发件人的 IP 地址。有时也称其为 _硬失败_。  </li><li>`softfail (reason)`：SPF 记录已将主机指定为不允许发送，但正处于转换状态。</li><li>`neutral`：SPF 记录明确声明它没有断言 IP 地址是否被授权发送。</li><li>`none`：域没有 SPF 记录或者 SPF 记录未计算得到结果。</li><li>`temperror`：发生暂时性错误。 例如，DNS 错误。 相同的检查稍后可能会成功。</li><li>`permerror`：出现永久错误。例如，域的 SPF 记录格式非常不规范。  </li></ul>|
|
