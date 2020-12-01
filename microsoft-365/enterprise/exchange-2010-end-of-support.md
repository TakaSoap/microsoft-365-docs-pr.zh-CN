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
description: Exchange 2010 已到达支持终止。 使用此规划指南准备升级到 Exchange Online 或本地 Exchange Server 的较新版本。
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519687"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 支持终止路线图

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Exchange Server 2010 在 **2020 年10月13日** 到达其支持的结束。 如果尚未开始从 Exchange 2010 迁移到 Microsoft 365、Office 365 或 Exchange 2016，现在是开始进行规划的时间。

## <a name="what-does-end-of-support-mean"></a>*支持终止的* 含义是什么？

大多数 Microsoft 产品都有支持生命周期，在此期间，他们将获得新的功能、缺陷修补程序、安全修补程序等。 此生命周期通常是从产品的初始版本中持续10年的时间。 此生命周期的结束被称为产品的支持终止。 由于 Exchange 2010 在2020年10月13日到达其支持的结束时间，Microsoft 不再提供：

- 可能出现的问题的技术支持。
- 针对可能会影响服务器稳定性和可用性的问题的 Bug 修补程序。
- 安全修补程序可能会使服务器易受安全漏洞破坏。
- 时区更新。

在此日期之后，你的 Exchange 2010 安装将继续运行。 但由于上面列出的更改，强烈建议您尽快从 Exchange 2010 迁移。

有关即将结束支持的详细信息，请参阅可 [帮助您从 Office 2010 服务器和客户端进行升级的资源](upgrade-from-office-2010-servers-and-products.md)。

## <a name="what-are-my-options"></a>我的选项是什么？

了解你的选项并准备迁移计划是个好的时间。 可执行下列操作：

- 完全迁移到 Microsoft 365。 使用直接转换、最小混合或完全混合迁移迁移邮箱。 然后删除本地 Exchange 服务器和 Active Directory。
- 将 Exchange 2010 服务器迁移到本地服务器上的 Exchange 2016。

> [!IMPORTANT]
> 如果你的组织选择将邮箱迁移到 Microsoft 365，但计划保留 DirSync 或 Azure AD Connect，以继续从本地 Active Directory 中管理用户帐户，你至少需要保留一个 Microsoft Exchange server 内部部署。 如果删除了所有 Exchange 服务器，则不能在 Exchange Online 中更改 Exchange 收件人，因为颁发机构的来源仍在本地 Active Directory 中。 需要对其进行更改。 在这种情况下，您有以下几种选择：
>
>- *建议：* 如果您将邮箱迁移到 Microsoft 365，并在10月13日之前将服务器升级到2020，请使用 Exchange 2010 连接到 Microsoft 365 并迁移邮箱。 接下来，将 Exchange 2010 迁移到 Exchange 2016，并取消所有剩余的 Exchange 2010 服务器。
>- 如果您未完成邮箱迁移和本地服务器升级（10月13日，2020），请先将本地 Exchange 2010 服务器升级到 Exchange 2016。 然后，使用 Exchange 2016 连接到 Microsoft 365 并迁移邮箱。

> [!NOTE]
> 稍微复杂一些，但还可以将邮箱迁移到 Microsoft 365，同时将您的本地 Exchange 2010 服务器迁移到 Exchange 2016。

若要避免停止对 Exchange Server 2010 的支持，可以采用三种途径。

