---
title: 在租户允许/阻止列表中管理允许和阻止
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全门户的租户允许/阻止列表中配置允许和阻止。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587583"
---
# <a name="manage-the-tenant-allowblock-list"></a>管理租户允许/阻止列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 目前，你 **无法** 配置租户允许/阻止列表中的允许项。

在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) （没有 Exchange Online 邮箱）的 Microsoft 365 组织中，您可能对 EOP 筛选裁定有意见不一致。 例如，一条好邮件可能标记为 (误报) ，或者可能允许错误消息通过 (漏报) 。

安全与合规中心中的租户允许/阻止&提供了一种手动替代 Microsoft 365 筛选裁定的方法。 租户允许/阻止列表在邮件流期间和用户单击时使用。 您可以指定要始终阻止的 URL 或文件。

本文介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止列表中的条目;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到租户 **允许/阻止列表** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。

- 使用文件的 SHA256 哈希值指定文件。 若要在 Windows 中查找文件的 SHA256 哈希值，在命令提示符中运行以下命令：

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。 不支持感知哈希 (pHash) 值。

- 本文稍后的租户允许/阻止列表一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。

- 租户允许/阻止列表允许最多 500 个 URL 条目和 500 个文件哈希条目。

- 每个条目的最大字符数为：
  - 文件哈希 = 64
  - URL = 250

- 条目应在 30 分钟内处于活动状态。

- 默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。 可以指定日期或将其设置为永不过期。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要在租户允许/阻止列表中添加和删除值，你需要是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对租户允许/阻止列表进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > 
  > - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>使用安全&中心在租户允许/阻止列表中创建 URL 条目

