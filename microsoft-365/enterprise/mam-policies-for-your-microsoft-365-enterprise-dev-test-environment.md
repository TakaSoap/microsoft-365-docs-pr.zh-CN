---
title: 适用于 Microsoft 365 企业版测试环境的设备合规性策略
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境中。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367091"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于 Microsoft 365 企业版测试环境的设备合规性策略

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

本文介绍如何将适用于企业的 Windows 10 设备和 Microsoft 365 应用程序的 Intune 设备合规性策略添加到 Microsoft 365 for 企业测试环境。

添加 Intune 设备合规性策略涉及两个阶段：
- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [第2阶段：为 Windows 10 设备创建设备合规性策略](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果您想要仅使用最低要求以轻量方式配置 MAM 策略，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置 MAM 策略，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它作为选项提供，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>第2阶段：为 Windows 10 设备创建设备合规性策略

在此阶段中，将为 Windows 10 设备创建设备合规性策略。 此阶段使用 Microsoft Intune 和 [Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 添加组，并创建合规性策略。

1. 转到 [microsoft 365 管理中心](https://admin.microsoft.com)，并使用全局管理员帐户登录到你的 microsoft 365 测试实验室订阅。 选择 " **终结点管理器** " 管理中心。 [终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)将打开。

    如果未 **启用 "设备管理尚未启用** " 的邮件，则选择 "Intune" 作为 MDM 颁发机构。 有关具体步骤，请参阅 [设置移动设备管理机构](/mem/intune/fundamentals/mdm-authority-set)。

    终结点管理器管理中心侧重于设备管理和应用管理。 有关此管理中心的教程，请参阅 [教程：演练 Intune In Microsoft 终结点管理器](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。

2. 在 **"组**" 中，添加一个名为 "**托管 Windows 10 设备用户**" 的新 **Microsoft 365** 或 **安全** 组，其中包含 **已分配** 的成员身份类型。 在接下来的步骤中，你将向此组分配合规性策略。 

    有关具体步骤，以及有关 **Microsoft 365** 或 **安全** 组的信息，请参阅 [添加组以组织用户和设备](/mem/intune/fundamentals/groups-add)。

3. 在 " **设备**" 中，创建 Windows 10 合规性策略。 将此策略分配给您创建的 **托管 Windows 10 设备用户** 组。

    在策略中，您可以阻止简单密码、需要防火墙、需要运行 Microsoft Defender 反恶意软件服务，等等。 合规性策略通常包括基本设置或每个设备应具有的最低基本设置。

    有关具体步骤，以及可以配置的可用合规性设置的信息，请参阅 [使用合规性策略设置管理的设备的规则](/mem/intune/protect/device-compliance-get-started)。

完成后，你将拥有设备合规性策略，用于测试 **托管 Windows 10 设备用户** 组中的成员。
  
## <a name="next-step"></a>后续步骤

在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。

## <a name="see-also"></a>另请参阅

[适用于企业测试实验室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 企业版概述](microsoft-365-overview.md)

[企业移动性 + 安全性 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
