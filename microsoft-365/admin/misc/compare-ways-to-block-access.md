---
title: 比较阻止访问的方法
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 了解如何在员工离开Microsoft 365时阻止对员工的访问权限。
ms.openlocfilehash: d9099f375af4d3fb6ff7c4583ec2bb925e7f0c342711ade8b8f83c4676cdc4d1
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824189"
---
# <a name="compare-ways-to-block-access"></a>比较阻止访问的方法

当员工离开组织时，如果条件好或坏，你需要阻止他们访问Microsoft 365。 可通过以下几种方法实现此要求。
  
|阻止访问的方法|定义|最佳做法|
|:-----|:-----|:-----|
|阻止登录  <br/> |阻止用户访问登录Microsoft 365一个方法就是将用户的登录状态更改为 **"已阻止登录"。** 这可以防止他们从计算机Microsoft 365登录电子邮件，尽管他们仍然可以查看以前下载或同步的电子邮件和文档。 如果你使用的是 Blackberry Enterprise 服务，也可以禁用其访问。  <br/> |在员工计划离开组织或计划长期离开时使用。  <br/> |
|重置用户密码  <br/> |另一种防止用户访问Microsoft 365重置其密码。 这将阻止他们使用其帐户，尽管他们仍可查看以前下载或同步的电子邮件和文档。 然后，你可以以他们帐户登录，然后将密码更改为你选择的密码之一。  <br/> |当员工突然永久离开，并且您觉得对业务数据有顾虑时，请使用 。  <br/> |
|删除所有分配的许可证  <br/> |另一个选项是删除Microsoft 365用户的任何许可证。 这将阻止他们使用应用程序和服务，如 Office 套件、Office Web 应用、Yammer和 SharePoint Online。 他们仍可登录，但无法使用这些服务。  <br/> |当您觉得此用户不再需要访问 Microsoft 365 中的特定功能时Microsoft 365。  <br/> <br> **重要提示：** 删除许可证后，用户邮箱将在 30 天后删除。
   
## <a name="related-articles"></a>相关文章

[将用户从用户Microsoft 365](../add-users/remove-former-employee.md)
    
[重置用户密码Microsoft 365](../add-users/reset-passwords.md)
    
[将许可证分配给企业Microsoft 365中的用户](../manage/assign-licenses-to-users.md)
    
[在企业版中删除Microsoft 365许可证](../manage/remove-licenses-from-users.md)
    

