---
title: 租户级 Microsoft 365 客户密钥（公共预览版）
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/26/2021
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
description: 了解如何在租户级别为 Microsoft 365 数据设置客户密钥。
ms.openlocfilehash: 811b153d5b0a472c6e542851fec45f1f42bca59b
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394700"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="8fad8-103">租户级别的 Microsoft 365 客户密钥概述 (公共预览版) </span><span class="sxs-lookup"><span data-stu-id="8fad8-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="8fad8-104">使用你提供的密钥，可以在 DEP (创建) 策略并将其分配给租户。</span><span class="sxs-lookup"><span data-stu-id="8fad8-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="8fad8-105">创建的租户范围的 DEP 对以下数据进行加密：</span><span class="sxs-lookup"><span data-stu-id="8fad8-105">The tenant-wide DEP you create encrypts the following data:</span></span>

- <span data-ttu-id="8fad8-106">Teams 聊天消息 (一对一聊天、群聊、会议聊天和频道对话) </span><span class="sxs-lookup"><span data-stu-id="8fad8-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="8fad8-107">Teams 媒体消息 (图像、代码段、视频消息、音频消息、wiki 图像) </span><span class="sxs-lookup"><span data-stu-id="8fad8-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="8fad8-108">Teams 存储中存储的 Teams 通话和会议录像</span><span class="sxs-lookup"><span data-stu-id="8fad8-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="8fad8-109">Teams 聊天通知</span><span class="sxs-lookup"><span data-stu-id="8fad8-109">Teams chat notifications</span></span>
- <span data-ttu-id="8fad8-110">Cortana 的 Teams 聊天建议</span><span class="sxs-lookup"><span data-stu-id="8fad8-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="8fad8-111">Teams 状态消息</span><span class="sxs-lookup"><span data-stu-id="8fad8-111">Teams status messages</span></span>
- <span data-ttu-id="8fad8-112">Exchange Online 的用户和信号信息</span><span class="sxs-lookup"><span data-stu-id="8fad8-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="8fad8-113">在应用程序级别未加密客户密钥 DEP 的 Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="8fad8-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>
- <span data-ttu-id="8fad8-114">MIP 精确数据 (EDM) 数据 – (数据文件架构、规则包和用于对敏感数据进行哈希运算的) </span><span class="sxs-lookup"><span data-stu-id="8fad8-114">MIP exact data match (EDM) data – (data file schemas, rule packages, and the salts used to hash the sensitive data)</span></span>

