---
title: 双重密钥加密概述和 FAQ
description: 适用于 Microsoft 365 的双重密钥加密的常见问题。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 98c61e66155e21624e8ecba460ebc3041e72ada5
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277649"
---
# <a name="double-key-encryption-frequently-asked-questions"></a><span data-ttu-id="42e64-103">双重密钥加密常见问题</span><span class="sxs-lookup"><span data-stu-id="42e64-103">Double Key Encryption frequently asked questions</span></span>

<span data-ttu-id="42e64-104">有关于双密钥加密工作方式的问题？</span><span class="sxs-lookup"><span data-stu-id="42e64-104">Have a question about how Double Key Encryption works?</span></span> <span data-ttu-id="42e64-105">在此处查找答案。</span><span class="sxs-lookup"><span data-stu-id="42e64-105">Check for an answer here.</span></span>

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a><span data-ttu-id="42e64-106">Microsoft 365 (DKE) 的双重密钥加密是什么？</span><span class="sxs-lookup"><span data-stu-id="42e64-106">What is Double Key Encryption for Microsoft 365 (DKE)?</span></span>

<span data-ttu-id="42e64-107">Microsoft 365 的双重密钥加密使客户能够保护高度敏感的数据，以满足专门的要求。</span><span class="sxs-lookup"><span data-stu-id="42e64-107">Double Key Encryption for Microsoft 365 enables customers to protect their highly sensitive data to meet specialized requirements.</span></span> <span data-ttu-id="42e64-108">它可帮助客户维护对其加密密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="42e64-108">It helps customers maintain full control of their encryption keys.</span></span> <span data-ttu-id="42e64-109">它使用两个键来保护数据;您的控件中有一个密钥，另一个密钥在 Microsoft Azure 中安全存储。</span><span class="sxs-lookup"><span data-stu-id="42e64-109">It uses two keys to protect data; one key in your control and a second key stored securely in Microsoft Azure.</span></span> <span data-ttu-id="42e64-110">查看使用双重密钥加密保护的数据需要对这两个密钥的访问权限。</span><span class="sxs-lookup"><span data-stu-id="42e64-110">Viewing data protected with Double Key Encryption requires access to both keys.</span></span> <span data-ttu-id="42e64-111">由于 Microsoft 只能访问其中的一个注册表项，因此 Microsoft 无法访问受保护的数据，从而确保您可以完全控制您的数据隐私和安全性。</span><span class="sxs-lookup"><span data-stu-id="42e64-111">Since Microsoft can access only one of these keys, protected data remains inaccessible to Microsoft, ensuring that you have full control over your data privacy and security.</span></span>  

<span data-ttu-id="42e64-112">您可以在所选位置 (本地密钥管理服务器或云) 中承载用于请求密钥的双密钥加密服务。</span><span class="sxs-lookup"><span data-stu-id="42e64-112">You can host the Double Key Encryption service used to request your key, in a location of your choice (on-premises key management server or in the cloud).</span></span> <span data-ttu-id="42e64-113">您可以像维护任何其他应用程序一样维护服务。</span><span class="sxs-lookup"><span data-stu-id="42e64-113">You maintain the service as you would any other application.</span></span> <span data-ttu-id="42e64-114">通过双密钥加密，可以控制对双密钥加密服务的访问。</span><span class="sxs-lookup"><span data-stu-id="42e64-114">Double Key Encryption enables you to control access to the Double Key Encryption service.</span></span> <span data-ttu-id="42e64-115">您可以将高度敏感的数据存储在本地，也可以将其移动到云。</span><span class="sxs-lookup"><span data-stu-id="42e64-115">You can store your highly sensitive data on-premises or move it to the cloud.</span></span> <span data-ttu-id="42e64-116">你可以确信阻止第三方访问，因为你可以保持对密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="42e64-116">You can be confident about preventing third-party access because you maintain full control of your key.</span></span> <span data-ttu-id="42e64-117">通过双密钥加密，可以将数据和密钥存储在相同的位置。</span><span class="sxs-lookup"><span data-stu-id="42e64-117">Double Key Encryption allows you to store your data and key in the same location.</span></span>

<span data-ttu-id="42e64-118">DKE 帮助您跨几个法规和标准（如常规 Data Protection 规章 (GDPR) 、健康保险可移植性和责任法案 (HIPAA) 、格雷姆里奇-比利雷法案 (GLBA) 、俄罗斯的数据本地化法–联邦法律）来满足法规要求。</span><span class="sxs-lookup"><span data-stu-id="42e64-118">DKE helps you meet regulatory requirements across several regulations and standards such as the General Data Protection Regulation (GDPR), the Health Insurance Portability and Accountability Act (HIPAA), the Gramm-Leach-Bliley Act (GLBA), Russia’s data localization law – Federal Law No.</span></span> <span data-ttu-id="42e64-119">242-FZ、澳大利亚的联邦隐私法案1988和新西兰的隐私法案1993。</span><span class="sxs-lookup"><span data-stu-id="42e64-119">242-FZ, Australia’s Federal Privacy Act 1988, and New Zealand’s Privacy Act 1993.</span></span>

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a><span data-ttu-id="42e64-120">是否可以对 Microsoft Office 内置敏感度标签使用双密钥加密？</span><span class="sxs-lookup"><span data-stu-id="42e64-120">Can I use Double Key Encryption with Microsoft Office built-in sensitivity labeling?</span></span>

