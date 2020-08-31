---
title: 信息屏障策略的属性
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 这是有关用于定义信息屏障段的 Azure Active Directory 用户帐户属性的参考文章。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b6fb9cbbe5840888114ba99a604d16117ec795d
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307991"
---
# <a name="attributes-for-information-barrier-policies"></a>信息屏障策略的属性

Azure Active Directory 中的某些属性可用于分段用户。 在定义段之后，这些段可用作信息屏障策略的筛选器。 例如，如果您的 (组织中的部门不能同时为两个部门) ，则可以使用 **部门** 定义用户的各个部门的用户区段。 

本文介绍如何使用具有信息障碍的属性，并提供可使用的属性列表。 若要了解有关信息障碍的详细信息，请参阅以下资源：
- [信息屏障](information-barriers.md)
- [在 Microsoft 团队中定义信息障碍策略](information-barriers-policies.md)
- [编辑 (或删除) 信息屏障策略](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何在信息屏障策略中使用属性

本文中列出的属性可用于定义或编辑用户的各个部分。 您定义的段用作参数 (在[信息屏障策略](information-barriers-policies.md)中) 称为*UserGroupFilter*值。

1. 确定要用于定义段的属性。  (请参阅本文中的 [参考](#reference) 部分。 ) 

2. 确保已为您在步骤1中选择的属性 (s) 的用户帐户填充了值。 查看用户帐户详细信息，如有必要，请编辑用户帐户以包含属性值。 

    - 若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户) ，请参阅 [Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)。

    - 若要编辑单个帐户，请参阅 [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

3. [使用 PowerShell 定义分段](information-barriers-policies.md#define-segments-using-powershell)，类似于以下示例：

    |示例  |Cmdlet  |
    |---------|---------|
    |使用部门属性定义名为 Segment1 的段     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |使用 MemberOf 属性定义名为 SegmentA 的段 (假设此属性包含组名称，例如 "BlueGroup" )      | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |使用 ExtensionAttribute1 定义名为 DayTraders 的段。 (假设此属性包含职务，如 "DayTrader" ) |`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > 在定义段时，请对所有段使用相同的属性。 例如，如果使用 *部门*定义一些分段，则使用 *部门*定义所有分段。 请勿使用使用*MemberOf*的*部门*和其他部门定义某些分段。 请确保您的段不重叠;应将每个用户仅分配给一个分段。 

## <a name="reference"></a>参考

下表列出了可用于信息障碍的属性。

|Azure Active Directory 属性名称<br/> (LDAP 显示名称)   |Exchange 属性名称  |
|---------|---------|
|合著       | 合著        |
|Company     |公司         |
|Department     |Department         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |Alias |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName    |UserPrincipalName    |
|邮件    |WindowsEmailAddress    |
|说明    |说明    |
|MemberOf    |MemberOfGroup    |

## <a name="related-topics"></a>相关主题

[在 Microsoft 团队中定义信息障碍策略](information-barriers-policies.md)

[信息屏障疑难解答](information-barriers-troubleshooting.md)

[信息屏障](information-barriers.md)



