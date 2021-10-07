---
title: 修改和删除租户允许/阻止列表中的条目
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何修改和删除安全门户中租户允许/阻止列表中的条目。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f2662ac41e5df5cf2eb36413d8a58568ff336841
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212001"
---
# <a name="modify-and-remove-entries-in-the-tenant-allowblock-list"></a>修改和删除租户允许/阻止列表中的条目

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

可以使用租户Microsoft 365 Defender PowerShell 修改和删除租户允许/阻止列表中的条目。

## <a name="use-the-microsoft-365-defender-portal"></a>使用 Microsoft 365 Defender 门户

### <a name="modify-entries-in-the-tenant-allowblock-list"></a>修改租户允许/阻止列表中的条目

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 选择包含要修改的条目类型的选项卡：
   - **发件人) 
   - **URL**
   - **Files**
   - **网络钓鱼**

3. 选择要修改的条目，然后单击"编辑 ![ "图标。](../../media/m365-cc-sc-edit-icon.png) **编辑**。 可以在出现的飞出控件中修改的值取决于您在上一步中所选的选项卡：
   - **发件人**
     - **永不过期** 和/或到期日期。
     - **可选注释**
   - **URL**
     - **永不过期** 和/或到期日期。
     - **可选注释**
   - **Files**
     - **永不过期** 和/或到期日期。
     - **可选注释**
   - **网络钓鱼**
     - **操作**：可以将值更改为"允许 **"或**"阻止 **"。**
4. 完成时，请单击“保存”。

> [!NOTE]
> 创建日期后最多只能延长 30 天。 阻止可延长最多 90 天，但与允许不同，也可以设置为永不过期。

### <a name="remove-entries-from-the-tenant-allowblock-list"></a>从租户允许/阻止列表中删除条目

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 选择包含要删除的条目类型的选项卡：
   - **发件人**
   - **URL**
   - **Files**
   - **网络钓鱼**

3. 选择要删除的条目，然后单击"删除 ![ 图标"。](../../media/m365-cc-sc-delete-icon.png) **删除**。

4. 在出现的警告对话框中，单击"删除 **"。**

## <a name="use-powershell"></a>使用 PowerShell

### <a name="modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>修改租户允许/阻止列表中的阻止文件和 URL 条目

若要修改租户允许/阻止列表中的阻止发件人、文件和 URL 条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

此示例更改指定阻止 URL 条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>从租户允许/阻止列表中删除 URL 或文件条目

若要从租户允许/阻止列表中删除发件人、文件和 URL 条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。

### <a name="modify-allow-or-block-spoofed-sender-entries"></a>修改允许或阻止欺骗发件人条目

若要修改租户允许/阻止列表中的允许或阻止欺骗发件人条目，请使用以下语法：

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

本示例将欺骗性发件人条目从"允许"更改为"阻止"。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。

### <a name="remove-allow-or-block-spoofed-sender-entries"></a>删除允许或阻止欺骗发件人条目

若要从租户允许/阻止列表中删除允许或阻止欺骗发件人条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。
