---
title: 为 Office 365 用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何使用安全性默认值为 Office 365 用户设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 914d01bf2f045c6752aba4f2df3a204c6a21d09c
ms.sourcegitcommit: 4d4d27a49eb258dc560439ca4baf61ebb9c1eff3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2020
ms.locfileid: "43075604"
---
# <a name="set-up-multi-factor-authentication"></a>设置多重身份验证
  
> [!IMPORTANT]
> 如果你在2019年10月21日之后购买了订阅或试用，并且意外提示您进行 MFA，则已为你的订阅自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

每个新的 Office 365 商业版或 Microsoft 365 商业版订阅都将自动启用安全性默认值。 这意味着每位用户都必须在其移动设备上设置多重身份验证 (MFA) 并安装 Authenticator 应用。 有关详细信息，请参阅[为 Office 365 设置双重验证](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。  

下面九种管理员角色每次登录时都需要执行额外的身份验证：
- 全局管理员
- SharePoint 管理员
- Exchange 管理员
- 条件访问管理员
- 安全管理员
- 支持管理员/密码管理员
- 计费管理员
- 用户管理员
- 身份验证管理员

必要时，系统将要求其他所有用户执行额外的身份验证。 有关详细信息，请参阅[什么是安全性默认值？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> 必须是 Office 365 全局管理员才能设置或修改多重身份验证。 <br><br>
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

如果之前使用基线策略设置了 MFA，则[必须将其关闭，再打开安全性默认值](#move-from-baseline-policies-to-security-defaults)。 但是，如果你有 Microsoft 365 商业版，或者你的订阅包含 [Azure Active Directory Premium 1 或 Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)，则你还可设置[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略。 若要使用条件访问策略，需要确保已启用[新式身份验证](#enable-modern-authentication-for-your-organization)。

> [!TIP]
> 若要向你的用户说明如何设置 Authenticator 应用，请访问[将 Microsoft Authenticator 用于 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)。

## <a name="manage-security-defaults"></a>管理安全性默认值

1. 使用全局管理员凭据登录[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。
2. 转到 [Azure Active Directory 属性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。

3. 在页面底部，选择“**管理安全性默认值**”。
4. 选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值。

## <a name="move-from-baseline-policies-to-security-defaults"></a>从基线策略改为安全性默认值

1. 在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)中，选择“**设置**”。

2. 在“**登录和安全**”旁边，**使登录更安全**下，选择“**查看**”。

3. 在“**使登录更安全**”下，选择“**管理**”。 

4. 在“** 门户条件访问 - 策略**”页面上，选择已**启用**的每项基线策略并将其设置为“**关**”。
5. 转到 [Azure Active Directory 属性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)页面。
6. 在页面底部，选择“**管理安全性默认值**”，再在“**启用安全性默认值**”窗格中，将“**启用安全性默认值**”开关设置为“**是**”。 

## <a name="enable-modern-authentication-for-your-organization"></a>为你的组织启用新式验证

所有 Office 2016 客户端应用程序均通过使用 Active Directory 身份验证库 (ADAL) 支持 MFA。 这意味着 Office 2016 客户端无需应用密码。 但是，需要确保为 Office 365 订阅启用了 ADAL 或新式验证。

1. 若要启用新式验证，请在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内依次选择“设置”****\>“设置”****，然后从“服务”**** 选项卡中的列表内选择“新式验证”****。

2. 选中“**新式验证**”面板中的“**启用新式验证**”框。 

    ![在“新式验证”面板中已选中启用复选框。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 自 2017 年 8 月起，包括 Skype for Business Online 和 Exchange Online 在内的所有新 Office 365 租户都默认启用新式验证。 若要检查 Skype for Business Online 的新式验证状态，请通过全局管理员凭据使用 Skype for Business Online PowerShell。 运行 Get-CsOAuthConfiguration 可检查 -ClientADALAuthOverride 的输出。 如果 -ClientADALAuthOverride 的输出为“Allowed”，表明新式验证处于开启状态。
若要查看 Exchange Online 的 MA 状态，请访问[在 Exchange Online 中启用新式身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

## <a name="related-articles"></a>相关文章

[确保 Office 365 和 Microsoft 365 商业版计划安全的十大方法](secure-your-business-data.md)

[在 Windows 设备上启用适用于 Office 2013 的新式验证](enable-modern-authentication.md)
