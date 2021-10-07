---
title: 组服务交互
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 组服务交互
ms.openlocfilehash: f20f8199811b8b34b4cb74ac18a989a79dde7759
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207459"
---
# <a name="groups-services-interactions"></a>组服务交互

Microsoft 365组为 Microsoft 365 平台中的大量服务和工作负载提供了一个通用结构，以便为最终用户提供连接体验。 核心是，存在Microsoft 365组以提供：

- 管理 Azure AD (成员身份) 
- 一个在邮箱、邮箱、邮箱 (Exchange进行Microsoft Teams对话Yammer) 
- 存储文件的位置 (SharePoint) 
- 计划日历 (Exchange) 
- 用于捕获笔记记录 (OneNote) 

在组创建时，还会设置大量其他资源，但在首次从服务访问它们之前，它们不可见：

- 用于管理 Planner (组) 
- 用于报告数据库 (Power BI) 
- Microsoft Stream (共享) 
- 共享表单和表单 (区域) 

跨Microsoft 365，其他服务能够与 Microsoft 365 组交互，以向组的成员提供其他特性和功能。
例如：

- Power Apps应用
- Power Automate工作流的工作流
- Project和基于瀑布的项目管理路线图
- Teams频道对话的会话
- Yammer关注社区

## <a name="user-interactions-with-groups"></a>用户与组的交互

Microsoft 365管理员和最终用户都可以从各种界面创建和管理组。 

### <a name="administrative-experiences"></a>管理体验

管理员可以从多个工作负载管理中心、支持脚本的命令行界面以及与 Microsoft 365 Graph API 交互的自定义生成应用创建和管理 Graph 组。 唯一的例外是Yammer组 –必须从 Web 界面Yammer组。

**相关设置**

在可以管理组设置的各种管理界面中，存在一些应注意的重叠。

**Microsoft 365 管理中心**

在Microsoft 365 管理中心中，默认情况下启用对组的来宾访问，以及允许所有者添加来宾的能力。 此管理中心不再对组提供组织级别控制。

**Azure AD 管理中心**

Azure AD 管理中心可控制用户是否可以在 Azure 门户创建组或分配所有者，以及过期和命名策略设置。

管理中心还提供了一些除上述功能外Microsoft 365 管理中心的来宾邀请控制措施，例如限制非所有者能否也邀请来宾

**SharePoint**

SharePoint所有者、成员和访问者安全组创建网站，前两个安全组最多与组对应Microsoft 365匹配。 虽然联机SharePoint的成员身份通常由关联的组Microsoft 365，但它不是双向关系。 对 Microsoft 365 组级别的成员身份的任何更改都反映在 SharePoint 中，但是，如果 SharePoint 组中的成员身份发生更改，则此更改不会反映在 Microsoft 365 组中。

### <a name="user-experiences"></a>用户体验

最终用户可以从组织内部的几个服务Microsoft 365组，而其他用户则只能与组共享。

以下服务允许最终用户创建组：

- Outlook
- Planner
- Project 网页版
- SharePoint
- Stream
- Microsoft Teams
- Yammer

#### <a name="restriction-of-group-creation"></a>组创建限制

控制团队的激增的一种常见方法是限制哪些用户可以创建团队。 这仅可通过限制组的创建完成。 这样做会影响从最终用户可能需要的其他服务创建组的能力。 Microsoft 365组不支持限制从某些应用或服务创建组，同时允许其他应用或服务创建组。

组创建限制的体验因应用和服务而异：

|应用或服务|体验|
|---|---|
|Outlook|**"新建组** "选项已从"人员"页面的"新建"菜单中删除|
|Planner|**新** 计划说明组创建已关闭，并提供将计划添加到现有组|
|Project和路线图|**"创建组** "菜单说明组创建受到限制，并建议使用现有组。|
|SharePoint|仍然能够创建未连接到组的工作组网站。|
|Stream|**"** 组"选项不会显示在"创建" **菜单下**。|
|Teams|用户不能使用新组创建团队，但仍可以创建利用现有组的团队。<br><br>**"创建团队"** 按钮将替换为"**从组创建团队"。**|
|Yammer|**"创建组"** 选项已从主"组/社区"导航中删除。|

