---
title: 向事件案例添加非Advanced eDiscovery数据源
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 您可以将非安全数据源添加到Advanced eDiscovery案例，并保留数据源。 非索引数据源会重新编制索引，因此将重新处理标记为部分索引的任何内容，使其完全且快速可搜索。
ms.openlocfilehash: a4702ebdfbd41b2541c51380a1d44dd133d506c9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193215"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>向事件案例添加非Advanced eDiscovery数据源

在这种情况下Advanced eDiscovery，并不一定满足将Microsoft 365数据源与事例保管人相关联的需求。 但是，您可能仍然需要将该数据与案例关联，以便可以搜索该数据、将其添加到审阅集并分析和审阅数据。 Advanced eDiscovery中的功能称为"*非* 托管数据源"，允许您向案例添加数据，而无需将其与保管人关联。 它还将相同的Advanced eDiscovery功能应用于可用于与保管人关联的数据的非托管数据。 可应用于非存储数据的两个最有用的内容是将其置于保留状态，然后使用 [高级索引处理它](indexing-custodian-data.md)。

## <a name="add-a-non-custodial-data-source"></a>添加非安全数据源

按照以下步骤添加和管理数据案例的非Advanced eDiscovery数据源。

1. 在 **Advanced eDiscovery** 主页上，单击要将数据添加到的大小写。

2. 单击"**数据源"** 选项卡，然后单击"**添加数据源**  >  **""添加数据位置"。**

3. 在 **"新建非空** 数据位置"飞出页上，选择要添加到案例的数据源。 可以添加多个邮箱和网站，方法是展开 **SharePoint或Exchange****部分，** 然后单击"编辑 **"。**

   ![添加SharePoint网站Exchange邮箱作为非安全数据源。](../media/NonCustodialDataSources1.png)

   - **SharePoint** - 单击 **"编辑**"添加网站。 在列表中选择网站，或者可以通过在搜索栏中键入网站的 URL 来搜索网站。 选择要添加为非保管人数据源的网站，然后单击"添加 **"。**

   - **Exchange** - 单击 **"编辑**"添加邮箱。 键入名称或别名 (在邮箱或通讯) 搜索框中键入至少三个字符。 选择要添加为非保管人数据源的邮箱，然后单击"添加 **"。**

   > [!NOTE]
   > 可以使用"SharePoint"和 **"Exchange"** 部分将与 Team 或 Yammer 组关联的网站和邮箱添加为非安全数据源。 必须单独添加与团队或组关联的邮箱Yammer网站。<br/><br/> 此外，不支持将根网站 URL (或) 作为SharePoint添加根网站 `https://contoso-my.sharepoint.com/personal/` `https://contoso-my.sharepoint.com/` URL。 您必须添加特定网站。

4. 添加非安全数据源后，您可以选择是否保留这些位置。 选中或取消 **选中数据源旁边的** "保留"复选框以将其保留。

5. 单击 **"** 新建非安全数据位置"飞出页底部的"添加"，将数据源添加到案例。

   您添加的每个非安全数据源都列在"数据源 **"页上** 。 非当前数据源由"源类型"列中 **的"数据位置** " **值** 标识。

   !["数据源"选项卡上的非主要数据源。](../media/NonCustodialDataSources2.png)

向案例添加非安全数据源后，将创建名为 *"重新* 索引非备份数据"的作业，并显示在案例的"作业"选项卡上。  创建作业后，将启动高级索引过程，并重新编制数据源索引。

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>管理非托管数据源的保留

将非托管数据源放在保留状态后，将自动创建包含案例的非托管数据源的保留策略。 当您将其他非安全数据源放在保留状态时，它们将被添加到此保留策略。

1. 打开Advanced eDiscovery案例并选择"保留 **"** 选项卡。

2. 单击 **NCDSHold- \<GUID\>**，其中 GUID 值对大小写是唯一的。

   该飞出页显示有关非保留数据源的信息和统计信息。

   ![非报表数据源保留的飞出页显示统计信息。](../media/NonCustodialDataSourcesHoldFlyout.png)

3. 单击 **"编辑** 保留"以查看置于保留状态的非托管数据源并执行以下管理任务：

   - 在 **"位置"** 页上，可以通过从保留项中删除非托管数据源来释放该数据源。 释放数据源不会从案例中删除非安全数据源。 它仅删除对数据源的保留。

   - 在 **"查询** "页上，可以编辑保留以创建应用于所有非查询数据源的基于查询的保留。
