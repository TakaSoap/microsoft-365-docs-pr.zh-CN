---
title: 为 Microsoft 365 商业版用户设置高级安全策略
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 设置 Office 365 高级威胁防护, 并保护敏感数据。
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663626"
---
# <a name="set-up-advanced-security-policies"></a>设置高级安全策略

除了可在[管理中心](security-features.md#microsoft-365-business-admin-center-security-features)中设置的策略之外, 还可以通过设置[Office 365 高级威胁防护](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)(ATP) 来添加针对网络威胁的额外保护。 您还可以通过设置[数据丢失防护](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP)、Azure 信息保护 (AIP)、 [Exchange Online 存档](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)以及在[Intune 门户](#go-to-intune-admin-center)中管理设备来保护敏感信息。

请参阅[前10种保护 Microsoft 365 业务计划的方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), 概述了保护业务的最重要方式, 包括使用 MFA 创建第二种登录窗体。

请参阅[保护您的业务培训视频](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787), 获取易于遵循说明的说明。

## <a name="increase-email-malware-protection"></a>增加电子邮件恶意软件保护

恶意软件是一种软件, 它可能会损坏计算机或网络, 并且可能会窃取您的数据, 包括个人或客户信息。 Microsoft 365 业务包括针对恶意软件保护的基准级别, 但你可以通过设置其他设置来提高此保护。 有关说明, 请参阅[启用恶意软件检测](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)培训视频。

## <a name="set-up-advanced-threat-protection-features"></a>设置高级威胁防护功能

- 防御**不安全附件:** ATP 通过在虚拟环境中打开电子邮件附件并对生成的行为进行分析来识别恶意内容。 对内容进行评估, 以确定其目的 (无论是正常还是恶意), ATP 会阻止传输不安全的附件, 从而帮助您抵御网络钓鱼骗术和勒索软件感染。 若要激活附件保护, 请参阅[设置 Office 365 ATP 安全附件](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)帮助文档, 并[防止恶意文件](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)较短的培训视频。
    
- **当用户单击恶意链接时保护您的环境:** ATP 还会在用户单击时检查电子邮件中的链接。 如果链接不安全, 则会警告用户不会访问网站, 或通知用户网站已被阻止。 这有助于防止仿冒骗术。 若要激活此设置, 请参阅[设置 Office 365 ATP 安全链接](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)帮助文档, 并[防止恶意网站](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)进行简短的培训视频。

- **保护你的环境免受仿冒网站的攻击:** ATP 反网络钓鱼对传入的邮件应用一组计算机学习模式和模拟检测算法, 以防止有人尝试从你的网络中提取信息, 因为它通过假装成为已知信息. 若要激活此设置, 请参阅[设置 ATP 反网络钓鱼](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies)帮助文档, 并[防止网络钓鱼尝试](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)进行简短的培训视频。

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

有关详细信息, 请参阅[安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。

## <a name="go-to-intune-admin-center"></a>转到 Intune 管理中心

1. 登录到[Azure 门户](https://portal.azure.com/)。

2. 在 "**搜索" 框**中选择 "**所有服务**", 然后键入*Intune* 。

3. 显示结果后, 单击 " **Microsoft Intune** " 旁边的 "开始", 使其成为收藏, 以便稍后查找。

除了管理中心之外, 你还可以使用 Intune 注册和管理你的组织的设备。 有关详细信息, 请参阅[Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和由[Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。

## <a name="microsoft-secure-score"></a>Microsoft 安全功能分数

