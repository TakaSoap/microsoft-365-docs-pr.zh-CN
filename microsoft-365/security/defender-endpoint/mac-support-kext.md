---
title: 解决 Microsoft Defender ATP for Mac 中的内核扩展问题
description: 解决 Microsoft Defender ATP for Mac 中与内核扩展相关的问题。
keywords: microsoft， defender， atp， mac， 内核， 扩展
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
ms.openlocfilehash: bdd5c6309a19863339b00e846c1c2670fc4f261b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187597"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a>解决 Microsoft Defender for Endpoint for Mac 中的内核扩展问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本文提供有关解决作为 Microsoft Defender for Endpoint for Mac 的一部分安装的内核扩展的问题的信息。

从 macOS High Sierra (10.13) 开始，macOS 要求在允许所有内核扩展在设备上运行之前得到明确批准。

如果在部署/安装 Microsoft Defender for Endpoint for Mac 期间未批准内核扩展，则应用程序将显示横幅提示你启用它：

   ![RTP 已禁用屏幕截图](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

还可以运行 ```mdatp health``` 。 它报告实时保护是否已启用，但不可用。 这表示未批准在设备上运行内核扩展。

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

以下各节提供有关如何解决此问题的指导，具体取决于你用于部署适用于 Mac 的 Microsoft Defender for Endpoint 的方法。

## <a name="managed-deployment"></a>托管部署

请参阅用于部署产品的管理工具对应的说明：

- [基于 JAMF 的部署](mac-install-with-jamf.md)
- [基于 Microsoft Intune 的部署](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>手动部署

如果安装产品后不到 30 分钟，请导航到"系统首选项安全性 & 隐私"，其中您必须允许开发人员  >  "Microsoft  Corporation"提供系统软件。

如果未看到此提示，则意味着 30 分钟或更长的时间已过，并且内核扩展尚未获得批准，无法在你的设备上运行：

![提示过期屏幕截图后的安全和隐私窗口](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

在这种情况下，您需要执行以下步骤以再次触发审批流程。

1. 在终端中，尝试安装驱动程序。 以下操作将失败，因为内核扩展未获准在设备上运行。 但是，它将再次触发审批流程。

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. 从 **菜单中打开** 系统  >  **首选项&隐私**"。  (，请首先关闭它。) 

3. **允许** 来自开发人员"Microsoft Corporation"的系统软件

4. 在终端中，再次安装驱动程序。 此时操作将成功：

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    横幅应从 Defender 应用程序中消失，现在应报告实时保护已启用 ```mdatp health``` 且可用：

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
