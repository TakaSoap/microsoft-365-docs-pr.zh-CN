---
title: Microsoft 365 业务安全性和合规性功能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
ms.openlocfilehash: bd61ad3bf1b34635a7b80f1c9ccf63fa98d31915
ms.sourcegitcommit: 274af83139ad7da3aa33366c3323d533d95c7db4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017514"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 业务安全性和合规性功能

Microsoft 365 商业版提供了简化的安全功能, 以帮助保护电脑、电话和平板电脑上的数据。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 商业管理员中心安全功能

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

您可以在管理中心管理许多 Microsoft 365 商业安全功能, 这为您提供了一种简单的方法来打开或关闭这些功能。 在管理中心, 您可以执行以下操作:
  
  
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
    
  - 自动检查电子邮件中的链接以进行评估, 如果它们是网络钓鱼方案的一部分。 这使您可以安全地访问不安全的网站。

- **[Azure 门户中的 Intune 的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    通过在 Azure 门户中访问 Intune 管理中心, 可以设置其他安全功能, 如 MacOS 设备、iPhone 和 Android 设备的管理, 以及 Windows 高级设备管理, 这些设备不能通过 Microsoft 使用365商业管理中心。
- **与 Azure AD P1 计划相同的[条件访问](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)**

    条件访问可帮助保护您的组织不受登录风险、访问来自意外网络或区域设置的尝试、访问尝试形成有风险的设备类型等。 在第一次身份验证完成后强制执行条件访问策略, 并使用来自第一种身份验证事件的信号来确定是否应批准、拒绝或 f 更好的验证 (例如, 第二种标识形式)。必填。

    条件访问功能包括:

    - 基于用户名、组和角色的访问权限
    - [基于应用程序的](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access)访问 
    - [基于位置的访问权限](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration); 仅允许来自受信任的 IP 范围或特定国家/地区的访问 
    - 需要对 access 进行 MFA
    - 阻止对使用[旧版身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)的应用的访问
    - 要求应用 tp 使用[Intune 应用保护](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - 自定义身份验证 (如与第三方提供商的 MFA), 例如双核。
   
    其他功能：
    - 混合 Azure AD 的[自助服务密码重置](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)
    
## <a name="compliance-features"></a>合规性功能

Microsoft 365 商业版订阅包括可帮助您维护合规性和法规标准的功能。

- **[数据丢失防护策略概述](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    您可以设置 DLP 以自动检测敏感信息, 如信用卡号、社会保险号码等, 以防止无意中与公司以外的用户共享。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online 存档许可证使邮件能够通过连续数据备份轻松存档。 它存储用户的所有电子邮件, 包括已删除的项目, 以备日后发现或还原时使用。 此外, 您还可以使用不同的保留策略来保留电子邮件数据以用于诉讼保留、电子数据展示或满足合规性要求。
    
- **[Azure 信息保护](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    信息保护可帮助您通过像 "不转发" 和 "不复制" 这样的控件来控制对电子邮件和文档中敏感信息的访问。 您还可以将敏感信息分类为 "机密", 并指定如何在企业外部和内部共享保密信息。 企业级加密易于应用于电子邮件和文档, 以确保信息保密。 Microsoft 365 商业版包括[Azure 信息保护计划 1](https://go.microsoft.com/fwlink/p/?linkid=871407)的所有功能。 您还可以安装适用于 Office 应用的 Azure 信息保护客户端外接程序。 有关更多详细信息, 请参阅[Azure 信息保护客户端管理员指南](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)。

您可以在安全&amp;合规性中心和 Intune 管理中心中管理这些功能。 随着时间的推移, 简化的控件将被添加到 Microsoft 365 Business 管理中心。
  
    
## <a name="faq"></a>常见问题

 ### <a name="are-these-security-features-available-in-all-markets"></a>这些安全功能在所有市场中是否可用？
  
是的, 在售出 Microsoft 365 业务的所有市场中, 这些功能都是可用的。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何查找安全&amp;合规性中心？
  
1. 使用管理员凭据[登录 Microsoft 365 商业](https://portal.microsoft.com/)版。 
    
2. 在左侧导航中, 找到**管理中心**并展开它。 
    
    ![在 Microsoft 365 管理中心的左侧导航中, 选择 "管理中心"。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 选择 **" &amp;安全合规性**" 以&amp;转到 "安全合规中心"。