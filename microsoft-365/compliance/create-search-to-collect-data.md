---
title: 创建搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 4b740b07b59b7500b8f57584767796b7f31ae87d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635972"
---
# <a name="create-a-search"></a>创建搜索

在您的案例的 "**搜索**" 选项卡上，您可以通过单击 "**新建搜索**" 并按照向导创建新的搜索。

![高级电子数据展示案例中的搜索向导](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>命名搜索并为其提供说明

每个具有事例的搜索应具有唯一的名称。 您可以选择为搜索提供说明。 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>选择要搜索的保管人和 custodial 位置

通过指定已添加到案例中的保管人，选择 "保管人内容位置" 进行搜索。 通过选择管理员，你将对映射到保管人的所有数据源运行搜索。 您还可以选择将搜索范围缩小到每个保管人的选定数据源。 有关如何添加保管人和管理其数据源的详细信息，请参阅[使用保管人](managing-custodians.md)。

## <a name="choose-non-custodial-locations"></a>选择非 custodial 位置

在某些情况下，您可能希望搜索与保管人不关联的数据源。 在这种情况下，您可以指定要搜索的位置，或选择搜索特定 Microsoft 服务（如搜索所有 Exchange 邮箱或所有 SharePoint 网站和 OneDrive 帐户）的所有内容位置。

## <a name="define-the-search-query-and-conditions"></a>定义搜索查询和条件

您可以使用预建的条件卡或使用关键字查询语言（KQL）定义搜索的关键字查询和任何条件。 有关详细信息，请参阅[构建搜索查询](building-search-queries.md)。
