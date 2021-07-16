---
title: 使用客户密钥执行服务加密
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: 本文将介绍服务加密如何与 Microsoft 365 中的客户密钥一Microsoft 365。
ms.openlocfilehash: 9a8558a0cf36f2040614ca3ffb61e7ba9936d40f
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463957"
---
# <a name="service-encryption-with-customer-key"></a><span data-ttu-id="98483-103">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="98483-103">Service encryption with Customer Key</span></span>

<span data-ttu-id="98483-104">Microsoft 365通过 BitLocker 和分布式密钥管理器和 DKM (启用基线、) 。</span><span class="sxs-lookup"><span data-stu-id="98483-104">Microsoft 365 provides baseline, volume-level encryption enabled through BitLocker and Distributed Key Manager (DKM).</span></span> <span data-ttu-id="98483-105">Microsoft 365内容添加了一层加密。</span><span class="sxs-lookup"><span data-stu-id="98483-105">Microsoft 365 offers an added layer of encryption for your content.</span></span> <span data-ttu-id="98483-106">此内容包括来自 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="98483-106">This content includes data from Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a><span data-ttu-id="98483-107">服务加密、BitLocker 和客户密钥如何协同工作</span><span class="sxs-lookup"><span data-stu-id="98483-107">How service encryption, BitLocker, and Customer Key work together</span></span>

<span data-ttu-id="98483-108">你的数据始终使用 BitLocker 和 DKM 在 Microsoft 365 服务中进行其余加密。</span><span class="sxs-lookup"><span data-stu-id="98483-108">Your data is always encrypted at rest in the Microsoft 365 service with BitLocker and DKM.</span></span> <span data-ttu-id="98483-109">有关详细信息，请参阅如何Exchange Online[电子邮件密码](exchange-online-secures-email-secrets.md)。</span><span class="sxs-lookup"><span data-stu-id="98483-109">For more information, see [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md).</span></span> <span data-ttu-id="98483-110">客户密钥提供了防止未经授权的系统或人员查看数据的额外保护，并补充了 Microsoft 数据中心中的 BitLocker 磁盘加密。</span><span class="sxs-lookup"><span data-stu-id="98483-110">Customer Key provides extra protection against viewing of data by unauthorized systems or personnel, and complements BitLocker disk encryption in Microsoft data centers.</span></span> <span data-ttu-id="98483-111">服务加密并不用于阻止 Microsoft 人员访问你的数据。</span><span class="sxs-lookup"><span data-stu-id="98483-111">Service encryption is not meant to prevent Microsoft personnel from accessing your data.</span></span> <span data-ttu-id="98483-112">相反，客户密钥可帮助你履行控制根密钥的法规或合规性义务。</span><span class="sxs-lookup"><span data-stu-id="98483-112">Instead, Customer Key helps you meet regulatory or compliance obligations for controlling root keys.</span></span> <span data-ttu-id="98483-113">您明确授权 Microsoft 365服务使用您的加密密钥来提供增值云服务，如电子数据展示、反恶意软件、反垃圾邮件、搜索索引等。</span><span class="sxs-lookup"><span data-stu-id="98483-113">You explicitly authorize Microsoft 365 services to use your encryption keys to provide value added cloud services, such as eDiscovery, anti-malware, anti-spam, search indexing, and so on.</span></span>

<span data-ttu-id="98483-114">客户密钥基于服务加密构建，可让你提供和控制加密密钥。</span><span class="sxs-lookup"><span data-stu-id="98483-114">Customer Key is built on service encryption and lets you provide and control encryption keys.</span></span> <span data-ttu-id="98483-115">Microsoft 365然后使用这些密钥加密你的其余数据，如联机服务条款 ([OST) ](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="98483-115">Microsoft 365 then uses these keys to encrypt your data at rest as described in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx).</span></span> <span data-ttu-id="98483-116">客户密钥可帮助您履行合规性义务，因为您可以控制用于加密Microsoft 365解密数据的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="98483-116">Customer Key helps you meet compliance obligations because you control the encryption keys that Microsoft 365 uses to encrypt and decrypt data.</span></span>
  
