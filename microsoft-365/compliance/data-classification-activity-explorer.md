---
title: 活动资源管理器入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器通过查看和筛选用户对你的标记内容执行的操作来完善数据分类功能的功能。
ms.openlocfilehash: d44d285959e0529a694b2022d35f2b7e7a575fdc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192255"
---
# <a name="get-started-with-activity-explorer"></a>活动资源管理器入门

通过[数据分类概述](data-classification-overview.md)[和内容](data-classification-content-explorer.md)资源管理器选项卡，您可以了解已发现和标记的内容以及该内容位于何处。 活动资源管理器通过允许你监视对已标记内容所执行的操作来完善此功能套件。 活动资源管理器提供已标记内容上活动的历史视图。 活动信息收集自活动Microsoft 365统一审核日志，在活动资源管理器 UI 中转换和提供。 

![占位符屏幕截图概述活动资源管理器。](../media/data-classification-activity-explorer-1.png)

有 30 多种不同筛选器可供使用，其中有：

- 日期范围
- 活动类型
- 位置
- 用户
- 敏感度标签
- 保留标签
- 文件路径
- DLP 策略



## <a name="prerequisites"></a>必备条件

访问和使用数据分类的每个帐户，都必须拥有从以下其中一个订阅向其分配的许可证：

- Microsoft 365 (E5)
- Office 365 (E5)
- 高级合规性（E5）加载项
- 高级威胁智能（E5）加载项
- Microsoft 365 E5/A5 信息保护和管控
- Microsoft 365 E5/A5 合规

### <a name="permissions"></a>权限

 若要获取对活动资源管理器选项卡的访问权限，必须为帐户显式分配这些角色组中任何一个的成员身份或明确授予该角色。

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Microsoft 365 角色组**

- 全局管理员
- 合规性管理员
- 安全管理员
- 合规性数据管理员

**Microsoft 365角色**

- 合规性管理员
- 安全管理员

## <a name="activity-types"></a>活动类型

活动资源管理器从多个活动源的审核日志中收集活动信息。 有关哪些标签活动可用于活动资源管理器的更多详细信息，请参阅活动资源管理器中可用的标签 [事件](data-classification-activity-explorer-available-events.md)。

 Office 本机应用程序、Azure 信息保护加载项、SharePoint Online、Exchange Online (标签的敏感度标签活动和保留标签活动) OneDrive。  示例如下：

- 已应用的标签
- 已更改（已升级、已降级或已删除）的标签
- 自动标记模拟
- 文件读取 

**Azure 信息保护 (AIP) 扫描程序和 AIP 客户端**

- 已应用保护
- 保护已更改
- 已删除保护
- 发现的文件 

活动资源管理器还通过收集来自 Exchange Online、SharePoint Online、OneDrive、Teams 聊天和频道 (预览) 、本地 SharePoint 文件夹和库、本地文件共享和 Windows 10 设备的 **DLP** 策略匹配事件 **DLP (终结点数据丢失) 。** 来自设备中的Windows 10事件包括文件：

- deletions
- creations
- 复制到剪贴板
- 修改内容
- 阅读
- 已打印
- 已重命名
- 复制到网络共享
- 由不允许的应用访问 

了解对敏感标记内容采取的操作的价值是，你可以看到已放置的控件（如数据丢失防护）是否有效。 [](dlp-learn-about-dlp.md) 如果无效，或者发现某项意外内容（如大量项目被标记为`highly confidential`并降级为`general`），则可管理各种策略并采取新操作来限制意外行为。

> [!NOTE]
> 活动资源管理器当前不监视 Exchange Online 的保留活动。

## <a name="see-also"></a>另请参阅

- [了解敏感度标签](sensitivity-labels.md)
- [了解保留策略和保留标签](retention.md)
- [了解敏感信息类型](sensitive-information-type-learn-about.md)
- [了解数据分类](data-classification-overview.md)
