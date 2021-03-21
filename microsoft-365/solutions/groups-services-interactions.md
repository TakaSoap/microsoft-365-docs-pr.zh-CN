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
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921020"
---
# <a name="groups-services-interactions"></a>组服务交互

Microsoft 365 组为 Microsoft 365 平台中的许多服务和工作负载提供了一个常见结构，为最终用户提供连接体验。 Microsoft 365 组的核心是提供：

- 管理 Azure AD (成员身份) 
- Exchange 邮箱、Microsoft Teams、Yammer (邮件和对话) 
- 用于将文件存储在 SharePoint () 
- 计划 Exchange (日历) 
- 用于捕获 OneNote (笔记的) 

在组创建时，还会设置大量其他资源，但在首次从服务访问它们之前，它们不可见：

- 用于管理 Planner (组) 
- 用于报告 Power BI (工作区) 
- Microsoft Stream (共享视频) 
- 共享表单和表单 (区域) 

在 Microsoft 365 中，其他服务能够与 Microsoft 365 组交互，以向组的成员提供其他特性和功能。
例如：

- Power Apps for apps
- 工作流的 Power Automate
- Project 网页和基于瀑布的项目管理路线图
- 用于基于频道的对话的 Teams
- Yammer for communities for interest

## <a name="user-interactions-with-groups"></a>用户与组的交互

管理员和最终用户可以通过各种界面创建和管理 Microsoft 365 组。 

### <a name="administrative-experiences"></a>管理体验

管理员可以从多个工作负载管理中心、支持脚本的命令行界面以及与 Graph API 交互的自定义生成应用创建和管理 Microsoft 365 组。 唯一的例外是 Yammer 组，必须从 Yammer Web 界面内创建组。

**相关设置**

在可以管理组设置的各种管理界面中，存在一些应注意的重叠。

**Microsoft 365 管理中心**

在 Microsoft 365 管理中心中，默认情况下启用对组的来宾访问，以及允许所有者添加来宾的能力。 此管理中心不再对组提供组织级别控制。

**Azure AD 管理中心**

Azure AD 管理中心控制用户是否可以在 Azure 门户创建组或分配所有者，以及过期和命名策略设置。

管理中心还提供了一些除 Microsoft 365 管理中心之外的来宾邀请控制措施，例如限制非所有者是否可以邀请来宾的能力

**SharePoint**

SharePoint 网站使用所有者、成员和访问者安全组创建，前两个安全组与 Microsoft 365 组对应方匹配。 虽然 SharePoint Online 网站的成员身份通常由关联的 Microsoft 365 组管理，但它不是双向关系。 对 Microsoft 365 组级别的成员身份的任何更改都反映在 SharePoint 中，但如果 SharePoint 组的成员身份发生更改，则这不会反映在 Microsoft 365 组中。

### <a name="user-experiences"></a>用户体验

最终用户可以从 Microsoft 365 中的一些服务创建组，在另外一些服务中，他们只能与组共享。

以下服务允许最终用户创建组：
                         
Outlook Planner Project 网页 SharePoint Stream Microsoft Teams Yammer

**组创建限制**

控制团队的激增的一种常见方法是限制哪些用户可以创建团队。 这仅可通过限制组的创建完成。 这样做会影响从最终用户可能需要的其他服务创建组的能力。 Microsoft 365 组不支持限制从某些应用或服务创建组，同时允许其他应用或服务创建组。

组创建限制的体验因应用和服务而异：


|应用或服务|体验|
|:-------------|:---------|
|Outlook|**"新建组** "选项已从"人员"页面的"新建"菜单中删除|
|规划器|**新** 计划说明组创建已关闭，并提供将计划添加到现有组|
|Project 网页和路线图|**"创建组** "菜单说明组创建受到限制，并建议使用现有组。|
|SharePoint|仍然能够创建未连接到组的工作组网站。|
|Stream|**"** 组"选项不会显示在"创建" **菜单下**。|
|Teams|用户不能使用新组创建团队，但仍可以创建利用现有组的团队。<br><br>**"创建团队"** 按钮将替换为"**从组创建团队"。**|
|Yammer|**"创建组"** 选项已从主"组/社区"导航中删除。|

