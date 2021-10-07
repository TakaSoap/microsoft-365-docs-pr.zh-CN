---
title: Project Server 2007 停止提供支持路线图
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: 2017 年 10 月 10 日，Project Server 2007、Project Portfolio Server 和 Project 2007 的支持结束。 使用本文现在规划升级。
ms.openlocfilehash: c492c7154006a139589cff1c768dd77c13804c07
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168454"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 停止提供支持路线图

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

2017 年Office 2007 服务器和应用程序的支持结束，您需要考虑迁移计划。 如果您当前使用的是 Project Server 2007 和相关产品，请注意以下停止提供支持的日期：
  
|**产品**|**支持结束日期**|
|:-----|:-----|
|Project Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|ProjectPortfolio Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Standard  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Professional  <br/> |2017 年 10 月 10 日  <br/> |
   
有关 2007 Office停用状态的信息，请参阅从 Office [2007 服务器和客户端产品升级](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-does-end-of-support-mean"></a>停止 *提供支持意味着什么* ？

大多数 Microsoft 产品都有一个支持生命周期，在此期间它们获取新功能、Bug 修复、安全修补程序等。 此生命周期通常自产品初始发布起持续 10 年。 此生命周期的结束称为产品的停止支持。 由于 Project Server 2007 于 2017 年 10 月 10 日终止支持，因此 Microsoft 不再提供：
  
- 针对可能会出现的问题的技术支持。
    
- 对可能会影响服务器稳定性和可用性的问题进行 Bug 修复。
    
- 针对可能导致服务器易受安全漏洞的漏洞进行安全修复。
    
- 时区更新。
    
安装 Project Server 2007 将在此日期之后继续运行。 但由于前面列出的更改，我们强烈建议您尽快从 Project Server 2007 迁移。
  
## <a name="what-are-my-options"></a>我的选项是什么？

如果使用的是 Project Server 2007，则需要了解迁移选项，包括：
  
- 迁移到Project Online
    
- 迁移到较新的本地版本的 Project Server (最好Project Server 2016) 
    
|**为什么我想要迁移到Project Online**|**为什么我想要迁移到Project Server 2016**|
|:-----|:-----|
| 我拥有移动用户。  <br/> <br/>迁移成本是硬件、 (、小时数和实现迁移成本的一) 。 <br/><br/>  迁移后，维护环境的成本是一个主要 (，例如自动更新、保证正常运行时间等) 。  <br/> | 业务规则限制我在云中运营业务。<br/><br/>  我需要控制环境更新。  |
   
> [!NOTE]
> 有关从 Office 2007 服务器迁移的选项的详细信息，请参阅帮助您从[Office 2007 服务器和客户端升级的资源](upgrade-from-office-2007-servers-and-products.md)。 请注意，Project Server 不支持混合配置，因为 Project Server 和 Project Online 无法共享同一资源库。 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>从 Project Server 2007 迁移时的重要注意事项

在计划从 Project Server 2007 迁移时，请考虑以下事项：
  
- **从 Microsoft** 合作伙伴获取帮助 - 从 Project Server 2007 进行升级可能充满挑战，并且需要进行很多准备和规划。 如果您不是最初在 Server 2007 中设置Project可能尤其具有挑战性。 幸运的是，无论你计划迁移到 microsoft 还是 Project Server 2016，microsoft 合作伙伴Project Online。 在 Microsoft 合作伙伴中心中搜索 Microsoft 合作伙伴以帮助进行 [迁移](https://go.microsoft.com/fwlink/p/?linkid=841249)。 搜索术语"*金牌Project* 项目组合管理"以查看具有金牌和项目组合管理专业知识的所有 Microsoft 合作伙伴Project。 
    
- **规划自定义项**- 迁移到 Project Server 2007 环境时，在 Project Server 2007 环境中进行的许多自定义Project Server 2016 Project Online。 版本之间的服务器Project存在显著差异。 受支持的所需操作系统、数据库服务器和客户端 Web 浏览器也有所不同。 规划如何测试或重新生成新环境的自定义项。 规划还提供了一个很好的机会来考虑是否仍然需要每个自定义项。 有关详细信息，请参阅[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)。 
    
- **时间和耐心**- 升级规划、执行和测试需要时间和精力，尤其是在升级到 Project Server 2016。 例如，如果您从 Project Server 2007 迁移到 Project Server 2016，则首先需要迁移到 Project Server 2010，检查数据，然后在迁移到每个后续版本时执行相同操作。 你可能需要与 Microsoft 合作伙伴联系，以估计需要多久以及需要多少费用。
    
## <a name="migrate-to-project-online"></a>迁移到Project Online

如果选择从 Project Server 2007 迁移到 Project Online，可以执行以下操作以手动迁移项目计划数据：
  
1. 将项目计划从 Project Server 2003 保存为 .mpp 格式。
    
2. 在 Project Professional 2013、Project Professional 2016 或 Project Online 桌面客户端中，打开每个 .mpp 文件，然后保存该文件并将其发布到Project Online。
    
您可以在 Project Online 中Microsoft Project Web App (PWA) 配置。 例如，重新创建任何所需的自定义域或企业日历。 Microsoft 合作伙伴也可以帮助完成此过程。
  
关键资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Online 入门](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |如何设置和使用Project Online <br/> |
|[Project Online服务说明](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |有关可用的不同Project Online计划的信息 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>迁移到较新的本地版本的 Project Server

我们强烈建议您迁移到新用户，以获得最佳价值和Project Online。 但我们还了解到，某些组织需要将项目数据保留在本地环境中。 如果选择将项目数据保留在本地，可以将 Project Server 2007 环境迁移到 Project Server 2010、Project Server 2013 或 Project Server 2016。
  
如果您无法迁移到 Project Online，建议您迁移到 Project Server 2016。 Project Server 2016包括以前版本 Project Server 的所有功能。 虽然某些功能仅在 Project Online 中可用，但它最匹配 Project Online。
  
每次迁移后，应检查数据是否成功迁移。
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>如何迁移到Project Server 2016？

Project Server 2007 和 Project Server 2016 之间的体系结构差异会阻止直接迁移路径。 因此，您必须将 Project Server 2007 数据迁移到 Project Server 的每个连续版本，直到达到Project Server 2016。
  
请按照以下步骤操作Project Server 2016：
  
1. 从 Project Server 2007 迁移到 Project Server 2010。
    
2. 从 Project Serve 2010 迁移到 Project Server 2013。
    
3. 从 Project Server 2013 迁移到 Project Server 2016。
    
每次迁移后，请确保数据已成功迁移。
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>步骤 1：从 Project Server 2007 迁移到 Project Server 2010

有关从 Project Server 2007 升级到 Project Server 2010 需要执行哪些操作的全面说明，请参阅 Upgrade [to Project Server 2010。](/previous-versions/office/project-server-2010/gg502590(v=office.14))
  
关键资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[ProjectServer 2010 升级概述](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |从 Project Server 2007 升级到 Project Server 2010 需要执行哪些操作的高层次视图 <br/> |
|[计划升级到 Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |从 Project Server 2007 升级到 Project Server 2010 时的计划注意事项，包括系统要求  <br/> |
   
#### <a name="how-do-i-upgrade"></a>如何升级？

有关详细信息，请参阅[Upgrade to Project Server 2010。](/previous-versions/office/project-server-2010/gg502590(v=office.14)) 但是，必须了解有两种不同的方法可用于升级：
  
- **数据库附加升级：** 此方法仅升级环境的内容，而不是配置设置。 如果要从仅支持 32 位服务器操作系统Office Project部署在硬件上的 Office Project Server 2007 升级，则是必需的。 有两种类型的数据库附加升级方法：
    
  - 完整数据库 ***附加*** 升级 - 迁移存储在 Office Project Server 2007 数据库中的项目数据，以及存储在 Microsoft Project 内容数据库中的 SharePoint Web App 网站数据。
    
  - **数据库附加 *核心升级***- 仅迁移存储在 Project 服务器数据库中的项目数据。
    
- **就地升级**：按固定顺序对现有硬件升级服务器场和服务器场中所有内容的配置数据。 启动升级过程时，安装程序会使整个服务器场脱机。 在升级Microsoft Project网站和 Web App 网站之前不可用，然后安装程序将重新启动服务器。 开始就地升级后，无法暂停升级或回滚到以前的版本。 最好制作生产环境的镜像，并就地升级到此环境，而不是在生产环境中。 
    
其他资源：
  
- [用于 Microsoft Project Server 2010 升级的 SuperFlow](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [从 Project Server 2007 迁移到 Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Project Web App Web 部件的升级注意事项](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project软件开发工具包 (SDK) ](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>步骤 2：迁移到 Project Server 2013

确认数据已成功迁移后，下一步是迁移到 Project Server 2013。
  
有关从 Project Server 2010 升级到 Project Server 2013 需要执行哪些操作的全面说明，请参阅 Upgrade [to Project Server 2013。](/project/upgrade-to-project-server-2016) 
  
关键资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Server 2013 升级过程概述](/project/upgrade-to-project-server-2016) <br/> |从 Project Server 2010 升级到 Project Server 2013 需要执行哪些操作概述  <br/> |
|[计划升级到 Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |从 Project Server 2010 升级到 Project Server 2013 时的计划注意事项，包括系统要求 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>升级到此版本的要了解的一些信息

[Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade)升级的新增功能介绍了此版本的升级的重要更改。 最值得注意的是： 
  
- 没有到 Project Server 2013 的就地升级。 数据库附加方法是从 Project Server 2010 升级到 Project Server 2013 的唯一受支持方法。
    
- 升级过程不仅会将 Project Server 2010 数据转换为 Project Server 2013 格式，而且还会将四个 Project Server 2010 数据库合并为一个 Project Web App 数据库。
    
- 在 2013 版本中，SharePoint Server 和 Project Server 都更改为基于声明的身份验证。 如果使用的是经典身份验证，则需要在升级时考虑此因素。 有关详细信息，请参阅[在 SharePoint 2013 中从经典模式身份验证迁移到基于声明的身份验证](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)。
    
其他资源：
  
- [升级到 Project Server 2013 的流程概述](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [升级数据库和 Project Web App 网站集 (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project服务器升级过程图](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [通过 8 个简单步骤Project到 Server 2010 到 2013 的出色的数据库合并](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>步骤 3：迁移到Project Server 2016

验证数据已成功迁移后，下一步是迁移到 Project Server 2016。
  
有关从 Project Server 2013 升级到 Project Server 2016 需要执行哪些操作的全面说明，[请参阅升级到](//project/upgrading-to-project-server-2016)Project Server 2016 。
  
关键资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Server 2016 升级流程概述](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |从 Project Server 2013 升级到 Project Server 2016 <br/> |
|[规划升级到 Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |从 Project Server 2013 升级到 Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>升级到此版本的要了解的一些信息

[有关升级的一些Project Server 2016](/project/plan-for-upgrade-to-project-server-2016)会告诉您此版本的升级的一些重要更改，其中包括：
  
- 创建要Project Server 2016 Project Server 2013 数据的 Project Server 2016 环境时，Project Server 2016 Server 2016 中包含 SharePoint 安装文件。 有关详细信息，请参阅部署[Project Server 2016。](/project/deploy-project-server-2016)
    
- 资源计划在资源计划中Project Server 2016。 你的 Project Server 2013 资源计划将迁移到 Project Server 2016 和 Project Online 中的资源Project Online。 有关详细信息 [，请参阅概述：](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 资源活动。 
    
## <a name="migrate-from-portfolio-server-2007"></a>从 Portfolio Server 2007 迁移

ProjectPortfolio Server 2007 与 Project Server 2007 一起用于项目组合策略、优先顺序和优化。 在此版本之后，Project创建项目组合服务器的其他版本。 但是，项目组合管理功能在 Project Server 2016 高级版 版本中Project Online。 但是，Project Portfolio Server 2007 的数据无法迁移到其中一个。 必须重新创建业务驱动因素等数据。
  
其他资源：
  
- [Project Online服务说明：](/office365/servicedescriptions/project-online-service-description/project-online-service-description)请参阅项目组合和项目组合Project Server 2016 Project Online 高级版。
    
- [Microsoft Office Project Portfolio Server 2007 迁移指南。](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>相关主题

[SharePointServer 2007 停止提供支持路线图](sharepoint-2007-end-of-support.md)
  
[帮助您从 Office 2007 服务器和客户端升级的资源](upgrade-from-office-2007-servers-and-products.md)
