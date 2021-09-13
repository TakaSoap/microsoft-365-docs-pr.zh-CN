---
title: 在租户允许/阻止列表中管理你的阻止
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全门户的租户允许/阻止列表中配置阻止。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2dc45779f7e5656e2edfcb1ea89ef19f95cc3d2e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59195930"
---
# <a name="add-blocks-in-the-tenant-allowblock-list"></a>在租户允许/阻止列表中添加块

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="use-the-microsoft-365-defender-portal"></a>使用 Microsoft 365 Defender 门户 

### <a name="create-block-sender-entries-in-the-tenant-allowblock-list"></a>在租户允许/阻止列表中创建阻止发件人条目

1. In the Microsoft 365 Defender portal， go to **Policies & rules Threat** \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 在" **租户允许/阻止列表** "页上，验证是否选择了"发件人 **"选项卡，** 然后单击"阻止 ![ 图标"。](../../media/m365-cc-sc-create-icon.png) **阻止**。

3. 在 **出现的"阻止发件人** "飞出中，配置以下设置：
   - **发件人电子邮件地址或域**：每行 (一个发件人电子邮件地址或域) ，最多 20 个。
   - **永不过期**：执行下列步骤之一：
     - 验证是否关闭该设置 (![ 关闭。) 并使用"删除"框指定条目 ](../../media/scc-toggle-off.png) 的到期日期。 

       或

     - 将开关移到右侧，将条目配置为永不过期： ![打开。](../../media/scc-toggle-on.png).
   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

### <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>在租户允许/阻止列表中创建阻止 URL 条目

1. In the Microsoft 365 Defender portal， go to **Policies & rules Threat** \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 在" **租户允许/阻止列表** "页上，验证 **"URL"** 选项卡已选中，然后单击"阻止 ![ 图标"。](../../media/m365-cc-sc-create-icon.png) **阻止**。

3. 在 **出现的"阻止 URL"** 飞出中，配置以下设置：
   - **添加包含通配符的 URL：** 每行输入一个 URL，最多输入 20 个。 有关 URL 条目的语法的详细信息，请参阅管理租户允许/阻止列表 中的 URL [语法部分](tenant-allow-block-list.md)。
   - **永不过期**：执行下列步骤之一：
     - 验证是否关闭该设置 (![ 关闭。) 并使用"删除"框指定条目 ](../../media/scc-toggle-off.png) 的到期日期。 

       或

     - 将开关移到右侧，将条目配置为永不过期： ![打开。](../../media/scc-toggle-on.png).
   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

### <a name="create-block-file-entries-in-the-tenant-allowblock-list"></a>在租户允许/阻止列表中创建阻止文件条目

1. In the Microsoft 365 Defender portal， go to **Policies & rules Threat** \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 在" **租户允许/阻止列表"** 页上，选择" **文件** "选项卡，然后单击"阻止 ![ 图标"。](../../media/m365-cc-sc-create-icon.png) **阻止**。

3. 在出现的 **"阻止文件** "飞出中，配置以下设置：
   - **添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。
   - **永不过期**：执行下列步骤之一：
     - 验证是否关闭该设置 (![ 关闭。) 并使用"删除"框指定条目 ](../../media/scc-toggle-off.png) 的到期日期。 

     或

     - 将开关移到右侧，将条目配置为永不过期： ![打开。](../../media/scc-toggle-on.png).
   - **可选说明**：输入条目的描述性文本。

4. 完成后，单击“**添加**”。

### <a name="create-spoofed-sender-block-entries"></a>创建欺骗性发件人阻止条目

**注意**：

- 仅 _明确_ 允许或阻止欺骗用户和域对中定义的发送基础结构的组合。
- 为域对配置允许或阻止条目时，来自该域对的邮件将不再显示在欺骗智能见解中。
- 欺骗性发件人的条目永不过期。
- 欺骗同时支持允许和阻止。 URL 仅支持允许。

1. In the Microsoft 365 Defender portal， go to **Policies & rules Threat** \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 在" **租户允许/阻止列表"** 页上，选择" **欺骗"** 选项卡，然后单击"阻止 ![ 图标"。](../../media/m365-cc-sc-create-icon.png) **添加** 。

3. 在出现的 **"添加新域对** "飞出中，配置以下设置：
   - **使用通配符添加新域对**：每行输入一个域对，最多输入 20 个域对。 有关欺骗性发件人条目的语法的详细信息，请参阅 [管理租户允许/阻止列表](tenant-allow-block-list.md)。
   - **欺骗类型**：选择下列值之一：
     - **内部**：欺骗性发件人位于组织所属的域中， ([接受的) 。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **外部**：欺骗性发件人位于外部域中。
   - **操作**：选择 **"允许"** 或"**阻止"。**

4. 完成后，单击“**添加**”。

## <a name="use-powershell"></a>使用 PowerShell

### <a name="add-block-sender-file-or-url-entries-to-the-tenant-allowblock-list"></a>将阻止发件人、文件或 URL 条目添加到租户允许/阻止列表

若要在租户允许/阻止列表中添加阻止发件人、文件或 URL 条目，请使用以下语法：

```powershell
New-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

本示例为特定日期过期的指定发件人添加阻止发件人条目。

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

本示例为永不过期的指定文件添加阻止文件条目。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

此示例为 contoso.com 及其所有子域（例如， (、www.contoso.com 和 contoso.com）添加 xyz.abc.contoso.com) 。 由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="add-spoofed-sender-block-entries"></a>添加欺骗性发件人阻止条目 

若要在租户允许/阻止列表中添加欺骗性发件人条目，请使用以下语法：

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。
