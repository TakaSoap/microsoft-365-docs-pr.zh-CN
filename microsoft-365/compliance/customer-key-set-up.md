---
title: 设置客户密钥
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何为用户设置客户密钥Microsoft 365。
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344670"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="e73c5-103">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="e73c5-103">Set up Customer Key</span></span>

<span data-ttu-id="e73c5-104">使用客户密钥，可以控制组织的加密密钥，然后配置Microsoft 365以使用它们加密 Microsoft 数据中心中的静态数据。</span><span class="sxs-lookup"><span data-stu-id="e73c5-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="e73c5-105">换句话说，客户密钥允许客户使用其密钥添加属于他们的加密层。</span><span class="sxs-lookup"><span data-stu-id="e73c5-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span>

<span data-ttu-id="e73c5-106">设置 Azure，然后你才能将客户密钥用于Office 365。</span><span class="sxs-lookup"><span data-stu-id="e73c5-106">Set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="e73c5-107">本文介绍了创建和配置所需 Azure 资源所需的步骤，然后提供了在 Office 365 中设置客户密钥的步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-107">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="e73c5-108">设置 Azure 后，可确定要分配哪个策略（以及哪些密钥）来加密组织中各种Microsoft 365数据。</span><span class="sxs-lookup"><span data-stu-id="e73c5-108">After you set up Azure, you determine which policy, and therefore, which keys, to assign to encrypt data across various Microsoft 365 workloads in your organization.</span></span> <span data-ttu-id="e73c5-109">有关客户密钥或一般概述，请参阅使用客户密钥进行服务加密[Office 365。](customer-key-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e73c5-109">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e73c5-110">我们强烈建议您遵循本文中的最佳方案。</span><span class="sxs-lookup"><span data-stu-id="e73c5-110">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="e73c5-111">这些称为"提示 **"和"\*\*\*\*重要"。**</span><span class="sxs-lookup"><span data-stu-id="e73c5-111">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="e73c5-112">客户密钥可让你控制其作用域可以与整个组织一样大的根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-112">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="e73c5-113">这意味着，使用这些密钥所导致错误可能会产生广泛影响，并可能导致服务中断或数据的不可撤消丢失。</span><span class="sxs-lookup"><span data-stu-id="e73c5-113">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="e73c5-114">设置客户密钥之前</span><span class="sxs-lookup"><span data-stu-id="e73c5-114">Before you set up Customer Key</span></span>

<span data-ttu-id="e73c5-115">在开始使用之前，请确保你拥有适合你的组织的 Azure 订阅和许可。</span><span class="sxs-lookup"><span data-stu-id="e73c5-115">Before you get started, ensure that you have the appropriate Azure subscriptions and licensing for your organization.</span></span> <span data-ttu-id="e73c5-116">使用付费 Azure 订阅，企业协议云服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e73c5-116">Use paid Azure Subscriptions using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="e73c5-117">不接受基于信用卡的付款。</span><span class="sxs-lookup"><span data-stu-id="e73c5-117">Credit Card based payments are not accepted.</span></span> <span data-ttu-id="e73c5-118">批准并设置帐户开票需求。</span><span class="sxs-lookup"><span data-stu-id="e73c5-118">Approve and set up the account needs for invoicing.</span></span> <span data-ttu-id="e73c5-119">你通过免费、试用、支持、MSDN 订阅和旧版支持下获取的订阅不符合资格。</span><span class="sxs-lookup"><span data-stu-id="e73c5-119">Subscriptions you got through Free, Trial, Sponsorships, MSDN Subscriptions, and those under Legacy Support are not eligible.</span></span>

