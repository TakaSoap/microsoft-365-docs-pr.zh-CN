---
title: 保护用户和设备的访问权限
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 了解如何保护用户和设备访问数据Microsoft 365服务，并防御数据丢失。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 121c5b8f1168e9986693fea128aa66626b3e31fe
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818536"
---
# <a name="protect-user-and-device-access"></a>保护用户和设备的访问权限

保护对Microsoft 365和服务的访问对于防御网络攻击和防止数据丢失至关重要。 相同的保护可以应用于环境中的其他 SaaS 应用程序，甚至应用于使用应用程序代理发布的Azure Active Directory应用程序。
  
## <a name="step-1-review-recommendations"></a>步骤 1：查看建议

用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>步骤 2：保护管理员帐户和访问权限
用于管理环境的管理帐户Microsoft 365提升的权限。 这些是黑客和网络攻击的有价值目标。 

首先，仅将管理员帐户用于管理。 管理员应具有单独的用户帐户，用于常规的非管理用途，并且仅在必要时使用其管理帐户来完成与其工作职能相关联的任务。

使用多重身份验证和条件访问保护管理员帐户。 有关详细信息，请参阅 [保护管理员帐户](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。 

接下来，在 Office 365 中配置特权访问Office 365。 特权访问管理可以对 Office 365 中的特权管理任务进行粒度访问控制。 它可以帮助保护组织免受可能使用现有特权管理员帐户（长期访问敏感数据或访问关键配置设置）的泄露。

- [特权访问管理概述](privileged-access-management-overview.md)
- [配置特权访问管理](privileged-access-management-configuration.md)

另一个首要建议是使用为管理工作特别配置的工作站。 这些是仅用于管理任务的专用设备。 请参阅 [保护特权访问](/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最后，可以通过在租户中创建两个或多个紧急访问帐户来缓解意外缺少管理访问的影响。 请参阅[管理 Azure AD 中的紧急访问帐户](/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步骤 3：配置推荐的标识和设备访问策略
MFA (和) 访问策略的多重身份验证是抵御帐户损坏和未授权访问的强大工具。 我们建议实现一组已一起测试的策略。 有关详细信息（包括部署步骤，请参阅 [标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)）。

 这些策略实现以下功能：
- 多重身份验证
- 条件访问
- Intune 应用保护 (应用和数据保护的设备) 
- Intune 设备合规性
- Azure AD 标识保护

实现 Intune 设备合规性需要设备注册。 通过管理设备，可以确保设备正常运行且合规，然后再允许它们访问环境中的资源。 请参阅 [在 Intune 中注册设备以管理](/mem/intune/user-help/enroll-windows-10-device)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步骤 4：配置SharePoint访问策略

Microsoft 建议通过设备访问控制SharePoint敏感和高度管控内容保护网站中的内容。 有关详细信息，请参阅[用于保护网站和文件SharePoint策略建议](../security/office-365-security/sharepoint-file-access-policies.md)。



