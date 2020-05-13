---
title: 为用户设置多重身份验证
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
description: 了解如何使用安全性默认值为用户设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213006"
---
# <a name="set-up-multi-factor-authentication"></a>设置多重身份验证
  
> [!IMPORTANT]
> 如果你在2019年10月21日之后购买了订阅或试用，并且意外提示了多重身份验证（MFA），则已为你的订阅自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

每个新 Microsoft 365 订阅将自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 这意味着，每个用户都必须设置多重身份验证（MFA），并在其移动设备上安装 Microsoft 身份验证器应用程序。 有关详细信息，请参阅为[Microsoft 365 帐户设置 MFA](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。

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

必要时，系统将要求其他所有用户执行额外的身份验证。

> [!NOTE]
> 您必须是全局管理员才能设置或修改 MFA <br><br>
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

如果您以前设置了具有基准策略的 MFA，[则必须将其关闭以启用安全默认](#move-from-baseline-policies-to-security-defaults)设置。 但是，如果你拥有 Microsoft 365 业务或你的订阅包括[Azure Active Directory 高级 P1 或 Azure Active Directory 高级 P2](https://azure.microsoft.com/pricing/details/active-directory/)，则还可以设置[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略。 若要使用条件访问策略，您需要确保禁用安全默认设置并启用[新式验证](#enable-modern-authentication-for-your-organization)。

> [!TIP]
> 若要向您的用户说明如何设置 Microsoft 身份验证器应用程序，请参阅[使用 Microsoft 身份验证器与 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)。

## <a name="manage-security-defaults"></a>管理安全性默认值

1. 使用全局管理员凭据登录[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。
2. 转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
3. 在页面底部，选择“**管理安全性默认值**”。
4. 选择 **"是"** 启用安全默认设置，单击 "**否**" 禁用安全默认设置，然后选择 "**保存**"。

## <a name="move-from-baseline-policies-to-security-defaults"></a>从基线策略改为安全性默认值

1. 转到 "[条件访问策略" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2. 选择启用的每个基准策略，并将 "**启用策略**" 设置为 "**关闭** **"** 。
3. 转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4. 在页面底部，选择 "**管理安全性默认**设置"，然后在 "**启用安全性**默认设置" 窗格中，将 "**启用安全默认**设置" 切换为 **"是**"，然后选择 "**保存**"。 

## <a name="enable-modern-authentication-for-your-organization"></a>为你的组织启用新式验证

所有 Office 2016 客户端应用程序均通过使用 Active Directory 身份验证库 (ADAL) 支持 MFA。 这意味着 Office 2016 客户端无需应用密码。 有关详细信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)。

但是，您需要确保为您的 Microsoft 365 订阅启用 ADAL 或新式验证。

1. 若要启用新式验证，请在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内依次选择“设置”****\>“设置”****，然后从“服务”**** 选项卡中的列表内选择“新式验证”****。

2. 选中**新式验证**面板中的 "**启用新式验证（推荐）** " 框，然后选择 "**保存更改**"。 

    ![在“新式验证”面板中已选中启用复选框。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> 从2017年8月起，所有新的包含 Skype for Business online 和 Exchange online 的 Microsoft 365 订阅默认启用新式身份验证。 若要检查 Skype for Business Online 的新式验证状态，请通过全局管理员凭据使用 Skype for Business Online PowerShell。 运行 Get-CsOAuthConfiguration 可检查 -ClientADALAuthOverride 的输出。 如果 -ClientADALAuthOverride 的输出为“Allowed”，表明新式验证处于开启状态。
若要查看 Exchange Online 的 MA 状态，请访问[在 Exchange Online 中启用新式身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

## <a name="related-articles"></a>相关文章

[保护 Microsoft 365 商业版计划的十大方法](secure-your-business-data.md)

[在 Windows 设备上启用适用于 Office 2013 的新式验证](enable-modern-authentication.md)
