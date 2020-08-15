---
title: 为你的 Microsoft 365 提高企业测试环境的 Microsoft 365 安全性
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
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可启用 Microsoft 365 企业版测试环境的其他 Microsoft 365 安全设置。
ms.openlocfilehash: 06273bda00635a65ed9821b2bac23c3a3ee1366a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686798"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>为你的 Microsoft 365 提高企业测试环境的 Microsoft 365 安全性

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

使用本文中的说明，您可以配置其他 Microsoft 365 设置，以提高 Microsoft 365 for 企业测试环境中的安全性。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果只想使用最低要求以轻型方式配置增加的 Microsoft 365 安全，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置增加的 Microsoft 365 安全，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试增强的 Microsoft 365 安全不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>第2阶段：配置增强的 Microsoft 365 安全性

在这一阶段，您为 Microsoft 365 启用了增强的 Microsoft 365 安全性，适用于企业测试环境。 有关其他详细信息和设置，请参阅 [Configure a 租户以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>配置 SharePoint Online 以阻止不支持新式身份验证的应用程序

不支持新式身份验证的应用程序不能对其应用 [标识和设备访问配置](microsoft-365-policies-configurations.md) ，这是保护 Microsoft 365 订阅及其数字资产的重要因素。 

1. 请转到 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)) 并使用全局管理员帐户登录到你的 microsoft 365 测试实验室订阅。
    
  - 如果使用的是轻型 Microsoft 365 测试环境，请从你的本地计算机登录。
    
  - 如果使用的是模拟企业 Microsoft 365 测试环境，请使用 [Azure 门户](https://portal.azure.com) 连接到 CLIENT1 虚拟机，然后从 CLIENT1 登录。
 
2. 在 "新建 **Microsoft 365 管理中心** " 选项卡上的左侧导航窗格中的 " **管理中心** " 下，单击 " **SharePoint**"。
3. 在 "新建 **SharePoint 管理中心** " 选项卡上，单击 " **策略 > 访问控制**"。
4. 单击 " **不支持新式身份验证的应用**"，选择 " **阻止访问**"，然后单击 " **保存**"。


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>为 SharePoint、OneDrive for Business 和 Microsoft 团队启用高级威胁防护

Office 365 高级威胁防护 (适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP) 保护您的组织不会在无意中共享恶意文件。

1. 转到 [安全 & 合规性中心](https://protection.office.com) ，并使用全局管理员帐户登录。

2. 在左侧导航窗格中的 " **威胁管理**" 下，单击 " **策略**"，然后单击 " **ATP 安全附件**"。 

3. 在 " **保护 SharePoint、OneDrive 和 Microsoft 团队中的文件**" 下。 选择 " **为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。

4. 单击“保存”****。


### <a name="enable-anti-malware"></a>启用反恶意软件

"恶意软件"包括病毒和间谍软件。 "病毒"会感染其他程序与数据，且会在整个计算机中寻找程序进行感染。 “间谍软件”指收集您的个人信息（如登录信息和个人数据），并将其发送给恶意软件作者的恶意软件。 

Microsoft 365 具有内置的恶意软件和垃圾邮件筛选功能，可帮助保护入站和出站邮件免受恶意软件的攻击，并帮助保护您免受垃圾邮件的攻击。 有关详细信息，请参阅 [反垃圾邮件 & 反恶意软件保护](../security/office-365-security/anti-spam-and-anti-malware-protection.md)。

若要确保正在对具有常见附件文件类型的文件执行反恶意软件处理，请执行以下操作：

1. 单击浏览器上的 "后退" 按钮返回到 " **策略** " 页。
2. 单击 " **反恶意软件**"。
3. 双击名为 " **默认**" 的策略。
4. 在 " **反恶意软件策略** " 窗口中，单击 " **设置**"。
4. 在 " **常用附件类型筛选器**" 下，选择 **"启用**"，然后单击 " **保存**"。


## <a name="phase-3-examine-the-security-dashboard"></a>第3阶段：检查安全仪表板

Microsoft 365 中的威胁管理可帮助您控制和管理对组织数据的移动设备访问，帮助保护您的组织不会丢失数据，并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。 您还可以使用威胁管理来保护您的域的信誉，并确定发件人是否是您的域中的恶意欺骗帐户。 

若要查看安全仪表板：

1. 如果需要，请转到 [安全 & 合规性中心](https://protection.office.com) ，并使用全局管理员帐户登录。

2. 在左侧导航窗格中的 " **威胁管理**" 下，单击 " **仪表板**"。

仔细查看仪表板上的所有卡片以熟悉提供的信息。

有关详细信息，请参阅 [安全仪表板](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)。


## <a name="phase-4-examine-microsoft-secure-score"></a>第4阶段：检查 Microsoft 安全分数

Microsoft 安全分数将安全状态显示为一个数字，表示您的当前级别相对于订阅中可用的功能。 此外，它还提供了可执行的改进操作的列表，以提高成绩。

1. 在浏览器中创建新的选项卡，然后转到 [Microsoft 365 安全中心](https://security.microsoft.com/)，然后单击 " **安全得分**"。
2. 在 " **概述**  " 选项卡上，记下当前安全分数以及它与全局平均和订阅（具有相似数量的许可证）的比较方式。
3. 在 " **改进操作** " 选项卡上，阅读可执行的操作列表，以增加成绩。

有关详细信息，请参阅 [Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。

## <a name="next-steps"></a>后续步骤

在您的测试环境中浏览其他 [信息保护](m365-enterprise-test-lab-guides.md#information-protection) 特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
