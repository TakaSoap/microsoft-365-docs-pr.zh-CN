---
title: 发送电子邮件通知并显示 DLP 策略的策略提示
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: 了解如何向 DLP) 策略 (数据丢失防护添加策略提示，以通知用户他们正在处理与 DLP 策略冲突的内容。
ms.openlocfilehash: cab4332324ec8d83b201823c98b952995e12962d
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760484"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>发送电子邮件通知并显示 DLP 策略的策略提示

数据丢失防护 (DLP) 策略可用于跨 Office 365 识别、监视和保护敏感信息。 你希望组织中使用此敏感信息的人员遵守 DLP 策略，但你不希望不必要地阻止他们完成工作。 这是电子邮件通知和策略提示可以提供帮助的情况。

![消息栏在 Excel 2016 中显示策略提示](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

在合规中心创建 DLP 策略时，可以将用户通知配置为：

- 向你选择的描述问题的人员发送电子邮件通知。

- 显示与 DLP 策略冲突的内容的策略提示：

  - 对于 Outlook 网页版 和 Outlook 2013 及更高版本中的电子邮件，在撰写邮件时，策略提示将显示在收件人上方的邮件顶部。

  - 对于OneDrive for Business帐户或 SharePoint Online 网站中的文档，策略提示由项上显示的警告图标指示。 若要查看详细信息，可以选择项目，然后选择 **“信息信息**![”窗格图标。](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) 在页面右上角打开详细信息窗格。

  - 对于存储在 DLP 策略中OneDrive for Business网站或 SharePoint Online 网站中的Excel、PowerPoint和 Word 文档，策略提示将显示在“消息栏”和“后台”视图 (**“文件**”菜单\>**信息**) 。

## <a name="add-user-notifications-to-a-dlp-policy"></a>将用户通知添加到 DLP 策略

创建 DLP 策略时，可以启用 **用户通知**。 启用用户通知后，Microsoft 365发送电子邮件通知和策略提示。 可以自定义向谁发送通知电子邮件、电子邮件文本和策略提示文本。

1. 转到 [https：// (https://compliance.microsoft.com/permissions] (https：// (https://compliance.microsoft.com/permissions)。

2. 使用工作或学校帐户进行登录。 你现在在安全 &amp; 合规中心。

3. 在安全&amp;合规中心\>左侧导航\>**数据丢失防护** \> **策略** \> **+ 创建策略**。

    ![创建策略按钮。](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)

4. 选择 **保护下一** 步所需的\>敏感信息类型的 DLP 策略模板。

    若要从空模板开始，请选择 **“下一步****自定义自定义** \> **策略**\>”。

5. 将策略命名为 **“下一**\>步”。

6. 若要选择要保护 DLP 策略的位置，请执行以下操作之一：

   - 选择“**Office 365下** 一\>步 **”中的所有位置**。

   - 选择“让我选择 **下一步****的特定位置**\>”。

   若要包括或排除整个位置，例如所有Exchange电子邮件或所有OneDrive帐户，请打开或关闭该位置的 **状态**。

   若要仅包含特定SharePoint网站或OneDrive帐户，请将 **状态** 切换为打开，然后单击 **“包括**”下的链接以选择特定的网站或帐户。

7. 选择“**下一步****使用高级设置**\>”。

8. 选择“**+ 新建规则**”。

9. 在规则编辑 **器的“用户通知**”下，打开状态。

    ![规则编辑器的“用户通知”部分。](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> 未受保护地发送通知电子邮件。

## <a name="options-for-configuring-email-notifications"></a>用于配置电子邮件通知的选项

对于 DLP 策略中的每个规则，您可以：

- 将通知发送给您选择的人员。这些人员可以包含内容的所有者、最后一次修改内容的人员、存储内容的网站所有者或特定用户。

- 使用 HTML 或令牌自定义通知中包含的文本。 有关详细信息，请参阅下面的部分。

> [!NOTE]
> 电子邮件通知只能发送到单个收件人，而不能发送给组或通讯组列表。 只有新内容才会触发电子邮件通知。 编辑现有内容将触发策略提示，但不会触发电子邮件通知。

![电子邮件通知选项。](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)

### <a name="default-email-notification"></a>默认电子邮件通知

通知具有以所执行操作开头的主题行，例如电子邮件的“通知”、“邮件被阻止”或文档的“访问被阻止”。 如果通知是关于文档的，则通知消息正文包含一个链接，该链接将转到文档存储的站点，并打开文档的策略提示，可在其中解决任何问题 (请参阅以下有关策略提示) 部分。 如果通知是关于消息的，则通知包含与 DLP 策略匹配的消息作为附件。

![通知消息。](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)

默认情况下，通知显示类似于网站上以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。

|如果 DLP 策略规则执行此操作...|然后SharePoint或OneDrive for Business文档的默认通知说明了这一点...|然后Outlook消息的默认通知说明了这一点...|
|---|---|---|
|发送通知，但不允许重写|此项与您的组织中的策略相冲突。|电子邮件与组织中的策略冲突。|
|阻止访问，发送通知，并允许重写|此项与您的组织中的策略相冲突。 如果不解决此冲突，可能会阻止对此文件的访问。|电子邮件与组织中的策略冲突。 消息未传递给所有收件人。|
|阻止访问，并向发送通知|此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。|电子邮件与组织中的策略冲突。 消息未传递给所有收件人。|

### <a name="custom-email-notification"></a>自定义电子邮件通知

可以创建自定义电子邮件通知，而不是向最终用户或管理员发送默认电子邮件通知。 自定义电子邮件通知支持 HTML，并且具有 5，000 个字符的限制。 可以使用 HTML 在通知中包含图像、格式和其他品牌。

还可以使用以下令牌来帮助自定义电子邮件通知。 这些令牌是变量，由发送的通知中的特定信息替换。

|标记|说明|
|---|---|
|%%AppliedActions%%|应用于内容的操作。|
|%%ContentURL%%|SharePoint Online 网站或OneDrive for Business网站上文档的 URL。|
|%%MatchedConditions%%|与内容匹配的条件。 使用此令牌可告知用户内容可能出现的问题。|

![显示令牌显示位置的通知消息。](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)

## <a name="options-for-configuring-policy-tips"></a>用于配置策略提示的选项

对于 DLP 策略中的每个规则，您可以配置策略提示用于：

- 简单地通知该用户此项内容与 DLP 策略相冲突，以便用户可以执行相应的操作来解决此冲突。 可以使用默认文本 (查看下表) 或输入有关组织特定策略的自定义文本。

- 允许用户替换 DLP 策略。（可选） 您可以：

  - 要求用户输入替换该策略的业务理由。 此信息已记录，可以在安全&amp;合规中心的“**报告**”部分的 DLP 报表中查看。

  - 允许用户报告误报并替换 DLP 策略。此信息还被记录下来用于报告，以便您可以使用误报来微调您的规则。

![策略提示选项。](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)

例如，你可能已将 DLP 策略应用于OneDrive for Business站点，用于检测 PII)  (个人身份信息，并且此策略有三个规则：

1. 第一个规则：如果在文档中检测到包含此敏感信息的实例少于五个，并且该文档与组织内部的人员共享，则“发送通知”操作将显示策略提示。对于策略提示，无需提供任何替换选项，因为此规则只是通知相关人员，但不会阻止访问。

2. 第二个规则：如果在文档中检测到包含此敏感信息的实例多于五个，并且该文档与组织内部的人员共享，则“阻止访问内容”操作将限制文件权限，并且“发送通知”操作会允许用户通过提供业务理由来替换该规则中的操作。 组织的业务有时要求内部人员共享 PII 数据，并且不希望 DLP 策略阻止此工作。

3. 第三个规则：如果在文档中检测到包含此敏感信息的实例多于五个，并且该文档与组织外部的人员共享，则“阻止访问内容”操作将限制文件权限，并且“发送通知”操作将不允许用户替换该规则中的操作，因为该信息是与外部共享的。决不允许您组织中的用户在组织外部共享 PII 数据。

### <a name="user-override-support"></a>用户替代支持

以下几点有助于您对使用策略提示替换规则的理解：

- 要重写的选项是按规则执行的，它替代规则中的所有操作 (除了发送通知之外，无法重写) 。

- 内容可以与 DLP 策略中的多个规则匹配，但只会显示来自最严格、优先级最高的规则的策略提示。 例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。 这会让用户看不到策略提示的级联方式。

- 如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。

- 如果使用 WithoutJustification、WithJustification 或 FlasePositives 设置 NotifyAllowOverride 操作，请确保 BlockAccess 设置为 true，BlockAccessScope 具有适当的值。 否则会出现策略提示，但用户将找不到一个选项以理由替代电子邮件。

#### <a name="availability-of-override"></a>替代的可用性

|通知规则 |通知/阻止操作  |替代可用  |需要理由  |
|---------|---------|---------|---------|
|仅通知     |通知         |否         |否         |
|Notify + AllowOverride     |通知         |否         |否         |
|Notify + AllowOverride + False positive     |通知         |否         |否         |
|通知 + AllowOverride + 并提供理由     |通知         |否         |否         |
|Notify + AllowOverride + False positive + 无理    |通知         |否         |否         |
|通知 + AllowOverride + False positive + 并提供理由     |通知         |否         |否         |
|Notify + Block     |阻止         |否         |否         |
|Notify + Block + AllowOverride     |阻止         |是         |否         |
|Notify + Block + AllowOverride + False positive     |阻止         |是         |否         |
|通知 + 阻止 + AllowOverride + 并提供理由     |阻止         |是         |是         |
|Notify + Block + AllowOverride + False positive + 无理     |阻止         |是         |否         |
|Notify + Block + AllowOverride + False positive + With justification     |阻止         |是         |是         |


## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>OneDrive for Business 网站或 SharePoint Online 网站上的策略提示

当OneDrive for Business网站或 SharePoint Online 网站上的文档与 DLP 策略中的规则匹配，并且该规则使用策略提示时，策略提示会在文档上显示特殊图标：

1. 如果该规则发送有关该文件的通知，则会显示警告图标。

2. 如果该规则阻止访问该文档，则会显示阻止图标。

   ![OneDrive帐户中文档上的策略提示图标。](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)

若要对文档执行操作，可以选择项目\>“选择 **信息信息**![”窗格图标。](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) 在页面右上角打开“详细信息”窗格“\>**视图策略提示**。

策略提示会列出问题及其内容，如果对策略提示配置了这些选项，则您可以选择“解决”，然后选择“替换”策略提示或“报告”误报。

![显示策略提示的信息窗格。](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)

![具有要替代的选项的策略提示。](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)

将 DLP 策略同步到网站，并定期以异步方式根据这些策略对内容进行评估，因此，您创建 DLP 策略的时间与开始看到策略提示的时间之间可能出现短暂的延迟。类似延迟还有可能出现在从您解决或替换策略提示到网站的文档上的图标消失的这段时间里。

### <a name="default-text-for-policy-tips-on-sites"></a>网站上的策略提示的默认文本

默认情况下，策略提示显示在网站上类似于以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。

|如果 DLP 策略规则执行此操作...|然后默认策略提示说明了这一点...|
|---|---|
|发送通知，但不允许重写|此项与您的组织中的策略相冲突。|
|阻止访问，发送通知，并允许重写|此项与您的组织中的策略相冲突。 如果不解决此冲突，可能会阻止对此文件的访问。|
|阻止访问，并向发送通知|此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。|

### <a name="custom-text-for-policy-tips-on-sites"></a>网站上的策略提示的自定义文本

可以从电子邮件通知中单独自定义策略提示的文本。 与电子邮件通知的自定义文本不同 (请参阅上述部分) ，策略提示的自定义文本不接受 HTML 或令牌。 相反，策略提示的自定义文本是纯文本，只有 256 个字符的限制。

## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>2013 Outlook 网页版和 Outlook 2013 及更高版本中的策略提示

在 Outlook 网页版 和 Outlook 2013 及更高版本中撰写新电子邮件时，如果在 DLP 策略中添加与规则匹配的内容，并且该规则使用策略提示，则会看到策略提示。 策略提示显示在邮件顶部，位于收件人上方，而消息正在撰写。

![正在撰写的邮件顶部的策略提示。](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)

策略提示适用于敏感信息是否显示在消息正文、主题行甚至消息附件中，如下所示。

![显示附件与 DLP 策略冲突的策略提示。](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)

如果策略提示配置为允许重写，则可以选择 **“显示详细信息** \> **替代”**\>输入业务理由或报告误报\>**替代**。

![已展开消息中的策略提示以显示“替代”选项。](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)

![策略提示对话框，可在其中重写策略提示。](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)

请注意，向电子邮件添加敏感信息时，添加敏感信息和显示策略提示时之间可能会有延迟。 当电子邮件使用Office消息加密 (OME) 进行加密，并且用于检测电子邮件的策略使用检测加密条件策略提示时，将不会显示。

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>Outlook 2013 及更高版本仅支持显示某些条件的策略提示

目前，Outlook 2013 及更高版本支持仅针对以下条件显示策略提示：

- 内容包含
- 共享内容

请注意，异常被视为条件，所有这些条件都适用于Outlook，其中它们将匹配内容并强制对内容执行保护措施。 但尚不支持向用户显示策略提示。 此外，Outlook不支持显示应用于动态分发组的 DLP 策略的策略提示。

### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a>Exchange管理中心与安全&amp;合规中心中的策略提示

策略提示可以适用于在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理中心创建的</a> DLP 策略和邮件流规则，也可以使用在安全&amp;合规中心创建的 DLP 策略，但不能同时使用这两者。 这是因为这些策略存储在不同的位置，但策略提示只能从单个位置绘制。

如果已在Exchange管理中心配置策略提示，则在安全&amp;合规中心配置的任何策略提示都不会显示在 Outlook 网页版 和 2013 及更高版本 Outlook的用户中，直到关闭Exchange管理中心中的提示。 这可确保当前Exchange邮件流规则 (也称为传输规则) 将继续工作，直到选择切换到安全&amp;合规中心为止。

请注意，虽然策略提示只能从单个位置绘制，但始终会发送电子邮件通知，即使你在安全&amp;合规中心和Exchange管理中心都使用 DLP 策略。

### <a name="default-text-for-policy-tips-in-email"></a>电子邮件中策略提示的默认文本

默认情况下，策略提示显示类似于以下电子邮件的文本。

|如果 DLP 策略规则执行此操作...|然后默认策略提示说明了这一点...|
|---|---|
|发送通知，但不允许重写|电子邮件与组织中的策略冲突。|
|阻止访问，发送通知，并允许重写|电子邮件与组织中的策略冲突。|
|阻止访问，并向发送通知|电子邮件与组织中的策略冲突。|

## <a name="policy-tips-in-excel-powerpoint-and-word"></a>Excel、PowerPoint 和 Word 中的策略提示

当用户在桌面版本的 Excel、PowerPoint 和 Word 中处理敏感内容时，策略提示可以实时通知他们内容与 DLP 策略冲突。 这要求：

- Office 文档存储在 OneDrive for Business 网站或 SharePoint Online 网站上。

- 站点包含在配置为使用策略提示的 DLP 策略中。

Office桌面程序直接从Office 365同步 DLP 策略，然后扫描文档以确保它们不会与 DLP 策略冲突，并实时显示策略提示。

> [!NOTE]
> Office桌面应用自行扫描文档以确定是否应显示 DLP 策略提示;它们不显示SharePoint联机网站或 OneDrive for Business网站已确定应显示在文件上的策略提示。 因此，你可能并不总是会在桌面应用中看到 DLP 策略提示，该提示在 SharePoint Online 网站或OneDrive for Business网站中看到。 相比之下，Web 上的Office应用程序仅显示 DLP 策略提示，SharePoint联机网站或OneDrive for Business网站已确定应显示这些提示。

根据您在 DLP 策略中对策略提示的配置方式，用户可以选择忽略策略提示、使用或不使用业务理由替换策略或报告误报。

在消息栏上显示策略提示。

![消息栏显示Excel 2016中的策略提示。](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

策略提示也显示在 Backstage 视图（“文件”选项卡上）中。

![Backstage 在Excel 2016中显示策略提示。](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)

如果对 DLP 策略中的策略提示配置了这些选项，您可以选择“解决”以“替换”策略提示或“报告”误报。

![Excel 2016的 Backstage 中的策略提示选项。](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)

在每个Office桌面程序中，人们可以选择关闭策略提示。 如果已关闭，则只是简单通知的策略提示将不会显示在消息栏或 Backstage 视图（“文件”选项卡上）上。 但是，仍会显示有关阻止和替换的策略提示，并且仍将收到电子邮件通知。 此外，关闭策略提示并不会将文档从任何已对其应用的 DLP 策略中予以免除。

### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示的默认文本

默认情况下，策略提示将在打开文档的消息栏和 Backstage 视图中显示类似于以下的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。

|如果 DLP 策略规则执行此操作...|然后默认策略提示说明了这一点...|
|---|---|
|发送通知，但不允许重写|此文件与您的组织中的策略相冲突。 有关详细信息，请转到 **“文件”** 菜单。|
|阻止访问，发送通知，并允许重写|此文件与您的组织中的策略相冲突。 如果不解决此冲突，可能会阻止对此文件的访问。 有关详细信息，请转到 **“文件”** 菜单。|
|阻止访问，并向发送通知|此文件与您的组织中的策略相冲突。 如果不解决此冲突，可能会阻止对此文件的访问。 有关详细信息，请转到 **“文件”** 菜单。|

### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a>Excel、PowerPoint 和 Word 中的策略提示的自定义文本

可以从电子邮件通知中单独自定义策略提示的文本。 与电子邮件通知的自定义文本不同 (请参阅上述部分) ，策略提示的自定义文本不接受 HTML 或令牌。 相反，策略提示的自定义文本是纯文本，只有 256 个字符的限制。

## <a name="more-information"></a>更多信息

- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [根据模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
- [预览)  (DLP 策略条件、异常和操作 ](./dlp-microsoft-teams.md)
- [创建 DLP 策略来保护具有 FCI 或其他属性的文档](protect-documents-that-have-fci-or-other-properties.md)
- [DLP 策略模板包含的内容](what-the-dlp-policy-templates-include.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
