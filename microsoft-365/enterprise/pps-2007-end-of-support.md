---
title: PerformancePoint Server 2007 停止提供支持路线图
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007、ProClarity 和 SharePoint Server 2007 已到达支持的结束。 阅读本文以帮助规划 BI 解决方案升级。
ms.openlocfilehash: 4a13e6f8a40de78c0d98b03369b52a78899fc7a9
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519593"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 停止提供支持路线图

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Office 2007 服务器和应用程序已达到其支持的结尾，包括您可能在商业智能 (BI) 解决方案中使用的服务器和应用程序。 下表列出了受影响的 BI 应用程序：
  
|**Microsoft BI 应用程序**|**日期支持结束**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6。3  <br/> ProClarity SharePoint Viewer 6。3  <br/> |2017 年 7 月 11 日  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |2017 年 10 月 10 日  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |2018 年 1 月 9 日  <br/> |
   
有关详细信息，请参阅可 [帮助您从 Office 2007 服务器和客户端升级的资源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-does-end-of-support-mean"></a>*支持终止的* 含义是什么？

与大多数 Microsoft 产品一样，PerformancePoint Server 2007 SP3、ProClarity 软件和 SharePoint Server 2007 SP3 都具有支持生命周期，在此期间，Microsoft 提供了新的功能、缺陷修补程序和安全更新。 产品的生命周期通常是从产品的初始版本中持续10年的时间。 该生命周期的结束被称为产品的支持终止。 由于 ProClarity、PerformancePoint Server 和 SharePoint Server 2007 已达到其支持的结尾，Microsoft 不再提供：
  
- 可能出现的问题的技术支持。
    
- 针对发现的问题以及可能影响服务器稳定性和可用性的问题的 Bug 修补程序。
    
- 针对发现的漏洞的安全修补程序，并可能使服务器或应用程序易受安全破坏。
    
- 时区更新。
    
您安装的 ProClarity、SharePoint Server 2007 SP3 和 PerformancePoint Server 2007 SP3 仍将继续运行，即使支持已结束。 但是，强烈建议您尽快从这些应用程序迁移。
  
## <a name="what-are-my-options"></a>我的选项是什么？

自2007起对 Microsoft BI 应用程序进行了大量更改，并且有几个选项需要考虑，如下表中所汇总。
  
|**如果您使用的是 .。。**|**浏览这些选项 .。。**|**请记住这一点 .。。**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 监视 &amp; 分析功能，包括：<br/>-PerformancePoint Monitoring Server <br/>-PerformancePoint 仪表板设计器<br/>-用于呈现 PerformancePoint 仪表板、记分卡和报表的 SharePoint Services (仪表板查看器) <br/> |Excel 在 (云中或本地) 中的 **浏览器中使用 excel** 。 有关概述，请参阅 [Excel 和 Microsoft 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。<br/><br/> 云或本地) 中的 **POWER BI** (。 有关概述，请参阅 [什么是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (本地) 。 有关概述，请参阅 [SQL Server Reporting Services (SSRS) ：创建、部署和管理移动和分页报告](https://go.microsoft.com/fwlink/?linkid=841342)。 <br/><br/> **PerformancePoint Services** (本地) 。 有关概述，请参阅 [什么是 PerformancePoint Services (SharePoint Server 2010) 的新增功能 ](https://go.microsoft.com/fwlink/?linkid=841343)。 <br/> |Excel 可用作联机 (基于云的) 或本地解决方案。 Excel 可以满足许多报告和仪表板需求。  <br/><br/> Power BI 可用作联机或本地解决方案。 Power BI 不包括在 Microsoft 365 中。 不过，你可以开始使用 Power BI for free。 稍后，根据您的数据使用和业务需求，您可以使用 Microsoft 365 E5 升级到 Power BI Pro。<br/> <br/> Reporting Services 和 PerformancePoint Services 都是本地解决方案。 <br/><br/> PerformancePoint Services 在 SharePoint Server 2010、SharePoint Server 2013 和 SharePoint Server 2016 中可用。 <br/> <br/> 在 PerformancePoint Server 2007 中提供的某些功能和报告类型在 Excel、Power BI、Reporting Services 或 PerformancePoint Services 中不可用。 查看可用的功能，以确定满足你的业务需求的最佳解决方案。 <br/> |
| ProClarity 软件，包括：<br/>-ProClarity Desktop Professional<br/> -ProClarity Analytics Server<br/>-ProClarity SharePoint Viewer<br/> |**与 Microsoft 合作伙伴合作** ，确定最符合您的需求的解决方案。 访问 [Microsoft 合作伙伴中心](https://go.microsoft.com/fwlink/?linkid=841249)。 <br/><br/> 您还可以考虑在浏览器、Power BI、SQL Server Reporting Services 或 PerformancePoint Services 中使用 excel 和 Excel。  <br/> |在其他 Microsoft 产品（包括 Excel、Power BI、Reporting Services 和 PerformancePoint Services）中提供了您的 ProClarity 软件的几个但并非所有功能。  <br/> |
|SharePoint Server 2007 Kpi (也称为 MOSS Kpi)   <br/> |Excel **Services 的 excel**。 有关概述，请参阅 [excel 和 Excel Services (SharePoint Server 2013) 中的商业智能 ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |使用 SharePoint Server 2007 创建的 MOSS Kpi 可在 SharePoint Server 2010、SharePoint Server 2013 和 SharePoint Server 2016 中使用。 但不能创建新的 MOSS Kpi。  <br/> |
|Excel 2007  <br/> |**Excel** (在云或本地) 中。 有关概述，请参阅 [BI 功能 In Excel 和 Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。 <br/><br/> 云或本地) 中的 **POWER BI** (。 有关概述，请参阅 [什么是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Excel 和 Power BI 都为你的组织提供基于云的解决方案和内部部署解决方案，并支持多种数据源。  <br/> |
   
### <a name="help-selecting-a-solution"></a>帮助选择解决方案

由于提供了很多 BI 选项，因此最好确定哪个选项是最佳选择。 我们提供了可帮助的联机指南。 [有关分析和报告，请参阅选择 Microsoft 商业智能 (BI) 工具](https://go.microsoft.com/fwlink/?linkid=839877)。
  
### <a name="what-if-i-dont-upgrade-now"></a>如果现在不升级，该怎么办？

你可以选择不立即升级。 现有的服务器和应用程序将继续运行。 但由于支持已结束，你将不会收到任何进一步的更新，包括安全更新。 如果你的服务器应用程序出现问题，你将无法从 Microsoft 技术支持获得帮助。
  
## <a name="how-do-i-plan-my-upgrade"></a>如何规划升级？

在浏览完升级选项之后，下一步是准备升级计划。 以下各节包含可帮助的信息和其他资源。 有四个主要选项，包括在云中或本地使用的两个选项，以及两个仅适用于本地的选项：
  
|**选项**|**在云中还是内部部署？**|
|:-----|:-----|
|[使用 SharePoint Server (本地) 的 Excel ](#excel-with-sharepoint-server-on-premises) <br/> |两者都有  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |两者都有  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |仅本地  <br/> |
|[PerformancePoint 服务](#use-performancepoint-services-on-premises) <br/> |仅本地  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>在云中或内部部署中使用 Excel () 

使用 Excel （也称为 *Excel Services* In SharePoint Server），您可以在浏览器窗口中查看和使用工作簿，即使计算机上未安装 excel 也是如此。 您可以使用 Excel 创建报表、记分卡和仪表板。 然后，与其他人共享您的工作簿，他们可以在浏览器中使用 Excel，无论他们是在 Microsoft 365 还是本地 SharePoint Server 中使用 SharePoint Online。 您可以使用存储在本地或在云中的数据，这使您可以使用多种数据源。
  
下表比较了使用 Excel 与 Microsoft 365 结合使用 Excel 和 SharePoint Server 的主要优势。 有关详细信息，请执行以下步骤。
  
|**使用 Microsoft 365 (云中的 Excel)**|**使用 SharePoint Server (本地) 的 Excel**|
|:-----|:-----|
|**您将获得最新版本的 Excel**。 使用 Microsoft 365，你可以获得最新版本的 Excel，其中包括功能强大的新图表类型、快速轻松地创建图表和表格以及支持更多数据源的功能。 <br/> <br/> **安装更简单**。 Excel 包含在 Microsoft 365 for business 中，因此不会对你的部件进行繁重的提升。 注册并登录，你将能够更快、更高效地运行，而不是升级你的本地服务器。 <br/> <br/> **用户可以随时随地访问他们的工作簿**。 用户可以使用其计算机、智能手机和平板电脑，从任何位置安全地查看工作簿。 <br/> <br/> **还有更多！** 请参阅 [BI 功能和 Excel 和 Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。 <br/> |**管理全局设置**。 作为 SharePoint 管理员，您可以指定全局设置，如安全性、负载平衡、会话管理、工作簿缓存和外部数据连接。 <br/> <br/> **可以将 Excel services 与 PerformancePoint services 结合使用**。 您可以将 Excel Services 和 PerformancePoint Services 配置为 SharePoint Server 安装的一部分，并在 PerformancePoint 仪表板中包括 Excel Services 报表。 <br/> <br/> **还有更多！** 请参阅 [excel 和 Excel Services (SharePoint Server 2013) 中的商业智能 ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>使用 Microsoft 365 (云中的 Excel) 

如果你迁移到 Microsoft 365，你将拥有最新的服务和应用程序，包括 Excel 2016。 PerformancePoint Services 在 Microsoft 365 中不可用，因此你将使用 Excel 工作簿或其他报表替换 PerformancePoint 仪表板内容。 好消息是 Excel 2016 具有大量新图表类型，并且在 Excel 中创建引人注目的仪表板比以往更轻松。 并会定期添加新功能。 若要了解详细信息，请参阅 [Excel 2016 For Windows 中的新增功能](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)。
  
此外，如果您购买了50个以上的 Microsoft 365，Microsoft FastTrack 团队可以帮助您进行设置。 若要了解详细信息，请访问 [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)。
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>使用 SharePoint Server (本地) 的 Excel

如果升级到较新版本的 SharePoint，则可以使用 excel Services 或浏览器中的 Excel，如下所示：
  
- SharePoint Server 2010 中的 Excel Services
    
- SharePoint Server 2013 中的 Excel Services
    
- Excel （它是 Office Online Server 的一部分）独立于 SharePoint Server 2016 安装
    
您还可以在新版本的 SharePoint Server 中配置 PerformancePoint Services，并将其与 Excel 一起使用。
  
若要了解有关你的 SharePoint 升级选项的详细信息，请参阅 [Sharepoint Server 2007 end of Support 路线图](sharepoint-2007-end-of-support.md)。
  
若要了解有关 Excel Services 的详细信息，请参阅 [Excel services 概述 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841362)。
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>在云中或内部部署中使用 Power BI () 

Power BI 是一套用于分析数据和共享见解的业务分析工具。 使用 Power BI，可以使用内部部署或联机数据源创建交互式报告和仪表板。 用户可以在其计算机或移动设备上查看和使用报告和仪表板。
  
Power BI 不是 Microsoft 365 或 SharePoint Server 的一部分。 它是一个单独的服务，包括 Power BI Desktop、Power BI 网关和 Power BI 服务。 Power BI 还与 SharePoint Online 集成。 你可以立即开始使用 Power BI 免费版。 根据您的数据使用和业务需求，您可以在以后通过 Microsoft 365 E5 升级到 Power BI Pro。 若要了解详细信息，请参阅 [什么是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>使用 Reporting Services (本地) 

SQL Server Reporting Services 提供了一个强大的报告解决方案。 您可以在本机模式或 SharePoint 集成模式下配置 Reporting Services。 您可以使用多种不同的工具创作报告，包括报告设计器、报告生成器和 Power View。 使用最新版本的 SQL Server，您还可以使用 SQL Server 移动报表发布服务器来提供可扩展到任何屏幕大小的报告。 这允许查看者使用其移动设备上的报告。 若要了解详细信息，请参阅 [SQL Server Reporting Services (SSRS) ：创建、部署和管理移动和分页报告](https://go.microsoft.com/fwlink/?linkid=841342)。
  
### <a name="use-performancepoint-services-on-premises"></a> (本地) 使用 PerformancePoint Services

PerformancePoint Server 2007 与 SharePoint Server 2007 分开销售。 从 SharePoint Server 2010 开始，PerformancePoint Services 是 SharePoint Server 中的服务应用程序。 因此，无需购买单独的服务器许可证或硬件即可使用 PerformancePoint Services。
  
若要从 PerformancePoint Server 2007 移动到 PerformancePoint Services，请转到 SharePoint Server 的更新版本并配置 PerformancePoint Services。 您移动的 SharePoint Server 版本决定了您是否可以将现有的仪表板内容从 PerformancePoint Server 2007 导入到 PerformancePoint Services。
  
- 如果升级到 SharePoint Server 2010，则可以将 PerformancePoint 仪表板内容从 PerformancePoint Server 2007 导入 SharePoint Server 2010 中的 PerformancePoint Services。 若要了解详细信息，请参阅 [导入向导：将 PerformancePoint Server 2007 内容重设为 SharePoint server 2010](https://go.microsoft.com/fwlink/?linkid=838873)。
    
- 如果移动到 SharePoint Server 2013 或 SharePoint Server 2016，则很可能需要创建新的仪表板内容 (数据源、报表、记分卡和仪表板页面) 。
    
若要开始了解 PerformancePoint Services 升级计划，请参阅以下资源：
  
- [SharePoint Server 2007 结束支持路线图](sharepoint-2007-end-of-support.md)
    
- 当您知道要移动到的 SharePoint 版本时，请参阅 PerformancePoint Services 的相应文章：
    
  - [规划 PerformancePoint Services (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [SharePoint Server 2013 中的 PerformancePoint Services 概述](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [SharePoint Server 2016 中的 PerformancePoint Services 概述](https://go.microsoft.com/fwlink/?linkid=874704)
    
升级到 PerformancePoint Services 时，将获得几种新的功能和增强功能。 PerformancePoint Services 提供改进的记分卡;新的可视化项，如 "分解树" 和 "KPI 详细信息" 报表;更多图表类型;更好的时间智能筛选功能;和改进的可访问性合规性。 若要了解详细信息，请参阅 [什么是 PerformancePoint Services (SharePoint Server 2010) 的新增功能 ](https://go.microsoft.com/fwlink/?linkid=841343)。
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>在哪里可以获取有关升级的帮助？

无论是本地升级还是迁移到 Microsoft 365，我们都建议您与 Microsoft 合作伙伴合作。 合格的合作伙伴可帮助您确定最能满足您的业务需求和帮助您的部署的解决方案。 访问 [Microsoft 合作伙伴中心](https://go.microsoft.com/fwlink/?linkid=841249)，并使用搜索筛选器查找解决方案提供商。
  
## <a name="related-topics"></a>相关主题

[可帮助您从 Office 2007 服务器和客户端进行升级的资源](upgrade-from-office-2007-servers-and-products.md)