<span data-ttu-id="98483-117">客户密钥增强了组织满足合规性要求的能力，这些要求指定了与云服务提供商的关键安排。</span><span class="sxs-lookup"><span data-stu-id="98483-117">Customer Key enhances the ability of your organization to meet the demands of compliance requirements that specify key arrangements with the cloud service provider.</span></span> <span data-ttu-id="98483-118">使用客户密钥，你可以为应用程序级别的静态Microsoft 365数据提供和控制根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="98483-118">With Customer Key, you provide and control the root encryption keys for your Microsoft 365 data at-rest at the application level.</span></span> <span data-ttu-id="98483-119">因此，你可以对组织的密钥进行控制。</span><span class="sxs-lookup"><span data-stu-id="98483-119">As a result, you exercise control over your organization's keys.</span></span>

## <a name="customer-key-with-hybrid-deployments"></a><span data-ttu-id="98483-120">混合部署的客户密钥</span><span class="sxs-lookup"><span data-stu-id="98483-120">Customer Key with hybrid deployments</span></span>

<span data-ttu-id="98483-121">客户密钥仅加密云中的其余数据。</span><span class="sxs-lookup"><span data-stu-id="98483-121">Customer Key only encrypts data at rest in the cloud.</span></span> <span data-ttu-id="98483-122">客户密钥无法保护本地邮箱和文件。</span><span class="sxs-lookup"><span data-stu-id="98483-122">Customer Key does not work to protect your on-premises mailboxes and files.</span></span> <span data-ttu-id="98483-123">可以使用另一种方法（如 BitLocker）加密本地数据。</span><span class="sxs-lookup"><span data-stu-id="98483-123">You can encrypt your on-premises data using another method, such as BitLocker.</span></span>

## <a name="about-data-encryption-policies"></a><span data-ttu-id="98483-124">关于数据加密策略</span><span class="sxs-lookup"><span data-stu-id="98483-124">About data encryption policies</span></span>

<span data-ttu-id="98483-125">数据加密策略 (DEP) 定义加密层次结构。</span><span class="sxs-lookup"><span data-stu-id="98483-125">A data encryption policy (DEP) defines the encryption hierarchy.</span></span> <span data-ttu-id="98483-126">该服务使用此层次结构，使用你管理的每个密钥和受 Microsoft 保护的可用性密钥加密数据。</span><span class="sxs-lookup"><span data-stu-id="98483-126">This hierarchy is used by the service to encrypt data using each of the keys you manage and the availability key that's protected by Microsoft.</span></span> <span data-ttu-id="98483-127">使用 PowerShell cmdlet 创建 DEP，然后分配这些 DESP 以加密应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="98483-127">You create DEPs using PowerShell cmdlets, and then assign those DEPs to encrypt application data.</span></span> <span data-ttu-id="98483-128">客户密钥支持三种类型的 MICROSOFT 365，每种策略类型使用不同的 cmdlet，并提供不同类型的数据的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="98483-128">There are three types of DEPs supported by Microsoft 365 Customer Key, each policy type uses different cmdlets and provides coverage for a different type of data.</span></span> <span data-ttu-id="98483-129">你可以定义的 DESP 包括：</span><span class="sxs-lookup"><span data-stu-id="98483-129">The DEPs you can define include:</span></span>

<span data-ttu-id="98483-130">**用于多个 Microsoft 365 工作负荷的 DEP** 这些 DEP 可跨租户内所有用户的多个 M365 工作负载加密数据。</span><span class="sxs-lookup"><span data-stu-id="98483-130">**DEP for multiple Microsoft 365 workloads** These DEPs encrypt data across multiple M365 workloads for all users within the tenant.</span></span> <span data-ttu-id="98483-131">这些工作负载包括：</span><span class="sxs-lookup"><span data-stu-id="98483-131">These workloads include:</span></span>

