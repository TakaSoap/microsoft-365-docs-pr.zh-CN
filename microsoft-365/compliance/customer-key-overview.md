---
title: Office 365 中的客户密钥的服务加密
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
description: 使用 "客户密钥"，可以控制组织的加密密钥，然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。
ms.openlocfilehash: df47f0df0f30de3529982099cb59efe2a741cd34
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "43029868"
---
# <a name="service-encryption-with-customer-key-in-office-365"></a><span data-ttu-id="ff6c7-103">Office 365 中的客户密钥的服务加密</span><span class="sxs-lookup"><span data-stu-id="ff6c7-103">Service encryption with Customer Key in Office 365</span></span>

<span data-ttu-id="ff6c7-104">Office 365 提供了通过 BitLocker 和分布式密钥管理器（DKM）启用的基准、卷级加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-104">Office 365 provides baseline, volume-level encryption enabled through BitLocker and Distributed Key Manager (DKM).</span></span> <span data-ttu-id="ff6c7-105">Office 365 在应用程序级别为你的内容提供了额外的加密层。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-105">Office 365 offers an added layer of encryption at the application level for your content.</span></span> <span data-ttu-id="ff6c7-106">此内容包含来自 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件的数据。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-106">This content includes data from Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="ff6c7-107">这一添加的加密层称为 "服务加密"。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-107">This added layer of encryption is called service encryption.</span></span>

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a><span data-ttu-id="ff6c7-108">服务加密、BitLocker 和客户密钥如何协同工作</span><span class="sxs-lookup"><span data-stu-id="ff6c7-108">How service encryption, BitLocker, and Customer Key work together</span></span>

<span data-ttu-id="ff6c7-109">服务加密可确保在应用程序层对 rest 上的内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-109">Service encryption ensures that content at rest is encrypted at the application layer.</span></span> <span data-ttu-id="ff6c7-110">**Office 365 服务中的静态数据始终在 BitLocker 和 DKM 中进行加密**。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-110">**Your data is always encrypted at rest in the Office 365 service with BitLocker and DKM**.</span></span> <span data-ttu-id="ff6c7-111">有关详细信息，请参阅 "Office 365 的安全性、隐私和合规性信息"，以及[Exchange Online 如何保护您的电子邮件密码](exchange-online-secures-email-secrets.md)。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-111">For more information, see the "Security, Privacy, and Compliance Information for Office 365", and [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md).</span></span> <span data-ttu-id="ff6c7-112">客户密钥可提供其他保护，以防止未经授权的系统或人员查看数据，并补充 Microsoft 数据中心中的 BitLocker 磁盘加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-112">Customer Key provides additional protection against viewing of data by unauthorized systems or personnel, and complements BitLocker disk encryption in Microsoft datacenters.</span></span> <span data-ttu-id="ff6c7-113">服务加密并不意味着阻止 Microsoft 人员访问客户数据。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-113">Service encryption is not meant to prevent Microsoft personnel from accessing customer data.</span></span> <span data-ttu-id="ff6c7-114">主要目的是帮助客户满足控制根键的管理法规或合规性义务。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-114">The primary purpose is to assist customers in meeting regulatory or compliance obligations for controlling root keys.</span></span> <span data-ttu-id="ff6c7-115">客户显式授权 O365 服务使用其加密密钥来提供增值云服务，如电子数据展示、反恶意软件、反垃圾邮件、搜索索引等。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-115">Customers explicitly authorize O365 services to use their encryption keys to provide value added cloud services, such as eDiscovery, anti-malware, anti-spam, search indexing, etc.</span></span>

<span data-ttu-id="ff6c7-116">客户密钥是基于服务加密构建的，允许你提供和控制加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-116">Customer Key is built on service encryption and lets you provide and control encryption keys.</span></span> <span data-ttu-id="ff6c7-117">然后，Office 365 将使用这些密钥来加密 rest 上的数据，如[联机服务条款（OST）](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-117">Office 365 then uses these keys to encrypt your data at rest as described in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx).</span></span> <span data-ttu-id="ff6c7-118">客户密钥可帮助您满足合规性义务，因为您控制 Office 365 用于加密和解密数据的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-118">Customer Key helps you meet compliance obligations because you control the encryption keys that Office 365 uses to encrypt and decrypt data.</span></span>
  
