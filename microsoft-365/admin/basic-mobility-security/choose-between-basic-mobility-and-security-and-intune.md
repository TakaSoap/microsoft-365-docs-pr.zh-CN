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
ms.openlocfilehash: b9568d0aad03fc3c8a5c81d02f98f5b238124a82
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930161"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>在基本移动性和安全性或 Intune 之间进行选择

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) 是特定 microsoft 365 计划附带的独立产品，而基本移动和安全是 microsoft 365 计划的一部分。 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>基本移动性和安全性和 Intune 的可用性
 
基本移动性和安全性和 Intune 都包含在各种计划中，如下表所述。

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
|Microsoft 365 教育版 A1 |是|是|
|Microsoft 365 教育版 A3 |是|是|
|Microsoft 365 教育版 A5 |是|是|
|Microsoft Intune |否|是|
|企业移动性 & 安全 E3 |否|是|
|企业移动性 & 安全 E5 |否|是|

>[!NOTE]
>如果你已在使用 Microsoft Intune，则无法开始使用基本移动性和安全性。

 有关详细信息，请参阅 [Microsoft 365 和 Office 365 platform 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 

## <a name="differences-in-capabilities"></a>功能方面的差异

Microsoft Intune 和内置基本移动性和安全性都使您能够管理组织中的移动设备，但功能方面的主要差异如下表所述。

>[!NOTE]
>*通过首先设置基本移动性和安全性，然后添加 Microsoft Intune，* 可以在同一 Microsoft 365 业务标准组织中使用 Intune 和基本移动性和安全性管理用户及其移动设备。 这使您可以选择基本移动性和安全性或功能更丰富的 Intune 解决方案。 分配 Intune 许可证以启用 Intune 功能。

|**功能区**|**功能突出显示**|**基本移动性和安全性**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|设备类型|管理不同的操作系统平台和主要管理模式变体。 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS，iPad OS|
|设备合规性|设置和管理安全策略，如设备级 PIN 锁定和 jailbreak 检测。 |Android 9 及更高版本的设备上的限制。 请参阅 [详细信息](capabilities.md)。 |是|
|基于设备合规性的条件访问 |阻止不符合的设备访问来自云的公司电子邮件和数据。 |在 Windows 10 上不受支持。<br/>限制为控制对 Exchange Online、SharePoint Online 和 Outlook 的访问。 |否 |
|设备配置  |配置设备设置 (例如，禁用摄像头) |设备合规性|设置和管理安全策略，如设备级 PIN 锁定和 jailbreak 检测。 |Android 9 及更高版本的设备上的限制。 请参阅 [详细信息](capabilities.md)。 |是|
 |一组有限的设置。 |是|
|电子邮件配置文件  |在设备上设置本机电子邮件配置文件。 |是|是|
|WiFi 配置文件 |在设备上设置本机 WiFi 配置文件。 |否|是|
|VPN 配置文件 |在设备上设置本机 VPN 配置文件。 |否|是|
|MDM 应用程序管理 |将内部业务线应用程序和应用商店中的应用商店部署到用户。 |否|是|
|MAM |确保您的用户可以使用 Office mobile 和业务线应用程序安全地访问公司信息，方法是将操作限制为复制、剪切、粘贴和另存为，仅对那些已针对企业数据进行了审批的应用程序进行限制。 |否|是|
|Managed browser  |使用边缘应用启用更安全的 web 浏览。 |否|是|
|零接触注册计划 Autopilot)  |注册大量公司拥有的设备，同时简化用户设置。 |否|是|
|||

除了上表中列出的功能外，基本移动性和安全性和 Intune 都包括一组通过 internet 向设备发送命令的远程操作。 例如，您可以从员工的设备中删除 Office 数据，同时保留个人数据 (报废) 、从员工设备删除 Office 应用程序 (擦除) ，或将设备重置为其出厂设置 (完全擦除) 。 

基本移动性和安全性远程操作包括撤出、擦除和完全擦除。 有关基本移动性和安全操作的详细信息，请参阅 [基本移动性和安全性的功能](capabilities.md)。

使用 Intune 可以执行以下一组操作：

-   仅限 Autopilot 重置 (窗口
-  [Bitlocker 密钥轮替](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)  仅 (Windows) 
-  [使用擦除、停用或手动 unenrolling 设备](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [禁用激活 loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)  仅 (iOS) 
-  [全新启动](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)  仅 (Windows) 
- [完全扫描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)  仅 (Windows 10) 
- [查找设备](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)  仅 (iOS) 
- [丢失模式](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)  仅 (iOS) -[快速扫描](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus) (仅限 Windows 10) 
- [适用于 Android 的远程控制](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [远程锁定](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [重命名设备](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  仅 (Windows[重置密码](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)重[启](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)  ) 
-  仅将 Windows Defender 安全智能更新 (Windows) 
-  仅 windows 10 PIN 重置 (Windows) 
-  [发送自定义通知](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android、iOS、iPad OS) 
-  [同步设备](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

有关 Intune 操作的详细信息，请参阅 [Microsoft Intune 文档](https://docs.microsoft.com/mem/intune/)。