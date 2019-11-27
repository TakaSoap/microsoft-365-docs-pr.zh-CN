---
title: 使用数据分类内容资源管理器（预览版）
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
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268442"
---
# <a name="using-data-classification-content-explorer-preview"></a>使用数据分类内容资源管理器（预览版）

数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。

## <a name="content-explorer"></a>内容资源管理器

内容资源管理器是具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。

![内容资源管理器折叠的屏幕截图](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>权限

有两个角色可授予对内容资源管理器的访问权限：

- **内容资源管理器列表查看器**：此角色的成员资格允许你查看每个项目及其位置。

- **内容资源管理器内容查看器**：此角色的成员资格允许你查看列表中每个项目的内容。

用于访问内容资源管理器的帐户必须具有其中一个或两个角色。 这些角色是独立角色，不具有累积性。 例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。 如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。

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
