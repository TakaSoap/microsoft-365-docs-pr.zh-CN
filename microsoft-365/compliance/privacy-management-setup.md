---
title: 'Microsoft 隐私管理预览版 (入门) '
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: 了解如何为组织设置隐私管理、设置角色和权限以及配置重要设置。
ms.openlocfilehash: 1472b20b32315480f5b7b237ca91a465de293747
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247526"
---
# <a name="get-started-with-privacy-management-preview"></a>隐私管理与预览 (入门) 

本文内容：了解如何为组织设置对隐私管理的访问权限、如何开始评估数据以及如何处理重要 **设置**。

## <a name="who-can-access-privacy-management"></a>Who可以访问隐私管理

隐私管理的公共预览版在 Microsoft 365 合规中心 中提供，适用于在 Office 365 和 Microsoft 365 中拥有 E1、E3 和 E5 企业许可证的组织。 当隐私管理进入常规可用性时，使用公共预览版的组织将需要获取新的许可证。

有关详细的许可指南，请参阅 [适用于安全性与合规性的 Microsoft 365 许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

> [!Note]
> 美国政府隐私管理的公共预览版不适用于美国政府 Community (GCC) 、GCC 高或国防部 (DoD) 客户。

## <a name="set-up-privacy-management"></a>设置隐私管理

若要开始使用隐私管理，首先获取试用版许可证并登录。 然后，您可以为用户分配权限并查看设置。

### <a name="get-trial-license"></a>获取试用许可证

若要开始使用公共预览版，全局管理员可以从管理中心获取免费隐私管理 [试用许可证](https://aka.ms/purchasem365privacy)。 选择"开始试用"开始。 你的许可证将持续一个月，可以在公共预览版期间根据需要无需任何费用续订它。

获取订阅后，最多允许激活 30 分钟。 然后返回到隐私管理以开始。 你将被要求确认你同意条款和个人数据评估过程， ([了解) 。](privacy-management.md#how-we-evaluate-your-data) 可以完整查看提供的链接，然后再继续。 一旦同意，隐私管理可能需要最多 24 小时才能开始提供有关组织数据的见解。

如果你没有获得订阅或同意使用隐私管理条款所需的角色，系统将提示你联系全局管理员寻求帮助。

### <a name="set-user-permissions-and-assign-roles"></a>设置用户权限和分配角色

隐私管理使用基于角色的访问控制 (RBAC) 权限模型。 只有分配了角色的用户才能访问隐私管理，并且每个用户允许的操作受角色类型限制。

我们建议全局管理员在首次使用隐私管理时登录合规性中心并设置用户权限。 为快速入门，隐私管理角色组有权访问隐私管理的所有功能。 对于同一个人可能在隐私管理解决方案中履行所有职责的组织，此组可能非常适合。 其他隐私角色允许你进行更精细的控制，并将用户分配给所选功能。

若要详细了解角色组以及如何授予访问权限，请参阅设置 [用户权限和分配角色](privacy-management-permissions.md)。

### <a name="manage-settings"></a>管理设置

可通过设置管理主页右上角的齿轮访问该页面。 它允许隐私管理管理员跨隐私管理配置基本属性。

在开始之前，你可能希望查看默认配置并做出任何所需的调整。 若要了解有关选项的详细信息，请参阅 [管理隐私管理设置](privacy-management-settings.md)。

## <a name="get-initial-data-insights"></a>获取初始数据见解

登录隐私管理后，你将进入概述 **页面** 。 此页面提供有关存储在 Microsoft 365 环境中个人数据的见解，以帮助您快速发现问题、识别风险指标并采取措施解决问题。 你的概述应在注册前 24 小时内填充初始见解。 当你继续使用隐私管理时，概述页面将刷新以继续提供最新信息。

为了进一步深入了解数据，数据配置文件页将提供更多的可视化和分析，并按地理位置和按服务Microsoft 365组织数据。

若要了解有关这些页面的信息，请参阅 [查找和可视化数据](privacy-management-data-profile.md)。

## <a name="get-started-with-default-policies"></a>默认策略入门 

隐私管理将有助于启动数据评估过程，方法为创建三个使用默认设置的策略，使用用于数据最小化、数据过度利用和数据传输的模板。 默认情况下，这些策略将启用，但不会自动触发通知邮件或修正提示。 初始设置后，可以继续创建和自定义自己的策略。 若要了解更多信息，请参阅 [创建和管理策略](privacy-management-policies.md)。
