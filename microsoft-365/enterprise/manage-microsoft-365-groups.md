---
title: 管理 Microsoft 365 组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 了解如何管理 Microsoft 365 组。
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328487"
---
# <a name="manage-microsoft-365-groups"></a>管理 Microsoft 365 组

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

您可以通过几种不同的方式管理 Microsoft 365 组，具体取决于您的配置。 你可以在 Active Directory 域服务 (AD DS) 中或在[Azure Active directory (AZURE AD) 管理中心](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)中管理[Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)、PowerShell 中的用户帐户。 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>规划将管理组的位置和方式

如何管理用户帐户的位置和方式取决于要用于 Microsoft 365 的标识模型。 这两个整体模型为仅云和混合模式。
  
### <a name="cloud-only"></a>仅限云

您可以使用以下内容创建和管理组：

- [Microsoft 365 管理员中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理中心](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>混合

AD DS 组与 Microsoft 365 从 AD DS 同步，因此您必须使用内部部署 AD DS 工具来管理这些组。

您还可以创建和管理独立于 AD DS 组的 Azure AD 组，但可以包含 AD DS 中的用户和组。 在这种情况下，您可以使用：

- [Microsoft 365 管理员中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理中心](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>允许用户创建和管理自己的组

Azure AD 允许组所有者而不是 IT 管理员来管理组。 此功能称为*自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。 

用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。

>[!Note]
>自助服务组管理仅适用于 Azure AD 安全和 Microsoft 365 组。 它对已启用邮件的组、通讯组列表或从 AD DS 同步的任何组不可用。
>

有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

## <a name="set-up-dynamic-group-membership"></a>设置动态组成员身份

Azure AD 支持配置一系列规则，以自动将用户帐户添加或删除为 Azure AD 组的成员。 这称为*动态组成员身份*。 这些规则将基于用户帐户属性，如部门或国家/地区。

下面是如何应用这些规则：

- 如果新用户帐户符合组的所有规则，则其会变为成员。
- 如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。
- 如果用户帐户不匹配组的所有规则，则其不会添加到组。
- 如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。

若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。

请参阅[为动态 Azure AD 组创建并配置规则的说明](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

## <a name="set-up-automatic-licensing"></a>设置自动许可

您可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给该组的所有成员。 这称为*基于组的许可*。 如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。

对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配相应的 Microsoft 365 企业版许可证。

确保所有组成员都有足够的许可证。 如果许可证用完，将不会向新用户分配许可证，直到许可证可用。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。
>

有关详细信息，请参阅 [AZURE AD 中的基于组的许可基础](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)。

请参阅 [为 Azure 安全组配置基于组的许可的说明](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。