有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的租户 [允许/阻止列表的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法部分。

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 在" **租户允许/阻止列表** "页上，验证 **"URL"** 选项卡是否被选中，然后单击"阻止 **"**

3. 在 **出现的"阻止 URL"** 飞出中，配置以下设置：

   - **添加要阻止的 URL：** 每行输入一个 URL，最多输入 20 个。

   - **永不过期**：执行下列步骤之一：

     - 验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 

       或

     - 将开关移到右侧，将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>使用安全&中心在租户允许/阻止列表中创建文件条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 在"**租户允许/阻止列表"页上**，选择"**文件"** 选项卡，然后单击"阻止 **"。**

3. 在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：

   - **添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。

   - **永不过期**：执行下列步骤之一：

     - 验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 

     或

     - 将开关移到右侧，将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全&中心查看租户允许/阻止列表中的条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 选择 **"URL"** 选项卡或" **文件"** 选项卡。

单击以下列标题以按升序或降序排序：

- **值**：URL 或文件哈希。
- **上次更新日期**
- **到期日期**
- **注意**

单击 **"搜索**"，输入值的全部或一部分，然后按 Enter 查找特定值。 完成后，单击"清除搜索 **""** ![ 清除搜索图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) "。

单击"**筛选器"。** 在出现的 **"** 筛选器"飞出中，配置以下任一设置：

- **永不过期**：选择关闭： ![ 关闭 ](../../media/scc-toggle-off.png) 或打开： ![ 打开切换 ](../../media/scc-toggle-on.png) 。

- **Last updated**： Select a start date (**From**) ， an end date (**To**) both.

- **到期日期：** 选择开始日期 (**From**) ，结束日期 (**到**) 两者。

完成后，单击"应用 **"。**

若要清除现有筛选器，请单击 **"筛选器"，** 在出现的"筛选器"飞出中，单击"清除 **筛选器"。**

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>使用安全&中心修改租户允许/阻止列表中的阻止条目

不能修改条目中的现有阻止 URL 或文件值。 若要修改这些值，需要删除并重新创建条目。

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 选择 **"URL"** 选项卡或" **文件"** 选项卡。

3. 选择要修改的阻止条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 在出现的"飞出"中，配置以下设置：

   - **永不过期**：执行下列步骤之一：

     - 验证是否关闭该设置 (关闭) 并使用"过期 ![ ](../../media/scc-toggle-off.png) **时间"** 框指定条目的到期日期。

       或

     - 将开关移到右侧，将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选说明**：输入条目的描述性文本。

5. 完成后，单击“**保存**”。

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>使用安全&中心从租户允许/阻止列表中删除阻止条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 选择 **"URL"** 选项卡或" **文件"** 选项卡。

3. 选择要删除的阻止条目，然后单击"删除 **删除"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 在出现的警告对话框中，单击"删除 **"。**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>使用 PowerShell 将阻止条目添加到租户允许/阻止列表

若要在租户允许/阻止列表中添加阻止条目，请使用以下语法：

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

此示例为 contoso.com 及其所有子域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加一个阻止 URL 条目。 由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

本示例为永不过期的指定文件添加阻止文件条目。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 查看租户允许/阻止列表中的条目

若要查看租户允许/阻止列表中的条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

此示例返回所有阻止的 URL。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

此示例返回指定文件哈希值的信息。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改租户允许/阻止列表中的阻止条目

不能修改阻止条目中的现有 URL 或文件值。 若要修改这些值，需要删除并重新创建条目。

若要修改租户允许/阻止列表中的阻止条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

本示例更改指定阻止条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 从租户允许/阻止列表中删除阻止条目

若要从租户允许/阻止列表中删除阻止条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>租户允许/阻止列表的 URL 语法

- 允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。

- 例如，不允许使用文件名 (，例如test.pdf) 。

- 不支持 Unicode，但 Punycode 支持。

- 如果下列所有语句都为 true，则允许使用主机名：
  - 主机名包含一个时间段。
  - 在周期的左侧至少有一个字符。
  - 此期间右侧至少有两个字符。

  例如， `t.co` 是允许的 `.com` ; `contoso.` 或者是不允许的。

- 不隐含子路径。

  例如， `contoso.com` 不包括 `contoso.com/a` 。

- 在 () 允许使用通配符或*通配符：

  - 左通配符后面必须后跟一个时间段，以指定子域。

    例如， `*.contoso.com` 允许 ; `*contoso.com` 不允许。

  - 右通配符必须按照正斜杠 (/) 指定路径。

    例如， `contoso.com/*` 是允许的 `contoso.com*` ; `contoso.com/ab*` 或者是不允许的。

  - 右通配符不隐含所有子路径。

    例如， `contoso.com/*` 不包括 `contoso.com/a` 。

  - `*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。

  - IP 地址中不允许使用通配符。

- 在下列 (提供了) ~ 字符：

  - 左波浪符表示域及其所有子域。

    例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。

- 包含协议（如 、 (）的 URL) 将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。

- 不支持或不需要用户名或密码。

- 引号 ("或") 无效字符。

- 如果可能，URL 应包含所有重定向。

### <a name="url-entry-scenarios"></a>URL 条目方案

以下各节介绍了有效的 URL 条目及其结果。

#### <a name="scenario-no-wildcards"></a>方案：无通配符

**条目**： `contoso.com`

- **允许匹配**： contoso.com

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
  - contoso.com/a/?q=joe@t.com

- **允许不匹配和****阻止不匹配**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>应用场景：左波浪符

**条目**： `~contoso.com`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **允许不匹配和****阻止不匹配**：

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>应用场景：右通配符后缀

**条目**： `contoso.com/*`

- **允许匹配** 和 **阻止匹配**：

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **允许不匹配和****阻止不匹配**：contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>应用场景：左通配符子域和右通配符后缀

**条目**： `*.contoso.com/*`

- **允许匹配** 和 **阻止匹配**：

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **允许不匹配和****阻止不匹配**：contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>应用场景：左右波浪符

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

- **域值缺失或无效**：

  - contoso
  - \*.contoso。\*
  - \*.com
  - \*.pdf

- **文本上的通配符或不带空格字符的通配符**：

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
