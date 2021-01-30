---
title: 使用客户密钥执行服务加密
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: 本文将介绍服务加密如何与 Microsoft 365 中的客户密钥一起工作。
ms.openlocfilehash: efb2ba9c2532973a096c509b57639544fc2ddbe5
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058485"
---
# <a name="service-encryption-with-customer-key"></a><span data-ttu-id="c1a3c-103">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="c1a3c-103">Service encryption with Customer Key</span></span>

<span data-ttu-id="c1a3c-104">Microsoft 365 提供通过 BitLocker 和分布式密钥管理器和 DKM (启用的基线) 。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-104">Microsoft 365 provides baseline, volume-level encryption enabled through BitLocker and Distributed Key Manager (DKM).</span></span> <span data-ttu-id="c1a3c-105">Microsoft 365 在内容的应用程序层添加了一层加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-105">Microsoft 365 offers an added layer of encryption at the application layer for your content.</span></span> <span data-ttu-id="c1a3c-106">此内容包括来自 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件的数据。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-106">This content includes data from Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="c1a3c-107">此添加的加密层称为服务加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-107">This added layer of encryption is called service encryption.</span></span>

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a><span data-ttu-id="c1a3c-108">服务加密、BitLocker 和客户密钥如何协同工作</span><span class="sxs-lookup"><span data-stu-id="c1a3c-108">How service encryption, BitLocker, and Customer Key work together</span></span>

<span data-ttu-id="c1a3c-109">服务加密可确保静态内容在服务层加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-109">Service encryption ensures that content at rest is encrypted at the service layer.</span></span> <span data-ttu-id="c1a3c-110">**你的数据在 Microsoft 365** 服务中始终使用 BitLocker 和 DKM 进行其余加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-110">**Your data is always encrypted at rest in the Microsoft 365 service with BitLocker and DKM**.</span></span> <span data-ttu-id="c1a3c-111">有关详细信息，请参阅"安全、隐私和合规性信息"以及 Exchange Online 如何 [保护电子邮件密码](exchange-online-secures-email-secrets.md)。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-111">For more information, see the "Security, Privacy, and Compliance Information", and [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md).</span></span> <span data-ttu-id="c1a3c-112">客户密钥提供了防止未经授权的系统或人员查看数据的额外保护，并补充了 Microsoft 数据中心中的 BitLocker 磁盘加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-112">Customer Key provides additional protection against viewing of data by unauthorized systems or personnel, and complements BitLocker disk encryption in Microsoft datacenters.</span></span> <span data-ttu-id="c1a3c-113">服务加密不应阻止 Microsoft 人员访问客户数据。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-113">Service encryption is not meant to prevent Microsoft personnel from accessing customer data.</span></span> <span data-ttu-id="c1a3c-114">主要目的是帮助客户履行控制根密钥的法规或合规性义务。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-114">The primary purpose is to assist customers in meeting regulatory or compliance obligations for controlling root keys.</span></span> <span data-ttu-id="c1a3c-115">客户明确授权 O365 服务使用其加密密钥来提供增值云服务，如电子数据展示、反恶意软件、反垃圾邮件、搜索索引等。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-115">Customers explicitly authorize O365 services to use their encryption keys to provide value added cloud services, such as eDiscovery, anti-malware, anti-spam, search indexing, etc.</span></span>

<span data-ttu-id="c1a3c-116">客户密钥基于服务加密构建，可让你提供和控制加密密钥。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-116">Customer Key is built on service encryption and lets you provide and control encryption keys.</span></span> <span data-ttu-id="c1a3c-117">然后，Microsoft 365 使用这些密钥加密你的其余数据，如联机服务条款[ (OST) 。 ](https://www.microsoft.com/licensing/product-licensing/products.aspx)</span><span class="sxs-lookup"><span data-stu-id="c1a3c-117">Microsoft 365 then uses these keys to encrypt your data at rest as described in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx).</span></span> <span data-ttu-id="c1a3c-118">客户密钥有助于你履行合规性义务，因为你控制 Microsoft 365 用于加密和解密数据的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-118">Customer Key helps you meet compliance obligations because you control the encryption keys that Microsoft 365 uses to encrypt and decrypt data.</span></span>
  
