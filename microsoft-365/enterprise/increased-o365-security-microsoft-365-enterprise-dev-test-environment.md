---
title: 提高了Microsoft 365测试环境Microsoft 365的安全性
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南为企业Microsoft 365环境启用Microsoft 365安全设置。
ms.openlocfilehash: 08b1db95a35debfa465d57d30ab0a8a2bd9f9732
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58567900"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>提高了Microsoft 365测试环境Microsoft 365的安全性

*本测试实验室指南只能用于Microsoft 365测试环境。*

按照本文中的说明，配置其他 Microsoft 365 设置以提高企业测试Microsoft 365的安全性。

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](../downloads/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你只想根据最低要求Microsoft 365安全性，请按照轻型基本配置[中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟企业中配置Microsoft 365安全性，请按照传递身份验证[中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试Microsoft 365安全性不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 的目录同步。 它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>阶段 2：配置增强Microsoft 365安全性

在此阶段，为企业Microsoft 365环境Microsoft 365安全性提高。 有关其他详细信息和设置，请参阅 [配置租户以提升安全性](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>配置 SharePoint Online 以阻止不支持新式验证的应用

不支持新式身份验证的应用无法应用[标识](../security/office-365-security/microsoft-365-policies-configurations.md)和设备访问配置，这是保护你的 Microsoft 365 订阅及其数字资产的重要元素。 

1. 转到"Microsoft 365 管理中心 () ，然后使用全局管理员Microsoft 365登录到 [https://portal.microsoft.com](https://portal.microsoft.com) 你的测试实验室订阅。
    
  - 如果你使用的是轻型测试Microsoft 365，请从本地计算机登录。
    
  - 如果你使用的是模拟的企业Microsoft 365环境，请使用[Azure](https://portal.azure.com)门户连接到 CLIENT1 虚拟机，然后从 CLIENT1 登录。
 
2. 在新的 **"Microsoft 365 管理中心"** 选项卡上，在左侧导航 **窗格中的**"管理中心"下，单击 **"SharePoint"。**
3. 在"管理SharePoint **选项卡上**，单击"访问控制 **>策略"。**
4. 单击 **不支持新式验证的应用，选择**"**阻止访问**"，然后单击"保存 **"。**


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>为 Office 365、SharePoint 和 OneDrive for Business 启用 Defender Microsoft Teams

defender for Office 365 for SharePoint， OneDrive， and Microsoft Teams protects your organization from inadvertently sharing malicious files.

1. 转到安全 [与&](https://protection.office.com) 中心，然后使用全局管理员帐户登录。

2. 在左侧导航窗格中的 **"威胁管理**"下，单击"策略"，然后单击"保险箱 **附件"。** 

3. 在 **"保护文件SharePoint、OneDrive和Microsoft Teams"** 下。 选择 **打开 ATP 作为SharePoint、OneDrive和Microsoft Teams。**

4. 单击“保存”。


### <a name="enable-anti-malware"></a>启用反恶意软件

"恶意软件"包括病毒和间谍软件。 "病毒"会感染其他程序与数据，且会在整个计算机中寻找程序进行感染。 “间谍软件”指收集您的个人信息（如登录信息和个人数据），并将其发送给恶意软件作者的恶意软件。 

Microsoft 365内置恶意软件和垃圾邮件筛选功能，可帮助保护入站和出站邮件免受恶意软件的攻击，并保护您免受垃圾邮件的侵害。 有关详细信息，请参阅 [反垃圾邮件&反恶意软件保护](../security/office-365-security/anti-spam-and-anti-malware-protection.md)。

为确保对具有常见附件文件类型的文件执行反恶意软件处理：

1. 单击浏览器上的后退按钮返回到"策略 **"** 页面。
2. 单击 **"反恶意软件"。**
3. 双击名为"默认" **的策略**。
4. 在"**反恶意软件策略"** 窗口中，单击 **"设置"。**
4. 在"**常见附件类型"筛选器** 下，选择 **"打开"，** 然后单击"保存 **"。**


## <a name="phase-3-examine-the-security-dashboard"></a>阶段 3：检查安全仪表板

Microsoft 365中的威胁管理可帮助您控制和管理对组织数据的移动设备访问，帮助保护组织避免数据丢失，并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。 您还可以使用威胁管理来保护域的信誉，并确定发件人是否恶意欺骗域中的帐户。 

查看安全仪表板：

1. 如果需要，请转到安全与&[](https://protection.office.com)中心，然后使用全局管理员帐户登录。

2. 在左侧导航窗格中的 **"威胁管理**"下，单击"仪表板 **"。**

仔细查看仪表板上的所有卡片，以熟悉提供的信息。

有关详细信息，请参阅安全 [仪表板](../security/office-365-security/security-dashboard.md)。


## <a name="phase-4-examine-microsoft-secure-score"></a>阶段 4：检查 Microsoft 安全分数

Microsoft 安全功能分数以数字显示安全状态，它指明了相对于订阅中可用功能的当前级别。 它还为你提供了可用于提高分数的改进操作列表。

1. 在浏览器中创建新选项卡，然后转到安全 [Microsoft 365，](https://security.microsoft.com/)然后单击"安全 **分数"。**
2. 在" **概述**  "选项卡上，记下当前的安全分数及其与全局平均值和许可证数量相似的订阅之间的比较方式。
3. 在 **"改进操作** "选项卡上，通读可采取的操作列表以提高分数。

有关详细信息，请参阅 [Microsoft 安全分数](../security/defender/microsoft-secure-score.md)。

## <a name="next-steps"></a>后续步骤

探索 [测试环境中](m365-enterprise-test-lab-guides.md#information-protection) 的其他信息保护特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)