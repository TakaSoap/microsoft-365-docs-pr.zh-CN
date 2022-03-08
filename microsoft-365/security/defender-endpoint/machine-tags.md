---
title: 创建和管理设备标签
description: 使用设备标记对设备进行分组以捕获上下文，并启用动态列表创建作为事件的一部分
keywords: 标记， 设备标记， 设备组， 组， 修正， 级别， 规则， aad 组， 角色， 分配， 排名
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 65df8553f5ee3b7dd7876557398e0d4aa22c7bd5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323517"
---
# <a name="create-and-manage-device-tags"></a>创建和管理设备标签

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

在设备上添加标记，创建逻辑组等同。 设备标记支持网络适当映射，可附加不同的标记以捕获上下文，并启用在事件过程中创建动态列表。 标记可在设备清单视图中 **用作筛选器，** 或用于对设备进行分组。 有关设备分组详细信息，请参阅 [创建和管理设备组](machine-groups.md)。

可以使用以下方法在设备上添加标记：

- 使用门户
- 设置注册表项值

> [!NOTE]
> 将标记添加到设备的时间与标记在设备列表和设备页面中的可用性之间可能有一些延迟。

若要使用 API 添加设备标记，请参阅 [添加或删除设备标记 API](add-or-remove-machine-tags.md)。

## <a name="add-and-manage-device-tags-using-the-portal"></a>使用门户添加和管理设备标记

1. 选择要用于管理标签的设备。 可以从以下任一视图选择或搜索设备：

   - **安全操作仪表板** - 从具有活动警报的热门设备部分选择设备名称。
   - **警报队列** - 从警报队列中选择设备图标旁边的设备名称。
   - **设备清单** - 从设备列表中选择设备名称。
   - **搜索框** - 从下拉菜单中选择设备，然后输入设备名称。

     还可通过文件和 IP 视图访问警报页面。

2. 从 **"响应操作** "行中选择"管理标记"。

    :::image type="content" alt-text="管理标记按钮的图像。" source="images/manage-tags-option.png":::

3. 键入 以查找或创建标记

    :::image type="content" alt-text="在设备上添加标记的图像1。" source="images/create-new-tag.png":::

标记将添加到设备视图，并且也会反映在 **设备清单** 视图中。 然后，可以使用 **标记** 筛选器查看相关设备列表。

> [!NOTE]
> 筛选可能对包含括号的标记名称不起作用。
>
> 创建新标记时，将显示现有标记的列表。 该列表只显示通过门户创建的标记。 不会显示从客户端设备创建的现有标记。

您还可以从此视图中删除标记。

:::image type="content" alt-text="在 device2 上添加标记的图像。" source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>通过设置注册表项值添加设备标记

> [!NOTE]
> 仅适用于以下设备：
>
> - Windows 11
> - Windows 10版本 1709 或更高版本
> - Windows Server 版本 1803 或更高版本
> - Windows Server 2016
> - Windows Server 2012 R2
> - Windows Server 2008 R2 SP1
> - Windows 8.1
> - Windows 7 SP1

> [!NOTE]
> 标记中可以设置的最大字符数为 200。

当你需要对特定设备列表应用上下文操作时，具有类似标记的设备可能很方便。

使用以下注册表项在设备上添加标记：

- 注册表项： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- 注册表项值 (REG_SZ) ： `Group`
- 注册表项数据： `Name of the tag you want to set`

> [!NOTE]
> 设备标记是每天生成的设备信息报告的一部分。 或者，你可以选择重新启动将传输新设备信息报告的终结点。
>
> 如果需要删除使用上述注册表项添加的标记，请清除注册表项数据的内容，而不是删除"Group"项。
