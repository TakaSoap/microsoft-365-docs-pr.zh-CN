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
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="179c3-103">跨租户邮箱迁移 (预览) </span><span class="sxs-lookup"><span data-stu-id="179c3-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="179c3-104">以前，当 Exchange Online 租户需要将邮箱移动到同一 Exchange Online 服务中的另一个租户时，他们必须将其完全离开本地，然后载入新租户。</span><span class="sxs-lookup"><span data-stu-id="179c3-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="179c3-105">借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="179c3-106">这无需离开和载入邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="179c3-107">通常，在合并或资产重组期间，需要能够将用户和内容移动到新租户。</span><span class="sxs-lookup"><span data-stu-id="179c3-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="179c3-108">当目标租户管理员执行移动时，这称为拉取移动，类似于本地到云载入迁移。</span><span class="sxs-lookup"><span data-stu-id="179c3-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="179c3-109">跨租户 Exchange 邮箱移动由租户管理员完全自助服务，使用已知的接口，这些接口可以编写脚本到将用户转换到其新组织所需的较大工作流中。</span><span class="sxs-lookup"><span data-stu-id="179c3-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="179c3-110">管理员可以使用可通过移动邮箱管理角色使用的 `New-MigrationBatch` cmdlet 执行跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="179c3-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="179c3-111">移动过程包括邮箱同步和最终完成期间租户授权检查。</span><span class="sxs-lookup"><span data-stu-id="179c3-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="179c3-112">迁移的用户必须作为 MailUsers 存在于目标租户 Exchange Online 系统中，并带有特定属性标记才能启用跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="179c3-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="179c3-113">对于未在目标租户中正确设置的用户，系统移动将失败。</span><span class="sxs-lookup"><span data-stu-id="179c3-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="179c3-114">移动完成后，源系统邮箱将转换为 MailUser，并且目标地址 (显示为 Exchange) 中的 ExternalEmailAddress，并标记目标租户的路由地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="179c3-115">此过程将旧版 MailUser 保留到源租户中，并允许共存和邮件路由一段时间。</span><span class="sxs-lookup"><span data-stu-id="179c3-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="179c3-116">当业务流程允许时，源租户可能会删除源 MailUser 或将其转换为邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="179c3-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="179c3-117">仅混合或云中的租户或两者的任意组合都支持跨租户 Exchange 邮箱迁移。</span><span class="sxs-lookup"><span data-stu-id="179c3-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="179c3-118">本文介绍跨租户邮箱移动的过程，并提供有关如何为内容移动准备源租户和目标租户的指导。</span><span class="sxs-lookup"><span data-stu-id="179c3-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="179c3-119">准备源租户和目标租户</span><span class="sxs-lookup"><span data-stu-id="179c3-119">Preparing source and target tenants</span></span>

<span data-ttu-id="179c3-120">跨租户 Exchange 邮箱迁移功能需要跨租户迁移的授权和范围。</span><span class="sxs-lookup"><span data-stu-id="179c3-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="179c3-121">使用 Azure 企业应用程序和密钥保管库存储解决方案，租户管理员现在能够管理从一个租户到另一个租户的 Exchange Online 邮箱迁移的授权和范围。</span><span class="sxs-lookup"><span data-stu-id="179c3-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="179c3-122">跨租户邮箱移动支持邀请和同意模型，以在 Azure AD (Azure AD) 应用程序，用于在租户对之间进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="179c3-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="179c3-123">还需要其他组件，如组织关系和迁移终结点。</span><span class="sxs-lookup"><span data-stu-id="179c3-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="179c3-124">本节不包含在目标目录中准备 MailUser 用户对象所需的特定步骤，也不包括提交迁移批处理的示例命令。</span><span class="sxs-lookup"><span data-stu-id="179c3-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="179c3-125">请参阅" [准备目标用户对象以迁移此信息](#prepare-target-user-objects-for-migration) "。</span><span class="sxs-lookup"><span data-stu-id="179c3-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="179c3-126">先决条件</span><span class="sxs-lookup"><span data-stu-id="179c3-126">Prerequisites</span></span>

<span data-ttu-id="179c3-127">跨租户邮箱移动功能需要 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) 建立特定于租户对的 Azure 应用程序，以安全存储和访问用于对邮箱从一个租户迁移到另一个租户进行身份验证和授权迁移的证书/密码，从而删除在租户之间共享证书/密码的任何要求。</span><span class="sxs-lookup"><span data-stu-id="179c3-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="179c3-128">在启动之前，请确保你拥有运行部署脚本的必要权限，以便配置 Azure Key Vault、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。</span><span class="sxs-lookup"><span data-stu-id="179c3-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="179c3-129">通常，全局管理员有权执行所有配置步骤。</span><span class="sxs-lookup"><span data-stu-id="179c3-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="179c3-130">此外，在运行安装程序之前，源租户中需要启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="179c3-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="179c3-131">这些组用于将邮箱列表的范围从源租户 (有时称为资源) 租户移动到目标租户。</span><span class="sxs-lookup"><span data-stu-id="179c3-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="179c3-132">这允许源租户管理员限制或限定需要移动的特定邮箱集，以防止迁移非预期用户。</span><span class="sxs-lookup"><span data-stu-id="179c3-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="179c3-133">不支持嵌套组。</span><span class="sxs-lookup"><span data-stu-id="179c3-133">Nested groups are not supported.</span></span>

<span data-ttu-id="179c3-134">你还需要与受信任的合作伙伴公司通信 (将邮箱移动到其) 以获取其 Microsoft 365 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="179c3-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="179c3-135">此租户 ID 用于"组织关系" `DomainName` 字段。</span><span class="sxs-lookup"><span data-stu-id="179c3-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="179c3-136">若要获取订阅的租户 ID，请登录到 Microsoft 365 管理中心并转到 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="179c3-137">单击租户 ID 属性的复制图标以将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="179c3-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="179c3-138">下面是该过程的工作方式。</span><span class="sxs-lookup"><span data-stu-id="179c3-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="邮箱迁移的租户准备。":::

