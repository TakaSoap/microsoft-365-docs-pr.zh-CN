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
ms.openlocfilehash: 91d5689bfb64d272c896c0e92422ce1f45fd5f72
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984896"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="61f5e-103">Microsoft 365 电子数据展示工具中的解密</span><span class="sxs-lookup"><span data-stu-id="61f5e-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="61f5e-104">加密是文件保护和信息保护策略的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="61f5e-104">Encryption is an important part of your file protection and information protection strategy.</span></span> <span data-ttu-id="61f5e-105">所有类型的组织都使用加密技术来保护其组织中的敏感内容，并确保只有适当的人员才能访问该内容。</span><span class="sxs-lookup"><span data-stu-id="61f5e-105">Organizations of all types use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span>

<span data-ttu-id="61f5e-106">若要对加密内容执行常见的电子数据展示任务，电子数据展示管理器需要在从内容搜索、核心电子数据展示事例和高级电子数据展示事例中导出时对电子邮件内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="61f5e-106">To execute common eDiscovery tasks on encrypted content, eDiscovery managers were required to decrypt email message content as it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="61f5e-107">使用 Microsoft 加密技术加密的内容在导出之后才可供审阅。</span><span class="sxs-lookup"><span data-stu-id="61f5e-107">Content encrypted with Microsoft encryption technologies was not available for review until after it was exported.</span></span>

<span data-ttu-id="61f5e-108">为了便于在电子数据展示工作流中管理加密内容，Microsoft 365 电子数据展示工具现在合并了附加到电子邮件和在 Exchange Online 中发送的加密文件的解密。</span><span class="sxs-lookup"><span data-stu-id="61f5e-108">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools now incorporate decryption of encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="61f5e-109">在此新功能之前，只有受权限管理保护的电子邮件的内容 (，未对附加的文件) 解密。</span><span class="sxs-lookup"><span data-stu-id="61f5e-109">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) were decrypted.</span></span> <span data-ttu-id="61f5e-110">现在，如果将使用 Microsoft 加密技术加密的文件附加到与搜索条件匹配的电子邮件，则在准备审阅搜索结果时将对加密的文件进行解密。</span><span class="sxs-lookup"><span data-stu-id="61f5e-110">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for review.</span></span> <span data-ttu-id="61f5e-111">这使电子数据展示管理者可以在预览搜索结果时查看加密的电子邮件附件的内容，并在将其添加到高级电子数据展示中的审阅集后查看这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="61f5e-111">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results, and review them once they have been added to a review set in Advanced eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="61f5e-112">即将开始，Microsoft 365 电子数据展示工具将支持存储在 SharePoint Online 和 OneDrive for Business 中的加密文档。</span><span class="sxs-lookup"><span data-stu-id="61f5e-112">Starting soon, Microsoft 365 eDiscovery tools will support encrypted documents stored in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="61f5e-113">这将包括在应用了敏感度标签时加密的文档。</span><span class="sxs-lookup"><span data-stu-id="61f5e-113">This will include documents that are encrypted as a result of sensitivity labels applied to them.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="61f5e-114">支持的加密技术</span><span class="sxs-lookup"><span data-stu-id="61f5e-114">Supported encryption technologies</span></span>

