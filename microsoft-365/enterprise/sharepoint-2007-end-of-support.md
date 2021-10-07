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
ms.localizationpriority: medium
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
description: 对 SharePoint Server 2007 的支持已于 2017 年 10 月结束。 本文介绍升级、迁移和支持选项。
ms.openlocfilehash: d09e0cf58ef814a76cdac28f6029189eaf655efc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197265"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>SharePoint Server 2007 停止提供支持路线图

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

**2017 年 10 月 10** Microsoft Office SharePoint，Microsoft Office SharePoint Server 2007 停止提供支持。 如果您尚未从 SharePoint Server 2007 迁移到 Microsoft 365 或本地 SharePoint Server 的更高版本，那么现在该开始规划了。 本文提供的资源可帮助你将数据迁移到 SharePoint Online 或在本地升级 SharePoint Server。
  
## <a name="what-does-end-of-support-mean"></a>停止 *提供支持意味着什么* ？

SharePoint与大多数 Microsoft 产品一样，服务器具有支持生命周期，在此期间 Microsoft 提供新功能、Bug 修复、安全修补程序等。 此生命周期通常自产品初始发布起持续 10 年。 此生命周期的结束称为产品的停止支持。 在停止提供支持后，Microsoft 将不再提供：
  
- 针对可能会出现的问题的技术支持。
    
- 对可能会影响服务器稳定性和可用性的问题进行 Bug 修复。
    
- 针对可能导致服务器易受安全漏洞的漏洞进行安全修复。
    
- 时区更新。
    
2017 年 10 月 10 日之后，SharePoint Server 2007 场仍可运行，但不会发布该产品的更多更新、修补程序或修补程序，包括安全修补程序/修补程序。 Microsoft 支持已将支持工作完全转移到产品的最新版本。 由于不再支持或修补安装，因此应升级产品或迁移重要数据。
  
