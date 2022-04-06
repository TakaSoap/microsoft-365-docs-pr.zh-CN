---
title: 在 Jamf 中设置设备Pro
description: 了解如何在 macOS 上为 Microsoft Defender for Endpoint 在 Jamf Pro设置设备组
keywords: device， group， microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c22a1a68af2722e6b17d155a37632c1f6417b605
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471750"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>在 Jamf 设备组中设置 macOS 设备组的 Microsoft Defender for endpoint Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

将设备组设置为类似于组策略组织 (OUS) 、Microsoft Endpoint Configuration Manager 的设备集合和 Intune 的设备组。

1. 导航到 **"静态计算机组"**。

2. 选择 **新建**。 

   :::image type="content" source="images/jamf-pro-static-group.png" alt-text="Jamf Pro1 页面" lightbox="images/jamf-pro-static-group.png":::

3. 提供显示名称，然后选择"保存 **"**。

   :::image type="content" source="images/jamfpro-machine-group.png" alt-text="Jamf Pro2 页面" lightbox="images/jamfpro-machine-group.png":::

4. 现在，你将在静态计算机 **组下看到 Contoso** **的计算机组**。

   :::image type="content" source="images/contoso-machine-group.png" alt-text="Jamf Pro3 页面" lightbox="images/contoso-machine-group.png":::

## <a name="next-step"></a>后续步骤
- [在 Jamf 中设置 macOS 策略上的 Microsoft Defender for Endpoint Pro](mac-jamfpro-policies.md)
