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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全门户的租户允许/阻止列表中管理允许和阻止。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8411ca98b48b19c7ecf3085c450fbf40e5185474
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210385"
---
# <a name="manage-the-tenant-allowblock-list"></a>管理租户允许/阻止列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> 本文中介绍的一些功能在预览版中，可能会更改，并且并不是在所有组织中都可用。
>
> 如果你的组织没有本文中所述的欺骗功能，请参阅使用欺骗智能策略和 EOP 中的欺骗智能见解管理欺骗发件人中的旧版欺骗 [管理体验](walkthrough-spoof-intelligence-insight.md)。

在Microsoft 365没有邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，您可能会与 EOP 筛选裁定不一致。 例如，一条好邮件可能标记为 (误报) ，或者可能通过错误负数 (错误) 。

租户门户中的租户允许/阻止Microsoft 365 Defender提供了一种方法，可以手动替代Microsoft 365裁定。 租户允许/阻止列表在传入邮件的邮件流期间 (不适用于组织内部邮件) 用户单击时。 可以指定以下类型的替代：

- 要阻止的 URL。
- 要阻止的文件。
- 要阻止的发件人电子邮件或域。
- 允许或阻止欺骗发件人。 如果替代欺骗智能见解中的允许或阻止裁定[](learn-about-spoof-intelligence.md)，欺骗发件人将成为仅出现在租户允许/阻止列表中的"欺骗"选项卡上的手动允许或阻止条目。 在欺骗智能检测到欺骗性发件人之前，还可以在此处手动创建允许或阻止欺骗发件人的允许或阻止条目。
- 允许的 URL。
- 要允许的文件。
- 要允许的发件人电子邮件或域。

本文介绍如何在 Microsoft 365 Defender 门户的租户允许/阻止列表中或在 PowerShell (Exchange Online PowerShell 中为 Microsoft 365 组织配置条目，Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。 若要直接转到租户 **允许/阻止列表页面** ，请使用 <https://security.microsoft.com/tenantAllowBlockList> 。

- 使用文件的 SHA256 哈希值指定文件。 若要在命令提示符中查找文件的 SHA256 哈希Windows，在命令提示符中运行以下命令：

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。 不支持感知哈希 (pHash) 值。

- 本文稍后的租户允许/阻止列表一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。

- 租户允许/阻止列表允许最多 500 个发件人条目、500 个 URL 条目、500 个文件哈希条目和 1024 个欺骗 (欺骗发件人) 条目。

- 每个条目的最大字符数为：
  - 文件哈希 = 64
  - URL = 250

- 条目应在 30 分钟内处于活动状态。

- 默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。 可以指定日期或将其设置为永不过期。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 分配 权限，才能执行本文中的步骤：
  - **发件人、URL 和文件**：
    - 若要在租户允许/阻止列表中添加和删除值，你需要是组织管理、安全管理员或安全操作员角色组的成员，或者你分配有 Tenant **AllowBlockList Manager** 角色。
    - 若要对租户允许/阻止列表进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。
  - **欺骗**：以下组合之一：
    - **组织管理**
    - **安全管理员**<u>和</u>**仅查看配置** 或 **仅查看组织管理**。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

## <a name="configure-the-tenant-allowblock-list"></a>配置租户允许/阻止列表

### <a name="use-the-microsoft-365-defender-portal"></a>使用 Microsoft 365 Defender 门户

In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

若要添加所有块，请参阅 [在租户允许/阻止列表中添加块](manage-tenant-blocks.md)。

若要添加所有允许，请参阅租户 [允许/阻止列表中的添加允许](manage-tenant-allows.md)。

若要修改和删除所有块并允许，请参阅修改和删除租户允许/阻止列表中的 [条目](modify-remove-entries-tenant-allow-block.md)。

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell

若要管理所有允许和阻止，请参阅在租户允许 [/](manage-tenant-blocks.md)阻止列表中添加阻止、在租户允许 [/](manage-tenant-allows.md)阻止列表中添加允许和修改和删除租户允许 [/阻止列表中的条目](modify-remove-entries-tenant-allow-block.md)。

## <a name="view-entries-in-the-tenant-allowblock-list"></a>查看租户允许/阻止列表中的条目

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 选择您想要的选项卡。 可用的列取决于所选的选项卡：

   - **发件人**：
     - **值**：发件人域或电子邮件地址。
     - **操作**：值 **Allow** 或 **Block**。
     - **上次更新**
     - **删除 on**
     - **备注**
   - **URL：**
     - **值**：URL。
     - **操作**：值 **Allow** 或 **Block**。
     - **上次更新**
     - **删除 on**
     - **备注**
   - **Files**
     - **值**：文件哈希。
     - **操作**：值 **Allow** 或 **Block**。
     - **上次更新**
     - **删除 on**
     - **备注**
   - **网络钓鱼**
     - **欺骗用户**
     - **发送基础结构**
     - **欺骗类型**：值 **Internal** 或 **External**。
     - **操作**：值 **Block** 或 **Allow**。

   可以单击列标题以按升序或降序排序。

   可以单击 **"分组** "对结果进行分组。 可用的值取决于所选的选项卡：

   - **发件人**：可以按操作 对结果 **进行分组**。
   - **URL：** 可以按操作 对结果 **进行分组**。
   - **文件**：可以按操作 对结果 **进行分组**。
   - **欺骗：** 你可以按操作或欺骗 **类型****对结果进行分组**。

   单击 **"搜索**"，输入值的全部或一部分，然后按 Enter 查找特定值。 完成后，单击"清除 ![ 搜索图标"。](../../media/m365-cc-sc-close-icon.png) **清除搜索**。

   单击 **"筛选** "筛选结果。 显示在"筛选器 **"飞出** 控件中的可用值取决于所选的选项卡：

   - **发件人**
     - **操作**
     - **永不过期**
     - **上次更新日期**
     - **删除 on**
   - **URL**
     - **操作**
     - **永不过期**
     - **上次更新日期**
     - **删除 on**
   - **Files**
     - **操作**
     - **永不过期**
     - **上次更新**
     - **删除 on**
   - **网络钓鱼**
     - **操作**
     - **欺骗类型**

   完成后，单击“**应用**”。 若要清除现有筛选器，请单击 **"筛选器"，** 在出现的"**筛选器**"飞出中，单击"清除 **筛选器"。**