![Exchange Server 2010 升级路径](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

以下各节更详细地探讨了每个选项。

## <a name="migrate-to-microsoft-365"></a>迁移到 Microsoft 365

将电子邮件迁移到 Microsoft 365 是帮助您停用 Exchange 2010 部署的最佳和最简单的选项。 通过迁移到 Microsoft 365，你可以从旧技术到当前功能的单个跃点，包括：

- 合规性功能，如保留策略、In-Place 和诉讼保留、就地电子数据展示等。
- Microsoft Teams。
- Power BI。
- 重点收件箱。
- MyAnalytics.

Microsoft 365 还会先获取新的功能和体验，以便你的组织可以立即开始使用它们。 此外，您无需担心：

- 购买和维护硬件。
- 支付热量和冷却您的服务器。
- 及时了解安全性、产品和时区的修补程序。
- 维护存储和软件以支持合规性要求。
- 升级到新版本的 Exchange。 你始终处于 Microsoft 365 中的最新版本的 Exchange。

### <a name="how-should-i-migrate-to-microsoft-365"></a>我应该如何迁移到 Microsoft 365？

根据您的组织，有几个选项可用于获取 Microsoft 365。 首先，需要考虑几个因素，例如：
- 需要移动的座位或邮箱的数量。
- 你希望迁移持续多长时间。
- 迁移过程中是否需要在您的本地安装和 Microsoft 365 之间实现无缝集成。
 
此表显示了您的迁移选项以及确定要使用哪种方法的最重要的因素。

|迁移选项|组织大小|持续时间|
|---|---|---|
|直接转换迁移|座位数少于150|一周或更少|
|最小混合迁移|座位数少于150|几个星期或更少|
|完全混合迁移|超过150的座位|几周或更多|

以下各节提供了这些方法的概述。 有关详细信息，请参阅 [确定迁移路径](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。

### <a name="cutover-migration"></a>直接转换迁移

在直接转换迁移中，将所有邮箱、通讯组、联系人等迁移到 Office 365 时设置的日期和时间。 完成后，请关闭本地 Exchange 服务器，并以独占方式开始使用 Microsoft 365。

转换迁移对于没有许多邮箱的小型组织非常有用，希望快速访问 Microsoft 365，并且不希望处理其他方法的复杂性。 但应在一周或更短时间内完成。 并要求用户重新配置其 Outlook 配置文件。 直接转换迁移最多可迁移2000个邮箱，但我们建议您最多使用150个邮箱。 如果你尝试迁移更多的，则可以在你的截止时间之后停止转移所有邮箱，IT 支持人员可能会遇到请求，以帮助用户重新配置 Outlook。

以下是有关直接转换迁移的注意事项：

- Microsoft 365 将需要通过 TCP 端口443使用 Outlook Anywhere 连接到您的 Exchange 2010 服务器。
- 所有内部部署邮箱都将移至 Microsoft 365。
- 您需要具有对用户邮箱具有读取访问权限的本地管理员帐户。
- 要在 Microsoft 365 中使用的 Exchange 2010 接受的域需要添加为服务中的已验证域。
- 在开始迁移的时间和开始完成阶段的过程中，Microsoft 365 将定期同步 Microsoft 365 和本地邮箱。 这样，你就可以完成迁移，而无需担心你的内部部署邮箱中留下的电子邮件。
- 用户将收到其 Microsoft 365 帐户的新临时密码。 他们将需要在用户首次登录邮箱时对其进行更改。
- 你将需要一个 Microsoft 365 许可证，其中包含你迁移的每个用户邮箱的 Exchange Online。
- 用户需要在各自的每台设备上设置一个新的 Outlook 配置文件，并再次下载他们的电子邮件。 Outlook 将下载的电子邮件数量可能有所不同。 有关详细信息，请参阅 [在 Outlook 中脱机工作](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)。

若要了解有关直接转换迁移的详细信息，请参阅：

- [关于直接转换电子邮件迁移，您需要了解的内容](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [执行电子邮件到 Office 365 的直接转换迁移](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>最小混合迁移

在最小混合或快速迁移中，你可以在几周内将几百个邮箱移动到 Microsoft 365。 此方法不支持高级混合迁移功能，如共享的忙/闲日历信息。

最小混合迁移对于需要花费更多时间将其邮箱迁移到 Microsoft 365 的组织非常有用，但仍计划在几个星期内完成迁移。 您将获得更高级的 *完全混合迁移* 的一些优势，而不会带来很多复杂性。 您可以控制在给定时间要迁移的邮箱数和邮箱数。 将使用本地帐户的用户名和密码创建 Microsoft 365 邮箱。 与直接转换迁移不同，用户不需要重新创建其 Outlook 配置文件。

以下是有关最小混合迁移的注意事项：

- 你需要在内部部署 Active Directory 服务器和 Microsoft 365 之间执行一次性目录同步。
- 用户将能够使用与邮箱相同的用户名和密码登录到其 Microsoft 365 邮箱。
- 你将需要一个 Microsoft 365 许可证，其中包含你迁移的每个用户邮箱的 Exchange Online。
- 用户无需在大多数设备上设置新的 Outlook 配置文件，尽管一些较旧的 Android 手机可能需要新的配置文件。 用户不需要 redownload 他们的电子邮件。

有关详细信息，请参阅 [使用最少混合将 Exchange 邮箱快速迁移到 Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)。

### <a name="full-hybrid"></a>完全混合

在完全混合迁移中，您有多个数百个、多达数万个邮箱，并且将部分或全部移动到 Microsoft 365。 由于这些迁移的时间通常较长，混合迁移使其能够：

- 向本地用户显示 Microsoft 365 中用户的忙/闲日历信息，反之亦然。
- 请参阅包含内部部署和 Microsoft 365 中的收件人的统一全局地址列表。
- 查看所有用户的完整 Outlook 收件人属性，而不管他们是在本地还是在 Microsoft 365 中。
- 使用 TLS 和证书在本地 Exchange 服务器和 Office 365 之间进行安全的电子邮件通信。
- 将在内部部署 Exchange 服务器和 Microsoft 365 之间发送的邮件视为内部邮件，使其能够：
  - 由传输和合规性代理对内部邮件进行正确评估和处理。
  - 绕过反垃圾邮件筛选器。

完全混合迁移最适用于希望在多个月或更多个月内保持混合配置的组织。 您将获得本部分前面列出的功能，以及目录同步、更好的集成合规性功能，以及使用在线邮箱移动将邮箱移动到 Microsoft 365 的能力。 Microsoft 365 成为本地组织的扩展。

关于完全混合迁移，要考虑的事项：

- 它们并不适合所有组织。 由于完全混合迁移的复杂性，少于几百个邮箱的组织通常不会看到证明所涉及的工作量和成本的好处。 在这种情况下，我们建议您改用直接转换或最少的混合迁移。
- 您需要使用 Azure Active Directory (Azure AD) 在本地 Active Directory 服务器和 Microsoft 365 之间建立目录同步。
- 用户将能够使用与登录到本地网络时相同的用户名和密码登录到他们的 Microsoft 365 邮箱。  (此功能需要使用密码同步和/或 Active Directory 联合身份验证服务的 Azure AD 连接) 。
- 您需要一个 Microsoft 365 许可证，其中包括您迁移的每个用户邮箱的 Exchange Online。
- 用户无需在大多数设备上设置新的 Outlook 配置文件，但某些旧的 Android 手机可能需要新的配置文件。 用户不需要 redownload 他们的电子邮件。

> [!IMPORTANT]
> 如果您的组织选择将邮箱迁移到 Microsoft 365，但计划保留 DirSync 或 Azure AD Connect 以继续从本地 Active Directory 中管理用户帐户，则需要在本地至少保留一台 Exchange server。 如果删除了所有 Exchange 服务器，将无法更改 exchange Online 中的 Exchange 收件人。 这是因为颁发机构的来源仍保留在本地 Active Directory 中，需要进行更改。

如果完整的混合迁移听起来非常适合您，请参阅以下有用的资源：

- [Exchange 部署助理](https://aka.ms/exdeploy)
- [Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)
- [混合配置向导](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [混合配置向导常见问题解答](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [混合部署先决条件](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>升级到本地 Exchange Server 的较新版本

我们强烈认为，可以通过完全迁移到 Microsoft 365 来获得最佳价值和用户体验。 但我们知道，某些组织需要在本地保留一些 Exchange 服务器。 这可能是因为管理法规要求，以确保数据不会存储在外部数据中心中，因为您具有无法在云中满足的独特的设置或要求，或者因为您仍在本地使用 Active Directory 而需要 Exchange 来管理云邮箱。 在任何情况下，如果您保留 Exchange 本地，则应确保将 Exchange 2010 环境升级到至少 Exchange 2013 或 Exchange 2016。

为了获得最佳体验，我们建议您将其余的本地环境升级到 Exchange 2016。 如果要直接从 Exchange Server 2010 转到 Exchange Server 2016，则无需安装 Exchange Server 2013。

Exchange 2016 包含早期版本的 Exchange 的所有功能。 它与 Microsoft 365 提供的体验最为匹配，但某些功能仅在 Microsoft 365 中可用。 请查看你缺少的几个内容：

|Exchange 发布|功能|
|---|---|
|**Exchange 2013**|简化的体系结构可将服务器角色的数量减少到三个 (邮箱、客户端访问和边缘传输) |
||数据丢失防护策略 (DLP) ，可帮助防止敏感信息泄露|
||改进的 Outlook Web App 体验|
|**Exchange 2016**|*Exchange 2013 中的功能和 .。。*|
||将服务器角色进一步简化为仅限邮箱和边缘传输|
||改进了 DLP 以及与 SharePoint 的集成|
||改进的数据库恢复能力|
||在线文档协作|

|注意事项|更多信息|
|---|---|
|支持日期结束|与 Exchange 2010 一样，每个 Exchange 版本都有自己的支持结束日期：<br/><br/>Exchange 2013-4 月2023<br/>Exchange 2016-10 月2025<br/><br/>较早的支持结束日期，您将更快地执行另一个迁移。 4月2023比你想像的要大得多！|
|迁移到 Exchange 2013 或2016的路径|无论您选择 Exchange 2013 还是 Exchange 2016，从 Exchange 2010 到较新版本的迁移路径都是相同的：<br/><br/>将 Exchange 2013 或2016安装到现有的 Exchange 2010 组织中。<br/>将服务和其他基础结构移到 Exchange 2013 或2016。<br/>将邮箱和公用文件夹移动到 Exchange 2013 或2016停止剩余 Exchange 2010 服务器。|
|版本共存|迁移到 Exchange 2013 或 Exchange 2016 时，您可以将其中一个版本安装到现有的 Exchange 2010 组织中。 这使您可以安装一个或多个 Exchange 2013 或 Exchange 2016 服务器并执行迁移。|
|服务器硬件|服务器硬件要求已从 Exchange 2010 更改。 请确保硬件兼容。 请在此处查找有关每个版本的硬件要求的详细信息：<br/><br/>[Exchange 2016 系统要求](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Exchange 2013 系统要求](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>随着 Exchange 性能的显著改进以及较新的服务器中计算的计算能力和存储容量的增加，您可能需要较少的服务器来支持相同数量的邮箱。|
|操作系统版本|每个版本支持的最低操作系统版本为：<br/><br/>Exchange 2016-Windows Server 2012<br/>Exchange 2013-Windows Server 2008 R2 SP1<br/><br/>您可以在 Exchange 可支持性 [矩阵](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)中找到有关操作系统支持的详细信息。|
|Active Directory 林功能级别|每个版本支持的最小 Active Directory 林功能级别为：<br/><br/>Exchange 2016-Windows Server 2008 R2 SP1<br/>Exchange 2013-Windows Server 2003<br/><br/>可以在 [Exchange 可支持性矩阵](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)中找到有关林功能级别支持的详细信息。|
|Office 客户端版本|每个版本的受支持的 Office 客户端版本最低为：<br/><br/>Exchange 2016-Office 2010 (并提供最新的更新) <br/>Exchange 2013-Office 2007 SP3<br/><br/>有关 Office 客户端支持的详细信息，请参阅 Exchange 可支持性 [矩阵](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)。||| 


使用以下资源可帮助您进行迁移：

- [Exchange 部署助理](https://aka.ms/exdeploy)
- Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016)、 [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)的 Active Directory 架构更改
- Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016)、 [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)的系统要求
- Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016)、 [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)的先决条件

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 客户端和服务器以及 Windows 7 的选项的摘要

有关 Office 2010 客户端和服务器以及 Windows 7 的升级、迁移和移动到云选项的直观摘要，请参阅[终止支持海报](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![对 Office 2010 客户端和服务器和 Windows 7 海报的支持结束](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

本页面海报说明了在 Microsoft 365 企业版中突出显示了对 Office 2010 客户端和服务器产品和 Windows 7 的响应停止的各种途径，并突出显示了 Microsoft 企业版中的首选路径和选项支持。

您还可以 [下载](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 此海报并在信件、法律或 tabloid (11 x 17) 格式打印它。

## <a name="what-if-i-need-help"></a>如果我需要帮助，该怎么办？

如果你正在迁移到 Microsoft 365，你可能有资格使用我们的 Microsoft FastTrack 服务。 FastTrack 提供了最佳实践、工具和资源，使您能够以尽可能顺畅的方式迁移到 Microsoft 365。 最好的是，支持工程师将引导您完成规划和设计以迁移您的最后一个邮箱。 有关 FastTrack 的详细信息，请参阅 [Microsoft FastTrack](https://fasttrack.microsoft.com/)。

如果在迁移到 Microsoft 365 的过程中遇到问题，并且您不使用 FastTrack，或者您正在迁移到较新版本的 Exchange Server，则可以使用以下资源：

- [技术社区](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [客户支持](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>相关文章

[帮助从 Office 2010 服务器和客户端升级的相关资源](upgrade-from-office-2010-servers-and-products.md)
