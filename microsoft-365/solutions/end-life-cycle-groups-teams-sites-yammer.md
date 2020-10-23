---
title: 组、团队和 Yammer 的生命周期选项结束
ms.reviewer: mmclean
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
description: 组、团队和 Yammer 的生命周期选项的结束。
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681706"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>组、团队和 Yammer 的生命周期选项结束

Microsoft 365 组和 Microsoft 团队使用各种连接的服务。 删除组或团队时，也会删除连接的服务中的大多数信息。 本文介绍在删除之前将信息从组或团队中移出时保留信息的选项。

不再需要的组或团队的常见做法是将这些文件移出团队，并将它们存储在其他位置，如作为存储库或存档的 SharePoint 文档库。 此做法基于旧样式的工作，其中信息存储在文件和文件夹中，并且通过电子邮件进行通信。

下表概述了与组和团队相关联的服务，以及每个服务中发现的内容的主要类型：

|服务|内容的类型|
|:------|:---------------|
|Teams|频道对话、频道中的文件|
|Forms|调查结构和结果|
|OneNote|Notebook|
|Outlook|邮件和日历|
|Planner|项目状态和任务信息|
|Power Automate|工作流|
|Power BI|数据、报告和仪表板|
|Web 上的项目|项目计划|
|路线图|路线图|
|SharePoint|文件、列表、工作组通道 wiki 数据|
|Stream|视频|
|Yammer|对话|

删除组或团队时，也会删除大多数关联的资源。 其中的一些例外包括流中的视频，它们仍将保留，并且仍由上载/录制的人员拥有，如电源自动化中的流程。 Web 上 Project 中的项目和路线图数据将保留在 CD 中，并且可以单独还原。

组和团队在30天内保留为软删除状态，可随时还原。 但是，在30天后，所有相关的资源（如服务和内容）都将从 Microsoft 365 环境中完全清除。 保留策略保护的任何内容仍可通过电子数据展示搜索。

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>组连接服务的生命周期结束注意事项

在删除组或团队时，团队和组所有者和 IT 管理员需要考虑三个关键方面。

**Content**

在团队不再工作或存在时是否需要保留内容？ 它是否足以依赖 Microsoft 365 的保留功能，或者是否是不提供保留的应用程序和服务中的一些内容？ 出于记录管理目的，内容是否需要保留以供存档，或用于将来使用和参考目的？

在存档或删除任何团队之前，必须先询问这些问题，以避免任何潜在的数据丢失。

**服务**

在各应用程序和服务的内容之上，是否需要保留其当前的工作表单？ 例如，Power BI report 是否需要能够继续访问，表单结果是否需要在可视化摘要视图中可用，SharePoint 中的列表是否已链接到或嵌入到任意位置？

与内容注意事项类似，在删除基础组之前，必须询问这些问题，只是导出内容可能不够。

**限制**

向团队邀请来宾时，工作流会在将其添加到团队之前在主机组织的 Azure Active Directory 中创建自己的身份。 删除团队后，不会从 Azure Active Directory 中删除来宾，因此这些来宾仍存在于 Microsoft 团队环境中。 虽然来宾无法访问未与他们共享的组、网站、团队或内容，但它们仍可能利用 Microsoft 团队中的功能，例如发起聊天、语音和视频呼叫以及使用应用。

团队或组所有者可以邀请外部用户成为 Azure Active Directory 中的来宾，将其添加到团队，并将其从团队中删除。 但是，团队所有者无法从 Azure Active Directory 中删除来宾–这仅可由全局管理员或用户管理员执行。

因此，执行来宾审查以及了解在删除团队删除时是否需要从 Azure Active Directory 中删除来宾非常重要。 可能存在有效的来宾保留在目录中的情况，例如，是一个或多个其他团队的成员，或者使用其他 Microsoft 365 或 Azure 服务。

## <a name="teams"></a>Teams

特定于团队的内容主要是对话的形式。

无法使用本机 Microsoft 团队功能复制或移动通道中的对话。 但是，可以使用 Graph API 导出它们。

此外，如果将保留策略应用于团队，则通过电子数据展示搜索来保留和提供会话。 可以导出电子数据展示搜索中的 (项，但不会保留原始源中的任何上下文或结构–它们只是单独的邮件。 ) 

### <a name="archiving-a-team"></a>存档团队

[存档团队](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)的好处在于，它提供了对团队的完全访问权限，以便用户仍可以浏览频道对话和打开的文件，即使他们不是活动的也是如此。 此外，如果需要继续处理这些团队 (例如，在项目扩展) 的情况下，团队可能会 unarchived。

当团队由所有者存档时，对于团队中的内容，以及在选择了关联的 SharePoint 网站的情况下，会将其设置为只读。 此操作的目标是确保通道中的对话在其现有状态中保留，以及基于 SharePoint 的内容（如文件和 wiki）。

