---
title: '在 Microsoft Defender for Business 预览版中 (设备) '
description: '了解如何在 Microsoft Defender for Business 预览版中 (设备) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 5982934fa03c5898a2bd1908fd2f9a8487db2bba
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62465490"
---
# <a name="manage-devices-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中 (设备) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

在 Microsoft Defender for Business (预览) 中，你可以按如下方式管理设备：

- [查看已载入设备列表](#view-the-list-of-onboarded-devices) 以查看其风险级别、曝光级别和运行状况状态
- [在具有威胁](#take-action-on-a-device-that-has-threat-detections) 检测的设备上采取措施
- [将设备载入 Defender for Business (预览) ](#onboard-a-device)  
- [从 Defender for Business 预览版 (设备) ](#offboard-a-device)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="view-the-list-of-onboarded-devices"></a>查看已载入设备列表

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="设备清单的屏幕截图":::

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中，选择" **设备清单"**。

3. 选择设备以打开其飞出面板，可在其中了解有关其状态和采取措施的更多信息。 

   如果你尚未列出任何设备，将设备载入 [Microsoft Defender for Business (预览) ](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>在具有威胁检测的设备上采取措施

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="包含详细信息和可用操作选定设备的屏幕截图":::

1. 在Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) "导航窗格中，选择"设备 **清单"**。 

2. 选择设备以打开其飞出面板，并查看显示的信息。

3. Select the ellipsis (**...**) to open the actions menu. 

4. 选择一个操作，如 **运行防病毒扫描** 或 **启动自动调查**。 

## <a name="onboard-a-device"></a>载入设备

请参阅 [将设备载入到 Microsoft Defender for Business (预览) ](mdb-onboard-devices.md)。

## <a name="offboard-a-device"></a>载出设备

请参阅 [载出设备](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device)。

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 预览版 (中的威胁) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [创建或编辑设备组](mdb-create-edit-device-groups.md)
