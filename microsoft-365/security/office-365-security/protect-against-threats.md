---
title: 防范 Microsoft Defender for Office 365、反恶意软件、反网络钓鱼、反垃圾邮件、保险箱 链接、保险箱 附件、零时差自动清除 (ZAP) 、MDO 安全配置中的威胁
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以在 Microsoft 365 中学习威胁防护并为组织配置使用方法。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5a0be5171a2de07792cd259dc6547046d7c1630
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507160"
---
# <a name="protect-against-threats"></a>抵御威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

这是一个快速的指南，它将 Defender for Office 365 的配置分成块。 如果你对 Microsoft Office 365 中的威胁防护功能不了解，不知道从哪里开始，或者你喜欢通过 *上手* 来学习，使用这个指南作为一个清单和开始。

> [!IMPORTANT]
> **包括了适合每种策略的初步推荐设置；然后，很多选项都可用，你可以调整设置以满足具体的组织需要**。 预留大概 30 分钟以让你的策略或更改在你的数据中心中正常工作。
>
> 若要跳过手动配置 Defender for Office 365 中的大多数策略，可以使用"标准"或"严格"级别的预设安全策略。 有关详细信息，请参阅在 EOP 中预设安全策略[和Microsoft Defender for Office 365](preset-security-policies.md)。

## <a name="requirements"></a>要求

### <a name="subscriptions"></a>订阅

威胁防护功能含在 *所有* Microsoft 或 Office 365 订阅中；然而，一些订阅有高级功能。 下面的表格列出了包含在此文章中的防护功能，以及最低订阅要求。

> [!TIP]
> 请注意，除了启用审核的说明之外，步骤还启动反恶意软件、反网络钓鱼和反垃圾邮件，这些操作标记为 **EOP Office 365 Exchange Online Protection (的** 一) 。 在一篇Defender for Office 365中，这 (Defender for Office 365 **)** EOP，并基于 EOP。

