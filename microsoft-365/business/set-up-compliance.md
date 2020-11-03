---
title: 为 Microsoft 365 商业高级版增加威胁防护
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 设置合规性功能以防止数据丢失，并帮助保护您的客户和客户的敏感信息。
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841165"
---
# <a name="set-up-compliance-features"></a>设置合规性功能

你的 Microsoft 365 商业高级版附带了保护数据和设备的功能，可帮助您保持和客户的敏感信息安全。

## <a name="set-up-dlp-features"></a>设置 DLP 功能

请参阅 [从模板创建 DLP 策略](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) ，以获取有关如何设置策略以防止个人数据丢失保护的示例。 
  
DLP 提供了许多不同区域设置的多种可供使用的策略模板。 例如，澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。 有关完整列表，请参阅 [DLP 策略模板包含的内容](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) 。 所有这些模板都可以像 PII 模板示例一样启用。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>使用 Exchange Online 存档设置电子邮件保留

 **Exchange Online 存档** 许可证功能通过保留电子数据展示的电子邮件内容来帮助维护合规性和法规标准。 它还有助于降低风险（如果有 lawsuit），并提供了在安全破坏或需要恢复已删除项目的情况下恢复数据的方法。 您可以使用诉讼保留来保留用户的所有内容，或使用保留策略来自定义要保留的内容。
  
**诉讼保留：** 通过将用户的整个邮箱置于诉讼保留中，可以保留所有邮箱内容（包括已删除项目）。 
    
若要将邮箱置于诉讼保留状态，请在管理中心：
    
1. 在左侧导航中，转到 " **用户** \> **活动用户** "。
    
2. 选择要将其邮箱置于诉讼保留状态的用户。 在 "用户" 窗格中，展开 " **邮件设置** "，然后在 " **其他设置** " 旁边，选择 " **编辑 Exchange 属性** "。
    
3. 在用户的 "邮箱" 页上，在左侧导航中选择 "* * 邮箱功能 * *"，然后选择 " **诉讼保留** " 下的 " **启用** " 链接。
    
4. 在 " **诉讼保留** " 对话框中，可以在 " **诉讼保留持续时间** " 字段中指定诉讼保留期限。 如果要放置无限保留，请将该字段留空。 您还可以添加注释，并将邮箱所有者定向到网站，您可能需要详细了解诉讼保留。 \>**保存** 。
    
**保留：** 您可以启用自定义保留策略，例如，在保留期结束时保留特定时间或永久删除内容。 若要了解详细信息，请参阅 [保留策略概述](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。

## <a name="set-up-sensitivity-labels"></a>设置敏感度标签

敏感度标签随附有 Azure 信息保护 (AIP) 计划1，并通过应用标签来帮助您对文档和电子邮件进行分类，并可选择对其进行保护。 可以由管理员自动应用标签，这些管理员定义规则和条件、手动按用户或通过使用用户提供建议的组合。

若要设置敏感度标签，请查看 [创建和管理敏感度标签](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 视频。



### <a name="install-the-azure-information-protection-client-manually"></a>手动安装 Azure 信息保护客户端

若要手动安装 AIP 客户端：

1. 从 [Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载 **AzinfoProtection_UL.exe** 。
 
2. 您可以通过查看 Word 文档，并确保 " **开始** " 选项卡上的 " **敏感度** " 选项可用来验证安装是否正常进行。
<br/>![Word 文档中的 "保护" 选项卡下拉箭头。](../media/word-sensitivity.png)

有关详细信息，请参阅 [安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。
