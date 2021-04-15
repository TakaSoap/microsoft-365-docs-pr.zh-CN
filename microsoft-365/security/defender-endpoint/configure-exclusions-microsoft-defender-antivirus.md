---
title: 设置 Microsoft Defender 防病毒扫描的排除项
description: 你可以排除文件 (包括由指定进程修改的文件) Microsoft Defender AV 扫描的文件夹。 使用 PowerShell 验证排除项。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764659"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="37e20-104">配置并验证 Microsoft Defender 防病毒扫描的排除项</span><span class="sxs-lookup"><span data-stu-id="37e20-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="37e20-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="37e20-105">**Applies to:**</span></span>

- [<span data-ttu-id="37e20-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37e20-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="37e20-107">你可以从 Microsoft Defender 防病毒扫描中排除某些文件、文件夹、进程和进程打开的文件。</span><span class="sxs-lookup"><span data-stu-id="37e20-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="37e20-108">此类排除项适用于 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、按需 [扫描](run-scan-microsoft-defender-antivirus.md)和 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="37e20-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="37e20-109">进程打开的文件的排除项仅适用于实时保护。</span><span class="sxs-lookup"><span data-stu-id="37e20-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="37e20-110">配置和验证排除</span><span class="sxs-lookup"><span data-stu-id="37e20-110">Configure and validate exclusions</span></span>

<span data-ttu-id="37e20-111">若要配置和验证排除项，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="37e20-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="37e20-112">[根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="37e20-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="37e20-113">这使你能够基于文件扩展名、文件名或位置从 Microsoft Defender 防病毒扫描中排除文件。</span><span class="sxs-lookup"><span data-stu-id="37e20-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="37e20-114">[配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="37e20-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="37e20-115">这使你可以从特定进程打开的扫描中排除文件。</span><span class="sxs-lookup"><span data-stu-id="37e20-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="37e20-116">定义排除项的建议</span><span class="sxs-lookup"><span data-stu-id="37e20-116">Recommendations for defining exclusions</span></span>
[!IMPORTANT]
<span data-ttu-id="37e20-117">Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件（例如用于企业管理、数据库管理和其他企业方案和情况的文件）的自动排除项。</span><span class="sxs-lookup"><span data-stu-id="37e20-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
<span data-ttu-id="37e20-118">定义排除项会降低 Microsoft Defender 防病毒所提供的保护。</span><span class="sxs-lookup"><span data-stu-id="37e20-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="37e20-119">您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="37e20-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="37e20-120">以下是定义排除项时应记住的建议列表：</span><span class="sxs-lookup"><span data-stu-id="37e20-120">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="37e20-121">从技术上说，排除项是一个保护差距，在定义排除项时，始终考虑其他缓解措施。</span><span class="sxs-lookup"><span data-stu-id="37e20-121">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="37e20-122">其他缓解措施可以非常简单，只需确保排除的位置具有适当的访问控制列表 (ACL) 、审核策略、由最新的软件等进行处理。</span><span class="sxs-lookup"><span data-stu-id="37e20-122">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="37e20-123">定期查看排除项。</span><span class="sxs-lookup"><span data-stu-id="37e20-123">Review the exclusions periodically.</span></span> <span data-ttu-id="37e20-124">作为审阅过程的一部分，重新检查和重新强制执行缓解。</span><span class="sxs-lookup"><span data-stu-id="37e20-124">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="37e20-125">理想情况下，避免定义主动排除项。</span><span class="sxs-lookup"><span data-stu-id="37e20-125">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="37e20-126">例如，不要仅因为你认为将来可能会出现问题而排除某些内容。</span><span class="sxs-lookup"><span data-stu-id="37e20-126">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="37e20-127">仅将排除项用于特定问题（主要围绕性能，有时围绕排除可以缓解的应用程序兼容性）。</span><span class="sxs-lookup"><span data-stu-id="37e20-127">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="37e20-128">审核排除列表更改。</span><span class="sxs-lookup"><span data-stu-id="37e20-128">Audit the exclusion list changes.</span></span> <span data-ttu-id="37e20-129">安全管理员应保留有关添加特定排除的原因的足够上下文。</span><span class="sxs-lookup"><span data-stu-id="37e20-129">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="37e20-130">您应该能够提供答案，并说明排除特定路径的原因的特定原因。</span><span class="sxs-lookup"><span data-stu-id="37e20-130">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="37e20-131">相关文章</span><span class="sxs-lookup"><span data-stu-id="37e20-131">Related articles</span></span>

- [<span data-ttu-id="37e20-132">Windows Server 2016 上的 Microsoft Defender 防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="37e20-132">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="37e20-133">定义排除时要避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="37e20-133">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
