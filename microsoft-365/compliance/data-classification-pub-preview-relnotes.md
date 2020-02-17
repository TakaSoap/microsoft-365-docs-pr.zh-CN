---
title: 数据分类预览版的发行说明（预览版）
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
description: 数据分类公共预览版的发行说明。
ms.openlocfilehash: 1beae92089833327cedf6090690530d9e5457a37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076359"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>数据分类公共预览版的发行说明（预览版）

此公共预览版引入了新功能：在你创建任何策略*前*，开始扫描你的敏感内容和标记的内容。 这称为 ** 零变更管理 **。 这样，你就可以看到你环境中所有保留和灵敏度标签的影响，并使你能够开始评估你的保护和治理策略需求。

请查看这些发行说明，以便在此公共预览版中获得最佳体验。 从现在到正式发布 (GA) 期间，我们将致力于解决这些问题。

## <a name="permissions-for-accessing-content-explorer"></a>访问内容资源管理器的权限

对内容资源管理器的访问权限受到高度限制，因为它允许你读取已扫描文件的内容。 对内容资源管理器的访问需要 **内容资源管理器列表查看器**以及**内容资源管理器内容查看器**角色组中的成员身份。 默认情况下，没有帐户可访问内容资源管理器。 请参阅[使用数据分类内容资源管理器（预览版）](data-classification-content-explorer.md#permissions)。 全局管理员、合规性管理员或数据管理员可以分配必要的 ** 内容资源管理器列表查看器 ** 和 ** 内容资源管理器内容查看器 ** 角色组成员身份。

> [!TIP]
> 在全球范围内部署基于角色的访问控制 (RBAC) 时，** 内容资源管理器列表查看器 ** 和 ** 内容资源管理器内容查看器 ** 角色组可能不会显示在 "权限" 页面上。 如果它们未出现在 "权限" 页面上，则必须创建一个自定义角色组，并将 `data classification list viewer` 角色和或 `data classification content viewer` 角色（复数）分配到你的自定义角色组。

## <a name="exchange-mailbox-count"></a>Exchange 邮箱计数

当你深入了解 Exchange 邮箱时，你会注意到出现一个小的工具提示。 这是为了表明以下事实：敏感信息类型，敏感度标签和保留标签显示的合计计数可能与邮箱中找到的项目数不完全匹配。 这是因为深入了解文件夹时，将提取内容的实时视图（已分类），同时会计算总计数。

## <a name="seeing-guids-instead-of-label-names"></a>查看 GUID 而不是标签名称

私人预览版客户遇到过的一些情况是，已迁移的标签或者在删除内容中带有内容标记的标签时，会导致标签名称在内容资源管理器和活动资源管理器中解析为 32 位 GUID，而不是标签名称。 

## <a name="rendering-of-encrypted-documents"></a>加密文档的呈现

已加密的 SharePoint、Exchange 和 OneDrive 文件将不会在内容资源管理器中呈现。 这是一项敏感问题，需要在内容资源管理器中查看文件内容和将内容保持加密的需求之间取得平衡。 通过 ** 内容资源管理器列表查看器 ** 和 ** 内容资源管理器内容查看器 ** 角色组授予的权限，你将看到文件的列表视图、文件元数据和可用于通过 web 客户端访问内容的链接。

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 搜索中保留标签名称的支持字符

SharePoint 搜索不支持包含 `-` 或者 `_` 的保留标签名称。 例如 `Label-MIP` 和 `Label_MIP` 不受支持。 SharePoint 搜索支持敏感性标签名称和敏感信息类型名称中的这些字符。

## <a name="see-also"></a>另请参阅

- [数据分类入门（预览）](data-classification-overview.md)
- [查看标签活动（预览）](data-classification-activity-explorer.md)
- [查看已应用标签的内容（预览）](data-classification-content-explorer.md)
- [敏感度标签](sensitivity-labels.md)
- [保留标签](labels.md)
- [敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)

