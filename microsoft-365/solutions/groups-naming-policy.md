---
title: Microsoft 365组命名策略
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
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: 了解如何为组创建命名Microsoft 365策略。
ms.openlocfilehash: 9fb75feb255ee6d58313f4cfaf3486c4a8cd63b4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213405"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365组命名策略

可以使用组命名策略为组织中用户创建的组强制实施一致的命名策略。 命名策略可帮助你和用户识别组的功能、成员身份、地理区域或创建组的用户。 命名策略还可以帮助对通讯簿中的组进行分类。 可以使用该策略阻止在组名称和别名中使用的特定单词。

命名策略应用于跨所有组工作负载创建的组 (如 Outlook、Microsoft Teams、SharePoint、Planner、Yammer 等) 。 它将应用于组名和组别名。 当用户创建组时，以及为现有组编辑组名称、别名、说明或头像时，也会应用该规则。

> [!TIP]
> A Microsoft 365 group naming policy only applies to Microsoft 365 groups. 它不适用于在 Exchange Online 中创建的通讯Exchange Online。 若要为通讯组创建命名策略，请参阅创建通讯 [组命名策略](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。

组命名策略包含以下功能：

- **前缀后缀命名策略**：可以使用前缀或后缀来定义组的命名约定 (例如："US \_ My Group \_ Engineering") 。 前缀/后缀可以是固定字符串或用户属性（如 [Department]），这些属性将基于创建组的用户进行替换。

- **自定义阻止的词语**：可以上载一组特定于组织、将在用户创建的组中被阻止的被阻止的单词。  (例如："CEO、Payroll、HR") 。

## <a name="licensing-requirements"></a>许可要求

对 Microsoft 365 组使用 Azure AD 命名策略需要你拥有但不一定为每个唯一用户分配 Azure Active Directory Premium P1 许可证或 Azure AD Basic EDU 许可证 (包括来宾) ，它是一个或多个 Microsoft 365 组的成员。

创建组命名策略的管理员也要求这样做。

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix命名策略

前缀和后缀可以是固定字符串或用户属性。

### <a name="fixed-strings"></a>固定字符串

可以使用短字符串来帮助区分 GAL 中的组和组工作负荷的左侧导航。 一些常见前缀后缀是关键字，如"Grp \_ Name"、"Name" \# 和 \_ "Name"

### <a name="attributes"></a>属性

可以使用可帮助标识创建组（如 [部门]）和从何处创建组（如 [国家/地区]）的属性。

示例：

- Policy = "GRP [GroupName] [Department]"
- 用户的部门 = 工程
- 已创建组名称 = "GRP My Group Engineering"

支持Azure Active Directory (Azure AD) 属性有 [Department]、[Company]、[Office]、[StateOrProvince]、[CountryOrRegion] 和 [Title]。

- 不支持的用户属性被视为固定字符串，例如 [postalCode]。

- 不支持扩展属性和自定义属性。

建议使用为组织中所有用户填充值的属性，而不要使用具有较长值的属性。

### <a name="things-to-look-out-for"></a>要查找的方面

- 在策略创建期间，总前缀和后缀字符串长度限制为 53 个字符。

- 前缀和后缀可以包含在组名和组别名中支持的特殊字符。 当前缀和后缀包含组别名中不允许的特殊字符时，它们仅应用于组名称。 因此，在这种情况下，应用于组名的前缀和后缀将不同于应用于组别名的前缀和后缀。

  > [!NOTE]
  > 组名称 (.) 或连字符 (-) ，但名称开头或结尾处除外。 在 (_) 名称中的任意位置（包括名称的开头或结尾处）都允许使用下划线字符。

- 如果要在连接的Yammer Office 365，请避免在命名策略中使用下列字符 \# ：@、、、、、。 \[ \] \<, and \> 如果这些字符在命名策略中，Yammer用户将无法创建组。

> [!Tip]
> - 使用短字符串作为后缀。
> - 将属性与值一同使用。
> - 不要太具有创意，总名称长度最多为 264 个字符。
> - Upload组织特定的阻止词语来限制使用。

## <a name="custom-blocked-words"></a>自定义阻止的词语

可以在组名和别名中输入将阻止的被阻止单词的逗号分隔列表。

不执行子字符串搜索;具体而言，需要用户输入的名称和自定义阻止的词语之间的完全匹配才能触发失败。

**要查找的一些内容**：

- 阻止的单词不区分大小写。

- 当用户输入阻止的单词时，组客户端将显示一条包含被阻止单词的错误消息。

- 使用的被阻止的单词没有字符限制。

- 限制为 5000 个单词，可以设置为阻止的单词。

## <a name="admin-override"></a>管理员替代

所有组工作负载和终结点中的一些管理员都免除了这些策略，以便他们可以使用这些阻止的词语及其所需的命名约定创建组。 以下是从组命名策略中排除的管理员角色列表。

- 全局管理员

- 合作伙伴第 1 层支持

- 合作伙伴第 2 层支持

- 用户帐户管理员

## <a name="how-to-set-up-the-naming-policy"></a>如何设置命名策略

设置命名策略：

1. 在 [Azure Active Directory](https://aad.portal.azure.com)中，在"管理 **"下**，单击"组 **"。**
2. 在 **"设置"** 下，单击 **"命名策略"。**
3. 选择" **组命名策略"** 选项卡。
4. 在 **"当前** 策略"下，选择是否需要前缀或后缀或同时需要两者，然后选中相应的复选框。
5. 在每个 **行的属性** 和 **字符串** 之间选择，然后指定属性或字符串。
6. 添加所需的前缀和后缀后，单击"保存 **"。**

![Screenshot of the groups naming policy settings in Azure Active Directory.](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[用于配置组设置的 Azure Active Directory cmdlet](/azure/active-directory/enterprise-users/groups-settings-cmdlets)