在 SharePoint 网站中，没有可见的更改，但是，如果将 Microsoft 365 组的基于 SharePoint 的权限组设置为 "网站访问者" 级别，则无法对任何文件或列表进行任何更改。 这包括适用于团队的 OneNote 笔记本，因为这会存储在 SharePoint 网站内的网站资产库中。

存档团队后，如果设置) ，则基础 Microsoft 365 组仍受过期策略 (的限制，因此所有者必须继续续订团队。

在将团队的频道对话和 SharePoint 网站内容设置为只读时，不会将同一个应用于其他关联的服务：

- 还可以创建、修改和删除 Planner 存储桶和任务
- 表单仍可以接收提交
- Outlook 邮箱仍可接收电子邮件
- Power BI 仪表板、报表和数据仍可修改
- 仍可在 web 上的 Project 中编辑项目和路线图
- 仍可在流中上载、修改和删除视频
- 如果需要将邮件发布到已存档的团队的某个频道，则仍然可以创建、修改和删除 "电源自动化" 中的流， (这些流将会失败。但是，如果需要将邮件发布到存档) 团队的某个频道，则

## <a name="forms"></a>Forms

虽然可以将窗体从单个帐户移动到一个组，但不能将其从一个组移动或复制到另一个组。 在团队被删除时，有三个选项可用于窗体。

**复制表单**

可以将表单 [共享为模板](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)，以允许其他用户将其复制到自己的帐户或组。 这不会保留结果提交中的数据;仅限表单结构，如问题和设置。

**将结果导出到电子表格**

如果需要保留表单响应的数据，则可通过 [将结果导出到 Excel 电子表格](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)来实现此目的。 这只会将问题及其响应导出为数据，而不包括由窗体创建的图表。


**删除表单**

删除组的同时也会导致删除任何关联的表单，组成员可以 [直接删除它们](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) 而不是组的所有者–但是，这是一个不提供任何其他好处的手动步骤。

## <a name="onenote"></a>OneNote

组中包含的 OneNote 笔记本存储在关联的 SharePoint 网站内的 "网站资产" 库中。 尽管笔记本文件有时可以分布在多个单独的文件中，但不能单独复制和打开它们。 而是必须使用 OneNote 2016 移动或导出 OneNote 笔记本的内容。

**将页面和分区移动到其他笔记本**

[将页面或分区单独移动到其他笔记本](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) 使所有者有机会清除其数据，只需保留所需的内容。

**将整个笔记本导出为程序包**

如果需要将整个笔记本保留为其现有结构，则可以将其 [导出为 OneNote 程序包](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) 文件，然后将其导入到新位置。 或者，这可用作将内容保留在单个文件而不是现有的多文件结构中的方法。

**打印为 PDF 格式**

在笔记本中的某些内容只需保留以供参考或作为记录的情况下，可以将单个页面 [打印到 PDF 并存储在其他位置](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)。

## <a name="mailbox-and-calendar"></a>邮箱和日历

使用与组关联的邮箱并不常见，即使可能已在团队频道中进行了许多对话也是如此。 邮箱仅存储直接通过电子邮件发送给它的电子邮件，不包括直接发送到频道的电子邮件。

在某些情况下，存储在邮箱中的电子邮件可能只是会议、Planner 任务更新和其他应用程序或系统生成的邮件的通知。 应查看邮箱的内容以确定是否应保留或删除内容，这一点很重要。

如果将保留策略应用于 Exchange，则电子邮件和日历项目将保留并可通过电子数据展示搜索使用。

**导出邮件和日历**

团队或组成员可以将 [邮箱和日历的内容导出到 Outlook 数据/个人存储 (PST) 文件](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)中。 然后，可以将此文件存储在其他位置，或者可以将内容导入到不同的邮箱中。 不建议使用前者，因为 PST 文件的内容不在 Outlook 中打开，并且文件本身可能会随着时间的推移而损坏。

**IT-执行内容迁移**

管理员可以使用第三方工具在邮箱之间迁移电子邮件和日历内容，而无需任何用户干预。 一个可能的存储位置是专门创建的共享邮箱，它只是用作组邮箱内容的 "存档"。

## <a name="planner"></a>Planner

每个组或团队可以有多个计划。 在脱离过程中，请务必确保每个计划的内容都得到保留，以确保其内容是否保留。 与其他产品一样，有几种方法可以在规划器中分离内容。

**将计划导出到电子表格**

如果只需要为记录保留目的保留计划副本，最简单的方法是将 [计划导出到 Excel 电子表格](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)。 这是单向操作，因为没有用于从电子表格导入计划的选项。

> [!IMPORTANT]
> 将计划导出到 Excel 将在计划中获取大部分信息，但不包含注释、链接或文件。

**将任务复制并移动到另一个计划**

虽然这似乎是一个解决方案，但只能在同一组内的 [计划之间复制或移动](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) 单个任务，这样，如果与计划相关联的组正在删除，则会对福利进行否定。

**复制整个计划**

此外，还可以 [复制整个计划](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)。 但是，它不能指向现有组，也不能位于同一个组中。 复制计划将创建一个新组。 此外，复制整个计划时不包含注释、工作分配、链接、附件或日期。

## <a name="power-automate"></a>Power Automate

在 Power 自动执行中创建并与组或团队关联的流不属于该组，而是由创建者拥有，只是与其他用户和组共享。 因此，如果组或团队被删除，它们不会受到影响。

**更改流的所有权**

如果工作流需要继续运行，则任何所有者都可以简单地将其他用户或 Microsoft 365 组添加为所有者。

**导出流**

如果工作流不需要继续运行，但需要保留以供将来使用，则可以将其 [导出为文件](https://flow.microsoft.com/blog/import-export-bap-packages/) 并在以后再次导入。

## <a name="power-bi"></a>Power BI

Power BI 数据和工作区可以独立于组和团队进行操作，如其他工作负载提供了不同的 offboarded 方式。

**将报告复制到另一个工作区**

如果报表需要在组或团队的有效期之外保留其功能状态，则可以将其 [从现有工作区复制到 POWER BI 中的其他工作区](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)。

**从仪表板或报表中导出数据**

此外，如果报表不再需要处于活动状态，但需要保留数据，则可以将其 [导出到 Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)。

## <a name="project"></a>Project

在 web 上的 Project 中创建的项目和路线图可与 Microsoft 365 组相关联，并提供与 Power BI 类似的分离方法。

**将项目分配给另一个组**

如果需要将项目保留在组或团队的生命周期之外的功能状态中，则可以使用 Dynamics 365 管理中心将其 [分配给不同的 Microsoft 365 组](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) 。

**从项目或路线图中导出数据**

使用 Dynamics 365 管理中心可以将 [用户数据从项目导出](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) 到电子表格，或者如果使用 PowerShell 脚本，可以将数据导出到项目文件 (。MPP) 和 XML 文件格式。

## <a name="sharepoint"></a>SharePoint
工作组通道中的所有文件都存储在关联组的 SharePoint 网站中的文档库中。 在某些情况下，文档之外的内容可能存在于 SharePoint 中，例如列表或页面。
文件通常存储在 SharePoint 网站中的三个主要位置：

- 页面-网站页面库
- 页面中使用的图像–网站资产库
- 频道–文档库中的文件
- Wiki 页面–团队 Wiki 数据库

如果网站中嵌套了一个或多个子网站，则需要为每个子网站重复执行脱离过程。 如果团队包含专用通道，每个频道都有一个单独的 SharePoint 网站。

从组或团队中删除文件时，请务必注意，这些文件可以与不是组或团队成员的用户共享 (是组织内部还是外部) ，因此可能有必要将即将发生的更改传递给他们。

**下载文件**

在上面提到的某个库中，在 SharePoint 中存储的文件的情况下，可以将这些文件 [下载到本地计算机](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)。

**移动文件**

此外，还可以将文件移动到 SharePoint 中的其他位置，如不同网站中的库。
参阅 https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**导出列表** 存储在 SharePoint 列表中的数据可以 [导出到 Excel 电子表格](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)，并再次导入到另一个网站中的列表。

或者，可以使用第三方工具来迁移网站之间的列表，以保留函数、列表视图、格式和其他属性。

**"导出" wiki 文件**

团队频道中的 Wiki 内容存储在关联的 SharePoint 网站的专用库中的 HTML 格式的文件中。 无法轻松导出和导入到其他频道 wiki，但可以转换为 HTML 文件并作为网页打开。

## <a name="microsoft-stream"></a>Microsoft Stream

与电源自动化一样，与组或团队关联的流中的视频实际上并不归组所有，并且在删除组时不会删除这些视频。 Stream 中的视频由上载或创建视频的人所有，即使他们将用户或组添加为所有者也是如此。 在团队频道中记录的会议也是如此。它们由启动录制的人员拥有。

**添加其他所有者**

由于视频保留在流中而不考虑组删除，原始所有者可以 [与其他用户和组共享视频，甚至可以将其添加为所有者](https://docs.microsoft.com/stream/portal-edit-video)。

**下载视频**

在不需要在流中保留或需要将视频存储在其他位置（如记录管理系统）的情况下，所有者可以在 [本地下载](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

与 Microsoft 团队中的对话不同，Yammer 提供了用户和管理员选项来移动或导出对话。

**将对话移动到另一个组或社区**

任何用户都可以将对话移动到另一个 Yammer 组，而不只是所有者或管理员。 在 [经典 Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)以及 [新的 yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) 接口中都可以这样做。

**导出网络数据**

Yammer 网络管理员可以执行 [网络数据导出](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)，但这样做将导出整个网络的所有对话。 生成的导出但列出了组 ID，因此可以基于此 ID 筛选对话。
