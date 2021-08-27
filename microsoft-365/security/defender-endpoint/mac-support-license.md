---
title: 解决 Mac 上 Microsoft Defender for Endpoint 的许可证问题
description: 解决 Mac 上的 Microsoft Defender for Endpoint 中的许可证问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 性能
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
ms.openlocfilehash: 5b1cee16f4eccaa8f6fd36d8764b1305cba3131f
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611279"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>解决 macOS 上 Microsoft Defender for Endpoint 的许可证问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

当你在 [macOS](microsoft-defender-endpoint-mac.md) 上完成 Microsoft Defender for Endpoint 和 [手动](mac-install-manually.md) 部署测试或概念证明 (PoC) 时，你可能会收到以下错误：

![许可证错误的图像。](images/no-license-found.png)

**消息：** 

未找到许可证

看起来你的组织没有订阅Microsoft 365 企业版许可证。

请与管理员联系以寻求帮助。

**原因：** 

你已部署和/或安装了适用于 macOS 的 Microsoft Defender 终结点程序包 ("下载安装程序包") ，但你可能尚未运行配置脚本 ("下载载入程序包") ，或者你尚未向用户分配许可证。

**解决方案：**

按照以下 MicrosoftDefenderATPOnboardingMacOs.py 说明操作： [客户端配置](mac-install-manually.md#client-configuration)
