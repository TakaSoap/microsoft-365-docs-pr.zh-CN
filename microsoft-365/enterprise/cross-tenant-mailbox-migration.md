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
ms.openlocfilehash: f24f519ec3bb12622d74c1d02fbc0bb017aa2b24
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476405"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="979e4-103">跨租户邮箱迁移 (预览) </span><span class="sxs-lookup"><span data-stu-id="979e4-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="979e4-104">以前，当 Exchange Online 租户需要将邮箱移动到同一 Exchange Online 服务中的另一个租户时，他们必须将其完全离开本地，然后载入新租户。</span><span class="sxs-lookup"><span data-stu-id="979e4-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="979e4-105">借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="979e4-106">这将无需离开和载入邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="979e4-107">通常，在合并或资产重组期间，你需要能够将用户和内容移动到新租户。</span><span class="sxs-lookup"><span data-stu-id="979e4-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="979e4-108">当目标租户管理员执行移动时，称为"拉取"移动，类似于本地到云载入迁移。</span><span class="sxs-lookup"><span data-stu-id="979e4-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="979e4-109">跨租户 Exchange 邮箱移动由租户管理员完全自助，使用已知的接口，可以将这些接口编写成更大的工作流，以将用户转换到其新组织。</span><span class="sxs-lookup"><span data-stu-id="979e4-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="979e4-110">管理员可以使用可通过"移动邮箱"管理角色使用的 `New-MigrationBatch` cmdlet 执行跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="979e4-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="979e4-111">移动过程包括邮箱同步和最终完成期间租户授权检查。</span><span class="sxs-lookup"><span data-stu-id="979e4-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="979e4-112">迁移的用户必须作为 MailUsers 存在于目标租户 Exchange Online 系统中，并带有特定属性标记才能启用跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="979e4-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="979e4-113">对于未在目标租户中正确设置的用户，系统移动将失败。</span><span class="sxs-lookup"><span data-stu-id="979e4-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="979e4-114">移动完成后，源系统邮箱将转换为 MailUser，targetAddress (在 Exchange) 中显示为 ExternalEmailAddress，并标记目标租户的路由地址。</span><span class="sxs-lookup"><span data-stu-id="979e4-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="979e4-115">此过程将旧版 MailUser 保留于源租户中，并允许共存一段时间和邮件路由。</span><span class="sxs-lookup"><span data-stu-id="979e4-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="979e4-116">当业务流程允许时，源租户可能会删除源 MailUser 或将其转换为邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="979e4-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="979e4-117">仅混合或云中的租户或两者的任意组合支持跨租户 Exchange 邮箱迁移。</span><span class="sxs-lookup"><span data-stu-id="979e4-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="979e4-118">本文介绍了跨租户邮箱移动的过程，并提供了有关如何为内容移动准备源租户和目标租户的指南。</span><span class="sxs-lookup"><span data-stu-id="979e4-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="979e4-119">准备源租户和目标租户</span><span class="sxs-lookup"><span data-stu-id="979e4-119">Preparing source and target tenants</span></span>

<span data-ttu-id="979e4-120">跨租户 Exchange 邮箱迁移功能需要跨租户迁移的授权和范围。</span><span class="sxs-lookup"><span data-stu-id="979e4-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="979e4-121">通过使用 Azure 企业应用程序和密钥保管库存储解决方案，租户管理员现在能够管理从一个租户到另一个租户的 Exchange Online 邮箱迁移的授权和范围。</span><span class="sxs-lookup"><span data-stu-id="979e4-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="979e4-122">跨租户邮箱移动支持邀请和同意模型，以在 Azure AD (Azure AD) 应用程序，用于在租户对之间进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="979e4-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="979e4-123">还需要其他组件，如组织关系和迁移终结点。</span><span class="sxs-lookup"><span data-stu-id="979e4-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="979e4-124">本节不包含在目标目录中准备 MailUser 用户对象所需的特定步骤，也不包括提交迁移批处理的示例命令。</span><span class="sxs-lookup"><span data-stu-id="979e4-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="979e4-125">有关此信息 [，请参阅准备目标用户对象进行](#prepare-target-user-objects-for-migration) 迁移。</span><span class="sxs-lookup"><span data-stu-id="979e4-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="979e4-126">先决条件</span><span class="sxs-lookup"><span data-stu-id="979e4-126">Prerequisites</span></span>

<span data-ttu-id="979e4-127">跨租户邮箱移动功能需要 [Azure Key Vault](/azure/key-vault/basic-concepts) 来建立特定于租户对的 Azure 应用程序，以安全存储和访问用于对邮箱从一个租户迁移到另一个租户进行身份验证和授权迁移的证书/密码，从而删除在租户之间共享证书/密码的任何要求。</span><span class="sxs-lookup"><span data-stu-id="979e4-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="979e4-128">在启动之前，请确保你拥有运行部署脚本的必要权限，以便配置 Azure Key Vault、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。</span><span class="sxs-lookup"><span data-stu-id="979e4-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="979e4-129">通常，全局管理员具有执行所有配置步骤的权限。</span><span class="sxs-lookup"><span data-stu-id="979e4-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="979e4-130">此外，在运行安装程序之前，源租户中需要启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="979e4-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="979e4-131">这些组用于将邮箱列表的范围从源租户 (有时称为资源) 租户移动到目标租户。</span><span class="sxs-lookup"><span data-stu-id="979e4-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="979e4-132">这允许源租户管理员限制或限定需要移动的特定邮箱集，以防止迁移非预期用户。</span><span class="sxs-lookup"><span data-stu-id="979e4-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="979e4-133">不支持嵌套组。</span><span class="sxs-lookup"><span data-stu-id="979e4-133">Nested groups are not supported.</span></span>

<span data-ttu-id="979e4-134">你还需要与受信任的合作伙伴公司联系 (将邮箱移动到其) 以获取其 Microsoft 365 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="979e4-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="979e4-135">此租户 ID 用于"组织关系" `DomainName` 字段。</span><span class="sxs-lookup"><span data-stu-id="979e4-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="979e4-136">若要获取订阅的租户 ID，请登录到 Microsoft 365 管理中心并转到 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="979e4-137">单击"租户 ID"属性的复制图标，将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="979e4-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="979e4-138">下面是此过程的工作方式。</span><span class="sxs-lookup"><span data-stu-id="979e4-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="邮箱迁移的租户准备。":::

