---
title: 在 Jamf Pro 中设置设备组
description: 了解如何在 Jamf Pro for Microsoft Defender for Endpoint for macOS 中设置设备组
keywords: device， group， microsoft， defender， atp， mac， installation， deploy， uninstallation， intune， jamfpro， macos， catalina， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861595"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>在 Jamf Pro 中的 macOS 设备组上设置 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

将设备组设置为类似于组策略组织 (OUS) 、Microsoft Endpoint Configuration Manager 的设备集合和 Intune 的设备组。

1. 导航到 **静态计算机组**。

2. 选择"**新建"。** 

    ![Jamf Pro1 的图像](images/jamf-pro-static-group.png)

3. 提供显示名称， **然后选择保存**。

    ![Jamf Pro2 的图像](images/jamfpro-machine-group.png)

4. 现在，你将在静态 **计算机组下看到 Contoso** **的计算机组**。

    ![Jamf Pro3 的图像](images/contoso-machine-group.png)

## <a name="next-step"></a>后续步骤
- [在 Jamf Pro 中的 macOS 策略上设置 Microsoft Defender for Endpoint](mac-jamfpro-policies.md)
