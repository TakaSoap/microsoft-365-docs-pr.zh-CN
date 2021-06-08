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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809175"
---
# <a name="manage-the-tenant-allowblock-list"></a>管理租户允许/阻止列表

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> 本文中所述的功能在预览版中，可能会更改，并且并非在所有组织中都可用。  如果你的组织没有本文中所述的欺骗功能，请参阅使用欺骗智能策略和 EOP 中的欺骗智能见解管理欺骗发件人中的旧版欺骗 [管理体验](walkthrough-spoof-intelligence-insight.md)。
>
> 目前，你 **无法** 配置租户允许/阻止列表中的允许 URL 或文件项。

在Microsoft 365没有邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，您可能会与 EOP 筛选裁定不一致。 例如，一条好邮件可能标记为 (误报) ，或者可能允许错误消息通过 (漏报) 。

安全与合规中心中的租户&/阻止列表提供了一种手动覆盖Microsoft 365裁定的方法。 租户允许/阻止列表在邮件流期间和用户单击时使用。 可以指定以下类型的替代：

- 要阻止的 URL。
- 要阻止的文件。
- 允许或阻止欺骗发件人。 如果替代欺骗智能见解中的允许或阻止裁定[](learn-about-spoof-intelligence.md)，欺骗发件人将成为仅出现在租户允许/阻止列表中的"欺骗"选项卡上的手动允许或阻止条目。 在欺骗智能检测到欺骗性发件人之前，还可以在此处手动创建允许或阻止欺骗发件人的允许或阻止条目。

本文介绍如何在安全& 合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到租户 **允许/阻止列表** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。

- 使用文件的 SHA256 哈希值指定文件。 若要在命令提示符中查找文件的 SHA256 哈希Windows，在命令提示符中运行以下命令：

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

- 在 Exchange Online 网站中 分配 权限，才能执行本文中的步骤：
  - **URL 和文件**：
    - 若要在租户允许/阻止列表中添加和删除值，你需要是组织管理或安全 **管理员角色****组** 的成员。
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

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>使用安全&中心在租户允许/阻止列表中创建阻止 URL 条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 在" **租户允许/阻止列表** "页上，验证 **"URL"** 选项卡是否被选中，然后单击"阻止 **"**

