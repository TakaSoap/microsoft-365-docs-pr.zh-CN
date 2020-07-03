---
title: 将非 custodial 数据源添加到高级电子数据展示事例
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
description: 您可以将非 custodial 数据源添加到高级电子数据展示事例，并在数据源中放置保留。 非 custodial 数据源是编制索引，因此被视为部分索引的任何内容都将重新处理，以使其完全和快速地可搜索。
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024742"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>将非 custodial 数据源添加到高级电子数据展示事例

在高级电子数据展示事例中，它并不总是满足将 Microsoft 365 数据源与事例中的管理员相关联的需求。 但您可能仍需要将该数据与大小写相关联，以便对其进行搜索、将其添加到审阅集并进行查看。 称为 "*非 custodial" 数据源*的新功能使您可以向事例添加数据，而无需将数据与保管人进行关联。 它还将相同的高级电子数据展示功能应用于可用于与保管人关联的数据的非 custodial 数据。 可应用于非 custodial 数据的两个最有用的功能是将其置于保留状态，并使用[高级索引](indexing-custodian-data.md)进行处理。

## <a name="add-a-non-custodial-data-source"></a>添加非 custodial 数据源

按照以下步骤在高级电子数据展示事例中添加和管理非 custodial 数据源。

1. 在**高级电子数据展示**主页上，单击要向其添加数据的事例。

2. 在 "**源**" 页上，单击 "**数据位置**" 选项卡，然后单击 "**添加数据位置**"。

3. 单击 "**添加数据位置**"，然后选择要添加到该事例的数据源。 您可以添加多个邮箱和网站。

4. 在向导的 "**选择位置**" 页上，将邮箱或网站（或两者）添加为事例中的非 custodial 数据源。

5. 添加数据源后，单击 "**下一步**"。

6. 在 "**就地保留**" 页上，选择或取消选择关联的复选框，以选择要置于保留状态的数据源。

7. 验证保留选择，然后单击 "**提交**"。

   您添加的每个非 custodial 数据源都列在 "**数据源**" 页上。

   此外，将创建一个名为 "*索引非 custodial" 数据*的作业，并将其显示在该案例的 "**作业**" 选项卡上。 在创建作业之后，启动的高级索引过程和数据源将编制索引。

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>管理对非 custodial 数据源的保留

在非 custodial 数据源上放置保留后，将自动创建包含该事例的所有非 custodial 数据源的保留策略。 将其他非 custodial 数据源置于保留状态时，它们将被添加到此保留策略中。

1. 在该事例的**主页**上，单击 "**保留**" 选项卡。

2. 在 "**保留**" 页上，单击 " **NCDSHold- \<GUID\> **"，其中 GUID 值对事例是唯一的。

3. 在弹出页面上，单击 "**编辑保留**" 以查看置于保留状态的所有非 custodial 数据源。

您可以在非 custodial 数据源上执行以下管理任务：

- 您可以编辑保留以创建一个应用于该情况下的所有非 custodial 数据源的基于查询的保留。

- 您可以从保留中释放非 custodial 数据源。 释放数据源不会从事例中删除非 custodial 数据源。 它仅删除在数据源上放置的保留。