<span data-ttu-id="179c3-140">[请参阅此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。</span><span class="sxs-lookup"><span data-stu-id="179c3-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="179c3-141">准备租户</span><span class="sxs-lookup"><span data-stu-id="179c3-141">Prepare tenants</span></span>

<span data-ttu-id="179c3-142">在高级别上，执行安装脚本时将执行以下配置操作。</span><span class="sxs-lookup"><span data-stu-id="179c3-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="179c3-143">准备目标租户：</span><span class="sxs-lookup"><span data-stu-id="179c3-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="179c3-144">如果未提供现有 Azure 资源组，则使用 SCRIPT (创建一) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="179c3-145">如果未提供现有密钥保管库，则使用 SCRIPT (创建一) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="179c3-146">为 SCRIPT (Office 365 Exchange Online 邮箱迁移应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="179c3-147">如果指定了用于 (或现有证书) 一个新证书，以将密码 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="179c3-148">将创建一个新的 Azure AD 应用程序 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="179c3-149">证书/密码将上载到迁移应用程序 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="179c3-150">邮箱迁移权限分配给 SCRIPT (应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="179c3-151">部署脚本将暂停，直到目标管理员同意使用 SCRIPT 脚本 (自己的) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="179c3-152">目标租户管理员同意向应用程序授予的权限 (手动) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="179c3-153">组织关系将创建到目标租户 (SCRIPT) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="179c3-154">创建迁移终结点以将邮箱拉至 SCRIPT (目标) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="179c3-155">准备源租户：</span><span class="sxs-lookup"><span data-stu-id="179c3-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="179c3-156">源租户管理员接受来自手动迁移目标租户 (邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="179c3-157">源租户管理员在租户中创建一个启用邮件的安全组，以包含允许迁移应用程序在 MANUAL (移动的) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="179c3-158">创建与目标租户的组织关系，指定邮箱迁移应用程序应用于 OAuth 验证，以接受 SCRIPT (移动) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="179c3-159">目标租户管理员的分步说明</span><span class="sxs-lookup"><span data-stu-id="179c3-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="179c3-160">从 [gitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview)SetupCrossTenantRelationshipForTargetTenant.ps1下载目标租户安装程序的脚本。</span><span class="sxs-lookup"><span data-stu-id="179c3-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="179c3-161">将脚本 (SetupCrossTenantRelationshipForTargetTenant.ps1) 保存到要执行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="179c3-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="179c3-162">创建到 Exchange Online 目标租户的远程 PowerShell 连接。</span><span class="sxs-lookup"><span data-stu-id="179c3-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="179c3-163">同样，请确保你拥有运行部署脚本的必要权限，以便配置 Azure 密钥保管库存储和证书、移动邮箱应用程序、EXO 迁移终结点和 EXO 组织关系。</span><span class="sxs-lookup"><span data-stu-id="179c3-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="179c3-164">将文件文件夹目录更改为脚本位置或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。</span><span class="sxs-lookup"><span data-stu-id="179c3-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="179c3-165">运行具有以下参数和值的脚本。</span><span class="sxs-lookup"><span data-stu-id="179c3-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="179c3-166">参数</span><span class="sxs-lookup"><span data-stu-id="179c3-166">Parameter</span></span> | <span data-ttu-id="179c3-167">值</span><span class="sxs-lookup"><span data-stu-id="179c3-167">Value</span></span> | <span data-ttu-id="179c3-168">必需或可选</span><span class="sxs-lookup"><span data-stu-id="179c3-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="179c3-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="179c3-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="179c3-170">目标租户域，如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="179c3-170">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="179c3-171">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-171">Required</span></span> |
    | <span data-ttu-id="179c3-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="179c3-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="179c3-173">源租户域，例如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="179c3-173">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="179c3-174">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-174">Required</span></span> |
    | <span data-ttu-id="179c3-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="179c3-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="179c3-176">源租户管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="179c3-177">这是将同意使用从目标管理员发送的邮箱迁移应用程序的源租户管理员。这是将接收应用程序的电子邮件邀请的管理员。</span><span class="sxs-lookup"><span data-stu-id="179c3-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="179c3-178">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-178">Required</span></span> |
    | <span data-ttu-id="179c3-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="179c3-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="179c3-180">源租户组织 ID (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="179c3-181">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-181">Required</span></span> |
    | <span data-ttu-id="179c3-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="179c3-182">-SubscriptionId</span></span>                             | <span data-ttu-id="179c3-183">用于创建资源的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="179c3-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="179c3-184">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-184">Required</span></span> |
    | <span data-ttu-id="179c3-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="179c3-185">-ResourceGroup</span></span>                              | <span data-ttu-id="179c3-186">包含或将包含密钥保管库的 Azure 资源组名称。</span><span class="sxs-lookup"><span data-stu-id="179c3-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="179c3-187">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-187">Required</span></span> |
    | <span data-ttu-id="179c3-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="179c3-188">-KeyVaultName</span></span>                               | <span data-ttu-id="179c3-189">将存储邮箱迁移应用程序证书/密码的 Azure Key Vault 实例。</span><span class="sxs-lookup"><span data-stu-id="179c3-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="179c3-190">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-190">Required</span></span> |
    | <span data-ttu-id="179c3-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="179c3-191">-CertificateName</span></span>                            | <span data-ttu-id="179c3-192">在密钥保管库中生成或搜索证书时证书名称。</span><span class="sxs-lookup"><span data-stu-id="179c3-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="179c3-193">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-193">Required</span></span> |
    | <span data-ttu-id="179c3-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="179c3-194">-CertificateSubject</span></span>                         | <span data-ttu-id="179c3-195">Azure 密钥保管库证书主题名称，例如 CN=contoso_fabrikam。</span><span class="sxs-lookup"><span data-stu-id="179c3-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="179c3-196">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-196">Required</span></span> |
    | <span data-ttu-id="179c3-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="179c3-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="179c3-198">要用于已创建的邮件迁移应用程序。</span><span class="sxs-lookup"><span data-stu-id="179c3-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="179c3-199">可选</span><span class="sxs-lookup"><span data-stu-id="179c3-199">Optional</span></span> |
    | <span data-ttu-id="179c3-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="179c3-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="179c3-201">为邮箱迁移应用程序（如 Exchange 或 MSGraph (Exchange）授予移动邮箱所需的权限，MSGraph 用于使用此应用程序向资源租户邮箱发送同意链接) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="179c3-202">必需</span><span class="sxs-lookup"><span data-stu-id="179c3-202">Required</span></span> |
    | <span data-ttu-id="179c3-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="179c3-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="179c3-204">用于使用为迁移创建的应用程序的参数，用于向源租户管理员发送同意链接邀请。如果不存在，将提示目标管理员的凭据连接到 Azure 邀请管理器，并作为目标管理员发送邀请。</span><span class="sxs-lookup"><span data-stu-id="179c3-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="179c3-205">可选</span><span class="sxs-lookup"><span data-stu-id="179c3-205">Optional</span></span> |
    | <span data-ttu-id="179c3-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="179c3-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="179c3-207">存储密钥保管库审核日志的存储帐户。</span><span class="sxs-lookup"><span data-stu-id="179c3-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="179c3-208">可选</span><span class="sxs-lookup"><span data-stu-id="179c3-208">Optional</span></span> |
    | <span data-ttu-id="179c3-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="179c3-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="179c3-210">包含用于存储密钥保管库审核日志的存储帐户的资源组。</span><span class="sxs-lookup"><span data-stu-id="179c3-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="179c3-211">可选</span><span class="sxs-lookup"><span data-stu-id="179c3-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="179c3-212">请确保在运行脚本之前已安装 Azure AD PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="179c3-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="179c3-213">有关安装 ![ 步骤， ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) 请参阅此处</span><span class="sxs-lookup"><span data-stu-id="179c3-213">Please refer to ![here](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="179c3-214">脚本将暂停，并要求您接受或同意在此过程期间创建的 Exchange 邮箱迁移应用程序。</span><span class="sxs-lookup"><span data-stu-id="179c3-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="179c3-215">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-215">Here is an example.</span></span>

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

7. <span data-ttu-id="179c3-216">远程 PowerShell 会话中将显示 URL。</span><span class="sxs-lookup"><span data-stu-id="179c3-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="179c3-217">复制为租户许可提供的链接，并将其粘贴到 Web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="179c3-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="179c3-218">使用全局管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="179c3-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="179c3-219">显示以下屏幕时，选择"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="179c3-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="&quot;接受权限&quot;对话框":::

9. <span data-ttu-id="179c3-221">切换回远程 PowerShell 会话并按 Enter 继续。</span><span class="sxs-lookup"><span data-stu-id="179c3-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="179c3-222">该脚本将配置其余的设置对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="179c3-223">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="179c3-224">目标管理员设置现已完成！</span><span class="sxs-lookup"><span data-stu-id="179c3-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="179c3-225">源租户管理员的分步说明</span><span class="sxs-lookup"><span data-stu-id="179c3-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="179c3-226">以目标管理员在设置过程中指定的 -ResourceTenantAdminEmail 登录邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="179c3-227">从目标租户查找电子邮件邀请，然后选择" **开始"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="179c3-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="你已被邀请对话框":::

2. <span data-ttu-id="179c3-229">选择 **"** 接受"接受邀请。</span><span class="sxs-lookup"><span data-stu-id="179c3-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="接受权限的对话框":::

   > [!NOTE]
   > <span data-ttu-id="179c3-231">如果未收到此电子邮件或找不到此电子邮件，则为目标租户管理员提供直接 URL，可提供给你接受邀请。</span><span class="sxs-lookup"><span data-stu-id="179c3-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="179c3-232">URL 应输入目标租户管理员的远程 PowerShell 会话的脚本中。</span><span class="sxs-lookup"><span data-stu-id="179c3-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="179c3-233">在 Microsoft 365 管理中心或远程 PowerShell 会话中，创建一个或多个启用邮件的安全组，以控制目标租户允许的邮箱列表，以将 () 从源租户移动到目标租户。</span><span class="sxs-lookup"><span data-stu-id="179c3-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="179c3-234">无需提前填充此组，但必须至少提供一个组，以运行脚本 (安装) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="179c3-235">不支持嵌套组。</span><span class="sxs-lookup"><span data-stu-id="179c3-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="179c3-236">从 gitHub SetupCrossTenantRelationshipForTargetResource.ps1下载源租户设置的脚本 [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) ：.</span><span class="sxs-lookup"><span data-stu-id="179c3-236">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="179c3-237">使用 Exchange 管理员权限创建到源租户的远程 PowerShell 连接。</span><span class="sxs-lookup"><span data-stu-id="179c3-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="179c3-238">由于 Azure 应用程序创建过程，配置源租户（仅目标租户）不需要全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="179c3-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="179c3-239">将目录更改为脚本位置或验证脚本当前是否保存到远程 PowerShell 会话中当前的位置。</span><span class="sxs-lookup"><span data-stu-id="179c3-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="179c3-240">运行具有以下必需参数和值的脚本。</span><span class="sxs-lookup"><span data-stu-id="179c3-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="179c3-241">参数</span><span class="sxs-lookup"><span data-stu-id="179c3-241">Parameter</span></span> | <span data-ttu-id="179c3-242">值</span><span class="sxs-lookup"><span data-stu-id="179c3-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="179c3-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="179c3-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="179c3-244">源租户为迁移范围内标识/邮箱创建的启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="179c3-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="179c3-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="179c3-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="179c3-246">源租户域名，例如 fabrikam \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="179c3-246">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="179c3-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="179c3-247">-ApplicationId</span></span> | <span data-ttu-id="179c3-248">Azure 应用程序 ID (用于) 的应用程序的 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="179c3-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="179c3-249">可通过 Azure 门户获取的应用程序 ID (Azure AD、企业应用程序、应用名称、) ID 或包含在邀请电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="179c3-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="179c3-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="179c3-250">-TargetTenantDomain</span></span> | <span data-ttu-id="179c3-251">目标租户域名，如 contoso \. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="179c3-251">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="179c3-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="179c3-252">-TargetTenantId</span></span> | <span data-ttu-id="179c3-253">目标租户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="179c3-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="179c3-254">例如，contoso 租户的 Azure AD \. onmicrosoft.com ID。</span><span class="sxs-lookup"><span data-stu-id="179c3-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="179c3-255">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="179c3-256">源管理员设置现已完成！</span><span class="sxs-lookup"><span data-stu-id="179c3-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="179c3-257">验证设置</span><span class="sxs-lookup"><span data-stu-id="179c3-257">Verify setup</span></span>

<span data-ttu-id="179c3-258">验证目标中的源租户和目标租户以及迁移终结点中的组织关系是否成功创建。</span><span class="sxs-lookup"><span data-stu-id="179c3-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="179c3-259">目标租户</span><span class="sxs-lookup"><span data-stu-id="179c3-259">Target tenant</span></span>

<span data-ttu-id="179c3-260">**组织关系**</span><span class="sxs-lookup"><span data-stu-id="179c3-260">**Organization relationship**</span></span>

<span data-ttu-id="179c3-261">验证已使用此命令创建和配置组织关系对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="179c3-262">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="179c3-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="179c3-263">**迁移终结点**</span><span class="sxs-lookup"><span data-stu-id="179c3-263">**Migration endpoint**</span></span>

<span data-ttu-id="179c3-264">验证已使用此命令创建和配置迁移终结点对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="179c3-265">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="179c3-266">源租户</span><span class="sxs-lookup"><span data-stu-id="179c3-266">Source tenant</span></span>

<span data-ttu-id="179c3-267">**组织关系**</span><span class="sxs-lookup"><span data-stu-id="179c3-267">**Organization relationship**</span></span>

<span data-ttu-id="179c3-268">验证已使用此命令创建和配置组织关系对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="179c3-269">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="179c3-270">将邮箱移回原始源</span><span class="sxs-lookup"><span data-stu-id="179c3-270">Move mailboxes back to the original source</span></span>

<span data-ttu-id="179c3-271">如果需要将邮箱移回原始源租户，则需要在新的源租户和新目标租户中运行相同的步骤和脚本集。</span><span class="sxs-lookup"><span data-stu-id="179c3-271">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="179c3-272">将更新或追加现有组织关系对象，而不是重新创建该对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-272">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="179c3-273">准备目标用户对象进行迁移</span><span class="sxs-lookup"><span data-stu-id="179c3-273">Prepare target user objects for migration</span></span>

<span data-ttu-id="179c3-274">迁移的用户必须存在于目标租户和 Exchange Online 系统中 (作为 MailUsers) 使用特定属性进行标记才能启用跨租户移动。</span><span class="sxs-lookup"><span data-stu-id="179c3-274">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="179c3-275">对于未在目标租户中正确设置的用户，系统移动将失败。</span><span class="sxs-lookup"><span data-stu-id="179c3-275">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="179c3-276">以下部分详细介绍了目标租户的 MailUser 对象要求。</span><span class="sxs-lookup"><span data-stu-id="179c3-276">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="179c3-277">先决条件</span><span class="sxs-lookup"><span data-stu-id="179c3-277">Prerequisites</span></span>
  
<span data-ttu-id="179c3-278">必须确保在目标组织中设置以下对象和属性。</span><span class="sxs-lookup"><span data-stu-id="179c3-278">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="179c3-279">对于从源组织移动的任何邮箱，必须在目标组织中设置 MailUser 对象：</span><span class="sxs-lookup"><span data-stu-id="179c3-279">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="179c3-280">目标 MailUser 必须具有源邮箱中的这些属性或分配有新的 User 对象：</span><span class="sxs-lookup"><span data-stu-id="179c3-280">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="179c3-281">ExchangeGUID (源到目标) 流 – 邮箱 GUID 必须匹配。</span><span class="sxs-lookup"><span data-stu-id="179c3-281">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="179c3-282">如果目标对象上不存在移动过程，则移动过程将不会继续进行。</span><span class="sxs-lookup"><span data-stu-id="179c3-282">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="179c3-283">ArchiveGUID (源到目标) 流 – 存档 GUID 必须匹配。</span><span class="sxs-lookup"><span data-stu-id="179c3-283">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="179c3-284">如果目标对象上不存在移动过程，则移动过程将不会继续进行。</span><span class="sxs-lookup"><span data-stu-id="179c3-284">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="179c3-285"> (仅在源邮箱已启用存档时，才需要) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-285">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="179c3-286">LegacyExchangeDN (作为 proxyAddress， "x500： <LegacyExchangeDN> ") – LegacyExchangeDN 必须作为 x500： proxyAddress 存在于目标 MailUser 上。</span><span class="sxs-lookup"><span data-stu-id="179c3-286">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="179c3-287">如果目标对象上不存在移动过程，则移动过程将不会继续进行。</span><span class="sxs-lookup"><span data-stu-id="179c3-287">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="179c3-288">UserPrincipalName – UPN 将符合用户的新标识或目标公司 (例如，user@northwindtraders.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-288">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="179c3-289">主 SMTP 地址 – 主 SMTP 地址与用户的新公司地址 (例如，user@northwind.com) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-289">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="179c3-290">TargetAddress/ExternalEmailAddress – MailUser 将引用托管在源租户中的用户当前邮箱 (例如user@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-290">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="179c3-291">分配此值时，请确认你已/正在分配 PrimarySMTPAddress，否则此值将设置会导致移动失败的 PrimarySMTPAddress。</span><span class="sxs-lookup"><span data-stu-id="179c3-291">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="179c3-292">无法将源邮箱中的旧版 smtp 代理地址添加到目标 MailUser。</span><span class="sxs-lookup"><span data-stu-id="179c3-292">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="179c3-293">例如，您无法在CONTOSO.COM租户对象中维护 MEU fabrikam.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-293">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="179c3-294">域仅与一个 Azure AD 或 Exchange Online 租户关联。</span><span class="sxs-lookup"><span data-stu-id="179c3-294">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="179c3-295">示例 **目标** MailUser 对象：</span><span class="sxs-lookup"><span data-stu-id="179c3-295">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="179c3-296">属性</span><span class="sxs-lookup"><span data-stu-id="179c3-296">Attribute</span></span>             | <span data-ttu-id="179c3-297">值</span><span class="sxs-lookup"><span data-stu-id="179c3-297">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="179c3-298">Alias</span><span class="sxs-lookup"><span data-stu-id="179c3-298">Alias</span></span>                 | <span data-ttu-id="179c3-299">LaraN</span><span class="sxs-lookup"><span data-stu-id="179c3-299">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="179c3-300">RecipientType</span><span class="sxs-lookup"><span data-stu-id="179c3-300">RecipientType</span></span>         | <span data-ttu-id="179c3-301">MailUser</span><span class="sxs-lookup"><span data-stu-id="179c3-301">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="179c3-302">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="179c3-302">RecipientTypeDetails</span></span>  | <span data-ttu-id="179c3-303">MailUser</span><span class="sxs-lookup"><span data-stu-id="179c3-303">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="179c3-304">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="179c3-304">UserPrincipalName</span></span>     | <span data-ttu-id="179c3-305">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="179c3-305">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="179c3-306">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="179c3-306">PrimarySmtpAddress</span></span>    | <span data-ttu-id="179c3-307">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="179c3-307">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="179c3-308">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="179c3-308">ExternalEmailAddress</span></span>  | <span data-ttu-id="179c3-309">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="179c3-309">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="179c3-310">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="179c3-310">ExchangeGuid</span></span>          | <span data-ttu-id="179c3-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="179c3-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="179c3-312">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="179c3-312">LegacyExchangeDN</span></span>      | <span data-ttu-id="179c3-313">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="179c3-313">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="179c3-314"> (FYDIBOHF23SPDLT) /cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="179c3-314">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="179c3-315">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="179c3-315">EmailAddresses</span></span>        | <span data-ttu-id="179c3-316">x500：/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="179c3-316">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="179c3-317">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="179c3-317">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="179c3-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="179c3-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="179c3-319">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="179c3-319">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="179c3-320">示例 **源** 邮箱对象：</span><span class="sxs-lookup"><span data-stu-id="179c3-320">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="179c3-321">属性</span><span class="sxs-lookup"><span data-stu-id="179c3-321">Attribute</span></span>             | <span data-ttu-id="179c3-322">值</span><span class="sxs-lookup"><span data-stu-id="179c3-322">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="179c3-323">Alias</span><span class="sxs-lookup"><span data-stu-id="179c3-323">Alias</span></span>                 | <span data-ttu-id="179c3-324">LaraN</span><span class="sxs-lookup"><span data-stu-id="179c3-324">LaraN</span></span>                                                                    |
     | <span data-ttu-id="179c3-325">RecipientType</span><span class="sxs-lookup"><span data-stu-id="179c3-325">RecipientType</span></span>         | <span data-ttu-id="179c3-326">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="179c3-326">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="179c3-327">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="179c3-327">RecipientTypeDetails</span></span>  | <span data-ttu-id="179c3-328">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="179c3-328">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="179c3-329">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="179c3-329">UserPrincipalName</span></span>     | <span data-ttu-id="179c3-330">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="179c3-330">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="179c3-331">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="179c3-331">PrimarySmtpAddress</span></span>    | <span data-ttu-id="179c3-332">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="179c3-332">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="179c3-333">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="179c3-333">ExchangeGuid</span></span>          | <span data-ttu-id="179c3-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="179c3-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="179c3-335">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="179c3-335">LegacyExchangeDN</span></span>      | <span data-ttu-id="179c3-336">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="179c3-336">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="179c3-337"> (FYDIBOHF23SPDLT) /cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="179c3-337">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="179c3-338">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="179c3-338">EmailAddresses</span></span>        | <span data-ttu-id="179c3-339">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="179c3-339">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="179c3-340">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="179c3-340">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="179c3-341">其他属性可能已包含在 Exchange 混合写回中。</span><span class="sxs-lookup"><span data-stu-id="179c3-341">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="179c3-342">如果没有，应包含它们。</span><span class="sxs-lookup"><span data-stu-id="179c3-342">If not, they should be included.</span></span> 
   - <span data-ttu-id="179c3-343">msExchBlockedSendersHash – 将来自客户端的联机安全且阻止的发件人数据写回本地 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="179c3-343">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="179c3-344">msExchSafeRecipientsHash – 将联机安全且阻止的发件人数据从客户端写回本地 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="179c3-344">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="179c3-345">msExchSafeSendersHash – 将来自客户端的安全和阻止的发件人数据写回本地 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="179c3-345">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="179c3-346">如果源邮箱位于 LitigationHold 中，并且源邮箱"可恢复的项目"大小大于数据库默认 (30 GB) ，将不会继续移动，因为目标配额小于源邮箱大小。</span><span class="sxs-lookup"><span data-stu-id="179c3-346">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="179c3-347">您可以更新目标 MailUser 对象以将 ELC 邮箱标志从源环境转换到目标，这将触发目标系统将 MailUser 的配额扩展到 100 GB，从而允许移动到目标。</span><span class="sxs-lookup"><span data-stu-id="179c3-347">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="179c3-348">这些说明仅适用于运行 Azure AD Connect 的混合标识，因为标记 ELC 标志的命令不会向租户管理员公开。</span><span class="sxs-lookup"><span data-stu-id="179c3-348">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="179c3-349">示例 – 就目前来说，无担保</span><span class="sxs-lookup"><span data-stu-id="179c3-349">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="179c3-350">此脚本假定连接到源邮箱 (源值) 和目标本地 Active Directory (标记 ADUser 对象) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-350">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="179c3-351">如果源已启用诉讼或单个项目恢复，请对目标帐户进行此项设置。</span><span class="sxs-lookup"><span data-stu-id="179c3-351">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="179c3-352">这会将目标帐户的垃圾站大小增加至 100 GB。</span><span class="sxs-lookup"><span data-stu-id="179c3-352">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="179c3-353">非混合目标租户可以在迁移前修改 MailUsers 的"可恢复的项目"文件夹的配额，方法为运行以下命令以对 MailUser 对象启用诉讼保留，将配额增加至 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` GB：</span><span class="sxs-lookup"><span data-stu-id="179c3-353">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="179c3-354">请注意，这适用于混合租户。</span><span class="sxs-lookup"><span data-stu-id="179c3-354">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="179c3-355">目标组织的用户必须通过适用于组织的适当 Exchange Online 订阅获得许可。</span><span class="sxs-lookup"><span data-stu-id="179c3-355">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="179c3-356">您可以在邮箱移动之前应用许可证，但仅在使用 ExchangeGUID 和代理地址正确设置目标 MailUser 之后。</span><span class="sxs-lookup"><span data-stu-id="179c3-356">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="179c3-357">在应用 ExchangeGUID 之前应用许可证将导致在目标组织中设置新的邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-357">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="179c3-358">在邮箱或 MailUser 对象上应用许可证时，会擦除所有 SMTP 类型代理地址，以确保 Exchange EmailAddresses 数组中仅包含已验证的域。</span><span class="sxs-lookup"><span data-stu-id="179c3-358">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="179c3-359">必须确保目标 MailUser 之前没有与源 ExchangeGuid 不匹配的 ExchangeGuid。</span><span class="sxs-lookup"><span data-stu-id="179c3-359">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="179c3-360">如果目标 MEU 之前已获得 Exchange Online 许可并预配了邮箱，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="179c3-360">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="179c3-361">如果目标 MailUser 之前已授权或拥有与源 ExchangeGuid 不匹配的 ExchangeGuid，则需要清理云 MEU。</span><span class="sxs-lookup"><span data-stu-id="179c3-361">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="179c3-362">对于这些云 MEUS，你可以运行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 。</span><span class="sxs-lookup"><span data-stu-id="179c3-362">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="179c3-363">此过程是不可逆的。</span><span class="sxs-lookup"><span data-stu-id="179c3-363">This process is irreversible.</span></span> <span data-ttu-id="179c3-364">如果对象具有 softDeleted 邮箱，则在此时间点之后无法还原它。</span><span class="sxs-lookup"><span data-stu-id="179c3-364">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="179c3-365">但是，清除后，可以将正确的 ExchangeGuid 同步到目标对象，MRS 将源邮箱连接到新创建的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-365">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="179c3-366"> (新参数上参考 EHLO 博客) </span><span class="sxs-lookup"><span data-stu-id="179c3-366">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="179c3-367">使用此命令查找以前是邮箱的对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-367">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```

    <span data-ttu-id="179c3-368">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-368">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="179c3-369">使用此命令清除软删除的邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-369">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="179c3-370">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-370">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="179c3-371">执行邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="179c3-371">Perform mailbox migrations</span></span>

<span data-ttu-id="179c3-372">跨租户 Exchange 邮箱迁移作为从目标租户启动的迁移批处理提交。</span><span class="sxs-lookup"><span data-stu-id="179c3-372">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="179c3-373">这类似于从 Exchange 内部部署迁移到 Microsoft 365 时，就地迁移批处理的运行方式。</span><span class="sxs-lookup"><span data-stu-id="179c3-373">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="179c3-374">创建迁移批处理</span><span class="sxs-lookup"><span data-stu-id="179c3-374">Create Migration batches</span></span>

<span data-ttu-id="179c3-375">下面是开始移动的示例迁移批处理 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="179c3-375">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="179c3-376">CSV 文件中的电子邮件地址必须是目标租户中指定的地址，而不是源租户中指定的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-376">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="179c3-377">选择跨租户选项时，新 Exchange 管理中心也支持迁移批处理提交。</span><span class="sxs-lookup"><span data-stu-id="179c3-377">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="179c3-378">更新本地 MailUsers</span><span class="sxs-lookup"><span data-stu-id="179c3-378">Update on-premises MailUsers</span></span>

<span data-ttu-id="179c3-379">邮箱从源移动到目标之后，应确保使用新的 targetAddress 更新内部部署邮件用户（源和目标）。</span><span class="sxs-lookup"><span data-stu-id="179c3-379">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="179c3-380">在示例中，移动中使用的 targetDeliveryDomain **contoso.onmicrosoft.com。**</span><span class="sxs-lookup"><span data-stu-id="179c3-380">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="179c3-381">使用此 targetAddress 更新邮件用户。</span><span class="sxs-lookup"><span data-stu-id="179c3-381">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="179c3-382">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="179c3-382">Frequently asked questions</span></span>

<span data-ttu-id="179c3-383">**移动后，是否需要更新源本地中的 RemoteMailbox？**</span><span class="sxs-lookup"><span data-stu-id="179c3-383">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="179c3-384">是，当源租户邮箱移动到目标租户时，应更新源本地用户 (RemoteRoutingAddress/ExternalEmailAddress) targetAddress。</span><span class="sxs-lookup"><span data-stu-id="179c3-384">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="179c3-385">虽然邮件路由可以跨具有不同 targetAddresses 的多个邮件用户执行引用，但邮件用户的忙/闲查找必须面向邮箱用户的位置。</span><span class="sxs-lookup"><span data-stu-id="179c3-385">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="179c3-386">忙/闲查找不会追踪多个重定向。</span><span class="sxs-lookup"><span data-stu-id="179c3-386">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="179c3-387">**Teams 聊天文件夹内容是否跨租户迁移？**</span><span class="sxs-lookup"><span data-stu-id="179c3-387">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="179c3-388">否，Teams 聊天文件夹内容不会跨租户迁移。</span><span class="sxs-lookup"><span data-stu-id="179c3-388">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="179c3-389">**如何查看跨租户移动移动，而不是我的载入和载出移动？**</span><span class="sxs-lookup"><span data-stu-id="179c3-389">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="179c3-390">使用 `-flags` 参数。</span><span class="sxs-lookup"><span data-stu-id="179c3-390">Use the `-flags` parameter.</span></span> <span data-ttu-id="179c3-391">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-391">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="179c3-392">**能否提供用于复制测试中使用的属性的示例脚本？**</span><span class="sxs-lookup"><span data-stu-id="179c3-392">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="179c3-393">示例 – 就目前来说，无担保</span><span class="sxs-lookup"><span data-stu-id="179c3-393">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="179c3-394">此脚本假定与源邮箱 (连接，以获取源值) 和目标本地 Active Directory 域服务 (，以标记 ADUser 对象) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-394">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="179c3-395">如果源已启用诉讼或单个项目恢复，请对目标帐户进行此项设置。</span><span class="sxs-lookup"><span data-stu-id="179c3-395">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="179c3-396">这会将目标帐户的垃圾站大小增加至 100 GB。</span><span class="sxs-lookup"><span data-stu-id="179c3-396">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="179c3-397">**移动使用邮箱后如何访问第 1 天的 Outlook？**</span><span class="sxs-lookup"><span data-stu-id="179c3-397">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="179c3-398">由于只有一个租户可以拥有一个域，因此邮箱移动完成后，以前的主 SMTP 地址将不会与目标租户中的用户关联;仅与新租户关联的域。</span><span class="sxs-lookup"><span data-stu-id="179c3-398">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="179c3-399">Outlook 使用用户新的 UPN 对服务进行身份验证，Outlook 配置文件希望查找旧版主 SMTP 地址以匹配目标系统中邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-399">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="179c3-400">由于旧地址不在目标系统中，Outlook 配置文件无法连接以查找新移动的邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-400">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="179c3-401">对于此初始部署，用户将需要使用新的 UPN 主 SMTP 地址重新生成其配置文件，并重新同步 OST 内容。</span><span class="sxs-lookup"><span data-stu-id="179c3-401">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="179c3-402">在批处理用户以完成时进行相应规划。</span><span class="sxs-lookup"><span data-stu-id="179c3-402">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="179c3-403">创建 Outlook 客户端配置文件以及将后续 OST 和 OAB 文件下载到客户端时，您需要考虑网络利用率和容量。</span><span class="sxs-lookup"><span data-stu-id="179c3-403">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="179c3-404">**我需要成为哪些 Exchange RBAC 角色的成员来设置或完成跨租户移动？**</span><span class="sxs-lookup"><span data-stu-id="179c3-404">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="179c3-405">执行邮箱移动时，存在基于委派职责假设的角色矩阵。</span><span class="sxs-lookup"><span data-stu-id="179c3-405">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="179c3-406">目前，需要两个角色：</span><span class="sxs-lookup"><span data-stu-id="179c3-406">Currently, two roles are required:</span></span>  

- <span data-ttu-id="179c3-407">第一个角色用于建立将内容移入或移出租户/组织边界的授权的一次设置任务。</span><span class="sxs-lookup"><span data-stu-id="179c3-407">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="179c3-408">由于将数据从组织控制中移出是所有公司的一个关键问题，因此，我们选择具有 OrgAdmin (分配的最高) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-408">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="179c3-409">此角色必须更改或设置一个新的 OrganizationRelationship，用于定义远程组织的 -MailboxMoveCapability。</span><span class="sxs-lookup"><span data-stu-id="179c3-409">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="179c3-410">只有 OrgAdmin 可以更改 MailboxMoveCapability 设置，而 OrganizationRelationhip 上的其他属性也可由联合共享管理员管理。</span><span class="sxs-lookup"><span data-stu-id="179c3-410">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="179c3-411">执行实际移动命令的角色可以委派给较低级别的函数。</span><span class="sxs-lookup"><span data-stu-id="179c3-411">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="179c3-412">"移动邮箱"角色分配有使用参数将邮箱移进组织或将邮箱移出 `-RemoteTenant` 组织的功能。</span><span class="sxs-lookup"><span data-stu-id="179c3-412">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="179c3-413">**如何针对转换后的邮箱 (到 MailUser 转换) 上的 targetAddress (TargetDeliveryDomain) ？**</span><span class="sxs-lookup"><span data-stu-id="179c3-413">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="179c3-414">当通过匹配目标对象上的电子邮件地址 (proxyAddress) 转换为 MailUser 时，Exchange 邮箱使用 MRS 在原始源邮箱上创建 targetAddress。</span><span class="sxs-lookup"><span data-stu-id="179c3-414">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="179c3-415">此过程将接受传递到移动命令中的 -TargetDeliveryDomain 值，然后检查目标端上该域的匹配代理。</span><span class="sxs-lookup"><span data-stu-id="179c3-415">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="179c3-416">当我们找到匹配项时，匹配的 proxyAddress 将用于在转换的邮箱上设置 ExternalEmailAddress (targetAddress) ， (MailUser) 对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-416">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="179c3-417">**邮箱权限如何转换？**</span><span class="sxs-lookup"><span data-stu-id="179c3-417">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="179c3-418">邮箱权限包括"代表发送"和"邮箱访问"：</span><span class="sxs-lookup"><span data-stu-id="179c3-418">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="179c3-419">代表用户 (AD：publicDelegates) 存储具有用户邮箱代理访问权限的收件人的 DN。</span><span class="sxs-lookup"><span data-stu-id="179c3-419">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="179c3-420">此值存储在 Active Directory 中，当前不会作为邮箱转换的一部分移动。</span><span class="sxs-lookup"><span data-stu-id="179c3-420">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="179c3-421">如果源邮箱设置了 publicDelegates，则当 MEU 到邮箱的转换通过运行在目标环境中完成时，你需要在目标邮箱上重新标记 publicDelegates。 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`</span><span class="sxs-lookup"><span data-stu-id="179c3-421">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="179c3-422">当主体和代理都移动到目标系统时，邮箱中存储的邮箱权限将随邮箱一起移动。</span><span class="sxs-lookup"><span data-stu-id="179c3-422">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="179c3-423">例如，向用户TestUser_7租户中的邮箱TestUser_8 FullAccess SourceCompany.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="179c3-423">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="179c3-424">在邮箱移动完成TargetCompany.onmicrosoft.com，在目标目录中设置相同的权限。</span><span class="sxs-lookup"><span data-stu-id="179c3-424">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="179c3-425">在源租户和目标租户TestUser_7 *Get-MailboxPermission* 的示例如下所示。</span><span class="sxs-lookup"><span data-stu-id="179c3-425">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="179c3-426">Exchange cmdlet 相应地以源和目标作为前缀。</span><span class="sxs-lookup"><span data-stu-id="179c3-426">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="179c3-427">下面是移动前邮箱权限输出的示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-427">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="179c3-428">下面是移动后邮箱权限输出的示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-428">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="179c3-429">不支持跨租户邮箱和日历权限。</span><span class="sxs-lookup"><span data-stu-id="179c3-429">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="179c3-430">必须将主体和代理组织到合并移动批处理中，以便同时从源租户转换这些连接邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-430">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="179c3-431">**应向目标 MailUser 代理地址添加哪些 X500 代理以启用迁移？**</span><span class="sxs-lookup"><span data-stu-id="179c3-431">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="179c3-432">跨租户邮箱迁移要求将源邮箱对象的 LegacyExchangeDN 值标记为目标 MailUser 对象的 x500 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-432">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="179c3-433">示例：</span><span class="sxs-lookup"><span data-stu-id="179c3-433">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="179c3-434">除了此 X500 代理之外，还需要将源邮箱的所有 X500 代理复制到目标中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-434">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="179c3-435">**Azure 密钥保管库是否是必需的，以及何时进行交易？**</span><span class="sxs-lookup"><span data-stu-id="179c3-435">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="179c3-436">是的，Azure 订阅需要使用密钥保管库来存储证书以授权迁移。</span><span class="sxs-lookup"><span data-stu-id="179c3-436">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="179c3-437">与使用用户名和密码向源&登录迁移不同，跨租户邮箱迁移使用 OAuth 和此证书作为密码/凭据。</span><span class="sxs-lookup"><span data-stu-id="179c3-437">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="179c3-438">必须在所有邮箱迁移中维护对密钥保管库的访问权限，因为密钥保管库在迁移开始时和结束时访问一次，在增量同步期间每 24 小时访问一次。</span><span class="sxs-lookup"><span data-stu-id="179c3-438">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="179c3-439">你可以在此处查看 AKV 成本 [计算详细信息]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="179c3-439">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="179c3-440">**您是否对批处理有任何建议？**</span><span class="sxs-lookup"><span data-stu-id="179c3-440">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="179c3-441">每批不要超过 2000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-441">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="179c3-442">强烈建议在截止日期前两周提交批处理，因为同步期间对最终用户没有影响。如果需要超过 50，000 个邮箱数量的指南，可以在以下位置联系工程反馈crosstenantmigrationpreview@service.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="179c3-442">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="179c3-443">**如果我将服务加密与客户密钥一同使用，该做什么？**</span><span class="sxs-lookup"><span data-stu-id="179c3-443">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="179c3-444">邮箱将在移动之前解密。</span><span class="sxs-lookup"><span data-stu-id="179c3-444">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="179c3-445">如果仍然需要客户密钥，请确保在目标租户中配置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="179c3-445">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="179c3-446">有关详细信息 [，](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) 请参阅此处。</span><span class="sxs-lookup"><span data-stu-id="179c3-446">See [here](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) for more information.</span></span>  

<span data-ttu-id="179c3-447">**估计的迁移时间是什么？**</span><span class="sxs-lookup"><span data-stu-id="179c3-447">**What is the estimated migration time?**</span></span>

<span data-ttu-id="179c3-448">为了帮助您规划迁移，此处的表显示了有关[](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)何时预期批量邮箱迁移或单个迁移完成的准则。</span><span class="sxs-lookup"><span data-stu-id="179c3-448">To help you plan your migration, the table present [here](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="179c3-449">这些估计基于以前客户迁移的数据分析。</span><span class="sxs-lookup"><span data-stu-id="179c3-449">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="179c3-450">由于每个环境都是唯一的，因此确切的迁移速度可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="179c3-450">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="179c3-451">请记住，此功能当前处于预览阶段，SLA 及任何适用的服务级别不适用于此功能预览状态期间的任何性能或可用性问题。</span><span class="sxs-lookup"><span data-stu-id="179c3-451">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="179c3-452">已知问题</span><span class="sxs-lookup"><span data-stu-id="179c3-452">Known issues</span></span>  

-  <span data-ttu-id="179c3-453">**问题：无法迁移自动展开的存档。**</span><span class="sxs-lookup"><span data-stu-id="179c3-453">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="179c3-454">跨租户迁移功能支持迁移特定用户的主邮箱和存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-454">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="179c3-455">但是，如果源中的用户具有自动展开的存档，这意味着多个存档邮箱，则此功能无法迁移其他存档。</span><span class="sxs-lookup"><span data-stu-id="179c3-455">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="179c3-456">**问题：具有非拥有的 smtp 代理Address 块 MRS 的云 MailUsers 将移动后台。**</span><span class="sxs-lookup"><span data-stu-id="179c3-456">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="179c3-457">创建目标租户 MailUser 对象时，必须确保所有 SMTP 代理地址都属于目标租户组织。</span><span class="sxs-lookup"><span data-stu-id="179c3-457">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="179c3-458">如果不属于本地租户的目标邮件用户上存在 SMTP 代理地址，则阻止将 MailUser 转换为邮箱。</span><span class="sxs-lookup"><span data-stu-id="179c3-458">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="179c3-459">这是因为我们保证邮箱对象只能从租户对租户声明的域具有权威性 (域发送邮件) ：</span><span class="sxs-lookup"><span data-stu-id="179c3-459">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="179c3-460">使用 Azure AD Connect 从本地同步用户时，使用指向邮箱所在的源租户的 ExternalEmailAddress 预配本地 MailUser 对象 (laran@contoso.onmicrosoft.com) 并且将 PrimarySMTPAddress 标记为驻留在目标租户 (Lara.Newton@northwind.com) 中的域。</span><span class="sxs-lookup"><span data-stu-id="179c3-460">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="179c3-461">这些值将同步到租户，并设置相应的邮件用户并准备迁移。</span><span class="sxs-lookup"><span data-stu-id="179c3-461">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="179c3-462">此处显示了一个示例对象。</span><span class="sxs-lookup"><span data-stu-id="179c3-462">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="179c3-463">EmailAddresses /proxyAddresses *数组* 中不存在contoso.onmicrosoft.com地址。 </span><span class="sxs-lookup"><span data-stu-id="179c3-463">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="179c3-464">**问题：具有"外部"主 SMTP 地址的 MailUser 对象被修改/重置为"内部"公司声明的域**</span><span class="sxs-lookup"><span data-stu-id="179c3-464">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="179c3-465">MailUser 对象是指向非本地邮箱的指针。</span><span class="sxs-lookup"><span data-stu-id="179c3-465">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="179c3-466">对于跨租户邮箱迁移，从目标组织的角度来看，我们使用 MailUser 对象来表示源邮箱 (，或者从源组织的角度) 目标邮箱 (表示) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-466">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="179c3-467">MailUsers 将具有一个 ExternalEmailAddress (targetAddress) ，该地址指向实际邮箱 (ProxyTest@fabrikam.onmicrosoft.com) 的 smtp 地址和表示目录中邮箱用户的显示 SMTP 地址的 primarySMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-467">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="179c3-468">某些组织选择将主 SMTP 地址显示为外部 SMTP 地址，而不是本地租户拥有/验证的地址 (例如 fabrikam.com 而不是contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-468">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="179c3-469">但是，通过许可操作将 Exchange 服务计划对象应用于 MailUser 后，主 SMTP 地址将修改为由本地组织验证的 (contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="179c3-469">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="179c3-470">有两个潜在原因：</span><span class="sxs-lookup"><span data-stu-id="179c3-470">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="179c3-471">当任何 Exchange 服务计划应用于 MailUser 时，Azure AD 进程开始强制执行代理清理，以确保本地组织无法从另一个租户发送邮件、欺骗或邮件。</span><span class="sxs-lookup"><span data-stu-id="179c3-471">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="179c3-472">如果本地组织未验证该地址，将删除具有这些服务计划的收件人对象上的任何 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-472">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="179c3-473">与示例中的情况一样，Fabikam.com租户不验证 contoso.onmicrosoft.com 域，因此清理会删除该fabrikam.com域。</span><span class="sxs-lookup"><span data-stu-id="179c3-473">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="179c3-474">如果希望在迁移之前或迁移后在 MailUser 上保留这些外部域，则需要更改迁移过程，以在移动完成后或移动之前去除许可证，以确保用户应用了预期的外部品牌。</span><span class="sxs-lookup"><span data-stu-id="179c3-474">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="179c3-475">您需要确保邮箱对象已正确许可，不会影响邮件服务。</span><span class="sxs-lookup"><span data-stu-id="179c3-475">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="179c3-476">此处显示了用于删除邮件租户中 MailUser Contoso.onmicrosoft.com的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="179c3-476">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="179c3-477">此处显示了分配的 ServicePlans 集的结果。</span><span class="sxs-lookup"><span data-stu-id="179c3-477">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="179c3-478">用户的 PrimarySMTPAddress 不再被清理。</span><span class="sxs-lookup"><span data-stu-id="179c3-478">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="179c3-479">fabrikam.com域不归 contoso.onmicrosoft.com所有，并且将保留为目录中显示的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="179c3-479">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="179c3-480">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="179c3-480">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="179c3-481">当 msExchRemoteRecipientType 设置为 8 (DeprovisionMailbox) 时，对于迁移到目标租户的本地 MailUsers，Azure 中的代理清理逻辑将删除非域，将 primarySMTP 重置为拥有域。</span><span class="sxs-lookup"><span data-stu-id="179c3-481">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="179c3-482">通过清除本地 MailUser 中的 msExchRemoteRecipientType，代理清理逻辑将不再适用。</span><span class="sxs-lookup"><span data-stu-id="179c3-482">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="179c3-483">以下是包括 Exchange Online 的完整服务计划集。</span><span class="sxs-lookup"><span data-stu-id="179c3-483">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="179c3-484">名称</span><span class="sxs-lookup"><span data-stu-id="179c3-484">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="179c3-485">高级电子数据展示存储 (500GB) </span><span class="sxs-lookup"><span data-stu-id="179c3-485">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="179c3-486">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="179c3-486">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="179c3-487">数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="179c3-487">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="179c3-488">Exchange Enterprise CAL Services (EOP、DLP) </span><span class="sxs-lookup"><span data-stu-id="179c3-488">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="179c3-489">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="179c3-489">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="179c3-490">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="179c3-490">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="179c3-491">Exchange Online (P1) </span><span class="sxs-lookup"><span data-stu-id="179c3-491">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="179c3-492">Exchange Online (计划 1) </span><span class="sxs-lookup"><span data-stu-id="179c3-492">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="179c3-493">Exchange Online（计划 2）</span><span class="sxs-lookup"><span data-stu-id="179c3-493">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="179c3-494">适用于 Exchange Online 的 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="179c3-494">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="179c3-495">适用于 Exchange Server 的 Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="179c3-495">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="179c3-496">Exchange Online 非活动用户加载项</span><span class="sxs-lookup"><span data-stu-id="179c3-496">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="179c3-497">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="179c3-497">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="179c3-498">Exchange Online 多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="179c3-498">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="179c3-499">Exchange Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="179c3-499">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="179c3-500">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="179c3-500">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="179c3-501">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="179c3-501">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="179c3-502">信息屏障</span><span class="sxs-lookup"><span data-stu-id="179c3-502">Information Barriers</span></span>                              |
   | <span data-ttu-id="179c3-503">适用于 Office 365 的信息保护 - 高级版</span><span class="sxs-lookup"><span data-stu-id="179c3-503">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="179c3-504">适用于 Office 365 的信息保护 - 标准版</span><span class="sxs-lookup"><span data-stu-id="179c3-504">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="179c3-505">MyAnalytics 的见解</span><span class="sxs-lookup"><span data-stu-id="179c3-505">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="179c3-506">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="179c3-506">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="179c3-507">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="179c3-507">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="179c3-508">Microsoft 商业中心</span><span class="sxs-lookup"><span data-stu-id="179c3-508">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="179c3-509">Microsoft MyAnalytics（完整版）</span><span class="sxs-lookup"><span data-stu-id="179c3-509">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="179c3-510">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="179c3-510">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="179c3-511">Microsoft Defender for Office 365 (计划 1) </span><span class="sxs-lookup"><span data-stu-id="179c3-511">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="179c3-512">Microsoft Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="179c3-512">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="179c3-513">Office 365 特权访问管理</span><span class="sxs-lookup"><span data-stu-id="179c3-513">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="179c3-514">Office 365 中的高级加密</span><span class="sxs-lookup"><span data-stu-id="179c3-514">Premium Encryption in Office 365</span></span>                  |
    
