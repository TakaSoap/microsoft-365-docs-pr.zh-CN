---
title: 使用数据分类内容资源管理器（预览版）
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
description: 内容资源管理器可用于在本机查看标记的项目。
ms.openlocfilehash: 205ec6b4f2049e18ee95f25505d8a58d7eb7ac77
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409687"
---
# <a name="using-data-classification-content-explorer-preview"></a>使用数据分类内容资源管理器（预览版）

数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。

## <a name="prerequisites"></a>先决条件

访问和使用活动资源管理器的每个帐户，都必须拥有从以下之一订阅向其分配的许可证：

- Microsoft 365 (E5)
- Office 365 (E5)
- 高级合规性（E5）加载项
- 高级威胁智能（E5）加载项

## <a name="content-explorer"></a>内容资源管理器

内容资源管理器可显示具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。

### <a name="sensitive-information-types"></a>敏感信息类型

[DLP 策略](data-loss-prevention-policies.md)可帮助保护定义为**敏感信息类型**的敏感信息。 Microsoft 365 在多个不同区域包含[适用于众多常用敏感信息类型的定义](what-the-sensitive-information-types-look-for.md)它们已准备就绪可供使用。 例如，信用卡号、银行帐号、国民身份证号码和 Windows Live ID 服务编号。

### <a name="sensitivity-labels"></a>敏感度标签

[灵敏度标签](sensitivity-labels.md)只是一个标记，指出项目对你的组织的价值。 该标签可手动应用，也可自动应用。 应用后，它将嵌入到文档中并始终保留在文档上。 可通过敏感度标签实现各种保护行为，例如强制水印或加密。 如果启用了终结点保护，你甚至还可阻止项目脱离组织控制。

必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。 有关详细信息，请参阅[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签（公共预览版）](sensitivity-labels-sharepoint-onedrive-files.md)。

### <a name="retention-labels"></a>保留标签

[保留标签](labels.md)可用于定义带标记的项目将保留多长时间以及删除项目前要采取哪些操作。 这些标签可手动应用，也可通过策略自动应用。 它们在帮助组织持续遵守法律法规要求方面发挥着作用。

![内容资源管理器折叠的屏幕截图](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>权限

有两个角色可授予对内容资源管理器的访问权限：

- **内容资源管理器列表查看器**：此角色组的成员资格允许你查看每个项目及其位置。 已为此角色组预分配 `data classification list viewer` 角色。

- **内容资源管理器内容查看器**：此角色组的成员资格允许你查看列表中每个项目的内容。 已为此角色组预分配 `data classification content viewer` 角色。

用于访问内容资源管理器的帐户必须具有其中一个或两个角色组。 这些角色组是独立角色组，不具有累积性。 例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。 如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。

你还可以将任一个角色或全部两个角色都分配到自定义角色组，以便对内容资源管理器的访问权限进行量身定制。

全局管理员、合规性管理员或数据管理员可以分配必要的  内容资源管理器列表查看器  和  内容资源管理器内容查看器  角色组成员身份。

### <a name="how-to-use-content-explorer"></a>如何使用内容资源管理器

1. 打开“**Microsoft 365 合规中心**”  > “**数据分类**” > “**内容资源管理器**”。
2. 如果知道标签的名称或敏感信息类型，可将其键入“搜索” 框。
3. 或者，你可以通过展开标签类型并从列表中选择标签来浏览该项目，下面显示了列表的保留标签部分中的项目。
4. 选择“**所有**”位置下的某个位置，然后向下钻取文件夹结构到该项目。
5. 双击以在本机上打开内容资源管理器中的项目。

## <a name="see-also"></a>另请参阅

- [敏感度标签](sensitivity-labels.md)
- [保留标签](labels.md)
- [敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)
- [保留策略概述](retention-policies.md)
- [数据丢失防护概述](data-loss-prevention-policies.md)
