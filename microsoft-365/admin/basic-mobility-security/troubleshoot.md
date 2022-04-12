---
title: 基本移动性和安全性疑难解答
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 尝试执行以下步骤来跟踪基本的移动性和安全问题
ms.openlocfilehash: c8c4fe674ff3a803659223a004e304a5779a83d7
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780712"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>基本移动性和安全性疑难解答

如果尝试在基本移动性和安全性中注册设备时遇到问题，请尝试此处的步骤来跟踪问题。 如果常规步骤未解决此问题，请参阅后面的一个部分，其中包含设备类型的特定步骤。

## <a name="steps-to-try-first"></a>首先尝试的步骤

若要开始，请检查以下内容：

- 请确保设备尚未注册到另一个移动设备管理提供商，例如Intune。

- 确保设备设置为正确的日期和时间。

- 切换到设备上其他 WIFI 或手机网络。

- 对于 Android 或 iOS 设备，请卸载并重新安装设备上的Intune 公司门户应用。 

## <a name="ios-phone-or-tablet"></a>iOS 手机或平板电脑

- 确保已设置 APN 证书。 有关详细信息，请参阅 [为 iOS 设备创建 APN 证书](create-an-apns-certificate-for-ios-devices.md)。

- 在 **设置** > **GeneralProfile** >  **(或设备管理)** 中，确保尚未安装管理配置文件。 如果是，请将其删除。

- 如果看到错误消息“设备无法注册”，请登录Microsoft 365并确保已将包含Exchange Online的许可证分配给已登录到设备的用户。

- 如果看到错误消息“配置文件安装失败”，请尝试以下操作之一：

    - 确保 Safari 是设备上的默认浏览器，并且未禁用 Cookie。

    - 重新启动设备，然后导航到 portal.manage.microsoft.com。 使用Microsoft 365用户 ID 和密码登录，并尝试手动安装配置文件。

## <a name="windows-rt"></a>Windows RT

- 确保在Microsoft 365中设置域以使用基本移动性和安全性。 有关详细信息，请参阅 [“设置基本移动性和安全性](set-up.md)”。
    
- 请确保用户选择“ **打开** ”，而不是选择 **“加入**”。

## <a name="windows-10-pc"></a>Windows 10电脑

- 确保在Microsoft 365中设置域以使用基本移动性和安全性。 有关详细信息，请参阅 [“设置基本移动性和安全性](set-up.md)”。
    
- 除非已Azure Active Directory Premium，否则请确保用户 **仅选择设备管理注册**，而不是选择 **连接**。

## <a name="android-phone-or-tablet"></a>Android 手机或平板电脑

- 确保设备正在运行 Android。

- 确保 Chrome 是最新的，并设置为默认浏览器。

- 如果看到错误消息“我们无法注册此设备”，请登录Microsoft 365并确保已将包含Exchange Online的许可证分配给已登录到设备的用户。

- 检查设备上的通知区域，查看是否正在挂起任何所需的最终用户操作，以及是否已完成操作。