---
title: 解决 Microsoft Defender for Endpoint for Mac 的性能问题
description: 解决 Microsoft Defender for Endpoint for Mac 中的性能问题。
keywords: microsoft， defender， atp， mac， 性能
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
ms.openlocfilehash: 87190d9e0bb62d42642374bd7c9f6f3acad3c80a
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379379"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>解决 Microsoft Defender for Endpoint for Mac 的性能问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主题提供了一些常规步骤，可用于缩小与 Microsoft Defender for Endpoint for Mac 相关的性能问题。

RTP (实时) 是适用于 Mac 的 Microsoft Defender for Endpoint 的一项功能，可持续监视你的设备并保护设备免受威胁。 它包含文件和进程监视以及其他启发。

根据你正在运行的应用程序和设备特征，在运行适用于 Mac 的 Microsoft Defender for Endpoint 时可能会遇到性能不优化的问题。 特别是，在短时间内访问许多资源的应用程序或系统进程可能会导致 Microsoft Defender for Endpoint for Mac 中的性能问题。

以下步骤可用于排查并缓解这些问题：

1. 使用下列方法之一禁用实时保护并观察性能是否提高。 此方法有助于缩小 Microsoft Defender for Endpoint for Mac 是否导致性能问题。

    如果你的设备不是由你的组织管理的，可以使用以下选项之一禁用实时保护：

    - 从用户界面。 打开 Microsoft Defender for Endpoint for Mac 并导航到"**管理设置"。**

      ![管理实时保护屏幕截图](images/mdatp-36-rtp.png)

    - 从终端。 出于安全目的，此操作需要提升权限。

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    如果你的设备由你的组织管理，则管理员可以使用设置适用于 Mac 的 Microsoft Defender for Endpoint 的首选项中的说明禁用 [实时保护](mac-preferences.md)。

2. 打开 Finder 并导航到 **应用程序**  >  **实用程序**。 打开 **活动监视器** 并分析哪些应用程序正在使用您系统上的资源。 典型示例包括软件更新和编译器。

3. 将 Microsoft Defender for Endpoint for Mac 配置为排除导致性能问题的进程或磁盘位置，并重新启用实时保护。

    有关详细信息 [，请参阅配置和验证适用于 Mac](mac-exclusions.md) 的 Microsoft Defender 终结点的排除项。
