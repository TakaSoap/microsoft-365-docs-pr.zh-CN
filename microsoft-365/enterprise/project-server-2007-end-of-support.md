---
title: Project Server 2007 停止提供支持路线图
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: 在2017年10月10日，支持 Project Server 2007、项目组合服务器和项目2007。 现在可以使用本文规划升级。
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519795"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 停止提供支持路线图

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

在2017中，Office 2007 服务器和应用程序的支持已结束，您需要考虑迁移计划。 如果你当前使用的是 Project Server 2007 和相关产品，请注意以下支持结束的日期：
  
|**产品**|**支持结束日期**|
|:-----|:-----|
|Project Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|项目组合服务器2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Standard  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 专业版  <br/> |2017 年 10 月 10 日  <br/> |
   
有关 Office 2007 服务器即将退休的详细信息，请参阅 [从 Office 2007 服务器和客户端产品升级](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-does-end-of-support-mean"></a>*支持终止的* 含义是什么？

大多数 Microsoft 产品都有支持生命周期，在此期间，他们将获得新的功能、缺陷修补程序、安全修补程序等。 此生命周期通常是从产品的初始版本中持续10年的时间。 此生命周期的结束被称为产品的支持终止。 由于 Project Server 2007 在2017年10月10日已达到其支持的结束时间，Microsoft 不再提供：
  
- 可能出现的问题的技术支持。
    
- 针对可能会影响服务器稳定性和可用性的问题的 Bug 修补程序。
    
- 安全修补程序可能会使服务器易受安全漏洞破坏。
    
- 时区更新。
    
在此日期之后，Project Server 2007 的安装将继续运行。 但由于前面列出的更改，强烈建议您尽早从 Project Server 2007 迁移。
  
## <a name="what-are-my-options"></a>我的选项是什么？

如果使用的是 Project Server 2007，您需要浏览迁移选项，其中包括：
  
- 迁移到 Project Online
    
- 迁移到 Project Server 的更新的本地版本 (最好的 Project Server 2016) 
    
|**为什么我更喜欢迁移到 Project Online**|**为什么我更喜欢迁移到 Project Server 2016**|
|:-----|:-----|
| 我有移动用户。  <br/> <br/>迁移成本是一个重要的顾虑 (硬件、软件、时间和实现) 的努力。 <br/><br/>  迁移后，维护我的环境的成本是一个主要问题 (例如，自动更新、保证的正常运行时间等) 。  <br/> | 业务规则限制我在云中运行我的业务。<br/><br/>  我需要控制环境的更新。  |
   
> [!NOTE]
> 有关从 Office 2007 服务器移动的选项的详细信息，请参阅可 [帮助您从 office 2007 服务器和客户端进行升级的资源](upgrade-from-office-2007-servers-and-products.md)。 请注意，Project Server 不支持混合配置，因为 Project Server 和 Project Online 无法共享同一个资源池。 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>从 Project Server 2007 迁移时的重要注意事项

当您计划从 Project Server 2007 迁移时，请考虑以下事项：
  
- **从 Microsoft 合作伙伴获取帮助** -从 Project Server 2007 升级可能会非常困难，并且需要进行大量准备和规划。 如果您不是最初设置 Project Server 2007 的人，则可能尤其有挑战性。 幸运的是，有一些 Microsoft 合作伙伴可以提供帮助，无论您计划迁移到 Project Server 2016 还是 Project Online。 搜索 Microsoft 合作伙伴以帮助你在 [Microsoft 合作伙伴中心](https://go.microsoft.com/fwlink/p/?linkid=841249)上进行迁移。 在 "  *黄金项目" 和 "项目组合管理* " 一词中搜索，以查看在 Project 中具有专业技能的所有 Microsoft 合作伙伴的列表。 
    
- **规划自定义项** -当迁移到 project server 2016 或 project Online 时，在 project server 2007 环境中所做的许多自定义设置可能不起作用。 在不同版本的 Project Server 体系结构中有很大差异。 受支持的必需的操作系统、数据库服务器和客户端 web 浏览器也不同。 规划如何测试或重新生成新环境的自定义项。 规划还提供了一个很好的机会来考虑是否仍需要每个自定义项。 有关详细信息，请参阅[Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061)。 
    
- **时间和耐心** 升级规划、执行和测试需要花费时间和精力，尤其是在升级到 Project Server 2016 时。 例如，如果从 Project Server 2007 迁移到 Project Server 2016，首先需要迁移到 Project Server 2010，检查数据，然后在迁移到每个后续版本时执行相同的操作。 您可能需要与 Microsoft 合作伙伴核实，以获取估计所需时间和成本。
    
## <a name="migrate-to-project-online"></a>迁移到 Project Online

如果选择从 Project Server 2007 迁移到 Project Online，则可以执行以下操作来手动迁移项目计划数据：
  
1. 将项目计划从 Project Server 2003 保存到. mpp 格式。
    
2. 在 Project Professional 2013、Project Professional 2016 或 Project Online 桌面客户端中，打开每个 mpp 文件，然后将其保存并发布到 Project Online。
    
您可以在 Project Online 中手动创建 Microsoft Project Web App (PWA) 配置。 例如，重新创建任何所需的自定义域或企业日历。 Microsoft 合作伙伴也可以帮助此过程。
  
主要资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Online 入门](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |如何设置和使用 Project Online <br/> |
|[Project Online 服务说明](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |有关可供您使用的不同 Project Online 计划的信息 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>迁移到 Project Server 的更新的本地版本

我们强烈认为，通过迁移到 Project Online，你可以获得最佳价值和用户体验。 但我们还了解，某些组织需要将项目数据保留在本地环境中。 如果选择将您的项目数据保留在本地，则可以将 Project Server 2007 环境迁移到 Project Server 2010、Project Server 2013 或 Project Server 2016。
  
如果无法迁移到 Project Online，我们建议您迁移到 Project Server 2016。 Project Server 2016 包含早期版本的 Project Server 的所有功能。 虽然某些功能仅在 Project Online 中可用，但它与 Project Online 的体验最接近。
  
每次迁移后，应检查数据是否已成功迁移。
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>如何迁移到 Project Server 2016？

Project Server 2007 与 Project Server 2016 之间的体系结构差异阻止了直接迁移路径。 因此，您必须将 Project Server 2007 数据迁移到 Project Server 的每个后续版本，直到达到 Project Server 2016。
  
请按照以下步骤到 Project Server 2016：
  
1. 从 Project Server 2007 迁移到 Project Server 2010。
    
2. 从 Project for 2010 to Project Server 2013 进行迁移。
    
3. 从 Project Server 2013 迁移到 Project Server 2016。
    
在每次迁移之后，请确保成功迁移数据。
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>步骤1：从 Project Server 2007 迁移到 Project Server 2010

有关从 Project Server 2007 升级到 Project Server 2010 时需要执行的操作的综合说明，请参阅 [upgrade To Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)。
  
主要资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Server 2010 升级概述](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |从 Project Server 2007 升级到 Project Server 2010 需要执行的操作的高级视图 <br/> |
|[计划升级到 Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |从 Project Server 2007 升级到 Project Server 2010 时的规划注意事项，包括系统要求  <br/> |
   
#### <a name="how-do-i-upgrade"></a>如何升级？

有关详细信息，请参阅 [Upgrade To Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)。 但请务必了解，您可以使用两种不同的方法来进行升级：
  
- **数据库附加升级：** 此方法仅升级您的环境的内容，而不是配置设置。 如果您是从部署在仅支持32位服务器操作系统的硬件上的 Office Project Server 2007 进行升级，则需要使用此方法。 有两种类型的数据库附加升级方法：
    
  - **数据库附加 *完全升级*** -迁移存储在 Office project Server 2007 数据库中的项目数据，以及存储在 SharePoint 内容数据库中的 Microsoft project Web App 网站数据。
    
  - **数据库附加 *核心升级*** -仅迁移存储在 project Server 数据库中的项目数据。
    
- **就地升级**：服务器场的配置数据和服务器场中的所有内容都在现有硬件上按固定顺序进行升级。 在开始升级过程时，安装程序会将整个服务器场脱机。 在升级完成之前，网站和 Microsoft Project Web App 网站不可用，然后安装程序将重新启动服务器。 开始就地升级后，将无法暂停升级或回滚到以前的版本。 最好是制作生产环境的镜像映像，并执行到此环境的就地升级，而不是生产环境中。 
    
其他资源：
  
- [用于 Microsoft Project Server 2010 升级的工作流](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [从 Project Server 2007 迁移到 Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Project Web App Web 部件的升级注意事项](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project 软件开发工具包 (SDK) ](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>步骤2：迁移到 Project Server 2013

在验证数据是否已成功迁移之后，下一步是迁移到 Project Server 2013。
  
有关从 Project Server 2010 升级到 Project Server 2013 时需要执行的操作的综合说明，请参阅 [upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)。 
  
主要资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Server 2013 升级过程概述](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |从 Project Server 2010 升级到 Project Server 2013 所需的操作概述  <br/> |
|[计划升级到 Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |从 Project Server 2010 升级到 Project Server 2013 时的规划注意事项，包括系统要求 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>升级到此版本需要了解的事项

[Project Server 2013 中的新增功能升级](https://go.microsoft.com/fwlink/p/?linkid=841824) 介绍了此版本的升级的重要更改。 最明显的包括： 
  
- 没有到 Project Server 2013 的就地升级。 数据库附加方法是从 Project Server 2010 升级到 Project Server 2013 的唯一受支持的方法。
    
- 升级过程不仅会将 Project Server 2010 数据转换为 Project Server 2013 格式，还会将四个 Project Server 2010 数据库合并到一个 Project Web App 数据库中。
    
- 在2013版本中，SharePoint Server 和 Project Server 都更改为基于声明的身份验证。 如果使用的是经典身份验证，则需要考虑升级的这一因素。 有关详细信息，请参阅[在 SharePoint 2013 中从经典模式身份验证迁移到基于声明的身份验证](https://go.microsoft.com/fwlink/p/?linkid=841825)。
    
其他资源：
  
- [升级到 Project Server 2013 的流程概述](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [升级数据库和 Project Web App 网站集 (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server 升级过程关系图](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [在8个简单的步骤中执行大量数据库整合（Project Server 2010 至2013迁移）](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>步骤3：迁移到 Project Server 2016

在验证数据是否已成功迁移之后，下一步是迁移到 Project Server 2016。
  
有关从 Project Server 2013 升级到 Project Server 2016 时需要执行的操作的综合说明，请参阅 [upgrade To Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016)。
  
主要资源：
  
|**Resource**|**说明**|
|:-----|:-----|
|[Project Server 2016 升级流程概述](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |从 Project Server 2013 升级到 Project Server 2016 所需的操作概述 <br/> |
|[规划升级到 Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |从 Project Server 2013 升级到 Project Server 2016 的规划注意事项 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>升级到此版本需要了解的事项

[您需要了解的有关 Project Server 2016 升级的相关内容](https://go.microsoft.com/fwlink/p/?linkid=841827) 会告诉您对此版本的升级有一些重要更改，其中包括：
  
- 当您创建要将 Project server 2013 数据迁移到的 Project Server 2016 环境时，Project Server 2016 安装文件包含在 SharePoint Server 2016 中。 有关详细信息，请参阅 [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)。
    
- 资源计划在 Project Server 2016 中已被弃用。 您的 Project Server 2013 资源计划将迁移到 Project Server 2016 和 Project Online 中的资源预订。 有关详细信息，请参阅 [概述：资源预订](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。 
    
## <a name="migrate-from-portfolio-server-2007"></a>从项目组合服务器2007迁移

项目组合服务器2007与 Project Server 2007 结合使用，以实现项目组合策略、优先顺序和优化。 在此版本之后，不会创建任何其他版本的 Project 项目组合服务器。 但是，项目组合管理功能在 Project Server 2016 和 Project Online 的 Premium 版本中可用。 但不能将来自项目组合服务器2007的数据迁移到其中之一。 需要重新创建业务驱动因素等数据。
  
其他资源：
  
- [Project Online 服务说明：](https://go.microsoft.com/fwlink/p/?linkid=841280) 请参阅 Project Server 2016 和 Project Online 高级版中包含的项目组合管理功能。
    
- [Microsoft Office Project 项目组合服务器2007迁移指南。](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>相关主题

[SharePoint Server 2007 结束支持路线图](sharepoint-2007-end-of-support.md)
  
[可帮助您从 Office 2007 服务器和客户端进行升级的资源](upgrade-from-office-2007-servers-and-products.md)
  