<span data-ttu-id="ff6c7-119">客户密钥增强了贵组织满足符合性要求的能力，这些要求通过云服务提供商指定关键安排。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-119">Customer Key enhances the ability of your organization to meet the demands of compliance requirements that specify key arrangements with the cloud service provider.</span></span> <span data-ttu-id="ff6c7-120">使用 "客户密钥"，可以在应用程序级别为 Office 365 数据提供和控制根加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-120">With Customer Key, you provide and control the root encryption keys for your Office 365 data at-rest at the application level.</span></span> <span data-ttu-id="ff6c7-121">因此，您可以控制组织的键。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-121">As a result, you exercise control over your organization's keys.</span></span> <span data-ttu-id="ff6c7-122">如果决定退出该服务，请撤消对您的组织的根密钥的访问。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-122">If you decide to exit the service, you revoke access to your organization's root keys.</span></span> <span data-ttu-id="ff6c7-123">对于所有 Office 365 服务，吊销密钥的访问权限是路径中的第一步，用于数据删除。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-123">For all Office 365 services, revoking access to the keys is the first step on the path towards data deletion.</span></span> <span data-ttu-id="ff6c7-124">通过撤销对密钥的访问权限，该服务无法读取数据。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-124">By revoking access to the keys, the data is unreadable to the service.</span></span>

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a><span data-ttu-id="ff6c7-125">客户密钥在 Office 365 中对静态数据进行加密</span><span class="sxs-lookup"><span data-stu-id="ff6c7-125">Customer Key encrypts data at rest in Office 365</span></span>

<span data-ttu-id="ff6c7-126">使用您提供的密钥，Office 365 的客户密钥加密：</span><span class="sxs-lookup"><span data-stu-id="ff6c7-126">Using keys you provide, Customer Key for Office 365 encrypts:</span></span>

- <span data-ttu-id="ff6c7-127">SharePoint Online、OneDrive for Business 和团队文件。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-127">SharePoint Online, OneDrive for Business, and Teams files.</span></span>
- <span data-ttu-id="ff6c7-128">上载到 OneDrive for business 的文件。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-128">Files uploaded to OneDrive for Business.</span></span>
- <span data-ttu-id="ff6c7-129">Exchange Online 邮箱内容，包括电子邮件正文内容、日历条目和电子邮件附件中的内容。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-129">Exchange Online mailbox content including e-mail body content, calendar entries, and the content within email attachments.</span></span>
- <span data-ttu-id="ff6c7-130">Skype for Business 中的文本对话。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-130">Text conversations from Skype for Business.</span></span>

<span data-ttu-id="ff6c7-131">目前，我们并不提供对 Skype 会议直播和 Skype 会议内容上载的加密密钥的客户控制。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-131">We don't currently offer customer control of the encryption keys for Skype Meeting Broadcast and Skype Meeting content uploads.</span></span> <span data-ttu-id="ff6c7-132">而是将此内容与 Office 365 中的其他所有内容一起加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-132">Instead, this content is encrypted along with all other content in Office 365.</span></span>

### <a name="customer-key-with-hybrid-deployments"></a><span data-ttu-id="ff6c7-133">包含混合部署的客户密钥</span><span class="sxs-lookup"><span data-stu-id="ff6c7-133">Customer Key with hybrid deployments</span></span>

<span data-ttu-id="ff6c7-134">客户密钥仅对云中的静态数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-134">Customer Key only encrypts data at rest in the cloud.</span></span> <span data-ttu-id="ff6c7-135">客户密钥不能保护您的内部部署邮箱和文件。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-135">Customer Key does not work to protect your on-premises mailboxes and files.</span></span> <span data-ttu-id="ff6c7-136">您可以使用其他方法（例如 BitLocker）对本地数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-136">You can encrypt your on-premises data using another method, such as BitLocker.</span></span>

