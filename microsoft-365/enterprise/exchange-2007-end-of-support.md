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
description: 了解在 2007 Exchange Server后的选项，并开始规划迁移到 Microsoft 365、Office 365 或 Exchange 2016。
ms.openlocfilehash: d5e79666c0e8e9804a63c89a0095a8725f14cd35
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178775"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 停止提供支持路线图

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Exchange Server 2007 年 4 月终止支持。 如果您尚未开始从 Exchange 2007 迁移到 Microsoft 365、Office 365 或 Exchange 2016，那么现在该开始规划了。
  
## <a name="what-does-end-of-support-mean"></a>停止 *提供支持意味着什么* ？

Exchange Server几乎所有 Microsoft 产品一样，我们提供了一个支持生命周期，在此期间我们提供新功能、Bug 修复、安全修补程序等。 此生命周期通常自产品初始版本起持续 10 年。 此生命周期的结束称为产品的停止支持。 自 2007 Exchange 2017 年 4 月 11 日终止支持以来，Microsoft 不再提供：
  
- 针对可能会出现的问题的技术支持。
    
- 对可能会影响服务器稳定性和可用性的问题进行 Bug 修复。
    
- 针对可能导致服务器易受安全漏洞的漏洞进行安全修复。
    
- 时区更新。
    
2007 Exchange 2007 的安装将在支持结束日期后继续运行。 但由于没有新的更新或支持，我们强烈建议您尽快从 Exchange 2007 迁移。
  
