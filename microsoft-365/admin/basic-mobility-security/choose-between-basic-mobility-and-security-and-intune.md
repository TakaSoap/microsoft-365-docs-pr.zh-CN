---
title: 在基本移动性和安全性与 Intune 之间选择
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 基本移动性和安全性是基本移动Microsoft 365的一部分。
ms.openlocfilehash: 0a461bc7462300bb2b27b5d027c2b4d4582b7d14
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166226"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>在"基本移动性和安全性"或"Intune"之间选择

[Microsoft Intune](/mem/intune/)是一种包含在特定Microsoft 365中的独立产品，而 Basic Mobility and Security 是 Microsoft 365计划的一部分。

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>基本移动性和安全性与 Intune 的可用性

基本移动性和安全性以及 Intune 均包含在各种计划中，如下表所述。

| 计划 | 基本移动性和安全性 | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 应用版|是|否|
|Microsoft 365 商业基础版|是|否|
|Microsoft 365 商业标准版|是|否|
|Office 365 E1 |是|否|
|Office 365 E3 |是|否|
|Office 365 E5 |是|否|
|Microsoft 365 商业高级版 |是|是|
|Microsoft 365一线 3 |是|是|
|Microsoft 365 企业版 E3 |是|是|
|Microsoft 365 企业版 E5 |是|是|
|Microsoft 365 教育版A1 |是|是|
|Microsoft 365 教育版 A3 |是|是|
|Microsoft 365 教育版 A5 |是|是|
|Microsoft Intune |否|是|
|Enterprise移动性&安全性 E3 |否|是|
|企业移动性 + 安全性 E5 |否|是|

> [!NOTE]
> 如果已在使用基本移动性和安全性，你无法开始使用Microsoft Intune。

 有关详细信息，请参阅[Microsoft 365和Office 365平台服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。

## <a name="differences-in-capabilities"></a>功能差异

Microsoft Intune和内置的基本移动性和安全性都为您提供了管理组织中移动设备的能力，但功能上存在一些关键差异，如下表所述。

> [!NOTE]
> 可以在同一 Microsoft 365 商业标准版 组织中使用 Intune 和基本移动性和安全性来管理用户及其移动设备，方法为先设置 *基本* 移动性和安全性，然后添加Microsoft Intune。 这允许你选择"基本移动性和安全性"或功能更丰富的 Intune 解决方案。 分配 Intune 许可证以启用 Intune 功能。

| 功能区域 | 功能突出显示 | 基本移动性和安全性 | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|设备类型|管理不同的操作系统平台和主要管理模式变体。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad OS|
|设备合规性|设置和管理安全策略，如设备级别的 PIN 锁定和越狱检测。 |Android 9 及更高版本设备上的限制。 请参阅 [详细信息](capabilities.md)。 |是|
|基于设备合规性的条件访问 |防止不相容的设备从云中访问公司电子邮件和数据。 |不支持在Windows 10。<br/>仅限于控制对 Exchange Online、SharePoint Online 和 Outlook 的访问。 |是 |
|设备配置  |配置设备 (例如，禁用相机) |有限的设置集。|是|
|电子邮件配置文件  |在设备上预配本机电子邮件配置文件。 |是|是|
|WiFi 配置文件 |在设备上预配本机 WiFi 配置文件。 |否|是|
|VPN 配置文件 |在设备上预配本机 VPN 配置文件。 |否|是|
|移动应用管理  |将内部业务线应用和从应用商店部署到用户。 |否|是|
|移动应用程序保护  |使用户可以使用他们所知的 Office 移动和业务线应用安全地访问公司信息，同时通过帮助将复制、剪切、粘贴和另存为等操作限制为仅针对经公司数据批准的那些应用，从而确保数据安全。 即使设备未注册到基本移动性和安全性，也有效。 请参阅使用 MAM 策略保护应用数据。 |否|是|
|托管浏览器  |使用 Edge 应用启用更安全的 Web 浏览。 |否|是|
|AutoPilot (零触摸注册)  |注册大量企业拥有的设备，同时简化用户设置。 |否|是|
|||

除了上表中列出的功能之外，基本移动性和安全性以及 Intune 还包括一组通过 Internet 将命令发送到设备的远程操作。 例如，你可以从员工设备中删除 Office 数据，同时就地保留个人数据 (停用) ，从员工的设备 (擦除) 中删除 Office 应用，或将设备重置为出厂设置 (完全擦除) 。

基本移动和安全远程操作包括停用、擦除和完全擦除。 有关基本移动和安全操作的信息，请参阅 [基本移动性和安全性的功能](capabilities.md)。

借助 Intune，你可以执行以下一组操作：

-   仅 Autopilot (Windows重置
-  [Bitlocker 密钥旋转](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Windows仅) 
-  [使用擦除、停用或手动注销设备](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [禁用激活 loc](/mem/intune/remote-actions/device-activation-lock-disable)   (iOS) 
-  [全新开始](/mem/intune/remote-actions/device-fresh-start)   (Windows) 
- [完全扫描](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Windows 10仅) 
- [查找设备](/mem/intune/remote-actions/device-locate)   (iOS) 
- [丢失模式](/mem/intune/remote-actions/device-lost-mode)   (iOS) -[仅 (Windows 10](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)快速) 
- [适用于 Android 的远程控制](/mem/intune/remote-actions/teamviewer-support)
- [远程锁定](/mem/intune/remote-actions/device-remote-lock)
- [重命名设备](/mem/intune/remote-actions/device-rename)
-  [重置密码](/mem/intune/remote-actions/device-passcode-reset)[仅](/mem/intune/remote-actions/device-restart)   (Windows密码) 
-  仅Windows Defender更新 (Windows安全) 
-  Windows 10仅 (Windows PIN 重置) 
-  [发送自定义通知](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android、iOS、iPad 操作系统) 
-  [同步设备](/mem/intune/remote-actions/device-sync)

有关 Intune 操作详细信息，请参阅Microsoft Intune[文档](/mem/intune/)。
