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
description: 管理员可以了解高级垃圾邮件筛选器服务 (ASF) Exchange Online Protection 和 EOP) 的反垃圾邮件策略中 () 。
ms.openlocfilehash: 2a79a6721a587e3033e71e6e46856a21cffe7bcc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827333"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>EOP 中禁用 (ASF) 高级垃圾邮件筛选器

> [!NOTE]
> 反垃圾邮件策略中当前可用的 ASF 设置正在弃用。 我们建议不要在反垃圾邮件策略中使用这些设置。 这些 ASF 设置的功能将合并到筛选堆栈的其他部分中。 有关详细信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，反垃圾邮件策略 (也称为垃圾邮件筛选策略或内容筛选器策略中的高级垃圾邮件筛选器 (ASF) 设置也称为垃圾邮件筛选策略或内容筛选策略) 允许管理员根据特定邮件属性将邮件标记为垃圾邮件。 ASF 专门提供这些属性，因为它们在垃圾邮件中通常是发现的。 根据属性，ASF 检测会将邮件标记为 **"垃圾邮件"** 或 **"高可信度垃圾邮件"。**

> [!NOTE]
> 启用一个或多个 ASF 设置是垃圾邮件筛选的一种有期方法。 不可将按 ASF 筛选的邮件报告为误报。 你可以按以下条件识别由 ASF 筛选的邮件：
>
> - 定期运行最终用户垃圾邮件隔离通知。
>
> - 存在隔离的已筛选邮件。
>
> - 添加到 `X-CustomSpam:` 邮件中的特定 X-header 字段，如本主题中所述。

以下各节介绍了安全 & 合规中心的反垃圾邮件策略、Exchange Online PowerShell 或独立 EOP PowerShell 和[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) ([为的](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)ASF 设置和) 选项。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="enable-disable-or-test-asf-settings"></a>启用、禁用或测试 ASF 设置

对于每个 ASF 设置，反垃圾邮件策略中提供以下选项：

