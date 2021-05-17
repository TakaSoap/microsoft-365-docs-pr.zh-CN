---
title: 易受攻击的设备报告 - 危险和漏洞管理
description: 显示易受攻击的设备趋势和当前统计信息的报告。 目标是了解设备曝光的目的和范围。
keywords: Microsoft Defender for Endpoint-tvm 易受攻击的设备， Microsoft Defender for Endpoint， tvm， reduce threat & vulnerability exposure， reduce threat and vulnerability， monitor security configuration
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
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245476"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="77e19-105">易受攻击的设备报告 - 危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="77e19-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77e19-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="77e19-106">**Applies to:**</span></span>

- [<span data-ttu-id="77e19-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77e19-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="77e19-108">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="77e19-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="77e19-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77e19-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="77e19-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="77e19-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77e19-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="77e19-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="77e19-112">该报告显示包含易受攻击的设备趋势和当前统计信息的图形和条形图。</span><span class="sxs-lookup"><span data-stu-id="77e19-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="77e19-113">目标是了解设备曝光的目的和范围。</span><span class="sxs-lookup"><span data-stu-id="77e19-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="77e19-114">通过访问易受攻击Microsoft Defender 安全中心报告中>**报告**</span><span class="sxs-lookup"><span data-stu-id="77e19-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="77e19-115">有两列：</span><span class="sxs-lookup"><span data-stu-id="77e19-115">There are two columns:</span></span>

- <span data-ttu-id="77e19-116">趋势 (随着时间的推移) 。</span><span class="sxs-lookup"><span data-stu-id="77e19-116">Trends (over time).</span></span> <span data-ttu-id="77e19-117">可以显示过去 30 天、3 个月、6 个月或自定义日期范围。</span><span class="sxs-lookup"><span data-stu-id="77e19-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="77e19-118">今天 (最新) </span><span class="sxs-lookup"><span data-stu-id="77e19-118">Today (current information)</span></span>

<span data-ttu-id="77e19-119">**筛选器**：你可以按漏洞严重性级别、攻击可用性、漏洞年数、操作系统平台、Windows 10版本或设备组筛选数据。</span><span class="sxs-lookup"><span data-stu-id="77e19-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="77e19-120">**向下钻** 取：如果你希望进一步浏览某个见解，请选择相关条形图，以查看"设备清单"页中的已筛选设备列表。</span><span class="sxs-lookup"><span data-stu-id="77e19-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="77e19-121">可以从中导出列表。</span><span class="sxs-lookup"><span data-stu-id="77e19-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="77e19-122">严重性级别图形</span><span class="sxs-lookup"><span data-stu-id="77e19-122">Severity level graphs</span></span>

<span data-ttu-id="77e19-123">根据在该设备上发现的最严重漏洞，每台设备仅计数一次。</span><span class="sxs-lookup"><span data-stu-id="77e19-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![当前设备漏洞严重性级别的一个图，以及一个显示一段时间级别的图表。](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="77e19-125">攻击可用性图</span><span class="sxs-lookup"><span data-stu-id="77e19-125">Exploit availability graphs</span></span>

<span data-ttu-id="77e19-126">根据最高级别的已知攻击，每台设备仅计数一次。</span><span class="sxs-lookup"><span data-stu-id="77e19-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![当前设备攻击可用性的一个图和一个显示一段时间可用性的图形。](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="77e19-128">漏洞年龄图</span><span class="sxs-lookup"><span data-stu-id="77e19-128">Vulnerability age graphs</span></span>

<span data-ttu-id="77e19-129">每台设备仅在最旧的漏洞发布日期下计算一次。</span><span class="sxs-lookup"><span data-stu-id="77e19-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="77e19-130">较旧的漏洞被利用的可能性更大。</span><span class="sxs-lookup"><span data-stu-id="77e19-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![一张当前设备漏洞年数的图形，一张显示随着时间的年数的图形。](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="77e19-132">操作系统平台图的易受攻击的设备</span><span class="sxs-lookup"><span data-stu-id="77e19-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="77e19-133">因软件漏洞而公开的每个操作系统上的设备数量。</span><span class="sxs-lookup"><span data-stu-id="77e19-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![一张按操作系统平台显示当前易受攻击的设备的图形，以及一张显示操作系统平台随着时间的易受攻击的设备的图形。](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="77e19-135">按版本图Windows 10易受攻击的设备</span><span class="sxs-lookup"><span data-stu-id="77e19-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="77e19-136">因易受攻击的应用程序或操作系统Windows 10每个版本上的设备数量。</span><span class="sxs-lookup"><span data-stu-id="77e19-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![按版本显示当前易受攻击Windows 10的一个图，以及一个按版本Windows 10易受攻击的设备的图形。](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="77e19-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="77e19-138">Related topics</span></span>

- [<span data-ttu-id="77e19-139">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="77e19-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="77e19-140">安全性建议</span><span class="sxs-lookup"><span data-stu-id="77e19-140">Security recommendations</span></span>](tvm-security-recommendation.md)
