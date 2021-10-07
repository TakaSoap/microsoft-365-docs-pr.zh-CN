---
title: Android 上的 Microsoft Defender for Endpoint - 隐私信息
description: 隐私控制，如何配置影响隐私的策略设置，以及 Android 上的 Microsoft Defender for Endpoint 中收集的诊断数据信息。
keywords: microsoft， defender， Microsoft Defender for Endpoint， android， 隐私， 诊断
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 185ffab8d4fb67040d11dbf8b36459b94341a0d2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176903"
---
# <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Android 上的 Microsoft Defender for Endpoint - 隐私信息

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

Android 上的 Defender for Endpoint 从已配置的 Android 设备收集信息，并存储到具有 Defender for Endpoint 的同一租户中。 该信息的收集有助于使适用于 Android 的 Endpoint 的 Defender 保持安全、最新、如预期运行并支持服务。

有关数据存储详细信息，请参阅适用于终结点数据存储[和隐私的 Microsoft Defender。](data-storage-privacy.md)

收集的信息有助于使适用于 Android 的 Defender for Endpoint 保持安全、最新、如预期运行并支持服务。

有关 Android 和 iOS 移动设备上的 Microsoft Defender for Endpoint 的最常见隐私问题详细信息，请参阅适用于终结点的 Microsoft Defender 和 Android 和 [iOS 移动设备上的隐私](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)。

## <a name="required-data"></a>所需数据

必需数据包含使适用于 Android 的 Defender for Endpoint 按预期工作所需的数据。 此数据对于服务操作至关重要，可以包含与最终用户、组织、设备和应用相关的数据。 以下是要收集的数据类型列表：

### <a name="app-information"></a>应用信息

有关设备上 **恶意** Android (程序包) API 的信息，包括

- 安装源
- 存储 APK (文件路径) 位置
- 安装时间、APK 大小和权限

### <a name="web-page--network-information"></a>网页/网络信息

- 仅在检测到恶意连接或网页时，网站的完整 URL。
- 连接信息
- 协议类型 (如 HTTP、HTTPS 等) 

### <a name="device-and-account-information"></a>设备和帐户信息

- 设备信息，如&时间、Android 版本、OEM 型号、CPU 信息和设备标识符。
- 设备标识符是以下项之一：
  - Wi-Fi适配器 MAC 地址
  - [Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (由 Android 在首次启动设备时生成) 。
  - 随机生成的全局唯一标识符 (GUID) 。

- 租户、设备和用户信息
  - Azure Active Directory (AD) 设备 ID 和 Azure 用户 ID：唯一标识设备，即 Azure Active Directory 中的用户。
  - Azure 租户 ID：用于标识组织中组织的 GUID Azure Active Directory。
  - Microsoft Defender for Endpoint 组织 ID：与设备所属的企业关联的唯一标识符。 允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响。
  - 用户主体名称：用户的电子邮件 ID

### <a name="product-and-service-usage-data"></a>产品或服务使用情况数据

仅为设备上安装的 Microsoft Defender for Endpoint 应用收集以下信息。 

- 应用包信息，包括名称、版本以及应用升级状态。
- 在应用中执行的操作。
- 威胁检测信息，例如威胁名称、类别等。
- 由 Android 生成的崩溃报告日志。

## <a name="optional-data"></a>可选数据

可选数据包括诊断数据和反馈数据。 可选诊断数据是一种附加数据，有助于我们改进产品并提供增强的信息来帮助检测、诊断和修复问题。 可选诊断数据包括：

- 应用、CPU 和网络使用情况。
- 从应用的角度来看，设备的状态，包括扫描状态、扫描计时、授予的应用权限和升级状态。
- 管理员配置的功能。
- 有关设备上浏览器的基本信息。

**反馈 通过** 用户提供的应用内反馈收集数据

- 用户的电子邮件地址（如果他们选择提供它）。
- 反馈类型 (、笑脸、想法) 以及用户提交的任何反馈评论。
