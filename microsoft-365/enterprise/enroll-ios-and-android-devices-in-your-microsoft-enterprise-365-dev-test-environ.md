---
title: 在适用于企业测试环境的 Microsoft 365 注册 iOS/iPadOS 和 Android 设备
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南在测试环境中注册Microsoft 365并远程管理设备。
ms.openlocfilehash: 7610348febcc8c2054c50d7f7a6f1433e9b62306
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189113"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>在适用于企业测试Microsoft 365注册 iOS 和 Android 设备

*本测试实验室指南只能用于Microsoft 365测试环境。*

本文介绍如何在适用于企业测试环境的 Microsoft 365 注册和测试 iOS/iPadOS 和 Android 设备的基本移动设备管理功能。

在测试环境中注册 iOS/iPadOS 和 Android 设备涉及三个阶段：
- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：注册 iOS/iPadOS 和 Android 设备](#phase-2-enroll-your-ios-and-android-devices)
- [第 3 阶段：远程管理 iOS/iPadOS 和 Android 设备](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你想要按照最低要求以轻型方式注册 iOS/iPadOS 和 Android 设备，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中注册 iOS/iPadOS 和 Android 设备，请按照传递 [身份验证 中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并且可以在代表典型组织的环境中试验它。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>阶段 2：注册 iOS 和 Android 设备

如果你正在考虑使用移动设备管理 (MDM) 解决方案来管理设备，可以使用Microsoft Intune。 使用任意 MDM 提供程序（包括 Intune）时，设备将"注册"。 注册后，他们将收到你配置的功能和设置。 

在 Intune 中，有一些注册 iOS/iPadOS 和 Android 设备的方法。 你可以选择最适合你的组织的注册选项。 有关详细信息和指导，请参阅以下文章：

- [部署指南：在部署中注册 iOS 和 iPadOS Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [部署指南：在 Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

如果你已准备好使用 Intune 进行设备管理，并且需要一些指南，则以下信息可能会有所帮助：

- [设备管理概述](/mem/intune/fundamentals/what-is-device-management)
- [教程：Microsoft Endpoint Manager 中的 Intune 演练](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [部署指南：安装或移动到Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>第 3 阶段：远程管理 iOS 和 Android 设备

Microsoft Intune远程锁定和密码重置功能。 如果有人丢失了设备，你可以远程锁定设备。 如果有人忘记了自己的密码，可以远程重置密码。

- 若要远程锁定 iOS/iPadOS 或 Android 设备，请参阅使用 [Intune 远程锁定设备](/mem/intune/remote-actions/device-remote-lock)。
- 若要远程重置密码，请参阅在 [Intune 中重置或删除设备密码](/mem/intune/remote-actions/device-passcode-reset)。

有关你可以远程运行的其他任务，请参阅 [可用的设备操作](/mem/intune/remote-actions/device-management#available-device-actions)。
    
## <a name="next-step"></a>后续步骤

探索 [测试环境中](m365-enterprise-test-lab-guides.md#mobile-device-management) 的其他移动设备管理功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)
  
[适用于企业测试Microsoft 365的设备合规性策略](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 企业版概述](microsoft-365-overview.md)