## <a name="about-the-data-encryption-policy-dep"></a><span data-ttu-id="ff6c7-137">关于数据加密策略（DEP）</span><span class="sxs-lookup"><span data-stu-id="ff6c7-137">About the data encryption policy (DEP)</span></span>

<span data-ttu-id="ff6c7-138">数据加密策略定义加密层次结构，以使用您提供的每个密钥以及由 Microsoft 保护的可用性密钥来加密数据。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-138">A data encryption policy defines the encryption hierarchy to encrypt data using each of the keys you provide as well as the availability key protected by Microsoft.</span></span> <span data-ttu-id="ff6c7-139">您使用 PowerShell cmdlet 创建 DEPs，这些 cmdlet 因每个服务而异，并将这些 DEPs 分配给加密应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-139">You create DEPs using PowerShell cmdlets, which are different for each service, and assign those DEPs to encrypt application data.</span></span> <span data-ttu-id="ff6c7-140">例如：</span><span class="sxs-lookup"><span data-stu-id="ff6c7-140">For example:</span></span>

<span data-ttu-id="ff6c7-141">**Exchange Online 和 Skype For business**最高可为每个租户创建 50 DEPs。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-141">**Exchange Online and Skype for Business** You can create up to 50 DEPs per tenant.</span></span> <span data-ttu-id="ff6c7-142">将 DEPs 关联到 Azure Key Vault 中的客户密钥，然后将 DEPs 分配给各个邮箱。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-142">You associate DEPs to your Customer Keys in Azure Key Vault and then assign DEPs to individual mailboxes.</span></span> <span data-ttu-id="ff6c7-143">将 DEP 分配到邮箱时：</span><span class="sxs-lookup"><span data-stu-id="ff6c7-143">When you assign a DEP to a mailbox:</span></span>

- <span data-ttu-id="ff6c7-144">为邮箱移动标记邮箱。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-144">the mailbox is marked for a mailbox move.</span></span> <span data-ttu-id="ff6c7-145">根据此处在[office 365 服务中的移动请求中](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)所述的 office 365 中的优先级。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-145">Based on priorities in Office 365 as described here [Move requests in the Office 365 service](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).</span></span>

- <span data-ttu-id="ff6c7-146">移动邮箱时，会进行加密。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-146">The encryption takes place while the mailbox is moved.</span></span> <span data-ttu-id="ff6c7-147">允许使用新的 DEP 对邮箱进行加密，以72小时为单位。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-147">Allow 72 hours for the mailbox to become encrypted with the new DEP.</span></span> <span data-ttu-id="ff6c7-148">如果邮箱在你分配 DEP 之后等待72小时后未加密，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-148">If the mailboxes aren't encrypted after waiting 72 hours from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="ff6c7-149">稍后，您可以刷新 DEP 或根据 "[管理 Office 365 的客户密钥](customer-key-manage.md)" 中所述，为邮箱指定一个不同的 dep。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-149">Later, you can either refresh the DEP or assign a different DEP to the mailbox as described in [Manage Customer Key for Office 365](customer-key-manage.md).</span></span> <span data-ttu-id="ff6c7-150">每个邮箱必须具有适当的许可证，才能分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-150">Each mailbox must have appropriate licenses in order to assign a DEP.</span></span> <span data-ttu-id="ff6c7-151">有关许可的详细信息，请参阅[设置客户密钥之前](customer-key-set-up.md#before-you-set-up-customer-key)。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-151">For more information about licensing, see [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).</span></span>

