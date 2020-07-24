---
title: 了解记录
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解有关记录的信息，以帮助您在 Microsoft 365 中实现记录管理解决方案。
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372517"
---
# <a name="learn-about-records"></a>了解记录

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

在 Microsoft 365 中管理记录可帮助组织遵守公司策略、法律或法规义务，同时降低风险和法律责任。

当内容被标记为记录时：

- 会针对[允许或阻止对记录项进行的操作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)施加限制。

- 记录了有关该项的其他活动。

- 保留期结束时将其删除时，拥有处置证明。

使用[保留标签](retention.md#retention-labels)将内容标记为记录。 你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。

通过使用保留标签来将内容标记为记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>比较对允许或阻止的操作的限制

使用以下表格识别应用标准保留标签和将内容标记为记录的保留标签后，对内容施加的限制。 

标准保留标签的配置为无需将内容标记为记录，即可保留数据。

>[!NOTE] 
> 为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。 锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](#record-versioning)功能。 因此，对于标记为记录的所有 Exchange 项目，该行为会映射到**记录 - 已锁定**列，而**记录 - 已解锁列**则不相关。


|操作| 保留标签 |记录 - 已锁定| 记录 - 已解锁|
|:-----|:-----|:-----|:-----|:-----|
|编辑内容|允许 | **阻止** | 允许|
|编辑属性（包括重命名）|Allowed |允许 | Allowed|
|删除|允许 <sup>1</sup> |**阻止** | **阻止**|
|复制|Allowed |允许 | Allowed|
|在容器 <sup>2</sup> 中移动|Allowed |允许 | Allowed|
|围绕容器 <sup>2</sup> 移动|允许 |如果从未解锁，则允许 | 允许|
|打开/读取|Allowed |允许 | Allowed|
|更改标签|允许 |允许 - 仅容器管理员 | 允许 - 仅容器管理员|
|删除标签|允许 |允许 - 仅容器管理员 | 允许 - 仅容器管理员|

页脚：

<sup>1</sup>OneDrive 和 Exchange 支持此功能，方法是在安全位置保留一份副本，但 SharePoint 阻止此功能。

向用户发送一条消息，询问用户是否尝试删除 SharePoint 中带标记的文档：

![指明项未从 SharePoint 中删除的消息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup>容器包括 SharePoint 文档库和 Exchange 邮箱。


## <a name="using-retention-labels-to-declare-records"></a>使用保留标签声明记录

创建保留标签时，可视需要使用保留标签将内容标记为记录：

1. 在 Microsoft 365 合规性中心，转到“记录管理”****\>“文件计划”****。 在“文件计划”**** 页面上，选择“创建标签”****。

2. 在向导的“**标签设置**”页面上，选择将内容分类为记录的选项。
    
   ![选中“使用标签将内容分类为‘记录’”复选框](../media/recordversioning6.png)

3. 根据需要，将保留标签应用于 SharePoint 或 OneDrive 文档和 Exchange 电子邮件。 有关说明，请参阅以下内容：
    
    - [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
    
    - [自动向内容应用保留标签](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a>对内容应用已配置保留标签

当用户可对应用中的内容应用将内容标记为记录的保留标签时：

- 对于 Exchange，任何拥有邮箱写入权限的用户均可应用这些标签。 
- 对于 SharePoint 和 OneDrive，默认“成员”组（“参与”权限级别）中的任何用户均可应用这些标签。

使用保留标签标记为记录的文档示例：

![标记为记录的文档的详细信息窗格](../media/recordversioning7.png)

## <a name="record-versioning"></a>记录版本控制

将文档标记为记录并限制可对记录执行的操作是任何记录管理解决方案的重要目标。 但是，用户创建后续版本时也可能需要开展协作。

例如，你可以将销售合同标记为记录，但需要使用新条款更新合同，并将最新版本标记为新记录，同时保留先前的记录版本。 对于这些类型的方案，SharePoint 和 OneDrive 现在支持*记录版本控制*。 OneNote 笔记本文件夹不支持记录版本控制。

若要使用记录版本控制，首先标记文档并将其标记为记录。 完成此操作后，名为“*记录状态*”的文档属性将显示在保留标签旁边，初始记录状态为“**已锁定**”。 

现在，可执行下列操作：

  - **通过解锁和锁定记录状态属性，持续编辑文档的各个版本并将其保留为记录。** 只有当“**记录状态**”属性设置为“**已锁定**”时，才会保留新版本的记录。 在已锁定和已解锁之间切换可降低保留不必要的文档版本和副本的风险。

  - **将文档自动保存在位于网站集内的本地记录存储库中。** SharePoint 和 OneDrive 中的每个网站集将内容保存在其保留库中。 记录版本保存在此库中的“记录”文件夹内。

  - **保存包含所有版本的始终更新的文档。** 默认情况下，每个 SharePoint 和 OneDrive 文档的项菜单上都有可用的版本历史记录。 在此版本历史记录中，你可以轻松查看哪些版本是记录并查看这些文档。

对于具有将项标记为记录的保留标签的任何文档，记录版本控制自动可用。 当用户使用详细信息窗格查看文档属性时，可以将“**记录状态**”从“**已锁定**”切换为“**已解锁**”。 执行此操作即可在保留库的“记录”文件夹中创建一个记录，该记录将在其中保存剩余的保留期。 

当文档处于已解锁状态时，拥有标准编辑权限的任何用户均可编辑此文件。 但是，用户无法编辑此文件，因为它仍然是记录。 完成编辑后，用户可再次将“**记录状态**”从“**已解锁**”切换回“**已锁定**”，此状态下可阻止用户进一步编辑该记录。
<br/><br/>

![标记为记录的文档上的记录状态属性](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>锁定和解锁记录

在向文档应用将内容标记为记录的保留标签后，任何拥有参与权限或更窄权限水平的用户可解锁记录或锁定未解锁的记录。
<br/><br/>

![记录状态显示记录文档已解锁](../media/recordversioning9.png)

当用户解锁记录时，将会发生以下操作：

1. 如果当前网站集没有保留库，将会创建一个。

2. 如果保留库没有“记录”文件夹，将会创建一个。

3. “复制到”**** 操作会将文档的最新版本复制到“记录”文件夹。 “复制到”**** 操作仅包含最新版本，不包含先前版本。 此复制的文档现在被视为文档的记录版本，其文件名格式为：\[标题 GUID 版本\#\]

4. 在“记录”文件夹中创建的副本已添加到原始文档的版本历史记录中，此版本将在注释字段中显示“**记录**”一词。

5. 原始文档现已成为可编辑但不可删除的新版本。 文档库列“**项为记录**”仍显示“**是**”值，因为文档仍是记录，即使它现在可以编辑。

当用户锁定记录时，原始文档同样无法编辑。 但是，是解锁记录的操作将版本复制到保留库中的“记录”文件夹。

### <a name="record-versions"></a>记录版本

每次用户解锁记录时，都会将最新版本复制到保留库的“记录”文件夹中，该版本在版本历史记录的“注释”**** 字段中的值为“记录”****。
<br/><br/>

![保留库中显示的记录](../media/recordversioning10.png)

要查看版本历史记录，请在文档库中选择一个文档，然后在项菜单中单击“版本历史记录”****。

### <a name="where-records-are-stored"></a>存储记录的位置。

记录保存在网站集顶层站点的保留库内的“记录”文件夹中。 在顶层站点的左侧导航中，选择“**网站内容**\>**”，“保留库”**。
<br/><br/>

![保留库](../media/recordversioning11.png)

<br/><br/>

![保留库中的“记录”文件夹](../media/recordversioning12.png)

保留库仅对网站集管理员可见。 此外，默认情况下保留库不存在。 仅当受保存标签影响的内容在网站集中第一次删除时才会创建。

### <a name="searching-the-audit-log-for-record-versioning-events"></a>搜索记录版本控制事件的审核日志

锁定和解锁记录的操作会记录在审核日志中。 你可以搜索特定活动“将记录状态更改为已锁定”**** 和“将记录状态更改为已解锁”****，这些活动位于安全与合规性中心“审核日志搜索”**** 页面“活动”**** 下拉列表中的“文件和页面活动”**** 部分。
<br/><br/>

![在审核日志中搜索记录版本控制事件](../media/recordversioning13.png)

有关搜索这些事件的详细信息，请参阅[在安全与合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)的“文件和页面活动”部分。

## <a name="next-steps"></a>后续步骤

如果还没有用于记录管理的保留标签，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。

若要了解有关记录的处置，请参阅[处置内容](disposition.md)。
