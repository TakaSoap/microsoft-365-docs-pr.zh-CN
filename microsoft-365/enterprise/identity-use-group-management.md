---
title: 步骤 5：使用组进行管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 可以使用组来自动管理某些管理任务。
ms.openlocfilehash: 0d46a2af5683b8da40275302460d453f1f14acbe
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831655"
---
# <a name="step-5-use-groups-for-management"></a>步骤 5：使用组进行管理

![第 2 阶段 - 标识](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>允许用户创建和管理自己的组

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将标识可由组所有者而不是 IT 管理员来管理的 Azure Active Directory (Azure AD) 组。 此功能称为*自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。 

用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。

>[!Note]
>自助服务组管理仅适用于 Azure AD 安全和 Office 365 组。 不适用于启用邮件的组、通讯组列表或已从本地 Active Directory 域服务 (AD DS) 同步的任何组。
>

有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-self-service-groups)。

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>设置动态组成员身份

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将创建一系列规则来为 Azure AD 组的成员自动添加或删除用户帐户。 这称为*动态组成员身份*。 这些规则将基于用户帐户属性，如部门或国家/地区。

下面是如何应用这些规则：

- 如果新用户帐户符合组的所有规则，则其会变为成员。
- 如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。
- 如果用户帐户不匹配组的所有规则，则其不会添加到组。
- 如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。

若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。

请参阅[为动态 Azure AD 组创建并配置规则的说明](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

此部分的结果是：

- 可以为动态成员身份配置的 Azure AD 组集
- 每个动态组的规则集

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：自动化许可和组成员身份](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-dyn-groups)。

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>设置自动许可

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将在 Azure AD 中配置安全组，以将许可证从一组订阅自动分配到组的所有成员。 这称为*基于组的许可*。 如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。

对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配相应的 Microsoft 365 企业版许可证。

确保所有组成员都有足够的许可证。 如果许可证用完，将不会向新用户分配许可证，直到许可证可用。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”**。
>

有关更多信息，请参阅 [Azure Active Directory 中基于组的许可基础知识](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)。

请参阅[为 Azure 安全组配置基于组的许可的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。

此部分的结果是：

- 已标识哪些安全组适用于基于组的许可。
- 已为基于组的许可配置了这些组。

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：自动化许可和组成员身份](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-group-license)。

|||
|:-------|:-----|
|![第 6 步](./media/stepnumbers/Step6.png)| [配置标识治理](identity-configure-identity-governance.md) |
