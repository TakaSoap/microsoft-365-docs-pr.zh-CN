---
title: Microsoft 365 安全与合规中心中的权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用 Microsoft 365 安全中心或 Microsoft 365 合规中心，可以集中管理与安全或合规性相关的所有任务的权限。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5322a972a93ee603ef31754288e9ab9b7eb401a9
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604277"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Microsoft 365 合规中心和 Microsoft 365 安全中心中的权限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


组织需要管理跨所有 Microsoft 365 服务的安全和合规性方案。 并且你需要灵活地向组织 IT 组中的正确人员授予正确的管理员权限。 使用 Microsoft 365 安全中心或 Microsoft 365 合规中心，可以集中管理与安全或合规性相关的所有任务的权限。

在全局管理员将用户添加到这些管理员角色后，这些管理员将可以访问跨 Microsoft 365 中所有服务（例如，Microsoft 365 安全中心、Microsoft 365 合规中心、Azure、Office 365 和企业移动性 + 安全性）的功能和数据。

## <a name="what-the-microsoft-365-roles-are"></a>Microsoft 365 角色是什么

Microsoft 365 合规中心和 Microsoft 365 安全中心中显示的角色均为 Azure Active Directory 角色。 这些角色旨在与组织 IT 组中的工作职能保持一致，从而可以轻松地使人员获得完成其工作所需的所有权限。

****

|角色|说明|
|---|---|
|**全局管理员**|访问所有 Microsoft 365 服务中的所有管理功能的权限。 只有全局管理员才能分配其他管理员角色。 更多信息，请参阅[全局管理员/公司管理员](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)。|
|**合规性数据管理员**|在 Microsoft 365 中跟踪组织的数据，确保数据受到保护，并深入了解任何问题以帮助缓解风险。 有关详细信息，请参阅[合规性数据管理员](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#compliance-data-administrator)。|
|**合规性管理员**|帮助组织遵守任何法规要求，管理电子数据展示案例，并维护 Microsoft 365 位置、标识和应用中的数据治理策略。 有关详细信息，请参阅[合规性管理员](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#compliance-administrator)。|
|**安全操作员**|查看、调查和响应对 Microsoft 365 用户、设备和内容的活动威胁。 有关详细信息，请参阅[安全操作员](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-operator)。|
|**安全信息读取者**|查看和调查对 Microsoft 365 用户、设备和内容的活动威胁，但（不同于安全操作员）他们无权采取措施来进行响应。 有关详细信息，请参阅[安全信息读取者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-reader)。|
|**安全管理员**|通过管理安全策略、查看 Microsoft 365 产品中的安全分析和报告以及及时了解威胁形势来控制组织的总体安全。 有关详细信息，请参阅[安全管理员](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-administrator)。|
|**全局读取者**|只读版本的 **全局管理员** 角色。 查看 Microsoft 365 中所有设置和管理信息。 有关详细信息，请参阅 [全局信息读取者](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#global-reader)。|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>全局管理员可以管理 Azure Active Directory 中的角色。

在 Microsoft 365 合规中心和 Microsoft 365 安全中心中，选择一个角色后，可查看其分配。 但若要管理这些分配，需要转到 Azure Active Directory。

有关详细信息，请参阅[查看和分配 Azure Active Directory 中的管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

![链接以管理 Azure Active Directory 中的权限](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>管理服务中的角色，而不是 Azure Active Directory 中的角色

Microsoft 365 合规中心和 Microsoft 365 安全中心中显示的角色也会显示在他们拥有权限的服务中。 例如，可以在安全与合规中心中看到这些角色。

![安全与合规中心中的角色](../../media/m365-roles-in-o365-scc.png)

若要了解安全与合规中心内的角色安排，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="breaking-inheritance"></a>中断继承

在 Azure Active Directory 中管理这些角色时，你是在为 **所有** Microsoft 365 服务集中管理这些角色，了解这一点非常重要。 然而，在管理特定服务（例如安全与合规中心），所管理的角色 **仅** 针对特定服务。 服务中角色的分配和权限覆盖授予 Azure Active Directory 角色的任何权限。

可能很有用。 例如，如果一个人被分配为安全管理员角色，那么他就无权管理事件。 但是，你可以使用 Microsoft Defender for Endpoint 中的权限来向其提供该服务中的事件管理特定的权限。

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>在何处查找每个 Microsoft 365 服务的角色信息

通过将用户分配到 Microsoft 365 合规性或安全管理员角色之一，你可以授予该用户对一系列 Microsoft 365 服务的权限。 使用下面的链接可以找到关于每个服务中角色特定权限的更多信息。

****

|Microsoft 365 服务|角色信息|
|---|---|
|Office 365 和 Microsoft 365 商业版计划中的管理员角色|[Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Azure Active Directory (Azure AD) 和 Azure AD Identity Protection|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Microsoft Defender for Identity 角色组](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure 信息保护|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|合规性管理器|[合规性管理器](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager-setup#set-user-permissions-and-assign-roles)|
|Exchange Online|[Exchange 基于角色的访问控制](https://docs.microsoft.com/exchange/understanding-role-based-access-control-exchange-2013-help)|
|Intune|[Intune 基于角色的访问控制](https://docs.microsoft.com/intune/role-based-access-control)|
|托管桌面|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[基于角色的访问控制](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|安全与合规中心|[Microsoft 365 管理员角色](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|安全功能分数|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [关于 Office 365 中的 SharePoint 管理员角色](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/Skype for Business|[Azure AD 管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Endpoint|[Microsoft Defender for Endpoint 基于角色的访问控制](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>即将推出

我们仍在研究 Microsoft 365 合规中心和 Microsoft 365 安全中心中的权限。 例如，我们目前正致力于支持以下功能：

- 管理 Microsoft 365 合规中心和 Microsoft 365 安全中心中的角色，而不是转到 Azure Active Directory。
- 通过添加或删除特定权限来自定义角色。
- 创建具有所选权限的自定义角色。
