---
title: 在租户允许/阻止列表中管理允许和阻止的 Url
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全 & 合规性中心的租户允许/阻止列表中配置 URL 条目。
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614960"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>管理租户允许/阻止列表中的 URL

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 本主题中所述的功能处于预览阶段，可能会发生更改，并且在所有组织中均不可用。

在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，您可能不同意 EOP 筛选判定。 例如，良好的邮件可能会被标记为 "错误" (误报) ，或者可能允许通过 (false 否定) 的错误消息。

Security & 合规性中心中的租户允许/阻止列表为你提供了一种手动替代 Microsoft 365 筛选 verdicts 的方法。 在邮件流期间和用户单击时使用租户允许/阻止列表。 可以在 "租户允许/阻止" 列表中指定允许或阻止的 Url。

本主题介绍如何使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中的 Microsoft 365 组织配置租户允许/阻止列表中的条目;没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **租户允许/阻止列表** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。

- 在本主题后面的 [租户允许/阻止列表部分的 url 语法](#url-syntax-for-the-tenant-allowblock-list) 中介绍了可用的 url 值。

- 租户允许/阻止列表允许 Url 最多为500个条目。

- 条目应在15分钟内处于活动状态。

- 阻止项优先于允许项。

- 默认情况下，租户允许/阻止列表中的条目将在30天后过期。 您可以指定一个日期或将它们设置为永不过期。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要添加和删除租户允许/阻止列表中的值，您需要是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。
  - 若要对租户允许/阻止列表进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>使用安全 & 合规性中心在租户允许/阻止列表中创建 URL 条目

有关 URL 项的语法的详细信息，请参阅本主题后面的 [租户允许/阻止列表部分的 URL 语法](#url-syntax-for-the-tenant-allowblock-list) 。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。

2. 在 "**租户允许/阻止列表**" 页上，确认已选择 " **url** " 选项卡，然后单击 "**添加**"

3. 在出现的 " **添加新 url** " 浮出控件中，配置以下设置：

   - **添加带通配符的 url**：每行输入一个 URL，最多为20个。

   - **阻止/允许**：选择是否要 **允许** 或 **阻止** 指定的 url。

   - **永不过期**：执行下列步骤之一：

     - 验证设置是否已关闭 (![ 切换 ](../../media/scc-toggle-off.png)) 并使用 " **过期时间** " 框指定条目的到期日期。

     或

     - 将切换向右移动以将条目配置为永不过期： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **可选注释**：输入条目的描述性文本。

4. 完成后，请单击 " **添加**"。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全 & 合规性中心查看租户允许/阻止列表中的条目

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。

2. 选择 " **url** " 选项卡。

单击以下列标题，以按升序或降序进行排序：

- **值**
- **操作**： **阻止** 或 **允许**。
- **上次更新日期**
- **过期日期**
- **注意**

单击 " **组** " 将按 **操作** 对条目进行分组 (**阻止** 或 **允许**) 或 " **无**"。

单击 " **搜索**"，输入全部或部分值，然后按 enter 以查找特定值。 完成后，请单击 " **清除搜索**" "清除 ![ 搜索" 图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

单击 " **筛选**"。 在出现的 **筛选器** 浮出控件中，配置以下任一设置：

- **操作**：选择 " **允许**"、" **阻止** " 或两者。

- **永不过期**：选中 "关闭 (![ 切换 ](../../media/scc-toggle-off.png) ") 或 "在 ![) 上 (切换" ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。

- **上次更新** 时间： **从**) 中选择开始日期 (，结束日期 (**为**) 或同时更新两者。

- **过期日期**： **从**) 中选择开始日期 (，结束日期 (为) 或同时 **为** 两者。

完成后，请单击 " **应用**"。

若要清除现有筛选器，请单击 " **筛选**"，并在出现的 **筛选器** 浮出控件中，单击 " **清除筛选**"

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>使用安全 & 合规性中心修改租户允许/阻止列表中的条目

您不能修改 URL 值本身。 相反，您需要删除并重新创建该条目。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。

2. 选择 " **url** " 选项卡。

3. 选择要修改的条目，然后单击 " **编辑** ![ 编辑图标" ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 在出现的浮出控件中，配置以下设置：

   - **阻止/允许**：选择 " **允许** " 或 " **阻止**"。

   - **永不过期**：执行下列步骤之一：

     - 验证设置是否已关闭 (![ 切换 ](../../media/scc-toggle-off.png)) 并使用 " **过期时间** " 框指定条目的到期日期。

     或

     - 将切换向右移动以将该项配置为永不过期： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **可选注释**：输入条目的描述性文本。

5. 完成时，请单击“保存”。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>使用安全 & 合规性中心删除租户允许/阻止列表中的条目

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。

2. 选择 " **url** " 选项卡。

3. 选择要删除的条目，然后单击 " **删除** ![ 删除图标" ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 在出现的警告对话框中，单击 " **删除**"。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 在租户允许/阻止列表中添加条目

若要添加租户允许/阻止列表中的条目，请使用以下语法：

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

本示例为 contoso.com 和所有子域 (添加 URL 阻止项，例如，contoso.com、www.contoso.com 和 xyz.abc.contoso.com) 。 由于我们未使用 ExpirationDate 或 NoExpiration 参数，因此该条目将在30天后过期。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 查看租户允许/阻止列表中的条目

若要查看租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

本示例返回所有被阻止的 Url。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改租户允许/阻止列表中的条目

您不能修改 URL 值本身。 相反，您需要删除并重新创建该条目。

若要修改租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

本示例将更改指定条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 删除租户允许/阻止列表中的条目

若要从租户允许/阻止列表中删除条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

本示例将从租户允许/阻止列表中删除指定的 URL 条目。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>租户允许/阻止列表的 URL 语法

- 允许使用 IP4v 和 IPv6 地址，但 TCP/UDP 端口不允许。

- 不允许使用文件名扩展 (例如，test.pdf) 。

- Unicode 不受支持，但 Punycode 是。

- 如果下列所有语句都为真，则允许使用主机名：

  - 主机名包含一个句点。
  - 句点的左侧至少有一个字符。
  - 句点的右侧至少有两个字符。

  例如， `t.co` 允许; `.com` 或 `contoso.` 不允许。

- 不暗含子路径。

  例如，不 `contoso.com` 包括 `contoso.com/a` 。

- 在以下方案中允许使用通配符 ( * ) ：

  - 左侧通配符后面必须跟一个句点以指定一个子域。

    例如， `*.contoso.com` 允许; `*contoso.com` 不允许。

  - 右通配符必须遵循正斜杠 (/) 指定路径。

    例如， `contoso.com/*` 允许; `contoso.com*` 或 `contoso.com/ab*` 不允许。

  - 所有子路径都不是由右侧通配符暗示的。

    例如，不 `contoso.com/*` 包括 `contoso.com/a` 。

  - `*.com*` 无效 (不是可解析的域，右通配符不跟正斜线) 。

  - IP 地址中不允许使用通配符。

- 在以下方案中，可以使用颚化符 (~) 字符：

  - 左波形符表示域和所有子域。

    例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。

- 包含协议的 URL 项 (例如、、 `http://` `https://` 或 `ftp://`) 将失败，因为 url 条目适用于所有协议。

- 不支持或不需要用户名或密码。

- 引号 ( "或" ) 是无效字符。

- URL 应尽可能包含所有重定向。

### <a name="url-entry-scenarios"></a>URL 入口应用场景

以下各节介绍了有效的 URL 条目及其结果。

#### <a name="scenario-no-wildcards"></a>方案：不带通配符

**条目**： `contoso.com`

- **允许匹配**： contoso.com

- **允许不匹配**：

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. .com/q = a@contoso

- **块匹配**：

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. .com/q = a@contoso

- **阻止不匹配**： abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>方案： Left 通配符 (子域) 

**条目**： `*.contoso.com`

- **允许匹配** 和 **阻止匹配**：

  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配** 和 **阻止不匹配**：

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>方案： path 顶部的右通配符

**条目**： `contoso.com/a/*`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso/a/？ q = joe@t .com

- **允许不匹配** 和 **阻止不匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. .com/q = a@contoso

#### <a name="scenario-left-tilde"></a>方案：左波形符

**条目**： `~contoso.com`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配** 和 **阻止不匹配**：

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>方案：右侧通配符后缀

**条目**： `contoso.com/*`

- **允许匹配** 和 **阻止匹配**：

  - contoso/？ q = whatever@fabrikam
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow 不匹配** 和 **阻止不匹配**： contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>方案：左通配符子域和右侧通配符后缀

**条目**： `*.contoso.com/*`

- **允许匹配** 和 **阻止匹配**：

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow 不匹配** 和 **阻止不匹配**： contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>方案：左和右波形符

**条目**： `~contoso.com~`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **允许不匹配** 和 **阻止不匹配**：

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>方案： IP 地址

**条目**： `1.2.3.4`

- **允许匹配** 和 **阻止匹配**：1.2.3。4

- **允许不匹配** 和 **阻止不匹配**：

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>使用右侧通配符的 IP 地址

**条目**： `1.2.3.4/*`

- **允许匹配** 和 **阻止匹配**：

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>无效条目的示例

以下条目无效：

- **缺少或无效的域值**：

  - 尚未
  - \*尚未.\*
  - \*.com
  - \*.pdf

- **文本上的通配符或不含间距的字符**：

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **带有端口的 IP 地址**：

  - contoso.com:443
  - abc.contoso.com:25

- **不描述的通配符**：

  - \*
  - \*.\*

- **中间通配符**：

  - conto \* so.com
  - conto ~ .com

- **双通配符**

  - contoso.com/\*\*
  - contoso.com/\*/\*
