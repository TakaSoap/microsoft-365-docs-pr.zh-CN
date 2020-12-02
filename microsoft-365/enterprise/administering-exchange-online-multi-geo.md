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
localization_priority: normal
description: 了解如何使用 PowerShell 在 Microsoft 365 环境中管理 Exchange Online 多地理位置设置。
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552003"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>在多地理位置环境中管理 Exchange Online 邮箱

需要 Exchange Online PowerShell 才能查看和配置 Microsoft 365 环境中的多地理属性。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

你需要 [Microsoft Azure Active Directory PowerShell 模块](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 或 v1.x 中的更高版本才能查看用户对象的 **PreferredDataLocation** 属性。 无法通过 AAD PowerShell 直接修改通过 AAD Connect 同步到 AAD 中的用户对象的 **PreferredDataLocation** 值。 可以通过 AAD PowerShell 修改仅限云的用户对象。 若要连接到 Azure AD PowerShell，请参阅[连接到 PowerShell](connect-to-microsoft-365-powershell.md)。

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>使用 Exchange Online PowerShell 直接连接到某个地理位置

通常，Exchange Online PowerShell 将连接到中心地理位置。 但你也可以直接连接到附属地理位置。 由于性能有所改进，因此，当你仅管理附属地理位置中的用户时，我们建议直接连接到该位置。

[安装和维护 EXO V2 模块](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)中介绍了安装和使用 EXO V2 模块的要求。

若要将 Exchange Online PowerShell 连接到特定地理位置， *ConnectionUri* 参数与常规连接说明不同。 命令和值的其余部分是相同的。

具体来说，您需要将 `?email=<emailaddress>` 值添加到 _ConnectionUri_ 值的末尾。 `<emailaddress>` 是目标地理位置中 **任何** 邮箱的电子邮件地址。 您对该邮箱的权限或与您的凭据的关系不是一个因素;电子邮件地址只是告诉 Exchange Online PowerShell 在哪里连接。

Microsoft 365 或 Microsoft 365 GCC 客户通常不需要使用 _ConnectionUri_ 参数连接到 Exchange Online PowerShell。 但是，若要连接到特定地理位置，您需要使用 _ConnectionUri_ 参数，以便可以 `?email=<emailaddress>` 在值中使用。

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>连接到 Exchange Online PowerShell 中的地理位置

以下连接说明适用于或未配置为多重身份验证 (MFA) 的帐户。

1. 在 Windows PowerShell 窗口中，通过运行以下命令加载 EXO V2 模块：

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. 在以下示例中，admin@contoso.onmicrosoft.com 是管理员帐户，目标地理位置是邮箱 olga@contoso.onmicrosoft.com 所在的位置。

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. 在出现的提示中，输入 admin@contoso.onmicrosoft.com 的密码。 如果将帐户配置为进行 MFA，还需要输入安全代码。

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
> 如果数据库名称中的地理位置代码与 **MailboxRegion** 值不匹配，则会自动将该邮箱放入位置队列并移动到由 **MailboxRegion** 值指定的地理位置， (Exchange Online 会在这些属性值) 之间查找不匹配项。

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
> - 如前所述，不能对本地 Active Directory 中的同步用户对象使用此过程。 你需要在 Active Directory 中更改 **PreferredDataLocation** 值，并使用 AAD Connect 进行同步。 有关详细信息，请参阅 [Azure Active Directory Connect 同步：为 Microsoft 365 资源配置首选数据位置](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)。
>
> - 将邮箱重定位到新的地理位置所花费的时间取决于若干因素：
>
>   - 邮箱的大小和类型。
>   - 正在移动的邮箱数量。
>   - 移动资源的可用性。

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>将非活动邮箱移动到特定地理位置

您无法移动出于合规性目的而保留的非活动邮箱 (例如，诉讼保留) 上的邮箱通过更改其 **PreferredDataLocation** 值来实现。 若要将非活动邮箱移动到不同地理位置，请执行以下步骤：

1. 恢复非活动邮箱。 有关说明，请参阅 [恢复非活动邮箱](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)。

2. 通过将 \<MailboxIdentity\> 邮箱的名称、别名、帐户或电子邮件地址替换并在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中运行以下命令，阻止托管文件夹助理处理恢复的邮箱：

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. 向恢复的邮箱分配 **Exchange Online 计划 2** 许可证。 这一步是将邮箱置于诉讼保留状态的必要条件。 有关说明，请参阅 [向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

4. 按照上一节中所述，在邮箱上配置 **PreferredDataLocation** 值。

5. 确认邮箱已移动到新的地理位置之后，将恢复的邮箱重新置于诉讼保留状态。 有关说明，请参阅 [将邮箱置于诉讼保留状态](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)。

6. 验证诉讼保留是否就绪后，允许托管文件夹助理通过将 \<MailboxIdentity\> 邮箱的名称、别名、帐户或电子邮件地址替换并在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中运行以下命令来再次处理邮箱：

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. 通过删除与邮箱关联的用户帐户，使邮箱再次处于非活动状态。 有关说明，请参阅 [从组织中删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)。 此步骤还将释放 Exchange Online 计划2许可证，以供其他用途。

**注意**：将非活动邮箱移到其他地理位置时，可能会影响内容搜索结果或从以前的地理位置搜索邮箱的功能。 有关详细信息，请参阅 [在多地理位置环境中搜索和导出内容](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)。

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>在特定地理位置中创建新的云邮箱

若要在特定地理位置中创建新邮箱，你需要执行以下任一步骤：

- 按照上一步 [将现有仅云邮箱移动到特定地理位置](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)部分中所述配置 **PreferredDataLocation** 值，*然后再* 在 Exchange Online 中创建邮箱。 例如，在分配许可证前配置用户的 **PreferredDataLocation** 值。

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

你可以使用标准载入工具和流程将邮箱从本地 Exchange 组织迁移到 Exchange Online，这些工具和流程包括 [EAC 中的“迁移”仪表板](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)，以及 Exchange Online PowerShell 中的 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet。

第一步是验证用户对象对于要载入的每个邮箱是否存在，并验证是否在 Azure AD 中配置了正确的 **PreferredDataLocation** 值。 载入工具将考虑 **PreferredDataLocation** 值，并将邮箱直接迁移到指定地理位置。

或者，你可以使用以下步骤，通过 Exchange Online PowerShell 中 [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet 在特定地理位置中直接载入邮箱。

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
