---
title: 适用于 Microsoft 365 企业版测试环境的设备合规性策略
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境中。
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487408"
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

在此阶段，为 Windows 10 设备创建设备合规性策略。
  
1. 转到 [microsoft 365 管理中心](https://admin.microsoft.com) ，并使用全局管理员帐户登录 microsoft 365 测试实验室订阅。
1. 在浏览器的新选项卡上，在上打开 Azure 门户 [https://portal.azure.com](https://portal.azure.com) 。
1. 在 Azure 门户的搜索框中，输入 **intune**，然后选择 **intune**。
1. 如果您在 " **Microsoft Intune** " 窗格中看到 "**尚未启用设备管理**" 消息，请选择它。 在 " **移动设备管理机构** " 窗格中，选择 " **Intune MDM 颁发机构**"，然后选择 " **选择**"。
1. 刷新浏览器选项卡。
1. 在左侧导航窗格中，选择 " **组**"。
1. 在 " **组-所有组** " 窗格中，选择 " **+ 新建组**"。
1. 在**组**窗格中，选择 **"组类型**的**Microsoft 365** " 或 "**安全**"，在 "**名称**" 中输入**托管 Windows 10 设备用户**，在 "**成员身份类型**" 中选择 "**已分配**"，然后选择 "**创建**"
1. 选择 " **Microsoft Intune**"。
1. 在 " **Microsoft Intune** " 窗格中的 " **快速任务** " 列表中，选择 " **创建合规性策略**"。
1. 在 " **合规性策略配置文件** " 窗格中，选择 " **创建策略**"。
1. 在 " **创建策略** " 窗格中的 " **名称**" 中，输入 **Windows 10**。 在 "**平台**" 中，选择 " **windows 10 及更高版本**"，在**Windows 10 合规性策略**窗格中选择 **"确定"** ，然后选择 "**创建**"。
1. 选择 " **合规性策略配置文件**"，然后选择 **Windows 10** 策略名称。
1. 在 " **Windows 10** " 窗格中，选择 " **分配**"，然后选择 " **选择要包含的组**"。
1. 在 " **选择要包含的组** " 窗格中，选择 " **托管 Windows 10 设备用户** " 组，然后选择 " **选择**"。
1. 选择 " **保存**"，选择 " **Microsoft Intune-概述**"，然后在左侧导航中选择 " **客户端应用** "。
1. 在 " **客户端应用** " 窗格中，选择 " **应用**"，然后选择 " **添加**"。
1. 在 "**添加应用程序**" 窗格中，选择 "**应用程序类型**"，然后选择 " **Microsoft 365 套件**下的**Windows 10** "。
1. 在 " **添加应用程序** " 窗格中，选择 " **应用程序套件信息**"。
1. 在 "**应用套件信息**" 窗格中，在 "**套件名称**" 和 "**套件说明**" 中输入 "**适用于企业的 Microsoft 365 应用**"，然后选择 **"确定"**。
1. 在 " **添加应用程序** " 窗格中，选择 " **配置应用程序套件**"，然后选择 **"确定"**。
1. 在 " **添加应用程序** " 窗格中，选择 " **应用程序套件设置**"。
1. 对于 " **更新频道**"，选择 " **半年企业**"，然后选择 **"确定"**。
1. 在 " **添加应用程序** " 窗格中，选择 " **添加**"。

现在，你已拥有设备合规性策略，用于测试 **Windows 10** 设备合规性策略中的所选应用和 **托管 windows 10 设备用户** 组的成员。 请注意，如果选择 **Microsoft 365** 作为组类型，则会创建其他资源。
  
## <a name="next-step"></a>后续步骤

在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。

## <a name="see-also"></a>另请参阅

[适用于企业测试实验室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 企业版概述](microsoft-365-overview.md)

[企业移动性 + 安全性 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
