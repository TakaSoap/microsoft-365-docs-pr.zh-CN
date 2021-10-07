---
title: 使用 PowerShell 将 IMAP 迁移到 Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: 了解如何使用 PowerShell 执行 Internet 邮件访问协议 (IMAP) 迁移到 Microsoft 365。
ms.openlocfilehash: 08cffcbe3a08031df05da68358da062200eb99c5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163236"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>使用 PowerShell 将 IMAP 迁移到 Microsoft 365

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

作为部署 Microsoft 365 过程的一部分，您可以选择将 Internet 邮件访问协议 (IMAP) 电子邮件服务中的用户邮箱内容迁移到 Microsoft 365。 本文将向您介绍如何通过 Exchange Online PowerShell 执行电子邮件 IMAP 迁移的任务。

> [!NOTE]
> 您还可以使用 Exchange 管理中心来执行 IMAP 迁移。 请参阅 [迁移 IMAP 邮箱](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

估计完成该任务的时间：2-5 分钟，用于创建迁移批处理。 迁移批处理启动后，迁移的持续时间会有所不同，具体取决于批处理中邮箱的数量、每个邮箱的大小和可用网络容量。 有关影响将邮箱迁移到邮箱服务器所花费时间的其他Microsoft 365，请参阅迁移[性能](/Exchange/mailbox-migration/office-365-migration-best-practices)。

你必须先获得权限，然后才能执行此过程。要查看你需要哪些权限，请参阅[收件人权限](/exchange/recipients-permissions-exchange-2013-help)主题的一个表中的"迁移"条目。

若要使用 Exchange Online PowerShell cmdlet，你需要登录并将 cmdlet 导入你的本地 Windows PowerShell 会话。有关说明，请参阅[使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。

以下限制适用于 IMAP 迁移：

- 只有在用户收件箱或其他邮件文件夹中的项目才会被迁移。你不能迁移联系人、日历项目或任务。

- 最多可以从用户邮箱迁移 500,000 个项目。

- 能够迁移的邮件最大大小为 35 MB。

## <a name="migration-steps"></a>迁移步骤

### <a name="step-1-prepare-for-an-imap-migration"></a>步骤 1：准备 IMAP 迁移
<a name="BK_Step1"> </a>

- **如果你的 IMAP 组织有一个域，请将其添加为你的组织接受Microsoft 365域。** 如果要对邮箱使用已拥有Microsoft 365域，首先必须将其添加为接受域，以Microsoft 365。 添加后，可以在应用程序内创建Microsoft 365。 有关详细信息，请参阅验证[域](../admin/setup/add-domain.md)。

- **将每个用户添加到Microsoft 365，以便他们拥有一个邮箱。** 有关说明，请参阅[向企业Microsoft 365用户](../admin/add-users/add-users.md)。

- **获取 IMAP 服务器的 FQDN**。在创建 IMAP 迁移终结点时，你需要提供从中迁移邮箱数据的 IMAP 服务器的完全限定域名 (FQDN)（也称为完整的计算机名称）。可使用 IMAP 客户端或 PING 命令来验证你能否使用此 FQDN 通过 Internet 与 IMAP 服务器进行通信。

- **配置防火墙以允许 IMAP 连接**。你可能必须打开托管 IMAP 服务器的组织的防火墙中的端口，以便于迁移期间来自 Microsoft 数据中心的网络通信被允许进入托管 IMAP 服务器的组织。有关 Microsoft 数据中心使用的 IP 地址列表，请参阅 [Exchange Online URL 和 IP 地址范围](./urls-and-ip-address-ranges.md)。

- **分配管理员帐户权限以访问 IMAP 组织中的邮箱**。如果你在 CSV 文件中使用管理员凭据，则你使用的帐户必须具有必要的权限才能访问内部部署邮箱。访问用户邮箱所需的权限将由特定的 IMAP 服务器决定。

- **要使用 Exchange Online PowerShell cmdlet**，你需要登录并将 cmdlet 导入到你的本机 Windows PowerShell 会话。有关说明，请参阅 [使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

    有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。

- **验证你是否可以连接到 IMAP 服务器**。在 Exchange Online PowerShell 中运行以下命令以测试到 IMAP 服务器的连接设置。

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    对于 **Port** 参数的值，通常为未加密或传输层安全性 (TLS) 连接使用 143，为 SSL 连接使用 993。

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>步骤 2：为 IMAP 迁移批处理创建 CSV 文件
<a name="BK_Step2"> </a>

确定 IMAP 迁移批处理中你要迁移邮箱的用户组。CSV 文件中的每一行都包含连接到 IMAP 邮件系统中邮箱所需的信息。

以下是每个用户的必需特性：

- **EmailAddress** 指定用户邮箱Microsoft 365 ID。

- **UserName** 指定帐户用来访问 IMAP 服务器上邮箱的登录名。

- **Password** 指定 **UserName** 栏内帐户的密码。

以下是 CSV 文件格式的一个示例。在此示例中，将迁移三个邮箱：

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

对于 **UserName** 属性，除了用户名以外，你还可以使用具有已分配的必要权限的帐户的凭据来访问 IMAP 服务器上的邮箱，以下是用于一些 IMAP 服务器的某些特定格式：

 **Microsoft Exchange：**

如果你正在从 Microsoft Exchange 的 IMAP 实施迁移电子邮件，请在 CSV 文件中为 **UserName** 属性使用格式 **Domain/Admin_UserName/User_UserName** 。 假设你正在从 Exchange 迁移 Terry Adams、Ann Beebe 和 Paul Cannon 的电子邮件。 你有一个邮件管理员帐户，其中用户名是 **mailadmin，** 密码是 **P \@ ssw0rd**。 您的 CSV 文件应如下所示：

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot：**

对于支持简单身份验证和安全层 (SASL) 的 IMAP 服务器（如 Dovecot IMAP 服务器），使用格式 **User_UserName*Admin_UserName** ，其中星号 ( * ) 为可配置的分隔符。 假设你正在使用管理员凭据 **mailadmin** 和 **P \@ ssw0rd** 从 Dovecot IMAP 服务器迁移这些相同用户的电子邮件。 您的 CSV 文件应如下所示：

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint：**

如果要从 Mirapoint Message Server 迁移电子邮件，请使用 #user **\@ domain#Admin_UserName#** 格式作为管理员凭据。 若要使用管理员凭据 **mailadmin** 和 **P \@ ssw0rd** 从 Mirapoint 迁移电子邮件，您的 CSV 文件将如下所示：

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP：**

一些源电子邮件系统（如 Courier IMAP）不支持使用邮箱管理员凭据将邮箱迁移到 Microsoft 365。 相反，您可以将源电子邮件系统设置为使用虚拟共享文件夹。 通过使用虚拟共享文件夹，您可以使用邮箱管理员凭据来访问源电子邮件系统上的用户邮箱。 有关如何配置 Courier IMAP 的虚拟共享文件夹的详细信息，请参阅[共享文件夹](https://go.microsoft.com/fwlink/p/?LinkId=398870)。

若要在源电子邮件系统上设置虚拟共享文件夹后迁移邮箱，你必须将可选的 **UserRoot** 属性包含在迁移文件中。此属性可指定每个用户的邮箱在源电子邮件系统上的虚拟共享文件夹结构中所处的位置。例如，指向 Terry 的邮箱的路径是 /users/terry.adams。

以下是包含 **UserRoot** 属性的 CSV 文件的示例：

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>步骤 3：创建 IMAP 迁移终结点
<a name="BK_Step3"> </a>

若要成功迁移电子邮件，Microsoft 365连接到源电子邮件系统并进行通信。 为此，Microsoft 365迁移终结点。 迁移终结点还定义同时迁移的邮箱数和每 24 小时执行一次的增量同步过程中同时同步的邮箱数。 要创建用于 IMAP 迁移的迁移终结点，首先[连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。

要在 Exchange Online PowerShell 中创建名为“IMAPEndpoint”的 IMAP 迁移终结点，运行以下命令：

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

你还可以添加参数以指定并发迁移、并发增量迁移和要使用的端口。以下 Exchange Online PowerShell 命令可创建一个名为"IMAPEndpoint"的 IMAP 迁移终结点，其支持 50 个并发迁移和最多 25 个并发增量同步。还要将终结点配置为对 TLS 加密使用 143 端口。

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

有关 **New-MigrationEndpoint** cmdlet 的详细信息，请参阅 [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)。

#### <a name="verify-it-worked"></a>验证它是否起作用

在 Exchange Online PowerShell 中运行以下命令来显示有关“IMAPEndpoint”的信息：

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>步骤 4：创建并启动 IMAP 迁移批处理
<a name="BK_Step4"> </a>

你可以使用 [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet 为 IMAP 迁移创建迁移批处理。你可以通过包括 _AutoStart_ 参数来创建迁移批处理并自动启动。或者，你可以创建迁移批处理，然后通过使用 [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet 启动它。

以下 Exchange Online PowerShell 命令会自动使用名为“IMAPEndpoint”的 IMAP 终结点来启动名为“IMAPBatch1”的迁移批处理。

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>验证它是否起作用

运行 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet 以显示有关"IMAPBatch1"的信息：

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

你还可以通过运行以下命令，验证该批处理是否已启动：

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>步骤 5：将电子邮件路由到Microsoft 365
<a name="BK_Step5"> </a>

电子邮件系统使用称为 MX 记录的 DNS 记录来查明电子邮件的传递位置。 在电子邮件迁移过程中，MX 记录指向您的源电子邮件系统。 至此，电子邮件Microsoft 365迁移已完成，是时候将 MX 记录指向 Microsoft 365。 这可帮助确保电子邮件已传递到你的Microsoft 365邮箱。 通过移动 MX 记录，您还可以在准备就绪的时候关闭旧的电子邮件系统。

对于许多 DNS 提供商，我们提供了有关更改 MX 记录的特定说明。 如果未包含您的 DNS 提供商，或者您希望了解大致方向，我们也提供了[常规 MX 记录说明](https://go.microsoft.com/fwlink/?LinkId=397449)。

你客户和合作伙伴的电子邮件系统可能需要 72 小时才能识别更改后的 MX 记录。请等待至少 72 个小时，然后才能继续执行下一项任务：步骤 6：删除 IMAP 迁移批处理。

### <a name="step-6-delete-imap-migration-batch"></a>步骤 6：删除 IMAP 迁移批处理
<a name="BK_Step6"> </a>

更改 MX 记录并验证所有电子邮件是否Microsoft 365邮箱后，通知用户其邮件将Microsoft 365。 此后，您可以删除 IMAP 迁移批处理。 在删除迁移批处理之前验证以下内容。

- 所有用户都正在使用Microsoft 365邮箱。 删除批处理后，发送到本地邮箱Exchange Server邮件不会复制到相应的Microsoft 365邮箱。

- Microsoft 365邮箱开始直接发送到邮箱后至少同步一次。 为此，请确保迁移批处理的"上次同步时间"框中的值比邮件开始直接路由到邮箱Microsoft 365更新。

要从 Exchange Online PowerShell 中删除“IMAPBatch1”迁移批处理，请运行以下命令：

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

有关 **Remove-MigrationBatch** cmdlet 的详细信息，请参阅 [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)。

#### <a name="verify-it-worked"></a>验证它是否起作用

在 Exchange Online PowerShell 中运行以下命令来显示有关“IMAPBatch1”的信息：

```powershell
Get-MigrationBatch IMAPBatch1"
```

此命令会返回状态为 **Removing** 的迁移批处理或返回错误消息，指出未找到该迁移批处理，验证该批处理已删除。

有关 **Get-MigrationBatch** cmdlet 的详细信息，请参阅 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。

## <a name="see-also"></a>另请参阅

[IMAP 迁移故障排除程序](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)