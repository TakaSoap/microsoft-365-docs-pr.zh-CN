---
title: 在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南在 Microsoft 365 测试环境中注册设备，并远程管理这些设备。
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487692"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

本文介绍了如何为 Microsoft 365 企业版测试环境中的 iOS 和 Android 设备注册和测试基本移动设备管理功能。

在测试环境中注册 iOS 和 Android 设备涉及三个阶段：
- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [第2阶段：注册 iOS 和 Android 设备](#phase-2-enroll-your-ios-and-android-devices)
- [第3阶段：远程管理 iOS 和 Android 设备](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果要使用最低要求以轻型方式注册 iOS 和 Android 设备，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟企业版中注册 iOS 和 Android 设备，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它作为选项提供，以便您可以测试自动授权和组成员身份，并且可以在代表典型组织的环境中进行试验。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>第2阶段：注册 iOS 和 Android 设备

首先，按照 [安装和登录到公司门户应用](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 中的说明，为您的测试环境自定义 Microsoft Intune 公司门户应用程序。

接下来，按照设置对 [贵公司资源的访问权限](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 注册 iOS 设备中的说明进行操作。

接下来，使用在 [Intune 中注册 android 设备](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 注册 android 设备中的说明。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>第3阶段：远程管理 iOS 和 Android 设备

Microsoft Intune 提供远程锁定和密码重置两种功能。 如果某人丢失了设备，则可以远程锁定设备。 如果有人忘记了密码，可以对其进行远程重置。
  
若要远程锁定 iOS 或 Android 设备，请执行以下操作：

1. [https://portal.azure.com](https://portal.azure.com)使用全局管理员帐户的凭据登录到 Azure 门户。
2. 在 Azure 门户中，在搜索框中输入 **intune** ，然后选择 **intune**。
3. 单击 " **设备 > 所有设备**"。
4. 在设备列表中，选择一个 iOS 或 Android 设备，然后选择 **远程锁定** 操作。
    
若要远程重置密码，请执行以下操作：

1. 如果需要，请 [https://portal.azure.com](https://portal.azure.com) 使用全局管理员帐户的凭据登录到 Azure 门户。
2. 在 Azure 门户中，在搜索框中输入 **intune** ，然后选择 **intune**。
3. 选择 "**设备**  >  **所有设备**"。
4. 从所管理的设备列表中，选择 iOS 或 Android 设备，选择 " **..."详细信息**，然后选择 " **删除密码** 设备远程操作"。

有关其他实验，请参阅 [可用设备操作](https://docs.microsoft.com/intune/device-management#available-device-actions)。
    
## <a name="next-step"></a>后续步骤

在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)
  
[适用于 Microsoft 365 企业版测试环境的设备合规性策略](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 企业版概述](microsoft-365-overview.md)
