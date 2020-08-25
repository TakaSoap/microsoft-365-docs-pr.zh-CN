---
title: EOP 中的 ASF 设置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 的反垃圾邮件策略中提供的高级垃圾邮件筛选器 (ASF) 设置。
ms.openlocfilehash: 6a670a9aba2204035646840d0f128ca9a90ece15
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867217"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP 中的高级垃圾邮件筛选器 (ASF) 设置

> [!NOTE]
> 反垃圾邮件策略中当前可用的 ASF 设置处于弃用过程中。 我们建议您不要在反垃圾邮件策略中使用这些设置。 这些 ASF 设置的功能将并入筛选堆栈的其他部分。 有关详细信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

在所有 Microsoft 365 组织中，EOP 中的反垃圾邮件策略中的高级垃圾邮件筛选器 (ASF) 设置允许管理员根据特定邮件属性将邮件标记为垃圾邮件。 ASF 专门针对这些属性，因为它们通常位于垃圾邮件中。 ASF 检测会将邮件标记为 **垃圾** 邮件或 **高可信度垃圾邮件**，具体取决于属性。

> [!NOTE]
> 启用一个或多个 ASF 设置是一种严格的垃圾邮件筛选方法。 您不能报告由 ASF 筛选为误报的邮件。 您可以通过以下方式识别通过 ASF 筛选的邮件：
>
> - 定期的最终用户垃圾邮件隔离通知。
>
> - 隔离中的已筛选邮件的存在情况。
>
> - 将 `X-CustomSpam:` 添加到邮件中的特定 X 标头字段，如本主题中所述。

以下各节介绍了安全性 & 合规性中心中的反垃圾邮件策略中提供的 ASF 设置和选项，以及 Exchange Online PowerShell 或独立 EOP PowerShell ([set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) and [set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)) 。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="enable-disable-or-test-asf-settings"></a>启用、禁用或测试 ASF 设置

对于每个 ASF 设置，反垃圾邮件策略中提供了以下选项：

