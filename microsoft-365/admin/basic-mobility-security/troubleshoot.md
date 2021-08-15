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
description: 尝试以下步骤以跟踪基本移动性和安全性问题
ms.openlocfilehash: 1ba964f052169b3937ecbc086abd4a686c0a66bb959c4b38d4280c1bbb0225a2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826707"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>基本移动性和安全性疑难解答

如果在尝试在基本移动性和安全性中注册设备时出现问题，请尝试此处的步骤以跟踪该问题。 如果常规步骤无法解决此问题，请参阅以下部分之一，其中提供设备类型的特定步骤。

## <a name="steps-to-try-first"></a>首先尝试的步骤

若要开始，请检查以下内容：

- 确保设备尚未向另一个移动设备管理提供程序（如 Intune）注册。

- 确保设备已设置为正确的日期和时间。

- 在设备上切换到其他 WIFI 或手机网络。

- 对于 Android 或 iOS 设备，卸载并重新安装Intune 公司门户应用。 

## <a name="ios-phone-or-tablet"></a>iOS 手机或平板电脑

- 请确保你已设置 APNs 证书。 有关详细信息，请参阅为 [iOS 设备创建 APNs 证书](create-an-apns-certificate-for-ios-devices.md)。

- 在 **设置**   >  **配置文件 (**   >  **或设备管理)** 中，确保尚未安装管理配置文件。 如果是，请将其删除。

- 如果看到错误消息"设备注册失败"，请登录到 Microsoft 365并确保已向登录到设备的用户分配了包含 Exchange Online 的许可证。

- 如果看到错误消息"配置文件安装失败"，请尝试以下操作之一：

    - 确保 Safari 是设备上的默认浏览器，并且未禁用 Cookie。

    - 重新启动设备，然后导航到 portal.manage.microsoft.com。 使用你的 Microsoft 365 ID 和密码登录，并尝试手动安装配置文件。

## <a name="windows-rt"></a>Windows RT

- 请确保域已设置为Microsoft 365基本移动性和安全性。 有关详细信息，请参阅设置 [基本移动性和安全性](set-up.md)。
    
- 确保用户选择"打开 **"，**   而不是选择"加入 **"。**

## <a name="windows-10-pc"></a>Windows 10电脑

- 请确保域已设置为Microsoft 365基本移动性和安全性。 有关详细信息，请参阅设置 [基本移动性和安全性](set-up.md)。
    
- 除非你已Azure Active Directory Premium，否则请确保用户选择仅在设备管理中注册 ****   ，而不是选择连接。 ****

## <a name="android-phone-or-tablet"></a>Android 手机或平板电脑

- 确保设备运行的是 Android 4.4 或更高版本。

- 确保 Chrome 是最新的，并设置为默认浏览器。

- 如果看到错误消息"我们无法注册此设备"，请登录到 Microsoft 365并确保已向登录到设备的用户分配了包含 Exchange Online 的许可证。

- 检查设备上的通知区域，以查看任何所需的最终用户操作是否挂起，如果是，则完成这些操作。