<span data-ttu-id="42e64-121">您需要使用 Azure 信息保护统一标签客户端，以使用双密钥加密来保护文档。</span><span class="sxs-lookup"><span data-stu-id="42e64-121">You'll need to use the Azure Information Protection unified labeling client to protect documents with Double Key Encryption.</span></span> <span data-ttu-id="42e64-122">目前，不能使用 Microsoft Office 的内置敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="42e64-122">Currently, you can't use Microsoft Office built-in sensitivity labeling.</span></span> 

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a><span data-ttu-id="42e64-123">我可以在 DKE 中使用哪些 Microsoft 365 应用？</span><span class="sxs-lookup"><span data-stu-id="42e64-123">What Microsoft 365 Apps can I use with DKE?</span></span>

<span data-ttu-id="42e64-124">您可以使用 DKE 标签来保护使用 Windows 上的 Word、Excel 和 PowerPoint 的桌面版本的文档。</span><span class="sxs-lookup"><span data-stu-id="42e64-124">You can use DKE labels to protect documents using the desktop versions of Word, Excel, and PowerPoint on Windows.</span></span> <span data-ttu-id="42e64-125">确保在 Windows 上使用12711或更高版本 (Word、PowerPoint 和 Excel) 的桌面版本。</span><span class="sxs-lookup"><span data-stu-id="42e64-125">Ensure that you're using \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a><span data-ttu-id="42e64-126">双密钥加密与现有保留的不同之处 HYOK) 解决方案中您自己的密钥 (？</span><span class="sxs-lookup"><span data-stu-id="42e64-126">How is Double Key Encryption different from the existing hold your own key (HYOK) solution?</span></span>

<span data-ttu-id="42e64-127">双密钥加密使用两个密钥对数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="42e64-127">Double Key Encryption encrypts your data with two keys.</span></span> <span data-ttu-id="42e64-128">你的加密密钥在你的控制中，第二个密钥存储在 Microsoft Azure 中，这样你就可以将加密的数据移动到云。</span><span class="sxs-lookup"><span data-stu-id="42e64-128">Your encryption key is in your control and the second key is stored in Microsoft Azure, allowing you to move your encrypted data to the cloud.</span></span> <span data-ttu-id="42e64-129">HYOK 仅使用一个密钥来保护你的内容，并且密钥始终在本地。</span><span class="sxs-lookup"><span data-stu-id="42e64-129">HYOK protects your content with only one key and the key is always on premises.</span></span>  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a><span data-ttu-id="42e64-130">是否可以在外部共享双密钥加密的文档？</span><span class="sxs-lookup"><span data-stu-id="42e64-130">Can Double Key Encrypted documents be shared externally?</span></span>

<span data-ttu-id="42e64-131">您可以在单独的租户上与用户共享双密钥加密的文档，只要这些用户具有以下条件：</span><span class="sxs-lookup"><span data-stu-id="42e64-131">You can share Double Key Encrypted documents with users on a separate tenant as long as those users:</span></span>

- <span data-ttu-id="42e64-132">拥有访问您的双重密钥加密服务中的密钥所需的权限。</span><span class="sxs-lookup"><span data-stu-id="42e64-132">Have the required permission to access your key in your Double Key Encryption service.</span></span>

- <span data-ttu-id="42e64-133">拥有在 Microsoft Azure 中访问密钥所需的权限。</span><span class="sxs-lookup"><span data-stu-id="42e64-133">Have the required permission to access your key in Microsoft Azure.</span></span>

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a><span data-ttu-id="42e64-134">通过 HYOK 保护的文档会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="42e64-134">What happens to documents that are protected with HYOK?</span></span>

<span data-ttu-id="42e64-135">部署双重密钥加密不会影响现有的 HYOK 设置。</span><span class="sxs-lookup"><span data-stu-id="42e64-135">Deploying Double Key Encryption won't affect your existing HYOK setup.</span></span> <span data-ttu-id="42e64-136">但是，我们建议您在与 HYOK 并行使用时开始使用双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="42e64-136">However, we recommend that you start using Double Key Encryption in parallel with HYOK.</span></span>

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a><span data-ttu-id="42e64-137">我是否可以在我的非 Microsoft 无成本环境中运行双重密钥加密？</span><span class="sxs-lookup"><span data-stu-id="42e64-137">Can I run Double Key Encryption in my non-Microsoft air-gapped environment?</span></span>

<span data-ttu-id="42e64-138">DKE 不支持这些环境，因为该服务需要访问 Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="42e64-138">DKE doesn't support these environments because the service requires access to Microsoft Azure.</span></span>

