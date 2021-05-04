---
title: 数据分类发行说明
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 数据分类发行说明。
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086703"
---
# <a name="data-classification-release-notes"></a>数据分类发行说明


## <a name="exchange-mailbox-count"></a>Exchange 邮箱计数

当你深入了解 Exchange 邮箱时，你会注意到出现一个小的工具提示。 这是为了表明以下事实：敏感信息类型，敏感度标签和保留标签显示的合计计数可能与邮箱中找到的项目数不完全匹配。 这是因为深入了解文件夹时，将提取内容的实时视图（已分类），同时会计算总计数。


## <a name="rendering-of-encrypted-documents"></a>加密文档的呈现

已加密的 SharePoint、Exchange 和 OneDrive 文件不会在内容资源管理器中呈现。 这是一项敏感问题，需要在内容资源管理器中查看文件内容和将内容保持加密的需求之间取得平衡。 通过 **内容资源管理器列表查看器** 和 **内容资源管理器内容查看器** 角色组授予的权限，你将看到文件的列表视图、文件元数据和可用于通过 web 客户端访问内容的链接。

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 搜索中保留标签名称的支持字符

SharePoint 搜索不支持包含 `-` 或者 `_` 的保留标签名称。 例如，`Label-MIP` 和 `Label_MIP` 不受支持。 SharePoint 搜索支持敏感性标签名称和敏感信息类型名称中的这些字符。

## <a name="onedrive-remains-in-preview"></a>OneDrive 仍处于预览状态

感谢你在我们的预览计划期间提供有关 OneDrive 集成的宝贵反馈。 随着我们处理具体的细节，你可能会遇到不一致的数据/流。 我们将继续展示 OneDrive 预览版，直到所有修补程序均准备就绪。 非常感谢你的持续支持。


## <a name="see-also"></a>另请参阅

- [数据分类入门（预览）](data-classification-overview.md)
- [查看标签活动（预览）](data-classification-activity-explorer.md)
- [查看已应用标签的内容（预览）](data-classification-content-explorer.md)
- [了解敏感度标签](sensitivity-labels.md)
- [了解保留策略和保留标签](retention.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)