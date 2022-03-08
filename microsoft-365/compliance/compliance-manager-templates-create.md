---
title: 在 Microsoft 合规性管理器创建评估模板
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在 Microsoft 合规性管理器中创建评估模板。 使用格式化的文件创建和修改Excel模板。
ms.openlocfilehash: 1c7ccbe01d3411ace40cfe6ccdbe4fcb4d90480b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316179"
---
# <a name="create-an-assessment-template-in-microsoft-compliance-manager"></a>在 Microsoft 合规性管理器创建评估模板

若要在合规性管理器中为自定义评估创建自己的新模板，你将使用经过特殊格式Excel电子表格来组合必要的控制数据。 完成电子表格后，将其导入合规性管理器。

若要了解有关设置电子表格格式的信息[，请参阅使用](compliance-manager-templates-format-excel.md)电子表格设置评估Excel。

## <a name="required-roles"></a>所需角色

只有具有全局管理员或合规性管理器管理角色的用户才能创建和修改模板。 详细了解角色 [和权限](compliance-manager-setup.md#set-user-permissions-and-assign-roles)。

## <a name="create-new-template-in-compliance-manager"></a>在合规性管理器中创建新模板

1. 转到合规性 **管理器中的** 评估模板页面。
2. 选择 **"创建新模板"**。 将打开模板创建向导。
3. 选择要创建的模板类型。 在这种情况下，请选择" **创建自定义模板"，** 然后选择"下一步 **"**。
4. 在"**Upload文件**"屏幕上，选择"浏览"查找并上载包含所有所需Excel模板数据的格式化文件。
5. 如果文件没有问题，将显示上载的文件的名称。 选择“**下一步**”以继续。  (如果需要更改文件，请选择"更改Upload **文件")**。
    - 如果文件出错，顶部的错误消息将说明错误。 你将需要修复文件并再次上传它。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。
6. " **审阅和完成"** 屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好批准后，选择" **创建模板"。**  (如果需要进行更改，请选择" **Back**.) 
7. 最后一个屏幕确认已创建一个新模板。 选择 **"完成** "退出向导。
8. 你将到达新模板的详细信息页面，可在其中 [创建评估](compliance-manager-assessments.md#create-assessments)。
