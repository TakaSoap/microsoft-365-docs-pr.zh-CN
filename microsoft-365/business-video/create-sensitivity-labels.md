---
title: 创建敏感度标签
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何创建和管理敏感度标签。
ms.openlocfilehash: ff3f7eb5ffddf797e254fac0ed8fc87d96940455
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701899"
---
# <a name="protect-documents-with-sensitivity-labels"></a>使用敏感度标签保护文档

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

敏感度标签允许你对业务敏感的内容进行分类和保护。

## <a name="try-it"></a>试一试！

1. 在 [管理中心，](https://admin.microsoft.com)选择 **合规性** 管理中心。
1. 选择 **"** 分类"，然后选择 **"敏感度"标签**。
1. 选择 **"创建标签**"，当出现警告时，选择 **"是"。**
1. 输入标签 **名称**、**工具提示和****说明**。 选择“**下一步**”。
1. 打开 **加密**。 选择想要分配权限的时间、是否希望用户对内容的访问权限过期以及是否允许脱机访问。
1. **选择"分配权限**"，然后 **添加这些电子邮件地址或域**。
1. 输入电子邮件地址或域名 (例如Contoso.org) 。  选择 **"** 添加"，然后对要添加的每个电子邮件地址或域重复上述步骤。
1. 从 **预设或自定义中选择权限**。
1. 使用下拉列表选择预设权限，如审阅 **者** 或 **查看器**，或选择 **自定义** 权限。 如果选择" **自定义"，** 请从列表中选择权限。 选择 **"保存****"，"保存**"，然后选择"**下一步"。**
1. 打开 **内容标记**，然后选择想要使用的标记。
1. 对于选择的每个标记，选择"**自定义文本"。** 输入要显示在文档中的文本，并设置字体和布局选项。 选择 **"** 保存"，然后对任何其他标记重复。 选择“**下一步**”。
1. （可选）启用 **终结点数据丢失防护**。 选择“**下一步**”。
1. （可选）启用 **自动标记**。 添加条件。 例如，在 **"检测包含的内容"下**，选择 **"添加条件"。** 输入条件;例如，添加一个条件，如果检测到 passport、Social Security 或其他敏感信息，将添加标签。 选择“**下一步**”。
1. 查看你的设置，然后选择"创建 **"。** 已创建标签。 对需要的其他标签重复此过程。
1. 默认情况下，标签按此顺序显示在 Office 应用中 **：机密**、**内部** 和公共 **。** 若要更改顺序，请针对每个标签选择省略号 (更多操作) ，然后将标签上移或下移。 通常，权限从最低级别到最高级别的权限列出。
1. 若要向标签添加子标签，请选择" **更多操作**"，然后 **添加子级别**。
1. 完成后，选择 **"发布标签"，****选择要发布的标签**，然后选择"**添加"。** 选择要发布的标签，然后选择"添加"、"完成"和"下一 **步"。**
1. 默认情况下，新标签策略将应用于每个人。 如果要限制策略应用于的用户，请选择" **选择用户或组**"，然后 **添加**。 选择要应用策略的人，然后选择"添加、完成"和"下一 **步"。**
1. 如果需要文档和电子邮件的默认标签，请从下拉列表中选择想要的标签。 查看其余设置，根据需要调整，然后选择"下一 **步"。**
1. 输入 **策略****的名称** 和说明。 选择“**下一步**”。
1. 查看你的设置，然后选择"发布 **"。**

为了让标签正常工作，每个用户都需要下载 Azure 信息保护统一标签客户端。 在 Web **上** AzinfoProtection_UL.exe，然后从 Microsoft 下载中心下载它，然后在用户计算机上运行它。

下次打开 Office 应用（如 Word）时，你将看到已创建的敏感度标签。 若要更改或应用标签，请选择"敏感度"，然后选择标签。

