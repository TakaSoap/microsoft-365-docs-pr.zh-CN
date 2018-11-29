---
title: 用于 Microsoft 365 企业版测试环境的 MAM 策略
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南添加到 Microsoft 365 企业版 Intune 移动应用程序管理 (MAM) 策略测试环境。
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866028"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>用于 Microsoft 365 企业版测试环境的 MAM 策略

使用本文中的说明，您添加到 Microsoft 365 企业版 Intune 移动应用程序管理 (MAM) 策略测试环境。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要配置的最低硬件要求与轻型方式 MAM 策略，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要配置 MAM 策略模拟企业中，按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>第 2 阶段：为 iOS 和 Android 设备创建和部署 MAM 策略

在此阶段中，创建和部署两个不同的 MAM 策略：一个适用于 iOS 设备的策略和一个适用于 Android 设备的策略。
  
1. 转到 Office 365 门户: ([https://portal.office.com](https://portal.office.com)) 和 Office 365 试用版订阅与全局管理员帐户登录。
    
2. 在浏览器的新建选项卡上，打开 Azure 门户： [https://portal.azure.com](https://portal.azure.com)。

3. Azure 门户选项卡在 Internet Explorer 中，在导航窗格中，单击**所有服务**，键入**Intune**，，然后都单击**Intune**。
    
4. 如果您看到**尚未启用尚未设备管理**消息**Microsoft Intune**刀片上，单击该选项。在**移动设备管理证书颁发机构**刀片中，单击**Intune MDM 证书颁发机构**，，然后单击**选择**。刷新您浏览器的选项卡。
    
5. 在左侧导航窗格中，单击“组”****。
    
6. 在**组所有组**刀片中，单击 **+ 新建组**。
    
7. 在**组**刀片中，选择**Office 365** **组类型？**，请在**名称**框中，键入**托管 iOS 设备用户**在**成员资格类型**，选择**已分配**，然后单击**创建**。 
    
8. 关闭**组**刀片。
    
9. 在**组所有组**刀片中，单击**添加**。
    
10. 在**组**刀片中，选择**Office 365** **组类型？**，请在**名称**框中，键入**托管 Android 设备用户**在**成员资格类型**，选择**已分配**，然后单击**创建**。
    
11. 关闭**组所有组**刀片。
    
12. 在**Intune**刀片，在**快速的任务**列表中，单击**创建合规性策略**。
    
13. 在**合规性策略配置文件**刀片中，单击**创建策略**。
    
14. 在**创建策略**刀片，在**名称**框中，键入**iOS**。在**平台**中，选择**iOS**、 **iOS 合规性策略**刀片上, 单击**确定**，然后单击**创建**。
    
15. 在**合规性策略配置文件**刀片中，单击**创建策略**。
    
16. 在**创建策略**刀片，在**名称**框中，键入**Android**。**平台**中, 选择**Android**， **Android 合规性策略**刀片上, 单击**确定**，然后单击**创建**。
    
17. 在**合规性策略配置文件**刀片中，单击**Android**的策略名称。
    
18. **Android-属性**刀片的左侧导航中，单击**分配**，，然后单击**选择组**。
    
19. **选择组**刀片上,**托管 Android 设备用户**的组中，单击，然后单击**选择**。
    
20. 单击**保存**，然后关闭**Android-分配**刀片。
    
21. 在**合规性策略配置文件**刀片中，单击**iOS**策略名称。
    
22. 在**iOS-属性**刀片左侧导航窗格中，单击**工作分配**，然后单击**选择组**。
    
23. 在**选择组**刀片中，单击**托管 iOS 设备用户**组中，，然后单击**选择**。
    
24. 单击**保存**，然后关闭**iOS-分配**刀片。
    
25. 关闭**合规性策略配置文件**刀片。
    
26. 在**Intune**刀片，单击左侧导航窗格中的**管理应用程序**。
    
27. 在**移动应用程序**刀片中，单击**应用程序**。
    
28. 在应用程序列表中，单击**PowerPoint** 
    
29. 在**PowerPoint 概述**刀片中，单击**分配 > 选择组 > 托管 iOS 设备 > 选择**。在**类型**中，选择**有空**，，然后单击**保存**。
    
30. 对于以下应用程序重复步骤 29:
    
    - Outlook for Android
    
    - Word for iOS
    
    - Excel for iOS
    
    - Outlook iOS
    
    - 适用于 iOS iPad 的 Microsoft Dynamics CRM
    
    - 适用于 iOS iPhone 的 Microsoft Dynamics CRM
    
    - 适用于 Android 手机的 Dynamics CRM
    
    - 适用于 Android 平板电脑的 Dynamics CRM
    
    - Excel for Android
    
    - Word for Android
    
    - OneNote for iOS
    
31. 关闭**移动应用程序的应用程序**刀片。
    
32. 在**移动应用程序**刀片中，单击**应用程序保护策略**。
    
33. 在**应用程序保护策略**刀片中，单击**添加策略**。
    
34. 在**添加策略**刀片中，键入**iOS**，，然后单击**选择所需的应用程序**。
    
35. 在**应用程序**刀片， **PowerPoint**、 **iPhone 上的 Microsoft Dynamics CRM**、 **Excel**、 **iPhone 上的 Microsoft Dynamics CRM**、 **Word**、 **OneNote**和**Outlook**中，单击，然后单击**选择**。
    
36. 在**添加策略**刀片中，单击**创建**。
    
37. 在**应用程序保护策略**刀片中，单击**添加策略**。
    
38. **添加策略**刀片上, 键入**Android**，在**平台**选择**Android** ，然后单击**选择所需的应用程序**。
    
39. 在**应用程序**刀片中，单击**PowerPoint**、**平板电脑的 Dynamics CRM**、 **Excel**、 **Word**、 **Outlook**和**电话的 Dynamics CRM**、，然后单击**选择**。
    
40. 在**添加策略**刀片中，单击**创建**。
    
现在你有两个 MAM 策略，一个适用于 iOS 设备的策略和一个适用于 Android 设备的策略，并已准备好对所选应用的测试设置进行测试。 
  
## <a name="next-step"></a>后续步骤

浏览您的测试环境中其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 Enterprise 测试实验室指南](m365-enterprise-test-lab-guides.md)。
  
[在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[企业移动 + 安全 (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
