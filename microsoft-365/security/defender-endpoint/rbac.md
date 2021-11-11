---
title: 使用基于角色的访问控制授予对网站门户的Microsoft 365 Defender访问权限
description: 在安全操作内创建角色和组以授予对门户的访问权限。
keywords: rbac， role， based， access， control， groups， control， tier， aad
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 59b7f7f9aad9406fc5575f4ada5f45a68dd81b22
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914436"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>使用基于角色的访问控制管理门户访问

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- Azure Active Directory
- Office 365

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-rbac-abovefoldlink)。

使用基于角色的访问控制 (RBAC) ，可以在安全操作团队内创建角色和组，以授予对门户的适当访问权限。 根据你创建的角色和组，你可以精细控制有权访问门户的用户可以看到和执行哪些操作。 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bJ2a]

大型异地分布式安全操作团队通常采用基于层的模型来分配和授权对安全门户的访问。 典型的层包括以下三个级别：

层|说明|
:---|:---|
第 1 层|**本地安全运营团队/IT 团队** <br> 此团队通常会会审并调查其地理位置中包含的警报，并上报至第 2 层（如果需要进行主动修正）。|
第 2 层|**区域安全运营团队** <br> 此团队可以看到其区域的所有设备并执行修正操作。|
第 3 层|**全球安全运营团队** <br> 此团队由安全专家组成，有权从门户查看和执行所有操作。|

> [!NOTE]
> 对于第 0 层资源[](/azure/active-directory/privileged-identity-management/pim-configure)，Privileged Identity Management安全管理员参考，以便更精细地控制适用于终结点和Microsoft 365 Defender。  

Defender for Endpoint RBAC 旨在支持你基于层或基于角色的选择模型，让你可以精细地控制哪些角色可以看到、他们可以访问的设备以及他们可以采取的操作。 RBAC 框架以以下控件为中心：

- **控制谁可以采取特定操作**
  - 创建自定义角色并控制他们可以通过粒度访问的 Defender for Endpoint 功能。
- **控制哪些人可以看到有关特定设备组的信息**
  - [按特定条件](machine-groups.md)（如名称、标记、域和其他条件）创建设备组，然后使用特定用户Azure Active Directory (Azure AD) 访问它们。

若要实现基于角色的访问，你需要定义管理员角色、分配相应的权限，Azure AD分配给这些角色的用户组。

### <a name="before-you-begin"></a>开始之前

在使用 RBAC 之前，了解可以授予权限的角色以及启用 RBAC 的后果非常重要。

> [!WARNING]
> 在启用该功能之前，在 Azure AD 中必须拥有全局管理员角色或安全管理员角色，并且准备好 Azure AD 组来降低门户外被锁定的风险，这一点很重要。 

首次登录到 Microsoft 365 Defender门户时，将被授予完全访问权限或只读访问权限。 向具有安全管理员或全局管理员角色的用户授予完全访问权限Azure AD。 只读访问权限授予在安全读取者角色的用户Azure AD。 

具有 Defender for Endpoint 全局管理员角色的用户可以不受限制地访问所有设备，无论其设备组关联和用户Azure AD分配如何

> [!WARNING]
> 最初，只有具有 Azure AD 全局管理员或安全管理员权限的用户才能在 Microsoft 365 Defender 门户中创建和分配角色，因此在 Azure AD 中准备好正确的组Azure AD非常重要。
>
> **启用基于角色的访问控制将导致具有只读权限的用户 (例如，分配给 Azure AD 安全读者角色) 的用户在被分配到角色之前将失去访问权限。** 
>
>具有管理员权限的用户将自动分配具有完整权限的默认内置 Defender 全局管理员角色 Defender。 选择使用 RBAC 后，你可以将全局管理员Azure AD安全管理员的其他用户分配给 Defender for Endpoint 全局管理员角色。 
>
> 选择使用 RBAC 后，无法像第一次登录门户时一样还原到初始角色。

## <a name="related-topic"></a>相关主题

- [RBAC 角色](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [在 Microsoft Defender for Endpoint 中创建和管理设备组](machine-groups.md)