<span data-ttu-id="c1a3c-119">客户密钥增强了组织满足合规性要求的能力，这些要求指定了与云服务提供商的关键安排。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-119">Customer Key enhances the ability of your organization to meet the demands of compliance requirements that specify key arrangements with the cloud service provider.</span></span> <span data-ttu-id="c1a3c-120">使用客户密钥，您可以在应用程序级别提供和控制 Microsoft 365 静态数据的根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-120">With Customer Key, you provide and control the root encryption keys for your Microsoft 365 data at-rest at the application level.</span></span> <span data-ttu-id="c1a3c-121">因此，你可以对组织的密钥进行控制。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-121">As a result, you exercise control over your organization's keys.</span></span> <span data-ttu-id="c1a3c-122">如果决定退出该服务，则撤消对组织的根密钥的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-122">If you decide to exit the service, you revoke access to your organization's root keys.</span></span> <span data-ttu-id="c1a3c-123">对于所有 Microsoft 365 服务，撤销对密钥的访问是数据删除路径的第一步。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-123">For all Microsoft 365 services, revoking access to the keys is the first step on the path towards data deletion.</span></span> <span data-ttu-id="c1a3c-124">通过撤销对密钥的访问，数据对服务不可读。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-124">By revoking access to the keys, the data is unreadable to the service.</span></span>

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a><span data-ttu-id="c1a3c-125">客户密钥对 Office 365 中的其余数据进行加密</span><span class="sxs-lookup"><span data-stu-id="c1a3c-125">Customer Key encrypts data at rest in Office 365</span></span>

<span data-ttu-id="c1a3c-126">使用你提供的密钥，客户密钥进行加密：</span><span class="sxs-lookup"><span data-stu-id="c1a3c-126">Using keys you provide, Customer Key encrypts:</span></span>

- <span data-ttu-id="c1a3c-127">SharePoint Online、OneDrive for Business 和 Teams 文件。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-127">SharePoint Online, OneDrive for Business, and Teams files.</span></span>
- <span data-ttu-id="c1a3c-128">上传到 OneDrive for Business 的文件。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-128">Files uploaded to OneDrive for Business.</span></span>
- <span data-ttu-id="c1a3c-129">Exchange Online 邮箱内容，包括电子邮件正文内容、日历条目和电子邮件附件中的内容。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-129">Exchange Online mailbox content including e-mail body content, calendar entries, and the content within email attachments.</span></span>
- <span data-ttu-id="c1a3c-130">来自 Skype for Business 的文本对话。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-130">Text conversations from Skype for Business.</span></span>

<span data-ttu-id="c1a3c-131">我们当前不为客户提供对 Skype 会议直播和 Skype 会议内容上载加密密钥的控制。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-131">We don't currently offer customer control of the encryption keys for Skype Meeting Broadcast and Skype Meeting content uploads.</span></span> <span data-ttu-id="c1a3c-132">相反，此内容与 Office 365 中的所有其他内容一起加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-132">Instead, this content is encrypted along with all other content in Office 365.</span></span>

### <a name="customer-key-with-hybrid-deployments"></a><span data-ttu-id="c1a3c-133">混合部署的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c1a3c-133">Customer Key with hybrid deployments</span></span>

<span data-ttu-id="c1a3c-134">客户密钥仅加密云中的其余数据。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-134">Customer Key only encrypts data at rest in the cloud.</span></span> <span data-ttu-id="c1a3c-135">客户密钥无法保护本地邮箱和文件。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-135">Customer Key does not work to protect your on-premises mailboxes and files.</span></span> <span data-ttu-id="c1a3c-136">可以使用另一种方法（如 BitLocker）加密本地数据。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-136">You can encrypt your on-premises data using another method, such as BitLocker.</span></span>

