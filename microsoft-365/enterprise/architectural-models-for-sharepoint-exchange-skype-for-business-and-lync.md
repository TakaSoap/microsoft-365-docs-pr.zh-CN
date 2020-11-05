---
title: SharePoint、Exchange、Skype for Business 和 Lync 的体系结构模型
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: 获取介绍 SharePoint、Exchange、Skype for Business 和 Lync 的体系结构模型、部署和平台选项的 IT 海报。
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919816"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>SharePoint、Exchange、Skype for Business 和 Lync 的体系结构模型

本文中的 IT 海报介绍了 SharePoint、Exchange、Skype for Business 和 Lync 的体系结构模型和部署选项。 它们还提供了在 Microsoft Azure 中部署 SharePoint 的设计信息。
  
通过使用 Microsoft 365，可以通过云提供熟悉的协作和通信服务。 在少数例外情况下，无论您是在维护本地部署还是使用 Microsoft 365，用户体验都保持不变。 

此统一的用户体验会使在何处放置每个工作负荷的决策复杂化。 此外，它还会引发问题：
  
- 如何选择单个工作负载的平台？
    
- 将任何服务保留在内部部署是否有意义？
    
- 在什么情况下适合使用混合部署？
    
- Azure 如何适应图片？
    
- Azure 支持哪些配置的 Office server 工作负荷？
    
> [!TIP]
> 本文中的大多数海报都以多种语言提供。 可用的语言包括中文、英语、法语、德语、意大利语、日语、朝鲜语、葡萄牙语、俄语和西班牙语。 若要下载其中一种语言的海报，请在海报缩略图图像下，选择 " **更多语言** "。
  
请将你的想法告诉我们！ 在 [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com)向我们发送电子邮件。 
  
使用以下链接获取所需的海报：
  
