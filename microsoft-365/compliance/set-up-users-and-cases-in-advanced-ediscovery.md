---
title: 在 Office 365 高级电子数据展示中设置用户和案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何配置用户角色、创建案例，以及如何将用户分配到 Office 365 高级电子数据展示中的案例。  '
ms.openlocfilehash: 76d5e6ab503cc053e31811cc06ac12545a9eeb7e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557736"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>在高级电子数据展示中设置用户和案例（经典）

本主题介绍如何为高级电子数据展示（经典）设置用户和案例。
  
> [!IMPORTANT]
> 随着我们继续在较新版本的高级电子数据展示中进行投资，我们宣布退出 Office 365 高级电子数据展示，也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0 1.0*。 如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。 高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。 若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。 
  
## <a name="prerequisites"></a>先决条件

在高级电子数据展示中设置事例和用户之前，需要满足以下条件：
  
- 若要使用高级电子数据展示分析用户的数据，必须为用户（数据管理员）分配 Office 365 E5 许可证。 或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。 分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。 
    
- 您必须是 Office 365 安全&amp;合规中心中的电子数据展示管理器角色组的成员，才能创建电子数据展示事例并向其添加成员。 若要将自己添加到安全&amp;合规中心中的电子数据展示管理器角色组，您必须是 Office 365 组织中的全局管理员。 如果您不是全局管理员，则必须要求全局管理员将您添加到电子数据展示管理器角色组。 有关详细信息，请参阅：
    
  - [Microsoft 365 安全&amp;合规中心中的权限](~/security/office-365-security/protect-against-threats.md)
    
  - [在 Microsoft 365 安全&amp;合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>步骤1：为用户分配电子数据展示权限

第一步是为用户分配安全&amp;合规性中心中的要求权限，以便可以将其添加为电子数据展示事例的成员。 在安全&amp;合规中心中将用户添加为案例的成员后，他们将能够在高级电子数据展示中访问此案例。
  
若要向用户分配必要的权限，以便可以将其添加为电子数据展示事例的成员，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的第1步。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>步骤2：创建电子数据展示事例并添加成员

下一步是在安全&amp;合规中心中创建新的电子数据展示事例并添加成员。 然后，这种情况的成员将能够访问高级电子数据展示中的案例。
  
1. 若要创建新的电子数据展示事例，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-2-create-a-new-case)步骤2。
    
2. 若要将成员添加到电子数据展示事例，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-3-add-members-to-a-case)步骤3
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>步骤3：在高级电子数据展示中进行案例

创建电子数据展示事例并添加成员后，您（或任何情况的成员）可以在高级电子数据展示中访问相应的事例。 若要在高级电子数据展示中访问事例，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)第8步。
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[准备数据](prepare-data-for-advanced-ediscovery.md)
 
