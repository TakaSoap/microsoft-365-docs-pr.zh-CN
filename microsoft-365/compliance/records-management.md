---
title: Microsoft 365 中的记录管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 通过 Microsoft 365 中的记录管理，你可以将保留计划应用到文件计划中，以管理保留、记录声明和处置。
ms.openlocfilehash: 410fa890e159d18e3aacedbf08be44ee047ee189
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158162"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>了解 Microsoft 365 中的记录管理

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

所有类型的组织都需要记录管理解决方案跨公司数据管理法规、法律和业务关键记录。Microsoft 365 中的记录管理有助于组织管理其法律义务，提供证明遵守法规的能力，并通过定期处置不再需要保留、不再具有价值或不再需要用于业务目的的项目来提高效率。

请使用以下功能支持 Microsoft 365 中的记录管理解决方案：

- **将内容标记为记录**。创建并配置将内容标记为[记录](#records)的保留标签，该类标签随后可由用户应用，或通过标识敏感信息、关键字或内容类型自动应用。

- **使用文件计划迁移和管理保留要求**。通过使用[文件计划](file-plan-manager.md)，可将现有保留计划引入 Microsoft 365，或者构建一个新的保留计划来增强管理功能。

- **使用保留标签配置保留和删除设置**。根据各种因素（包括上次修改日期或上次创建日期）配置有关保留期和操作的 [保留标签](retention.md#retention-labels)。

- 使用 [基于事件的保留](event-driven-retention.md)，**在事件发生时启动不同的保留期**。

- 使用 [处置评审](disposition.md#disposition-reviews)和 [记录删除](disposition.md#disposition-of-records)证明 **审核并验证处置**。

- 使用 [导出选项](disposition.md#filter-and-export-the-views)**导出有关所有已处置项的信息**。

- 为组织中的记录管理器功能 **设置特定权限**，以便 [具有正确的访问权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

借助这些功能，你可以将组织的保留计划和要求合并到用以管理保留、记录声明和处置的记录管理解决方案中，从而支持完整的内容生命周期。

除了阅读联机文档，你还可以收听有关记录管理的[网络研讨会录制内容](https://aka.ms/MIPC/Video-RecordsManagementWebinar)并下载随附的[常见问题幻灯片组](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)，这种方法可能也会非常有用。

## <a name="records"></a>记录

将内容声明为记录时：

- 会针对[允许或阻止对记录项进行的操作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)施加限制。

- 记录了有关该项的其他活动。

- 保留期结束时将其删除时，拥有处置证明。

使用 [保留标签](retention.md#retention-labels)将内容标记为 **记录** 或 **管理记录**。 这两者之间的差异将在下一节中介绍。 你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录或合规性记录的内容。

通过使用保留标签来声明记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>比较对允许或阻止的操作的限制

使用以下表格识别应用标准保留标签和将内容标记为记录或合规性记录的保留标签后，对内容施加的限制。

标准保留标签具有保留设置和操作，但不会将内容标记为记录或合规性记录。

> [!NOTE]
> 为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。 锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](record-versioning.md)功能。 因此，对于标记为记录的所有 Exchange 项目，该行为会映射到 **记录 - 已锁定** 列，而 **记录 - 已解锁列** 则不相关。


|操作| 保留标签 |记录 - 已锁定| 记录 - 已解锁| 合规性记录 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|编辑内容|允许 | **阻止** | Allowed | **阻止**|
|编辑属性（包括重命名）|Allowed |Allowed | Allowed| **阻止**|
|删除|允许 <sup>1</sup> |**阻止** |**阻止**| **阻止**|
|复制|允许 |Allowed | Allowed| 允许|
|在容器 <sup>2</sup> 中移动|允许 |Allowed | Allowed| 允许|
|围绕容器 <sup>2</sup> 移动|允许 |如果从未解锁，则允许 | **阻止** | **阻止**|
|打开/读取|允许 |Allowed | Allowed| Allowed|
|更改标签|允许 |允许 - 仅容器管理员 | 允许 - 仅容器管理员| **已阻止**
|删除标签|允许 |允许 - 仅容器管理员 | 允许 - 仅容器管理员| **已阻止**

页脚：

<sup>1</sup>OneDrive 和 Exchange 支持此功能，方法是在安全位置保留一份副本，但 SharePoint 阻止此功能。

当你将保留标签应用于具有文档附件的列表项时，该文档不会继承保留设置，因此可以从列表项中删除。 相比之下，如果该列表项被声明为带有保留标签的记录，则文档附件将继承保留设置，并且无法删除。

<sup>2</sup> 个容器包括 SharePoint 文档库、OneDrive 帐户和 Exchange 邮箱。

> [!IMPORTANT]
> 合规性记录的最重要的差别是，在应用到内容后，任何人（哪怕是是全局管理员）都无法删除标签。
>
> 为合规性记录配置的保留标签还具有以下管理员限制：
>
> - 保存标签后，不能缩短保留期，只能对其进行扩展。
> - 自动标记策略不支持这些标签，必须使用[保留标签策略](create-apply-retention-labels.md)应用这些标签。
>
> 此外，合规性标签无法应用于在 SharePoint 中签出的文档。
>
> 由于存在这些限制和不可逆操作，在针对保留标签选择此选项之前，请确保自己确实需要使用合规性记录。 为帮助防止意外配置，默认情况下该选项不可用，但必须先使用 PowerShell 启用。 有关说明，请参阅[使用保留标签 声明记录](declare-records.md)。

## <a name="configuration-guidance"></a>配置指南

请参阅[记录管理入门](get-started-with-records-management.md)。本文提供了有关订阅、权限的信息，以及记录管理方案的端到端配置指南链接。