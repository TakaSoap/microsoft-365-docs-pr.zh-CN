---
title: 将Microsoft 365许可证分配给用户帐户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 介绍如何将Microsoft 365许可证分配给用户帐户，无论是单独分配还是基于组成员身份。
ms.openlocfilehash: dd941be0d257aa356cf6e69bfdd59a8d1743ed93
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159458"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>将Microsoft 365许可证分配给用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

对于仅云标识模型，可以在Microsoft 365用户帐户时，根据用户帐户的创建方式分配这些许可证。

对于混合标识模型，当 Active Directory 域服务 (AD DS) 用户帐户首次同步时，不会自动为其分配位置或 Microsoft 365 许可证。 **在分配许可证之前或之前，必须使用用户位置配置每个用户帐户。**

在任一情况下，都必须向用户帐户分配许可证，以便Microsoft 365访问电子邮件和Microsoft Teams。

你可以单独或自动通过组成员身份向用户帐户分配许可证。

若要Microsoft 365用户帐户分配许可证，可以使用：

- [Microsoft 365 管理员中心](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD 管理中心

## <a name="group-based-licensing"></a>基于组的许可

可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给组的所有成员。 这称为 *基于组的许可*。 如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。

确保所有组成员都有足够的许可证。 如果许可证用完，将不会向新用户分配许可证，直到许可证可用。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。
>

有关详细信息，请参阅 [Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)中基于组的许可。

## <a name="next-steps"></a>后续步骤

使用已分配许可证的一组适当的用户帐户，你现在可以：

- [实现安全性](../security/office-365-security/security-roadmap.md)
- [部署客户端软件，如Microsoft 365 应用版](/DeployOffice/deployment-guide-microsoft-365-apps)
- [设置设备管理](device-management-roadmap-microsoft-365.md)
- [配置服务和应用程序](configure-services-and-applications.md)