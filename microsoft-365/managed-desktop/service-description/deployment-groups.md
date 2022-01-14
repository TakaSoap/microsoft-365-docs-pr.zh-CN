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
ms.openlocfilehash: acadc3315f1605259f90739866cb73b6b1e1cc9c
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034865"
---
# <a name="device-deployment-groups"></a>设备部署组

Microsoft 托管桌面使用部署组来管理对设备的更新和配置更改的发布。 设备将添加到部署组 ("圈"或"更新组") 注册到部署组Microsoft 托管桌面。 部署组允许设备接收分段时间线中的更改。

你可能希望分配某些设备仅用于测试目的，或指定特定的早期采用者来首先接收更改。 如果你有关键设备（如主管人员使用的设备）或执行业务关键型功能的设备，你可能希望将它们保持在以最慢的速度获取更新的组中。 Microsoft 托管桌面允许你指定设备应留在以下任一组中。

- **测试**：最适合用于测试的设备，或可以容忍频繁更改和接触新功能并提供早期反馈的用户。 该组经常接收更改，并且此组的体验具有强大的影响。 测试组不受任何已建立的服务级别协议和用户支持。 最好首先仅移动几台设备，然后检查用户体验。 Microsoft 托管桌面不会自动将设备分配给此组;它仅包含你指定的设备。
- **第** 一：非常适合早期采用者、志愿者或指定的验证者、IT 专业人员或业务职能代表，即可以验证更改并提供体验反馈的人。
- **广泛** 接收最后一次更改。 你的大多数组织通常都在此组中。 还可以指定必须在此组中并且只应最后接收更改的设备，因为它们执行业务关键功能或属于关键角色的用户。 
- **自动**：如果希望将设备自动分配给Microsoft 托管桌面组之一，请选择此选项。  (我们不会将设备自动分配给 Test.) 如果你想要释放之前指定的设备以便可以再次自动分配它，请选择此选项。 

Microsoft 托管桌面使用一些其他组来控制部署，但无法为其分配设备。 但是，你可以将设备从这些组移动到本文中的组之一。 有关如何在组中管理更新Windows，请参阅如何在组中[处理](updates.md)Microsoft 托管桌面。

如果设备位于你指定的组中，分配了的组 **将****说管理员**。如果Microsoft 托管桌面组，则说明"自动 **"。** 当设备正在移动到组时，它将 **表示挂起**。 " **组** "字段始终显示设备当前位于的组，并且仅在移动完成时更新。

> [!IMPORTANT]
> 不要尝试直接修改这些组的成员身份。 始终按照将设备分配给部署 [组 中所述的步骤操作](../working-with-managed-desktop/assign-deployment-group.md)。
