---
title: 组、团队和团队的生命周期结束Yammer
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
description: 组、团队和团队的生命周期结束Yammer。
ms.openlocfilehash: f1f91e64af7e16016398a7c326feec5a9b073ca9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333778"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>组、团队和团队的生命周期结束Yammer

Microsoft 365组Microsoft Teams可处理各种已连接服务。 删除组或团队时，连接服务中的大部分信息也会被删除。 本文介绍在删除信息之前将信息从组或团队中移动来保留信息的选项。

对于不再需要的组或团队，一种常见做法是将文件从团队中移到另一个位置（如充当存储库或存档的 SharePoint 文档库）。 此做法基于旧式工作，其中信息存储在文件和文件夹中，并且通过电子邮件进行通信。

下表概述了与组和团队关联的服务，以及每个组和团队中的内容的关键类型：

|服务|内容的类型|
|:------|:---------------|
|Teams|频道对话、频道中的文件|
|表单|调查结构和结果|
|OneNote|笔记本|
|Outlook|邮件和日历|
|Planner|Project状态和任务信息|
|Power Automate|工作流|
|Power BI|数据、报表和仪表板|
|Project网页|Project计划|
|路线图|路线图|
|SharePoint|文件、列表Teams频道 Wiki 数据|
|Stream|视频|
|Yammer|对话|

删除组或团队时，还会删除大部分关联的资源。 其中一些例外情况包括 Stream 中的视频，这些视频仍保留且仍归上传/录制人员所有，就像流式传输Power Automate。 Project Web Project中的数据和路线图数据将保留在 CDS 中，并可以单独还原。

组和团队将保持软删除状态 30 天，并且随时都可以还原。 但是，30 天后，它们以及任何关联的资源（如服务和内容）将完全从Microsoft 365清除。 受保留策略保护的任何内容仍然可以通过电子数据展示搜索使用。

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>组连接的服务的生命周期结束注意事项

团队和组所有者以及 IT 管理员在删除组或团队时需要考虑三个关键方面。

**Content**

在团队不再可用或存在后，是否需要保留内容？ 是否足够依赖应用程序的保留Microsoft 365，或者应用和服务中是否包含一些未提供保留的内容？ 内容是否需要保留以用于记录管理、存档或供将来使用和参考？

必须先询问这些问题，然后才能存档或删除任何团队，以避免任何潜在的数据丢失。

**服务**

除了各种应用和服务的内容外，它们是否需要保持其当前工作形式？ 例如，Power BI报告是否需要继续可供访问，窗体结果是否需要在可视摘要视图中可用，SharePoint列表是否链接到或嵌入到任何位置？

与内容注意事项类似，在删除基础组之前，必须提出这些问题，因为仅导出内容可能是不够的。

**来宾**

当来宾受邀加入团队时，工作流会先在主机组织的 Azure Active Directory创建其标识，然后再将来宾添加到团队。 删除团队后，不会将来宾Azure Active Directory因此，来宾仍存在于Microsoft Teams环境中。 虽然来宾无法访问尚未与它们共享的组、网站、团队或内容，但他们仍可以使用 Microsoft Teams 中的功能，例如发起聊天、语音和视频呼叫以及使用应用。

团队或组所有者可以邀请外部用户成为 Azure Active Directory中的来宾、将其添加到团队以及从团队中删除他们。 但是，团队所有者无法将来宾从 Azure Active Directory - 这只能由全局管理员或用户管理员执行。

因此，执行来宾评审以及了解在团队删除时是否需要从来宾Azure Active Directory很重要。 来宾可能仍保留在目录中，例如是一个或多个其他团队的成员，或者使用其他 Microsoft 365 Azure 服务。

## <a name="teams"></a>Teams

Teams内容主要是对话形式。

频道中的对话不能使用本机或Microsoft Teams移动。 但是，可以使用 Graph API 导出它们。

此外，如果将保留策略应用于Teams，对话将保留并通过电子数据展示搜索提供。 使用高级电子数据展示，你可以[重新构建Teams对话。](/microsoft-365/compliance/conversation-review-sets)


### <a name="archiving-a-team"></a>存档团队

存档 [团队的好处](/microsoftteams/archive-or-delete-a-team) 是，它可以像现在一样提供对团队的完全访问权限，以便用户仍可浏览频道对话并打开文件，即使他们没有处于活动状态。 此外，如果需要在项目扩展服务中继续 (团队，可以取消存档) 。

当所有者存档团队时，对于团队中的内容以及关联的网站（如果选中）的成员，该团队SharePoint只读。 此操作的目标是确保频道中的对话保持其现有状态，以及基于SharePoint的内容（如文件和 Wiki）。

