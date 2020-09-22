---
title: 跨租户邮箱迁移
description: 如何在 Microsoft 365 或 Office 365 租户之间移动邮箱。
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f649a72dc5569e8aec46347df295aa3ff9d93613
ms.sourcegitcommit: 327163f70eac0de568ebe3c9a97a744c3ed408cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177139"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>跨租户邮箱迁移 (预览) 

以前，当 Exchange Online 租户需要将邮箱移动到同一个 Exchange Online 服务中的另一个租户时，他们必须完全将其分离到本地，然后再将其集成到新租户。 使用新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在其本地系统中具有最少基础结构依赖关系的租户之间移动邮箱。 这就消除了分离和板载邮箱的需求。

通常情况下，在合并或 divestitures 过程中，您需要能够将用户和内容移动到新的租户中。 当目标租户管理员执行移动时，它称为 "拉" 移动，类似于内部部署到云载入迁移。

跨租户 Exchange 邮箱移动由租户管理员完全自行维护，使用可编写为将用户转换为其新组织所需的更大工作流的已知接口。 管理员可以使用 `New-MigrationBatch` 通过移动邮箱管理角色提供的 cmdlet 来执行跨租户移动。 移动过程包括在邮箱同步和最终完成期间的租户授权检查。 
 
迁移的用户必须以 MailUsers 形式存在于目标租户 Exchange Online 系统中，并标记有特定属性以启用跨租户移动。 对于在目标租户中未正确设置的用户，系统将发生故障移动。 

