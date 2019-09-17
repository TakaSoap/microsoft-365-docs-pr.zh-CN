---
title: 使用解决方案提供商
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: 您可以与 Microsoft 认证的解决方案提供商合作，以购买和管理组织或学校的产品和服务。
keywords: 合作伙伴、解决方案提供商
ms.openlocfilehash: bb78e1a704529fd2d12ff49639913fe80b75be7a
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994073"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a>在 Microsoft Store for Business 中使用解决方案提供商

您可以与 Microsoft 认证的解决方案提供商合作，以购买和管理组织或学校的产品和服务。 在获取设置的过程中，需要执行几个步骤。 

该过程如下所示：
- 管理员使用在 Microsoft Store for Business 中**查找解决方案提供商**查找和联系解决方案提供商。 
- 解决方案提供商向客户发送来自合作伙伴中心的请求，以成为其解决方案提供商。
- 客户接受 Microsoft Store for Business 中的邀请，并开始使用解决方案提供商。
- 客户可以在 Microsoft Store for Business 中管理与合作伙伴的关系设置。 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a>解决方案提供商可以为我的组织或学校做些什么？

解决方案提供商可以通过多种方式与您协作。 当解决方案提供商发送其请求以与你的合作伙伴合作时，它们将在其中选择一个。

| 解决方案提供程序函数 | 说明 | 
| ------ | ------------------- | 
| 增值 | 解决方案提供商将 Microsoft 产品销售给你的组织或学校。 |
| 委派管理员 | 解决方案提供商管理组织或学校的产品和服务。 在 Azure Active Directory （AD）中，合作伙伴将成为租户的全局管理员。 这样，他们就可以管理诸如创建用户帐户、分配和管理许可证以及密码重置等服务。 |
| & 委派管理员的转销商 | 为您的组织或学校销售和管理 Microsoft 产品和服务的解决方案提供商。 |
| 合作伙伴 | 您可以向解决方案提供商提供租户中的用户帐户，并代表其他 Microsoft 服务工作。 |
| Microsoft 产品 & Services 协议（MPSA）合作伙伴 | 如果你已通过 MPSA 程序使用了多个解决方案提供商，则可以允许合作伙伴查看彼此的购买。 |
| OEM 电脑合作伙伴 | 解决方案提供商可以上传[使用 Autopilot 管理](https://docs.microsoft.com/microsoft-store/add-profile-to-devices)的电脑的设备 id。   |
| 业务线（LOB）合作伙伴 | 解决方案提供商可以开发、提交和管理特定于您的组织或学校的 LOB 应用程序。 |

## <a name="find-a-solution-provider"></a>查找解决方案提供商

你可以在 Microsoft Store for Business and 教育中找到合作伙伴。 

1. 登录[Microsoft store For Business](https://businessstore.microsoft.com/)或[Microsoft store for 教育](https://educationstore.microsoft.com/)版。
2. 选择 "**查找解决方案提供商**"。
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. 优化列表或搜索解决方案提供商。 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. 当您找到要使用的解决方案提供商时，请单击 "**联系人**"。
5. 完成并发送窗体。

解决方案提供商将与你取得联系。 你将有机会了解更多相关信息。 如果您决定使用解决方案提供商，他们将向您发送来自合作伙伴中心的电子邮件邀请。 

## <a name="work-with-a-solution-provider"></a>使用解决方案提供商

一旦找到了解决方案提供商并决定使用它们，他们就会向您发送一封邀请，让他们从合作伙伴中心协同工作。 在 Microsoft Store for Business 或教育版中，需要接受邀请。 之后，你可以管理他们的权限。

**接受解决方案提供商邀请**
1. **关注电子邮件链接**-你将收到一封电子邮件，其中包含可接受来自解决方案提供商的解决方案提供商邀请的链接。 此链接将带你转到 Microsoft Store for Business 或教育版。
2. **接受邀请**-On **accept Partner 请柬**，选择 "**授权**" 以接受邀请，接受 Microsoft 云协议的条款，并开始使用解决方案提供商。 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a>委派管理员权限

根据解决方案提供商发出的请求，接受邀请的部分将包括同意向解决方案提供商授予委派管理员权限。 当解决方案提供程序请求包括作为委派的管理员时，将会发生这种情况。 有关详细信息，请参阅[AZURE AD 中的委派管理员权限](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)。 

如果您不想将管理员权限委派给解决方案提供商，则需要取消邀请，而不是接受它。 

如果您将管理员权限委派给解决方案提供商，则可以在以后删除。 

**删除委派管理员权限**
1. 登录[Microsoft store For Business](https://businessstore.microsoft.com/)或[Microsoft store for 教育](https://educationstore.microsoft.com/)版。
2. 选择**合作伙伴**
3. 选择要管理的合作伙伴。
4. 选择 "**删除委派权限**"。 

解决方案提供商仍将能够与你协作，例如，作为转销商。 
