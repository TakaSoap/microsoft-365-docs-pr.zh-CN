---
title: Microsoft 365 商业安全功能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 了解 Microsoft 365 商业版附带的安全功能。
ms.openlocfilehash: adf1cf183022f3d2c19364b9f60868e285f78637
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660517"
---
# <a name="microsoft-365-business-security-features"></a>Microsoft 365 商业安全功能

Microsoft 365 商业版提供了简化的安全功能, 以帮助保护电脑、电话和平板电脑上的数据。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 商业管理员中心安全功能

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

您可以在管理中心管理许多 Microsoft 365 商业安全功能, 这为您提供了一种简单的方法来打开或关闭这些功能。 在管理中心, 您可以执行以下操作:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [设置 Android 或 iOS 设备的应用程序管理设置](app-protection-settings-for-android-and-ios.md)。 
    
    这些设置包括在设定的时间段后从非活动设备中删除文件、对工作文件进行加密、要求用户设置 PIN 等。
    
- [设置 Windows 10 设备的应用程序保护设置](protection-settings-for-windows-10-devices.md)。 
    
    这些设置可应用于公司拥有的或个人拥有的设备上的公司数据。
    
- [设置 Windows 10 设备的设备保护设置](protection-settings-for-windows-10-pcs.md)。 
    
    您可以启用[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)加密以在设备丢失或被盗时帮助保护数据, 并启用[Windows 漏洞防护](https://go.microsoft.com/fwlink/p/?linkid=871404)以提供针对勒索软件的高级防护。 
    
- [从设备中删除公司数据](remove-company-data.md)
    
    如果设备丢失、被盗或员工离开你的公司, 你可以远程擦除公司数据。
    
- [将 Windows 10 设备重置为其出厂设置](reset-devices-to-factory-settings.md)。 
    
    您可以重置任何已应用设备保护设置的 Windows 10 设备。
    
## <a name="additional-security-features"></a>其他安全功能 

Microsoft 365 商业版中的高级功能可帮助您保护业务, 抵御网络威胁并保护敏感信息。
  
- **[Office 365 高级威胁防护](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    高级威胁防护 (ATP) 可帮助保护您的业务免受复杂的网络钓鱼和勒索软件攻击, 旨在危害员工或客户信息。 这些功能包括： 
    
  - 完善的附件扫描和 AI 分析, 以检测并丢弃危险邮件。
    
  - 自动检查电子邮件中的 web 链接以评估是否为网络钓鱼架构的一部分。 这使您可以安全地访问不安全的网站。
    
- **[数据丢失防护策略概述](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    您可以设置 DLP 以自动检测敏感信息, 如信用卡号、社会保险号码等, 以防止无意中与公司以外的用户共享。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online 存档许可证使邮件能够通过连续数据备份轻松存档。 它存储用户的所有电子邮件, 包括已删除的项目, 以备日后发现或还原时使用。 此外, 您还可以使用不同的保留策略来保留电子邮件数据以用于诉讼保留、电子数据展示或满足合规性要求。
    
- **[Azure 信息保护](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    信息保护可帮助您通过像 "不转发" 和 "不复制" 这样的控件来控制对电子邮件和文档中敏感信息的访问。 您还可以将敏感信息分类为 "机密", 并指定如何在企业外部和内部共享保密信息。 企业级加密易于应用于电子邮件和文档, 以确保信息保密。 Microsoft 365 商业版包括[Azure 信息保护计划 1](https://go.microsoft.com/fwlink/p/?linkid=871407)的所有功能。 您还可以安装适用于 Office 应用的 Azure 信息保护客户端外接程序。 有关更多详细信息, 请参阅[Azure 信息保护客户端 admininstrator 指南](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)。
    
- **[Azure 门户中的 Intune 的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    通过在 Azure 门户中访问 Intune 管理中心, 可以设置其他安全功能, 如 MacOS 设备、iPhone 和 Android 设备的管理, 以及 Windows 高级设备管理, 这些设备不能通过 Microsoft 使用365商业管理中心。
    
以下各节介绍如何在安全&amp;合规性中心和 Intune 管理中心中管理这些功能。 随着时间的推移, 简化的控件将被添加到 Microsoft 365 Business 管理中心。
  
    
## <a name="faq"></a>常见问题

 ### <a name="are-these-security-features-available-in-all-markets"></a>这些安全功能在所有市场中是否可用？
  
是的, 在售出 Microsoft 365 业务的所有市场中, 这些功能都是可用的。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何查找安全&amp;合规性中心？
  
1. 使用管理员凭据[登录 Microsoft 365 商业](https://portal.microsoft.com/)版。 
    
2. 在左侧导航中, 找到**管理中心**并展开它。 
    
    ![在 Microsoft 365 管理中心的左侧导航中, 选择 "管理中心"。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 选择 **" &amp;安全合规性**" 以&amp;转到 "安全合规中心"。