## <a name="about-the-data-encryption-policy-dep"></a><span data-ttu-id="c1a3c-137">关于 DEP 策略 (策略) </span><span class="sxs-lookup"><span data-stu-id="c1a3c-137">About the data encryption policy (DEP)</span></span>

<span data-ttu-id="c1a3c-138">数据加密策略定义加密层次结构，以使用你提供的每个密钥以及受 Microsoft 保护的可用性密钥加密数据。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-138">A data encryption policy defines the encryption hierarchy to encrypt data using each of the keys you provide as well as the availability key protected by Microsoft.</span></span> <span data-ttu-id="c1a3c-139">使用 PowerShell cmdlet 创建 DEPS（每个服务有所不同），并分配这些 DEPS 以加密应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-139">You create DEPs using PowerShell cmdlets, which are different for each service, and assign those DEPs to encrypt application data.</span></span> <span data-ttu-id="c1a3c-140">例如：</span><span class="sxs-lookup"><span data-stu-id="c1a3c-140">For example:</span></span>

<span data-ttu-id="c1a3c-141">**Exchange Online 和 Skype for Business** 每个租户可以创建最多 50 个 DEPS。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-141">**Exchange Online and Skype for Business** You can create up to 50 DEPs per tenant.</span></span> <span data-ttu-id="c1a3c-142">将 DEPS 关联到 Azure 密钥保管库中的客户密钥，然后将 DEPs 分配给各个邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-142">You associate DEPs to your Customer Keys in Azure Key Vault and then assign DEPs to individual mailboxes.</span></span> <span data-ttu-id="c1a3c-143">将 DEP 分配给邮箱时：</span><span class="sxs-lookup"><span data-stu-id="c1a3c-143">When you assign a DEP to a mailbox:</span></span>

- <span data-ttu-id="c1a3c-144">邮箱被标记为进行邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-144">the mailbox is marked for a mailbox move.</span></span> <span data-ttu-id="c1a3c-145">根据 Microsoft 365 中优先级，如此处所述 [，移动 Microsoft 365 服务中的请求](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-145">Based on priorities in Microsoft 365 as described here [Move requests in the Microsoft 365 service](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).</span></span>

- <span data-ttu-id="c1a3c-146">邮箱移动时进行加密。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-146">The encryption takes place while the mailbox is moved.</span></span> <span data-ttu-id="c1a3c-147">允许使用新的 DEP 加密邮箱 72 小时。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-147">Allow 72 hours for the mailbox to become encrypted with the new DEP.</span></span> <span data-ttu-id="c1a3c-148">如果在分配 DEP 后等待 72 小时后邮箱未加密，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-148">If the mailboxes aren't encrypted after waiting 72 hours from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="c1a3c-149">稍后，您可以刷新 DEP 或为邮箱分配不同的 DEP，如管理 [Office 365](customer-key-manage.md)的客户密钥中所述。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-149">Later, you can either refresh the DEP or assign a different DEP to the mailbox as described in [Manage Customer Key for Office 365](customer-key-manage.md).</span></span> <span data-ttu-id="c1a3c-150">每个邮箱必须具有适当的许可证才能分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-150">Each mailbox must have appropriate licenses in order to assign a DEP.</span></span> <span data-ttu-id="c1a3c-151">有关许可详细信息，请参阅设置 [客户密钥之前](customer-key-set-up.md#before-you-set-up-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-151">For more information about licensing, see [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).</span></span>

> [!NOTE]
> <span data-ttu-id="c1a3c-152">DEP 可以应用于满足用户邮箱许可要求的租户的共享邮箱、公用文件夹邮箱和 Microsoft 365 组邮箱，即使其中某些邮箱类型不能是分配的许可证 (公用文件夹邮箱和 Microsoft 365 组邮箱) 或需要用于增加存储 (共享邮箱) 的许可证。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-152">The DEP can be applied to a shared mailbox, public folder mailbox, and Microsoft 365 group mailbox for tenants that meet the licensing requirement for user mailboxes, even though some of these mailbox types cannot be an assigned license (public folder mailbox and Microsoft 365 group mailbox) or need a license for increasing storage (shared mailbox).</span></span>

