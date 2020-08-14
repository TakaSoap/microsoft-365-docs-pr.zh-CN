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
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: 了解如何为 Microsoft 365 组创建命名策略。
ms.openlocfilehash: 0072abf4f249af544e8234fdedec584a71c214a7
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662516"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 组命名策略

您可以使用组命名策略为组织中的用户创建的组强制实施一致的命名策略。 命名策略可帮助您和您的用户标识组、成员身份、地理区域或创建组的用户的功能。 命名策略还有助于对通讯簿中的组进行分类。 您可以使用该策略阻止在组名称和别名中使用特定字词。

命名策略适用于跨所有组工作负载创建的组， (如 Outlook、Microsoft 团队、SharePoint、Planner、Yammer 等 ) 。 它将应用于组名称和组别名。 当用户创建组时，或者在编辑现有组的组名称或别名时，将应用此方法。

> [!TIP]
> Microsoft 365 组命名策略仅适用于 Microsoft 365 组。 它不适用于 Exchange Online 中创建的通讯组。 若要创建通讯组的命名策略，请参阅 [创建通讯组命名策略](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。

组命名策略包含以下功能：

- **前缀后缀命名策略**：可以使用前缀或后缀定义组的命名约定 (例如： "US \_ My Group \_ 工程" ) 。 前缀/后缀可以是固定字符串或像 [部门] 这样的用户属性，将根据创建组的用户进行替换。

- **自定义阻止的词**：您可以将特定于您的组织的一组阻止的词上载到用户创建的组中被阻止。  (例如： "CEO，工资表，HR" ) 。

## <a name="licensing-requirements"></a>许可要求

使用 Microsoft 365 组的 Azure AD 命名策略要求您拥有（但不一定要为每个唯一用户分配 Azure Active Directory Premium P1 许可证或 Azure AD Basic EDU 许可证） (包括属于一个或多个 Microsoft 365 组成员的来宾) 。

这对于创建组命名策略的管理员来说也是必需的。

## <a name="prefix-suffix-naming-policy"></a>前缀-后缀命名策略

前缀和后缀可以是固定字符串，也可以是用户属性。

### <a name="fixed-strings"></a>固定字符串

您可以使用简短字符串来帮助您区分 GAL 中的组和组工作负荷的左侧导航。 某些常用前缀后缀是关键字，如 "Grp \_ Name"、" \# name"、" \_ name"

### <a name="attributes"></a>属性

您可以使用可帮助标识创建组（如 [部门]）的用户以及从 [国家/地区] 创建组的位置的属性。

示例：

- Policy = "GRP [个名] [部门]"
- 用户所在的部门 = 工程
- 创建的组名称 = "GRP My Group 工程"

受支持的 Azure Active Directory (Azure AD) 属性为 [部门]、[Company]、[Office]、[StateOrProvince]、[CountryOrRegion] 和 [Title]。

- 不受支持的用户属性被视为固定字符串，例如 [邮政编码]。

- 不支持扩展属性和自定义属性。

建议使用已为组织中的所有用户填充的值的属性，而不要使用具有较长值的属性。

### <a name="things-to-look-out-for"></a>要查看的内容

- 在创建策略的过程中，总前缀和后缀字符串长度限制为53个字符。

- 前缀和后缀可以包含组名和组别名中支持的特殊字符。 当前缀和后缀包含在组别名中不允许的特殊字符时，它们仅应用于组名称。 因此，在这种情况下，应用于组名称的前缀和后缀将不同于应用于组别名的前缀和后缀。

  > [!NOTE]
  > 组名称的开头或结尾处只允许 ) 或连字符 ( )  ( 的句点。 组名称中的任意位置（包括名称的开头或结尾）都允许有下划线 (_) 。

- 如果使用的是 Yammer Office 365 连接的组，请避免在命名策略中使用以下字符： @、 \# 、、 \[ \] 、 \<, and \> 。 如果这些字符位于命名策略中，则常规 Yammer 用户将无法创建组。

> [!Tip]
> - 将短字符串用作后缀。
> - 将属性与值结合使用。
> - 不太富有创意，总名称长度最多为264个字符。
> - 将组织特定阻止的词上传以限制使用。

## <a name="custom-blocked-words"></a>自定义阻止的单词

您可以输入将在组名称和别名中阻止的阻止单词的逗号分隔列表。

不执行任何子字符串搜索;具体来说，用户输入名称和自定义阻止词之间的完全匹配是触发故障所必需的。

**要查看的内容**：

- 被阻止的单词不区分大小写。

- 当用户输入被阻止的单词时，组客户端将显示一条错误消息，其中包含被阻止的单词。

- 使用的阻止词中没有字符限制。

- 有5000个字的限制可被设置为阻止的词。

## <a name="admin-override"></a>管理员替代

某些管理员在所有组的工作负荷和终结点中免除这些策略，以便他们可以使用这些阻止的词语以及所需的命名约定创建组。 下面列出了从组命名策略中免除的管理员角色。

- 全局管理员

- 合作伙伴第1层支持

- 合作伙伴第2层支持

- 用户帐户管理员

- 目录编写者

## <a name="how-to-set-up-the-naming-policy"></a>如何设置命名策略

若要设置命名策略，请执行以下操作：

1. 在 " [Azure Active Directory](https://aad.portal.azure.com)" 中的 " **管理**" 下，单击 " **组**"。
2. 在 " **设置**" 下，单击 " **命名策略**"。
3. 选择 " **组命名策略** " 选项卡。
4. 在 " **当前策略**" 下，选择是否需要前缀或后缀，或者同时选择这两者，并选中相应的复选框。
5. 在每个行的 **属性** 和 **字符串** 中进行选择，然后指定属性或字符串。
6. 添加所需的前缀和后缀后，单击 " **保存**"。

![Azure Active Directory 中的组命名策略设置的屏幕截图](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>相关主题

[用于配置组设置的 Azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