- **On**： ASF adds the corresponding X-header field to the message， and either marks the **message** as Spam (SCL 5 or 6 for [Increase spam score settings](#increase-spam-score-settings)) or High **confidence spam** (SCL 9 for Mark as spam [settings](#mark-as-spam-settings)) .

- **关闭**：ASF 设置已禁用。 这是默认值，建议您不要更改此值。

- **Test**： ASF adds the corresponding X-header field to the message. TestModeAction 管理中心的值由 **Test 模式选项确定 (** *TestModeAction*) 值：

  - **无**：邮件路由和传递不受 ASF 检测的影响。 邮件仍受 EOP 中的其他类型的筛选和规则的约。

  - **添加添加到 *AddXHeader* (X 标头) **：X 标头值 `X-CustomSpam: This message was filtered by the custom spam filter option` 已添加到邮件中。 可以在收件箱规则或邮件流规则 (（亦称为"传输规则"）) 影响邮件的路由和传递。

  - **发送 Bcc 邮件 (*BccMessage*) **：指定的电子邮件地址 * (TestModeBccToRecipients* 参数) 值添加到邮件的 Bcc 字段，并且邮件会传递给 Bcc 收件人。 在安全与&中心内，可以使用分号分隔多个 (;) 。 在 PowerShell 中，可以使用逗号分隔多个电子邮件地址。

  **注意**：

  - 测试模式对以下 ASF 设置不可用：

    - **有条件发件人 ID 筛选：硬失败错误 (** *MarkAsSpamFromAddressAuthFail*) 
    - 使用*MarkAsSpamNdrBackscatter* (**NDR**) 
    - **SPF 记录***：MarkAsSpamSpfRecordHardFail (失败) *

  - 相同的测试模式操作 *适用于所有设置为* Test 的 ASF **设置**。 无法为不同 ASF 设置配置不同的测试模式操作。

## <a name="increase-spam-score-settings"></a>增加垃圾邮件得分设置

以下 ASF 设置可将检测邮件的垃圾邮件可信度 (SCL) 设置为 5 或 6，与 **垃圾邮件筛选** 的验证内容以及反垃圾邮件策略中的相应操作相对应。

****

|反垃圾邮件策略设置|说明|添加 X 标头|
|---|---|---|
|**到远程站点的图像链接** <br/><br/> *IncreaseScoreWithImageLinks*|包含 `<Img>` 指向远程站点链接的 HTML 标记 (例如，使用 http) 标记为垃圾邮件。|`X-CustomSpam: Image links to remote sites`|
|**URL 重定向到其他端口** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|包含重定向到 80 (HTTP) 、8080 (备用 HTTP) 或 443 (HTTPS 之外的 TCP 端口的超链接的邮件会) 被标记为垃圾邮件。|`X-CustomSpam: URL redirect to other port`|
|**URL 中的数字 IP 地址** <br/><br/> *IncreaseScoreWithNumericIps*|包含基于数字的 URL 的邮件 (通常会被) 为垃圾邮件"|`X-CustomSpam: Numeric IP in URL`|
|**至 .biz 或 .info 网站的 URL** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|邮件正文中包含 .biz 或 .info 链接的邮件会标记为垃圾邮件。|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>标记为垃圾邮件设置

以下 ASF 设置将检测到的邮件的 SCL 设置为 9，对应于 **"高可信** 度垃圾邮件筛选器"验证和反垃圾邮件策略中对应的操作。

****

|反垃圾邮件策略设置|说明|添加 X 标头|
|---|---|---|
|**空邮件** <br/><br/> *MarkAsSpamEmptyMessages*|邮件正文中没有主题内容，没有内容，附件也不会被标记为高可信度垃圾邮件。|`X-CustomSpam: Empty Message`|
|**HTML 格式 的 JavaScript 或 VBScript** <br/><br/> *MarkAsSpamJavaScriptInHtml*|使用 HTML 格式的 JavaScript 或 Visual Basic Script Edition 的邮件标记为高可信度垃圾邮件。 <br/><br/> 这些脚本语言用于电子邮件中，以导致自动出现特定操作。|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**HTML 格式的 Frame 或 IFrame 标签** <br><br/> *MarkAsSpamFramesInHtml*|包含或 `<frame>` `<iframe>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <br/><br/> 这些标记用于电子邮件中，以格式化显示文本或图形的页面。|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**HTML 格式的对象标记** <br><br/> *MarkAsSpamObjectTagsInHtml*|包含 `<object>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <br/><br/> 此标记允许在 HTML 窗口中运行插件或应用程序。|`X-CustomSpam: Object tag in html`|
|**HTML 格式的嵌入式标记** <br><br/> *MarkAsSpamEmbedTagsInHtml*|包含 `<embed>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <br/><br/> 此标记允许在 HTML 文档中嵌入不同种类的不同类型的文档 (如声音、电影或图片) 。|`X-CustomSpam: Embed tag in html`|
|**HTML 格式的表单标记** <br><br/> *MarkAsSpamFormTagsInHtml*|包含 `<form>` HTML 标记的邮件被标记为高可信度垃圾邮件。 <br/><br/> 此标记用于创建网站表单。 电子邮件广告经常包含该标记，以获取收件人的信息。|`X-CustomSpam: Form tag in html`|
|**HTML 格式的网络臭虫** <br><br/> *MarkAsSpamWebBugsInHtml*|Web *bug (* token>也称为 *网络信号*) 是一种图形元素 (通常小至一像素 x 1 像素) 则用于确定是否被阅读的邮件。 <br/><br/> 包含网页 bug 的邮件被标记为高可信度垃圾邮件。 <br/><br/> 合法新闻稿可能使用 Web Bug，尽管许多人认为这会简化隐私。 |`X-CustomSpam: Web bug`|
|**应用敏感词列表** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft 保留了与潜在的不可编辑邮件关联的词的动态列表（不可编辑）。 <br/><br/> 主题或邮件正文中包含敏感词语列表中的邮件标记为高可信度垃圾邮件。|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF 记录：硬失败** <br><br/> *MarkAsSpamSpfRecordHardFail*|从 IP 地址发送的邮件，但源电子邮件域的 SPF 发件人策略框架 (SPF) 记录中未指定的邮件被标记为高可信度垃圾邮件。 <br/><br/> 测试模式对此设置不可用。|`X-CustomSpam: SPF Record Fail`|
|**有条件发件人 ID 筛选：硬失败** <br><br/> *MarkAsSpamFromAddressAuthFail*|未通过有条件发件人 ID 检查的邮件被标记为垃圾邮件。 <br/><br/> 此设置组合了 SPF 检查与发件人 ID 检查，以提供保护，防止包含被阻止发件人的邮件标题。 <br/><br/> 测试模式对此设置不可用。|`X-CustomSpam: SPF From Record Fail`|
|**NDR 退信** <br><br/> *MarkAsSpamNdrBackscatter*|*退信式垃圾邮件是* 无用的未送达报告 (也称为 NDR，或退回电子邮件中的) 出电子邮件中的外部发件人导致的。 有关详细信息，请参阅[退信消息和 EOP。](backscatter-messages-and-eop.md) <br/><br/> 在下列环境中，不需要配置此设置，因为将传送合法的 NDR，并将退信消息标记为垃圾邮件： <ul><li>具有 Exchange Online 邮箱的 Microsoft 365 组织。</li><li>内部部署电子邮件组织通过 EOP 路由 *出站* 电子邮件。</li></ul><br/> 在将入站电子邮件保护到内部部署邮箱的独立 EOP 环境中，打开或关闭此设置可能会导致出现的结果： <ul><li> **打开**：发送合法的 NDR，并将退信标记为垃圾邮件。</li><li>**关闭**：合法的 NDR 和退信式垃圾邮件通过正常垃圾邮件筛选。 最合法的 NDR 将会传递给原始邮件发件人。 某些（不是所有）退信标记为高可信度垃圾邮件。 根据定义，退信式垃圾邮件只能传递到欺骗性发件人，不能传递到原始发件人。</li></ul><br/> 测试模式对此设置不可用。|`X-CustomSpam: Backscatter NDR`|
|
