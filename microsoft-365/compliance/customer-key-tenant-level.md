---
title: 租户级 Microsoft 365 客户密钥（公共预览版）
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 了解如何为 Microsoft 365 租户内的所有数据设置客户密钥。
ms.openlocfilehash: 682eed7eb2e80535af1acf68808c708e1a25d80f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242372"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="4be67-103">租户级别的 Microsoft 365 客户密钥 (公共预览版) </span><span class="sxs-lookup"><span data-stu-id="4be67-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="4be67-104">使用提供的密钥，您可以创建 DEP (数据) 策略并将其分配给租户。</span><span class="sxs-lookup"><span data-stu-id="4be67-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="4be67-105">DEP 对租户中以下工作负载的数据进行加密：</span><span class="sxs-lookup"><span data-stu-id="4be67-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="4be67-106">Teams 聊天消息 (一对一聊天、群聊、会议聊天和频道对话) </span><span class="sxs-lookup"><span data-stu-id="4be67-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="4be67-107">Teams 媒体 (图像、代码段、视频消息、音频消息、wiki 图像) </span><span class="sxs-lookup"><span data-stu-id="4be67-107">Teams media messages (images, code snippets, videos messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="4be67-108">Teams 存储中存储的 Teams 通话和会议录像</span><span class="sxs-lookup"><span data-stu-id="4be67-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="4be67-109">Teams 聊天通知</span><span class="sxs-lookup"><span data-stu-id="4be67-109">Teams chat notifications</span></span>
- <span data-ttu-id="4be67-110">Cortana 的 Teams 聊天建议</span><span class="sxs-lookup"><span data-stu-id="4be67-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="4be67-111">Teams 状态消息</span><span class="sxs-lookup"><span data-stu-id="4be67-111">Teams status messages</span></span>
- <span data-ttu-id="4be67-112">Exchange Online 的用户和信号信息</span><span class="sxs-lookup"><span data-stu-id="4be67-112">User and signal information for Exchange Online</span></span>

<span data-ttu-id="4be67-113">对于 Microsoft Teams，从 DEP 分配给租户起，租户级别的客户密钥将加密新数据。</span><span class="sxs-lookup"><span data-stu-id="4be67-113">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="4be67-114">公共预览版不支持加密过去的数据。</span><span class="sxs-lookup"><span data-stu-id="4be67-114">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="4be67-115">对于 Exchange Online，客户密钥加密所有现有和新数据。</span><span class="sxs-lookup"><span data-stu-id="4be67-115">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="4be67-116">每个租户可以创建多个 DEP，但在任何时间点只能分配一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="4be67-116">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="4be67-117">分配 DEP 时，加密将自动开始，但可能需要一些时间才能完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="4be67-117">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="4be67-118">租户级别策略为 Microsoft 365 的客户密钥添加了更广泛的控制</span><span class="sxs-lookup"><span data-stu-id="4be67-118">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="4be67-119">如果你已经为 Exchange Online 和 Sharepoint Online 设置了客户密钥，下面将说明新的租户级公共预览版如何适应。</span><span class="sxs-lookup"><span data-stu-id="4be67-119">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="4be67-120">创建的租户级加密策略对 Microsoft 365 中的 Microsoft Teams 和 Exchange Online 工作负载的所有数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="4be67-120">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="4be67-121">此策略不会干扰已在客户密钥中创建的微调的 DEP。</span><span class="sxs-lookup"><span data-stu-id="4be67-121">This policy doesn't interfere with finely tuned DEPs you've already created in Customer Key.</span></span>

<span data-ttu-id="4be67-122">示例：</span><span class="sxs-lookup"><span data-stu-id="4be67-122">Examples:</span></span>

<span data-ttu-id="4be67-123">保存在 OneDrive for Business 和 SharePoint 中的 Microsoft Teams 文件和一些 Teams 通话和会议录像由 SharePoint Online DEP 进行加密。</span><span class="sxs-lookup"><span data-stu-id="4be67-123">Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="4be67-124">单个 SharePoint Online DEP 对单个地理位置中的内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="4be67-124">A single SharePoint Online DEP encrypts content within a single geo.</span></span>

