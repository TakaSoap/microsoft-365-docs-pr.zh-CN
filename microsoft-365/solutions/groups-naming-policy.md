---
title: Microsoft 365 组命名策略
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: 了解如何为 Microsoft 365 组创建命名策略。
ms.openlocfilehash: 9bc0a4c7e1ae6ad532c97b442a2bc50880a942fc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698671"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 组命名策略

可以使用组命名策略对组织中用户创建的组强制实施一致的命名策略。 命名策略可帮助你和用户识别组、成员身份、地理区域或组创建者的功能。 命名策略还有助于对通讯簿中的组进行分类。 可以使用该策略阻止在组名称和别名中使用的特定单词。

命名策略应用于跨所有组工作负载创建的组 (如 Outlook、Microsoft Teams、SharePoint、Planner、Yammer 等) 。 它将应用于组名称和组别名。 当用户创建组时，以及编辑现有组的组名称或别名时，将应用它。

> [!TIP]
> Microsoft 365 组命名策略仅适用于 Microsoft 365 组。 它不适用于在 Exchange Online 中创建的通讯组。 若要为通讯组创建命名策略，请参阅"[创建通讯组命名策略"。](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)

组命名策略包含以下功能：

- **前缀后缀命名** 策略：可以使用前缀或后缀来定义组的命名约定 (例如："US \_ My Group \_ Engineering") 。 前缀/后缀可以是固定字符串或用户属性（如 [Department]），这些属性将基于创建组的用户进行替换。

- **自定义阻止的词语**：可以上载一组特定于您的组织的阻止词，这些词语将在用户创建的组中被阻止。  (例如："CEO、Payroll、HR") 。

## <a name="licensing-requirements"></a>许可要求

使用 Microsoft 365 组的 Azure AD 命名策略需要你拥有（但不一定）为每个唯一用户 (（包括作为一个或多个 Microsoft 365 组的成员的来宾) ）分配 Azure Active Directory Premium P1 许可证或 Azure AD Basic EDU 许可证。

创建组命名策略的管理员也要求这样做。

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix命名策略

前缀和后缀可以是固定字符串或用户属性。

### <a name="fixed-strings"></a>固定字符串

可以使用短字符串来帮助区分 GAL 中的组和组工作负荷的左侧导航。 一些常见前缀后缀是关键字，如"Grp \_ \# Name"、"Name"、"Name" \_

### <a name="attributes"></a>属性

可以使用可帮助标识创建组（如 [Department]）和从何处创建组（如 [国家/地区]）的属性。

示例：

- Policy = "GRP [GroupName] [Department]"
- 用户部门 = 工程
- 已创建的组名称 = "GRP 我的组工程"

支持的 Azure Active Directory (Azure AD) 属性是 [Department]、[Company]、[Office]、[StateOrProvince]、[CountryOrRegion]和 [Title]。

- 不支持的用户属性被视为固定字符串，例如 [postalCode]。

- 不支持扩展属性和自定义属性。

建议使用为组织中所有用户填充值的属性，并且不使用具有较长值的属性。

### <a name="things-to-look-out-for"></a>要查找的方面

- 在策略创建期间，总前缀和后缀字符串长度限制为 53 个字符。

- 前缀和后缀可以包含组名称和组别名中支持的特殊字符。 当前缀和后缀包含组别名中不允许的特殊字符时，它们仅应用于组名称。 因此，在这种情况下，应用于组名称的前缀和后缀将不同于应用于组别名的前缀和后缀。

  > [!NOTE]
  > 除名称的开头或结尾之外， (.) 或连字符 (-) 在组名称中的任何位置均允许。 允许 (_) 名称中的任意位置使用下划线字符，包括名称的开头或结尾。

- 如果使用的是 Yammer Office 365 连接组，请避免在命名策略中使用下列字符：@、 \# \[ \] \<, and \> 。 如果这些字符在命名策略中，常规 Yammer 用户将无法创建组。

> [!Tip]
> - 使用短字符串作为后缀。
> - 将属性与值一同使用。
> - 不要太具有创意，总名称长度最多为 264 个字符。
> - 上传组织特定阻止的词语以限制使用。

## <a name="custom-blocked-words"></a>自定义被阻止的单词

可以输入一个逗号分隔的阻止词列表，这些单词将在组名称和别名中阻止。

不执行子字符串搜索;具体而言，用户输入的名称和自定义阻止的单词之间需要完全匹配才能触发失败。

**要查找的方面**：

- 阻止的单词不区分大小写。

- 当用户输入阻止的单词时，组客户端将显示一条包含被阻止单词的错误消息。

- 使用的被阻止的单词没有字符限制。

- 限制为 5000 个单词，可以设置为阻止的单词。

## <a name="admin-override"></a>管理员替代

某些管理员在所有组工作负载和终结点中都免除这些策略，以便他们可以使用这些阻止的词语及其所需的命名约定创建组。 以下是从组命名策略中排除的管理员角色列表。

- 全局管理员

- 合作伙伴层 1 支持

- 合作伙伴第 2 层支持

- 用户帐户管理员

## <a name="how-to-set-up-the-naming-policy"></a>如何设置命名策略

设置命名策略：

1. 在 [Azure Active Directory 中的](https://aad.portal.azure.com)"管理 **"** 下，单击 **"组"。**
2. 在 **"设置**"下 **，单击"命名策略"。**
3. 选择 **"组命名策略"** 选项卡。
4. 在 **"当前** 策略"下，选择是需要前缀还是后缀或同时需要两者，然后选中相应的复选框。
5. 在每个 **行的属性** 和 **字符串** 之间选择，然后指定属性或字符串。
6. 添加所需的前缀和后缀后，单击"保存 **"。**

![Azure Active Directory 中组命名策略设置的屏幕截图](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作治理计划](collaboration-governance-first.md)

[用于配置组设置的 Azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