在 SharePoint 网站中，没有可见的更改，但是，当 Microsoft 365 组的基于 SharePoint 的权限组设置为"网站访问者"级别时，不能更改任何文件或列表。 这包括团队OneNote笔记本，因为此笔记本存储在网站内的网站资产SharePoint库中。

存档团队后，基础 Microsoft 365 组仍受过期策略 (如果设置为) ，则所有者必须继续续订团队。

虽然团队的频道对话和SharePoint网站内容设置为只读，但相同的内容不适用于其他关联服务：

- 仍可以创建、修改和删除 Planner 存储桶和任务
- 表单仍可接收提交
- 邮箱Outlook仍可接收电子邮件
- Power BI仪表板、报表和数据仍可修改
- 仍可以在 Web 上的Project编辑项目和路线图
- 视频仍可在 Stream 中上载、修改和删除
- Power Automate流仍可创建、修改、删除，并且将继续运行 (但是，如果需要将邮件张贴到存档团队邮箱的频道，这些流) 

## <a name="forms"></a>表单

虽然窗体可以从单个帐户移动到一个组，但不能从一个组移动或复制到另一个组。 删除团队时，有三个选项可用于表单。

**复制表单**

表单可以 [作为模板共享](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)，从而允许其他用户将其复制到其自己的帐户或组。 这不会保留结果提交的数据;仅表单结构，如问题和设置。

**将结果导出到电子表格**

如果需要保留表单响应的数据，可以通过将结果导出到电子表格中Excel[实现](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)。 这将仅将问题及其响应导出为数据 ，不包括由 Forms 创建的图形。


**删除表单**

虽然删除组也会导致删除任何关联的表单，但组成员可以直接删除这些表单，而无需成为[](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0)组的所有者，但这是一个手动步骤，不会提供任何额外好处。

## <a name="onenote"></a>OneNote

包含在OneNote中的笔记本存储在关联网站中的"网站资产"SharePoint库中。 笔记本文件有时可以分布于多个单独的文件中，但无法仅单独复制和打开它们。 相反，必须使用OneNote移动或导出笔记本OneNote 2016。

**将页面和分区移动到另一个笔记本**

[将页面或分区分别](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) 移动到另一个笔记本，使所有者有机会清理其数据并仅保留需要保留的内容。

**将整个笔记本导出为包**

如果需要保留整个笔记本的现有结构，可以将其导出为 [OneNote](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) 包文件，然后导入到新位置。 或者，这可用作将内容保留在单个文件中而不是现有多文件结构中的方法。

**打印为 PDF 格式**

如果笔记本的一些内容只需要保留作为参考或记录，可以将单个页面打印为 [PDF，并存储在其他位置](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)。

## <a name="mailbox-and-calendar"></a>邮箱和日历

使用与组关联的邮箱的情况并不少见，即使在团队频道中可能进行了很多对话。 邮箱仅存储直接通过电子邮件发送的电子邮件，不包括直接发送到频道的电子邮件。

在某些情况下，邮箱中存储的电子邮件可能只是会议、Planner 任务更新以及其他应用或系统生成的邮件的通知。 检查邮箱的内容以确定应保留还是删除内容，这一点很重要。

如果将保留策略应用于 Exchange，电子邮件和日历项目将保留并通过电子数据展示搜索提供。

**导出邮件和日历**

团队或团队成员可以将邮箱和日历的内容导出到 [Outlook 数据/](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)个人存储 (PST) 文件。 然后，此文件可以存储在其他位置，也可以将内容导入到其他邮箱中。 不建议使用前者，因为如果不在 Outlook 中打开 PST 文件，则不能搜索该文件的内容，并且文件本身会随着时间的推移而损坏。

**IT 执行的内容迁移**

管理员可以使用第三方工具在邮箱之间迁移电子邮件和日历内容，而无需任何用户干预。 一个潜在的存储位置可能是完全作为组邮箱内容的"存档"创建的共享邮箱。

## <a name="planner"></a>Planner

每个组或团队可以有多个计划。 在载出过程中，确保解决每个计划的内容是否保留的问题非常重要。 与其他产品一样，Planner 中具有多种从内容上离开的方法。

**将计划导出到电子表格**

如果只需要保留计划副本以便保留记录，最简单的方法是将计划导出 [到 Excel 电子表格](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)。 这是单向操作，因为无法从电子表格导入计划。

> [!IMPORTANT]
> 将计划导出到 Excel 将获取计划中大部分信息，但不包括注释、链接或文件。

**将任务复制并移动到另一个计划**

尽管这看起来像是解决方案，但单个任务只能在同一[](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b)个组内的计划之间复制或移动，如果删除与计划关联的组，则这样做会否定其中的好处。

**复制整个计划**

也可以复制 [整个计划](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)。 但是，这不能用于现有组，甚至不能位于同一个组内。 复制计划将创建一个新组。 此外，复制整个计划将不包括注释、工作分配、链接、附件或日期。

