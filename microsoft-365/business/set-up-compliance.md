---
title: 为 Microsoft 365 商业版增加威胁防护
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668375"
---
# <a name="set-up-compliance-features"></a>设置合规性功能

你的 Microsoft 365 业务提供了保护数据和设备的功能, 并帮助您保护您的用户和客户的敏感信息。

## <a name="set-up-dlp-features"></a>设置 DLP 功能

有关如何设置策略以防止个人身份信息 (PII) 的示例, 请参阅[从模板创建 DLP 策略](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。 
  
DLP 提供了许多不同区域设置的多种可供使用的策略模板。 例如, 澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。有关完整列表, 请参阅[DLP 策略模板包含的内容](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。 所有这些模板都可以像 PII 模板示例一样启用。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>使用 Exchange Online 存档设置电子邮件保留

 **Exchange Online 存档**许可证功能通过保留电子数据展示的电子邮件内容来帮助维护合规性和法规标准。 它还有助于在 lawsuit 事件中降低风险, 并提供了在安全破坏后或需要恢复已删除项目的情况下恢复数据的方法。 您可以使用诉讼保留来保留用户的所有内容, 或使用保留策略来自定义要保留的内容。
  
**诉讼保留:** 通过将用户的整个邮箱置于诉讼保留中, 可以保留所有邮箱内容 (包括已删除项目)。 
    
若要将邮箱置于诉讼保留状态, 请在管理中心:
    
1. 在左侧导航中, 转到 "**用户** \> **活动用户**"。
    
2. 选择要将其邮箱置于诉讼保留状态的用户, 并在用户窗格中展开 "**邮件设置**", 然后选择 "**其他设置**" 旁边的 "**编辑 Exchange 属性**"。
    
3. 在用户的 "邮箱" 页上, 在左侧导航中选择 "* * 邮箱功能 * *", 然后选择 "**诉讼保留**" 下的 "**启用**" 链接。
    
4. 在 "**诉讼保留**" 对话框中, 您可以在 "**诉讼保留持续时间**" 字段中指定诉讼保留期, 如果您想要设置无限保留, 则将字段留空。 您还可以添加注释, 并将邮箱所有者引导到网站, 您可能需要详细了解诉讼保留\> **保存**。
    
**保留:** 您可以启用自定义保留策略, 例如, 在保留期结束时保留特定时间或永久删除内容。 若要了解详细信息, 请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。

## <a name="set-up-azure-information-protection-features"></a>设置 Azure 信息保护功能

Azure 信息保护 (AIP) 通过应用标签帮助您分类和 (可选) 保护文档和电子邮件。 可以由管理员自动应用标签, 这些管理员定义规则和条件、手动按用户或通过使用用户提供建议的组合。

在 web 上的 Outlook 中, 您可以将以下内置标签和限制应用于您的电子邮件:
  
- **不转发**: 收件人可以阅读邮件, 但不能转发、打印或复制内容
    
- **加密**: 对整个邮件进行加密。 收件人在访问加密内容之前必须确认其标识, 并且无法删除加密。
    
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
