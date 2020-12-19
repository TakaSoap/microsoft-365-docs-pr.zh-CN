---
title: 交叉租户邮箱迁移
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
ms.openlocfilehash: f151f02af695eb54eaf8f4f97936f4985fc7f8c0
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719198"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>跨租户邮箱迁移 (预览) 

以前，当 Exchange Online 租户需要将邮箱移动到同一 Exchange Online 服务中的另一个租户时，他们必须将其完全离开本地，然后载入新租户。 借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。 这无需离开和载入邮箱。

通常，在合并或资产重组期间，需要能够将用户和内容移动到新租户。 当目标租户管理员执行移动时，这称为拉取移动，类似于本地到云载入迁移。

跨租户 Exchange 邮箱移动由租户管理员完全自助服务，使用已知的接口，这些接口可以编写脚本到将用户转换到其新组织所需的较大工作流中。 管理员可以使用可通过移动邮箱管理角色使用的 `New-MigrationBatch` cmdlet 执行跨租户移动。 移动过程包括邮箱同步和最终完成期间租户授权检查。 
 
迁移的用户必须作为 MailUsers 存在于目标租户 Exchange Online 系统中，并带有特定属性标记才能启用跨租户移动。 对于未在目标租户中正确设置的用户，系统移动将失败。  

移动完成后，源系统邮箱将转换为 MailUser，并且目标地址 (显示为 Exchange) 中的 ExternalEmailAddress，并标记目标租户的路由地址。 此过程将旧版 MailUser 保留到源租户中，并允许共存和邮件路由一段时间。 当业务流程允许时，源租户可能会删除源 MailUser 或将其转换为邮件联系人。 

仅混合或云中的租户或两者的任意组合都支持跨租户 Exchange 邮箱迁移。

本文介绍跨租户邮箱移动的过程，并提供有关如何为内容移动准备源租户和目标租户的指导。  

## <a name="preparing-source-and-target-tenants"></a>准备源租户和目标租户

跨租户 Exchange 邮箱迁移功能需要跨租户迁移的授权和范围。 使用 Azure 企业应用程序和密钥保管库存储解决方案，租户管理员现在能够管理从一个租户到另一个租户的 Exchange Online 邮箱迁移的授权和范围。 跨租户邮箱移动支持邀请和同意模型，以在 Azure AD (Azure AD) 应用程序，用于在租户对之间进行身份验证。 还需要其他组件，如组织关系和迁移终结点。

本节不包含在目标目录中准备 MailUser 用户对象所需的特定步骤，也不包括提交迁移批处理的示例命令。 请参阅" [准备目标用户对象以迁移此信息](#prepare-target-user-objects-for-migration) "。

## <a name="prerequisites"></a>先决条件

跨租户邮箱移动功能需要 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) 建立特定于租户对的 Azure 应用程序，以安全存储和访问用于对邮箱从一个租户迁移到另一个租户进行身份验证和授权迁移的证书/密码，从而删除在租户之间共享证书/密码的任何要求。 

在启动之前，请确保你拥有运行部署脚本的必要权限，以便配置 Azure Key Vault、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。 通常，全局管理员有权执行所有配置步骤。

此外，在运行安装程序之前，源租户中需要启用邮件的安全组。 这些组用于将邮箱列表的范围从源租户 (有时称为资源) 租户移动到目标租户。 这允许源租户管理员限制或限定需要移动的特定邮箱集，以防止迁移非预期用户。 不支持嵌套组。

你还需要与受信任的合作伙伴公司通信 (将邮箱移动到其) 以获取其 Microsoft 365 租户 ID。 此租户 ID 用于"组织关系" `DomainName` 字段。

若要获取订阅的租户 ID，请登录到 Microsoft 365 管理中心并转到 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。 单击租户 ID 属性的复制图标以将其复制到剪贴板。

下面是该过程的工作方式。

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="邮箱迁移的租户准备。":::

