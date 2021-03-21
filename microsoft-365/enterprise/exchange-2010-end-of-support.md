---
title: Exchange 2010 支持终止路线图
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 已终止支持。 使用此规划路线图准备升级到 Exchange Online 或本地 Exchange Server版本。
ms.openlocfilehash: f3531802283368e533ba6646415d4acc019687bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926990"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 支持终止路线图

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Exchange Server 2010 年 10 月 **13** 日终止支持。 如果尚未开始从 Exchange 2010 到 Microsoft 365、Office 365 或 Exchange 2016 的迁移，那么现在可以开始规划了。

## <a name="what-does-end-of-support-mean"></a>停止 *提供支持意味着什么* ？

大多数 Microsoft 产品都有一个支持生命周期，在此期间它们获取新功能、Bug 修复、安全修补程序等。 此生命周期通常自产品初始发布起持续 10 年。 此生命周期的结束称为产品的停止支持。 由于 Exchange 2010 于 2020 年 10 月 13 日终止支持，因此 Microsoft 不再提供：

- 针对可能会出现的问题的技术支持。
- 对可能会影响服务器稳定性和可用性的问题进行 Bug 修复。
- 针对可能导致服务器易受安全漏洞的漏洞进行安全修复。
- 时区更新。

您安装的 Exchange 2010 将在此日期之后继续运行。 但由于上述更改，我们强烈建议您尽快从 Exchange 2010 迁移。

有关即将停止提供支持的信息，请参阅帮助您从 Office [2010 服务器和客户端升级的资源](upgrade-from-office-2010-servers-and-products.md)。

## <a name="what-are-my-options"></a>我的选项是什么？

是时候探索你的选项并准备迁移计划了。 可以执行下列操作：

- 完全迁移到 Microsoft 365。 使用转换、最小混合或完全混合迁移迁移邮箱。 然后删除本地 Exchange 服务器和 Active Directory。
- 将 Exchange 2010 服务器迁移到本地服务器的 Exchange 2016。

> [!IMPORTANT]
> 如果组织选择将邮箱迁移到 Microsoft 365，但计划保留 DirSync 或 Azure AD Connect 以继续从本地 Active Directory 管理用户帐户，则需要至少保留一台本地 Microsoft Exchange 服务器。 如果删除所有 Exchange 服务器，将无法对 Exchange Online 中的 Exchange 收件人进行更改，因为授权源仍保留在内部部署 Active Directory 中。 需要在那里进行更改。 在此方案中，有以下选项：
>
>- *建议：* 如果在 2020 年 10 月 13 日之前将邮箱迁移到 Microsoft 365 并升级服务器，请使用 Exchange 2010 连接到 Microsoft 365 并迁移邮箱。 接下来，将 Exchange 2010 迁移到 Exchange 2016，并停止使用任何剩余的 Exchange 2010 服务器。
>- 如果您未在 2020 年 10 月 13 日之前完成邮箱迁移和内部部署服务器升级，请首先将本地 Exchange 2010 服务器升级到 Exchange 2016。 然后使用 Exchange 2016 连接到 Microsoft 365 并迁移邮箱。

> [!NOTE]
> 虽然这稍微复杂一些，但您也可以将邮箱迁移到 Microsoft 365，同时将本地 Exchange 2010 服务器迁移到 Exchange 2016。

以下是避免对 2010 年 10 月支持终止的三Exchange Server路径。