有关即将Office 2007 服务器的信息，请参阅 Plan [your upgrade from Office 2007 servers and products。](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>我的选项是什么？

可以执行下列操作：
  
- 通过使用Microsoft 365迁移、分步迁移或混合迁移迁移到客户端。
    
- 将 Exchange 2007 服务器迁移到本地Exchange更高版本的客户端。
    
以下各节更详细地探讨每个选项。
  
### <a name="migrate-to-microsoft-365"></a>迁移到 Microsoft 365

将电子邮件迁移到 Microsoft 365是帮助停用 2007 年 2007 年 Exchange最佳且最简单的选项。 通过迁移到 Microsoft 365，你可以从 10 年技术到最现代功能进行单个跃点，包括：
  
- 合规性功能，如保留策略In-Place和诉讼保留、就地电子数据展示等
    
- Microsoft 365 组
    
- 重点收件箱
    
- MyAnalytics
    
- REST API，用于以编程方式访问电子邮件、日历、联系人等
    
Microsoft 365还首先获取新功能和体验，因此你和用户通常可以立即开始使用它们。 你无需担心：
  
- 购买和维护硬件。
    
- 支付热和冷服务器费用。
    
- 保持最新的安全、产品和时区修补程序。
    
- 维护存储和软件以支持合规性要求。
    
- 升级到新版本的 Exchange。 使用 Microsoft 365，你始终可以使用最新版本的 Exchange。
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>如何迁移到Microsoft 365？

有一些迁移选项。 需要考虑一些方面，包括：

- 需要移动的席位或邮箱数。
- 希望迁移持续多久。
- 在迁移过程中，您是否需要在内部部署安装和Microsoft 365无缝集成。

此表显示了迁移选项以及决定使用哪种方法的最重要的因素：
  

|**迁移选项**|**组织规模**|**Duration**|
|:-----|:-----|:-----|
|直接转换迁移  <br/> |少于 150 个席位  <br/> |一周或更少  <br/> |
|暂存迁移  <br/> |多于 150 个席位  <br/> |几周  <br/> |
|完全混合迁移  <br/> |几百到数千个座位  <br/> |几个月或更久  <br/> |
   
以下各节概述了这些方法。 有关详细信息，请参阅 [确定迁移路径](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。 
  
#### <a name="cutover-migration"></a>直接转换迁移

在直接转换迁移中，将迁移所有邮箱、通讯组、联系人等，Microsoft 365预先选择日期和时间进行迁移。 迁移完成后，您将关闭内部部署Exchange服务器，并开始以独占Microsoft 365服务器。
  
对于没有很多邮箱、希望快速访问 Microsoft 365 并且不想处理其他方法的一些复杂情况的小组织来说，转换迁移是很好的选择。 但是，应在一周或更少时间完成，并且要求用户重新配置其Outlook配置文件。 虽然转换迁移最多可处理 2，000 个邮箱，但我们强烈建议使用它迁移最多 150 个邮箱。 如果尝试迁移更多邮箱，在截止时间之前转移所有邮箱的时间可能用完，并且 IT 支持人员可能会因请求帮助用户重新配置邮箱而Outlook。
  
如果您正在考虑执行转换迁移，请考虑以下操作：
  
- Microsoft 365 TCP 端口 443 Outlook Anywhere 连接到 Exchange 2007 服务器。
    
- 所有内部部署邮箱都将移动到Microsoft 365。
    
- 您需要具有用户邮箱的读取访问权限的本地管理员帐户。
    
- 要Exchange的 2007 接受的域Microsoft 365需要添加为服务中的已验证域。
    
- 从开始迁移到开始完成阶段之间，Microsoft 365将定期同步Microsoft 365和内部部署邮箱。 这样，您即可完成迁移，而无需担心电子邮件会遗留在本地邮箱中。
    
- 用户将收到其帐户的新临时Microsoft 365密码。 第一次登录邮箱时，需要更改密码。
    
- 您需要一个Microsoft 365许可证，其中包含Exchange Online迁移的每个用户邮箱的邮箱。
    
- 用户需要在每个设备上设置新的Outlook配置文件，并再次下载他们的电子邮件。 要下载的电子邮件Outlook可能会有所不同。 有关详细信息，请参阅更改 [脱机邮件的保留时间](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
有关转换迁移详细信息，请参阅：
  
- [有关转换电子邮件迁移的需知信息](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [执行电子邮件的切换迁移](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>暂存迁移

在分步迁移中，您具有几百个或几千个要迁移到 Microsoft 365 的邮箱，需要一周或一周以上的时间才能完成迁移，并且不需要任何高级混合迁移功能（如共享忙/闲日历信息）。
  
对于需要花更多时间来将邮箱迁移到 Microsoft 365但仍计划在几周内完成迁移的组织，分步迁移非常适合。 可以分批迁移邮箱。 您可以控制在给定时间迁移的邮箱数和邮箱数。 例如，您可以对同一部门中的用户邮箱进行批处理，以确保它们全部同时移动。 或者，您可能将执行邮箱保留到最后一批。 与使用转换迁移一样，用户需要重新创建其Outlook配置文件。
  
如果您正在考虑执行分步迁移，请考虑以下操作：
  
- Microsoft 365 TCP 端口 443 上的 Exchange Anywhere 连接到 Outlook 2007 服务器。
    
- 您需要具有用户邮箱的读取访问权限的本地管理员帐户。
    
- 计划Exchange 2007 接受的域的域Microsoft 365需要添加为服务中的已验证域。
    
- 您需要创建一个 CSV 文件，该文件包含计划分批迁移的每个邮箱的全名和电子邮件地址。 您还需要包含要迁移的每个邮箱的新密码，并将该密码发送给每个用户。 用户首次登录新邮箱时，系统将提示Microsoft 365密码。
    
- 在启动迁移批处理到开始完成阶段之间，Microsoft 365将定期同步批处理Microsoft 365邮箱和内部部署邮箱。 这样，您即可完成迁移，而无需担心电子邮件会遗留在本地邮箱中。
    
- 您需要一个Microsoft 365许可证，其中包含Exchange Online迁移的每个用户邮箱的邮箱。
    
- 用户需要在每个设备上设置新的Outlook配置文件，并再次下载他们的电子邮件。 要下载的电子邮件Outlook可能会有所不同。 有关详细信息，请参阅更改 [脱机邮件的保留时间](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
有关分步迁移详细信息，请参阅：
  
- [有关分步电子邮件迁移的需知信息](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [执行电子邮件的分步迁移](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>完全混合

在完全混合迁移中，贵组织具有数百个（最多数万个）邮箱，并且您希望将其中一部分或全部移动到 Microsoft 365。 由于这些迁移通常是长期迁移，因此混合迁移可以：
  
- 向本地用户显示本地用户日历中的Microsoft 365忙/闲日历信息，反之亦然。
    
- 请参阅统一的全局地址列表，其中包含内部部署和本地Microsoft 365。
    
- 查看Outlook的完整收件人属性，而不管他们是在本地还是Microsoft 365。
    
- 使用 TLS 和证书Exchange内部部署服务器Microsoft 365之间的安全电子邮件通信。
    
- 在本地服务器和服务器Exchange发送Microsoft 365视为内部邮件，从而使这些邮件能够：
    
  - 由面向内部邮件的传输和合规性代理正确评估和处理。
    
  - 绕过反垃圾邮件筛选器。
    
完全混合迁移最适合希望保持混合配置数月或数月以上的组织。 您将获得本节前面列出的功能，以及目录同步、更好的集成合规性功能，以及使用联机邮箱移动将邮箱移动到 Microsoft 365 和从 Microsoft 365 的功能。 Microsoft 365成为本地组织的扩展。
  
如果您正在考虑执行完全混合迁移，请考虑以下操作：
  
- 完全混合迁移并不适合所有类型的组织。 由于完全混合迁移的复杂性，拥有少于几百个邮箱的组织通常看不到证明设置一个邮箱所需的工作量和成本合理的好处。 如果这看起来像是您的组织，我们建议你改为考虑使用转换迁移或分步迁移。
    
- 您需要在 Exchange 2007 组织中至少部署一Exchange 2013 服务器，以充当"混合服务器"。 此服务器将Microsoft 365您的 Exchange 2007 服务器进行通信。
    
- Microsoft 365需要通过 TCP 端口 443 使用 Outlook Anywhere 连接到"混合服务器"。
    
- 你需要在本地 Active Directory 服务器和 Microsoft 365 之间Azure Active Directory (Azure AD) 连接设置目录Microsoft 365。
    
- 用户将能够使用与登录到本地网络Microsoft 365相同的用户名和密码登录到其邮箱。  (此功能需要 Azure AD 连接密码同步和/或 Active Directory 联合身份验证服务。) 
    
- 您需要一个Microsoft 365许可证，其中包含Exchange Online迁移的每个用户邮箱的邮箱。
    
- 用户无需在大部分设备上设置新的 Outlook 配置文件，尽管某些较旧的 Android 手机可能需要新的配置文件。 用户不需要重新下载其电子邮件。
    
如果完全混合迁移适合您，请参阅以下资源来帮助进行迁移：
  
- [Exchange部署助理](/exchange/exchange-deployment-assistant)
    
- [Exchange Server 混合部署](/exchange/exchange-hybrid)
    
- [混合配置向导](/exchange/hybrid-configuration-wizard)
    
- [混合配置向导常见问题解答](/exchange/hybrid-configuration-wizard-faqs)
    
- [混合部署先决条件](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>迁移到更高版本的 Exchange Server

我们强烈建议您迁移到新用户，以获得最佳价值和Microsoft 365。 但我们还知道，某些组织需要将电子邮件保留在本地。 这可能是因为法规要求，以保证数据不会存储在位于另一个国家/地区或类似国家/地区中的数据中心。 如果您选择将电子邮件保留在本地，您可以将 Exchange 2007 环境迁移到 Exchange 2010、Exchange 2013 或 Exchange 2016。
  
如果您无法迁移到 Microsoft 365，建议您迁移到 Exchange 2016。 Exchange 2016 包含早期版本的 Exchange。 它还最匹配可用于Microsoft 365，尽管某些功能仅在 Microsoft 365。 查看你缺少的一些内容：
  
|**Exchange发布**|**功能**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based访问控制 (ACL 权限)   <br/>  Outlook Web App 邮箱策略  <br/>  能够在组织之间共享忙/闲日历和委派日历  <br/> |
|Exchange 2013  <br/> | *2010 Exchange及 ... 中的功能*  <br/>  简化的体系结构，将服务器角色的数量减少到三个 (邮箱、客户端访问、边缘传输)   <br/>  数据丢失防护策略 (DLP) ，有助于防止敏感信息泄露  <br/>  改进Outlook Web App体验  <br/> |
|Exchange 2016  <br/> | *2013 Exchange及 ... 中的功能*  <br/>  将服务器角色进一步简化为仅邮箱和边缘传输  <br/>  改进了 DLP 以及与 SharePoint  <br/>  改进了数据库恢复能力  <br/>  联机文档协作 |
   
#### <a name="which-version-should-i-migrate-to"></a>我应该迁移到哪个版本？

建议最初假定您将迁移到 2016 Exchange迁移。 然后，使用以下信息确认您的假设或排除 Exchange 2016。 如果由于某种原因无法迁移到 Exchange 2016，请对 Exchange 2013 执行相同的过程，等等。
  
|**注意事项**|**详细信息**|
|:-----|:-----|
|支持结束日期  <br/> | 与 Exchange 2007 一样，Exchange版本都有自己的支持结束日期：  <br/> *Exchange 2010 年 1* 月 - 2020 年 1 月  <br/> *Exchange 2013* 年 4 月 - 2023 年 4 月  <br/> *Exchange 2016 年 10* 月 - 2025 年 10 月  <br/>  支持终止越早，需要执行另一个迁移越早。<br/> |
|2010 Exchange 2013 的迁移路径。  <br/> |下面是迁移到 2010 年 Exchange 2013 Exchange的常规阶段：  <br/> - 将 Exchange 2010 或 2013 安装到现有 Exchange 2007 组织中。 <br/>- 将服务和其他基础结构移动到 Exchange 2010 或 2013。<br/>- 将邮箱和公用文件夹移动到 Exchange 2010 或 2013。<br/>- 停用 Exchange 2007 服务器。 |
|2016 Exchange迁移路径  <br/> |下面是迁移到 Exchange 2016 的常规阶段：  <br/> - 将 Exchange 2013 安装到现有 Exchange 2007 组织中。<br/>- 将服务和其他基础结构移动到 Exchange 2013。<br/>- 将邮箱和公用文件夹移动到 Exchange 2013。<br/>- 停用 Exchange 2007 服务器。<br/>- 将 Exchange 2016 安装到现有 Exchange 2013 组织中。<br/>- 将邮箱、公用文件夹、服务和其他基础结构移动到 Exchange 2016 (顺序并不重要) 。 停用 2013 Exchange剩余服务器。<br/><br/> **注意：** 从 2013 Exchange 2013 Exchange 2016 迁移非常简单。 这两个版本的硬件要求几乎相同，并且这些版本非常兼容。 因此，可以重新生成为 Exchange 2013 购买的服务器，Exchange 2016。 对于联机邮箱移动，大多数用户甚至不会注意到他们的邮箱已从服务器中移动，然后在使用 Exchange 2016 重新构建后又移回。           |
|版本共存  <br/> | 迁移到 ...  <br/> **Exchange 2016：Exchange** 2016 无法安装在包含 Exchange 2007 服务器的组织中。 首先需要迁移到 Exchange 2010 或 2013 (我们强烈建议使用 Exchange 2013) ，删除所有 Exchange 2007 服务器，然后迁移到 Exchange 2016。  <br/> **Exchange 2010 或 Exchange 2013：** 您可以将 2010 Exchange 2013 Exchange 2013 安装到现有 Exchange 2007 组织中。 这使您能够在 2010 或 2013 Exchange安装一个或多个服务器并执行迁移。  <br/> |
|服务器硬件  <br/> | 服务器硬件要求自 2007 Exchange已更改。 确保你的硬件兼容。 有关详细信息，请参阅：  <br/> [Exchange 2016 系统要求](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 系统要求](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 系统要求](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  你会发现，性能Exchange以及新服务器中的计算能力和存储容量的提升意味着您可能需要更少的服务器来支持相同数量的邮箱。  <br/> |
|操作系统版本  <br/> | 每个版本支持的最低操作系统版本为：  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  有关操作系统支持详细信息，请参阅[Exchange可支持性矩阵。](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Active Directory 林功能级别  <br/> | 每个版本支持的最低 Active Directory 林功能级别为：  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  有关林功能级别支持的信息，请参阅[Exchange可支持性矩阵"](/Exchange/plan-and-deploy/supportability-matrix)。  <br/> |
|Office客户端版本  <br/> | 每个版本的Office支持的最低客户端版本为：  <br/> **Exchange 2016** - Office 2010 (最新更新)   <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  有关客户端支持Office，请参阅[Exchange可支持性矩阵。](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
   
#### <a name="how-do-i-migrate"></a>如何迁移？

如果你决定将电子邮件保留在本地，请使用以下资源来帮助进行迁移：
  
- [Exchange部署助理](/exchange/exchange-deployment-assistant)
    
- Exchange [2016、2013、2010](/Exchange/plan-and-deploy/active-directory/ad-schema-changes)的 Active Directory[架构更改](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)[](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
    
- Exchange [2016、2013、2010](/Exchange/plan-and-deploy/system-requirements)[的系统要求](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))[](/exchange/exchange-2013-system-requirements-exchange-2013-help)
    
- Exchange [2016、2013、2010](/Exchange/plan-and-deploy/prerequisites)[的先决条件](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))[](/exchange/exchange-2013-prerequisites-exchange-2013-help)
    
## <a name="get-help"></a>获取帮助

如果你要迁移到 Microsoft 365，你可能有资格使用我们的 Microsoft FastTrack 服务。 FastTrack提供了最佳做法、工具和资源，使迁移到 Microsoft 365尽可能无缝。 首先，支持工程师将分步完成迁移，从规划和设计到迁移最后一个邮箱。 有关此FastTrack，请参阅 Microsoft [FastTrack。](https://fasttrack.microsoft.com/)
  
如果在迁移到 Microsoft 365 时遇到问题，并且没有使用 FastTrack，或迁移到更高版本的 Exchange Server，我们将提供帮助。 以下是可以使用的一些资源：
  
- [技术社区](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [客户支持](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>相关主题

[有助于升级 Office 2007 服务器和客户端的资源](upgrade-from-office-2007-servers-and-products.md)