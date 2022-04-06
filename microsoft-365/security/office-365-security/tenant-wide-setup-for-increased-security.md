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
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
description: 本主题将指导你完成影响租户环境安全性的租户范围内设置Microsoft 365配置。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96f31d0fb9eb3ef9d6eaec396fdac8fe96b96c3d
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476348"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>配置 Microsoft 365 租户以提高安全性

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本主题将指导你完成影响租户环境安全性的租户范围内设置Microsoft 365配置。 你的安全需求可能需要更多或更少的安全性。 使用这些建议作为起点。

## <a name="check-office-365-secure-score"></a>检查Office 365安全分数

Office 365安全分数根据常规活动和安全设置分析组织的安全性，并分配分数。 首先记下当前分数。 调整一些租户范围的设置将增加你的分数。 目标不是获得最大分数，而是注意保护环境的机会，这些机会不会对用户的工作效率造成负面影响。 请参阅 [Microsoft 安全分数](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>优化威胁管理门户中Microsoft 365 Defender策略

Microsoft 365 Defender门户包含用于保护环境的功能。 它还包括可用于监视和采取措施的报告和仪表板。 某些区域具有默认策略配置。 某些区域不包括默认策略或规则。 访问电子邮件和协作策略 **&**\>策略&**策略** \> **"** 下的这些策略，以调整威胁管理设置，实现更安全的环境。

|领域|默认策略？|建议|
|---|---|---|
|**防钓鱼**|是|配置默认的防钓鱼策略，如下所述：[在 EOP 和 Defender](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365) 中配置防钓鱼保护设置Office 365。 <p> 详细信息： <ul><li>[Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [模拟见解](impersonation-insight.md)</li><li>[EOP 中的欺骗智能见解](learn-about-spoof-intelligence.md)</li><li>[管理租户允许/阻止列表](tenant-allow-block-list.md)。</li></ul>|
|**反恶意软件引擎**|是|配置默认反恶意软件策略，如下所述： [在 EOP 中配置反恶意软件保护设置](protect-against-threats.md#part-1---anti-malware-protection-in-eop)。 <p> 详细信息： <ul><li>[反恶意软件保护](anti-malware-protection.md)</li><li>[建议的反恶意软件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[配置反恶意软件策略](configure-anti-malware-policies.md)</li></ul>|
|**Defender for Office 365 中的安全附件**|否|配置"附件"保险箱全局设置，并创建"保险箱 附件"策略，如下所述：在 [Microsoft Defender](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365) 中配置 保险箱 Attachments 设置Office 365。 <p> 详细信息： <ul><li>[推荐保险箱附件设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[保险箱 Microsoft Defender for Office 365](safe-attachments.md)</li><li>[设置安全附件策略](set-up-safe-attachments-policies.md)</li><li>[用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)</li><li>[Microsoft 365 E5 中的安全文档](safe-docs.md)</li></ul>|
|**保险箱 Microsoft Defender for Office 365**|否|配置链接的全局设置保险箱创建保险箱链接策略，如下所述：在 [Microsoft Defender](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365) 中配置 保险箱 链接设置Office 365。 <p> 详细信息： <ul><li>[推荐保险箱链接设置](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[设置安全链接策略](set-up-safe-links-policies.md)</li><li>[保险箱 Microsoft Defender for Office 365](safe-links.md)</li><li>[在 Microsoft Defender for 保险箱 中配置链接的全局Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**反垃圾邮件 (邮件筛选)**|是|配置默认反垃圾邮件策略，如下所述： [在 EOP 中配置反垃圾邮件保护设置](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> 详细信息： <ul><li>[建议的反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[EOP 中的反垃圾邮件保护](anti-spam-protection.md)</li><li>[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)</li></ul>|
|***电子邮件身份验证***|是|电子邮件身份验证使用 DNS 记录向电子邮件中添加有关邮件源和发件人的可验证信息。 Microsoft 365自动为默认域配置电子邮件 (onmicrosoft.com) ，Microsoft 365管理员还可以为自定义域配置电子邮件身份验证。 使用三种身份验证方法： <ul><li>发件人策略框架 (SPF) 。</li><ul><li>有关设置，请参阅[在 Microsoft 365 中设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>域密钥标识的邮件 (DKIM) 。</li><ul><li>请参阅 [使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</li><li>配置 DKIM 后，在 Microsoft 365 Defender 门户中启用它。</li></ul><li>基于域的邮件身份验证、报告和一致性 (DMARC) 。</li><ul><li>对于 DMARC [设置，使用 DMARC 验证邮件Microsoft 365](use-dmarc-to-validate-email.md)。</li></ul></ul>|

> [!NOTE]
> 对于 SPF 的非标准部署、混合部署和疑难解答：Microsoft 365如何使用发件人策略框架 [ (SPF) 防止欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>在仪表板门户中查看Microsoft 365 Defender报表

访问这些报告和仪表板，详细了解环境的运行状况。 随着组织使用服务，这些报告Office 365更加丰富。 现在，请熟悉可以监视和采取操作的操作。

|仪表板|说明|
|---|---|
|电子邮件安全报告|这些报告在 Exchange Online Protection 中提供。 有关详细信息，请参阅在电子邮件[门户中查看Microsoft 365 Defender报告](view-email-security-reports.md)。|
|Defender for Office 365 报告|报告仅在 Defender for Office 365。 有关详细信息，请参阅在 Office 365 门户中查看适用于[Microsoft 365 Defender报告](view-reports-for-mdo.md)。|
|邮件流报告和见解|这些报告和见解位于 EAC Exchange管理 (中心) 。 有关详细信息，请参阅邮件[流报告和](/exchange/monitoring/mail-flow-reports/mail-flow-reports)[邮件流见解](/exchange/monitoring/mail-flow-insights/mail-flow-insights)。|
|[威胁资源管理器（或实时检测）](threat-explorer.md)|如果你正在调查或遇到对租户的攻击，请使用资源管理器 (或实时检测) 分析威胁。 资源管理器 (实时检测报告) 显示一段时间的攻击量，并且你可以按威胁系列、攻击者基础结构等分析此数据。 您还可以为"事件"列表标记任何可疑电子邮件。|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>配置Exchange Online范围内的其他设置

下面是一些建议的其他设置。

|领域|建议|
|---|---|
|**邮件流规则** (也称为传输规则) |添加邮件流规则，通过阻止可执行文件类型和包含宏的Office来帮助防范勒索软件。 有关详细信息，请参阅使用[邮件流规则检查邮件Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <p> 请参阅以下其他主题： <ul><li>[防范勒索软件](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[恶意软件和勒索软件保护Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[从 Office 365 中的勒索软件攻击中Office 365](recover-from-ransomware.md)</li></ul> <p> 创建邮件流规则以防止电子邮件自动转发到外部域。 有关详细信息，请参阅使用安全 [分数缓解客户端外部转发规则](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 详细信息：[邮件流规则 (传输规则) Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**新式验证**|新式验证是使用 MFA 身份验证和 MFA (的先决条件) 。 建议使用 MFA 来保护对云资源（包括电子邮件）的访问。 <p> 请参阅以下主题： <ul><li>[在 Exchange Online 中启用或禁用新式身份验证](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online：为租户启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 默认情况下，为 Office 2016 客户端、SharePoint Online 和 OneDrive for Business 启用新式OneDrive for Business。 <p> 详细信息：[新式验证如何适用于 Office 2013 和 Office 2016 客户端应用](../../enterprise/modern-auth-for-office-2013-and-2016.md)|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>在管理中心中配置租户SharePoint策略

Microsoft 建议从SharePoint保护级别配置团队网站。 有关详细信息，请参阅[用于保护网站和文件SharePoint策略建议](sharepoint-file-access-policies.md)。

SharePoint级别配置的工作组网站允许使用匿名访问链接与外部用户共享文件。 建议采用这种方法，而不是通过电子邮件发送文件。

若要支持基线保护的目标，请配置租户范围的共享策略，如此处所建议。 与租户范围策略不同，单个网站的共享设置可能更加严格，但不允许。

|领域|包括默认策略|建议|
|---|---|---|
|**共享** (SharePoint Online 和 OneDrive for Business) |是|默认情况下启用外部共享。 建议使用这些设置： <ul><li>允许向经过身份验证的外部用户共享和使用匿名访问 (默认设置) 。</li><li>匿名访问链接将在这几天内过期。 如果需要，请输入一个数字，如 30 天。</li><li>默认链接类型 - 选择"内部 (仅组织内部) 。 希望使用匿名链接共享的用户必须从共享菜单中选择此选项。</li></ul> <p> 详细信息： [外部共享概述](/sharepoint/external-sharing-overview)|

SharePoint管理中心OneDrive for Business管理中心包含相同的设置。 任一管理中心中的设置均适用于这两者。

## <a name="configure-settings-in-azure-active-directory"></a>配置Azure Active Directory

请务必在租户中访问这两Azure Active Directory，以完成租户范围的设置，以更安全的环境。

### <a name="configure-named-locations-under-conditional-access"></a>在条件访问 (配置命名) 

如果组织包括具有安全网络访问权限的办事处，将受信任的 IP 地址范围Azure Active Directory命名位置。 此功能有助于减少登录风险事件报告的误报数。

请参阅：[Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>阻止不支持新式验证的应用

多重身份验证需要支持新式验证的应用。 不支持新式身份验证的应用无法使用条件访问规则阻止。

对于安全环境，请确保对不支持新式验证的应用禁用身份验证。 可以使用即将Azure Active Directory的控件进行此操作。

同时，使用下列方法之一为 SharePoint Online 和 OneDrive for Business：

- 使用 PowerShell，请参阅 [阻止不使用新式验证的应用](/mem/intune/protect/app-modern-authentication-block)。
- 在管理中心SharePoint<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank"></a>"设备访问"页面"控制不使用新式验证的应用的访问"中对此进行配置。 选择"阻止"。

## <a name="get-started-with-defender-for-cloud-apps-or-office-365-cloud-app-security"></a>适用于云应用或应用的 Defender Office 365 云应用安全

使用Office 365 云应用安全评估风险，对可疑活动发出警报，并自动采取措施。 需要Office 365 E5计划。

或者，使用 Microsoft Defender for Cloud Apps 获取更深层次的可见性，即使在授予访问权限后，也可以全面控制所有云应用程序，包括Office 365。

由于此解决方案推荐 EMS E5 计划，我们建议你从 Defender for Cloud Apps 开始，以便你可以将此功能与环境中的其他 SaaS 应用程序一同使用。 从默认策略和设置开始。

详细信息：

- [部署 Microsoft Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security)
- [有关 Microsoft Defender for Cloud Apps 的详细信息](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [什么是 Defender for Cloud Apps 许可？](/cloud-app-security/what-is-cloud-app-security)

:::image type="content" source="../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png" alt-text="云应用 Defender 仪表板" lightbox="../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png":::

## <a name="additional-resources"></a>其他资源

这些文章和指南提供了用于保护安全环境的其他Microsoft 365信息：

- [适用于政治宣传活动、](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 非营利组织和其他敏捷型组织的 Microsoft 安全指南 (可以在任何环境中使用这些建议，尤其是仅云环境) 

- [针对标识和设备的建议安全策略](microsoft-365-policies-configurations.md) 和配置 (这些建议包括 AD FS 环境) 