## <a name="where-can-i-store-double-key-encrypted-documents"></a><span data-ttu-id="42e64-139">在哪里可以存储双密钥加密文档？</span><span class="sxs-lookup"><span data-stu-id="42e64-139">Where can I store Double Key Encrypted documents?</span></span>

<span data-ttu-id="42e64-140">您可以在本地或在云中存储双密钥加密的文档。</span><span class="sxs-lookup"><span data-stu-id="42e64-140">You can store Double Key Encrypted documents on-premises or in the cloud.</span></span> <span data-ttu-id="42e64-141">在云中，你可以将加密的内容移动到 SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="42e64-141">In the cloud, you can move encrypted content to SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="42e64-142">由于 Microsoft 对你的私钥没有访问权限，因此加密的数据在 Microsoft 中保持不透明。</span><span class="sxs-lookup"><span data-stu-id="42e64-142">Since Microsoft doesn't have access to your private key, the encrypted data remains opaque to Microsoft.</span></span> <span data-ttu-id="42e64-143">这也意味着您无法在 Office Web Apps 中联机查看加密的文档。</span><span class="sxs-lookup"><span data-stu-id="42e64-143">This also means that you can't view the encrypted documents online in Office Web Apps.</span></span>

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a><span data-ttu-id="42e64-144">哪些区域和语言是可在中使用的双密钥加密？</span><span class="sxs-lookup"><span data-stu-id="42e64-144">What regions and languages is Double Key Encryption available in?</span></span> <span data-ttu-id="42e64-145">在全球范围内是否可以使用双重密钥加密？</span><span class="sxs-lookup"><span data-stu-id="42e64-145">Is Double Key Encryption available worldwide?</span></span>

<span data-ttu-id="42e64-146">DKE 标签与 Microsoft 信息保护中的其他敏感度标签本地化为相同的语言。</span><span class="sxs-lookup"><span data-stu-id="42e64-146">DKE labels are localized to the same languages as other sensitivity labels in Microsoft Information Protection.</span></span> <span data-ttu-id="42e64-147">双重密钥加密在全球范围内可用。</span><span class="sxs-lookup"><span data-stu-id="42e64-147">Double Key Encryption is available worldwide.</span></span>

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a><span data-ttu-id="42e64-148">是否可以将非 DKE 标签转换为 DKE 标签？</span><span class="sxs-lookup"><span data-stu-id="42e64-148">Can I convert a non-DKE label to a DKE label?</span></span>

<span data-ttu-id="42e64-149">否。</span><span class="sxs-lookup"><span data-stu-id="42e64-149">No.</span></span> <span data-ttu-id="42e64-150">创建标签后，不能向其添加 DKE。</span><span class="sxs-lookup"><span data-stu-id="42e64-150">You can’t add DKE to a label after you create it.</span></span> <span data-ttu-id="42e64-151">相反，您必须选择 " **使用双密钥加密** "，并在创建标签时提供您的双密钥加密服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="42e64-151">Instead, you must choose **Use Double Key Encryption** and provide the URL of your Double Key Encryption service when you create the label.</span></span>

## <a name="how-do-i-roll-my-dke-keys"></a><span data-ttu-id="42e64-152">如何滚动我的 DKE 键？</span><span class="sxs-lookup"><span data-stu-id="42e64-152">How do I roll my DKE keys?</span></span>

<span data-ttu-id="42e64-153">有关滚动 (也称为 "旋转或重新加密) 在 Azure 中存储的密钥的说明，请参阅 [Azure 信息保护租户密钥的操作](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="42e64-153">For instructions on rolling (also called rotating or rekeying) the key you store in Azure, see [Operations for your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).</span></span>

<span data-ttu-id="42e64-154">有关为 DKE 服务创建新密钥的信息，请参阅 [租户和关键设置](double-key-encryption.md#tenant-and-key-settings) 。</span><span class="sxs-lookup"><span data-stu-id="42e64-154">See [Tenant and key settings](double-key-encryption.md#tenant-and-key-settings) for information on creating a new key for the DKE service.</span></span>

<span data-ttu-id="42e64-155">创建密钥时，需要设置名称和 GUID。</span><span class="sxs-lookup"><span data-stu-id="42e64-155">When you create a key, you set up a name and a GUID.</span></span> <span data-ttu-id="42e64-156">然后，如果您旋转某个键，则保留具有名称和 GUID 的旧记录，但添加一个名称相同但 GUID 不同的新记录。</span><span class="sxs-lookup"><span data-stu-id="42e64-156">Then, if you rotate a key, you keep the old record with the name and GUID but add a new record with the same name but different GUID.</span></span> <span data-ttu-id="42e64-157">新密钥设置为活动，以便公钥 API 开始为新的加密返回它。</span><span class="sxs-lookup"><span data-stu-id="42e64-157">The new key gets set as active so that the public key API starts returning it for new encryption.</span></span> <span data-ttu-id="42e64-158">这两个密钥都可用于解密，以便可以解密新内容和旧内容。</span><span class="sxs-lookup"><span data-stu-id="42e64-158">Both keys are available for decryption so that new content and old content can be decrypted.</span></span>
