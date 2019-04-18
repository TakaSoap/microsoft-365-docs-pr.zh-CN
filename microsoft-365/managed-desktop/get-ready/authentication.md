---
title: 为 Microsoft 托管桌面准备本地资源访问
description: 确保 Azure AD 可以与本地 AD 通信以提供身份验证的重要步骤
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: db52a11eb192a28dbec827c565e36ad4a81d8e3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901206"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备本地资源访问

在 Microsoft 托管桌面中, 设备会自动加入 azure Active Directory (azure AD)。 这意味着, 如果您使用的是本地 active directory, 则必须检查一些事项, 以确保加入到 Azure AD 的设备可以与您的本地 active directory 进行通信。 

> [!NOTE]  
> *混合*Microsoft 托管桌面不支持 Azure AD 加入。

通过 Azure Active Directory, 用户可以利用单一登录 (SSO), 这意味着在每次使用资源时, 他们通常不需要提供凭据。

有关加入 azure Active Directory 的信息, 请参阅 how [to: Plan a azure AD join 实现](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。 有关加入到 azure ad 的设备上的单一登录 (sso) 的背景信息, 请参阅[本地资源的 SSO 在 Azure ad 联接设备上的工作原理](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)。


本主题介绍要检查的内容, 以确保依赖于本地 Active Directory 连接的应用和其他资源将在 Microsoft 托管桌面中正常运行。


## <a name="single-sign-on-for-on-premises-resources"></a>本地资源的单一登录

默认情况下, 使用 UPN 和密码的单一登录 (SSO) 在 Microsoft 托管桌面设备上启用。 但您的用户也可以使用 Windows Hello 企业版, 这需要执行一些额外的设置步骤。 

### <a name="single-sign-on-by-using-upn-and-password"></a>使用 UPN 和密码的单一登录

在大多数组织中, 用户将能够使用 SSO 在 Microsoft 托管桌面设备上通过 UPN 和密码进行身份验证。 但是, 为了确保这能够正常运行, 应仔细检查以下各项:

- 确认已设置 Azure AD Connect 并使用运行 Windows server 2008 R2 或更高版本的本地 Active Directory 服务器。
- 确认 azure ad Connect 运行的是受支持的版本, 并将其设置为将这三个属性与 Azure ad 同步: 
    - 内部部署 Active Directory (最终用户所在的位置) 的 DNS 域名称
    - 本地 Active Directory (最终用户所在的位置) 的 NetBIOS
    - SAM 帐户的用户名称


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>使用 Windows Hello 企业版的单一登录

Microsoft 托管桌面设备还通过采用 Windows Hello 企业版为你的用户提供了快速、passwordless 的体验。 若要确保 Windows hello 企业版能够正常工作, 而您的用户无需提供各自的 UPN 和密码, 请访问[使用 Windows Hello 企业版的本地单一登录配置 Azure AD 加入设备](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)以检查要求, 然后按照此处提供的步骤操作。


## <a name="apps-and-resources-that-use-authentication"></a>使用身份验证的应用程序和资源

请参阅了解 azure 内容集中[应用程序和资源的注意事项](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources), 以获取有关设置应用程序以与 Azure Active Directory 配合使用的完整指南。 摘要:


- 如果您使用**基于云的应用程序**(例如, 添加到 Azure AD 应用程序库中的应用程序), 则大多数不需要进一步准备使用 Microsoft 托管桌面。 但是, 任何不使用 Web 帐户管理器 (WAM) 的 Win32 应用程序可能仍会提示用户进行身份验证。

- 对于**托管在本地**的应用程序, 请务必将这些应用添加到浏览器中的 "受信任的网站" 列表中。 这将使 Windows 身份验证能够无缝工作, 而不提示用户提供凭据。 若要执行此操作, 请参阅[可配置的设置参考](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)中的[受信任站点](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites)。

- 如果使用的是 Active Directory 联合服务, 请检查是否已通过使用 "[使用 AD FS 验证和管理单一登录"](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))中的步骤启用 SSO。 

- 对于**内部部署和使用较旧协议**的应用程序, 只要设备有权访问内部部署域控制器进行身份验证, 则不需要额外的设置。 但是, 若要提供对这些应用程序的安全访问, 应部署 Azure AD 应用程序代理。 有关详细信息, 请参阅[通过 Azure Active Directory 应用程序代理远程访问本地应用程序](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。

- 不支持**在本地运行和依赖计算机身份验证**的应用程序, 因此应考虑将它们替换为较新的版本。

### <a name="network-shares-that-use-authentication"></a>使用身份验证的网络共享

用户无需额外的设置即可访问网络共享, 只要这些设备具有使用 UNC 路径的本地域控制器的访问权限即可。

### <a name="printers"></a>打印机

除非您已配置[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy), 否则 Microsoft 托管桌面设备将无法连接到发布到本地 Active Directory 的打印机。

虽然在仅云环境中无法自动发现打印机, 但只要设备具有对本地域控制器的访问权限, 用户就可以使用打印机路径或打印机队列路径的本地打印机。

<!--add fuller material on printers when available-->
