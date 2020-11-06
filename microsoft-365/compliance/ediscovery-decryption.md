---
title: 电子数据展示中的解密
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft 365 电子数据展示工具如何处理附加到电子邮件的加密文档。
ms.openlocfilehash: b7c1dc20b8e400b9880cc00a88a2d23a4b6d1979
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925580"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="3785a-103">Microsoft 365 电子数据展示工具中的解密</span><span class="sxs-lookup"><span data-stu-id="3785a-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="3785a-104">组织使用加密技术来保护组织中的敏感内容，并确保只有适当的人员才能访问该内容。</span><span class="sxs-lookup"><span data-stu-id="3785a-104">Organizations use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span> <span data-ttu-id="3785a-105">组织使用各种类型的加密（Microsoft 加密技术和第三方技术）来满足其安全要求并保护其敏感信息。</span><span class="sxs-lookup"><span data-stu-id="3785a-105">Organizations use various types of encryption, both Microsoft encryption technologies and third-party technologies to meet their security requirements and protect their sensitive information.</span></span>

<span data-ttu-id="3785a-106">到目前为止，在 Microsoft 365 中的电子数据展示工作流中管理加密内容需要对加密项进行特殊处理，具体取决于所使用的加密类型和工作流中的特定阶段。</span><span class="sxs-lookup"><span data-stu-id="3785a-106">To date, managing encrypted content in the eDiscovery workflow in Microsoft 365 requires special handling of encrypted items depending on the type of encryption used and the specific stage in the workflow.</span></span> <span data-ttu-id="3785a-107">这主要是通过在从内容搜索、核心电子数据展示事例和高级电子数据展示事例中导出电子邮件内容时对其进行解密来实现的。</span><span class="sxs-lookup"><span data-stu-id="3785a-107">This was primarily achieved by decrypting email message content when it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="3785a-108">在导出之前，无法预览使用 Microsoft 加密技术加密的内容。</span><span class="sxs-lookup"><span data-stu-id="3785a-108">Content encrypted with Microsoft encryption technologies couldn't be previewed until it was exported.</span></span> <span data-ttu-id="3785a-109">在高级电子数据展示中，对加密内容进行了处理错误标记，这要求您下载加密的项目，对其进行解密，然后将解密的文件上传到审阅集。</span><span class="sxs-lookup"><span data-stu-id="3785a-109">In Advanced eDiscovery, encrypted content was flagged with a processing error, which required that you download the encrypted item, decrypt it, and then upload the decrypted file to a review set.</span></span>

<span data-ttu-id="3785a-110">为了更轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具可以对附加到电子邮件的加密文件和在 Exchange Online 中发送的加密文件进行解密。</span><span class="sxs-lookup"><span data-stu-id="3785a-110">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools can decrypt encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="3785a-111">在此新功能之前，只有受权限管理保护的电子邮件的内容 (和未附加的文件) 解密。</span><span class="sxs-lookup"><span data-stu-id="3785a-111">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) was decrypted.</span></span> <span data-ttu-id="3785a-112">现在，如果将使用 Microsoft 加密技术加密的文件附加到与搜索条件匹配的电子邮件，则在准备预览搜索结果时，将对加密文件进行解密。</span><span class="sxs-lookup"><span data-stu-id="3785a-112">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for preview.</span></span> <span data-ttu-id="3785a-113">这样，电子数据展示管理者就可以在预览搜索结果时查看加密电子邮件附件的内容。</span><span class="sxs-lookup"><span data-stu-id="3785a-113">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="3785a-114">支持的加密技术</span><span class="sxs-lookup"><span data-stu-id="3785a-114">Supported encryption technologies</span></span>

