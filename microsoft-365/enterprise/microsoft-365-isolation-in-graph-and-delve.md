---
title: Microsoft 365Microsoft 租户和租户Graph Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文介绍租户隔离Microsoft 365在租户和Office Graph中Delve。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464060"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365Microsoft 租户和租户Graph Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft 租户中的租户Graph

[Microsoft Graph](https://developer.microsoft.com/graph)模型 Microsoft 365 服务（包括 Exchange Online、SharePoint Online、Yammer、Skype for Business、Azure Active Directory 等）以及外部服务（如其他 Microsoft 服务 或第三方服务）中的活动。 Microsoft Graph组件在整个Microsoft 365。 Microsoft Graph 表示内容和活动的集合，以及在整个 Office 套件中发生的关系。 它使用复杂的机器学习技术将用户连接到相关内容、对话和周围的人员。 例如，SharePoint Online 中的租户索引具有用于处理 Delve 查询的 Microsoft Graph 索引，SharePoint Online 中的分析处理引擎用于存储信号和计算见解，Exchange Online 将每个用户的收件人缓存作为输入计算到租户分析中。

Microsoft Graph包含有关企业对象（如人员与文档）的信息，以及这些对象之间的关系和交互。 关系和交互表示为 *边缘*。 Microsoft Graph按租户进行分段，因此边缘只能在同一租户中的节点之间存在。  节点 *是* 具有统一资源标识符 (URI) 、节点类型、访问控制列表以及一组包含元数据和边缘的 Facet 的实体。  每个节点都有关联的元数据和边缘，如 Common  Knowledge Model 中一样排列成多个 Facet。 *元数据* 是存储在节点上的命名属性，可用于搜索、筛选或分析 Microsoft Graph。 Facet 是节点上元数据和边缘的逻辑集合。 每个方面描述节点的一个方面。 

Microsoft Graph不会将所有数据引入单个存储库;相反，它会存储有关保存在其他位置的数据的元数据和关系。 Microsoft Graph由多个数据存储和处理组件组成：

- 租户Graph应用商店提供针对高效分析进行优化的批量存储。
- 利用活动内容缓存，可以快速随机访问活动节点和边缘，以驱动用户体验。
- 输入路由器通知组件租户图的内部和外部更改。

每个工作负载中的分析可推断与租户范围内计算相关的见解，并推送到租户图。 租户分析对租赁中所有活动的原因，以生成对行为模式的见解。 例如，Exchange Online计算每个用户的收件人缓存，并分析每个用户邮箱的高效原因。 这些每用户分析在每个人上生成一组 *RecipientCache* 边缘，这些边缘又推送到租户图。 这样可使分析处理尽可能接近源数据。

## <a name="tenant-isolation-in-delve"></a>租户隔离Delve

如前所述，Microsoft Graph 提供了可帮助用户发现和协作处理企业中当前活动的体验，并提供了一个以实体为中心的平台，用于分析工作负载及 Microsoft 365 之外的内容和活动。 Delve是 Microsoft Graph 支持的第一个此类Graph。
Delve是一Microsoft 365 Web 体验，它通过 Microsoft Microsoft 365 Yammer Enterprise向Microsoft 365用户显示Graph。 Web 体验将数据显示为不同的板，每个板都有一个特定主题，例如"我周围的趋势 *"或"**我修改的"。* 每个板由若干个文档卡片组成，这些卡片显示文档的摘要文本和图片。 该卡片允许用户执行打开文档或Yammer页等操作。 Microsoft 365 租户中的每个人都有一个页面，其中显示此人最相关的文档，以及可以调用 Exchange Online 或 Skype for Business 与此人交互的图标。 由于Delve基于 Microsoft Graph API，因此受基于租户的 API 隔离的约束。