---
title: Microsoft Defender for Endpoint - 移动威胁防护
ms.reviewer: ''
description: Microsoft Defender for Endpoint 中的移动威胁防护概述
keywords: 移动， defender， Microsoft Defender for Endpoint， ios， mtd， android， 安全
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce5d8fcf693b6586c134b8fe2381d3881e68d9d3
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767590"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender for Endpoint - 移动威胁防护

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

Android 和 iOS 上的 Microsoft Defender for Endpoint 是我们移动 **威胁防护解决方案 (MTD)**。 通常，公司会积极保护电脑免受漏洞影响和恶意攻击，但通常不会监视和保护移动设备。 在移动平台具有内置保护（如应用隔离和经过审查的消费者应用商店）的位置，这些平台仍易受基于 Web 或其他复杂攻击的攻击。 随着越来越多的员工使用设备工作并访问敏感信息，公司必须部署 MTD 解决方案来保护设备和你的资源免受对移动设备的日益复杂的攻击。

## <a name="key-capabilities"></a>关键功能

Android 和 iOS 上的 Microsoft Defender for Endpoint 提供以下关键功能：有关最新功能和优势的信息，请阅读 [我们的公告](https://aka.ms/mdeblog)。

<br>

|功能|说明|
|---|---|
|Web 保护|防钓鱼、阻止不安全的网络连接以及支持自定义指示器。|
|仅 Android (恶意软件防护) |扫描恶意应用。|
|越狱检测 (仅 iOS) |已越狱设备的检测。|
|TVM (威胁和漏洞)  |已载入移动设备的漏洞评估。 访问此页面[了解有关](next-gen-threat-and-vuln-mgt.md) Microsoft Defender for Endpoint 危险和漏洞管理的更多信息。 *请注意，在此预览版中仅支持 iOS 上的操作系统漏洞。*|
|统一警报|来自统一 M365 安全控制台中所有平台的警报|
|条件访问、条件启动|阻止有风险的设备访问公司资源。 此外，还可以将 Defender for Endpoint 风险信号添加到 MAM (应用) |
|隐私控制。 在预览 (请参阅下面的) |通过控制 Microsoft Defender for Endpoint 发送的数据，在威胁报告中配置隐私。 *请注意，隐私控制当前仅适用于已注册的设备。稍后将添加未注册设备的控件*|
|与 Microsoft Tunnel|可以与 MICROSOFT TUNNEL集成，这是一种 VPN 网关解决方案，可在单个应用中实现安全性和连接性。 当前仅在 Android 上可用|

所有这些功能都适用于适用于终结点许可证持有者的 Microsoft Defender。 有关详细信息，请参阅 [许可要求](minimum-requirements.md#licensing-requirements)。


## <a name="overview-and-deploy"></a>概述和部署

可通过 MEM 管理中心在移动设备上部署 Microsoft Defender Microsoft Endpoint Manager (终结点) 。 观看此视频，快速了解 MTD 功能和部署：

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

### <a name="deploy"></a>部署

下表总结了如何在 Android 和 iOS 上部署 Microsoft Defender for Endpoint。 有关详细文档，请参阅 
- [Android 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md) 概述，
- [iOS 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-ios.md)

**Android**

|注册类型     |详细信息      |
|--------------------|-------------|
|Android Enterprise Intune Unified Endpoint Manager (Microsoft Endpoint Manager) |[在 Android Enterprise注册的设备上部署](android-intune.md#deploy-on-android-enterprise-enrolled-devices)|
|使用 Intune Unified Endpoint Manager (Microsoft Endpoint Manager) 的设备管理员|[在设备管理员注册的设备上部署](android-intune.md#deploy-on-device-administrator-enrolled-devices)|
|非托管 BYOD 或由 MAM 管理的其他统一终结点管理员/安装程序应用保护策略 (设备) |[在 MAM 应用中配置应用保护策略 (Defender) ](android-configure-mam.md)|

**iOS**

|注册类型     |详细信息      |
|--------------------|-------------|
|使用 Intune Unified Endpoint Manager (Microsoft Endpoint Manager) |1. [部署为 iOS 应用商店应用](ios-install.md)<br/>2. [为监督的 iOS 设备设置没有 VPN 的 Web 保护](ios-install.md#complete-deployment-for-supervised-devices)|
|未 (INtune UEM) 注册的 BYOD (Microsoft Endpoint Manager) |[部署为 iOS 应用商店应用](ios-install.md)|
|非托管 BYOD 或由 MAM 管理的其他 UEM/安装程序应用保护策略 (设备) |[在 MAM 应用中配置应用保护策略 (Defender) ](ios-install-unmanaged.md)|

### <a name="end-user-onboarding"></a>最终用户载入

- [为 iOS](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview) 注册的设备配置零接触载入：管理员可以配置零接触安装，以在已注册的 iOS 设备上以静默方式载入 Microsoft Defender for Endpoint，而无需用户打开该应用。 

- [配置条件访问以强制用户](android-configure.md#conditional-access-with-defender-for-endpoint-on-android)载入：这可应用以确保最终用户在部署后载入到 Microsoft Defender for Endpoint 应用。 观看此视频，观看有关使用 Defender for Endpoint 风险信号配置条件访问的快速演示。 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>简化载入

- [iOS - Zero-Touch载入](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview)
- [Android Enterprise - 设置始终打开 VPN](android-intune.md#auto-setup-of-always-on-vpn)。
- [iOS - 自动设置 VPN 配置文件](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="pilot-evaluation"></a>试点评估

使用 Microsoft Defender for Endpoint 评估移动威胁防护时，可以先验证是否满足特定条件，然后再继续将服务部署到更大的设备集。 可以定义退出条件并确保在广泛部署之前满足这些条件。

这有助于减少推出服务时可能出现的潜在问题。 下面是一些测试和退出条件，它们可能会有所帮助：

- 设备显示在设备清单列表中：在移动设备上成功载入 Defender for Endpoint 后，验证设备是否列在安全控制台的设备 [清单中](https://security.microsoft.com)。

- 在 Android 设备上运行恶意软件检测测试：从 Google Play 商店安装任何测试病毒应用，并验证它是否被 Microsoft Defender for Endpoint 检测到。 下面是可用于此测试的示例应用： [测试病毒](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus)。 请注意，在 Android Enterprise工作配置文件上，仅支持工作配置文件。

- 运行网络钓鱼测试：浏览 https://smartscreentestratings2.net 到 并验证它是否被 Microsoft Defender for Endpoint 阻止。 请注意，在 Android Enterprise工作配置文件上，仅支持工作配置文件。

- 警报显示在仪表板中：验证上述检测测试的警报是否显示在 [安全控制台上](https://security.microsoft.com)。

## <a name="configure"></a>配置

- [配置 Android 功能](android-configure.md)
- [配置 iOS 功能](ios-configure-features.md)
- [为受监督的 iOS 设备配置没有 VPN 的 Web 保护](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="resources"></a>资源

- [Android 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md)
- [iOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-ios.md)
- 阅读我们的公告，随时了解即将 [发布的通知](https://aka.ms/mdeblog)。

