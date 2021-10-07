---
title: 组、团队和团队的生命周期结束Yammer
ms.reviewer: mmclean
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
description: 组、团队和团队的生命周期结束Yammer。
ms.openlocfilehash: 883af3878bd0bc68aa539fc1cc36b66c4f1cfe9e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190121"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>组、团队和团队的生命周期结束Yammer

Microsoft 365组和Microsoft Teams使用多个连接的服务。 删除组或团队时，连接服务中的大部分信息也会被删除。 本文介绍在删除信息之前将信息从组或团队中移动来保留信息的选项。

对于不再需要的组或团队，常见做法是将文件从团队中移到其他位置（如文档库）SharePoint存档。 此做法基于旧式工作，其中信息存储在文件和文件夹中，并且通过电子邮件进行通信。

下表概述了与组和团队关联的服务，以及每个组和团队中的内容的关键类型：

|服务|内容的类型|
|:------|:---------------|
|Teams|频道对话、频道中的文件|
|Forms|调查结构和结果|
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

删除组或团队时，还会删除大部分关联的资源。 例外情况包括：

- Stream 中的视频保留且归上传/录制人员所有
- 流Power Automate流保留并归创建者所有。
- Project Web Project中的数据和路线图数据将保留在 CDS 中，并可以单独还原。

组和团队将保持软删除状态 30 天，并且随时都可以还原。 但是，30 天后，它们以及任何关联的资源（如服务和内容）会从Microsoft 365清除。 受保留策略保护的任何内容仍然可以通过电子数据展示搜索使用。

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>组连接的服务的生命周期结束注意事项

团队和组所有者以及 IT 管理员在删除组或团队时需要考虑三个关键方面。

**内容**

团队不再存在后，是否需要保留内容？ 是否足以依赖保留功能Microsoft 365，还是应用和服务中无法提供保留的一些内容？ 是否需要保留内容以用于记录管理、存档或将来使用和参考目的？

为了避免任何潜在的数据丢失，必须先询问这些问题，然后才能存档或删除任何团队。

**服务**

内容是否需要保持其当前工作形式？ 例如，Power BI报告是否需要继续可供访问？ 窗体结果是否需要在可视摘要视图中可用？ 列表中列表是否SharePoint链接或嵌入到任何位置？

在删除基础组之前，必须提出这些问题，因为导出内容可能不够用。

**来宾**

当来宾受邀加入团队时，在将来宾添加到团队Azure Active Directory在主机组织的组织中创建来宾帐户。 删除团队后，不会从团队中删除Azure Active Directory。 虽然来宾无法访问尚未与它们共享的组、网站、团队或内容，但他们仍可以使用 Microsoft Teams 中的功能，例如开始聊天、语音和视频呼叫以及使用应用。

团队或组所有者可以通过将组织外部的某人添加到团队来Azure Active Directory成为团队中的来宾。 但是，团队所有者无法从用户中删除Azure Active Directory。 删除帐户只能由全局管理员或用户管理员执行。

执行来宾评审并了解在团队删除时是否需要从来宾Azure Active Directory很重要。 可能存在来宾保留在目录中的有效情况，例如是其他团队的成员，或者使用其他 Microsoft 365 或 Azure 服务。

## <a name="teams"></a>Teams

Teams内容主要是对话形式。

频道中的对话无法复制或移动使用本机Microsoft Teams功能。 但是，可以使用 Graph API 导出它们。

此外，如果将保留策略应用于Teams，则保留对话并通过电子数据展示搜索提供。 使用高级电子数据展示，可以[重新构建Teams聊天对话](/microsoft-365/compliance/conversation-review-sets)。


### <a name="archiving-a-team"></a>存档团队

存档 [团队的好处是](/microsoftteams/archive-or-delete-a-team) ，它可以像现在一样提供对团队的完全访问权限。 用户仍可以浏览频道对话并打开文件，即使他们未处于活动状态。 此外，如果需要继续处理团队，可以取消存档 (例如，如果项目已) 。

当所有者存档团队时，对于团队中的内容以及关联的网站（如果选中）的成员，该团队SharePoint只读。 此操作的目标是确保频道中的对话保持其现有状态，以及基于SharePoint的内容（如文件和 Wiki）。

在SharePoint网站中没有任何可见更改。 但是，无法更改任何文件或列表，因为 SharePoint 组的权限设置为Microsoft 365 **网站访问者**。 这包括团队OneNote笔记本，存储在网站内的网站资产库中SharePoint笔记本。