[请参阅此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>准备租户

在高级别上，执行安装脚本时将执行以下配置操作。

准备目标租户：

1. 如果未提供现有 Azure 资源组，则使用 SCRIPT (创建一) 。
2. 如果未提供现有密钥保管库，则使用 SCRIPT (创建一) 。
3. 为 SCRIPT (Office 365 Exchange Online 邮箱迁移应用程序) 。
4. 如果指定了用于 (或现有证书) 一个新证书，以将密码 (SCRIPT) 。
5. 将创建一个新的 Azure AD 应用程序 (SCRIPT) 。
6. 证书/密码将上载到迁移应用程序 (SCRIPT) 。
7. 邮箱迁移权限分配给 SCRIPT (应用程序) 。
8. 部署脚本将暂停，直到目标管理员同意使用 SCRIPT 脚本 (自己的) 。
9. 目标租户管理员同意向应用程序授予的权限 (手动) 。
10. 组织关系将创建到目标租户 (SCRIPT) 。
11. 创建迁移终结点以将邮箱拉至 SCRIPT (目标) 。

准备源租户：

1. 源租户管理员接受来自手动迁移目标租户 (邮箱) 。
2. 源租户管理员在租户中创建一个启用邮件的安全组，以包含允许迁移应用程序在 MANUAL (移动的) 。
3. 创建与目标租户的组织关系，指定邮箱迁移应用程序应用于 OAuth 验证，以接受 SCRIPT (移动) 。

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>目标租户管理员的分步说明

1. 从 [gitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview)SetupCrossTenantRelationshipForTargetTenant.ps1下载目标租户安装程序的脚本。 
2. 将脚本 (SetupCrossTenantRelationshipForTargetTenant.ps1) 保存到要执行脚本的计算机。
3. 创建到 Exchange Online 目标租户的远程 PowerShell 连接。 同样，请确保你拥有运行部署脚本的必要权限，以便配置 Azure 密钥保管库存储和证书、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。
4. 将文件文件夹目录更改为脚本位置或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。
5. 运行具有以下参数和值的脚本。

    | 参数 | 值 | 必需或可选
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | 目标租户域，如 contoso \. onmicrosoft.com。 | 必需 |
    | -ResourceTenantDomain                       | 源租户域，例如 fabrikam \. onmicrosoft.com。 | 必需 |
    | -ResourceTenantAdminEmail                   | 源租户管理员的电子邮件地址。 这是将同意使用从目标管理员发送的邮箱迁移应用程序的源租户管理员。这是将接收应用程序的电子邮件邀请的管理员。 | 必需 |
    | -ResourceTenantId                           | 源租户组织 ID (GUID) 。 | 必需 |
    | -SubscriptionId                             | 用于创建资源的 Azure 订阅。 | 必需 |
    | -ResourceGroup                              | 包含或将包含密钥保管库的 Azure 资源组名称。 | 必需 |
    | -KeyVaultName                               | 将存储邮箱迁移应用程序证书/密码的 Azure Key Vault 实例。 | 必需 |
    | -CertificateName                            | 在密钥保管库中生成或搜索证书时证书名称。 | 必需 |
    | -CertificateSubject                         | Azure 密钥保管库证书主题名称，例如 CN=contoso_fabrikam。 | 必需 |
    | -ExistingApplicationId                      | 要用于已创建的邮件迁移应用程序。 | 可选 |
    | -AzureAppPermissions                        | 为邮箱迁移应用程序（如 Exchange 或 MSGraph (Exchange）授予移动邮箱所需的权限，MSGraph 用于使用此应用程序向资源租户邮箱发送同意链接) 。 | 必需 |
    | -UseAppAndCertGeneratedForSendingInvitation | 用于使用为迁移创建的应用程序的参数，用于向源租户管理员发送同意链接邀请。如果不存在，将提示目标管理员的凭据连接到 Azure 邀请管理器，并作为目标管理员发送邀请。 | 可选 |
    | -KeyVaultAuditStorageAccountName            | 存储密钥保管库审核日志的存储帐户。 | 可选 |
    | -KeyVaultAuditStorageResourceGroup          | 包含用于存储密钥保管库审核日志的存储帐户的资源组。 | 可选 |
    ||||

    >[!Note]
    > 请确保在运行脚本之前已安装 Azure AD PowerShell 模块。 有关安装 ![ 步骤， ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) 请参阅此处

6. 脚本将暂停，并要求您接受或同意在此过程期间创建的 Exchange 邮箱迁移应用程序。 下面是一个示例。

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. 远程 PowerShell 会话中将显示 URL。 复制为租户许可提供的链接，并将其粘贴到 Web 浏览器中。

8. 使用全局管理员凭据登录。 显示以下屏幕时，选择"接受 **"。**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="&quot;接受权限&quot;对话框":::

9. 切换回远程 PowerShell 会话并按 Enter 继续。

10. 该脚本将配置其余的设置对象。 下面是一个示例。

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

目标管理员设置现已完成！

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>源租户管理员的分步说明

1.  以目标管理员在设置过程中指定的 -ResourceTenantAdminEmail 登录邮箱。 从目标租户查找电子邮件邀请，然后选择" **开始"** 按钮。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="你已被邀请对话框":::

2. 选择 **"** 接受"接受邀请。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="接受权限的对话框":::

   > [!NOTE]
   > 如果未收到此电子邮件或找不到此电子邮件，则为目标租户管理员提供直接 URL，可提供给你接受邀请。 URL 应输入目标租户管理员的远程 PowerShell 会话的脚本中。

3. 在 Microsoft 365 管理中心或远程 PowerShell 会话中，创建一个或多个启用邮件的安全组，以控制目标租户允许的邮箱列表，以将 () 从源租户移动到目标租户。 无需提前填充此组，但必须至少提供一个组，以运行脚本 (安装) 。 不支持嵌套组。 

4. 从 gitHub SetupCrossTenantRelationshipForTargetResource.ps1下载源租户设置的脚本 [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ：. 

5. 使用 Exchange 管理员权限创建到源租户的远程 PowerShell 连接。 由于 Azure 应用程序创建过程，配置源租户（仅目标租户）不需要全局管理员权限。

6. 将目录更改为脚本位置或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。

7. 运行具有以下必需参数和值的脚本。

    | 参数 | 值 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 源租户为迁移范围内标识/邮箱创建的启用邮件的安全组。 |
    | -ResourceTenantDomain | 源租户域名，例如 fabrikam \. onmicrosoft.com。 |
    | -ApplicationId | Azure 应用程序 ID (用于) 的应用程序的 GUID 标识符。 可通过 Azure 门户获取的应用程序 ID (Azure AD、企业应用程序、应用名称、) ID 或包含在邀请电子邮件中。  |
    | -TargetTenantDomain | 目标租户域名，如 contoso \. onmicrosoft.com。 |
    | -TargetTenantId | 目标租户的租户 ID。 例如，contoso 租户的 Azure AD \. onmicrosoft.com ID。 |
    |||

    下面是一个示例。
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

源管理员设置现已完成！

### <a name="verify-setup"></a>验证设置

验证目标中的源租户和目标租户以及迁移终结点中的组织关系是否成功创建。

#### <a name="target-tenant"></a>目标租户

**组织关系**

验证已使用此命令创建和配置组织关系对象。

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
如以下示例所示：

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**迁移终结点**

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

**组织关系**

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

### <a name="move-mailboxes-back-to-the-original-source"></a>将邮箱移回原始源

如果需要将邮箱移回原始源租户，则需要在新的源租户和新目标租户中运行相同的步骤和脚本集。 将更新或追加现有组织关系对象，而不是重新创建该对象。

## <a name="prepare-target-user-objects-for-migration"></a>准备目标用户对象进行迁移

迁移的用户必须存在于目标租户和 Exchange Online 系统中 (作为 MailUsers) 使用特定属性进行标记才能启用跨租户移动。 对于未在目标租户中正确设置的用户，系统移动将失败。 以下部分详细介绍了目标租户的 MailUser 对象要求。

### <a name="prerequisites"></a>先决条件
  
必须确保在目标组织中设置以下对象和属性。  

1. 对于从源组织移动的任何邮箱，必须在目标组织中设置 MailUser 对象： 

   - 目标 MailUser 必须具有源邮箱中的这些属性或分配有新的 User 对象：
      - ExchangeGUID (源到目标) 流 – 邮箱 GUID 必须匹配。 如果目标对象上不存在移动过程，则移动过程将不会继续进行。 
      - ArchiveGUID (源到目标) 流 – 存档 GUID 必须匹配。 如果目标对象上不存在移动过程，则移动过程将不会继续进行。  (仅在源邮箱已启用存档时，才需要) 。 
      - LegacyExchangeDN (作为 proxyAddress， "x500： <LegacyExchangeDN> ") – LegacyExchangeDN 必须作为 x500： proxyAddress 存在于目标 MailUser 上。 如果目标对象上不存在移动过程，则移动过程将不会继续进行。 
      - UserPrincipalName – UPN 将符合用户的新标识或目标公司 (例如，user@northwindtraders.onmicrosoft.com) 。 
      - 主 SMTP 地址 – 主 SMTP 地址与用户的新公司地址 (例如，user@northwind.com) 。 
      - TargetAddress/ExternalEmailAddress – MailUser 将引用托管在源租户中的用户当前邮箱 (例如user@contoso.onmicrosoft.com) 。 分配此值时，请确认你已/正在分配 PrimarySMTPAddress，否则此值将设置会导致移动失败的 PrimarySMTPAddress。 
      - 无法将源邮箱中的旧版 smtp 代理地址添加到目标 MailUser。 例如，您无法在CONTOSO.COM租户对象中维护 MEU fabrikam.onmicrosoft.com) 。 域仅与一个 Azure AD 或 Exchange Online 租户关联。
 
     示例 **目标** MailUser 对象：
 
     | 属性             | 值                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       |  (FYDIBOHF23SPDLT) /cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500：/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     示例 **源** 邮箱对象：

     | 属性             | 值                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       |  (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - 其他属性可能已包含在 Exchange 混合写回中。 如果没有，应包含它们。 
   - msExchBlockedSendersHash – 将来自客户端的联机安全且阻止的发件人数据写回本地 Active Directory。
   - msExchSafeRecipientsHash – 将联机安全且阻止的发件人数据从客户端写回本地 Active Directory。
   - msExchSafeSendersHash – 将来自客户端的安全和阻止的发件人数据写回本地 Active Directory。

2. 如果源邮箱位于 LitigationHold 中，并且源邮箱"可恢复的项目"大小大于数据库默认 (30 GB) ，将不会继续移动，因为目标配额小于源邮箱大小。 您可以更新目标 MailUser 对象以将 ELC 邮箱标志从源环境转换到目标，这将触发目标系统将 MailUser 的配额扩展到 100 GB，从而允许移动到目标。 这些说明仅适用于运行 Azure AD Connect 的混合标识，因为标记 ELC 标志的命令不会向租户管理员公开。

    >[!Note]
    > 示例 – 就目前来说，无担保<br/>此脚本假定连接到源邮箱 (源值) 和目标本地 Active Directory (标记 ADUser 对象) 。 如果源已启用诉讼或单个项目恢复，请对目标帐户进行此项设置。  这会将目标帐户的垃圾站大小增加至 100 GB。

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. 非混合目标租户可以在迁移前修改 MailUsers 的"可恢复的项目"文件夹的配额，方法为运行以下命令以对 MailUser 对象启用诉讼保留，将配额增加至 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` GB： 请注意，这适用于混合租户。

4. 目标组织的用户必须通过适用于组织的适当 Exchange Online 订阅获得许可。 您可以在邮箱移动之前应用许可证，但仅在使用 ExchangeGUID 和代理地址正确设置目标 MailUser 之后。 在应用 ExchangeGUID 之前应用许可证将导致在目标组织中设置新的邮箱。 

    > [!Note]
    > 在邮箱或 MailUser 对象上应用许可证时，会擦除所有 SMTP 类型代理地址，以确保 Exchange EmailAddresses 数组中仅包含已验证的域。 

5. 必须确保目标 MailUser 之前没有与源 ExchangeGuid 不匹配的 ExchangeGuid。 如果目标 MEU 之前已获得 Exchange Online 许可并预配了邮箱，则可能会发生这种情况。 如果目标 MailUser 之前已授权或拥有与源 ExchangeGuid 不匹配的 ExchangeGuid，则需要清理云 MEU。 对于这些云 MEUS，你可以运行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 。  

    > [!Caution]
    > 此过程是不可逆的。 如果对象具有 softDeleted 邮箱，则在此时间点之后无法还原它。 但是，清除后，可以将正确的 ExchangeGuid 同步到目标对象，MRS 将源邮箱连接到新创建的目标邮箱。  (新参数上参考 EHLO 博客)   

    使用此命令查找以前是邮箱的对象。

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

跨租户 Exchange 邮箱迁移作为从目标租户启动的迁移批处理提交。 这类似于从 Exchange 内部部署迁移到 Microsoft 365 时，就地迁移批处理的运行方式。 

### <a name="create-migration-batches"></a>创建迁移批处理

下面是开始移动的示例迁移批处理 cmdlet。

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV 文件中的电子邮件地址必须是目标租户中指定的地址，而不是源租户中指定的电子邮件地址。

选择跨租户选项时，新 Exchange 管理中心也支持迁移批处理提交。

#### <a name="update-on-premises-mailusers"></a>更新本地 MailUsers

邮箱从源移动到目标之后，应确保使用新的 targetAddress 更新内部部署邮件用户（源和目标）。 在示例中，移动中使用的 targetDeliveryDomain **contoso.onmicrosoft.com。** 使用此 targetAddress 更新邮件用户。

## <a name="frequently-asked-questions"></a>常见问题解答

**移动后，是否需要更新源本地中的 RemoteMailbox？**

是，当源租户邮箱移动到目标租户时，应更新源本地用户 (RemoteRoutingAddress/ExternalEmailAddress) targetAddress。  虽然邮件路由可以跨具有不同 targetAddresses 的多个邮件用户执行引用，但邮件用户的忙/闲查找必须面向邮箱用户的位置。 忙/闲查找不会追踪多个重定向。 

**Teams 聊天文件夹内容是否跨租户迁移？**  

否，Teams 聊天文件夹内容不会跨租户迁移。  

**如何查看跨租户移动移动，而不是我的载入和载出移动？**

使用 `-flags` 参数。 下面是一个示例。

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**能否提供用于复制测试中使用的属性的示例脚本？**

> [!Note]
> 示例 – 就目前来说，无担保<br/>此脚本假定与源邮箱 (连接，以获取源值) 和目标本地 Active Directory 域服务 (，以标记 ADUser 对象) 。 如果源已启用诉讼或单个项目恢复，请对目标帐户进行此项设置。  这会将目标帐户的垃圾站大小增加至 100 GB。

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
**移动使用邮箱后如何访问第 1 天的 Outlook？**

由于只有一个租户可以拥有一个域，因此邮箱移动完成后，以前的主 SMTP 地址将不会与目标租户中的用户关联;仅与新租户关联的域。 Outlook 使用用户新的 UPN 对服务进行身份验证，Outlook 配置文件希望查找旧版主 SMTP 地址以匹配目标系统中邮箱。 由于旧地址不在目标系统中，Outlook 配置文件无法连接以查找新移动的邮箱。 

对于此初始部署，用户将需要使用新的 UPN 主 SMTP 地址重新生成其配置文件，并重新同步 OST 内容。 

> [!Note]
> 在批处理用户以完成时进行相应规划。 创建 Outlook 客户端配置文件以及将后续 OST 和 OAB 文件下载到客户端时，您需要考虑网络利用率和容量。 
 
**我需要成为哪些 Exchange RBAC 角色的成员来设置或完成跨租户移动？**
 
执行邮箱移动时，存在基于委派职责假设的角色矩阵。 目前，需要两个角色：  

- 第一个角色用于建立将内容移入或移出租户/组织边界的授权的一次设置任务。 由于将数据从组织控制中移出是所有公司的一个关键问题，因此，我们选择具有 OrgAdmin (分配的最高) 。 此角色必须更改或设置一个新的 OrganizationRelationship，用于定义远程组织的 -MailboxMoveCapability。 只有 OrgAdmin 可以更改 MailboxMoveCapability 设置，而 OrganizationRelationhip 上的其他属性也可由联合共享管理员管理。 
 
- 执行实际移动命令的角色可以委派给较低级别的函数。 "移动邮箱"角色分配有使用参数将邮箱移进组织或将邮箱移出 `-RemoteTenant` 组织的功能。  

**如何针对转换后的邮箱 (到 MailUser 转换) 上的 targetAddress (TargetDeliveryDomain) ？**
 
当通过匹配目标对象上的电子邮件地址 (proxyAddress) 转换为 MailUser 时，Exchange 邮箱使用 MRS 在原始源邮箱上创建 targetAddress。 此过程将接受传递到移动命令中的 -TargetDeliveryDomain 值，然后检查目标端上该域的匹配代理。 当我们找到匹配项时，匹配的 proxyAddress 将用于在转换的邮箱上设置 ExternalEmailAddress (targetAddress) ， (MailUser) 对象。
 
**邮箱权限如何转换？**

邮箱权限包括"代表发送"和"邮箱访问"： 

- 代表用户 (AD：publicDelegates) 存储具有用户邮箱代理访问权限的收件人的 DN。 此值存储在 Active Directory 中，当前不会作为邮箱转换的一部分移动。 如果源邮箱设置了 publicDelegates，则当 MEU 到邮箱的转换通过运行在目标环境中完成时，你需要在目标邮箱上重新标记 publicDelegates。 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 
 
- 当主体和代理都移动到目标系统时，邮箱中存储的邮箱权限将随邮箱一起移动。 例如，向用户TestUser_7租户中的邮箱TestUser_8 FullAccess SourceCompany.onmicrosoft.com。 在邮箱移动完成TargetCompany.onmicrosoft.com，在目标目录中设置相同的权限。 在源租户和目标租户TestUser_7 *Get-MailboxPermission* 的示例如下所示。 Exchange cmdlet 相应地以源和目标作为前缀。 
 
下面是移动前邮箱权限输出的示例。 

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
 
> [!Note]
> 不支持跨租户邮箱和日历权限。 必须将主体和代理组织到合并移动批处理中，以便同时从源租户转换这些连接邮箱。 

**应向目标 MailUser 代理地址添加哪些 X500 代理以启用迁移？**  

跨租户邮箱迁移要求将源邮箱对象的 LegacyExchangeDN 值标记为目标 MailUser 对象的 x500 电子邮件地址。  

示例：  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> 除了此 X500 代理之外，还需要将源邮箱的所有 X500 代理复制到目标中的邮箱。  

**Azure 密钥保管库是否是必需的，以及何时进行交易？**  

是的，Azure 订阅需要使用密钥保管库来存储证书以授权迁移。 与使用用户名和密码向源&登录迁移不同，跨租户邮箱迁移使用 OAuth 和此证书作为密码/凭据。 必须在所有邮箱迁移中维护对密钥保管库的访问权限，因为密钥保管库在迁移开始时和结束时访问一次，在增量同步期间每 24 小时访问一次。 你可以在此处查看 AKV 成本 [计算详细信息]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)。  

**您是否对批处理有任何建议？**  

每批不要超过 2000 个邮箱。 强烈建议在截止日期前两周提交批处理，因为同步期间对最终用户没有影响。如果需要超过 50，000 个邮箱数量的指南，可以在以下位置联系工程反馈crosstenantmigrationpreview@service.microsoft.com。

**如果我将服务加密与客户密钥一同使用，该做什么？**

邮箱将在移动之前解密。 如果仍然需要客户密钥，请确保在目标租户中配置客户密钥。 有关详细信息 [，](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) 请参阅此处。  

**估计的迁移时间是什么？**

为了帮助您规划迁移，此处的表显示了有关[](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)何时预期批量邮箱迁移或单个迁移完成的准则。 这些估计基于以前客户迁移的数据分析。 由于每个环境都是唯一的，因此确切的迁移速度可能会有所不同。  

请记住，此功能当前处于预览阶段，SLA 及任何适用的服务级别不适用于此功能预览状态期间的任何性能或可用性问题。

## <a name="known-issues"></a>已知问题  

-  **问题：无法迁移自动展开的存档。** 跨租户迁移功能支持迁移特定用户的主邮箱和存档邮箱。 但是，如果源中的用户具有自动展开的存档，这意味着多个存档邮箱，则此功能无法迁移其他存档。

- **问题：具有非拥有的 smtp 代理Address 块 MRS 的云 MailUsers 将移动后台。** 创建目标租户 MailUser 对象时，必须确保所有 SMTP 代理地址都属于目标租户组织。 如果不属于本地租户的目标邮件用户上存在 SMTP 代理地址，则阻止将 MailUser 转换为邮箱。 这是因为我们保证邮箱对象只能从租户对租户声明的域具有权威性 (域发送邮件) ： 

   - 使用 Azure AD Connect 从本地同步用户时，使用指向邮箱所在的源租户的 ExternalEmailAddress 预配本地 MailUser 对象 (laran@contoso.onmicrosoft.com) 并且将 PrimarySMTPAddress 标记为驻留在目标租户 (Lara.Newton@northwind.com) 中的域。 这些值将同步到租户，并设置相应的邮件用户并准备迁移。 此处显示了一个示例对象。
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > EmailAddresses /proxyAddresses *数组* 中不存在contoso.onmicrosoft.com地址。 

- **问题：具有"外部"主 SMTP 地址的 MailUser 对象被修改/重置为"内部"公司声明的域**

   MailUser 对象是指向非本地邮箱的指针。 对于跨租户邮箱迁移，从目标组织的角度来看，我们使用 MailUser 对象来表示源邮箱 (，或者从源组织的角度) 目标邮箱 (表示) 。 MailUsers 将具有一个 ExternalEmailAddress (targetAddress) ，该地址指向实际邮箱 (ProxyTest@fabrikam.onmicrosoft.com) 的 smtp 地址和表示目录中邮箱用户的显示 SMTP 地址的 primarySMTP 地址。 某些组织选择将主 SMTP 地址显示为外部 SMTP 地址，而不是本地租户拥有/验证的地址 (例如 fabrikam.com 而不是contoso.com) 。  但是，通过许可操作将 Exchange 服务计划对象应用于 MailUser 后，主 SMTP 地址将修改为由本地组织验证的 (contoso.com) 。 有两个潜在原因：
   
   - 当任何 Exchange 服务计划应用于 MailUser 时，Azure AD 进程开始强制执行代理清理，以确保本地组织无法从另一个租户发送邮件、欺骗或邮件。 如果本地组织未验证该地址，将删除具有这些服务计划的收件人对象上的任何 SMTP 地址。 与示例中的情况一样，Fabikam.com租户不验证 contoso.onmicrosoft.com 域，因此清理会删除该fabrikam.com域。 如果希望在迁移之前或迁移后在 MailUser 上保留这些外部域，则需要更改迁移过程，以在移动完成后或移动之前去除许可证，以确保用户应用了预期的外部品牌。 您需要确保邮箱对象已正确许可，不会影响邮件服务。<br/><br/>此处显示了用于删除邮件租户中 MailUser Contoso.onmicrosoft.com的示例脚本。

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
 
       用户的 PrimarySMTPAddress 不再被清理。 fabrikam.com域不归 contoso.onmicrosoft.com所有，并且将保留为目录中显示的主 SMTP 地址。

       下面是一个示例。

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - 当 msExchRemoteRecipientType 设置为 8 (DeprovisionMailbox) 时，对于迁移到目标租户的本地 MailUsers，Azure 中的代理清理逻辑将删除非域，将 primarySMTP 重置为拥有域。 通过清除本地 MailUser 中的 msExchRemoteRecipientType，代理清理逻辑将不再适用。 <br/><br>以下是包括 Exchange Online 的完整服务计划集。

   | 名称                                              |
   |---------------------------------------------------|
   | 高级电子数据展示存储 (500GB)                |
   | 客户密码箱                                  |
   | 数据丢失防护                              |
   | Exchange Enterprise CAL Services (EOP、DLP)        |
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
   | 信息屏障                              |
   | 适用于 Office 365 的信息保护 - 高级版   |
   | 适用于 Office 365 的信息保护 - 标准版  |
   | MyAnalytics 的见解                           |
   | Microsoft 365 高级审核                   |
   | Microsoft Bookings                                |
   | Microsoft 商业中心                         |
   | Microsoft MyAnalytics（完整版）                      |
   | Office 365 高级电子数据展示                    |
   | Microsoft Defender for Office 365 (计划 1)     |
   | Microsoft Defender for Office 365 (计划 2)     |
   | Office 365 特权访问管理           |
   | Office 365 中的高级加密                  |
    
