---
title: 管理 Microsoft 365 组
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: 了解如何管理组Microsoft 365组。
ms.openlocfilehash: 28d8bae8aaed6d02fe082824c07afe03bdc0ce5a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150758"
---
# <a name="manage-microsoft-365-groups"></a>管理 Microsoft 365 组

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

您可以使用几种Microsoft 365管理组，具体取决于您的配置。 可以在 Microsoft 365 管理中心、PowerShell、Active Directory 域服务 (AD DS) 或[Azure Active Directory (Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)) 管理中心中管理用户帐户。 [](/admin) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>规划管理组位置和方式

在哪里以及如何管理用户帐户取决于要用于用户帐户的标识Microsoft 365。 这两种整体模型是仅云模型和混合模型。
  
### <a name="cloud-only"></a>仅限云

创建和管理组时，需要：

- [Microsoft 365 管理员中心](/admin)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理中心](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>混合

AD DS 组与来自 AD DS Microsoft 365同步，因此必须使用本地 AD DS 工具管理这些组。

还可以创建和管理独立于 AD DS 组但可以包含 AD DS 中的用户和组的 Azure AD 组。 在这种情况下，可以使用：

- [Microsoft 365 管理员中心](/admin)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 管理中心](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>允许用户创建和管理自己的组

Azure AD 允许由组所有者而不是 IT 管理员管理的组。 此功能称为 *自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。 

用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。

>[!Note]
>自助服务组管理仅适用于 Azure AD 安全和 Microsoft 365 组。 它不适用于启用邮件的组、通讯组列表或从 AD DS 同步的任何组。
>

有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

## <a name="set-up-dynamic-group-membership"></a>设置动态组成员身份

Azure AD 支持配置一系列规则，以自动添加或删除用户帐户作为 Azure AD 组的成员。 这称为 *动态组成员身份*。 这些规则将基于用户帐户属性，如部门或国家/地区。

下面是如何应用这些规则：

- 如果新用户帐户符合组的所有规则，则其会变为成员。
- 如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。
- 如果用户帐户不匹配组的所有规则，则其不会添加到组。
- 如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。

若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。

请参阅[为动态 Azure AD 组创建并配置规则的说明](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

## <a name="set-up-automatic-licensing"></a>设置自动许可

可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给组的所有成员。 这称为 *基于组的许可*。 如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。

对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配相应的 Microsoft 365 企业版许可证。

确保所有组成员都有足够的许可证。 如果许可证用完，将不会向新用户分配许可证，直到许可证可用。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。
>

有关详细信息，请参阅 [Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal)中基于组的许可基础知识。

请参阅 [为 Azure 安全组](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)配置基于组的许可的说明。