> [!TIP]
> 如果尚未规划升级或迁移，请参阅[：SharePoint 2007](sharepoint-2007-migration-options.md)迁移选项，了解一些开始迁移位置的示例。 还可以搜索可帮助升级[或](https://go.microsoft.com/fwlink/?linkid=841249)迁移迁移或迁移Microsoft 365或 (两) 。
  
有关 Office 2007 服务器和停止提供支持的信息，请参阅帮助您从[Office 2007 服务器和客户端升级的资源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-are-my-options"></a>我的选项是什么？

你的第一个停止位置应该是 [产品生命周期网站](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007)。 如果你有一个过期本地 Microsoft 产品，请检查其支持结束日期，以便你有一年左右的时间计划升级或迁移。 选择下一步时，请考虑哪些产品功能足够好、更好、最好。 下面是一个示例： 
  
|**Good**|**更好**|**最好**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint 混合  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint 混合  <br/> |
   
如果选择"足够好"选项，则很快需要在从 SharePoint Server 2007 完成迁移后开始规划其他升级。 

>[!NOTE] 
>支持结束日期可能会发生变化。 查看产品 [生命周期网站](https://support.microsoft.com/lifecycle)。
  
## <a name="where-can-i-go-next"></a>接下来如何操作？

SharePoint可以在自己的服务器上本地安装服务器。 或者，可以使用 SharePoint Online，这是一种联机服务，属于 Microsoft 365。 可用的选项包括：
  
- 迁移到 SharePoint Online。
    
- 在本地SharePoint升级 SharePoint Server。
    
- 执行上述两项。
    
- 实现SharePoint[混合](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)解决方案。
    
请注意与维护服务器场、维护或迁移自定义项以及升级 SharePoint 服务器所需的硬件相关的隐藏成本。 必要时，在本地SharePoint服务器场是一种奖励。 但是，如果在不进行大量自定义的旧版 SharePoint 服务器上运行服务器场，可以从迁移到 SharePoint Online 中获益。
  
> [!IMPORTANT]
> 如果很少使用 SharePoint 2007 中的内容，则还有另一个选项。 某些 SharePoint 管理员选择创建 Microsoft 365 订阅，设置一个新的 SharePoint Online 网站，然后完全离开 SharePoint 2007，仅将基本文档提交到全新的 SharePoint Online 网站。 然后，可以将数据从 SharePoint 2007 网站排入存档。 考虑您的用户如何处理来自 SharePoint 2007 安装的数据。 可能有一些用于管理需求的创意方法。
  
|**SharePoint联机 (SPO)**|**SharePoint服务器本地**|
|:-----|:-----|
|计划/执行/验证 (时间成本高)   <br/> |计划/执行/验证 (时间成本高)   <br/> |
|资金成本更低 (无需购买硬件)   <br/> |硬件 +开发人员/ (的资金成本更高)   <br/> |
|迁移中的一次成本  <br/> |每次未来迁移重复一次成本  <br/> |
|较低的总拥有/维护成本  <br/> |高总拥有/维护成本  <br/> |
   
迁移到 Microsoft 365 时，一次移动会在前面花费更高昂的成本，同时组织数据并决定对云采取哪些操作以及留下哪些内容。 但是，将来的升级是自动的，你不再需要管理硬件和软件更新。 此外，服务器场的启动时间将受 MICROSOFT 服务级别协议和 [SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) (支持) 。
  
### <a name="migrate-to-sharepoint-online"></a>迁移到 SharePoint Online

确保 SharePoint Online 具有所有所需的功能。 请参阅[Microsoft 365和Office 365服务说明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)。
  
不能直接从 2007 SharePoint迁移到 SharePoint Online。 你移动到 SharePoint Online 将手动完成。 如果升级到 SharePoint Server 2013 或 SharePoint Server 2016，可以使用 SharePoint 迁移 API (将信息迁移到 OneDrive for Business，例如) 。
  
|**在线专业人员**|**Online con**|
|:-----|:-----|
|Microsoft 提供 SPO 硬件以及所有硬件管理。  <br/> |本地服务器和 SPO SharePoint可用功能可能不同。  <br/> |
|你是订阅的 Sharepoint 管理员或全局管理员，并且可以将管理员分配到 SPO 网站。  <br/> |SharePoint Server 内部部署中的服务器场管理员可用的某些操作不存在，或不一定包含在 Microsoft 365 中的 SharePoint 管理员角色中。  <br/> |
|Microsoft 对基础硬件和软件应用修补程序、修补程序和更新。 <br/> |由于服务中无法访问基础文件系统，因此自定义受到限制。  <br/> |
|Microsoft 发布了 [服务级别协议，](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) 并快速移动以解决服务级别事件。 <br/> |备份和还原以及其他恢复选项由 SharePoint Online 中的服务自动执行。 如果未使用，则覆盖备份。 <br/> |
|Microsoft 在服务中持续执行安全测试和服务器性能调整。 <br/> |对用户界面和其他SharePoint的更改由服务安装，可能需要打开或关闭。 <br/> |
|Microsoft 365符合许多行业标准[：Microsoft 合规性产品/服务](/compliance/regulatory/offering-home)。  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)迁移的帮助有限。  <br/> 大部分升级是手动的，或通过 SharePoint Online 和 OneDrive Migration Content Roadmap 中所述的 SPO[迁移 API。](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft 支持工程师和数据中心员工将不能不受限制地访问你的订阅。 <br/> |如果需要升级硬件以支持较新版本的 SharePoint，或者升级需要辅助服务器场，则可能会增加额外的成本。  <br/> |
|合作伙伴可帮助完成将数据迁移到 SharePoint Online 的一SharePoint作业。  <br/> ||
|联机产品将自动更新。 虽然功能可能会弃用，但不存在真正停止提供支持的情况。 <br/> ||
   
如果你已决定新建一个Microsoft 365网站，并根据需要手动将数据迁移到该网站，请检查你的Microsoft 365[选项](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>在本地SharePoint服务器升级

在升级中无法跳过SharePoint版本。 升级将串行进行：
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
从 SharePoint 2007 升级到 SharePoint Server 2016 意味着需要大量时间投入，并且涉及硬件 (SQL 服务器的成本也必须) 、软件和管理。 自定义项将需要升级或放弃。
  
> [!NOTE]
> 可以维护生命周期结束的 SharePoint 2007 场，将 SharePoint Server 2016 场安装在新硬件 (上，以便单独的服务器场并行运行) ，然后计划并执行内容 (的手动迁移以下载和重新上载内容，例如) 。 但请注意手动移动的一些错误，例如将最后修改的帐户替换为执行手动移动的帐户别名的文档移动。 还要考虑必须提前完成的工作，例如重新创建网站、子网站、权限和列表结构。 提前考虑可以移入存储或删除哪些数据，以减少迁移的影响。
  
在升级之前清理环境很重要。 在升级之前，一定要确保现有服务器场正常运行，并且一定在停用之前运行！
  
请记住查看 *受支持和不受支持的升级路径*： 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
如果有自定义项，则制定迁移路径中每个步骤的计划至关重要： 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**本地专业人员**|**本地 con**|
|:-----|:-----|
|从服务器硬件上SharePoint对服务器场的所有方面进行完全控制。  <br/> |所有中断和修复都由你的公司负责 (如果你的产品未过去停止提供支持，你可以联系付费的 Microsoft) 。  <br/> |
|本地 SharePoint 服务器的完整功能集，通过混合将本地服务器场连接到 SharePoint Online 订阅的选项。  <br/> |升级、修补程序、安全修补程序以及本地托管的 SharePoint Server 的所有维护。  <br/> |
|可进行更大自定义的完全访问权限。  <br/> |[必须在本地](/compliance/regulatory/offering-home) 手动配置 Microsoft 合规性产品/服务。  <br/> |
|安全测试和服务器性能调整在内部部署服务器上 (控制) 。  <br/> |Microsoft 365可能会向 SharePoint Online 提供不与本地 SharePoint 交互的功能。  <br/> |
|合作伙伴可帮助将数据迁移到下一版本的 SharePoint Server (及) 。  <br/> |您的 SharePoint Server 网站不会自动使用[SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016)证书，如 SharePoint Online 中所见。  <br/> |
|完全控制命名约定、备份和还原以及 SharePoint Server 内部部署中的其他恢复选项。  <br/> |SharePoint本地服务器对产品生命周期很敏感。  <br/> |
   
### <a name="upgrade-resources"></a>升级资源

确保您的环境满足硬件和软件要求，然后遵循支持的升级方法。
  
- **的硬件/软件要求**： 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **的软件边界和限制**： 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **的升级过程概述**： 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 和本地SharePoint混合解决方案

如果迁移需求的答案介于本地提供的自控制与 SharePoint Online 提供的所有权成本较低之间，则可以通过混合将 SharePoint Server 2013 或 2016 场连接到 SharePoint Online。 [了解混合SharePoint解决方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)。
  
如果您确定混合 SharePoint Server 服务器场将有利于您的业务，请熟悉现有的混合类型以及如何在本地 SharePoint 服务器场和 Microsoft 365 订阅之间配置连接。
  
| 选项 | 说明 |
|:-----|:-----|
[Microsoft 合规性产品/服务](/compliance/regulatory/offering-home)  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)迁移的帮助有限。  <br/> 大部分升级是手动的，或通过 SharePoint Online 和 OneDrive Migration Content Roadmap 中所述的 SPO[迁移 API。](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft 支持工程师和数据中心员工对订阅没有不受限制的管理员访问权限。<br/> |如果需要升级硬件基础结构以支持较新版本的 SharePoint，或者升级需要辅助服务器场，则可能会增加额外的成本。  <br/> |
|合作伙伴可帮助完成将数据迁移到 SharePoint Online 的一SharePoint作业。  <br/> ||
|联机产品会在整个服务中自动更新。 虽然功能可能会弃用，但不存在真正停止提供支持的情况。<br/> ||
   
如果你已决定新建一个Microsoft 365网站，并根据需要手动将数据迁移到该网站，请检查你的Microsoft 365[选项](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>在本地SharePoint升级 SharePoint Server

在升级中无法跳过SharePoint版本。 升级将串行进行：
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
从 SharePoint 2007 升级到 SharePoint Server 2016 意味着需要大量时间投入，并且涉及硬件 (SQL 服务器的成本也必须) 、软件和管理。 自定义项将需要升级或放弃。
  
> [!NOTE]
> 可以维护生命周期结束的 SharePoint 2007 场，将 SharePoint Server 2016 场安装在新硬件 (上，以便单独的服务器场并行运行) ，然后计划并执行内容 (的手动迁移以下载和重新上载内容，例如) 。 但请注意手动移动的潜在错误，例如将上次修改的帐户替换为执行手动移动的帐户别名的文档移动，以及必须提前完成的工作，如重新创建网站、子网站、权限和列表结构。 请考虑可以移入存储或删除哪些数据，以减少迁移的影响。
  
在升级之前清理环境。 在升级之前以及停用之前，一定要确保现有服务器场正常运行！ 
  
请记住查看 *受支持和不受支持的升级路径*： 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
如果有 *自定义项*，则规划迁移路径中每个步骤的升级至关重要： 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**本地Pro**|**本地 Con**|
|:-----|:-----|
|从服务器硬件上SharePoint对服务器场的所有方面进行完全控制。  <br/> |所有中断和修复都由你的公司负责。  (如果你的产品未停止提供支持，你可以参与付费 Microsoft 支持。)   <br/> |
|本地 SharePoint 服务器的完整功能集，通过混合将本地服务器场连接到 SharePoint Online 订阅的选项。  <br/> |升级、修补程序、安全修补程序以及本地托管的 SharePoint Server 的所有维护。  <br/> |
|可进行更大自定义的完全访问权限。  <br/> |[必须在本地](/compliance/regulatory/offering-home) 手动配置 Microsoft 合规性产品/服务。  <br/> |
|安全测试和服务器性能调整在本地由你控制。  <br/> |Microsoft 365可能会向 SharePoint Online 提供不与 SharePoint Server 本地互操作的功能  <br/> |
|合作伙伴可帮助将数据迁移到下一版本的 SharePoint Server (及) 。  <br/> |您的 SharePoint Server 网站不会自动使用[SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016)证书，如 SharePoint Online 中所见。  <br/> |
|完全控制命名约定、备份和还原以及 SharePoint Server 内部部署中的其他恢复选项。  <br/> |SharePoint本地服务器对产品生命周期很敏感。  <br/> |
   
### <a name="upgrade-resources"></a>升级资源

确保您的环境满足硬件和软件要求。 然后按照支持的升级方法操作。
  
- **针对：的硬件/软件要求：** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **针对： 的软件边界和限制：** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **以下的升级过程概述：** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 和本地SharePoint混合解决方案

如果迁移需求的答案介于本地提供的自控制与 SharePoint Online 提供的所有权成本较低之间，则可以通过混合将 SharePoint Server 2013 或 2016 场连接到 SharePoint Online。 [了解混合SharePoint解决方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
如果您确定混合 SharePoint Server 服务器场将有利于您的业务，请熟悉现有的混合类型以及如何在本地 SharePoint 服务器场和 Microsoft 365 订阅之间配置连接。
  
查看工作原理的一个好方法就是创建Microsoft 365/测试环境，可以使用测试实验室指南[进行设置](m365-enterprise-test-lab-guides.md)。 获取试用版或购买Microsoft 365订阅后，可以在 SharePoint Online 中创建网站集、Web 和文档库，可以将数据迁移到其中。 可以使用迁移 API 手动迁移，或者，如果要将"我的网站"内容迁移到OneDrive for Business向导进行迁移。
  
> [!NOTE]
> 请记住，若要使用混合选项，SharePoint 2007 服务器场需要在本地升级到 SharePoint Server 2013 或 SharePoint Server 2016。
  
## <a name="related-topics"></a>相关主题

[排查并恢复 (Office SharePoint Server 2007) ](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[解决 (SharePoint Server 2010) ](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[在 SharePoint 2013 中解决数据库升级问题](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[搜索 Microsoft 合作伙伴以帮助升级](https://go.microsoft.com/fwlink/?linkid=841249)
  
[帮助您从 Office 2007 服务器和客户端升级的资源](upgrade-from-office-2007-servers-and-products.md)
