---
title: 创建组织范围内的签名和免责声明
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 管理电子邮件签名，包括进入或离开组织的所有电子邮件的法律免责声明或披露声明。
ms.openlocfilehash: d2e8b93825b98724bfd2698d95b93289dee30e00
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531179"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>创建组织范围内的签名和免责声明

 您可以通过向进入或离开组织的电子邮件添加电子邮件签名、法律免责声明或披露声明来管理电子邮件签名。 可将其设置为应用于所有待收和待发邮件，如下所示。 也可将其应用到某些邮件，例如包含特定字词或文本模式的邮件。

## <a name="watch-create-a-company-wide-email-signature"></a>观看：创建公司范围的电子邮件签名
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">"Microsoft 365 管理中心"</a>中，选择 **"Exchange"。**
1. 选择 **"邮件流"。**
1. 选择 **"添加 +**"，然后选择"**应用免责声明"。**
1. 在" **新建规则"** 页上，完成步骤。 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。

## <a name="create-a-signature-that-applies-to-all-messages"></a>创建一个应用于所有邮件的签名

> [!TIP]
> 组织范围内的签名称为"免责声明"，无论它们包含何种内容。 例如，它们只能是一个签名，也可以包括你的地址、法律免责声明或其他你需要的信息。
    
::: moniker range="o365-worldwide"

转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> 的管理中心。

::: moniker-end

1. 选择应用启动器 ![ 应用启动器图标 ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) 。，然后选择"管理员 **"。**
   
    找不到需要的应用？ 从应用启动器中，选择 **"** 所有应用"以查看可用应用的字母列表。 可在此处搜索特定应用。 
    
2. 选择 **"管理中心**"，然后选择 **"Exchange"。**
    
3. 在"邮件流"下，选择"**规则"。**
    
4. 选择 **+** " (添加) "图标，然后选择"**应用免责声明"。**
    
5. 为规则命名。
    
6. 在 **"应用此规则"** 下，选择 **"[应用于所有邮件]"。**
    
    > [!TIP]
    > [了解](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)有关应用条件的详细信息。  (此范围文章适用于Exchange Server，但它也适用于 Microsoft 365.)  
  
7. 在"执行以下操作"下，保留" **附加免责声明**"处于选中状态。 
    
8.  选择 **"输入文本** "并键入免责声明。 
    
    > [!TIP]
    > [深入了解](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)如何设置免责声明格式。  (本文适用于Exchange Server，但也适用于 Microsoft 365.)  

9. 选择 **"选择一** 个"，然后选择 **"自动** 换行"作为回退选项。 然后选择" **确定**"。 这意味着如果由于加密或其他邮件设置而无法添加免责声明，免责声明将封装在邮件信封中。
    
10. 保留" **用安全性级别审核此规则**"处于选中状态。然后选择要在邮件日志中使用的" **低**"、" **中**"或" **高**"。 
    
11. 选择" **强制使用**"，立即打开免责声明，除非需要首先进行测试。 
    
12. 选择" **更多选项**"，以包含其他条件或例外。 
    
13. 完成后，选择" **保存**"。 
    
## <a name="limitations-of-organization-wide-signatures"></a>组织范围签名的限制

在管理电子邮件签名时，不能执行以下操作Microsoft 365：
  
- 直接在最新电子邮件回复或转发下插入签名
    
- 在用户的"已发送项目"文件夹中显示服务器端电子邮件签名
    
- 在电子邮件签名中嵌入图像
    
- 跳过包含无法更新的变量 (例如，由于未为用户或用户提供) 
    
若要获得这些和管理电子邮件签名的其他功能，请使用第三方工具。 请对电子邮件签名软件 **执行 Internet 搜索**。 许多提供商是 Microsoft 金牌合作伙伴，其软件提供这些功能。 
  
## <a name="more-resources"></a>更多资源

有关使用 PowerShell 的信息，请参阅组织范围内的邮件免责声明、签名、页脚或[Exchange Online。](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

## <a name="related-content"></a>相关内容

[将电子邮件和联系人迁移到Microsoft 365 (](migrate-email-and-contacts-admin.md)视频) \
[用户电子邮件设置](../email/office-365-user-email-settings.md) (文章) \
[概述Microsoft 365 管理中心] (概述Microsoft 365 管理中心] (。/admin-overview/admin-center-overview.md)  (视频) 

