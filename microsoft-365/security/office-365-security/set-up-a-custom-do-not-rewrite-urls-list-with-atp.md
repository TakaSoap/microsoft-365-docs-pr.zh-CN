---
title: 使用 ATP 安全链接设置自定义不重写 Url 列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何为 Office 365 ATP 安全链接策略中的用户组设置用户的自定义已阻止 Url 和不重写的 Url 列表。
ms.openlocfilehash: d7bd6c7d4c3dccfb4a16b2b2f172f8f75123692e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046300"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>使用 ATP 安全链接设置自定义不重写 Url 列表

> [!IMPORTANT]
> 本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。 如果您是在 Outlook 中查找有关安全链接的信息的家庭用户，请参阅[Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)。

使用[Office 365 高级威胁防护](office-365-atp.md)（ATP），您的组织可以有一个[自定义的阻止 url](set-up-a-custom-blocked-urls-list-atp.md)，这样，当用户单击电子邮件中的 web 地址（Url）或某些 Office 文档时，将阻止这些 Url 转到这些 url。 您的组织还可以为组织中的特定组提供自定义的 "不重写" 列表。 "不重写" 列表使某些用户能够访问由[Office 365 中的 ATP 安全链接](atp-safe-links.md)阻止的 url。

本文介绍如何指定从 ATP 安全链接扫描中排除的 Url 的列表，以及需要牢记的几个重要事项。

## <a name="set-up-a-do-not-rewrite-list"></a>设置 "不重写" 列表

ATP 安全链接保护使用多个列表，包括组织的阻止 Url 列表和 "不重写" 列表中的例外。 如果您具有必要的权限，则可以设置自定义的 "不重写" 列表。 在添加或编辑适用于组织中特定收件人的安全链接策略时，可以执行此操作。

若要编辑（或定义） ATP 策略，必须为您分配适当的角色。 下表包括一些示例。 若要了解详细信息，请参阅[安全性 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

|角色  |分配的位置/方式  |
|---------|---------|
|全局管理员 |默认情况下，注册购买 Microsoft 365 的人是全局管理员。 （请参阅[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。）         |
|安全管理员 |Azure Active Directory 管理中心（[https://aad.portal.azure.com](https://aad.portal.azure.com)）|
|Exchange Online 组织管理 |Exchange 管理中心（[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)） <br>或 <br>  PowerShell cmdlet （请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)） |

> [!TIP]
> 若要了解有关角色和权限的详细信息，请参阅[Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>查看或编辑自定义 "不重写" Url 列表

1. 转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。

2. 在左侧导航中的 "**威胁管理** \> **策略** \> **安全链接**" 下。

3. 在 "**适用于特定收件人的策略**" 部分，选择 "**新建**" （"新建" 按钮类似**+** 于加号（））以创建新策略。 （也可以编辑现有策略。）<br/>![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. 为策略指定名称和说明。

5. 在 "**不重写以下 url"** 部分，选择 "**输入一个有效的 url** " 框，然后键入 URL，然后选择加号（+）。

6. 在 "**应用**于" 部分中，选择 **"收件人是其成员**"，然后选择要包括在策略中的组。 选择 "**添加**"，然后选择 **"确定"**。

7. 添加完 Url 后，在屏幕的右下角，选择 "**保存**"。

> [!NOTE]
> 请务必查看您的组织的已阻止 Url 的自定义列表。 请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。

## <a name="important-points-to-keep-in-mind"></a>需要牢记的要点

- 您在 "不重写" 列表中指定的任何 Url 将从 ATP 安全链接扫描中排除，用于您指定的收件人。

- 如果您在 "不重写" 列表中已经有 Url 列表，请务必查看该列表并根据需要添加通配符。 例如，如果您的现有列表中有类似`https://contoso.com/a`的条目，并且您希望在策略`https://contoso.com/a/b`中包含类似的子路径，请将通配符添加到您的`https://contoso.com/a/*`条目，使其看起来像这样。

- 当您为 ATP 安全链接策略指定 "不重写" 列表时，可以包含最大为三个通配符星号（\*）。 通配符（\*）用于显式包含前缀或子域。 该条目`contoso.com`与相同`*.contoso.com/*`，因为`*.contoso.com/*`允许人们访问指定域中的子域和路径。

下表列出了可以输入的内容的示例以及这些项有何影响。

|**示例条目**|**功能**|
|:-----|:-----|
|`contoso.com`|允许收件人访问的网站（如`https://contoso.com`不是子域或路径）。|
|`*.contoso.com/*`|允许收件人访问域、子域和路径， `https://www.contoso.com`例如、 `https://www.contoso.com` `https://maps.contoso.com`、或。 `https://www.contoso.com/a` <br/><br/> 此条目的本质`*contoso.com*`上优于，因为它不包含潜在的欺诈网站， `https://www.falsecontoso.com`如或`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|允许特定收件人访问类似`https://contoso.com/a`的网站，但不允许像这样的子路径`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|允许特定收件人访问像这样的子`https://contoso.com/a`网站之类的子网站`https://contoso.com/a/b`|