- **体系结构模型** ：使用这些资源可确定适用于 SharePoint 2016 和 Skype for business 2015 的理想平台和配置。
    
  - [Microsoft SharePoint 2016 体系结构模型](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016 数据库](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype for Business 2015 体系结构模型](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **平台** ：使用这些资源可确定适用于 SharePoint 2013、Exchange 2013 和 Lync 2013 的理想平台和配置。
    
  - [SharePoint 2013 平台选项](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 平台选项](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013 平台选项](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Azure 中的 SharePoint server 2013** ：使用这些 IT 海报在 azure 基础结构服务中设计和配置 sharepoint server 2013 工作负荷。
    
  - [使用 SharePoint Server 2013 的 Azure 中的 Internet 站点](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [设计示例： Azure for SharePoint 2013 中的 Internet 站点](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint 灾难恢复到 Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>体系结构模型海报

SharePoint 2016 和 Skype for business 2015 的 IT 海报提供了一种在易于打印的格式中比较部署方法的方法。 海报列出了所有配置或平台选项。 它们为每个选项提供了以下信息：
  
- **概述** ：平台的简短摘要，包括概念图。
    
- **最适用于** ：理想情况下适合于平台的常见方案。
    
- **许可证要求** ：部署所需的许可证。
    
- **体系结构任务** ：需要作为架构师做出的决策。
    
- **It 专业人员任务或责任** ： it 员工规划所需的日常职责。
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 体系结构模型

|Item|说明|
|---|---|
|[![SharePoint Server 2016 体系结构模型海报的缩略图。](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=52650)|此 IT 海报介绍了业务决策制定者和解决方案架构师需要了解的 SharePoint Online、Azure 和 SharePoint 本地配置。 <br/><br/> - **SharePoint Online (SaaS)** ：使用 SharePoint 通过软件作为服务 (SaaS) 订阅模型。 <br/> - **SharePoint 混合** ：按你自己的步调将 SharePoint 网站和应用移到云。 <br/> - **Azure 中的 SharePoint (IaaS)** ：将本地环境扩展到 Azure，并在其中部署 sharepoint 2016 服务器。 对于高可用性或灾难恢复环境和开发/测试环境，建议 (此模型。 )  <br/> - **Sharepoint 本地部署** ：规划、部署、维护和自定义你维护的数据中心中的 sharepoint 环境。|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016 数据库

|Item|说明|
|---|---|
|[![SharePoint Server 2016 数据库海报的缩略图。](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=55041)|此 IT 海报是 SharePoint Server 2016 数据库的快速参考。 你将看到每个数据库的详细信息： <br/><br/> - 大小 <br/> - 扩展指南 <br/> - I/O 模式 <br/> - 要求： <br/><br/>  第一个页面显示 SharePoint 系统数据库和包含多个数据库的服务应用程序。 第二页显示了具有单个数据库的所有服务应用程序。 <br/><br/>  有关详细信息，请参阅 [SharePoint Server 2016 中的数据库类型和说明](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions)。|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype for Business 2015 体系结构模型

|Item|说明|
|---|---|
|[![Skype for Business 体系结构模型海报的缩略图。](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=55022)|此海报介绍了 Skype for Business Online、内部部署、混合和云专用分支 exchange (PBX) 。 此外，还介绍了业务决策制定者和解决方案架构师需要了解的与 Exchange 和 SharePoint 配置的集成。 <br/><br/> 海报面向 IT 专业人员，以了解可供 Skype for business Online 和 Skype for business 内部部署使用的基本体系结构模型的认识。 <br/><br/>从最适合您的组织需求和规划的配置开始。 考虑并根据需要使用其他配置。 例如，您可能需要考虑与 Exchange 和 SharePoint 集成，或者考虑利用 Microsoft 云 PBX 产品的解决方案。|
   
## <a name="platform-options-posters"></a>平台选项海报

SharePoint 2013、Exchange 2013 和 Lync 2013 的 IT 海报提供了一种快速比较部署方法的方法。 每个海报都会列出所有配置或平台选项。 它提供了每个选项的以下信息：
  
- **概述** ：平台的简短摘要，包括概念图。
    
- **最适用于** ：理想情况下适合于平台的常见方案。
    
- **许可证要求** ：部署所需的许可证。
    
- **体系结构任务** ：需要作为架构师做出的决策。
    
- **It 专业人员任务或责任** ： it 员工规划所需的日常职责。
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013 平台选项

|Item|说明|
|---|---|
|[![SharePoint 2013 平台选项海报的缩略图图像。](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=40332)|对于业务决策者和设计师，此海报显示了 SharePoint 2013 的平台选项、Microsoft 365 中的 SharePoint、microsoft 365、Azure 和仅本地部署中的本地混合。 其中包括每个体系结构的概述、建议、许可证要求以及每个平台的架构师和 IT 专业人员任务的列表。 该海报突出显示了 Azure 上的几个 SharePoint 解决方案。|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013 平台选项

|Item|说明|
|---|---|
|[![Exchange 平台选项海报的缩略图图像。](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=42676)|对于业务决策者和架构师，本海报介绍了 Exchange 2013 的平台选项。 客户可以从使用 Microsoft 365 的 Exchange Online、混合 Exchange、Exchange Server 本地和托管 Exchange 中进行选择。 海报详细介绍了每个体系结构选项，包括每个体系结构的理想方案、许可证要求和 IT 专业人员职责。|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013 平台选项

|Item|说明|
|---|---|
|[![Lync 2013 平台选项海报的缩略图。](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=41677)|对于业务决策者和架构师，本海报介绍了 Lync 2013 的平台选项。 客户可以使用 Microsoft 365、混合 Lync、Lync Server 本地和托管 Lync 从 Lync Online 中进行选择。 IT 海报详细介绍了每个体系结构选项，包括每个体系结构的理想方案、许可证要求和 IT 专业人员职责。|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Azure 解决方案中的 SharePoint 海报

Azure 中的 SharePoint 的 IT 海报显示了使用 SharePoint Server 2013 的基于 Azure 的解决方案。
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Microsoft Azure 中使用 SharePoint Server 2013 的 Internet 站点

|Item|说明|
|---|---|
|[![使用 SharePoint Server 2013 海报的 Azure 中的 Internet 站点的图像。](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=41992)|此海报概括介绍了 Azure 中面向 internet 的网站的关键设计活动和建议体系结构。  <br/><br/> 有关详细信息，请参阅以下文章：  <br/><br/> - [使用 SharePoint Server 2013 的 Azure 中的 Internet 站点](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [适用于 SharePoint 2013 的 Azure 体系结构](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Azure for SharePoint 2013 中的 Internet 站点

|Item|说明|
|---|---|
|[![Microsoft Azure for SharePoint Server 2013 海报中的 Internet 网站的图像。](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=41991)|使用此设计示例作为 Azure 中使用 SharePoint Server 2013 的面向 internet 的网站体系结构的起始点。 <br/><br/> 有关详细信息，请参阅以下文章：  <br/><br/> - [使用 SharePoint Server 2013 的 Azure 中的 Internet 站点](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [适用于 SharePoint 2013 的 Azure 体系结构](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>SharePoint 灾难恢复到 Microsoft Azure

|Item|说明|
|---|---|
|[![SharePoint 灾难恢复过程到 Azure 的海报的图像。](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [更多语言](https://www.microsoft.com/download/details.aspx?id=41993)|此 IT 海报显示 Azure 中的灾难恢复环境的体系结构原则。 <br/><br/> 有关详细信息，请参阅以下文章：  <br/><br/> - [Azure 中的 SharePoint Server 2013 灾难恢复](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [适用于 SharePoint 2013 的 Azure 体系结构](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>另请参阅

- [Microsoft 365 解决方案和体系结构中心](../solutions/solution-architecture-center.md)
  
- [Microsoft 云体系结构模型](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 测试实验室指南](m365-enterprise-test-lab-guides.md)
  
- [混合解决方案](hybrid-solutions.md)

