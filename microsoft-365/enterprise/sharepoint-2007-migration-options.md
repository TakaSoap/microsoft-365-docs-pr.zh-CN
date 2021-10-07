---
title: SharePoint 2007 迁移选项需要考虑
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文包含有关使用 SharePoint Server 2007 帮助用户规划升级的信息。
ms.openlocfilehash: 9f374e3e4f2282a7740575c60eb52e7095321c92
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210193"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint 2007 迁移选项需要考虑

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft SharePoint 2007 和 SharePoint Server 2007 已终止支持。 是时候升级了！ 本文提供有关迁移选项的信息。
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>适用于升级的常见SharePoint

有多种方法可以升级 SharePoint 服务器环境。 如果您有一个 Microsoft Office SharePoint Server 2007 服务器场，下面是升级方法的一些示例：
  
- 数据库附加
    
- 并行升级
    
- 就地升级
    
- 具有 (数据库/单独的数据库附加数据库的混合升级) 
    
- SharePoint混合 (联机连接到本地SharePoint) 
    
- 在网站集或库之间手动移动数据
    
- FastTrack向导升级到 Microsoft 365 (SharePoint [Online 部署顾问](https://aka.ms/spoguidance)) 
    
- 迁移到 SharePoint Online (SPO) API Microsoft 365
    
哪些方法最适合你？
  
您了解服务器场执行和用于哪些操作是升级时的强大功能。 用户使用服务器场SharePoint将帮助您从选项中进行选择。
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 还有逐步升级，此处未介绍。 若要查看特定于步骤的升级文章的列表，请参阅 SharePoint [Server 2007 停止提供支持路线图](sharepoint-2007-end-of-support.md)。 
  
请记住检查[产品生命周期](https://support.microsoft.com/lifecycle/search)和系统要求，了解你要升级到SharePoint版本的产品生命周期和系统要求。 因此，你将知道何时需要下一次升级 (例如，如果暂停 SharePoint Server 2010 等旧版产品以规划更多升级，请确保你知道其支持结束日期) ，并确保你有支持你的计划的硬件。 
  
如果你计划将部分或所有 SharePoint 站点转换到云中的 Microsoft 365，那么此时需要为指向[Microsoft 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library)和 Office 365 服务说明的链接添加书签。 你需要使用服务说明来了解 SharePoint Online 功能，以及这些功能与本地 SharePoint 服务器的区别。 升级 Microsoft Office SharePoint Server 2007 服务器场的功能。 如果安装中的网站已损坏，请先修复这些网站，之后进行升级。
  
## <a name="a-note-about-managing-risk"></a>关于管理风险的注释

"并行"等方法在升级逻辑方案中非常重要。 在并行升级时，您可以维护 Microsoft Office SharePoint Server 2007 服务器场，但从该服务器场构建下一个版本 (SharePoint Server 2010) 新硬件上。 这有三方面的帮助：
  
1. 可以使用数据库附加对 Microsoft Office SharePoint Server 2007 数据库进行备份，以单独升级这些数据库。
    
2. 如果您确定 Microsoft Office SharePoint Server 2007 服务器场上仅使用少量关键文档库和其他信息，您可以选择手动将数据从 Microsoft Office SharePoint Server 2007 移动到 SharePoint Server 2010，或仅执行特定网站和 Web 到下一 (，这可以使作业更易于) 。
    
3. 您直接对 Microsoft Office SharePoint Server 2007 服务器场执行较少操作，升级时服务器场包含的数据就更安全。
    
In-Place升级等方法将直接作用于 Microsoft Office SharePoint Server 2007 场，从而减少放弃路径和从环境开始轻松选择的选项。 尽可能在一些安全措施中 (如采用和测试原始环境备份) 。 例如，如果您的 Microsoft Office SharePoint Server 2007 服务器场是虚拟服务器场，并且出于备份和还原目的被复制，那么在升级的服务窗口之前备份和还原最新的数据库。 如果您知道您可以选择还原数据库备份，则不仅为您提供了故障安全，还使您大为信心。
  
> [!TIP]
> 适用于[Microsoft Office SharePoint Server 2007、SharePoint Server 2010、SharePoint](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)) [Server 2013 和 SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)[的](/SharePoint/upgrade-and-update/best-practices-for-upgrade)升级最佳做法文档已存在。 [](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) 还可以搜索具有[升级](https://partnercenter.microsoft.com/pcv/search)或迁移或迁移Microsoft 365 Microsoft 合作伙伴。 
  
## <a name="make-your-plan"></a>制定计划

如果需要升级，则需要一个计划，在这种情况下，一个大小并不适合所有情况。 你的计划可能很简单，例如"使用 Microsoft 365 Online 创建 SharePoint 订阅，注册域，然后重定向用户以将文件保存到那里"。 它可能不是。 该决定由你决定，由你和用户真正需要决定。
  
> [!NOTE]
> 在生命周期已终止的软件上运行存在风险。 如果发现问题，将不再修补不再提供支持的产品。 这也意味着，如果出现新的安全威胁，将不会出现安全修补程序或修补程序，因为生命周期结束产品不再受支持。 请避免这种情况！ 
  
### <a name="first-know-your-farm"></a>首先，了解服务器场

在升级时，您的决策应基于您的服务器场对您的组织所完成的工作。 它满足哪些需求？ 它的角色是什么？ 公司中的每个服务器场可能具有不同的角色。 一些SharePoint服务器场可能是 *关键* 服务器场，一些可能是文件存档，其中用于安全保存。 或者，如果服务器场一次填充许多角色，则您可能需要了解网站集、Web 甚至文档库所执行哪些操作、任何自定义项及其重要级别。 在此级别分析数据似乎需要做大量工作，但在升级或迁移域之前，可以省去控制域的时间和精力。 在了解所有移动部件和最重要的位后，你还将了解你已增长并可以留下哪些内容。 这些知识仅对今后会大有益处。 
  
那么，对于您的服务器场，用户SharePoint什么？
  
- 内置SharePoint功能
    
- 大型数据集 (，如文件存档) 
    
- 可用性
    
- 服务器场中的关键应用、Web 部件或文档 (任务关键型服务器场) 
    
- 符合合规性标准
    
- 自定义
    
如果你从 SharePoint 服务器场运行对业务至关重要的内容，假设它充当有关客户端服务要求的重要数据的大型目录，你可能会在"关键应用"旁边加一个刻度，但也可以放在"可用性"旁边，也就是说，如果一段时间你无法使用 SharePoint，你的业务会受到影响。 同样，您可能要检查"自定义"，因为服务器场提供的关键服务基于自定义代码、网站定义或协同工作的很多自定义项。
  
如果 SharePoint满足这些需求，并且除了使用软件内置内容外无需执行任何操作，并且通常更新它并执行正常的管理和维护，则您可能选择了"内置 SharePoint"-这也是您坐在较旧版本的 SharePoint 上的原因。 换句话说，在 Microsoft Office SharePoint Server 2007 停止提供支持之前，它已执行所需的操作，并且您现在不需要升级。
  
当您为这些项创建项目符号列表时，您将为升级创建条件。 换句话说，任何升级都必须符合此条考虑。 这为你提供了一种排除当前不适合你需求的方法的方法的方法。
  
### <a name="a-simple-sample-plan"></a>简单示例计划

在升级将采取的路径上，可能需要与领导层和其他管理员SharePoint一致。 SharePoint服务器管理员通常与Microsoft SQL Server合作，与网络和安全团队等合作。 如果有很多利益干系人，你可能需要就升级和迁移计划达成一致或进行调整。 例如，如果你迁移数据以便公司部分使用 SharePoint Online Microsoft 365，可能需要在网络内部进行性能调整或测试。 应提前通知受影响的团队。
  
在我的简单示例中，我SharePoint管理员的建议，然后列出所有利益干系人达成一致的计划。 为清楚起见，请记录你的协议和决策。
  
该计划在深入分析服务器场后开始，并尝试确定服务器场的角色、要点和其他重要信息，这些信息将导致缩小一些升级选项范围。 之后，升级建议由管理员SharePoint利益干系人就行动计划达成一致。
  
我的"最重要的"项目符号列表：
  
- 可用性、内置于SharePoint和合规性标准。
    
- 大部分数据位于三个网站集上，开发人员团队使用的一个会议工作区尤其重要，并且在全球多个时区中大量使用。
    
- 还有一些广泛使用的其他网站。
    
- 根网站集 ("会议工作区"和"文档"两个文档) 最大，每个文档 (超过 8000 个) 。 我们具有大量包含电子表格附件的存档文档和列表。
    
- 有十四个包含敏感数据的库列表必须保持合规性。
    
- 我们必须能够随时随地进行保留和电子数据发现。
    
- 由于 InfoSec 规则，其中某些数据必须位于本地。
    
 **我的升级和迁移选择：**
  
| 是 | 否 |
|:-----|:-----|
|升级数据库附加数据库  <br/> |就地升级  <br/> |
|使用服务器场并行升级  <br/> |混合升级  <br/> |
|针对个人网站数据Microsoft 365 (中的将 API 迁移到 SPO)   <br/> |SharePoint目前 (混合)   <br/> |
|一些手动数据迁移到 SharePoint Online，用于关键数据  <br/> |FastTrack向导升级到 Microsoft 365  <br/> |
   
 **我的建议计划：**
  
在本地升级，并行升级SharePoint虚拟化版本，以便可以先升级数据库。 从 2007 SharePoint 2010 SharePoint 2010。 管理员和开发人员测试生成的服务器场。 用户测试生成的服务器场。 修复在此期间出现的任何停止显示问题。 同样，将 2010 SharePoint 2010 数据库并行升级到 SharePoint 2013。 测试。 用户测试/试点。 修复在此期间出现的任何停止显示问题。
  
- 考虑搜索联合混合与 SPO 是否满足您的需求。
    
- 如果你想要[FastTrack](https://fasttrack.microsoft.com)升级到 SharePoint Online，请考虑使用帮助。 
    
- 确定是否可以将任何网站集卸载到 Microsoft 365 订阅。  (Microsoft 365符合许多[合规性标准](/compliance/regulatory/offering-home)。 Microsoft 365[电子数据展示，](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da)[并且可以通过合规](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E)中心进行保留)  
    
否则，请继续并行升级到 SharePoint Server 2016。
  
> [!NOTE]
> 在规划升级的管理员提供的建议与实际过程之间是升级所依赖的其他利益干系人的对话。 例如，有时会强制管理员更改其计划。 无论最终决定是什么，您都应记录下一个达成一致计划的内容。 它可能如下所示： 
  
 **我的行动计划：**
  
在本地，我们使用虚拟环境在 SharePoint Server 2010 和 2013 中生成默认环境。 SharePoint服务器 2016 将基于满足 2016 年系统要求的新硬件构建。 我们会将数据库附加到从 SharePoint 2007 到 SharePoint Server 2016 之间的所有版本升级数据库。 目前，如果本机功能还没有满足我们的需求，将在 SharePoint Server 2016 环境中重新创建和测试核心自定义项。 如果成功，我们将有一个本地服务器场，位于具有升级数据库的新硬件上，并且自定义更少。 我们将升级后的内容数据库附加到 SharePoint Server 2013 中的新网站集、测试、用户测试/试点，然后执行 DNS 剪切到新的 SharePoint Server 2016 环境以实时使用。
  
- 目前，我们不考虑 SharePoint Server 2016 和 SharePoint Online 之间的联合混合。
    
- 估计有 35% 的网站可以转换为具有虚域的新 SPO 网站，或者最终OneDrive for Business存储。 寻找转换站点或将新站点路由到 SPO 的其他机会。
    
- 迁移的这一部分包括手动迁移、拖放到个人OneDrive for Business，一部分通过迁移 API 执行。
    
应按照计划执行更详细的步骤或指向特定升级方向的一些链接。 MOSS 2007 计算机不应停用，为了进行比较，应维护虚拟环境;但是，当用户重定向到 SharePoint Server 2016 时，将完成升级。
  
选择方法的一个主要因素通常是升级的总成本和时间成本 (您将在 SharePoint Migration Roadmap 一文) 。 但是，提前规划将大大有助于你设置预期、做出明智的选择以及确定成功的外观。
  
## <a name="related-links"></a>相关链接

[帮助您从 Office 2007 服务器和客户端升级的资源](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft 生命周期策略和生命周期搜索](https://support.microsoft.com/lifecycle)
  
[搜索可帮助升级或迁移的 Microsoft 合作伙伴](https://partnercenter.microsoft.com/pcv/search)
