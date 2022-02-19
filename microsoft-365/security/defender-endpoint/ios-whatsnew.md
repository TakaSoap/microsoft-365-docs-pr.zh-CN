---
title: iOS 上的 Microsoft Defender for Endpoint 的新增功能
description: 了解 iOS 上早期版本的 Microsoft Defender for Endpoint 的主要更改。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， macos， whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: sunasing
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 503ae29fd371948f68b0c25aafe34f02f7bb8f1d
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62903692"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-ios"></a>iOS 上的 Microsoft Defender for Endpoint 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="improved-experience-on-supervised-ios-devices"></a>改进的受监督 iOS 设备体验

iOS 上的 Microsoft Defender for Endpoint 现在具有监督 iOS/iPadOS 设备的专门功能，因为平台在这些类型的设备上提供了增强的管理功能。 它还可以提供 Web 保护 **，而无需在设备上设置本地 VPN**。 这为最终用户提供了无缝体验，同时仍受到网络钓鱼和其他基于 Web 的攻击的保护。 有关详细信息，请访问 [本文档](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-app-store"></a>Microsoft Defender for Endpoint 现在是应用商店中的 Microsoft Defender

Microsoft Defender for Endpoint 现已在应用商店 **中作为 Microsoft Defender** 提供。 通过此更新，该应用将在美国地区作为 **消费者的预览版提供**。 根据你使用工作或个人帐户登录应用后，你将有权访问适用于终结点的 Microsoft Defender 功能或适用于个人 Microsoft Defender 的功能。 有关详细信息，请参阅 [此博客](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals)。

## <a name="threat-and-vulnerability-management"></a>威胁和漏洞管理

2022 年 1 月 25 日，我们宣布在 Android 和 iOS 上正式发布威胁和漏洞管理。 有关详细信息，请参阅此处 [的 techcommunity 文章](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)。

## <a name="1124210103"></a>1.1.24210103

- 解决了受监督设备的 Internet 连接问题。 有关详细信息，请参阅在已注册 [的 iOS 设备上部署适用于终结点的 Defender](ios-install.md)。
- Bug 修复。

## <a name="1123250104"></a>1.1.23250104

- 性能优化 - 使用此版本测试电池性能，并告诉我们您的反馈。
- **适用于已注册的 iOS** 设备的零接触载入 - 借助此版本，已添加通过 Microsoft Endpoint Manager (Intune) 注册的零接触板预览。 有关详细信息，请参阅本文档 [，](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview) 详细了解安装和配置。
- **隐私控制** - 配置网络钓鱼警报报告的隐私控制。 有关详细信息，请参阅配置 [iOS 功能](ios-configure-features.md)。

## <a name="1123010101"></a>1.1.23010101

- Bug 修复和性能改进 
  - 此版本进行了性能优化。 使用此版本测试电池性能，并告诉我们您的反馈。

## <a name="1120240103"></a>1.1.20240103
- 设备运行状况卡 - 设备运行状况卡向最终用户通知任何挂起的软件更新。
- 可用性增强功能 - 最终用户现在可以从 MSDefender 应用本身禁用 Defender for Endpoint VPN。 在此更新之前，最终用户必须仅从 设置禁用 VPN。
- Bug 修复。

## <a name="1120020101"></a>1.1.20020101
- UX 增强功能 - 适用于终结点的 Microsoft Defender 具有新外观。
- Bug 修复。

## <a name="1117240101"></a>1.1.17240101
- 此版本通常提供对通过 Intune (MAM) 移动应用的支持。 有关详细信息，请参阅 [适用于应用保护策略的 Microsoft Defender 终结点风险信号](https://techcommunity.microsoft.com/t5/intune-customer-success/microsoft-defender-for-endpoint-risk-signals-available-for-your/ba-p/2186322)
- **越狱检测** 通常可用。 有关详细信息，请参阅基于 [设备风险信号设置条件访问策略](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)。
- **已注册设备的 VPN 配置文件的自动** 设置Microsoft Endpoint Manager (Intune) 通常可用。 有关详细信息，请参阅为已注册的 [iOS 设备自动设置 VPN 配置文件](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)。
- Bug 修复。

## <a name="1115140101"></a>1.1.15140101

- **越狱检测** 为预览版。 有关详细信息，请参阅基于 [设备风险信号设置条件访问策略](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)。
- **对于通过** Intune 应用程序注册的设备，VPN 配置文件的Microsoft Endpoint Manager (预览) 。 有关详细信息，请参阅为已注册的 [iOS 设备自动设置 VPN 配置文件](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)。
- Microsoft Defender ATP 产品名称现已更新到应用商店中的 Microsoft Defender for Endpoint。
- 改进了登录体验。
- Bug 修复。

## <a name="1115010101"></a>1.1.15010101

- 在此版本中，我们将宣布支持 iPadOS/iPad设备。
- Bug 修复。
