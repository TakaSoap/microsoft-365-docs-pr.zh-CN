---
title: 在 Microsoft 365 企业版测试环境中实现更高的 Office 365 安全性
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
description: 使用此测试实验室指南启用其他 Office 365 安全设置 Microsoft 365 企业版测试环境。
ms.openlocfilehash: 18e7b682d20c2212ae73783d668250d28b04075f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865666"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>在 Microsoft 365 企业版测试环境中实现更高的 Office 365 安全性

使用本文中的说明，您可以配置其他 Office 365 设置，以提高 Microsoft 365 企业版测试环境中的安全性。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要配置的最低硬件要求与轻型方式增加的 Office 365 安全，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要在模拟企业中配置增加的 Office 365 安全性，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试增加的 Office 365 安全不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。 


## <a name="phase-2-configure-increased-office-365-security"></a>第 2 阶段： 配置增加的 Office 365 安全性

在此阶段，您为 Microsoft 365 企业版测试环境中启用增加的 Office 365 安全。有关其他详细信息和设置，请参阅[Configure Office 365 租户为了提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>配置 SharePoint Online，从而阻止应用程序不支持现代身份验证

不支持现代的身份验证的应用程序不能具有[标识和设备访问配置](microsoft-365-policies-configurations.md)应用于它们，这是保护您的 Microsoft 365 订阅和其数字资产的重要组成部分。 

1. 转到 Office 365 门户 ([https://portal.office.com](https://portal.office.com)) 和 Office 365 试用版订阅与全局管理员帐户登录。
    
  - 如果您使用的轻型 Microsoft 365 测试环境，登录本地计算机中。
    
  - 如果您使用模拟的企业 Microsoft 365 测试环境，使用[Azure 门户网站](https://portal.azure.com)连接到 CLIENT1 虚拟机，并然后登录从 CLIENT1。
 
2. 从**Microsoft 365 管理中心**选项卡，单击**管理**。
3. 在新的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > SharePoint**。
4. 在新的**SharePoint 管理中心**选项卡上，单击**访问控制**。
5. 在**应用程序不支持现代身份验证**，下单击**块 > 确定**。


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>启用高级对 SharePoint、 OneDrive 和 Microsoft 团队的威胁保护 (ATP)

Office 365 高级威胁保护 (ATP) 是一项功能的 Exchange Online Protection (EOP)，可帮助保持利用您的电子邮件的恶意软件。与 ATP，Exchange 管理员中心 (EAC) 或安全中创建策略和合规性中心，帮助确保您的用户访问仅链接或在标识为不恶意的电子邮件中的附件。有关详细信息，请参阅[高级的威胁保护安全的附件和安全的链接](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)。

1. 在浏览器的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > 安全和合规性**。
2. 在新的**安全和合规性**选项卡，单击**威胁管理 > 策略**。
3. 单击**ATP 安全附件**。
4. 在**安全附件**窗格中，选择**SharePoint、 OneDrive 和 Microsoft 团队 ATP 打开**，，然后单击**保存**。

### <a name="enable-anti-malware"></a>启用反恶意软件

恶意软件组成病毒和间谍软件。病毒感染其他程序和数据，并在您要查找程序感染的计算机整个传播。间谍软件是指收集您的个人信息，例如登录信息和个人数据，并将其发送回恶意软件作者的恶意软件。 

Office 365 具有内置的恶意软件和垃圾邮件筛选功能，帮助防止恶意软件的入站和出站邮件，并帮助您免受垃圾邮件。有关详细信息，请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

若要确保正在执行的反恶意软件处理对与常见的附件文件类型的文件：

1. 单击浏览器以返回到**策略**页上的后退按钮。
2. 单击**反恶意软件**。
3. 双击名为**Default**的策略。
4. 在**反恶意软件策略**窗口中，单击**设置**。
4. 下**常见附件类型筛选器**中，单击**上 > 保存**。


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>第 3 阶段： 检查 Office 365 安全工具和日志

在此阶段中，您查看内置服务，通知您关于安全事件和测量总体安全状况。

### <a name="threat-management-dashboard"></a>威胁管理仪表板

Office 365 威胁管理可以帮助您控制和管理移动设备访问您组织的数据，帮助保护您的组织免受数据丢失，帮助防止恶意软件和垃圾邮件的入站和出站邮件。您还使用从您的域帐户管理以保护您的域的声誉并确定恶意欺骗发件人的威胁。有关详细信息，请参阅[Office 365 安全性和合规性中心中的威胁 management](https://docs.microsoft.com/office365/securitycompliance/threat-management)。

使用以下步骤查看 Office 365 威胁管理仪表板：

1. 在浏览器的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > 安全和合规性**。
2. 在新的**安全和合规性**选项卡，单击**威胁管理 > 仪表板**。
3. 在新**仪表板**选项卡在浏览器中，记下的恶意软件趋势、 见解和其他部分的仪表板。

### <a name="office-365-cloud-app-security-dashboard"></a>Office 365 云应用程序安全性仪表板

Office 365 云应用程序安全性，以前称为 Office 365 高级安全管理，允许您创建的监视和通知您在 Office 365 订阅中，可疑活动，以便可以调查，并采取可能的策略修复操作。有关详细信息，请参阅[概述的 Office 365 云应用程序安全性](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)。

1. 在浏览器的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > 安全和合规性**。
2. 在新的**安全和合规性**选项卡，单击**通知 > 管理高级通知 > 转到 Office 365 云应用程序安全性**。
3. 在新的**云应用程序安全性**选项卡上，记下仪表板视图和列表的监视的 Office 365 订阅中的各种活动的默认策略。
4. 单击仪表板图标可查看正在跟踪的云应用程序安全性活动摘要。
5. 单击**调查**（眼镜图标），然后选择**活动日志**以查看最新登录的列表和其他活动。

### <a name="secure-score"></a>安全分数

1. 在浏览器中创建新选项卡，并转到**securescore.office.com**。
2. 在**仪表板选项卡**上，记下您当前的安全排名和队列中的操作列表来提高您的分数。

有关信息和链接在生产中配置这些设置的**信息保护**阶段，请参阅[Configure 增加的 Office 365 安全性](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)步骤。

## <a name="next-step"></a>后续步骤

浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)

