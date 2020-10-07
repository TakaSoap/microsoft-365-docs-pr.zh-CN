---
title: Microsoft 365 中的协作管理概述
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
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 了解如何在 Microsoft 365 组、团队、SharePoint 和 Yammer 中管理相关功能。
ms.openlocfilehash: 8784f14530ec94a3151ef58589944947b5de9514
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377577"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Microsoft 365 中的协作管理概述

Microsoft 365 提供了一组丰富的工具来实施您的组织可能需要的任何管理功能。 本文指导 IT 专业人员提出正确的问题，以确定他们的治理要求以及如何根据组织的配置文件来满足这些要求。

## <a name="what-are-microsoft-365-groups"></a>什么是 Microsoft 365 组？

我们知道，目前的组织使用的是各种各样的工具集。 拥有团队聊天的开发人员团队、负责发送电子邮件的开发人员以及通过企业社会进行连接的整个组织。 由于每个组都是唯一的，并且具有自己的功能需求和工作样式，因此使用多个协作工具。 有些将仅使用电子邮件，而其他人将主要驻留在聊天中。 

如果用户认为 IT 提供的工具不能满足其需求，他们可能会下载其喜爱的使用者应用程序来支持其应用场景。 虽然此过程允许用户快速入门，但它会导致在组织中遇到多个登录、难以共享且没有查看内容的单一位置的用户体验。 此概念称为 "隐藏 IT"，并给组织带来了巨大风险。 它降低了统一管理用户访问、确保安全性和服务合规性需求的能力。

Microsoft 365 组、团队和 Yammer 等服务可为用户提供协作，并通过提供协作所需的工具降低了阴影风险。 通过 Microsoft 365 组，您可以选择要与之进行协作的一组人员，并轻松为要共享的人员设置资源的集合。 向组添加成员会自动将所需的权限授予组提供的所有资产。 团队和 Yammer 都使用 Microsoft 365 组来管理其成员资格。

![显示 Microsoft 365 组和相关服务的图表](../media/microsoft-365-groups-hub-spoke.png)

Microsoft 365 组包括各种控制措施，包括过期策略、命名约定和阻止的词语策略，可帮助您管理组织中的组。 有关详细信息，请参阅 [规划 microsoft 365 组和 Microsoft 团队的组织和生命周期管理](plan-organization-lifecycle-governance.md) 。

## <a name="technical-architecture"></a>技术体系结构

Microsoft 365 支持以下三种主要的通信方法：

- Outlook：通过使用共享组收件箱和日历的电子邮件进行协作
- Microsoft 团队：一种基于持久聊天的工作区，您可以在其中围绕各种主题（按特定子组组织的主题）进行非正式、实时的对话
- Yammer：协作的企业社交体验

> [!NOTE]
> 通过其他团队应用程序（如 SharePoint、Planner 或 Stream）创建新组-将使用 Outlook 收件箱创建一个组，并能够连接到团队。

根据创建组的位置，将自动预配某些资源，如：
- [收件箱](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -组成员之间的电子邮件对话。 此收件箱有一个电子邮件地址，可以将其设置为接受来自组外部的人的邮件，甚至来自您的组织外部的邮件，这与传统的通讯组列表非常相似。
 - [日历](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) –用于计划与组相关的事件
- [SharePoint 团队网站](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) –中心存储库，其中提供了与您的组相关的信息、链接和内容
- [OneNote 笔记本](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) –用于收集想法、研究和信息
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) –用于分配和管理组成员中的项目任务
- [Yammer 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) –一个用于提供对话和共享信息的常见位置
- 团队– Microsoft 365 中的基于聊天的工作区
- Stream-视频流服务

> [!NOTE]
> 当通过 Yammer 或团队创建新的 Office 365 组时，该组在 Outlook 或通讯簿中不可见，因为这些用户之间的主通信在其各自的客户端中发生。 Yammer 组不能连接到团队。

## <a name="collaboration-options"></a>协作选项

在 Microsoft 365 中有多个位置需要进行协作和对话。 了解从何处开始对话可帮助您定义通信策略。

![显示何时使用团队、Yammer 和 Outlook 的图示](../media/inner-loop-outer-loop.png)

- 团队：基于聊天的工作区 (高速度协作) – inner 循环
  - 为与每天合作的人员进行协作而构建
  - 通过单一体验将信息放在用户的手边
  - 添加选项卡、连接器和 bot
  - 实时聊天、音频/视频会议、录制的会议

- Yammer：跨组织 (企业社交) –外部循环连接
  - 实践的社区-跨职能组的人员，这些人共享共同的兴趣或专业技能，但不一定每天都在进行协作。
  - 领导层连接、学习社区、基于角色的社区

- 邮箱和日历 (基于电子邮件的协作) 
  - 用于与一组人员进行目标通信
  - 与其他组成员的会议的共享日历
 
每个组都将获取一个连接的 SharePoint 团队网站，用户可以在其中共享内容、创建自定义页面和作者新闻。 您还可以 [将现有 SharePoint 团队网站连接到新的 Microsoft 365 组](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)。

## <a name="illustrations"></a>阐释

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>面向 IT 架构师的 Microsoft 365 中的 Microsoft Teams 和相关生产力服务
Microsoft 365 中生产力服务的逻辑体系结构，以 Microsoft Teams 为主导。

|**项**|**说明**|
|:-----|:-----|
|[![Teams 逻辑体系结构海报缩略图](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>2019 年 4 月更新   |Microsoft 提供了一系列生产力服务，这些服务协同工作，提供数据治理、安全性和符合性相关功能的协作体验。 <br/> <br/>此系列图示展示了企业架构师生产力服务的逻辑体系结构，以 Microsoft Teams 为主导。|


### <a name="groups-in-microsoft-365-for-it-architects"></a>面向 IT 架构师的 Microsoft 365 中的组
对于 Microsoft 365 中的组，IT 架构师需要了解的信息

|**项**|**说明**|
|:-----|:-----|
|[![组信息图的缩略图](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 2019 年 6 月更新|这些图示详细介绍了不同类型的组，如何创建和管理这些组，以及一些治理建议。|

## <a name="conference-sessions"></a>会议会话

观看这些会议会话以了解有关 Microsoft 365 组和团队的公司治理的详细信息。

**知识**

了解 Microsoft 365 组中的基础知识和新创新，包括在规模扩展方面的管理和治理、驱动使用和采用的最佳实践以及自助服务。

- [接纳 Microsoft 365 组](https://www.youtube.com/watch?v=dAamBF1gb7M)

**管理**

了解如何设置您的组过期生命周期、命名策略、分类标签、与外部来宾的协作以及管理组创建权限。

- [使用 Office 365 组转换协作和抵抗影子 IT](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**客户示例**

请参阅 Microsoft 365 组、SharePoint、团队和 Yammer 如何协同工作以提供全局协作平台的幕后示例。

- [使用 Office 365 组、SharePoint、团队和 Yammer 查找你的协作最佳位置](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
