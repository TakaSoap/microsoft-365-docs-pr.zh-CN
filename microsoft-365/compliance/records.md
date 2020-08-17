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
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685438"
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
> 为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。 锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](record-versioning.md)功能。 因此，对于标记为记录的所有 Exchange 项目，该行为会映射到**记录 - 已锁定**列，而**记录 - 已解锁列**则不相关。


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

## <a name="next-steps"></a>后续步骤

如果还没有用于记录管理的保留标签，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。

若要将内容标记为记录，请参阅[使用保留标签声明记录](declare-records.md)。
