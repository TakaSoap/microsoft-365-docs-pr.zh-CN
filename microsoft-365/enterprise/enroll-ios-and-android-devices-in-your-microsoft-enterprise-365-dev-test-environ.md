---
title: 在 Microsoft 365 for 企业版测试环境中注册 iOS/iPadOS 和 Android 设备
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南在 Microsoft 365 测试环境中注册设备，并远程管理这些设备。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367079"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

本文介绍如何在 Microsoft 365 for 企业测试环境中注册和测试适用于 iOS/iPadOS 和 Android 设备的基本移动设备管理功能。

在测试环境中注册 iOS/iPadOS 和 Android 设备涉及三个阶段：
- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [第2阶段：注册 iOS/iPadOS 和 Android 设备](#phase-2-enroll-your-ios-and-android-devices)
- [第3阶段：远程管理 iOS/iPadOS 和 Android 设备](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果要以使用最低要求的轻型方式注册 iOS/iPadOS 和 Android 设备，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中注册 iOS/iPadOS 和 Android 设备，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它作为选项提供，以便您可以测试自动授权和组成员身份，并且可以在代表典型组织的环境中进行试验。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>第2阶段：注册 iOS 和 Android 设备

如果你正在考虑移动设备管理 (MDM) 解决方案来管理设备，则可以使用 Microsoft Intune。 在使用任何 MDM 提供程序（包括 Intune）时，设备都将 "注册"。 注册后，他们会收到您配置的功能和设置。 

在 Intune 中，有几种方法可以注册 iOS/iPadOS 和 Android 设备。 您可以选择最适合您的组织的注册选项。 有关详细信息和指导，请参阅以下文章：

- [部署指南：在 Microsoft Intune 中注册 iOS 和 iPadOS 设备](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [部署指南：在 Microsoft Intune 中注册 Android 设备](/mem/intune/fundamentals/deployment-guide-enrollment-android)

如果你已准备好使用 Intune 进行设备管理，并希望获得一些指导，以下信息可能会有所帮助：

- [设备管理概述](/mem/intune/fundamentals/what-is-device-management)
- [教程： Microsoft 终结点管理器中的演练 Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [部署指南：设置或移动到 Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>第3阶段：远程管理 iOS 和 Android 设备

Microsoft Intune 提供远程锁定和密码重置功能。 如果某人丢失了设备，则可以远程锁定设备。 如果有人忘记了密码，可以对其进行远程重置。

- 若要远程锁定 iOS/iPadOS 或 Android 设备，请参阅 [使用 Intune 远程锁定设备](/mem/intune/remote-actions/device-remote-lock)。
- 若要远程重置密码，请参阅 [在 Intune 中重置或删除设备密码](/mem/intune/remote-actions/device-passcode-reset)。

有关可远程运行的其他任务，请参阅 [可用的设备操作](/mem/intune/remote-actions/device-management#available-device-actions)。
    
## <a name="next-step"></a>后续步骤

在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)
  
[适用于 Microsoft 365 企业版测试环境的设备合规性策略](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 企业版概述](microsoft-365-overview.md)
