---
title: 创建组织范围的签名和免责声明
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 了解如何向进入或离开组织的所有电子邮件添加电子邮件签名、法律免责声明或泄露声明。
ms.openlocfilehash: a63f21dff90c70d39e3709d4c34b53d99a315a59
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42360663"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>创建组织范围的签名和免责声明

 可向发送到组织或从组织发出的电子邮件添加电子邮件签名、法律免责声明或公开声明。可将其设置为应用于所有待收和待发邮件，如下所示。也可将其应用到某些邮件，例如包含特定字词或文本模式的邮件。

 观看有关创建公司范围的电子邮件签名的简短视频。 <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="create-a-signature-that-applies-to-all-messages"></a>创建一个应用于所有邮件的签名

> [!TIP]
> 组织范围内的签名称为 "免责声明"，无论它们包括什么。 例如，它们可以只是一个签名，也可以包括您的地址、法律免责声明或所需的其他信息。
    
::: moniker range="o365-worldwide"

转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

::: moniker-end

::: moniker range="o365-germany"

转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> 的管理中心。

::: moniker-end

1. 选择 Office 365](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)中![的应用启动器图标，然后选择 "**管理员**"。
   
    找不到需要的应用？从应用启动器中，选择“**所有应用**”，以查看可供使用的 Office 365 应用的列表（按字母顺序排列）。可在此处搜索特定应用。 
    
2. 选择 "**管理中心**"，然后选择 " **Exchange**"。
    
3. 在 "邮件流" 下，选择 "**规则**"。
    
4. 选择 " **+** （添加）" 图标，然后选择 "**应用免责声明**"。
    
5. 为规则命名。
    
6. 在 "**应用此规则**" 下，选择 " **[应用于所有邮件]**"。
    
    > [!TIP]
    > [了解](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)有关应用条件的详细信息。 （此范围文章适用于 Exchange Server，但也适用于 Office 365。） 
  
7. 在"执行以下操作"下，保留" **附加免责声明**"处于选中状态。 
    
8.  选择 "**输入文本**"，然后键入免责声明。 
    
    > [!TIP]
    > [深入了解](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)如何设置免责声明格式。 （此格式文章适用于 Exchange Server，但也适用于 Office 365。） 

9. 选择 "**选择一个**"，然后选择 "**包装**为回退" 选项。 然后选择" **确定**"。 这意味着如果由于加密或其他邮件设置而无法添加免责声明，免责声明将封装在邮件信封中。
    
10. 保留" **用安全性级别审核此规则**"处于选中状态。然后选择要在邮件日志中使用的" **低**"、" **中**"或" **高**"。 
    
11. 选择" **强制使用**"，立即打开免责声明，除非需要首先进行测试。 
    
12. 选择" **更多选项**"，以包含其他条件或例外。 
    
13. 完成后，选择" **保存**"。 
    
## <a name="limitations-of-office-365-organization-wide-signatures"></a>Office 365 组织的全球签名的限制

您不能对 Office 365 签名执行以下操作：
  
- 直接在最新电子邮件答复或转发下插入签名
    
- 在用户的 "已发送邮件" 文件夹中显示服务器端电子邮件签名
    
- 在电子邮件签名中嵌入图像
    
- 跳过包含无法更新的变量的行（例如，由于没有为用户提供此值）
    
若要获取这些功能和其他功能，请使用第三方工具。 请为**电子邮件签名软件**执行 internet 搜索。 许多提供商是 Microsoft 金牌合作伙伴，其软件提供这些功能。 
  
## <a name="more-resources"></a>更多资源

- 有关使用 PowerShell 的信息，请参阅[组织范围内的邮件免责声明、签名、页脚或在 Office 365 中的标题](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)。 
    

