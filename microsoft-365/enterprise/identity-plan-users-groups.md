---
title: 步骤 1：计划用户和组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 计划为组织工作的一组用户和组。
ms.openlocfilehash: 05b854c182b6f624cf143ed93920c344391ee416
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981803"
---
# <a name="step-1-plan-for-users-and-groups"></a>步骤 1：计划用户和组

*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将创建身份基础结构，以将用户、组和组成员身份与正确配置中的安全功能结合。这将允许你：

- 维持对有权访问环境中资源的用户的控制。
- 使用控件保护访问权限可确保身份的高可靠性（用户是其声明的身份）和从安全设备进行访问。
- 使用合适的权限预配环境中的资源，以减少潜在的危害和数据泄露。 
- 监控环境中的异常用户行为并自动采取措施。

## <a name="plan-your-primary-identity-provider"></a>计划主标识提供者

若要创建身份基础结构，需指定主标识提供者。此服务存储用户帐户及其属性、组及其成员身份，并支持其正在进行的管理。

当组织采用 Microsoft 365 企业版时，主标识提供者将为以下之一：

- **Active Directory 域服务 (AD DS)**，托管在运行 Windows Server 的计算机上的 Intranet 标识提供程序。 它通常由具有现有本地标识提供程序的组织使用。
- **Azure Active Directory (Azure AD**)，基于云的标识即服务 (IDaaS)，提供管理和保护环境的广泛功能。 它通常由不具备现有本地基础结构的组织使用。

如果组织具有现有本地标识提供者，则需要将用户帐户和组从 AD DS 同步到 Azure AD，以提供对 Microsoft 365 企业版基于云的服务无缝访问体验。 此外，还可以使用 Azure AD 来创建和管理仅存在于 Microsoft 云中的组。

在 Azure AD 中计划好用户和组后，可以：

- 管理所有云应用程序的所有 Azure AD 帐户。 
- 使用同一组控件来保护跨环境对应用程序的访问。
- 与外部合作伙伴进行协作。
- 监控异常帐户行为（如可疑的登录尝试）并自动采取措施。

按照以下两个部分中的说明来计划和实施用户帐户和组。

## <a name="categorize-your-users"></a>对用户分类
可使用多种方式对组织中的用户进行分类。例如，某些用户是员工，他们拥有永久身份。某些用户是供应商、承包商或合作伙伴，他们拥有临时身份。某些用户是外部用户，他们没有用户帐户但仍必须被授予访问特定服务和资源的权限，以支持交互和协作。例如：

- 租户帐户表示组织中许可访问云服务的用户。
- 企业到企业 (B2B) 帐户表示组织外部邀请加入协作的用户。

评估组织的用户类型。什么是分组？例如，可以按组织的高级职能或用途对用户进行分组。

此外，可以将某些云服务与组织外部没有任何用户帐户的用户共享，而且你还需要标识这些用户组。

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>计划 AD DS 和 Azure AD 组

可将 Azure AD 中的组用于多个目的，以简化云环境的管理。例如，对于 Azure AD 组，可以：

- 只要在 Azure AD 中添加组或从 AD DS 中同步组，就可以使用基于组的许可将许可证自动分配到用户帐户。 
- 根据用户帐户属性（如部门）将用户帐户动态添加到特定组。  
- 自动预配软件即服务 (SaaS) 应用程序的用户，并通过多重身份验证和其他条件访问规则来保护对这些应用程序的访问。
- 预配 SharePoint Online 团队网站的权限和访问权限级别。此外，Azure AD 组还可与敏感度或 Azure 信息保护标签一起使用，以保护具有加密和权限的文件。 

## <a name="results"></a>结果

完成这一步后，将具有：

- Azure AD 中的用户帐户列表，对应于组织中的员工，以及为组织工作或与组织协作的供应商、承包商和外部合作伙伴。
- Azure AD 中的组集合及其成员身份，反映用户帐户和其他组的逻辑集合，用于自动许可预配 Microsoft 云服务的安全设置。

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-user-groups)。

创建 Azure AD 用户和组后，便可以开始分配许可证和使用 OneDrive for Business 或 Exchange Online 等生产力工作负载。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [保护你的特权标识](identity-designate-protect-admin-accounts.md) |

