---
title: 安全链接
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 在本文中，管理员可以了解 Office 365 的 Defender 中的安全链接保护，以保护其组织免受使用恶意 Url 的网络钓鱼和其他攻击的攻击。
ms.openlocfilehash: f2a747b0776a16ac981158ab866f28699583a06b
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616316"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的安全链接

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender For Office 365](office-365-atp.md)的商业客户。 如果使用的是 Outlook.com、Microsoft 365 系列或 Microsoft 365 个人，并且要在 Outlook 中查找有关 Safelinks 的信息，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全链接是在 [Office 365 的 Defender](office-365-atp.md) 中的一项功能，可提供邮件流中的入站电子邮件的 URL 扫描和重写，以及电子邮件和其他位置中的 url 和链接的单击时验证时间。 除了 Exchange Online Protection (EOP) 中的入站电子邮件 [和反恶意软件保护](anti-spam-and-anti-malware-protection.md) 之外，还会对安全链接进行扫描。 安全链接扫描可帮助保护您的组织免受网络钓鱼和其他攻击中使用的恶意链接的攻击。

安全链接保护在以下位置可用：

- **电子邮件**：对电子邮件中的链接的安全链接保护由安全链接策略控制。 没有默认安全链接策略，因此， **若要获取电子邮件中安全链接的保护，您需要创建一个或多个安全链接策略**。 有关说明，请参阅 [在 Microsoft Defender For Office 365 中设置安全链接策略](set-up-atp-safe-links-policies.md)。

  有关电子邮件的安全链接保护的详细信息，请参阅本文后面的 "电子邮件的 [安全链接设置](#safe-links-settings-for-email-messages) " 一节。

- **Microsoft 团队** (当前位于点击预览) ：对团队对话、组聊天或频道中的链接的安全链接保护也受安全链接策略控制。 没有默认安全链接策略，因此， **若要在团队中获取安全链接的保护，您需要创建一个或多个安全链接策略**。

  有关团队中的安全链接保护的详细信息，请参阅本主题后面的 " [Microsoft 团队的安全链接设置](#safe-links-settings-for-microsoft-teams) " 一节。

- **Office 365 应用程序**： office 365 应用程序的安全链接保护在受支持的桌面、移动设备和 web 接入点中可用。 在不安全链接策略 **之外** 的全局设置中为 Office 365 应用程序 **配置** 安全链接保护。 有关说明，请参阅 [在 Microsoft Defender For Office 365 中配置安全链接设置的全局设置](configure-global-settings-for-safe-links.md)。

  但是，对 Office 365 应用程序的安全链接保护仅 **适用** 于包含在活动安全链接策略中的用户。 如果用户不包含在活动的安全链接策略中，则用户不会在受支持的 Office 365 应用程序中获取安全链接保护。

  有关 Office 365 应用程序中的安全链接保护的详细信息，请参阅本文后面的 " [office 365 应用程序的安全链接设置](#safe-links-settings-for-office-365-apps) " 一节。

本文包括以下类型的安全链接设置的详细说明：

