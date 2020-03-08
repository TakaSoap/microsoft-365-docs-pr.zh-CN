---
title: 启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备
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
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 以仅在几个步骤中保护本地的 Active Directory 加入 Windows 10 设备。
ms.openlocfilehash: 625eb7ac344b060409101d650ff30044d073f5bf
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561452"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备

如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。
若要设置此保护，可以实现**混合 AZURE AD 加入的设备**。 这些设备将加入本地 Active Directory 和 Azure Active Directory。

本视频介绍了有关如何针对最常见方案对此进行设置的步骤，在下面的步骤中也将对此进行详细介绍。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. 准备目录同步 

在将用户和计算机从本地 Active Directory 域同步之前，请查看 "[准备将目录同步到 Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)"。 具体而言：

   - 请确保目录中不存在以下属性的重复项： **mail**、 **proxyAddresses**和**userPrincipalName**。 这些值必须是唯一的，并且必须删除任何重复的值。
   
   - 我们建议您为每个本地用户帐户配置**userPrincipalName** （UPN）属性，以匹配与许可的 Microsoft 365 用户对应的主电子邮件地址。 例如： *mary.shelley@contoso.com*而不是*mary@contoso。本地*
   
   - 如果 Active Directory 域以不可路由的后缀（如*local*或*lan*）结尾，而不是 internet 路由后缀（如 *.com*或 *. org*），请先按照为[目录同步准备不可路由的域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)中所述的步骤调整本地用户帐户的 UPN 后缀。 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安装和配置 Azure AD Connect

若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory 中，请安装 Azure Active Directory Connect 并设置目录同步。 若要了解详细信息，请参阅[设置 Office 365 的目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。

> [!NOTE]
> 对于 Microsoft 365 商业版的步骤完全相同。 

在为 Azure AD Connect 配置选项时，我们建议您启用**密码同步**、**无缝单一登录**和**密码写回**功能，这在 Microsoft 365 商业版中也受支持。

> [!NOTE]
> 除了 Azure AD Connect 中的复选框之外，还需要执行一些额外的密码写回步骤。 有关详细信息，请参阅[操作方法：配置密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. 配置混合 Azure AD 加入

在将 Windows 10 设备启用成混合的 Azure AD 之前，请确保满足以下先决条件：

   - 您运行的是最新版本的 Azure AD Connect。

   - Azure AD connect 已同步要连接混合 Azure AD 的设备的所有计算机对象。 如果计算机对象属于特定的组织单位（OU），请确保将这些 Ou 设置为在 Azure AD connect 中进行同步。

若要将现有的加入域的 Windows 10 设备注册为已加入混合的 Azure AD，请按照教程中的步骤[操作： Configure Managed Azure Active Directory join for managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)domain。 这种混合-使现有的本地 Active Directory 加入了 Windows 10 计算机并将其设置为云就绪。
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. 为 Windows 10 启用自动注册

 若要在 Intune 中自动注册移动设备管理的 Windows 10 设备，请参阅[使用组策略自动注册 windows 10 设备](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)。 您可以在本地计算机级别或批量操作中设置组策略，您可以使用组策略管理控制台和 ADMX 模板在域控制器上创建此组策略设置。

## <a name="5-configure-seamless-single-sign-on"></a>5. 配置无缝单一登录

  在使用企业计算机时，无缝 SSO 会自动将用户登录到其 Microsoft 365 云资源。 只需部署[Azure Active Directory 无缝单一登录：快速入门](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)中介绍的两个组策略选项之一即可。 **组策略**选项不允许用户更改其设置，而**组策略首**选项设置值，但也将其保留为用户可配置的。

## <a name="6-set-up-windows-hello-for-business"></a>6. 设置 Windows Hello 企业版

 Windows Hello 企业版将使用强双重身份验证（2FA）替换密码，以登录到本地计算机。 一个因素是非对称密钥对，另一个是 PIN 或其他本地手势（如指纹或面部识别）（如果设备支持）。 我们建议您在可能的情况下将密码替换为2FA 和 Windows Hello 企业版。

若要配置混合 Windows Hello 企业版，请查看[混合密钥信任 Windows Hello 企业版先决条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)。 然后按照[配置混合 Windows Hello For Business 密钥信任设置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)中的说明操作。 
