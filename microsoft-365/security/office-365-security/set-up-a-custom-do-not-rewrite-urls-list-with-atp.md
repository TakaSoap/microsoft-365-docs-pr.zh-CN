---
title: 使用 ATP 安全链接设置自定义"请勿重写 URL"列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
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
description: 了解如何为用户设置自定义阻止的 URL 以及不重写 Office 365 ATP 安全链接策略中的用户组 URL 列表。
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825229"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>使用 ATP 安全链接设置自定义"请勿重写 URL"列表

> [!IMPORTANT]
> 本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。 如果您是家庭用户，而您正在查找有关 Outlook 中安全链接的信息，请参阅"高级 [应用程序Outlook.com信息](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)"。

借 [用 Office 365 高级威胁防](office-365-atp.md) 护 (ATP) ，你的组织可能会具有 [自定义的阻止 URL，](set-up-a-custom-blocked-urls-list-atp.md)这样，当用户单击电子邮件中的 Web 地址 (URL) 或某些 Office 文档时，他们无法转到这些 URL。 贵组织还可以为组织中特定组包含自定义"不重写"列表。 "不重写"列表让一些人们都可以访问通过其他方式在 Office 365 中的 ATP 安全链接[阻止的 URL。](atp-safe-links.md)

本文介绍如何指定从 ATP 安全链接扫描中排除的 URL 列表以及需要注意的一些重要注意事项。

> [!NOTE]
> 如果组织使用安全链接策略，则"请勿重写"列表是第三方网络钓鱼测试的唯一受支持方法。

## <a name="set-up-a-do-not-rewrite-list"></a>设置"不重写"列表

ATP 安全链接保护使用多个列表，其中包括你组织的阻止的 URL 列表和"不重写"列表用于异常。 如果你具有必要权限，可以设置自定义"不要重写"列表。 当您添加或编辑应用于您组织中特定收件人的安全链接策略时，将执行此操作。

若要编辑 (定义) ATP 策略，必须分配有适当的角色。 下表包含了一些示例。 若要了解详细信息，请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。

|Role|分配位置/分配方法|
|---|---|
|全局管理员|注册以购买 Microsoft 365 的人员是默认管理员。  (了解 [详细信息，请参阅 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 管理员角色) |
|安全管理员|Azure Active Directory 管理中心 [https://aad.portal.azure.com](https://aad.portal.azure.com) () |
|Exchange Online 组织管理|Exchange 管理中心 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ()  <br>或 <br>  PowerShell cmdlet (请参阅 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) |
|

> [!TIP]
> 若要了解有关角色和权限的详细信息，请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>查看或编辑自定义"不重写"URL 列表的方法

1. 转到 [https://protection.office.com](https://protection.office.com) 工作或学校帐户并进行登录。

2. 在左侧导航中的"威 **胁管理** \> **策略安全** \> **链接"下**。

3. 在" **适用于特定收件人的策略"** 部分中， (**新建** "按钮将与 **+** () ) 类似 () ) ，以创建新策略。  (选，可以编辑现有的 policy.) <br/>![选择"新建"为特定电子邮件收件人添加安全链接策略](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. 为策略指定名称和说明。

5. 当用户 **单击** 链接时，将重写 ON URL 并对它检查已知恶意链接列表。

6. 在" **不重写以下 URL"** 部分，选择 **"输入有效的 URL"框，** 输入 URL，然后选择加号 (+) 。

7. 在" **适用于"** 部分中， **选择"收件人为以下**组的成员"，然后选择要在 (的组) 你要包括在策略中的组。 选择 **'添加**'，然后选择'**确定'。**

8. 添加完 URL 后，在屏幕右下角选择"保存 **"。**

> [!NOTE]
> 务必查看组织的阻止 URL 的自定义列表。 请参阅 [使用 ATP 安全链接设置自定义已阻止 URL 列表](set-up-a-custom-blocked-urls-list-atp.md)。

## <a name="important-points-to-keep-in-mind"></a>需要记住的重要要点

- "不要重写"列表中指定的任何 URL 都将从用于指定收件人的 ATP 安全链接扫描中排除。

- 请考虑将常用内部 URL 添加到"不重写"列表中以改善用户体验。 例如，如果拥有本地服务，如 Skype for Business 或 Sharepoint，则可将其 URL 添加到列表中以将其排除在扫描中。

- 如果您的"不重写"列表中已有 URL 的列表，请确保查看该列表，并根据需要添加通配符。 例如，如果现有列表具有类似条目，并且你想要在策略中包含子 `https://contoso.com/a` 路径 `https://contoso.com/a/b` ，请向条目添加通配符，使其看起来像 `https://contoso.com/a/*` 。

- 如果为 ATP 安全链接策略指定"不重写"列表，可以包括最多三个通配 \* () 。 通配符明确包含前缀或子域。 例如，条目 `contoso.com` 与其他选项不同 `*.contoso.com/*` ， `*.contoso.com/*` 因为允许用户访问指定域中的子域和路径。

下表列出了您可以输入内容的示例，以及这些条目产生了什么影响。

****

|示例条目|功能|
|---|---|
|`contoso.com`|允许收件人访问类似子域 `https://contoso.com` 或路径的站点。|
|`*.contoso.com/*`|允许收件人访问域、子域和路径，例如 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` ，，，或 `https://www.contoso.com/a` 。 <br/><br/> 此条目本身就更加优 `*contoso.com*` ，因为它不包含潜在的恶意站点（如或 `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|允许特定收件人访问类似网站（如 `https://contoso.com/a` ），但不允许子路径访问 `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|允许特定收件人访问类似网站和 `https://contoso.com/a` 子路径 `https://contoso.com/a/b`|
|
