---
title: 在租户允许/阻止列表中管理你的允许和阻止的 URL
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
description: 管理员可以了解如何在安全与合规中心的"租户允许/阻止&"列表中& URL 条目。
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845938"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>管理租户允许/阻止列表中的 URL

> [!NOTE]
> 本主题中介绍的功能在预览版中、可能会发生变更，并不适用于所有组织。

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，你可能希望与 EOP 筛选 Verdict 的禁用。 例如，一条正常邮件可能标记为错误的邮件 (误报) ，或者对于错误的负面建议，可能允许 (错误) 的邮件。

通过安全与合规中心内的租户 &允许/阻止列表，可以手动替代 Microsoft 365 筛选结果。 在邮件流中和单击用户时会使用租户允许/阻止列表。 可以指定要在租户允许/阻止列表中允许或阻止的 URL。

本主题介绍如何在安全 & 合规中心内的租户允许/阻止列表中，或在具有 Exchange Online 邮箱的 Microsoft 365 组织的 PowerShell (Exchange Online PowerShell 中配置条目;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到"租户 **允许/阻止列表"** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。

- 本主题后面将会在"租户允许 [/阻止列表"部分的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍可用的 URL 值。

- 租户允许/阻止列表最多可允许 500 个 URL 条目。

- 条目应在 15 分钟内处于活动状态。

- 阻止条目优先于允许条目。

- 默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。 你可以指定日期或将其设置为永不过期。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要在租户允许/阻止列表中添加和删除值，您需要是以下角色组的成员之一：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 必须是以下角色之一的成员，才能对租户允许/阻止列表进行只读访问：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>使用安全与&中心在租户允许/阻止列表中创建 URL 条目

有关 URL 条目的语法的详细信息，请参阅本主题 [后面的"租户允许/阻止列表](#url-syntax-for-the-tenant-allowblock-list) "一节的 URL 语法。

1. 在安全与合规&中心，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 在" **租户允许/阻止列表** "页上，验证 **是否已选择"URL"** 选项卡，然后单击"添加 **"**

3. 在 **显示的"添加新** URL"浮出控件中，配置以下设置：

   - **添加带通配符的**URL：每行输入一个 URL，最多 20 个 URL。

   - **阻止/允许**：选择是 **要** 允许 **还是** 阻止指定的 URL。

   - **永不过期**：执行下列步骤之一：

     - 验证此设置是否禁用了 (![ ](../../media/scc-toggle-off.png) 状态) 并使用 **"过期"** 框指定条目的到期日期。

     或

     - 将切换开关移动到右侧可将条目配置为永不过期： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **可选注释**：输入条目的描述性文本。

4. 完成后，请单击"添加 **"。**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全与&中心查看租户允许/阻止列表中的条目

1. 在安全与合规&，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 选择 **"URL"** 选项卡。

单击以下列标题以按升序或降序进行排序：

- **值**
- **操作**：**阻止或****允许**。
- **上次更新日期**
- **到期日期**
- **注意**

单击 **"组**"将这些条目按 **"操作" (Block**或 **") "****或"无"来分组**。 **Block**

单击 **"搜索**"，输入全部或部分值，然后按 Enter 查找特定值。 完成后，请单击"清除搜索 **清除搜索** ![ "图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

单击"**筛选器"。** 在随 **后** 出现的"筛选器"浮出控件中，配置以下任意设置：

- **操作**：选择"**允许"和****/或"** 从中"两者。

- **永不过期**：选中 (![ 关闭 (](../../media/scc-toggle-off.png)) 或打开 ![ ("切换 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)) 。

- **Last updated**： Select a start date (**From**) ， an end date (**To**) or both.

- **到期日期：** 选择 **从 (结束** 日期 () ，结束日期（ (开始) **或**) 或两者。

完成后，单击"应用 **"。**

若要清除现有筛选器，请单击 **"筛选器"，** 然后在**出现的筛选器**浮出控件中单击"**清除筛选器"。**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>使用安全&合规中心修改租户允许/阻止列表中的条目

您不能修改 URL 值本身。 您需要删除该项，然后重新创建它。

1. 在安全与合规&中心，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 选择 **"URL"** 选项卡。

3. 选择要修改的条目，然后单击"编辑 **"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 在显示的浮出控件中，配置以下设置：

   - **阻止/允许**：选择 **"允许**"或 **"阻止"。**

   - **永不过期**：执行下列步骤之一：

     - 验证是否已在默认切换 (![ ](../../media/scc-toggle-off.png) 状态) 并使用 **"过期** "框指定条目的到期日期。

     或

     - 将切换开关移动到右侧可将条目配置为永不过期： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **可选注释**：输入条目的描述性文本。

5. 完成时，请单击“保存”****。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>使用安全与&中心删除租户允许/阻止列表中的条目

1. 在安全与合规&中心，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**

2. 选择 **"URL"** 选项卡。

3. 选择要删除的项，然后单击"删除 **"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 在出现的警告对话框中，单击"删除 **"。**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 在租户允许/阻止列表中添加条目

若要在租户允许/阻止列表中添加条目，请使用以下语法：

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

此示例为所有子域（如contoso.com、 (www.contoso.com 和xyz.abc.contoso.com) ）contoso.com。 因为我们未使用 ExpirationDate 或 NoExpiration 参数，该条目会在 30 天后过期。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 查看租户允许/阻止列表中的条目

若要查看租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

此示例返回所有已禁止的 URL。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改租户允许/阻止列表中的条目

您不能修改 URL 值本身。 您需要删除该项，然后重新创建它。

若要修改租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

本示例更改指定条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

有关语法和参数的详细信息，请参阅[Set-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 从租户允许/阻止列表中删除条目

若要从租户允许/阻止列表中删除条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

本示例从租户允许/阻止列表中删除指定的 URL 条目。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

有关语法和参数的详细信息，请参阅[Remove-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>租户允许/阻止列表的 URL 语法

- 允许 IP4v 和 IPv6 地址，但 TCP/UDP 端口不允许。

- 例如，不允许 (扩展名test.pdf) 。

- 不支持 Unicode，但 Punycode 是 Punycode。

- 下列所有语句都为真时，允许使用主机名：

  - 主机名中包含句点。
  - 句点左侧至少有一个字符。
  - 句点右侧至少有两个字符。

  例如，允许 `t.co` 或 `.com` `contoso.` 不允许。

- 子路径不为隐式路径。

  例如， `contoso.com` 不包括 `contoso.com/a` 。

- 在下列 (通) 通配符通配符：

  - 左侧通配符的后面必须为句点以指定子域。

    例如， `*.contoso.com` 允许; `*contoso.com` 不允许使用。

  - 正确的通配符必须遵循正斜 (/) 来指定路径。

    例如，允许 `contoso.com/*` 或 `contoso.com*` `contoso.com/ab*` 不允许。

  - 所有子路径都不由正确的通配符来表示。

    例如， `contoso.com/*` 不包括 `contoso.com/a` 。

  - `*.com*` 无效对象 (可解析的域无效，正确的通配符不遵循正斜) 。

  - IP 地址中不允许使用通配符。

- 在下列情况 () 和尾部字符类型：

  - 左色板表示域和所有子域。

    例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。

- 包含协议的 URL (例如 `http://` ，或 `https://` `ftp://`) 将失败，因为 URL 条目将应用于所有协议。

- 不支持或不要求使用用户名或密码。

- 引用 ("或"引用) 字符。

- URL 应包括所有可能的重定向。

### <a name="url-entry-scenarios"></a>URL 入口方案

下面的部分分说明有效的 URL 条目及其结果。

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
  
- **块匹配**：

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **阻止不匹配：abc-contoso.com**

#### <a name="scenario-left-wildcard-subdomain"></a>方案：子域 (留通配) 

**条目**： `*.contoso.com`

- **允许比赛** 和 **块匹配**：

  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配且****阻止不匹配**：

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>方案：路径顶部的右通配符

**条目**： `contoso.com/a/*`

- **允许比赛** 和 **块匹配**：

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/？q=joe@t.com

- **允许不匹配且****阻止不匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
#### <a name="scenario-left-tilde"></a>场景：左色

**条目**： `~contoso.com`

- **允许比赛** 和 **块匹配**：

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配且****阻止不匹配**：

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>方案：右侧的通配符后缀

**条目**： `contoso.com/*`

- **允许比赛** 和 **块匹配**：

  - contoso.com/？q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **允许不匹配且****阻止不匹配**：contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>方案：左侧通配符子域和右通配符后缀

**条目**： `*.contoso.com/*`

- **允许比赛** 和 **块匹配**：

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **允许不匹配且****阻止未匹配**：contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>场景：左和右量

**条目**： `~contoso.com~`

- **允许比赛** 和 **块匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **允许不匹配且****阻止不匹配**：

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>方案：IP 地址

**条目**： `1.2.3.4`

- **允许比赛** 和 **块匹配**：1.2.3.4

- **允许不匹配且****阻止不匹配**：

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>具有正确通配符的 IP 地址

**条目**： `1.2.3.4/*`

- **允许比赛** 和 **块匹配**：

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>无效条目示例

以下条目无效：

- **缺少域值或无效的域值**：

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **文本通配符或不包含空格字符**：

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

  - \*contoso.com
  - conto~so.com

- **双通配符**

  - contoso.com/\*\*
  - contoso.com/\*/\*
