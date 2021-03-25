---
title: 解决 Microsoft Defender ATP for Mac 的许可证问题
description: 解决 Microsoft Defender ATP for Mac 中的许可证问题。
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
ms.openlocfilehash: 645c3657bdd1540ac95b68460b4dff6d25627c2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185918"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>解决 Microsoft Defender for Endpoint for Mac 的许可证问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

当你要完成适用于 [Mac](microsoft-defender-endpoint-mac.md) 的 Microsoft Defender for Endpoint 和 [手动](mac-install-manually.md) 部署测试或 PoC (概念证明) ，你可能会收到以下错误：

![许可证错误的图像](images/no-license-found.png)

**消息：** 

未找到许可证

看起来你的组织没有 Microsoft 365 企业版订阅的许可证。

请与管理员联系以寻求帮助。

**原因：** 

你已部署和/或安装了适用于 macOS 的 Microsoft Defender for Endpoint 程序包 ("下载安装程序包") 但你可能已运行配置脚本 ("下载载入程序包") 。

**解决方案：**

按照以下 MicrosoftDefenderATPOnboardingMacOs.py 说明操作： [客户端配置](mac-install-manually.md#client-configuration)

