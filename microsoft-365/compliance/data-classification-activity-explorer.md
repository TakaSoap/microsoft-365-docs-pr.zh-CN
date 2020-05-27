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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器通过查看和筛选用户对你的标记内容执行的操作来完善数据分类功能的功能。
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327838"
---
# <a name="get-started-with-activity-explorer"></a>活动资源管理器入门

数据分类概述和内容浏览器选项卡使你可以查看已发现和已标记的内容以及该内容的位置。 活动资源管理器通过允许你监视对已标记内容所执行的操作来完善此功能套件。 活动资源管理器提供历史视图。

![占位符屏幕截图概述活动资源管理器](../media/data-classification-activity-explorer-1.png)

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

### <a name="permissions"></a>权限

 若要访问“活动资源管理器”选项卡，必须在其中任一角色或角色组中向帐户分配成员身份。

**Microsoft 365 角色组**

- 全局管理员
- 合规性管理员
- 安全管理员
- 合规性数据管理员

## <a name="activity-type"></a>活动类型

Microsoft 365 监视和报告跨 SharePoint Online 和 OneDrive 和的活动类型，例如：

- 已应用的标签
- 已更改（已升级、已降级或已删除）的标签
- 自动标记模拟

了解对敏感的已标记内容采取何种措施的价值在于，你可以查看已经实施的控件（例如[数据丢失防护策略](data-loss-prevention-policies.md)）是否有效。 如果无效，或者发现某项意外内容（如大量项目被标记为`highly confidential`并降级为`general`），则可管理各种策略并采取新操作来限制意外行为。

> [!NOTE]
> 活动资源管理器当前不监视 Exchange Online 的保留活动。

## <a name="see-also"></a>另请参阅
- [敏感度标签](sensitivity-labels.md)
- [保留标签](labels.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [保留策略概述](retention-policies.md)
