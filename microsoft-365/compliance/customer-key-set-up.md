---
title: 在应用程序级别设置客户密钥
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何为 Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥。
ms.openlocfilehash: a7a0c807b8778960d423d6b7d8afc20430ba89ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922716"
---
# <a name="set-up-customer-key-at-the-application-level"></a><span data-ttu-id="ea2a6-103">在应用程序级别设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="ea2a6-103">Set up Customer Key at the application level</span></span>

<span data-ttu-id="ea2a6-104">使用客户密钥，可以控制组织的加密密钥，然后配置 Microsoft 365 以使用它们加密 Microsoft 数据中心中的静态数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="ea2a6-105">换句话说，客户密钥允许客户使用其密钥添加属于他们的加密层。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="ea2a6-106">其余数据包括存储在邮箱中的 Exchange Online 和 Skype for Business 数据以及存储在 SharePoint Online 和 OneDrive for Business 中的文件。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="ea2a6-107">必须先设置 Azure，然后才能使用 Office 365 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="ea2a6-108">本文介绍了创建和配置所需 Azure 资源所需的步骤，然后提供了在 Office 365 中设置客户密钥的步骤。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-108">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="ea2a6-109">完成 Azure 设置后，可确定要分配给组织中邮箱和文件的策略，以及要分配的密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="ea2a6-110">未为其分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="ea2a6-111">有关客户密钥或一般概述的信息，请参阅使用 Office [365 中的客户密钥进行服务加密](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ea2a6-112">我们强烈建议您遵循本文中的最佳方案。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-112">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="ea2a6-113">这些称为"提示 **"和"\*\*\*\*重要"。**</span><span class="sxs-lookup"><span data-stu-id="ea2a6-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="ea2a6-114">客户密钥可让你控制其作用域可以与整个组织一样大的根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="ea2a6-115">这意味着，使用这些密钥所导致错误可能会产生广泛影响，并可能导致服务中断或数据的不可撤消丢失。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="ea2a6-116">设置客户密钥之前</span><span class="sxs-lookup"><span data-stu-id="ea2a6-116">Before you set up Customer Key</span></span>

<span data-ttu-id="ea2a6-117">在开始使用之前，请确保你拥有适合你的组织的许可。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="ea2a6-118">使用付费的、已开票的 Azure 订阅，企业协议云服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-118">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="ea2a6-119">客户密钥不支持使用即付即用计划或信用卡购买的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-119">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="ea2a6-120">从 2020 年 4 月 1 日起，Office 365 中的客户密钥在 Office 365 E5、M365 E5、M365 E5 合规性和 M365 E5 信息保护 & SK 中提供。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-120">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="ea2a6-121">Office 365 高级合规性 SKU 不再可用于购买新许可证。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="ea2a6-122">现有 Office 365 高级合规性许可证将继续受支持。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="ea2a6-123">若要了解本文中的概念和过程，请查看 [Azure Key Vault](/azure/key-vault/) 文档。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="ea2a6-124">此外，请熟悉 Azure 中使用的术语，例如 Azure [AD 租户](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>

<span data-ttu-id="ea2a6-125">FastTrack 仅用于收集注册客户密钥所需的租户和服务配置信息。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-125">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="ea2a6-126">客户密钥产品/服务通过 FastTrack 发布，以便你和我们的合作伙伴可以使用同一方法提交所需信息。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-126">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="ea2a6-127">FastTrack 还便于存档你在产品/服务中提供的数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-127">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="ea2a6-128">如果您需要文档之外更多的支持，请联系 Microsoft 咨询服务 (MCS) 、顶级现场工程 (PFE) 或 Microsoft 合作伙伴寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-128">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="ea2a6-129">若要提供有关客户密钥（包括文档）的反馈，请将你的想法、建议和观点发送给客户 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-129">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="ea2a6-130">设置客户密钥的步骤概述</span><span class="sxs-lookup"><span data-stu-id="ea2a6-130">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="ea2a6-131">若要设置客户密钥，请按列出的顺序完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-131">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="ea2a6-132">本文的其余部分提供了每个任务的详细说明，或链接到过程中每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-132">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="ea2a6-133">**在 Azure 和 Microsoft FastTrack 中：**</span><span class="sxs-lookup"><span data-stu-id="ea2a6-133">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="ea2a6-134">大部分任务都将通过远程连接到 Azure PowerShell 来完成。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-134">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="ea2a6-135">为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="ea2a6-136">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="ea2a6-136">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="ea2a6-137">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="ea2a6-137">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="ea2a6-138">注册可能需要一到五个工作日。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-138">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="ea2a6-139">提交激活 Office 365 客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="ea2a6-139">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="ea2a6-140">创建两个新的 Azure 订阅后，你将需要通过完成 Microsoft FastTrack 门户中托管的 Web 表单来提交相应的客户密钥优惠请求。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-140">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="ea2a6-141">**FastTrack 团队不提供有关客户密钥的帮助。Office 仅使用 FastTrack 门户，以允许你** 提交表单，并帮助我们跟踪客户密钥的相关产品/服务。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-141">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="ea2a6-142">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="ea2a6-142">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="ea2a6-143">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="ea2a6-143">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="ea2a6-144">启用密钥保管库，然后确认软删除</span><span class="sxs-lookup"><span data-stu-id="ea2a6-144">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="ea2a6-145">通过创建或导入密钥将密钥添加到每个密钥保管库</span><span class="sxs-lookup"><span data-stu-id="ea2a6-145">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="ea2a6-146">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="ea2a6-146">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="ea2a6-147">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="ea2a6-147">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="ea2a6-148">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="ea2a6-148">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="ea2a6-149">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="ea2a6-149">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="ea2a6-150">**在 Office 365 中：**</span><span class="sxs-lookup"><span data-stu-id="ea2a6-150">**In Office 365:**</span></span>
  
