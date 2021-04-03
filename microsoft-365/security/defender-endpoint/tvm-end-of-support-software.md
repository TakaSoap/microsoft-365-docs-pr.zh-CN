---
title: 规划支持终止的软件和硬件版本
description: 发现并规划不再受支持且不会接收安全更新的软件和硬件版本。
keywords: 威胁和漏洞管理， mdatp tvm 安全建议， 网络安全建议， 可操作的安全建议
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29adf8a542d97a981a07dac167343f3774aa5af4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500152"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="77950-104">使用威胁和漏洞管理规划支持终止的软件和硬件版本</span><span class="sxs-lookup"><span data-stu-id="77950-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77950-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="77950-105">**Applies to:**</span></span>

- [<span data-ttu-id="77950-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77950-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="77950-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="77950-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="77950-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77950-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="77950-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="77950-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77950-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="77950-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="77950-111">软件或软件版本的支持终止 (EOS) （也称为生命周期结束 (EOL) ）意味着它们将不再受支持或获得服务，并且不会接收安全更新。</span><span class="sxs-lookup"><span data-stu-id="77950-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="77950-112">当你使用具有结束支持的软件或软件版本时，你将使组织面临安全漏洞、法律和财务风险。</span><span class="sxs-lookup"><span data-stu-id="77950-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="77950-113">安全与 IT 管理员必须协同工作，并确保组织的软件清单配置为获得最佳结果、合规性和正常的网络生态系统。</span><span class="sxs-lookup"><span data-stu-id="77950-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="77950-114">他们应检查删除或替换已到达停止支持的应用的选项，并更新不再受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="77950-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="77950-115">最好在支持日期结束之前 **创建** 和实施计划。</span><span class="sxs-lookup"><span data-stu-id="77950-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="77950-116">查找不再受支持的软件或软件版本</span><span class="sxs-lookup"><span data-stu-id="77950-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="77950-117">从"威胁和漏洞管理"菜单中，导航到"[**安全建议"。**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="77950-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="77950-118">转到筛选器 **面板** 并查找标记部分。</span><span class="sxs-lookup"><span data-stu-id="77950-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="77950-119">选择一个或多个 EOS 标记选项。</span><span class="sxs-lookup"><span data-stu-id="77950-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="77950-120">然后 **应用**。</span><span class="sxs-lookup"><span data-stu-id="77950-120">Then **Apply**.</span></span>

    ![显示 EOS 软件、EOS 版本和即将推出的 EOS 版本的屏幕截图标记。](images/tvm-eos-tag.png)

3. <span data-ttu-id="77950-122">你将看到与已结束支持的软件、停止提供支持的软件版本或即将停止提供支持的版本相关的建议列表。</span><span class="sxs-lookup"><span data-stu-id="77950-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="77950-123">这些标记还显示在软件清单 [页面中](tvm-software-inventory.md) 。</span><span class="sxs-lookup"><span data-stu-id="77950-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![带 EOS 标记的建议。](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="77950-125">版本和日期列表</span><span class="sxs-lookup"><span data-stu-id="77950-125">List of versions and dates</span></span>

<span data-ttu-id="77950-126">若要查看已终止支持或即将结束或支持的版本列表以及这些日期，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="77950-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="77950-127">对于版本已终止支持或即将停止提供支持的软件，将在安全建议飞出中显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="77950-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![版本分发链接的屏幕截图。](images/eos-upcoming-eos.png)

2. <span data-ttu-id="77950-129">选择 **版本分发** 链接以转到软件深化页面。</span><span class="sxs-lookup"><span data-stu-id="77950-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="77950-130">其中，你可以看到经过筛选的版本列表，其中标记将它们标识为支持终止或即将停止提供支持。</span><span class="sxs-lookup"><span data-stu-id="77950-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![包含支持软件终止的软件向下钻取页面的屏幕截图。](images/software-drilldown-eos.png)

3. <span data-ttu-id="77950-132">选择要打开的表中的某个版本。</span><span class="sxs-lookup"><span data-stu-id="77950-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="77950-133">例如，版本 10.0.18362.1。</span><span class="sxs-lookup"><span data-stu-id="77950-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="77950-134">将显示一个显示支持日期结束的飞出图。</span><span class="sxs-lookup"><span data-stu-id="77950-134">A flyout will appear with the end of support date.</span></span>

    ![支持结束日期的屏幕截图。](images/version-eos-date.png)

<span data-ttu-id="77950-136">在确定哪些软件和硬件版本由于停止支持状态而易受攻击后，您必须决定是更新还是从组织中删除它们。</span><span class="sxs-lookup"><span data-stu-id="77950-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="77950-137">这样做将降低组织对漏洞和高级永久性威胁的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="77950-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77950-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="77950-138">Related topics</span></span>

- [<span data-ttu-id="77950-139">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="77950-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="77950-140">安全性建议</span><span class="sxs-lookup"><span data-stu-id="77950-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="77950-141">软件库存</span><span class="sxs-lookup"><span data-stu-id="77950-141">Software inventory</span></span>](tvm-software-inventory.md)
