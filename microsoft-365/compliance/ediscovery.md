---
title: 电子数据展示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 143b3ab8-8cb0-4036-a5fc-6536d837bfce
description: Microsoft 365 提供了许多不同的电子数据展示工具，可用于搜索和保存在不同位置（如 Exchange 邮箱、SharePoint 和 OneDrive for Business 网站、Microsoft 365 组和 Skype for business 会话）中找到的内容。
ms.openlocfilehash: 6735ce5df0978c75117324f702d1c2f758208bd1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631757"
---
# <a name="ediscovery-in-microsoft-365"></a>Microsoft 365 中的电子数据展示

电子发现（亦称为"电子数据展示"）是用于识别和传递可用作法律案件证据的电子信息的过程。 您可以使用 Microsoft 365 中的电子数据展示工具搜索 Exchange Online 邮箱、Microsoft 365 组、Microsoft 团队、SharePoint Online 和 OneDrive for business 网站以及 Skype for business 会话和 Yammer 团队中的内容。 您可以使用内容搜索工具在相同的电子数据展示搜索中搜索邮箱和网站。 此外，您还可以使用核心电子数据展示事例来标识、保留和导出邮箱和网站中的内容。 如果您的组织具有 Office 365 E5 或 Microsoft 365 E5 订阅（或相关的 E5 附加订阅），您可以使用 Microsoft 365 中的高级电子数据展示解决方案进一步管理保管人和分析内容。
  
Microsoft 365 提供以下电子数据展示工具：
  
