---
title: 为 Microsoft 365 企业版测试环境增加了 Microsoft 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可启用 Microsoft 365 企业版测试环境中的其他 Microsoft 365 安全设置。
ms.openlocfilehash: 3173796167a0a9fb59e23ee2dc6eebf5000ed3d7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672688"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>为 Microsoft 365 企业版测试环境增加了 Microsoft 365 安全性

*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*

使用本文中的说明，您可以配置其他 Microsoft 365 设置以提高 Microsoft 365 企业版测试环境的安全性。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>阶段 1：构建 Microsoft 365 企业版测试环境。

如果只想使用最低要求以轻型方式配置增加的 Microsoft 365 安全，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置增加的 Microsoft 365 安全，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试增强的 Microsoft 365 安全不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。 此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>第2阶段：配置增强的 Microsoft 365 安全性

在这一阶段，您为 Microsoft 365 企业版测试环境启用了增强的 Microsoft 365 安全性。 有关其他详细信息和设置，请参阅[Configure a Office 365 租户以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>配置 SharePoint Online 以阻止不支持新式身份验证的应用程序

不支持新式身份验证的应用程序不能对其应用[标识和设备访问配置](microsoft-365-policies-configurations.md)，这是保护 Microsoft 365 订阅及其数字资产的重要因素。 

1. 转到 Microsoft 365 管理中心（[https://portal.microsoft.com](https://portal.microsoft.com)），并使用全局管理员帐户登录到你的 Office 365 测试实验室订阅。
    
  - 如果使用的是轻型 Microsoft 365 测试环境，请从你的本地计算机登录。
    
  - 如果使用的是模拟企业 Microsoft 365 测试环境，请使用[Azure 门户](https://portal.azure.com)连接到 CLIENT1 虚拟机，然后从 CLIENT1 登录。
 
2. 在 "新建**Microsoft 365 管理中心**" 选项卡上，单击 "**管理中心 > SharePoint**"。
3. 在 "新建**SharePoint 管理中心**" 选项卡上，单击 "**访问控制**"。
4. 在**不支持新式身份验证的应用**下，单击 "**阻止**"，然后单击 **"确定"**。


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>为 SharePoint、OneDrive for Business 和 Microsoft 团队启用高级威胁防护

适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 高级威胁防护（ATP）可防止您的组织无意中共享恶意文件。

1. 转到 " [Office 365 安全 & 合规中心](https://protection.office.com)"，并使用全局管理员帐户登录。

2. 在左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略 > 安全附件**"。 

3. 选择 "**为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。

4. 单击“保存”****。


### <a name="enable-anti-malware"></a>启用反恶意软件

"恶意软件"包括病毒和间谍软件。 "病毒"会感染其他程序与数据，且会在整个计算机中寻找程序进行感染。 “间谍软件”指收集您的个人信息（如登录信息和个人数据），并将其发送给恶意软件作者的恶意软件。 

Office 365 具有内置的恶意软件和垃圾邮件筛选功能，可帮助保护入站和出站邮件免受恶意软件的攻击，并帮助保护您免受垃圾邮件的攻击。 有关详细信息，请参阅[反垃圾邮件 & Office 365 中的反恶意软件保护](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

若要确保正在对具有常见附件文件类型的文件执行反恶意软件处理，请执行以下操作：

1. 单击浏览器上的 "后退" 按钮返回到 "**策略**" 页。
2. 单击 "**反恶意软件**"。
3. 双击名为 "**默认**" 的策略。
4. 在 "**反恶意软件策略**" 窗口中，单击 "**设置**"。
4. 在 "**常用附件类型筛选器**" 下，单击 **"> 保存**"。


## <a name="phase-3-examine-the-threat-management-dashboard"></a>第3阶段：检查威胁管理仪表板

Office 365 的威胁管理可帮助您控制和管理对组织数据的移动设备访问，帮助保护组织不会丢失数据，并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。 您还可以使用威胁管理来保护您的域的信誉，并确定发件人是否是您的域中的恶意欺骗帐户。 有关详细信息，请参阅[Microsoft 365 安全中心中的威胁管理](https://docs.microsoft.com/office365/securitycompliance/threat-management)。

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>后续步骤

有关信息**保护**阶段中的 "为[Microsoft 365 配置增强的安全性](infoprotect-configure-increased-security-office-365.md)" 步骤，请参阅在生产中配置这些设置的信息和链接。

在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)

