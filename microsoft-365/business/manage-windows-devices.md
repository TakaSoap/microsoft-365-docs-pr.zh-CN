---
title: 启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 以保护本地 AD 加入 Windows 10 设备。
ms.openlocfilehash: 452e884f952a4b2c2e87148bb7203ed48a48d944
ms.sourcegitcommit: 3a632d8ec009abf1aac57363eaf78aeeda5db136
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37376087"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备

如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。
若要进行此设置，您可以实现**混合的 AZURE AD 加入的设备**。 这些是同时连接到本地 Active Directory 和 Azure Active Directory 的设备。

下面的视频详细介绍了如何对此进行设置，以了解在以下步骤中也详细介绍的最常见方案。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. 准备目录同步 

在将用户和计算机从本地 Active Directory 域同步之前，请查看 "[准备将目录同步到 Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)"。 具体而言：

   - 确保目录中不存在以下属性的重复项： **mail**、 **proxyAddresses**和**userPrincipalName**。 这些值应是唯一的，并且应删除任何重复项。
   
   - 建议将每个本地用户帐户的**userPrincipalName** （UPN）属性配置为与与许可的 Microsoft 365 用户相对应的主电子邮件地址相匹配。 例如*mary.shelley@contoso.com* ，而不是*mary @ contoso. 本地*
   
   - 如果 Active Directory 域以不可路由的后缀（如*local*或*lan*）结尾，而不是 internet 路由后缀（如 .com 或 *. org*），则需要先按照中所述调整本地用户帐户的 UPN 后缀，如中所述 *。*[为目录同步准备不可路由的域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)。 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安装和配置 Azure AD Connect

若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory 中，请安装 Azure Active Directory Connect 并设置目录同步。 若要了解详细信息，请参阅[设置 Office 365 的目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。

> [!NOTE]
> 对于 Microsoft 365 商业版的步骤完全相同。 

在为 Azure AD Connect 配置选项时，我们建议启用**密码同步**和**无缝单一登录**，以及 Microsoft 365 商业版中也支持的**密码写回**功能。

> [!NOTE]
> 除了 Azure AD Connect 中的复选框之外，还需要执行一些额外的密码写回步骤。 有关详细信息，请参阅[操作方法：配置密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. 配置混合 Azure AD 加入

在将 Windows 10 设备设置为混合使用 Azure AD 之前，应确保满足以下先决条件：

   - 您运行的是最新版本的 Azure AD connect。

   - Azure AD connect 已同步要连接混合 Azure AD 的设备的所有计算机对象。 如果计算机对象属于特定的组织单位（OU），请确保将这些 Ou 设置为在 Azure AD connect 中进行同步。

若要将现有的加入域的 Windows 10 设备注册为已加入混合的 Azure AD，请按照教程中的步骤[操作： Configure Managed Azure Active Directory join for managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)domain。 这将混合启用现有的本地 Active Directory 加入 Windows 10 计算机，并将其设置为云就绪。
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. 为 Windows 10 启用自动注册

 若要在 Intune 中自动注册移动设备管理的 Windows 10 设备，请参阅[使用组策略自动注册 windows 10 设备](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)。 你可以在本地计算机级别或批量操作中设置组策略，可以使用组策略管理控制台和 ADMX 模板在域控制器上创建此组策略设置。

## <a name="5-configure-seamless-single-sign-on"></a>5. 配置无缝单一登录

  在使用企业计算机时，无缝 SSO 将自动将用户登录到其 Microsoft 365 云资源。 只需部署[Azure Active Directory 无缝单一登录：快速入门](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)中介绍的两个组策略选项之一即可。 **组策略**选项不允许用户更改其设置，而**组策略首**选项设置值，但也将其保留为用户可配置的。

## <a name="6-set-up-windows-hello-for-business"></a>6. 设置 Windows Hello 企业版

 Windows Hello 企业版将使用强双重身份验证（2FA）替换密码，以登录到本地计算机。 一个因素是非对称密钥对，另一个是 PIN 或其他本地手势（如指纹或面部识别）（如果设备支持）。 我们建议您在可能的情况下将密码替换为2FA 和 Windows Hello 企业版。

若要配置混合 Windows Hello 企业版，请查看[混合密钥信任 Windows Hello 企业版先决条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)。 然后按照[配置混合 Windows Hello For Business 密钥信任设置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)中的说明操作。 