|防护类型|订阅要求|
|---|---|
|审核日志（出于报告的目的）|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|反恶意软件保护|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|防钓鱼保护|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|反垃圾邮件保护|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|保护电子邮件和附件文档中的恶意 URL 和文件Office链接 (保险箱附件保险箱文件) |[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>角色和权限

若要Defender for Office 365策略，必须分配有适当的角色。 看看下面的表格，了解可以执行这些操作的角色。

|角色或角色组|在哪里了解更多信息|
|---|---|
|全局管理员|[关于 Microsoft 365 管理员角色](../../admin/add-users/about-admin-roles.md)|
|安全管理员|[Azure AD内置角色](/azure/active-directory/roles/permissions-reference#security-administrator)
|Exchange Online 组织管理|[Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo)|

若要了解更多信息，请参阅 Microsoft 365 Defender [门户中的权限](permissions-microsoft-365-security-center.md)。

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>打开用于报告和调查的审核日志记录

- 早点开始审核日志。 对于以下步骤中的 **一些步骤** ，你需要将审核功能启用。 审核日志在包括[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。 若要查看威胁防护报告、电子邮件安全报告和 [资源管理器](threat-explorer.md)中 [](view-email-security-reports.md)的数据，审核日志记录必须 *打开*。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection-in-eop"></a>第 1 部分 - EOP 中的反恶意软件保护

有关建议的反恶意软件设置的信息，请参阅 [EOP 反恶意软件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。

1. 打开 **网站门户中的**"反恶意软件"Microsoft 365 Defender页面。<https://security.microsoft.com/antimalwarev2>

2. 在 **"反恶意软件"** 页上，单击该名称 (**") "** 默认"策略。

3. 在打开的策略详细信息飞出控件中，单击 **"编辑保护设置"**，然后配置以下设置：
   - **保护设置** 部分：
     - **启用常用附件筛选器**：选择 (启用) 。 单击 **"自定义文件类型** "以添加更多文件类型。
     - **启用恶意软件的零时差自动清除**：验证此设置是否被选中。 有关恶意软件的 ZAP 详细信息，请参阅适用于恶意软件的零时 ([ZAP) 清除](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)。
   - **隔离策略**：保留默认值 AdminOnlyAccessPolicy 为选中状态。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。
   - **通知** 部分：验证是否未选择任何通知设置。

   完成时，请单击“保存”。

4. 返回策略详细信息浮出控件，单击“**关闭**”。

有关配置反恶意软件策略的详细说明，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>第 2 部分 - EOP 和 Defender for Office 365

[反钓鱼软件防护](anti-phishing-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。 高级反钓鱼保护在 [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 中可用。

有关反网络钓鱼策略的建议设置详细信息，请参阅 [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) 防钓鱼策略设置和 Microsoft Defender for Office 365 中的反网络钓鱼[策略设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。

以下过程介绍如何配置默认的防钓鱼策略。 设置中可用的Defender for Office 365会进行清晰标记。

1. 打开 **网站门户中的**"防钓鱼"Microsoft 365 Defender页面。<https://security.microsoft.com/antiphishing>

2. 在 **"防钓鱼"** 页面上，单击该名称，选择名为 **"Office365** 反钓鱼默认 (默认) "策略。

3. 在出现的策略详细信息飞出中，配置以下设置：
   - **网络钓鱼阈值&保护** 部分：单击"编辑 **保护** 设置"，然后配置打开的飞出控件中的以下设置：
     - **网络钓鱼电子邮件阈值**<sup>\*</sup>：选择 **2 - (** 标准) **或 3 - 更主动** (严格) 。
     - **模拟** 部分 <sup>\*</sup>：配置以下值：
       - 选择"允许用户保护"，单击出现的"管理 **(nn) 发件人 ()**"链接，然后添加内部和外部发件人，防止模拟，例如组织的会员、CEO、CFO 和其他高级领导。
       - 选择 **"启用要保护** 的域"，然后配置出现的以下设置：
         - 选择 **"包括我拥有域**"以保护接受域中的内部发件人 (通过单击"查看我的域) 进行模拟"。
         - 若要保护其他域中的发件人，请选择"包括自定义域"，单击出现的"管理 (nn) 自定义域 **()**"链接，然后添加防止模拟的其他域。
     - 添加受信任发件人和域部分：单击"管理 **(nn) 受信任发件人 (s) 和域 ()**"以根据需要将发件人和发件人域例外配置为模拟保护。<sup>\*</sup>
     - 邮箱智能设置 <sup>\*</sup>：验证是否 **选择了"启用邮箱智能****"和"启用模拟保护的** 智能"。
     - **欺骗** 部分：验证 **是否选择了"启用欺骗** 智能"。

     完成后，单击“**保存**”。

   - **"** 操作 **"部分：** 单击"编辑操作"，在打开的飞出控件中配置以下设置：
     - **"邮件** 操作"部分：配置以下设置：
       - **如果检测到邮件为模拟用户**<sup>\*</sup>：请选择" **隔离邮件"**。 将显示 **"应用** 隔离策略"框，选择适用于 [](quarantine-policies.md)由用户模拟保护隔离的邮件的隔离策略。
       - **如果邮件被检测为模拟域**<sup>\*</sup>：请选择" **隔离邮件"**。 将显示 **"应用** 隔离策略"框，选择适用于 [](quarantine-policies.md)由域模拟保护隔离的邮件的隔离策略。
       - **如果邮箱智能检测到模拟**<sup>\*</sup>用户：选择"将邮件移动到收件人的垃圾邮件文件夹" (Standard **) "或**"隔离 (严格) "。 如果选择"**隔离邮件"，** 则会显示"应用隔离策略"框，其中选择 [](quarantine-policies.md)适用于由邮箱智能保护隔离的邮件的隔离策略。
       - **如果邮件被检测** 为欺骗邮件：选择"将邮件移动到收件人的垃圾邮件文件夹" (标准 **) 或"** 隔离" (严格) 。  如果选择"**隔离邮件"，** 则会显示"应用隔离策略"框，选择适用于 [](quarantine-policies.md)通过欺骗智能保护隔离的邮件的隔离策略。
     - **安全&"部分** ：配置以下设置：
       - **显示第一个联系人安全提示**：选择 (打开) 。
       - **显示用户模拟安全提示**<sup>\*</sup>：选择 (启用) 。
       - **显示域模拟安全提示**<sup>\*</sup>：选择 (启用) 。
       - **显示用户模拟异常字符安全提示**<sup>\*</sup>：选择 (启用) 。
       - **显示 (？)** 欺骗的未经身份验证的发件人：选择 (打开) 。
       - **显示"via"标记**：选择 (打开) 。

     完成后，单击“**保存**”。

   <sup>\*</sup>此设置仅适用于Defender for Office 365。

4. 单击 **"保存"** ，然后单击" **关闭"**

有关配置防钓鱼策略的详细说明，请参阅在 [EOP](configure-anti-phishing-policies-eop.md) 中配置防钓鱼策略和在 Microsoft Defender for Office 365 [中配置防钓鱼策略](configure-mdo-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection-in-eop"></a>第 3 部分 - EOP 中的反垃圾邮件保护

有关建议的反垃圾邮件设置的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

1. 打开 **网站门户中的**"反垃圾邮件策略"Microsoft 365 Defender页面。<https://security.microsoft.com/antispam>

2. 在 **"反垃圾邮件策略**"页上，通过单击该名称 (列表中的"默认) "选择名为"反垃圾邮件入站策略"的策略。

3. 在出现的策略详细信息飞出中，配置以下设置：
   - **批量电子邮件阈值&"垃圾邮件属性"** 部分：单击 **"编辑垃圾邮件阈值和属性"**。 在出现的"飞出"中，配置以下设置：
     - **批量电子邮件阈值**：将此值设置为 5 (Strict) 或 6 (Standard) 。
     - 将其他设置保留为默认值 (**"****关闭"** 或"无") 。

     完成后，单击“**保存**”。

   - **"** 操作"部分：单击 **"编辑操作"**。 在出现的"飞出"中，配置以下设置：
     - **"邮件操作** "部分：
       - **垃圾邮件**：验证" **将邮件移动到** 垃圾邮件"文件夹 ("标准) 或 **选择"隔离** 邮件 (严格) "。
       - **高可信度垃圾邮件**：选择 **"隔离邮件"**。
       - **网络钓鱼：** 选择" **隔离邮件"**。
       - **高可信度网络钓鱼**：验证 **是否选择了** 隔离邮件。
       - **批量**：验证"**将邮件移动到** 垃圾邮件文件夹"是否 (标准) 或选择"隔离邮件 (严格)  "。

       对于您选择"隔离邮件"的每个操作，将出现"选择隔离策略"框，您可以在[](quarantine-policies.md)其中选择适用于由反垃圾邮件保护隔离的邮件的隔离策略。

     - **在隔离邮箱中保留此天数：** 验证值 **30** 天。
     - **启用垃圾邮件安全提示**：验证此设置是否 (启用) 。
     - **在 ZAP (启用零** 时) 清除：验证此设置是否 (启用) 。
       - **启用网络钓鱼邮件**：验证是否选中此设置 (启用) 。 有关详细信息，请参阅针对网络钓鱼的 [ZAP (零) 清除](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)。
       - **启用垃圾邮件：** 验证是否选中此设置 (启用) 。 有关详细信息，请参阅零 [时差自动清除 (ZAP) 垃圾邮件](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)。

     完成后，单击“**保存**”。

   - **允许和阻止的发件人** 和域部分：查看或编辑允许的发件人和允许的域，如在 [EOP](create-block-sender-lists-in-office-365.md) 中创建阻止的发件人列表或在 [EOP](create-safe-sender-lists-in-office-365.md) 中创建安全发件人列表中所述。

     完成后，单击“**保存**”。

4. 完成后，单击“关闭”。

有关配置反垃圾邮件策略的详细说明，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>第四部分 - 防护恶意 URL 和文件带来的威胁（Defender for Office 365 中的安全链接和安全附件）

抵御恶意 URL 和文件的单击时防护在包含 [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的订阅中可用。 通过 “[安全附件](safe-attachments.md)”和“[安全链接](safe-links.md)”策略设置。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Defender for Office 365 中的安全附件策略

有关附件的建议设置保险箱，请参阅 。[保险箱附件设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

1. 在 保险箱 **门户** 中打开"Microsoft 365 Defender附件"页。<https://security.microsoft.com/safeattachmentv2>

2. 在"**保险箱"** 页上，单击"全局设置"，然后在出现的飞出页面上配置以下设置：
   - **打开 Defender for Office 365、** SharePoint、OneDrive 和 Microsoft Teams：![打开此设置 (切换](../../media/scc-toggle-on.png)。) 。

     > [!IMPORTANT]
     > **在打开"保险箱附件SharePoint OneDrive** Microsoft Teams，请确认审核日志记录已在你的组织中打开。 此操作通常由在审核日志中分配了审核日志角色Exchange Online。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！

   - **打开 保险箱 客户端Office**![文档：打开此设置 (切换](../../media/scc-toggle-on.png)。) 。 请注意，此功能仅对所需的许可证类型可用且有意义。 有关详细信息，请参阅 保险箱 [Documents in Microsoft 365 E5](safe-docs.md)。
   - **允许用户单击"受保护的** 视图"，即使保险箱将![文件标识为恶意文件：验证此设置是否 (切换为关闭。](../../media/scc-toggle-off.png)) 。

   完成后，单击"保存 **"**

3. 返回到"保险箱 **"页上**，单击"创建![图标"](../../media/m365-cc-sc-create-icon.png)。

4. 在打开 **的"保险箱** 附件"策略向导中，配置以下设置：
   - **命名策略** 页面：
     - **名称**：输入一些唯一的描述性信息。
     - **说明**：输入可选说明。
   - **用户和域** 页面：因为这是你的第一个策略，你可能想要最大化覆盖范围，请考虑在"域"[](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)框中 **输入接受的** 域。 否则，可以使用"用户 **"** 和" **组"** 框进行更精细的控制。 可以通过选择"排除这些用户、组和域"并输入值 **来指定例外** 。
   - **设置** 页面：
     - **保险箱未知恶意软件响应：** 选择"阻止 **"**。
     - **隔离策略**：默认值为空，表示使用 AdminOnlyAccessPolicy 策略。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。
     - **重定向包含检测到的附件的** 附件： **启用** 重定向：打开此设置 (选择) 并输入电子邮件地址以接收检测到的邮件。
     - **如果扫描保险箱超时或错误** (应用附件检测响应：验证) 是否选中此设置。

5. 完成后，单击提交 **，****然后单击完成。**

6.  (建议) 全局管理员或 SharePoint Online 管理员，运行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet，在 SharePoint Online PowerShell 中将 _DisallowInfectedFileDownload_ `$true` 参数设置为 。
   - `$true`阻止所有检测到文件的操作（除了删除）。 用户无法打开、移动、复制或共享检测到的文件。
   - `$false`阻止所有除删除和下载的操作。 人员可以选择接受风险并下载检测到的文件。

7. 预留至多 30 分钟以让更改传播到所有 Microsoft 365 数据中心。

有关为附件配置保险箱策略和全局设置的保险箱，请参阅下列主题：

- [在保险箱中设置"附件"Microsoft Defender for Office 365](set-up-safe-attachments-policies.md)
- [为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件](turn-on-mdo-for-spo-odb-and-teams.md)
- [Microsoft 365 E5 中的安全文档](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>在 Defender for Office 365 中设置安全链接策略

有关链接的建议设置保险箱，请参阅保险箱[链接设置](recommended-settings-for-eop-and-office365.md#safe-links-settings)。

1. 在 保险箱 **门户** 中打开"Microsoft 365 Defender链接"页。<https://security.microsoft.com/safelinksv2>

2. 在"**保险箱**"页上，单击"全局设置"，然后在出现的飞出页面上配置以下设置：
   - **设置支持的应用部分中的内容Office 365应用：**
     - **Use 保险箱 Links in Office 365 apps**： Verify this setting is turned on (![Toggle on.](../../media/scc-toggle-on.png)) .
     - **Do not track when users click protected links in Office 365 apps**： Turn this setting off (![切换为关闭。](../../media/scc-toggle-off.png)) 。
     - **不允许用户在应用中单击以** 访问Office 365 URL![：验证此设置是否 (打开。](../../media/scc-toggle-on.png)) 。

   完成后，单击"保存 **"**

3. 返回到"保险箱 **"页上**，单击"创建![图标"](../../media/m365-cc-sc-create-icon.png)。

4. 在打开 **的保险箱** 链接策略向导中，配置以下设置：
   - **命名策略** 页面：
     - **名称**：输入一些唯一的描述性信息。
     - **说明**：输入可选说明。
   - **用户和域** 页面：因为这是你的第一个策略，你可能想要最大化覆盖范围，请考虑在"域"[](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)框中 **输入接受的** 域。 否则，可以使用"用户 **"** 和" **组"** 框进行更精细的控制。 可以通过选择"排除这些用户、组和域"并输入值 **来指定例外** 。
   - **Url &单击保护设置** 页面：
     - **"对电子邮件中的潜在恶意 URL 的操作"** 部分：
       - **打开：保险箱** 用户单击电子邮件中的链接时，链接将检查已知恶意链接的列表：选择其设置 (打开) 。
       - **Apply 保险箱 Links to email messages sent within the organization**： Select this setting (turn on) .
       - **对指向文件的可疑链接应用实时 URL** 扫描：选择此设置 (打开) 。
       - **等待 URL 扫描完成，然后再传递邮件**：选择此设置 (打开) 。
       - **不要重写 URL**，请仅通过保险箱链接 API 进行检查：确认未选中此设置 (关闭) 。
     - **请勿重写电子邮件中的以下 URL**：我们对此设置没有具体的建议。 有关详细信息，请参阅链接策略中的"不要重写[保险箱 URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)列表。
     - **部分中针对潜在恶意 URL Microsoft Teams** 操作：
       - ***On： 保险箱 links checks a list of known， malicious links when users click links in Microsoft Teams**： Select this setting (turn on) .
     - **单击"保护设置"** 部分：
       - **跟踪用户单击** 次数：验证此设置是否 (启用) 。
       - **让用户单击以访问原始 URL**：关闭此设置 (未) 。
       - 在通知和警告页面上显示组织品牌：选择此设置 (将其打开) 只有在按照自定义[组织的 Microsoft 365](../../admin/setup/customize-your-organization-theme.md) 主题中的说明上载公司徽标后，此设置才有意义。
   - **通知** 页面：
     - **如何通知用户？** section：（可选）可以选择"使用 **自定义通知文本** "输入要使用自定义的通知文本。 还可以选择"使用 **Microsoft 翻译工具进行自动本地化**"，将自定义通知文本翻译为用户语言。 否则，保留 **"使用默认通知文本"** 为选中状态。

5. 完成后，单击提交 **，****然后单击完成。**

有关为链接配置 保险箱 链接策略和全局设置的保险箱，请参阅下列主题：

- [在 Microsoft Defender for Office 365 中设置安全链接策略](set-up-safe-links-policies.md)
- [配置"链接"保险箱全局Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>现在为 SharePoint Online 或 OneDrive for Business 中检测到的文件设置警报

若要在 SharePoint Online 或 OneDrive for Business文件被标识为恶意文件时收到通知，可以设置警报，如本节中所述。

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & collaboration** \> **Policys & Alert** \> **policy**.

2. 在" **警报策略"** 页上，单击" **新建警报策略"**。

3. 将 **打开"新建警报策略** "向导。 在" **名称** "页上，配置以下设置：
   - **名称**：输入唯一的描述性名称。 比如，你可以在库中键入恶意文件。
   - **说明**：输入可选说明。
   - **严重性：** 选择 **"低、** 中 **"** 或" **高"**。
   - **类别**：选择 **威胁管理**。

   完成后，单击"下一 **步"**

4. 在" **创建警报设置"** 页上，配置以下设置：
   - **要提醒什么？** section： **Activity is** \> **Detected malware in file**.
   - **您希望如何触发警报** 部分 **：每次选择** 活动匹配规则时验证。

   完成后，单击"下一 **步"**

5. 在 **"设置收件人"** 页上，配置以下设置：
   - **发送电子邮件通知**：验证此设置是否被选中。
   - **电子邮件收件人**：选择一个或多个全局管理员、安全管理员或安全读者，他们应在检测到恶意文件时收到通知。
   - **每日通知限制**：验证 **未选择** 限制。

   完成后，单击"下一 **步"**

6. 在" **查看设置"** 页上，查看设置，验证"是， **立即** 打开"已选中，然后单击"完成 **"**

若要了解有关警报策略的更多信息，请参阅警报[策略Microsoft 365 合规中心](../../compliance/alert-policies.md)。

> [!NOTE]
> 当你完成配置时，使用这些链接开始工作负载调查：
>
> - [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
> - [使用 Microsoft 365 Defender 门户管理邮件中的隔离Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
> - [在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到恶意文件需采取的操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [以管理员角色管理隔离的邮件和Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>安装后任务和接下来的步骤

配置威胁防护功能之后，确保监控这些功能的运行情况！ 检查并修改你的策略，让它们按你的需求运行。 同时，关注可以增加价值的新功能和服务。

|需执行的操作|了解详细信息的资源|
|---|---|
|通过查看报告了解威胁防护功能如何为你的阻止工作|[电子邮件安全报告](view-email-security-reports.md) <p> [Microsoft Defender for Office 365 报告](view-reports-for-mdo.md) <p> [威胁资源管理器](threat-explorer.md)|
|定期检查和修改你的威胁防护策略（如有需要）|[安全功能分数](../defender/microsoft-secure-score.md) <p> [Microsoft 365 威胁调查和响应功能](./office-365-ti.md)|
|关注新功能和服务更新|[标准和目标发布选项](../../admin/manage/release-options-in-office-365.md) <p> [消息中心](../../admin/manage/message-center.md) <p> [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [服务说明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