<span data-ttu-id="979e4-140">[请参阅此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。</span><span class="sxs-lookup"><span data-stu-id="979e4-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="979e4-141">准备租户</span><span class="sxs-lookup"><span data-stu-id="979e4-141">Prepare tenants</span></span>

<span data-ttu-id="979e4-142">在高级别上，执行安装程序脚本时将执行以下配置操作。</span><span class="sxs-lookup"><span data-stu-id="979e4-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="979e4-143">准备目标租户：</span><span class="sxs-lookup"><span data-stu-id="979e4-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="979e4-144">如果未提供现有的 Azure 资源组，则使用 SCRIPT (一) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="979e4-145">如果未提供现有密钥保管库，则使用 SCRIPT (一) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="979e4-146">为 SCRIPT 脚本迁移的 Office 365 Exchange Online 邮箱迁移应用程序 (访问) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="979e4-147">新证书将 (或现有证书（如果指定) ，以将密码保留到 SCRIPT (迁移) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="979e4-148">新的 Azure AD 应用程序是使用 SCRIPT (创建的) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="979e4-149">证书/密码将上载到迁移应用程序 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="979e4-150">邮箱迁移权限将分配给 SCRIPT (应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="979e4-151">部署脚本将暂停，直到目标管理员同意使用 SCRIPT (自己的) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="979e4-152">目标租户管理员同意向应用程序授予手动 (权限) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="979e4-153">将创建与目标租户的组织 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="979e4-154">创建迁移终结点以将邮箱拉至 SCRIPT (目标) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="979e4-155">准备源租户：</span><span class="sxs-lookup"><span data-stu-id="979e4-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="979e4-156">源租户管理员接受来自手动迁移目标租户 (邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="979e4-157">源租户管理员在租户中创建启用邮件的安全组，以包含允许迁移应用程序在手动迁移 (移动) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="979e4-158">创建与目标租户的组织关系，指定邮箱迁移应用程序应该用于 OAuth 验证，以接受 SCRIPT (移动) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="979e4-159">目标租户管理员的分步说明</span><span class="sxs-lookup"><span data-stu-id="979e4-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="979e4-160">从 [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview)SetupCrossTenantRelationshipForTargetTenant.ps1下载目标租户设置的脚本。</span><span class="sxs-lookup"><span data-stu-id="979e4-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="979e4-161">将脚本 (SetupCrossTenantRelationshipForTargetTenant.ps1) 保存到要执行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="979e4-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="979e4-162">创建到 Exchange Online 目标租户的远程 PowerShell 连接。</span><span class="sxs-lookup"><span data-stu-id="979e4-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="979e4-163">同样，请确保你拥有运行部署脚本的必要权限，以便配置 Azure 密钥保管库存储和证书、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。</span><span class="sxs-lookup"><span data-stu-id="979e4-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="979e4-164">将文件文件夹目录更改为脚本位置，或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。</span><span class="sxs-lookup"><span data-stu-id="979e4-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="979e4-165">运行具有以下参数和值的脚本。</span><span class="sxs-lookup"><span data-stu-id="979e4-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="979e4-166">参数</span><span class="sxs-lookup"><span data-stu-id="979e4-166">Parameter</span></span> | <span data-ttu-id="979e4-167">值</span><span class="sxs-lookup"><span data-stu-id="979e4-167">Value</span></span> | <span data-ttu-id="979e4-168">必需或可选</span><span class="sxs-lookup"><span data-stu-id="979e4-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="979e4-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="979e4-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="979e4-170">目标租户域，如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="979e4-171">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-171">Required</span></span> |
    | <span data-ttu-id="979e4-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="979e4-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="979e4-173">源租户域，如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="979e4-174">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-174">Required</span></span> |
    | <span data-ttu-id="979e4-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="979e4-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="979e4-176">源租户管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="979e4-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="979e4-177">这是将同意使用从目标管理员发送的邮箱迁移应用程序的源租户管理员。这是将接收应用程序的电子邮件邀请的管理员。</span><span class="sxs-lookup"><span data-stu-id="979e4-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="979e4-178">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-178">Required</span></span> |
    | <span data-ttu-id="979e4-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="979e4-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="979e4-180">源租户组织 ID (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="979e4-181">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-181">Required</span></span> |
    | <span data-ttu-id="979e4-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="979e4-182">-SubscriptionId</span></span>                             | <span data-ttu-id="979e4-183">用于创建资源的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="979e4-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="979e4-184">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-184">Required</span></span> |
    | <span data-ttu-id="979e4-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="979e4-185">-ResourceGroup</span></span>                              | <span data-ttu-id="979e4-186">包含或将包含密钥保管库的 Azure 资源组名称。</span><span class="sxs-lookup"><span data-stu-id="979e4-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="979e4-187">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-187">Required</span></span> |
    | <span data-ttu-id="979e4-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="979e4-188">-KeyVaultName</span></span>                               | <span data-ttu-id="979e4-189">将存储邮箱迁移应用程序证书/密码的 Azure Key Vault 实例。</span><span class="sxs-lookup"><span data-stu-id="979e4-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="979e4-190">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-190">Required</span></span> |
    | <span data-ttu-id="979e4-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="979e4-191">-CertificateName</span></span>                            | <span data-ttu-id="979e4-192">在密钥保管库中生成或搜索证书时证书名称。</span><span class="sxs-lookup"><span data-stu-id="979e4-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="979e4-193">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-193">Required</span></span> |
    | <span data-ttu-id="979e4-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="979e4-194">-CertificateSubject</span></span>                         | <span data-ttu-id="979e4-195">Azure 密钥保管库证书主题名称，例如 CN=contoso_fabrikam。</span><span class="sxs-lookup"><span data-stu-id="979e4-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="979e4-196">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-196">Required</span></span> |
    | <span data-ttu-id="979e4-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="979e4-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="979e4-198">邮件迁移应用程序，如果已创建，将使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="979e4-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="979e4-199">可选</span><span class="sxs-lookup"><span data-stu-id="979e4-199">Optional</span></span> |
    | <span data-ttu-id="979e4-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="979e4-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="979e4-201">为邮箱迁移应用程序（如 Exchange 或 MSGraph (Exchange）授予移动邮箱所需的权限、使用此应用程序向资源租户租户发送同意链接邀请的 MSGraph) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="979e4-202">必需</span><span class="sxs-lookup"><span data-stu-id="979e4-202">Required</span></span> |
    | <span data-ttu-id="979e4-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="979e4-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="979e4-204">用于使用为迁移创建的应用程序的参数，用于向源租户管理员发送同意链接邀请。如果不存在，这将提示目标管理员的凭据连接到 Azure 邀请管理器，并将邀请作为目标管理员发送。</span><span class="sxs-lookup"><span data-stu-id="979e4-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="979e4-205">可选</span><span class="sxs-lookup"><span data-stu-id="979e4-205">Optional</span></span> |
    | <span data-ttu-id="979e4-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="979e4-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="979e4-207">存储密钥保管库审核日志的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="979e4-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="979e4-208">可选</span><span class="sxs-lookup"><span data-stu-id="979e4-208">Optional</span></span> |
    | <span data-ttu-id="979e4-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="979e4-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="979e4-210">包含用于存储密钥保管库审核日志的存储帐户的资源组。</span><span class="sxs-lookup"><span data-stu-id="979e4-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="979e4-211">可选</span><span class="sxs-lookup"><span data-stu-id="979e4-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="979e4-212">请确保在运行脚本之前已安装 Azure AD PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="979e4-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="979e4-213">有关安装 ![ 步骤， ](/powershell/azure/install-az-ps?view=azps-5.1.0) 请参阅此处</span><span class="sxs-lookup"><span data-stu-id="979e4-213">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="979e4-214">脚本将暂停，并要求您接受或同意在此过程期间创建的 Exchange 邮箱迁移应用程序。</span><span class="sxs-lookup"><span data-stu-id="979e4-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="979e4-215">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-215">Here is an example.</span></span>

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

7. <span data-ttu-id="979e4-216">URL 将显示在远程 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="979e4-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="979e4-217">复制为租户许可提供的链接并将其粘贴到 Web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="979e4-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="979e4-218">使用全局管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="979e4-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="979e4-219">显示以下屏幕时，选择"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="979e4-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="&quot;接受权限&quot;对话框":::

9. <span data-ttu-id="979e4-221">切换回远程 PowerShell 会话并按 Enter 继续。</span><span class="sxs-lookup"><span data-stu-id="979e4-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="979e4-222">该脚本将配置其余的安装程序对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="979e4-223">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="979e4-224">目标管理员设置现已完成！</span><span class="sxs-lookup"><span data-stu-id="979e4-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="979e4-225">源租户管理员的分步说明</span><span class="sxs-lookup"><span data-stu-id="979e4-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="979e4-226">以目标管理员在设置过程中指定的 -ResourceTenantAdminEmail 登录邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="979e4-227">从目标租户查找电子邮件邀请，然后选择" **入门"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="979e4-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="你已被邀请对话框":::

2. <span data-ttu-id="979e4-229">选择 **"接受** "接受邀请。</span><span class="sxs-lookup"><span data-stu-id="979e4-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="接受权限的对话框":::

   > [!NOTE]
   > <span data-ttu-id="979e4-231">如果未收到此电子邮件或找不到此电子邮件，则为目标租户管理员提供了直接 URL，可提供给你接受邀请。</span><span class="sxs-lookup"><span data-stu-id="979e4-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="979e4-232">目标租户管理员的远程 PowerShell 会话脚本中的 URL 应包含。</span><span class="sxs-lookup"><span data-stu-id="979e4-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="979e4-233">在 Microsoft 365 管理中心或远程 PowerShell 会话中，创建一个或多个启用邮件的安全组，以控制目标租户允许的邮箱列表，以将 (从源租户移动到目标租户) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="979e4-234">无需提前填充此组，但必须至少提供一个组，以运行脚本 (步骤) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="979e4-235">不支持嵌套组。</span><span class="sxs-lookup"><span data-stu-id="979e4-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="979e4-236">从 gitHub SetupCrossTenantRelationshipForResourceTenant.ps1下载源租户设置的脚本 [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ：。</span><span class="sxs-lookup"><span data-stu-id="979e4-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="979e4-237">使用 Exchange 管理员权限创建到源租户的远程 PowerShell 连接。</span><span class="sxs-lookup"><span data-stu-id="979e4-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="979e4-238">由于 Azure 应用程序创建过程，配置源租户（仅目标租户）不需要全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="979e4-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="979e4-239">将目录更改为脚本位置或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。</span><span class="sxs-lookup"><span data-stu-id="979e4-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="979e4-240">运行具有以下必需参数和值的脚本。</span><span class="sxs-lookup"><span data-stu-id="979e4-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="979e4-241">参数</span><span class="sxs-lookup"><span data-stu-id="979e4-241">Parameter</span></span> | <span data-ttu-id="979e4-242">值</span><span class="sxs-lookup"><span data-stu-id="979e4-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="979e4-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="979e4-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="979e4-244">源租户为迁移范围内标识/邮箱创建的启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="979e4-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="979e4-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="979e4-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="979e4-246">源租户域名，如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-246">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="979e4-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="979e4-247">-ApplicationId</span></span> | <span data-ttu-id="979e4-248">Azure 应用程序 ID (用于) 的应用程序的 GUID 和 GUID。</span><span class="sxs-lookup"><span data-stu-id="979e4-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="979e4-249">可通过 Azure 门户获取的应用程序 ID (Azure AD、企业应用程序、应用名称、应用程序 ID) 包含在邀请电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="979e4-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="979e4-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="979e4-250">-TargetTenantDomain</span></span> | <span data-ttu-id="979e4-251">目标租户域名，如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-251">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="979e4-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="979e4-252">-TargetTenantId</span></span> | <span data-ttu-id="979e4-253">目标租户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="979e4-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="979e4-254">例如，contoso 租户的 Azure AD onmicrosoft.com \. ID。</span><span class="sxs-lookup"><span data-stu-id="979e4-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="979e4-255">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="979e4-256">源管理员设置现已完成！</span><span class="sxs-lookup"><span data-stu-id="979e4-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="979e4-257">验证设置</span><span class="sxs-lookup"><span data-stu-id="979e4-257">Verify setup</span></span>

<span data-ttu-id="979e4-258">验证目标中的源和目标租户以及迁移终结点中的组织关系是否创建成功。</span><span class="sxs-lookup"><span data-stu-id="979e4-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="979e4-259">目标租户</span><span class="sxs-lookup"><span data-stu-id="979e4-259">Target tenant</span></span>

<span data-ttu-id="979e4-260">**组织关系**</span><span class="sxs-lookup"><span data-stu-id="979e4-260">**Organization relationship**</span></span>

<span data-ttu-id="979e4-261">验证已使用此命令创建和配置组织关系对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="979e4-262">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="979e4-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="979e4-263">**迁移终结点**</span><span class="sxs-lookup"><span data-stu-id="979e4-263">**Migration endpoint**</span></span>

<span data-ttu-id="979e4-264">验证已使用此命令创建和配置迁移终结点对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="979e4-265">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="979e4-266">源租户</span><span class="sxs-lookup"><span data-stu-id="979e4-266">Source tenant</span></span>

<span data-ttu-id="979e4-267">**组织关系**</span><span class="sxs-lookup"><span data-stu-id="979e4-267">**Organization relationship**</span></span>

<span data-ttu-id="979e4-268">验证已使用此命令创建和配置组织关系对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="979e4-269">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="979e4-270">验证安装脚本</span><span class="sxs-lookup"><span data-stu-id="979e4-270">Verify Setup Script</span></span>

<span data-ttu-id="979e4-271">如果在配置源租户或目标租户期间收到任何错误，可以运行位于 [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 上的 VerifySetup.ps1 脚本并查看输出。</span><span class="sxs-lookup"><span data-stu-id="979e4-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="979e4-272">下面是在目标租户上运行VerifySetup.ps1的示例：</span><span class="sxs-lookup"><span data-stu-id="979e4-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="979e4-273">下面是源租户上VerifySetup.ps1的示例：</span><span class="sxs-lookup"><span data-stu-id="979e4-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="979e4-274">将邮箱移回原始源</span><span class="sxs-lookup"><span data-stu-id="979e4-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="979e4-275">如果需要将邮箱移回原始源租户，则需要在新的源租户和新目标租户中运行相同的步骤和脚本集。</span><span class="sxs-lookup"><span data-stu-id="979e4-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="979e4-276">将更新或追加现有组织关系对象，而不是重新创建该对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="979e4-277">准备目标用户对象进行迁移</span><span class="sxs-lookup"><span data-stu-id="979e4-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="979e4-278">迁移的用户必须存在于目标租户和 Exchange Online 系统中 (MailUsers) 使用特定属性进行标记以启用跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="979e4-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="979e4-279">对于未在目标租户中正确设置的用户，系统移动将失败。</span><span class="sxs-lookup"><span data-stu-id="979e4-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="979e4-280">以下部分详细介绍了目标租户的 MailUser 对象要求。</span><span class="sxs-lookup"><span data-stu-id="979e4-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="979e4-281">先决条件</span><span class="sxs-lookup"><span data-stu-id="979e4-281">Prerequisites</span></span>
  
<span data-ttu-id="979e4-282">必须确保在目标组织中设置以下对象和属性。</span><span class="sxs-lookup"><span data-stu-id="979e4-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="979e4-283">对于从源组织移动的任何邮箱，必须在目标组织中设置 MailUser 对象：</span><span class="sxs-lookup"><span data-stu-id="979e4-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="979e4-284">目标 MailUser 必须具有源邮箱中的这些属性或分配有新的 User 对象：</span><span class="sxs-lookup"><span data-stu-id="979e4-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="979e4-285">ExchangeGUID (源到目标邮箱的直接) – 邮箱 GUID 必须匹配。</span><span class="sxs-lookup"><span data-stu-id="979e4-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="979e4-286">如果目标对象上不存在移动过程，则移动过程将不会继续进行。</span><span class="sxs-lookup"><span data-stu-id="979e4-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="979e4-287">ArchiveGUID (源到目标用户) – 存档 GUID 必须匹配。</span><span class="sxs-lookup"><span data-stu-id="979e4-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="979e4-288">如果目标对象上不存在移动过程，则移动过程将不会继续进行。</span><span class="sxs-lookup"><span data-stu-id="979e4-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="979e4-289"> (仅在源邮箱已启用存档) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="979e4-290">LegacyExchangeDN (流作为 proxyAddress， "x500： <LegacyExchangeDN> ") – LegacyExchangeDN 必须作为 x500： proxyAddress 存在于目标 MailUser 上。</span><span class="sxs-lookup"><span data-stu-id="979e4-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="979e4-291">如果目标对象上不存在移动过程，则移动过程将不会继续进行。</span><span class="sxs-lookup"><span data-stu-id="979e4-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="979e4-292">UserPrincipalName – UPN 将与用户的 NEW 标识或目标公司 (例如，user@northwindtraders.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="979e4-293">主 SMTP 地址 – 主 SMTP 地址将与用户的 NEW 公司地址 (例如，user@northwind.com) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="979e4-294">TargetAddress/ExternalEmailAddress – MailUser 将引用托管在源租户中的用户当前邮箱 (例如 user@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="979e4-295">分配此值时，请验证是否还分配了 PrimarySMTPAddress，否则此值将设置会导致移动失败的 PrimarySMTPAddress。</span><span class="sxs-lookup"><span data-stu-id="979e4-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="979e4-296">不能将源邮箱中的旧版 smtp 代理地址添加到目标 MailUser。</span><span class="sxs-lookup"><span data-stu-id="979e4-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="979e4-297">例如，无法在租户 contoso.com MEU 上 fabrikam.onmicrosoft.com MEU) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="979e4-298">域仅与一个 Azure AD 或 Exchange Online 租户关联。</span><span class="sxs-lookup"><span data-stu-id="979e4-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="979e4-299">示例 **目标** MailUser 对象：</span><span class="sxs-lookup"><span data-stu-id="979e4-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="979e4-300">属性</span><span class="sxs-lookup"><span data-stu-id="979e4-300">Attribute</span></span>             | <span data-ttu-id="979e4-301">值</span><span class="sxs-lookup"><span data-stu-id="979e4-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="979e4-302">Alias</span><span class="sxs-lookup"><span data-stu-id="979e4-302">Alias</span></span>                 | <span data-ttu-id="979e4-303">LaraN</span><span class="sxs-lookup"><span data-stu-id="979e4-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="979e4-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="979e4-304">RecipientType</span></span>         | <span data-ttu-id="979e4-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="979e4-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="979e4-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="979e4-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="979e4-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="979e4-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="979e4-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="979e4-308">UserPrincipalName</span></span>     | <span data-ttu-id="979e4-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="979e4-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="979e4-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="979e4-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="979e4-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="979e4-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="979e4-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="979e4-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="979e4-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="979e4-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="979e4-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="979e4-314">ExchangeGuid</span></span>          | <span data-ttu-id="979e4-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="979e4-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="979e4-316">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="979e4-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="979e4-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="979e4-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="979e4-318"> (FYDIBOHF23SPDLT) /cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="979e4-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="979e4-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="979e4-319">EmailAddresses</span></span>        | <span data-ttu-id="979e4-320">x500：/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="979e4-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="979e4-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="979e4-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="979e4-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="979e4-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="979e4-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="979e4-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="979e4-324">示例 **源** Mailbox 对象：</span><span class="sxs-lookup"><span data-stu-id="979e4-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="979e4-325">属性</span><span class="sxs-lookup"><span data-stu-id="979e4-325">Attribute</span></span>             | <span data-ttu-id="979e4-326">值</span><span class="sxs-lookup"><span data-stu-id="979e4-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="979e4-327">Alias</span><span class="sxs-lookup"><span data-stu-id="979e4-327">Alias</span></span>                 | <span data-ttu-id="979e4-328">LaraN</span><span class="sxs-lookup"><span data-stu-id="979e4-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="979e4-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="979e4-329">RecipientType</span></span>         | <span data-ttu-id="979e4-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="979e4-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="979e4-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="979e4-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="979e4-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="979e4-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="979e4-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="979e4-333">UserPrincipalName</span></span>     | <span data-ttu-id="979e4-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="979e4-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="979e4-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="979e4-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="979e4-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="979e4-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="979e4-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="979e4-337">ExchangeGuid</span></span>          | <span data-ttu-id="979e4-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="979e4-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="979e4-339">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="979e4-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="979e4-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="979e4-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="979e4-341"> (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="979e4-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="979e4-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="979e4-342">EmailAddresses</span></span>        | <span data-ttu-id="979e4-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="979e4-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="979e4-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="979e4-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="979e4-345">其他属性可能已包含在 Exchange 混合写回中。</span><span class="sxs-lookup"><span data-stu-id="979e4-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="979e4-346">如果没有，应包含它们。</span><span class="sxs-lookup"><span data-stu-id="979e4-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="979e4-347">msExchBlockedSendersHash – 将来自客户端的联机安全发件人和阻止的发件人数据写回本地 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="979e4-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="979e4-348">msExchSafeRecipientsHash – 将来自客户端的联机安全发件人和阻止的发件人数据写回本地 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="979e4-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="979e4-349">msExchSafeSendersHash – 将来自客户端的联机安全发件人和阻止的发件人数据写回本地 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="979e4-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="979e4-350">如果源邮箱位于 LitigationHold 中，且源邮箱"可恢复的项目"大小大于数据库默认 (30 GB) ，将不会继续移动，因为目标配额小于源邮箱大小。</span><span class="sxs-lookup"><span data-stu-id="979e4-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="979e4-351">您可以更新目标 MailUser 对象以将 ELC 邮箱标志从源环境转换到目标，这将触发目标系统将 MailUser 的配额扩展到 100 GB，从而允许移动到目标。</span><span class="sxs-lookup"><span data-stu-id="979e4-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="979e4-352">这些说明仅适用于运行 Azure AD Connect 的混合标识，因为标记 ELC 标志的命令不会向租户管理员公开。</span><span class="sxs-lookup"><span data-stu-id="979e4-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="979e4-353">示例 - 就像现在一样，无担保</span><span class="sxs-lookup"><span data-stu-id="979e4-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="979e4-354">此脚本假定与源邮箱 (连接，以获取源值) 和目标本地 Active Directory (标记 ADUser 对象) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="979e4-355">如果源已启用诉讼或单个项目恢复，则对目标帐户设置此项。</span><span class="sxs-lookup"><span data-stu-id="979e4-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="979e4-356">这会将目标帐户的垃圾站大小增加至 100 GB。</span><span class="sxs-lookup"><span data-stu-id="979e4-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="979e4-357">非混合目标租户可以在迁移之前修改 MailUsers 的"可恢复的项目"文件夹的配额，方法为运行以下命令以对 MailUser 对象启用诉讼保留，将配额增加至 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` GB：。</span><span class="sxs-lookup"><span data-stu-id="979e4-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="979e4-358">请注意，这适用于混合租户。</span><span class="sxs-lookup"><span data-stu-id="979e4-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="979e4-359">目标组织的用户必须获得适用于组织的适当 Exchange Online 订阅的许可。</span><span class="sxs-lookup"><span data-stu-id="979e4-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="979e4-360">您可以在邮箱移动之前应用许可证，但仅在使用 ExchangeGUID 和代理地址正确设置目标 MailUser 之后。</span><span class="sxs-lookup"><span data-stu-id="979e4-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="979e4-361">在应用 ExchangeGUID 之前应用许可证将导致在目标组织中设置新邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="979e4-362">对 Mailbox 或 MailUser 对象应用许可证时，会擦除所有 SMTP 类型 proxyAddresses，以确保 Exchange EmailAddresses 数组中仅包含已验证的域。</span><span class="sxs-lookup"><span data-stu-id="979e4-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="979e4-363">必须确保目标 MailUser 之前没有与 Source ExchangeGuid 不匹配的 ExchangeGuid。</span><span class="sxs-lookup"><span data-stu-id="979e4-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="979e4-364">如果目标 MEU 之前已获得 Exchange Online 许可并预配了邮箱，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="979e4-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="979e4-365">如果目标 MailUser 以前已获得许可，或者拥有与 Source ExchangeGuid 不匹配的 ExchangeGuid，则需要清理云 MEU。</span><span class="sxs-lookup"><span data-stu-id="979e4-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="979e4-366">对于这些云 MEUS，你可以运行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 。</span><span class="sxs-lookup"><span data-stu-id="979e4-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="979e4-367">此过程是不可逆的。</span><span class="sxs-lookup"><span data-stu-id="979e4-367">This process is irreversible.</span></span> <span data-ttu-id="979e4-368">如果对象具有 softDeleted 邮箱，则此时之后将无法还原。</span><span class="sxs-lookup"><span data-stu-id="979e4-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="979e4-369">但是，清除后，您可以将正确的 ExchangeGuid 同步到目标对象，MRS 将源邮箱连接到新创建的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="979e4-370"> (参数上引用 EHLO 博客。) </span><span class="sxs-lookup"><span data-stu-id="979e4-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="979e4-371">使用此命令查找以前是邮箱的对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="979e4-372">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="979e4-373">使用此命令清除软删除的邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="979e4-374">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="979e4-375">执行邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="979e4-375">Perform mailbox migrations</span></span>

<span data-ttu-id="979e4-376">跨租户 Exchange 邮箱迁移作为从目标租户启动的迁移批处理提交。</span><span class="sxs-lookup"><span data-stu-id="979e4-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="979e4-377">这类似于从 Exchange 本地迁移到 Microsoft 365 时，内部迁移批处理的运行方式。</span><span class="sxs-lookup"><span data-stu-id="979e4-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="979e4-378">创建迁移批处理</span><span class="sxs-lookup"><span data-stu-id="979e4-378">Create Migration batches</span></span>

<span data-ttu-id="979e4-379">下面是用于启动移动的迁移批处理 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="979e4-380">CSV 文件中的电子邮件地址必须是目标租户中指定的电子邮件地址，而不是源租户中指定的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="979e4-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="979e4-381">选择跨租户选项时，也支持从新的 Exchange 管理中心提交迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="979e4-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="979e4-382">更新本地 MailUsers</span><span class="sxs-lookup"><span data-stu-id="979e4-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="979e4-383">邮箱从源移动到目标之后，应确保使用新的 targetAddress 更新内部部署邮件用户（源和目标用户）。</span><span class="sxs-lookup"><span data-stu-id="979e4-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="979e4-384">在示例中，移动中使用的 targetDeliveryDomain contoso.onmicrosoft.com **。**</span><span class="sxs-lookup"><span data-stu-id="979e4-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="979e4-385">更新具有此 targetAddress 的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="979e4-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="979e4-386">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="979e4-386">Frequently asked questions</span></span>

<span data-ttu-id="979e4-387">**移动后是否需要更新源本地中的 RemoteMailboxes？**</span><span class="sxs-lookup"><span data-stu-id="979e4-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="979e4-388">是，当源租户邮箱移动到目标租户时，应更新源本地 (的 targetAddress (RemoteRoutingAddress/ExternalEmailAddress) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="979e4-389">虽然邮件路由可以遵循不同 targetAddresses 的多个邮件用户的引荐，但邮件用户的忙/闲查找必须面向邮箱用户的位置。</span><span class="sxs-lookup"><span data-stu-id="979e4-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="979e4-390">忙/闲查找不会追踪多个重定向。</span><span class="sxs-lookup"><span data-stu-id="979e4-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="979e4-391">**Teams 聊天文件夹内容是否跨租户迁移？**</span><span class="sxs-lookup"><span data-stu-id="979e4-391">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="979e4-392">否，Teams 聊天文件夹内容不会跨租户迁移。</span><span class="sxs-lookup"><span data-stu-id="979e4-392">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="979e4-393">**如何查看跨租户移动，而不是我的载入和离开移动？**</span><span class="sxs-lookup"><span data-stu-id="979e4-393">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="979e4-394">使用 `-flags` 参数。</span><span class="sxs-lookup"><span data-stu-id="979e4-394">Use the `-flags` parameter.</span></span> <span data-ttu-id="979e4-395">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-395">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="979e4-396">**能否提供用于复制测试中使用的属性的示例脚本？**</span><span class="sxs-lookup"><span data-stu-id="979e4-396">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="979e4-397">示例 - 就像现在一样，无担保</span><span class="sxs-lookup"><span data-stu-id="979e4-397">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="979e4-398">此脚本假定与源邮箱 (连接，以获取源值) 和目标本地 Active Directory 域服务 (以标记 ADUser) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-398">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="979e4-399">如果源已启用诉讼或单个项目恢复，则对目标帐户设置此项。</span><span class="sxs-lookup"><span data-stu-id="979e4-399">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="979e4-400">这会将目标帐户的垃圾站大小增加至 100 GB。</span><span class="sxs-lookup"><span data-stu-id="979e4-400">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="979e4-401">**移动使用邮箱后，如何访问第 1 天 Outlook？**</span><span class="sxs-lookup"><span data-stu-id="979e4-401">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="979e4-402">由于只有一个租户可以拥有一个域，因此邮箱移动完成后，以前的主 SMTPAddress 不会与目标租户中的用户关联;仅与新租户关联的域。</span><span class="sxs-lookup"><span data-stu-id="979e4-402">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="979e4-403">Outlook 使用用户新的 UPN 对服务进行身份验证，并且 Outlook 配置文件希望查找旧版主 SMTPAddress 以匹配目标系统中邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-403">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="979e4-404">由于旧地址不在目标系统中，Outlook 配置文件将不会连接以查找新移动的邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-404">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="979e4-405">对于此初始部署，用户将需要使用新的 UPN 主 SMTP 地址重新构建其配置文件，然后重新同步 OST 内容。</span><span class="sxs-lookup"><span data-stu-id="979e4-405">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="979e4-406">在批处理用户以完成时进行相应规划。</span><span class="sxs-lookup"><span data-stu-id="979e4-406">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="979e4-407">创建 Outlook 客户端配置文件以及将后续 OST 和 OAB 文件下载到客户端时，您需要考虑网络利用率和容量。</span><span class="sxs-lookup"><span data-stu-id="979e4-407">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="979e4-408">**我需要成为哪些 Exchange RBAC 角色的成员，以设置或完成跨租户移动？**</span><span class="sxs-lookup"><span data-stu-id="979e4-408">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="979e4-409">存在一个角色矩阵，这些角色基于执行邮箱移动时委派的职责假设。</span><span class="sxs-lookup"><span data-stu-id="979e4-409">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="979e4-410">目前，需要两个角色：</span><span class="sxs-lookup"><span data-stu-id="979e4-410">Currently, two roles are required:</span></span>  

- <span data-ttu-id="979e4-411">第一个角色用于建立将内容移入或移出租户/组织边界的授权的一次设置任务。</span><span class="sxs-lookup"><span data-stu-id="979e4-411">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="979e4-412">由于将数据从组织控制中移出是所有公司的重要问题，因此，我们选择具有组织管理员 (OrgAdmin) 的最高分配角色。</span><span class="sxs-lookup"><span data-stu-id="979e4-412">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="979e4-413">此角色必须更改或设置一个新的 OrganizationRelationship，该关系定义远程组织的 -MailboxMoveCapability。</span><span class="sxs-lookup"><span data-stu-id="979e4-413">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="979e4-414">只有 OrgAdmin 可以更改 MailboxMoveCapability 设置，而 OrganizationRelationhip 上的其他属性也可由联合共享管理员进行管理。</span><span class="sxs-lookup"><span data-stu-id="979e4-414">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="979e4-415">执行实际移动命令的角色可以委派给较低级别的函数。</span><span class="sxs-lookup"><span data-stu-id="979e4-415">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="979e4-416">"移动邮箱"角色分配有使用 参数将邮箱移进组织或将邮箱移出组织 `-RemoteTenant` 的功能。</span><span class="sxs-lookup"><span data-stu-id="979e4-416">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="979e4-417">**如何确定为已转换为 MailUser 转换邮箱 (的邮箱上的 targetAddress) TargetDeliveryDomain (选择哪个 SMTP 地址) ？**</span><span class="sxs-lookup"><span data-stu-id="979e4-417">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="979e4-418">在通过匹配目标对象上的电子邮件地址 (proxyAddress) 转换为 MailUser 时，使用 MRS 在原始源邮箱上创建 targetAddress 移动。</span><span class="sxs-lookup"><span data-stu-id="979e4-418">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="979e4-419">该过程采用传入移动命令的 -TargetDeliveryDomain 值，然后在目标端检查该域的匹配代理。</span><span class="sxs-lookup"><span data-stu-id="979e4-419">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="979e4-420">当我们找到匹配项时，匹配的 proxyAddress 将用于在转换的邮箱上设置 ExternalEmailAddress (targetAddress) （现在 (MailUser) 对象）。</span><span class="sxs-lookup"><span data-stu-id="979e4-420">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="979e4-421">**邮箱权限如何转换？**</span><span class="sxs-lookup"><span data-stu-id="979e4-421">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="979e4-422">邮箱权限包括"代表发送"和"邮箱访问"：</span><span class="sxs-lookup"><span data-stu-id="979e4-422">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="979e4-423">代表用户 (AD：publicDelegates) 将具有用户邮箱访问权限的收件人的 DN 存储为代理。</span><span class="sxs-lookup"><span data-stu-id="979e4-423">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="979e4-424">此值存储在 Active Directory 中，当前不会作为邮箱转换的一部分移动。</span><span class="sxs-lookup"><span data-stu-id="979e4-424">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="979e4-425">如果源邮箱设置了 publicDelegates，则运行 在目标环境中完成 MEU 到邮箱转换后，您需要在目标邮箱上重新标记 publicDelegates。 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`</span><span class="sxs-lookup"><span data-stu-id="979e4-425">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="979e4-426">将主体和代理移动到目标系统时，邮箱中存储的邮箱权限将随邮箱一起移动。</span><span class="sxs-lookup"><span data-stu-id="979e4-426">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="979e4-427">例如，向用户TestUser_7租户中的邮箱TestUser_8 FullAccess SourceCompany.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-427">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="979e4-428">邮箱移动完成后，TargetCompany.onmicrosoft.com 目标目录中设置相同的权限。</span><span class="sxs-lookup"><span data-stu-id="979e4-428">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="979e4-429">对源租户和目标TestUser_7 *Get-MailboxPermission* 的示例如下所示。</span><span class="sxs-lookup"><span data-stu-id="979e4-429">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="979e4-430">Exchange cmdlet 相应地以源和目标作为前缀。</span><span class="sxs-lookup"><span data-stu-id="979e4-430">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="979e4-431">下面是移动之前邮箱权限输出的示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-431">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="979e4-432">下面是移动后邮箱权限输出的示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-432">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="979e4-433">不支持跨租户邮箱和日历权限。</span><span class="sxs-lookup"><span data-stu-id="979e4-433">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="979e4-434">必须将主体和代理组织到合并移动批处理中，以便同时从源租户转换这些连接的邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-434">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="979e4-435">**应向目标 MailUser 代理地址添加哪些 X500 代理以启用迁移？**</span><span class="sxs-lookup"><span data-stu-id="979e4-435">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="979e4-436">跨租户邮箱迁移要求将源邮箱对象的 LegacyExchangeDN 值标记为目标 MailUser 对象上的 x500 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="979e4-436">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="979e4-437">示例：</span><span class="sxs-lookup"><span data-stu-id="979e4-437">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="979e4-438">除了此 X500 代理之外，还需要将源中的邮箱的所有 X500 代理复制到目标中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-438">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="979e4-439">**如果移动不起作用，我在哪里开始疑难解答？**</span><span class="sxs-lookup"><span data-stu-id="979e4-439">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="979e4-440">首先运行位于 [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) VerifySetup.ps1脚本并查看输出。</span><span class="sxs-lookup"><span data-stu-id="979e4-440">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="979e4-441">下面是在目标租户上运行VerifySetup.ps1的示例：</span><span class="sxs-lookup"><span data-stu-id="979e4-441">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="979e4-442">下面是在源租户上运行VerifySetup.ps1的 eExample：</span><span class="sxs-lookup"><span data-stu-id="979e4-442">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="979e4-443">**源租户和目标租户能否使用相同的域名？**</span><span class="sxs-lookup"><span data-stu-id="979e4-443">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="979e4-444">不正确。</span><span class="sxs-lookup"><span data-stu-id="979e4-444">No.</span></span> <span data-ttu-id="979e4-445">源和目标租户域名必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="979e4-445">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="979e4-446">例如，域的源 contoso.com 和目标域 fourthcoffee.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-446">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="979e4-447">**共享邮箱是否移动且仍正常工作？**</span><span class="sxs-lookup"><span data-stu-id="979e4-447">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="979e4-448">是的，但我们仅保留存储权限，如以下文章所述：</span><span class="sxs-lookup"><span data-stu-id="979e4-448">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="979e4-449">Microsoft Docs |在 Exchange Online 中管理收件人的权限</span><span class="sxs-lookup"><span data-stu-id="979e4-449">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="979e4-450">Microsoft 支持|如何在 Office 365 专用中授予 Exchange 和 Outlook 邮箱权限</span><span class="sxs-lookup"><span data-stu-id="979e4-450">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="979e4-451">**是否要求 Azure 密钥保管库以及何时进行事务？**</span><span class="sxs-lookup"><span data-stu-id="979e4-451">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="979e4-452">是的，Azure 订阅需要使用密钥保管库来存储证书以授权迁移。</span><span class="sxs-lookup"><span data-stu-id="979e4-452">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="979e4-453">与使用用户名或密码&源进行身份验证的加入迁移不同，跨租户邮箱迁移使用 OAuth 和此证书作为密码/凭据。</span><span class="sxs-lookup"><span data-stu-id="979e4-453">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="979e4-454">必须在所有邮箱迁移中维护对密钥保管库的访问，因为密钥保管库在迁移开始时和结束时访问一次，在增量同步期间每 24 小时访问一次。</span><span class="sxs-lookup"><span data-stu-id="979e4-454">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="979e4-455">你可以在此处查看 AKV 成本 [计算详细信息]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="979e4-455">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="979e4-456">**您是否对批处理有任何建议？**</span><span class="sxs-lookup"><span data-stu-id="979e4-456">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="979e4-457">每个批次不要超过 2000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-457">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="979e4-458">强烈建议在截止日期前两周提交批处理，因为同步期间对最终用户没有影响。如果需要超过 50，000 个邮箱数量的指南，可以联系工程反馈通讯组列表，crosstenantmigrationpreview@service.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="979e4-458">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="979e4-459">**如果我将服务加密与客户密钥一同使用，该做什么？**</span><span class="sxs-lookup"><span data-stu-id="979e4-459">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="979e4-460">移动之前将解密邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-460">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="979e4-461">如果仍然需要客户密钥，请确保在目标租户中配置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="979e4-461">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="979e4-462">有关详细信息 [，](../compliance/customer-key-overview.md) 请参阅此处。</span><span class="sxs-lookup"><span data-stu-id="979e4-462">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="979e4-463">**估计的迁移时间是什么？**</span><span class="sxs-lookup"><span data-stu-id="979e4-463">**What is the estimated migration time?**</span></span>

<span data-ttu-id="979e4-464">为了帮助您规划迁移，此处的表显示了有关[](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)何时应完成批量邮箱迁移或单个迁移的准则。</span><span class="sxs-lookup"><span data-stu-id="979e4-464">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="979e4-465">这些估计基于以前客户迁移的数据分析。</span><span class="sxs-lookup"><span data-stu-id="979e4-465">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="979e4-466">由于每个环境都是唯一的，因此确切的迁移速度可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="979e4-466">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="979e4-467">请记住，此功能当前处于预览阶段，SLA 及任何适用的服务级别不适用于此功能的预览状态期间的任何性能或可用性问题。</span><span class="sxs-lookup"><span data-stu-id="979e4-467">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="979e4-468">已知问题</span><span class="sxs-lookup"><span data-stu-id="979e4-468">Known issues</span></span>  

-  <span data-ttu-id="979e4-469">**问题：无法迁移自动展开的存档。**</span><span class="sxs-lookup"><span data-stu-id="979e4-469">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="979e4-470">跨租户迁移功能支持迁移特定用户的主邮箱和存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="979e4-470">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="979e4-471">但是，如果源中的用户具有自动展开的存档（这意味着多个存档邮箱）无法迁移其他存档，并且应该会失败。</span><span class="sxs-lookup"><span data-stu-id="979e4-471">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="979e4-472">**问题：具有非拥有 smtp 代理的云邮件用户地址块 MRS 移动后台。**</span><span class="sxs-lookup"><span data-stu-id="979e4-472">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="979e4-473">创建目标租户 MailUser 对象时，必须确保所有 SMTP 代理地址都属于目标租户组织。</span><span class="sxs-lookup"><span data-stu-id="979e4-473">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="979e4-474">如果不属于本地租户的目标邮件用户上存在 SMTP 代理Address，则阻止 MailUser 到 Mailbox 的转换。</span><span class="sxs-lookup"><span data-stu-id="979e4-474">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="979e4-475">这是因为我们保证邮箱对象只能从租户对租户声明的域具有权威性 (域发送邮件) ：</span><span class="sxs-lookup"><span data-stu-id="979e4-475">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="979e4-476">使用 Azure AD Connect 从本地同步用户时，使用指向邮箱所在的源租户的 ExternalEmailAddress 预配本地 MailUser 对象 (laran@contoso.onmicrosoft.com) 并且将 PrimarySMTPAddress 标记为驻留在目标租户 (Lara.Newton@northwind.com) 中的域。</span><span class="sxs-lookup"><span data-stu-id="979e4-476">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="979e4-477">这些值将同步到租户，并设置相应的邮件用户并准备迁移。</span><span class="sxs-lookup"><span data-stu-id="979e4-477">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="979e4-478">此处显示了一个示例对象。</span><span class="sxs-lookup"><span data-stu-id="979e4-478">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="979e4-479">EmailAddresses / proxyAddresses *数组中不存在* contoso.onmicrosoft.com 地址。 </span><span class="sxs-lookup"><span data-stu-id="979e4-479">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="979e4-480">**问题：具有"外部"主 SMTP 地址的 MailUser 对象被修改/重置为"内部"公司声明的域**</span><span class="sxs-lookup"><span data-stu-id="979e4-480">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="979e4-481">MailUser 对象是指向非本地邮箱的指针。</span><span class="sxs-lookup"><span data-stu-id="979e4-481">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="979e4-482">对于跨租户邮箱迁移，从目标组织的角度看，我们使用 MailUser 对象表示源邮箱 () 或目标邮箱 (（从源组织的角度来看) ）。</span><span class="sxs-lookup"><span data-stu-id="979e4-482">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="979e4-483">MailUsers 将具有一个 ExternalEmailAddress (targetAddress) ，该地址指向实际邮箱 (ProxyTest@fabrikam.onmicrosoft.com) 的 smtp 地址和表示目录中邮箱用户的显示 SMTP 地址的 primarySMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="979e4-483">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="979e4-484">一些组织选择将主 SMTP 地址显示为外部 SMTP 地址，而不是本地租户拥有/验证的地址 (如 fabrikam.com，而不是 contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-484">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="979e4-485">但是，通过许可操作将 Exchange 服务计划对象应用于 MailUser 后，主 SMTP 地址将修改为本地组织验证的域 (contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="979e4-485">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="979e4-486">有两个可能的原因：</span><span class="sxs-lookup"><span data-stu-id="979e4-486">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="979e4-487">当任何 Exchange 服务计划应用于 MailUser 时，Azure AD 进程开始强制执行代理清理，以确保本地组织无法从另一个租户发送邮件、欺骗邮件或邮件。</span><span class="sxs-lookup"><span data-stu-id="979e4-487">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="979e4-488">如果本地组织未验证该地址，将删除具有这些服务计划的收件人对象上的任何 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="979e4-488">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="979e4-489">与示例中的情况一样，Fabikam.com 租户未验证 contoso.onmicrosoft.com 域，因此清理会删除该 fabrikam.com 域。</span><span class="sxs-lookup"><span data-stu-id="979e4-489">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="979e4-490">如果您希望在迁移之前或迁移后在 MailUser 上保留这些外部域，则需要更改迁移过程，以在移动完成后或移动之前去除许可证，以确保用户应用了预期的外部品牌。</span><span class="sxs-lookup"><span data-stu-id="979e4-490">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="979e4-491">您需要确保邮箱对象已正确许可，不会影响邮件服务。</span><span class="sxs-lookup"><span data-stu-id="979e4-491">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="979e4-492">删除邮件租户中 MailUser 上的服务 Contoso.onmicrosoft.com 脚本如下所示。</span><span class="sxs-lookup"><span data-stu-id="979e4-492">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="979e4-493">此处显示了分配的 ServicePlans 集的结果。</span><span class="sxs-lookup"><span data-stu-id="979e4-493">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="979e4-494">用户的 PrimarySMTPAddress 不再被清理。</span><span class="sxs-lookup"><span data-stu-id="979e4-494">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="979e4-495">the fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span><span class="sxs-lookup"><span data-stu-id="979e4-495">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="979e4-496">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="979e4-496">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="979e4-497">当 msExchRemoteRecipientType 设置为 8 (DeprovisionMailbox) 时，对于迁移到目标租户的本地 MailUsers，Azure 中的代理清理逻辑将删除非所有者域，将 primarySMTP 重置为拥有域。</span><span class="sxs-lookup"><span data-stu-id="979e4-497">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="979e4-498">通过清除本地 MailUser 中的 msExchRemoteRecipientType，代理清理逻辑将不再适用。</span><span class="sxs-lookup"><span data-stu-id="979e4-498">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="979e4-499">以下是包括 Exchange Online 的一整套可能的服务计划。</span><span class="sxs-lookup"><span data-stu-id="979e4-499">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="979e4-500">名称</span><span class="sxs-lookup"><span data-stu-id="979e4-500">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="979e4-501">高级电子数据展示存储 (500GB) </span><span class="sxs-lookup"><span data-stu-id="979e4-501">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="979e4-502">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="979e4-502">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="979e4-503">数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="979e4-503">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="979e4-504">Exchange Enterprise CAL Services (EOP、DLP) </span><span class="sxs-lookup"><span data-stu-id="979e4-504">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="979e4-505">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="979e4-505">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="979e4-506">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="979e4-506">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="979e4-507">Exchange Online (P1) </span><span class="sxs-lookup"><span data-stu-id="979e4-507">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="979e4-508">Exchange Online (计划 1) </span><span class="sxs-lookup"><span data-stu-id="979e4-508">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="979e4-509">Exchange Online（计划 2）</span><span class="sxs-lookup"><span data-stu-id="979e4-509">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="979e4-510">适用于 Exchange Online 的 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="979e4-510">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="979e4-511">适用于 Exchange Server 的 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="979e4-511">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="979e4-512">Exchange Online 非活动用户加载项</span><span class="sxs-lookup"><span data-stu-id="979e4-512">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="979e4-513">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="979e4-513">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="979e4-514">Exchange Online 多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="979e4-514">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="979e4-515">Exchange Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="979e4-515">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="979e4-516">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="979e4-516">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="979e4-517">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="979e4-517">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="979e4-518">信息屏障</span><span class="sxs-lookup"><span data-stu-id="979e4-518">Information Barriers</span></span>                              |
   | <span data-ttu-id="979e4-519">适用于 Office 365 的信息保护 - 高级版</span><span class="sxs-lookup"><span data-stu-id="979e4-519">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="979e4-520">适用于 Office 365 的信息保护 - 标准版</span><span class="sxs-lookup"><span data-stu-id="979e4-520">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="979e4-521">MyAnalytics 的见解</span><span class="sxs-lookup"><span data-stu-id="979e4-521">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="979e4-522">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="979e4-522">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="979e4-523">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="979e4-523">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="979e4-524">Microsoft 商业中心</span><span class="sxs-lookup"><span data-stu-id="979e4-524">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="979e4-525">Microsoft MyAnalytics（完整版）</span><span class="sxs-lookup"><span data-stu-id="979e4-525">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="979e4-526">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="979e4-526">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="979e4-527">Microsoft Defender for Office 365 (计划 1) </span><span class="sxs-lookup"><span data-stu-id="979e4-527">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="979e4-528">Microsoft Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="979e4-528">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="979e4-529">Office 365 特权访问管理</span><span class="sxs-lookup"><span data-stu-id="979e4-529">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="979e4-530">Office 365 中的高级加密</span><span class="sxs-lookup"><span data-stu-id="979e4-530">Premium Encryption in Office 365</span></span>                  |
