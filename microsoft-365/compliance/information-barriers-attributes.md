---
title: 信息屏障策略的属性
description: 本文引用了可用于定义信息屏障段的 Azure Active Directory 用户帐户属性。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c45a2733c1fa7cf6d05cff747a9cfcdba1b124cc
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126159"
---
# <a name="attributes-for-information-barrier-policies"></a>信息屏障策略的属性

Azure Active Directory 中的某些属性可用于划分用户。 定义线段后，这些线段可以用作信息屏障策略的筛选器。 例如，可以使用"部门"按组织内部的部门定义用户细分 (假定没有一名员工同时为两个部门) 。

本文介绍如何将属性与信息障碍一同使用，并提供了可以使用的属性列表。 若要了解有关信息屏障详细信息，请参阅以下资源：

- [信息屏障](information-barriers.md)
- [在 Microsoft Teams 中定义信息屏障策略](information-barriers-policies.md)
- [编辑 (或删除) 信息屏障策略](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何在信息屏障策略中使用属性

本文中列出的属性可用于定义或编辑用户细分。 你定义的区段用作 (策略中) *UserGroupFilter* [值的参数](information-barriers-policies.md)。

1. 确定要用于定义线段的属性。  ([请参阅本文中的](#reference) 参考部分。) 

2. 确保用户帐户已针对在步骤 1 中 () 属性填充了值。 查看用户帐户详细信息，如有必要，编辑用户帐户以包含属性值。 

    - 若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户) ，请参阅"使用[Office 365 PowerShell 配置用户帐户属性"。](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

    - 若要编辑单个帐户，请参阅使用 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)添加或更新用户配置文件信息。

3. [使用 PowerShell](information-barriers-policies.md#define-segments-using-powershell)定义线段，类似于以下示例：

    |**示例**|**Cmdlet**|
    |:----------|:---------|
    | 使用 Department 属性定义名为 Segment1 的线段 | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | 使用 MemberOf 属性定义名为 SegmentA 的 (假定此属性包含组名称，例如"BlueGroup")  | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | 使用 ExtensionAttribute1 定义名为 DayTraders 的 (假定此属性包含职务，例如"DayTrader")  | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > 定义线段时，请为所有线段使用相同的属性。 例如，如果使用 Department 定义某些线 *段，则* 使用 Department 定义所有 *线段*。 请勿使用 Department 定义某些 *分段，* 而使用 *MemberOf 定义其他分段*。 确保线段不重叠;每个用户应只分配到一个区段。

## <a name="reference"></a>参考

下表列出了可用于信息障碍的属性。

|**AZURE Active Directory 属性名称 (<br/> LDAP 显示名称)**|**Exchange 属性名称**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | 公司 |
| Department | Department |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| 邮件 | WindowsEmailAddress |
| 说明 | 说明 |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>资源

- [在 Microsoft Teams 中定义信息屏障策略](information-barriers-policies.md)
- [信息屏障疑难解答](information-barriers-troubleshooting.md)
- [信息屏障](information-barriers.md)