## <a name="services-interactions-with-groups"></a>服务与组的交互

请参阅"Microsoft 365中的组"海报，了解不同类型的组、如何创建和管理这些组，以及一些治理建议。

[![组信息图的缩略图。](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

下表概述了组与Microsoft 365的组交互：

|产品|功能|服务是否<br>是否存在没有组？|服务能否<br>创建组|是否删除<br>实例删除组|
|---|---|---|---|---|
|Azure AD|成员身份、组控件、来宾|是|是|是|
|Exchange|日历、邮箱|是|是|是|
|Forms|表单|是|否|否|
|OneNote|笔记本|是|否|否|
|Planner|任务板|否|是|是|
|Power Apps应用|应用|是|否|否|
|Power Automate|工作流|是|否|否|
|Power BI (经典) |工作区|否|是|是|
|Power BI (新) |工作区|是|否|是|
|Project 网页版|Project计划|是|是|否|
|路线图|路线图|是|是|否|
|SharePoint|网站|是|是|是|
|Stream|频道、视频|是|是|是|
|Teams|团队|否|是|是|
|Yammer|组|是|是|是|

虽然上表提供了组与 Microsoft 365 服务交互的简要概述，但您应该了解许多细微差别和细微差别。 以下各节将深入探讨特定的工作负荷及其与组的交互。

## <a name="azure-ad"></a>Azure AD

Azure AD 跨组织提供基础标识Microsoft 365。

**向组提供的关键功能**

- 组成员身份
- 命名策略
- 过期策略
- 来宾
- 组创建限制

**Azure AD 能否创建组？**

可以，Microsoft 365 Azure AD 通过管理 Web 门户、PowerShell 或 Graph API 创建组。

**Azure AD 是否存在没有组？**

是的，Azure AD 执行大量与组Microsoft 365服务。 每个Microsoft 365组都表示为 Azure AD 中的对象。

**每个组能否有多个 Azure AD 实例？**

否，只有一个 Azure AD 实例。

**Azure AD 能否与多个组关联？**

是的，因为 Azure AD 是提供组成员身份服务的基础平台。

**Azure AD 与组关联能否更改？**

否，Azure AD 是存在组的基础平台。

**删除实例是否删除组？**

在 Azure AD 中删除组将删除相关的组关联的服务和内容。

## <a name="teams"></a>Teams

Teams是一个以聊天为中心的工作区，旨在通过提供与各种 Microsoft 和第三方服务交互的单数界面来增强协作。

默认情况下，创建团队时，与 Microsoft 365 组关联的邮箱和日历在 Exchange 中的全局地址列表中Outlook。 如果用户希望在同一组组上同时使用 Outlook 和 Teams，则管理员可以Microsoft 365覆盖此方法。

**向组提供的关键功能**

- 对话
- 频道&选项卡
- 会议

**能否Teams组？**

是的，创建新团队将创建新Microsoft 365组。 也可以为当前没有团队的现有组创建团队。

**团队是否存在没有组？**

否，没有组，团队不可能存在。

**每个组可以有多个团队吗？**

否，团队和组之间的关系是 1：1。

**团队能否与多个组关联？**

否，团队本身只能与一个组关联。

**团队与组关联能否发生变化？**

否，团队只能与最初关联的组相关联。

**删除团队是否删除该组？**

可以，删除Microsoft Teams将删除组、组关联的服务和内容。

## <a name="exchange"></a>Exchange

Exchange Online提供消息传递、日历、联系人和关联功能。 在组上下文中，仅关联单个资源，而不是整个服务实例。

**向组提供的关键功能**

- 邮箱和日历
- 能够向所有组的成员发送电子邮件
- 存储Teams电子数据展示的频道对话、Planner 注释

**能否Exchange组？**

可以，从管理中心以及管理中心Exchange Online组Outlook。 您还可以将通讯Exchange列表转换为Microsoft 365组。

**是否存在Exchange组？**

是的，Exchange Online提供了许多服务，包括共享邮箱和日历，没有任何组关联。

**每个组能否有多个邮箱Exchange日历实例？**

否，组只能有Exchange Online邮箱和日历。

**能否Exchange多个组关联邮箱和日历？**

否，邮箱和日历与组具有 1：1 关系。 可以与其他用户或组共享邮箱，但这不会建立任何形式的服务关联。

**邮箱Exchange日历是否与组关联会发生变化？**

否，不能将邮箱和日历更改为其他组。 但是，可以使用第三方工具将内容从一个邮箱Outlook另一个邮箱。

**删除邮箱是否删除该组？**

可以，删除邮箱Exchange将删除组以及组关联的服务和内容。

## <a name="forms"></a>Forms

表单提供基于 Web 的调查和测验。

**向组提供的关键功能**

- 表单的所有权

**窗体可以创建组吗？**

否，Forms 无法创建组。

**是否存在没有组的表单？**

可以，可以直接在最终用户帐户中创建调查和测验。

**每个组可以有多个表单吗？**

可以，可以有多个表单与一个组关联。

**表单能否与多个组关联？**

否，表单只能与单个组关联。

**表单与组的关联能否更改？**

否，一旦表单与组关联 (直接在内部创建，或所有权从单个组) 无法移动到另一个组。

**删除表单是否将删除该组？**

否，不能从 Forms 界面中删除组，只能从单个窗体中删除组。

## <a name="onenote"></a>OneNote

OneNote是数字笔记本应用程序。 使用OneNote创建的笔记本是关联的 SharePoint 网站中的文件，而不是与组连接的服务。

**向组提供的关键功能**

- 共享笔记本 (组关联的SharePoint库) 

**能否OneNote组？**

否，OneNote无法创建组。

**没有OneNote笔记本是否存在？**

可以，笔记本可以直接在OneDrive或其他共享位置创建。

**每个组能否OneNote笔记本？**

是，默认情况下会创建一个笔记本，可以添加其他笔记本，但是从组关联的OneNote指向笔记本的任何链接将始终转到默认笔记本。

**一个OneNote笔记本能否与多个组关联？**

否，笔记本存储在与组关联的网站SharePoint，并且从各种接口链接。 但是，它可以与其他组共享，方式与个人共享的方式相同。

**笔记本与组关联能否更改？**

否，笔记本本身与组关联，并且可以从其他已连接组的服务直接访问，但是内容可以从一个笔记本移动到另一个笔记本OneNote应用程序中。

**删除笔记本是否删除该组？**

否，但是OneNote笔记本时，某些组关联的服务中的链接可能会断开。

## <a name="planner"></a>Planner

Planner 是轻型组任务管理服务。

**向组提供的关键功能**

- 用于管理组任务的板

**Planner 可以创建组吗？**

是的，创建计划将创建新组。

**Planner 板是否存在没有组？**

否，计划必须与组关联。

**每个组能否有多个计划？**

可以，每个组可以有多个计划。

**计划能否与多个组关联？**

否，计划仅依赖组成员身份来确定访问权限。

**计划与组关联能否更改？**

否，但是复制计划会创建新组。

> [!NOTE]
> 由任何其他应用程序创建的组不会自动显示在用户的 Planner 中。 若要最初访问该板，他们将需要从另一个基于组的界面（如Outlook）。

**删除计划是否删除该组？**

可以，删除计划将删除组和组关联的服务和内容。

## <a name="power-apps"></a>Power Apps

Power Apps提供一个画布，用于应用开发，而无需使用代码。

**向组提供的关键功能**

- 可以与要运行和修改的组共享应用

**能否Power Apps组？**

不能，Power Apps创建一个Microsoft 365组。

**是否存在Power Apps组？**

可以，可以在网站中创建应用Power Apps并驻留在创建者帐户内，直到共享或发布。

**每个组能否有多个应用？**

可以，可以有多个应用与一个组共享。

**应用能否与多个组关联？**

可以，可以与多个组共享应用。

**应用与组关联能否发生变化？**

是，由于Power Apps组Microsoft 365只是共享 ，因此应用仍与创建者驻留。

> [!IMPORTANT]
> [必须先启用安全组，然后才能与组共享应用](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。

**删除应用是否删除该组？**

否，除了与应用共享外，这些应用不会连接到组。

## <a name="power-automate"></a>Power Automate

Power Automate (以前称为Microsoft Flow) 工作流和自动化服务。

**向组提供的关键功能**

- 工作流可以与要运行和修改的组共享。

**能否Power Automate组？**

否，Power Automate无法在Microsoft 365关联的上下文中创建一个组。

但是，可以创建执行各种操作（如创建 Azure AD 安全组或更新组成员身份）Microsoft 365流。

**是否存在没有组的流？**

是，可以在创建流Power Automate并驻留在创建者帐户内，直到共享或发布。

**每个组能否有多个流？**

可以，可以与一个组共享多个流。

**流能否与多个组关联？**

是，可以与多个组共享流。

**流与组关联能否更改？**

可以，因为Power Automate组Microsoft 365只是共享，所以流仍与创建者一起驻留。

**删除流是否删除组？**

否，Power Apps，流不会连接到组，而不是与它们共享。

## <a name="power-bi-classic"></a>Power BI (经典) 

Power BI提供交互式数据驱动的仪表板和报表。

**向组提供的关键功能**

- 数据报告

**能否Power BI组？**

是，创建经典工作区将创建Microsoft 365组。

**没有Power BI一个经典工作区吗？**

否[，Power BI中的经典工作区必须与组关联](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。

**每个组能否Power BI多个工作区？**

否，经典工作区和组之间的关系是 1：1。

**工作区能否与多个组关联？**

从技术上说，不是，虽然经典工作区是使用组创建的，但内容可以在组外部与用户和安全组共享。

**工作区与组关联能否更改？**

否，经典工作区本身与组相关联，但内容可以从 Power BI 接口内的一个工作区移动到另一个工作区，或者通过本地导出内容。

**删除工作区是否删除该组？**

可以，删除网站中的Power BI将删除组和组关联的服务和内容。

## <a name="power-bi-new"></a>Power BI (新) 

Power BI提供交互式数据驱动的仪表板和报表。

虽然在 Power BI 中创建新工作区不会创建 Microsoft 365 组，但通过任何其他方式创建组 (在 Power BI 中创建新的) 工作区。

**向组提供的关键功能**

- 数据报告

**能否Power BI组？**

否，无法从新的 Microsoft 365接口创建Power BI组。

**没有组Power BI新工作区是否存在？**

可以，在未与组关联的Power BI中创建报表和Microsoft 365。

**每个组能否有多个工作区？**

是的[，由 Power BI创建的多个工作区可以与单个组共享](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。

**工作区能否与多个组关联？**

否，由 Power BI创建的工作区只能与单个组关联。

**工作区与组关联能否更改？**

是，否。 由 Power BI创建的工作区一次只能与一个组关联，但随时都可以更改关联。 在由Power BI中创建的工作区将永久关联到该组。

**删除工作区是否删除该组？**

可以，删除网站中的Power BI将删除组和组关联的服务和内容。

## <a name="project-for-the-web"></a>Project 网页版

Project Web 支持创建项目计划、甘特图和路线图。
为组提供的关键功能。

- Project计划

**能否Project Web 创建组？**

可以，可以直接从 Web Microsoft 365创建新Project组。

**项目是否存在没有组？**

可以，项目可以存在，而无需与Microsoft 365关联，但是任务分配需要组关联。

**每个组能否有多个项目？**

可以，可以连接单个组中的多个项目。

**项目能否与多个组关联？**

否，项目只能与单个组关联。

**项目与组的关联能否更改？**

否，一旦建立与组的关联，它就无法更改。

**删除项目是否删除该组？**

否，在 Web Project中删除项目不会删除组。

## <a name="roadmap"></a>路线图

路线图提供了使用 Web 和 Project 创建项目Project Online。

**向组提供的关键功能**

- Project路线图

**路线图能否创建组？**

可以，可以直接根据路线图Microsoft 365组。

**路线图是否存在没有组？**

可以，无需与组关联即可Microsoft 365路线图，但共享路线图需要组关联。

**每个组能否有多个路线图？**

可以，可将多个路线图连接到单个组。

**路线图能否与多个组关联？**

否，路线图只能与单个组关联。

**路线图与组关联能否发生变化？**

否，一旦建立与组的关联，它就无法更改。

**删除路线图是否删除该组？**

否，删除路线图不会删除该组。

## <a name="sharepoint"></a>SharePoint

SharePoint是一个基于 Web 的内容管理平台，它为许多服务提供了存储Microsoft 365服务。

**向组提供的关键功能**

- 文档库
- 存储笔记本OneNote库
- 存储 wiki Teams文件

**能否SharePoint组？**

是，默认情况下，在 SharePoint创建Microsoft 365组。 还可以为现有网站创建组和（可选）团队。

**是否存在SharePoint组的网站？**

可以，SharePoint许多非组关联的服务和网站，例如通信和中心网站。 

**每个组能否有多个网站？**

否，每个组只能有一个网站。 专用频道Teams使用未连接到组的其他网站。

**网站能否与多个组关联？**

从技术上说没有，但在使用组创建网站时，内容可以与其他组共享。

**网站与组关联能否更改？**

否，网站本身与组关联，但内容可以通过在本地导出内容或通过使用第三方工具从 SharePoint 界面中的一个网站移动到另一个网站。

**删除网站是否删除组？**

可以，删除网站SharePoint将删除组和组关联的服务和内容。

## <a name="stream"></a>Stream

Microsoft Stream 是一个视频托管和共享平台。

**向组提供的关键功能**

- 视频存储
- Teams会议录制
- 视频频道

**Stream 可以创建组吗？**

可以，可以直接从 Stream Microsoft 365组。

**Stream 是否存在没有组？**

可以，视频频道和视频可以存在于 Stream 中，而无需与组关联。

**每个组能否有多个视频和频道？**

可以，每个组中可以有多个视频和频道。

**视频或频道能否与多个组关联？**

可以，当视频或频道与组一起创建时，可以与其他组共享。

**其与组关联能否更改？**

是和否;Stream 中的视频归原始上传者或会议录制器所有，因此可以与任何组关联，但是视频频道只能与最初创建的组相关联。

**删除视频或频道是否删除该组？**

否，删除视频或频道不会删除组。 但是，在 Stream 中删除组本身将删除与组关联的服务和内容，实际视频除外。

## <a name="yammer"></a>Yammer

Yammer是一个企业社交平台，旨在促进组织内部和组织之间的社区参与。

在邮箱 (之前称为"组") 创建Yammer会创建一个邮箱，但目前尚未使用。

与Microsoft 365关联的组Yammer组不能与Microsoft Teams。

**向组提供的关键功能**

- 对话区域

**能否Yammer组Microsoft 365组？**

是，如果连接了Yammer且用户能够创建组，则Yammer Microsoft 365组将新建一个组。

不能Yammer接口或服务（Microsoft 365组本身）创建与组关联的Yammer组。

**没有Yammer组，是否存在Microsoft 365组？**

可以，可以创建一个没有Yammer组Microsoft 365组。

如果 Yammer 平台未连接到 Microsoft 365 组，或者用户无法创建 Microsoft 365 组，Yammer组将创建不带 Microsoft 365 组关联。

**每个组能否Yammer多个Microsoft 365组？**

否，Yammer组与Microsoft 365之间的关系是 1：1。

**一个Yammer组能否与多个组Microsoft 365关联？**

否，Yammer组只能与单个组Microsoft 365关联。 可以与其他用户共享帖子或将帖子移动到其他Yammer组。

**一个Yammer组与一个组Microsoft 365的关联吗？**

否，Yammer组只能与最初关联的Microsoft 365组关联。

**删除组Yammer是否删除Microsoft 365组？**

可以，删除 Yammer将删除相关的 Microsoft 组和组关联的服务和内容。

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)
