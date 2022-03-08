---
title: 设备部署组
description: 用于管理更新和其他更改的部署组
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 624bde84da9a0c35f5814e3b6c67c2d190683fc6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330295"
---
# <a name="device-deployment-groups"></a>设备部署组

Microsoft 托管桌面组管理更新版本和设备配置更改。 设备将添加到部署组 ("圈"或"更新组) 注册到部署组时自动Microsoft 托管桌面。 部署组允许设备接收分段时间线中的更改。

你可能希望分配某些设备仅用于测试目的，或指定特定的早期采用者来首先接收更改。 如果你有关键设备（如主管人员使用的设备或执行业务关键功能的设备），你可能希望将它们保持在以最慢的速度获取更新的组中。 Microsoft 托管桌面允许你指定设备应留在以下任一组中。

| Group | 说明 |
| ----- | ----- |
| 测试 | 测试组最适合用于测试的设备，或可以容忍频繁更改、公开新功能并能够提供早期反馈的用户。<br><br>该组经常接收更改，并且此组的体验具有强大的影响。 测试组不受任何已建立的服务级别协议和用户支持。 最好首先仅移动几台设备，然后查看用户体验。 Microsoft 托管桌面不会自动向此组分配设备。 此组将仅包含你指定的设备。
| First | 第一组非常适合早期采用者、志愿者、指定的验证者、IT 专业人员或业务职能代表。 即，可以验证更改并提供体验反馈的人。
| 快速 | Fast 组非常适合业务职能代表。 这些人员可以在广泛部署之前验证更改。
| 宽泛 | Broad 组最后接收更改。<br><br>你的大多数组织通常都在此组中。 你可以指定必须在此组中的设备。 这些设备应最后收到更改，因为它们执行业务关键功能，或属于关键角色的用户。
| 自动 | 如果希望将设备自动Microsoft 托管桌面组之一，请选择"自动"。<br><br>我们不会自动将设备分配给 Test。 如果要释放之前指定的设备，以便可以再次自动分配该设备，请选择此选项。

有关如何在组中管理更新Windows，请参阅如何在组中[处理](updates.md)Microsoft 托管桌面。

## <a name="labels"></a>标签

"按列分配的组"包含以下标签：

| 标签 | 说明 |
| ----- | ----- |
| 管理员 | 设备位于你指定的组中。 |
| 自动 | Microsoft 托管桌面组。 |
| Pending | 设备正在移动到组。 |

" **组** "列始终显示设备当前位于的组，并且仅在移动完成时更新。

> [!IMPORTANT]
> 不要尝试直接修改这些组的成员身份。 始终按照将设备分配给 [部署组中所述的步骤操作](../working-with-managed-desktop/assign-deployment-group.md)。
