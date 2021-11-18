---
title: 选择创建组时Microsoft 365域
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: 了解如何使用 PowerShell 配置电子邮件地址策略，选择Microsoft 365组时使用的域。
ms.openlocfilehash: 31b84304643190f343ae9ee74a947ecf6741f135
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61063306"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>选择创建组时Microsoft 365域

一些组织使用单独的电子邮件域，以区分不同的业务部分。 可以指定在用户创建组时，应该Microsoft 365域。
  
如果您的组织需要用户在企业的默认接受域外的其他域中创建其组，您可以通过使用 PowerShell 为 EAP (电子邮件地址策略) 允许此操作。

在运行 PowerShell cmdlet 之前，请下载并安装一个模块，该模块可让你与组织交谈。 请查看连接[远程Exchange Online PowerShell 进行远程访问](/powershell/exchange/connect-to-exchange-online-powershell)。

## <a name="example-scenarios"></a>示例场景

假设你的企业的主域是 Contoso.com。 但组织的默认接受域是 service.contoso.com。 这意味着将在例如 service.contoso.com (中创建组 jimsteam@service.contoso.com) 。
  
假设你还在组织中配置了子域。 您也希望在这些域中创建组：
  
- students.contoso.com 学生
    
- faculty.contoso.com 教职员工
    
以下两种方案说明了如何做到这一点。

> [!NOTE]
> 当你拥有多个 EAP 时，将按优先级顺序评估它们。 值 1 表示最高优先级。 EAP 匹配后，不会进一步计算 EAP，并且按匹配的 EAP 在组上标记的地址。 > 如果没有符合指定条件的 EAP，则组将设置在组织的默认接受域中。 请参阅管理[域中的接受Exchange Online，](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)详细了解如何添加接受域。
  
### <a name="scenario-1"></a>方案 1

以下示例演示如何在 Microsoft 365 域中设置组织的所有 groups.contoso.com 组。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>方案 2

假设你想要控制在哪些子域中Microsoft 365创建组。 你想要：
  
- 学生创建的组 (部门设置为"学生") 域中 students.groups.contoso.com组。 请使用此命令：
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- 教职员工创建的组 (部门设置为"教职员工"或电子邮件地址的用户faculty.contoso.com) ) 域中 faculty.groups.contoso.com 组。 请使用此命令：
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 由任何其他用户创建的组在 groups.contoso.com 域中创建。 请使用此命令：
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>更改电子邮件地址策略

若要更改现有 EAP 的优先级或电子邮件地址模板，请使用 Set-EmailAddressPolicy cmdlet。
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

更改 EAP 不会影响已预配的组。
  
## <a name="delete-email-address-policies"></a>删除电子邮件地址策略

若要删除 EAP，请使用 Remove-EmailAddressPolicy cmdlet。
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

更改 EAP 不会影响已预配的组。
  
## <a name="hybrid-requirements"></a>混合要求

如果您的组织在混合方案中配置，请查看使用本地 Exchange 混合配置[Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups)组，以确保组织满足创建 Microsoft 365 组的要求。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>有关使用电子邮件地址策略组的其他信息：

还有一些需要了解的方面：
  
- 组的创建速度取决于组织中配置的 EAP 数。
    
- 管理员和用户还可以在创建组时修改域。
    
- 用户组是使用标准查询来确定 (用户) 可用的用户属性。 查看 [-RecipientFilter](/powershell/exchange/recipientfilter-properties) 参数的可筛选属性，了解受支持的可筛选属性。 
    
- 如果未为组配置任何 EAP，则选择默认接受域以创建组。
    
- 如果删除接受域，应首先更新 EAPs，否则，组预配将受到影响。
    
- 最多可为组织配置 100 个电子邮件地址策略。
    
## <a name="related-content"></a>相关内容

[本文介绍的协作](collaboration-governance-overview.md#collaboration-governance-planning-recommendations) (规划) 

[Create your collaboration governance plan (](collaboration-governance-first.md) article) 

[在管理Microsoft 365中心创建一个](../admin/create-groups/create-groups.md) (组) 