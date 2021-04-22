---
title: 缓解零日漏洞 - 威胁和漏洞管理
description: 了解如何通过威胁和漏洞管理查找并减少环境中零日漏洞。
keywords: Microsoft Defender for Endpoint tvm zero day vulnerabilities， tvm， threat & vulnerability management， zero day， 0-day， mitigate 0 day vulnerabilities， vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be508e646a67f01887814a0e72170e438ee86212
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933057"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="6396f-104">缓解零日漏洞 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="6396f-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6396f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6396f-105">**Applies to:**</span></span>

- [<span data-ttu-id="6396f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6396f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6396f-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="6396f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6396f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6396f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6396f-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6396f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6396f-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6396f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="6396f-111">零日漏洞是公开披露的漏洞，尚未发布正式的修补程序或安全更新程序。</span><span class="sxs-lookup"><span data-stu-id="6396f-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="6396f-112">零日漏洞通常具有高严重性级别，并且被主动利用。</span><span class="sxs-lookup"><span data-stu-id="6396f-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="6396f-113">威胁和漏洞管理将仅显示其拥有相关信息的零日漏洞。</span><span class="sxs-lookup"><span data-stu-id="6396f-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="6396f-114">查找有关零日漏洞的信息</span><span class="sxs-lookup"><span data-stu-id="6396f-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="6396f-115">一旦发现零日漏洞，相关信息将在 Microsoft Defender 安全中心通过以下体验传达。</span><span class="sxs-lookup"><span data-stu-id="6396f-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="6396f-116">威胁和漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="6396f-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="6396f-117">在"顶级安全建议"卡片中查找带零日标记的建议。</span><span class="sxs-lookup"><span data-stu-id="6396f-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![带零日标记的热门建议。](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="6396f-119">在"最易受攻击的软件"卡中查找带零日标记的顶级软件。</span><span class="sxs-lookup"><span data-stu-id="6396f-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![具有零日标记的易受攻击的软件。](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="6396f-121">"漏洞"页</span><span class="sxs-lookup"><span data-stu-id="6396f-121">Weaknesses page</span></span>

<span data-ttu-id="6396f-122">查找已命名的零日漏洞以及说明和详细信息。</span><span class="sxs-lookup"><span data-stu-id="6396f-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="6396f-123">如果此漏洞分配了 CVE ID，你将在 CVE 名称旁边看到零日标签。</span><span class="sxs-lookup"><span data-stu-id="6396f-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="6396f-124">如果此漏洞未分配 CVE ID，你将在类似于"TVM-XXXX-XXXX"的内部临时名称下找到它。</span><span class="sxs-lookup"><span data-stu-id="6396f-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="6396f-125">分配官方 CVE-ID 后，该名称将更新，但以前的内部名称仍可搜索，并位于侧面板中。</span><span class="sxs-lookup"><span data-stu-id="6396f-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![零日示例，针对"漏洞"页面的 CVE-2020-17087。](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="6396f-127">软件清单页</span><span class="sxs-lookup"><span data-stu-id="6396f-127">Software inventory page</span></span>

<span data-ttu-id="6396f-128">查找带零日标记的软件。</span><span class="sxs-lookup"><span data-stu-id="6396f-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="6396f-129">按"零日"标记进行筛选，以仅查看具有零日漏洞的软件。</span><span class="sxs-lookup"><span data-stu-id="6396f-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![软件清单页中的 Windows Server 2016 零日示例。](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="6396f-131">"软件"页</span><span class="sxs-lookup"><span data-stu-id="6396f-131">Software page</span></span>

<span data-ttu-id="6396f-132">查找受零日漏洞影响的每个软件的零日标记。</span><span class="sxs-lookup"><span data-stu-id="6396f-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Windows Server 2016 软件页的零日示例。](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="6396f-134">"安全建议"页</span><span class="sxs-lookup"><span data-stu-id="6396f-134">Security recommendations page</span></span>

<span data-ttu-id="6396f-135">查看有关修正和缓解选项的清晰建议，包括解决方法（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="6396f-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="6396f-136">按"零日"标记进行筛选，以仅查看解决零日漏洞的安全建议。</span><span class="sxs-lookup"><span data-stu-id="6396f-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="6396f-137">如果有软件具有零日漏洞和其他要解决的漏洞，你将获得有关所有漏洞的一个建议。</span><span class="sxs-lookup"><span data-stu-id="6396f-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![安全建议页中的 Windows Server 2016 零日示例。](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="6396f-139">解决零日漏洞</span><span class="sxs-lookup"><span data-stu-id="6396f-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="6396f-140">转到安全建议页面，然后选择一个零日建议。</span><span class="sxs-lookup"><span data-stu-id="6396f-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="6396f-141">将打开一个空出场，并提供有关该软件的零日和其他漏洞的信息。</span><span class="sxs-lookup"><span data-stu-id="6396f-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="6396f-142">如果缓解选项和解决方法可用，将会提供相关链接。</span><span class="sxs-lookup"><span data-stu-id="6396f-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="6396f-143">在可以部署修补程序或安全更新之前，解决方法可能会帮助降低此零日漏洞带来的风险。</span><span class="sxs-lookup"><span data-stu-id="6396f-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="6396f-144">打开修正选项并选择注意类型。</span><span class="sxs-lookup"><span data-stu-id="6396f-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="6396f-145">建议对零日漏洞使用"注意"修正选项，因为更新尚未发布。</span><span class="sxs-lookup"><span data-stu-id="6396f-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="6396f-146">由于没有要执行的特定操作，因此无法选择截止日期。</span><span class="sxs-lookup"><span data-stu-id="6396f-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="6396f-147">如果你希望修正此软件存在较旧的漏洞，你可以替代"需要注意"的修正选项并选择"更新"。</span><span class="sxs-lookup"><span data-stu-id="6396f-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![安全建议页中 Windows Server 2016 的零日飞出示例。](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="6396f-149">跟踪零日修正活动</span><span class="sxs-lookup"><span data-stu-id="6396f-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="6396f-150">转到威胁和漏洞管理 [修正](tvm-remediation.md) 页面以查看修正活动项。</span><span class="sxs-lookup"><span data-stu-id="6396f-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="6396f-151">如果选择"注意需要"修正选项，则没有进度栏、票证状态或截止日期，因为我们可以监视任何实际操作。</span><span class="sxs-lookup"><span data-stu-id="6396f-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="6396f-152">您可以按修正类型（如"软件更新"或"需要注意"）进行筛选，以查看同一类别的所有活动项。</span><span class="sxs-lookup"><span data-stu-id="6396f-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="6396f-153">修补零日漏洞</span><span class="sxs-lookup"><span data-stu-id="6396f-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="6396f-154">当修补程序在零日发布时，建议将更改为"更新"，其旁边的蓝色标签显示"零日的新安全更新"。</span><span class="sxs-lookup"><span data-stu-id="6396f-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="6396f-155">它不再视为零日，将从所有页面中删除零日标记。</span><span class="sxs-lookup"><span data-stu-id="6396f-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![建议使用新的修补程序标签"更新 Microsoft Windows 10"。](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="6396f-157">相关文章</span><span class="sxs-lookup"><span data-stu-id="6396f-157">Related articles</span></span>

- [<span data-ttu-id="6396f-158">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="6396f-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6396f-159">仪表板</span><span class="sxs-lookup"><span data-stu-id="6396f-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="6396f-160">安全性建议</span><span class="sxs-lookup"><span data-stu-id="6396f-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="6396f-161">软件库存</span><span class="sxs-lookup"><span data-stu-id="6396f-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="6396f-162">我组织中的漏洞</span><span class="sxs-lookup"><span data-stu-id="6396f-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