存档团队后，基础 Microsoft 365 组仍受过期策略 (如果设置为) ，因此所有者必须继续续订团队。

虽然团队的频道对话和SharePoint网站内容设置为只读，但不适用于其他关联服务：

- 规划器存储桶和任务仍可创建、修改和删除。
- 表单仍可接收提交。
- 邮箱Outlook仍可接收电子邮件。
- Power BI仪表板、报表和数据仍可修改。
- 仍可以在 Web 上的Project编辑项目和路线图。
- 视频仍可在 Stream 中上载、修改和删除。
- Power Automate流仍可创建、修改、删除，并且将继续运行。  (如果需要将邮件张贴到存档团队的频道，他们将失败。) 

## <a name="forms"></a>Forms

虽然窗体可以从单个帐户移动到一个组，但无法从一个组移动或复制到另一个组。 删除团队时，有三个选项可用于表单。

**复制表单**

表单可以 [作为模板共享](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)，从而允许其他用户将其复制到其自己的帐户或组。 这不会保留结果提交的数据;仅表单结构，如问题和设置。

**将结果导出到电子表格**

如果需要保留表单响应的数据，可以通过将结果导出到一个电子表格Excel[实现](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)。 这将仅将问题及其响应导出为数据，不包括由 Forms 创建的图形。

**删除表单**

虽然删除组也会导致删除任何关联的表单，但组成员可以直接删除这些表单，而不需要[](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0)成为组的所有者。 但是，这是一个手动步骤，不提供任何其他好处。

## <a name="onenote"></a>OneNote

包含在OneNote中的笔记本存储在关联网站中的"网站资产"SharePoint库中。 笔记本文件有时可以分布于多个单独的文件中，但无法单独复制和打开它们。 相反，必须使用OneNote移动或导出笔记本OneNote 2016。

**将页面和分区移动到另一个笔记本**

[将页面或分区分别](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) 移动到另一个笔记本，使所有者有机会清理其数据并仅保留需要保留的内容。

**将整个笔记本导出为包**

如果需要保留整个笔记本的现有结构，可以将其导出为OneNote[包](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309)文件，然后导入到新位置。 相反，这可用作将内容保留在单个文件（而不是现有多文件结构）中的方法。

**打印为 PDF 格式**

如果笔记本的一些内容只需要保留作为参考或记录，可以将单个页面打印为 [PDF，并存储在其他位置](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)。

## <a name="mailbox-and-calendar"></a>邮箱和日历

使用与组关联的邮箱的情况并不少见，即使在团队频道中可能进行了很多对话。 邮箱仅存储直接通过电子邮件发送的电子邮件，不包括直接发送到频道的电子邮件。

在某些情况下，邮箱中存储的电子邮件可能是会议、Planner 任务更新以及其他应用或系统生成的邮件的通知。 检查邮箱内容以确定应保留还是删除内容，这一点很重要。

如果保留策略应用于Exchange，电子邮件和日历项目将保留并通过电子数据展示搜索提供。

**导出邮件和日历**

团队或团队成员可以将邮箱和日历的内容导出到 pst [Outlook/Personal 存储 (PST](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)) 文件。 然后，此文件可以存储在其他位置，也可以将内容导入到其他邮箱中。 不建议使用前者，因为 PST 文件的内容如果不在 Outlook 中打开，则不可搜索，并且文件本身会随着时间的推移而损坏。

**IT 执行的内容迁移**

管理员可以使用第三方工具在邮箱之间迁移电子邮件和日历内容，而无需任何用户干预。 一个潜在的存储位置可能是完全作为组邮箱内容的"存档"创建的共享邮箱。

## <a name="planner"></a>Planner

每个组或团队可以有多个计划。 在离开过程中，确保满足每个计划的保留要求非常重要。 与其他服务一样，Planner 中的内容有若干种离开的方法。

**将计划导出到电子表格**

如果只需要保留计划副本以便保留记录，最简单的方法是将计划导出到一个Excel[电子表格](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a)。 这是单向操作 - 无法从电子表格导入计划。

> [!IMPORTANT]
> 将计划导出Excel将在计划中获取大部分信息，但不包括注释、链接或文件。

**将任务复制并移动到另一个计划**

虽然将任务复制或移动到另一个计划看起来像解决方案，但单个任务只能在同[](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b)一组内的计划之间复制或移动。 如果正在删除与计划关联的组，则将不会备份数据。

**复制整个计划**

也可以复制 [整个计划](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4)。 无法将复制操作复制到现有组。 复制计划将创建一个新组。 此外，复制整个计划不包括注释、工作分配、链接、附件或日期。

