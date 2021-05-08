---
title: 设置扫描的Microsoft Defender 防病毒项
description: 你可以排除 (文件，包括由指定进程修改) 的文件以及文件夹被Microsoft Defender 防病毒。 使用 PowerShell 验证排除项。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275116"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="ac2c2-104">配置并验证扫描的Microsoft Defender 防病毒项</span><span class="sxs-lookup"><span data-stu-id="ac2c2-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ac2c2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ac2c2-105">**Applies to:**</span></span>

- [<span data-ttu-id="ac2c2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac2c2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ac2c2-107">你可以从扫描中排除某些文件、文件夹、进程和进程打开Microsoft Defender 防病毒文件。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="ac2c2-108">此类排除项适用于 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、按需 [扫描](run-scan-microsoft-defender-antivirus.md)和 [始终实时保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="ac2c2-109">进程打开的文件的排除项仅适用于实时保护。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="ac2c2-110">配置和验证排除</span><span class="sxs-lookup"><span data-stu-id="ac2c2-110">Configure and validate exclusions</span></span>

<span data-ttu-id="ac2c2-111">若要配置和验证排除项，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="ac2c2-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="ac2c2-112">[根据文件名、扩展名和文件夹位置配置并验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="ac2c2-113">可以基于文件扩展Microsoft Defender 防病毒文件扩展名、文件名或位置从扫描中排除文件。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="ac2c2-114">[配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="ac2c2-115">你可以从特定进程打开的扫描中排除文件。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="ac2c2-116">推荐排除项的定义</span><span class="sxs-lookup"><span data-stu-id="ac2c2-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac2c2-117">Microsoft Defender 防病毒许多基于已知操作系统行为和典型管理文件（如在企业管理、数据库管理和其他企业方案和情况中使用的那些文件）的自动排除项。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="ac2c2-118">定义排除项会降低由组织提供的Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ac2c2-119">您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="ac2c2-120">定义排除项时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="ac2c2-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="ac2c2-121">从技术上说，排除项是一个保护缺陷。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="ac2c2-122">定义排除项时，始终考虑缓解。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="ac2c2-123">其他缓解措施可能非常简单，只需确保排除的位置具有适当的访问控制列表 (ACL) 、审核策略、由最新的软件等进行处理。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="ac2c2-124">定期查看排除项。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-124">Review the exclusions periodically.</span></span> <span data-ttu-id="ac2c2-125">在审查过程中重新检查和重新强制执行缓解。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="ac2c2-126">理想情况下，避免定义旨在主动的排除项。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="ac2c2-127">例如，不要仅因为你认为将来可能会出现问题而排除某些内容。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="ac2c2-128">仅将排除项用于特定问题，例如与排除项可以缓解的性能或应用程序兼容性有关的问题。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="ac2c2-129">审核排除列表更改。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="ac2c2-130">安全管理员应保留有关添加特定排除的原因的足够上下文。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="ac2c2-131">您应该能够提供答案，并说明排除特定路径的原因的特定原因。</span><span class="sxs-lookup"><span data-stu-id="ac2c2-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ac2c2-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="ac2c2-132">Related articles</span></span>

- [<span data-ttu-id="ac2c2-133">Microsoft Defender 防病毒排除项Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ac2c2-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ac2c2-134">定义排除时要避免的常见错误</span><span class="sxs-lookup"><span data-stu-id="ac2c2-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
