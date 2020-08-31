---
title: 重置密码
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- TopSMBIssues
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: '了解如何在 Microsoft 365 for business 订阅中重置用户的密码。 '
ms.openlocfilehash: 6159b62cb6c1e09cb86732cc27cc4c4c87328a42
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307285"
---
# <a name="reset-passwords"></a>重置密码

观看有关重置用户密码的简短视频。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。
  
## <a name="let-users-reset-their-own-passwords"></a>允许用户重置自己的密码

强烈建议设置自助服务密码重置。通过此方式，无需为用户手动重置密码。若要了解操作方式，请参阅[允许用户在 Office 365 中重置其密码](let-users-reset-passwords.md)。
  
## <a name="reset-a-business-password-for-someone-else"></a>重置其他人的业务密码

这些步骤仅适用于使用 Microsoft 365 for business plan 的人员。 若要执行此操作，您需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../admin-overview/admin-overview.md)

 
::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 在 " **活动用户** " 页上，选择该用户，然后选择 " **重置密码**"。
    
3. 按照 " **重置密码** " 页上的说明操作，为用户自动生成一个新密码或为其创建一个新密码，然后选择 " **重置**"。  
    
4. 输入用户可访问的电子邮件地址，以便他们接收新密码，并跟踪它们以确保其获得。
 
  
## <a name="reset-my-admin-password"></a>重置管理员密码

如果您忘记了密码但可以登录到 Microsoft 365，请使用这些步骤，因为例如，您的密码保存在浏览器中： 
    
1. 选择您的姓名 (图标) 在 **"我的帐户**  >  **个人信息**" 的右上角 >。 
          
2. 在 " **联系人详细信息**" 下，仔细检查你的 **备用电子邮件** 是否准确，以及你是否提供了移动电话号码。 如果不是，请立即更改。 
        
3. 注销：在上面的图像中的右上角选择您的姓名 () "注销" 中显示为 " **Diane** " \> **Sign out**。 
        
4. 现在再次登录：在 \> **下一步**键入您的用户名 \> ，然后选择 " **忘记了密码**"。 
    
5. 按照向导中的步骤重置密码。 它使用您的备用联系人信息来验证您是否是正确的重置密码的人。 
    
如果你忘记了密码，但无法登录： 
    
- 请求企业中的其他全局管理员为您重置密码。

- 请确保您已提供备用联系人信息，包括移动电话号码。 
    
- 或者，请 [致电 Microsoft 支持部门](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)。 
    
## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>同时为组织中的所有人重置所有业务密码
<a name="bkmk_forgot"> </a>

这些步骤适用于拥有数十位用户的企业。 如果你有成百上千个用户，请参阅下一节：批量重置密码 (最多为40个用户一次) 。
  
1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
    
2. 选择 " **显示名称** " 旁边的选项以选择您的企业中的所有人。 然后取消选中你自己。 重置其他所有用户的密码时无法重置自己的密码。
    
3. 选择 " **重置密码**"。 

4. 按照 " **重置密码** " 页上的说明操作，然后选择 " **重置**"。  如果选择自动生成密码，则将显示新的临时密码。   
    
5. 输入可在其中接收临时密码的电子邮件地址。 你需要向用户通知其临时密码。
    

  
## <a name="reset-business-passwords-in-bulk"></a>批量重置业务密码
<a name="bkmk_forgot"> </a>

使用 PowerShell! 请查看这篇由 Eyal Doron 发表的文章：[使用 PowerShell 管理密码](https://go.microsoft.com/fwlink/?linkid=853696)。
  
相关文章：[为多个用户帐户设置密码](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。
  
有关概述信息，请参阅 [PowerShell For Microsoft 365 administrators](https://support.microsoft.com/office/40fdcbd4-c34f-42ab-8678-8b3751137ef1)。
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>为企业中的所有用户强制更改密码
<a name="bkmk_forgot"> </a>

请参阅这篇由 Microsoft MVP Vasil Michev 撰写的出色博客文章：[为 Office 365 中的所有用户强制更改密码](https://go.microsoft.com/fwlink/?linkid=853693)。
  
## <a name="im-lost"></a>我迷惑了！
<a name="bkmk_forgot"> </a>

请尝试阅读此文：[我忘记了 Office 所用的帐户用户名或密码。](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-articles"></a>相关文章
<a name="bkmk_forgot"> </a>
  
[允许用户重置自己的密码](let-users-reset-passwords.md)

[将个人用户密码设置为永不过期](set-password-to-never-expire.md)

[为组织设置密码过期策略](../manage/set-password-expiration-policy.md)

[还原用户](restore-user.md)

[删除以前的员工](remove-former-employee.md)

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
