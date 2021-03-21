---
title: 双密钥加密概述和常见问题解答
description: 有关 Microsoft 365 的双密钥加密的常见问题。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922046"
---
# <a name="double-key-encryption-frequently-asked-questions"></a><span data-ttu-id="ebc72-103">双密钥加密常见问题</span><span class="sxs-lookup"><span data-stu-id="ebc72-103">Double Key Encryption frequently asked questions</span></span>

<span data-ttu-id="ebc72-104">对双密钥加密的工作原理有一个问题？</span><span class="sxs-lookup"><span data-stu-id="ebc72-104">Have a question about how Double Key Encryption works?</span></span> <span data-ttu-id="ebc72-105">请在此处查看答案。</span><span class="sxs-lookup"><span data-stu-id="ebc72-105">Check for an answer here.</span></span>

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a><span data-ttu-id="ebc72-106">什么是 Microsoft 365 和 DKE (双密钥) ？</span><span class="sxs-lookup"><span data-stu-id="ebc72-106">What is Double Key Encryption for Microsoft 365 (DKE)?</span></span>

<span data-ttu-id="ebc72-107">Microsoft 365 的双密钥加密使客户能够保护其高度敏感的数据，以满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="ebc72-107">Double Key Encryption for Microsoft 365 enables customers to protect their highly sensitive data to meet specialized requirements.</span></span> <span data-ttu-id="ebc72-108">它帮助客户保持对加密密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="ebc72-108">It helps customers maintain full control of their encryption keys.</span></span> <span data-ttu-id="ebc72-109">它使用两个密钥来保护数据;控件中的一个键，另一个密钥安全存储在 Microsoft Azure 中。</span><span class="sxs-lookup"><span data-stu-id="ebc72-109">It uses two keys to protect data; one key in your control and a second key stored securely in Microsoft Azure.</span></span> <span data-ttu-id="ebc72-110">查看受双密钥加密保护的数据需要访问这两个密钥。</span><span class="sxs-lookup"><span data-stu-id="ebc72-110">Viewing data protected with Double Key Encryption requires access to both keys.</span></span> <span data-ttu-id="ebc72-111">由于 Microsoft 只能访问其中一个密钥，因此受保护数据仍无法访问 Microsoft，从而确保你可以完全控制数据隐私和安全性。</span><span class="sxs-lookup"><span data-stu-id="ebc72-111">Since Microsoft can access only one of these keys, protected data remains inaccessible to Microsoft, ensuring that you have full control over your data privacy and security.</span></span>  

<span data-ttu-id="ebc72-112">可以在选择的位置（本地密钥管理服务器或云密钥管理服务器 (用于请求密钥的双密钥加密) 。</span><span class="sxs-lookup"><span data-stu-id="ebc72-112">You can host the Double Key Encryption service used to request your key, in a location of your choice (on-premises key management server or in the cloud).</span></span> <span data-ttu-id="ebc72-113">像维护任何其他应用程序一样维护服务。</span><span class="sxs-lookup"><span data-stu-id="ebc72-113">You maintain the service as you would any other application.</span></span> <span data-ttu-id="ebc72-114">双密钥加密使您能够控制对双密钥加密服务的访问。</span><span class="sxs-lookup"><span data-stu-id="ebc72-114">Double Key Encryption enables you to control access to the Double Key Encryption service.</span></span> <span data-ttu-id="ebc72-115">可以在本地存储高度敏感的数据或将其移动到云中。</span><span class="sxs-lookup"><span data-stu-id="ebc72-115">You can store your highly sensitive data on-premises or move it to the cloud.</span></span> <span data-ttu-id="ebc72-116">你可以确信阻止第三方访问，因为你保持对密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="ebc72-116">You can be confident about preventing third-party access because you maintain full control of your key.</span></span> <span data-ttu-id="ebc72-117">双密钥加密允许您将数据和密钥存储在同一位置。</span><span class="sxs-lookup"><span data-stu-id="ebc72-117">Double Key Encryption allows you to store your data and key in the same location.</span></span>

<span data-ttu-id="ebc72-118">DKE 可帮助你满足多项法规和标准，如《一般数据保护条例》 (GDPR) 、健康保险可移植性和责任法案 (HIPAA) 、格雷姆-格雷姆-拉雷法案 (GLBA) 、俄罗斯的数据本地化法 – 联邦法律第 2004。</span><span class="sxs-lookup"><span data-stu-id="ebc72-118">DKE helps you meet regulatory requirements across several regulations and standards such as the General Data Protection Regulation (GDPR), the Health Insurance Portability and Accountability Act (HIPAA), the Gramm-Leach-Bliley Act (GLBA), Russia’s data localization law – Federal Law No.</span></span> <span data-ttu-id="ebc72-119">242-FZ、澳大利亚联邦隐私法案 1988 和新西兰隐私法案 1993。</span><span class="sxs-lookup"><span data-stu-id="ebc72-119">242-FZ, Australia’s Federal Privacy Act 1988, and New Zealand’s Privacy Act 1993.</span></span>

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a><span data-ttu-id="ebc72-120">能否将双密钥加密Microsoft Office内置敏感度标签？</span><span class="sxs-lookup"><span data-stu-id="ebc72-120">Can I use Double Key Encryption with Microsoft Office built-in sensitivity labeling?</span></span>