- <span data-ttu-id="98483-132">Teams一 (聊天、群聊、会议聊天和频道对话时显示聊天) </span><span class="sxs-lookup"><span data-stu-id="98483-132">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="98483-133">Teams媒体消息 (图像、代码段、视频消息、音频消息、wiki 图像) </span><span class="sxs-lookup"><span data-stu-id="98483-133">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="98483-134">Teams存储中存储的呼叫和Teams录制</span><span class="sxs-lookup"><span data-stu-id="98483-134">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="98483-135">Teams聊天通知</span><span class="sxs-lookup"><span data-stu-id="98483-135">Teams chat notifications</span></span>
- <span data-ttu-id="98483-136">Teams聊天建议Cortana</span><span class="sxs-lookup"><span data-stu-id="98483-136">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="98483-137">Teams状态消息</span><span class="sxs-lookup"><span data-stu-id="98483-137">Teams status messages</span></span>
- <span data-ttu-id="98483-138">用户和信号Exchange Online</span><span class="sxs-lookup"><span data-stu-id="98483-138">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="98483-139">Exchange Online未通过邮箱 DEP 加密的邮箱</span><span class="sxs-lookup"><span data-stu-id="98483-139">Exchange Online mailboxes that aren't already encrypted by mailbox DEPs</span></span>
- <span data-ttu-id="98483-140">Microsoft 信息保护：</span><span class="sxs-lookup"><span data-stu-id="98483-140">Microsoft Information Protection:</span></span>

  - <span data-ttu-id="98483-141">EDM (数据) 精确匹配，包括数据文件架构、规则包和用于对敏感数据进行哈希运算的量。</span><span class="sxs-lookup"><span data-stu-id="98483-141">Exact data match (EDM) data, including data file schemas, rule packages, and the salts used to hash the sensitive data.</span></span> <span data-ttu-id="98483-142">对于 EDM Microsoft Teams，多工作负载 DEP 会从将 DEP 分配给租户时对新数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="98483-142">For EDM and Microsoft Teams, the multi-workload DEP encrypts new data from the time you assign the DEP to the tenant.</span></span> <span data-ttu-id="98483-143">例如Exchange Online，客户密钥会加密所有现有和新数据。</span><span class="sxs-lookup"><span data-stu-id="98483-143">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

  - <span data-ttu-id="98483-144">敏感度标签的标签配置</span><span class="sxs-lookup"><span data-stu-id="98483-144">Label configuration for sensitivity labels</span></span>

<span data-ttu-id="98483-145">多工作负荷 DEP 不加密以下类型的数据。</span><span class="sxs-lookup"><span data-stu-id="98483-145">Multi-workload DEPs don't encrypt the following types of data.</span></span> <span data-ttu-id="98483-146">相反，Microsoft 365使用其他类型的加密来保护此数据。</span><span class="sxs-lookup"><span data-stu-id="98483-146">Instead, Microsoft 365 uses other types of encryption to protect this data.</span></span>

- <span data-ttu-id="98483-147">SharePoint和OneDrive for Business数据。</span><span class="sxs-lookup"><span data-stu-id="98483-147">SharePoint and OneDrive for Business data.</span></span>
- <span data-ttu-id="98483-148">Microsoft Teams保存在 OneDrive for Business 和 SharePoint Online 中的Teams和一些呼叫和会议录像SharePoint联机 DEP 进行加密。</span><span class="sxs-lookup"><span data-stu-id="98483-148">Microsoft Teams files and some Teams call and meeting recordings saved in OneDrive for Business and SharePoint Online are encrypted using the SharePoint Online DEP.</span></span>
- <span data-ttu-id="98483-149">其他Microsoft 365客户密钥Yammer支持的其他工作负载，例如 Yammer 和 Planner。</span><span class="sxs-lookup"><span data-stu-id="98483-149">Other Microsoft 365 workloads such as Yammer and Planner that aren't currently supported by Customer Key.</span></span>
- <span data-ttu-id="98483-150">Teams实时事件数据。</span><span class="sxs-lookup"><span data-stu-id="98483-150">Teams Live Event data.</span></span>

<span data-ttu-id="98483-151">可以为每个租户创建多个 DEP，但一次只能分配一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-151">You can create multiple DEPs per tenant but only assign one DEP at a time.</span></span> <span data-ttu-id="98483-152">分配 DEP 时，加密将自动开始，但需要一段时间才能完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="98483-152">When you assign the DEP, encryption begins automatically but takes some time to complete depending on the size of your tenant.</span></span>

<span data-ttu-id="98483-153">**用于邮箱Exchange Online的 DEP** 邮箱 DEP 可更精确地控制邮箱内Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="98483-153">**DEPs for Exchange Online mailboxes** Mailbox DEPs provide more precise control over individual mailboxes within Exchange Online.</span></span> <span data-ttu-id="98483-154">使用邮箱 DEP 加密存储在不同类型的 EXO 邮箱（如 UserMailbox、MailUser、Group、PublicFolder 和 Shared 邮箱）中的数据。</span><span class="sxs-lookup"><span data-stu-id="98483-154">Use mailbox DEPs to encrypt data stored in EXO mailboxes of different types such as UserMailbox, MailUser, Group, PublicFolder, and Shared mailboxes.</span></span> <span data-ttu-id="98483-155">每个租户最多可以有 50 个活动 DECP，并将这些 DESP 分配给各个邮箱。</span><span class="sxs-lookup"><span data-stu-id="98483-155">You can have up to 50 active DEPs per tenant and assign those DEPs to individual mailboxes.</span></span> <span data-ttu-id="98483-156">可以将一个 DEP 分配给多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="98483-156">You can assign one DEP to multiple mailboxes.</span></span>

