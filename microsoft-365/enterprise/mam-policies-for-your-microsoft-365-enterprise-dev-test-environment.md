---
title: 适用于 Microsoft 365 企业版测试环境的设备合规性策略
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境中。
ms.openlocfilehash: d20b050bfc56776656bf1d485b2e107a9debe2f7
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353184"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>适用于 Microsoft 365 企业版测试环境的设备合规性策略

使用本文中的说明, 可以向 Microsoft 365 企业版测试环境中添加 Intune 设备合规性策略。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第1阶段: 构建 Microsoft 365 企业版测试环境

如果只想使用最低要求以轻型方式配置 MAM 策略, 请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置 MAM 策略, 请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟企业测试环境, 其中包括连接到 Internet 的模拟 intranet 和 Active directory 域服务 (AD DS) 林的目录同步。 此处提供了此选项, 以便您可以测试自动授权和组成员身份, 并在代表典型组织的环境中进行试验。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>第2阶段: 为 Windows 10 设备创建设备合规性策略

在此阶段中, 将为 Windows 10 设备创建设备合规性策略。
  
1. 转到 office 365 门户 ([https://portal.office.com](https://portal.office.com)), 并使用全局管理员帐户登录到你的 office 365 测试实验室订阅。
    
2. 在浏览器的新选项卡上, 在上打开 Azure [https://portal.azure.com](https://portal.azure.com)门户。

3. 在浏览器中的 "Azure 门户" 选项卡上, 在导航窗格中, 单击 "**所有服务**", 键入**Intune**, 然后单击 " **intune**"。
    
4. 如果您在**Microsoft Intune**边栏上发现**尚未启用 "设备管理**" 消息, 请单击它。 在 "**移动设备管理机构**" 边栏选项卡上, 单击 " **Intune MDM 颁发机构**", 然后单击 "**选择**"。 刷新浏览器选项卡。
    
5. 在左侧导航窗格中，单击“组”****。
    
6. 在 "**组-所有组**" 边栏选项卡上, 单击 " **+ 新建组**"。
    
7. 在**组**边栏上, 选择 **"组类型**的**Office 365** ？", 在 "**名称**" 中键入**托管 Windows 10 设备用户**, 在 "**成员身份类型**" 中选择 "**已分配**", 然后单击 "**创建**"。 
    
8. 关闭“组”**** 边栏选项卡。
    
11. 关闭 "**组-所有组**" 边栏选项卡。
    
12. 在**Microsoft Intune**边栏上的 "**快速任务**" 列表中, 单击 "**创建合规性策略**"。
    
13. 在“符合性策略配置文件”**** 边栏选项卡上，单击“创建策略”****。
    
14. 在 "**创建策略**" 边栏上的 "**名称**" 中, 键入**Windows 10**。 在 "**平台**" 中, 选择 " **windows 10 及更高版本**", 在**windows 10 合规性策略**边栏上单击 **"确定**", 然后单击 "**创建**"。 关闭**Windows 10**边栏。
    
15. 在 "**合规性策略配置文件**" 边栏选项卡上, 单击**Windows 10**策略名称。
    
16. 在**Windows 10**边栏上, 单击 "**分配**", 然后单击 "**选择要包含的组**"。
    
17. 在 "**选择要包括的组**" 边栏选项卡上, 单击 "**托管 Windows 10 设备用户**" 组, 然后单击 "**选择**"。
    
18. 单击 "**保存**", 然后关闭 " **Windows 10 工作分配**" 边栏选项卡。
    
19. 关闭“符合性策略配置文件”**** 边栏选项卡。
    
20. 在**Microsoft Intune**边栏上, 单击左侧导航栏中的 "**客户端应用**"。
    
21. 在**客户端应用程序**边栏中, 单击 "**应用程序**", 然后单击 "**添加**"。 

22. 在 "**添加应用程序**" 边栏选项卡上, 选择 "**应用类型**", 然后选择 " **Office 365 套件**下的**Windows 10** "。

23. 单击 "**配置应用程序套件**", 然后单击 **"确定"**。

24. 单击 "**应用套件信息**", 在 "**套件名称**" 中键入**office apps for** windows 10, 在**套件**中键入适用于**windows 10 的 office 应用程序**, 然后单击 **"确定"**。

25. 单击 "**应用套件设置**", 选择 "**半年****更新频道**", 然后单击 **"确定"**。

26. 在 "**添加应用程序**" 边栏选项卡上, 单击 "**添加**"。

现在, 你已拥有设备合规性策略, 用于测试**Windows 10**设备合规性策略中的所选应用和**托管 windows 10 设备用户**组的成员。 
  
## <a name="next-step"></a>后续步骤

在您的测试环境中探索其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[企业移动性 + 安全性 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
