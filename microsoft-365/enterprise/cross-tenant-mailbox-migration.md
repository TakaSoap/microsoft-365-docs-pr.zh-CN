---
title: 交叉租户邮箱迁移
description: 如何在租户或租户Microsoft 365 Office 365邮箱。
ms.author: kvice
author: kelleyvice-msft
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 6b2ef03984e6ed7c9b93476869e998bb06b78a30
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58566828"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>跨租户邮箱迁移 (预览) 

以前，当 Exchange Online 租户需要将邮箱移动到同一 Exchange Online 服务中的另一个租户时，他们必须将其完全离开本地，然后载入新租户。 借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。 这将无需离开和载入邮箱。

通常，在合并或资产重组期间，你需要能够将用户和内容移动到新租户。 当目标租户管理员执行移动时，这称为"拉取"移动，类似于本地到云载入迁移。

跨租户Exchange邮箱移动完全由租户管理员提供自助服务，使用已知的接口，这些接口可编写脚本到将用户转换到其新组织所需的较大工作流中。 管理员可以使用可通过"移动邮箱"管理角色使用的 `New-MigrationBatch` cmdlet 执行跨租户移动。 移动过程包括邮箱同步和最终完成期间租户授权检查。

迁移的用户必须作为 MailUsers Exchange Online目标租户系统中，并带有特定属性标记才能启用跨租户移动。 对于未在目标租户中正确设置的用户，系统移动将失败。

移动完成后，源系统邮箱将转换为 MailUser，并且 targetAddress (显示为 Exchange) 中的 ExternalEmailAddress，并标记目标租户的路由地址。 此过程将旧版 MailUser 保留于源租户中，并允许共存一段时间和邮件路由。 当业务流程允许时，源租户可能会删除源 MailUser 或将其转换为邮件联系人。

跨租户Exchange邮箱迁移仅支持混合或云中的租户，或两者的任意组合。

本文介绍了跨租户邮箱移动的过程，并提供了有关如何为内容移动准备源租户和目标租户的指南。

## <a name="preparing-source-and-target-tenants"></a>准备源租户和目标租户

跨租户迁移Exchange迁移功能需要跨租户迁移的授权和范围。 通过使用 Azure Enterprise应用程序和密钥保管库存储解决方案，租户管理员现在能够管理从一个租户到另一个租户Exchange Online邮箱迁移的授权和范围。 跨租户邮箱移动支持邀请和同意模型，以Azure Active Directory (Azure AD) 应用程序，用于在租户对之间进行身份验证。 还需要其他组件，如组织关系和迁移终结点。

