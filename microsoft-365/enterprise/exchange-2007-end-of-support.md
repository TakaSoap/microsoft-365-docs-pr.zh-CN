---
title: Exchange 2007 停止提供支持路线图
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 了解 2007 Exchange Server终止支持后的选项，并开始计划迁移到 Microsoft 365、Office 365 或 Exchange 2016。
ms.openlocfilehash: 8aecc835fbdde21f6651946acd15c4c70788b3da
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824391"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 停止提供支持路线图

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

2007 Exchange Server于2017年4月终止支持。 如果尚未从 2007 Exchange开始迁移到 Microsoft 365、Office 365 或 2016 Exchange，现在是时候开始规划了。

## <a name="what-does-end-of-support-mean"></a>*终止支持* 意味着什么？

与几乎所有 Microsoft 产品一样，Exchange Server具有支持生命周期，在此期间我们提供新功能、bug 修复、安全修复等。 此生命周期通常从产品的初始版本持续 10 年。 此生命周期的结束称为产品的终止支持。 自 2007 Exchange于 2017 年 4 月 11 日终止支持以来，Microsoft 不再提供：

- 对可能发生的问题的技术支持。

- 针对可能影响服务器稳定性和可用性的问题的 Bug 修复。

- 针对可能使服务器易受安全漏洞影响的漏洞的安全修复。

- 时区更新。

Exchange 2007 的安装将在支持结束日期后继续运行。 但是，由于没有新的更新或支持，我们强烈建议你尽快从 Exchange 2007 迁移。

有关即将终止支持Office 2007 服务器的详细信息，请参阅[从 Office 2007 服务器和产品规划升级](upgrade-from-office-2007-servers-and-products.md)。

## <a name="what-are-my-options"></a>我的选项是什么？

可以执行下列操作：

- 使用直接迁移、分阶段迁移或混合迁移迁移到Microsoft 365。

- 将Exchange 2007 服务器迁移到本地服务器上较新版本的Exchange。

以下部分更详细地探讨了每个选项。

### <a name="migrate-to-microsoft-365"></a>迁移到 Microsoft 365

将电子邮件迁移到Microsoft 365是帮助停用 Exchange 2007 部署的最佳和最简单的选项。 迁移到Microsoft 365后，可以从 10 年前的技术到最先进的功能进行单一跃点，包括：

- 合规性功能，如保留策略、In-Place和诉讼保留、就地电子数据展示等

- Microsoft 365 组

- 重点收件箱

- MyAnalytics

- 用于以编程方式访问电子邮件、日历、联系人等的 REST API

Microsoft 365还首先获取新功能和体验，因此你和你的用户通常可以立即开始使用它们。 你不必担心：

- 购买和维护硬件。

- 支付加热和冷却你的服务器。

- 在安全性、产品和时区修复方面保持最新。

- 维护存储和软件以支持合规性要求。

- 升级到新版本的Exchange。 使用Microsoft 365，始终使用最新版本的Exchange。

#### <a name="how-should-i-migrate-to-microsoft-365"></a>如何迁移到Microsoft 365？

有一些迁移选项。 需要考虑一些事项，包括：

- 需要移动的座位或邮箱数。
- 希望迁移持续多久。
- 迁移期间是否需要在本地安装与Microsoft 365之间无缝集成。

下表显示了迁移选项以及确定要使用哪种方法的最重要因素：

|迁移选项|组织大小|期限|
|---|---|---|
|直接转换迁移|少于 150 个座位|一周或更短的时间|
|暂存迁移|超过 150 个座位|几周|
|完全混合迁移|数百到数千个座位|几个月或更短的时间|

以下部分概述了这些方法。 有关详细信息，请参阅 [“确定迁移路径](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)”。

#### <a name="cutover-migration"></a>直接转换迁移

在转换迁移中，将所有邮箱、通讯组、联系人等迁移到预选日期和时间Microsoft 365。 迁移完成后，请关闭本地Exchange服务器，并开始专门使用Microsoft 365。

直接转换迁移非常适合没有多个邮箱、希望快速Microsoft 365且不想处理其他方法的一些复杂性的小组织。 但是，它应在一周或更短的时间内完成，并且需要用户重新配置其Outlook配置文件。 直接迁移最多可以处理 2，000 个邮箱，但我们强烈建议使用它来迁移最多 150 个邮箱。 如果尝试迁移更多内容，则在截止时间之前传输所有邮箱的时间可能会过多，而 IT 支持人员可能会因为请求帮助用户重新配置Outlook而不知所措。

如果正在考虑执行直接迁移，请考虑以下事项：

- Microsoft 365需要通过 TCP 端口 443 使用Outlook任意位置连接到 Exchange 2007 服务器。

