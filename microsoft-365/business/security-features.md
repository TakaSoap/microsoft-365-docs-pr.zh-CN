---
title: Microsoft 365 业务安全功能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: 了解 Microsoft 365 业务附带的安全功能。
ms.openlocfilehash: bfddb419dbe5db441741a73ecb49e3d52649e382
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865711"
---
# <a name="microsoft-365-business-security-features"></a>Microsoft 365 业务安全功能

Microsoft 365 业务提供简化的安全功能来帮助保护您的 Pc、 电话和平板电脑上的数据。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 Business admin center 安全功能

您可以管理的许多 Microsoft 365 业务安全功能在管理中心，为您提供了一种以启用或禁用这些功能的简化的方法。在管理中心中可以执行以下操作：
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [设置应用程序管理 Android 或 iOS 设备](app-protection-settings-for-android-and-ios.md)。 
    
    这些设置包括设置段时间后从非活动状态的设备中删除文件、 加密工作文件需要用户设置 PIN，等等。
    
- [设置 Windows 10 设备的应用程序保护设置](protection-settings-for-windows-10-devices.md)。 
    
    这些设置可以应用于上同时拥有公司，公司数据或个人拥有设备中。
    
- [设置 Windows 10 设备的设备保护设置](protection-settings-for-windows-10-pcs.md)。 
    
    您可以启用[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)加密以帮助保护数据，以防设备丢失或被盗，并启用[Windows 利用 Guard](https://go.microsoft.com/fwlink/p/?linkid=871404)提供高级的防范勒索软件。 
    
- [从设备中删除公司数据](remove-company-data.md)
    
    如果设备会丢失，盗，或员工离开公司，您可以远程擦除公司数据。
    
- [为出厂设置重置 Windows 10 设备](reset-devices-to-factory-settings.md)。 
    
    您可以重置具有设备保护设置应用于它们的任何 Windows 10 设备。
    
## <a name="additional-security-features"></a>其他安全功能 

Microsoft 365 企业版中的高级的功能均可用于帮助您保护您的企业网络威胁和保护敏感信息。
  
- **[Office 365 高级威胁防护](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    高级威胁保护 (ATP) 帮助保护您的业务复杂网络钓鱼和勒索软件攻击旨在损害员工或客户信息。功能包括：
    
  - 复杂的附件扫描和驱动 AI 分析检测并放弃危险的邮件。
    
  - 自动检查评估的电子邮件中的 web 链接它们是否网络钓鱼方案的一部分。这将保持您安全访问不安全的网站。
    
- **[数据丢失预防策略概述](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    您可以设置 DLP 自动检测敏感信息，如信用卡号、 社会保险号码等要阻止其无意共享到公司外线。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archiving 许可证允许与连续数据备份轻松存档邮件。它存储所有用户的电子邮件，包括已删除的项目，以防发现或还原需要更高版本。此外，您可以使用不同的保留策略，以保留的诉讼保留电子数据展示，电子邮件数据或满足合规性要求。
    
- **[Azure 信息保护](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    可以使用类似的控件来控制访问电子邮件和文档中的敏感信息的信息保护帮助"不转接"和"不复制。"您还可以进行分类"2 私有 3 机密"的敏感信息，并指定如何保密的信息可以共享外部和内部业务。企业级加密很容易适用于电子邮件和文档保护私人信息。Microsoft 365 业务包括[Azure 信息保护计划 1](https://go.microsoft.com/fwlink/p/?linkid=871407)的所有功能。您还可以安装 Azure 信息保护客户端外接程序 Office 应用程序。有关详细信息，请参阅[Azure 信息保护客户端管理员指南](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)。
    
- **[Intune 的 Azure 门户中的完整功能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    访问管理中心 Azure 门户中的允许您设置其他安全功能，如管理 MacOS 设备、 iPhone 和 Android 设备以及高级的设备管理的 Windows Intune 的不提供通过 Microsoft365 业务的管理中心。
    
以下各节介绍了安全中的这些功能的管理方式&amp;合规性中心和 Intune 管理中心。随着时间的推移简化的控件将添加到 Microsoft 365 业务管理中心。
  
## <a name="set-up-advanced-threat-protection-features"></a>设置高级威胁保护功能

- **Protect 针对不安全的附件：** ATP 标识通过在虚拟环境中打开电子邮件附件的恶意内容和执行分析的结果行为。内容进行评估，以确定其用途 （是否正常或恶意），然后 ATP 阻止传递不安全的附件，帮助您防御网络钓鱼方案和勒索软件病毒感染。若要激活附件保护，请参阅[Office 365 ATP 安全附件策略设置](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)。
    
- 当用户单击恶意链接保护您的环境： ATP 还在用户单击它们的时间检查电子邮件中的链接。如果不安全的链接，用户警告不以访问网站，或通知网站已被阻止。这有助于防止网络钓鱼方案。您还可以[设置 Office 365 ATP 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[Office 365 ATP 安全链接策略设置](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
## <a name="set-up-dlp-features"></a>设置 DLP 功能

有关如何设置策略防御个人身份信息 (PII) 的示例，请参阅[Create DLP 策略模板](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。 
  
DLP 附带了许多准备使用策略模板的许多不同的区域设置。例如，澳大利亚财务数据、 加拿大个人信息法案美国财务数据，等等。有关的完整列表，请参阅[什么 DLP 策略模板包括](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。所有这些模板可以启用类似于 PII 模板示例。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>与 Exchange Online Archiving 的电子邮件保留设置

 **Exchange Online Archiving**许可证功能为您提供帮助维护法规遵从性和规章标准保留电子邮件内容的电子数据展示的能力。此外有助于降低发生诉讼风险，并提供一种安全隐患后或当您需要恢复已删除的项目时恢复数据。若要激活这些功能，可以使用诉讼保留要保留的所有用户的内容，或保留策略用于更高版本的自定义。 
  
**诉讼保留：** 您可以保留所有邮箱内容，包括已删除的项目，通过将用户的整个邮箱置于诉讼保留。 
    
若要将邮箱置于诉讼保留状态，在管理中心中：
    
1. 在左侧导航窗格中，转到**用户** \> **活动用户**。
    
2. 选择的用户的邮箱您想要置于诉讼保留在用户窗格中，展开**邮件设置**和**其他设置**旁边选择**编辑 Exchange 属性**。
    
3. 在用户的邮箱页上，选择 * * 邮箱功能 * * 在左侧导航窗格中，然后选择**诉讼保留**下的**启用**链接。
    
4. 在**诉讼保留**对话框可以指定诉讼保留持续时间，在**诉讼保留持续时间**字段中，将字段保留为空，如果您要放置无限期保留。此外可以添加备注，并直接您可能需要解释更多有关诉讼保留的网站的邮件框所有者\>**保存**。
    
**保留：** 您可以启用自定义的保留策略，例如，若要保留特定时间段的或在保留期结束永久删除内容。若要了解详细信息，请参阅[Overview of 保留策略](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
## <a name="set-up-azure-information-protection-features"></a>设置 Azure 信息保护功能

Azure 信息保护 (AIP) 是一种基于云的解决方案，可以帮助组织分类和 （可选） 通过应用标签保护的文档和电子邮件。标签可以由管理员定义规则和条件，手动由用户或用户有建议组合自动应用。

对所有用户自动启用能够在 web 上的 Outlook 中发送电子邮件时应用以下限制：
  
- **不要转发**： 收件人可以阅读消息，但他们不能转发、 打印或复制内容
    
- **加密**： 对整个邮件进行加密。收件人必须采取额外的步骤来访问加密的内容之前，请确认他们的身份，并不能删除加密。
    
- **2 私有 3 机密**： 为您的组织中的员工提供完整的权限，对电子邮件内容和附件，但不适用于您的组织外部的人员。数据所有者可以跟踪，并取消任何时刻的内容。
    
- **高度机密**： 此限制可以应用于高度机密数据，以允许员工能够查看、 编辑和答复，但不是转发、 打印，或将数据复制。数据所有者可以跟踪，并取消任何时刻的内容。

### <a name="make-sure-azure-information-protection-is-activated"></a>请确保已激活 Azure 信息保护

若要验证 AIP 被激活：

1. 登录到[Azure Active Directory 管理中心](https://portal.azure.com/)。

    此外可以通过查找**管理中心**逼真中\>，在管理中心的左侧导航窗格中的**Azure Active Directory** 。

2. *Azure 信息保护*在**搜索框**中，选择**所有服务**和 tyoe。

3. 后显示结果，请单击开始下一步到**Azure 信息保护**，以使其成为收藏夹并可以轻松找到更高版本。

4. 选择**Azure 信息保护** \> **保护激活**，并确保将状态设置为激活。 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>查看 Azure 信息保护策略和默认标签 

若要查看和修改，现有标签：

1. 在 Azure 信息保护仪表板，选择**分类** \> * * 标签。 <br/>![Azure 信息保护标准标签。](media/AIPLabels.png)

2. 您可以选择任意标签，若要查看选项，您可以更改显示名称、 颜色等。
 
3. 请参阅[修改并创建新的标签](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)如果您想要创建您自己的。 

### <a name="install-the-azure-information-protection-client-manually"></a>手动安装 Azure 信息保护客户端

手动安装 AIP 客户端：

1. 从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载**AzInfoProtection.exe** 。
 
2. 您可以验证安装通过查看 Word 文档，并确保**保护**选项位于**主页**选项卡上运行。 <br/>![保护选项卡 Word 文档中的下拉列表。](media/Word_Protect.png)

有关详细信息，请参阅[安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)
    
## <a name="faq"></a>常见问题解答

 ### <a name="are-these-security-features-available-in-all-markets"></a>是否所有市场中提供这些安全功能？
  
是，这些功能出售 Microsoft 365 企业版的所有市场中都可用。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>如何查找安全&amp;合规性中心？
  
1. 通过使用管理员凭据[登录到 Microsoft 365 Business](https://portal.microsoft.com/) 。 
    
2. 在左侧导航窗格中，找到**管理中心**并展开该数字。 
    
    ![在 Microsoft 365 管理中心中左侧导航窗格中，选择管理中心。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. 选择**安全&amp;合规性**转到安全&amp;合规性中心。 
    
 ### <a name="how-do-i-find-the-intune-admin-center"></a>如何查找 Intune 管理中心？
  
  
1. 通过使用管理员凭据[登录到 Microsoft 365 Business](https://portal.microsoft.com/) 。 
    
2. 在左侧导航窗格中，找到**管理中心**并展开该数字。 
    
3. 选择**Intune**转到 Intune 管理中心。 
    