<span data-ttu-id="98483-157">默认情况下，使用 Microsoft 管理的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="98483-157">By default your mailboxes get encrypted using Microsoft-managed keys.</span></span> <span data-ttu-id="98483-158">将客户密钥 DEP 分配给邮箱时：</span><span class="sxs-lookup"><span data-stu-id="98483-158">When you assign a Customer Key DEP to a mailbox:</span></span>

- <span data-ttu-id="98483-159">如果邮箱是使用多工作负荷 DEP 加密的，则只要用户或系统操作访问邮箱数据，该服务就使用新邮箱 DEP 来重新包装邮箱。</span><span class="sxs-lookup"><span data-stu-id="98483-159">If the mailbox is encrypted using a multi-workload DEP, the service rewraps the mailbox using the new mailbox DEP as long as a user or a system operation accesses the mailbox data.</span></span>

- <span data-ttu-id="98483-160">如果邮箱已使用 Microsoft 托管的密钥加密，则只要用户或系统操作访问邮箱数据，该服务就使用新邮箱 DEP 重新包装邮箱。</span><span class="sxs-lookup"><span data-stu-id="98483-160">If the mailbox is already encrypted using Microsoft-managed keys, the service rewraps the mailbox using the new mailbox DEP as long as a user or a system operation accesses the mailbox data.</span></span>

