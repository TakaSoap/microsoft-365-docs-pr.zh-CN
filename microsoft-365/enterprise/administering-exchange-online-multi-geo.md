---
title: 在多地理位置环境中管理 Exchange Online 邮箱
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
ms.localizationpriority: medium
description: 了解如何使用 PowerShell Exchange Online环境中管理多Microsoft 365设置。
ms.openlocfilehash: 2e4be2fd506f89579866c61bbf4a8a41aadc0d03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189197"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>在多地理位置环境中管理 Exchange Online 邮箱

Exchange Online需要 PowerShell 才能查看和配置环境中多地理位置Microsoft 365属性。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

你需要 [Microsoft Azure Active Directory PowerShell 模块](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 或 v1.x 中的更高版本才能查看用户对象的 **PreferredDataLocation** 属性。 无法通过 AAD PowerShell 直接修改通过 AAD Connect 同步到 AAD 中的用户对象的 **PreferredDataLocation** 值。 可以通过 AAD PowerShell 修改仅限云的用户对象。 若要连接到 Azure AD PowerShell，请参阅[连接到 PowerShell](connect-to-microsoft-365-powershell.md)。

在Exchange Online多地理位置环境中，无需执行任何手动步骤将地理位置添加到租户。 收到消息中心帖子显示多地理位置已可供Exchange Online后，所有可用地理位置都已准备好并配置为可供使用。

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>使用 Exchange Online PowerShell 直接连接到某个地理位置

通常，Exchange Online PowerShell 将连接到中心地理位置。 但你也可以直接连接到附属地理位置。 由于性能有所改进，因此，当你仅管理附属地理位置中的用户时，我们建议直接连接到该位置。

[安装和维护 EXO V2 模块](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)中介绍了安装和使用 EXO V2 模块的要求。

若要将 Exchange Online PowerShell 连接到特定地理位置 *，ConnectionUri* 参数不同于常规连接说明。 命令和值的其余部分是相同的。

具体而言，需要将值添加到 `?email=<emailaddress>` _ConnectionUri_ 值的末尾。 `<emailaddress>` 是目标 **地理位置** 中任何邮箱的电子邮件地址。 您拥有该邮箱的权限或与凭据的关系不是一个因素;该电子邮件地址只是Exchange Online PowerShell 连接位置。

Microsoft 365或Microsoft 365 GCC客户通常不需要使用 _ConnectionUri_ 参数连接到 Exchange Online PowerShell。 但是，若要连接到特定地理位置，你需要使用 _ConnectionUri_ 参数，以便可以在 `?email=<emailaddress>` 值中使用它。

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>连接 PowerShell 中Exchange Online地理位置

以下连接说明适用于已配置或未配置为使用 MFA 身份验证的多重 (帐户) 。

1. 在 Windows PowerShell 窗口中，通过运行以下命令加载 EXO V2 模块：

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. 在下面的示例中，admin@contoso.onmicrosoft.com 是管理员帐户，而目标地理位置是邮箱 olga@contoso.onmicrosoft.com 所在的位置。

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. 在出现的提示中 admin@contoso.onmicrosoft.com 密码。 如果该帐户配置为使用 MFA，则还需要输入安全代码。

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>查看在 Exchange Online 组织中配置的可用地理位置

若要在 Microsoft 365 多地理位置中查看配置的地理位置的列表，请在 Exchange Online PowerShell 中运行以下命令：

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>查看 Exchange Online 组织的中心地理位置

若要查看租户的中心地理位置，请在 Exchange Online PowerShell 中运行以下命令：

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>查找邮箱的地理位置

Exchange Online PowerShell 中的 **Get-Mailbox** cmdlet 显示邮箱的以下多地理位置相关属性：

- **Database**：对地理位置代码对应的数据库名称的前 3 个字母，告知你邮箱当前位于何处。 对于在线存档邮箱，应使用 **ArchiveDatabase** 属性。

- **MailboxRegion**：指定管理员设置的地理位置代码（从 Azure AD 中的 **PreferredDataLocation** 同步）。

- **MailboxRegionLastUpdateTime**：指明 MailboxRegion 的最后（自动或手动）更新时间。

若要查看邮箱的这些属性，请使用以下语法：

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

例如，若要查看邮箱 chris@contoso.onmicrosoft.com 的地理位置信息，请运行以下命令：

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

此命令的输出如下所示：

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> 如果数据库名称中的地理位置代码与 **MailboxRegion** 值不匹配，则邮箱将自动放入重定位队列，并移动到 **MailboxRegion** 值 (Exchange Online 指定的地理位置，以查找这些属性值) 之间的不匹配。

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>将现有的仅限云邮箱移动到特定地理位置

仅限云的用户是未通过 AAD Connect 同步到租户的用户。 此用户是在 Azure AD 中直接创建的。 使用用于 Windows PowerShell 的 Azure AD 模块中的 **Get-MsolUser** 和 **Set-MsolUser** cmdlet 来查看或指定将在其中存储仅限云的用户邮箱的地理位置。

若要查看用户的 **PreferredDataLocation** 值，请在 Azure AD PowerShell 中使用此语法：

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

例如，若要查看用户 michelle@contoso.onmicrosoft.com 的 **PreferredDataLocation** 值，请运行以下命令：

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

若要修改仅限云的用户对象的 **PreferredDataLocation** 值，请在 Azure AD PowerShell 中使用以下语法：

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

例如，若要为用户 michelle@contoso.onmicrosoft.com 将 **PreferredDataLocation** 值设置为欧盟 (EUR) 地理位置，请运行以下命令：

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - 如前所述，您无法对来自本地 Active Directory 的同步用户对象使用此过程。 你需要在 Active Directory 中更改 **PreferredDataLocation** 值，并使用 AAD Connect 进行同步。 有关详细信息，请参阅 [Azure Active Directory Connect 同步：为 Microsoft 365 资源配置首选数据位置](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)。
>
> - 将邮箱重定位到新的地理位置所花费的时间取决于若干因素：
>
>   - 邮箱的大小和类型。
>   - 正在移动的邮箱数量。
>   - 移动资源的可用性。

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>将非活动邮箱移动到特定地理位置

不能移动出于合规性目的保留的非活动 (例如，诉讼保留中的邮箱) **PreferredDataLocation** 值。 若要将非活动邮箱移动到其他地理位置，请执行以下步骤：

1. 恢复非活动邮箱。 有关说明，请参阅 [恢复非活动邮箱](../compliance/recover-an-inactive-mailbox.md)。

2. 通过替换邮箱的名称、别名、帐户或电子邮件地址，在 Exchange Online PowerShell 中运行以下命令，阻止 \<MailboxIdentity\> [托管文件夹助理处理恢复的邮箱](/powershell/exchange/connect-to-exchange-online-powershell)：

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. 将Exchange Online **计划 2** 许可证分配给恢复的邮箱。 需要执行此步骤才能将邮箱重新置于诉讼保留状态。 有关说明，请参阅 [向用户分配许可证](../admin/manage/assign-licenses-to-users.md)。

4. 如上一节中所述，在邮箱上配置 **PreferredDataLocation** 值。

5. 确认邮箱已移动到新地理位置后，将恢复的邮箱重新置于诉讼保留状态。 有关说明，请参阅[将邮箱置于诉讼保留。](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold)

6. 在确认诉讼保留已就位后，允许托管文件夹助理再次处理邮箱，方法为将邮箱替换为名称、别名、帐户或电子邮件地址，在 Exchange Online PowerShell 中运行以下 \<MailboxIdentity\> [命令](/powershell/exchange/connect-to-exchange-online-powershell)：

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. 通过删除与邮箱关联的用户帐户，使邮箱再次变为非活动状态。 有关说明，请参阅 [从组织中删除用户](../admin/add-users/delete-a-user.md)。 此步骤还针对其他Exchange Online发布计划 2 许可证。

**注意**：将非活动邮箱移动到其他地理位置时，可能会影响内容搜索结果或从以前的地理位置搜索邮箱的能力。 有关详细信息，请参阅在多地理位置 [环境中搜索和导出内容](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)。

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>在特定地理位置中创建新的云邮箱

若要在特定地理位置中创建新邮箱，你需要执行以下任一步骤：

- 配置 **PreferredDataLocation** 值，如前面的将 [](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)现有仅云邮箱移动到特定地理位置部分所述，然后再在Exchange Online。 例如，在分配许可证之前，在用户上配置 **PreferredDataLocation** 值。

- 在设置 **PreferredDataLocation** 值的同时分配许可证。

若要在特定地理位置中创建新的仅限云许可用户（未通过 AAD Connect 同步），请在 Azure AD PowerShell 中使用以下语法：

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

此示例使用下面的值为 Elizabeth Brunner 创建新用户帐户：

- 用户主体名称：ebrunner@contoso.onmicrosoft.com
- 名字：Elizabeth
- 姓氏：Brunner
- 显示名称：Elizabeth Brunner
- 密码： 随机生成，并显示在命令的结果中（因为我们未使用 *Password* 参数）
- 许可证：`contoso:ENTERPRISEPREMIUM` (E5)
- 位置：澳大利亚 (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

有关创建新用户帐户和在 Azure AD PowerShell 中查找 LicenseAssignment 值的详细信息，请参阅[使用 PowerShell 创建用户帐户](create-user-accounts-with-microsoft-365-powershell.md)和[使用 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。

> [!NOTE]
> 如果使用 Exchange Online PowerShell 启用邮箱并需要在 **PreferredDataLocation** 中所指定的地理位置中直接创建邮箱，你需要直接针对云服务使用诸如 **Enable-Mailbox** 或 **New-Mailbox** 等 Exchange Online cmdlet。 如果在本地 Exchange PowerShell 中使用 **Enable-RemoteMailbox** cmdlet，则会在中心地理位置创建邮箱。

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>在特定地理位置中载入现有本地邮箱

你可以使用标准载入工具和流程将邮箱从本地 Exchange 组织迁移到 Exchange Online，这些工具和流程包括 [EAC 中的“迁移”仪表板](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)，以及 Exchange Online PowerShell 中的 [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet。

第一步是验证用户对象对于要载入的每个邮箱是否存在，并验证是否在 Azure AD 中配置了正确的 **PreferredDataLocation** 值。 载入工具将考虑 **PreferredDataLocation** 值，并将邮箱直接迁移到指定地理位置。

或者，你可以使用以下步骤，通过 Exchange Online PowerShell 中 [New-MoveRequest](/powershell/module/exchange/new-moverequest) cmdlet 在特定地理位置中直接载入邮箱。

1. 验证用户对象对于要载入的每个邮箱是否存在，并且是否在 Azure AD 中将 **PreferredDataLocation** 设置为所需的值。 **PreferredDataLocation** 的值将同步到 Exchange Online 中对应邮件用户对象的 **MailboxRegion** 属性。

2. 使用本主题前面的连接说明直接连接到特定附属地理位置。

3. 在 Exchange Online PowerShell 中，通过运行以下命令，将用于执行邮箱迁移的本地管理员凭据存储在一个变量中：

   ```powershell
   $RC = Get-Credential
   ```

4. 在 Exchange Online PowerShell 中，创建一个类似于以下示例的新 **New-MoveRequest**：

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. 为需要从本地 Exchange 迁移到当前连接的附属地理位置的每个邮箱重复步骤 4。

6. 如果需要将其他邮箱迁移到不同的附属地理位置，请为每个特定位置重复步骤 2-4。

## <a name="multi-geo-reporting"></a>多地理位置报告

Microsoft 365 管理中心中的“**多地理位置使用情况报告**”按地理位置显示用户计数。 该报告显示当前月份的用户分布，并提供过去 6 个月的历史数据。

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)