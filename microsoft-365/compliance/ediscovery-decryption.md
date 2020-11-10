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
description: 了解 Microsoft 365 电子数据展示工具如何处理附加到电子邮件的加密文档。
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951115"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="5ad6f-103">Microsoft 365 电子数据展示工具中的解密</span><span class="sxs-lookup"><span data-stu-id="5ad6f-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="5ad6f-104">加密是文件保护和信息保护策略的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-104">Encryption is an important part of your file protection and information protection strategy.</span></span> <span data-ttu-id="5ad6f-105">所有类型的组织都使用加密技术来保护其组织中的敏感内容，并确保只有适当的人员才能访问该内容。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-105">Organizations of all types use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span>

<span data-ttu-id="5ad6f-106">若要对加密内容执行常见的电子数据展示任务，电子数据展示管理器需要在从内容搜索、核心电子数据展示事例和高级电子数据展示事例中导出时对电子邮件内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-106">To execute common eDiscovery tasks on encrypted content, eDiscovery managers were required to decrypt email message content as it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="5ad6f-107">使用 Microsoft 加密技术加密的内容在导出之后才可供审阅。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-107">Content encrypted with Microsoft encryption technologies was not available for review until after it was exported.</span></span>

<span data-ttu-id="5ad6f-108">为了便于在电子数据展示工作流中管理加密内容，Microsoft 365 电子数据展示工具现在合并了附加到电子邮件和在 Exchange Online 中发送的加密文件的解密。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-108">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools now incorporate decryption of encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="5ad6f-109">在此新功能之前，只有受权限管理保护的电子邮件的内容 (，未对附加的文件) 解密。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-109">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) were decrypted.</span></span> <span data-ttu-id="5ad6f-110">现在，如果将使用 Microsoft 加密技术加密的文件附加到与搜索条件匹配的电子邮件，则在准备审阅搜索结果时将对加密的文件进行解密。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-110">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for review.</span></span> <span data-ttu-id="5ad6f-111">这使电子数据展示管理者可以在预览搜索结果时查看加密的电子邮件附件的内容，并在将其添加到高级电子数据展示中的审阅集后查看这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-111">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results, and review them once they have been added to a review set in Advanced eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad6f-112">即将启动 Microsoft 365 电子数据展示工具将支持存储在 SharePoint Online 和 OneDrive for Business 中的加密文档。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-112">Starting soon Microsoft 365 eDiscovery tools will support encrypted documents stored in SharePoint Online and OneDrive for Business.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="5ad6f-113">支持的加密技术</span><span class="sxs-lookup"><span data-stu-id="5ad6f-113">Supported encryption technologies</span></span>

<span data-ttu-id="5ad6f-114">Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-114">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="5ad6f-115">这些技术包括 Office 邮件加密、Microsoft 信息保护 (即将推出) 和 Azure 权限管理。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-115">These technologies include Office Message Encryption, Microsoft Information Protection (coming soon), and Azure Rights Management.</span></span> <span data-ttu-id="5ad6f-116">有关 Microsoft 加密技术的详细信息，请参阅 [加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-116">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="5ad6f-117">不支持由第三方加密技术加密的内容。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-117">Content encrypted by third-party encryption technologies isn't supported.</span></span> <span data-ttu-id="5ad6f-118">这在预览或导出使用非 Microsoft 技术加密的内容时不提供支持。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-118">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="5ad6f-119">支持加密项目的电子数据展示活动</span><span class="sxs-lookup"><span data-stu-id="5ad6f-119">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="5ad6f-120">下表列出了在 Microsoft 365 电子数据展示工具中执行的任务，这些任务支持附加到电子邮件 massages 的加密文件的解密。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-120">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="5ad6f-121">可对附加到与搜索条件相匹配的电子邮件的加密文件执行支持任务。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-121">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="5ad6f-122">值为 "N/A" 表示该函数在相应的电子数据展示工具中不可用。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-122">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="5ad6f-123">电子数据展示任务</span><span class="sxs-lookup"><span data-stu-id="5ad6f-123">eDiscovery task</span></span>  |<span data-ttu-id="5ad6f-124">内容搜索</span><span class="sxs-lookup"><span data-stu-id="5ad6f-124">Content search</span></span>  |<span data-ttu-id="5ad6f-125">核心电子数据展示</span><span class="sxs-lookup"><span data-stu-id="5ad6f-125">Core eDiscovery</span></span>  |<span data-ttu-id="5ad6f-126">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="5ad6f-126">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="5ad6f-127">搜索加密文件中的内容</span><span class="sxs-lookup"><span data-stu-id="5ad6f-127">Search for content in encrypted files</span></span>     |<span data-ttu-id="5ad6f-128">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-128">Yes</span></span>      |<span data-ttu-id="5ad6f-129">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-129">Yes</span></span>      |<span data-ttu-id="5ad6f-130">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-130">Yes</span></span>      |
|<span data-ttu-id="5ad6f-131">预览加密文件</span><span class="sxs-lookup"><span data-stu-id="5ad6f-131">Preview encrypted files</span></span>     |<span data-ttu-id="5ad6f-132">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-132">Yes</span></span>      |<span data-ttu-id="5ad6f-133">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-133">Yes</span></span>     |<span data-ttu-id="5ad6f-134">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-134">Yes</span></span>       |
|<span data-ttu-id="5ad6f-135">查看审阅集中的加密文件</span><span class="sxs-lookup"><span data-stu-id="5ad6f-135">Review encrypted files in a review set</span></span>    |<span data-ttu-id="5ad6f-136">不适用</span><span class="sxs-lookup"><span data-stu-id="5ad6f-136">N/A</span></span>      |<span data-ttu-id="5ad6f-137">不适用</span><span class="sxs-lookup"><span data-stu-id="5ad6f-137">N/A</span></span>        | <span data-ttu-id="5ad6f-138">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-138">Yes</span></span>        |
|<span data-ttu-id="5ad6f-139">导出加密文件</span><span class="sxs-lookup"><span data-stu-id="5ad6f-139">Export encrypted files</span></span>    |<span data-ttu-id="5ad6f-140">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-140">Yes</span></span>       |<span data-ttu-id="5ad6f-141">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-141">Yes</span></span>  |<span data-ttu-id="5ad6f-142">是</span><span class="sxs-lookup"><span data-stu-id="5ad6f-142">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="5ad6f-143">电子数据展示中的解密要求</span><span class="sxs-lookup"><span data-stu-id="5ad6f-143">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="5ad6f-144">您必须分配有 RMS 解密角色才能预览、审阅和导出使用 Microsoft 加密技术加密的附加文件。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-144">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="5ad6f-145">您还必须分配此角色以查看和查询在高级电子数据展示中添加到审阅集的加密电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-145">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="5ad6f-146">默认情况下，此角色分配给 Office 365 安全 & 合规中心中的电子数据展示管理器角色组。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-146">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="5ad6f-147">有关 RMS 解密角色的详细信息，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。</span><span class="sxs-lookup"><span data-stu-id="5ad6f-147">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