- **安全链接策略中的设置**：这些设置仅适用于特定策略中包含的用户，并且这些设置在策略之间可能有所不同。 这些设置包括：

  - [电子邮件的安全链接设置](#safe-links-settings-for-email-messages)
  - [Microsoft 团队的安全链接设置](#safe-links-settings-for-microsoft-teams)
  - ["安全链接策略" 中的 "不重写以下 Url" 列表](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **全局安全链接设置**：这些设置在全局范围内配置，而不是在安全链接策略中进行配置。 但是，这些设置仅适用于包含在活动安全链接策略中的用户。 这些设置包括：

  - [Office 365 应用程序的安全链接设置](#safe-links-settings-for-office-365-apps)
  - [安全链接的 "阻止以下 Url" 列表](#block-the-following-urls-list-for-safe-links)

下表介绍了 Microsoft 365 和 Office 365 组织中的安全链接的应用场景，其中包括适用于 Office 的 Defender 365 (换句话说，缺少许可不是示例) 中的一个问题。

****

|方案|结果|
|---|---|
|Jean 是市场营销部门的成员。 针对 Office 365 应用程序的安全链接保护在安全链接的全局设置中处于打开状态，并且存在适用于市场营销部门成员的安全链接策略。 Jean 在电子邮件中打开 PowerPoint 演示文稿，然后单击演示文稿中的 URL。|Jean 受安全链接保护。 <p> Jean 包含在安全链接策略中，并且启用了对 Office 365 应用的安全链接保护。 <p> 有关 Office 365 应用程序中的安全链接保护要求的详细信息，请参阅本文后面的 " [office 365 应用程序的安全链接设置](#safe-links-settings-for-office-365-apps) " 一节。|
|丽丽的 Microsoft 365 E5 组织没有配置安全链接策略。 Chris 收到来自外部发件人的电子邮件，其中包含最终单击的恶意网站的 URL。|丽丽不受安全链接的保护。 <p> 管理员必须至少为任何人创建一个安全链接策略，以在入站电子邮件中获取安全链接保护。 若要获取安全链接保护，必须在策略条件中包含 Chris。|
|在 Pat 的组织中，没有管理员创建任何安全链接策略，但启用了针对 Office 365 应用的安全链接保护。 Pat 打开 Word 文档并单击文件中的 URL。|Pat 不受安全链接的保护。 <p> 尽管 Office 365 应用程序的安全链接保护是全局打开的，但 Pat 不包含在任何活动的安全链接策略中，因此无法应用保护。|
|在工作先生的组织中，在 `https://tailspintoys.com` 安全链接的全局设置中的 " **阻止以下 url** " 列表中配置。 包含 "已加入" 的安全链接策略已存在。 先生接收包含 URL 的电子邮件 `https://tailspintoys.com/aboutus/trythispage` 。 先生单击 URL。|可能会自动阻止该 URL。这取决于列表中的 URL 条目和已使用的电子邮件客户端。 有关详细信息，请参阅本主题后面的 ["阻止以下 url" 安全链接的列表](#block-the-following-urls-list-for-safe-links) "一节。|
|晓明和 Julia 都适用于 contoso.com。 很长时间之前，管理员配置了适用于晓明和 Julia 的安全链接策略。 晓明将向 Julia 发送一封电子邮件，而不知道该电子邮件包含恶意 URL。|**如果** 应用于她的安全链接策略被配置为应用于内部收件人之间的邮件，则 Julia 受安全链接保护。 有关详细信息，请参阅本主题后面的 "电子邮件的 [安全链接设置](#safe-links-settings-for-email-messages) " 一节。|

## <a name="safe-links-settings-for-email-messages"></a>电子邮件的安全链接设置

安全链接扫描传入电子邮件中的已知恶意超链接。 使用 Microsoft 标准 URL 前缀重写扫描的 Url： `https://nam01.safelinks.protection.outlook.com` 。 重写链接后，将对其进行分析以查找潜在的恶意内容。

安全链接重写 URL 后，即使邮件转发或答复，URL 仍将被重写。 不会重写在转发或答复的邮件中添加的其他链接。

以下列表介绍了适用于电子邮件的安全链接策略中的设置：

- **选择邮件中未知的潜在恶意 url 的操作**：启用或禁用电子邮件中的安全链接扫描。 建议的值为 **"开**"。 启用此设置将导致以下操作。

  - Outlook (C2R) 在 Windows 上启用安全链接扫描。
  - 重写 Url，并在用户单击邮件中的 Url 时通过安全链接保护来路由用户。
  - 单击时，将对照已知恶意 Url 的列表和 ["阻止以下 url" 列表](#block-the-following-urls-list-for-safe-links)检查 url。
  - 没有有效信誉的 Url 将在后台以异步方式触发。

- **对指向文件的可疑链接和链接应用实时 URL 扫描**：启用对链接的实时扫描，包括指向可下载内容的电子邮件中的链接。 已启用建议的值。

  - **等待 URL 扫描完成后再传递邮件**：

    - 已启用：包含 Url 的邮件将一直保留到扫描完成为止。 仅在将 Url 确认为安全之后，才会传递邮件。 这是建议的值。
    - 已禁用：如果无法完成 URL 扫描，则发送邮件。

- **将安全链接应用于在组织内发送的电子邮件**：启用或禁用安全链接扫描在同一 Exchange Online 组织中的内部发件人和内部收件人之间发送的邮件。 已启用建议的值。

- **不跟踪用户单击**：启用或禁用存储安全链接单击电子邮件中单击的 url 的数据。 建议的值是将此设置保留为未选中状态 (跟踪用户单击) 。

  URL 单击 "跟踪" 以查找内部发件人和内部收件人之间发送的电子邮件中的链接当前不受支持。

- **不允许用户单击到原始 url**：允许或阻止用户通过单击 [警告页](#warning-pages-from-safe-links) 到原始 url。 建议值为已启用。

- **请勿重写以下 url**：保留 url。 保留一个不需要扫描的安全 Url 的自定义列表。 此列表对于每个安全链接策略都是唯一的。 有关 "不 **重写以下 url** " 列表的详细信息，请参阅本文后面的 ["不重写以下 Url" 安全链接策略中的列表](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) "一节。

有关安全链接策略的标准策略设置和严格策略设置的建议值的详细信息，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

- **收件人筛选器**：需要指定用于确定策略适用于的收件人条件和例外。 您可以将这些属性用于条件和例外：

  - **收件人为**
  - **收件人域为**
  - **收件人为以下组的成员**

  只能使用条件或例外一次，但条件或例外可以包含多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

- **优先级**：如果创建多个策略，则可以指定它们的应用顺序。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

  有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="how-safe-links-works-in-email-messages"></a>安全链接在电子邮件中的工作方式

在较高的层次上，以下是安全链接保护对电子邮件中的 Url 的处理方式：

1. 所有电子邮件都通过 EOP，其中 internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器，然后将邮件传递到收件人的邮箱。

2. 用户在其邮箱中打开邮件，然后单击邮件中的 URL。

3. 安全链接在打开网站之前立即检查 URL：

   - 如果 URL 包含在 " **阻止以下 url** " 列表中，则会打开一个 [阻止的 URL 警告](#blocked-url-warning) 。

   - 如果 URL 指向已确定为 "恶意" 的网站，则会出现 " [恶意网站警告](#malicious-website-warning) " 页 (或) 打开 "其他警告" 页面。

   - 如果该 URL 指向一个可下载文件，并且应用于该用户的策略中启用了指向 "文件" 设置的 " **应用实时 URL 扫描" 和 "指向文件** 设置的链接"，则会检查下载的文件。

   - 如果确定该 URL 是安全的，则会打开该网站。

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft 团队的安全链接设置

> [!IMPORTANT]
> 从2020年3月起，此功能处于预览阶段，仅适用于 Microsoft 团队技术采用计划的成员 (点击) 。 有关发布计划的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。

在安全链接策略中启用或禁用对 Microsoft 团队的安全链接保护。 具体来说，您可以使用 " **选择对 Microsoft 团队中的未知或可能有害的 url 执行操作** " 设置。 建议的值为 **"开**"。

适用于电子邮件中的链接的安全链接策略中的以下设置也适用于团队中的链接：

- **对指向文件的可疑链接和链接应用实时 URL 扫描**
- **不跟踪用户点击**
- **不允许用户单击到原始 URL**

前面的 " [电子邮件安全链接设置](#safe-links-settings-for-email-messages) " 部分对这些设置进行了说明。

打开 Microsoft 团队的安全链接保护后，在受保护的用户单击链接时，将根据已知恶意链接列表检查团队中的 Url (单击) 的保护。 不重写 Url。 如果发现链接是恶意的，用户将有以下体验：

- 如果在团队对话、分组聊天或频道中单击了链接，下面的屏幕截图中所示的警告页将显示在默认 web 浏览器中。
- 如果从固定的选项卡单击了链接，则警告页将出现在该选项卡中的 "团队" 界面中。由于安全原因，在 web 浏览器中打开链接的选项被禁用。
- 根据配置策略中的 " **不允许用户单击到原始 url** " 设置的方式，将不允许用户在原始 url 中单击，否则将不允许 (**继续 (不建议** 在屏幕截图) 中) 。 建议您启用 " **不允许用户单击到原始 url** 设置"，以便用户无法单击原始 url。

如果发送链接的用户未包含在启用团队保护的安全链接策略中，则用户可以在其计算机或设备上的原始 URL 中随意单击。

![报告恶意链接的工作组页面的安全链接。](../../media/tp-safe-links-for-teams-malicious.png)

单击 "警告" 页上的 "返回" 按钮 **将把用户** 返回到其原始的上下文或 URL 位置。 但是，再次单击原始链接将导致重新扫描 URL 的安全链接，因此警告页将重新出现。

### <a name="how-safe-links-works-in-teams"></a>安全链接在团队中的工作方式

在较高的层次上，以下是 Microsoft 团队中的 Url 的安全链接保护的工作方式：

1. 用户启动 "团队" 应用。

2. Microsoft 365 验证用户的组织是否包含 Microsoft Defender for Office 365，以及该用户是否包含在启用 Microsoft 团队保护的活动安全链接策略中。

3. 在聊天、群研讨、频道和选项卡中单击用户时，将对 Url 进行验证。

## <a name="safe-links-settings-for-office-365-apps"></a>Office 365 应用程序的安全链接设置

针对 Office 365 应用程序的安全链接保护将检查 Office 文档中的链接，而不是电子邮件中的链接 (，但它可以检查电子邮件中附加的 Office 文档中的链接，) 中打开该文档。

适用于 Office 365 应用程序的安全链接保护具有以下客户端要求：

- Microsoft 365 应用或 Microsoft 365 商业高级版。
  - Windows、Mac 或 web 浏览器上的当前版本的 Word、Excel 和 PowerPoint。
  - IOS 或 Android 设备上的 Office 应用程序。
  - Windows 上的 Visio。
  - 在 web 浏览器中的 OneNote。

- Office 365 应用程序配置为使用新式验证。 有关详细信息，请参阅 [如何在 office 2013、office 2016 和 office 2019 客户端应用程序中运行新式验证](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)。

- 用户使用其工作或学校帐户登录。 有关详细信息，请参阅 [登录 Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)。

为安全链接的全局设置（而不是安全链接策略）中的 Office 365 应用程序配置安全链接保护。 但是，为了能够应用 Office 365 应用程序的安全链接保护，打开 Office 文档并单击链接的用户必须包含在活动的安全链接策略中。

以下安全链接设置适用于 Office 365 应用：

- **Office 365 应用程序**：启用或禁用在受支持的 Office 365 应用程序中进行安全链接扫描。 默认值和建议值为 **"开**"。

- **在用户单击安全链接时不进行跟踪**：启用或禁用存储安全链接单击在桌面版本 Word、Excel、PowerPoint 和 Visio 中单击的 url 的数据。 建议的值为 **Off**，这表示跟踪用户单击。

- **不允许用户单击 "通过指向原始 url 的安全链接"**：允许或阻止用户在桌面版本 Word、Excel、PowerPoint 和 Visio 中的原始 url 中单击，以在 [网页](#warning-pages-from-safe-links) 中单击。 默认值和建议值为 **"开**"。

若要为 Office 365 应用程序配置安全链接设置，请参阅 [Configure Safe links protection For office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。

有关标准策略设置和严格策略设置的推荐值的详细信息，请参阅 [安全链接的全局设置](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)。

### <a name="how-safe-links-works-in-office-365-apps"></a>安全链接在 Office 365 应用程序中的工作方式

在较高的层次上，以下是安全链接保护对 Office 365 应用中的 Url 的工作方式。 上一节中介绍了受支持的 Office 365 应用程序。

1. 用户在包含 Microsoft 365 应用或 Microsoft 365 商业高级版的组织中使用其工作或学校帐户进行登录。

2. 用户打开并单击链接到受支持的 Office 应用程序中的 Office 文档。

3. 安全链接在打开目标网站之前立即检查 URL：

   - 如果 URL 包含在跳过安全链接扫描的列表中 (**阻止以下 url** 列表) 将打开 " [阻止的 url 警告](#blocked-url-warning) " 页。

   - 如果 URL 指向已确定为 "恶意" 的网站，则会出现 " [恶意网站警告](#malicious-website-warning) " 页 (或) 打开 "其他警告" 页面。

   - 如果该 URL 指向一个可下载文件，并且应用于该用户的安全链接策略已配置为扫描到可下载内容的链接， (会对 **指向文件) 的可疑链接和链接应用实时 URL 扫描，同时** 会检查可下载文件。

   - 如果该 URL 被认为是安全的，则会将用户转到该网站。

   - 如果安全链接扫描无法完成，则安全链接保护不会触发。 在 Office 桌面客户端中，用户将收到警告，然后再继续转到目标网站。

> [!NOTE]
> 在每个会话开始时可能需要几秒钟的时间来验证用户是否已启用 Office 的安全链接。

## <a name="block-the-following-urls-list-for-safe-links"></a>安全链接的 "阻止以下 Url" 列表

**Block 以下 url** 列表定义了以下位置中的安全链接扫描始终阻止的链接：

- 电子邮件。
- Windows 和 Mac 中的 Office 365 应用中的文档。
- Office for iOS 和 Android 中的文档。

当活动安全链接策略中的用户在受支持的应用程序中单击被阻止的链接时，将转到 " [阻止的 URL 警告](#blocked-url-warning) " 页。

可以在安全链接的全局设置中配置 Url 的列表。 有关说明，请参阅 [Configure the "Block 以下 url" 列表](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。

**注意**：

- 有关在任何位置阻止的真正通用的 Url 列表，请参阅 [在租户允许/阻止列表中管理 url](tenant-allow-block-list.md)。

- 限额
  - 最大条目数为500。
  - 条目的最大长度为128个字符。
  - 所有条目都不能超过10000个字符。

- 不要在 URL 的末尾包含正斜杠 (`/`) 。 例如，使用 `https://www.contoso.com` ，not `https://www.contoso.com/` 。

- 例如 "仅域"-"URL (" `contoso.com` 或 " `tailspintoys.com`) " 将阻止包含域的任何 URL。

- 您可以阻止子域，而不阻止整个域。 例如， `toys.contoso.com*` 阻止包含子域的任何 url，但它不会阻止包含完整域的 url `contoso.com` 。

- 每个 URL 条目最长可包含三个通配符 (`*`) 。

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"阻止以下 Url" 列表的输入语法

下表介绍了您可以输入的值的示例及其结果：

****

|值|结果|
|---|---|
|`contoso.com` <p> 或 <p> `*contoso.com*`|阻止域、子域和路径。 例如、、 `https://www.contoso.com` `https://sub.contoso.com` 和 `https://contoso.com/abc` 将被阻止。|
|`https://contoso.com/a`|块 `https://contoso.com/a` ，但不是其他子路径（如） `https://contoso.com/a/b` 。|
|`https://contoso.com/a*`|块 `https://contoso.com/a` 和其他子路径（如） `https://contoso.com/a/b` 。|
|`https://toys.contoso.com*`|`toys`在此示例中阻止子域 () 但允许单击其他域 url (如 `https://contoso.com` 或 `https://home.contoso.com`) 。|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"安全链接策略" 中的 "不重写以下 Url" 列表

> [!NOTE]
> 如果您的组织使用安全链接策略，则不会 **重写以下 url** 列表，这是第三方仿冒测试的唯一受支持的方法。

每个安全链接策略包含 **"不重写以下 url"** 列表，可用于指定不是由安全链接扫描重写的 url。 换句话说，此列表允许包含在该策略中的用户访问指定的 Url，该 Url 将被安全链接阻止。 您可以在不同的安全链接策略中配置不同的列表。 策略处理在第一 (之后停止，最高优先级的) 策略将应用于用户。 因此，只有一个 **不重写以下 url** 列表应用于包含在多个活动安全链接策略中的用户。

若要将条目添加到新的或现有安全链接策略的列表中，请参阅 [创建安全链接策略](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 或 [修改安全链接策略](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。

**注意**：

- 以下客户端无法识别 "在安全链接策略中不 **重写以下 url"** 列表。 可以阻止策略中包含的用户基于在这些客户端中的安全链接扫描结果来访问 Url：

  - Microsoft Teams
  - Office web apps

  有关允许随处使用的 Url 的真正通用列表，请参阅 [在租户允许/阻止列表中管理 url](tenant-allow-block-list.md)。

- 考虑将常用的内部 Url 添加到列表中，以改进用户体验。 例如，如果您有本地服务（如 Skype for Business 或 SharePoint），则可以添加这些 Url 以将其排除在扫描之外。

- 如果您已不重写安全链接策略中 **的以下 url** 条目，请务必查看列表并根据需要添加通配符。 例如，您的列表有类似的条目， `https://contoso.com/a` 后来决定包含类似的子路径 `https://contoso.com/a/b` 。 不添加新条目，而是将通配符添加到现有条目中，使其变得如此 `https://contoso.com/a/*` 。

- 每个 URL 条目最长可包含三个通配符 (`*`) 。 通配符显式包含前缀或子域。 例如，输入项与 `contoso.com` 不同 `*.contoso.com/*` ，因为 `*.contoso.com/*` 允许用户访问指定域中的子域和路径。

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"不重写以下 Url" 列表的输入语法

下表介绍了您可以输入的值的示例及其结果：

****

|值|结果|
|---|---|
|`contoso.com`|允许访问（ `https://contoso.com` 而非子域或路径）。|
|`*.contoso.com/*`|允许访问域、子域和路径 (例如，、、 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` 或 `https://www.contoso.com/a`) 。 <p> 此条目的本质上优于 `*contoso.com*` ，因为它不允许潜在的欺诈网站，如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|允许访问 `https://contoso.com/a` ，但不允许像这样的子路径 `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|允许访问 `https://contoso.com/a` 和子路径，如 `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>来自安全链接的警告页面

此部分包含在单击 URL 时安全链接保护触发的各种警告页面的示例。

请注意，已更新几个警告页面。 如果您还没有看到更新的页面，很快就会了。 更新的页面包括新的配色方案、更多的详细信息，以及在给定警告和建议的情况下能够继续使用网站的功能。

### <a name="scan-in-progress-notification"></a>扫描正在进行的通知

安全链接正在扫描单击的 URL。 您可能需要等待几分钟，然后再次尝试链接。

!["正在扫描链接" 通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

原始通知页面如下所示：

![原始 "正在扫描链接" 通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>可疑邮件警告

单击的 URL 位于类似于其他可疑邮件的电子邮件中。 建议您先仔细检查电子邮件，然后再继续转到网站。

!["从可疑邮件单击链接" 警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>网络钓鱼尝试警告

单击的 URL 位于已标识为 "网络钓鱼" 攻击的电子邮件中。 因此，电子邮件中的所有 Url 都将被阻止。 我们建议您不要继续转到网站。

!["从仿冒邮件单击链接" 警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>恶意网站警告

单击的 URL 指向已被标识为恶意的网站。 我们建议您不要继续转到网站。

!["此网站被分类为恶意" 警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

原始警告页面如下所示：

![原始 "此网站已被分类为恶意" 警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>阻止的 URL 警告

您的组织中的管理员已手动阻止单击的 URL (在 "安全链接) 的全局设置" 中 **阻止以下 url** 列表。 安全链接未扫描链接，因为它已被手动阻止。

管理员手动阻止特定 Url 的原因有多种。 如果您认为不应阻止该网站，请与管理员联系。

!["此网站被管理员阻止" 警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

原始警告页面如下所示：

![原始 "此网站已根据组织的 URL 策略被阻止" 警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>错误警告

出现了某种类型的错误，无法打开该 URL。

!["无法加载您尝试访问的页面" 警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

原始警告页面如下所示：

![原始 "无法加载此网页" 警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
