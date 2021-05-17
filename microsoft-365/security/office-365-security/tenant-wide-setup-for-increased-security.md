---
title: 配置 Microsoft 365 租户以提高安全性
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: 本主题将指导你完成对影响租户环境安全性的租户范围内设置Microsoft 365配置。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: efcc468dc9b6a41af79ecf2f22a6ad58a410e08f
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650322"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>配置 Microsoft 365 租户以提高安全性

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本主题将指导你完成对影响租户环境安全性的租户范围内设置Microsoft 365配置。 你的安全需求可能需要更多或更少的安全性。 使用这些建议作为起点。

## <a name="check-office-365-secure-score"></a>检查Office 365安全分数

Office 365安全分数根据常规活动和安全设置分析组织的安全性，并分配分数。 首先记下当前分数。 调整一些租户范围的设置将增加你的分数。 目标不是获得最大分数，而是注意保护环境的机会，这些机会不会对用户的工作效率产生负面影响。 请参阅 [Microsoft 安全分数](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>优化安全中心Microsoft 365策略

安全Microsoft 365包括用于保护环境的功能。 它还包括可用于监视和采取措施的报告和仪表板。 某些区域具有默认策略配置。 某些区域不包括默认策略或规则。 访问威胁管理下的这些策略，以调整威胁管理设置，以创建更安全的环境。

****

|领域|包括默认策略|建议|
|---|---|---|
|**防钓鱼**|是|如果你有自定义域，请配置默认的防钓鱼策略来保护你的最有价值用户的电子邮件帐户，例如 CEO，并保护你的域。 <p> 查看[Office 365](set-up-anti-phishing-policies.md)中的反网络钓鱼策略，并参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略或在 Microsoft Defender 中配置防钓鱼策略[Office 365。](configure-atp-anti-phishing-policies.md)|
|**反恶意软件引擎**|是| 编辑默认策略： <ul><li>常见附件类型筛选器：选择"打开"</li></ul> <p> 您还可以创建自定义恶意软件筛选器策略，并应用于组织中指定的用户、组或域。 <p> 详细信息： <ul><li>[反恶意软件保护](anti-malware-protection.md)</li><li>[配置反恶意软件策略](configure-anti-malware-policies.md)</li></ul>|
|**保险箱Microsoft Defender for Office 365**|否|在"附件"保险箱主页上，单击"**全局设置**"并启用此设置： <ul><li>**启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365**</li></ul> <p> 使用保险箱创建"附件"策略： <ul><li> **阻止**：选择 **"阻止** "作为未知恶意软件响应。</li><li>**启用重定向**：选中此框并输入电子邮件地址，例如管理员或隔离帐户。</li><li>**如果恶意软件扫描附件出现时间过或出现错误，请** 应用上述选择：选中此框。</li><li>**_应用于_*： **收件人域是选择** \> 你的域。</li></ul> <p> 详细信息[：保险箱附件SharePoint、OneDrive和Microsoft Teams](mdo-for-spo-odb-and-teams.md)设置保险箱[附件策略](set-up-safe-attachments-policies.md)|
|**保险箱Microsoft Defender for Office 365**|是|在"链接"保险箱，单击"**全局设置"：** <ul><li>**Use 保险箱 Links in： Office 365 applications**： Verify this setting is turned on.</li><li>**Do not track when users click 保险箱 Links**： Turn this setting off to track user clicks.</li></ul> <p> 使用保险箱创建链接策略： <ul><li>**选择邮件中未知潜在恶意 URL 的操作**：验证此设置为 **"打开"。**</li><li>**Select the action for unknown or potentially malicious urls within Microsoft Teams**： Verify this setting is **On**.</li><li>**对指向文件的可疑链接应用实时 URL** 扫描：选中此框。</li><li>**等待 URL 扫描完成，然后再传递消息**：选中此框。</li><li>**Apply 保险箱 Links to email messages sent within the organization**： Check this box</li><li>**不允许用户单击到原始 URL：** 选中此框。</li><li>**应用于**： **收件人域是选择** \> 你的域。</li></ul> <p> 详细信息：[设置保险箱链接策略。](set-up-safe-links-policies.md)|
|**反垃圾邮件 (邮件筛选)**|是| 要关注哪些方面： <ul><li>垃圾邮件过多 — 选择"自定义"设置并编辑"默认垃圾邮件筛选器"策略。</li><li>欺骗智能 — 审查欺骗你的域的发件人。 阻止或允许这些发件人。</li></ul> <p> 详细信息[：Microsoft 365电子邮件反垃圾邮件保护。](anti-spam-protection.md)|
|***电子邮件身份验证***|是|电子邮件身份验证使用域名系统 (DNS) 向电子邮件添加有关电子邮件发件人的可验证信息。 Microsoft 365为默认域设置电子邮件 (onmicrosoft.com) ，Microsoft 365管理员也可以对自定义域使用电子邮件身份验证。 使用三种身份验证方法： <ul><li>发件人策略框架 (SPF) 。</li><ul><li>有关设置，请参阅在 Microsoft 365[中设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>域密钥标识的邮件 (DKIM) 。</li><ul><li>请参阅 [使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</li><li>配置 DKIM 后，在安全中心启用它。</li></ul><li>基于域的邮件身份验证、报告和一致性 (DMARC) 。</li><ul><li>对于 DMARC[设置 使用 DMARC 验证电子邮件Microsoft 365。](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> 对于 SPF 的非标准部署、混合部署和故障排除：Microsoft 365 如何使用发件人策略框架[ (SPF](how-office-365-uses-spf-to-prevent-spoofing.md)) 防止欺骗。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>查看安全与合规中心中的仪表板和报告

访问这些报告和仪表板，详细了解环境的运行状况。 随着组织使用服务，这些报告Office 365更加丰富。 现在，请熟悉可以监视和采取操作的操作。 有关详细信息，请参阅：安全[与合规Microsoft 365报告](../../compliance/reports-in-security-and-compliance.md)。

****

|仪表板|说明|
|---|---|
|[威胁管理仪表板](security-dashboard.md)|在安全中心的"威胁管理"部分，使用此仪表板查看已处理的威胁，并作为向业务决策者报告已执行的威胁调查和响应功能以确保业务安全的方便工具。|
|[威胁资源管理器（或实时检测）](threat-explorer.md)|这同样位于 **安全中心的"** 威胁管理"部分。 如果你正在调查或遇到对租户的攻击，请使用资源管理器 (或实时检测) 分析威胁。 资源管理器 (实时检测报告) 显示一段时间的攻击量，并且你可以按威胁系列、攻击者基础结构等分析此数据。 您还可以为"事件"列表标记任何可疑电子邮件。|
|报表 — 仪表板|在安全 **中心的**"报告"部分，查看 SharePoint Online Exchange Online报告。 还可以从"查看Azure Active Directory (") 访问 Azure AD) 、用户活动报告和 Azure AD 审核日志 Azure AD **帐户。**|
|

![安全中心仪表板](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>配置Exchange Online租户范围内的其他设置

安全中心中还包括安全中心Exchange安全和保护的许多控件。 无需在这两处配置它们。 下面是一些建议的其他设置。

****

|领域|包括默认策略|建议|
|---|---|---|
|**邮件Flow (** 规则，也称为传输规则) |否|添加邮件流规则，通过阻止可执行文件类型和包含宏的文件类型Office反勒索软件。 有关详细信息，请参阅 Use [mail flow rules to inspect message attachments in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <p> 请参阅以下其他主题： <ul><li>[防范勒索软件](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[恶意软件和勒索软件保护Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[从 Office 365 中的勒索软件Office 365](recover-from-ransomware.md)</li></ul> <p> 创建邮件流规则以防止电子邮件自动转发到外部域。 有关详细信息，请参阅使用安全分数缓解客户端 [外部转发规则](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 详细信息：[邮件流规则 (传输规则) Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**启用新式验证**|否|新式验证是使用多重身份验证和 MFA (的先决条件) 。 建议使用 MFA 来保护对云资源（包括电子邮件）的访问。 <p> 请参阅以下主题： <ul><li>[在 Exchange Online 中启用或禁用新式身份验证](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business联机：为租户启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 默认情况下，为 Office 2016 客户端、SharePoint Online 和 OneDrive for Business 启用新式OneDrive for Business。 <p> 详细信息：[新式验证如何适用于 Office 2013 和 Office 2016 客户端应用](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>在管理中心中配置租户SharePoint策略

Microsoft 建议从SharePoint保护级别配置团队网站。 有关详细信息，请参阅[用于保护网站和文件SharePoint策略建议](sharepoint-file-access-policies.md)。

SharePoint级别配置的工作组网站允许使用匿名访问链接与外部用户共享文件。 建议采用这种方法，而不是通过电子邮件发送文件。

若要支持基线保护的目标，请配置租户范围的共享策略，如此处所建议。 与租户范围策略不同，单个网站的共享设置可能更加严格，但不允许。

****

|领域|包括默认策略|建议|
|---|---|---|
|**共享** (SharePoint Online 和 OneDrive for Business) |是|默认情况下启用外部共享。 建议使用这些设置： <ul><li>允许与经过身份验证的外部用户共享和使用匿名访问 (默认设置) 。</li><li>匿名访问链接将在这几天内过期。 如果需要，请输入一个数字，如 30 天。</li><li>默认链接类型 - 选择"内部 (仅组织内部) " 希望使用匿名链接共享的用户必须从共享菜单中选择此选项。</li></ul> <p> 详细信息： [外部共享概述](/sharepoint/external-sharing-overview)|
|

SharePoint管理中心OneDrive for Business管理中心包含相同的设置。 任一管理中心中的设置均适用于这两者。

## <a name="configure-settings-in-azure-active-directory"></a>配置 Azure Active Directory

请务必在租户中访问这两Azure Active Directory，以完成租户范围的设置，以创建更安全的环境。

### <a name="configure-named-locations-under-conditional-access"></a>在条件访问 (配置命名) 

如果组织包括具有安全网络访问权限的办事处，将受信任的 IP 地址范围Azure Active Directory命名位置。 此功能有助于减少登录风险事件报告的误报数。

请参阅[：Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>阻止不支持新式验证的应用

多重身份验证需要支持新式验证的应用。 不支持新式身份验证的应用无法使用条件访问规则阻止。

对于安全环境，请确保对不支持新式验证的应用禁用身份验证。 可以使用即将Azure Active Directory的控件来完成此操作。

同时，使用下列方法之一为 SharePoint Online 和 OneDrive for Business：

- 使用 PowerShell，请参阅 [阻止在 ADAL ](/mem/intune/protect/app-modern-authentication-block)应用中不使用新式 () 。

- 在管理中心SharePoint"设备访问"页面"控制不使用新式验证的应用的访问"中对此进行配置。 选择"阻止"。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>开始云应用安全或Office 365 云应用安全

使用Office 365 云应用安全评估风险，对可疑活动发出警报，并自动采取措施。 需要Office 365 E5 计划。

或者，Microsoft Cloud App Security在授予访问权限后获取更深层次的可见性、全面的控件以及针对所有云应用程序（包括云应用程序）Office 365。

由于此解决方案建议使用 EMS E5 计划，因此我们建议你从 云应用安全开始，以便你可以将此方法用于环境中的其他 SaaS 应用程序。 从默认策略和设置开始。

详细信息：

- [部署 Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)

- [有关 Microsoft Cloud App Security 的更多信息](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [什么是云应用安全？](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security 仪表板](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>其他资源

这些文章和指南提供了用于保护安全环境的其他Microsoft 365信息：

- [适用于政治宣传活动、](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 非营利组织和其他敏捷型组织的 Microsoft 安全指南 (可以在任何环境中使用这些建议，尤其是仅云环境) 

- [针对标识和设备的建议安全策略](microsoft-365-policies-configurations.md) 和配置 (这些建议包括 AD FS 环境) 