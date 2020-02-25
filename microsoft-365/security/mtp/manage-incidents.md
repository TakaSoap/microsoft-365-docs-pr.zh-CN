---
title: 管理 Microsoft 威胁防护中的事件
description: 了解如何分配、更新状态
keywords: 事件, 事件, 警报, 相关警报, 分配, 更新, 状态, 管理, 分类, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b8f7e3bbb6d2348c3f19e8df251d700d8adf8e33
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235081"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>管理 Microsoft 威胁防护中的事件

**适用于：**
- Microsoft 威胁防护



管理事件对于确保控制和解决威胁至关重要。 在 Microsoft 威胁防护中，你有权管理设备、用户和邮箱相关事件。 


从“事件队列”**** 中选择事件后，就可以管理事件了。 

可以编辑事件的名称、解决事件、设置其分类和确定。 还可以将事件分配给自己，添加事件标记和备注。

如果在调查时希望将警报从一个事件转移到另一个事件，还可以从“警报”选项卡执行相关操作，从而创建一个包含所有相关警报的较大或较小的事件。

## <a name="edit-incident-name"></a>编辑事件名称
默认情况下，将为事件分配一个编号。 可以修改事件名称，以便更好地与首选命名约定保持一致。
 
## <a name="assign-incidents"></a>分配事件
如果尚未分配事件，可以选择“分配给我”**** 将事件分配给自己。 执行此操作时，假定所有权不仅限于事件，而且还针对与之关联的所有警报。

## <a name="set-status-and-classification"></a>设置状态和分类
### <a name="incident-status"></a>事件状态
可通过在调查期间更改事件的状态来为事件分类（例如“活动”**** 或“已解决”****）。 这可帮助你整理和管理团队对事件的响应方式。

例如，SOC 分析人员可以查看当天的紧急“活动”**** 事件，并决定将其分配给自己进行调查。

或者，如果事件已得到修正，SOC 分析人员可能将该事件设置为“已解决”****。 解决事件后，系统将自动关闭事件中仍处于打开状态的所有警报。 

### <a name="classification-and-determination"></a>分类和确定
可以选择不设置分类，也可以决定指定事件为真实/误报事件。 这样做有助于团队查看模式并从中了解相关信息。 

## <a name="add-comments"></a>添加备注
可以添加备注并查看有关事件的历史事件，以便了解以前对其所做的更改。

每当对警报进行更改或添加备注时，都会在“备注”和“历史记录”部分进行记录。

添加的备注会立即显示在窗格中。

## <a name="add-incident-tags"></a>添加事件标记
可以向事件添加自定义标记，例如，标记一组具有共同特征的事件。 以后可以筛选包含特定标记的所有事件的事件队列。

