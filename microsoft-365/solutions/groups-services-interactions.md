---
title: 组服务交互
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 组服务交互
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613222"
---
# <a name="groups-services-interactions"></a>组服务交互

Microsoft 365 组为 Microsoft 365 平台中的大量服务和工作负载提供了一个通用结构，以便为最终用户提供连接体验。 在其核心中，有一个 Microsoft 365 组可提供：

- 一种管理成员身份 (Azure AD 的方法) 
- 邮件和对话的位置 (Exchange 邮箱、Microsoft 团队、Yammer) 
- 用于将文件存储 (SharePoint 的位置) 
- 安排 (Exchange) 的日历
- 用于捕获笔记 (OneNote) 的笔记本

在创建组的同时，还设置了许多其他资源，但是在首次从服务访问时，它们不可见：

- 用于管理组任务 (Planner) 的主板
- 用于报告 (Power BI) 的工作区
-  (Microsoft Stream) 的共享视频区域
-  (表单的共享表单区域) 

在 Microsoft 365 中，其他服务能够与 Microsoft 365 组进行交互，以提供对组成员的其他功能和功能。
此示例包括：

- 应用程序的电源应用程序
- 工作流的自动电源
- 基于瀑布的项目管理的 web 和路线图上的项目
- 基于频道的对话的团队
- Yammer 适用于感兴趣的社区

## <a name="user-interactions-with-groups"></a>用户与组的交互

可以从各种接口（包括管理员和最终用户）创建和管理 Microsoft 365 组。 

### <a name="administrative-experiences"></a>管理体验

管理员可以从多个工作负荷管理中心、支持脚本编写的命令行界面以及与 Graph API 交互的自定义应用程序创建和管理 Microsoft 365 组。 唯一的例外是 Yammer 组–必须在 Yammer web 界面中创建。

**相关设置**

在可以管理组设置的各个管理界面中，有几个重叠需要注意。

**Microsoft 365 管理中心**

在 Microsoft 365 管理中心中，默认情况下会启用对组的来宾访问权限，这是允许所有者添加来宾的功能。 来自此管理中心的组没有更多的组织级控件可用。

**Azure AD 管理中心**

Azure AD 管理中心提供了有关用户是否可以在 Azure 门户中创建组或分配所有者，以及过期和命名策略设置的控制。

管理中心还提供了一些超过 Microsoft 365 管理中心的来宾邀请控制措施，例如，限制非所有者是否也可以邀请来宾的功能

**SharePoint**

SharePoint 网站是使用所有者、成员和访问者安全组创建的，其中前两个匹配的是其 Microsoft 365 组的对应项。 虽然 SharePoint Online 网站的成员身份通常由关联的 Microsoft 365 组管理，但它并不是双向关系。 对 Microsoft 365 组级别的成员身份所做的任何更改都将反映在 SharePoint 中，但是，如果 SharePoint 组中的成员身份发生了更改，则不会在 Microsoft 365 组中反映出来。

### <a name="user-experiences"></a>用户体验

最终用户可以从 Microsoft 365 中的多个服务创建组，并且在其他用户中只能与组共享。

以下服务允许最终用户创建组：
                         
适用于 web SharePoint Stream 的 Outlook Planner 项目 Microsoft 团队 Yammer

**组创建限制**

控制团队的数量的常用方法是限制哪些用户可以创建这些团队。 这只能通过限制组创建来实现。 这样做会影响从其他服务创建组的能力，在这种情况下，最终用户可能需要这些组。 Microsoft 365 组不支持从某些应用或服务中限制组创建的功能，同时允许其他应用程序或服务。

组创建限制的体验因应用程序和服务而异：


|应用或服务|体验|
|:-------------|:---------|
|Outlook|从 "人员" 页面的 "新建" 菜单中删除了 "**新建组**" 选项|
|Planner|**新计划** 说明已关闭组创建，并提供将计划添加到现有组中的功能|
|Web 和路线图的项目|"**创建组**" 菜单说明组创建受到限制，并建议使用现有组。|
|SharePoint|仍可以创建未连接到组的团队网站。|
|Stream|"**创建" 菜单** 下不显示 "**组**" 选项。|
|Teams|用户无法使用新组创建团队，但仍可创建利用现有组的团队。<br><br>"**创建团队**" 按钮将 **从组中的 "创建团队" 中** 替换。|
|Yammer|"**创建组**" 选项将从 "主组/社区导航" 中删除。|

