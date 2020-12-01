---
title: SharePoint Server 2007 停止提供支持路线图
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: 对 SharePoint Server 2007 的支持在10月2017结束。 在本文中，了解你的升级、迁移和支持选项。
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519630"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>SharePoint Server 2007 停止提供支持路线图

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

在 **2017 年10月 10** 日，Microsoft Office SharePoint Server 2007 已到达支持终止。 如果尚未从 SharePoint Server 2007 迁移到 Microsoft 365 或本地 SharePoint Server 的更新版本，现在是开始规划的时间。 本文提供的资源可帮助您将数据迁移到 SharePoint Online 或升级本地 SharePoint Server。
  
## <a name="what-does-end-of-support-mean"></a>*支持终止的* 含义是什么？

与大多数 Microsoft 产品一样，SharePoint Server 也具有支持生命周期，在此期间，Microsoft 提供了新的功能、缺陷修补程序、安全修补程序等。 此生命周期通常是从产品的初始版本中持续10年的时间。 此生命周期的结束被称为产品的支持终止。 在支持结束后，Microsoft 不再提供：
  
- 可能出现的问题的技术支持。
    
- 针对可能会影响服务器稳定性和可用性的问题的 Bug 修补程序。
    
- 安全修补程序可能会使服务器易受安全漏洞破坏。
    
- 时区更新。
    
在10月 10 2017 日之后，你的 SharePoint Server 2007 场仍将运行，但不会为产品发布任何进一步的更新、修补程序或修补程序，包括安全修补程序/修补程序。 Microsoft 支持已将其支持工作完全转移到产品的较新版本。 因为您的安装不再受支持或修补，所以应升级产品或迁移重要数据。
  
> [!TIP]
> 如果尚未计划升级或迁移，请参阅： [SharePoint 2007 迁移选项，以](sharepoint-2007-migration-options.md) 了解开始位置的一些示例。 你还可以搜索可帮助升级或 Microsoft 365 迁移的 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=841249) (或同时使用这两种) 。
  
