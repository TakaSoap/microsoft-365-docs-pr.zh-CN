---
title: 选择创建 Microsoft 365 组时要使用的域
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: '了解如何在使用 PowerShell 配置电子邮件地址策略时选择要在创建 Microsoft 365 组时使用的域。 '
ms.openlocfilehash: 5569f42f15835be02a20166e64ce09a08b146dd7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388205"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>选择创建 Microsoft 365 组时要使用的域

 一些组织使用单独的电子邮件域，以区分不同的业务部分。 您可以指定在用户创建 Microsoft 365 组时应使用的域。
  
如果您的组织需要用户在企业的默认接受域以外的其他域中创建其组，则可以通过使用 PowerShell 配置电子邮件地址策略（EAPs）来允许这样做。
  
在运行 PowerShell cmdlet 之前，请下载并安装可让您与您的组织对话的模块。 请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785881)。
  
## <a name="example-scenarios"></a>示例场景

假设您的企业的主域是 Contoso.com。 但您的组织的默认接受域是 service.contoso.com。 这意味着将在 service.contoso.com 中创建组（例如，jimsteam@service.contoso.com）。
  
假设您在组织中配置了子域。 您还希望在这些域中创建组：
  
- students.contoso.com 学生版
    
- 教职员工成员的 faculty.contoso.com
    
以下两种方案说明了如何实现此目的。
  
> [!NOTE]
> 当您拥有多个 EAPs 时，将按优先级顺序对它们进行评估。 值为1表示最高优先级。 EAP 匹配后，将不会评估任何其他 EAP，并且在该组上标记的地址按匹配的 EAP 进行。 > 如果没有 EAPs 匹配指定条件，则会在组织的默认接受域中设置组。 请查看在[Exchange Online 中管理接受的域](https://go.microsoft.com/fwlink/p/?LinkId=785428)，以了解有关如何添加接受域的详细信息。 
  
### <a name="scenario-1"></a>方案 1

下面的示例演示如何在 groups.contoso.com 域中预配组织中的所有 Microsoft 365 组。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>方案 2

假设您想要控制在其中创建的子域 Microsoft 365 组。 你想要：
  
- 由 students.groups.contoso.com 域中的学生（将**部门**设置为**学生**的用户）创建的组。 请使用此命令：
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- 由教职员（在 "**部门**" 设置为 "教职员"**或 "电子邮件地址**" 的用户）在 faculty.groups.contoso.com 域中创建的组。 请使用此命令：
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Groups.contoso.com 域中的所有其他用户。 请使用此命令：
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>更改电子邮件地址策略

若要更改现有 EAP 的优先级或电子邮件地址模板，请使用 Update-emailaddresspolicy cmdlet。
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

更改 EAP 对已设置的组没有影响。
  
## <a name="delete-email-address-policies"></a>删除电子邮件地址策略

若要删除 EAP，请使用 Update-emailaddresspolicy cmdlet。
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

更改 EAP 对已设置的组没有影响。
  
## <a name="hybrid-requirements"></a>混合要求

如果您的组织是在混合方案中配置的，请查看[使用本地 Exchange 混合配置 Microsoft 365 组](https://go.microsoft.com/fwlink/p/?LinkId=785430)，以确保您的组织满足创建 Microsoft 365 组的要求。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>有关使用电子邮件地址策略组的其他信息：

还需要了解几个问题：
  
- 创建快速组的方式取决于您的组织中配置的 EAPs 的数量。
    
- 管理员和用户也可以在创建组时修改域。
    
- 用户组是使用已有的标准查询（用户属性）确定的。 对于受支持的可筛选属性，请查看[-RecipientFilter 参数的可筛选属性](https://go.microsoft.com/fwlink/p/?LinkId=785918)。 
    
- 如果没有为组配置任何 EAPs，则选择 "创建组的默认接受域"。
    
- 如果删除接受域，则应首先更新 EAPs，否则组设置将受到影响。
    
- 可以为组织配置最大值为100的电子邮件地址策略。
    
## <a name="related-articles"></a>相关文章

[在管理中心创建 Microsoft 365 组](create-groups.md)