- 所有本地邮箱都将移至Microsoft 365。

- 需要具有对用户邮箱的读取访问权限的本地管理员帐户。

- 要在Microsoft 365中使用的 Exchange 2007 接受域需要添加为服务中的已验证域。

- 从开始迁移到开始完成阶段，Microsoft 365将定期同步Microsoft 365和本地邮箱。 这使你能够完成迁移，而无需担心在本地邮箱中留下电子邮件。

- 用户将收到其Microsoft 365帐户的新临时密码。 他们第一次登录到邮箱时需要更改密码。

- 需要一个Microsoft 365许可证，其中包括迁移的每个用户邮箱的Exchange Online。

- 用户需要在其每个设备上设置新的Outlook配置文件，然后再次下载其电子邮件。 Outlook下载的电子邮件量可能会有所不同。 有关详细信息，请 [参阅更改要保持脱机的邮件量](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。

有关直接迁移的详细信息，请参阅：

- [有关直接转换电子邮件迁移需要了解的内容](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)

- [执行电子邮件的转换迁移](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)

#### <a name="staged-migration"></a>暂存迁移

在分阶段迁移中，有几百或几千个要迁移到Microsoft 365的邮箱，需要一周或更多的时间才能完成迁移，并且不需要任何高级混合迁移功能，例如共享的“忙/忙”日历信息。

分阶段迁移非常适合需要花费更多时间将邮箱迁移到Microsoft 365但仍计划在几周内完成迁移的组织。 可以分批迁移邮箱。 你可以控制在给定时间迁移的邮箱数和邮箱数。 例如，可以对同一部门中的用户批处理邮箱，以确保它们同时移动。 或者，你可以将执行邮箱保留到最后一批。 与直接迁移一样，用户需要重新创建其Outlook配置文件。

如果正在考虑执行分阶段迁移，请考虑以下事项：

- Microsoft 365需要通过 TCP 端口 443 使用Outlook任意位置连接到 Exchange 2007 服务器。

- 需要具有对用户邮箱的读取访问权限的本地管理员帐户。

- Microsoft 365中计划使用的 Exchange 2007 接受域需要添加为服务中的已验证域。

- 需要创建一个 CSV 文件，其中包含计划批处理中迁移的每个邮箱的全名和电子邮件地址。 还需要为要迁移的每个邮箱包含一个新密码，并将该密码发送给每个用户。 第一次登录到新Microsoft 365邮箱时，系统会提示用户更改密码。

- 从开始迁移批处理到开始完成阶段，Microsoft 365将定期同步批处理中包含的Microsoft 365和本地邮箱。 这使你能够完成迁移，而无需担心在本地邮箱中留下电子邮件。

- 需要一个Microsoft 365许可证，其中包括迁移的每个用户邮箱的Exchange Online。

- 用户需要在其每个设备上设置新的Outlook配置文件，然后再次下载其电子邮件。 Outlook下载的电子邮件量可能会有所不同。 有关详细信息，请 [参阅更改要保持脱机的邮件量](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。

有关分阶段迁移的详细信息，请参阅：

- [有关分阶段电子邮件迁移需要了解的内容](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)

- [执行电子邮件的分阶段迁移](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)

#### <a name="full-hybrid"></a>完全混合

在完全混合迁移中，你的组织拥有数百个（最多数万个）邮箱，你希望将部分或全部邮箱移动到Microsoft 365。 由于这些迁移通常是较长期的，因此混合迁移使以下操作成为可能：

- 向本地用户显示Microsoft 365用户的忙/忙日历信息，反之亦然。

- 请参阅统一的全局地址列表，其中包含本地和Microsoft 365中的收件人。

- 查看所有用户的完整Outlook收件人属性，无论他们是在本地还是在Microsoft 365。

- 使用 TLS 和证书保护本地Exchange服务器与Microsoft 365之间的电子邮件通信。

- 将本地Exchange服务器和Microsoft 365之间发送的消息视为内部消息，使其能够：

  - 由针对内部消息的传输和合规性代理正确评估和处理。

  - 绕过反垃圾邮件筛选器。

完全混合迁移最适合希望在混合配置中保留数月或更久的组织。 你将获取本部分前面列出的功能，以及目录同步、更好的集成合规性功能，以及使用联机邮箱移动将邮箱移入和移出Microsoft 365的能力。 Microsoft 365成为本地组织的扩展。

如果正在考虑执行完全混合迁移，请考虑以下事项：

- 完全混合迁移不适用于所有类型的组织。 由于完全混合迁移的复杂性，邮箱少于几百个的组织通常不会看到一些好处来证明设置邮箱所需的努力和成本是合理的。 如果这听起来像你的组织，我们建议你考虑进行直接迁移或分阶段迁移。

- 需要在 Exchange 2007 组织中部署至少一台 Exchange 2013 服务器才能充当“混合服务器”。 此服务器将代表Exchange 2007 服务器与Microsoft 365进行通信。

- Microsoft 365需要使用 TCP 端口 443 上的任意位置Outlook连接到“混合服务器”。

- 需要使用本地 Active Directory服务器和Microsoft 365之间的Azure Active Directory (Azure AD) 连接设置目录同步。

- 用户将能够使用与登录本地网络时相同的用户名和密码登录到其Microsoft 365邮箱。  (此功能需要Azure AD 连接密码同步和/或Active Directory 联合身份验证服务.) 

- 需要一个Microsoft 365许可证，其中包括迁移的每个用户邮箱的Exchange Online。

- 用户无需在其大多数设备上设置新的Outlook配置文件，尽管一些较旧的 Android 手机可能需要新的配置文件。 用户无需重新卸载其电子邮件。

如果完全混合迁移听起来适合你，请参阅以下资源来帮助迁移：

- [Exchange部署助手](/exchange/exchange-deployment-assistant)

- [Exchange Server 混合部署](/exchange/exchange-hybrid)

- [混合配置向导](/exchange/hybrid-configuration-wizard)

- [混合配置向导常见问题解答](/exchange/hybrid-configuration-wizard-faqs)

- [混合部署先决条件](/exchange/hybrid-deployment-prerequisites)

### <a name="migrate-to-a-newer-version-of-exchange-server"></a>迁移到较新版本的Exchange Server

我们坚信，可以通过迁移到Microsoft 365来实现最佳价值和用户体验。 但我们也明白，某些组织需要将电子邮件保留在本地。 这可能是因为法规要求，为了保证数据不会存储在另一个国家/地区的数据中心或类似国家/地区。 如果选择将电子邮件保留在本地，可以将Exchange 2007 环境迁移到 2010 年Exchange、2013 Exchange或 2016 Exchange。

如果无法迁移到Microsoft 365，建议迁移到 2016 Exchange。 Exchange 2016 包括以前版本的Exchange的所有功能。 它还与Microsoft 365提供的体验最为匹配，尽管某些功能仅在Microsoft 365中可用。 查看你缺少的一些内容：

|Exchange版本|功能|
|---|---|
|Exchange 2010| Role-Based 访问控制 (没有 ACL 的权限)  <br/> Outlook Web App 邮箱策略 <br/> 能够在组织之间共享闲/忙和委托日历|
|Exchange 2013| *Exchange 2010 和...* <br/> 简化了将服务器角色数减少到三个 (邮箱、客户端访问、边缘传输)  <br/> 有助于防止敏感信息泄漏的 DLP)  (数据丢失防护策略 <br/> 改进了Outlook Web App体验|
|Exchange 2016| *Exchange 2013 和...* <br/> 进一步简化了仅用于邮箱和边缘传输的服务器角色 <br/> 改进了 DLP 以及与 SharePoint 的集成 <br/> 改进了数据库复原能力 <br/> 联机文档协作|

#### <a name="which-version-should-i-migrate-to"></a>应迁移到哪个版本？

我们建议最初假设你将迁移到 2016 Exchange。 然后，使用以下信息来确认你的假设或排除 2016 Exchange。 如果出于某种原因无法迁移到 Exchange 2016，请使用 Exchange 2013 等执行相同的过程。

|注意事项|更多信息|
|---|---|
|支持日期结束| 与 Exchange 2007 一样，每个版本的Exchange都有其自己的支持终止日期： <br/> *Exchange 2010* - 2020 年 1 月 <br/> *Exchange 2013 - 2023* 年 4 月 <br/> *Exchange 2016 - 2025 年 10* 月 <br/> 支持结束得越早，你越早需要执行另一个迁移。|
|Exchange 2010 和 2013 的迁移路径。|下面是迁移到 Exchange 2010 或 2013 Exchange的常规阶段： <br/> - 将 Exchange 2010 或 2013 安装到现有的 Exchange 2007 组织中。 <br/>- 将服务和其他基础结构移至 2010 或 2013 Exchange。<br/>- 将邮箱和公用文件夹移到 2010 或 2013 Exchange。<br/>- 解除剩余Exchange 2007 服务器的授权。|
|2016 Exchange迁移路径|下面是迁移到 2016 Exchange的常规阶段： <br/> - 将 Exchange 2013 安装到现有的 Exchange 2007 组织中。<br/>- 将服务和其他基础结构移到 2013 Exchange。<br/>- 将邮箱和公用文件夹移到 2013 Exchange。<br/>- 解除剩余Exchange 2007 服务器的授权。<br/>- 将 Exchange 2016 安装到现有的 Exchange 2013 组织中。<br/>- 将邮箱、公用文件夹、服务和其他基础结构移动到 2016 Exchange (顺序并不重要) 。 解除剩余Exchange 2013 服务器的授权。<br/><br/> **注意：** 从 Exchange 2013 迁移到 2016 Exchange很简单。 这两个版本的硬件要求几乎相同，并且这些版本非常兼容。 因此，可以重新生成为 Exchange 2013 购买的服务器，并在该服务器上安装 Exchange 2016。 对于联机邮箱移动，大多数用户甚至不会注意到他们的邮箱已从服务器上移开，然后在使用 2016 Exchange重新生成后返回。|
|版本共存| 迁移到... <br/> **Exchange 2016：** Exchange 2016 无法安装在包含 Exchange 2007 服务器的组织中。 首先需要迁移到 Exchange 2010 或 2013 (我们强烈建议Exchange 2013) ，删除所有Exchange 2007 服务器，然后迁移到 2016 Exchange。 <br/> **Exchange 2010 或 Exchange 2013：可以将 2010** Exchange或 2013 Exchange安装到现有的 Exchange 2007 组织中。 这使你能够安装一个或多个Exchange 2010 或 2013 服务器并执行迁移。|
|服务器硬件| 服务器硬件要求已从 2007 Exchange更改。 确保硬件兼容。 有关详细信息，请参阅： <br/> [Exchange 2016 年系统要求](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 年系统要求](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 年系统要求](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/> 你会发现，Exchange性能的重大改进，以及较新服务器中计算能力和存储容量的增加，意味着可能需要更少的服务器来支持相同数量的邮箱。|
|操作系统版本| 每个版本支持的最低操作系统版本为： <br/> **Exchange 2016** - Windows Server 2012 <br/> **Exchange 2013** - Windows服务器 2008 R2 SP1 <br/> **Exchange 2010** - Windows服务器 2008 SP2 <br/> 在[Exchange可支持性矩阵](/Exchange/plan-and-deploy/supportability-matrix)中查找有关操作系统支持的详细信息。|
|Active Directory 林功能级别| 每个版本的最小受支持的 Active Directory 林功能级别为： <br/> **Exchange 2016** Windows服务器 2008 R2 SP1 <br/> **Exchange 2013** Windows服务器 2003 <br/> **Exchange 2010** Windows Server 2003 <br/> 在[Exchange可支持性矩阵](/Exchange/plan-and-deploy/supportability-matrix)中查找有关林功能级别支持的详细信息。|
|Office客户端版本| 每个版本的最小受支持的Office客户端版本为： <br/> **Exchange 2016** - Office 2010 (最新更新)  <br/> **Exchange 2013** - Office 2007 SP3 <br/> **Exchange 2010** - Office 2003 <br/> 在Exchange[可支持性矩阵](/Exchange/plan-and-deploy/supportability-matrix)中查找有关Office客户端支持的详细信息。|

#### <a name="how-do-i-migrate"></a>如何实现迁移？

如果决定将电子邮件保留在本地，请使用以下资源来帮助迁移：

- [Exchange部署助手](/exchange/exchange-deployment-assistant)

- [Exchange 2016、2013](/Exchange/plan-and-deploy/active-directory/ad-schema-changes)、[2010](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help) 的 Active Directory 架构更改 [](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)

- [2016、2013、2010](/Exchange/plan-and-deploy/system-requirements) Exchange的系统要求 [](/exchange/exchange-2013-system-requirements-exchange-2013-help)[](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))

- [2016、2013、2010](/Exchange/plan-and-deploy/prerequisites) Exchange先决条件 [](/exchange/exchange-2013-prerequisites-exchange-2013-help)[](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))

## <a name="get-help"></a>获取帮助

如果要迁移到Microsoft 365，则可能有资格使用我们的Microsoft FastTrack服务。 FastTrack提供了最佳做法、工具和资源，使迁移到Microsoft 365尽可能无缝。 最重要的是，支持工程师将引导你完成迁移，从规划和设计到迁移最后一个邮箱。 有关FastTrack的详细信息，请[参阅Microsoft FastTrack](https://fasttrack.microsoft.com/)。

如果在迁移到Microsoft 365期间遇到问题，但未使用FastTrack或迁移到较新版本的Exchange Server，我们来提供帮助。 下面是一些可以使用的资源：

- [技术社区](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)

- [客户支持](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>相关主题

[有助于升级 Office 2007 服务器和客户端的资源](upgrade-from-office-2007-servers-and-products.md)