有关 Office 2007 服务器和支持结束的详细信息，请参阅可 [帮助您从 Office 2007 服务器和客户端进行升级的资源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-are-my-options"></a>我的选项是什么？

您的第一位应是 [产品生命周期网站](https://go.microsoft.com/fwlink/?linkid=843148)。 如果你的本地 Microsoft 产品已过期，请检查其支持日期的结束日期，以便在一年中安排升级或迁移。 选择下一步时，请考虑哪些产品功能足够好、更好且最佳。 下面是一个示例： 
  
|**Good**|**能**|**最好**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint 混合  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint 混合  <br/> |
   
如果选择 "足够好" 选项，则在从 SharePoint Server 2007 迁移完成后，您很快需要开始规划另一次升级。 

>[!NOTE] 
>支持终止日期可能会发生变化。 检查 [产品生命周期网站](https://support.microsoft.com/lifecycle)。
  
## <a name="where-can-i-go-next"></a>接下来如何操作？

可以在自己的服务器上的本地安装 SharePoint Server。 或者，您可以使用 SharePoint Online，这是 Microsoft 365 中的一种联机服务。 可用的选项包括：
  
- 迁移到 SharePoint Online。
    
- 升级本地 SharePoint Server。
    
- 执行上述两项操作。
    
- 实现 [SharePoint 混合](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) 解决方案。
    
请注意与维护服务器场、维护或迁移自定义项相关的隐藏成本，以及升级 SharePoint Server 所需的硬件。 如果需要，可获得内部部署 SharePoint Server 服务器场的回报。 但是，如果在不进行大量自定义的旧版 SharePoint 服务器上运行服务器场，则可以从迁移到 SharePoint Online 中受益。
  
> [!IMPORTANT]
> 如果不经常使用 SharePoint 2007 中的内容，也可以选择其他选项。 一些 SharePoint 管理员选择创建 Microsoft 365 订阅，设置新的 SharePoint Online 网站，然后将其完全从 SharePoint 2007 中裁出，仅将必要的文档带到全新的 SharePoint Online 网站。 然后，可以将数据从 SharePoint 2007 网站中排出到存档中。 考虑您的用户如何使用 SharePoint 2007 安装中的数据。 可能有一些创造性的方法可以管理您的需求。
  
|**SharePoint Online (SPO)**|**SharePoint Server 本地**|
|:-----|:-----|
|高成本的时间 (规划/执行/验证)   <br/> |高成本的时间 (规划/执行/验证)   <br/> |
|降低资金成本， (不购买硬件)   <br/> |资金的成本较高 (硬件 + devs/admins)   <br/> |
|迁移的一次性成本  <br/> |每次迁移时重复的一次性成本  <br/> |
|低总拥有成本/维护  <br/> |高总拥有成本/维护  <br/> |
   
当您迁移到 Microsoft 365 时，一次性移动将具有较高的成本，而您可以对数据进行组织，并决定在云和背后留下的内容。 但未来的升级将自动进行，并且您将不再需要管理硬件和软件更新。 此外，您的服务器场的启动时间将由 Microsoft 服务级别协议 ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) 支持。
  
### <a name="migrate-to-sharepoint-online"></a>迁移到 SharePoint Online

确保 SharePoint Online 具有所需的所有功能。 请参阅 [Microsoft 365 和 Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)。
  
您不能直接从 SharePoint 2007 迁移到 SharePoint Online。 您的迁移到 SharePoint Online 将手动执行。 如果升级到 SharePoint Server 2013 或 SharePoint Server 2016，则可以使用 SharePoint 迁移 API (将信息迁移到 OneDrive for business 中，例如) 。
  
|**Online pro**|**联机 con**|
|:-----|:-----|
|Microsoft 提供 SPO 硬件和所有硬件管理。  <br/> |可用功能在本地 SharePoint Server 和 SPO 之间可能有所不同。  <br/> |
|你是订阅的全局管理员，并且可以将管理员分配给 SPO 网站。  <br/> |在本地 SharePoint Server 中，服务器场管理员可使用的某些操作不存在，或者不一定包含在 Microsoft 365 中的 SharePoint 管理员角色中。  <br/> |
|Microsoft 对底层硬件和软件应用修补程序、修补程序和更新。 <br/> |由于在服务中没有对基础文件系统的访问权限，因此自定义项受到限制。  <br/> |
|Microsoft 发布 [服务级别协议](https://go.microsoft.com/fwlink/?linkid=843153) 并快速移动以解决服务级别事件。 <br/> |SharePoint Online 中的服务将自动执行备份和还原以及其他恢复选项。 如果不使用备份，则将其覆盖。 <br/> |
|Microsoft 在服务中不断执行安全测试和服务器性能调整。 <br/> |对用户界面和其他 SharePoint 功能的更改由服务安装，并且可能需要开启或关闭。 <br/> |
|Microsoft 365 符合多种行业标准： [microsoft 合规性服务](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |迁移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)协助受到限制。  <br/> 大部分升级都是手动进行的，也可以通过 [SharePoint Online 和 OneDrive 迁移内容路线图](https://go.microsoft.com/fwlink/?linkid=843184)中介绍的 SPO 迁移 API 进行。  <br/> |
|Microsoft 支持工程师和数据中心员工不会对你的订阅进行无限制的管理员访问。 <br/> |如果需要升级硬件以支持较新版本的 SharePoint，或者如果升级需要辅助服务器场，则可能会有额外的成本。  <br/> |
|合作伙伴可协助将数据迁移到 SharePoint Online 的一次性作业。  <br/> ||
|在线产品将自动更新。 尽管功能可能弃用，但也没有真正的支持结束。 <br/> ||
   
如果你已决定创建新的 Microsoft 365 网站，并将向其手动迁移数据，请查看你的 [Microsoft 365 选项](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>升级本地 SharePoint Server

没有办法跳过 SharePoint 升级中的版本。 升级以串行的顺序进行：
  
- SharePoint 2007 \> Sharepoint server 2010 \> sharepoint server 2013 \> sharepoint server 2016
   
从 SharePoint 2007 迁移到 SharePoint Server 2016 意味着需要大量的时间，并且会涉及硬件的成本 (SQL server 也必须升级) 、软件和管理。 需要升级或放弃自定义项。
  
> [!NOTE]
> 可以维护您的生命期结束的 SharePoint 2007 场，将 SharePoint Server 2016 场安装在新的硬件 (，以便单独的服务器场并行运行) ，然后规划和执行内容 (的手动迁移，以下载和重新上载内容，例如) 。 但请注意，手动移动的一些陷阱，例如，文档移动将上次修改的帐户替换为执行手动移动的帐户别名。 还要考虑必须提前完成的工作，如重新创建网站、子网站、权限和列表结构。 提前考虑可以移动到存储或删除的数据，以降低迁移的影响。
  
在升级之前清理环境非常重要。 一定要确保现有服务器场在升级之前正常运行，当然不应在停止之前运行！
  
请记住查看 *支持的和不受支持的升级路径*： 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
如果您具有自定义项，则在迁移路径中为每个步骤制定一个计划至关重要： 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**本地 pro**|**本地 con**|
|:-----|:-----|
|从服务器硬件上完全控制 SharePoint 场的各个方面。  <br/> |所有中断和修复都是贵公司的责任 (如果你的产品不是支持的结束) ，你可以联系付费 Microsoft 支持部门。  <br/> |
|SharePoint Server 本地的完整功能集以及通过混合将本地服务器场连接到 SharePoint Online 订阅的选项。  <br/> |在本地托管的 SharePoint Server 的升级、修补程序、安全修补程序和所有维护。  <br/> |
|完全访问权限以进行更好的自定义。  <br/> |[Microsoft 合规性产品](https://go.microsoft.com/fwlink/?linkid=843165) 必须在本地手动配置。  <br/> |
|在您的控制) 下，对您的本地 (执行安全测试和服务器性能调整。  <br/> |Microsoft 365 可能会对 SharePoint Online 可用的功能，这些功能不能与本地 SharePoint Server 进行互操作。  <br/> |
|合作伙伴可以协助将数据迁移到下一版本的 SharePoint Server (，但不能迁移到) 之外。  <br/> |您的 SharePoint Server 站点不会自动使用在 SharePoint Online 中显示的 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 证书。  <br/> |
|完全控制命名约定、备份和还原以及本地 SharePoint Server 中的其他恢复选项。  <br/> |本地 SharePoint Server 对产品生命周期非常敏感。  <br/> |
   
### <a name="upgrade-resources"></a>升级资源

确保您的环境满足硬件和软件要求，然后遵循受支持的升级方法。
  
- **的硬件/软件要求**： 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **的软件边界和限制**： 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- 以下项 **的升级过程概述**： 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 和本地部署之间创建 SharePoint 混合解决方案

如果迁移的答案需要在本地提供的自控制和 SharePoint Online 提供的更低的所有权之间，则可以通过混合将 SharePoint Server 2013 或2016服务器场连接到 SharePoint Online。 [了解 SharePoint 混合解决方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)。
  
如果你确定混合 SharePoint 服务器场将对你的业务有益，请熟悉现有的混合类型，以及如何配置你的本地 SharePoint 场和 Microsoft 365 订阅之间的连接。
  
| 选项 | 说明 |
|:-----|:-----|
[Microsoft 合规性产品/服务](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |迁移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)协助受到限制。  <br/> 大部分升级都是手动进行的，也可以通过 [SharePoint Online 和 OneDrive 迁移内容路线图](https://go.microsoft.com/fwlink/?linkid=843184)中介绍的 SPO 迁移 API 进行。  <br/> |
|Microsoft 支持工程师和数据中心员工对你的订阅没有无限制的管理员访问权限。<br/> |如果需要升级硬件基础结构以支持较新版本的 SharePoint，或者如果升级需要辅助服务器场，则可能会有额外的成本。  <br/> |
|合作伙伴可协助将数据迁移到 SharePoint Online 的一次性作业。  <br/> ||
|在线产品通过服务自动更新。 尽管功能可能弃用，但也没有真正的支持结束。<br/> ||
   
如果你已决定创建新的 Microsoft 365 网站，并将向其手动迁移数据，请查看你的 [Microsoft 365 选项](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>升级本地 SharePoint Server

没有办法跳过 SharePoint 升级中的版本。 升级以串行的顺序进行：
  
- SharePoint 2007 \> Sharepoint server 2010 \> sharepoint server 2013 \> sharepoint server 2016
   
从 SharePoint 2007 迁移到 SharePoint Server 2016 意味着需要大量的时间，并将涉及硬件的成本 (SQL server 也必须升级) 、软件和管理。 需要升级或放弃自定义项。
  
> [!NOTE]
> 可以维护您的生命期结束的 SharePoint 2007 场，将 SharePoint Server 2016 场安装在新的硬件 (，以便单独的服务器场并行运行) ，然后规划和执行内容 (的手动迁移，以下载和重新上载内容，例如) 。 但是，请注意手动移动的潜在缺陷，例如，文档移动将上次修改的帐户替换为执行手动移动的帐户别名，并且必须提前完成的工作（如重新创建网站、子网站、权限和列表结构）。 考虑可以移动到存储或删除的数据，以降低迁移的影响。
  
在升级之前清理环境。 一定要确保您的现有服务器场在升级之前正常运行，并且在您停止工作之前！ 
  
请记住查看 *支持的和不受支持的升级路径*： 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
如果您具有 *自定义项*，则在迁移路径中为每个步骤规划升级都很重要： 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**本地 Pro**|**本地 Con**|
|:-----|:-----|
|从服务器硬件上完全控制 SharePoint 场的各个方面。  <br/> |所有中断和修复都是贵公司的责任。  (如果你的产品尚不支持，你可以联系付费 Microsoft 支持部门。 )   <br/> |
|SharePoint Server 本地的完整功能集以及通过混合将本地服务器场连接到 SharePoint Online 订阅的选项。  <br/> |在本地托管的 SharePoint Server 的升级、修补程序、安全修补程序和所有维护。  <br/> |
|完全访问权限以进行更好的自定义。  <br/> |[Microsoft 合规性产品](https://go.microsoft.com/fwlink/?linkid=843165) 必须在本地手动配置。  <br/> |
|安全测试和服务器性能调整在您的内部部署下执行。  <br/> |Microsoft 365 可能会对 SharePoint Online 可用的功能，这些功能不能与本地 SharePoint Server 进行互操作  <br/> |
|合作伙伴可以帮助将数据迁移到 SharePoint Server 的下一个版本 (和) 之外。  <br/> |您的 SharePoint Server 网站不会自动使用在 SharePoint Online 中显示的 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 证书。  <br/> |
|完全控制命名约定、备份和还原以及本地 SharePoint Server 中的其他恢复选项。  <br/> |本地 SharePoint Server 对产品生命周期非常敏感。  <br/> |
   
### <a name="upgrade-resources"></a>升级资源

请确保您的环境满足硬件和软件要求。 然后遵循受支持的升级方法。
  
- **的硬件/软件要求：** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **的软件边界和限制：** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **以下项的升级过程概述：** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 和本地部署之间创建 SharePoint 混合解决方案

如果迁移的答案需要在本地提供的自控制和 SharePoint Online 提供的更低的所有权之间，则可以通过混合将 SharePoint Server 2013 或2016服务器场连接到 SharePoint Online。 [了解 SharePoint 混合解决方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
如果你确定混合 SharePoint 服务器场将对你的业务有益，请熟悉现有的混合类型，以及如何配置你的本地 SharePoint 场和 Microsoft 365 订阅之间的连接。
  
若要了解其工作原理，一种很好的方法是创建 Microsoft 365 开发/测试环境，您可以使用 [测试实验室指南](m365-enterprise-test-lab-guides.md)对其进行设置。 在获取试用版或购买的 Microsoft 365 订阅后，可以在 SharePoint Online 中创建可将数据迁移到的网站集、web 和文档库。 您可以通过使用迁移 API 手动迁移，或者如果要通过混合向导将我的网站内容迁移到 OneDrive for business，则可以进行手动迁移。
  
> [!NOTE]
> 请记住，若要使用 "混合" 选项，您的 SharePoint 2007 服务器场将需要升级到 SharePoint Server 2013 或 SharePoint Server 2016 （本地）。
  
## <a name="related-topics"></a>相关主题

[ (Office SharePoint Server 2007 的疑难解答和恢复升级) ](https://go.microsoft.com/fwlink/?linkid=843192)
  
[解决 SharePoint Server 2010 (的升级问题) ](https://go.microsoft.com/fwlink/?linkid=843194)
  
[在 SharePoint 2013 中解决数据库升级问题](https://go.microsoft.com/fwlink/?linkid=843195)
  
[搜索 Microsoft 合作伙伴以帮助进行升级](https://go.microsoft.com/fwlink/?linkid=841249)
  
[可帮助您从 Office 2007 服务器和客户端进行升级的资源](upgrade-from-office-2007-servers-and-products.md)
  