<span data-ttu-id="ea2a6-151">Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-151">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="ea2a6-152">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea2a6-152">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="ea2a6-153">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="ea2a6-153">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="ea2a6-154">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="ea2a6-154">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="ea2a6-155">SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-155">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="ea2a6-156">为每个 SharePoint Online 和 OneDrive for Business 地理位置 (DEP) 数据加密策略</span><span class="sxs-lookup"><span data-stu-id="ea2a6-156">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="ea2a6-157">验证 SharePoint Online、OneDrive for Business 和 Teams 文件的文件加密</span><span class="sxs-lookup"><span data-stu-id="ea2a6-157">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="ea2a6-158">完成 Azure Key Vault 和 Microsoft FastTrack for Customer Key 中的任务</span><span class="sxs-lookup"><span data-stu-id="ea2a6-158">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="ea2a6-159">在 Azure 密钥保管库中完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-159">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="ea2a6-160">无论是打算为 Exchange Online 和 Skype for Business 设置客户密钥，还是为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥，或者为 Office 365 中所有受支持的服务设置客户密钥，都需要完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-160">You'll need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="ea2a6-161">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="ea2a6-161">Create two new Azure subscriptions</span></span>

<span data-ttu-id="ea2a6-162">客户密钥需要两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-162">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="ea2a6-163">作为最佳做法，Microsoft 建议创建用于客户密钥的新 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-163">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="ea2a6-164">对于同一 Azure Active Directory (Microsoft Azure Active Directory) 租户中的应用程序，只能授权 Azure 密钥保管库密钥，你必须使用与将分配 DEP 的组织一同使用的同一 Azure AD 租户创建新订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-164">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="ea2a6-165">例如，使用在组织中具有全局管理员权限的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-165">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="ea2a6-166">有关详细步骤，请参阅 [注册 Azure 作为组织](/azure/active-directory/fundamentals/sign-up-organization)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-166">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ea2a6-167">客户密钥要求 DEP 策略中每个数据加密策略 (两) 。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-167">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="ea2a6-168">为此，必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-168">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="ea2a6-169">最佳做法是，Microsoft 建议你组织单独的成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-169">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="ea2a6-170">你应仅使用这些 Azure 订阅来管理 Office 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-170">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="ea2a6-171">这可保护你的组织，以防你的其中一个运营者意外、有意或恶意删除或以其他方式管理他们负责的密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-171">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>
>

