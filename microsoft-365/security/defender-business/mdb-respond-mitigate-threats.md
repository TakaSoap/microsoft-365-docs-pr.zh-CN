---
title: '响应和缓解 Microsoft Defender for Business 预览版 (威胁) '
description: 检测到威胁时，你可以采取措施来响应和缓解这些威胁。
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
ms.openlocfilehash: cbd05b701c5276644e98671c9f07b4fbcf27c682
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421122"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business-preview"></a>响应和缓解 Microsoft Defender for Business 预览版 (威胁) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未包含 (一些) 。

通过Microsoft 365 Defender门户，安全团队可以响应并缓解检测到的威胁。

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 请注意主页上的卡片。 卡片一目了然地显示检测到的威胁数，以及受影响的用户帐户数、 (终结点) 和其他资产。 下图是你可能会看到的卡片示例：

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="客户门户中的Microsoft 365 Defender屏幕截图":::

3. 选择卡片上的按钮或链接以查看详细信息并采取措施。 例如，我们的 **"处于** 风险中的设备"卡片包含" **查看详细信息"** 按钮。 选择该按钮将我们导航到 **"设备清单** "页，如下图所示：

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="设备清单的屏幕截图":::

   " **设备清单** "页列出了公司设备及其风险级别和曝光级别。

4. 选择一个项目，例如设备。 将打开一个飞出窗格，并显示有关为该项目生成的警报和事件的详细信息，如下图所示：  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="所选设备的飞出窗格屏幕截图":::

5. 在飞出菜单上，查看显示的信息。 选择省略号 (...) 打开列出可用操作菜单，如下图所示： 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="所选设备的可用操作屏幕截图":::

6. 选择可用操作。 例如，你可以选择"运行 **防病毒扫描**"，这Microsoft Defender 防病毒在设备上启动快速扫描。 或者，可以选择启动 **自动调查** 以在设备上触发自动调查。

## <a name="next-steps"></a>后续步骤

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [在 Microsoft Defender for Business 预览版中 (设备) ](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)