<span data-ttu-id="8fad8-115">对于 Microsoft 信息保护和 Microsoft Teams，租户级别的客户密钥会从将 DEP 分配给租户时对新数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-115">For Microsoft Information Protection and Microsoft Teams, Customer Key at the tenant level encrypts new data from the time you assign the DEP to the tenant.</span></span> <span data-ttu-id="8fad8-116">公共预览版不支持加密过去的数据。</span><span class="sxs-lookup"><span data-stu-id="8fad8-116">Public preview doesn't support encrypting past data.</span></span> <span data-ttu-id="8fad8-117">对于 Exchange Online，客户密钥会加密所有现有和新数据。</span><span class="sxs-lookup"><span data-stu-id="8fad8-117">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="8fad8-118">可以为每个租户创建多个 DEP，但一次只能分配一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="8fad8-118">You can create multiple DEPs per tenant but can only assign one DEP at a time.</span></span> <span data-ttu-id="8fad8-119">分配 DEP 时，加密将自动开始，但需要一段时间才能完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="8fad8-119">When you assign the DEP, encryption begins automatically but takes some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="8fad8-120">租户级别策略为 Microsoft 365 的客户密钥添加了更广泛的控制</span><span class="sxs-lookup"><span data-stu-id="8fad8-120">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="8fad8-121">如果你已设置 Exchange Online 和 Sharepoint Online 的客户密钥，下面将说明新的租户级别公共预览的适用方式。</span><span class="sxs-lookup"><span data-stu-id="8fad8-121">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="8fad8-122">你创建的租户级加密策略对 Microsoft 365 中的 Microsoft Teams 和 Exchange Online 工作负载的所有数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-122">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="8fad8-123">但是，对于 Exchange Online，如果已经将客户密钥 DEP 分配给各个邮箱，租户级别的策略将不会覆盖这些 DECP。</span><span class="sxs-lookup"><span data-stu-id="8fad8-123">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="8fad8-124">租户级别的策略将仅加密未分配邮箱级别的客户密钥 DEP 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8fad8-124">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span> <span data-ttu-id="8fad8-125">使用租户级别 DEP 加密用户邮箱时，其所有内容都将被加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-125">When you encrypt a user mailbox using a tenant level DEP, all its content gets encrypted.</span></span> <span data-ttu-id="8fad8-126">有关在应用程序级别使用 DEP 加密内容的信息，请参阅使用客户密钥 [进行服务加密](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-126">For information about what gets encrypted with a DEP at the application level, see [Service encryption with Customer Key](customer-key-overview.md).</span></span>

## <a name="data-that-isnt-encrypted-with-customer-key-at-the-tenant-level"></a><span data-ttu-id="8fad8-127">在租户级别未使用客户密钥加密的数据</span><span class="sxs-lookup"><span data-stu-id="8fad8-127">Data that isn't encrypted with Customer Key at the tenant level</span></span>

<span data-ttu-id="8fad8-128">客户密钥不会在租户级别加密以下类型的数据。</span><span class="sxs-lookup"><span data-stu-id="8fad8-128">Customer Key doesn't encrypt the following types of data at the tenant level.</span></span> <span data-ttu-id="8fad8-129">相反，Microsoft 365 使用其他类型的加密来保护此数据。</span><span class="sxs-lookup"><span data-stu-id="8fad8-129">Instead, Microsoft 365 uses other types of encryption to protect this data.</span></span>

- <span data-ttu-id="8fad8-130">已在应用程序级别使用客户密钥 DEP 加密的 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="8fad8-130">Exchange online mailboxes that you've already encrypted using a Customer Key DEP at the application level.</span></span> <span data-ttu-id="8fad8-131">未为其分配客户密钥 DEP 的邮箱将使用租户级别的 DEP 进行加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-131">Mailboxes that don't have a Customer Key DEP assigned to them will be encrypted using the tenant level DEP.</span></span> <span data-ttu-id="8fad8-132">这种安排意味着你可能有一些使用租户级别 DEP 加密的邮箱，还有一些使用应用程序级别 DEP 加密的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8fad8-132">This arrangement means that you may have some mailboxes encrypted with a tenant level DEP and some mailboxes encrypted with application level DEPs.</span></span>
- <span data-ttu-id="8fad8-133">SharePoint 和 OneDrive for Business 在应用程序级别使用客户密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-133">SharePoint and OneDrive for Business use Customer Key at the application level.</span></span> <span data-ttu-id="8fad8-134">单个 DEP 对单个地理位置的 SharePoint 中的内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-134">A single DEP encrypts content in SharePoint for a single geo.</span></span>
- <span data-ttu-id="8fad8-135">保存在 OneDrive for Business 和 SharePoint 中的 Microsoft Teams 文件和一些 Teams 通话和会议录像由 SharePoint Online DEP 进行加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-135">Microsoft Teams files and some Teams call and meeting recordings saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span>

<span data-ttu-id="8fad8-136">Microsoft 365 客户密钥当前不支持的任何工作负载或方案。</span><span class="sxs-lookup"><span data-stu-id="8fad8-136">Any workloads or scenarios that aren't currently supported by Customer Key for Microsoft 365.</span></span>

- <span data-ttu-id="8fad8-137">其他 Microsoft 365 工作负载，如 Yammer、Planner 等。</span><span class="sxs-lookup"><span data-stu-id="8fad8-137">Other Microsoft 365 workloads such as Yammer, Planner, and so on.</span></span>
- <span data-ttu-id="8fad8-138">Teams 实时事件和&实时事件的问答。</span><span class="sxs-lookup"><span data-stu-id="8fad8-138">Teams Live Events and Q&A in Live Events.</span></span> <span data-ttu-id="8fad8-139">对于 Teams，此方案是唯一一个未通过租户级别的客户密钥加密的方案。</span><span class="sxs-lookup"><span data-stu-id="8fad8-139">For Teams, this scenario is the only one that isn't encrypted by Customer Key at the tenant level.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="8fad8-140">在租户级别设置客户密钥 (公共预览版) </span><span class="sxs-lookup"><span data-stu-id="8fad8-140">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="8fad8-141">这些步骤与在应用程序级别设置客户密钥的步骤类似，但不完全相同。</span><span class="sxs-lookup"><span data-stu-id="8fad8-141">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="8fad8-142">仅对测试租户中的测试数据使用此公共预览。</span><span class="sxs-lookup"><span data-stu-id="8fad8-142">Only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="8fad8-143">不要将此版本与生产数据或生产环境一同使用。</span><span class="sxs-lookup"><span data-stu-id="8fad8-143">Don't use this release with production data or in your production environment.</span></span> <span data-ttu-id="8fad8-144">如果你已经拥有客户密钥的生产部署，请使用以下步骤在测试环境中在租户级别设置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-144">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span> <span data-ttu-id="8fad8-145">向租户分配租户级别 DEP 后，你可以启动验证过程，并联系你 m365ck@microsoft.com 或问题。</span><span class="sxs-lookup"><span data-stu-id="8fad8-145">Once you've assigned a tenant level DEP to your tenant, you can start the validation process and contact m365ck@microsoft.com with any questions or concerns.</span></span> <span data-ttu-id="8fad8-146">还可以在 [Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation)静态加密的验证说明的公共预览中查找记录验证步骤。</span><span class="sxs-lookup"><span data-stu-id="8fad8-146">You can also find documented validation steps in the public preview of [Validation Instructions for Data-at-rest Encryption for Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation).</span></span>

<span data-ttu-id="8fad8-147">你通过远程连接到 Azure PowerShell 完成大部分任务。</span><span class="sxs-lookup"><span data-stu-id="8fad8-147">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="8fad8-148">为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8fad8-148">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="8fad8-149">开始之前：</span><span class="sxs-lookup"><span data-stu-id="8fad8-149">Before you begin:</span></span>

- <span data-ttu-id="8fad8-150">你需要使用具有合规性管理员角色的工作或学校帐户在租户级别设置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-150">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="8fad8-151">确保你的组织具有适当的许可。</span><span class="sxs-lookup"><span data-stu-id="8fad8-151">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="8fad8-152">使用付费的、已开票的 Azure 订阅，企业协议云服务提供商。</span><span class="sxs-lookup"><span data-stu-id="8fad8-152">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="8fad8-153">客户密钥不支持使用即付即用计划或信用卡购买的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8fad8-153">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="8fad8-154">从 2020 年 4 月 1 日起，Office 365 中的客户密钥在 Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 合规性和 Microsoft 365 E5 信息保护 & 治理 SK 中提供。</span><span class="sxs-lookup"><span data-stu-id="8fad8-154">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="8fad8-155">Office 365 高级合规性 SKU 不再可用于新许可证。</span><span class="sxs-lookup"><span data-stu-id="8fad8-155">Office 365 Advanced Compliance SKU is no longer available for new licenses.</span></span> <span data-ttu-id="8fad8-156">现有 Office 365 高级合规性许可证将继续受支持。</span><span class="sxs-lookup"><span data-stu-id="8fad8-156">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="8fad8-157">虽然该服务可以在租户下至少具有一个经过适当许可的用户进行启用，但仍应确保从该服务受益的所有用户都有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="8fad8-157">While the service can be enabled with a minimum of one appropriately licensed user under the tenant, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="8fad8-158">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="8fad8-158">Create two new Azure subscriptions</span></span>

<span data-ttu-id="8fad8-159">客户密钥要求 DEP 策略中每个数据加密策略 (两) 。</span><span class="sxs-lookup"><span data-stu-id="8fad8-159">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="8fad8-160">若要创建两个密钥，必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8fad8-160">To create two keys, you must create two Azure subscriptions.</span></span> <span data-ttu-id="8fad8-161">最佳做法是，Microsoft 建议你组织单独的成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-161">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="8fad8-162">仅使用这些 Azure 订阅来管理 Microsoft 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-162">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="8fad8-163">如果你的一个运营者意外、有意或恶意删除或以其他方式管理他们负责的密钥，遵循这些准则有助于保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="8fad8-163">Following these guidelines helps protect your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="8fad8-164">对于你可以为组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="8fad8-164">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="8fad8-165">遵循此最佳做法有助于最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="8fad8-165">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="8fad8-166">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="8fad8-166">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="8fad8-167">根加密密钥的临时或永久丢失可能会导致服务操作中断甚至出现灾难性问题，并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="8fad8-167">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="8fad8-168">因此，用于客户密钥的资源需要强大的保护。</span><span class="sxs-lookup"><span data-stu-id="8fad8-168">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="8fad8-169">与客户密钥一起使用的所有 Azure 资源都提供除默认配置以外的保护机制。</span><span class="sxs-lookup"><span data-stu-id="8fad8-169">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="8fad8-170">Azure 订阅可以通过防止立即和不可撤销取消的方式进行标记或注册。</span><span class="sxs-lookup"><span data-stu-id="8fad8-170">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="8fad8-171">此过程称为注册强制保留期。</span><span class="sxs-lookup"><span data-stu-id="8fad8-171">This process is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="8fad8-172">为 Azure 订阅注册强制保留期所需的步骤需要与 Microsoft 协作。</span><span class="sxs-lookup"><span data-stu-id="8fad8-172">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="8fad8-173">此过程最多可能需要 5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="8fad8-173">This process can take up to five business days.</span></span> <span data-ttu-id="8fad8-174">以前，此过程有时称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="8fad8-174">Previously, this process was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="8fad8-175">在联系 Microsoft 365 团队之前，你必须对使用客户密钥的每个 Azure 订阅执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8fad8-175">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="8fad8-176">在启动之前，请确保已安装 [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) 模块。</span><span class="sxs-lookup"><span data-stu-id="8fad8-176">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="8fad8-177">使用 Azure PowerShell 登录。</span><span class="sxs-lookup"><span data-stu-id="8fad8-177">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="8fad8-178">有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-178">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="8fad8-179">运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="8fad8-179">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="8fad8-180">对于每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fad8-180">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="8fad8-181">请与 Microsoft 联系，让该过程在 m365ck@microsoft.com[完成。](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8fad8-181">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="8fad8-182">在电子邮件中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="8fad8-182">Include the following content in your email:</span></span>

   <span data-ttu-id="8fad8-183">**主题**：客户密钥 \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="8fad8-183">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="8fad8-184">**正文**：要完成其强制保留期的订阅 ID。</span><span class="sxs-lookup"><span data-stu-id="8fad8-184">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="8fad8-185">每个订阅Get-AzProviderFeature的订阅输出。</span><span class="sxs-lookup"><span data-stu-id="8fad8-185">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="8fad8-186">完成此过程的服务级别协议 (SLA) 在向 Microsoft 通知 (并验证) 你已注册订阅以使用强制保留期后，5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="8fad8-186">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="8fad8-187">从 Microsoft 收到注册完成通知后，通过运行 Get-AzProviderFeature 命令验证注册状态。</span><span class="sxs-lookup"><span data-stu-id="8fad8-187">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="8fad8-188">如果已验证，Get-AzProviderFeature返回 Registration **State** 属性的值 **Registered。**</span><span class="sxs-lookup"><span data-stu-id="8fad8-188">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="8fad8-189">对于每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fad8-189">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="8fad8-190">若要完成此过程，请运行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="8fad8-190">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="8fad8-191">对于每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fad8-191">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="8fad8-192">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="8fad8-192">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="8fad8-193">[Azure](/azure/key-vault/general/overview)密钥保管库入门中记录了创建密钥保管库的步骤，可指导你完成安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建该资源组中密钥保管库的步骤。</span><span class="sxs-lookup"><span data-stu-id="8fad8-193">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="8fad8-194">创建密钥保管库时，必须选择 SKU：Standard 或 Premium。</span><span class="sxs-lookup"><span data-stu-id="8fad8-194">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="8fad8-195">标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护）并且高级 SKU 允许使用 HSM 来保护密钥保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-195">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="8fad8-196">客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="8fad8-196">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="8fad8-197">使用任一类型的密钥的操作成本相同，因此成本的唯一差别是每个受 HSM 保护的密钥的每月成本。</span><span class="sxs-lookup"><span data-stu-id="8fad8-197">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="8fad8-198">有关详细信息 [，请参阅密钥保管](https://azure.microsoft.com/pricing/details/key-vault/) 库定价。</span><span class="sxs-lookup"><span data-stu-id="8fad8-198">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8fad8-199">将高级 SKU 密钥保管库和 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。</span><span class="sxs-lookup"><span data-stu-id="8fad8-199">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="8fad8-200">对密钥保管库使用通用前缀，并包括密钥保管库和密钥的使用和范围的缩写。</span><span class="sxs-lookup"><span data-stu-id="8fad8-200">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="8fad8-201">例如，对于保管库将位于北美的 Contoso 服务，可能的名称对是 Contoso-O365-NA-VaultA1 和 Contoso-O365-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="8fad8-201">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="8fad8-202">保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。</span><span class="sxs-lookup"><span data-stu-id="8fad8-202">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="8fad8-203">配置后，无法更改保管库名称，因此最佳做法是制定一份书面设置计划，并使用第二个人验证计划是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="8fad8-203">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="8fad8-204">如果可能，在非配对区域创建保管库。</span><span class="sxs-lookup"><span data-stu-id="8fad8-204">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="8fad8-205">成对的 Azure 区域跨服务失败域提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="8fad8-205">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="8fad8-206">因此，可以将区域对视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="8fad8-206">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="8fad8-207">放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。</span><span class="sxs-lookup"><span data-stu-id="8fad8-207">An Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="8fad8-208">为数据加密策略中使用的两个区域选择区域（这些区域已配对）意味着总共只有两个可用性区域在使用。</span><span class="sxs-lookup"><span data-stu-id="8fad8-208">Choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="8fad8-209">大多数地理位置只有两个区域，因此尚无法选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="8fad8-209">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="8fad8-210">如果可能，请为与数据加密策略一同使用的两个保管库选择两个非配对区域。</span><span class="sxs-lookup"><span data-stu-id="8fad8-210">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="8fad8-211">此方案从共四个可用性区域中获益。</span><span class="sxs-lookup"><span data-stu-id="8fad8-211">This scenario benefits from a total of four regions of availability.</span></span> <span data-ttu-id="8fad8-212">有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：当前](/azure/best-practices-availability-paired-regions) 区域对列表的 Azure 配对区域。</span><span class="sxs-lookup"><span data-stu-id="8fad8-212">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="8fad8-213">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="8fad8-213">Assign permissions to each key vault</span></span>

<span data-ttu-id="8fad8-214">对于每个密钥保管库，你将需要为客户密钥定义三组单独的权限，具体取决于你的实现。</span><span class="sxs-lookup"><span data-stu-id="8fad8-214">For each key vault, you'll need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="8fad8-215">例如，需要为每个权限集定义一组权限：</span><span class="sxs-lookup"><span data-stu-id="8fad8-215">For example, you'll need to define one set of permissions for each of these:</span></span>
  
- <span data-ttu-id="8fad8-216">**将为组织执行** 密钥保管库日常管理的关键保管库管理员。</span><span class="sxs-lookup"><span data-stu-id="8fad8-216">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="8fad8-217">这些任务包括备份、创建、获取、导入、列表和还原。</span><span class="sxs-lookup"><span data-stu-id="8fad8-217">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="8fad8-218">分配给密钥保管库管理员的权限集不包括删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="8fad8-218">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="8fad8-219">这是有意为之，也是一项重要的做法。</span><span class="sxs-lookup"><span data-stu-id="8fad8-219">This is intentional and an important practice.</span></span> <span data-ttu-id="8fad8-220">通常不删除加密密钥，因为这样做会永久破坏数据。</span><span class="sxs-lookup"><span data-stu-id="8fad8-220">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="8fad8-221">作为最佳实践，默认情况下不要向密钥保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="8fad8-221">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="8fad8-222">相反，请为密钥保管库参与者保留此策略，并且仅在明确了解后果后将其短期分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="8fad8-222">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="8fad8-223">若要向贵组织的用户分配这些权限，请通过 Azure PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8fad8-223">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="8fad8-224">有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-224">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="8fad8-225">运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="8fad8-225">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="8fad8-226">例如：</span><span class="sxs-lookup"><span data-stu-id="8fad8-226">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="8fad8-227">**可以更改 Azure** 密钥保管库本身权限的密钥保管库参与者。</span><span class="sxs-lookup"><span data-stu-id="8fad8-227">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="8fad8-228">当员工离开或加入团队时，或者当密钥保管库管理员合法需要删除或还原密钥的极少数情况下，你将需要更改这些权限。</span><span class="sxs-lookup"><span data-stu-id="8fad8-228">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="8fad8-229">需要向这组密钥保管库参与者授予密钥保管库上的参与者角色。</span><span class="sxs-lookup"><span data-stu-id="8fad8-229">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="8fad8-230">可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="8fad8-230">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="8fad8-231">有关详细步骤，请参阅使用 [Role-Based访问控制](/azure/active-directory/role-based-access-control-configure) 管理对 Azure 订阅资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8fad8-231">For detailed steps, see [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="8fad8-232">默认情况下，创建订阅的管理员具有此访问权限，并且能够将其他管理员分配到参与者角色。</span><span class="sxs-lookup"><span data-stu-id="8fad8-232">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="8fad8-233">**Microsoft 365** 静态数据加密服务，该服务在租户级别处理客户密钥的工作。</span><span class="sxs-lookup"><span data-stu-id="8fad8-233">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="8fad8-234">若要向 Microsoft 365 授予权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用下列语法：</span><span class="sxs-lookup"><span data-stu-id="8fad8-234">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="8fad8-235">其中：</span><span class="sxs-lookup"><span data-stu-id="8fad8-235">Where:</span></span>

  - <span data-ttu-id="8fad8-236">*保管库* 名称是创建的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="8fad8-236">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="8fad8-237">示例：对于 Microsoft 365 静态数据加密服务，将 *Microsoft 365 appID 替换为*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="8fad8-237">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="8fad8-238">启用密钥保管库，然后确认软删除</span><span class="sxs-lookup"><span data-stu-id="8fad8-238">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="8fad8-239">如果可以快速恢复密钥，不太可能因意外或恶意删除密钥而遇到服务中断。</span><span class="sxs-lookup"><span data-stu-id="8fad8-239">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="8fad8-240">启用此配置（称为软删除）后，才能将密钥与客户密钥一同使用。</span><span class="sxs-lookup"><span data-stu-id="8fad8-240">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="8fad8-241">启用软删除后，您可以在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="8fad8-241">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="8fad8-242">若要在密钥保管库上启用软删除，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8fad8-242">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="8fad8-243">使用 Windows PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8fad8-243">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="8fad8-244">有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-244">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="8fad8-245">运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8fad8-245">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="8fad8-246">本示例中， *保管库* 名称是要启用软删除的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="8fad8-246">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="8fad8-247">通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置了软删除。</span><span class="sxs-lookup"><span data-stu-id="8fad8-247">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="8fad8-248">如果为密钥保管库正确配置了软删除，则"启用 _软_ 删除"属性将返回值 **True**：</span><span class="sxs-lookup"><span data-stu-id="8fad8-248">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="8fad8-249">通过创建或导入密钥将密钥添加到每个密钥保管库</span><span class="sxs-lookup"><span data-stu-id="8fad8-249">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="8fad8-250">有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在密钥保管库中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-250">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="8fad8-251">直接在密钥保管库中创建密钥是不太复杂的方法，而导入密钥可提供对密钥生成方式的总控制。</span><span class="sxs-lookup"><span data-stu-id="8fad8-251">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="8fad8-252">使用 RSA 密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-252">Use the RSA keys.</span></span> <span data-ttu-id="8fad8-253">Azure Key Vault 不支持使用椭圆曲线键换行和取消环绕。</span><span class="sxs-lookup"><span data-stu-id="8fad8-253">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="8fad8-254">若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-254">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="8fad8-255">其中：</span><span class="sxs-lookup"><span data-stu-id="8fad8-255">Where:</span></span>

- <span data-ttu-id="8fad8-256">*保管* 库名称是你想要创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="8fad8-256">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="8fad8-257">*key name* 是你想要提供新密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="8fad8-257">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="8fad8-258">使用与上述密钥保管库类似的命名约定命名密钥。</span><span class="sxs-lookup"><span data-stu-id="8fad8-258">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="8fad8-259">这样，在只显示键名称的工具中，字符串是自描述的。</span><span class="sxs-lookup"><span data-stu-id="8fad8-259">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="8fad8-260">如果要使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则请指定 **Software**。</span><span class="sxs-lookup"><span data-stu-id="8fad8-260">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="8fad8-261">例如，</span><span class="sxs-lookup"><span data-stu-id="8fad8-261">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="8fad8-262">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="8fad8-262">Check the recovery level of your keys</span></span>

<span data-ttu-id="8fad8-263">Microsoft 365 要求 Azure 密钥保管库订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。</span><span class="sxs-lookup"><span data-stu-id="8fad8-263">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="8fad8-264">可以通过查看密钥上的恢复级别来确认这些设置。</span><span class="sxs-lookup"><span data-stu-id="8fad8-264">You can confirm these settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="8fad8-265">若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-265">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="8fad8-266">如果恢复级别属性返回除 **Recoverable+ProtectedSubscription** 值外的其他值，则需要查看本文，并确保已遵循所有步骤将订阅置于"不取消"列表，并且在每个密钥保管库上启用了"软删除"。</span><span class="sxs-lookup"><span data-stu-id="8fad8-266">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="8fad8-267">接下来，将 电子邮件中的 输出屏幕截图 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` 发送到 m365ck@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="8fad8-267">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="8fad8-268">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="8fad8-268">Back up Azure Key Vault</span></span>

<span data-ttu-id="8fad8-269">创建密钥或更改密钥后，立即备份密钥并存储备份副本（联机和脱机）。</span><span class="sxs-lookup"><span data-stu-id="8fad8-269">Immediately following creation or any change to a key, back up the key and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="8fad8-270">不要将脱机副本连接到任何网络。</span><span class="sxs-lookup"><span data-stu-id="8fad8-270">Don't connect offline copies to any network.</span></span> <span data-ttu-id="8fad8-271">相反，将它们存储在物理安全或商业存储设备中。</span><span class="sxs-lookup"><span data-stu-id="8fad8-271">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="8fad8-272">应至少将一份备份副本存储在发生灾难时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="8fad8-272">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="8fad8-273">如果密钥保管库密钥被永久销毁或呈现为不可操作，备份 blob 是还原密钥材料的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="8fad8-273">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="8fad8-274">Azure 密钥保管库外部且已导入 Azure 密钥保管库的密钥不符合备份条件，因为客户密钥使用密钥所需的元数据不存在于外部密钥中。</span><span class="sxs-lookup"><span data-stu-id="8fad8-274">Keys that are external to Azure Key Vault and were imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="8fad8-275">只有从 Azure 密钥保管库获取的备份可用于使用客户密钥执行还原操作。</span><span class="sxs-lookup"><span data-stu-id="8fad8-275">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="8fad8-276">因此，在上载或创建密钥后，必须备份 Azure 密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="8fad8-276">So, it's essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="8fad8-277">若要创建 Azure 密钥保管库密钥的备份，请运行 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-277">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="8fad8-278">确保输出文件使用后缀 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="8fad8-278">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="8fad8-279">此 cmdlet 生成的输出文件已加密，不能在 Azure Key Vault 外部使用。</span><span class="sxs-lookup"><span data-stu-id="8fad8-279">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="8fad8-280">备份只能还原到进行备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8fad8-280">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="8fad8-281">例如：</span><span class="sxs-lookup"><span data-stu-id="8fad8-281">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="8fad8-282">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="8fad8-282">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="8fad8-283">在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="8fad8-283">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="8fad8-284">特别是，如果使用除本主题中所述的步骤外的其他步骤设置密钥和保管库，应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。</span><span class="sxs-lookup"><span data-stu-id="8fad8-284">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="8fad8-285">若要验证密钥是否已启用 get、wrapKey 和 unwrapKey 操作：</span><span class="sxs-lookup"><span data-stu-id="8fad8-285">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="8fad8-286">运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-286">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="8fad8-287">在输出中，查找访问策略，并查找适用于 GUID (的 Microsoft 365) ID。</span><span class="sxs-lookup"><span data-stu-id="8fad8-287">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="8fad8-288">所有三个操作（get、wrapKey 和 unwrapKey）都必须显示在"密钥权限"下。</span><span class="sxs-lookup"><span data-stu-id="8fad8-288">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="8fad8-289">如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-289">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="8fad8-290">示例：对于 Microsoft 365 静态数据加密服务，将 *Microsoft 365 appID 替换为*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="8fad8-290">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="8fad8-291">若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-291">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="8fad8-292">客户密钥无法使用过期密钥，尝试使用过期密钥的操作将失败，并可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="8fad8-292">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="8fad8-293">我们强烈建议用于客户密钥的密钥没有过期日期。</span><span class="sxs-lookup"><span data-stu-id="8fad8-293">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="8fad8-294">一旦设置过期日期，就无法删除，但可以更改为其他日期。</span><span class="sxs-lookup"><span data-stu-id="8fad8-294">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="8fad8-295">如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="8fad8-295">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="8fad8-296">到期日期设置为 12/31/9999 外日期的密钥无法通过 Microsoft 365 验证。</span><span class="sxs-lookup"><span data-stu-id="8fad8-296">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="8fad8-297">若要更改已设置为 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fad8-297">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="8fad8-298">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="8fad8-298">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="8fad8-299">完成 Azure 中设置密钥保管库并添加密钥的所有步骤后，运行以下命令，获取每个密钥保管库中密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="8fad8-299">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="8fad8-300">稍后创建和分配每个 DEP 时，将需要使用这些 URI，因此将此信息保存在一个安全的位置。</span><span class="sxs-lookup"><span data-stu-id="8fad8-300">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="8fad8-301">请记住，针对每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="8fad8-301">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="8fad8-302">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="8fad8-302">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="8fad8-303">为租户设置客户密钥加密策略</span><span class="sxs-lookup"><span data-stu-id="8fad8-303">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="8fad8-304">您需获得权限，然后才能运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8fad8-304">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="8fad8-305">虽然本文列出了 cmdlet 的所有参数，但如果这些参数未包含在分配给您的权限中，则您可能无法访问这些参数。</span><span class="sxs-lookup"><span data-stu-id="8fad8-305">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="8fad8-306">若要查找在贵组织中运行任何 cmdlet 或参数所需的权限，请参阅 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-306">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="8fad8-307">创建策略</span><span class="sxs-lookup"><span data-stu-id="8fad8-307">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="8fad8-308">说明：允许合规性管理员使用两个 AKV 根密钥 (DEP) 数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-308">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="8fad8-309">创建策略后，可以使用 cmdlet 分配Set-M365DataAtRestEncryptionPolicyAssignment策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-309">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="8fad8-310">第一次分配密钥或旋转密钥后，新密钥可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="8fad8-310">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="8fad8-311">如果新的 DEP 需要 24 小时以上才能生效，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="8fad8-311">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="8fad8-312">示例：</span><span class="sxs-lookup"><span data-stu-id="8fad8-312">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="8fad8-313">参数：</span><span class="sxs-lookup"><span data-stu-id="8fad8-313">Parameters:</span></span>

| <span data-ttu-id="8fad8-314">名称</span><span class="sxs-lookup"><span data-stu-id="8fad8-314">Name</span></span> | <span data-ttu-id="8fad8-315">说明</span><span class="sxs-lookup"><span data-stu-id="8fad8-315">Description</span></span> | <span data-ttu-id="8fad8-316">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="8fad8-316">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="8fad8-317">名称</span><span class="sxs-lookup"><span data-stu-id="8fad8-317">Name</span></span>|<span data-ttu-id="8fad8-318">数据加密策略的友好名称</span><span class="sxs-lookup"><span data-stu-id="8fad8-318">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="8fad8-319">网络</span><span class="sxs-lookup"><span data-stu-id="8fad8-319">N</span></span>|
|<span data-ttu-id="8fad8-320">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="8fad8-320">AzureKeyIDs</span></span>|<span data-ttu-id="8fad8-321">指定 Azure 密钥保管库密钥的两个 URI 值（用逗号分隔）以与数据加密策略关联</span><span class="sxs-lookup"><span data-stu-id="8fad8-321">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="8fad8-322">网络</span><span class="sxs-lookup"><span data-stu-id="8fad8-322">N</span></span>|
|<span data-ttu-id="8fad8-323">说明</span><span class="sxs-lookup"><span data-stu-id="8fad8-323">Description</span></span>|<span data-ttu-id="8fad8-324">数据加密策略的说明</span><span class="sxs-lookup"><span data-stu-id="8fad8-324">Description of the data encryption policy</span></span>|<span data-ttu-id="8fad8-325">网络</span><span class="sxs-lookup"><span data-stu-id="8fad8-325">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="8fad8-326">分配策略</span><span class="sxs-lookup"><span data-stu-id="8fad8-326">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

<span data-ttu-id="8fad8-327">说明：此 cmdlet 用于配置默认数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-327">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="8fad8-328">然后，此策略将用于加密所有支持工作负载的数据。</span><span class="sxs-lookup"><span data-stu-id="8fad8-328">This policy will be used to then encrypt data across all support workloads.</span></span>

<span data-ttu-id="8fad8-329">示例：</span><span class="sxs-lookup"><span data-stu-id="8fad8-329">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

<span data-ttu-id="8fad8-330">参数：</span><span class="sxs-lookup"><span data-stu-id="8fad8-330">Parameters:</span></span>

| <span data-ttu-id="8fad8-331">名称</span><span class="sxs-lookup"><span data-stu-id="8fad8-331">Name</span></span> | <span data-ttu-id="8fad8-332">说明</span><span class="sxs-lookup"><span data-stu-id="8fad8-332">Description</span></span> | <span data-ttu-id="8fad8-333">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="8fad8-333">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="8fad8-334">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="8fad8-334">-DataEncryptionPolicy</span></span>|<span data-ttu-id="8fad8-335">指定需要分配的数据加密策略;指定策略名称或策略 ID。</span><span class="sxs-lookup"><span data-stu-id="8fad8-335">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="8fad8-336">网络</span><span class="sxs-lookup"><span data-stu-id="8fad8-336">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="8fad8-337">修改或刷新策略</span><span class="sxs-lookup"><span data-stu-id="8fad8-337">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="8fad8-338">说明：该 cmdlet 可用于修改或刷新现有策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-338">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="8fad8-339">它还可用于启用或禁用策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-339">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="8fad8-340">第一次分配密钥或旋转密钥后，新密钥可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="8fad8-340">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="8fad8-341">如果新的 DEP 需要 24 小时以上才能生效，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="8fad8-341">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="8fad8-342">示例：</span><span class="sxs-lookup"><span data-stu-id="8fad8-342">Examples:</span></span>

<span data-ttu-id="8fad8-343">禁用数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-343">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="8fad8-344">刷新数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-344">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

<span data-ttu-id="8fad8-345">参数：</span><span class="sxs-lookup"><span data-stu-id="8fad8-345">Parameters:</span></span>

| <span data-ttu-id="8fad8-346">名称</span><span class="sxs-lookup"><span data-stu-id="8fad8-346">Name</span></span> | <span data-ttu-id="8fad8-347">说明</span><span class="sxs-lookup"><span data-stu-id="8fad8-347">Description</span></span> | <span data-ttu-id="8fad8-348">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="8fad8-348">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="8fad8-349">-Identity</span><span class="sxs-lookup"><span data-stu-id="8fad8-349">-Identity</span></span>|<span data-ttu-id="8fad8-350">指定要修改的数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-350">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="8fad8-351">网络</span><span class="sxs-lookup"><span data-stu-id="8fad8-351">N</span></span>|
|<span data-ttu-id="8fad8-352">-Refresh</span><span class="sxs-lookup"><span data-stu-id="8fad8-352">-Refresh</span></span>|<span data-ttu-id="8fad8-353">在 Azure Key Vault 中旋转任意关联密钥后，使用 Refresh 开关更新数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-353">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="8fad8-354">不必为此开关指定值。</span><span class="sxs-lookup"><span data-stu-id="8fad8-354">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="8fad8-355">Y</span><span class="sxs-lookup"><span data-stu-id="8fad8-355">Y</span></span>|
|<span data-ttu-id="8fad8-356">- 已启用</span><span class="sxs-lookup"><span data-stu-id="8fad8-356">-Enabled</span></span>|<span data-ttu-id="8fad8-357">Enabled 参数启用或禁用数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-357">The Enabled parameter enables or disables the data encryption policy.</span></span> <span data-ttu-id="8fad8-358">在禁用策略之前，必须从租户取消分配它。</span><span class="sxs-lookup"><span data-stu-id="8fad8-358">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="8fad8-359">有效值为：</span><span class="sxs-lookup"><span data-stu-id="8fad8-359">Valid values are:</span></span></br > <span data-ttu-id="8fad8-360">$true：策略已启用</span><span class="sxs-lookup"><span data-stu-id="8fad8-360">$true: The policy is enabled</span></span></br > <span data-ttu-id="8fad8-361">$true：启用此策略。此为默认值。
</span><span class="sxs-lookup"><span data-stu-id="8fad8-361">$false: The policy is disabled.</span></span>|<span data-ttu-id="8fad8-362">Y</span><span class="sxs-lookup"><span data-stu-id="8fad8-362">Y</span></span>|
|<span data-ttu-id="8fad8-363">-Name</span><span class="sxs-lookup"><span data-stu-id="8fad8-363">-Name</span></span>|<span data-ttu-id="8fad8-364">Name 参数指定数据加密策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8fad8-364">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="8fad8-365">Y</span><span class="sxs-lookup"><span data-stu-id="8fad8-365">Y</span></span>|
|<span data-ttu-id="8fad8-366">-Description</span><span class="sxs-lookup"><span data-stu-id="8fad8-366">-Description</span></span>|<span data-ttu-id="8fad8-367">Description 参数指定数据加密策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="8fad8-367">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="8fad8-368">Y</span><span class="sxs-lookup"><span data-stu-id="8fad8-368">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="8fad8-369">获取策略详细信息</span><span class="sxs-lookup"><span data-stu-id="8fad8-369">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="8fad8-370">说明：此 cmdlet 列出了为租户创建的所有 M365DataAtRest 加密策略或有关特定策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8fad8-370">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="8fad8-371">示例：</span><span class="sxs-lookup"><span data-stu-id="8fad8-371">Examples:</span></span>

<span data-ttu-id="8fad8-372">本示例返回组织中 M365DatAtRest 加密策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="8fad8-372">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="8fad8-373">此示例返回名为"NAM Policy"的数据加密策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8fad8-373">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="8fad8-374">参数：</span><span class="sxs-lookup"><span data-stu-id="8fad8-374">Parameters:</span></span>

| <span data-ttu-id="8fad8-375">名称</span><span class="sxs-lookup"><span data-stu-id="8fad8-375">Name</span></span> | <span data-ttu-id="8fad8-376">说明</span><span class="sxs-lookup"><span data-stu-id="8fad8-376">Description</span></span> | <span data-ttu-id="8fad8-377">可选 (Y/N) </span><span class="sxs-lookup"><span data-stu-id="8fad8-377">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="8fad8-378">-Identity</span><span class="sxs-lookup"><span data-stu-id="8fad8-378">-Identity</span></span>|<span data-ttu-id="8fad8-379">指定要列出其详细信息的数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-379">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="8fad8-380">Y</span><span class="sxs-lookup"><span data-stu-id="8fad8-380">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="8fad8-381">获取策略分配信息</span><span class="sxs-lookup"><span data-stu-id="8fad8-381">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="8fad8-382">说明：此 cmdlet 列出当前分配给租户的策略。</span><span class="sxs-lookup"><span data-stu-id="8fad8-382">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key-at-the-tenant-level"></a><span data-ttu-id="8fad8-383">从租户级别的客户密钥载出</span><span class="sxs-lookup"><span data-stu-id="8fad8-383">Offboarding from Customer Key at the tenant level</span></span>

<span data-ttu-id="8fad8-384">如果需要还原到 Microsoft 管理的密钥，可以。</span><span class="sxs-lookup"><span data-stu-id="8fad8-384">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="8fad8-385">当你离开时，你的数据会使用每个工作负荷支持的默认加密重新加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-385">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="8fad8-386">例如，Exchange Online 支持使用 Microsoft 管理的密钥进行默认加密。</span><span class="sxs-lookup"><span data-stu-id="8fad8-386">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="8fad8-387">如果你决定从租户级别的"客户密钥 ["](mailto:m365ck@microsoft.com) 中注销租户，请 m365ck@microsoft.com 请求"禁用"租户的服务。</span><span class="sxs-lookup"><span data-stu-id="8fad8-387">If you decide to offboard your tenant from Customer Key at the tenant level, email [m365ck@microsoft.com](mailto:m365ck@microsoft.com) with a request to "disable" the service for the tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fad8-388">载出与数据清除不同。</span><span class="sxs-lookup"><span data-stu-id="8fad8-388">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="8fad8-389">数据清除会从 Microsoft 365 中永久加密删除组织的数据，但无法从载出中删除。</span><span class="sxs-lookup"><span data-stu-id="8fad8-389">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="8fad8-390">无法对租户级别的策略执行数据清除。</span><span class="sxs-lookup"><span data-stu-id="8fad8-390">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="8fad8-391">有关数据清除路径的信息，请参阅 [撤销密钥并开始数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-391">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="8fad8-392">关于可用性密钥</span><span class="sxs-lookup"><span data-stu-id="8fad8-392">About the availability key</span></span>

<span data-ttu-id="8fad8-393">有关可用性密钥的信息，请参阅 [了解可用性密钥](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-393">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="8fad8-394">密钥旋转</span><span class="sxs-lookup"><span data-stu-id="8fad8-394">Key rotation</span></span>

<span data-ttu-id="8fad8-395">有关旋转或滚动用于客户密钥的密钥的信息，请参阅滚动或旋转 [客户密钥或可用性密钥](customer-key-availability-key-roll.md)。</span><span class="sxs-lookup"><span data-stu-id="8fad8-395">For information about rotating or rolling keys that you use with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="8fad8-396">更新 DEP 以使用新版本的密钥时，将运行 Set-M365DataAtRestEncryptionPolicy cmdlet，如本文前面所述。</span><span class="sxs-lookup"><span data-stu-id="8fad8-396">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8fad8-397">已知问题</span><span class="sxs-lookup"><span data-stu-id="8fad8-397">Known issues</span></span>

<span data-ttu-id="8fad8-398">当你在租户级别启用客户密钥时，你无法在 Microsoft Teams 中创建新团队。</span><span class="sxs-lookup"><span data-stu-id="8fad8-398">When you enable Customer Key at the tenant level, you can't create a new team in Microsoft Teams.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8fad8-399">相关文章</span><span class="sxs-lookup"><span data-stu-id="8fad8-399">Related articles</span></span>

- [<span data-ttu-id="8fad8-400">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="8fad8-400">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="8fad8-401">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="8fad8-401">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="8fad8-402">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="8fad8-402">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="8fad8-403">服务加密</span><span class="sxs-lookup"><span data-stu-id="8fad8-403">Service Encryption</span></span>](office-365-service-encryption.md)