## <a name="services-interactions-with-groups"></a>与组的服务交互

请参阅 Microsoft 365 海报中的组，以获取有关不同类型的组、如何创建和管理这些组以及几个监管建议的信息。

[![组信息图的缩略图](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

下表提供了 Microsoft 365 组与各种服务的交互的概述：

|产品|功能|服务是否<br>是否存在没有组的情况？|服务是否可以<br>是否创建组？|删除<br>实例是否删除组？|
|:---|:---|:---|:---|:---|
|Azure AD|成员资格、组控件、来宾|是|是|是|
|Exchange|日历、邮箱|是|是|是|
|Forms|表单|是|否|否|
|OneNote|Notebook|是|否|否|
|Planner|任务板|否|是|是|
|Power Apps 应用|应用|是|否|否|
|Power Automate|工作流|是|否|否|
|Power BI (经典) |工作区|否|是|是|
|Power BI (新) |工作区|是|否|是|
|Project 网页版|项目计划|是|是|否|
|路线图|路线图|是|是|否|
|SharePoint|Site|是|是|是|
|Stream|频道、视频|是|是|是|
|Teams|团队|否|是|是|
|Yammer|组|是|是|是|

[！注意] 上表提供了与 Microsoft 365 服务的组交互的高级概述，您应该了解许多细微差别和复杂之处。 以下各节更深入地介绍了特定工作负荷及其与组的交互。

## <a name="azure-ad"></a>Azure AD

Azure AD 在 Microsoft 365 中提供了基础标识管理功能。

**提供给组的主要功能**

- 组成员身份
- 命名策略
- 过期策略
- 限制
- 组创建限制

**Azure AD 是否可以创建组？**

是的，可以从 Azure AD 创建 Microsoft 365 组，方法是通过管理 web 门户、PowerShell 或 Graph API。

**Azure AD 是否不存在组？**

是的，Azure AD 执行大量与 Microsoft 365 组没有关系的服务。 每个 Microsoft 365 组都表示为 Azure AD 中的一个对象。

**每个组是否可以有多个 Azure AD 实例？**

否，只有一个 Azure AD 实例。

**Azure AD 是否可以与多个组关联？**

是，因为 Azure AD 是提供组成员身份服务的基础平台。

**Azure AD 与组的关联是否可以更改？**

否，Azure AD 是组存在的基础平台。

**删除实例是否删除了组？**

在 Azure AD 中删除组将删除与组关联的相关服务和内容。

## <a name="teams"></a>Teams

团队是一个以聊天为中心的工作区，旨在通过提供与各种 Microsoft 和第三方服务交互的单一界面来增强协作。

默认情况下，在创建团队时，与 Microsoft 365 组关联的邮箱和日历将隐藏在 Exchange 中的全局地址列表和 Outlook 中。 如果用户希望同时在同一个 Microsoft 365 组上使用 Outlook 和团队，则管理员可以手动将其重写。

**提供给组的主要功能**

- 对话
- 频道 & 选项卡
- 会议

**团队是否可以创建组？**

是的，创建新的团队将创建新的 Microsoft 365 组。 此外，还可以为现有组创建当前不具有一个团队的团队。

**是否存在没有组的团队？**

否，不能存在没有组的团队。

**每个组是否可以有多个团队？**

否，团队和组之间的关系为1:1。

**团队是否可以与多个组关联？**

不能，团队本身只能与单个组相关联。

**团队与组的关联是否可以更改？**

否，团队只能与最初关联的组相关联。

**删除团队是否删除了组？**

是的，删除 Microsoft 团队中的团队将删除组、与组关联的服务和内容。

## <a name="exchange"></a>Exchange

Exchange Online 提供了邮件、日历、联系人和相关功能。 在组的上下文中，仅与一个资源相关联–而不是与整个服务实例相关联。

**提供给组的主要功能**

- 邮箱和日历
- 能够通过电子邮件发送所有组成员
- 存储团队频道对话以用于电子数据展示目的、Planner 注释

**Exchange 是否可以创建组？**

是的，可以从 Exchange Online 管理中心和 Outlook 创建组。 您还可以将 Exchange 通讯组列表转换为 Microsoft 365 组。

**Exchange 是否不存在组？**

是的，Exchange Online 提供了许多服务，包括共享邮箱和日历，没有任何组关联。

**每个组是否可以有多个 Exchange 邮箱或日历实例？**

不可以，组只能有一个 Exchange Online 邮箱和日历。

**Exchange 邮箱和日历是否可以与多个组关联？**

否，邮箱和日历与组有1:1 关系。 可以与其他用户或组共享邮箱，但这不会建立任何形式的服务关联。

**Exchange 邮箱或日历与组的关联是否可以更改？**

否，不能将邮箱和日历更改为其他组。 但是，可以在 Outlook 或使用第三方工具将内容从一个邮箱移动到另一个邮箱。

**删除邮箱是否删除了组？**

是的，删除 Exchange 中的邮箱将删除该组以及与组关联的服务和内容。

## <a name="forms"></a>Forms

表单提供基于 web 的调查和测验。

**提供给组的主要功能**

- 表单的所有权

**表单是否可以创建组？**

否，窗体无法创建组。

**表单是否存在而没有组？**

是的，可以直接在最终用户帐户中创建调查和测验。

**每个组是否可以有多个窗体？**

是的，可以有多个窗体与组关联。

**表单是否可以与多个组关联？**

不能，窗体只能与单个组相关联。

**窗体与组的关联是否可以更改？**

否，一旦将窗体与组相关联 (在中直接创建，或从单个) 转移的所有权，则无法将其移到其他组。

**删除该表单会删除此组吗？**

否，不能从窗体界面中删除组，只能从单个窗体中删除。

## <a name="onenote"></a>OneNote

OneNote 是一个数字笔记本应用程序。 使用组创建的 OneNote 笔记本是关联的 SharePoint 网站中的文件，而不是与组连接的服务。

**提供给组的主要功能**

- 共享笔记本 (存储在与组关联的 SharePoint 库中) 

**OneNote 是否可以创建组？**

否，OneNote 应用程序无法创建组。

**OneNote 笔记本是否在没有组的情况下存在？**

是的，笔记本可以直接在 OneDrive 中创建，也可以在其他共享位置创建。

**每个组是否可以有多个 OneNote 笔记本？**

是的，默认情况下会创建笔记本，并且可以添加其他人，但与组关联的服务的 OneNote 链接将始终转到默认笔记本。

**OneNote 笔记本是否可以与多个组关联？**

否，笔记本存储在与组关联的 SharePoint 网站库中并从各种接口进行链接。 但可以与其他组共享，其方式与与个人共享的方式相同。

**笔记本与组的关联是否可以更改？**

否，笔记本本身与组相关联，并且可以从其他组连接服务直接访问，但是可以在 OneNote 应用程序中将内容从一个笔记本移动到另一个笔记本。

**删除笔记本是否删除了此组？**

否，但如果删除了 OneNote 笔记本，某些与组相关的服务中的链接可能会断开。

## <a name="planner"></a>Planner

Planner 是一种轻型组任务管理服务。

**提供给组的主要功能**

- 用于管理组任务的板

**规划者是否可以创建组？**

是的，创建计划将创建新组。

**是否不存在具有组的 Planner 面板？**

否，计划必须与组相关联。

**每个组是否可以有多个计划？**

是的，每个组可以有多个计划。

**计划是否可以与多个组关联？**

否，计划只依赖于组成员身份来确定访问权限。

**计划与组的关联是否可以更改？**

但如果复制计划，则会创建一个新组。

> [!NOTE]
> 由任何其他应用程序创建的组不会为用户自动显示在 Planner 中。 若要访问主板，最初需要从其他基于组的界面（如 Outlook）打开它。

**删除该计划是否删除了此组？**

是的，删除计划将删除组和组相关的服务和内容。

## <a name="power-apps"></a>Power Apps

节能应用程序为无需代码的应用程序开发提供了画布。

**提供给组的主要功能**

- 可以与组共享应用程序以进行运行和修改

**电源应用是否可以创建组？**

否，Power Apps 无法创建 Microsoft 365 组。

**是否在没有组的情况下存在电源应用？**

是的，可以在 Power 应用程序中创建应用程序，并将其驻留在创建者帐户中，直到共享或发布。

**每个组是否可以有多个应用程序？**

是的，可以有多个与组共享的应用程序。

**是否可以将应用程序与多个组关联？**

是的，可以与多个组共享应用程序。

**应用与组的关联是否可以更改？**

是，因为电源应用和 Microsoft 365 组之间的关联仅共享–应用程序仍与创建者驻留在一起。

> [!IMPORTANT]
> [在与用户共享应用程序之前，必须启用组的安全性](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。

**删除应用程序是否删除组？**

否，应用不会连接到组，而不是与它们共享。

## <a name="power-automate"></a>Power Automate

电源自动运行 (以前称为 Microsoft Flow) 提供工作流和自动化服务。

**提供给组的主要功能**

- 可以将工作流与组共享，以进行运行和修改。

**能否对组进行电源自动创建？**

不，电源自动化无法在关联的上下文中创建 Microsoft 365 组。

但是，可以创建执行各种操作（如创建 Azure AD 安全组或更新 Microsoft 365 组的成员身份）的流。

**是否存在不含组的流？**

是的，在 Power 自动化中可以创建流，并驻留在创建者帐户中，直到共享或发布。

**每个组是否可以有多个流？**

是的，可以有多个流与组共享。

**流是否可以与多个组关联？**

是的，可以与多个组共享流。

**流与组的关联是否可以更改？**

是的，由于电源自动化与 Microsoft 365 组之间的关联仅共享–该流仍将与创建者驻留在一起。

**删除流是否删除组？**

否，与电源应用一样，流不会连接到组，而不是与它们共享。

## <a name="power-bi-classic"></a>Power BI (经典) 

Power BI 提供交互式数据驱动仪表板和报告。

**提供给组的主要功能**

- 数据报告

**Power BI 是否可以创建组？**

是的，创建经典工作区将创建 Microsoft 365 组。

**是否在没有组的情况下存在 Power BI 经典工作区？**

不是， [POWER BI 中的经典工作区必须与组相关联](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。

**每个组是否可以有多个 Power BI 工作区？**

否，经典工作区和组之间的关系为1:1。

**是否可以将工作区与多个组关联？**

从技术上讲，如果使用组创建经典工作区，则可以在具有用户和安全组的组外共享内容。

**工作区与组的关联是否可以更改？**

否，经典工作区本身与组关联，但可以在 Power BI 接口中将内容移动到另一个工作区，也可以通过在本地导出内容。

**删除该工作区是否删除了此组？**

是的，删除 Power BI 中的工作区将删除组和组相关的服务和内容。

## <a name="power-bi-new"></a>Power BI (新) 

Power BI 提供交互式数据驱动仪表板和报告。

在 Power BI 中创建新的工作区不会创建 Microsoft 365 组时，通过任何其他方式创建一个组将会在 Power BI 中创建一个新的 (而不是经典) 工作区。

**提供给组的主要功能**

- 数据报告

**Power BI 是否可以创建组？**

否，不能从新的 Power BI 接口创建 Microsoft 365 组。

**新的 Power BI 工作区在没有组的情况下存在吗？**

是的，在 Power BI 中创建的报告和工作区可能与 Microsoft 365 组不关联。

**每个组是否可以有多个工作区？**

是的， [由 POWER BI 创建的多个工作区可以与单个组共享](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。

**是否可以将工作区与多个组关联？**

否，Power BI 创建的工作区只能与单个组相关联。

**工作区与组的关联是否可以更改？**

"是" 和 "否"。 Power BI 创建的工作区一次只能与一个组关联，但可以随时更改关联。 组在 Power BI 中创建的工作区将永久关联到该组。

**删除该工作区是否删除了此组？**

是的，删除 Power BI 中的工作区将删除组和组相关联的服务和内容。

## <a name="project-for-the-web"></a>Project 网页版

为 web 项目提供了创建项目计划、甘特图和路线图的功能。
提供给组的主要功能。

- 项目计划

**可以为 web 创建一个组的项目吗？**

是的，可以直接从 web 项目创建新的 Microsoft 365 组。

**是否存在不包含组的项目？**

是的，项目可以存在，但不与 Microsoft 365 组关联，但任务分配需要组关联。

**每个组是否可以有多个项目？**

是的，可以在一个组中连接多个项目。

**项目是否可以与多个组关联？**

否，一个项目只能与一个组相关联。

**项目与组的关联是否可以更改？**

否，一旦建立与组的关联，就无法更改。

**删除项目后删除了组吗？**

否，删除 web 项目中的项目不会删除组。

## <a name="roadmap"></a>路线图

通过路线图，可以为 web 和 Project Online 的 Project 创建项目路线图。

**提供给组的主要功能**

- 项目路线图

**路线图是否可以创建组？**

是的，可以直接从路线图创建新的 Microsoft 365 组。

**是否存在没有组的路线图？**

是的，路线图可以存在，但不与 Microsoft 365 组关联，但共享路线图需要组关联。

**每个组是否可以有多个路线图？**

是的，可以将多个路线图连接到单个组。

**是否可以将路线图与多个组关联？**

否，一个路线图只能与一个组相关联。

**路线图与组的关联是否可以更改？**

否，一旦建立与组的关联，就无法更改。

**删除该路线图是否删除了此组？**

否，删除路线图不会删除组。

## <a name="sharepoint"></a>SharePoint

SharePoint 是一种基于 web 的内容管理平台，可提供多种 Microsoft 365 服务的其他内容和存储服务。

**提供给组的主要功能**

- 文档库
- OneNote 笔记本存储库
- 团队 wiki 文件的存储

**SharePoint 是否可以创建组？**

是的，默认情况下，在 SharePoint 中创建团队网站将创建 Microsoft 365 组。 此外，还可以为现有网站创建组和（可选）团队。

**SharePoint 网站是否存在而不包含组？**

是的，SharePoint 提供了大量与非组关联的服务和网站，如通信和中心网站。 

**每个组是否可以有多个站点？**

不能，每个组只能有一个站点。 团队中的专用通道使用未连接到组的其他网站。

**是否可以将网站与多个组关联？**

从技术上说，在使用组创建网站时，可以与其他组共享内容。

**网站与组的关联是否可以更改？**

否，网站本身与组关联，但可以通过在本地导出内容或使用第三方工具将内容从一个网站移到另一个网站。

**删除网站是否删除组？**

是，删除 SharePoint 中的网站将删除组和组相关的服务和内容。

## <a name="stream"></a>Stream

Microsoft Stream 是一个视频托管和共享平台。

**提供给组的主要功能**

- 视频存储
- 团队会议录制
- 视频通道

**是否可以流创建组？**

是的，可以直接从 Stream 创建一个新的 Microsoft 365 组。

**是否存在没有组的流？**

是的，视频通道和视频可以存在于 Stream 中，而不会与组相关联。

**每个组是否可以有多个视频和通道？**

是的，每个组中可以有多个视频和频道。

**视频或通道是否可以与多个组关联？**

是的，虽然使用组创建视频或频道，但可以与其他组共享。

**它与组的关联是否可以更改？**

是和否;Stream 中的视频由原始上载程序或会议录制器拥有，因此可以与任何组关联，但视频通道只能与最初在其中创建的组相关联。

**删除视频或频道是否删除了组？**

否，删除视频或频道不会删除该组。 但是，删除 Stream 中的组本身将会删除与组关联的服务和内容（实际视频除外）。

## <a name="yammer"></a>Yammer

Yammer 是一个企业社交平台，旨在促进组织内部和组织之间的社区参与。

在 Yammer 中创建一个以前称为 "组" ) 的社区 (将创建一个邮箱，但目前不使用。

与 Yammer 关联的 Microsoft 365 组不能与 Microsoft 团队中的团队一起使用。

**提供给组的主要功能**

- 会话区域

**Yammer 是否可以创建 Microsoft 365 组？**

是，在 Yammer 中创建新组将创建一个新的 Microsoft 365 组（如果已连接平台，并且用户能够创建组）。

不能在 Yammer 本身之外的任何接口或服务中创建具有关联的 Microsoft 365 组的 Yammer 组。

**Yammer 组是否存在不包含 Microsoft 365 的组？**

是的，可以在没有 Microsoft 365 组的情况下创建 Yammer 组。

如果 Yammer 平台未连接到 Microsoft 365 组，或者用户不能创建 Microsoft 365 组，则在没有 Microsoft 365 组关联的情况下创建 Yammer 组。

**每个 Microsoft 365 组是否可以有多个 Yammer 组？**

不是，Yammer 组和 Microsoft 365 组之间的关系为1:1。

**Yammer 组是否可以与多个 Microsoft 365 组关联？**

不能，Yammer 组只能与一个 Microsoft 365 组相关联。 可以与其他 Yammer 组共享帖子或将其移至其他 Yammer 组。

**Yammer 组与 Microsoft 365 组的关联是否可以更改？**

否，Yammer 组只能与最初与之关联的 Microsoft 365 组相关联。

**删除 Yammer 组是否删除了 Microsoft 365 组？**

是，删除 Yammer 中的组将删除相关的 Microsoft 组和与组关联的服务和内容。

## <a name="related-topics"></a>相关主题

[协作治理规划分步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

