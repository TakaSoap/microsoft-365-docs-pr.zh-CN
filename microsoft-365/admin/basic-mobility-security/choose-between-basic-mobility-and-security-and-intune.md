---
title: 在基本移动性和安全性和 Intune 之间进行选择
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本移动性和安全性是 Microsoft 365 计划的一部分。
ms.openlocfilehash: d4595428dd2e2b14948b9f788720fcadcf9eb895
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336761"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>在基本移动性和安全性和 Intune 之间进行选择

Microsoft Intune 是一种独立的产品，其中包含一些 Microsoft 365 计划，而基本移动性 & 安全性是 Microsoft 365 计划的一部分。 这两项都包含在各种计划中，如下表所述。

|**计划**|**基本移动性和安全性**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Microsoft 365 应用版|是|否|
|Microsoft 365 商业基础版|是|否|
|Microsoft 365 商业标准版|是|否|
|Office 365 E1 |是|否|
|Office 365 E3 |是|否|
|Office 365 E5 |是|否|
|Microsoft 365 商业高级版 |是|是|
|Microsoft 365 Firstline 3 |是|是|
|Microsoft 365 企业版 E3 |是|是|
|Microsoft 365 企业版 E5 |是|是|
|Microsoft 365 Eductation A1 |是|是|
|Microsoft 365 教育版 A3 |是|是|
|Microsoft 365 教育版 A5 |是|是|
|Microsoft Intune |否|是|
|企业移动性 & 安全 E3 |否|是|
|企业移动性 & 安全 E5 |否|是|

>[!NOTE]
>如果你已在使用 Microsoft Intune，则无法开始使用基本移动性和安全性。

## <a name="differences-in-capabilities"></a>功能方面的差异

Microsoft Intune 和内置基本移动性和安全性都使您能够管理组织中的移动设备，但功能方面的主要差异如下表所述。

>[!NOTE]
>通过首先设置基本移动性和安全性，然后添加 Microsoft Intune，可以在同一 Microsoft 365 业务标准组织中使用 Intune 和基本移动性和安全性管理用户及其移动设备。 这使您可以选择是使用基本移动性和安全性还是功能更丰富的 Intune 解决方案来管理用户的设备。 在模式中，许可证分配确定设备注册到的服务。 分配 Intune 许可证以启用仅 Intune 功能。

|**功能区**|**功能突出显示**|**基本移动性和安全性**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|设备类型|不同的操作系统平台和主要管理模式变体。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS<br/>iPad OS|
|设备合规性|设置和管理安全策略，如设备级 PIN 锁定和 jailbreak 检测。 |Android 9 及更高版本的设备上的限制。 有关详细信息，请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。|是|
|基于设备合规性的条件访问 |阻止不符合的设备访问来自云的公司电子邮件和数据。 |-在 Windows 10 上不受支持。<br/>-限制为控制对 Exchange Online、Sharepoint Online 和 Outlook 服务的访问。 |否|
|设备配置  |配置设备设置 (例如，禁用摄像头) 。 |一组有限的设置。有关详细信息，请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。 |是|
|远程操作  |通过 internet 将命令发送到设备。 例如，删除员工设备中的 Office 数据，同时保留个人数据 (停用) 。 |停用<br/>擦除<br/>删除|-Autopilot 仅)  (重置窗口<br/>- [Bitlocker 密钥轮替](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  仅 (Windows) <br/>- [删除](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [禁用激活 loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)  仅 (iOS) <br/>- [全新启动](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  仅 (Windows) <br/>- [完全扫描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  仅 (Windows 10) <br/>- [查找设备](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)  仅 (iOS) <br/>- [丢失模式](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  仅 (iOS) <br/>- 仅限 Windows 10 中的[快速扫描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) () <br/>- [适用于 Android 的远程控制](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [远程锁定](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [重命名设备](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [重置密码](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [重启](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)  仅 (Windows) <br/>- [注销](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>-仅更新 windows Defender 安全智能 (Windows) <br/>-Windows 10 PIN 重置 (仅限 Windows) <br/>- [擦](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [发送自定义通知](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android、iOS、iPad OS) <br/>- [同步设备](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|电子邮件配置文件  |在设备上设置本机电子邮件配置文件。 |是|是|
|WIFI 配置文件 |在设备上设置本机 WIFI 配置文件。 |否|是|
|VPN 配置文件 |在设备上设置本机 VPN 配置文件。 |否|是|
|MDM 应用程序管理  |将内部业务线应用程序和应用商店中的应用商店部署到用户。 |否|是|
|移动应用程序保护  |使用户能够使用他们知道的 Office mobile 和业务线应用程序来安全地访问公司信息，同时通过帮助限制复制、剪切、粘贴和另存为的操作（仅限于为公司数据审批的那些应用）来确保数据的安全性。 即使设备未注册到 MDM 也是有效的。 请参阅使用 MAM 策略保护应用数据。 |否|是|
|Managed browser  |使用边缘应用启用更安全的 web 浏览。 |否|是|
|零接触注册计划 |注册大量公司拥有的设备，同时简化用户设置。 |否|是|
