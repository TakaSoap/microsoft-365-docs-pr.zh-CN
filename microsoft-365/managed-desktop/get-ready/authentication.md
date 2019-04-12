---
title: 为 Microsoft 托管桌面准备本地资源访问
description: 确保 Azure AD 可以与本地 AD 通信以提供身份验证的重要步骤
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824462"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备本地资源访问

在 Microsoft 托管桌面中, 设备会自动加入 Azure Active Directory。 这意味着, 如果您使用的是本地 active directory, 则必须检查一些事项, 以确保加入到 Azure AD 的设备可以与您的本地 active directory 进行通信。 

> [!NOTE]  
> *混合*Microsoft 托管桌面不支持 Azure AD 加入。

通过 Azure Active Directory, 用户可以利用单一登录 (SSO), 这意味着他们在每次想要执行某些操作时, 通常都不需要提供凭据。 如果你完全是 Azure active directory 的新内容, 请参阅 how [to: Plan a azure AD join 实现](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--但是, 在引用 azure Active Directory 文档时, 请记住 Microsoft 不支持*混合*Azure ad join托管桌面。


本主题介绍要检查的内容, 以确保依赖于本地 Active Directory 连接的应用和其他资源将在 Microsoft 托管桌面中正常运行。


> [!IMPORTANT]  
> 若要使用户能够在 Azure Active Directory 中注册设备并注册 Intune (Microsoft 托管桌面必需), 请按照[配置设备设置](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings)中的步骤操作, 然后再继续本主题的其余部分。


## <a name="single-sign-on-for-on-premises-resources"></a>本地资源的单一登录

默认情况下, 使用 UPN 或密码 (默认方法) 的设备的单一登录 (SSO) 应已生效。 但您也可以使用 Windows Hello 企业版, 这需要执行一些额外的设置步骤。 有关 sso 的背景信息, 请参阅[本地资源的 sso 在 Azure AD 联接设备上的工作原理](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)。


### <a name="single-sign-on-by-using-upn-and-passwords"></a>使用 UPN 和密码的单一登录

用户无需特殊设置即可通过 UPN 和密码进行身份验证--默认情况下, 你可以从 Azure 获取此设置。 但是, 为了确保这能够正常运行, 应仔细检查以下各项:

- 确认已使用运行 Windows server 2008 R2 或更高版本的本地 Active directory 服务器设置 Azure Active directory (AAD) 连接。
- AAD 连接运行受支持的版本, 并将其设置为将这三个关键属性与 Azure AD 同步: 
    - 用户在本地 Active Directory 中存在的 DNS 域的名称
    - 用户在本地 Active Directory 中存在的 NetBIOS 域名
    - SAM 帐户的用户名称


### <a name="sso-by-using-windows-hello-for-business"></a>使用 Windows Hello 企业版的 SSO

你也可以通过使用 Windows Hello 企业版, 为你的用户提供快速、passwordless 的体验。 若要对此进行设置, 请参阅[使用 Windows Hello 企业版上的本地单一登录配置 Azure AD 加入设备](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)以检查要求, 然后按照此处提供的步骤进行操作。


## <a name="apps-and-resources-that-use-authentication"></a>使用身份验证的应用程序和资源

请参阅了解 azure 内容集中[应用程序和资源的注意事项](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources), 以获取有关设置应用程序以与 Azure Active Directory 配合使用的完整指南。 摘要:


- 如果您使用**基于云的应用程序**(例如, 添加到 Azure AD 应用程序库中的应用程序), 则大多数不需要进一步准备使用 Microsoft 托管桌面。 但是, 任何不使用 Web 帐户管理器 (WAM) 的 Win32 应用 () {验证此首字母缩略词} 仍可能会提示用户进行身份验证。

- 对于**托管在本地**的应用程序, 请务必将这些应用添加到浏览器中的 "受信任的网站" 列表中。 这将使 Windows 身份验证能够无缝工作, 而不提示用户提供凭据。

- 如果使用的是 Active Directory 联合服务, 请按照[Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))中的步骤操作。 

- 对于**内部部署和使用较旧协议**的应用程序, 只要设备具有对本地域控制器的访问权限, 就不需要额外的设置。 但是, 若要提供对这些应用程序的安全访问, 应部署 Azure AD 应用程序代理。 有关详细信息, 请参阅[通过 Azure Active Directory 应用程序代理远程访问本地应用程序](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。

- 不支持**在本地运行和依赖计算机身份验证**的应用程序, 因此应考虑将它们替换为较新的版本。

## <a name="network-shares-that-use-authentication"></a>使用身份验证的网络共享

用户无需额外的设置即可访问网络共享, 只要这些设备具有使用 UNC 路径的本地域控制器的访问权限即可。

## <a name="printers"></a>打印机

虽然无法在仅云环境中自动发现打印机, 但您的用户也可以使用打印机的 UNC 路径直接添加它们。

<!--add fuller material on printers when available-->