<span data-ttu-id="61f5e-115">Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项。</span><span class="sxs-lookup"><span data-stu-id="61f5e-115">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="61f5e-116">这些技术包括 Office 邮件加密和 Azure 权限管理。</span><span class="sxs-lookup"><span data-stu-id="61f5e-116">These technologies include Office Message Encryption and Azure Rights Management.</span></span> <span data-ttu-id="61f5e-117">有关 Microsoft 加密技术的详细信息，请参阅 [加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="61f5e-117">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="61f5e-118">不支持由第三方加密技术加密的内容。</span><span class="sxs-lookup"><span data-stu-id="61f5e-118">Content encrypted by third-party encryption technologies isn't supported.</span></span> <span data-ttu-id="61f5e-119">这在预览或导出使用非 Microsoft 技术加密的内容时不提供支持。</span><span class="sxs-lookup"><span data-stu-id="61f5e-119">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="61f5e-120">支持加密项目的电子数据展示活动</span><span class="sxs-lookup"><span data-stu-id="61f5e-120">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="61f5e-121">下表列出了在 Microsoft 365 电子数据展示工具中执行的任务，这些任务支持附加到电子邮件 massages 的加密文件的解密。</span><span class="sxs-lookup"><span data-stu-id="61f5e-121">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="61f5e-122">可对附加到与搜索条件相匹配的电子邮件的加密文件执行支持任务。</span><span class="sxs-lookup"><span data-stu-id="61f5e-122">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="61f5e-123">值为 "N/A" 表示该函数在相应的电子数据展示工具中不可用。</span><span class="sxs-lookup"><span data-stu-id="61f5e-123">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="61f5e-124">电子数据展示任务</span><span class="sxs-lookup"><span data-stu-id="61f5e-124">eDiscovery task</span></span>  |<span data-ttu-id="61f5e-125">内容搜索</span><span class="sxs-lookup"><span data-stu-id="61f5e-125">Content search</span></span>  |<span data-ttu-id="61f5e-126">核心电子数据展示</span><span class="sxs-lookup"><span data-stu-id="61f5e-126">Core eDiscovery</span></span>  |<span data-ttu-id="61f5e-127">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="61f5e-127">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="61f5e-128">搜索加密文件中的内容</span><span class="sxs-lookup"><span data-stu-id="61f5e-128">Search for content in encrypted files</span></span>     |<span data-ttu-id="61f5e-129">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-129">Yes</span></span>      |<span data-ttu-id="61f5e-130">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-130">Yes</span></span>      |<span data-ttu-id="61f5e-131">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-131">Yes</span></span>      |
|<span data-ttu-id="61f5e-132">预览加密文件</span><span class="sxs-lookup"><span data-stu-id="61f5e-132">Preview encrypted files</span></span>     |<span data-ttu-id="61f5e-133">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-133">Yes</span></span>      |<span data-ttu-id="61f5e-134">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-134">Yes</span></span>     |<span data-ttu-id="61f5e-135">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-135">Yes</span></span>       |
|<span data-ttu-id="61f5e-136">查看审阅集中的加密文件</span><span class="sxs-lookup"><span data-stu-id="61f5e-136">Review encrypted files in a review set</span></span>    |<span data-ttu-id="61f5e-137">不适用</span><span class="sxs-lookup"><span data-stu-id="61f5e-137">N/A</span></span>      |<span data-ttu-id="61f5e-138">不适用</span><span class="sxs-lookup"><span data-stu-id="61f5e-138">N/A</span></span>        | <span data-ttu-id="61f5e-139">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-139">Yes</span></span>        |
|<span data-ttu-id="61f5e-140">导出加密文件</span><span class="sxs-lookup"><span data-stu-id="61f5e-140">Export encrypted files</span></span>    |<span data-ttu-id="61f5e-141">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-141">Yes</span></span>       |<span data-ttu-id="61f5e-142">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-142">Yes</span></span>  |<span data-ttu-id="61f5e-143">是</span><span class="sxs-lookup"><span data-stu-id="61f5e-143">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="61f5e-144">电子数据展示中的解密要求</span><span class="sxs-lookup"><span data-stu-id="61f5e-144">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="61f5e-145">您必须分配有 RMS 解密角色才能预览、审阅和导出使用 Microsoft 加密技术加密的附加文件。</span><span class="sxs-lookup"><span data-stu-id="61f5e-145">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="61f5e-146">您还必须分配此角色以查看和查询在高级电子数据展示中添加到审阅集的加密电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="61f5e-146">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="61f5e-147">默认情况下，此角色分配给 Office 365 安全 & 合规中心中的电子数据展示管理器角色组。</span><span class="sxs-lookup"><span data-stu-id="61f5e-147">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="61f5e-148">有关 RMS 解密角色的详细信息，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。</span><span class="sxs-lookup"><span data-stu-id="61f5e-148">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