移动完成后，源系统邮箱将转换为 MailUser，并且在 Exchange) 中显示为 ExternalEmailAddress 的 targetAddress (将标记为与目标租户的路由地址。 此过程会将旧版 MailUser 保留在源租户中，并允许存在一段共存和邮件路由。 当业务流程允许时，源租户可能会删除源 MailUser 或将其转换为邮件联系人。 

仅支持混合或云中的租户的跨租户 Exchange 邮箱迁移，或二者的任意组合。

本文介绍跨租户邮箱移动的过程，并提供有关如何为内容移动准备源和目标租户的指南。 

## <a name="preparing-source-and-target-tenants"></a>准备源和目标租户

跨租户 Exchange 邮箱迁移功能需要针对跨租户迁移进行授权和作用域。 通过使用 Azure 企业应用程序和密钥存储库存储解决方案，租户管理员现在可以管理从一个租户到另一个租户的 Exchange Online 邮箱迁移的授权和作用域。 跨租户邮箱移动支持邀请和同意模型，以在租户对之间进行身份验证 (Azure AD) 应用程序建立 Azure Active Directory。 此外，还需要其他组件（如组织关系和迁移终结点）。

本节不包括在目标目录中准备 MailUser 用户对象所需的特定步骤，也不包括用于提交迁移批处理的示例命令。 有关此信息，请参阅 [准备目标用户对象以供迁移](#prepare-target-user-objects-for-migration) 。

## <a name="prerequisites"></a>先决条件

跨租户邮箱移动功能要求 [Azure 密钥保管库](https://docs.microsoft.com/azure/key-vault/basic-concepts) 建立租户对特定的 azure 应用程序，以安全地存储和访问用于对从一个租户到另一个租户的邮箱迁移进行身份验证和授权的证书/机密，从而消除了在租户之间共享证书/密码的任何要求。 

在开始之前，请确保您具有运行部署脚本的必要权限，以便配置 Azure Key Vault、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。 通常，全局管理员有权执行所有配置步骤。

此外，还需要在运行安装程序之前在源租户中启用邮件的安全组。 这些组用于对可以从源 (（有时称为 "资源) 租户"）移动到目标租户的邮箱列表进行作用域。 这样，源租户管理员可以限制或限定需要移动的特定邮箱集，从而防止迁移意外的用户。 嵌套组不受支持。

您还需要与您要将邮箱移动到的受信任合作伙伴公司 (进行通信，) 获取其 Microsoft 365 租户 ID。 在 "组织" 关系字段中使用此租户 ID `DomainName` 。

若要获取订阅的租户 ID，请登录到 Microsoft 365 管理中心并转到 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。 单击 "租户 ID" 属性的 "复制" 图标，将其复制到剪贴板。

下面展示了此过程的工作原理。

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg" alt-text="邮箱迁移的租户准备。":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg).
--> 

### <a name="prepare-tenants"></a>准备租户

在高级别上执行安装脚本时，会进行以下配置操作。

准备目标租户：

1. 如果未提供现有 Azure 资源组，则会在脚本)  (创建一个新的 Azure 资源组。
2. 如果未提供现有的密钥存储库，则会在脚本)  (创建一个新的密钥存储库。
3. 将为 Office 365 Exchange Online 邮箱迁移应用程序 (脚本) 创建新的访问策略。
4. 如果指定) 将机密保存到迁移应用程序 (SCRIPT) 中，则 (或现有证书中创建一个新证书。
5.  (脚本) 创建新的 Azure AD 应用程序。
6. 证书/机密将上载到迁移应用程序 (脚本) 中。
7. 邮箱迁移权限分配给应用程序 (脚本) 。
8. 部署脚本将暂停，直至目标管理员将同意为自己的应用程序 (脚本) 。
9. 目标租户管理员同意 (手动) 向应用程序授予的权限。
10. 将为目标租户 (脚本) 创建一个组织关系。
11. 创建迁移终结点以将邮箱拉入目标租户 (脚本) 。

准备源租户：

1. 源租户管理员接受来自目标租户 (手动) 的邮箱迁移应用程序邀请的许可。
2. 源租户管理员在其租户中创建已启用邮件的安全组，以包含迁移应用程序允许移动的邮箱列表 (手动) 。
3. 将为指定邮箱迁移应用程序的目标租户创建一个组织关系，以便将移动请求 (脚本) 中的 "OAuth 验证"。

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>针对目标租户管理员的分步说明

1. 从 [GitHub 存储库](https://github.com/microsoft/cross-tenant/releases/tag/Preview)中下载目标租户安装程序的 SetupCrossTenantRelationshipForTargetTenant.ps1 脚本。 
2. 将脚本 ( # A0) 保存到将在其中执行脚本的计算机。
3. 创建与 Exchange Online 目标租户的远程 PowerShell 连接。 此外，请确保您具有运行部署脚本的必要权限，以便配置 Azure Key Vault 存储和证书、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。
4. 将文件文件夹目录更改为脚本位置，或验证脚本当前是否已保存到远程 PowerShell 会话中的当前位置。
5. 使用以下参数和值运行脚本。

    | 参数 | 值 | 必需或可选
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | 源租户域，如 fabrikam \. onmicrosoft.com。 | 必需 |
    | -ResourceTenantAdminEmail                   | 源租户管理员的电子邮件地址。 这是将同意使用从目标管理员发送的邮箱迁移应用程序的源租户管理员。这是将接收应用程序的电子邮件邀请的管理员。 | 必需 |
    | -TargetTenantDomain                         | 目标租户域，如 contoso \. onmicrosoft.com。 | 必需 |
    | -ResourceTenantId                           | 源租户组织 ID (GUID) 。 | 必需 |
    | -SubscriptionId                             | 用于创建资源的 Azure 订阅。 | 必需 |
    | -ResourceGroup                              | 包含或将包含密钥保管库的 Azure 资源组名称。 | 必需 |
    | -KeyVaultName                               | 将存储邮箱迁移应用程序证书/机密的 Azure Key Vault 实例。 | 必需 |
    | -CertificateName                            | 在密钥保管库中生成或搜索证书时的证书名称。 | 必需 |
    | -CertificateSubject                         | Azure Key Vault 证书使用者名称，例如 CN = contoso_fabrikam。 | 必需 |
    | -ExistingApplicationId                      | 要使用的邮件迁移应用程序（如果已经创建了一个）。 | 可选 |
    | -AzureAppPermissions                        | 授予邮箱迁移应用程序所需的权限，例如 Exchange 或 MSGraph (Exchange 以移动邮箱，MSGraph 使用此应用程序将同意链接邀请发送到资源租户) 。 | 必需 |
    | -UseAppAndCertGeneratedForSendingInvitation | 用于使用为迁移创建的应用程序的参数，用于向源租户管理员发送同意链接邀请。如果不存在，则会提示目标管理员的凭据连接到 Azure 邀请管理器，并将邀请作为目标管理员发送。 | 可选 |
    | -KeyVaultAuditStorageAccountName            | 将存储主要保管库审核日志的存储帐户。 | 可选 |
    | -KeyVaultAuditStorageResourceGroup          | 包含存储密钥保管库审核日志的存储帐户的资源组。 | 可选 |
    ||||

6. 该脚本将暂停，并要求您接受或同意在此过程中创建的 Exchange 邮箱迁移应用程序。 下面是一个示例。

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ``` 

7. 将在远程 PowerShell 会话中显示一个 URL。 复制为您的租户同意提供的链接，并将其粘贴到 Web 浏览器中。

8. 使用全局管理员凭据登录。 出现以下屏幕时，选择 " **接受**"。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text=""接受权限" 对话框":::
    
9. 切换回远程 PowerShell 会话并按 Enter 继续。

10. 脚本将配置其余的安装程序对象。 下面是一个示例。

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

目标管理员设置现已完成！

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>有关源租户管理员的分步说明

1.  在设置过程中，以由目标管理员指定的-ResourceTenantAdminEmail 的身份登录邮箱。 查找来自目标租户的电子邮件邀请，然后选择 " **开始入门** " 按钮。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text=""已 invided" 对话框":::

2. 选择 " **接受** " 接受邀请。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="用于接受 permissons 的对话框":::

   > [!NOTE]
   > 如果你未收到此电子邮件或找不到此电子邮件，则会向目标租户管理员提供一个直接 URL，以接受邀请。 URL 应在目标租户管理员的远程 PowerShell 会话的脚本中。

3. 在 Microsoft 365 管理中心或远程 PowerShell 会话中，创建一个或多个已启用邮件的安全组以控制目标租户允许的邮箱列表，以将源租户中的 (移动) 从源租户推送到目标租户。 您无需提前填充此组，但必须至少提供一个组，才能运行 "安装步骤" (脚本) 。 不支持嵌套组。 

4. 在 [此处](https://github.com/microsoft/cross-tenant/releases/tag/Preview)从 GitHub 存储库中下载源租户安装程序的 SetupCrossTenantRelationshipForTargetResource.ps1 脚本。 

5. 使用 Exchange 管理员权限创建与源租户的远程 PowerShell 连接。 由于 Azure 应用程序创建过程，不需要全局管理员权限来配置源租户（仅限目标租户）。

6. 将目录更改为脚本位置，或验证脚本当前是否已保存到远程 PowerShell 会话中的当前位置。

7. 运行带有以下必需参数和值的脚本。

    | 参数 | 值 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 由源租户为在迁移范围内的标识/邮箱创建的已启用邮件的安全组。 |
    | -ResourceTenantDomain | 源租户域名，如 fabrikam \. onmicrosoft.com。 |
    | -TargetTenantDomain | 目标租户域名，如 contoso \. onmicrosoft.com。 |
    | -ApplicationId | 用于迁移的应用程序的 Azure 应用程序 ID (GUID) 。 通过 Azure 门户提供的应用程序 ID (Azure AD、企业应用程序、应用名称、应用程序 ID) 或包含在邀请电子邮件中。  |
    | -TargetTenantId | 目标租户的租户 ID。 例如，contoso onmicrosoft.com 租户的 Azure AD 租户 ID \. 。 |
    |||
    
    下面是一个示例。
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

源管理员设置现已完成！

### <a name="verify-setup"></a>验证安装程序

验证是否成功创建了目标中的源租户和目标租户以及迁移终结点中的组织关系。

#### <a name="target-tenant"></a>目标租户

**组织关系**

验证是否已使用此命令创建并配置了组织关系对象。

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
如以下示例所示：

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**迁移终结点**

验证是否已使用此命令创建并配置迁移终结点对象。

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

下面是一个示例。

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>源租户

**组织关系**

验证是否已使用此命令创建并配置了组织关系对象。

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
下面是一个示例。

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>将邮箱移回原始源

如果要将邮箱移回原始源租户，则需要在新的源和新的目标租户中运行相同的一组步骤和脚本。 现有的组织关系对象将被更新或追加，而不是重新创建。

## <a name="prepare-target-user-objects-for-migration"></a>为迁移准备目标用户对象

迁移的用户必须在目标租户和 Exchange Online 系统中存在 (作为 MailUsers) 标有特定属性以启用跨租户移动。 对于在目标租户中未正确设置的用户，系统将发生故障移动。 以下部分详细介绍了目标租户的 MailUser 对象要求。

### <a name="prerequisites"></a>先决条件
  
您必须确保在目标组织中设置以下对象和属性。  

1. 对于从源组织移动的任何邮箱，必须在目标组织中预配 MailUser 对象： 
   - 目标 MailUser 必须包含源邮箱中的这些属性，或使用新的 User 对象分配这些属性：
      - ExchangeGUID (从源到目标) 的直接流–邮箱 GUID 必须匹配。 如果目标对象上不存在，则移动过程不会继续。 
      - ArchiveGUID (从源到目标) 的直接流–存档 GUID 必须匹配。 如果目标对象上不存在，则移动过程不会继续。  (仅当源邮箱已启用存档) 时才需要这样做。 
      - LegacyExchangeDN (flow as proxyAddress，"x500： <LegacyExchangeDN> " ) – LegacyExchangeDN 必须在目标 MailUser 上以 x500： proxyAddress 的形式存在。 如果目标对象上不存在，则移动进程不会继续。 
      - UserPrincipalName – UPN 将与用户的新标识或目标公司 (例如，user@northwindtraders.onmicrosoft.com) 相一致。 
      - 主 SMTPAddress –主 SMTP 地址将与用户的新公司 (例如，user@northwind.com) 。 
      - TargetAddress/ExternalEmailAddress – MailUser 将引用在源租户 (中托管的用户的当前邮箱，例如 user@contoso.onmicrosoft.com) 。 在分配此值时，请验证您是否具有/也分配了 PrimarySMTPAddress，否则此值将设置将导致移动失败的 PrimarySMTPAddress。 
      - 您不能将旧 smtp 代理地址从源邮箱添加到目标 MailUser。 例如，您无法在 fabrikam.onmicrosoft.com 租户对象) 中的 MEU 上维护 contoso.com。 域仅与一个 Azure AD 或 Exchange Online 租户相关联。
 
    **目标**MailUser 对象示例：
 
    | 属性             | 值                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | LaraN                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP： LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = 第一个组织/ou = Exchange 管理组                                                                   |
    |                       |  (FYDIBOHF23SPDLT) /cn = 收件人/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500：/o = 第一个组织/ou = Exchange 管理组 (FYDIBOHF23SPDLT) /cn = 收件人/cn = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | smtp： LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP： Lara \. Newton@northwind.com                                                                                           |
    |||

   示例 **源** 邮箱对象：

   | 属性             | 值                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = 第一个组织/ou = Exchange 管理组                   |
   |                       |  (FYDIBOHF23SPDLT) /cn = 收件人/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | smtp： LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP： Lara \. Newton@contoso.com          |
   |||

   - 其他属性可能已包含在 Exchange 混合写回中。 如果不是，则应包含它们。 
   - msExchBlockedSendersHash –将从客户端到本地 Active Directory 的安全和被阻止的发件人数据写回到本地。
   - msExchSafeRecipientsHash –将从客户端到本地 Active Directory 的安全和被阻止的发件人数据写回到本地。
   - msExchSafeSendersHash –将从客户端到本地 Active Directory 的安全和被阻止的发件人数据写回到本地。

2. 如果源邮箱在 LitigationHold 上，源邮箱可恢复的项目大小大于数据库默认值 (30 GB) ，由于目标配额小于源邮箱大小，移动不会继续。 您可以更新目标 MailUser 对象，将 ELC 邮箱标记从源环境转换为目标，这将触发目标系统将 MailUser 的配额扩展到 100 GB，从而允许移动到目标。 这些说明仅适用于运行 Azure AD Connect 的混合身份，因为用于标记 ELC 标志的命令不会向租户管理员公开。

    >[!Note]
    > 示例-原样，无担保<br/>此脚本假定连接到源邮箱 (，以获取源值) 和目标本地 Active Directory (以标记 Microsoft.rtc.management.adconnect.schema.aduser 对象) 。 如果源已启用诉讼或单个项目恢复，请在目标帐户上设置此设置。  这会将目标帐户的转储程序大小增加到 100 GB。

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. 在迁移之前，非混合目标租户可以修改 MailUsers 的 "可恢复的项目" 文件夹中的配额，方法是运行以下命令，在 MailUser 对象上启用诉讼保留，并将配额增加到 100 GB： `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 。 注释此操作不适用于混合中的租户。

4. 目标组织中的用户必须具有适用于组织的相应 Exchange Online 订阅的许可。 您可以在邮箱移动前应用许可证，但只有在使用 ExchangeGUID 和代理地址正确设置目标 MailUser 之后。 在应用 ExchangeGUID 之前应用许可证将导致在目标组织中预配新邮箱。 

    > [!Note]
    > 在对邮箱或 MailUser 对象应用许可证时，将会对所有 SMTP 类型 proxyAddresses 进行清理，以确保 Exchange EmailAddresses 阵列中仅包含已验证的域。 

5. 必须确保目标 MailUser 没有与源 ExchangeGuid 不匹配的以前的 ExchangeGuid。 如果目标 MEU 之前已授权使用 Exchange Online 并预配了邮箱，则可能会出现这种情况。 如果目标 MailUser 之前已授权或具有与源 ExchangeGuid 不匹配的 ExchangeGuid，则需要执行云 MEU 的清理。 对于这些云 Meu，您可以运行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 命令。 

    > [!Caution]
    > 此过程是不可逆的。 如果对象具有 softDeleted 邮箱，则在此之后无法还原。 但是，清除后，可以将正确的 ExchangeGuid 同步到目标对象，MRS 会将源邮箱连接到新创建的目标邮箱。  (在新参数上引用 EHLO 博客。 )  
 
    使用此命令查找以前为邮箱的对象。

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    下面是一个示例。 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    使用此命令清除软删除的邮箱。

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    下面是一个示例。

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>执行邮箱迁移

跨租户 Exchange 邮箱迁移作为从目标租户启动的迁移批处理提交。 这类似于在从本地 Exchange 本地迁移到 Microsoft 365 时，进行中的迁移批处理的工作方式。 

### <a name="create-migration-batches"></a>创建迁移批处理

以下是用于启动关闭移动的迁移批处理 cmdlet 示例。

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV 文件中的电子邮件地址必须是目标租户中指定的地址，而不是源租户中的电子邮件地址。

在选择 "跨租户" 选项时，新的 Exchange 管理中心也支持迁移批提交。
 
#### <a name="update-on-premises-mailusers"></a>更新本地 MailUsers

邮箱从源移动到目标后，应确保使用新的 targetAddress 更新本地邮件用户（源和目标）。 在此示例中，移动中使用的 targetDeliveryDomain 是 **contoso \. onmicrosoft.com**。 使用此 targetAddress 更新邮件用户。
 
## <a name="frequently-asked-questions"></a>常见问题
 
**是否需要在移动后在源本地更新 RemoteMailboxes？**
 
是的，当源租户邮箱移动到目标租户时，应更新源本地用户的 targetAddress (RemoteRoutingAddress/ExternalEmailAddress) 。  虽然邮件路由可以跟踪使用不同 targetAddresses 的多个邮件用户之间的引用，但邮件用户的忙/闲查找必须以邮箱用户的位置为目标。 忙/闲查找将不会跟踪多个重定向。 
 
**团队是否聊天文件夹内容迁移跨租户？** 

否，团队聊天文件夹内容不会迁移跨租户。 
 
**我如何才能看到跨租户移动而不是我的加入和脱离移动的移动？**

使用 `-flags` 参数。 下面是一个示例。

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**您可以提供用于复制测试中使用的属性的示例脚本吗？**

> [!Note]
> 示例-原样，无担保<br/>此脚本假定连接到源邮箱 (以获取源值) 和目标本地 Active Directory 域服务 (以标记 Microsoft.rtc.management.adconnect.schema.aduser 对象) 。 如果源已启用诉讼或单个项目恢复，请在目标帐户上设置此设置。  这会将目标帐户的转储程序大小增加到 100 GB。

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**如何在移动使用邮箱后在第1天访问 Outlook？**

由于只有一个租户可以拥有域，所以在邮箱移动完成时，将不会将前一个主 SMTPAddress 与目标租户中的用户关联。仅适用于与新租户关联的域。 Outlook 使用新 UPN 对服务进行身份验证，并且 Outlook 配置文件预期查找旧主 SMTPAddress 以匹配目标系统中的邮箱。 由于旧版地址不在目标系统中，outlook 配置文件将不会连接以查找新移动的邮箱。 

对于此初始部署，用户需要使用其新 UPN、主 SMTP 地址和重新同步 OST 内容重建其配置文件。 

> [!Note]
> 在批处理用户完成时进行相应的规划。 在创建 Outlook 客户端配置文件，并将后续 OST 和 OAB 文件下载到客户端时，需要考虑网络利用率和容量。 
 
**我需要作为其成员的 Exchange RBAC 角色才能设置或完成跨租户移动？**
 
根据执行邮箱移动时假设的委托职责，有一个角色矩阵。 目前，需要两个角色：  

- 第一个角色适用于一次性设置任务，用于建立将内容移入或移出租户/组织边界的授权。 由于将数据从组织控制中移出是所有公司的重要问题，因此我们选择了组织管理员 (OrgAdmin) 中分配的最高角色。 此角色必须更改或设置一个新的 Set-organizationrelationship，用于定义与远程组织的-MailboxMoveCapability。 只有 OrgAdmin 可以更改 MailboxMoveCapability 设置，而 OrganizationRelationhip 上的其他属性可以由联合共享管理员进行管理。 
 
- 执行实际 move 命令的角色可以委派给较低级别的函数。 移动邮箱的角色分配了使用参数将邮箱移入或移出组织的功能 `-RemoteTenant` 。  

**我们如何定位在转换后的邮箱上为 targetAddress (TargetDeliveryDomain) 选择的 SMTP 地址 (到 MailUser 转换) ？**
 
Exchange 邮箱移动使用 MRS 在将原始源邮箱转换为 MailUser 时通过) 目标对象上的电子邮件地址 (proxyAddress 来手工创建原始源邮箱上的 targetAddress。 此过程将使用传递到 move 命令的-TargetDeliveryDomain 值，然后在目标端为该域检查匹配的代理。 找到匹配项时，将使用匹配的 proxyAddress 设置已转换邮箱上的 ExternalEmailAddress (targetAddress)  (现在 MailUser) 对象。
 
**邮箱权限如何转换？**

邮箱权限包括 "代表发送" 和 "邮箱访问"： 

- 代表发送 (AD： publicDelegates) 将访问用户邮箱的收件人的 DN 存储为代理人。 此值存储在 Active Directory 中，并且当前不作为邮箱转换的一部分移动。 如果源邮箱已设置 publicDelegates，则在使用命令的目标环境中，如果 MEU 到邮箱转换完成，将需要对目标邮箱上的 publicDelegates `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 。 
 
- 当主体和代理都移到目标系统时，存储在邮箱中的邮箱权限将随邮箱一起移动。 例如，用户 TestUser_7 被授予租户 SourceCompany.onmicrosoft.com 中邮箱 TestUser_8 的 FullAccess。 邮箱移动完成到 TargetCompany.onmicrosoft.com 后，将在目标目录中设置相同的权限。 在源和目标租户中使用 *add-mailboxpermission* TestUser_7 的示例如下所示。 Exchange cmdlet 将相应地加上源和目标。 
 
下面的示例展示了邮箱权限在移动前的输出。 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
下面的示例展示了邮箱权限在移动后的输出。 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> 不支持跨租户邮箱和日历权限。 您必须将主体和代理组织到合并的移动批处理中，以便从源租户同时转换这些连接的邮箱。 
 
## <a name="known-issues"></a>已知问题 

-  **问题：无法迁移自动扩展存档。** 跨租户迁移功能支持特定用户的主邮箱和存档邮箱的迁移。 如果源中的用户有一个自动扩展的存档–即有多个存档邮箱，则该功能无法迁移其他存档。

- **问题：具有非拥有的 smtp proxyAddress 的云 MailUsers 阻止 MRS 移动背景。** 创建目标租户 MailUser 对象时，必须确保所有 SMTP 代理地址都属于目标租户组织。 如果 SMTP proxyAddress 在不属于本地租户的目标邮件用户上存在，则会阻止 MailUser 转换为邮箱。 这是因为我们的保证，邮箱对象只能从受租户) 授权的域发送邮件 (域： 
- 
   - 在使用 Azure AD Connect 从本地同步用户时，将本地 MailUser 对象设置为 ExternalEmailAddress 指向 laran@contoso) onmicrosoft.com 中 (存在邮箱的源租户， \. 并将 PrimarySMTPAddress 标记为驻留在目标租户 (Lara Newton@northwind 中的域。) \. com。 这些值将同步到租户，并设置适当的邮件用户并准备好迁移。 此处显示了一个示例对象。
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > EmailAddresses/proxyAddresses 数组中*不*存在*contoso. .onmicrosoft \. com*地址。

- **问题：将 "外部" 主 SMTP 地址的 MailUser 对象修改/重置为 "内部" 公司声明域**

   MailUser 对象是指向非本地邮箱的指针。 在跨租户邮箱迁移的情况下，我们使用 MailUser 对象表示源邮箱 (从目标组织的视角) 或源组织的 "角度") 中的目标邮箱 (。 MailUsers 将有一个 ExternalEmailAddress (targetAddress) 指向实际邮箱的 smtp 地址 (ProxyTest \@ fabrikam \. onmicrosoft.com) 和 primarySMTP 地址表示在目录中显示的邮箱用户的 smtp 地址。 有些组织会选择将主 SMTP 地址显示为外部 SMTP 地址，而不是作为本地租户 (（如 fabrikam.com 而不是 contoso.com) ）所拥有/验证的地址。  但是，一旦将 Exchange service plan 对象应用于 MailUser 通过许可操作，主 SMTP 地址将被修改为显示为由本地组织 (contoso.com) 验证的域。 有以下两个可能的原因：
   
   - 将任何 Exchange 服务计划应用于 MailUser 时，Azure AD 进程都将开始强制实施代理清理，以确保本地组织无法从其他租户发送邮件传出、欺骗或邮件。 如果本地组织未验证地址，则具有这些服务计划的收件人对象上的任何 SMTP 地址都将被删除。 与此示例中的情况一样，Fabikam \. com 域不会由 contoso \. onmicrosoft.com 租户验证，因此清理操作会删除该 fabrikam \. com 域。 如果您希望在迁移之前或迁移之后将这些外部域保留在 MailUser 上，则需要在移动完成后或移动之前更改迁移过程以去除许可证，以确保用户应用了预期的外部品牌。 您需要确保已正确授权邮箱对象不会影响邮件服务。<br/><br/>此处显示了用于删除 Contoso onmicrosoft.com 租户中的 MailUser 上的服务计划的示例脚本 \. 。

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       此处显示了所分配的 ServicePlans 集的结果。

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
 
       用户的 PrimarySMTPAddress 不再会再被清理。 Fabrikam.com 域不归 contoso.onmicrosoft.com 租户所有，并将作为目录中显示的主 SMTP 地址保留。

       下面是一个示例。

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - 如果 msExchRemoteRecipientType 设置为 8 (DeprovisionMailbox) ，对于迁移到目标租户的本地 MailUsers，Azure 中的代理清理逻辑将删除 nonowned 域，并将 primarySMTP 重置为拥有的域。 通过清除本地 MailUser 中的 msExchRemoteRecipientType，代理清理逻辑不再适用。 <br/><br>以下是包括 Exchange Online 的一组可能的服务计划。

   | 名称                                              |
   |---------------------------------------------------|
   | 高级电子数据展示存储 (500GB)                |
   | 客户密码箱                                  |
   | 数据丢失防护                              |
   | Exchange Enterprise CAL 服务 (EOP、DLP)        |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                               |
   | Exchange Online (计划 1)                           |
   | Exchange Online（计划 2）                          |
   | 适用于 Exchange Online 的 Exchange Online Archiving     |
   | 适用于 Exchange Server 的 Exchange Online Archiving     |
   | Exchange Online 非活动用户加载项              |
   | Exchange Online Kiosk                             |
   | Exchange Online 多地理位置功能                         |
   | Exchange Online 计划 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | 信息障碍                              |
   | 适用于 Office 365 的信息保护 - 高级版   |
   | 适用于 Office 365 的信息保护 - 标准版  |
   | 通过 MyAnalytics 的见解                           |
   | Microsoft 365 高级审核                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics（完整版）                      |
   | Office 365 高级电子数据展示                    |
   | Office 365 高级威胁防护（计划 1）    |
   | Office 365 高级威胁防护（计划 2）    |
   | Office 365 特权访问管理           |
   | Outlook Customer Manager                          |
   | Office 365 中的高级加密                  |
   || 
 