## <a name="power-automate"></a>Power Automate

在Power Automate中创建且与组或团队关联的流不属于该组。 它们归创建者所有，仅与其他用户和组共享。 因此，如果删除组或团队，则它们不会受到影响。

**更改流的所有权**

如果流需要继续运行，任何所有者都可以将其他用户或Microsoft 365组添加为所有者。

**导出流**

如果流不需要继续运行，但需要保留供将来使用，可以将其导出为文件，稍后再次导入。 [](https://flow.microsoft.com/blog/import-export-bap-packages/)

## <a name="power-bi"></a>Power BI

Power BI数据和工作区可以独立于组和团队运行，并且与其他工作负载一样，提供不同方式的离开。

**将报告复制到其他工作区**

如果在删除组或工作组后需要报表，可以将报表从现有工作区复制到[Power BI。](/power-bi/connect-data/service-datasets-copy-reports)

**从仪表板或报表导出数据**

相反，如果报表不再需要处于活动状态，但需要保留数据，可以导出到[Excel。](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

在 Web Project 中创建的项目和路线图与 Microsoft 365 组相关联，并且具有类似于 Power BI 的方法。

**将项目分配给另一个组**

如果需要在组或工作组的生命周期后将项目保持其功能状态，可以将其分配给不同的Microsoft 365[组](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project)。 这可以使用 Dynamics 365 管理中心完成。

**从项目或路线图导出数据**

使用 Dynamics 365 管理中心，可以导出项目中的用户 [数据到电子表格](/project-for-the-web/export-user-data-from-project-for-the-web) 。 还可将数据导出到Project文件 (。MPP) PowerShell 创建和 XML 文件格式。

## <a name="sharepoint"></a>SharePoint

团队频道中的所有文件都存储在SharePoint组的网站中。 在某些情况下，文档外的内容可能存在于SharePoint，如列表或页面。

文件通常存储在网站中的三个主要SharePoint位置：

- 页面 - 网站页面库
- 页面中使用的图像 – 网站资产库
- 频道中的文件 – 文档库
- Wiki 网页 – Teams Wiki 数据库

如果网站具有一个或多个子网站，则需要针对每个子网站重复执行离开过程。 如果团队包含私人频道，则每个频道SharePoint单独的网站。

从组或团队删除文件时，必须考虑它们可能会与不是组或团队成员的用户共享。 你可能希望与他们传达即将发生的更改。

**下载文件**

存储在SharePoint库之一中的文件可以[下载到本地计算机](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)。

**移动文件**

此外，可以将文件移动到网站中的SharePoint[如不同网站中的库](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)。

**导出列表**

存储在列表SharePoint中的数据可以导出到 Excel[电子表格](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)，并再次导入到另一个网站中的列表。

或者，第三方工具可用于在网站之间迁移列表，以便保留功能、列表视图、格式设置和其他属性。

**"导出"Wiki 文件**

团队频道中的 Wiki 内容存储在与网站关联的网站专用库中的 HTML 格式SharePoint文件中。 它们无法轻松导出并导入其他频道 Wiki，但可以转换为 HTML 文件并作为网页打开。

## <a name="microsoft-stream"></a>Microsoft Stream

与 Power Automate一样，Stream 中与组或团队关联的视频实际上并不归组所有，在删除组时不会删除。 Stream 中的视频归上传或创建视频的用户所有，即使他们添加用户或组作为所有者。 在频道中Teams会议归开始录制的人所有。

**添加其他所有者**

因为视频在组删除时保留在 Stream 中，所以原始所有者可以与其他用户和组共享视频，甚至可以将它们 [添加为所有者](/stream/portal-edit-video)。

**下载视频**

如果视频不需要保留在 Stream 中或需要存储在记录管理系统等备用位置，则所有者可以在本地 [下载它](/stream/portal-download-video)。

## <a name="yammer"></a>Yammer

与 Microsoft Teams 中的Yammer不同，Yammer为用户和管理员提供了移动或导出对话的选项。

**将对话移动到其他组或社区**

对话可以移动到其他用户Yammer组，而不只是所有者或管理员。 这一点在经典[Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)[和新的 Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)接口中都可行。

**导出网络数据**

Yammer管理员导出[网络数据](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 但是，这样做将导出整个网络的所有对话。 生成的导出将列出组 ID。 可以基于此 ID 筛选对话。

## <a name="related-topics"></a>相关主题

[删除以前的员工和安全数据](/microsoft-365/admin/add-users/remove-former-employee)