<span data-ttu-id="3785a-115">Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项。</span><span class="sxs-lookup"><span data-stu-id="3785a-115">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="3785a-116">这些技术包括 Office 邮件加密、Microsoft 信息保护 (敏感标签) 和 Azure 权限管理。</span><span class="sxs-lookup"><span data-stu-id="3785a-116">These technologies include Office Message Encryption, Microsoft Information Protection (sensitivity labels), and Azure Rights Management.</span></span> <span data-ttu-id="3785a-117">有关 Microsoft 加密技术的详细信息，请参阅 [加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="3785a-117">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="3785a-118">不支持由第三方加密技术加密的内容。</span><span class="sxs-lookup"><span data-stu-id="3785a-118">Content encrypted by third-party encryption technologies is not supported.</span></span> <span data-ttu-id="3785a-119">这在预览或导出使用非 Microsoft 技术加密的内容时不提供支持。</span><span class="sxs-lookup"><span data-stu-id="3785a-119">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="3785a-120">支持加密项目的电子数据展示活动</span><span class="sxs-lookup"><span data-stu-id="3785a-120">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="3785a-121">下表列出了在 Microsoft 365 电子数据展示工具中执行的任务，这些任务支持附加到电子邮件 massages 的加密文件的解密。</span><span class="sxs-lookup"><span data-stu-id="3785a-121">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="3785a-122">可对附加到与搜索条件相匹配的电子邮件的加密文件执行支持任务。</span><span class="sxs-lookup"><span data-stu-id="3785a-122">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="3785a-123">值为 "N/A" 表示该函数在相应的电子数据展示工具中不可用。</span><span class="sxs-lookup"><span data-stu-id="3785a-123">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="3785a-124">电子数据展示任务</span><span class="sxs-lookup"><span data-stu-id="3785a-124">eDiscovery task</span></span>  |<span data-ttu-id="3785a-125">内容搜索</span><span class="sxs-lookup"><span data-stu-id="3785a-125">Content Search</span></span>  |<span data-ttu-id="3785a-126">核心电子数据展示</span><span class="sxs-lookup"><span data-stu-id="3785a-126">Core eDiscovery</span></span>  |<span data-ttu-id="3785a-127">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="3785a-127">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="3785a-128">搜索加密文件中的内容</span><span class="sxs-lookup"><span data-stu-id="3785a-128">Search for content in encrypted files</span></span>     |<span data-ttu-id="3785a-129">否</span><span class="sxs-lookup"><span data-stu-id="3785a-129">No</span></span>      |<span data-ttu-id="3785a-130">否</span><span class="sxs-lookup"><span data-stu-id="3785a-130">No</span></span>      |<span data-ttu-id="3785a-131">否</span><span class="sxs-lookup"><span data-stu-id="3785a-131">No</span></span>      |
|<span data-ttu-id="3785a-132">预览加密文件</span><span class="sxs-lookup"><span data-stu-id="3785a-132">Preview encrypted files</span></span>     |<span data-ttu-id="3785a-133">是</span><span class="sxs-lookup"><span data-stu-id="3785a-133">Yes</span></span>      |<span data-ttu-id="3785a-134">是</span><span class="sxs-lookup"><span data-stu-id="3785a-134">Yes</span></span>     |<span data-ttu-id="3785a-135">是</span><span class="sxs-lookup"><span data-stu-id="3785a-135">Yes</span></span>       |
|<span data-ttu-id="3785a-136">查看审阅集中的加密文件</span><span class="sxs-lookup"><span data-stu-id="3785a-136">Review encrypted files in a review set</span></span>    |<span data-ttu-id="3785a-137">不适用</span><span class="sxs-lookup"><span data-stu-id="3785a-137">N/A</span></span>      |<span data-ttu-id="3785a-138">不适用</span><span class="sxs-lookup"><span data-stu-id="3785a-138">N/A</span></span>        | <span data-ttu-id="3785a-139">是</span><span class="sxs-lookup"><span data-stu-id="3785a-139">Yes</span></span>        |
|<span data-ttu-id="3785a-140">导出加密文件</span><span class="sxs-lookup"><span data-stu-id="3785a-140">Export encrypted files</span></span>    |<span data-ttu-id="3785a-141">是</span><span class="sxs-lookup"><span data-stu-id="3785a-141">Yes</span></span>       |<span data-ttu-id="3785a-142">是</span><span class="sxs-lookup"><span data-stu-id="3785a-142">Yes</span></span>  |<span data-ttu-id="3785a-143">是</span><span class="sxs-lookup"><span data-stu-id="3785a-143">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="3785a-144">电子数据展示中的解密要求</span><span class="sxs-lookup"><span data-stu-id="3785a-144">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="3785a-145">您必须分配有 RMS 解密角色才能预览、审阅和导出使用 Microsoft 加密技术加密的附加文件。</span><span class="sxs-lookup"><span data-stu-id="3785a-145">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="3785a-146">您还必须分配此角色以查看和查询在高级电子数据展示中添加到审阅集的加密电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3785a-146">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="3785a-147">默认情况下，此角色分配给 Office 365 安全 & 合规中心中的电子数据展示管理器角色组。</span><span class="sxs-lookup"><span data-stu-id="3785a-147">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3785a-148">有关 RMS 解密角色的详细信息，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。</span><span class="sxs-lookup"><span data-stu-id="3785a-148">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
