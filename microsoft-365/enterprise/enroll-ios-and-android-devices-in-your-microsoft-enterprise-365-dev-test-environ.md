---
title: 在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南注册 Microsoft 365 测试环境中的设备和远程管理它们。
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865536"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备

按照本文中提供的说明进行操作，您将能够注册和 Microsoft 365 企业版测试环境中测试用于 iOS 和 Android 设备的基本的移动设备管理功能。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要注册的最低硬件要求与轻型方式的 iOS 和 Android 设备，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要注册 iOS 和 Android 设备模拟企业中的，按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>阶段 2： 注册您的 iOS 和 Android 设备

首先，使用中的说明[安装和登录到的公司门户应用程序](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)自定义 Microsoft Intune 的公司门户应用程序的测试环境。

注册 iOS 设备，接下来，使用[设置访问公司资源](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)中的说明。

注册 Android 设备，接下来，使用[注册中 Intune Android 设备](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)中的说明。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>第 3 阶段： 远程管理您的 iOS 和 Android 设备

Microsoft Intune 提供远程锁定和密码重置功能。如果某人丢失其设备，您可以远程锁定设备。如果某人忘记其密码，您可以重置密码远程。
  
远程锁定 iOS 或 Android 设备：

1. 登录到 Azure 门户在[https://portal.azure.com](https://portal.azure.com)的全局管理员帐户凭据。
2. 单击**所有服务**，键入**Intune**，，然后都单击**Intune**。
3. 单击**设备 > 所有设备**。
4. 在设备的列表中，单击 iOS 或 Android 设备，然后单击**远程锁定**操作。

    
远程重置密码：

1. 如果需要登录到 Azure 门户在[https://portal.azure.com](https://portal.azure.com)的全局管理员帐户凭据。
2. 单击**所有服务**，键入**Intune**，，然后都单击**Intune**。
3. 单击**设备 > 所有设备**。
4. 从设备列表中，您将管理、 单击 iOS 或 Android 设备，并选择 **...更多**。然后选择**删除密码**设备远程操作。

有关其他实验，请参阅[可用设备操作](https://docs.microsoft.com/intune/device-management#available-device-actions)。

    
## <a name="next-step"></a>后续步骤

浏览您的测试环境中其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)
  
[用于 Microsoft 365 企业版测试环境的 MAM 策略](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[企业移动 + 安全 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