<span data-ttu-id="c1a3c-153">**SharePoint Online、OneDrive for Business 和 Teams 文件** 如果使用的是多地理位置功能，则每个地理位置最多为组织创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-153">**SharePoint Online, OneDrive for Business, and Teams files** If you're using the multi-geo feature, you can create up to one DEP per geo for your organization.</span></span> <span data-ttu-id="c1a3c-154">可以针对每个地理位置使用不同的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-154">You can use different Customer Keys for each geo.</span></span> <span data-ttu-id="c1a3c-155">如果未使用多地理位置功能，则只能为每个租户创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-155">If you're not using the multi-geo feature, you can only create one DEP per tenant.</span></span> <span data-ttu-id="c1a3c-156">分配 DEP 时，加密将自动开始，但可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-156">When you assign the DEP, encryption begins automatically but can take some time to complete.</span></span> <span data-ttu-id="c1a3c-157">请参阅"设置 [客户密钥"中的详细信息](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-157">Refer to the details in [Set up Customer Key](customer-key-set-up.md).</span></span>

## <a name="leaving-the-service"></a><span data-ttu-id="c1a3c-158">离开服务</span><span class="sxs-lookup"><span data-stu-id="c1a3c-158">Leaving the service</span></span>

<span data-ttu-id="c1a3c-159">客户密钥通过允许您在离开 Microsoft 365 服务时吊销密钥来帮助你履行合规性义务。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-159">Customer Key assists you in meeting compliance obligations by allowing you to revoke your keys when you leave the Microsoft 365 service.</span></span> <span data-ttu-id="c1a3c-160">在离开服务时吊销密钥时，可用性密钥将被删除，从而导致数据的加密删除。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-160">When you revoke your keys as part of leaving the service, the availability key is deleted resulting in cryptographic deletion of your data.</span></span> <span data-ttu-id="c1a3c-161">加密删除可以减少数据保留的风险，这一风险对于满足安全性和合规性义务都非常重要。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-161">Cryptographic deletion mitigates the risk of data remanence which is important for meeting both security and compliance obligations.</span></span> <span data-ttu-id="c1a3c-162">有关数据清除过程和密钥吊销的信息，请参阅" [撤销密钥"并启动数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-162">For information about the data purge process and key revocation, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

### <a name="encryption-ciphers-used-by-customer-key"></a><span data-ttu-id="c1a3c-163">客户密钥使用的加密密码</span><span class="sxs-lookup"><span data-stu-id="c1a3c-163">Encryption ciphers used by Customer Key</span></span>

<span data-ttu-id="c1a3c-164">客户密钥使用各种加密密码来加密密钥，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="c1a3c-164">Customer Key uses a variety of encryption ciphers to encrypt keys as shown in the following figures.</span></span>

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="c1a3c-165">用于加密 Exchange Online 和 Skype for Business 的密钥的加密密码</span><span class="sxs-lookup"><span data-stu-id="c1a3c-165">Encryption ciphers used to encrypt keys for Exchange Online and Skype for Business</span></span>

![Exchange Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c1a3c-167">用于加密 SharePoint Online、OneDrive for Business 和 Teams 文件的密钥的加密密码</span><span class="sxs-lookup"><span data-stu-id="c1a3c-167">Encryption ciphers used to encrypt keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

![SharePoint Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a><span data-ttu-id="c1a3c-169">相关文章</span><span class="sxs-lookup"><span data-stu-id="c1a3c-169">Related articles</span></span>

- [<span data-ttu-id="c1a3c-170">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="c1a3c-170">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c1a3c-171">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="c1a3c-171">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c1a3c-172">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c1a3c-172">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c1a3c-173">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c1a3c-173">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="c1a3c-174">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="c1a3c-174">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="c1a3c-175">服务加密</span><span class="sxs-lookup"><span data-stu-id="c1a3c-175">Service Encryption</span></span>](office-365-service-encryption.md)
