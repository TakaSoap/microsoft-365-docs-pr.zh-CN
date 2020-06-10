---
title: 恢复非活动邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果以前的员工返回到您的组织，或者如果雇用新员工来承担 departed 员工的工作职责，则可以在 Office 365 中恢复非活动邮箱的内容。 恢复非活动邮箱时，会将其转换为新邮箱，其中包含非活动邮箱的内容。 '
ms.openlocfilehash: 63d71d2f6e23af55d94f006e772f35747c83d59c
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678968"
---
# <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

非活动邮箱（一种软删除的邮箱）用于在之前员工离开您的组织后保留他/她的电子邮件。 如果该员工返回到您的组织或其他员工承担前一个员工的工作职责，则可以通过两种方法使非活动邮箱的内容对用户可用： 
  
- **恢复非活动邮箱。** 如果以前的员工返回到您的组织，或者雇用新员工来承担前一个员工的工作职责，则可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为一个新的活动邮箱，其中包含非活动邮箱的内容。 恢复后，非活动邮箱不再存在。 本主题中的过程描述了此方法。 
    
- **还原非活动邮箱。** 如果其他员工承担前一个员工的工作职责，或者如果其他用户需要访问非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。 您还可以从非活动邮箱还原存档。 有关此方法的过程，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。

有关恢复和还原非活动邮箱之间的差异的详细信息，以及恢复非活动邮箱后所发生情况的描述，请参阅[More information](#more-information)部分。
  
## <a name="before-you-begin"></a>开始之前

- 您必须使用 Exchange Online PowerShell 来恢复非活动邮箱。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 运行以下命令获取组织中非活动邮箱的标识信息。 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    使用此命令返回的信息来恢复特定的非活动邮箱。

## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

将**新邮箱**Cmdlet 与*InactiveMailbox*参数一起使用可恢复非活动邮箱。 
  
1. 创建包含非活动邮箱的属性的变量。 
    
    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 此示例使用在上一个命令中获取的属性，并将非活动邮箱恢复到用户 Ann Beebe 的活动邮箱。 请确保为*Name*和*MicrosoftOnlineServicesID*参数指定的值在您的组织中是唯一的。 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    已恢复的非活动邮箱的主 SMTP 地址将与*MicrosoftOnlineServicesID*参数指定的值相同。 
    
恢复非活动邮箱后，还会创建一个新的用户帐户。 您必须通过分配许可证来激活此用户帐户。 若要在 Microsoft 365 管理中心中分配许可证，请参阅为[microsoft 365 商业版分配或取消分配许可证](https://go.microsoft.com/fwlink/p/?LinkId=276798)。
  
## <a name="more-information"></a>详细信息

- **恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。 相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。 非活动邮箱将保留，并且仍保留非活动状态。 对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。 仍可以使用就地电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。 

- **恢复非活动邮箱时，会发生什么情况？** 恢复非活动邮箱时，将发生以下事件： 

   - 应用于非活动邮箱的保留将根据在恢复之前应用于非活动邮箱的保留的类型进行更改或删除。
  
     - **诉讼保留。** 如果启用了非活动邮箱的诉讼保留，则会将其从恢复的邮箱中删除。
  
     - **就地保留**就地保留将从恢复的邮箱中删除。 这意味着恢复的邮箱将从任何就地保留或就地电子数据展示搜索中作为源邮箱删除。
     
     - **使用保留锁定的 Microsoft 365 保留策略。** 如果将非活动邮箱分配给具有保留锁定（称为*锁定的保留策略*）的保留策略，则会将恢复的邮箱分配给同一个锁定的保留策略。 有关锁定的保留策略的详细信息，请参阅[了解保留策略](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)。
  
     - **Microsoft 365 保留策略，无保留锁定。** 非活动邮箱将从应用于它的任何未锁定的 Microsoft 365 保留策略中删除。 但是，在恢复的邮箱上启用了诉讼保留，以防止根据删除超过特定年龄的内容的任何组织范围的保留策略来删除邮箱内容。 您可以保留诉讼保留或将其删除。 有关详细信息，请参阅[创建诉讼保留](create-a-litigation-hold.md)。

  - 单个项目恢复期间（由 **RetainDeletedItemsFor** 邮箱属性定义）设置为 30 天。通常情况下，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。将此值设置为最大值 30 天，可留出更多时间从非活动邮箱中恢复任何已永久删除（或清除）的数据。您也可以禁用单个项目恢复，或将单个项目恢复期设置为默认的 14 天。有关详细信息，请参阅 [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769)。
  
  - 保留挂起已启用，保留挂起持续时间设置为 30 天。 这意味着，分配给新邮箱的默认 Exchange 保留策略和任何组织范围或 Exchange 365 范围的保留策略将不会被处理30天。 这使复职员工或恢复的非活动邮箱的新所有者有时间来管理旧邮件。 否则，Exchange 或 Microsoft 365 保留策略可能会删除旧邮箱项目（或根据为 Exchange 或 Microsoft 365 保留策略配置的设置，将项目移至存档邮箱（如果已启用）。 30天后，保留挂起会过期， **RetentionHoldEnabled**邮箱属性设置为**False**，并且托管文件夹助理将开始处理分配给邮箱的策略。 如果您不需要此额外的时间，则可以删除保留挂起。 您也可以使用 **Set-Mailbox -EndDateForRetentionHold** 命令，增加保留挂起的持续时间。 有关详细信息，请参阅 [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300)。

- **如果您需要保留非活动邮箱的原始状态，请将恢复的邮箱置于保留状态。** 若要防止新邮箱所有者或保留策略从已恢复的非活动邮箱中永久删除任何邮件，您可以将邮箱置于诉讼保留状态。 有关详细信息，请参阅 [将邮箱放到诉讼保留中](https://go.microsoft.com/fwlink/?linkid=856286)。
    
- **恢复非活动邮箱时可以使用哪些用户 ID？** 恢复非活动邮箱时，为*MicrosoftOnlineServicesID*参数指定的值可能与与非活动邮箱关联的原始值不同。 您还可以使用原始用户 ID。 但如前面所述，在恢复非活动邮箱时，请确保用于*Name*和*MicrosoftOnlineServicesID*的值在组织内是唯一的。 
    
- **如果非活动邮箱的邮箱保留期尚未过期该怎么办？** 如果非活动邮箱是在 30 天内进行软删除的，则不能使用 **New-Mailbox -InactiveMailbox** 命令对其进行恢复。 您必须通过还原相应的用户帐户来恢复它。 有关详细信息，请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 运行以下命令。 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    如果不存在 **ExternalDirectoryObjectId** 属性的值，则说明邮箱保留期已过期，您可以通过运行 **New-Mailbox -InactiveMailbox** 命令恢复非活动邮箱。 如果**ExternalDirectoryObjectId**属性的值为，则软删除的邮箱保留期尚未过期，您必须通过还原用户帐户来恢复邮箱。 请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **请考虑在恢复非活动邮箱后启用存档邮箱。** 这样，复职用户或新员工就可以将旧邮件移动到存档邮箱。 当保留挂起过期时，作为分配给 Exchange Online 邮箱的默认 Exchange 保留策略的一部分的存档策略将把两年或更早的项目移动到存档邮箱中。 如果未启用存档邮箱，早于两年的项目将保留在用户的主邮箱中。 有关详细信息，请参阅[Enable archive 邮箱](enable-archive-mailboxes.md)。
 