## <a name="power-automate"></a>Power Automate

在 Power Automate 中创建且与组或团队关联的流不属于组，而归创建者所有，仅与其他用户和组共享。 因此，如果删除组或团队，则它们不会受到影响。

**更改流的所有权**

如果工作流需要继续运行，则任何所有者只需将其他用户或 Microsoft 365 组添加为所有者。

**导出流**

如果工作流不需要继续运行，但需要保留供将来使用，可以将其导出为文件，稍后再次导入。 [](https://flow.microsoft.com/blog/import-export-bap-packages/)

## <a name="power-bi"></a>Power BI

Power BI 数据和工作区可以独立于组和团队运行，并且与其他工作负载一样，提供不同方式进行离开。

**将报告复制到其他工作区**

如果需要在组或团队的生命周期之外保持报表的功能状态，可以将报表从现有工作区复制到 Power BI 中的另一 [个工作区](/power-bi/connect-data/service-datasets-copy-reports)。

**从仪表板或报表导出数据**

或者，如果报表不再需要处于活动状态，但需要保留数据，可以导出到 [Excel](/power-bi/visuals/power-bi-visualization-export-data)。

## <a name="project"></a>Project

在 Project 网页版中创建的项目和路线图可以与 Microsoft 365 组相关联，并提供类似于 Power BI 的载出方法。

**将项目分配给另一个组**

如果需要在组或团队的生命周期之外保持项目的功能状态，可以使用 Dynamics 365 管理中心将其分配给其他 [Microsoft 365](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) 组。

**从项目或路线图导出数据**

使用 Dynamics 365 管理中心，可以将[](/project-for-the-web/export-user-data-from-project-for-the-web)项目的用户数据导出到电子表格，或者，如果使用 PowerShell 脚本，可以将数据导出到 Project (。MPP) 和 XML 文件格式。

## <a name="sharepoint"></a>SharePoint
团队频道中的所有文件都存储在关联组的 SharePoint 网站的文档库中。 在某些情况下，除文档外的内容可能存在于 SharePoint 中，如列表或页面。
文件通常存储在 SharePoint 网站的三个主要位置：

- 页面 - 网站页面库
- 页面中使用的图像 – 网站资产库
- 频道中的文件 – 文档库
- Wiki 网页 – Teams Wiki 数据库

如果网站下方嵌套了一个或多个子网站，则需要针对每个子网站重复执行载出过程。 如果团队包含私人频道，则每个频道都有单独的 SharePoint 网站。

从组或团队删除文件时，必须考虑它们可能会与不是组或工作组 (成员的用户共享 (无论是组织) 的内部用户还是外部用户，因此，向它们传达即将发生的更改可能值得。

**下载文件**

对于存储在上述库之一的 SharePoint 中的文件，可以将这些文件 [下载到本地计算机](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)。

**移动文件**

此外，可以将文件移动到 SharePoint 中的另一个位置，如不同网站中的库。
参考： https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**导出列表** 存储在 SharePoint 列表中的数据可以导出到 [Excel](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)电子表格，并再次导入到另一个网站中的列表。

或者，第三方工具可用于在网站之间迁移列表，以便保留功能、列表视图、格式设置和其他属性。

**"导出"Wiki 文件**

团队频道中的 Wiki 内容存储在相关 SharePoint 网站的专用库中的 HTML 格式文件中。 它们无法轻松导出并导入其他频道 Wiki，但可以转换为 HTML 文件并作为网页打开。

## <a name="microsoft-stream"></a>Microsoft Stream

与 Power Automate 一样，Stream 中与组或团队关联的视频实际上并不归组所有，在删除组时不会删除。 Stream 中的视频归上传或创建视频的用户所有，即使他们添加用户或组作为所有者。 在 Teams 频道中录制的会议也是这种情况;它们归发起录制的人所有。

**添加其他所有者**

由于视频保留在 Stream 中而不考虑组删除，因此原始所有者可以与其他用户和组共享视频，甚至可以将它们 [添加为所有者](/stream/portal-edit-video)。

**下载视频**

如果视频不需要保留在 Stream 中或需要存储在记录管理系统等备用位置，则所有者可以本地 [下载它](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

与 Microsoft Teams 中的对话不同，Yammer 为用户和管理员提供了移动或导出对话的选项。

**将对话移动到其他组或社区**

对话可以通过任何用户（而不仅是所有者或管理员）移动到另一个 Yammer 组。 这一点在经典 [Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)和新的 [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) 界面中都可行。

**导出网络数据**

Yammer 网络管理员可以 [执行网络数据](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)导出，但这样做将导出整个网络的所有对话。 但是，生成的导出会列出组 ID，因此可以基于此筛选对话。