- [内容搜索](#content-search)

- [核心电子数据展示](#core-ediscovery)

- [高级电子数据展示](#advanced-ediscovery)

> [!NOTE]
> 高级电子数据展示（经典）（也称为*高级电子数据展示*v1.0）（通过单击 "**切换到高级电子数据展示**"，可在核心电子数据展示案例中使用的高级电子数据展示版本将被停用。 其功能已由 Microsoft 365 中的高级电子数据展示解决方案替换。 有关停用高级电子数据展示 v1.0 的详细信息，请参阅[旧电子数据展示工具的退休](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。

## <a name="content-search"></a>内容搜索

下表包含一些主题的链接，这些主题将帮助您使用内容搜索工具。
  
|**主题**|**说明**|
|:-----|:-----|
|[运行内容搜索](content-search.md) <br/> |了解如何使用内容搜索工具在单个搜索的组织中搜索邮箱、公用文件夹、Microsoft 365 组、Microsoft 团队、SharePoint Online 网站、一个驱动器的商业位置和 Skype for Business 对话。  <br/> |
|[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md) <br/> |了解可用于搜索组织中的邮箱和网站中的内容的电子邮件和文件属性和搜索条件。  <br/> |
|[查看内容搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md) <br/> |了解如何使用搜索统计信息显示和比较一个或多个内容搜索的统计信息，以及如何配置新的和现有的搜索以在搜索查询中返回每个关键字的统计信息。  <br/> |
|[导出搜索结果](export-search-results.md) <br/> |了解如何导出内容搜索的结果。  <br/> |
|[配置内容搜索的权限筛选](permissions-filtering-for-content-search.md) <br/> |了解如何使用权限筛选使电子数据展示管理器仅搜索组织中的邮箱和网站的子集。  <br/> |
|[导出内容搜索报告](export-a-content-search-report.md) <br/> |了解如何下载导出报告，而无需导出实际搜索结果。  <br/> |
|[内容搜索限制](limits-for-content-search.md) <br/> |了解内容搜索工具的限制，例如一次可以运行的最大搜索数。  <br/> |
|[内容搜索中未编制索引的项目](partially-indexed-items-in-content-search.md) <br/> |了解 Exchange 和 SharePoint 中的未编制索引的项目，您可以在运行搜索时在估计的搜索结果统计信息中包含这些项目。 您还可以在导出搜索结果时包含未编制索引的项目。  <br/> |
|[搜索和删除电子邮件](search-for-and-delete-messages-in-your-organization.md) <br/> |了解如何使用内容搜索来搜索和删除组织中*所有*邮箱的电子邮件。 这可帮助你查找和删除可能有害或高风险的电子邮件。  <br/> |
|[使用内容搜索在邮箱和 OneDrive 帐户中搜索用户列表](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) <br/> |了解如何使用脚本在邮箱和一个驱动器的业务网站中搜索一组用户。 有关如何在创建和运行内容搜索时快速生成可用于源内容位置的电子邮件地址列表的步骤，请参阅[创建所有 OneDrive 位置的列表](https://docs.microsoft.com/onedrive/list-onedrive-urls)。  <br/> |
|[使用内容搜索进行目标收集](use-content-search-for-targeted-collections.md) <br/> |了解如何使用本文中的 Windows PowerShell 脚本，以使用内容搜索来执行目标集合。 目标集合表示要搜索特定的文件夹，因为您确信项目的响应方式（或特权项目）位于该文件夹中。 使用本文中的脚本获取要搜索的特定邮箱或网站文件夹的文件夹 ID 或路径。  <br/> |
|||
  
## <a name="core-ediscovery"></a>核心电子数据展示

下表包含一些主题的链接，这些主题将帮助您使用核心电子数据展示事例。 您可以使用核心电子数据展示事例添加可访问案例的电子数据展示管理器，在与案例相关的内容位置上放置电子数据展示保留，搜索内容，并从该案例导出搜索结果。
  
|**主题**|**说明**|
|:-----|:-----|
|[核心电子数据展示入门](get-started-core-ediscovery.md) |了解如何分配电子数据展示权限并创建核心电子数据展示事例。 本主题还概述了核心电子数据展示工作流。<br/> |
|[创建电子数据展示保留](create-ediscovery-holds.md)|了解如何创建与核心电子数据展示事例相关联的电子数据展示保留，以保留与正在调查的事例相关的内容。|
|[在核心电子数据展示事例中搜索内容](search-for-content-in-core-ediscovery.md)|了解如何搜索与事例相关的内容。 您可以快速创建在保留时搜索内容位置的搜索。|
|[从核心电子数据展示事例导出内容](export-content-in-core-ediscovery.md)|了解如何从核心电子数据展示事例导出和下载内容。|
|[关闭、重新打开和删除核心电子数据展示事例](close-reopen-delete-core-ediscovery-cases.md)|了解如何管理核心电子数据展示事例的生命周期。|
|[分配电子数据展示权限](assign-ediscovery-permissions.md)|了解如何将权限分配给用户，以便他们可以搜索内容、保留保留的内容位置以及执行其他与电子数据展示相关的任务。|
|[为核心电子数据展示设置合规性边界](set-up-compliance-boundaries.md)|了解如何使用合规性边界在组织内创建逻辑边界，以控制电子数据展示管理器可以搜索的内容位置。|
|||
  
## <a name="advanced-ediscovery"></a>高级电子数据展示

Microsoft 365 中的高级电子数据展示解决方案（也称为*高级电子数据展示*v2.0）构建在 Office 365 中现有的电子数据展示和分析功能之上。 此电子数据展示解决方案提供了一个端到端工作流，用于保留、收集、查看、分析和导出对组织的内部和外部调查做出响应的内容。 它还允许法律团队管理保管人和整个法律封存通知工作流，以便与案例中所涉及的保管人进行通信。

|**主题**|**说明**|
|:-----|:-----|
|[高级电子数据展示概述](overview-ediscovery-20.md)|本文介绍了高级电子数据展示2.0，并提供了高级电子数据展示的内置工作流以及如何与电子发现参考模型概述的电子数据展示过程的层次概述|.
|[高级电子数据展示入门](get-started-with-advanced-ediscovery.md)|了解如何开始使用高级电子数据展示，包括所需的许可和必要的电子数据展示权限。 本文介绍如何创建高级电子数据展示事例并提供高级电子数据展示工作流的指导。|
|[使用保管人](managing-custodians.md)|了解如何在高级电子数据展示中使用保管人。 本主题链接到分步说明，以将保管人添加到一个案例中，在一个事例中管理保管人，以及通过搜索审核日志在 Microsoft 365 中查看保管人活动。|
|[处理通信](managing-custodian-communications.md)|了解如何在高级电子数据展示中管理合法保留通知过程。 这包括创建和自动化通知工作流以及用户如何确认保留通知。
|[解决处理错误](processing-data-for-case.md)|了解有关高级索引以及如何修正来自 custodial 和非 custodial 内容位置（如 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户）的内容中的索引错误的信息。 您可以批量修正错误，然后将修正的文件上传到审阅集或修正评审集内的各个处理错误。|
|[收集事例数据](collecting-data-for-ediscovery.md)|了解如何搜索 custodial 内容位置中的内容，然后将相关事例数据添加到评审集。 将内容复制到审阅集时，数据将从原始内容位置复制到 Microsoft 提供的 Azure 存储位置。 这为审阅过程提供了一组静态文档。|
|[管理审阅集](managing-review-sets.md)|了解如何在审阅集中审阅事例数据。 这包括查看、查询、筛选和标记审阅集中的文档。
|[分析评审集中的数据](analyzing-data-in-review-set.md)|了解如何对审阅集中的文档运行分析。 运行分析的结果包括邻近重复检测、电子邮件线程和主题标识。|
|[导出事例数据](exporting-data-ediscover20.md)|了解如何从外部审阅的案例中导出数据。|
|||
