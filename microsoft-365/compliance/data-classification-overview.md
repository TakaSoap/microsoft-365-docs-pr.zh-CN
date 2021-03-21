---
title: 数据分类入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 借助数据分类仪表板，你可以了解组织中已发现和分类了多少敏感数据。
ms.openlocfilehash: 8f3bb2da1e7011fef334ec345a02d7facedc25fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922676"
---
# <a name="know-your-data---data-classification-overview"></a>了解你的数据 - 数据分类概述

作为 Microsoft 365 管理员或合规性管理员，你可以评估并标记组织中的内容，以便控制其去向，随时随地提供保护，并确保根据组织的需要保留和删除该内容。 你可以通过应用[敏感度标签](sensitivity-labels.md)、[保留标签](retention.md#retention-labels)和敏感信息类型分类来实现这一目标。 可通过多种方法进行发现、评估和标记，但最终的结果是，你可能拥有大量的文档和电子邮件，它们使用其中一个或两个标签进行了标记和分类。 应用保留标签和敏感度标签后，你希望了解如何在租户中使用这些标签以及对这些项目所执行的操作。 数据分类页面提供了对内容主体的可见性，具体如下：

- 已分类为敏感信息类型的项目数量以及这些分类是什么
- Microsoft 365 和 Azure 信息保护中应用最多的敏感度标签
- 应用最多的保留标签
- 用户对敏感内容所执行的操作的摘要
- 敏感数据和已保留数据的位置

此外，还可在数据分类页面上管理以下功能：
- [可训练的分类器](classifier-learn-about.md)
- [敏感信息类型](./sensitive-information-type-entity-definitions.md)

可以在“**Microsoft 365 合规中心**”或“**Microsoft 365 安全中心**” > “**分类**” > “**数据分类**”中找到数据分类。

获取介绍我们的数据分类功能的视频教程。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

创建任何策略前，数据分类将先扫描敏感内容和标记内容。 这称为 **零变更管理**。 这样，你就可以看到你环境中所有保留和灵敏度标签的影响，并使你能够开始评估你的保护和治理策略需求。

## <a name="prerequisites"></a>先决条件

许多不同的订阅都支持终结点 DLP。 若要查看终结点 DLP 的许可选项，请参阅[信息保护许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。 

### <a name="permissions"></a>权限

 为了访问数据分类页面，必须在以下任一角色或角色组中向帐户分配成员身份。

**Microsoft 365 角色组**

- 全局管理员
- 合规性管理员
- 安全管理员
- 合规性数据管理员

## <a name="sensitive-information-types-used-most-in-your-content"></a>内容中的最常用敏感信息类型

Microsoft 365 附带了许多敏感信息类型的定义，例如包含社会安全号码或信用卡号的项目。 有关敏感信息类型的详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。

敏感信息类型卡片显示了在整个组织中找到并标记的最常用敏感信息类型。

![最常用敏感信息类型](../media/data-classification-sens-info-types-card.png)

若要了解任何给定分类类别中的项目数量，请将鼠标悬停在该类别的栏上。

![最常用敏感信息类型悬停详细信息](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> 如果卡片上显示消息“找不到包含敏感信息的数据”。 这表示你的组织中没有任何项目归类为敏感信息类型，也没有对任何项目进行爬网。 要开始使用标签，请参阅：
>- [开始使用敏感度标签](get-started-with-sensitivity-labels.md)
>- [开始使用保留策略和保留标签](get-started-with-retention.md)
>- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a>应用于内容的最常用敏感度标签

通过 Microsoft 365 或 Azure 信息保护 (AIP) 将敏感度标签应用于项目时，会出现两种情况：

- 指示项目对组织的价值的标记已嵌入到文档中，可随时随地进行跟踪
- 标记的存在将实现各种保护行为，例如强制性水印或加密。 如果启用了终结点保护，你甚至还可阻止项目脱离组织控制。

有关敏感度标签的详细信息，请参阅[了解敏感度标签](sensitivity-labels.md)。

必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。 有关详细信息，请参阅[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。

敏感度标签卡片按敏感度级别显示项目（电子邮件或文档）的数量。

![按敏感度标签分类占位符屏幕快照对内容进行细分](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> 如果尚未创建或发布任何敏感度标签，或者任何内容均未应用敏感度标签，则此卡片将显示消息“未检测到任何敏感度标签”。 若要开始使用敏感度标签，请参阅：
>- [开始使用敏感度标签](get-started-with-sensitivity-labels.md)或[配置 Azure 信息保护策略](/azure/information-protection/configure-policy)（对于 AIP）

## <a name="top-retention-labels-applied-to-content"></a>应用于内容的最常用保留标签

保留标签用于管理组织中的内容的保留和处置方式。 应用后，它们可用于控制项目在删除之前的保留方式，是否应在删除之前对其进行评审，保留期何时到期以及是否应将其标记为记录。 有关详细信息，请参阅[了解保留策略和保留标签](retention.md)。

“应用最多的保留标签”卡片显示具有给定保留标签的项目数量。

![应用最多的保留标签占位符屏幕快照](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> 如果此卡片显示消息“未检测到任何保留标签”，则表示尚未创建或发布任何保留标签，或者任何内容均未应用保留标签。 要开始使用保留标签，请参阅：
>- [开始使用保留策略和保留标签](get-started-with-retention.md)

## <a name="top-activities-detected"></a>检测到的热门活动

此卡片提供用户对具有敏感度标签的项目执行的最常见操作的快速摘要。 可使用[活动资源管理器](data-classification-activity-explorer.md)深入了解 Microsoft 365 对位于 Windows 10 终结点上的已标记内容进行跟踪的八种不同活动。

> [!NOTE]
> 如果此卡片显示消息“未检测到任何活动”，则表示未对文件执行任何操作，或者未启用用户和管理员审核功能。 若要打开审核日志，请参阅：
>- [在安全与合规中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a>按位置列出的敏感度和保留标签数据

数据分类报告的重点是让用户了解具有标签的项目数量及其位置。 通过这些卡片，你可以了解在 Exchange、SharePoint 和 OneDrive 等应用中具有标签的项目数量。

> [!NOTE]
> 如果此卡片显示消息“未检测到任何位置”，则表示尚未创建或发布任何敏感度标签，或者任何内容均未应用保留标签。 若要开始使用敏感度标签，请参阅：
>- [敏感度标签](sensitivity-labels.md)

## <a name="see-also"></a>另请参阅

- [查看标签活动](data-classification-activity-explorer.md)
- [查看带标签的内容](data-classification-content-explorer.md)
- [了解敏感度标签](sensitivity-labels.md)
- [了解保留策略和保留标签](retention.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [了解可训练的分类器（预览版）](classifier-learn-about.md)