---
title: '在 Microsoft Defender for Business 预览版中 (设备) '
description: '了解如何在 Microsoft Defender for Business 预览版中 (设备) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 5bb36ecb0ca2d382ce64a6746b1c6bfcfceff22b
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421134"
---
# <a name="manage-devices-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中 (设备) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未包含 (一些) 。

在 Microsoft Defender for Business (预览) 中，你可以按如下方式管理设备：

- [查看已载入设备列表](#view-the-list-of-onboarded-devices) 以查看其风险级别、曝光级别和运行状况状态
- [在具有威胁](#take-action-on-a-device-that-has-threat-detections) 检测的设备上采取措施
- [将设备载入 Defender for Business (预览) ](#onboard-a-device)  
- [从 Defender for Business 预览版 (设备) ](#offboard-a-device)

## <a name="view-the-list-of-onboarded-devices"></a>查看已载入设备列表

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="设备清单的屏幕截图":::

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 在导航窗格中，选择"**设备清单"。**

3. 选择设备以打开其飞出面板，可在其中了解有关其状态和采取措施的更多信息。 

   如果你尚未列出任何设备，将设备载入 Microsoft [Defender for Business (预览版) ](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>在具有威胁检测的设备上采取措施

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="包含详细信息和可用操作选定设备的屏幕截图":::

1. 在Microsoft 365 Defender门户 () "导航窗格中，选择" [https://security.microsoft.com](https://security.microsoft.com) 设备 **清单"。** 

2. 选择设备以打开其飞出面板，并查看显示的信息。

3. Select the ellipsis (**...**) to open the actions menu. 

4. 选择一个操作，如 **运行防病毒扫描** 或 **启动自动调查**。 

## <a name="onboard-a-device"></a>载入设备

请参阅[将设备载入到 Microsoft Defender for Business (预览) 。 ](mdb-onboard-devices.md)

## <a name="offboard-a-device"></a>载出设备

请参阅 [载出设备](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device)。

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中响应 (缓解) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [创建或编辑设备组](mdb-create-edit-device-groups.md)
