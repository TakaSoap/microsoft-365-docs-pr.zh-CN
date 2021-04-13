---
title: 解决 Android 上的 Microsoft Defender for Endpoint 上的问题
description: 解决 Android 上的 Microsoft Defender for Endpoint 的问题
keywords: microsoft， defender， atp， mde， android， 云， 连接， 通信
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1a19582073565a958aab444541381f5772b6f4f1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687599"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Android 上的 Microsoft Defender for Endpoint 问题疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

在载入设备时，你可能会在安装应用后看到登录问题。

在载入期间，在设备上安装应用后，你可能会遇到登录问题。

本文提供的解决方案可帮助解决登录问题。  

## <a name="sign-in-failed---unexpected-error"></a>登录失败 - 意外错误
**登录失败：意外***错误，请稍后尝试*

![登录失败错误意外错误的图像](images/f9c3bad127d636c1f150d79814f35d4c.png)

**消息：**

意外错误，请稍后尝试

**原因：**

设备上安装了旧版本的"Microsoft Authenticator"应用。

**解决方案：**

从 Google Play 应用商店安装最新版本和 [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) 并重试

## <a name="sign-in-failed---invalid-license"></a>登录失败 - 许可证无效

**登录失败：许可证***无效，请联系管理员*

![登录失败的图像请联系管理员](images/920e433f440fa1d3d298e6a2a43d4811.png)

**邮件：***许可证无效，请联系管理员*

**原因：**

你未分配 Microsoft 365 许可证，或者你的组织没有 Microsoft 365 企业版订阅的许可证。

**解决方案：**

请与管理员联系以寻求帮助。

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>某些 OEM 设备上不会阻止网络钓鱼页面

**适用于：** 仅特定 OEM

-   **小米**

某些用户不会阻止 Defender for Android 终结点检测到的网络钓鱼和有害的 Web 威胁。 以下功能在这些设备上不起作用。

![报告不安全网站的图像](images/0c04975c74746a5cdb085e1d9386e713.png)


**原因：**

用户设备包括新的权限模型。 这将阻止 Defender for Endpoint for Android 在后台运行时显示弹出窗口。

用户权限："在后台运行时显示弹出窗口"。

![弹出窗口设置的图像](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**解决方案：**

对一些设备启用所需的权限。

- 在后台运行时显示弹出窗口。
