---
title: Microsoft 365 商业高级版安全性和合规性功能
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 了解设备中提供Microsoft 365 商业高级版保护电脑、手机和平板电脑上的数据。
ms.openlocfilehash: 50b74ed18d641e8de38db3284c3ef3abf319825f4f7dbe02b6575f6c0fbc6f85
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53887557"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 商业高级版安全性和合规性功能

Microsoft 365 商业高级版提供简化的安全功能，以帮助保护电脑、手机和平板电脑上的数据。
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 管理中心安全功能

可以在管理中心管理Microsoft 365 商业高级版许多安全保护功能，这为你提供了打开或关闭这些功能的简化方法。 在管理中心中，可以执行以下操作：
  
- [设置 Android 或 iOS 设备的应用程序管理设置](app-protection-settings-for-android-and-ios.md) 。 
    
    这些设置包括在设置期限后从非活动设备中删除文件、加密工作文件、要求用户设置 PIN 等。
    
- [为设备设置Windows 10设置](protection-settings-for-windows-10-devices.md)。 
    
    这些设置可应用于公司拥有的设备或个人拥有的设备上的公司数据。
    
- [为设备设置Windows 10设置](protection-settings-for-windows-10-pcs.md)。 
    
    你可以启用[BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)加密以帮助保护设备丢失或被盗时的数据，并启用 Windows[攻击防护](/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection)，以针对勒索软件提供高级保护。 
    
- [从设备中删除公司数据](remove-company-data.md)
    
    如果设备丢失、被盗或员工离开公司，你可以远程擦除公司数据。
    
- [将Windows 10设备重置为出厂设置](reset-devices-to-factory-settings.md)。 
    
    你可以重置Windows 10设备保护设置的任何设备。
    
## <a name="additional-security-features"></a>其他安全功能 

Microsoft 365商业高级版中的高级功能可用来帮助您保护企业免受网络威胁并保护敏感信息。
  
- **[Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md)**
    
    Microsoft Defender for Office 365帮助保护你的企业免受旨在泄露员工或客户信息的复杂的网络钓鱼和勒索软件攻击。 这些功能包括： 
    
  - 复杂的附件扫描和 AI 功能分析，用于检测和丢弃危险邮件。
    
  - 自动检查电子邮件中的链接，以评估它们是否属于网络钓鱼计划。 这可让你安全地访问不安全的网站。

- **[Azure 门户中 Intune 的完整功能](/mem/intune/fundamentals/what-is-intune)**
    
    通过访问 Azure 门户中的 Intune 管理中心，你可以设置其他安全功能，如 MacOS 设备、iPhone 和 Android 设备的管理，以及 Windows 的高级设备管理，这些功能无法通过 Microsoft 365 管理中心 实现。
- **与 [计划相同的](/azure/active-directory/conditional-access/overview)条件Azure AD Premium P1访问**


    条件访问可帮助保护组织免受登录风险、来自意外网络或区域设置的访问尝试、来自风险设备类型的访问尝试等等。 条件访问策略是在完成第一次身份验证之后强制执行的，并且它使用来自第一个身份验证事件的信号来确定尝试的访问是应该批准、拒绝还是需要更多证明 (例如第二种标识) 。

    包含的条件访问功能包括：

    - 基于用户名、组和角色的访问
    - 基于 [应用的访问](/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [根据位置访问](/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration); 仅允许从受信任的 IP 范围或特定国家/地区访问 
    - 需要 MFA 访问
    - 阻止访问使用旧式 [身份验证的应用](/azure/active-directory/conditional-access/block-legacy-authentication)
    - 要求应用使用 [Intune 应用保护](/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - 自定义身份验证，如使用第三方提供程序的 MFA，例如 DUO。
   
    其他功能：
    - [混合](/azure/active-directory/authentication/concept-sspr-customization) Azure AD 的自助服务密码重置
    
## <a name="compliance-features"></a>合规性功能

你的Microsoft 365 商业高级版订阅包括可帮助你保持合规性和法规标准的功能。

- **[了解 DLP)  (](../compliance/dlp-learn-about-dlp.md)** 数据丢失) 。 
    
    您可以将 DLP 设置为自动检测敏感信息，如信用卡号、社会保险号等，以防止他们无意中在公司外共享。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archiving许可证允许使用连续数据备份轻松存档邮件。 它将存储用户的所有电子邮件，包括已删除的邮件，以防稍后需要这些邮件进行发现或还原。 此外，您可以使用不同的保留策略保留诉讼保留、电子数据展示或满足合规性要求的电子邮件数据。
    
- **[敏感度标签](../compliance/sensitivity-labels.md)**

   Microsoft 365 商业高级版 Azure 信息保护计划[1](https://go.microsoft.com/fwlink/p/?linkid=871407)的所有功能。 通过此计划，你可以创建敏感度标签，通过"不要转发"和"不复制"等控件，你可以控制对电子邮件和文档中敏感信息的访问。 还可以将敏感信息分类为"机密"，并指定如何在企业外部和内部共享机密信息。 Enterprise级加密可轻松应用于电子邮件和文档，以保持你的信息的私密性。 还可以为应用安装 Azure 信息保护客户端Office加载项。 有关详细信息，请参阅 [Azure 信息保护统一标签客户端](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)。 对于敏感度标签 **，请安装** AzInfoProtection_UL.exe。

可以在安全与合规中心和 Intune 管理中心 &amp; 内管理这些功能。 随着时间的推移，简化的控件将添加到Microsoft 365 管理中心。
  
    
## <a name="faq"></a>常见问题解答

 ### <a name="are-these-security-features-available-in-all-markets"></a>这些安全功能是否在所有市场中可用？
  
是的，这些功能在销售产品的所有Microsoft 365 商业高级版可用。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何查找安全与 &amp; 合规中心？
  
1. [使用管理员Microsoft 365 商业高级版](https://portal.microsoft.com/)登录登录。 
    
2. 在左侧导航中，找到 **"管理中心"并** 展开它。 
    
    ![In the left nav in the Microsoft 365 管理中心， choose Admin centers.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 选择 **" &amp; 安全合规性** "以转到"安全 &amp; 与合规中心"。
