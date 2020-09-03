---
title: 基本移动性和安全性疑难解答
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 请尝试执行以下步骤来跟踪基本移动性和安全问题
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336746"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>基本移动性和安全性疑难解答

如果您在尝试以基本移动性和安全性注册设备时遇到问题，请尝试此处的步骤来跟踪问题。 如果常规步骤不能解决问题，请参阅后面的部分，其中包含针对你的设备类型的特定步骤。

## <a name="steps-to-try-first"></a>首先尝试的步骤

若要开始，请检查以下各项：

- 确保设备尚未使用其他移动设备管理提供程序（如 Intune）进行注册。
    
- 请确保该设备已设置为正确的日期和时间。
    
- 切换到设备上的不同 WIFI 或蜂窝网络。
    
- 对于 Android 或 iOS 设备，请在设备上卸载并重新安装 Intune 公司门户应用。 

## <a name="ios-phone-or-tablet"></a>iOS 电话或平板电脑

- 请确保已设置 APNs 证书。 有关详细信息，请参阅 [Create a APNs Certificate For iOS 设备](create-an-apns-certificate-for-ios-devices.md)。
    
- 在 " **设置**   >  **常规**   >  **配置文件 (" 或 "设备管理) **" 中，确保尚未安装管理配置文件。 如果是，请将其删除。
    
- 如果您看到错误消息 "设备未能注册"，请登录 Microsoft 365，并确保已将包含 Exchange Online 的许可证分配给登录到该设备的用户。
    
- 如果您看到错误消息 "配置文件无法安装"，请尝试以下操作之一：
    
    - 请确保 Safari 是设备上的默认浏览器，并且未禁用该 cookie。
    
    - 重新启动设备，然后导航到 portal.manage.microsoft.com。 使用 Microsoft 365 用户 ID 和密码登录，并尝试手动安装配置文件。    

## <a name="windows-rt"></a>Windows RT

- 确保您的域已在 Microsoft 365 中设置为使用基本移动性和安全性。 有关详细信息，请参阅 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)。
    
- 确保用户选择 " **打开"**，   而不是选择 " **加入**"。    

## <a name="windows-10-pc"></a>Windows 10 电脑

- 确保您的域已在 Microsoft 365 中设置为使用基本移动性和安全性。 有关详细信息，请参阅 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)。
    
- 除非您拥有 Azure Active Directory Premium，否则请确保用户 **只选择 "在设备管理中注册"**，   而不是选择 " **连接**"。

## <a name="android-phone-or-tablet"></a>Android 手机或平板电脑

- 请确保设备运行的是 Android 4.4 或更高版本。
    
- 请确保 Chrome 是最新的，并且设置为默认浏览器。
    
- 如果您看到错误消息 "我们无法注册此设备"，请登录 Microsoft 365，并确保已将包含 Exchange Online 的许可证分配给登录到该设备的用户。
    
- 检查设备上的通知区域以查看是否有任何必需的最终用户操作挂起，如果是，则完成操作。