![Exchange Server 2010 升级路径](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

以下各节更详细地探讨每个选项。

## <a name="migrate-to-microsoft-365"></a>迁移到 Microsoft 365

将电子邮件迁移到 Microsoft 365 是帮助你停用 Exchange 2010 部署的最佳且最简单的选项。 迁移到 Microsoft 365 后，你可以从旧技术到当前功能进行单个跃点，包括：

- 合规性功能，如保留策略、In-Place和诉讼保留、就地电子数据展示等。
- Microsoft Teams。
- Power BI。
- 重点收件箱。
- MyAnalytics。

Microsoft 365 还首先获取新功能和体验，以便你的组织可以立即开始使用它们。 此外，也无需担心：

- 购买和维护硬件。
- 支付热和冷服务器费用。
- 保持最新的安全、产品和时区修补程序。
- 维护存储和软件以支持合规性要求。
- 升级到新版本的 Exchange。 你始终在 Microsoft 365 中使用最新版本的 Exchange。

### <a name="how-should-i-migrate-to-microsoft-365"></a>如何迁移到 Microsoft 365？

根据你的组织，你具有一些访问 Microsoft 365 的选项。 首先，需要考虑一些方面，例如：
- 需要移动的席位或邮箱数。
- 希望迁移持续多久。
- 在迁移期间，是否需要本地安装和 Microsoft 365 之间的无缝集成。
 
此表显示了迁移选项以及决定使用哪种方法的最重要的因素。

|迁移选项|组织规模|持续时间|
|---|---|---|
|直接转换迁移|少于 150 个席位|一周或更少|
|最小混合迁移|少于 150 个席位|几周或更久|
|完全混合迁移|多于 150 个席位|几周或更久|

以下各节概述了这些方法。 有关详细信息，请参阅 [确定迁移路径](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。

### <a name="cutover-migration"></a>直接转换迁移

在直接转换迁移中，您可以在设置的日期和时间将所有邮箱、通讯组、联系人等迁移到 Office 365。 完成后，您将关闭内部部署 Exchange 服务器，并开始以独占方式使用 Microsoft 365。

对于没有很多邮箱、想要快速到达 Microsoft 365 并且不想处理其他方法的复杂性的小组织来说，转换迁移非常不错。 但应在一周或更之后完成。 而且，它要求用户重新配置其 Outlook 配置文件。 虽然转换迁移最多可迁移 2，000 个邮箱，但我们建议您最多使用 150 个邮箱。 如果尝试迁移更多邮箱，在截止时间之前转移所有邮箱的时间可能会用完，并且 IT 支持人员可能会因请求帮助用户重新配置 Outlook 而感到不知所措。

下面是有关转换迁移的要考虑的一些内容：

- Microsoft 365 将需要通过 TCP 端口 443 使用 Outlook Anywhere 连接到 Exchange 2010 服务器。
- 所有本地邮箱都将移动到 Microsoft 365。
- 您需要具有用户邮箱的读取访问权限的本地管理员帐户。
- 需要将想要在 Microsoft 365 中使用的 Exchange 2010 接受域添加为服务中的已验证域。
- 从开始迁移到开始完成阶段，Microsoft 365 将定期同步 Microsoft 365 和本地邮箱。 这样，您即可完成迁移，而无需担心电子邮件会遗留在本地邮箱中。
- 用户将收到其 Microsoft 365 帐户的新临时密码。 第一次登录邮箱时，用户需要更改它们。
- 对于迁移的每个用户邮箱，需要包含 Exchange Online 的 Microsoft 365 许可证。
- 用户需要在每个设备上设置新的 Outlook 配置文件，并再次下载他们的电子邮件。 Outlook 将下载的电子邮件数量可能会有所不同。 有关详细信息，请参阅在 [Outlook 中脱机工作](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)。

若要了解有关转换迁移的更多信息，请参阅：

- [有关转换电子邮件迁移的需知信息](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [执行电子邮件到 Office 365 的转换迁移](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>最小混合迁移

在最小混合或快速迁移中，您可以在几周内将几百个邮箱移动到 Microsoft 365。 此方法不支持高级混合迁移功能，如共享忙/闲日历信息。

最少混合迁移非常适用于需要花更多时间将其邮箱迁移到 Microsoft 365 但仍计划在几周内完成迁移的组织。 你可以从更高级的完全混合迁移获得一些好处，而无需任何复杂性。 您可以控制在给定时间要迁移的邮箱数和邮箱数。 Microsoft 365 邮箱将创建为本地帐户的用户名和密码。 而且，与转换迁移不同，用户不必重新创建其 Outlook 配置文件。

下面是有关最小混合迁移的要考虑的一些内容：

- 你需要在本地 Active Directory 服务器和 Microsoft 365 之间执行一次目录同步。
- 用户将能够使用与邮箱之前相同的用户名和密码登录其 Microsoft 365 邮箱。
- 对于迁移的每个用户邮箱，需要包含 Exchange Online 的 Microsoft 365 许可证。
- 用户无需在大部分设备上设置新的 Outlook 配置文件，尽管某些较旧的 Android 手机可能需要新的配置文件。 用户无需重新下载其电子邮件。

有关详细信息，请参阅使用最小混合[快速将 Exchange 邮箱迁移到 Office 365。](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>完全混合

在完全混合迁移中，您拥有数百个（最多数万个）邮箱，并且您将部分或全部移动到 Microsoft 365。 由于这些迁移通常是长期迁移，因此混合迁移可以：

- 向本地用户显示 Microsoft 365 中的用户的忙/闲日历信息，反之亦然。
- 请参阅包含本地和 Microsoft 365 中的收件人的统一全局地址列表。
- 查看所有用户的完整 Outlook 收件人属性，无论他们是本地用户还是 Microsoft 365 用户。
- 使用 TLS 和证书保护本地 Exchange 服务器与 Office 365 之间的电子邮件通信安全。
- 将在本地 Exchange 服务器和 Microsoft 365 之间发送的邮件视为内部邮件，从而使这些邮件能够：
  - 由面向内部邮件的传输和合规性代理正确评估和处理。
  - 绕过反垃圾邮件筛选器。

完全混合迁移最适合希望保持混合配置数月或数月以上的组织。 你可以获取本节前面列出的功能，以及目录同步、更好的集成合规性功能，以及使用联机邮箱移动将邮箱移动到 Microsoft 365 和从 Microsoft 365 移动邮箱的功能。 Microsoft 365 将成为本地组织的扩展。

有关完全混合迁移需要考虑的一些内容：

- 它们并不适合所有组织。 由于完全混合迁移的复杂性，拥有少于几百个邮箱的组织通常看不到证明所涉及工作量和成本合理的好处。 在这种情况下，我们建议你改为考虑使用"转换"或"最小混合迁移"。
- 你需要在本地 Active Directory 服务器和 Microsoft 365 之间使用 Azure Active Directory (Azure AD) Connect 设置目录同步。
- 用户将能够使用登录到本地网络时使用的相同用户名和密码登录其 Microsoft 365 邮箱。  (此功能需要 Azure AD Connect 密码同步和/或 Active Directory 联合身份验证服务) 。
- 您需要一个 Microsoft 365 许可证，其中包含迁移的每个用户邮箱的 Exchange Online。
- 尽管某些较旧的 Android 手机可能需要新的配置文件，但用户无需在大部分设备上设置新的 Outlook 配置文件。 用户无需重新下载其电子邮件。

> [!IMPORTANT]
> 如果组织选择将邮箱迁移到 Microsoft 365，但计划保留 DirSync 或 Azure AD Connect 以继续从本地 Active Directory 管理用户帐户，则需要至少保留一台本地 Exchange 服务器。 如果删除所有 Exchange 服务器，将无法在 Exchange Online 中更改 Exchange 收件人。 这是因为授权源仍保留在本地 Active Directory 中，并且需要在那里进行更改。

如果完全混合迁移适合您，请参阅以下有用资源：

- [Exchange 部署助理](/exchange/exchange-deployment-assistant)
- [Exchange Server 混合部署](/exchange/exchange-hybrid)
- [混合配置向导](/exchange/hybrid-configuration-wizard)
- [混合配置向导常见问题解答](/exchange/hybrid-configuration-wizard-faqs)
- [混合部署先决条件](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>升级到本地部署Exchange Server版本

我们强烈建议你通过完全迁移到 Microsoft 365 获得最佳价值和用户体验。 但我们了解一些组织需要将某些 Exchange 服务器保留在本地。 这可能是由于法规要求、保证数据不存储在外数据中心中、因为您具有在云中无法满足的独特设置或要求，或者因为您仍使用本地 Active Directory，因此您需要 Exchange 来管理云邮箱。 在任何情况下，如果您将 Exchange 保留在本地，则应确保 Exchange 2010 环境已至少升级到 Exchange 2013 或 Exchange 2016。

为了获得最佳体验，建议您将其余本地环境升级到 Exchange 2016。 如果你想要直接从 Exchange Server 2010 到 Exchange Server 2016，无需安装 Exchange Server 2013。

Exchange 2016 包括以前 Exchange 版本的所有功能。 虽然某些功能仅在 Microsoft 365 中可用，但它与 Microsoft 365 提供的体验最为匹配。 查看你缺少的一些内容：

|Exchange 版本|功能|
|---|---|
|**Exchange 2013**|简化的体系结构将邮箱、客户端访问、边缘传输 (服务器角色的数量减少为三) |
||数据丢失防护策略 (DLP) ，有助于防止敏感信息泄露|
||改进Outlook Web App体验|
|**Exchange 2016**|*Exchange 2013 中的功能和 ...*|
||将服务器角色进一步简化为仅邮箱和边缘传输|
||改进的 DLP 与 SharePoint 的集成|
||改进了数据库恢复能力|
||联机文档协作|

|注意事项|更多信息|
|---|---|
|支持结束日期|与 Exchange 2010 一样，每个版本的 Exchange 都有自己的支持结束日期：<br/><br/>Exchange 2013 - 2023 年 4 月<br/>Exchange 2016 - 2025 年 10 月<br/><br/>支持结束日期越早，需要执行另一个迁移越早。 2023 年 4 月比您想象得要近很多！|
|Exchange 2013 或 2016 的迁移路径|无论选择 Exchange 2013 还是 Exchange 2016，从 Exchange 2010 到较新版本的迁移路径都是相同的：<br/><br/>将 Exchange 2013 或 2016 安装到现有的 Exchange 2010 组织中。<br/>将服务和其他基础结构移动到 Exchange 2013 或 2016。<br/>将邮箱和公用文件夹移动到 Exchange 2013 或 2016 停止使用其余 Exchange 2010 服务器。|
|版本共存|迁移到 Exchange 2013 或 Exchange 2016 时，您可以将任一版本安装到现有 Exchange 2010 组织中。 这使您能够安装一个或多个 Exchange 2013 或 Exchange 2016 服务器并执行迁移。|
|服务器硬件|Exchange 2010 中的服务器硬件要求已更改。 确保你的硬件兼容。 在此处了解有关每个版本的硬件要求更多信息：<br/><br/>[Exchange 2016 系统要求](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Exchange 2013 系统要求](/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>随着 Exchange 性能的显著改善以及较新服务器中的计算能力和存储容量的增加，您可能需要更少的服务器来支持相同数量的邮箱。|
|操作系统版本|每个版本支持的最低操作系统版本为：<br/><br/>Exchange 2016 - Windows Server 2012<br/>Exchange 2013 - Windows Server 2008 R2 SP1<br/><br/>有关操作系统支持的信息，请参阅 [Exchange 可支持性矩阵](/exchange/plan-and-deploy/supportability-matrix)。|
|Active Directory 林功能级别|每个版本支持的最低 Active Directory 林功能级别为：<br/><br/>Exchange 2016 - Windows Server 2008 R2 SP1<br/>Exchange 2013 - Windows Server 2003<br/><br/>有关林功能级别支持的信息，请参阅 Exchange [可支持性矩阵](/exchange/plan-and-deploy/supportability-matrix)。|
|Office 客户端版本|每个版本支持的最低 Office 客户端版本为：<br/><br/>Exchange 2016 - Office 2010 (最新更新) <br/>Exchange 2013 - Office 2007 SP3<br/><br/>有关 Office 客户端支持详细信息，请参阅 [Exchange 可支持性矩阵](/exchange/plan-and-deploy/supportability-matrix)。||| 


使用以下资源来帮助进行迁移：

- [Exchange 部署助理](/exchange/exchange-deployment-assistant)
- Exchange [2016 、2013](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016)的 Active Directory [架构更改](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Exchange [2016 和 2013](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016)[的系统要求](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016)和 [2013 的先决条件](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 客户端、服务器和 Windows 7 的选项摘要

有关 Office 2010 客户端和服务器以及 Windows 7 的升级、迁移和移动到云选项的直观摘要，请参阅[终止支持海报](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![停止支持 Office 2010 客户端和服务器以及 Windows 7 海报](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

此单页海报演示了响应 Office 2010 客户端和服务器产品和 Windows 7 达到支持终止的各种途径，并突出显示了 Microsoft 365 企业版中的首选路径和选项支持。

您还可以下载 [此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) ，以 11 x 17 格式的信件、 (或文) 打印。

## <a name="what-if-i-need-help"></a>如果需要帮助，如何？

如果你要迁移到 Microsoft 365，你可能有资格使用我们的 Microsoft FastTrack 服务。 FastTrack 提供了最佳做法、工具和资源，可尽可能无缝地迁移到 Microsoft 365。 最好有一位支持工程师，负责将你完成从规划和设计到迁移最后一个邮箱的阶段。 有关 FastTrack 的更多信息，请参阅[Microsoft FastTrack。](https://fasttrack.microsoft.com/)

如果在迁移到 Microsoft 365 期间遇到问题，并且不使用 FastTrack，或者正在迁移到较新版本的 Exchange Server，可以使用以下资源：

- [技术社区](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [客户支持](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>相关文章

[帮助从 Office 2010 服务器和客户端升级的相关资源](upgrade-from-office-2010-servers-and-products.md)