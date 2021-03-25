---
title: 安全链接
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
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
description: 在本文中，管理员可以了解 Defender for Office 365 中的安全链接保护，以保护其组织免受网络钓鱼和使用恶意 URL 的其他攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ec3ab1a255e9eaa8c190ed5c248c9587273e03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203842"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的安全链接

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。 如果你使用的是 Outlook.com、Microsoft 365 家庭版或 Microsoft 365 个人版，并且正在查找有关 Outlook 中安全链接的信息，请参阅高级安全[Outlook.com。](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

安全链接是 Defender [for Office 365](defender-for-office-365.md) 中的一项功能，它提供邮件流中入站电子邮件的 URL 扫描和重写，以及电子邮件和其他位置中 URL 和链接的单击验证时间。 除了 Exchange Online Protection ([](anti-spam-and-anti-malware-protection.md) EOP 策略中的入站电子邮件中的常规反垃圾邮件和反恶意软件保护外，安全链接扫描) 。 安全链接扫描可帮助保护组织免受钓鱼和其他攻击中使用的恶意链接的攻击。

安全链接保护可在以下位置使用：

- **电子邮件：** 电子邮件中链接的安全链接保护由安全链接策略控制。 没有默认的安全链接策略，因此若要保护电子邮件中的安全链接，需要创建一 **个或多个安全链接策略**。 有关说明，请参阅在 [Microsoft Defender for Office 365](set-up-safe-links-policies.md)中设置安全链接策略。

  有关电子邮件的安全链接保护详细信息，请参阅本文稍后介绍的电子邮件的安全[](#safe-links-settings-for-email-messages)链接设置部分。

- **Microsoft Teams** (TAP Preview) ：Teams 对话、群聊或频道中的链接的安全链接保护也由安全链接策略控制。 没有默认的安全链接策略，因此若要在 Teams 中保护安全链接，需要创建一个或多个安全 **链接策略**。

  有关 Teams 中的安全链接保护详细信息，请参阅本文稍后介绍 [的 Microsoft Teams](#safe-links-settings-for-microsoft-teams) 安全链接设置部分。

- **Office 365 应用**：Office 365 应用的安全链接保护在受支持的桌面、移动和 Web aps 中可用。 在 **安全** 链接策略之外的全局设置中为 Office 365 应用配置安全链接保护。 有关说明，请参阅 [为 Microsoft Defender for Office 365 中的安全链接设置配置全局设置](configure-global-settings-for-safe-links.md)。

  但是，Office 365 应用的安全链接保护仅适用于活动安全链接策略中包含的用户。 如果用户未包含在活动安全链接策略中，则用户不会在受支持的 Office 365 应用中获得安全链接保护。

  有关 Office 365 应用中安全链接保护详细信息，请参阅本文稍后介绍 [的 Office 365](#safe-links-settings-for-office-365-apps) 应用的安全链接设置部分。

本文包含以下安全链接设置的详细说明：

- **安全链接策略中的** 设置：这些设置仅适用于特定策略中包含的用户，并且策略之间的设置可能不同。 这些设置包括：

  - [电子邮件的安全链接设置](#safe-links-settings-for-email-messages)
  - [Microsoft Teams 的安全链接设置](#safe-links-settings-for-microsoft-teams)
  - [安全链接策略中的"不重写以下 URL"列表](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **全局安全链接设置**：这些设置是全局配置的，而不是在安全链接策略中配置的。 但是，这些设置仅适用于活动安全链接策略中包含的用户。 这些设置包括：

  - [Office 365 应用的安全链接设置](#safe-links-settings-for-office-365-apps)
  - [安全链接的"阻止以下 URL"列表](#block-the-following-urls-list-for-safe-links)

下表介绍了 Microsoft 365 和 Office 365 组织中安全链接的方案，其中包括 Defender for Office 365 (换句话说，缺少许可在示例) 中永远不会是问题。

****

|方案|结果|
|---|---|
|表示是市场营销部门的成员。 Office 365 应用的安全链接保护在安全链接的全局设置中打开，并且存在适用于市场营销部门成员的安全链接策略。 在电子邮件中打开 PowerPoint 演示文稿，然后单击演示文稿中的 URL。|百分之百受安全链接保护。 <p> Office 365 应用的安全链接保护包含在安全链接策略中，且 Office 365 应用的安全链接保护已打开。 <p> 有关 Office 365 应用中安全链接保护的要求详细信息，请参阅本文稍后介绍 [的 Office 365](#safe-links-settings-for-office-365-apps) 应用的安全链接设置部分。|
|Chris 的 Microsoft 365 E5 组织未配置安全链接策略。 Chris 从外部发件人收到一封电子邮件，其中包含他最终单击的恶意网站的 URL。|Chris 不受安全链接保护。 <p> 管理员必须至少为任何人创建一个安全链接策略，才能在入站电子邮件中获得安全链接保护。 Chris 必须包含在策略条件中才能获得安全链接保护。|
|在 Pat 的组织中，管理员未创建任何安全链接策略，但 Office 365 应用的安全链接保护已打开。 Pat 打开 Word 文档并单击该文件中的 URL。|Pat 不受安全链接保护。 <p> 尽管 Office 365 应用的安全链接保护已全局打开，但 Pat 未包含在任何活动的安全链接策略中，因此无法应用保护。|
|在 Lee 的组织中，在安全链接的全局设置中的"阻止以下 `https://tailspintoys.com` **URL"** 列表中进行配置。 包含 Lee 的安全链接策略已存在。 Lee 收到一封包含 URL 的电子邮件 `https://tailspintoys.com/aboutus/trythispage` 。 Lee 单击 URL。|可能为 Lee 自动阻止 URL;这取决于列表中的 URL 条目和所使用的电子邮件客户端 Lee。 有关详细信息，请参阅本文稍后介绍[](#block-the-following-urls-list-for-safe-links)的安全链接的"阻止以下 URL"列表部分。|
|Jamie 和 Julia 都负责 contoso.com。 在不久之前，管理员配置了适用于 Jamie 和 Julia 的安全链接策略。 Jamie 向 Julia 发送了一封电子邮件，但不知道该电子邮件包含恶意 URL。|如果适用于 Julia 的安全链接策略配置为应用于内部收件人之间的邮件，则 Julia 受安全链接保护。 有关详细信息，请参阅本文稍后 [介绍的电子邮件](#safe-links-settings-for-email-messages) 的安全链接设置部分。|

## <a name="safe-links-settings-for-email-messages"></a>电子邮件的安全链接设置

安全链接扫描传入电子邮件中是否包含已知的恶意超链接。 扫描的 URL 使用 Microsoft 标准 URL 前缀重写 `https://nam01.safelinks.protection.outlook.com` ：。 重写链接后，将分析潜在恶意内容。

在安全链接重写 URL 之后，即使手动将邮件转发或答复给外部收件人， (URL 仍) 。 不会重写添加到转发或答复邮件的其他链接。 但是，在收件箱规则或SMTP 转发自动转发的情况下，不会在发送给最终收件人的邮件中重写 URL，除非该收件人还受安全链接保护，或者URL 已在以前的通信中重写。 

以下列表介绍了适用于电子邮件的安全链接策略中的设置：

- **选择邮件中未知潜在恶意 URL 的操作**：启用或禁用电子邮件中的安全链接扫描。 建议的值是 **On**。 打开此设置会导致以下操作。

  - Windows 上的 Outlook (C2R) 启用安全链接扫描。
  - 当单击邮件中的 URL 时，URL 将被重写，用户通过安全链接保护进行路由。
  - 单击后，将针对已知恶意 URL 列表和"阻止以下 URL"列表检查[URL。](#block-the-following-urls-list-for-safe-links)
  - 没有有效信誉的 URL 将在后台异步触发。

- **对指向文件的** 可疑链接应用实时 URL 扫描：启用链接（包括指向可下载内容的电子邮件中的链接）实时扫描。 建议的值已启用。

  - **等待 URL 扫描完成，然后再传递邮件**：

    - 已启用：包含 URL 的邮件将一直进行，直到扫描完成。 仅在确认 URL 是安全的之后，才传递邮件。 这是建议的值。
    - 已禁用：如果 URL 扫描无法完成，无论如何都传递邮件。

- **将安全链接应用于组织** 内部发送的电子邮件：启用或禁用对同一 Exchange Online 组织中内部发件人和内部收件人之间发送的邮件的安全链接扫描。 建议的值已启用。

- **Do not track user clicks**： Enables or disables storing Safe Links click data for URLs clicked in email messages. 建议的值是保持此设置未选择 (跟踪用户单击) 。

  目前不支持在内部发件人和内部收件人之间发送的电子邮件中的链接的 URL 单击跟踪。

- **不允许用户单击到原始 URL：** 允许或阻止用户通过警告 [页面](#warning-pages-from-safe-links) 单击到原始 URL。 推荐值已启用。

- **在通知和警告页面上** 显示组织品牌：此选项在警告页面上显示组织的品牌。 品牌打造可帮助用户识别合法警告，因为默认 Microsoft 警告页面经常被攻击者使用。 有关自定义品牌打造详细信息，请参阅将品牌添加到组织的 [Azure Active Directory 登录页面](/azure/active-directory/fundamentals/customize-branding)。

- **不要重写以下 URL：** 保留 URL。 保留不需要扫描的安全 URL 的自定义列表。 该列表对于每个安全链接策略都是唯一的。 有关不重写以下 **URL** 列表的信息，请参阅本文稍后的安全链接策略 [](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)中的"不重写以下 URL"列表一节。

有关安全链接策略的"标准"和"严格"策略设置的建议值详细信息，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

- **收件人** 筛选器：需要指定确定策略适用的收件人条件和例外。 可以将这些属性用于条件和例外：

  - **收件人为**
  - **收件人域为**
  - **收件人为以下组的成员**

  一次只能使用一个条件或例外，但条件或例外可以包含多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

- **优先级**：如果创建多个策略，可以指定策略的应用顺序。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

  有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="how-safe-links-works-in-email-messages"></a>安全链接在电子邮件中的工作方式

在高级别上，下面将说明安全链接保护在电子邮件中的 URL 上的工作原理：

1. 所有电子邮件均通过 EOP，其中 Internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器在邮件传递到收件人邮箱之前。

2. 用户在邮箱中打开邮件，并单击邮件中的 URL。

3. 安全链接在打开网站之前立即检查 URL：

   - 如果 URL 包含在"阻止以下 **URL"** 列表中，将打开 [阻止的 URL](#blocked-url-warning) 警告。

   - 如果 URL 指向已确定为恶意的网站，将打开恶意 (或其他警告[](#malicious-website-warning)) 页面。

   - 如果 URL 指向可下载的文件，并且适用于用户的策略中启用了"对指向文件的可疑链接和链接应用实时 **URL** 扫描"设置，则选中可下载的文件。

   - 如果确定 URL 是安全的，将打开网站。

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft Teams 的安全链接设置

> [!IMPORTANT]
> 自 2020 年 3 月起，此功能为预览版，仅适用于 Microsoft Teams 技术采用计划 (TAP) 。 有关发布计划的信息，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。

在安全链接策略中为 Microsoft Teams 启用或禁用安全链接保护。 具体来说，使用" **为 Microsoft Teams 中的未知或潜在恶意 URL 选择操作"** 设置。 建议的值是 **On**。

适用于电子邮件中链接的安全链接策略中的以下设置也适用于 Teams 中的链接：

- **对指向文件的可疑链接应用实时 URL 扫描**
- **不跟踪用户单击**
- **不允许用户单击至初始 URL**

这些设置在以前的电子邮件 [安全链接设置部分中进行了说明](#safe-links-settings-for-email-messages) 。

为 Microsoft Teams 启用安全链接保护后，当受保护的用户单击链接时，将针对已知恶意链接列表检查 Teams 中的 URL (单击时保护) 。 不重写 URL。 如果发现链接是恶意链接，用户将具有以下体验：

- 如果在 Teams 对话、群聊或频道中单击了链接，则以下屏幕截图中显示的警告页面将显示在默认 Web 浏览器中。
- 如果从固定选项卡单击了链接，则警告页面将显示在该选项卡内的 Teams 界面中。出于安全考虑，禁用在 Web 浏览器中打开链接的选项。
- 根据策略中"不允许用户单击到原始 **URL"** 设置的配置方式，用户将允许或不允许单击到原始 URL (是否继续 (屏幕截图) 中不建议) 。  我们建议您启用"不允许用户单击访问原始 **URL"** 设置，以便用户无法单击到原始 URL。

如果发送链接的用户未包含在启用了 Teams 保护的安全链接策略中，则用户可以自由单击访问其计算机或设备上的原始 URL。

!["Teams 安全链接"页面报告恶意链接。](../../media/tp-safe-links-for-teams-malicious.png)

单击 **警告页面上的** "返回"按钮将用户返回到其原始上下文或 URL 位置。 但是，再次单击原始链接将导致安全链接重新扫描 URL，因此警告页面将重新出现。

### <a name="how-safe-links-works-in-teams"></a>安全链接在 Teams 中的工作方式

在高级别上，下面将说明安全链接保护在 Microsoft Teams 中对 URL 的工作原理：

1. 用户启动 Teams 应用。

2. Microsoft 365 验证用户组织是否包括适用于 Office 365 的 Microsoft Defender，并且用户是否包含在启用了 Microsoft Teams 保护的活动安全链接策略中。

3. 在用户单击聊天、群聊、频道和选项卡时验证 URL。

## <a name="safe-links-settings-for-office-365-apps"></a>Office 365 应用的安全链接设置

Office 365 应用的安全链接保护检查 Office 文档中的链接，而不是电子邮件 (但它可以在打开 Office 文档后检查电子邮件中附加的 Office) 中的链接。

Office 365 应用的安全链接保护具有以下客户端要求：

- Microsoft 365 应用版或 Microsoft 365 商业高级版。
  - Windows、Mac 或 Web 浏览器中 Word、Excel 和 PowerPoint 的当前版本。
  - iOS 或 Android 设备上的 Office 应用。
  - Windows 上的 Visio。
  - Web 浏览器中的 OneNote。

- Office 365 应用配置为使用新式验证。 有关详细信息，请参阅新式验证如何适用于 [Office 2013、Office 2016 和 Office 2019 客户端应用](../../enterprise/modern-auth-for-office-2013-and-2016.md)。

- 用户使用工作或学校帐户登录。 有关详细信息，请参阅登录到[Office。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

在安全链接的全局设置中（而不是在安全链接策略中）为 Office 365 应用配置安全链接保护。 但是，若要应用 Office 365 应用的安全链接保护，打开 Office 文档并单击链接的用户必须包含在活动的安全链接策略中。

以下安全链接设置适用于 Office 365 应用：

- **Office 365 应用程序**：启用或禁用受支持的 Office 365 应用中的安全链接扫描。 默认值和推荐值为 **On。**

- **Do not track when users click Safe Links**： Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word， Excel， PowerPoint， and Visio. 建议值为 **Off**，这意味着将跟踪用户点击量。

- **不允许用户** 单击指向原始 URL 的安全链接：允许或阻止用户在桌面版 Word、Excel、PowerPoint 和 Visio 中单击通过警告页面指向原始 URL。 [](#warning-pages-from-safe-links) 默认值和推荐值为 **On。**

若要为 Office 365 应用配置安全链接设置，请参阅为 [Office 365](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)应用配置安全链接保护。

有关"标准"和"严格"策略设置的建议值详细信息，请参阅安全链接 [的全局设置](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。

### <a name="how-safe-links-works-in-office-365-apps"></a>安全链接在 Office 365 应用中的工作方式

在高级别上，下面将说明安全链接保护在 Office 365 应用中对 URL 的工作原理。 支持的 Office 365 应用在上一部分中进行了介绍。

1. 用户在包含 Microsoft 365 应用版或 Microsoft 365 商业高级版的组织使用工作或学校帐户登录。

2. 用户打开并单击受支持的 Office 应用中的 Office 文档链接。

3. 安全链接在打开目标网站之前立即检查 URL：

   - 如果 URL 包含在跳过安全链接扫描的列表中 (将打开阻止的 URL ) 阻止[的 URL 警告](#blocked-url-warning)页。

   - 如果 URL 指向已确定为恶意的网站，将打开恶意 (或其他警告[](#malicious-website-warning)) 页面。

   - 如果 URL 指向可下载的文件，并且将适用于用户的安全链接策略配置为扫描指向可下载内容的链接 (应用实时 **URL** 扫描，以检查指向文件) 的可疑链接和链接，将检查可下载文件。

   - 如果 URL 被视为安全 URL，则用户将访问网站。

   - 如果安全链接扫描无法完成，不会触发安全链接保护。 在 Office 桌面客户端中，在用户继续访问目标网站之前，将警告用户。

> [!NOTE]
> 在每个会话开始时，可能需要几秒钟来验证用户是否启用了 Office 安全链接。

## <a name="block-the-following-urls-list-for-safe-links"></a>安全链接的"阻止以下 URL"列表

" **阻止以下 URL"** 列表定义安全链接扫描始终阻止的链接，这些链接位于以下位置：

- 电子邮件。
- Windows 和 Mac 中的 Office 365 应用中的文档。
- Office for iOS 和 Android 中的文档。

当活动安全链接策略中的用户单击受支持的应用中的阻止链接时，他们会访问阻止 [的 URL 警告](#blocked-url-warning) 页面。

在安全链接的全局设置中配置 URL 列表。 有关说明，请参阅 [配置"阻止以下 URL"列表](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。

**注意**：

- 有关被阻止的 URL 的真正通用列表，请参阅管理 [租户允许/阻止列表](tenant-allow-block-list.md)。

- 限制：
  - 最大条目数为 500。
  - 条目的最大长度为 128 个字符。
  - 所有条目不能超过 10，000 个字符。

- 不要在 URL 末尾添加 `/` () 斜杠。 例如，使用 `https://www.contoso.com` ，而不是 `https://www.contoso.com/` 。

- 例如或 (仅域 URL) `contoso.com` `tailspintoys.com` 将阻止包含该域的任何 URL。

- 可以阻止子域，但不阻止整个域。 例如，阻止包含子域的任何 URL，但不阻止包含完整域 `toys.contoso.com*` 的 `contoso.com` URL。

- 每个 URL 条目可以包含最多三 () `*` 通配符。

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"阻止以下 URL"列表的条目语法

下表介绍了您可以输入的值及其结果的示例：

****

|值|结果|
|---|---|
|`contoso.com` <p> 或者 <p> `*contoso.com*`|阻止域、子域和路径。 例如， `https://www.contoso.com` `https://sub.contoso.com` 、 和 `https://contoso.com/abc` 被阻止。|
|`https://contoso.com/a`|阻止 `https://contoso.com/a` 但不阻止其他子路径（如 `https://contoso.com/a/b` ）。|
|`https://contoso.com/a*`|块 `https://contoso.com/a` 和其他子路径（如 `https://contoso.com/a/b` ）。|
|`https://toys.contoso.com*`|阻止此示例中 (`toys` 子域) 但允许单击其他域 URL (或 `https://contoso.com` `https://home.contoso.com`) 。|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>安全链接策略中的"不重写以下 URL"列表

> [!NOTE]
> 如果组织使用安全链接策略，则不重写以下 **URL** 列表是第三方网络钓鱼测试唯一受支持的方法。

每个安全链接策略都包含一个"不重写以下 **URL"** 列表，您可以使用该列表指定安全链接扫描未重写的 URL。 换句话说，该列表允许策略中包含的用户访问指定的 URL，否则安全链接会阻止这些 URL。 可以在不同的安全链接策略中配置不同的列表。 策略处理在用户应用第一 (策略后) 可能停止。 因此，只有一个"不 **重写以下 URL"** 列表应用于包含在多个活动安全链接策略中的用户。

若要将条目添加到新的或现有的安全链接策略中的列表，请参阅 [创建安全链接策略](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 或修改 [安全链接策略](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。

**注意**：

- 以下客户端无法识别安全链接策略中的 **不** 重写以下 URL 列表。 根据这些客户端中安全链接扫描的结果，可阻止包含在这些安全管理中的用户访问 URL：

  - Microsoft Teams
  - Office Web 应用

  有关任何地方允许的 URL 的真正通用列表，请参阅 [管理租户允许/阻止列表](tenant-allow-block-list.md)。

- 请考虑将常用的内部 URL 添加到列表中，以改进用户体验。 例如，如果你有本地服务（如 Skype for Business 或 SharePoint），你可以添加这些 URL 以将其从扫描中排除。

- 如果安全链接策略中已有"不重写以下 **URL"** 条目，请务必查看列表并根据需要添加通配符。 例如，你的列表有一个类似 的条目 `https://contoso.com/a` ，你稍后决定包括子路径，如 `https://contoso.com/a/b` 。 不要添加新条目，而是向现有条目添加通配符，以便它成为 `https://contoso.com/a/*` 。

- 每个 URL 条目可以包含最多三 () `*` 通配符。 通配符明确包括前缀或子域。 例如，条目与 不同，因为允许用户访问指定域中的子域 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 和路径。

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"不重写以下 URL"列表的条目语法

下表介绍了您可以输入的值及其结果的示例：

****

|值|结果|
|---|---|
|`contoso.com`|允许访问 `https://contoso.com` 子域或路径，但不能访问子域或路径。|
|`*.contoso.com/*`|允许访问域、子域和路径 (例如、 `https://www.contoso.com` `https://www.contoso.com` 或 `https://maps.contoso.com` `https://www.contoso.com/a`) 。 <p> 此条目本质上优于 ，因为它不允许潜在的欺诈性网站 `*contoso.com*` ，如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|允许访问 `https://contoso.com/a` ，但不允许访问子路径（如 ） `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|允许访问 `https://contoso.com/a` 和子路径，如 `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>安全链接中的警告页面

本节包含单击 URL 时安全链接保护触发的各种警告页面的示例。

请注意，已更新多个警告页面。 如果还没有看到更新的页面，你很快就会看到。 更新的页面包括新的配色方案、更多详细信息，以及即使给定警告和建议，仍可以继续访问网站。

### <a name="scan-in-progress-notification"></a>扫描正在进行通知

单击的 URL 正由安全链接进行扫描。 在再次尝试链接之前，可能需要等待片刻。

!["正在扫描链接"通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

原始通知页面如下所示：

![原始"正在扫描链接"通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>可疑邮件警告

单击的 URL 位于类似于其他可疑邮件的电子邮件中。 我们建议您在继续网站之前仔细检查电子邮件。

!["从可疑邮件单击链接"警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>网络钓鱼尝试警告

单击的 URL 位于已标识为网络钓鱼攻击的电子邮件中。 因此，电子邮件中所有 URL 都将被阻止。 建议您不要继续访问该网站。

!["从网络钓鱼邮件中单击链接"警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>恶意网站警告

单击的 URL 指向已标识为恶意的网站。 建议您不要继续访问该网站。

!["此网站被分类为恶意"警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

原始警告页面如下所示：

![原始"此网站已分类为恶意"警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>阻止的 URL 警告

单击的 URL 已被您组织的管理员手动阻止 (安全链接列表的全局设置中的"阻止以下 URL") 。 安全链接未扫描该链接，因为它已被手动阻止。

管理员手动阻止特定 URL 的原因有多种。 如果认为不应阻止网站，请与管理员联系。

!["此网站被管理员阻止"警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

原始警告页面如下所示：

![原始"根据组织的 URL 策略阻止此网站"警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>错误警告

发生了某种错误，无法打开 URL。

!["无法加载您尝试访问的页面"警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

原始警告页面如下所示：

![原始"无法加载此网页"警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
