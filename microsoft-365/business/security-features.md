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
ms.openlocfilehash: 24d4c4e79e7d8737beb82336796956774f127209
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286846"
---
# <a name="microsoft-365-business-security-features"></a>Microsoft 365 商业安全功能

Microsoft 365 商业版提供了简化的安全功能, 以帮助保护电脑、电话和平板电脑上的数据。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 商业管理员中心安全功能

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
  
## <a name="set-up-advanced-threat-protection-features"></a>设置高级威胁防护功能

- 防御**不安全附件:** ATP 通过在虚拟环境中打开电子邮件附件并对生成的行为进行分析来识别恶意内容。 对内容进行评估, 以确定其目的 (无论是正常还是恶意), ATP 会阻止传输不安全的附件, 从而帮助您抵御网络钓鱼骗术和勒索软件感染。 若要激活附件保护, 请参阅[设置 Office 365 ATP 安全附件策略](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)。
    
- 当用户单击恶意链接时保护你的环境: ATP 还检查用户单击时电子邮件中的链接。 如果链接不安全, 则会警告用户不会访问网站, 或通知用户网站已被阻止。 这有助于防止仿冒骗术。 您可以[设置 office 365 atp 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc), 或[设置 office 365 atp 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
## <a name="set-up-dlp-features"></a>设置 DLP 功能

有关如何设置策略以防止个人身份信息 (PII) 的示例, 请参阅[从模板创建 DLP 策略](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。 
  
DLP 提供了许多不同区域设置的多种可供使用的策略模板。 例如, 澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。有关完整列表, 请参阅[DLP 策略模板包含的内容](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。 所有这些模板都可以像 PII 模板示例一样启用。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>使用 Exchange Online 存档设置电子邮件保留

 **Exchange Online 存档**许可证功能使您能够通过保留电子邮件内容以用于电子数据展示来帮助维护合规性和法规标准。 它还有助于在发生诉讼时降低风险, 并提供在安全破坏或需要恢复已删除项目时恢复数据的方法。 若要激活这些功能, 您可以使用诉讼保留来保留用户的所有内容, 或使用保留策略以进行更好的自定义。 
  
**诉讼保留:** 通过将用户的整个邮箱置于诉讼保留中, 可以保留所有邮箱内容 (包括已删除项目)。 
    
若要将邮箱置于诉讼保留状态, 请在管理中心:
    
1. 在左侧导航中, 转到 "**用户** \> **活动用户**"。
    
2. 选择要将其邮箱置于诉讼保留状态的用户, 并在用户窗格中展开 "**邮件设置**", 然后选择 "**其他设置**" 旁边的 "**编辑 Exchange 属性**"。
    
3. 在用户的 "邮箱" 页上, 在左侧导航中选择 "* * 邮箱功能 * *", 然后选择 "**诉讼保留**" 下的 "**启用**" 链接。
    
4. 在 "**诉讼保留**" 对话框中, 您可以在 "**诉讼保留持续时间**" 字段中指定诉讼保留期, 如果您想要设置无限保留, 则将字段留空。 您还可以添加注释, 并将邮箱所有者引导到网站, 您可能需要详细了解诉讼保留\> **保存**。
    
**保留:** 您可以启用自定义保留策略, 例如, 在保留期结束时保留特定时间或永久删除内容。 若要了解详细信息, 请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
## <a name="set-up-azure-information-protection-features"></a>设置 Azure 信息保护功能

Azure 信息保护 (AIP) 是一种基于云的解决方案, 可帮助组织通过应用标签来分类和 (可选) 保护其文档和电子邮件。 可以由管理员自动应用标签, 这些管理员定义规则和条件、手动由用户手动应用或为用户提供建议的组合。

为所有用户自动启用了在 web 上的 Outlook 中发送电子邮件时应用以下限制的能力:
  
- **不转发**: 收件人可以阅读邮件, 但不能转发、打印或复制内容
    
- **加密**: 对整个邮件进行加密。 收件人在访问加密内容之前, 必须执行额外的步骤来确认其标识, 并且无法删除加密。
    
- **机密**: 为组织中的员工提供对电子邮件内容和附件的完全权限, 但不授予组织外部的人员。 数据所有者可以随时跟踪和撤消内容。
    
- **高度机密**: 此限制可应用于高度机密数据, 允许员工查看、编辑和回复, 但不能转发、打印或复制数据。 数据所有者可以随时跟踪和撤消内容。

### <a name="make-sure-azure-information-protection-is-activated"></a>请确保已激活 Azure 信息保护

若要验证是否已激活 AIP, 请执行以下操作:

1. 登录到[Azure 门户](https://portal.azure.com/)。

2. 选择 "**所有服务**", 并在 "**搜索" 框**中键入*Azure 信息保护*。

3. 显示结果后, 单击 " **Azure 信息保护**" 旁边的 "开始", 使其成为收藏且易于查找。

4. 选择 " **Azure 信息保护** \> **激活**", 并确保将 "状态" 设置为 "已激活"。 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>查看 Azure 信息保护策略和默认标签 

若要查看和修改现有标签, 请执行以下操作:

1. 在 "Azure 信息保护" 仪表板中, 选择 "**分类** \> **标签**"。 <br/>![用于 Azure 信息保护的标准标签。](media/AIPLabels.png)

2. 您可以选择任何标签以查看选项, 您可以更改显示名称、颜色等。
 
3. 若要创建自己的[标签, 请参阅修改和创建新标签](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)。 

### <a name="install-the-azure-information-protection-client-manually"></a>手动安装 Azure 信息保护客户端

若要手动安装 AIP 客户端:

1. 从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载**azinfoprotection.exe** 。
 
2. 您可以通过查看 Word 文档并确保 "**主页**" 选项卡上的 "**保护**" 选项可用来验证安装是否正常。 <br/>![Word 文档中的 "保护" 选项卡下拉箭头。](media/Word_Protect.png)

有关详细信息, 请参阅[安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>转到 Intune 管理中心

1. 登录到[Azure 门户](https://portal.azure.com/)。

2. 在 "**搜索" 框**中选择 "**所有服务**", 然后键入*Intune* 。

3. 显示结果后, 单击 " **Microsoft Intune** " 旁边的 "开始", 使其成为收藏, 以便稍后查找。
 
您可以使用 Intune 注册和管理组织的设备。 有关详细信息, 请参阅[Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和由[Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。
    
## <a name="faq"></a>常见问题

 ### <a name="are-these-security-features-available-in-all-markets"></a>这些安全功能在所有市场中是否可用？
  
是的, 在售出 Microsoft 365 业务的所有市场中, 这些功能都是可用的。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何查找安全&amp;合规性中心？
  
1. 使用管理员凭据[登录 Microsoft 365 商业](https://portal.microsoft.com/)版。 
    
2. 在左侧导航中, 找到**管理中心**并展开它。 
    
    ![在 Microsoft 365 管理中心的左侧导航中, 选择 "管理中心"。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 选择 **" &amp;安全合规性**" 以&amp;转到 "安全合规中心"。