4. 完成后，单击“**添加**”。

## <a name="view-sender-file-or-url-entries-in-the-tenant-allowblock-list"></a>查看租户允许/阻止列表中的发件人、文件或 URL 条目

若要查看租户允许/阻止列表中的阻止发件人、文件或 URL 条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListItems -ListType <Sender | FileHash | URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

此示例返回指定文件哈希值的信息。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

此示例返回所有阻止的 URL。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

## <a name="view-spoofed-sender-entries"></a>查看欺骗性发件人条目

若要查看租户允许/阻止列表中的欺骗性发件人条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

此示例返回租户允许/阻止列表中所有欺骗性发件人条目。

```powershell
Get-TenantAllowBlockListSpoofItems
```

此示例返回所有允许内部欺骗发件人条目。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

此示例返回外部的所有被阻止的欺骗发件人条目。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>租户允许/阻止列表的 URL 语法

- 允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。

- 例如，不允许使用文件名 (，例如test.pdf) 。

- 不支持 Unicode，但 Punycode 支持。

- 如果下列所有语句都为 true，则允许使用主机名：
  - 主机名包含一个时间段。
  - 在周期的左侧至少有一个字符。
  - 此期间右侧至少有两个字符。

  例如， `t.co` 允许; `.com` 或 `contoso.` 不允许。

- 不允许隐含子路径。

  例如， `contoso.com` 不包括 `contoso.com/a` 。

- 在 () 允许使用通配符或*通配符：

  - 左通配符后面必须后跟一个时间段，以指定子域。

    例如， `*.contoso.com` 允许 ; `*contoso.com` 不允许。

  - 右通配符必须按照 / (/) 左斜线来指定路径。

    例如， `contoso.com/*` 允许; `contoso.com*` 或 `contoso.com/ab*` 不允许。

  - `*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。

  - IP 地址中不允许使用通配符。

- 在下列 (提供了) ~ 字符：

  - 左波浪符表示域和所有子域。

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

- **允许不匹配和****阻止不匹配：contoso.com**

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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>租户允许/阻止列表中欺骗发件人条目的域对语法

租户允许/阻止列表中欺骗发件人的域对使用以下语法： `<Spoofed user>, <Sending infrastructure>` 。

- **欺骗用户**：此值涉及在电子邮件客户端的"来源"框中显示的欺骗用户的电子邮件地址。  此地址也称为 `5322.From` 地址。 有效值包括：
  - 单个电子邮件地址 (例如，chris@contoso.com) 。
  - 电子邮件域 (例如，contoso.com) 。
  - 通配符 (例如 \* ，) 。

- **发送基础结构**：此值指示来自欺骗用户的邮件来源。 有效值包括：
  - 反向 DNS 查找 (PTR 记录) 源电子邮件服务器的 IP 地址的 IP 地址 (例如，fabrikam.com) 。
  - 如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。

下面是用于标识欺骗性发件人的有效域对的一些示例：

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

欺骗性发件人条目的最大数量为 1000。

添加域对仅允许或阻止欺骗用户 *和发送* 基础结构的组合。 它不允许来自任何来源的欺骗用户的电子邮件，也不允许来自任何欺骗用户的发送基础结构源的电子邮件。 

例如，为以下域对添加允许条目：

- **域**： gmail.com
- **基础结构**：tms.mx.com

仅允许 *来自该域* 的邮件和发送基础结构对进行欺骗。 不允许其他发件人 gmail.com 欺骗邮件。 来自来自其他域的其他域中的发件人 tms.mx.com 欺骗智能进行检查。
