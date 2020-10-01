---
title: 将 Microsoft 365 许可证分配给用户帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 介绍如何将 Microsoft 365 许可证单独或基于组成员身份分配给用户帐户。
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326503"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>将 Microsoft 365 许可证分配给用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

对于仅限云的标识模型，可以根据创建的方式将 Microsoft 365 许可证分配给用户帐户，具体取决于您的创建方式。

对于混合标识模型，如果 Active Directory 域服务 (AD DS) 用户帐户首次同步，则不会自动为其分配位置或 Microsoft 365 许可证。 **在分配许可证之前或之前，必须使用用户位置配置每个用户帐户。**

在这两种情况下，都必须将许可证分配给用户帐户，以便您的用户可以访问 Microsoft 365 服务，例如电子邮件和 Microsoft 团队。

您可以通过组成员身份单独或自动将许可证分配给用户帐户。

若要将 Microsoft 365 许可证分配给单个用户帐户，您可以使用：

- [Microsoft 365 管理员中心](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD 管理中心

## <a name="group-based-licensing"></a>基于组的许可

您可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给该组的所有成员。 这称为*基于组的许可*。 如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。

确保所有组成员都有足够的许可证。 如果许可证用完，将不会向新用户分配许可证，直到许可证可用。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。
>

有关更多 informaion，请参阅 [AZURE AD 中的基于组的许可](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

## <a name="next-steps"></a>后续步骤

对于已分配有许可证的一组适当的用户帐户，您现在可以执行以下操作：

- [实施安全性](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [部署客户端软件，例如 Microsoft 365 应用程序](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [设置设备管理](device-management-roadmap-microsoft-365.md)
- [配置服务和应用程序](configure-services-and-applications.md)