<span data-ttu-id="ff6c7-152">**SharePoint Online、OneDrive For business 和团队文件**如果您使用的是多地理位置功能，则可以为您的组织为每个地理位置创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-152">**SharePoint Online, OneDrive for Business, and Teams files** If you're using the multi-geo feature, you can create up to one DEP per geo for your organization.</span></span> <span data-ttu-id="ff6c7-153">您可以为每个地理位置使用不同的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-153">You can use different Customer Keys for each geo.</span></span> <span data-ttu-id="ff6c7-154">如果不使用多地理位置功能，则只能为每个租户创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-154">If you're not using the multi-geo feature, you can only create one DEP per tenant.</span></span> <span data-ttu-id="ff6c7-155">分配 DEP 时，加密会自动开始，但可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-155">When you assign the DEP, encryption begins automatically but can take some time to complete.</span></span> <span data-ttu-id="ff6c7-156">请参阅[设置适用于 Office 365 的客户密钥](customer-key-set-up.md)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-156">Refer to the details in [Set up Customer Key for Office 365](customer-key-set-up.md).</span></span>

## <a name="leaving-the-service"></a><span data-ttu-id="ff6c7-157">离开服务</span><span class="sxs-lookup"><span data-stu-id="ff6c7-157">Leaving the service</span></span>

<span data-ttu-id="ff6c7-158">客户密钥允许你在离开 Office 365 服务时撤销你的密钥，从而帮助你满足合规性义务。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-158">Customer Key assists you in meeting compliance obligations by allowing you to revoke your keys when you leave the Office 365 service.</span></span> <span data-ttu-id="ff6c7-159">在退出服务的过程中吊销密钥时，将删除可用性密钥，从而导致加密删除了数据。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-159">When you revoke your keys as part of leaving the service, the availability key is deleted resulting in cryptographic deletion of your data.</span></span> <span data-ttu-id="ff6c7-160">加密删除降低了数据 remanence 的风险，这对于满足安全和合规性义务来说非常重要。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-160">Cryptographic deletion mitigates the risk of data remanence which is important for meeting both security and compliance obligations.</span></span> <span data-ttu-id="ff6c7-161">有关数据清除过程和密钥吊销的信息，请参阅[废除您的密钥并启动数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-161">For information about the data purge process and key revocation, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

### <a name="encryption-ciphers-used-by-customer-key"></a><span data-ttu-id="ff6c7-162">客户密钥使用的加密密码</span><span class="sxs-lookup"><span data-stu-id="ff6c7-162">Encryption ciphers used by Customer Key</span></span>

<span data-ttu-id="ff6c7-163">"客户密钥" 使用各种加密密码来加密密钥，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ff6c7-163">Customer Key uses a variety of encryption ciphers to encrypt keys as shown in the following figures.</span></span>

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="ff6c7-164">用于加密 Exchange Online 和 Skype for business 的密钥的加密密码</span><span class="sxs-lookup"><span data-stu-id="ff6c7-164">Encryption ciphers used to encrypt keys for Exchange Online and Skype for Business</span></span>

![Exchange Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="ff6c7-166">用于加密 SharePoint Online、OneDrive for Business 和团队文件的密钥的加密密码</span><span class="sxs-lookup"><span data-stu-id="ff6c7-166">Encryption ciphers used to encrypt keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

![SharePoint Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a><span data-ttu-id="ff6c7-168">相关文章</span><span class="sxs-lookup"><span data-stu-id="ff6c7-168">Related articles</span></span>

- [<span data-ttu-id="ff6c7-169">设置适用于 Office 的客户密钥365</span><span class="sxs-lookup"><span data-stu-id="ff6c7-169">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="ff6c7-170">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="ff6c7-170">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="ff6c7-171">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="ff6c7-171">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="ff6c7-172">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="ff6c7-172">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="ff6c7-173">Office 365 中的客户密码箱</span><span class="sxs-lookup"><span data-stu-id="ff6c7-173">Customer Lockbox in Office 365</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="ff6c7-174">Office 365 服务加密</span><span class="sxs-lookup"><span data-stu-id="ff6c7-174">Office 365 Service Encryption</span></span>](office-365-service-encryption.md)
