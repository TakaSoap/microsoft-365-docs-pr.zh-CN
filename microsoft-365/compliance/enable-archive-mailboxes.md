---
title: 在 Microsoft 365 合规性中心中启用存档邮箱
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
description: 了解如何启用或禁用存档邮箱以支持组织的邮件保留、电子数据展示和保留要求。
ms.openlocfilehash: be7939f11c6aea0161f76c3796ca2ff8bd515ba0
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241391"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>在合规性中心中启用存档邮箱

Microsoft 365 中的存档（又称为 *就地存档*）为用户提供额外的邮箱存储空间。 有关详细信息，请参阅 [了解存档邮箱](archive-mailboxes.md)。

使用本文中的信息在 Microsoft 365 合规中心内或使用 PowerShell 启用或禁用存档邮箱。 另请了解如何对用户的存档邮箱运行自动诊断检查，以识别任何问题和建议的解决方法。

## <a name="get-the-necessary-permissions"></a>获取必要的权限

必须在 Exchange Online 中分配“邮件收件人”角色, 才能启用或禁用存档邮箱。 默认情况下, 此角色将分配给 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>的 **权限** 页上的“收件人管理”和“组织管理”角色组。 

如果在 Microsoft 365 合规中心中看不到 **存档** 页，则请管理员为你分配必要的权限。

## <a name="enable-an-archive-mailbox"></a>启用存档邮箱

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>并登录。

2. 在 Microsoft 365 合规中心的左侧窗格中，单击“**信息治理**”，然后单击“**存档**”选项卡。

   将显示“存档”页。“存档邮箱”列表示每个用户的存档邮箱已启用还是禁用。

   > [!NOTE]
   > **存档** 页面最多显示500个用户。

3. 在邮箱的列表中，选择要启用存档邮箱的用户。

   ![单击所选用户的详细信息窗格中的“启用”以启用存档邮箱。](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

4. 在所选用户的详细信息窗格中, 单击 **启用**。

   将显示警告，指示如果启用存档邮箱，用户邮箱中早于分配给邮箱的存档策略的项目将移动到新的存档邮箱。默认存档策略是分配给 ExchangeOnline 邮箱的保留策略的一部分，在项目传递到邮箱或用户创建两年后，它会将项目移动到存档邮箱。有关详细信息，请参阅本文的 **详细信息** 部分。

5. 单击“是”启用存档邮箱。

   可能需要一些时间才会创建存档邮箱。创建后，“**存档邮箱: 已启用**”将显示在所选用户的详细信息窗格中。可能需要单击“**刷新**”“![刷新”图标 ](../media/O365-MDM-Policy-RefreshIcon.gif) 才能更新详细信息窗格中的信息。

> [!TIP]
> 您也可以通过选择多个禁用存档邮箱的用户（使用 Shift 或 Ctrl 键）批量启用存档邮箱。选择多个邮箱后，在详细信息窗格中，单击“启用”。

## <a name="disable-an-archive-mailbox"></a>禁用存档邮箱

还可以使用 Microsoft 365 合规中心中的“**存档**”页面禁用用户的存档邮箱。禁用存档邮箱后，可以在禁用后的 30 天内重新将其连接到用户的主邮箱。在这种情况下，存档邮箱的原始内容都会进行还原。30 天后，原始存档邮箱的内容就会永久删除且无法恢复。因此，如果在禁用存档邮箱 30 天后重新启用此邮箱，则会新建一个存档邮箱。

分配给用户邮箱的默认存档策略会在邮件传递到邮箱两年后将其移动到存档邮箱。如果你禁用用户的存档邮箱，将不会对邮箱项目执行任何操作，它们将保留在用户的主邮箱中。

若要禁用存档邮箱：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>并登录。

2. 在 Microsoft 365 合规中心的左侧窗格中，单击“**信息治理**”，然后单击“**存档**”选项卡。

   将显示“存档”页。“存档邮箱”列表示每个用户的存档邮箱已启用还是禁用。

   > [!NOTE]
   > **存档** 页面最多显示500个用户。

3. 在邮箱的列表中，选择要禁用存档邮箱的用户。

4. 在详细信息窗格中，单击“禁用”。

   将显示一条警告消息，指出你有 30 天的时间重新启用存档邮箱，30 天后，存档中的所有信息将被永久删除。 

5. 单击“是”以禁用存档邮箱。

   可能需要一些时间才会禁用存档邮箱。禁用后，“**存档邮箱: 已禁用**”将显示在所选用户的详细信息窗格中。可能需要单击“**刷新**”“![刷新”图标 ](../media/O365-MDM-Policy-RefreshIcon.gif) 才能更新详细信息窗格中的信息。

> [!TIP]
> 您也可以通过选择多个启用存档邮箱的用户（使用 Shift 或 Ctrl 键）批量禁用存档邮箱。选择多个邮箱后，在详细信息窗格中，单击“禁用”。

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>使用 Exchange Online PowerShell 启用或禁用存档邮箱。

可以使用 Exchange Online PowerShell 启用存档邮箱。使用 PowerShell 的主要原因是，可以为你组织中的所有用户快速启用存档邮箱。

第一步是连接到 Exchange Online PowerShell。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

连接到 Exchange Online 后, 可运行以下部分中的命令来启用或禁用存档邮箱。

### <a name="enable-archive-mailboxes"></a>启用存档邮箱

运行以下命令, 为单个用户启用存档邮箱。

```powershell
Enable-Mailbox -Identity <username> -Archive
```

运行以下命令, 为贵公司所有用户启用存档邮箱 (当前未启用存档邮箱)。

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>禁用存档邮箱

运行以下命令, 为单个用户禁用存档邮箱。

```powershell
Disable-Mailbox -Identity <username> -Archive
```

运行以下命令, 为贵公司所有用户禁用存档邮箱 (当前启用存档邮箱)。

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="run-diagnostics-on-archive-mailboxes"></a>在存档邮箱上运行诊断

你可以对用户的存档邮箱运行自动诊断检查，以识别任何问题和建议的解决方法。

若要运行诊断检查，请单击下面的按钮。 

> [!div class="nextstepaction"]
> [运行测试: 存档邮箱](https://aka.ms/PillarArchiveMailbox)

![在存档邮箱上运行诊断。](../media/ArchiveMailboxDiagnostics.png)

将在 Microsoft 365 管理中心中打开浮出控件页面。 输入要检查的邮箱的电子邮件地址，然后单击“**运行测试**”。

> [!NOTE]
> 必须是 Microsoft 365 全局管理员才能使用存档邮箱诊断检查。 此外，此功能不适用于 Microsoft 365 政府云、由世纪互联运营的 Microsoft 365 或 Microsoft 365 德国。

## <a name="next-steps"></a>后续步骤

请考虑为其他存储空间启用 [自动扩展存档](autoexpanding-archiving.md)。 有关说明，请参阅 [启用自动扩展存档](enable-autoexpanding-archiving.md)。
