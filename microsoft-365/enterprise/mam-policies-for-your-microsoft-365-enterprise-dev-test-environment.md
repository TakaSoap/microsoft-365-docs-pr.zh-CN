---
title: 适用于企业测试Microsoft 365的设备合规性策略
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略Microsoft 365企业测试环境。
ms.openlocfilehash: ec73211a21e9e064b729b93d9e88b7c5c69b21fe
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150806"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于企业测试Microsoft 365的设备合规性策略

*本测试实验室指南只能用于Microsoft 365测试环境。*

本文介绍如何向企业测试环境添加适用于Windows 10和Microsoft 365 企业应用版的 Intune Microsoft 365合规性策略。

添加 Intune 设备合规性策略涉及两个阶段：
- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：为设备创建Windows 10策略](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你希望仅采用满足最低要求的轻型方式配置 MAM 策略，请按照轻型基本配置 [中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中配置 MAM 策略，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>阶段 2：为设备创建Windows 10策略

在此阶段中，你将为设备创建Windows 10策略。 此阶段Microsoft Intune和Microsoft Endpoint Manager管理中心添加[](https://go.microsoft.com/fwlink/?linkid=2109431)组，并创建合规性策略。

1. 转到["Microsoft 365 管理中心"，](https://admin.microsoft.com)使用全局管理员帐户Microsoft 365你的测试实验室订阅，然后选择"Endpoint Manager<a href="https://go.microsoft.com/fwlink/?linkid=2109431" target="_blank">中心"。</a>

    如果显示类似于 **你尚未启用设备** 管理的消息，则选择 Intune 作为 MDM 颁发机构。 有关具体步骤，请参阅 [设置移动设备管理机构](/mem/intune/fundamentals/mdm-authority-set)。

    管理Endpoint Manager中心侧重于设备管理和应用管理。 有关此管理中心的教程，请参阅[教程：Microsoft Endpoint Manager 中的演练 Intune。](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. 在 **"组**"中，Microsoft 365"已分配成员身份"类型的名为 **"** 托管Windows 10组或"安全"组。  在以下步骤中，将合规性策略分配给该组。 

    有关特定步骤，以及 **有关Microsoft 365****组** 的信息，请参阅添加 [组以组织用户和设备](/mem/intune/fundamentals/groups-add)。

3. 在 **"设备"** 中，创建Windows 10合规性策略。 将此策略分配给Windows 10 **托管设备** 用户组。

    在你的策略中，可以阻止简单密码、需要防火墙、要求运行 Microsoft Defender 反恶意软件服务等。 合规性策略通常包括基本设置，或每个设备应具有的最低设置。

    有关特定步骤以及可配置的可用合规性设置的信息，请参阅使用合规性策略为管理的设备 [设置规则](/mem/intune/protect/device-compliance-get-started)。

完成后，你有一个设备合规性策略，用于测试托管Windows 10 **用户组** 的成员。
  
## <a name="next-step"></a>后续步骤

探索 [测试环境中](m365-enterprise-test-lab-guides.md#mobile-device-management) 的其他移动设备管理功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365测试实验室指南](m365-enterprise-test-lab-guides.md)。
  
[在适用于企业测试Microsoft 365注册 iOS 和 Android 设备](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 企业版概述](microsoft-365-overview.md)

[企业移动性 + 安全性 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
