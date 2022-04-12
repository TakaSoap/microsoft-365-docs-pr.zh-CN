---
title: 在基本移动性和安全性与Intune之间进行选择
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
description: 基本移动性和安全性是Microsoft 365计划的一部分。
ms.openlocfilehash: 36190be6345188503e7ba5147b72918a342aba73
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781174"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>选择“基本移动性和安全性”或“Intune

[Microsoft Intune](/mem/intune/)是某些Microsoft 365计划中包含的独立产品，而基本移动性和安全性是Microsoft 365计划的一部分。

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>基本移动性和安全性和Intune的可用性

基本移动性和安全性和Intune都包含在各种计划中，如下表所述。

| 计划 | 基本移动性和安全性 | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 应用版|是|否|
|Microsoft 365 商业基础版|是|否|
|Microsoft 365 商业标准版|是|否|
|Office 365 E1 |是|否|
|Office 365 E3 |是|否|
|Office 365 E5 |是|否|
|Microsoft 365 商业高级版 |是|是|
|Microsoft 365第一行 3 |是|是|
|Microsoft 365 企业版 E3 |是|是|
|Microsoft 365 企业版 E5 |是|是|
|Microsoft 365 教育版 A1 |是|是|
|Microsoft 365 教育版 A3 |是|是|
|Microsoft 365 教育版 A5 |是|是|
|Microsoft Intune |否|是|
|Enterprise移动性&安全 E3 |否|是|
|企业移动性 + 安全性 E5 |否|是|

> [!NOTE]
> 如果已在使用Microsoft Intune，则无法开始使用基本移动性和安全性。

 有关详细信息，请参阅[Microsoft 365和Office 365平台服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。

## <a name="differences-in-capabilities"></a>功能差异

Microsoft Intune和内置的基本移动性和安全性都使你能够管理组织中的移动设备，但在功能方面存在主要差异，如下表所述。

> [!NOTE]
> 可以先设置基本移动性和安全性，然后添加Microsoft Intune，从而在同一Microsoft 365 商业标准版组织中使用 *Intune和基本移动性和安全* 性来管理用户及其移动设备。 这样就可以选择基本的移动性和安全性或功能更丰富的Intune解决方案。 分配Intune许可证以启用Intune功能。

| 功能区域 | 功能突出显示 | 基本移动性和安全性 | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|设备类型|管理不同的 OS 平台和主要管理模式变体。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS、iPad OS|
|设备合规性|设置和管理安全策略，例如设备级别 PIN 锁定和越狱检测。 |Android 设备上的限制。 请参阅 [详细信息](capabilities.md)。 |是|
|基于设备符合性的条件访问 |防止不符合的设备从云访问公司电子邮件和数据。 |Windows 10不支持。<br/>仅限于控制对Exchange Online、SharePoint联机和Outlook的访问。 |是 |
|设备配置  |配置设备设置 (例如，禁用相机) |有限的设置集。|是|
|电子邮件配置文件  |在设备上预配本机电子邮件配置文件。 |是|是|
|WiFi 配置文件 |在设备上预配本机 WiFi 配置文件。 |否|是|
|VPN 配置文件 |在设备上预配本机 VPN 配置文件。 |否|是|
|移动应用管理  |将内部业务线应用和应用商店部署到用户。 |否|是|
|移动应用程序保护  |使用户能够使用他们认识的Office移动应用和业务线应用安全地访问公司信息，同时通过帮助限制复制、剪切、粘贴和另存为等操作来确保数据的安全性，仅限那些已为企业数据管理的应用。 即使设备未注册到基本移动性和安全性，也可正常工作。 请参阅使用 MAM 策略保护应用数据。 |否|是|
|托管浏览器  |使用 Edge 应用启用更安全的 Web 浏览。 |否|是|
|AutoPilot)  (零触控注册程序 |注册大量公司拥有的设备，同时简化用户设置。 |否|是|

除了上表中列出的功能外，基本移动性和安全性和Intune还包括一组远程操作，这些操作通过 Internet 将命令发送到设备。 例如，你可以在停用)  (保留个人数据的同时，从员工的设备中删除Office数据，从员工设备中删除Office应用 (擦除) ，或者将设备重置为其工厂设置 (完全擦除) 。

基本移动性和安全性远程操作包括停用、擦除和完全擦除。 有关基本移动性和安全性操作的详细信息，请参阅 [基本移动性和安全性功能](capabilities.md)。

使用Intune有以下一组操作：

- [Autopilot 重置](/mem/autopilot/windows-autopilot-reset)（仅限 Windows）
- [Bitlocker 密钥恢复](https://support.microsoft.com/windows/finding-your-bitlocker-recovery-key-in-windows-6b71ad27-0b89-ea08-f143-056f5ab347d6)仅 (Windows) 
- [使用擦除、停用或手动取消注册设备](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
- 仅) 禁用 iOS ([激活锁](/mem/intune/remote-actions/device-activation-lock-disable)
- [刚开始](/mem/intune/remote-actions/device-fresh-start) (Windows仅) 
- [完全扫描](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)（仅限 Windows 10）
- [查找设备](/mem/intune/remote-actions/device-locate)（仅限 iOS）
-  (iOS [的丢失模式](/mem/intune/remote-actions/device-lost-mode)仅) -[快速扫描](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) (Windows 10仅) 
- [适用于 Android 的远程控制](/mem/intune/remote-actions/teamviewer-support)
- [远程锁定](/mem/intune/remote-actions/device-remote-lock)
- [重命名设备](/mem/intune/remote-actions/device-rename)
- [仅重置密码](/mem/intune/remote-actions/device-passcode-reset)[重启](/mem/intune/remote-actions/device-restart) (Windows) 
- 仅[) 更新Windows Defender安全智能](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Windows
- [WINDOWS 10 PIN 重置](/windows/security/identity-protection/hello-for-business/hello-feature-pin-reset)仅 (Windows) 
-  (Android、iOS、iPad OS) [发送自定义通知](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)
- [同步设备](/mem/intune/remote-actions/device-sync)

有关Intune操作的详细信息，[请参阅Microsoft Intune文档](/mem/intune/)。