- **On**： ASF 将对应的 X 头字段添加到邮件中，并将邮件标记为 **垃圾** 邮件 (SCL 5 或6，以 [增加垃圾邮件得分设置](#increase-spam-score-settings)) 或 **高可信度垃圾邮件** (SCL 9 [用作垃圾邮件设置](#mark-as-spam-settings)) 。

- **Off**：禁用 ASF 设置。 这是默认值，我们建议您不要更改它。

- **测试**： ASF 将对应的 X 标头字段添加到邮件中。  (*TestModeAction*) 值的**测试模式选项**决定了邮件所发生的情况：

  - **无**：邮件传递不受 ASF 检测的影响。 邮件仍服从其他类型的筛选和 EOP 中的规则。

  - ** (*AddXHeader*) 中添加默认的 x 标头文本 **：将 x 标头值 `X-CustomSpam: This message was filtered by the custom spam filter option` 添加到邮件中。 您可以使用收件箱规则或邮件流规则中的此值 (也称为传输规则) ，以影响邮件的传递。

  - **发送密件抄送邮件 (*BccMessage*) **：指定的电子邮件地址 (PowerShell) 中的 *TestModeBccToRecipients* 参数值将添加到邮件的 "密件抄送" 字段，并且邮件将传递给其他密件抄送收件人。 在安全 & 合规性中心中，可以用分号分隔多个电子邮件地址 (; ) 。 在 PowerShell 中，可以用逗号分隔多个电子邮件地址。

  **注意**：

  - 测试模式对以下 ASF 设置不可用：

    - **条件发件人 ID 筛选：硬失败** (*MarkAsSpamFromAddressAuthFail*) 
    - **NDR 退信** (*MarkAsSpamNdrBackscatter*) 
    - **SPF 记录： hard fail** (*MarkAsSpamSpfRecordHardFail*) 

  - 将相同的测试模式操作应用于 *所有* 设置为 **测试**的 ASF 设置。 您不能为不同的 ASF 设置配置不同的测试模式操作。

## <a name="increase-spam-score-settings"></a>增加垃圾邮件得分设置

以下 ASF 设置将垃圾邮件可信度 (SCL) 设置为5或6，这与 **垃圾** 邮件筛选器判定和反垃圾邮件策略中的相应操作相对应。

****

|反垃圾邮件策略设置|说明|添加了 X 标头|
|---|---|---|
|**到远程站点的图像链接** <br/><br/> *IncreaseScoreWithImageLinks*|包含 `<Img>` 指向远程网站的 HTML 标记链接的邮件 (例如，使用 http) 被标记为垃圾邮件。|`X-CustomSpam: Image links to remote sites`|
|**URL 重定向到其他端口** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|包含用于重定向到 80 (HTTP) 、8080 (备用 HTTP) 或 443 (HTTPS) 的超链接的邮件被标记为垃圾邮件。|`X-CustomSpam: URL redirect to other port`|
|**URL 中的数字 IP 地址** <br/><br/> *IncreaseScoreWithNumericIps*|包含基于数字的 Url 的邮件 (通常会将 IP 地址) 标记为垃圾邮件。|`X-CustomSpam: Numeric IP in URL`|
|**至 .biz 或 .info 网站的 URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|`.biz` `.info` 邮件正文中包含或链接的邮件被标记为垃圾邮件。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>标记为垃圾邮件设置

以下 ASF 设置将检测到的邮件的 SCL 设置为9，这对应于 **高可信度垃圾邮件** 筛选程序判定和反垃圾邮件策略中的相应操作。

****

|反垃圾邮件策略设置|说明|添加了 X 标头|
|---|---|---|
|**空邮件** <br/><br/> *MarkAsSpamEmptyMessages*|没有主题的邮件、邮件正文中没有内容，并且不会将任何附件标记为高可信度垃圾邮件。|`X-CustomSpam: Empty Message`|
|**HTML 格式 的 JavaScript 或 VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|在 HTML 中使用 JavaScript 或 Visual Basic Script Edition 的邮件被标记为高可信度垃圾邮件。 <br/><br/> 这些脚本语言在电子邮件中用于导致特定操作自动发生。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 格式的 Frame 或 IFrame 标签** <br><br/> *MarkAsSpamFramesInHtml*|包含 `<frame>` 或 HTML 标记的邮件被 `<iframe>` 标记为高可信度垃圾邮件。 <br/><br/> 这些标记在电子邮件中使用，以设置用于显示文本或图形的页面的格式。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 格式的对象标记** <br><br/> *MarkAsSpamObjectTagsInHtml*|包含 HTML 标记的邮件被 `<object>` 标记为高可信度垃圾邮件。 <br/><br/> 此标记允许插件或应用程序在 HTML 窗口中运行。|`X-CustomSpam: Object tag in html`|
|**HTML 格式的嵌入式标记** <br><br/> *MarkAsSpamEmbedTagsInHtml*|包含 HTML 标记的邮件被 `<embed>` 标记为高可信度垃圾邮件。 <br/><br/> 此标记允许在 HTML 文档中嵌入不同种类的文档 (例如，声音、视频或图片) 。|`X-CustomSpam: Embed tag in html`|
|**HTML 格式的表单标记** <br><br/> *MarkAsSpamFormTagsInHtml*|包含 HTML 标记的邮件被 `<form>` 标记为高可信度垃圾邮件。 <br/><br/> 此标记用于创建网站表单。 电子邮件广告经常包含该标记，以获取收件人的信息。|`X-CustomSpam: Form tag in html`|
|**HTML 格式的网络臭虫** <br><br/> *MarkAsSpamWebBugsInHtml*|*Web 臭虫* (也称为*Web 信标*) 是一个图形元素 (通常) 由一个像素组成，在电子邮件中使用它来确定邮件是否由收件人阅读。 <br/><br/> 包含 web bug 的邮件被标记为高可信度垃圾邮件。 <br/><br/> 合法的新闻稿可能会使用 web 臭虫，尽管许多人认为这是 invasion 的隐私。 |`X-CustomSpam: Web bug`|
|**应用敏感词列表** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft 维护一个动态但不可编辑的、与潜在攻击性邮件关联的单词列表。 <br/><br/> 包含主题或邮件正文中的敏感单词列表中的单词的邮件被标记为高可信度垃圾邮件。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 记录：硬失败** <br><br/> *MarkAsSpamSpfRecordHardFail*|从 SPF 发件人策略框架中未指定的 IP 地址发送的邮件 (的源电子邮件域的 DNS 中的 SPF) 记录被标记为高可信度垃圾邮件。 <br/><br/> 测试模式对此设置不可用。|`X-CustomSpam: SPF Record Fail`|
|**有条件发件人 ID 筛选：硬失败** <br><br/> *MarkAsSpamFromAddressAuthFail*|硬失败的邮件条件发件人 ID 检查被标记为垃圾邮件。 <br/><br/> 此设置将 SPF 检查与发件人 ID 检查组合在一起，以帮助防止包含伪造发件人的邮件头。 <br/><br/> 测试模式对此设置不可用。|`X-CustomSpam: SPF From Record Fail`|
|**NDR 退信** <br><br/> *MarkAsSpamNdrBackscatter*|*退信* 是非送达报告 (也称为 "ndr" 或 "退回邮件") 电子邮件中的伪造发件人造成的。 有关详细信息，请参阅 [退信 messages AND EOP](backscatter-messages-and-eop.md)。 <br/><br/> 您无需在以下环境中配置此设置，因为会传递合法 Ndr，并且退信会被标记为垃圾邮件： <ul><li>使用 Exchange Online 邮箱的 Microsoft 365 组织。</li><li>通过 EOP 路由 *出站* 电子邮件的内部部署电子邮件组织。</li></ul><br/> 在将入站电子邮件保护到本地邮箱的独立 EOP 环境中，打开或关闭此设置的结果如下： <ul><li> **打开**：将传递合法 ndr，并将退信标记为垃圾邮件。</li><li>**Off**：合法的 ndr 和退信通过正常的垃圾邮件筛选。 大多数合法的 Ndr 将传递给原始邮件发件人。 某些（而非全部）退信被标记为高可信度垃圾邮件。 根据定义，退信只能传递给欺骗性发件人，而不能传递给原始发件人。</li></ul><br/> 测试模式对此设置不可用。|`X-CustomSpam: Backscatter NDR`|
|
