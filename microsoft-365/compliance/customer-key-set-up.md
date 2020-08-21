---
title: 设置客户密钥
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
ms.openlocfilehash: 87c18c1695d2963fc8a0c064d34d2b6cdc14199c
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845830"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="368b2-103">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-103">Set up Customer Key</span></span>

<span data-ttu-id="368b2-104">使用客户密钥，你可以控制组织的加密密钥，然后配置 Microsoft 365 以使用它们加密 Microsoft 的数据中心内的静态数据。</span><span class="sxs-lookup"><span data-stu-id="368b2-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="368b2-105">换句话说，客户密钥允许客户将属于他们的加密层与密钥一起添加。</span><span class="sxs-lookup"><span data-stu-id="368b2-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="368b2-106">具有处于唯一状态的 Exchange Online 和 Skype for Business 中的数据，这些数据存储在 SharePoint Online 和 OneDrive for Business 中的邮箱和文件中。</span><span class="sxs-lookup"><span data-stu-id="368b2-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="368b2-107">必须先设置 Azure，然后才能将客户密钥用于 Office 365。</span><span class="sxs-lookup"><span data-stu-id="368b2-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="368b2-108">本主题介绍创建和配置所需 Azure 资源需遵循的步骤，然后提供在 Office 365 中设置客户密钥的步骤。</span><span class="sxs-lookup"><span data-stu-id="368b2-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="368b2-109">完成 Azure 设置后，你将确定要分配给组织中邮箱和文件的策略以及哪些密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="368b2-110">未为其分配策略的邮箱和文件将使用由 Microsoft 进行控制和管理的加密策略。</span><span class="sxs-lookup"><span data-stu-id="368b2-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="368b2-111">有关客户密钥或常规概述的详细信息，请参阅 [Office 365 中使用客户密钥进行服务加密](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="368b2-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="368b2-112">强烈建议您遵循本主题中的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="368b2-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="368b2-113">这些被称为**TIP 和** **IMPORTANT。**</span><span class="sxs-lookup"><span data-stu-id="368b2-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="368b2-114">客户密钥使你可以控制其作用域可能在整个组织范围内的根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="368b2-115">这意味着，使用这些关键所做的错误可能会对你造成广泛影响，并且可能会导致数据服务中断或无法撤消丢失数据。</span><span class="sxs-lookup"><span data-stu-id="368b2-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="368b2-116">设置客户密钥之前</span><span class="sxs-lookup"><span data-stu-id="368b2-116">Before you set up Customer Key</span></span>

<span data-ttu-id="368b2-117">在开始之前，请确保您具有适合你的组织的相应许可。</span><span class="sxs-lookup"><span data-stu-id="368b2-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="368b2-118">Office 365 E5 或高级合规 SKU 中提供 Microsoft 365 中的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-118">Customer Key in Microsoft 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span> <span data-ttu-id="368b2-119">若要了解本主题中的概念和过程，请查看 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 文档。</span><span class="sxs-lookup"><span data-stu-id="368b2-119">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="368b2-120">同时，您也熟悉 Azure 中使用的条款，例如 [租户](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="368b2-120">Also, become familiar with the terms used in Azure, for example, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).</span></span>

<span data-ttu-id="368b2-121">FastTrack 仅用于收集用于注册客户密钥的必需租户和服务配置信息。</span><span class="sxs-lookup"><span data-stu-id="368b2-121">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="368b2-122">客户密钥优惠通过 FastTrack 发布，便于你和我们的合作伙伴使用相同方法提交所需信息。</span><span class="sxs-lookup"><span data-stu-id="368b2-122">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="368b2-123">FastTrack 还便于存档在产品/服务中提供的数据。</span><span class="sxs-lookup"><span data-stu-id="368b2-123">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="368b2-124">如果还需要文档以外的其他支持，请与 Microsoft 咨询服务 (MCS) Premier Field Engineering (PFE) 或 Microsoft 合作伙伴获取帮助。</span><span class="sxs-lookup"><span data-stu-id="368b2-124">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="368b2-125">要提供有关客户密钥的反馈，包括文档、向你的想点、建议和customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="368b2-125">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="368b2-126">设置客户密钥的步骤概述</span><span class="sxs-lookup"><span data-stu-id="368b2-126">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="368b2-127">若要设置客户密钥，请按列出的顺序完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-127">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="368b2-128">本文的其余部分提供了每个任务的详细说明，或链接指向该过程中每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="368b2-128">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="368b2-129">**在 Azure 和 Microsoft FastTrack 中：**</span><span class="sxs-lookup"><span data-stu-id="368b2-129">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="368b2-130">您将通过远程连接到 Azure PowerShell 来完成大部分这些任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-130">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="368b2-131">为了获得最佳结果，请使用 Azure PowerShell 的 4.4.0 版本或更高版本。</span><span class="sxs-lookup"><span data-stu-id="368b2-131">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="368b2-132">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="368b2-132">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="368b2-133">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="368b2-133">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="368b2-134">注册可能需要一到五个工作日。</span><span class="sxs-lookup"><span data-stu-id="368b2-134">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="368b2-135">提交请求以激活 Office 365 客户密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-135">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="368b2-136">创建两个新的 Azure 订阅后，你将需要通过完成 Microsoft FastTrack 门户中承载的 Web 表单提交相应的客户密钥/服务请求。</span><span class="sxs-lookup"><span data-stu-id="368b2-136">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="368b2-137">**FastTrack 团队不协助客户密钥。Office 只需使用 FastTrack 门户提交表单，并帮助我们跟踪与客户密钥的相关产品/服务**。</span><span class="sxs-lookup"><span data-stu-id="368b2-137">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="368b2-138">在每个订阅中创建高级 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="368b2-138">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="368b2-139">向每个密钥保管人分配权限</span><span class="sxs-lookup"><span data-stu-id="368b2-139">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="368b2-140">启用密钥保管库后进行确认删除</span><span class="sxs-lookup"><span data-stu-id="368b2-140">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="368b2-141">通过创建或导入密钥为每个密钥保管库添加密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-141">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="368b2-142">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="368b2-142">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="368b2-143">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="368b2-143">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="368b2-144">验证 Azure Key Vault 配置设置</span><span class="sxs-lookup"><span data-stu-id="368b2-144">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="368b2-145">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="368b2-145">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="368b2-146">**在 Office 365 中：**</span><span class="sxs-lookup"><span data-stu-id="368b2-146">**In Office 365:**</span></span>
  
<span data-ttu-id="368b2-147">Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="368b2-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="368b2-148">创建数据加密策略 (DEP) 用于 Exchange Online 和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="368b2-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="368b2-149">为邮箱分配 DEP</span><span class="sxs-lookup"><span data-stu-id="368b2-149">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="368b2-150">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="368b2-150">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="368b2-151">SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="368b2-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="368b2-152">为每个 SharePoint Online (OneDrive for Business) 创建数据加密策略</span><span class="sxs-lookup"><span data-stu-id="368b2-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="368b2-153">验证 SharePoint Online、OneDrive for Business 和 Teams 文件的文件加密</span><span class="sxs-lookup"><span data-stu-id="368b2-153">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="368b2-154">在 Azure 密钥保管库和适用于客户密钥的 Microsoft FastTrack 中完成任务</span><span class="sxs-lookup"><span data-stu-id="368b2-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="368b2-155">在 Azure 密钥保管库中完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-155">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="368b2-156">无论是要为 Exchange Online 和 Skype for Business 设置了"客户密钥"，还是为 SharePoint Online、OneDrive for Business 和 Teams 文件设置了"客户密钥"，或 Office 365 中所有受支持的服务，都需要完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="368b2-156">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="368b2-157">创建两个新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="368b2-157">Create two new Azure subscriptions</span></span>

<span data-ttu-id="368b2-158">客户密钥需要两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="368b2-158">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="368b2-159">作为最佳做法，Microsoft 建议创建新的 Azure 订阅以用于客户密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-159">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="368b2-160">Azure Key Vault 密钥只能被授予同一 Azure Active Directory (AAD) 租户中的应用程序，你必须使用与将分配 DeSP 的组织所用的相同 Azure AD 租户创建新订阅。</span><span class="sxs-lookup"><span data-stu-id="368b2-160">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="368b2-161">例如，使用在组织中拥有全局管理员权限的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="368b2-161">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="368b2-162">有关详细步骤，[请参阅"注册作为组织"的 Azure。](https://azure.microsoft.com/documentation/articles/sign-up-organization/)</span><span class="sxs-lookup"><span data-stu-id="368b2-162">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="368b2-163">客户密钥要求每个数据加密策略需要两个密钥 (DEP) 。</span><span class="sxs-lookup"><span data-stu-id="368b2-163">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="368b2-164">为此，你必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="368b2-164">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="368b2-165">作为最佳做法，Microsoft 建议在每个订阅中配置组织的单独成员。</span><span class="sxs-lookup"><span data-stu-id="368b2-165">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="368b2-166">此外，这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-166">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="368b2-167">这将在防止你的组织意外、有意删除或恶意删除时受到保护，否则不对其负责的密钥进行管理。</span><span class="sxs-lookup"><span data-stu-id="368b2-167">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="368b2-168">建议设置新的 Azure 订阅，这些订阅仅用于管理 Azure 密钥保管库资源，以便用于客户密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-168">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="368b2-169">对于可为组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="368b2-169">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="368b2-170">遵循这些最佳做法可最大限度地减少人为错误的影响，同时帮助管理客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="368b2-170">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="368b2-171">提交请求以激活 Office 365 客户密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-171">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="368b2-172">完成 Azure 步骤后，你将需要在 Microsoft FastTrack 门户中提交优 [惠请求](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="368b2-172">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="368b2-173">一经通过 FastTrack Web 门户提交请求后，Microsoft 将验证你提供的 Azure Key Vault 配置数据和联系人信息。</span><span class="sxs-lookup"><span data-stu-id="368b2-173">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="368b2-174">您在产品/服务表单中所做的有关组织的授权主管的选择至关重要，并且这是完成客户密钥注册所必需的。</span><span class="sxs-lookup"><span data-stu-id="368b2-174">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="368b2-175">表单中选择的组织主管将用于确保撤销和销销用于客户密钥数据加密策略的所有密钥的任何请求的真实性。</span><span class="sxs-lookup"><span data-stu-id="368b2-175">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="368b2-176">一步只需执行一次才能激活 Exchange Online 和 Skype for Business 的客户密钥，并需要第二次才能激活 SharePoint Online 和 OneDrive for Business 的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-176">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="368b2-177">要提交用于激活客户密钥的产品/服务，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="368b2-177">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="368b2-178">使用在组织中拥有全局管理员权限的工作或学校帐户登录到 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="368b2-178">Using a work or school account that has global administrator permissions in your organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="368b2-179">登录后，浏览到 **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="368b2-179">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="368b2-180">从**导航**栏选择"部署 **"或**选择 **"在'部署信息卡\*\*\*\*上查看'部署'** 资源"，然后查看当前产品/服务列表。</span><span class="sxs-lookup"><span data-stu-id="368b2-180">Choose **Deploy** from the navigation bar **OR** select **View all deployment resources** on the **Deploy** information card, and review the list of current offers.</span></span>

4. <span data-ttu-id="368b2-181">选择适用于您的优惠的信息卡：</span><span class="sxs-lookup"><span data-stu-id="368b2-181">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="368b2-182">**Exchange Online 和 Skype for Business：** 为 **Exchange Online 产品选择请求加密密钥帮助** 。</span><span class="sxs-lookup"><span data-stu-id="368b2-182">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange online** offer.</span></span>

   - <span data-ttu-id="368b2-183">**SharePoint Online、OneDrive 和 Teams 文件：** 为 **Sharepoint 和 OneDrive 产品选择请求加密密钥** 帮助。</span><span class="sxs-lookup"><span data-stu-id="368b2-183">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.</span></span>

5. <span data-ttu-id="368b2-184">查看优惠详细信息后，选择"继续**执行第 2 步"。**</span><span class="sxs-lookup"><span data-stu-id="368b2-184">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="368b2-185">填写所有适用的详细信息，并在优惠表单上填写请求的信息。</span><span class="sxs-lookup"><span data-stu-id="368b2-185">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="368b2-186">特别注意你所选择的选择，您希望向组织内人员授权批准加密密钥和数据的永久及不可恢复销销。</span><span class="sxs-lookup"><span data-stu-id="368b2-186">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="368b2-187">完成表单后，选择"**提交"。**</span><span class="sxs-lookup"><span data-stu-id="368b2-187">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="368b2-188">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="368b2-188">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="368b2-189">根加密密钥的临时或永久丢失可能非常中断，甚至可能会导致服务操作的统计性问题，并且会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="368b2-189">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="368b2-190">因此，与客户密钥一起使用的资源需要强有强的保护。</span><span class="sxs-lookup"><span data-stu-id="368b2-190">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="368b2-191">用于客户密钥的所有 Azure 资源都提供一些不在默认配置的保护机制。</span><span class="sxs-lookup"><span data-stu-id="368b2-191">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="368b2-192">可以标记或注册 Azure 订阅，从而阻止立即和不可撤销。</span><span class="sxs-lookup"><span data-stu-id="368b2-192">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="368b2-193">这称为注册强制保留期。</span><span class="sxs-lookup"><span data-stu-id="368b2-193">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="368b2-194">为强制保留期注册 Azure 订阅所需的步骤需要与 Microsoft 365 团队进行协作。</span><span class="sxs-lookup"><span data-stu-id="368b2-194">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="368b2-195">此过程可能花费一到五个工作日。</span><span class="sxs-lookup"><span data-stu-id="368b2-195">This process can take from one to five business days.</span></span> <span data-ttu-id="368b2-196">以前，这有时称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="368b2-196">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="368b2-197">联系 Microsoft 365 团队之前，必须为用于客户密钥的每个 Azure 订阅执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="368b2-197">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="368b2-198">在开始之前， [请确保已安装 Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模块。</span><span class="sxs-lookup"><span data-stu-id="368b2-198">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="368b2-199">使用 Azure PowerShell 登录。</span><span class="sxs-lookup"><span data-stu-id="368b2-199">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="368b2-200">有关说明，请参阅["使用 Azure PowerShell 登录"。](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="368b2-200">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="368b2-201">运行 Register-AzProviderFeature cmdlet 注册订阅，以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="368b2-201">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="368b2-202">为每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="368b2-202">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="368b2-203">请联系 Microsoft 以完成该过程。</span><span class="sxs-lookup"><span data-stu-id="368b2-203">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="368b2-204">对于 SharePoint 和 OneDrive for Business 团队，[请与spock@microsoft.com。](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="368b2-204">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="368b2-205">对于 Exchange Online 和 Skype for Business，[请联系exock@microsoft.com。](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="368b2-205">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="368b2-206">在电子邮件中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="368b2-206">Include the following in your email:</span></span>

   <span data-ttu-id="368b2-207">**Subject：Customer**Key for \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="368b2-207">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="368b2-208">**正文**：已完成强制保留期的订阅 ID。</span><span class="sxs-lookup"><span data-stu-id="368b2-208">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="368b2-209">每个订阅的 Get-AzProviderFeature 的输出。</span><span class="sxs-lookup"><span data-stu-id="368b2-209">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="368b2-210">一年的 (协议 (SLA) 完成此过程的过程是 5 个工作日，一则表示 Microsoft 已被 (并且已验证) 你已注册你的订阅以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="368b2-210">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="368b2-211">收到 Microsoft 发送的注册注册通知完成的通知后，按如下所示运行 Get-AzProviderFeature 命令以验证注册状态。</span><span class="sxs-lookup"><span data-stu-id="368b2-211">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="368b2-212">如果已验证，Get-AzProviderFeature 命令将返回注册**状态属性的值"已\*\*\*\*注册"。**</span><span class="sxs-lookup"><span data-stu-id="368b2-212">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="368b2-213">为每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="368b2-213">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="368b2-214">若要完成此过程，请运行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="368b2-214">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="368b2-215">为每个订阅执行此操作。</span><span class="sxs-lookup"><span data-stu-id="368b2-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="368b2-216">在每个订阅中创建高级 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="368b2-216">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="368b2-217">创建密钥保管库的步骤会记录在 Azure Key [Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)入门中。Azure Key Vault 安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组和在该资源组中创建密钥保管库的步骤。</span><span class="sxs-lookup"><span data-stu-id="368b2-217">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="368b2-218">创建密钥保管库时，必须选择 SKU：标准版或高级版。</span><span class="sxs-lookup"><span data-stu-id="368b2-218">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="368b2-219">标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护），并且高级 SKU 允许使用 HSM 保护密钥保管密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-219">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="368b2-220">客户密钥接受使用任一 SKU 的密钥保管，但 Microsoft 强烈建议你仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="368b2-220">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="368b2-221">两种类型的运营的成本都相同，因此，唯一的成本差异是每个受 HSM 保护的密钥的每月成本。</span><span class="sxs-lookup"><span data-stu-id="368b2-221">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="368b2-222">有关详细信息 [，请参阅密钥保管库定](https://azure.microsoft.com/pricing/details/key-vault/) 价。</span><span class="sxs-lookup"><span data-stu-id="368b2-222">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="368b2-223">将高级 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，仅使用标准 SKU 密钥和密钥进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="368b2-223">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="368b2-224">对于将使用客户密钥的每个 Microsoft 365 服务，在你创建的两个 Azure 订阅中创建一个密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="368b2-224">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="368b2-225">例如，对于 Exchange Online 和仅 Skype for Business，或仅限 SharePoint Online 和 OneDrive for Business，你只会创建一对保管库。</span><span class="sxs-lookup"><span data-stu-id="368b2-225">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="368b2-226">若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥，您需要创建两对密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="368b2-226">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="368b2-227">应对反映要使用的数据加密策略与之关联的数据加密策略的密钥保管进行命名约定。</span><span class="sxs-lookup"><span data-stu-id="368b2-227">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="368b2-228">请参阅下面的"最佳实践"部分，了解命名约定建议。</span><span class="sxs-lookup"><span data-stu-id="368b2-228">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="368b2-229">为每个数据加密策略创建一组单独的成对保管的存储库。</span><span class="sxs-lookup"><span data-stu-id="368b2-229">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="368b2-230">对于 Exchange Online，当您向邮箱分配策略时，将选择数据加密策略的作用域。</span><span class="sxs-lookup"><span data-stu-id="368b2-230">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="368b2-231">一个邮箱只能分配一个策略，并且最多可以创建 50 个策略。</span><span class="sxs-lookup"><span data-stu-id="368b2-231">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="368b2-232">对于 SharePoint Online，策略的范围是地理位置或地理位置的组织内 _的所有数据_。</span><span class="sxs-lookup"><span data-stu-id="368b2-232">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="368b2-233">创建密钥保管库也需要创建 Azure 资源组，因为关键保管库需要存储容量 (尽管平均小的) 和密钥保管库进行日志记录（如果启用，则还会生成存储的数据）。</span><span class="sxs-lookup"><span data-stu-id="368b2-233">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="368b2-234">作为最佳做法，Microsoft 建议使用不同的管理员来管理每个资源组，并且管理与将管理所有相关客户主要资源的管理员集相一对。</span><span class="sxs-lookup"><span data-stu-id="368b2-234">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="368b2-235">为了最大限度地提高可用性，你的关键保管库应位于 Microsoft 365 服务接近的区域中。</span><span class="sxs-lookup"><span data-stu-id="368b2-235">To maximize availability, your key vaults should be in regions close to your Microsoft 365 service.</span></span> <span data-ttu-id="368b2-236">例如，如果您的 Exchange Online 组织位于北美，请将关键保管库置于北美。</span><span class="sxs-lookup"><span data-stu-id="368b2-236">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="368b2-237">如果您的 Exchange Online 组织在欧洲，请将关键保管人分于欧洲。</span><span class="sxs-lookup"><span data-stu-id="368b2-237">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="368b2-238">对密钥保管库使用一个公用前缀， 并对保管人和 (项的使用和范围（例如，对于在北美洲托管的 Contoso SharePoint 服务的话，可能的一对名为 Contoso-O365SP-NA-VaultA1 和 Contoso-O365SP-NAultA2）的使用和范围。这包括有关这些保管人的使用和范围的缩写。</span><span class="sxs-lookup"><span data-stu-id="368b2-238">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="368b2-239">存储库名称是 Azure 中的全局唯一字符串，因此可能需要尝试对期名称的变体，以防其他 Azure 客户已经声明了所需的名称。</span><span class="sxs-lookup"><span data-stu-id="368b2-239">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="368b2-240">由于无法更改 2017 年 7 月的存储库名称，因此最佳做法是，使用书面编写计划设置并使用第二个人验证计划是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="368b2-240">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="368b2-241">如果可能，请在非配对区域中创建你的保管者。</span><span class="sxs-lookup"><span data-stu-id="368b2-241">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="368b2-242">配对的 Azure 区域在服务故障域中提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="368b2-242">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="368b2-243">因此，可以要求将区域对作为对应的备份区域。</span><span class="sxs-lookup"><span data-stu-id="368b2-243">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="368b2-244">这意味着放置在一个区域中的 Azure 资源将通过配对区域自动获取容错。</span><span class="sxs-lookup"><span data-stu-id="368b2-244">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="368b2-245">因此，选择在一个数据加密策略中使用的两个保管区域，其中区域是成对的表示仅使用共有两个可用性区域。</span><span class="sxs-lookup"><span data-stu-id="368b2-245">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="368b2-246">大多数地理区域只有两个区域，因此，尚未选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="368b2-246">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="368b2-247">如果可能，请为用于数据加密策略的两个保管库选择两个非配对地区。</span><span class="sxs-lookup"><span data-stu-id="368b2-247">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="368b2-248">这一总可用性从四个区域中受益。</span><span class="sxs-lookup"><span data-stu-id="368b2-248">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="368b2-249">有关详细信息，请参阅 ["业务连续性和灾难恢复 (BCDR) ：Azure 配对区域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) "以获取区域对列表。</span><span class="sxs-lookup"><span data-stu-id="368b2-249">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="368b2-250">向每个密钥保管人分配权限</span><span class="sxs-lookup"><span data-stu-id="368b2-250">Assign permissions to each key vault</span></span>

<span data-ttu-id="368b2-251">对于每个关键保管库，您需要根据你的实施定义客户密钥定义三个单独的权限集。</span><span class="sxs-lookup"><span data-stu-id="368b2-251">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="368b2-252">例如，您需要为以下每个对象定义一个权限集：</span><span class="sxs-lookup"><span data-stu-id="368b2-252">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="368b2-253">**将对组织的密钥** 保管库进行日常管理的关键保管者。</span><span class="sxs-lookup"><span data-stu-id="368b2-253">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="368b2-254">这些任务包括备份、创建、获取、导入、列表和还原。</span><span class="sxs-lookup"><span data-stu-id="368b2-254">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="368b2-255">分配给关键保管库管理员的权限集不包括删除键的权限。</span><span class="sxs-lookup"><span data-stu-id="368b2-255">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="368b2-256">这个重要做法是重要的做法，</span><span class="sxs-lookup"><span data-stu-id="368b2-256">This is intentional and an important practice.</span></span> <span data-ttu-id="368b2-257">通常不会删除加密密钥，因为这样操作会永久销销数据。</span><span class="sxs-lookup"><span data-stu-id="368b2-257">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="368b2-258">作为最佳实践，默认情况下不要将此权限授予密钥保管库管理员。</span><span class="sxs-lookup"><span data-stu-id="368b2-258">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="368b2-259">而是要保留此功能以供主要保管人参与者使用，并且只在清楚了解后果后只将它分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="368b2-259">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="368b2-260">若要将这些权限分配给组织用户，请使用 Azure PowerShell 登录到 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="368b2-260">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="368b2-261">有关说明，请参阅["使用 Azure PowerShell 登录"。](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="368b2-261">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="368b2-262">运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="368b2-262">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="368b2-263">例如：</span><span class="sxs-lookup"><span data-stu-id="368b2-263">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="368b2-264">**可更改 Azure Key Vault** 本身的权限的密钥保管者。</span><span class="sxs-lookup"><span data-stu-id="368b2-264">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="368b2-265">在员工离开或加入团队时，你需要更改这些权限，或在几大少数情况下，大家保管管理员自行需要删除或还原密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="368b2-265">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="368b2-266">需向此保管库明的参与者授予这组关键保管者。 **Contributor**</span><span class="sxs-lookup"><span data-stu-id="368b2-266">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="368b2-267">你可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="368b2-267">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="368b2-268">有关详细步骤，请参阅 ["使用基于角色的访问控制"管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="368b2-268">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="368b2-269">创建订阅的管理员隐式具有此访问权限，并具有向参与者角色分配其他管理员的功能。</span><span class="sxs-lookup"><span data-stu-id="368b2-269">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="368b2-270">如果你计划将客户密钥用于 Exchange Online 和 Skype for Business，需要授予 Microsoft 365 权限，以代表 Exchange Online 和 Skype for Business 使用密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="368b2-270">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Microsoft 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="368b2-271">同样，如果你计划对 SharePoint Online 和 OneDrive for Business 使用客户密钥，则需要添加 Microsoft 365 的权限，以代表 SharePoint Online 和 OneDrive for Business 使用密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="368b2-271">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Microsoft 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="368b2-272">若要授予 Microsoft 365 的权限，请使用以下 **语法运行 Set-AzKeyVaultAccessPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="368b2-272">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="368b2-273">其中：</span><span class="sxs-lookup"><span data-stu-id="368b2-273">Where:</span></span>

    - <span data-ttu-id="368b2-274">*存储库名称* 是你创建的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="368b2-274">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="368b2-275">对于 Exchange Online 和 Skype for Business，将*Office 365 appID 替换为*`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="368b2-275">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="368b2-276">对于 SharePoint Online、OneDrive for Business 和 Teams 文件，将*Office 365 appID 替换为*`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="368b2-276">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="368b2-277">示例：为 Exchange Online 和 Skype for Business 设置权限：</span><span class="sxs-lookup"><span data-stu-id="368b2-277">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="368b2-278">示例：为 SharePoint Online、OneDrive for Business 和 Teams 文件设置权限：</span><span class="sxs-lookup"><span data-stu-id="368b2-278">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="368b2-279">启用密钥保管库后进行确认删除</span><span class="sxs-lookup"><span data-stu-id="368b2-279">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="368b2-280">当你可以快速恢复密钥时，你可能因意外或恶意删除的密钥而体验到长时间的服务中断。</span><span class="sxs-lookup"><span data-stu-id="368b2-280">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="368b2-281">您需要启用此配置（称为"自动删除"）后才可以将密钥与客户密钥一起使用。</span><span class="sxs-lookup"><span data-stu-id="368b2-281">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="368b2-282">启用"Soft Delete"允许您在删除后 90 天内恢复密钥或保管库，而无需从备份中还原密钥或附件。</span><span class="sxs-lookup"><span data-stu-id="368b2-282">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="368b2-283">若要启用密钥保管库上的"Soft Delete"，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="368b2-283">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="368b2-284">通过 Windows Powershell 登录到 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="368b2-284">Sign in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="368b2-285">有关说明，请参阅["使用 Azure PowerShell 登录"。](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="368b2-285">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="368b2-286">运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="368b2-286">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="368b2-287">在此示例中， *被保管人名称* 为你启用了"soft delete"的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="368b2-287">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="368b2-288">通过运行 **Get-AzKeyVault** cmdlet 确认已为密钥保管库配置了"soft delete"。</span><span class="sxs-lookup"><span data-stu-id="368b2-288">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="368b2-289">如果为密钥保管库正确配置了"soft delete"，_则"Soft Delete Enabled"_ 属性的值为**True：**</span><span class="sxs-lookup"><span data-stu-id="368b2-289">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="368b2-290">通过创建或导入密钥为每个密钥保管库添加密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-290">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="368b2-291">有两种方法可以向 Azure 密钥保管库中添加密钥;可直接在密钥保管库中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-291">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="368b2-292">直接在键保管库中创建键是不太复杂的方法，而导入密钥可提供对生成密钥方式的总控制。</span><span class="sxs-lookup"><span data-stu-id="368b2-292">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="368b2-293">若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-293">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="368b2-294">其中：</span><span class="sxs-lookup"><span data-stu-id="368b2-294">Where:</span></span>

- <span data-ttu-id="368b2-295">*存储库名称* 是你希望在其中创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="368b2-295">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="368b2-296">*项名称* 是要为新项命名的名称。</span><span class="sxs-lookup"><span data-stu-id="368b2-296">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="368b2-297">使用类似的命名约定命名密钥，如上所述对于密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="368b2-297">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="368b2-298">这样，在仅显示密钥名称的工具中，字符串为自描述。</span><span class="sxs-lookup"><span data-stu-id="368b2-298">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="368b2-299">如果要使用 HSM 保护该密钥，请确保将 **HSM 指定** 为 _Destination 参数的值_ ，否则请指定 **Software**。</span><span class="sxs-lookup"><span data-stu-id="368b2-299">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="368b2-300">例如，</span><span class="sxs-lookup"><span data-stu-id="368b2-300">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="368b2-301">若要直接将密钥导入密钥保管库，需要有一个嵌套硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="368b2-301">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="368b2-302">一些组织首选这种方法来建立密钥的验证，然后此方法还提供以下方法：</span><span class="sxs-lookup"><span data-stu-id="368b2-302">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following:</span></span>
  
- <span data-ttu-id="368b2-303">用于导入的工具集包括来自用于加密所生成的密钥的 Exchange 密钥 (KEK) 的证明，并且该密钥是在由 nCipher 制造的一个定型 HSM 内生成的。</span><span class="sxs-lookup"><span data-stu-id="368b2-303">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="368b2-304">该工具集包括来自 nCipher 的证明，Azure Key Vault 安全性世界也是在 nCipher 的一种形型 HSM 制造中生成的。</span><span class="sxs-lookup"><span data-stu-id="368b2-304">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="368b2-305">此证明向你证明 Microsoft 也使用正版 NCipher 硬件。</span><span class="sxs-lookup"><span data-stu-id="368b2-305">This attestation proves to you that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="368b2-306">与你的安全组进行检查，以确定是否需要上面的证明。</span><span class="sxs-lookup"><span data-stu-id="368b2-306">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="368b2-307">有关在内部创建密钥并将其导入关键保管库的详细步骤，请参阅["如何为 Azure 密钥保管库生成并传输受 HSM 保护的密钥"。](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)</span><span class="sxs-lookup"><span data-stu-id="368b2-307">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="368b2-308">使用 Azure 说明在每个密钥保管库中创建密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-308">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="368b2-309">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="368b2-309">Check the recovery level of your keys</span></span>

<span data-ttu-id="368b2-310">Microsoft 365 要求 Azure 密钥保管库订阅被设置为"不取消"，并且客户密钥使用的密钥已启用了"已自动删除"。</span><span class="sxs-lookup"><span data-stu-id="368b2-310">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="368b2-311">你可以通过查看密钥上的恢复级别进行确认。</span><span class="sxs-lookup"><span data-stu-id="368b2-311">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="368b2-312">若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-312">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="368b2-313">如果 _恢复级别属性返回_ 除 **"可恢复 - ProtectedSubscription"的值之外的任何值**，则需要查看本主题并确保你已遵循所有将订阅置于"不取消"列表上的步骤，并且已在每个密钥保管库上启用了"已自动删除"。</span><span class="sxs-lookup"><span data-stu-id="368b2-313">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="368b2-314">备份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="368b2-314">Back up Azure Key Vault</span></span>

<span data-ttu-id="368b2-315">创建之后或对密钥的任何更改后，立即执行备份的备份和存储副本（联机和脱机）。</span><span class="sxs-lookup"><span data-stu-id="368b2-315">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="368b2-316">脱机副本不应该连接到任何网络，例如物理安全或商业存储设施。</span><span class="sxs-lookup"><span data-stu-id="368b2-316">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="368b2-317">至少应将一个备份副本存储在发生灾难时可以访问的位置中。</span><span class="sxs-lookup"><span data-stu-id="368b2-317">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="368b2-318">备份 blob 是还原密钥材料唯一的方法，这应该是密钥保证密钥永久损坏或以其他方式呈现的不可操作。</span><span class="sxs-lookup"><span data-stu-id="368b2-318">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="368b2-319">Azure Key Vault 外部的且已导入到 Azure 密钥保管库的密钥不限定为备份，因为客户密钥使用所需的元数据在外部密钥中不存在。</span><span class="sxs-lookup"><span data-stu-id="368b2-319">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="368b2-320">只有 Azure 密钥 Vault 进行的备份可用于通过客户密钥执行还原操作。</span><span class="sxs-lookup"><span data-stu-id="368b2-320">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="368b2-321">因此，一定要在上传或创建密钥后创建 Azure 密钥保管库的备份。</span><span class="sxs-lookup"><span data-stu-id="368b2-321">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="368b2-322">若要创建 Azure 密钥保管库的备份，请 [运行 Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-322">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="368b2-323">确保输出文件使用后缀 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="368b2-323">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="368b2-324">此 cmdlet 产生的输出文件将进行加密，不能在 Azure 密钥保管库外部使用。</span><span class="sxs-lookup"><span data-stu-id="368b2-324">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="368b2-325">备份只能还原到从中获取备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="368b2-325">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="368b2-326">对于输出文件，选择存储库名称和项名的组合。</span><span class="sxs-lookup"><span data-stu-id="368b2-326">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="368b2-327">这将使文件名自描述。</span><span class="sxs-lookup"><span data-stu-id="368b2-327">This will make the file name self-describing.</span></span> <span data-ttu-id="368b2-328">同时，它还可以确保备份文件名不会被合并。</span><span class="sxs-lookup"><span data-stu-id="368b2-328">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="368b2-329">例如：</span><span class="sxs-lookup"><span data-stu-id="368b2-329">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="368b2-330">验证 Azure Key Vault 配置设置</span><span class="sxs-lookup"><span data-stu-id="368b2-330">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="368b2-331">在 DEP 中使用密钥之前执行验证是可选的，但强烈建议使用。</span><span class="sxs-lookup"><span data-stu-id="368b2-331">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="368b2-332">特别是，如果您使用步骤设置您的密钥和存储库（而不是本主题中介绍的盘）来设置密钥和存储库，应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。</span><span class="sxs-lookup"><span data-stu-id="368b2-332">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="368b2-333">验证是否已启用获取、wrapKey 和 unwrapKey 操作：</span><span class="sxs-lookup"><span data-stu-id="368b2-333">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="368b2-334">运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-334">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="368b2-335">在输出中，查找访问策略以及 Exchange Online 标识 (GUID)  (GUID 或 SharePoint Online 标识 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="368b2-335">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="368b2-336">所有这三个权限必须在"密钥的权限"下显示。</span><span class="sxs-lookup"><span data-stu-id="368b2-336">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="368b2-337">如果访问策略配置不正确，请运行 Set-AzKeyVaultAccessPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-337">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="368b2-338">例如，对于 Exchange Online 和 Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="368b2-338">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="368b2-339">例如，对于 SharePoint Online 和 OneDrive for Business：</span><span class="sxs-lookup"><span data-stu-id="368b2-339">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="368b2-340">若要验证未为密钥设置过期日期，请运行 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-340">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="368b2-341">客户密钥无法使用过期密钥，并且尝试通过过期密钥的操作将失败，并且可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="368b2-341">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="368b2-342">强烈建议用于客户密钥的密钥没有到期日期。</span><span class="sxs-lookup"><span data-stu-id="368b2-342">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="368b2-343">一个已设置、无法删除过期日期，但可以更改为不同的日期。</span><span class="sxs-lookup"><span data-stu-id="368b2-343">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="368b2-344">如果必须使用设置了过期日期的某个项，请将过期值更改为 12/31/9999/ 12。</span><span class="sxs-lookup"><span data-stu-id="368b2-344">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="368b2-345">过期日期为 9999 年 2 月 31 日以外的密钥无法通过 Microsoft 365 验证。</span><span class="sxs-lookup"><span data-stu-id="368b2-345">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="368b2-346">若要更改已设置为 1999 年 12 月 31 日以外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-346">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="368b2-347">不要对用于客户密钥的加密密钥设置到期日期。</span><span class="sxs-lookup"><span data-stu-id="368b2-347">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="368b2-348">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="368b2-348">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="368b2-349">在 Azure 中完成所有用于设置密钥保管库并添加密钥的步骤后，运行以下命令来获取每个密钥保管库中密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="368b2-349">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="368b2-350">稍后创建和分配每个 DEP 时需要使用这些 URI，因此请将此信息保存到安全的位置。</span><span class="sxs-lookup"><span data-stu-id="368b2-350">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="368b2-351">请记住针对每个密钥保管库运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="368b2-351">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="368b2-352">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="368b2-352">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="368b2-353">Office 365：为 Exchange Online 和 Skype for Business 设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-353">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="368b2-354">在开始之前，请确保已完成安装 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-354">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="368b2-355">有关 [信息，请参阅 Azure Key Vault 和 Microsoft FastTrack 中的完成](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-355">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="368b2-356">要为 Exchange Online 和 Skype for Business 设置客户密钥，需要通过远程连接到 Exchange Online 的工具来执行这些Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="368b2-356">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="368b2-357">创建数据加密策略 (DEP) 用于 Exchange Online 和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="368b2-357">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="368b2-358">DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="368b2-358">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="368b2-359">为 Microsoft 365 中的邮箱分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="368b2-359">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="368b2-360">Microsoft 365 随后使用策略中标识的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="368b2-360">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="368b2-361">若要创建 DEP，您需要之前获得的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="368b2-361">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="368b2-362">有关[说明，请参阅"获取每个 Azure 密钥保管库密钥的 URI"。](#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="368b2-362">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="368b2-363">记住！</span><span class="sxs-lookup"><span data-stu-id="368b2-363">Remember!</span></span> <span data-ttu-id="368b2-364">创建 DEP 时，需指定驻留在两个不同 Azure Key Vault 中的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-364">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="368b2-365">确保这些密钥位于两个单独的 Azure 区域，以确保地域冗余。</span><span class="sxs-lookup"><span data-stu-id="368b2-365">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="368b2-366">若要创建 DEP，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="368b2-366">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="368b2-367">在本地计算机上，使用在组织中拥有全局管理员权限的工作或学校帐户[，在 Windows PowerShell 窗口中连接到 Exchange Online PowerShell。](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="368b2-367">On your local computer, using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="368b2-368">若要创建 DEP，请键入以下命令来使用 New-DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="368b2-368">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="368b2-369">其中：</span><span class="sxs-lookup"><span data-stu-id="368b2-369">Where:</span></span>

   - <span data-ttu-id="368b2-370">*PolicyName* 是您要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="368b2-370">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="368b2-371">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="368b2-371">Names cannot contain spaces.</span></span> <span data-ttu-id="368b2-372">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="368b2-372">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="368b2-373">*策略描述* 是策略的用户友好描述，有助于您记住策略的用法。</span><span class="sxs-lookup"><span data-stu-id="368b2-373">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="368b2-374">您可以在描述中包含空格。</span><span class="sxs-lookup"><span data-stu-id="368b2-374">You can include spaces in the description.</span></span> <span data-ttu-id="368b2-375">例如"美国亚库的邮箱的根键"。</span><span class="sxs-lookup"><span data-stu-id="368b2-375">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="368b2-376">*KeyVaultURI1* 是策略中第一个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="368b2-376">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="368b2-377">例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。</span><span class="sxs-lookup"><span data-stu-id="368b2-377">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="368b2-378">*KeyVaultURI2* 是策略中第二个键的 URI。</span><span class="sxs-lookup"><span data-stu-id="368b2-378">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="368b2-379">例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。</span><span class="sxs-lookup"><span data-stu-id="368b2-379">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="368b2-380">两个 URI 之间用逗号和空格分隔。</span><span class="sxs-lookup"><span data-stu-id="368b2-380">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="368b2-381">示例：</span><span class="sxs-lookup"><span data-stu-id="368b2-381">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="368b2-382">有关语法和参数的详细信息，请参阅[New-DataEncryptionPolicy。](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)</span><span class="sxs-lookup"><span data-stu-id="368b2-382">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="368b2-383">为邮箱分配 DEP</span><span class="sxs-lookup"><span data-stu-id="368b2-383">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="368b2-384">使用 Set-Mailbox cmdlet 为邮箱分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="368b2-384">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="368b2-385">分配策略后，Microsoft 365 可以使用 DEP 中指定的密钥加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="368b2-385">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="368b2-386">*其中，MailboxIdParameter*指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="368b2-386">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="368b2-387">有关 Set-Mailbox cmdlet 的详细信息，请参阅[Set-Mailbox。](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="368b2-387">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="368b2-388">对于 [将 Outlook for iOS 和 Outlook for Android 与混合新式验证一](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)起使用的本地邮箱，同步到 Exchange Online 租户的本地邮箱数据可以使用 Set-MailUser cmdlet 分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="368b2-388">For [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), the on-premises mailbox data that is synchronized into your Exchange Online tenant can have DEP assigned using the Set-MailUser cmdlet.</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="368b2-389">其中 *MailUserIdParameter* 指定邮件用户 (一个也称为启用邮件) 。</span><span class="sxs-lookup"><span data-stu-id="368b2-389">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="368b2-390">有关 Set-MailUser cmdlet 的详细信息，请参阅 [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="368b2-390">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="368b2-391">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="368b2-391">Validate mailbox encryption</span></span>

<span data-ttu-id="368b2-392">加密邮箱可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="368b2-392">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="368b2-393">对于首次分配策略，邮箱还必须将它从一个数据库完全移动到另一个数据库，服务才能加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="368b2-393">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="368b2-394">建议你等待 72 小时，然后再在更改 DEP 或首次为邮箱分配 DEP 之后尝试验证加密。</span><span class="sxs-lookup"><span data-stu-id="368b2-394">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="368b2-395">使用 Get-MailboxStatistics cmdlet 可确定邮箱是否加密。</span><span class="sxs-lookup"><span data-stu-id="368b2-395">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="368b2-396">如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值;如果邮箱未 **加密，则** 返回 false 值。</span><span class="sxs-lookup"><span data-stu-id="368b2-396">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="368b2-397">完成邮箱移动的时间取决于首次向其分配 DEP 的邮箱数以及邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="368b2-397">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="368b2-398">如果从分配 DEP 指定的一周后未对邮箱加密，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="368b2-398">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="368b2-399">Office 365：为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-399">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="368b2-400">在开始之前，请确保已完成安装 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-400">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="368b2-401">有关 [信息，请参阅 Azure Key Vault 和 Microsoft FastTrack 中的完成](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 任务。</span><span class="sxs-lookup"><span data-stu-id="368b2-401">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="368b2-402">若要设置 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥，需要通过远程连接到 SharePoint Online 和 Windows PowerShell 来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="368b2-402">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="368b2-403">为每个 SharePoint Online (OneDrive for Business) 创建数据加密策略</span><span class="sxs-lookup"><span data-stu-id="368b2-403">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="368b2-404">将 DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="368b2-404">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="368b2-405">你可以将 DEP 应用于位于一个地理位置（也称为"地理"）中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="368b2-405">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="368b2-406">如果使用 Office 365 多地理位置功能，可以为每个地理位置创建一个 DEP，使每个地理位置使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-406">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="368b2-407">如果你未使用多地理位置，则可在组织中创建一个 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件。</span><span class="sxs-lookup"><span data-stu-id="368b2-407">If you are not using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="368b2-408">Microsoft 365 使用 DEP 中标识的密钥对该地理位置中的数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="368b2-408">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="368b2-409">若要创建 DEP，您需要之前获得的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="368b2-409">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="368b2-410">有关[说明，请参阅"获取每个 Azure 密钥保管库密钥的 URI"。](#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="368b2-410">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="368b2-411">记住！</span><span class="sxs-lookup"><span data-stu-id="368b2-411">Remember!</span></span> <span data-ttu-id="368b2-412">创建 DEP 时，需指定驻留在两个不同 Azure Key Vault 中的两个密钥。</span><span class="sxs-lookup"><span data-stu-id="368b2-412">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="368b2-413">确保这些密钥位于两个单独的 Azure 区域，以确保地域冗余。</span><span class="sxs-lookup"><span data-stu-id="368b2-413">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="368b2-414">若要创建 DEP，需要使用 Windows PowerShell 远程连接到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="368b2-414">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="368b2-415">在本地计算机上，使用在组织中拥有全局管理员权限的工作或学校帐户[连接到 SharePoint Online Powershell。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="368b2-415">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="368b2-416">在 Microsoft SharePoint Online 命令行管理程序中，运行 Register-SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368b2-416">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="368b2-417">注册 DEP 时，加密将从地理位置中的数据开始。</span><span class="sxs-lookup"><span data-stu-id="368b2-417">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="368b2-418">这可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="368b2-418">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="368b2-419">验证文件加密</span><span class="sxs-lookup"><span data-stu-id="368b2-419">Validate file encryption</span></span>

 <span data-ttu-id="368b2-420">若要验证 SharePoint Online、OneDrive for Business 和 Teams 文件的加密 [，请连接到 SharePoint Online PowerShell，](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)然后使用 Get-SPODataEncryptionPolicy cmdlet 检查租户的状态。</span><span class="sxs-lookup"><span data-stu-id="368b2-420">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="368b2-421">如果 _启用_ 了客户密钥加密 **且所有** 网站中的所有文件均已加密，则 State 属性返回注册的值。</span><span class="sxs-lookup"><span data-stu-id="368b2-421">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="368b2-422">如果加密仍在进行中，此 cmdlet 则提供有关网站完成百分比的信息。</span><span class="sxs-lookup"><span data-stu-id="368b2-422">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="368b2-423">相关文章</span><span class="sxs-lookup"><span data-stu-id="368b2-423">Related articles</span></span>

- [<span data-ttu-id="368b2-424">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="368b2-424">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="368b2-425">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-425">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="368b2-426">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-426">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="368b2-427">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="368b2-427">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="368b2-428">服务加密</span><span class="sxs-lookup"><span data-stu-id="368b2-428">Service Encryption</span></span>](office-365-service-encryption.md)