- <span data-ttu-id="98483-161">如果邮箱尚未使用默认加密进行加密，则服务将邮箱标记为移动。</span><span class="sxs-lookup"><span data-stu-id="98483-161">If the mailbox is not yet encrypted using default encryption, then the service marks the mailbox for a move.</span></span> <span data-ttu-id="98483-162">移动完成后，将进行加密。</span><span class="sxs-lookup"><span data-stu-id="98483-162">The encryption takes place once the move is complete.</span></span> <span data-ttu-id="98483-163">邮箱移动根据针对所有邮箱设置的优先级Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="98483-163">Mailbox moves are governed based on priorities set for all of Microsoft 365.</span></span> <span data-ttu-id="98483-164">有关详细信息，请参阅移动服务中的Microsoft 365[请求](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。</span><span class="sxs-lookup"><span data-stu-id="98483-164">For more information, see, [Move requests in the Microsoft 365 service](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).</span></span> <span data-ttu-id="98483-165">如果邮箱未在指定的时间内加密，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="98483-165">If the mailboxes aren't encrypted within the specified time, contact Microsoft.</span></span>

<span data-ttu-id="98483-166">稍后，您可以刷新 DEP 或为邮箱分配不同的 DEP，如管理客户密钥[for Office 365](customer-key-manage.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="98483-166">Later, you can either refresh the DEP or assign a different DEP to the mailbox as described in [Manage Customer Key for Office 365](customer-key-manage.md).</span></span> <span data-ttu-id="98483-167">每个邮箱必须具有适当的许可证，以分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-167">Each mailbox must have appropriate licenses to be assigned a DEP.</span></span> <span data-ttu-id="98483-168">有关许可详细信息，请参阅 [设置客户密钥之前](customer-key-set-up.md#before-you-set-up-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="98483-168">For more information about licensing, see [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).</span></span>

<span data-ttu-id="98483-169">对于符合用户邮箱的许可要求的租户，MICROSOFT 365共享邮箱、公用文件夹邮箱和组邮箱分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-169">DEPs can be assigned to a shared mailbox, public folder mailbox, and Microsoft 365 group mailbox for tenants that meet the licensing requirement for user mailboxes.</span></span> <span data-ttu-id="98483-170">对于非用户特定邮箱，不需要单独的许可证来分配客户密钥 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-170">You don't need separate licenses for non-user-specific mailboxes to assign Customer Key DEP.</span></span>

<span data-ttu-id="98483-171">对于分配给单个邮箱的客户密钥 DEP，可以请求 Microsoft 在离开服务时清除特定 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-171">For Customer Key DEPs that you assign to individual mailboxes, you can request that Microsoft purge specific DEPs when you leave the service.</span></span> <span data-ttu-id="98483-172">有关数据清除过程和密钥吊销的信息，请参阅 [撤销密钥并开始数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="98483-172">For information about the data purge process and key revocation, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

<span data-ttu-id="98483-173">在离开服务时撤销对密钥的访问权限时，可用性密钥将被删除，从而导致数据的加密删除。</span><span class="sxs-lookup"><span data-stu-id="98483-173">When you revoke access to your keys as part of leaving the service, the availability key is deleted, resulting in cryptographic deletion of your data.</span></span> <span data-ttu-id="98483-174">加密删除可以减少数据重新管理的风险，这一点对于履行安全和合规义务非常重要。</span><span class="sxs-lookup"><span data-stu-id="98483-174">Cryptographic deletion mitigates the risk of data remanence, which is important for meeting both security and compliance obligations.</span></span>

<span data-ttu-id="98483-175">**适用于 SharePoint Online 和 OneDrive for Business 的 DEP** 此 DEP 用于加密存储在 SPO 和 OneDrive for Business 中的内容，Microsoft Teams存储在 SPO 中的文件。</span><span class="sxs-lookup"><span data-stu-id="98483-175">**DEP for SharePoint Online and OneDrive for Business** This DEP is used to encrypt content stored in SPO and OneDrive for Business, including Microsoft Teams files stored in SPO.</span></span> <span data-ttu-id="98483-176">如果你使用的是多地理位置功能，你可以为组织为每个地理位置创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-176">If you're using the multi-geo feature, you can create one DEP per geo for your organization.</span></span> <span data-ttu-id="98483-177">如果未使用多地理位置功能，则只能为每个租户创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="98483-177">If you're not using the multi-geo feature, you can only create one DEP per tenant.</span></span> <span data-ttu-id="98483-178">请参阅设置客户 [密钥中的详细信息](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="98483-178">Refer to the details in [Set up Customer Key](customer-key-set-up.md).</span></span>

### <a name="encryption-ciphers-used-by-customer-key"></a><span data-ttu-id="98483-179">客户密钥使用的加密密码</span><span class="sxs-lookup"><span data-stu-id="98483-179">Encryption ciphers used by Customer Key</span></span>

<span data-ttu-id="98483-180">客户密钥使用各种加密密码来加密密钥，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="98483-180">Customer Key uses various encryption ciphers to encrypt keys as shown in the following figures.</span></span>

<span data-ttu-id="98483-181">用于加密多个 Microsoft 365 工作负荷数据的 DEP 的关键层次结构与用于单个邮箱的 DEP 的Exchange Online层次结构。</span><span class="sxs-lookup"><span data-stu-id="98483-181">The key hierarchy used for DEPs that encrypt data for multiple Microsoft 365 workloads is similar to the hierarchy used for DEPs for individual Exchange Online mailboxes.</span></span> <span data-ttu-id="98483-182">唯一的区别是，邮箱密钥将替换为相应的Microsoft 365工作负荷密钥。</span><span class="sxs-lookup"><span data-stu-id="98483-182">The only difference is that the Mailbox Key is replaced with the corresponding Microsoft 365 Workload Key.</span></span>

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="98483-183">加密密码，用于加密Exchange Online和Skype for Business</span><span class="sxs-lookup"><span data-stu-id="98483-183">Encryption ciphers used to encrypt keys for Exchange Online and Skype for Business</span></span>

![客户密钥Exchange Online加密密码](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="98483-185">加密密码，用于加密 SharePoint Online、OneDrive for Business和Teams密钥</span><span class="sxs-lookup"><span data-stu-id="98483-185">Encryption ciphers used to encrypt keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

![SharePoint Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a><span data-ttu-id="98483-187">相关文章</span><span class="sxs-lookup"><span data-stu-id="98483-187">Related articles</span></span>

- [<span data-ttu-id="98483-188">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="98483-188">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="98483-189">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="98483-189">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="98483-190">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="98483-190">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="98483-191">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="98483-191">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="98483-192">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="98483-192">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="98483-193">服务加密</span><span class="sxs-lookup"><span data-stu-id="98483-193">Service Encryption</span></span>](office-365-service-encryption.md)