<span data-ttu-id="4be67-125">对于 Exchange Online，您可以创建使用客户密钥加密一个或多个用户邮箱的 DEP。</span><span class="sxs-lookup"><span data-stu-id="4be67-125">For Exchange Online, you can create a DEP that encrypts one or more user mailboxes with Customer Key.</span></span> <span data-ttu-id="4be67-126">创建租户级别的策略时，该策略不会加密加密的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4be67-126">When you create a tenant-level policy, that policy will not encrypt the encrypted mailboxes.</span></span> <span data-ttu-id="4be67-127">但是，租户级别密钥将加密已不受 DEP 影响的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4be67-127">However,  the tenant-level key will encrypt the mailboxes that are not affected by a DEP already.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="4be67-128">在租户级别设置客户密钥 (预览版) </span><span class="sxs-lookup"><span data-stu-id="4be67-128">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="4be67-129">这些步骤与在应用程序级别设置客户密钥的步骤类似，但不完全相同。</span><span class="sxs-lookup"><span data-stu-id="4be67-129">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="4be67-130">应仅对此公共预览版与测试租户中的测试数据一同使用。</span><span class="sxs-lookup"><span data-stu-id="4be67-130">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="4be67-131">请勿将此版本与生产数据或生产环境一同使用。</span><span class="sxs-lookup"><span data-stu-id="4be67-131">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="4be67-132">如果你已经拥有客户密钥的生产部署，请使用这些步骤在测试环境中在租户级别设置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-132">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="4be67-133">你通过远程连接到 Azure PowerShell 来完成大部分任务。</span><span class="sxs-lookup"><span data-stu-id="4be67-133">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="4be67-134">为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4be67-134">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="4be67-135">在开始使用之前，请确保执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4be67-135">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="4be67-136">你需要使用具有合规性管理员角色的工作或学校帐户在租户级别设置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-136">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="4be67-137">确保你拥有组织的适当许可。</span><span class="sxs-lookup"><span data-stu-id="4be67-137">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="4be67-138">使用付费的已开票 Azure 订阅，企业协议云服务提供商。</span><span class="sxs-lookup"><span data-stu-id="4be67-138">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="4be67-139">客户密钥不支持使用即付即用计划或信用卡购买的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="4be67-139">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="4be67-140">从 2020 年 4 月 1 日起，Office 365 中的客户密钥在 Office 365 E5、M365 E5、M365 E5 合规性和 M365 E5 信息保护 & 治理 SUS 中提供。</span><span class="sxs-lookup"><span data-stu-id="4be67-140">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="4be67-141">Office 365 高级合规性 SKU 不再可用于购买新许可证。</span><span class="sxs-lookup"><span data-stu-id="4be67-141">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="4be67-142">现有 Office 365 高级合规性许可证将继续受支持。</span><span class="sxs-lookup"><span data-stu-id="4be67-142">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="4be67-143">虽然可以在具有相应许可证的租户下至少启用一个许可证来启用该服务，但您仍应确保从该服务受益的所有用户都有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="4be67-143">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="4be67-144">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="4be67-144">Create two new Azure subscriptions</span></span>