## <a name="services-interactions-with-groups"></a>服务与组的交互

请参阅 Microsoft 365 中的组海报，了解不同类型的组、如何创建和管理这些组，以及一些管理建议。

[![组信息图的缩略图](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

下表概述了 Microsoft 365 组与各种服务的交互：

|产品|功能|服务是否<br>是否存在没有组？|服务能否<br>创建组|是否删除<br>实例删除组|
|:---|:---|:---|:---|:---|
|Azure AD|成员身份、组控件、来宾|是|是|是|
|Exchange|日历、邮箱|是|是|是|
|Forms|表单|是|否|否|
|OneNote|Notebook|是|否|否|
|规划器|任务板|否|是|是|
|Power Apps 应用|应用|是|否|否|
|Power Automate|工作流|是|否|否|
|Power BI (经典) |工作区|否|是|是|
|Power BI (新增) |工作区|是|否|是|
|Project 网页版|项目计划|是|是|否|
|路线图|路线图|是|是|否|
|SharePoint|Site|是|是|是|
|Stream|频道、视频|是|是|是|
|Teams|团队|否|是|是|
|Yammer|组|是|是|是|

虽然上表提供了与 Microsoft 365 服务的组交互的简要概述，但您应该了解许多细微差别和细节。 以下各节将深入探讨特定的工作负荷及其与组的交互。

## <a name="azure-ad"></a>Azure AD

Azure AD 在 Microsoft 365 中提供基础标识管理功能。

**向组提供的关键功能**

- 组成员身份
- 命名策略
- 过期策略
- 来宾
- 组创建限制

**Azure AD 能否创建组？**

可以，可通过管理 Web 门户、PowerShell 或 Graph API 从 Azure AD 创建 Microsoft 365 组。

**Azure AD 是否存在没有组？**

是的，Azure AD 执行大量与 Microsoft 365 组无关系的服务。 每个 Microsoft 365 组都表示为 Azure AD 中的对象。

**每个组能否有多个 Azure AD 实例？**

否，只有一个 Azure AD 实例。

**Azure AD 能否与多个组关联？**

是的，因为 Azure AD 是提供组成员身份服务的基础平台。

**Azure AD 与组关联能否更改？**

否，Azure AD 是存在组的基础平台。

**删除实例是否删除组？**

在 Azure AD 中删除组将删除相关的组关联的服务和内容。

## <a name="teams"></a>Teams

Teams 是一个以聊天为中心的工作区，旨在通过提供与各种 Microsoft 和第三方服务交互的单数界面来增强协作。

默认情况下，创建团队时，与 Microsoft 365 组关联的邮箱和日历在 Exchange 和 Outlook 中的全局地址列表中都处于隐藏状态。 如果用户希望在同一 Microsoft 365 组上同时使用 Outlook 和 Teams，则管理员可以手动覆盖此选项。

**向组提供的关键功能**

- 对话
- 频道&选项卡
- 会议

**Teams 能否创建组？**

是的，创建新团队将创建新的 Microsoft 365 组。 也可以为当前没有团队的现有组创建团队。

**团队是否存在没有组？**

否，没有组，团队不可能存在。

**每个组可以有多个团队吗？**

否，团队和组之间的关系是 1：1。

**团队能否与多个组关联？**

否，团队本身只能与一个组关联。

**团队与组关联能否发生变化？**

否，团队只能与最初关联的组相关联。

**删除团队是否删除该组？**

可以，删除 Microsoft Teams 中的团队将删除组、组关联的服务和内容。

## <a name="exchange"></a>Exchange

Exchange Online 提供消息传递、日历、联系人和相关功能。 在组上下文中，仅关联单个资源，而不是整个服务实例。

**向组提供的关键功能**

- 邮箱和日历
- 能够向所有组的成员发送电子邮件
- 存储 Teams 频道对话以用于电子数据展示，Planner 评论

**Exchange 可以创建组吗？**

可以，可以同时从 Exchange Online 管理中心以及 Outlook 创建组。 您还可以将 Exchange 通讯组列表转换为 Microsoft 365 组。

**Exchange 是否存在没有组？**

是的，Exchange Online 提供了许多服务，包括共享邮箱和日历，没有任何组关联。

**每个组能否有多个 Exchange 邮箱或日历实例？**

否，组只能有一个 Exchange Online 邮箱和日历。

**Exchange 邮箱和日历能否与多个组关联？**

否，邮箱和日历与组具有 1：1 关系。 可以与其他用户或组共享邮箱，但这不会建立任何形式的服务关联。

**Exchange 邮箱或日历与组之间的关联是否可更改？**

否，不能将邮箱和日历更改为其他组。 但是，内容可以在 Outlook 中或通过使用第三方工具从一个邮箱移动到另一个邮箱。

**删除邮箱是否删除该组？**

可以，删除 Exchange 中的邮箱将删除组以及组关联的服务和内容。

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

否，一旦表单与直接在内部 (组关联，或者从单个组传输的所有权) 无法移动到另一个组。

**删除表单是否将删除该组？**

否，不能从 Forms 界面中删除组，只能从单个窗体中删除组。

## <a name="onenote"></a>OneNote

OneNote 是数字笔记本应用程序。 使用组创建的 OneNote 笔记本是关联的 SharePoint 网站中的文件，而不是组连接的服务。

**向组提供的关键功能**

- 共享笔记本 (组关联的 SharePoint 库库中) 

**OneNote 能否创建组？**

否，OneNote 应用程序无法创建组。

**是否存在没有组的 OneNote 笔记本？**

可以，笔记本可以直接在 OneDrive 或其他共享位置创建。

**每个组能否有多个 OneNote 笔记本？**

是，默认情况下会创建一个笔记本，可以添加其他笔记本，但是从组关联的服务到 OneNote 的任何链接将始终转到默认笔记本。

**OneNote 笔记本能否与多个组关联？**

否，笔记本存储在与组关联的 SharePoint 网站库中，并且从各种界面链接。 但是，它可以与其他组共享，方式与个人共享的方式相同。

**笔记本与组关联能否更改？**

否，笔记本本身与组关联，并且可以从其他已连接组的服务直接访问，但是内容可以从 OneNote 应用程序内的一个笔记本移动到另一个笔记本。

**删除笔记本是否删除该组？**

否，但是，如果删除了 OneNote 笔记本，则某些组关联的服务中可能会断开链接。

## <a name="planner"></a>规划器

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
> 由任何其他应用程序创建的组不会自动显示在用户的 Planner 中。 若要最初访问该板，他们将需要从另一个基于组的界面（如 Outlook）打开它。

**删除计划是否删除该组？**

可以，删除计划将删除组和组关联的服务和内容。

## <a name="power-apps"></a>Power Apps

Power Apps 提供了一个画布，用于应用开发，而无需使用代码。

**向组提供的关键功能**

- 可以与要运行和修改的组共享应用

**Power Apps 能否创建组？**

否，Power Apps 无法创建 Microsoft 365 组。

**是否存在没有组的 Power Apps？**

可以，应用可以在 Power Apps 中创建，并驻留在创建者帐户内，直到共享或发布。

**每个组能否有多个应用？**

可以，可以有多个应用与一个组共享。

**应用能否与多个组关联？**

是，可以与多个组共享应用。

**应用与组关联能否发生变化？**

可以，因为 Power Apps 和 Microsoft 365 组之间的关联只是共享 ，所以应用仍与创建者驻留在一起。

> [!IMPORTANT]
> [必须先启用安全组，然后才能与组共享应用](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。

**删除应用是否删除该组？**

否，除了与应用共享外，这些应用不会连接到组。

## <a name="power-automate"></a>Power Automate

Power Automate (以前称为 Microsoft Flow) 提供工作流和自动化服务。

**向组提供的关键功能**

- 工作流可以与要运行和修改的组共享。

**Power Automate 能否创建组？**

否，Power Automate 无法在与一个组关联的上下文中创建 Microsoft 365 组。

但是，可以创建执行各种操作（如创建 Azure AD 安全组或更新 Microsoft 365 组的成员身份）的流。

**是否存在没有组的流？**

是，可以在 Power Automate 中创建流，并驻留在创建者帐户内，直到共享或发布。

**每个组能否有多个流？**

可以，可以与一个组共享多个流。

**流能否与多个组关联？**

是，可以与多个组共享流。

**流与组关联能否更改？**

可以，因为 Power Automate 和 Microsoft 365 组之间的关联只是共享，所以流仍由创建者驻留。

**删除流是否删除组？**

否，与 Power Apps 一样，流未连接到组，而不是与它们共享。

## <a name="power-bi-classic"></a>Power BI (经典) 

Power BI 提供交互式数据驱动的仪表板和报告。

**向组提供的关键功能**

- 数据报告

**Power BI 能否创建组？**

是的，创建经典工作区将创建 Microsoft 365 组。

**是否存在没有组的 Power BI 经典工作区？**

否 [，Power BI 中的经典工作区必须与组关联](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。

**每个组能否有多个 Power BI 工作区？**

否，经典工作区和组之间的关系是 1：1。

**工作区能否与多个组关联？**

从技术上说，不是，虽然经典工作区是使用组创建的，但内容可以在组外部与用户和安全组共享。

**工作区与组关联能否更改？**

否，经典工作区本身与组相关联，但内容可以在 Power BI 界面中从一个工作区移动到另一个工作区，或者通过在本地导出内容。

**删除工作区是否删除该组？**

可以，删除 Power BI 中的工作区将删除组和组关联的服务和内容。

## <a name="power-bi-new"></a>Power BI (新增) 

Power BI 提供交互式数据驱动的仪表板和报告。

虽然在 Power BI 中创建新工作区不会创建 Microsoft 365 组，但通过任何其他方式创建组 (在 Power BI 中新建) 工作区。

**向组提供的关键功能**

- 数据报告

**Power BI 能否创建组？**

否，无法从新的 Power BI 界面创建 Microsoft 365 组。

**是否存在没有组的新 Power BI 工作区？**

可以，有可能在 Power BI 中创建不与 Microsoft 365 组关联的报表和工作区。

**每个组能否有多个工作区？**

可以 [，Power BI 创建的多个工作区可以与单个组共享](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。

**工作区能否与多个组关联？**

否，Power BI 创建的工作区只能与单个组关联。

**工作区与组关联能否更改？**

是，否。 Power BI 创建的工作区一次只能与一个组关联，但随时都可以更改关联。 在 Power BI 中由组创建的工作区将永久关联到该组。

**删除工作区是否删除该组？**

可以，删除 Power BI 中的工作区将删除组和组关联的服务和内容。

## <a name="project-for-the-web"></a>Project 网页版

Project 网页页面提供创建项目计划、甘特图和路线图的能力。
为组提供的关键功能。

- 项目计划

**Project 网页应用能否创建组？**

可以，可以直接从 Project 网页版创建新的 Microsoft 365 组。

**项目是否存在没有组？**

可以，项目可以在不与 Microsoft 365 组关联的情况下存在，但任务分配需要组关联。

**每个组能否有多个项目？**

可以，可以连接单个组中的多个项目。

**项目能否与多个组关联？**

否，项目只能与单个组关联。

**项目与组的关联能否更改？**

否，一旦建立与组的关联，它就无法更改。

**删除项目是否删除该组？**

否，在 Project 网页项目中删除项目不会删除该组。

## <a name="roadmap"></a>路线图

路线图提供了使用 Project 网页版和 Project Online 创建项目路线图的能力。

**向组提供的关键功能**

- 项目路线图

**路线图能否创建组？**

可以，可以直接根据路线图创建新的 Microsoft 365 组。

**路线图是否存在没有组？**

可以，路线图可以在不与 Microsoft 365 组关联的情况下存在，但共享路线图需要组关联。

**每个组能否有多个路线图？**

可以，可将多个路线图连接到单个组。

**路线图能否与多个组关联？**

否，路线图只能与单个组关联。

**路线图与组关联能否发生变化？**

否，一旦建立与组的关联，它就无法更改。

**删除路线图是否删除该组？**

否，删除路线图不会删除该组。

## <a name="sharepoint"></a>SharePoint

SharePoint 是基于 Web 的内容管理平台，可为许多 Microsoft 365 服务提供存储服务等。

**向组提供的关键功能**

- 文档库
- OneNote 笔记本存储库
- 存储 Teams Wiki 文件

**SharePoint 能否创建组？**

可以，默认情况下，在 SharePoint 中创建团队网站将创建 Microsoft 365 组。 还可以为现有网站创建组和（可选）团队。

**SharePoint 网站是否存在没有组？**

是的，SharePoint 提供许多非组关联的服务和网站，如通信和中心网站。 

**每个组能否有多个网站？**

否，每个组只能有一个网站。 Teams 中的私人频道使用未连接到组的其他网站。

**网站能否与多个组关联？**

从技术上说没有，但在使用组创建网站时，内容可以与其他组共享。

**网站与组关联能否更改？**

否，网站本身与组相关联，但内容可以通过在本地导出内容或通过使用第三方工具从 SharePoint 界面中的一个网站移动到另一个网站。

**删除网站是否删除组？**

可以，删除 SharePoint 中的网站将删除组和组关联的服务和内容。

## <a name="stream"></a>Stream

Microsoft Stream 是一个视频托管和共享平台。

**向组提供的关键功能**

- 视频存储
- Teams 会议录制
- 视频频道

**Stream 可以创建组吗？**

可以，可以直接从 Stream 创建新的 Microsoft 365 组。

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

Yammer 是一个企业社交平台，旨在促进组织内部和组织之间的社区参与。

在 Yammer (之前称为"组") 创建一个邮箱，但当前尚未使用。

与 Yammer 关联的 Microsoft 365 组不能与 Microsoft Teams 中的团队一同使用。

**向组提供的关键功能**

- 对话区域

**Yammer 能否创建 Microsoft 365 组？**

可以，如果平台已连接且用户能够创建组，则 Yammer 中创建新组将创建新的 Microsoft 365 组。

无法在除 Yammer 本身外的任何接口或服务中创建与 Microsoft 365 组关联的 Yammer 组。

**是否存在没有 Microsoft 365 组的 Yammer 组？**

可以，可以创建没有 Microsoft 365 组的 Yammer 组。

如果 Yammer 平台未连接到 Microsoft 365 组，或者用户无法创建 Microsoft 365 组，则创建 Yammer 组时将没有 Microsoft 365 组关联。

**每个 Microsoft 365 组能否有多个 Yammer 组？**

否，Yammer 组和 Microsoft 365 组之间的关系是 1：1。

**Yammer 组能否与多个 Microsoft 365 组相关联？**

否，Yammer 组只能与单个 Microsoft 365 组关联。 可以与其他 Yammer 组共享帖子或将帖子移动到其他 Yammer 组。

**Yammer 组与 Microsoft 365 组关联能否发生变化？**

否，Yammer 组只能与最初关联的 Microsoft 365 组相关联。

**删除 Yammer 组是否删除 Microsoft 365 组？**

可以，删除 Yammer 中的组将删除相关的 Microsoft 组和组关联的服务和内容。

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)