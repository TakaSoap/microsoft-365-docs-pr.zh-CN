---
title: 设备的 Microsoft 365 企业版的合规性策略测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南添加到 Microsoft 365 企业版 Intune 设备合规性策略测试环境。
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866028"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>设备的 Microsoft 365 企业版的合规性策略测试环境

使用本文中的说明，Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要配置的最低硬件要求与轻型方式 MAM 策略，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要配置 MAM 策略模拟企业中，按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>阶段 2： 创建 Windows 10 设备的设备合规性策略

在此阶段中，您将创建 Windows 10 设备的设备合规性策略。
  
1. 转到 Office 门户: ([https://office.com](https://office.com)) 和 Office 365 试用版订阅与全局管理员帐户登录。
    
2. 在浏览器的新建选项卡上，打开 Azure 门户： [https://portal.azure.com](https://portal.azure.com)。

3. 在浏览器中，在导航窗格中，Azure 门户选项卡上单击**所有服务**，键入**Intune**，，然后都单击**Intune**。
    
4. 如果您看到**尚未启用尚未设备管理**消息**Microsoft Intune**刀片上，单击该选项。在**移动设备管理证书颁发机构**刀片中，单击**Intune MDM 证书颁发机构**，，然后单击**选择**。刷新您浏览器的选项卡。
    
5. 在左侧导航窗格中，单击“组”****。
    
6. 在**组所有组**刀片中，单击 **+ 新建组**。
    
7. 在**组**刀片中，选择**Office 365** **组类型？**，请在**名称**框中，键入**托管 Windows 10 设备用户**在**成员资格类型**，选择**已分配**，然后单击**创建**。 
    
8. 关闭**组**刀片。
    
11. 关闭**组所有组**刀片。
    
12. 在**Microsoft Intune**刀片，在**快速的任务**列表中，单击**创建合规性策略**。
    
13. 在**合规性策略配置文件**刀片中，单击**创建策略**。
    
14. 在**创建策略**刀片，在**名称**框中，键入**Windows 10**。**平台**中, 选择**10 及更高版本的 Windows**，在**Windows 10 合规性策略**刀片中，单击**确定**，然后单击**创建**。关闭**Windows 10**刀片。
    
15. 在**合规性策略配置文件**刀片中，单击**Windows 10**策略名称。
    
16. 在**Windows 10**刀片中，单击**分配**，，然后单击**选择要包括的组**。
    
17. **选择要包括的组**刀片上, 单击**托管 Windows 10 设备用户**组中，，然后单击**选择**。
    
18. 单击**保存**，然后关闭**Windows 10-分配**刀片。
    
19. 关闭**合规性策略配置文件**刀片。
    
20. 在**Microsoft Intune**刀片中，单击左侧导航窗格中**客户端应用程序**。
    
21. 在**客户端应用程序**刀片中，单击**应用程序**，，然后单击**添加**。 

22. 在**添加应用程序**刀片中，选择**应用程序类型**，，然后选择**Office 365 套件**下**Windows 10** 。

23. **配置应用程序套件**，请单击，然后单击**确定**。

24. 单击**应用程序套件信息**、 键入**套件名称**，在**套件说明**框中， **Office 应用程序的 Windows 10** **Office 应用程序的 Windows 10** ，然后单击**确定**。

25. 单击**应用程序套件设置**，在**更新通道**中，选择**半年**，然后单击**确定**。

26. 在**添加应用程序**刀片中，单击**添加**。

现在，您具有设备合规性策略测试**Windows 10**设备合规性策略中选定的应用程序和**托管 Windows 10 设备用户**组的成员。 
  
## <a name="next-step"></a>后续步骤

浏览您的测试环境中其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 Enterprise 测试实验室指南](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[企业移动 + 安全 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