<span data-ttu-id="ebc72-121">你需要使用 Azure 信息保护统一标签客户端通过双密钥加密来保护文档。</span><span class="sxs-lookup"><span data-stu-id="ebc72-121">You'll need to use the Azure Information Protection unified labeling client to protect documents with Double Key Encryption.</span></span> <span data-ttu-id="ebc72-122">目前，你无法Microsoft Office内置敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="ebc72-122">Currently, you can't use Microsoft Office built-in sensitivity labeling.</span></span>

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a><span data-ttu-id="ebc72-123">我可以使用哪些 Microsoft 365 应用版与 DKE 一同使用？</span><span class="sxs-lookup"><span data-stu-id="ebc72-123">What Microsoft 365 Apps can I use with DKE?</span></span>

<span data-ttu-id="ebc72-124">可以使用 DKE 标签在 Windows 上使用桌面版本的 Word、Excel 和 PowerPoint 保护文档。</span><span class="sxs-lookup"><span data-stu-id="ebc72-124">You can use DKE labels to protect documents using the desktop versions of Word, Excel, and PowerPoint on Windows.</span></span> <span data-ttu-id="ebc72-125">确保使用 Windows 版桌面版 Word、PowerPoint 和 Excel (\*.12711) 更高版本。</span><span class="sxs-lookup"><span data-stu-id="ebc72-125">Ensure that you're using \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a><span data-ttu-id="ebc72-126">双密钥加密与 HYOK 解决方案中现有的保留密钥 (不同) ？</span><span class="sxs-lookup"><span data-stu-id="ebc72-126">How is Double Key Encryption different from the existing hold your own key (HYOK) solution?</span></span>

<span data-ttu-id="ebc72-127">双密钥加密使用两个密钥加密数据。</span><span class="sxs-lookup"><span data-stu-id="ebc72-127">Double Key Encryption encrypts your data with two keys.</span></span> <span data-ttu-id="ebc72-128">你的加密密钥在你的控制中，第二个密钥存储在 Microsoft Azure 中，以便你可以将加密数据移动到云。</span><span class="sxs-lookup"><span data-stu-id="ebc72-128">Your encryption key is in your control and the second key is stored in Microsoft Azure, allowing you to move your encrypted data to the cloud.</span></span> <span data-ttu-id="ebc72-129">HYOK 仅使用一个密钥保护内容，并且该密钥始终位于本地。</span><span class="sxs-lookup"><span data-stu-id="ebc72-129">HYOK protects your content with only one key and the key is always on premises.</span></span>  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a><span data-ttu-id="ebc72-130">能否在外部共享双密钥加密文档？</span><span class="sxs-lookup"><span data-stu-id="ebc72-130">Can Double Key Encrypted documents be shared externally?</span></span>

<span data-ttu-id="ebc72-131">你可以与单独租户上的用户共享双密钥加密文档，只要这些用户：</span><span class="sxs-lookup"><span data-stu-id="ebc72-131">You can share Double Key Encrypted documents with users on a separate tenant as long as those users:</span></span>

- <span data-ttu-id="ebc72-132">拥有访问双密钥加密服务中的密钥所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ebc72-132">Have the required permission to access your key in your Double Key Encryption service.</span></span>

- <span data-ttu-id="ebc72-133">拥有访问 Microsoft Azure 中的密钥所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ebc72-133">Have the required permission to access your key in Microsoft Azure.</span></span>

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a><span data-ttu-id="ebc72-134">使用 HYOK 保护的文档会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="ebc72-134">What happens to documents that are protected with HYOK?</span></span>

<span data-ttu-id="ebc72-135">部署双密钥加密不会影响现有的 HYOK 设置。</span><span class="sxs-lookup"><span data-stu-id="ebc72-135">Deploying Double Key Encryption won't affect your existing HYOK setup.</span></span> <span data-ttu-id="ebc72-136">但是，我们建议您开始与 HYOK 并行使用双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="ebc72-136">However, we recommend that you start using Double Key Encryption in parallel with HYOK.</span></span>

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a><span data-ttu-id="ebc72-137">能否在我的非 Microsoft 空心环境中运行双密钥加密？</span><span class="sxs-lookup"><span data-stu-id="ebc72-137">Can I run Double Key Encryption in my non-Microsoft air-gapped environment?</span></span>

<span data-ttu-id="ebc72-138">DKE 不支持这些环境，因为该服务需要访问 Microsoft Azure。</span><span class="sxs-lookup"><span data-stu-id="ebc72-138">DKE doesn't support these environments because the service requires access to Microsoft Azure.</span></span>

## <a name="where-can-i-store-double-key-encrypted-documents"></a><span data-ttu-id="ebc72-139">在哪里可以存储双密钥加密文档？</span><span class="sxs-lookup"><span data-stu-id="ebc72-139">Where can I store Double Key Encrypted documents?</span></span>

