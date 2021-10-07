---
title: 使用 PowerShell 分步迁移到 Microsoft 365
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: 了解如何使用 PowerShell 随着时间的推移，使用分步迁移将内容从源电子邮件系统Microsoft 365。
ms.openlocfilehash: 66e91b4480e4433f610e627d1cf4e64f439b929f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154826"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>使用 PowerShell 分步迁移到 Microsoft 365

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

您可以使用分步迁移将用户邮箱的内容从源电子邮件系统Microsoft 365迁移迁移。

本文将指导你完成使用 PowerShell 进行分步电子邮件迁移Exchange Online任务。 有关分 [步电子邮件迁移](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)您需要了解的内容主题概述了迁移过程。 当您了解本文的内容之后，则可以借此机会开始将一个电子邮件系统中的邮箱迁移到另一个电子邮件系统。

> [!NOTE]
> 您还可以使用 Exchange 管理中心来执行暂存迁移。 请参阅[执行电子邮件到电子邮件的分步Microsoft 365。](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

估计完成该任务的时间：2-5 分钟，用于创建迁移批处理。 迁移批处理启动后，迁移的持续时间会有所不同，具体取决于批处理中邮箱的数量、每个邮箱的大小和可用网络容量。 有关影响将邮箱迁移到邮箱服务器所花费时间的其他Microsoft 365，请参阅迁移[性能](/Exchange/mailbox-migration/office-365-migration-best-practices)。

您必须先获得权限，然后才能执行此过程。要查看您需要哪些权限，请参阅[收件人权限](/exchange/recipients-permissions-exchange-2013-help)主题中的"迁移"条目。

若要使用 Exchange Online PowerShell cmdlet，您需要登录并将 cmdlet 导入您的本地 Windows PowerShell 会话。有关说明，请参阅[使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。

## <a name="migration-steps"></a>迁移步骤

### <a name="step-1-prepare-for-a-staged-migration"></a>步骤 1：准备暂存迁移

在使用分步迁移将邮箱Microsoft 365迁移之前，必须对邮箱环境进行一些Exchange更改。

 **在您的内部部署 Exchange Server 上配置 Outlook 无处不在** 电子邮件迁移服务使用 Outlook 无处不在（也称为 RPC over HTTP）连接到您的内部部署 Exchange Server。有关如何为 Exchange Server 2007 和 Exchange 2003 设置 Outlook 无处不在 设置的信息，请参阅以下内容：

- [Exchange 2007:如何启用 Outlook 无处不在](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

- [如何使用 Exchange 2003 配置 Outlook 无处不在](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

> [!IMPORTANT]
> 您必须在 Outlook 无处不在 配置中使用受信任的证书颁发机构 (CA) 颁发的证书。Outlook 无处不在 不能通过自签名的证书进行配置。有关详细信息，请参阅[如何为 Outlook 无处不在配置 SSL](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))。

 **可选：确认您是否可以使用 Outlook 无处不在 连接到 Exchange 组织** 使用下列方法之一来测试您的连接设置。

- 使用公司网络外部的 Outlook 连接到您的内部部署 Exchange 邮箱。

- 使用 [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) 测试连接设置。 使用 Outlook 无处不在 (RPC over HTTP) 或 Outlook 自动发现测试。

- 在 Exchange Online PowerShell 中运行以下命令：

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **设置权限** 用于连接到内部部署 Exchange 组织 (（也称为迁移管理员) ）的本地用户帐户必须具有必要的权限才能访问要迁移到 Microsoft 365 的本地邮箱。 当您在此过程的稍后步骤 [3：](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) 创建迁移终结点 (创建迁移终结点来连接到您的电子邮件系统时，会) 。

要迁移邮箱，管理员必须拥有以下权限集之一：

- 内部部署组织中 Active Directory 中的 **Domain Admins** 组成员。

    或

- 分配了对每个内部部署邮箱的 **FullAccess** 权限以及可修改内部部署用户帐户上的 **TargetAddress** 属性的 **WriteProperty** 权限。

    或

- 分配了对存储用户邮箱的内部部署邮箱数据库上的 **Receive As** 权限以及可修改内部部署用户帐户上的 **TargetAddress** 属性的 **WriteProperty** 权限。

有关如何设置这些权限的说明，请参阅分配将邮箱迁移到 Microsoft 365[的权限。](/Exchange/mailbox-migration/assign-permissions-for-migration)

 **禁用统一消息 (UM)** 如果您要迁移的内部部署邮箱上开启了 UM，请先将其关闭，然后再执行迁移。迁移完成以后，打开邮箱的 UM。有关具体的操作方法步骤，请参阅 [禁用统一消息](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))。

 **使用目录同步在网站中创建新Microsoft 365。** 使用目录同步创建组织内部部署Microsoft 365用户。

创建用户以后，您需要对他们授予许可。您可以在创建用户之后的 30 天内添加许可证。有关添加许可证的步骤，请参阅[步骤 8：完成迁移后任务](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)。

 可以使用 Microsoft Azure Active Directory (Azure AD) 同步工具或 Microsoft Azure AD 同步服务在 Microsoft 365 中同步和创建本地Microsoft 365。 将邮箱迁移到 Microsoft 365后，您可以在内部部署组织中管理用户帐户，并且这些用户帐户会与 Microsoft 365 组织同步。 有关更多信息，请参阅[目录集成](/previous-versions/azure/azure-services/jj573653(v=azure.100))。

### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>步骤 2：为暂存迁移批处理创建 CSV 文件

确定要迁移到 Microsoft 365 本地邮箱的用户后，使用逗号分隔值 (CSV) 文件创建迁移批处理。 CSV 文件（由用户Microsoft 365运行迁移）的每一行都包含有关本地邮箱的信息。

> [!NOTE]
> 对于可以使用分步迁移迁移到邮箱的邮箱数没有Microsoft 365限制。 迁移批处理的 CSV 文件最多可包含 2,000 行。 若要迁移 2000 个以上邮箱，请创建额外的 CSV 文件并使用每个文件来创建新的迁移批处理。

 **支持的属性**

暂存迁移的 CSV 文件支持下列三个属性。CSV 文件中的每一行对应于一个邮箱并且必须包含属性的相应值。

|**属性**|**说明**|**是否必需？**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |为内部部署邮箱指定一个主要的 SMTP 电子邮件地址，例如，pilarp@contoso.com。  <br/> 对内部部署邮箱使用主 SMTP 地址，而不是来自内部部署Microsoft 365。 例如，如果本地域名为 contoso.com 但 Microsoft 365 电子邮件域名为 service.contoso.com，那么对于 CSV 文件中的电子邮件地址，可以使用 contoso.com 域名。  <br/> |必需  <br/> |
|密码  <br/> |要设置的新邮箱Microsoft 365密码。 适用于组织的任何密码Microsoft 365也适用于 CSV 文件中包含的密码。  <br/> |可选  <br/> |
|ForceChangePassword  <br/> |指定用户首次登录到其新邮箱时是否必须Microsoft 365密码。 对此参数的值使用 **True** 或 **False** 。 <br/> > [!NOTE]> 如果已通过在本地组织中部署 Active Directory 联合身份验证服务 (AD FS) 或更高版本来实现单一登录 (SSO) 解决方案，必须将 **ForceChangePassword** 属性值设为 **False**。          |可选  <br/> |

 **CSV 文件格式**

以下是 CSV 文件格式的示例。 本示例中，将三个内部部署邮箱迁移到Microsoft 365。

CSV 文件的第一行（即标题行）列出了在后续行中指定的属性（或字段）的名称。每个属性名称都用逗号分隔开。

```powershell
EmailAddress,Password,ForceChangePassword
pilarp@contoso.com,Pa$$w0rd,False
tobyn@contoso.com,Pa$$w0rd,False
briant@contoso.com,Pa$$w0rd,False
```

标题行下面的每行都表示一个用户，并提供将用于迁移该用户邮箱的信息。每行中属性值的顺序必须与标题行中属性名的顺序相同。

使用任何文本编辑器或 Excel 等应用程序创建 CSV 文件。将该文件另存为 .csv 或 .txt 文件。

> [!NOTE]
> 如果 CSV 文件包含非 ASCII 字符或特殊字符，请使用 UTF-8 或其他 Unicode 编码保存 CSV 文件。根据应用程序的不同，如果计算机的系统区域设置与 CSV 文件中使用的语言相匹配，则使用 UTF-8 或其他 Unicode 编码保存 CSV 文件可能会更容易。

### <a name="step-3-create-a-migration-endpoint"></a>步骤 3：创建迁移终结点
<a name="BK_Endpoint"> </a>

若要成功迁移电子邮件，Microsoft 365需要与源电子邮件系统连接并进行通信。 为此，Microsoft 365迁移终结点。 要使用 PowerShell 创建适用于暂存迁移的 Outlook 无处不在迁移终结点，首先[连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。

要在 Exchange Online PowerShell 中创建名为“StagedEndpoint”的 Outlook 无处不在迁移终结点，请运行以下命令：

```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

有关 **New-MigrationEndpoint** cmdlet 的详细信息，请参阅 [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)。

> [!NOTE]
> 可以使用 **New-MigrationEndpoint** cmdlet 指定服务要通过 **-TargetDatabase** 选项使用的数据库。在其他情况下，系统会从管理邮箱所在的 Active Directory 联合身份验证服务 (AD FS) 2.0 站点中随机分配数据库。

#### <a name="verify-it-worked"></a>验证它是否起作用

在 Exchange Online PowerShell 中，运行以下命令来显示有关“StagedEndpoint”迁移终结点的信息：

```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>步骤 4：创建并启动暂存迁移批处理
<a name="BK_Endpoint"> </a>

您可以在 Exchange Online PowerShell 中使用 **New-MigrationBatch** cmdlet 为直接转换迁移创建迁移批处理。您可以通过包括 _AutoStart_ 参数来创建迁移批处理并自动启动。或者，您可以通过使用 **Start-MigrationBatch** cmdlet 创建迁移批处理，然后手动启动。此示例创建名为"StagedBatch1"的迁移批处理并使用之前步骤中创建的迁移终结点。

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

此示例还会创建名为"StagedBatch1"的迁移批处理并使用之前步骤中创建的迁移终结点。由于未包括  _AutoStart_ 参数，因此必须在迁移主控板中手动启动迁移批处理或者通过使用 **Start-MigrationBatch** cmdlet 手动启动迁移批处理。如前所述，一次只能存在一个直接转换迁移批处理。

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>验证它是否起作用

在 Exchange Online PowerShell 中运行以下命令来显示有关“StagedBatch1”的信息：

```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

您还可以通过运行以下命令，验证该批处理是否已启动：

```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

有关 **Get-MigrationBatch** cmdlet 的详细信息，请参阅 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。

### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>步骤 5：将内部部署邮箱转换为启用邮件的用户
<a name="BK_Endpoint"> </a>

成功迁移一批邮箱以后，您需要某种方法使用户可以访问他们的邮件。 其邮箱已迁移的用户现在具有一个本地邮箱和一个Microsoft 365。 拥有邮箱的用户Microsoft 365将停止接收其本地邮箱中的新邮件。

由于您尚未完成迁移，因此您尚未准备好指示所有用户Microsoft 365发送电子邮件。 那么，可以为这些拥有两个邮箱的用户做些什么呢？ 您可以做的是更改您已迁移到邮件启用的用户的内部部署邮箱。 当您从邮箱更改为启用邮件的用户时，您可以指示用户Microsoft 365电子邮件，而不是访问其本地邮箱。

将本地邮箱转换为启用邮件的用户的另一个重要原因是，将代理地址复制到启用邮件的用户，以保留 Microsoft 365 邮箱中的代理地址。 这使您可以使用 Active Directory 管理来自内部部署组织的基于云的用户。 此外，如果决定在所有邮箱迁移到 Microsoft 365 后停止使用内部部署 Exchange Server 组织，则已复制到启用邮件的用户的代理地址将保留在内部部署 Active Directory 中。

### <a name="step-6-delete-a-staged-migration-batch"></a>步骤 6：删除暂存迁移批处理
<a name="BK_Endpoint"> </a>

 在迁移批处理中的所有邮箱都已成功迁移并且将批处理中的内部部署邮箱转换为启用邮件的用户之后，可以准备删除暂存迁移批处理。 请确保验证邮件是否正在转发到迁移批处理Microsoft 365邮箱。 当您删除暂存迁移批处理时，迁移服务将清除任何与迁移批处理相关的记录，同时删除迁移批处理。

要在 Exchange Online PowerShell 中删除“StagedBatch1”迁移批处理，请运行以下命令。

```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

有关 **Remove-MigrationBatch** cmdlet 的详细信息，请参阅 [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)。

#### <a name="verify-it-worked"></a>验证它是否起作用

在 Exchange Online PowerShell 中运行以下命令来显示有关“IMAPBatch1”的信息：

```powershell
Get-MigrationBatch StagedBatch1
```

此命令会返回状态为 **Removing** 的迁移批处理或返回错误消息，指出未找到该迁移批处理，验证该批处理已删除。

有关 **Get-MigrationBatch** cmdlet 的详细信息，请参阅 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。

### <a name="step7-assign-licenses-to-microsoft-365-users"></a>步骤 7：向用户Microsoft 365许可证
<a name="BK_Endpoint"> </a>

通过Microsoft 365许可证激活迁移帐户的用户帐户。 如果您不分配许可证，则在宽限期（30 天）结束后将禁用该邮箱。 若要在许可证分配Microsoft 365 管理中心，请参阅[分配或取消分配许可证](../admin/manage/assign-licenses-to-users.md)。

### <a name="step-8-complete-post-migration-tasks"></a>步骤 8：完成迁移后任务
<a name="BK_Postmigration"> </a>

- **创建自动发现 DNS 记录，以便用户可以轻松地访问他们的邮箱。** 在所有内部部署邮箱迁移到 Microsoft 365 后，您可以为 Microsoft 365 组织配置自动发现 DNS 记录，以使用户能够使用 Outlook 和移动客户端轻松连接到其新的 Microsoft 365 邮箱。 这一新的自动发现 DNS 记录必须使用相同的命名空间，该命名空间用于 Microsoft 365 组织。 例如，如果您的基于云的命名空间是 cloud.contoso.com，那么您需要创建的自动发现 DNS 记录是 autodiscover.cloud.contoso.com。

    Microsoft 365使用 CNAME 记录为客户端和移动客户端Outlook自动发现服务。 自动发现 CNAME 记录必须包含以下信息：

  - **别名：** autodiscover

  - **目标：** autodiscover.outlook.com

    有关详细信息，请参阅添加 [DNS 记录以连接你的域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

- **停止使用内部部署 Exchange 服务器。** 确认所有电子邮件都直接路由到 Microsoft 365 邮箱，并且不再需要维护内部部署电子邮件组织或不用计划实施 SSO 解决方案后，可以从服务器中卸载 Exchange 并删除内部部署 Exchange 组织。

    有关详细信息，请参阅以下资源：

  - [修改或删除 Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [如何删除 Exchange 2007 组织](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [如何卸载 Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
