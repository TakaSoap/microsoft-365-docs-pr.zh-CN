---
title: 在 Jamf 中设置设备Pro
description: 了解如何在 MacOS 上为 Microsoft Defender for Endpoint 在 Jamf Pro设置设备组
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d35cd0ecba75be5f6546840e5c80177f950b7193
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171049"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>在 Jamf 设备组中为 macOS 设备组设置 Microsoft Defender Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

将设备组设置为类似于组策略组织 (OUS) Microsoft Endpoint Configuration Manager设备集合和 Intune 的设备组。

1. 导航到 **静态计算机组**。

2. 选择"**新建"。** 

    ![Jamf Pro1 的图像。](images/jamf-pro-static-group.png)

3. 提供显示名称 **并选择保存。**

    ![Jamf Pro2 的图像。](images/jamfpro-machine-group.png)

4. 现在，你将在静态 **计算机组下看到 Contoso** **的计算机组**。

    ![Jamf Pro3 的图像。](images/contoso-machine-group.png)

## <a name="next-step"></a>后续步骤
- [在 Jamf 中设置 macOS 策略上的 Microsoft Defender for Endpoint Pro](mac-jamfpro-policies.md)
