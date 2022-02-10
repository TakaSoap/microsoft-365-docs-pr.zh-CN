---
title: 为 Microsoft 托管桌面准备本地资源访问权限
description: 确保用户能够与Azure AD AD 进行通信以提供身份验证的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 3db3d469f7b417035e6ae11507c54c6bad871a89
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520387"
---
# <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备本地资源访问权限

在Microsoft 托管桌面中，设备会自动加入Azure Active Directory (Azure AD) 。 因此，如果使用本地 Active Directory，必须确保加入 Azure AD 的设备可以与本地 Active Directory 通信。

> [!NOTE]  
> *混合* Azure AD不支持混合Microsoft 托管桌面。

Azure Active Directory可让用户利用单一 Sign-On (SSO) 。 单一登录意味着他们通常不需要每次使用资源时都提供凭据。

有关加入Azure Active Directory的信息，请参阅[如何：规划你的Azure AD实现](/azure/active-directory/devices/azureadjoin-plan)。 有关加入 Azure AD 的Sign-On (SSO) ，请参阅 [SSO 到](/azure/active-directory/devices/azuread-join-sso#how-it-works)本地资源在已加入 Azure AD 设备上的工作方式。

本文介绍了为确保应用和依赖于本地 Active Directory 连接的其他资源能够顺利使用本地 Active Directory 连接而必须检查Microsoft 托管桌面。

## <a name="single-sign-on-for-on-premises-resources"></a>用于Sign-On资源的单个资源

默认情况下Sign-On (设备) UPN 和密码启用单一 SSO Microsoft 托管桌面 SSO。 但是，您的用户还可使用 Windows Hello for Business，这需要一些额外的设置步骤。

### <a name="single-sign-on-by-using-upn-and-password"></a>单Sign-On UPN 和密码进行加密

在大多数组织中，用户将能够使用 SSO 通过 UPN 进行身份验证，并使用设备Microsoft 托管桌面密码。 若要确保此函数正常工作，应仔细检查以下内容：

- 确认Azure AD 连接已设置。 必须使用运行 Windows Server 2008 R2 或更高版本本地 Active Directory 服务器。
- 确认Azure AD 连接版本是否正在运行。 必须设置此属性，以将这三个属性与Azure AD：
    - 用户所在的本地 Active Directory (DNS 域名) 。
    - 用户所在的本地 Active Directory (NetBIOS) 。
    - 用户的 SAM 帐户名。

### <a name="single-sign-on-by-using-windows-hello-for-business"></a>使用 Sign-On for Business 进行Windows Hello单一应用

Microsoft 托管桌面企业应用，设备还可以为用户提供快速、无密码Windows Hello体验。 若要确保 Windows Hello for Business 正常工作，且用户不必提供各自的 UPN 和密码，请访问为本地 Single-Sign 配置加入 Azure AD 的设备 [On using Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) 检查要求，然后按照那里提供的步骤操作。

## <a name="apps-and-resources-that-use-authentication"></a>使用身份验证的应用和资源

请参阅[了解 Azure 内容](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)集内应用程序和资源注意事项，获取设置应用以使用 azure 内容集的完整Azure Active Directory。 摘要：

| 应用或服务 | 任务 |
| ------ | ------ |
| 基于云的应用 | 如果你使用 **基于云的应用**，例如添加到 Azure AD 应用库的应用，大多数应用都不需要进一步准备Microsoft 托管桌面。 但是，任何不使用 Web 帐户管理器或 WAM (Win32) 可能仍提示用户进行身份验证。 |
| 本地托管的应用 | 对于在本地 **托管的应用，** 请确保将这些应用添加到浏览器的受信任站点列表。 此步骤将使 Windows身份验证无缝工作，而不会提示用户提供凭据。 若要添加应用，请参阅可配置 [设置](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 参考 [中的受信任的站点](../working-with-managed-desktop/config-setting-ref.md)。 |
| Active Directory 联合服务 | 如果使用的是 Active Directory 联合服务，则使用使用 AD FS 验证和管理单一登录中的步骤检查 [SSO 是否已启用](/previous-versions/azure/azure-services/jj151809(v=azure.100))。 |
| 使用旧协议本地应用 | 对于 **本地和使用旧** 协议的应用，无需额外设置，只要设备有权访问本地域控制器进行身份验证。 但是，若要为这些应用程序提供安全访问，您应部署Azure AD代理。 有关详细信息，请参阅通过 Azure Active Directory [应用程序代理远程访问本地应用程序](/azure/active-directory/manage-apps/application-proxy)。 |
| 具有本地计算机身份验证本地应用 | 不支持 **在本地运行并依赖** 计算机身份验证的应用，因此应考虑将它们替换为较新版本。 |

### <a name="network-shares-that-use-authentication"></a>使用身份验证的网络共享

只要设备能够使用 UNC 路径访问本地域控制器，用户就无需进行额外的设置，即访问网络共享。

### <a name="printers"></a>打印机

Microsoft 托管桌面设备无法连接到发布到本地 Active Directory 的打印机，除非你已配置混合云[打印](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。

虽然无法自动在仅云环境中发现打印机，但只要设备可以访问本地域控制器，用户就可以通过使用打印机路径或打印机队列路径来使用本地打印机。

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
1. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. 准备用户访问数据 (本文) 。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