<span data-ttu-id="e73c5-120">Office 365E5、Microsoft 365 E5、Microsoft 365 E5 合规 和 Microsoft 365 E5 信息& SK 提供客户密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-120">Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs offer Customer Key.</span></span> <span data-ttu-id="e73c5-121">Office 365 高级合规版SKU 不再可用于购买新许可证。</span><span class="sxs-lookup"><span data-stu-id="e73c5-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="e73c5-122">现有Office 365 高级合规版许可证将继续受支持。</span><span class="sxs-lookup"><span data-stu-id="e73c5-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="e73c5-123">若要了解本文中的概念和过程，请查看 [Azure Key Vault](/azure/key-vault/) 文档。</span><span class="sxs-lookup"><span data-stu-id="e73c5-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="e73c5-124">此外，请熟悉 Azure 中使用的术语，例如 Azure [AD 租户](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>
  
<span data-ttu-id="e73c5-125">如果您需要文档之外更多的支持，请联系 Microsoft 咨询服务 (MCS) 、顶级现场工程 (PFE) 或 Microsoft 合作伙伴寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="e73c5-125">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="e73c5-126">若要提供有关客户密钥（包括文档）的反馈，请将你的想法、建议和观点发送给客户 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e73c5-126">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="e73c5-127">设置客户密钥的步骤概述</span><span class="sxs-lookup"><span data-stu-id="e73c5-127">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="e73c5-128">若要设置客户密钥，请按列出的顺序完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="e73c5-128">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="e73c5-129">本文的其余部分提供了每个任务的详细说明，或链接到过程中每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e73c5-129">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="e73c5-130">**在 Azure 和 Microsoft FastTrack 中：**</span><span class="sxs-lookup"><span data-stu-id="e73c5-130">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="e73c5-131">您将通过远程连接到远程连接到远程客户端来完成Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e73c5-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="e73c5-132">为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e73c5-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="e73c5-133">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="e73c5-133">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="e73c5-134">提交请求以激活客户密钥Office 365</span><span class="sxs-lookup"><span data-stu-id="e73c5-134">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [<span data-ttu-id="e73c5-135">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="e73c5-135">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="e73c5-136">注册可能需要一到五个工作日。</span><span class="sxs-lookup"><span data-stu-id="e73c5-136">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="e73c5-137">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="e73c5-137">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="e73c5-138">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="e73c5-138">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="e73c5-139">确保在密钥保管库上启用软删除</span><span class="sxs-lookup"><span data-stu-id="e73c5-139">Make sure soft delete is enabled on your key vaults</span></span>](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [<span data-ttu-id="e73c5-140">通过创建或导入密钥将密钥添加到每个密钥保管库</span><span class="sxs-lookup"><span data-stu-id="e73c5-140">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="e73c5-141">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="e73c5-141">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="e73c5-142">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e73c5-142">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="e73c5-143">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="e73c5-143">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="e73c5-144">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="e73c5-144">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="e73c5-145">完成 Azure Key Vault 和 Microsoft FastTrack for Customer Key 中的任务</span><span class="sxs-lookup"><span data-stu-id="e73c5-145">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="e73c5-146">在 Azure 密钥保管库中完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="e73c5-146">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="e73c5-147">你需要为使用客户密钥的所有 DEP 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-147">You'll need to complete these steps for all DEPs you use with Customer Key.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="e73c5-148">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="e73c5-148">Create two new Azure subscriptions</span></span>

<span data-ttu-id="e73c5-149">客户密钥需要两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-149">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="e73c5-150">作为最佳做法，Microsoft 建议创建用于客户密钥的新 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-150">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="e73c5-151">Azure 密钥保管库密钥只能针对同一 Azure Active Directory (Microsoft Azure Active Directory) 租户中的应用程序授权，你必须使用与将分配 DEP 的组织一同使用的 Azure AD 租户创建新订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-151">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="e73c5-152">例如，使用在组织中具有全局管理员权限的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="e73c5-152">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="e73c5-153">有关详细步骤，请参阅 [注册 Azure 作为组织](/azure/active-directory/fundamentals/sign-up-organization)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-153">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e73c5-154">客户密钥要求 DEP 策略中每个数据加密策略 (两) 。</span><span class="sxs-lookup"><span data-stu-id="e73c5-154">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="e73c5-155">为此，必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-155">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="e73c5-156">最佳做法是，Microsoft 建议你组织单独的成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-156">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="e73c5-157">你应仅使用这些 Azure 订阅来管理 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e73c5-157">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="e73c5-158">这可保护你的组织，以防你的其中一个运营者意外、有意或恶意删除或以其他方式管理他们负责的密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-158">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="e73c5-159">对于你可以为组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="e73c5-159">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="e73c5-160">遵循这些最佳做法将最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="e73c5-160">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="e73c5-161">提交请求以激活客户密钥Office 365</span><span class="sxs-lookup"><span data-stu-id="e73c5-161">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="e73c5-162">创建两个新的 Azure 订阅后，你需要在 [Microsoft FastTrack](https://fasttrack.microsoft.com/)门户中提交相应的客户密钥优惠请求。</span><span class="sxs-lookup"><span data-stu-id="e73c5-162">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="e73c5-163">在产品/服务表单中就组织中授权指定进行的选择对于完成客户密钥注册至关重要且必要。</span><span class="sxs-lookup"><span data-stu-id="e73c5-163">The selections that you make in the offer form about the authorized designations within your organization are critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="e73c5-164">贵组织中那些选定角色中的官员确保撤消和销毁用于客户密钥数据加密策略的所有密钥的请求的真实性。</span><span class="sxs-lookup"><span data-stu-id="e73c5-164">The officers in those selected roles within your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="e73c5-165">对于要用于组织的每个客户密钥 DEP 类型，需要执行一次此步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-165">You'll need to do this step once for each Customer Key DEP type that you intend to use for your organization.</span></span>

<span data-ttu-id="e73c5-166">**FastTrack 团队不提供有关客户密钥的帮助。Office 365只需使用 FastTrack 门户来提交表单，并帮助我们跟踪客户密钥的相关产品/服务。提交 FastTrack 请求后，联系相应的客户密钥载入团队以开始载入过程。**</span><span class="sxs-lookup"><span data-stu-id="e73c5-166">**The FastTrack team doesn't provide assistance with Customer Key. Office 365 simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key. Once you've submitted the FastTrack request, reach out to the corresponding Customer Key onboarding team to start the onboarding process.**</span></span>
  
<span data-ttu-id="e73c5-167">若要提交产品/服务以激活客户密钥，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e73c5-167">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="e73c5-168">使用在组织中具有全局管理员权限的工作或学校帐户，登录到 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-168">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="e73c5-169">登录后，选择相应的域。</span><span class="sxs-lookup"><span data-stu-id="e73c5-169">Once you're logged in, select the appropriate domain.</span></span>

3. <span data-ttu-id="e73c5-170">对于所选域 **，从顶部** 导航栏中选择"请求服务"，然后查看可用产品/服务的列表。</span><span class="sxs-lookup"><span data-stu-id="e73c5-170">For the selected domain, choose **Request services** from the top navigation bar, and review the list of available offers.</span></span>

4. <span data-ttu-id="e73c5-171">选择适用于你的产品/服务的信息卡：</span><span class="sxs-lookup"><span data-stu-id="e73c5-171">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="e73c5-172">**多个Microsoft 365工作负载：** 选择"**请求加密密钥帮助"，Microsoft 365** 产品/服务。</span><span class="sxs-lookup"><span data-stu-id="e73c5-172">**Multiple Microsoft 365 workloads:** Choose the **Request encryption key help for Microsoft 365** offer.</span></span>

   - <span data-ttu-id="e73c5-173">**Exchange Online和Skype for Business：** 选择"**请求加密密钥帮助"，Exchange** 产品/服务。</span><span class="sxs-lookup"><span data-stu-id="e73c5-173">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange** offer.</span></span>

   - <span data-ttu-id="e73c5-174">**SharePoint Online、OneDrive 和 Teams 文件：** 选择请求 **加密密钥帮助，SharePoint OneDrive for Business** 服务。</span><span class="sxs-lookup"><span data-stu-id="e73c5-174">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="e73c5-175">查看产品/服务详细信息后，选择"**继续"以执行步骤 2。**</span><span class="sxs-lookup"><span data-stu-id="e73c5-175">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="e73c5-176">在产品/服务表单上填写所有适用的详细信息和请求的信息。</span><span class="sxs-lookup"><span data-stu-id="e73c5-176">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="e73c5-177">请特别注意要授权贵组织的哪个官员批准对加密密钥和数据进行永久且不可恢复的销毁的选择。</span><span class="sxs-lookup"><span data-stu-id="e73c5-177">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="e73c5-178">完成表单后，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="e73c5-178">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="e73c5-179">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="e73c5-179">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="e73c5-180">根加密密钥的临时或永久丢失可能会导致服务操作中断甚至出现灾难性问题，并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="e73c5-180">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="e73c5-181">因此，用于客户密钥的资源需要强大的保护。</span><span class="sxs-lookup"><span data-stu-id="e73c5-181">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="e73c5-182">与客户密钥一起使用的所有 Azure 资源都提供除默认配置以外的保护机制。</span><span class="sxs-lookup"><span data-stu-id="e73c5-182">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="e73c5-183">你可以标记或注册 Azure 订阅，以保留 *强制保留期*。</span><span class="sxs-lookup"><span data-stu-id="e73c5-183">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="e73c5-184">强制保留期可阻止立即和不可撤销地取消 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-184">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="e73c5-185">若要将 Azure 订阅注册为强制保留期所需的步骤，需要与团队Microsoft 365协作。</span><span class="sxs-lookup"><span data-stu-id="e73c5-185">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="e73c5-186">此过程可能需要 1 到 5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="e73c5-186">This process can take from one to five business days.</span></span> <span data-ttu-id="e73c5-187">以前，强制保留期有时称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="e73c5-187">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="e73c5-188">在联系 Microsoft 365团队之前，你必须对使用客户密钥的每个 Azure 订阅执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-188">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="e73c5-189">在启动之前，[请确保Azure PowerShell Az](/powershell/azure/new-azureps-module-az)模块。</span><span class="sxs-lookup"><span data-stu-id="e73c5-189">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="e73c5-190">使用 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e73c5-190">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="e73c5-191">有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-191">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="e73c5-192">运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="e73c5-192">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="e73c5-193">针对每个订阅完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e73c5-193">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="e73c5-194">请与 Microsoft 联系以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="e73c5-194">Contact Microsoft to complete the process.</span></span>

   - <span data-ttu-id="e73c5-195">若要启用客户密钥以将 DEP 分配给各个Exchange Online，请联系[exock@microsoft.com](mailto:exock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-195">For enabling Customer Key for assigning DEP to individual Exchange Online mailboxes, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span>

   - <span data-ttu-id="e73c5-196">若要启用客户密钥以分配 DEP 以加密 SharePoint Online 和 OneDrive for Business 内容 (包括所有租户Teams文件) ，请与 spock@microsoft.com[联系。](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e73c5-196">For enabling Customer Key for assigning DEPs to encrypt SharePoint Online and OneDrive for Business content (including Teams files) for all tenant users, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span>

   - <span data-ttu-id="e73c5-197">若要启用客户密钥以分配 DEP 以加密所有租户用户的多个 Microsoft 365 工作负载 (Exchange Online、Teams、MIP EDM) ，请与 m365-ck@service.microsoft.com[联系。](mailto:m365-ck@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e73c5-197">For enabling Customer Key for assigning DEPs to encrypt content across multiple Microsoft 365 workloads (Exchange Online, Teams, MIP EDM) for all tenant users, contact [m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com).</span></span>

- <span data-ttu-id="e73c5-198">在电子邮件中包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="e73c5-198">Include the following information in your email:</span></span>

   <span data-ttu-id="e73c5-199">**主题**：客户密钥 \<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="e73c5-199">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="e73c5-200">**正文**：包括要完成其强制保留期的订阅 ID 和每个订阅Get-AzProviderFeature输出。</span><span class="sxs-lookup"><span data-stu-id="e73c5-200">**Body**:  Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="e73c5-201">完成此过程的服务级别协议 (SLA) 在向 Microsoft 通知 (并验证) 你已注册订阅以使用强制保留期后，5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="e73c5-201">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="e73c5-202">从 Microsoft 收到注册完成通知后，通过运行 Get-AzProviderFeature 命令验证注册状态。</span><span class="sxs-lookup"><span data-stu-id="e73c5-202">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="e73c5-203">如果已验证，Get-AzProviderFeature返回 Registration **State** 属性的值 **Registered。**</span><span class="sxs-lookup"><span data-stu-id="e73c5-203">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="e73c5-204">针对每个订阅完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-204">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="e73c5-205">若要完成此过程，请运行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="e73c5-205">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="e73c5-206">针对每个订阅完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-206">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="e73c5-207">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="e73c5-207">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="e73c5-208">Azure Key [Vault](/azure/key-vault/general/overview)入门中记录了创建密钥保管库的步骤，这些步骤将指导你完成安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建该资源组中密钥保管库的步骤。</span><span class="sxs-lookup"><span data-stu-id="e73c5-208">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="e73c5-209">创建密钥保管库时，必须选择 SKU：Standard 或 高级版。</span><span class="sxs-lookup"><span data-stu-id="e73c5-209">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="e73c5-210">标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护）。高级版 SKU 允许使用 HSM 保护密钥保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-210">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="e73c5-211">客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅高级版 SKU。</span><span class="sxs-lookup"><span data-stu-id="e73c5-211">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="e73c5-212">使用任一类型的密钥的操作成本相同，因此成本的唯一差别是每个受 HSM 保护的密钥的每月成本。</span><span class="sxs-lookup"><span data-stu-id="e73c5-212">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="e73c5-213">有关详细信息 [，请参阅密钥保管](https://azure.microsoft.com/pricing/details/key-vault/) 库定价。</span><span class="sxs-lookup"><span data-stu-id="e73c5-213">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e73c5-214">将 高级版 SKU 密钥保管库和 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。</span><span class="sxs-lookup"><span data-stu-id="e73c5-214">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="e73c5-215">对于每个Microsoft 365使用客户密钥的服务，在创建的两个 Azure 订阅中分别创建一个密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="e73c5-215">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="e73c5-216">例如，若要使客户密钥对 Exchange Online、SharePoint Online 和多工作负载方案使用 DESP，需要创建三对密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="e73c5-216">For example, to enable Customer Key to use DEPs for Exchange Online, SharePoint Online, and multi-workload scenarios, you'll create three pairs of key vaults.</span></span>
  
<span data-ttu-id="e73c5-217">对密钥保管库使用命名约定，该约定反映了您将与保管库关联的 DEP 的预定用途。</span><span class="sxs-lookup"><span data-stu-id="e73c5-217">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="e73c5-218">有关命名约定建议，请参阅下面的最佳做法部分。</span><span class="sxs-lookup"><span data-stu-id="e73c5-218">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="e73c5-219">为每个数据加密策略创建一组单独的配对保管库。</span><span class="sxs-lookup"><span data-stu-id="e73c5-219">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="e73c5-220">例如Exchange Online，在将策略分配给邮箱时，将选择数据加密策略的范围。</span><span class="sxs-lookup"><span data-stu-id="e73c5-220">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="e73c5-221">邮箱只能分配一个策略，并且可以创建最多 50 个策略。</span><span class="sxs-lookup"><span data-stu-id="e73c5-221">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="e73c5-222">SharePoint Online 策略的范围包括组织内地理位置或地理位置内 _的所有数据_。</span><span class="sxs-lookup"><span data-stu-id="e73c5-222">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span> <span data-ttu-id="e73c5-223">多工作负荷策略的范围包括所有用户支持的工作负荷的所有数据。</span><span class="sxs-lookup"><span data-stu-id="e73c5-223">The scope for a multi-workload policy includes all of the data across the supported workloads for all users.</span></span>

<span data-ttu-id="e73c5-224">创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量 (但小型) 和密钥保管库日志记录（如果启用）也会生成存储的数据。</span><span class="sxs-lookup"><span data-stu-id="e73c5-224">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="e73c5-225">作为最佳实践，Microsoft 建议使用单独的管理员来管理每个资源组，其管理与将管理所有相关客户密钥资源的一组管理员保持一致。</span><span class="sxs-lookup"><span data-stu-id="e73c5-225">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e73c5-226">若要最大化可用性，将密钥保管库放在 Microsoft 365 服务附近区域 例如，如果您的 Exchange Online 组织位于北美，则将密钥保管库放在北美。</span><span class="sxs-lookup"><span data-stu-id="e73c5-226">To maximize availability, place your key vaults in regions close to your Microsoft 365 service For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="e73c5-227">如果Exchange Online位于欧洲，请在欧洲放置密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="e73c5-227">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
>
> <span data-ttu-id="e73c5-228">对密钥保管库使用通用前缀，并包括密钥保管库和密钥 (的使用和范围的缩写，例如，对于保管库将位于北美洲的 Contoso SharePoint 服务，可能的名称对是 Contoso-CK-SP-NA-VaultA1 和 Contoso-CK-SP-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="e73c5-228">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-CK-SP-NA-VaultA1 and Contoso-CK-SP-NA-VaultA2.</span></span> <span data-ttu-id="e73c5-229">保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。</span><span class="sxs-lookup"><span data-stu-id="e73c5-229">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="e73c5-230">自 2017 年 7 日起，无法更改保管库名称，因此最佳做法是制定一份书面设置计划，并使用第二个人验证计划是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="e73c5-230">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
>
> <span data-ttu-id="e73c5-231">如果可能，在非配对区域创建保管库。</span><span class="sxs-lookup"><span data-stu-id="e73c5-231">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="e73c5-232">成对的 Azure 区域跨服务失败域提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="e73c5-232">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="e73c5-233">因此，可以将区域对视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="e73c5-233">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="e73c5-234">这意味着，放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。</span><span class="sxs-lookup"><span data-stu-id="e73c5-234">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="e73c5-235">因此，为数据加密策略中使用的两个保管库选择区域（这些区域已配对）意味着总共只有两个可用性区域在使用。</span><span class="sxs-lookup"><span data-stu-id="e73c5-235">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="e73c5-236">大多数地理位置只有两个区域，因此尚无法选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="e73c5-236">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="e73c5-237">如果可能，请为与数据加密策略一同使用的两个保管库选择两个非配对区域。</span><span class="sxs-lookup"><span data-stu-id="e73c5-237">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="e73c5-238">这从共四个可用性区域中获益。</span><span class="sxs-lookup"><span data-stu-id="e73c5-238">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="e73c5-239">有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：当前](/azure/best-practices-availability-paired-regions) 区域对列表的 Azure 配对区域。</span><span class="sxs-lookup"><span data-stu-id="e73c5-239">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="e73c5-240">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="e73c5-240">Assign permissions to each key vault</span></span>

<span data-ttu-id="e73c5-241">你将需要为每个密钥保管库定义三组单独的权限，具体取决于你的实现。</span><span class="sxs-lookup"><span data-stu-id="e73c5-241">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="e73c5-242">例如，您需要为以下各项定义一组权限：</span><span class="sxs-lookup"><span data-stu-id="e73c5-242">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="e73c5-243">**对组织执行** 密钥保管库日常管理的关键保管库管理员。</span><span class="sxs-lookup"><span data-stu-id="e73c5-243">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="e73c5-244">这些任务包括备份、创建、获取、导入、列表和还原。</span><span class="sxs-lookup"><span data-stu-id="e73c5-244">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e73c5-245">分配给密钥保管库管理员的权限集不包括删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="e73c5-245">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="e73c5-246">这是有意为之，也是一项重要的做法。</span><span class="sxs-lookup"><span data-stu-id="e73c5-246">This is intentional and an important practice.</span></span> <span data-ttu-id="e73c5-247">通常不删除加密密钥，因为这样做会永久破坏数据。</span><span class="sxs-lookup"><span data-stu-id="e73c5-247">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="e73c5-248">作为最佳实践，默认情况下不要向密钥保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="e73c5-248">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="e73c5-249">相反，请为密钥保管库参与者保留此策略，并且仅在明确了解后果后将其短期分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="e73c5-249">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="e73c5-250">若要向贵组织的用户分配这些权限，请通过密码登录 Azure Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e73c5-250">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="e73c5-251">有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-251">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="e73c5-252">运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="e73c5-252">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="e73c5-253">例如：</span><span class="sxs-lookup"><span data-stu-id="e73c5-253">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="e73c5-254">**可以更改 Azure** 密钥保管库本身权限的密钥保管库参与者。</span><span class="sxs-lookup"><span data-stu-id="e73c5-254">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="e73c5-255">当员工离开或加入团队时，你需要更改这些权限。</span><span class="sxs-lookup"><span data-stu-id="e73c5-255">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="e73c5-256">在密钥保管库管理员合法需要删除或还原密钥的极少数情况下，您还需要更改权限。</span><span class="sxs-lookup"><span data-stu-id="e73c5-256">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="e73c5-257">需要向这组密钥保管库参与者授予密钥保管 **库** 上的参与者角色。</span><span class="sxs-lookup"><span data-stu-id="e73c5-257">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="e73c5-258">可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="e73c5-258">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="e73c5-259">有关详细步骤，请参阅使用 [Role-Based访问控制管理对 Azure 订阅资源的访问权限](/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-259">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="e73c5-260">创建订阅的管理员具有隐式访问权限，并且能够将其他管理员分配到参与者角色。</span><span class="sxs-lookup"><span data-stu-id="e73c5-260">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="e73c5-261">**您Microsoft 365** 客户密钥使用每个密钥保管库的应用程序的权限，您需要授予 wrapKey、unwrapKey 和获取对相应 Microsoft 365 服务主体的权限。</span><span class="sxs-lookup"><span data-stu-id="e73c5-261">**Permissions to Microsoft 365 applications** for every key vault that you use for Customer Key, you need to give wrapKey, unwrapKey, and get permissions to the corresponding Microsoft 365 Service Principal.</span></span> 

<span data-ttu-id="e73c5-262">若要向服务主体Microsoft 365权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用下列语法：</span><span class="sxs-lookup"><span data-stu-id="e73c5-262">To give permission to Microsoft 365 Service Principal, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="e73c5-263">其中：</span><span class="sxs-lookup"><span data-stu-id="e73c5-263">Where:</span></span>

   - <span data-ttu-id="e73c5-264">*保管库* 名称是创建的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="e73c5-264">*vault name* is the name of the key vault you created.</span></span>
   - <span data-ttu-id="e73c5-265">对于 Exchange Online 和 Skype for Business，请将 *Office 365 appID* 替换为`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="e73c5-265">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="e73c5-266">对于 SharePoint Online、OneDrive for Business 和 Teams 文件，请将 *Office 365 appID* 替换为`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="e73c5-266">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="e73c5-267">对于适用于所有租户用户的 (Exchange、Teams、MIP EDM) ，请将 Office 365 *appID* 替换为`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="e73c5-267">For multi-workload policy (Exchange, Teams, MIP EDM) that applies to all tenant users, replace *Office 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  <span data-ttu-id="e73c5-268">示例：设置Exchange Online和Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="e73c5-268">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="e73c5-269">示例：设置 SharePoint Online、OneDrive for Business 和 Teams 权限：</span><span class="sxs-lookup"><span data-stu-id="e73c5-269">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a><span data-ttu-id="e73c5-270">确保在密钥保管库上启用软删除</span><span class="sxs-lookup"><span data-stu-id="e73c5-270">Make sure soft delete is enabled on your key vaults</span></span>

<span data-ttu-id="e73c5-271">如果可以快速恢复密钥，不太可能因意外或恶意删除密钥而遇到服务中断。</span><span class="sxs-lookup"><span data-stu-id="e73c5-271">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="e73c5-272">启用此配置（称为软删除）后，才能将密钥与客户密钥一同使用。</span><span class="sxs-lookup"><span data-stu-id="e73c5-272">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="e73c5-273">启用软删除后，您可以在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="e73c5-273">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="e73c5-274">若要在密钥保管库上启用软删除，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e73c5-274">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="e73c5-275">使用 Windows PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-275">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="e73c5-276">有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-276">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="e73c5-277">运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e73c5-277">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="e73c5-278">本示例中 *，保管库* 名称是要启用软删除的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="e73c5-278">In this example, *vault name* is the name of the key vault for which you're enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="e73c5-279">通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置了软删除。</span><span class="sxs-lookup"><span data-stu-id="e73c5-279">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="e73c5-280">如果为密钥保管库正确配置了软删除，则"启用 _软_ 删除"属性将返回值 **True**：</span><span class="sxs-lookup"><span data-stu-id="e73c5-280">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="e73c5-281">通过创建或导入密钥将密钥添加到每个密钥保管库</span><span class="sxs-lookup"><span data-stu-id="e73c5-281">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="e73c5-282">有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在密钥保管库中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-282">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="e73c5-283">直接在密钥保管库中创建密钥并不复杂，但导入密钥可完全控制密钥的生成方式。</span><span class="sxs-lookup"><span data-stu-id="e73c5-283">Creating a key directly in Key Vault is less complicated, but importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="e73c5-284">使用 RSA 密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-284">Use the RSA keys.</span></span> <span data-ttu-id="e73c5-285">Azure Key Vault 不支持使用椭圆曲线键换行和取消环绕。</span><span class="sxs-lookup"><span data-stu-id="e73c5-285">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="e73c5-286">若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73c5-286">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="e73c5-287">其中：</span><span class="sxs-lookup"><span data-stu-id="e73c5-287">Where:</span></span>

- <span data-ttu-id="e73c5-288">*保管* 库名称是你想要创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="e73c5-288">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="e73c5-289">*key name* 是你想要提供新密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="e73c5-289">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="e73c5-290">使用与上述密钥保管库类似的命名约定命名密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-290">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="e73c5-291">这样，在只显示键名称的工具中，字符串是自描述的。</span><span class="sxs-lookup"><span data-stu-id="e73c5-291">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="e73c5-292">如果要使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则请指定 **Software**。</span><span class="sxs-lookup"><span data-stu-id="e73c5-292">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="e73c5-293">例如，</span><span class="sxs-lookup"><span data-stu-id="e73c5-293">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="e73c5-294">若要将密钥直接导入密钥保管库，您需要具有 nCipher nShield 硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="e73c5-294">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="e73c5-295">一些组织倾向于使用此方法来建立其密钥的验证，然后此方法还提供以下证明：</span><span class="sxs-lookup"><span data-stu-id="e73c5-295">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="e73c5-296">用于导入的工具集包括来自 nCipher 的证明，证明用于加密生成的密钥的密钥 Exchange Key (KEK) 不可导出，并且是在 nCipher 制造的真正 HSM 内生成的。</span><span class="sxs-lookup"><span data-stu-id="e73c5-296">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="e73c5-297">工具集包括 nCipher 的证明，表明 Azure 密钥保管库安全世界也在 nCipher 制造的真正 HSM 上生成。</span><span class="sxs-lookup"><span data-stu-id="e73c5-297">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="e73c5-298">此证明证明 Microsoft 也使用正版 nCipher 硬件。</span><span class="sxs-lookup"><span data-stu-id="e73c5-298">This attestation proves that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="e73c5-299">请与安全组核实，确定是否需要上述证明。</span><span class="sxs-lookup"><span data-stu-id="e73c5-299">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="e73c5-300">有关在本地创建密钥并导入密钥保管库的详细步骤，请参阅如何为 Azure 密钥保管库生成和传输 [受 HSM 保护的密钥](/azure/key-vault/keys/hsm-protected-keys)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-300">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="e73c5-301">使用 Azure 说明在每个密钥保管库中创建密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-301">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="e73c5-302">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="e73c5-302">Check the recovery level of your keys</span></span>

<span data-ttu-id="e73c5-303">Microsoft 365 Azure Key Vault 订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。</span><span class="sxs-lookup"><span data-stu-id="e73c5-303">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="e73c5-304">可以通过查看密钥上的恢复级别来确认订阅设置。</span><span class="sxs-lookup"><span data-stu-id="e73c5-304">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="e73c5-305">若要检查密钥的恢复级别，Azure PowerShell运行以下Get-AzKeyVaultKey cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e73c5-305">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="e73c5-306">如果"恢复级别"属性返回除 **"Recoverable+ProtectedSubscription"** 值外的其他值，请确保将订阅置于"不取消"列表中，并且已在每个密钥保管库上启用软删除。</span><span class="sxs-lookup"><span data-stu-id="e73c5-306">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="e73c5-307">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e73c5-307">Back up Azure Key Vault</span></span>

<span data-ttu-id="e73c5-308">创建或更改密钥后，立即执行备份并存储备份副本（联机和脱机）。</span><span class="sxs-lookup"><span data-stu-id="e73c5-308">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="e73c5-309">不要将脱机副本连接到任何网络。</span><span class="sxs-lookup"><span data-stu-id="e73c5-309">Don't connect offline copies to any network.</span></span> <span data-ttu-id="e73c5-310">而是将它们存储在脱机位置，例如物理安全或商业存储设备中。</span><span class="sxs-lookup"><span data-stu-id="e73c5-310">Instead store them in an offline location, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="e73c5-311">应至少将一份备份副本存储在发生灾难时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="e73c5-311">At least one copy of the backup should be stored in a location that will be accessible if a disaster occurs.</span></span> <span data-ttu-id="e73c5-312">如果密钥保管库密钥被永久销毁或呈现为不可操作，备份 blob 是还原密钥材料的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="e73c5-312">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="e73c5-313">Azure 密钥保管库外部且导入到 Azure 密钥保管库的密钥不符合备份条件，因为外部密钥中不存在客户密钥使用该密钥所需的元数据。</span><span class="sxs-lookup"><span data-stu-id="e73c5-313">Keys that are external to Azure Key Vault and imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="e73c5-314">只有从 Azure 密钥保管库获取的备份可用于使用客户密钥执行还原操作。</span><span class="sxs-lookup"><span data-stu-id="e73c5-314">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="e73c5-315">因此，您必须在上载或创建密钥后创建 Azure Key Vault 备份。</span><span class="sxs-lookup"><span data-stu-id="e73c5-315">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="e73c5-316">若要创建 Azure 密钥保管库密钥的备份，请运行 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73c5-316">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="e73c5-317">确保输出文件使用后缀 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="e73c5-317">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="e73c5-318">此 cmdlet 生成的输出文件已加密，不能在 Azure Key Vault 外部使用。</span><span class="sxs-lookup"><span data-stu-id="e73c5-318">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="e73c5-319">备份只能还原到进行备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e73c5-319">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="e73c5-320">对于输出文件，选择保管库名称和密钥名称的组合。</span><span class="sxs-lookup"><span data-stu-id="e73c5-320">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="e73c5-321">这将使文件名自描述。</span><span class="sxs-lookup"><span data-stu-id="e73c5-321">This will make the file name self-describing.</span></span> <span data-ttu-id="e73c5-322">它还将确保备份文件名不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="e73c5-322">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="e73c5-323">例如：</span><span class="sxs-lookup"><span data-stu-id="e73c5-323">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="e73c5-324">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="e73c5-324">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="e73c5-325">在 DEP 中使用密钥之前验证是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="e73c5-325">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="e73c5-326">如果使用本文中所述的步骤来设置密钥和保管库，请验证 Azure Key Vault 资源的运行状况，然后再配置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-326">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="e73c5-327">若要验证密钥是否已启用 `get` 、 `wrapKey` 和 `unwrapKey` 操作：</span><span class="sxs-lookup"><span data-stu-id="e73c5-327">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="e73c5-328">运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73c5-328">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="e73c5-329">在输出中，查找访问策略和 Exchange Online GUID (GUID) 或 SharePoint Online 标识 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="e73c5-329">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="e73c5-330">以上所有三种权限都必须显示在"密钥权限"下。</span><span class="sxs-lookup"><span data-stu-id="e73c5-330">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="e73c5-331">如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73c5-331">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="e73c5-332">例如，对于 Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="e73c5-332">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="e73c5-333">例如，对于 SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="e73c5-333">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="e73c5-334">若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73c5-334">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="e73c5-335">客户密钥不能使用过期密钥。</span><span class="sxs-lookup"><span data-stu-id="e73c5-335">Customer Key can't use an expired key.</span></span> <span data-ttu-id="e73c5-336">尝试使用过期密钥的操作将失败，并可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="e73c5-336">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="e73c5-337">我们强烈建议用于客户密钥的密钥没有过期日期。</span><span class="sxs-lookup"><span data-stu-id="e73c5-337">We strongly recommend that keys used with Customer Key don't have an expiration date.</span></span> <span data-ttu-id="e73c5-338">一旦设置过期日期，就无法删除，但可以更改为其他日期。</span><span class="sxs-lookup"><span data-stu-id="e73c5-338">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="e73c5-339">如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="e73c5-339">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="e73c5-340">到期日期设置为 12/31/9999 外的日期的密钥无法通过Microsoft 365验证。</span><span class="sxs-lookup"><span data-stu-id="e73c5-340">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="e73c5-341">若要更改已设置为 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73c5-341">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="e73c5-342">不要设置与客户密钥一同使用的加密密钥的到期日期。</span><span class="sxs-lookup"><span data-stu-id="e73c5-342">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="e73c5-343">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="e73c5-343">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="e73c5-344">设置密钥保管库并添加密钥后，运行以下命令，获取每个密钥保管库中密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="e73c5-344">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="e73c5-345">稍后创建和分配每个 DEP 时，你将使用这些 URI，因此将此信息保存在一个安全的位置。</span><span class="sxs-lookup"><span data-stu-id="e73c5-345">You'll use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="e73c5-346">针对每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="e73c5-346">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="e73c5-347">在Azure PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e73c5-347">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a><span data-ttu-id="e73c5-348">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e73c5-348">Next steps</span></span>

<span data-ttu-id="e73c5-349">完成本文中的步骤后，即可创建和分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="e73c5-349">Once you've completed the steps in this article, you're ready to create and assign DEPs.</span></span> <span data-ttu-id="e73c5-350">有关说明，请参阅 [管理客户密钥](customer-key-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="e73c5-350">For instructions, see [Manage Customer Key](customer-key-manage.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="e73c5-351">相关文章</span><span class="sxs-lookup"><span data-stu-id="e73c5-351">Related articles</span></span>

- [<span data-ttu-id="e73c5-352">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="e73c5-352">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="e73c5-353">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="e73c5-353">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="e73c5-354">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="e73c5-354">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="e73c5-355">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="e73c5-355">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="e73c5-356">服务加密</span><span class="sxs-lookup"><span data-stu-id="e73c5-356">Service Encryption</span></span>](office-365-service-encryption.md)