3. 在 **出现的"阻止 URL"** 飞出中，配置以下设置：

   - **添加要阻止的 URL：** 每行输入一个 URL，最多输入 20 个。 有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的租户 [允许/阻止列表的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法部分。

   - **永不过期**：执行下列步骤之一：

     - 验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 

       或

     - 将开关移到右侧，将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>使用安全&中心在租户允许/阻止列表中创建阻止文件条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 在"**租户允许/阻止列表"** 页上，选择"**文件"** 选项卡，然后单击"阻止 **"。**

3. 在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：

   - **添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。

   - **永不过期**：执行下列步骤之一：

     - 验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 

     或

     - 将开关移到右侧，将条目配置为永不过期： ![切换开关打开](../../media/scc-toggle-on.png).

   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>使用安全&中心在租户允许/阻止列表中创建允许或阻止欺骗发件人条目

**注意**：

- 仅 _明确_ 允许或阻止欺骗用户和域对中定义的发送基础结构的组合。
- 为域对配置允许或阻止条目时，来自该域对的邮件将不再显示在欺骗智能见解中。
- 欺骗性发件人的条目永不过期。

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 在"**租户允许/阻止列表"** 页上，选择"**欺骗"** 选项卡，然后单击"添加 **"。**

3. 在出现的 **"添加新域对** "飞出中，配置以下设置：

   - **使用通配符添加新域对**：每行输入一个域对，最多输入 20 个域对。 有关欺骗性发件人条目的语法的详细信息，请参阅本文稍后的租户允许 [/](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 阻止列表部分中的欺骗性发件人条目的域对语法。

   - **欺骗类型**：选择下列值之一：
     - **内部**：欺骗性发件人位于组织所属的域中， ([接受的) 。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **外部**：欺骗性发件人位于外部域中。

   - **操作**：选择 **"允许"** 或"**阻止"。**

4. 完成后，单击“**添加**”。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全&中心查看租户允许/阻止列表中的条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 选择您想要的选项卡。 可用的列取决于所选的选项卡：

   - **URL：**
     - **值**：URL。
     - **操作**：值 **Block**。
     - **上次更新日期**
     - **到期日期**
     - **注意**

   - **Files**
     - **值**：文件哈希。
     - **操作**：值 **Block**。
     - **上次更新日期**
     - **到期日期**
     - **注意**

   - **网络钓鱼**
     - **欺骗用户**
     - **发送基础结构**
     - **欺骗类型**：值 **Internal** 或 **External**。
     - **操作**：值 **Block** 或 **Allow**。

   可以单击列标题以按升序或降序排序。

   可以单击 **"分组** "对结果进行分组。 可用的值取决于所选的选项卡：

   - **URL**：可以按操作 对结果 **进行分组**。
   - **文件**：可以按操作 对结果 **进行分组**。
   - **BCL 绕过的** 发件人域 **：** 此选项卡上未提供组。
   - **欺骗：** 你可以按操作或欺骗 **类型****对结果进行分组**。

   单击 **"搜索**"，输入值的全部或一部分，然后按 Enter 查找特定值。 完成后，单击"清除搜索 **""** ![ 清除搜索图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) "。

   单击 **"筛选** "筛选结果。 显示在"筛选器 **"飞出** 控件中的可用值取决于所选的选项卡：

   - **URL**
     - **Action**
     - **永不过期**
     - **上次更新日期**
     - **到期日期**

   - **Files**
     - **Action**
     - **永不过期**
     - **上次更新日期**
     - **到期日期**

   - **用于 BCL 绕过的发件人域**
     - **永不过期**
     - **上次更新日期**
     - **到期日期**

   - **网络钓鱼**
     - **Action**
     - **欺骗类型**

   完成后，单击"应用 **"。** 若要清除现有筛选器，请单击 **"筛选器"，** 在出现的"筛选器"飞出中，单击"清除 **筛选器"。**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>使用安全&中心修改租户允许/阻止列表中的条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 选择包含要修改的条目类型的选项卡：
   - **URL**
   - **Files**
   - **用于 BCL 绕过的发件人域**
   - **网络钓鱼**

3. 选择要修改的条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。 可以在出现的飞出控件中修改的值取决于您在上一步中所选的选项卡：

   - **URL**
     - **永不过期** 和/或到期日期。
     - **可选注释**

   - **Files**
     - **永不过期** 和/或到期日期。
     - **可选注释**

   - **用于 BCL 绕过的发件人域**
     - **永不过期** 和/或到期日期。

   - **网络钓鱼**
     - **操作**：可以将值更改为"允许 **"或**"阻止 **"。**

4. 完成时，请单击“保存”。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>使用安全&中心从租户允许/阻止列表中删除条目

1. 在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。

2. 选择包含要删除的条目类型的选项卡：
   - **URL**
   - **Files**
   - **用于 BCL 绕过的发件人域**
   - **网络钓鱼**

3. 选择要删除的条目，然后单击"删除 **删除图标** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) "。

4. 在出现的警告对话框中，单击"删除 **"。**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>使用 PowerShell 将阻止文件或 URL 条目添加到租户允许/阻止列表

若要在租户允许/阻止列表中添加阻止文件或 URL 条目，请使用以下语法：

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

本示例为永不过期的指定文件添加阻止文件条目。

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

此示例为 contoso.com 及其所有子域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加一个阻止 URL 条目。 由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>使用 PowerShell 将允许或阻止欺骗发件人条目添加到租户允许/阻止列表

若要在租户允许/阻止列表中添加欺骗性发件人条目，请使用以下语法：

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 查看租户允许/阻止列表中的阻止文件或 URL 条目

若要查看租户允许/阻止列表中的阻止文件或 URL 条目，请使用以下语法：

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
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

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 查看租户允许/阻止列表中的允许或阻止欺骗发件人条目

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

此示例返回外部的所有阻止的欺骗发件人条目。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改租户允许/阻止列表中的阻止文件和 URL 条目

若要修改租户允许/阻止列表中的阻止文件和 URL 条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

此示例更改指定阻止 URL 条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改租户允许/阻止列表中的允许或阻止欺骗发件人条目

若要修改租户允许/阻止列表中的允许或阻止欺骗发件人条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

本示例将欺骗性发件人条目从"允许"更改为"阻止"。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 从租户允许/阻止列表中删除 URL 或文件条目

若要从租户允许/阻止列表中删除文件和 URL 条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 从租户允许/阻止列表中删除允许或阻止欺骗发件人条目

若要从租户允许/阻止列表中删除允许或阻止欺骗发件人条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。

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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>租户允许/阻止列表中欺骗发件人条目的域对语法

租户允许/阻止列表中欺骗发件人的域对使用以下语法： `<Spoofed user>, <Sending infrastructure>` 。

- **欺骗用户**：此值涉及在电子邮件客户端的"来源"框中显示的欺骗用户的电子邮件地址。  此地址也称为 `5322.From` 地址。 有效值包括：
  - 个人电子邮件地址 (例如，chris@contoso.com) 。
  - 电子邮件域 (例如，contoso.com) 。
  - 通配符 (例如 \* ，) 。

- **发送基础结构**：此值指示来自欺骗用户的邮件来源。 有效值包括：
  - 反向 DNS 查找中的域 (PTR 记录) 源电子邮件服务器的 IP 地址的 IP 地址 (例如，fabrikam.com) 。
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

仅允许 *来自该域* 的邮件和发送基础结构对进行欺骗。 不允许其他发件人 gmail.com 欺骗邮件。 来自来自其他域的其他域中发件人 tms.mx.com 反欺骗智能进行检查。
