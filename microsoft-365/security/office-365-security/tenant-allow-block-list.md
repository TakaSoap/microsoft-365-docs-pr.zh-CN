---
title: 在租户允许/阻止列表中管理允许和阻止的 URL
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
description: 管理员可以了解如何在安全与合规中心的租户允许/阻止& URL 条目。
ms.openlocfilehash: f60e2f29bf9b880e9d2247fa59554300ae348a03
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683207"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>管理租户允许/阻止列表中的 URL

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且并非在所有组织中都可用。

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，您可能与 EOP 筛选裁定不一致。 例如，一条好邮件可能标记为误报 (误报) ，或者可能允许错误邮件通过漏报 (漏报) 。

安全与合规中心中的租户&/阻止列表提供了一种手动替代 Microsoft 365 筛选裁定的方法。 租户允许/阻止列表在邮件流期间和用户单击时使用。 可以在租户允许/阻止列表中指定允许或阻止的 URL。

本主题介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止列表条目;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到租户允许 **/阻止列表** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。

- 本文稍后的"租户允许/阻止列表"一节的 URL 语法中介绍了 [可用的](#url-syntax-for-the-tenant-allowblock-list) URL 值。

- 租户允许/阻止列表允许最多 500 个 URL 条目。

- 条目应在 15 分钟内处于活动状态。

- 阻止条目优先于允许条目。

- 默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。 可以指定日期或将其设置为永不过期。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要在租户允许/阻止列表中添加和删除值，你需要是组织 **管理或** 安全管理员角色 **组** 的成员。
  - 若要对租户允许/阻止列表进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>使用安全&中心在租户允许/阻止列表中创建 URL 条目

有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的"租户允许 [/阻止](#url-syntax-for-the-tenant-allowblock-list) 列表"一节的 URL 语法。

1. 在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 在 **"租户允许/阻止列表** "页上，验证是否选择了 **"URL"** 选项卡，然后单击"添加 **"**

3. 在 **出现的"添加新 URL"** 飞出中，配置以下设置：

   - **添加包含通配符的 URL：** 每行输入一个 URL，最多 20 个。

   - **阻止/允许**：选择 **是允许还是****阻止** 指定的 URL。

   - **永不过期**：执行下列步骤之一：

     - 验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 

     或

     - 将开关向右移动以将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选注意**：输入条目的描述性文本。

4. 完成后，单击"添加 **"。**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全&合规中心查看租户允许/阻止列表中的条目

1. 在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 选择 **"URL"** 选项卡。

单击以下列标题以按升序或降序排序：

- **值**
- **操作**： **阻止** 或 **允许**。
- **上次更新日期**
- **到期日期**
- **注意**

单击 **"分组**"按"操作" ("阻止"或") "或"无"对 **条目进行分组**。  

单击 **"搜索**"，输入全部或部分值，然后按 Enter 查找特定值。 完成后，单击" **清除搜索清除** ![ 搜索"图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

单击 **"筛选"。** 在 **出现的"** 筛选器"飞出中，配置以下任一设置：

- **操作**：选择 **"允许"****和/或"阻止**"。

- **永不过期**： 选择关闭： ![ 关闭 ](../../media/scc-toggle-off.png) 或打开： ![ 切换。 ](../../media/scc-toggle-on.png)

- **Last updated**： Select a start date (**From**) ， an end date (**To**) both.

- **到期日期：** 选择开始日期 (开始日期) 、结束日期 () 两者。  

完成后，单击"应用 **"。**

若要清除现有筛选器，请单击 **"筛选器**"，在出现的 **"** 筛选器"飞出中，单击 **"清除筛选器"。**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>使用安全&合规中心修改租户允许/阻止列表中的条目

不能修改 URL 值本身。 相反，需要删除条目并重新创建它。

1. 在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 选择 **"URL"** 选项卡。

3. 选择要修改的条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 在出现的飞出中，配置以下设置：

   - **阻止/允许**：选择 **"允许"** 或"**阻止"。**

   - **永不过期**：执行下列步骤之一：

     - 验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 

     或

     - 将开关向右移动以将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选注意**：输入条目的描述性文本。

5. 完成时，请单击“保存”。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>使用安全&合规中心从租户允许/阻止列表中删除条目

1. 在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 选择 **"URL"** 选项卡。

3. 选择要删除的条目，然后单击"删除 **"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 在出现的警告对话框中，单击"删除 **"。**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 在租户允许/阻止列表中添加条目

若要在租户允许/阻止列表中添加条目，请使用以下语法：

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

此示例为网站和contoso.com域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加 URL 阻止xyz.abc.contoso.com) 。 由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 查看租户允许/阻止列表中的条目

若要查看租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

此示例返回所有阻止的 URL。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改租户允许/阻止列表中的条目

不能修改 URL 值本身。 相反，需要删除条目并重新创建它。

若要修改租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

本示例更改指定条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 从租户允许/阻止列表中删除条目

若要从租户允许/阻止列表中删除条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

此示例从租户允许/阻止列表中删除指定的 URL 条目。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

有关语法和参数的详细信息，请参阅[Remove-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>租户允许/阻止列表的 URL 语法

- 允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。

- 例如，不允许使用 (扩展名test.pdf) 。

- 不支持 Unicode，但 Punycode 支持。

- 如果以下所有语句都为 true，则允许使用主机名：

  - 主机名包含一个时间段。
  - 在时间段的左侧至少有一个字符。
  - 此期间右侧至少有两个字符。

  例如， `t.co` 允许; `.com` `contoso.` 或不允许。

- 不隐含子路径。

  例如， `contoso.com` 不包括 `contoso.com/a` 。

- 在下列 (允许) *通配符：

  - 左通配符后必须跟一个时间段，以指定子域。

    例如， `*.contoso.com` 允许; `*contoso.com` 不允许。

  - 右通配符必须遵循正斜杠 (/) 指定路径。

    例如， `contoso.com/*` 允许; `contoso.com*` `contoso.com/ab*` 或不允许。

  - 右通配符不隐含所有子路径。

    例如， `contoso.com/*` 不包括 `contoso.com/a` 。

  - `*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。

  - IP 地址中不允许使用通配符。

- 下列情况下 (~) 符：

  - 左波浪符表示域和所有子域。

    例如 `~contoso.com` ，includes `contoso.com` 和 `*.contoso.com` 。

- 包含协议（例如， (，或) ）的 URL 条目将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。

- 不支持或不需要用户名或密码。

- 引号 ("或") 无效字符。

- URL 应包含所有重定向（如果可能）。

### <a name="url-entry-scenarios"></a>URL 条目方案

以下各节介绍了有效的 URL 条目及其结果。

#### <a name="scenario-no-wildcards"></a>方案：无通配符

**条目**： `contoso.com`

- **允许匹配**：contoso.com

- **允许不匹配**：

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **阻止匹配**：

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **阻止不匹配**： abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>方案：将通配符 (子域) 

**条目**： `*.contoso.com`

- **允许匹配** 和 **阻止匹配**：

  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配和****阻止不匹配**：

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>方案：路径顶部的右通配符

**条目**： `contoso.com/a/*`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/？q=joe@t.com

- **允许不匹配和****阻止不匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>方案：左波浪符

**条目**： `~contoso.com`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配和****阻止不匹配**：

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>方案：右通配符后缀

**条目**： `contoso.com/*`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com/？q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **允许不匹配和****阻止不匹配**： contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>方案：左通配符子域和右通配符后缀

**条目**： `*.contoso.com/*`

- **允许匹配** 和 **阻止匹配**：

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **允许不匹配和****阻止不匹配**： contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>方案：向左和向右波浪符

**条目**： `~contoso.com~`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **允许不匹配和****阻止不匹配**：

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>方案：IP 地址

**条目**： `1.2.3.4`

- **允许匹配** 和 **阻止匹配**：1.2.3.4

- **允许不匹配和****阻止不匹配**：

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>具有右通配符的 IP 地址

**条目**： `1.2.3.4/*`

- **允许匹配** 和 **阻止匹配**：

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>无效条目的示例

以下条目无效：

- **缺少或无效的域值**：

  - contoso
  - \*.contoso。\*
  - \*.com
  - \*.pdf

- **文本上的通配符或不带空格字符：**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **具有端口的 IP 地址**：

  - contoso.com:443
  - abc.contoso.com:25

- **非描述性通配符**：

  - \*
  - \*.\*

- **中间通配符**：

  - conto \* so.com
  - conto~so.com

- **双通配符**

  - contoso.com/\*\*
  - contoso.com/\*/\*
