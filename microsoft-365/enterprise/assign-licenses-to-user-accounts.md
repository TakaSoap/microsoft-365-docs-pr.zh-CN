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
description: 介绍如何单独或基于组成员身份向用户帐户分配 Microsoft 365 许可证。
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051528"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>将 Microsoft 365 许可证分配给用户帐户

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

对于仅云标识模型，可以在创建用户帐户时将 Microsoft 365 许可证分配给用户帐户，具体取决于创建方式。

对于混合标识模型，当 Active Directory 域服务 (AD DS) 用户帐户首次同步时，不会自动为其分配位置或 Microsoft 365 许可证。 **在分配许可证之前或之前，必须使用用户位置配置每个用户帐户。**

在任一情况下，都必须向用户帐户分配许可证，以便你的用户可以访问 Microsoft 365 服务，如电子邮件和 Microsoft Teams。

你可以单独或自动通过组成员身份向用户帐户分配许可证。

若要将 Microsoft 365 许可证分配给单个用户帐户，可以使用：

- [Microsoft 365 管理员中心](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD 管理中心

## <a name="group-based-licensing"></a>基于组的许可

可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给组的所有成员。 这称为 *基于组的许可*。 如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。

确保所有组成员都有足够的许可证。 如果许可证用完，将不会向新用户分配许可证，直到许可证可用。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。
>

有关详细信息，请参阅 [Azure AD 中](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)基于组的许可。

## <a name="next-steps"></a>后续步骤

通过已分配许可证的一组适当的用户帐户，你现在可以：

- [实现安全性](../security/defender-365-security/security-roadmap.md)
- [部署客户端软件，如 Microsoft 365 应用版](/DeployOffice/deployment-guide-microsoft-365-apps)
- [设置设备管理](device-management-roadmap-microsoft-365.md)
- [配置服务和应用程序](configure-services-and-applications.md)