<span data-ttu-id="ebc72-140">可以在本地或云中存储双密钥加密文档。</span><span class="sxs-lookup"><span data-stu-id="ebc72-140">You can store Double Key Encrypted documents on-premises or in the cloud.</span></span> <span data-ttu-id="ebc72-141">在云中，您可以将加密内容移动到 SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="ebc72-141">In the cloud, you can move encrypted content to SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="ebc72-142">由于 Microsoft 无法访问你的私钥，加密数据对 Microsoft 保持不透明。</span><span class="sxs-lookup"><span data-stu-id="ebc72-142">Since Microsoft doesn't have access to your private key, the encrypted data remains opaque to Microsoft.</span></span> <span data-ttu-id="ebc72-143">这也意味着你无法联机查看 Office Web Apps 中的加密文档。</span><span class="sxs-lookup"><span data-stu-id="ebc72-143">This also means that you can't view the encrypted documents online in Office Web Apps.</span></span>

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a><span data-ttu-id="ebc72-144">What regions and languages is Double Key Encryption available in？</span><span class="sxs-lookup"><span data-stu-id="ebc72-144">What regions and languages is Double Key Encryption available in?</span></span> <span data-ttu-id="ebc72-145">双密钥加密是否在全球可用？</span><span class="sxs-lookup"><span data-stu-id="ebc72-145">Is Double Key Encryption available worldwide?</span></span>

<span data-ttu-id="ebc72-146">DKE 标签本地化为与 Microsoft 信息保护中其他敏感度标签相同的语言。</span><span class="sxs-lookup"><span data-stu-id="ebc72-146">DKE labels are localized to the same languages as other sensitivity labels in Microsoft Information Protection.</span></span> <span data-ttu-id="ebc72-147">双密钥加密在全球范围内可用。</span><span class="sxs-lookup"><span data-stu-id="ebc72-147">Double Key Encryption is available worldwide.</span></span>

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a><span data-ttu-id="ebc72-148">能否将非 DKE 标签转换为 DKE 标签？</span><span class="sxs-lookup"><span data-stu-id="ebc72-148">Can I convert a non-DKE label to a DKE label?</span></span>

<span data-ttu-id="ebc72-149">不正确。</span><span class="sxs-lookup"><span data-stu-id="ebc72-149">No.</span></span> <span data-ttu-id="ebc72-150">创建 DKE 后，不能将 DKE 添加到标签。</span><span class="sxs-lookup"><span data-stu-id="ebc72-150">You can’t add DKE to a label after you create it.</span></span> <span data-ttu-id="ebc72-151">相反，你必须选择" **使用双密钥加密"，** 并创建标签时提供双密钥加密服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="ebc72-151">Instead, you must choose **Use Double Key Encryption** and provide the URL of your Double Key Encryption service when you create the label.</span></span>

## <a name="how-do-i-roll-my-dke-keys"></a><span data-ttu-id="ebc72-152">如何滚动 DKE 密钥？</span><span class="sxs-lookup"><span data-stu-id="ebc72-152">How do I roll my DKE keys?</span></span>

<span data-ttu-id="ebc72-153">有关滚动密钥 (也称为旋转或重新) Azure 中存储的密钥，请参阅 [Azure 信息保护租户密钥的操作](/azure/information-protection/operations-customer-managed-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="ebc72-153">For instructions on rolling (also called rotating or rekeying) the key you store in Azure, see [Operations for your Azure Information Protection tenant key](/azure/information-protection/operations-customer-managed-tenant-key).</span></span>

<span data-ttu-id="ebc72-154">有关 [为](double-key-encryption.md#tenant-and-key-settings) DKE 服务创建新密钥的信息，请参阅租户和密钥设置。</span><span class="sxs-lookup"><span data-stu-id="ebc72-154">See [Tenant and key settings](double-key-encryption.md#tenant-and-key-settings) for information on creating a new key for the DKE service.</span></span>

<span data-ttu-id="ebc72-155">创建密钥时，将设置名称和 GUID。</span><span class="sxs-lookup"><span data-stu-id="ebc72-155">When you create a key, you set up a name and a GUID.</span></span> <span data-ttu-id="ebc72-156">然后，如果旋转一个键，则保留具有名称和 GUID 的旧记录，但添加一个名称相同但 GUID 不同的新记录。</span><span class="sxs-lookup"><span data-stu-id="ebc72-156">Then, if you rotate a key, you keep the old record with the name and GUID but add a new record with the same name but different GUID.</span></span> <span data-ttu-id="ebc72-157">新密钥设置为活动，以便公钥 API 开始返回它以用于新加密。</span><span class="sxs-lookup"><span data-stu-id="ebc72-157">The new key gets set as active so that the public key API starts returning it for new encryption.</span></span> <span data-ttu-id="ebc72-158">这两个密钥都可用于解密，以便可以解密新内容和旧内容。</span><span class="sxs-lookup"><span data-stu-id="ebc72-158">Both keys are available for decryption so that new content and old content can be decrypted.</span></span>