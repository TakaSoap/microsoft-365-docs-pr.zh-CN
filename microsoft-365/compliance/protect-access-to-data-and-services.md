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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 了解如何保护用户和设备访问数据Microsoft 365服务，并防御数据丢失。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0feef7c88df39ac48deb192ddda372604f667cc5b7652b53ffcd50dce78f15ce
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53871581"
---
# <a name="protect-user-and-device-access"></a>保护用户和设备的访问权限

保护对Microsoft 365和服务的访问对于防御网络攻击和防止数据丢失至关重要。 相同的保护可以应用于环境中的其他 SaaS 应用程序，甚至应用于使用 Azure Active Directory 应用程序代理发布的本地应用程序。
  
## <a name="step-1-review-recommendations"></a>步骤 1：查看建议

用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>步骤 2：保护管理员帐户和访问权限
用于管理环境的管理帐户Microsoft 365提升的权限。 这些是黑客和网络攻击的有价值目标。 

首先，仅将管理员帐户用于管理。 管理员应具有单独的用户帐户，用于常规的非管理用途，并且仅在必要时使用其管理帐户来完成与其工作职能相关联的任务。

使用多重身份验证和条件访问保护管理员帐户。 有关详细信息，请参阅 [保护管理员帐户](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。 

接下来，在 Office 365 中配置特权访问Office 365。 特权访问管理允许在 Office 365 中对特权管理任务进行精细的访问控制。 它可以帮助保护组织免受可能使用现有特权管理员帐户（长期访问敏感数据或访问关键配置设置）的泄露。

- [特权访问管理概述](privileged-access-management-overview.md)
- [配置特权访问管理](privileged-access-management-configuration.md)

另一个首要建议是使用专为管理工作配置的工作站。 这些是仅用于管理任务的专用设备。 请参阅 [保护特权访问](/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最后，可以通过在租户中创建两个或多个紧急访问帐户来缓解意外缺少管理访问的影响。 请参阅 [在 Azure AD 中管理紧急访问帐户](/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>步骤 3：配置推荐的标识和设备访问策略
MFA (和) 访问策略的多重身份验证是抵御帐户损坏和未授权访问的强大工具。 我们建议实现一组已一起测试的策略。 有关详细信息（包括部署步骤，请参阅 [标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)）。

 这些策略实现以下功能：
- 多重身份验证
- 条件访问
- Intune 应用 (应用和数据保护功能，适用于) 
- Intune 设备合规性
- Azure AD 标识保护

实现 Intune 设备合规性需要设备注册。 通过管理设备，可以确保设备正常运行且合规，然后再允许它们访问环境中的资源。 请参阅 [在 Intune 中注册设备以管理](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>步骤 4：SharePoint设备访问策略

Microsoft 建议通过设备访问控制SharePoint敏感和高度管控内容保护网站中的内容。 有关详细信息，请参阅[用于保护网站和文件SharePoint策略建议](../security/office-365-security/sharepoint-file-access-policies.md)。