本节不包含在目标目录中准备 MailUser 用户对象所需的特定步骤，也不包括提交迁移批处理的示例命令。 有关此信息 [，请参阅准备目标用户对象进行](#prepare-target-user-objects-for-migration) 迁移。

## <a name="prerequisites"></a>先决条件

跨租户邮箱移动功能需要 [Azure Key Vault](/azure/key-vault/basic-concepts) 来建立特定于租户对的 Azure 应用程序，以安全存储和访问用于对邮箱从一个租户迁移到另一个租户进行身份验证和授权迁移的证书/密码，从而删除在租户之间共享证书/密码的任何要求。

在启动之前，请确保你拥有运行部署脚本的必要权限，以便配置 Azure Key Vault、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。 通常，全局管理员具有执行所有配置步骤的权限。

此外，在运行安装程序之前，源租户中需要启用邮件的安全组。 这些组用于将邮箱列表的范围从源租户 (有时称为资源) 租户移动到目标租户。 这允许源租户管理员限制或限定需要移动的特定邮箱集，以防止迁移非预期用户。 不支持嵌套组。

你还需要与你的受信任合作伙伴公司 (，你要将邮箱移动到) 以获取其Microsoft 365 ID。 此租户 ID 用于"组织关系" `DomainName` 字段。

若要获取订阅的租户 ID，请登录到 Microsoft 365 管理中心 并转到 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。 单击"租户 ID"属性的复制图标，将其复制到剪贴板。

下面是此过程的工作方式。

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="邮箱迁移的租户准备。":::

[请参阅此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。

<!--
[![Tenant preparation for mailbox migration.](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
-->

### <a name="prepare-tenants"></a>准备租户

在高级别上，执行安装程序脚本时将执行以下配置操作。

准备目标租户：

1. 如果未提供现有的 Azure 资源组，则使用 SCRIPT (一) 。
2. 如果未提供现有密钥保管库，则使用 SCRIPT (一) 。
3. 新的访问策略是使用 SCRIPT Office 365 Exchange Online 为 (创建) 。
4. 新证书将 (现有证书（如果指定) ，以将密码 (SCRIPT) 。
5. 新的 Azure AD 应用程序是在 SCRIPT (中创建) 。
6. 证书/密码将上载到迁移应用程序 (SCRIPT) 。
7. 邮箱迁移权限将分配给 SCRIPT (应用程序) 。
8. 部署脚本将暂停，直到目标管理员同意使用 SCRIPT (自己的) 。
9. 目标租户管理员同意向应用程序授予 (手动) 。
10. 将创建与目标租户的组织关系 (SCRIPT) 。
11. 创建迁移终结点以将邮箱拉至 SCRIPT (目标) 。

准备源租户：

1. 源租户管理员接受来自手动迁移目标租户 (邮箱) 。
2. 源租户管理员在租户中创建一个启用邮件的安全组，以包含允许迁移应用程序在手动迁移 (移动) 。
3. 创建与目标租户的组织关系，指定邮箱迁移应用程序应用于 OAuth 验证，以接受 SCRIPT (移动) 。

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>目标租户管理员的分步说明

1. 从 SetupCrossTenantRelationshipForTargetTenant.ps1 存储库下载目标租户设置的[GitHub 脚本](https://github.com/microsoft/cross-tenant/releases/tag/Preview)。
2. 将脚本 (SetupCrossTenantRelationshipForTargetTenant.ps1) 保存到要执行脚本的计算机。
3. 创建与目标租户的远程 PowerShell Exchange Online连接。 同样，请确保你拥有运行部署脚本的必要权限，以便配置 Azure 密钥保管库存储和证书、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。
4. 将文件文件夹目录更改为脚本位置，或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。
5. 运行具有以下参数和值的脚本。

   |参数|值|必需或可选
   |---|---|---|
   |-TargetTenantDomain|目标租户域，如 fabrikam \. onmicrosoft.com。|必需|
   |-ResourceTenantDomain|源租户域，如 contoso \. onmicrosoft.com。|必需|
   |-ResourceTenantAdminEmail|源租户管理员的电子邮件地址。 这是将同意使用从目标管理员发送的邮箱迁移应用程序的源租户管理员。这是将接收应用程序的电子邮件邀请的管理员。|必需|
   |-ResourceTenantId|源租户组织 ID (GUID) 。|必需|
   |-SubscriptionId|用于创建资源的 Azure 订阅。|必需|
   |-ResourceGroup|包含或将包含密钥保管库的 Azure 资源组名称。|必需|
   |-KeyVaultName|将存储邮箱迁移应用程序证书/密码的 Azure Key Vault 实例。|必需|
   |-CertificateName|在密钥保管库中生成或搜索证书时证书名称。|必需|
   |-CertificateSubject|Azure Key Vault 证书主题名称，例如 CN=contoso_fabrikam。|必需|
   |-AzureResourceLocation|Azure 资源组和密钥保管库的位置。|必需|
   |-ExistingApplicationId|邮件迁移应用程序，如果已创建，将使用该应用程序。|可选|
   |-AzureAppPermissions|为邮箱迁移应用程序（如 Exchange 或 MSGraph (Exchange）授予移动邮箱所需的权限，MSGraph 用于使用此应用程序向资源租户) 发送同意链接邀请。|必需|
   |-UseAppAndCertGeneratedForSendingInvitation|用于使用为迁移创建的应用程序的参数，用于向源租户管理员发送同意链接邀请。如果不存在，这将提示目标管理员的凭据连接到 Azure 邀请管理器，并将邀请作为目标管理员发送。|可选|
   |-KeyVaultAuditStorageAccountName|存储密钥保管库审核日志的存储帐户。|可选|
   |-KeyVaultAuditStorageResourceGroup|包含用于存储密钥保管库审核日志的存储帐户的资源组。|可选|
   ||||

    > [!NOTE]
    > 请确保在运行脚本之前已安装 Azure AD PowerShell 模块。 有关安装 [步骤，](/powershell/azure/install-az-ps) 请参阅此处

6. 脚本将暂停，并要求你接受或同意Exchange创建的邮件邮箱迁移应用程序。 下面是一个示例。

    ```powershell
    PS C:\PowerShell\> # Note: the below User.Invite.All permission is optional, and will only be used to retrieve access token to send invitation email to source tenant
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - User.Invite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```

7. URL 将显示在远程 PowerShell 会话中。 复制为租户许可提供的链接，并将其粘贴到 Web 浏览器中。

8. 使用全局管理员凭据登录。 显示以下屏幕时，选择"接受 **"。**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="&quot;接受权限&quot;对话框。":::

9. 切换回远程 PowerShell 会话并按 Enter 继续。

10. 该脚本将配置其余的安装程序对象。 下面是一个示例。

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

目标管理员设置现已完成！

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>源租户管理员的分步说明

1. 使用全局管理员凭据登录。 以目标管理员在设置过程中指定的 -ResourceTenantAdminEmail 登录邮箱。  从目标租户查找电子邮件邀请，然后选择 **"入门按钮**。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="你已被邀请对话框":::

2. 选择 **"接受** "接受邀请。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="用于接受权限的对话框。":::

   > [!NOTE]
   > 如果未收到此电子邮件或找不到此电子邮件，则为目标租户管理员提供了一个直接 URL，可提供给你接受邀请。 目标租户管理员的远程 PowerShell 会话脚本中的 URL 应包含。

3. 在 Microsoft 365 管理中心 或远程 PowerShell 会话中，创建一个或多个启用邮件的安全组，以控制目标租户允许的邮箱列表，以将 (从源租户) 移动到目标租户。 无需提前填充此组，但必须至少提供一个组，以运行脚本 (安装) 。 不支持嵌套组。

4. 从 SetupCrossTenantRelationshipForResourceTenant.ps1存储库下载源租户设置的 GitHub 脚本 [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ：。

5. 使用管理员权限创建到源租户的Exchange PowerShell 连接。 由于 Azure 应用程序创建过程，配置源租户（仅目标租户）不需要全局管理员权限。

6. 将目录更改为脚本位置或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。

7. 运行具有以下必需参数和值的脚本。

   |参数|值|
   |---|---|
   |-SourceMailboxMovePublishedScopes|源租户为迁移范围内标识/邮箱创建的启用邮件的安全组。|
   |-ResourceTenantDomain|源租户域名，如 contoso \. onmicrosoft.com。|
   |-ApplicationId|Azure 应用程序 ID (迁移) 的 GUID 值。 可通过 Azure 门户获取的应用程序 ID (Azure AD、Enterprise 应用程序、应用名称、应用程序 ID) 包含在邀请电子邮件中。|
   |-TargetTenantDomain|目标租户域名，如 fabrikam \. onmicrosoft.com。|
   |-TargetTenantId|目标租户的租户 ID。 例如，contoso 租户的 Azure AD onmicrosoft.com \. ID。|
   |||

    下面是一个示例。

    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.
    ```

源管理员设置现已完成！

### <a name="verify-setup"></a>验证设置

验证目标中的源和目标租户以及迁移终结点中的组织关系是否创建成功。

#### <a name="target-tenant"></a>目标租户

##### <a name="organization-relationship"></a>组织关系

验证已使用此命令创建和配置组织关系对象。

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
下面是一个示例：

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound
```

##### <a name="migration-endpoint"></a>迁移终结点

验证已使用此命令创建和配置迁移终结点对象。

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

下面是一个示例。

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308
```

#### <a name="source-tenant"></a>源租户

##### <a name="organization-relationship"></a>组织关系

验证已使用此命令创建和配置组织关系对象。

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

下面是一个示例。

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>验证安装脚本

如果在配置源租户或目标租户期间收到任何错误，可以运行位于 VerifySetup.ps1 上的 GitHub 脚本并查看输出。 [](https://github.com/microsoft/cross-tenant/releases/tag/Preview)

下面是在目标租户上运行VerifySetup.ps1的示例：

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

下面是源租户上VerifySetup.ps1的示例：

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>将邮箱移回原始源

如果需要将邮箱移回原始源租户，则需要在新源租户和新目标租户中运行相同的步骤和脚本集。 将更新或追加现有组织关系对象，而不是重新创建该对象。

## <a name="prepare-target-user-objects-for-migration"></a>准备目标用户对象进行迁移

迁移的用户必须存在于目标租户中，Exchange Online系统 (MailUsers) 使用特定属性进行标记，以启用跨租户移动。 对于未在目标租户中正确设置的用户，系统移动将失败。 以下部分详细介绍了目标租户的 MailUser 对象要求。

### <a name="prerequisites"></a>先决条件

必须确保在目标组织中设置以下对象和属性。

1. 对于从源组织移动的任何邮箱，必须在目标组织中设置 MailUser 对象：

   - 目标 MailUser 必须具有源邮箱中的这些属性或分配有新的 User 对象：
      - ExchangeGUID (源到目标邮箱的直接) – 邮箱 GUID 必须匹配。 如果目标对象上不存在移动过程，则移动过程将不会继续进行。
      - ArchiveGUID (源到目标用户) – 存档 GUID 必须匹配。 如果目标对象上不存在移动过程，则移动过程将不会继续进行。  (仅在源邮箱已启用存档) 。
      - LegacyExchangeDN (flow as proxyAddress， "x500： \<LegacyExchangeDN> ") – LegacyExchangeDN 必须作为 x500： proxyAddress 存在于目标 MailUser 上。 此外，还需要将源邮箱的所有 x500 地址复制到目标邮件用户。 如果目标对象上不存在移动过程，则移动过程将不会继续进行。 
      - UserPrincipalName – UPN 将与用户的新标识或目标公司 (例如，user@northwindtraders.onmicrosoft.com) 。
      - 主 SMTP 地址 – 主 SMTP 地址将与用户的 NEW 公司地址 (例如，user@northwind.com) 。
      - TargetAddress/ExternalEmailAddress – MailUser 将引用托管在源租户中的用户当前邮箱 (例如 user@contoso.onmicrosoft.com) 。 分配此值时，请验证是否还分配了 PrimarySMTPAddress，否则此值将设置会导致移动失败的 PrimarySMTPAddress。
      - 不能将源邮箱中的旧版 smtp 代理地址添加到目标 MailUser。 例如，无法在租户 contoso.com MEU 上 fabrikam.onmicrosoft.com MEU) 。 域仅与一个 Azure AD 或 Exchange Online关联。

     示例 **目标** MailUser 对象：

     |属性|值|
     |---|---|
     |别名|LaraN|
     |RecipientType|MailUser|
     |RecipientTypeDetails|MailUser|
     |UserPrincipalName|LaraN@northwintraders.onmicrosoft.com|
     |PrimarySmtpAddress|Lara.Newton@northwind.com|
     |ExternalEmailAddress|SMTP:LaraN@contoso.onmicrosoft.com|
     |ExchangeGuid|1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8|
     |LegacyExchangeDN|/o=First Organization/ou=Exchange Administrative Group|
     || (FYDIBOHF23SPDLT) /cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara|
     |EmailAddresses|x500：/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c8190|
     ||7273f1f9-Lara|
     ||smtp:LaraN@northwindtraders.onmicrosoft.com|
     ||SMTP:Lara.Newton@northwind.com|
     |||

     示例 **源** Mailbox 对象：

     |属性|值|
     |---|---|
     |别名|LaraN|
     |RecipientType|UserMailbox|
     |RecipientTypeDetails|UserMailbox|
     |UserPrincipalName|LaraN@contoso.onmicrosoft.com|
     |PrimarySmtpAddress|Lara.Newton@contoso.com|
     |ExchangeGuid|1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8|
     |LegacyExchangeDN|/o=First Organization/ou=Exchange Administrative Group|
     || (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara|
     |EmailAddresses|smtp:LaraN@contoso.onmicrosoft.com
     ||SMTP:Lara.Newton@contoso.com|
     |||

   - 混合回写中可能Exchange属性。 如果没有，应包含它们。
   - msExchBlockedSendersHash – 将来自客户端的联机安全发件人和阻止的发件人数据写回本地 Active Directory。
   - msExchSafeRecipientsHash – 将来自客户端的联机安全发件人和阻止的发件人数据写回本地 Active Directory。
   - msExchSafeSendersHash – 将来自客户端的联机安全发件人和阻止的发件人数据写回本地 Active Directory。

2. 如果源邮箱位于 LitigationHold 中，且源邮箱"可恢复的项目"大小大于数据库默认 (30 GB) ，将不会继续移动，因为目标配额小于源邮箱大小。 您可以更新目标 MailUser 对象以将 ELC 邮箱标志从源环境转换到目标，这将触发目标系统将 MailUser 的配额扩展到 100 GB，从而允许移动到目标。 这些说明仅适用于运行 Azure AD 连接混合标识，因为标记 ELC 标志的命令不会向租户管理员公开。

    > [!NOTE]
    > 示例 - 就像现在一样，无担保
    >
    > 此脚本假定与源邮箱 (连接，以获取源值) 和目标本地 Active Directory (标记 ADUser) 。 如果源已启用诉讼或单个项目恢复，则对目标帐户设置此项。  这会将目标帐户的垃圾站大小增加至 100 GB。

    ```powershell
    $ELCValue = 0
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}}
    ```

3. 非混合目标租户可以在迁移之前修改 MailUsers 的"可恢复的项目"文件夹的配额，方法为运行以下命令以对 MailUser 对象启用诉讼保留，将配额增加至 100 `Set-MailUser -EnableLitigationHoldForMigration` GB：。 请注意，这适用于混合租户。

4. 目标组织的用户必须获得适用于Exchange Online相应订阅的许可。 您可以在邮箱移动之前应用许可证，但仅在使用 ExchangeGUID 和代理地址正确设置目标 MailUser 之后。 在应用 ExchangeGUID 之前应用许可证将导致在目标组织中设置新邮箱。

    > [!NOTE]
    > 当您对 Mailbox 或 MailUser 对象应用许可证时，会擦除所有 SMTP 类型 proxyAddresses，以确保仅验证的域包含在 Exchange EmailAddresses 数组中。

5. 必须确保目标 MailUser 之前没有与 Source ExchangeGuid 不匹配的 ExchangeGuid。 如果目标 MEU 之前已获得邮箱许可，Exchange Online配置邮箱，则可能会发生这种情况。 如果目标 MailUser 以前已获得许可，或者拥有与 Source ExchangeGuid 不匹配的 ExchangeGuid，则需要清理云 MEU。 对于这些云 MEUS，你可以运行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 。

    > [!CAUTION]
    > 此过程是不可逆的。 如果对象具有 softDeleted 邮箱，则此时之后将无法还原。 但是，清除后，您可以将正确的 ExchangeGuid 同步到目标对象，MRS 将源邮箱连接到新创建的目标邮箱。  (参数上引用 EHLO 博客。) 

    使用此命令查找以前是邮箱的对象。

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    下面是一个示例。

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize

    Name       PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails
    ----       ---------------------------- ------------- --------------------
    John       UserMailbox                  MailUser      MailUser
    ```

    使用此命令清除软删除的邮箱。

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    下面是一个示例。

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm
    Are you sure you want to perform this action?
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.
    Do you want to continue?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y
    ```

## <a name="perform-mailbox-migrations"></a>执行邮箱迁移

跨租户Exchange邮箱迁移作为从目标租户启动的迁移批处理提交。 这类似于从本地迁移批处理迁移到本地Exchange迁移批处理Microsoft 365。

### <a name="create-migration-batches"></a>创建迁移批处理

下面是用于启动移动的迁移批处理 cmdlet 示例。

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!NOTE]
> CSV 文件中的电子邮件地址必须是目标租户中指定的地址，而不是源租户中指定的电子邮件地址。

选择跨租户选项时，还支持从Exchange管理中心提交迁移批处理。

#### <a name="update-on-premises-mailusers"></a>更新本地 MailUsers

邮箱从源移动到目标之后，应确保使用新的 targetAddress 更新内部部署邮件用户（源和目标用户）。 在示例中，移动中使用的 targetDeliveryDomain contoso.onmicrosoft.com **。** 更新具有此 targetAddress 的邮件用户。

## <a name="frequently-asked-questions"></a>常见问题解答

**在移动后，是否需要更新源本地中的 RemoteMailboxes？**

是，当源租户邮箱 (目标租户时，应更新源本地用户的 targetAddress (RemoteRoutingAddress/ExternalEmailAddress) 。  虽然邮件路由可以遵循不同 targetAddresses 的多个邮件用户的引荐，但邮件用户的忙/闲查找必须面向邮箱用户的位置。 忙/闲查找不会追踪多个重定向。

**是否Teams跨租户迁移会议？**

但是，当项目跨租户Teams，会议 URL 将不会更新。 由于目标租户中的 URL 无效，因此你将需要删除并重新创建Teams会议。

**聊天Teams内容是否跨租户迁移？**

否，Teams文件夹内容不会迁移跨租户。

**如何查看跨租户移动，而不是我的载入和离开移动？**

使用 `-flags` 参数。 下面是一个示例。

```powershell
Get-MoveRequest -Flags "CrossTenant"
```

**能否提供用于复制测试中使用的属性的示例脚本？**

> [!NOTE]
> 示例 - 就像现在一样，无担保<br/>此脚本假定与源邮箱 (连接，以获取源值) 和目标本地 Active Directory 域服务 (标记 ADUser 对象) 。 如果源已启用诉讼或单个项目恢复，则对目标帐户设置此项。  这会将目标帐户的垃圾站大小增加至 100 GB。

```powershell
#Dumps out the test mailboxes from SourceTenant
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit"
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

#################################################################
#Copy the file $outfile to the desktop of the target on-premises
#then run the below to create MEU in Target
#################################################################
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

#################################################################
# On AADSync machine, run AADSync
#################################################################
Start-ADSyncSyncCycle

#AADSync and FWDSync will create the target MEUs in the Target tenant
```

**移动使用邮箱Outlook第 1 天如何访问邮箱？**

由于只有一个租户可以拥有一个域，因此邮箱移动完成后，以前的主 SMTPAddress 不会与目标租户中的用户关联;仅与新租户关联的域。 Outlook用户使用新的 UPN 对服务进行身份验证，Outlook 配置文件希望查找旧版主 SMTPAddress 以匹配目标系统中邮箱。 由于旧地址不在目标系统中，Outlook 配置文件将不会连接以查找新移动的邮箱。

对于此初始部署，用户将需要使用新的 UPN 主 SMTP 地址重新构建其配置文件，然后重新同步 OST 内容。

> [!NOTE]
> 在批处理用户以完成时进行相应规划。 创建客户端配置文件并随后将 OST 和 OAB 文件下载到Outlook时，您需要考虑网络利用率和容量。

**我需要Exchange哪些 RBAC 角色来设置或完成跨租户移动？**

存在一个角色矩阵，这些角色基于执行邮箱移动时委派的职责假设。 目前，需要两个角色：

- 第一个角色用于建立将内容移入或移出租户/组织边界的授权的一次设置任务。 由于将数据从组织控制中移出是所有公司的重要问题，因此，我们选择具有组织管理员 (OrgAdmin) 的最高分配角色。 此角色必须更改或设置一个新的 OrganizationRelationship，该关系定义远程组织的 -MailboxMoveCapability。 只有 OrgAdmin 可以更改 MailboxMoveCapability 设置，而 OrganizationRelationhip 上的其他属性也可由联合共享管理员进行管理。

- 执行实际移动命令的角色可以委派给较低级别的函数。 "移动邮箱"角色分配有使用 参数将邮箱移进组织或将邮箱移出组织 `-RemoteTenant` 的功能。

**我们如何针对在转换为 MailUser 转换邮箱 (转换邮箱上的 targetAddress) TargetDeliveryDomain (选择哪个 SMTP) ？**

Exchange通过匹配目标对象上的电子邮件地址 (proxyAddress) ，使用 MRS 在原始源邮箱上创建 targetAddress 来移动邮箱。 该过程采用传入 move 命令的 -TargetDeliveryDomain 值，然后在目标端检查该域的匹配代理。 当我们找到匹配项时，匹配的 proxyAddress 将用于在转换的邮箱上设置 ExternalEmailAddress (targetAddress) （现在 (MailUser) 对象）。

**邮箱权限如何转换？**

邮箱权限包括"代表发送"和"邮箱访问"：

- 代表用户 (AD：publicDelegates) 将具有用户邮箱访问权限的收件人的 DN 存储为代理。 此值存储在 Active Directory 中，当前不会作为邮箱转换的一部分移动。 如果源邮箱设置了 publicDelegates，则运行 在目标环境中完成 MEU 到邮箱转换后，您需要在目标邮箱上重新标记 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` publicDelegates。

- 将主体和代理移动到目标系统时，邮箱中存储的邮箱权限将随邮箱一起移动。 例如，向用户TestUser_7向租户租户中的邮箱TestUser_8 FullAccess SourceCompany.onmicrosoft.com。 邮箱移动完成后，TargetCompany.onmicrosoft.com 目标目录中设置相同的权限。 对源租户和目标TestUser_7使用 *Get-MailboxPermission* 的示例如下所示。 Exchange cmdlet 的前缀与 source 和 target 的前缀一致。

下面是移动之前邮箱权限输出的示例。

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```

下面是移动后邮箱权限输出的示例。

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```

> [!NOTE]
> 不支持跨租户邮箱和日历权限。 必须将主体和代理组织到合并移动批处理中，以便同时从源租户转换这些连接的邮箱。

**应向目标 MailUser 代理地址添加哪些 X500 代理以启用迁移？**

跨租户邮箱迁移要求将源邮箱对象的 LegacyExchangeDN 值标记为目标 MailUser 对象上的 x500 电子邮件地址。

示例：

```powershell
LegacyExchangeDN value on source mailbox is:
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara

so the x500 email address to be added to target MailUser object would be:
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara
```

> [!NOTE]
> 除了此 X500 代理之外，还需要将源中的邮箱的所有 X500 代理复制到目标中的邮箱。

**如果移动不起作用，我在哪里开始疑难解答？**

首先运行位于 VerifySetup.ps1 上的[GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview)并查看输出。

下面是在目标租户上运行VerifySetup.ps1的示例：

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

下面是在源租户上运行VerifySetup.ps1的 eExample：

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**源租户和目标租户能否使用相同的域名？**

不需要。 源和目标租户域名必须是唯一的。 例如，域的源 contoso.com 和目标域 fourthcoffee.com。

**共享邮箱是否移动且仍正常工作？**

是的，但我们仅保留存储权限，如以下文章所述：

- [Microsoft Docs |管理邮件中收件人Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft 支持|如何在专用Exchange Outlook邮箱权限Office 365权限](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**是否要求 Azure 密钥保管库以及何时进行事务？**

是的，Azure 订阅需要使用密钥保管库来存储证书以授权迁移。 与使用用户名或密码&源进行身份验证的加入迁移不同，跨租户邮箱迁移使用 OAuth 和此证书作为密码/凭据。 必须在所有邮箱迁移中维护对密钥保管库的访问，因为密钥保管库在迁移开始时和结束时访问一次，在增量同步期间每 24 小时访问一次。 你可以在此处查看 AKV 成本 [计算详细信息](https://azure.microsoft.com/pricing/details/key-vault/)。

**您是否对批处理有任何建议？**

每个批次不要超过 2000 个邮箱。 强烈建议在截止日期前两周提交批处理，因为同步期间对最终用户没有任何影响。如果需要超过 50，000 个邮箱数量的指南，可以联系工程反馈通讯组列表，crosstenantmigrationpreview@service.microsoft.com。

**如果我将服务加密与客户密钥一同使用，该做什么？**

移动之前将解密邮箱。 如果仍然需要客户密钥，请确保在目标租户中配置客户密钥。 有关详细信息 [，](../compliance/customer-key-overview.md) 请参阅此处。

**估计的迁移时间是什么？**

为了帮助您规划迁移，此处的表显示了有关[](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)何时应完成批量邮箱迁移或单个迁移的准则。 这些估计基于以前客户迁移的数据分析。 由于每个环境都是唯一的，因此确切的迁移速度可能会有所不同。

请记住，此功能当前处于预览阶段，SLA 及任何适用的服务级别不适用于此功能的预览状态期间的任何性能或可用性问题。

## <a name="known-issues"></a>已知问题

- **问题：无法迁移自动展开的存档。** 跨租户迁移功能支持迁移特定用户的主邮箱和存档邮箱。 但是，如果源中的用户具有自动展开的存档（这意味着多个存档邮箱）无法迁移其他存档，并且应该会失败。

- **问题：具有非拥有 smtp 代理的云邮件用户地址块 MRS 移动后台。** 创建目标租户 MailUser 对象时，必须确保所有 SMTP 代理地址都属于目标租户组织。 如果不属于本地租户的目标邮件用户上存在 SMTP proxyAddress，则阻止 MailUser 到 Mailbox 的转换。 这是因为我们保证邮箱对象只能从租户对租户声明的域具有权威性 (域发送邮件) ：

  - 使用 Azure AD 连接 从本地同步用户时，使用指向邮箱所在的源租户的 ExternalEmailAddress 预配本地 MailUser 对象 (laran@contoso.onmicrosoft.com) 并且将 PrimarySMTPAddress 标记为驻留在目标租户 (Lara.Newton@northwind.com) 中的域。 这些值将同步到租户，并设置相应的邮件用户并准备迁移。 此处显示了一个示例对象。

    ```powershell
    target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses
    ExternalEmailAddress               EmailAddresses
    --------------------               --------------
    SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com}
    ```

   > [!NOTE]
   > EmailAddresses / proxyAddresses 数组中 *contoso.onmicrosoft.com* 地址。 

- **问题：具有"外部"主 SMTP 地址的 MailUser 对象被修改/重置为"内部"公司声明的域**

  MailUser 对象是指向非本地邮箱的指针。 对于跨租户邮箱迁移，从目标组织的角度看，我们使用 MailUser 对象表示源邮箱 () 或目标邮箱 (（从源组织的角度来看) ）。 MailUsers 将具有一个 ExternalEmailAddress (targetAddress) ，该地址指向实际邮箱 (ProxyTest@fabrikam.onmicrosoft.com) 的 smtp 地址和表示目录中邮箱用户的显示 SMTP 地址的 primarySMTP 地址。 一些组织选择将主 SMTP 地址显示为外部 SMTP 地址，而不是本地租户拥有/验证的地址 (如 fabrikam.com 而不是 contoso.com) 。  但是，一旦Exchange许可操作将服务计划对象应用于 MailUser，主 SMTP 地址将修改为本地组织验证 (contoso.com) 。 有两个可能的原因：

  - 当任何 Exchange 服务计划应用于 MailUser 时，Azure AD 进程将开始强制执行代理清理，以确保本地组织无法从另一个租户发送邮件、欺骗邮件或邮件。 如果本地组织未验证该地址，将删除具有这些服务计划的收件人对象上的任何 SMTP 地址。 与示例中的情况一样，Fabikam.com 租户未验证 contoso.onmicrosoft.com 域，因此清理会删除该 fabrikam.com 域。 如果您希望在迁移之前或迁移后在 MailUser 上保留这些外部域，则需要更改迁移过程，以在移动完成后或移动之前去除许可证，以确保用户应用了预期的外部品牌。 您需要确保邮箱对象已正确许可，不会影响邮件服务。<br/><br/>删除邮件租户中 MailUser 上的服务 Contoso.onmicrosoft.com 示例脚本如下所示。

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION"
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo
    ```

       此处显示了分配的 ServicePlans 集的结果。

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending
    ServicePlan           ProvisioningStatus
    -----------           ------------------
    ATP_ENTERPRISE        PendingProvisioning
    MICROSOFT_SEARCH      PendingProvisioning
    INTUNE_O365           PendingActivation
    PAM_ENTERPRISE        Disabled
    EXCHANGE_ANALYTICS    Disabled
    EQUIVIO_ANALYTICS     Disabled
    THREAT_INTELLIGENCE   Disabled
    LOCKBOX_ENTERPRISE    Disabled
    PREMIUM_ENCRYPTION    Disabled
    EXCHANGE_S_ENTERPRISE Disabled
    INFORMATION_BARRIERS  Disabled
    MYANALYTICS_P2        Disabled
    MIP_S_CLP1            Disabled
    MIP_S_CLP2            Disabled
    ADALLOM_S_O365        PendingInput
    RMS_S_ENTERPRISE      Success
    YAMMER_ENTERPRISE     Success
    PROJECTWORKMANAGEMENT Success
    BI_AZURE_P2           Success
    WHITEBOARD_PLAN3      Success
    SHAREPOINTENTERPRISE  Success
    SHAREPOINTWAC         Success
    KAIZALA_STANDALONE    Success
    OFFICESUBSCRIPTION    Success
    MCOSTANDARD           Success
    Deskless              Success
    STREAM_O365_E5        Success
    FLOW_O365_P3          Success
    POWERAPPS_O365_P3     Success
    TEAMS1                Success
    MCOEV                 Success
    MCOMEETADV            Success
    BPOS_S_TODO_3         Success
    FORMS_PLAN_E5         Success
    SWAY                  Success
    ```

    用户的 PrimarySMTPAddress 不再被清理。 the fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.

    下面是一个示例。

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress
    ------------------        -------------------------               --------------------
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com
    ```

    - 当 msExchRemoteRecipientType 设置为 8 (DeprovisionMailbox) 时，对于迁移到目标租户的本地 MailUsers，Azure 中的代理清理逻辑将删除非所有者域，将 primarySMTP 重置为拥有域。 通过清除本地 MailUser 中的 msExchRemoteRecipientType，代理清理逻辑将不再适用。

      下面是一组完整的可能服务计划，其中包括Exchange Online。

      |名称|
      |---|
      |Advanced eDiscovery 存储 (500GB) |
      |客户密码箱|
      |数据丢失防护|
      |Exchange Enterprise CAL Services (EOP、DLP) |
      |ExchangeEssentials|
      |ExchangeFoundation|
      |Exchange Online (P1) |
      |Exchange Online（计划 1）|
      |Exchange Online（计划 2）|
      |适用于 Exchange Online 的 Exchange Online Archiving|
      |适用于 Exchange Server 的 Exchange Online Archiving|
      |Exchange Online非活动用户加载项|
      |Exchange Online Kiosk|
      |Exchange Online 多地理位置功能|
      |Exchange Online 计划 1|
      |Exchange Online POP|
      |Exchange Online Protection|
      |信息屏障|
      |适用于 Office 365 的信息保护 - 高级版|
      |适用于 Office 365 的信息保护 - 标准版|
      |Insights MyAnalytics|
      |Microsoft 365高级审核|
      |Microsoft Bookings|
      |Microsoft 商业中心|
      |Microsoft MyAnalytics（完整版）|
      |Office 365 高级电子数据展示|
      |Microsoft Defender for Office 365 (计划 1) |
      |Microsoft Defender for Office 365 (计划 2) |
      |Office 365 特权访问管理|
      |高级版加密Office 365|
      ||
