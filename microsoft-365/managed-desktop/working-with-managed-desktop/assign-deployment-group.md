---
title: 将设备分配到部署组
description: 如何指定希望设备在哪个部署组中
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 6f3d2c79c23a37e1e1a965f9a3f416052a49fa76
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281419"
---
# <a name="assign-devices-to-a-deployment-group"></a>将设备分配到部署组

Microsoft 托管桌面将设备分配给各种部署组。 可以使用管理门户指定或更改设备分配到的组。 在设备注册或用户注册后更改分配。

> [!IMPORTANT]
> 如果更改分配，特定于该组的策略将应用于设备。 更改可能会安装最新版本的 Windows 10 (包括任何新功能或质量) 。 最好首先仅移动几台设备，然后检查生成的用户体验。 请注意，某些更新将重新启动设备。 仔细检查是否选择了正确的设备进行分配。 工作分配最多可能需要 24 小时才能生效。

**将设备分配给部署组：**

如果你想要将单独的设备移动到不同的组，请对每个组重复这些步骤。

1. In Microsoft Endpoint Manager， select **Devices** in the left pane.
1. 在"**Microsoft 托管桌面** 部分中，选择 **"设备"**。
1. 选择要分配的设备。 所有选定的设备都将分配给你指定的组。
1. 从 **菜单中选择** 设备操作。
1. 选择 **"将设备分配到组"**。 将打开一个飞入。
1. 使用下拉菜单选择要将设备移动到的组，然后选择"保存 **"**。 " **按列分配的组** "将更改为"挂起 **"**。

工作分配完成后，"按列分配的组"将更改为"管理员 (表明您进行了更改) "组"列将显示新的组分配。

> [!NOTE]
> 如果设备在"错误"或"挂起"注册状态，则不能将设备移动到其他组。
>
>如果设备尚未正确删除，它可能会显示"就绪"状态。 如果你移动此类设备，移动可能会无法完成。 如果在步骤 5 中未看到"按列分配的组"更改为"待定"，请在 Intune 中搜索设备以检查设备是否可用。 有关详细信息，请参阅[查看 Intune 中的设备详细信息](/mem/intune/remote-actions/device-inventory)。
