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
ms.openlocfilehash: 1e2624fea7a93013e4b4de2dd4ede4144000f075
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073079"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="305a6-103">跨租户邮箱迁移 (预览) </span><span class="sxs-lookup"><span data-stu-id="305a6-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="305a6-104">以前，当 Exchange Online 租户需要将邮箱移动到同一个 Exchange Online 服务中的另一个租户时，他们必须完全将其分离到本地，然后再将其集成到新租户。</span><span class="sxs-lookup"><span data-stu-id="305a6-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="305a6-105">使用新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在其本地系统中具有最少基础结构依赖关系的租户之间移动邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="305a6-106">这就消除了分离和板载邮箱的需求。</span><span class="sxs-lookup"><span data-stu-id="305a6-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="305a6-107">通常情况下，在合并或 divestitures 过程中，您需要能够将用户和内容移动到新的租户中。</span><span class="sxs-lookup"><span data-stu-id="305a6-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="305a6-108">当目标租户管理员执行移动时，它称为 "拉" 移动，类似于内部部署到云载入迁移。</span><span class="sxs-lookup"><span data-stu-id="305a6-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="305a6-109">跨租户 Exchange 邮箱移动由租户管理员完全自行维护，使用可编写为将用户转换为其新组织所需的更大工作流的已知接口。</span><span class="sxs-lookup"><span data-stu-id="305a6-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="305a6-110">管理员可以使用 `New-MigrationBatch` 通过移动邮箱管理角色提供的 cmdlet 来执行跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="305a6-111">移动过程包括在邮箱同步和最终完成期间的租户授权检查。</span><span class="sxs-lookup"><span data-stu-id="305a6-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="305a6-112">迁移的用户必须以 MailUsers 形式存在于目标租户 Exchange Online 系统中，并标记有特定属性以启用跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="305a6-113">对于在目标租户中未正确设置的用户，系统将发生故障移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="305a6-114">移动完成后，源系统邮箱将转换为 MailUser，并且在 Exchange) 中显示为 ExternalEmailAddress 的 targetAddress (将标记为与目标租户的路由地址。</span><span class="sxs-lookup"><span data-stu-id="305a6-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="305a6-115">此过程会将旧版 MailUser 保留在源租户中，并允许存在一段共存和邮件路由。</span><span class="sxs-lookup"><span data-stu-id="305a6-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="305a6-116">当业务流程允许时，源租户可能会删除源 MailUser 或将其转换为邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="305a6-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="305a6-117">仅支持混合或云中的租户的跨租户 Exchange 邮箱迁移，或二者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="305a6-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="305a6-118">本文介绍跨租户邮箱移动的过程，并提供有关如何为内容移动准备源和目标租户的指南。</span><span class="sxs-lookup"><span data-stu-id="305a6-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="305a6-119">准备源和目标租户</span><span class="sxs-lookup"><span data-stu-id="305a6-119">Preparing source and target tenants</span></span>

<span data-ttu-id="305a6-120">跨租户 Exchange 邮箱迁移功能需要针对跨租户迁移进行授权和作用域。</span><span class="sxs-lookup"><span data-stu-id="305a6-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="305a6-121">通过使用 Azure 企业应用程序和密钥存储库存储解决方案，租户管理员现在可以管理从一个租户到另一个租户的 Exchange Online 邮箱迁移的授权和作用域。</span><span class="sxs-lookup"><span data-stu-id="305a6-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="305a6-122">跨租户邮箱移动支持邀请和同意模型，以在租户对之间进行身份验证 (Azure AD) 应用程序建立 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="305a6-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="305a6-123">此外，还需要其他组件（如组织关系和迁移终结点）。</span><span class="sxs-lookup"><span data-stu-id="305a6-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="305a6-124">本节不包括在目标目录中准备 MailUser 用户对象所需的特定步骤，也不包括用于提交迁移批处理的示例命令。</span><span class="sxs-lookup"><span data-stu-id="305a6-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="305a6-125">有关此信息，请参阅 [准备目标用户对象以供迁移](#prepare-target-user-objects-for-migration) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="305a6-126">先决条件</span><span class="sxs-lookup"><span data-stu-id="305a6-126">Prerequisites</span></span>

<span data-ttu-id="305a6-127">跨租户邮箱移动功能要求 [Azure 密钥保管库](https://docs.microsoft.com/azure/key-vault/basic-concepts) 建立租户对特定的 azure 应用程序，以安全地存储和访问用于对从一个租户到另一个租户的邮箱迁移进行身份验证和授权的证书/机密，从而消除了在租户之间共享证书/密码的任何要求。</span><span class="sxs-lookup"><span data-stu-id="305a6-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="305a6-128">在开始之前，请确保您具有运行部署脚本的必要权限，以便配置 Azure Key Vault、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。</span><span class="sxs-lookup"><span data-stu-id="305a6-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="305a6-129">通常，全局管理员有权执行所有配置步骤。</span><span class="sxs-lookup"><span data-stu-id="305a6-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="305a6-130">此外，还需要在运行安装程序之前在源租户中启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="305a6-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="305a6-131">这些组用于对可以从源 (（有时称为 "资源) 租户"）移动到目标租户的邮箱列表进行作用域。</span><span class="sxs-lookup"><span data-stu-id="305a6-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="305a6-132">这样，源租户管理员可以限制或限定需要移动的特定邮箱集，从而防止迁移意外的用户。</span><span class="sxs-lookup"><span data-stu-id="305a6-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="305a6-133">嵌套组不受支持。</span><span class="sxs-lookup"><span data-stu-id="305a6-133">Nested groups are not supported.</span></span>

<span data-ttu-id="305a6-134">您还需要与您要将邮箱移动到的受信任合作伙伴公司 (进行通信，) 获取其 Microsoft 365 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="305a6-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="305a6-135">在 "组织" 关系字段中使用此租户 ID `DomainName` 。</span><span class="sxs-lookup"><span data-stu-id="305a6-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="305a6-136">若要获取订阅的租户 ID，请登录到 Microsoft 365 管理中心并转到 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="305a6-137">单击 "租户 ID" 属性的 "复制" 图标，将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="305a6-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="305a6-138">下面展示了此过程的工作原理。</span><span class="sxs-lookup"><span data-stu-id="305a6-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="邮箱迁移的租户准备。":::

<span data-ttu-id="305a6-140">[查看此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。</span><span class="sxs-lookup"><span data-stu-id="305a6-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="305a6-141">准备租户</span><span class="sxs-lookup"><span data-stu-id="305a6-141">Prepare tenants</span></span>

<span data-ttu-id="305a6-142">在高级别上执行安装脚本时，会进行以下配置操作。</span><span class="sxs-lookup"><span data-stu-id="305a6-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="305a6-143">准备目标租户：</span><span class="sxs-lookup"><span data-stu-id="305a6-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="305a6-144">如果未提供现有 Azure 资源组，则会在脚本)  (创建一个新的 Azure 资源组。</span><span class="sxs-lookup"><span data-stu-id="305a6-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="305a6-145">如果未提供现有的密钥存储库，则会在脚本)  (创建一个新的密钥存储库。</span><span class="sxs-lookup"><span data-stu-id="305a6-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="305a6-146">将为 Office 365 Exchange Online 邮箱迁移应用程序 (脚本) 创建新的访问策略。</span><span class="sxs-lookup"><span data-stu-id="305a6-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="305a6-147">如果指定) 将机密保存到迁移应用程序 (SCRIPT) 中，则 (或现有证书中创建一个新证书。</span><span class="sxs-lookup"><span data-stu-id="305a6-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="305a6-148"> (脚本) 创建新的 Azure AD 应用程序。</span><span class="sxs-lookup"><span data-stu-id="305a6-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="305a6-149">证书/机密将上载到迁移应用程序 (脚本) 中。</span><span class="sxs-lookup"><span data-stu-id="305a6-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="305a6-150">邮箱迁移权限分配给应用程序 (脚本) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="305a6-151">部署脚本将暂停，直至目标管理员将同意为自己的应用程序 (脚本) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="305a6-152">目标租户管理员同意 (手动) 向应用程序授予的权限。</span><span class="sxs-lookup"><span data-stu-id="305a6-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="305a6-153">将为目标租户 (脚本) 创建一个组织关系。</span><span class="sxs-lookup"><span data-stu-id="305a6-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="305a6-154">创建迁移终结点以将邮箱拉入目标租户 (脚本) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="305a6-155">准备源租户：</span><span class="sxs-lookup"><span data-stu-id="305a6-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="305a6-156">源租户管理员接受来自目标租户 (手动) 的邮箱迁移应用程序邀请的许可。</span><span class="sxs-lookup"><span data-stu-id="305a6-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="305a6-157">源租户管理员在其租户中创建已启用邮件的安全组，以包含迁移应用程序允许移动的邮箱列表 (手动) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="305a6-158">将为指定邮箱迁移应用程序的目标租户创建一个组织关系，以便将移动请求 (脚本) 中的 "OAuth 验证"。</span><span class="sxs-lookup"><span data-stu-id="305a6-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="305a6-159">针对目标租户管理员的分步说明</span><span class="sxs-lookup"><span data-stu-id="305a6-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="305a6-160">从 [GitHub 存储库](https://github.com/microsoft/cross-tenant/releases/tag/Preview)中下载目标租户安装程序的 SetupCrossTenantRelationshipForTargetTenant.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="305a6-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="305a6-161">将脚本 ( # A0) 保存到将在其中执行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="305a6-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="305a6-162">创建与 Exchange Online 目标租户的远程 PowerShell 连接。</span><span class="sxs-lookup"><span data-stu-id="305a6-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="305a6-163">此外，请确保您具有运行部署脚本的必要权限，以便配置 Azure Key Vault 存储和证书、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。</span><span class="sxs-lookup"><span data-stu-id="305a6-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="305a6-164">将文件文件夹目录更改为脚本位置，或验证脚本当前是否已保存到远程 PowerShell 会话中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="305a6-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="305a6-165">使用以下参数和值运行脚本。</span><span class="sxs-lookup"><span data-stu-id="305a6-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="305a6-166">参数</span><span class="sxs-lookup"><span data-stu-id="305a6-166">Parameter</span></span> | <span data-ttu-id="305a6-167">值</span><span class="sxs-lookup"><span data-stu-id="305a6-167">Value</span></span> | <span data-ttu-id="305a6-168">必需或可选</span><span class="sxs-lookup"><span data-stu-id="305a6-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="305a6-169">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="305a6-169">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="305a6-170">源租户域，如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="305a6-170">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="305a6-171">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-171">Required</span></span> |
    | <span data-ttu-id="305a6-172">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="305a6-172">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="305a6-173">源租户管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="305a6-173">Source tenant admin’s email address.</span></span> <span data-ttu-id="305a6-174">这是将同意使用从目标管理员发送的邮箱迁移应用程序的源租户管理员。这是将接收应用程序的电子邮件邀请的管理员。</span><span class="sxs-lookup"><span data-stu-id="305a6-174">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="305a6-175">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-175">Required</span></span> |
    | <span data-ttu-id="305a6-176">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="305a6-176">-TargetTenantDomain</span></span>                         | <span data-ttu-id="305a6-177">目标租户域，如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="305a6-177">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="305a6-178">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-178">Required</span></span> |
    | <span data-ttu-id="305a6-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="305a6-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="305a6-180">源租户组织 ID (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="305a6-181">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-181">Required</span></span> |
    | <span data-ttu-id="305a6-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="305a6-182">-SubscriptionId</span></span>                             | <span data-ttu-id="305a6-183">用于创建资源的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="305a6-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="305a6-184">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-184">Required</span></span> |
    | <span data-ttu-id="305a6-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="305a6-185">-ResourceGroup</span></span>                              | <span data-ttu-id="305a6-186">包含或将包含密钥保管库的 Azure 资源组名称。</span><span class="sxs-lookup"><span data-stu-id="305a6-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="305a6-187">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-187">Required</span></span> |
    | <span data-ttu-id="305a6-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="305a6-188">-KeyVaultName</span></span>                               | <span data-ttu-id="305a6-189">将存储邮箱迁移应用程序证书/机密的 Azure Key Vault 实例。</span><span class="sxs-lookup"><span data-stu-id="305a6-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="305a6-190">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-190">Required</span></span> |
    | <span data-ttu-id="305a6-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="305a6-191">-CertificateName</span></span>                            | <span data-ttu-id="305a6-192">在密钥保管库中生成或搜索证书时的证书名称。</span><span class="sxs-lookup"><span data-stu-id="305a6-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="305a6-193">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-193">Required</span></span> |
    | <span data-ttu-id="305a6-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="305a6-194">-CertificateSubject</span></span>                         | <span data-ttu-id="305a6-195">Azure Key Vault 证书使用者名称，例如 CN = contoso_fabrikam。</span><span class="sxs-lookup"><span data-stu-id="305a6-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="305a6-196">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-196">Required</span></span> |
    | <span data-ttu-id="305a6-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="305a6-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="305a6-198">要使用的邮件迁移应用程序（如果已经创建了一个）。</span><span class="sxs-lookup"><span data-stu-id="305a6-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="305a6-199">可选</span><span class="sxs-lookup"><span data-stu-id="305a6-199">Optional</span></span> |
    | <span data-ttu-id="305a6-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="305a6-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="305a6-201">授予邮箱迁移应用程序所需的权限，例如 Exchange 或 MSGraph (Exchange 以移动邮箱，MSGraph 使用此应用程序将同意链接邀请发送到资源租户) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="305a6-202">必需</span><span class="sxs-lookup"><span data-stu-id="305a6-202">Required</span></span> |
    | <span data-ttu-id="305a6-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="305a6-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="305a6-204">用于使用为迁移创建的应用程序的参数，用于向源租户管理员发送同意链接邀请。如果不存在，则会提示目标管理员的凭据连接到 Azure 邀请管理器，并将邀请作为目标管理员发送。</span><span class="sxs-lookup"><span data-stu-id="305a6-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="305a6-205">可选</span><span class="sxs-lookup"><span data-stu-id="305a6-205">Optional</span></span> |
    | <span data-ttu-id="305a6-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="305a6-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="305a6-207">将存储主要保管库审核日志的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="305a6-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="305a6-208">可选</span><span class="sxs-lookup"><span data-stu-id="305a6-208">Optional</span></span> |
    | <span data-ttu-id="305a6-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="305a6-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="305a6-210">包含存储密钥保管库审核日志的存储帐户的资源组。</span><span class="sxs-lookup"><span data-stu-id="305a6-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="305a6-211">可选</span><span class="sxs-lookup"><span data-stu-id="305a6-211">Optional</span></span> |
    ||||

6. <span data-ttu-id="305a6-212">该脚本将暂停，并要求您接受或同意在此过程中创建的 Exchange 邮箱迁移应用程序。</span><span class="sxs-lookup"><span data-stu-id="305a6-212">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="305a6-213">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-213">Here is an example.</span></span>

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

7. <span data-ttu-id="305a6-214">将在远程 PowerShell 会话中显示一个 URL。</span><span class="sxs-lookup"><span data-stu-id="305a6-214">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="305a6-215">复制为您的租户同意提供的链接，并将其粘贴到 Web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="305a6-215">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="305a6-216">使用全局管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="305a6-216">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="305a6-217">出现以下屏幕时，选择 " **接受** "。</span><span class="sxs-lookup"><span data-stu-id="305a6-217">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="_OL_QUOTE_PLACEHOLDER_接受权限_OL_QUOTE_PLACEHOLDER_ 对话框":::
    
9. <span data-ttu-id="305a6-219">切换回远程 PowerShell 会话并按 Enter 继续。</span><span class="sxs-lookup"><span data-stu-id="305a6-219">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="305a6-220">脚本将配置其余的安装程序对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-220">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="305a6-221">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-221">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="305a6-222">目标管理员设置现已完成！</span><span class="sxs-lookup"><span data-stu-id="305a6-222">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="305a6-223">有关源租户管理员的分步说明</span><span class="sxs-lookup"><span data-stu-id="305a6-223">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="305a6-224">在设置过程中，以由目标管理员指定的-ResourceTenantAdminEmail 的身份登录邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-224">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="305a6-225">查找来自目标租户的电子邮件邀请，然后选择 " **开始入门** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="305a6-225">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="_OL_QUOTE_PLACEHOLDER_已邀请您_OL_QUOTE_PLACEHOLDER_ 对话框":::

2. <span data-ttu-id="305a6-227">选择 " **接受** " 接受邀请。</span><span class="sxs-lookup"><span data-stu-id="305a6-227">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="接受权限的对话框":::

   > [!NOTE]
   > <span data-ttu-id="305a6-229">如果你未收到此电子邮件或找不到此电子邮件，则会向目标租户管理员提供一个直接 URL，以接受邀请。</span><span class="sxs-lookup"><span data-stu-id="305a6-229">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="305a6-230">URL 应在目标租户管理员的远程 PowerShell 会话的脚本中。</span><span class="sxs-lookup"><span data-stu-id="305a6-230">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="305a6-231">在 Microsoft 365 管理中心或远程 PowerShell 会话中，创建一个或多个已启用邮件的安全组以控制目标租户允许的邮箱列表，以将源租户中的 (移动) 从源租户推送到目标租户。</span><span class="sxs-lookup"><span data-stu-id="305a6-231">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="305a6-232">您无需提前填充此组，但必须至少提供一个组，才能运行 "安装步骤" (脚本) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-232">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="305a6-233">不支持嵌套组。</span><span class="sxs-lookup"><span data-stu-id="305a6-233">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="305a6-234">在 [此处](https://github.com/microsoft/cross-tenant/releases/tag/Preview)从 GitHub 存储库中下载源租户安装程序的 SetupCrossTenantRelationshipForTargetResource.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="305a6-234">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="305a6-235">使用 Exchange 管理员权限创建与源租户的远程 PowerShell 连接。</span><span class="sxs-lookup"><span data-stu-id="305a6-235">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="305a6-236">由于 Azure 应用程序创建过程，不需要全局管理员权限来配置源租户（仅限目标租户）。</span><span class="sxs-lookup"><span data-stu-id="305a6-236">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="305a6-237">将目录更改为脚本位置，或验证脚本当前是否已保存到远程 PowerShell 会话中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="305a6-237">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="305a6-238">运行带有以下必需参数和值的脚本。</span><span class="sxs-lookup"><span data-stu-id="305a6-238">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="305a6-239">参数</span><span class="sxs-lookup"><span data-stu-id="305a6-239">Parameter</span></span> | <span data-ttu-id="305a6-240">值</span><span class="sxs-lookup"><span data-stu-id="305a6-240">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="305a6-241">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="305a6-241">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="305a6-242">由源租户为在迁移范围内的标识/邮箱创建的已启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="305a6-242">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="305a6-243">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="305a6-243">-ResourceTenantDomain</span></span> | <span data-ttu-id="305a6-244">源租户域名，如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="305a6-244">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="305a6-245">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="305a6-245">-TargetTenantDomain</span></span> | <span data-ttu-id="305a6-246">目标租户域名，如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="305a6-246">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="305a6-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="305a6-247">-ApplicationId</span></span> | <span data-ttu-id="305a6-248">用于迁移的应用程序的 Azure 应用程序 ID (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="305a6-249">通过 Azure 门户提供的应用程序 ID (Azure AD、企业应用程序、应用名称、应用程序 ID) 或包含在邀请电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="305a6-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="305a6-250">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="305a6-250">-TargetTenantId</span></span> | <span data-ttu-id="305a6-251">目标租户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="305a6-251">Tenant ID of the target tenant.</span></span> <span data-ttu-id="305a6-252">例如，contoso onmicrosoft.com 租户的 Azure AD 租户 ID \. 。</span><span class="sxs-lookup"><span data-stu-id="305a6-252">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="305a6-253">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-253">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="305a6-254">源管理员设置现已完成！</span><span class="sxs-lookup"><span data-stu-id="305a6-254">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="305a6-255">验证安装程序</span><span class="sxs-lookup"><span data-stu-id="305a6-255">Verify setup</span></span>

<span data-ttu-id="305a6-256">验证是否成功创建了目标中的源租户和目标租户以及迁移终结点中的组织关系。</span><span class="sxs-lookup"><span data-stu-id="305a6-256">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="305a6-257">目标租户</span><span class="sxs-lookup"><span data-stu-id="305a6-257">Target tenant</span></span>

<span data-ttu-id="305a6-258">**组织关系**</span><span class="sxs-lookup"><span data-stu-id="305a6-258">**Organization relationship**</span></span>

<span data-ttu-id="305a6-259">验证是否已使用此命令创建并配置了组织关系对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-259">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="305a6-260">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="305a6-260">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="305a6-261">**迁移终结点**</span><span class="sxs-lookup"><span data-stu-id="305a6-261">**Migration endpoint**</span></span>

<span data-ttu-id="305a6-262">验证是否已使用此命令创建并配置迁移终结点对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-262">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="305a6-263">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-263">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="305a6-264">源租户</span><span class="sxs-lookup"><span data-stu-id="305a6-264">Source tenant</span></span>

<span data-ttu-id="305a6-265">**组织关系**</span><span class="sxs-lookup"><span data-stu-id="305a6-265">**Organization relationship**</span></span>

<span data-ttu-id="305a6-266">验证是否已使用此命令创建并配置了组织关系对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-266">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="305a6-267">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-267">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="305a6-268">将邮箱移回原始源</span><span class="sxs-lookup"><span data-stu-id="305a6-268">Move mailboxes back to the original source</span></span>

<span data-ttu-id="305a6-269">如果要将邮箱移回原始源租户，则需要在新的源和新的目标租户中运行相同的一组步骤和脚本。</span><span class="sxs-lookup"><span data-stu-id="305a6-269">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="305a6-270">现有的组织关系对象将被更新或追加，而不是重新创建。</span><span class="sxs-lookup"><span data-stu-id="305a6-270">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="305a6-271">为迁移准备目标用户对象</span><span class="sxs-lookup"><span data-stu-id="305a6-271">Prepare target user objects for migration</span></span>

<span data-ttu-id="305a6-272">迁移的用户必须在目标租户和 Exchange Online 系统中存在 (作为 MailUsers) 标有特定属性以启用跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-272">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="305a6-273">对于在目标租户中未正确设置的用户，系统将发生故障移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-273">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="305a6-274">以下部分详细介绍了目标租户的 MailUser 对象要求。</span><span class="sxs-lookup"><span data-stu-id="305a6-274">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="305a6-275">先决条件</span><span class="sxs-lookup"><span data-stu-id="305a6-275">Prerequisites</span></span>
  
<span data-ttu-id="305a6-276">您必须确保在目标组织中设置以下对象和属性。</span><span class="sxs-lookup"><span data-stu-id="305a6-276">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="305a6-277">对于从源组织移动的任何邮箱，必须在目标组织中预配 MailUser 对象：</span><span class="sxs-lookup"><span data-stu-id="305a6-277">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="305a6-278">目标 MailUser 必须包含源邮箱中的这些属性，或使用新的 User 对象分配这些属性：</span><span class="sxs-lookup"><span data-stu-id="305a6-278">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="305a6-279">ExchangeGUID (从源到目标) 的直接流–邮箱 GUID 必须匹配。</span><span class="sxs-lookup"><span data-stu-id="305a6-279">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="305a6-280">如果目标对象上不存在，则移动过程不会继续。</span><span class="sxs-lookup"><span data-stu-id="305a6-280">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="305a6-281">ArchiveGUID (从源到目标) 的直接流–存档 GUID 必须匹配。</span><span class="sxs-lookup"><span data-stu-id="305a6-281">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="305a6-282">如果目标对象上不存在，则移动过程不会继续。</span><span class="sxs-lookup"><span data-stu-id="305a6-282">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="305a6-283"> (仅当源邮箱已启用存档) 时才需要这样做。</span><span class="sxs-lookup"><span data-stu-id="305a6-283">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="305a6-284">LegacyExchangeDN (flow as proxyAddress，"x500： <LegacyExchangeDN> " ) – LegacyExchangeDN 必须在目标 MailUser 上以 x500： proxyAddress 的形式存在。</span><span class="sxs-lookup"><span data-stu-id="305a6-284">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="305a6-285">如果目标对象上不存在，则移动进程不会继续。</span><span class="sxs-lookup"><span data-stu-id="305a6-285">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="305a6-286">UserPrincipalName – UPN 将与用户的新标识或目标公司 (例如，user@northwindtraders.onmicrosoft.com) 相一致。</span><span class="sxs-lookup"><span data-stu-id="305a6-286">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="305a6-287">主 SMTPAddress –主 SMTP 地址将与用户的新公司 (例如，user@northwind.com) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-287">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="305a6-288">TargetAddress/ExternalEmailAddress – MailUser 将引用在源租户 (中托管的用户的当前邮箱，例如 user@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-288">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="305a6-289">在分配此值时，请验证您是否具有/也分配了 PrimarySMTPAddress，否则此值将设置将导致移动失败的 PrimarySMTPAddress。</span><span class="sxs-lookup"><span data-stu-id="305a6-289">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="305a6-290">您不能将旧 smtp 代理地址从源邮箱添加到目标 MailUser。</span><span class="sxs-lookup"><span data-stu-id="305a6-290">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="305a6-291">例如，您无法在 fabrikam.onmicrosoft.com 租户对象) 中的 MEU 上维护 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="305a6-291">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="305a6-292">域仅与一个 Azure AD 或 Exchange Online 租户相关联。</span><span class="sxs-lookup"><span data-stu-id="305a6-292">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="305a6-293">**目标** MailUser 对象示例：</span><span class="sxs-lookup"><span data-stu-id="305a6-293">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="305a6-294">属性</span><span class="sxs-lookup"><span data-stu-id="305a6-294">Attribute</span></span>             | <span data-ttu-id="305a6-295">值</span><span class="sxs-lookup"><span data-stu-id="305a6-295">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="305a6-296">Alias</span><span class="sxs-lookup"><span data-stu-id="305a6-296">Alias</span></span>                 | <span data-ttu-id="305a6-297">LaraN</span><span class="sxs-lookup"><span data-stu-id="305a6-297">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="305a6-298">RecipientType</span><span class="sxs-lookup"><span data-stu-id="305a6-298">RecipientType</span></span>         | <span data-ttu-id="305a6-299">MailUser</span><span class="sxs-lookup"><span data-stu-id="305a6-299">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="305a6-300">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="305a6-300">RecipientTypeDetails</span></span>  | <span data-ttu-id="305a6-301">MailUser</span><span class="sxs-lookup"><span data-stu-id="305a6-301">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="305a6-302">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="305a6-302">UserPrincipalName</span></span>     | <span data-ttu-id="305a6-303">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="305a6-303">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="305a6-304">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="305a6-304">PrimarySmtpAddress</span></span>    | <span data-ttu-id="305a6-305">Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="305a6-305">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="305a6-306">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="305a6-306">ExternalEmailAddress</span></span>  | <span data-ttu-id="305a6-307">SMTP： LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="305a6-307">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="305a6-308">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="305a6-308">ExchangeGuid</span></span>          | <span data-ttu-id="305a6-309">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="305a6-309">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="305a6-310">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="305a6-310">LegacyExchangeDN</span></span>      | <span data-ttu-id="305a6-311">/o = 第一个组织/ou = Exchange 管理组</span><span class="sxs-lookup"><span data-stu-id="305a6-311">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="305a6-312"> (FYDIBOHF23SPDLT) /cn = 收件人/cn = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="305a6-312">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="305a6-313">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="305a6-313">EmailAddresses</span></span>        | <span data-ttu-id="305a6-314">x500：/o = 第一个组织/ou = Exchange 管理组 (FYDIBOHF23SPDLT) /cn = 收件人/cn = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="305a6-314">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="305a6-315">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="305a6-315">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="305a6-316">smtp： LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="305a6-316">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="305a6-317">SMTP： Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="305a6-317">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="305a6-318">示例 **源** 邮箱对象：</span><span class="sxs-lookup"><span data-stu-id="305a6-318">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="305a6-319">属性</span><span class="sxs-lookup"><span data-stu-id="305a6-319">Attribute</span></span>             | <span data-ttu-id="305a6-320">值</span><span class="sxs-lookup"><span data-stu-id="305a6-320">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="305a6-321">Alias</span><span class="sxs-lookup"><span data-stu-id="305a6-321">Alias</span></span>                 | <span data-ttu-id="305a6-322">LaraN</span><span class="sxs-lookup"><span data-stu-id="305a6-322">LaraN</span></span>                                                                    |
   | <span data-ttu-id="305a6-323">RecipientType</span><span class="sxs-lookup"><span data-stu-id="305a6-323">RecipientType</span></span>         | <span data-ttu-id="305a6-324">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="305a6-324">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="305a6-325">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="305a6-325">RecipientTypeDetails</span></span>  | <span data-ttu-id="305a6-326">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="305a6-326">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="305a6-327">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="305a6-327">UserPrincipalName</span></span>     | <span data-ttu-id="305a6-328">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="305a6-328">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="305a6-329">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="305a6-329">PrimarySmtpAddress</span></span>    | <span data-ttu-id="305a6-330">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="305a6-330">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="305a6-331">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="305a6-331">ExchangeGuid</span></span>          | <span data-ttu-id="305a6-332">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="305a6-332">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="305a6-333">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="305a6-333">LegacyExchangeDN</span></span>      | <span data-ttu-id="305a6-334">/o = 第一个组织/ou = Exchange 管理组</span><span class="sxs-lookup"><span data-stu-id="305a6-334">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="305a6-335"> (FYDIBOHF23SPDLT) /cn = 收件人/cn = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="305a6-335">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="305a6-336">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="305a6-336">EmailAddresses</span></span>        | <span data-ttu-id="305a6-337">smtp： LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="305a6-337">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="305a6-338">SMTP： Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="305a6-338">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="305a6-339">其他属性可能已包含在 Exchange 混合写回中。</span><span class="sxs-lookup"><span data-stu-id="305a6-339">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="305a6-340">如果不是，则应包含它们。</span><span class="sxs-lookup"><span data-stu-id="305a6-340">If not, they should be included.</span></span> 
   - <span data-ttu-id="305a6-341">msExchBlockedSendersHash –将从客户端到本地 Active Directory 的安全和被阻止的发件人数据写回到本地。</span><span class="sxs-lookup"><span data-stu-id="305a6-341">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="305a6-342">msExchSafeRecipientsHash –将从客户端到本地 Active Directory 的安全和被阻止的发件人数据写回到本地。</span><span class="sxs-lookup"><span data-stu-id="305a6-342">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="305a6-343">msExchSafeSendersHash –将从客户端到本地 Active Directory 的安全和被阻止的发件人数据写回到本地。</span><span class="sxs-lookup"><span data-stu-id="305a6-343">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="305a6-344">如果源邮箱在 LitigationHold 上，源邮箱可恢复的项目大小大于数据库默认值 (30 GB) ，由于目标配额小于源邮箱大小，移动不会继续。</span><span class="sxs-lookup"><span data-stu-id="305a6-344">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="305a6-345">您可以更新目标 MailUser 对象，将 ELC 邮箱标记从源环境转换为目标，这将触发目标系统将 MailUser 的配额扩展到 100 GB，从而允许移动到目标。</span><span class="sxs-lookup"><span data-stu-id="305a6-345">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="305a6-346">这些说明仅适用于运行 Azure AD Connect 的混合身份，因为用于标记 ELC 标志的命令不会向租户管理员公开。</span><span class="sxs-lookup"><span data-stu-id="305a6-346">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="305a6-347">示例-原样，无担保</span><span class="sxs-lookup"><span data-stu-id="305a6-347">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="305a6-348">此脚本假定连接到源邮箱 (，以获取源值) 和目标本地 Active Directory (以标记 Microsoft.rtc.management.adconnect.schema.aduser 对象) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-348">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="305a6-349">如果源已启用诉讼或单个项目恢复，请在目标帐户上设置此设置。</span><span class="sxs-lookup"><span data-stu-id="305a6-349">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="305a6-350">这会将目标帐户的转储程序大小增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="305a6-350">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="305a6-351">在迁移之前，非混合目标租户可以修改 MailUsers 的 "可恢复的项目" 文件夹中的配额，方法是运行以下命令，在 MailUser 对象上启用诉讼保留，并将配额增加到 100 GB： `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 。</span><span class="sxs-lookup"><span data-stu-id="305a6-351">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="305a6-352">注释此操作不适用于混合中的租户。</span><span class="sxs-lookup"><span data-stu-id="305a6-352">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="305a6-353">目标组织中的用户必须具有适用于组织的相应 Exchange Online 订阅的许可。</span><span class="sxs-lookup"><span data-stu-id="305a6-353">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="305a6-354">您可以在邮箱移动前应用许可证，但只有在使用 ExchangeGUID 和代理地址正确设置目标 MailUser 之后。</span><span class="sxs-lookup"><span data-stu-id="305a6-354">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="305a6-355">在应用 ExchangeGUID 之前应用许可证将导致在目标组织中预配新邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-355">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="305a6-356">在对邮箱或 MailUser 对象应用许可证时，将会对所有 SMTP 类型 proxyAddresses 进行清理，以确保 Exchange EmailAddresses 阵列中仅包含已验证的域。</span><span class="sxs-lookup"><span data-stu-id="305a6-356">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="305a6-357">必须确保目标 MailUser 没有与源 ExchangeGuid 不匹配的以前的 ExchangeGuid。</span><span class="sxs-lookup"><span data-stu-id="305a6-357">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="305a6-358">如果目标 MEU 之前已授权使用 Exchange Online 并预配了邮箱，则可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="305a6-358">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="305a6-359">如果目标 MailUser 之前已授权或具有与源 ExchangeGuid 不匹配的 ExchangeGuid，则需要执行云 MEU 的清理。</span><span class="sxs-lookup"><span data-stu-id="305a6-359">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="305a6-360">对于这些云 Meu，您可以运行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 命令。</span><span class="sxs-lookup"><span data-stu-id="305a6-360">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="305a6-361">此过程是不可逆的。</span><span class="sxs-lookup"><span data-stu-id="305a6-361">This process is irreversible.</span></span> <span data-ttu-id="305a6-362">如果对象具有 softDeleted 邮箱，则在此之后无法还原。</span><span class="sxs-lookup"><span data-stu-id="305a6-362">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="305a6-363">但是，清除后，可以将正确的 ExchangeGuid 同步到目标对象，MRS 会将源邮箱连接到新创建的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-363">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="305a6-364"> (在新参数上引用 EHLO 博客。 ) </span><span class="sxs-lookup"><span data-stu-id="305a6-364">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="305a6-365">使用此命令查找以前为邮箱的对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-365">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="305a6-366">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-366">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="305a6-367">使用此命令清除软删除的邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-367">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="305a6-368">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-368">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="305a6-369">执行邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="305a6-369">Perform mailbox migrations</span></span>

<span data-ttu-id="305a6-370">跨租户 Exchange 邮箱迁移作为从目标租户启动的迁移批处理提交。</span><span class="sxs-lookup"><span data-stu-id="305a6-370">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="305a6-371">这类似于在从本地 Exchange 本地迁移到 Microsoft 365 时，进行中的迁移批处理的工作方式。</span><span class="sxs-lookup"><span data-stu-id="305a6-371">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="305a6-372">创建迁移批处理</span><span class="sxs-lookup"><span data-stu-id="305a6-372">Create Migration batches</span></span>

<span data-ttu-id="305a6-373">以下是用于启动关闭移动的迁移批处理 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-373">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="305a6-374">CSV 文件中的电子邮件地址必须是目标租户中指定的地址，而不是源租户中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="305a6-374">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="305a6-375">在选择 "跨租户" 选项时，新的 Exchange 管理中心也支持迁移批提交。</span><span class="sxs-lookup"><span data-stu-id="305a6-375">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="305a6-376">更新本地 MailUsers</span><span class="sxs-lookup"><span data-stu-id="305a6-376">Update on-premises MailUsers</span></span>

<span data-ttu-id="305a6-377">邮箱从源移动到目标后，应确保使用新的 targetAddress 更新本地邮件用户（源和目标）。</span><span class="sxs-lookup"><span data-stu-id="305a6-377">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="305a6-378">在此示例中，移动中使用的 targetDeliveryDomain 是 **contoso \. onmicrosoft.com** 。</span><span class="sxs-lookup"><span data-stu-id="305a6-378">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="305a6-379">使用此 targetAddress 更新邮件用户。</span><span class="sxs-lookup"><span data-stu-id="305a6-379">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="305a6-380">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="305a6-380">Frequently asked questions</span></span>
 
<span data-ttu-id="305a6-381">**是否需要在移动后在源本地更新 RemoteMailboxes？**</span><span class="sxs-lookup"><span data-stu-id="305a6-381">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="305a6-382">是的，当源租户邮箱移动到目标租户时，应更新源本地用户的 targetAddress (RemoteRoutingAddress/ExternalEmailAddress) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-382">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="305a6-383">虽然邮件路由可以跟踪使用不同 targetAddresses 的多个邮件用户之间的引用，但邮件用户的忙/闲查找必须以邮箱用户的位置为目标。</span><span class="sxs-lookup"><span data-stu-id="305a6-383">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="305a6-384">忙/闲查找将不会跟踪多个重定向。</span><span class="sxs-lookup"><span data-stu-id="305a6-384">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="305a6-385">**团队是否聊天文件夹内容迁移跨租户？**</span><span class="sxs-lookup"><span data-stu-id="305a6-385">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="305a6-386">否，团队聊天文件夹内容不会迁移跨租户。</span><span class="sxs-lookup"><span data-stu-id="305a6-386">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="305a6-387">**我如何才能看到跨租户移动而不是我的加入和脱离移动的移动？**</span><span class="sxs-lookup"><span data-stu-id="305a6-387">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="305a6-388">使用 `-flags` 参数。</span><span class="sxs-lookup"><span data-stu-id="305a6-388">Use the `-flags` parameter.</span></span> <span data-ttu-id="305a6-389">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-389">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="305a6-390">**您可以提供用于复制测试中使用的属性的示例脚本吗？**</span><span class="sxs-lookup"><span data-stu-id="305a6-390">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="305a6-391">示例-原样，无担保</span><span class="sxs-lookup"><span data-stu-id="305a6-391">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="305a6-392">此脚本假定连接到源邮箱 (以获取源值) 和目标本地 Active Directory 域服务 (以标记 Microsoft.rtc.management.adconnect.schema.aduser 对象) 。</span><span class="sxs-lookup"><span data-stu-id="305a6-392">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="305a6-393">如果源已启用诉讼或单个项目恢复，请在目标帐户上设置此设置。</span><span class="sxs-lookup"><span data-stu-id="305a6-393">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="305a6-394">这会将目标帐户的转储程序大小增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="305a6-394">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="305a6-395">**如何在移动使用邮箱后在第1天访问 Outlook？**</span><span class="sxs-lookup"><span data-stu-id="305a6-395">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="305a6-396">由于只有一个租户可以拥有域，所以在邮箱移动完成时，将不会将前一个主 SMTPAddress 与目标租户中的用户关联。仅适用于与新租户关联的域。</span><span class="sxs-lookup"><span data-stu-id="305a6-396">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="305a6-397">Outlook 使用新 UPN 对服务进行身份验证，并且 Outlook 配置文件预期查找旧主 SMTPAddress 以匹配目标系统中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-397">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="305a6-398">由于旧版地址不在目标系统中，outlook 配置文件将不会连接以查找新移动的邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-398">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="305a6-399">对于此初始部署，用户需要使用其新 UPN、主 SMTP 地址和重新同步 OST 内容重建其配置文件。</span><span class="sxs-lookup"><span data-stu-id="305a6-399">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="305a6-400">在批处理用户完成时进行相应的规划。</span><span class="sxs-lookup"><span data-stu-id="305a6-400">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="305a6-401">在创建 Outlook 客户端配置文件，并将后续 OST 和 OAB 文件下载到客户端时，需要考虑网络利用率和容量。</span><span class="sxs-lookup"><span data-stu-id="305a6-401">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="305a6-402">**我需要作为其成员的 Exchange RBAC 角色才能设置或完成跨租户移动？**</span><span class="sxs-lookup"><span data-stu-id="305a6-402">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="305a6-403">根据执行邮箱移动时假设的委托职责，有一个角色矩阵。</span><span class="sxs-lookup"><span data-stu-id="305a6-403">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="305a6-404">目前，需要两个角色：</span><span class="sxs-lookup"><span data-stu-id="305a6-404">Currently, two roles are required:</span></span>  

- <span data-ttu-id="305a6-405">第一个角色适用于一次性设置任务，用于建立将内容移入或移出租户/组织边界的授权。</span><span class="sxs-lookup"><span data-stu-id="305a6-405">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="305a6-406">由于将数据从组织控制中移出是所有公司的重要问题，因此我们选择了组织管理员 (OrgAdmin) 中分配的最高角色。</span><span class="sxs-lookup"><span data-stu-id="305a6-406">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="305a6-407">此角色必须更改或设置一个新的 Set-organizationrelationship，用于定义与远程组织的-MailboxMoveCapability。</span><span class="sxs-lookup"><span data-stu-id="305a6-407">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="305a6-408">只有 OrgAdmin 可以更改 MailboxMoveCapability 设置，而 OrganizationRelationhip 上的其他属性可以由联合共享管理员进行管理。</span><span class="sxs-lookup"><span data-stu-id="305a6-408">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="305a6-409">执行实际 move 命令的角色可以委派给较低级别的函数。</span><span class="sxs-lookup"><span data-stu-id="305a6-409">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="305a6-410">移动邮箱的角色分配了使用参数将邮箱移入或移出组织的功能 `-RemoteTenant` 。</span><span class="sxs-lookup"><span data-stu-id="305a6-410">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="305a6-411">**我们如何定位在转换后的邮箱上为 targetAddress (TargetDeliveryDomain) 选择的 SMTP 地址 (到 MailUser 转换) ？**</span><span class="sxs-lookup"><span data-stu-id="305a6-411">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="305a6-412">Exchange 邮箱移动使用 MRS 在将原始源邮箱转换为 MailUser 时通过) 目标对象上的电子邮件地址 (proxyAddress 来手工创建原始源邮箱上的 targetAddress。</span><span class="sxs-lookup"><span data-stu-id="305a6-412">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="305a6-413">此过程将使用传递到 move 命令的-TargetDeliveryDomain 值，然后在目标端为该域检查匹配的代理。</span><span class="sxs-lookup"><span data-stu-id="305a6-413">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="305a6-414">找到匹配项时，将使用匹配的 proxyAddress 设置已转换邮箱上的 ExternalEmailAddress (targetAddress)  (现在 MailUser) 对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-414">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="305a6-415">**邮箱权限如何转换？**</span><span class="sxs-lookup"><span data-stu-id="305a6-415">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="305a6-416">邮箱权限包括 "代表发送" 和 "邮箱访问"：</span><span class="sxs-lookup"><span data-stu-id="305a6-416">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="305a6-417">代表发送 (AD： publicDelegates) 将访问用户邮箱的收件人的 DN 存储为代理人。</span><span class="sxs-lookup"><span data-stu-id="305a6-417">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="305a6-418">此值存储在 Active Directory 中，并且当前不作为邮箱转换的一部分移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-418">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="305a6-419">如果源邮箱已设置 publicDelegates，则在使用命令的目标环境中，如果 MEU 到邮箱转换完成，将需要对目标邮箱上的 publicDelegates `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 。</span><span class="sxs-lookup"><span data-stu-id="305a6-419">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="305a6-420">当主体和代理都移到目标系统时，存储在邮箱中的邮箱权限将随邮箱一起移动。</span><span class="sxs-lookup"><span data-stu-id="305a6-420">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="305a6-421">例如，用户 TestUser_7 被授予租户 SourceCompany.onmicrosoft.com 中邮箱 TestUser_8 的 FullAccess。</span><span class="sxs-lookup"><span data-stu-id="305a6-421">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="305a6-422">邮箱移动完成到 TargetCompany.onmicrosoft.com 后，将在目标目录中设置相同的权限。</span><span class="sxs-lookup"><span data-stu-id="305a6-422">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="305a6-423">在源和目标租户中使用 *add-mailboxpermission* TestUser_7 的示例如下所示。</span><span class="sxs-lookup"><span data-stu-id="305a6-423">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="305a6-424">Exchange cmdlet 将相应地加上源和目标。</span><span class="sxs-lookup"><span data-stu-id="305a6-424">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="305a6-425">下面的示例展示了邮箱权限在移动前的输出。</span><span class="sxs-lookup"><span data-stu-id="305a6-425">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="305a6-426">下面的示例展示了邮箱权限在移动后的输出。</span><span class="sxs-lookup"><span data-stu-id="305a6-426">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="305a6-427">不支持跨租户邮箱和日历权限。</span><span class="sxs-lookup"><span data-stu-id="305a6-427">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="305a6-428">您必须将主体和代理组织到合并的移动批处理中，以便从源租户同时转换这些连接的邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-428">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="305a6-429">已知问题</span><span class="sxs-lookup"><span data-stu-id="305a6-429">Known issues</span></span> 

-  <span data-ttu-id="305a6-430">**问题：无法迁移自动扩展存档。**</span><span class="sxs-lookup"><span data-stu-id="305a6-430">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="305a6-431">跨租户迁移功能支持特定用户的主邮箱和存档邮箱的迁移。</span><span class="sxs-lookup"><span data-stu-id="305a6-431">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="305a6-432">如果源中的用户有一个自动扩展的存档–即有多个存档邮箱，则该功能无法迁移其他存档。</span><span class="sxs-lookup"><span data-stu-id="305a6-432">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="305a6-433">**问题：具有非拥有的 smtp proxyAddress 的云 MailUsers 阻止 MRS 移动背景。**</span><span class="sxs-lookup"><span data-stu-id="305a6-433">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="305a6-434">创建目标租户 MailUser 对象时，必须确保所有 SMTP 代理地址都属于目标租户组织。</span><span class="sxs-lookup"><span data-stu-id="305a6-434">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="305a6-435">如果 SMTP proxyAddress 在不属于本地租户的目标邮件用户上存在，则会阻止 MailUser 转换为邮箱。</span><span class="sxs-lookup"><span data-stu-id="305a6-435">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="305a6-436">这是因为我们的保证，邮箱对象只能从受租户) 授权的域发送邮件 (域：</span><span class="sxs-lookup"><span data-stu-id="305a6-436">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="305a6-437">在使用 Azure AD Connect 从本地同步用户时，将本地 MailUser 对象设置为 ExternalEmailAddress 指向 laran@contoso onmicrosoft.com 中 (存在邮箱的源租户 \.) 并将 PrimarySMTPAddress 标记为驻留在目标租户 (Lara.Newton@northwind com) 中的域 \. 。</span><span class="sxs-lookup"><span data-stu-id="305a6-437">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="305a6-438">这些值将同步到租户，并设置适当的邮件用户并准备好迁移。</span><span class="sxs-lookup"><span data-stu-id="305a6-438">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="305a6-439">此处显示了一个示例对象。</span><span class="sxs-lookup"><span data-stu-id="305a6-439">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="305a6-440">EmailAddresses/proxyAddresses 数组中 *不* 存在 *contoso. .onmicrosoft \. com* 地址。</span><span class="sxs-lookup"><span data-stu-id="305a6-440">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="305a6-441">**问题：将 "外部" 主 SMTP 地址的 MailUser 对象修改/重置为 "内部" 公司声明域**</span><span class="sxs-lookup"><span data-stu-id="305a6-441">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="305a6-442">MailUser 对象是指向非本地邮箱的指针。</span><span class="sxs-lookup"><span data-stu-id="305a6-442">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="305a6-443">在跨租户邮箱迁移的情况下，我们使用 MailUser 对象表示源邮箱 (从目标组织的视角) 或源组织的 "角度") 中的目标邮箱 (。</span><span class="sxs-lookup"><span data-stu-id="305a6-443">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="305a6-444">MailUsers 将有一个 ExternalEmailAddress (targetAddress) 指向实际邮箱的 smtp 地址 (ProxyTest \@ fabrikam \. onmicrosoft.com) 和 primarySMTP 地址表示在目录中显示的邮箱用户的 smtp 地址。</span><span class="sxs-lookup"><span data-stu-id="305a6-444">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="305a6-445">有些组织会选择将主 SMTP 地址显示为外部 SMTP 地址，而不是作为本地租户 (（如 fabrikam.com 而不是 contoso.com) ）所拥有/验证的地址。</span><span class="sxs-lookup"><span data-stu-id="305a6-445">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="305a6-446">但是，一旦将 Exchange service plan 对象应用于 MailUser 通过许可操作，主 SMTP 地址将被修改为显示为由本地组织 (contoso.com) 验证的域。</span><span class="sxs-lookup"><span data-stu-id="305a6-446">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="305a6-447">有以下两个可能的原因：</span><span class="sxs-lookup"><span data-stu-id="305a6-447">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="305a6-448">将任何 Exchange 服务计划应用于 MailUser 时，Azure AD 进程都将开始强制实施代理清理，以确保本地组织无法从其他租户发送邮件传出、欺骗或邮件。</span><span class="sxs-lookup"><span data-stu-id="305a6-448">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="305a6-449">如果本地组织未验证地址，则具有这些服务计划的收件人对象上的任何 SMTP 地址都将被删除。</span><span class="sxs-lookup"><span data-stu-id="305a6-449">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="305a6-450">与此示例中的情况一样，Fabikam \. com 域不会由 contoso \. onmicrosoft.com 租户验证，因此清理操作会删除该 fabrikam \. com 域。</span><span class="sxs-lookup"><span data-stu-id="305a6-450">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="305a6-451">如果您希望在迁移之前或迁移之后将这些外部域保留在 MailUser 上，则需要在移动完成后或移动之前更改迁移过程以去除许可证，以确保用户应用了预期的外部品牌。</span><span class="sxs-lookup"><span data-stu-id="305a6-451">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="305a6-452">您需要确保已正确授权邮箱对象不会影响邮件服务。</span><span class="sxs-lookup"><span data-stu-id="305a6-452">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="305a6-453">此处显示了用于删除 Contoso onmicrosoft.com 租户中的 MailUser 上的服务计划的示例脚本 \. 。</span><span class="sxs-lookup"><span data-stu-id="305a6-453">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="305a6-454">此处显示了所分配的 ServicePlans 集的结果。</span><span class="sxs-lookup"><span data-stu-id="305a6-454">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="305a6-455">用户的 PrimarySMTPAddress 不再会再被清理。</span><span class="sxs-lookup"><span data-stu-id="305a6-455">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="305a6-456">Fabrikam.com 域不归 contoso.onmicrosoft.com 租户所有，并将作为目录中显示的主 SMTP 地址保留。</span><span class="sxs-lookup"><span data-stu-id="305a6-456">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="305a6-457">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="305a6-457">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="305a6-458">如果 msExchRemoteRecipientType 设置为 8 (DeprovisionMailbox) ，对于迁移到目标租户的本地 MailUsers，Azure 中的代理清理逻辑将删除 nonowned 域，并将 primarySMTP 重置为拥有的域。</span><span class="sxs-lookup"><span data-stu-id="305a6-458">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="305a6-459">通过清除本地 MailUser 中的 msExchRemoteRecipientType，代理清理逻辑不再适用。</span><span class="sxs-lookup"><span data-stu-id="305a6-459">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="305a6-460">以下是包括 Exchange Online 的一组可能的服务计划。</span><span class="sxs-lookup"><span data-stu-id="305a6-460">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="305a6-461">名称</span><span class="sxs-lookup"><span data-stu-id="305a6-461">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="305a6-462">高级电子数据展示存储 (500GB) </span><span class="sxs-lookup"><span data-stu-id="305a6-462">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="305a6-463">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="305a6-463">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="305a6-464">数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="305a6-464">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="305a6-465">Exchange Enterprise CAL 服务 (EOP、DLP) </span><span class="sxs-lookup"><span data-stu-id="305a6-465">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="305a6-466">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="305a6-466">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="305a6-467">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="305a6-467">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="305a6-468">Exchange Online (P1) </span><span class="sxs-lookup"><span data-stu-id="305a6-468">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="305a6-469">Exchange Online (计划 1) </span><span class="sxs-lookup"><span data-stu-id="305a6-469">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="305a6-470">Exchange Online（计划 2）</span><span class="sxs-lookup"><span data-stu-id="305a6-470">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="305a6-471">适用于 Exchange Online 的 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="305a6-471">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="305a6-472">适用于 Exchange Server 的 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="305a6-472">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="305a6-473">Exchange Online 非活动用户加载项</span><span class="sxs-lookup"><span data-stu-id="305a6-473">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="305a6-474">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="305a6-474">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="305a6-475">Exchange Online 多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="305a6-475">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="305a6-476">Exchange Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="305a6-476">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="305a6-477">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="305a6-477">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="305a6-478">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="305a6-478">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="305a6-479">信息障碍</span><span class="sxs-lookup"><span data-stu-id="305a6-479">Information Barriers</span></span>                              |
   | <span data-ttu-id="305a6-480">适用于 Office 365 的信息保护 - 高级版</span><span class="sxs-lookup"><span data-stu-id="305a6-480">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="305a6-481">适用于 Office 365 的信息保护 - 标准版</span><span class="sxs-lookup"><span data-stu-id="305a6-481">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="305a6-482">通过 MyAnalytics 的见解</span><span class="sxs-lookup"><span data-stu-id="305a6-482">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="305a6-483">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="305a6-483">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="305a6-484">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="305a6-484">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="305a6-485">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="305a6-485">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="305a6-486">Microsoft MyAnalytics（完整版）</span><span class="sxs-lookup"><span data-stu-id="305a6-486">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="305a6-487">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="305a6-487">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="305a6-488">Microsoft Defender for Office 365 (计划 1) </span><span class="sxs-lookup"><span data-stu-id="305a6-488">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="305a6-489">Microsoft Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="305a6-489">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="305a6-490">Office 365 特权访问管理</span><span class="sxs-lookup"><span data-stu-id="305a6-490">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="305a6-491">Office 365 中的高级加密</span><span class="sxs-lookup"><span data-stu-id="305a6-491">Premium Encryption in Office 365</span></span>                  |
    
