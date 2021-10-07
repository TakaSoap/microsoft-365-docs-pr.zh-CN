---
title: EOP 中的 ASF 设置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP (中的反垃圾邮件策略 (ASF Exchange Online Protection (AS) F) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c3bb500ff27ca4d9dfe3b17e42ba1c254962a32c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154334"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP 中的 (垃圾邮件筛选器) ASF 设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 反垃圾邮件策略中当前可用的 ASF 设置正在被弃用。 我们建议您不要在反垃圾邮件策略中使用这些设置。 这些 ASF 设置的功能正在合并到筛选堆栈的其他部分。 有关详细信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

在所有 Microsoft 365 组织中，EOP 中反垃圾邮件策略 (ASF) 设置允许管理员根据特定邮件属性将邮件标记为垃圾邮件。 ASF 专门针对这些属性，因为它们通常位于垃圾邮件中。 根据 属性，ASF 检测将邮件标记为 **垃圾邮件或****高可信度垃圾邮件**。

> [!NOTE]
> 启用一个或多个 ASF 设置是进行垃圾邮件筛选的主动方法。 无法将按 ASF 筛选的邮件报告为误报。 您可以按如下操作标识由 ASF 筛选的邮件：
>
> - 定期最终用户垃圾邮件隔离通知。
> - 隔离邮件中是否存在筛选邮件。
> - 添加到 `X-CustomSpam:` 邮件中的特定 X 标头字段，如本文所述。

以下各节介绍了 Microsoft 365 Defender 门户中的反垃圾邮件策略、Exchange Online PowerShell 或独立 EOP PowerShell ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)和[Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)) 中可用的 ASF 设置和选项。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="enable-disable-or-test-asf-settings"></a>启用、禁用或测试 ASF 设置

对于每个 ASF 设置，反垃圾邮件策略中均提供以下选项：