<span data-ttu-id="ea2a6-172">对于你可以为组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="ea2a6-173">遵循这些最佳做法将最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="ea2a6-174">提交激活 Office 365 客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="ea2a6-174">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="ea2a6-175">完成 Azure 步骤后，你需要在 [Microsoft FastTrack](https://fasttrack.microsoft.com/)门户中提交产品/服务请求。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-175">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="ea2a6-176">通过 FastTrack Web 门户提交请求后，Microsoft 会验证所提供的 Azure Key Vault 配置数据和联系信息。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-176">Once you've submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="ea2a6-177">在产品/服务表单中有关组织授权官员的选择对于完成客户密钥注册至关重要且必要。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-177">The selections that you make in the offer form about the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="ea2a6-178">贵组织的官员确保撤消和销毁用于客户密钥数据加密策略的所有密钥的请求的真实性。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-178">The officers of your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="ea2a6-179">你需要执行此步骤一次以激活 Exchange Online 和 Skype for Business 范围的客户密钥，第二次激活 SharePoint Online 和 OneDrive for Business 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-179">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="ea2a6-180">若要提交产品/服务以激活客户密钥，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="ea2a6-181">使用在组织中具有全局管理员权限的工作或学校帐户，登录到 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-181">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="ea2a6-182">登录后，浏览 **到仪表板**。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-182">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="ea2a6-183">从 **导航** 栏中选择"部署 **"，或** 选择"部署信息卡"上的"查看所有部署资源"，然后查看当前产品/服务的列表。 </span><span class="sxs-lookup"><span data-stu-id="ea2a6-183">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="ea2a6-184">选择适用于你的产品/服务的信息卡：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-184">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="ea2a6-185">**Exchange Online 和 Skype for Business：** 选择" **请求 Exchange Online 服务加密密钥帮助** "。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-185">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="ea2a6-186">**SharePoint Online、OneDrive 和 Teams 文件：** 选择" **请求 Sharepoint 和 OneDrive 的** 加密密钥帮助"优惠。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-186">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="ea2a6-187">查看产品/服务详细信息后，选择"**继续"以执行步骤 2。**</span><span class="sxs-lookup"><span data-stu-id="ea2a6-187">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="ea2a6-188">在产品/服务表单上填写所有适用的详细信息和请求的信息。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-188">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="ea2a6-189">请特别注意要授权贵组织的哪个官员批准对加密密钥和数据进行永久且不可恢复的销毁的选择。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-189">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="ea2a6-190">完成表单后，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="ea2a6-190">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="ea2a6-191">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="ea2a6-191">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="ea2a6-192">根加密密钥的临时或永久丢失可能会导致服务操作中断甚至出现灾难性问题，并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-192">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="ea2a6-193">因此，用于客户密钥的资源需要强大的保护。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-193">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="ea2a6-194">与客户密钥一起使用的所有 Azure 资源都提供除默认配置以外的保护机制。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-194">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="ea2a6-195">你可以标记或注册 Azure 订阅，以保留 *强制保留期*。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-195">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="ea2a6-196">强制保留期可阻止立即和不可撤销地取消 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-196">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="ea2a6-197">若要将 Azure 订阅注册为强制保留期，需要与 Microsoft 365 团队协作。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-197">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="ea2a6-198">此过程可能需要 1 到 5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-198">This process can take from one to five business days.</span></span> <span data-ttu-id="ea2a6-199">以前，强制保留期有时称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-199">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="ea2a6-200">在联系 Microsoft 365 团队之前，你必须对使用客户密钥的每个 Azure 订阅执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-200">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="ea2a6-201">在启动之前，请确保已安装 [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) 模块。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-201">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="ea2a6-202">使用 Azure PowerShell 登录。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-202">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="ea2a6-203">有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-203">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ea2a6-204">运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-204">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="ea2a6-205">针对每个订阅完成此操作。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-205">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="ea2a6-206">请与 Microsoft 联系以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-206">Contact Microsoft to complete the process.</span></span> <span data-ttu-id="ea2a6-207">对于 SharePoint 和 OneDrive for Business 团队 [，请与](mailto:spock@microsoft.com)spock@microsoft.com 联系。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-207">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="ea2a6-208">对于 Exchange Online 和 Skype for Business，请联系 [exock@microsoft.com](mailto:exock@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-208">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="ea2a6-209">在电子邮件中包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-209">Include the following information in your email:</span></span>

   <span data-ttu-id="ea2a6-210">**主题**：客户密钥 \<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="ea2a6-210">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="ea2a6-211">**正文**：包括要完成其强制保留期的订阅 ID 和每个订阅Get-AzProviderFeature输出。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-211">**Body**: Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="ea2a6-212">完成此过程的服务级别协议 (SLA) 在向 Microsoft 通知 (并验证) 你已注册订阅以使用强制保留期后，5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-212">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="ea2a6-213">从 Microsoft 收到注册完成通知后，通过运行 Get-AzProviderFeature 命令验证注册状态。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-213">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="ea2a6-214">如果已验证，Get-AzProviderFeature返回 Registration **State** 属性的值 **Registered。**</span><span class="sxs-lookup"><span data-stu-id="ea2a6-214">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="ea2a6-215">针对每个订阅完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-215">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="ea2a6-216">若要完成此过程，请运行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-216">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="ea2a6-217">针对每个订阅完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-217">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="ea2a6-218">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="ea2a6-218">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="ea2a6-219">[Azure](/azure/key-vault/general/overview)密钥保管库入门中记录了创建密钥保管库的步骤，可指导你完成安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建该资源组中密钥保管库的步骤。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="ea2a6-220">创建密钥保管库时，必须选择 SKU：Standard 或 Premium。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="ea2a6-221">标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护）并且高级 SKU 允许使用 HSM 来保护密钥保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="ea2a6-222">客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="ea2a6-223">使用任一类型的密钥的操作成本相同，因此成本的唯一差别是每个受 HSM 保护的密钥的每月成本。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="ea2a6-224">有关详细信息 [，请参阅密钥保管](https://azure.microsoft.com/pricing/details/key-vault/) 库定价。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ea2a6-225">将高级 SKU 密钥保管库和 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="ea2a6-226">对于要使用客户密钥的每个 Microsoft 365 服务，在创建的两个 Azure 订阅中分别创建一个密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-226">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="ea2a6-227">例如，仅对于 Exchange Online 和 Skype for Business 或仅 SharePoint Online 和 OneDrive for Business，你将仅创建一对保管库。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you'll create only one pair of vaults.</span></span> <span data-ttu-id="ea2a6-228">若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥，需要创建两对密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="ea2a6-229">对密钥保管库使用命名约定，该约定反映了您将与保管库关联的 DEP 的预定用途。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="ea2a6-230">有关命名约定建议，请参阅下面的最佳做法部分。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="ea2a6-231">为每个数据加密策略创建一组单独的配对保管库。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="ea2a6-232">对于 Exchange Online，当您将策略分配给邮箱时，将选择数据加密策略的范围。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="ea2a6-233">邮箱只能分配一个策略，并且可以创建最多 50 个策略。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-233">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="ea2a6-234">SharePoint Online 策略的范围包括位于地理位置或地理位置的组织内 _的所有数据_。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-234">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="ea2a6-235">创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量 (但小型) 和密钥保管库日志记录（如果启用）也会生成存储的数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="ea2a6-236">作为最佳实践，Microsoft 建议使用单独的管理员来管理每个资源组，其管理与将管理所有相关客户密钥资源的一组管理员保持一致。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ea2a6-237">为了最大限度地提高可用性，密钥保管库应靠近 Microsoft 365 服务的区域。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-237">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="ea2a6-238">例如，如果您的 Exchange Online 组织位于北美，则将密钥保管库放在北美。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="ea2a6-239">如果您的 Exchange Online 组织在欧洲，将密钥保管库放在欧洲。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
> 
> <span data-ttu-id="ea2a6-240">对密钥保管库使用通用前缀，并包括密钥保管库和密钥 (的使用和范围的缩写，例如，对于保管库将位于北美洲的 Contoso SharePoint 服务，可能的名称对是 Contoso-O365SP-NA-VaultA1 和 Contoso-O365SP-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="ea2a6-241">保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="ea2a6-242">自 2017 年 7 日起，无法更改保管库名称，因此最佳做法是制定一份书面设置计划，并使用第二个人验证计划是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
> 
> <span data-ttu-id="ea2a6-243">如果可能，在非配对区域创建保管库。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="ea2a6-244">成对的 Azure 区域跨服务失败域提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="ea2a6-245">因此，可以将区域对视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="ea2a6-246">这意味着，放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="ea2a6-247">因此，为数据加密策略中使用的两个保管库选择区域（这些区域已配对）意味着总共只有两个可用性区域在使用。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-247">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="ea2a6-248">大多数地理位置只有两个区域，因此尚无法选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="ea2a6-249">如果可能，请为与数据加密策略一同使用的两个保管库选择两个非配对区域。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-249">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="ea2a6-250">这从共四个可用性区域中获益。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="ea2a6-251">有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：当前](/azure/best-practices-availability-paired-regions) 区域对列表的 Azure 配对区域。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="ea2a6-252">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="ea2a6-252">Assign permissions to each key vault</span></span>

<span data-ttu-id="ea2a6-253">你将需要为每个密钥保管库定义三组单独的权限，具体取决于你的实现。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-253">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="ea2a6-254">例如，您需要为以下各项定义一组权限：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-254">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="ea2a6-255">**对组织执行** 密钥保管库日常管理的关键保管库管理员。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-255">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="ea2a6-256">这些任务包括备份、创建、获取、导入、列表和还原。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-256">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ea2a6-257">分配给密钥保管库管理员的权限集不包括删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-257">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="ea2a6-258">这是有意为之，也是一项重要的做法。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-258">This is intentional and an important practice.</span></span> <span data-ttu-id="ea2a6-259">通常不删除加密密钥，因为这样做会永久破坏数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-259">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="ea2a6-260">作为最佳实践，默认情况下不要向密钥保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-260">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="ea2a6-261">相反，请为密钥保管库参与者保留此策略，并且仅在明确了解后果后将其短期分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-261">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="ea2a6-262">若要向贵组织的用户分配这些权限，请通过 Azure PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-262">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="ea2a6-263">有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-263">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="ea2a6-264">运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-264">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="ea2a6-265">例如：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-265">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="ea2a6-266">**可以更改 Azure** 密钥保管库本身权限的密钥保管库参与者。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-266">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="ea2a6-267">当员工离开或加入团队时，你需要更改这些权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-267">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="ea2a6-268">在密钥保管库管理员合法需要删除或还原密钥的极少数情况下，您还需要更改权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-268">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="ea2a6-269">需要向这组密钥保管库参与者授予密钥保管 **库** 上的参与者角色。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="ea2a6-270">可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="ea2a6-271">有关详细步骤，请参阅使用 [Role-Based访问控制管理对 Azure 订阅资源的访问权限](/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="ea2a6-272">创建订阅的管理员具有隐式访问权限，并且能够将其他管理员分配到参与者角色。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-272">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="ea2a6-273">如果你打算将客户密钥与 Exchange Online 和 Skype for Business 一同使用，则需要授予 Microsoft 365 代表 Exchange Online 和 Skype for Business 使用密钥保管库的权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="ea2a6-274">同样，如果你打算将客户密钥用于 SharePoint Online 和 OneDrive for Business，则需要添加 Microsoft 365 代表 SharePoint Online 和 OneDrive for Business 使用密钥保管库的权限。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="ea2a6-275">若要向 Microsoft 365 授予权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用下列语法：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-275">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="ea2a6-276">其中：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-276">Where:</span></span>

    - <span data-ttu-id="ea2a6-277">*保管库* 名称是创建的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-277">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="ea2a6-278">对于 Exchange Online 和 Skype for Business，将 *Office 365 appID 替换为*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="ea2a6-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="ea2a6-279">对于 SharePoint Online、OneDrive for Business 和 Teams 文件，将  *Office 365 appID* 替换为 `00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="ea2a6-279">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="ea2a6-280">示例：为 Exchange Online 和 Skype for Business 设置权限：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="ea2a6-281">示例：设置 SharePoint Online、OneDrive for Business 和 Teams 文件的权限：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-281">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="ea2a6-282">启用密钥保管库，然后确认软删除</span><span class="sxs-lookup"><span data-stu-id="ea2a6-282">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="ea2a6-283">如果可以快速恢复密钥，不太可能因意外或恶意删除密钥而遇到服务中断。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-283">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="ea2a6-284">你需要启用此配置（称为软删除）才能将密钥与客户密钥一同使用。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-284">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="ea2a6-285">启用软删除后，您可以在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-285">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="ea2a6-286">若要在密钥保管库上启用软删除，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="ea2a6-287">使用 Windows PowerShell 登录 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-287">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="ea2a6-288">有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-288">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ea2a6-289">运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-289">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="ea2a6-290">本示例中， *保管库* 名称是要启用软删除的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-290">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="ea2a6-291">通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置了软删除。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-291">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="ea2a6-292">如果为密钥保管库正确配置了软删除，则"启用 _软_ 删除"属性将返回值 **True**：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-292">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="ea2a6-293">通过创建或导入密钥将密钥添加到每个密钥保管库</span><span class="sxs-lookup"><span data-stu-id="ea2a6-293">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="ea2a6-294">有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在密钥保管库中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-294">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="ea2a6-295">直接在密钥保管库中创建密钥是不太复杂的方法，而导入密钥可提供对密钥生成方式的总控制。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-295">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="ea2a6-296">使用 RSA 密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-296">Use the RSA keys.</span></span> <span data-ttu-id="ea2a6-297">Azure Key Vault 不支持使用椭圆曲线键换行和取消环绕。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-297">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="ea2a6-298">若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-298">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="ea2a6-299">其中：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-299">Where:</span></span>

- <span data-ttu-id="ea2a6-300">*保管* 库名称是你想要创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-300">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="ea2a6-301">*key name* 是你想要提供新密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-301">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="ea2a6-302">使用与上述密钥保管库类似的命名约定命名密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="ea2a6-303">这样，在只显示键名称的工具中，字符串是自描述的。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-303">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="ea2a6-304">如果要使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则请指定 **Software**。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="ea2a6-305">例如，</span><span class="sxs-lookup"><span data-stu-id="ea2a6-305">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="ea2a6-306">若要将密钥直接导入密钥保管库，您需要具有 nCipher nShield 硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-306">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="ea2a6-307">一些组织倾向于使用此方法来建立其密钥的验证，然后此方法还提供以下证明：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-307">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="ea2a6-308">用于导入的工具集包括来自 nCipher 的证明，证明用于加密您生成的密钥的密钥 Exchange 密钥 (KEK) 不可导出，并且是在 nCipher 制造的真正 HSM 内生成的。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-308">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="ea2a6-309">工具集包括 nCipher 的证明，表明 Azure 密钥保管库安全世界也在 nCipher 制造的真正 HSM 上生成。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-309">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="ea2a6-310">此证明向你证明 Microsoft 也使用正版 nCipher 硬件。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-310">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="ea2a6-311">请与安全组核实，确定是否需要上述证明。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="ea2a6-312">有关在本地创建密钥并导入密钥保管库的详细步骤，请参阅如何为 Azure 密钥保管库生成和传输 [受 HSM 保护的密钥](/azure/key-vault/keys/hsm-protected-keys)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="ea2a6-313">使用 Azure 说明在每个密钥保管库中创建密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="ea2a6-314">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="ea2a6-314">Check the recovery level of your keys</span></span>

<span data-ttu-id="ea2a6-315">Microsoft 365 要求 Azure 密钥保管库订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-315">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="ea2a6-316">可以通过查看密钥上的恢复级别来确认订阅设置。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-316">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="ea2a6-317">若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="ea2a6-318">如果"恢复级别"属性返回除 **"Recoverable+ProtectedSubscription"** 值外的其他值，请确保将订阅置于"不取消"列表中，并且已在每个密钥保管库上启用软删除。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-318">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="ea2a6-319">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="ea2a6-319">Back up Azure Key Vault</span></span>

<span data-ttu-id="ea2a6-320">创建或更改密钥后，立即执行备份并存储备份副本（联机和脱机）。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-320">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="ea2a6-321">脱机副本不应连接到任何网络，例如物理安全或商业存储设备中。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-321">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="ea2a6-322">应至少将备份的一个副本存储在发生灾难时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-322">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="ea2a6-323">如果密钥保管库密钥被永久销毁或呈现为不可操作，备份 blob 是还原密钥材料的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-323">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="ea2a6-324">Azure 密钥保管库外部且已导入 Azure 密钥保管库的密钥不符合备份条件，因为外部密钥中不存在客户密钥使用该密钥所需的元数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-324">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="ea2a6-325">只有从 Azure 密钥保管库获取的备份可用于使用客户密钥执行还原操作。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-325">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="ea2a6-326">因此，您必须在上载或创建密钥后创建 Azure Key Vault 备份。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-326">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="ea2a6-327">若要创建 Azure 密钥保管库密钥的备份，请运行 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-327">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="ea2a6-328">确保输出文件使用后缀 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-328">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="ea2a6-329">此 cmdlet 生成的输出文件已加密，不能在 Azure Key Vault 外部使用。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-329">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="ea2a6-330">备份只能还原到进行备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-330">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="ea2a6-331">对于输出文件，选择保管库名称和密钥名称的组合。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-331">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="ea2a6-332">这将使文件名自描述。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-332">This will make the file name self-describing.</span></span> <span data-ttu-id="ea2a6-333">它还将确保备份文件名不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-333">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="ea2a6-334">例如：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-334">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="ea2a6-335">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="ea2a6-335">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="ea2a6-336">在 DEP 中使用密钥之前验证是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-336">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="ea2a6-337">如果使用本文中所述的步骤来设置密钥和保管库，请验证 Azure Key Vault 资源的运行状况，然后再配置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-337">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="ea2a6-338">若要验证密钥是否已启用 `get` 、 `wrapKey` 和 `unwrapKey` 操作：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-338">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="ea2a6-339">运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-339">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="ea2a6-340">在输出中，查找访问策略和 Exchange Online 标识 (GUID) 或 SharePoint Online 标识 (GUID) 查找。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-340">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="ea2a6-341">以上所有三种权限都必须显示在"密钥权限"下。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-341">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="ea2a6-342">如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-342">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="ea2a6-343">例如，对于 Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-343">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="ea2a6-344">例如，对于 SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-344">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="ea2a6-345">若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-345">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="ea2a6-346">客户密钥不能使用过期密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-346">Customer Key can't use an expired key.</span></span> <span data-ttu-id="ea2a6-347">尝试使用过期密钥的操作将失败，并可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-347">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="ea2a6-348">我们强烈建议用于客户密钥的密钥没有过期日期。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-348">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="ea2a6-349">一旦设置过期日期，就无法删除，但可以更改为其他日期。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-349">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="ea2a6-350">如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-350">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="ea2a6-351">到期日期设置为 12/31/9999 外日期的密钥无法通过 Microsoft 365 验证。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-351">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="ea2a6-352">若要更改已设置为 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-352">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="ea2a6-353">不要设置与客户密钥一同使用的加密密钥的到期日期。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-353">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="ea2a6-354">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="ea2a6-354">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="ea2a6-355">设置密钥保管库并添加密钥后，运行以下命令，获取每个密钥保管库中密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-355">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="ea2a6-356">稍后创建和分配每个 DEP 时，将需要使用这些 URI，因此将此信息保存在一个安全的位置。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-356">You'll need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="ea2a6-357">针对每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-357">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="ea2a6-358">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-358">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="ea2a6-359">Office 365：为 Exchange Online 和 Skype for Business 设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="ea2a6-359">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="ea2a6-360">开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-360">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="ea2a6-361">有关 [信息，请参阅完成 Azure Key Vault](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 和 Microsoft FastTrack 中的任务获取客户密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-361">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="ea2a6-362">若要为 Exchange Online 和 Skype for Business 设置客户密钥，你需要通过远程连接到 Exchange Online，使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-362">To set up Customer Key for Exchange Online and Skype for Business, you'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="ea2a6-363">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea2a6-363">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="ea2a6-364">DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-364">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="ea2a6-365">将 DEP 分配给 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-365">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="ea2a6-366">然后，Microsoft 365 将使用策略中标识的密钥来加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-366">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="ea2a6-367">若要创建 DEP，您需要之前获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-367">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="ea2a6-368">有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="ea2a6-368">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="ea2a6-369">请记住！</span><span class="sxs-lookup"><span data-stu-id="ea2a6-369">Remember!</span></span> <span data-ttu-id="ea2a6-370">创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-370">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="ea2a6-371">在两个独立的 Azure 区域创建这些密钥以确保地理位置冗余。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-371">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="ea2a6-372">若要创建 DEP，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-372">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="ea2a6-373">在本地计算机上，使用在组织中具有全局管理员权限的工作或学校帐户，在远程窗口中Windows PowerShell Exchange [Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ea2a6-373">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="ea2a6-374">若要创建 DEP，请通过New-DataEncryptionPolicy命令使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-374">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="ea2a6-375">其中：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-375">Where:</span></span>

   - <span data-ttu-id="ea2a6-376">*PolicyName* 是你想要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-376">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="ea2a6-377">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-377">Names can't contain spaces.</span></span> <span data-ttu-id="ea2a6-378">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-378">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="ea2a6-379">*策略* 说明是策略的用户友好说明，有助于你记住策略用于什么。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-379">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="ea2a6-380">可以在说明中包括空格。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-380">You can include spaces in the description.</span></span> <span data-ttu-id="ea2a6-381">例如，"美国及其区域邮箱的根密钥"。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-381">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="ea2a6-382">*KeyVaultURI1* 是策略中第一个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-382">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="ea2a6-383">例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-383">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="ea2a6-384">*KeyVaultURI2* 是策略中第二个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-384">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="ea2a6-385">例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-385">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="ea2a6-386">用逗号和空格分隔这两个 URI。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-386">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="ea2a6-387">示例：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-387">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="ea2a6-388">有关语法和参数的详细信息，请参阅 [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-388">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="ea2a6-389">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="ea2a6-389">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="ea2a6-390">使用 cmdlet 将 DEP Set-Mailbox邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-390">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="ea2a6-391">分配策略后，Microsoft 365 可以使用 DEP 中标识的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-391">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="ea2a6-392">其中 *MailboxIdParameter* 指定用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-392">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="ea2a6-393">有关此 cmdlet Set-Mailbox，请参阅 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-393">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="ea2a6-394">在混合环境中，您可以将 DEP 分配给同步到 Exchange Online 租户中的内部部署邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-394">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="ea2a6-395">若要为此同步的邮箱数据分配 DEP，请使用 Set-MailUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-395">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="ea2a6-396">有关混合环境中邮箱数据的信息，请参阅使用 Outlook [for iOS](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)和 Outlook for Android 和混合新式验证本地邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-396">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="ea2a6-397">其中 *MailUserIdParameter* 指定邮件 (也称为启用邮件的用户) 。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-397">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="ea2a6-398">有关此 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-398">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="ea2a6-399">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="ea2a6-399">Validate mailbox encryption</span></span>

<span data-ttu-id="ea2a6-400">加密邮箱可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-400">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="ea2a6-401">对于首次策略分配，邮箱还必须从一个数据库完全移动到另一个数据库，服务才能加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-401">For first-time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="ea2a6-402">建议在更改 DEP 或首次向邮箱分配 DEP 后等待 72 小时，然后再尝试验证加密。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-402">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="ea2a6-403">使用 Get-MailboxStatistics cmdlet 确定邮箱是否加密。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-403">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="ea2a6-404">如果邮箱已加密，IsEncrypted 属性将返回 **true** 值;如果邮箱未加密，则返回 **false** 值。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-404">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="ea2a6-405">完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-405">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="ea2a6-406">如果邮箱自分配 DEP 起一周后未加密，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-406">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="ea2a6-407">Office 365：为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="ea2a6-407">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="ea2a6-408">开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-408">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="ea2a6-409">有关 [信息，请参阅完成 Azure Key Vault](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 和 Microsoft FastTrack 中的任务获取客户密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-409">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="ea2a6-410">若要设置 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥，请通过远程连接到 SharePoint Online 和 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-410">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="ea2a6-411">为每个 SharePoint Online 和 OneDrive for Business 地理位置 (DEP) 数据加密策略</span><span class="sxs-lookup"><span data-stu-id="ea2a6-411">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="ea2a6-412">将 DEP 与 Azure Key Vault 中存储的一组密钥关联。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-412">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="ea2a6-413">将 DEP 应用于一个地理位置（也称为地理位置）的所有数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-413">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="ea2a6-414">如果使用 Office 365 的多地理位置功能，可以为每个地理位置创建一个 DEP，并能够为每个地理位置使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-414">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="ea2a6-415">如果不使用多地理位置，可以在组织中创建一个 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-415">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="ea2a6-416">Microsoft 365 使用 DEP 中标识的密钥来加密该地理位置的数据。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-416">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="ea2a6-417">若要创建 DEP，您需要之前获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-417">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="ea2a6-418">有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="ea2a6-418">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="ea2a6-419">请记住！</span><span class="sxs-lookup"><span data-stu-id="ea2a6-419">Remember!</span></span> <span data-ttu-id="ea2a6-420">创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-420">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="ea2a6-421">在两个独立的 Azure 区域创建这些密钥以确保地理位置冗余。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-421">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="ea2a6-422">若要创建 DEP，您需要使用 Windows PowerShell 远程连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-422">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="ea2a6-423">在本地计算机上，使用在组织中具有全局管理员权限的工作或学校帐户[连接到 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="ea2a6-423">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="ea2a6-424">在 Microsoft SharePoint Online 命令行管理程序 中，Register-SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-424">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="ea2a6-425">示例：</span><span class="sxs-lookup"><span data-stu-id="ea2a6-425">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="ea2a6-426">注册 DEP 时，加密从地理位置数据开始。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-426">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="ea2a6-427">加密可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-427">Encryption can take some time.</span></span> <span data-ttu-id="ea2a6-428">有关使用此参数的信息，请参阅 [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-428">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="ea2a6-429">验证文件加密</span><span class="sxs-lookup"><span data-stu-id="ea2a6-429">Validate file encryption</span></span>

 <span data-ttu-id="ea2a6-430">若要验证 SharePoint Online、OneDrive for Business 和 Teams 文件的加密，请连接到 [SharePoint Online PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell)然后使用 Get-SPODataEncryptionPolicy cmdlet 检查租户的状态。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-430">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="ea2a6-431">如果 _启用_ 客户 **密钥加密，** 并且所有站点中所有文件已加密，则 State 属性返回已注册的值。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-431">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="ea2a6-432">如果加密仍在进行中，此 cmdlet 将返回注册 **的值**。</span><span class="sxs-lookup"><span data-stu-id="ea2a6-432">If encryption is still in progress, this cmdlet returns a value of **registering**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ea2a6-433">相关文章</span><span class="sxs-lookup"><span data-stu-id="ea2a6-433">Related articles</span></span>

- [<span data-ttu-id="ea2a6-434">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="ea2a6-434">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="ea2a6-435">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="ea2a6-435">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="ea2a6-436">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="ea2a6-436">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="ea2a6-437">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="ea2a6-437">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="ea2a6-438">服务加密</span><span class="sxs-lookup"><span data-stu-id="ea2a6-438">Service Encryption</span></span>](office-365-service-encryption.md)