<span data-ttu-id="4be67-145">对于 DEP 策略的每个数据加密策略，客户密钥 (两) 。</span><span class="sxs-lookup"><span data-stu-id="4be67-145">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="4be67-146">为此，必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="4be67-146">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="4be67-147">作为最佳实践，Microsoft 建议组织单独的成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-147">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="4be67-148">仅使用这些 Azure 订阅来管理 Microsoft 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-148">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="4be67-149">这样可保护组织，以防您的一个运营商意外、有意或恶意删除或以其他方式管理他们负责的密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-149">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="4be67-150">你可以为组织创建的 Azure 订阅数量没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="4be67-150">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="4be67-151">遵循此最佳做法有助于最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="4be67-151">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="4be67-152">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="4be67-152">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="4be67-153">根加密密钥的临时或永久丢失可能会中断甚至对服务操作造成灾难性影响，并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="4be67-153">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="4be67-154">因此，用于客户密钥的资源需要强大的保护。</span><span class="sxs-lookup"><span data-stu-id="4be67-154">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="4be67-155">用于客户密钥的所有 Azure 资源都提供默认配置以外的保护机制。</span><span class="sxs-lookup"><span data-stu-id="4be67-155">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="4be67-156">Azure 订阅可以标记或注册，以防止立即取消和不可撤销的取消。</span><span class="sxs-lookup"><span data-stu-id="4be67-156">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="4be67-157">这称为注册强制保留期。</span><span class="sxs-lookup"><span data-stu-id="4be67-157">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="4be67-158">注册 Azure 订阅以保留强制保留期所需的步骤需要与 Microsoft 协作。</span><span class="sxs-lookup"><span data-stu-id="4be67-158">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="4be67-159">此过程最多可能需要 5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="4be67-159">This process can take up to five business days.</span></span> <span data-ttu-id="4be67-160">以前，这有时称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="4be67-160">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="4be67-161">在联系 Microsoft 365 团队之前，必须针对使用客户密钥的每个 Azure 订阅执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4be67-161">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="4be67-162">在启动之前，请确保已安装 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模块。</span><span class="sxs-lookup"><span data-stu-id="4be67-162">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="4be67-163">使用 Azure PowerShell 登录。</span><span class="sxs-lookup"><span data-stu-id="4be67-163">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="4be67-164">有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="4be67-164">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4be67-165">运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="4be67-165">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="4be67-166">对于每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4be67-166">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="4be67-167">请与 Microsoft 联系，在最终[m365ck@microsoft.com。](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4be67-167">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="4be67-168">在电子邮件中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="4be67-168">Include the following in your email:</span></span>

   <span data-ttu-id="4be67-169">**主题**：客户密钥 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="4be67-169">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="4be67-170">**正文**：要完成其强制保留期的订阅 ID。</span><span class="sxs-lookup"><span data-stu-id="4be67-170">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="4be67-171">每个订阅Get-AzProviderFeature输出。</span><span class="sxs-lookup"><span data-stu-id="4be67-171">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="4be67-172">一旦 Microsoft 通知 (并验证) 你已注册订阅以使用强制保留期，完成此过程的服务级别协议 (SLA) 需要五个工作日。</span><span class="sxs-lookup"><span data-stu-id="4be67-172">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="4be67-173">从 Microsoft 收到注册完成通知后，通过运行 Get-AzProviderFeature 命令验证注册状态。如下所示。</span><span class="sxs-lookup"><span data-stu-id="4be67-173">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="4be67-174">如果验证，则Get-AzProviderFeature返回 **注册** 状态属性的值 **"已注册"。**</span><span class="sxs-lookup"><span data-stu-id="4be67-174">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="4be67-175">对于每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4be67-175">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="4be67-176">若要完成此过程，请运行Register-AzResourceProvider命令。</span><span class="sxs-lookup"><span data-stu-id="4be67-176">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="4be67-177">对于每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4be67-177">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="4be67-178">在每个订阅中创建高级 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="4be67-178">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="4be67-179">Azure Key [Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)入门中记录了创建密钥保管库的步骤，这些步骤将指导你安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建该资源组中的关键保管库。</span><span class="sxs-lookup"><span data-stu-id="4be67-179">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="4be67-180">创建密钥保管库时，必须选择 SKU：Standard 或 Premium。</span><span class="sxs-lookup"><span data-stu-id="4be67-180">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="4be67-181">标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护）。高级 SKU 允许使用 HSM 来保护密钥保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-181">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="4be67-182">客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="4be67-182">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="4be67-183">使用任一类型的密钥的操作成本相同，因此成本的唯一差异是每个受 HSM 保护的密钥的每月成本。</span><span class="sxs-lookup"><span data-stu-id="4be67-183">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="4be67-184">有关详细信息 [，请参阅密钥保管](https://azure.microsoft.com/pricing/details/key-vault/) 库定价。</span><span class="sxs-lookup"><span data-stu-id="4be67-184">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4be67-185">将高级 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。</span><span class="sxs-lookup"><span data-stu-id="4be67-185">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="4be67-186">对密钥保管库使用通用前缀，并包括密钥保管库和密钥的使用和范围的缩写。</span><span class="sxs-lookup"><span data-stu-id="4be67-186">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="4be67-187">例如，对于将位于北美的保管库的 Contoso 服务，可能的名称对是 Contoso-O365-NA-VaultA1 和 Contoso-O365-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="4be67-187">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="4be67-188">保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。</span><span class="sxs-lookup"><span data-stu-id="4be67-188">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="4be67-189">配置后，无法更改保管库名称，因此最佳做法是制定书面设置计划，并使用第二个人验证计划是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="4be67-189">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="4be67-190">如果可能，在未配对区域创建保管库。</span><span class="sxs-lookup"><span data-stu-id="4be67-190">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="4be67-191">配对的 Azure 区域跨服务故障域提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="4be67-191">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="4be67-192">因此，可以将区域对视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="4be67-192">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="4be67-193">这意味着放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。</span><span class="sxs-lookup"><span data-stu-id="4be67-193">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="4be67-194">因此，为数据加密策略中使用的两个保管库选择区域（其中区域已配对）意味着仅总共使用两个可用性区域。</span><span class="sxs-lookup"><span data-stu-id="4be67-194">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="4be67-195">大多数地理位置只有两个区域，因此尚无法选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="4be67-195">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="4be67-196">如果可能，为用于数据加密策略的两个保管库选择两个未配对区域。</span><span class="sxs-lookup"><span data-stu-id="4be67-196">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="4be67-197">这从总共四个可用性区域中获益。</span><span class="sxs-lookup"><span data-stu-id="4be67-197">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="4be67-198">有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：Azure 配对](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 区域，了解区域对的当前列表。</span><span class="sxs-lookup"><span data-stu-id="4be67-198">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="4be67-199">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="4be67-199">Assign permissions to each key vault</span></span>

<span data-ttu-id="4be67-200">对于每个密钥保管库，你将需要为客户密钥定义三组单独的权限，具体取决于你的实现。</span><span class="sxs-lookup"><span data-stu-id="4be67-200">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="4be67-201">例如，您需要为以下各项定义一组权限：</span><span class="sxs-lookup"><span data-stu-id="4be67-201">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="4be67-202">**为组织** 执行密钥保管库日常管理的关键保管库管理员。</span><span class="sxs-lookup"><span data-stu-id="4be67-202">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="4be67-203">这些任务包括备份、创建、获取、导入、列表和还原。</span><span class="sxs-lookup"><span data-stu-id="4be67-203">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4be67-204">分配给密钥保管库管理员的权限集不包括删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="4be67-204">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="4be67-205">这是有意为之，也是一项重要做法。</span><span class="sxs-lookup"><span data-stu-id="4be67-205">This is intentional and an important practice.</span></span> <span data-ttu-id="4be67-206">通常不删除加密密钥，因为这样做会永久销毁数据。</span><span class="sxs-lookup"><span data-stu-id="4be67-206">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="4be67-207">作为最佳实践，默认情况下不要向密钥保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="4be67-207">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="4be67-208">相反，请为关键保管库参与者保留此权限，仅在明确了解后果后将其短期分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="4be67-208">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="4be67-209">若要向组织中用户分配这些权限，请通过 Azure PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="4be67-209">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="4be67-210">有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="4be67-210">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="4be67-211">运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="4be67-211">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="4be67-212">例如：</span><span class="sxs-lookup"><span data-stu-id="4be67-212">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="4be67-213">**可以更改 Azure** 密钥保管库本身权限的关键保管库参与者。</span><span class="sxs-lookup"><span data-stu-id="4be67-213">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="4be67-214">当员工离开或加入团队时，或者当密钥保管库管理员合法需要删除或还原密钥的权限时，你将需要更改这些权限。</span><span class="sxs-lookup"><span data-stu-id="4be67-214">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="4be67-215">需要向这组密钥保管库参与者授予密钥保管库的"参与者"角色。</span><span class="sxs-lookup"><span data-stu-id="4be67-215">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="4be67-216">可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="4be67-216">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="4be67-217">有关详细步骤，请参阅Role-Based [访问控制](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 管理对 Azure 订阅资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4be67-217">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="4be67-218">默认情况下，创建订阅的管理员具有此访问权限，并且能够将其他管理员分配到参与者角色。</span><span class="sxs-lookup"><span data-stu-id="4be67-218">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="4be67-219">**Microsoft 365** 静态数据加密服务，该服务在租户级别处理客户密钥的工作。</span><span class="sxs-lookup"><span data-stu-id="4be67-219">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="4be67-220">若要向 Microsoft 365 授予权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4be67-220">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="4be67-221">其中：</span><span class="sxs-lookup"><span data-stu-id="4be67-221">Where:</span></span>

  - <span data-ttu-id="4be67-222">*保管* 库名称是创建的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="4be67-222">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="4be67-223">示例：对于 Microsoft 365 静态数据加密服务，将 *Microsoft 365 appID 替换为*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="4be67-223">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="4be67-224">启用密钥保管库，然后确认软删除</span><span class="sxs-lookup"><span data-stu-id="4be67-224">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="4be67-225">当您可以快速恢复密钥时，您不太可能因意外或恶意删除的密钥而遇到扩展的服务中断。</span><span class="sxs-lookup"><span data-stu-id="4be67-225">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="4be67-226">启用此配置（称为"软删除"）后，才能将密钥与客户密钥一同使用。</span><span class="sxs-lookup"><span data-stu-id="4be67-226">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="4be67-227">启用软删除允许您在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="4be67-227">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="4be67-228">若要对密钥保管库启用软删除，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4be67-228">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="4be67-229">使用帐户登录 Azure Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4be67-229">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="4be67-230">有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="4be67-230">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4be67-231">运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4be67-231">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="4be67-232">本示例中， *保管库名称* 是要启用软删除的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="4be67-232">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="4be67-233">通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置软删除。</span><span class="sxs-lookup"><span data-stu-id="4be67-233">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="4be67-234">如果为密钥保管库正确配置软删除，则 _启用软_ 删除的属性将返回 **True 值**：</span><span class="sxs-lookup"><span data-stu-id="4be67-234">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="4be67-235">通过创建或导入密钥将密钥添加到每个密钥保管库</span><span class="sxs-lookup"><span data-stu-id="4be67-235">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="4be67-236">有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在 Key Vault 中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-236">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="4be67-237">直接在 Key Vault 中创建密钥是不太复杂的方法，而导入密钥可提供对密钥生成方式的完全控制。</span><span class="sxs-lookup"><span data-stu-id="4be67-237">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="4be67-238">使用 RSA 密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-238">Use the RSA keys.</span></span> <span data-ttu-id="4be67-239">Azure Key Vault 不支持使用椭圆曲线键环绕和解包。</span><span class="sxs-lookup"><span data-stu-id="4be67-239">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="4be67-240">若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-240">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="4be67-241">其中：</span><span class="sxs-lookup"><span data-stu-id="4be67-241">Where:</span></span>

- <span data-ttu-id="4be67-242">*保管* 库名称是你想要创建密钥的保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="4be67-242">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="4be67-243">*键* 名称是你想要提供新密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="4be67-243">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="4be67-244">使用与上述密钥保管库类似的命名约定命名密钥。</span><span class="sxs-lookup"><span data-stu-id="4be67-244">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="4be67-245">这样，在只显示键名称的工具中，字符串是自描述的。</span><span class="sxs-lookup"><span data-stu-id="4be67-245">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="4be67-246">如果您打算使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则，请指定 **Software**。</span><span class="sxs-lookup"><span data-stu-id="4be67-246">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="4be67-247">例如，</span><span class="sxs-lookup"><span data-stu-id="4be67-247">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="4be67-248">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="4be67-248">Check the recovery level of your keys</span></span>

<span data-ttu-id="4be67-249">Microsoft 365 要求 Azure 密钥保管库订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。</span><span class="sxs-lookup"><span data-stu-id="4be67-249">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="4be67-250">可以通过查看密钥的恢复级别来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="4be67-250">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="4be67-251">若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-251">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="4be67-252">如果恢复级别属性返回除 **"可恢复+ProtectedSubscription"** 值外的其他值，则需要查看本文，并确保已按照所有步骤将订阅置于"不取消"列表中，并确保在每个密钥保管库上启用了"软删除"。</span><span class="sxs-lookup"><span data-stu-id="4be67-252">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="4be67-253">接下来，将电子邮件输出的屏幕截图 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` 发送到m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="4be67-253">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="4be67-254">备份 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="4be67-254">Back up Azure Key Vault</span></span>

<span data-ttu-id="4be67-255">创建或对密钥的任何更改后，立即执行备份并存储备份的副本（联机和脱机）。</span><span class="sxs-lookup"><span data-stu-id="4be67-255">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="4be67-256">不要将脱机副本连接到任何网络。</span><span class="sxs-lookup"><span data-stu-id="4be67-256">Don't connect offline copies to any network.</span></span> <span data-ttu-id="4be67-257">相反，将它们存储在物理安全或商业存储设施中。</span><span class="sxs-lookup"><span data-stu-id="4be67-257">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="4be67-258">应至少将备份的一个副本存储在发生灾难时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="4be67-258">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="4be67-259">如果密钥保管库密钥被永久销毁或无法操作，备份 blob 是还原密钥材料的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="4be67-259">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="4be67-260">Azure 密钥保管库外部且已导入到 Azure 密钥保管库的密钥不符合备份条件，因为客户密钥使用密钥所需的元数据不存在于外部密钥中。</span><span class="sxs-lookup"><span data-stu-id="4be67-260">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="4be67-261">只有从 Azure Key Vault 获取的备份可用于使用客户密钥执行还原操作。</span><span class="sxs-lookup"><span data-stu-id="4be67-261">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="4be67-262">因此，在上载或创建密钥后，必须备份 Azure Key Vault。</span><span class="sxs-lookup"><span data-stu-id="4be67-262">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="4be67-263">若要创建 Azure Key Vault 密钥的备份，请运行 [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-263">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="4be67-264">确保输出文件使用后缀 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="4be67-264">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="4be67-265">此 cmdlet 生成的输出文件已加密，不能在 Azure 密钥保管库外部使用。</span><span class="sxs-lookup"><span data-stu-id="4be67-265">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="4be67-266">备份只能还原到进行备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="4be67-266">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="4be67-267">例如：</span><span class="sxs-lookup"><span data-stu-id="4be67-267">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="4be67-268">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="4be67-268">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="4be67-269">在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="4be67-269">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="4be67-270">特别是，如果使用除本主题中所述的步骤设置密钥和保管库外的步骤，应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。</span><span class="sxs-lookup"><span data-stu-id="4be67-270">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="4be67-271">若要验证密钥是否已启用 get、wrapKey 和 unwrapKey 操作：</span><span class="sxs-lookup"><span data-stu-id="4be67-271">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="4be67-272">运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-272">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="4be67-273">在输出中，查找访问策略，并查找适用于 GUID (的 Microsoft 365) ID。</span><span class="sxs-lookup"><span data-stu-id="4be67-273">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="4be67-274">所有三个操作（get、wrapKey 和 unwrapKey）都必须显示在"密钥权限"下。</span><span class="sxs-lookup"><span data-stu-id="4be67-274">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="4be67-275">如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-275">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="4be67-276">示例：对于 Microsoft 365 静态数据加密服务，将 *Microsoft 365 appID 替换为*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="4be67-276">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="4be67-277">若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-277">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="4be67-278">客户密钥无法使用过期密钥，并且尝试使用过期密钥的操作将失败，并可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="4be67-278">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="4be67-279">我们强烈建议用于客户密钥的密钥没有过期日期。</span><span class="sxs-lookup"><span data-stu-id="4be67-279">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="4be67-280">一旦设置过期日期，将无法删除，但可更改为其他日期。</span><span class="sxs-lookup"><span data-stu-id="4be67-280">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="4be67-281">如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="4be67-281">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="4be67-282">到期日期设置为 12/31/9999 日期的密钥无法通过 Microsoft 365 验证。</span><span class="sxs-lookup"><span data-stu-id="4be67-282">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="4be67-283">若要更改已设置为除 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be67-283">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="4be67-284">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="4be67-284">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="4be67-285">完成 Azure 中设置密钥保管库并添加密钥的所有步骤后，运行以下命令，获取每个密钥保管库中密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="4be67-285">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="4be67-286">稍后创建和分配每个 DEP 时，将需要使用这些 URI，因此将此信息保存在一个安全的位置。</span><span class="sxs-lookup"><span data-stu-id="4be67-286">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="4be67-287">请记住，针对每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="4be67-287">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="4be67-288">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="4be67-288">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="4be67-289">为租户设置客户密钥加密策略</span><span class="sxs-lookup"><span data-stu-id="4be67-289">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="4be67-290">您需获得权限，然后才能运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4be67-290">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="4be67-291">尽管本文列出了 cmdlet 的所有参数，但如果这些参数未包含在分配给您的权限中，则您可能无法访问这些参数。</span><span class="sxs-lookup"><span data-stu-id="4be67-291">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="4be67-292">若要查找在贵组织中运行任何 cmdlet 或参数所需的权限，请参阅 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)。</span><span class="sxs-lookup"><span data-stu-id="4be67-292">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="4be67-293">创建策略</span><span class="sxs-lookup"><span data-stu-id="4be67-293">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

<span data-ttu-id="4be67-294">说明：允许合规性管理员使用两个 AKV 根密钥 (DEP) 数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-294">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="4be67-295">创建后，可以使用 cmdlet 分配Set-M365DataAtRestEncryptionPolicy策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-295">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span> <span data-ttu-id="4be67-296">首次分配密钥或旋转密钥后，新密钥最多可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="4be67-296">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="4be67-297">如果新的 DEP 需要 24 小时以上才能生效，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="4be67-297">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="4be67-298">示例：</span><span class="sxs-lookup"><span data-stu-id="4be67-298">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="4be67-299">参数：</span><span class="sxs-lookup"><span data-stu-id="4be67-299">Parameters:</span></span>

| <span data-ttu-id="4be67-300">名称</span><span class="sxs-lookup"><span data-stu-id="4be67-300">Name</span></span> | <span data-ttu-id="4be67-301">说明</span><span class="sxs-lookup"><span data-stu-id="4be67-301">Description</span></span> | <span data-ttu-id="4be67-302">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="4be67-302">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="4be67-303">名称</span><span class="sxs-lookup"><span data-stu-id="4be67-303">Name</span></span>|<span data-ttu-id="4be67-304">数据加密策略的友好名称</span><span class="sxs-lookup"><span data-stu-id="4be67-304">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="4be67-305">网络</span><span class="sxs-lookup"><span data-stu-id="4be67-305">N</span></span>|
|<span data-ttu-id="4be67-306">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="4be67-306">AzureKeyIDs</span></span>|<span data-ttu-id="4be67-307">指定 Azure 密钥保管库密钥的两个 URI 值（用逗号分隔）以与数据加密策略关联</span><span class="sxs-lookup"><span data-stu-id="4be67-307">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="4be67-308">网络</span><span class="sxs-lookup"><span data-stu-id="4be67-308">N</span></span>|
|<span data-ttu-id="4be67-309">说明</span><span class="sxs-lookup"><span data-stu-id="4be67-309">Description</span></span>|<span data-ttu-id="4be67-310">数据加密策略的说明</span><span class="sxs-lookup"><span data-stu-id="4be67-310">Description of the data encryption policy</span></span>|<span data-ttu-id="4be67-311">网络</span><span class="sxs-lookup"><span data-stu-id="4be67-311">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="4be67-312">分配策略</span><span class="sxs-lookup"><span data-stu-id="4be67-312">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="4be67-313">说明：此 cmdlet 用于配置默认数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-313">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="4be67-314">然后，此策略将用于加密所有支持工作负载的数据。</span><span class="sxs-lookup"><span data-stu-id="4be67-314">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="4be67-315">示例：</span><span class="sxs-lookup"><span data-stu-id="4be67-315">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

<span data-ttu-id="4be67-316">参数：</span><span class="sxs-lookup"><span data-stu-id="4be67-316">Parameters:</span></span>
| <span data-ttu-id="4be67-317">名称</span><span class="sxs-lookup"><span data-stu-id="4be67-317">Name</span></span> | <span data-ttu-id="4be67-318">说明</span><span class="sxs-lookup"><span data-stu-id="4be67-318">Description</span></span> | <span data-ttu-id="4be67-319">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="4be67-319">Optional (Y/N)</span></span> |
|--|--|--|
<span data-ttu-id="4be67-320">-Policy</span><span class="sxs-lookup"><span data-stu-id="4be67-320">-Policy</span></span>|<span data-ttu-id="4be67-321">指定需要分配的数据加密策略;指定策略名称或策略 ID。</span><span class="sxs-lookup"><span data-stu-id="4be67-321">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="4be67-322">网络</span><span class="sxs-lookup"><span data-stu-id="4be67-322">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="4be67-323">修改或刷新策略</span><span class="sxs-lookup"><span data-stu-id="4be67-323">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="4be67-324">说明：该 cmdlet 可用于修改或刷新现有策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-324">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="4be67-325">它还可用于启用或禁用策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-325">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="4be67-326">首次分配密钥或旋转密钥后，新密钥最多可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="4be67-326">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="4be67-327">如果新的 DEP 需要 24 小时以上才能生效，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="4be67-327">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="4be67-328">示例：</span><span class="sxs-lookup"><span data-stu-id="4be67-328">Examples:</span></span>

<span data-ttu-id="4be67-329">禁用数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-329">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="4be67-330">刷新数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-330">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="4be67-331">参数：</span><span class="sxs-lookup"><span data-stu-id="4be67-331">Parameters:</span></span>
| <span data-ttu-id="4be67-332">名称</span><span class="sxs-lookup"><span data-stu-id="4be67-332">Name</span></span> | <span data-ttu-id="4be67-333">说明</span><span class="sxs-lookup"><span data-stu-id="4be67-333">Description</span></span> | <span data-ttu-id="4be67-334">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="4be67-334">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="4be67-335">-Identity</span><span class="sxs-lookup"><span data-stu-id="4be67-335">-Identity</span></span>|<span data-ttu-id="4be67-336">指定要修改的数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-336">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="4be67-337">网络</span><span class="sxs-lookup"><span data-stu-id="4be67-337">N</span></span>|
|<span data-ttu-id="4be67-338">-Refresh</span><span class="sxs-lookup"><span data-stu-id="4be67-338">-Refresh</span></span>|<span data-ttu-id="4be67-339">旋转 Azure 密钥保管库中的任何关联密钥后，使用 Refresh 开关更新数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-339">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="4be67-340">不必为此开关指定值。</span><span class="sxs-lookup"><span data-stu-id="4be67-340">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="4be67-341">Y</span><span class="sxs-lookup"><span data-stu-id="4be67-341">Y</span></span>|
|<span data-ttu-id="4be67-342">- 已启用</span><span class="sxs-lookup"><span data-stu-id="4be67-342">-Enabled</span></span>|<span data-ttu-id="4be67-343">Enabled 参数启用或禁用数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-343">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="4be67-344">在禁用策略之前，必须从租户取消分配它。</span><span class="sxs-lookup"><span data-stu-id="4be67-344">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="4be67-345">有效值为：</span><span class="sxs-lookup"><span data-stu-id="4be67-345">Valid values are:</span></span></br > <span data-ttu-id="4be67-346">$true：策略已启用</span><span class="sxs-lookup"><span data-stu-id="4be67-346">$true: The policy is enabled</span></span></br > <span data-ttu-id="4be67-347">$true：启用此策略。此为默认值。
</span><span class="sxs-lookup"><span data-stu-id="4be67-347">$false: The policy is disabled.</span></span>|<span data-ttu-id="4be67-348">Y</span><span class="sxs-lookup"><span data-stu-id="4be67-348">Y</span></span>|
|<span data-ttu-id="4be67-349">-名称</span><span class="sxs-lookup"><span data-stu-id="4be67-349">-Name</span></span>|<span data-ttu-id="4be67-350">Name 参数指定数据加密策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="4be67-350">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="4be67-351">Y</span><span class="sxs-lookup"><span data-stu-id="4be67-351">Y</span></span>
|<span data-ttu-id="4be67-352">-Description</span><span class="sxs-lookup"><span data-stu-id="4be67-352">-Description</span></span>|<span data-ttu-id="4be67-353">Description 参数指定数据加密策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="4be67-353">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="4be67-354">Y</span><span class="sxs-lookup"><span data-stu-id="4be67-354">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="4be67-355">获取策略详细信息</span><span class="sxs-lookup"><span data-stu-id="4be67-355">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="4be67-356">说明：此 cmdlet 列出了为租户创建的所有 M365DataAtRest 加密策略或特定策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4be67-356">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="4be67-357">示例：</span><span class="sxs-lookup"><span data-stu-id="4be67-357">Examples:</span></span>

<span data-ttu-id="4be67-358">此示例返回组织中 M365DatAtRest 加密策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="4be67-358">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="4be67-359">此示例返回名为"NAM Policy"的数据加密策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4be67-359">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="4be67-360">参数：</span><span class="sxs-lookup"><span data-stu-id="4be67-360">Parameters:</span></span>

| <span data-ttu-id="4be67-361">名称</span><span class="sxs-lookup"><span data-stu-id="4be67-361">Name</span></span> | <span data-ttu-id="4be67-362">说明</span><span class="sxs-lookup"><span data-stu-id="4be67-362">Description</span></span> | <span data-ttu-id="4be67-363">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="4be67-363">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="4be67-364">-Identity</span><span class="sxs-lookup"><span data-stu-id="4be67-364">-Identity</span></span>|<span data-ttu-id="4be67-365">指定要列出其详细信息的数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-365">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="4be67-366">Y</span><span class="sxs-lookup"><span data-stu-id="4be67-366">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="4be67-367">获取策略分配信息</span><span class="sxs-lookup"><span data-stu-id="4be67-367">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="4be67-368">说明：此 cmdlet 列出了当前分配给租户的策略。</span><span class="sxs-lookup"><span data-stu-id="4be67-368">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="4be67-369">从客户密钥注销</span><span class="sxs-lookup"><span data-stu-id="4be67-369">Offboarding from Customer Key</span></span>

<span data-ttu-id="4be67-370">如果需要恢复为 Microsoft 托管的密钥，可以。</span><span class="sxs-lookup"><span data-stu-id="4be67-370">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="4be67-371">当你离开时，你的数据会使用每个单独工作负载支持的默认加密重新加密。</span><span class="sxs-lookup"><span data-stu-id="4be67-371">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="4be67-372">例如，Exchange Online 支持使用 Microsoft 托管密钥进行默认加密。</span><span class="sxs-lookup"><span data-stu-id="4be67-372">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="4be67-373">如果你决定从租户级别的客户密钥退出租户，请通过电子邮件请求联系 Microsoft，以在 m365ck@microsoft.com 上"禁用 ["租户服务](mailto:m365ck@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4be67-373">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4be67-374">载出与数据清除不同。</span><span class="sxs-lookup"><span data-stu-id="4be67-374">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="4be67-375">数据清除会从 Microsoft 365 中永久加密删除组织的数据，但无法进行载出。</span><span class="sxs-lookup"><span data-stu-id="4be67-375">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="4be67-376">无法对租户级别的策略执行数据清除。</span><span class="sxs-lookup"><span data-stu-id="4be67-376">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="4be67-377">有关数据清除路径的信息，请参阅 ["撤销密钥"并启动数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="4be67-377">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="4be67-378">关于可用性密钥</span><span class="sxs-lookup"><span data-stu-id="4be67-378">About the availability key</span></span>

<span data-ttu-id="4be67-379">有关可用性密钥的信息，请参阅 [了解可用性密钥](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="4be67-379">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="4be67-380">键旋转</span><span class="sxs-lookup"><span data-stu-id="4be67-380">Key rotation</span></span>

<span data-ttu-id="4be67-381">有关用于客户密钥的旋转或滚动键的信息，请参阅滚动或 [旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="4be67-381">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="4be67-382">更新 DEP 以使用新版本的密钥时，将运行 Set-M365DataAtRestEncryptionPolicy cmdlet，如本文前面所述。</span><span class="sxs-lookup"><span data-stu-id="4be67-382">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4be67-383">相关文章：</span><span class="sxs-lookup"><span data-stu-id="4be67-383">Related articles:</span></span>

- [<span data-ttu-id="4be67-384">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="4be67-384">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="4be67-385">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="4be67-385">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="4be67-386">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="4be67-386">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="4be67-387">服务加密</span><span class="sxs-lookup"><span data-stu-id="4be67-387">Service Encryption</span></span>](office-365-service-encryption.md)