- **On**：ASF 向邮件添加相应的 X 标头字段，并将该邮件标记为"**垃圾邮件 (** SCL 5"或"6"，用于"增加垃圾邮件得分设置 [) "](#increase-spam-score-settings)或"高可信度垃圾邮件 **(** SCL 9"以标记为垃圾邮件设置 [) 。](#mark-as-spam-settings)
- **关闭**：禁用 ASF 设置。 这是默认值，建议不要更改它。
- **测试**：ASF 将相应的 X 标头字段添加到邮件。 对邮件会发生什么情况由 *TestModeAction (TestModeAction*) 确定： 
  - **无**：邮件传递不受 ASF 检测的影响。 邮件仍受 EOP 中其他类型的筛选和规则限制。
  - ***AddXHeader*** (添加默认 X 标头) ：X 标头值 `X-CustomSpam: This message was filtered by the custom spam filter option` 将添加到邮件中。 可以在收件箱规则或邮件流规则（也称为 (传输规则) 邮件传递）中使用此值。
  - **发送密件** 抄送邮件 (密件抄送) ：将 PowerShell) 中的 *TestModeBccToRecipients* 参数值指定的电子邮件地址 (添加到邮件的"密件抄送"字段中，并将邮件传递给其他密件抄送收件人。 在Microsoft 365 Defender门户中，使用分号分隔多个电子邮件地址 (;) 。 在 PowerShell 中，用逗号分隔多个电子邮件地址。

  **注意**:

  - 测试模式不适用于以下 ASF 设置：
    - **条件发件人 ID 筛选**：MarkAsSpamFromAddressAuthFail (硬 *失败)*
    - **NDR 退 (** *MarkAsSpamNdrBackscatter*) 
    - **SPF 记录**：MarkAsSpamSpfRecordHardFail (硬 *失败)*
  - 相同的测试模式操作将应用于 *设置为* 测试 的所有 ASF **设置**。 不能为不同的 ASF 设置配置不同的测试模式操作。

## <a name="increase-spam-score-settings"></a>增加垃圾邮件得分设置

以下 ASF 设置将检测到的邮件的垃圾邮件可信度 (SCL) 设置为 5 或 6，对应于垃圾邮件筛选器裁定和反垃圾邮件策略中的相应操作。

<br>

****

|反垃圾邮件策略设置|说明|已添加 X 标头|
|---|---|---|
|**指向远程网站的图像链接** <p> *IncreaseScoreWithImageLinks*|包含指向远程网站的 HTML 标记链接的邮件 `<Img>` (例如，使用 http) 标记为垃圾邮件。|`X-CustomSpam: Image links to remote sites`|
|**URL 中的数字 IP 地址** <p> *IncreaseScoreWithNumericIps*|通常，包含基于数字的 URL (IP 地址) 标记为垃圾邮件。|`X-CustomSpam: Numeric IP in URL`|
|**URL 重定向到其他端口** <p> *IncreaseScoreWithRedirectToOtherPort*|包含重定向到 80 (HTTP) 、8080 (备用 HTTP) 或 443 (HTTPS) 的超链接的邮件将被标记为垃圾邮件。|`X-CustomSpam: URL redirect to other port`|
|**指向 .biz 或 .info 网站的链接** <p> *IncreaseScoreWithBizOrInfoUrls*|邮件正文 `.biz` `.info` 中包含或链接的邮件被标记为垃圾邮件。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>标记为垃圾邮件设置

以下 ASF 设置将检测到的邮件的 SCL 设置为 9，对应于高可信度垃圾邮件筛选器裁定和反垃圾邮件策略中的相应操作。

<br>

****

|反垃圾邮件策略设置|说明|已添加 X 标头|
|---|---|---|
|**空邮件** <p> *MarkAsSpamEmptyMessages*|没有主题、邮件正文中没有任何内容以及没有附件的邮件被标记为高可信度垃圾邮件。|`X-CustomSpam: Empty Message`|
|**HTML 中的嵌入标记** <p> *MarkAsSpamEmbedTagsInHtml*|包含 `<embed>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <p> 此标记允许在 HTML 文档中嵌入不同类型的文档 (例如，声音、视频或图片) 。|`X-CustomSpam: Embed tag in html`|
|**HTML 格式 的 JavaScript 或 VBScript** <p> *MarkAsSpamJavaScriptInHtml*|使用 HTML 格式的 JavaScript Visual Basic Script Edition 的邮件标记为高可信度垃圾邮件。 <p> 这些脚本语言在电子邮件中用于使特定操作自动发生。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 格式的表单标记** <p> *MarkAsSpamFormTagsInHtml*|包含 `<form>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <p> 此标记用于创建网站表单。 电子邮件广告经常包含该标记，以获取收件人的信息。|`X-CustomSpam: Form tag in html`|
|**HTML 格式的框架或 iframe 标记** <p> *MarkAsSpamFramesInHtml*|包含或 `<frame>` `<iframe>` HTML 标记的邮件标记为高可信度垃圾邮件。 <p> 这些标记在电子邮件中用于设置页面的格式，用于显示文本或图形。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 格式的网络臭虫** <p> *MarkAsSpamWebBugsInHtml*|Web  bug (也称为 Web 信号 *)* 是一个图形元素 (通常小到一像素 x 一像素) 在电子邮件中用于确定邮件是否由收件人读取。 <p> 包含 Web Bug 的邮件被标记为高可信度垃圾邮件。 <p> 合法新闻稿可能会使用 Web Bug，尽管许多人认为这是一种隐私行为。 |`X-CustomSpam: Web bug`|
|**HTML 格式的对象标记** <p> *MarkAsSpamObjectTagsInHtml*|包含 `<object>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <p> 此标记允许插件或应用程序在 HTML 窗口中运行。|`X-CustomSpam: Object tag in html`|
|**敏感词** <p> *MarkAsSpamSensitiveWordList*|Microsoft 维护一个与潜在冒犯性邮件关联的动态但不可编辑的字词列表。 <p> 主题或邮件正文中包含敏感词列表中的词语的邮件被标记为高可信度垃圾邮件。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 记录：硬失败** <p> *MarkAsSpamSpfRecordHardFail*|从源电子邮件域的 SPF 发件人策略框架 (SPF) 记录中未指定的 IP 地址发送的邮件被标记为高可信度垃圾邮件。 <p> 测试模式对此设置不可用。|`X-CustomSpam: SPF Record Fail`|
|**发件人 ID 筛选硬失败** <p> *MarkAsSpamFromAddressAuthFail*|硬未通过条件发件人 ID 检查的邮件标记为垃圾邮件。 <p> 此设置将 SPF 检查与发件人 ID 检查相结合，以帮助防止包含伪造发件人的邮件头。 <p> 测试模式对此设置不可用。|`X-CustomSpam: SPF From Record Fail`|
|**退退** <p> *MarkAsSpamNdrBackscatter*|*退信式* 垃圾邮件是无用未送达 (，也称为"未送达报告"或) 伪造的发件人在电子邮件中退回邮件。 有关详细信息，请参阅退 [信消息和 EOP](backscatter-messages-and-eop.md)。 <p> 在下列环境中，无需配置此设置，因为会传递合法的NDDR，并且退退邮件被标记为垃圾邮件： <ul><li>Microsoft 365邮箱Exchange Online组织。</li><li>通过 EOP 路由 *出站* 电子邮件的本地电子邮件组织。</li></ul> <p> 在保护发送到内部部署邮箱的入站电子邮件的独立 EOP 环境中，打开或关闭此设置将产生以下结果： <ul><li> **On：** 传递合法NDR，退会标记为垃圾邮件。</li><li>**关闭**：合法NDR 和退箱经过常规垃圾邮件筛选。 大多数合法 NDR 将传递给原始邮件发件人。 一些（而不是全部）退信被标记为高可信度垃圾邮件。 根据定义，退信只能传递给欺骗性发件人，不能传递给原始发件人。</li></ul> <p> 测试模式对此设置不可用。|`X-CustomSpam: Backscatter NDR`|
|
