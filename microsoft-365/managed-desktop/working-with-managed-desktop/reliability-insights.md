---
title: 可靠性见解
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739757"
---
# <a name="reliability-insights"></a><span data-ttu-id="0431f-103">可靠性见解</span><span class="sxs-lookup"><span data-stu-id="0431f-103">Reliability insights</span></span>

<span data-ttu-id="0431f-104">此视图提供了托管设备的运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="0431f-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="0431f-105">若要查看可靠性数据，请选择"可靠性 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0431f-105">To view reliability data, select the **Reliability** tab.</span></span>


![可靠性窗格：左上方设备的可靠性、右上角的时间图的可靠性、底部顶部问题表。](../../media/insights_reliability.png)

<span data-ttu-id="0431f-108">" **跨设备** 的可靠性"部分通过报告被视为"正常运行"的设备百分比和自上次报告故障以来观察到的平均值，提供过去 14 天内部署的快速运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="0431f-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="0431f-109">右侧 **"时间可靠性** "图报告具有严重错误的设备数以及随着时间的推移观察到的关键错误总数。</span><span class="sxs-lookup"><span data-stu-id="0431f-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="0431f-110">" **主要问题** "部分详细介绍了检测到的特定问题，这些问题会影响至少 5% 的托管设备。</span><span class="sxs-lookup"><span data-stu-id="0431f-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="0431f-111">报告的详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="0431f-111">Reported details include:</span></span>

- <span data-ttu-id="0431f-112">问题类型</span><span class="sxs-lookup"><span data-stu-id="0431f-112">The type of issue</span></span>
    - <span data-ttu-id="0431f-113">应用程序崩溃，导致应用停止运行或意外停止</span><span class="sxs-lookup"><span data-stu-id="0431f-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="0431f-114">应用程序挂起，其中应用程序停止响应输入</span><span class="sxs-lookup"><span data-stu-id="0431f-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="0431f-115">严重错误，Windows遇到无法恢复的问题时发生</span><span class="sxs-lookup"><span data-stu-id="0431f-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="0431f-116">受同一问题影响的设备数量</span><span class="sxs-lookup"><span data-stu-id="0431f-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="0431f-117">数字表示的托管设备的百分比</span><span class="sxs-lookup"><span data-stu-id="0431f-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="0431f-118">特定问题的总发生次数</span><span class="sxs-lookup"><span data-stu-id="0431f-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="0431f-119">似乎是问题源的软件组件</span><span class="sxs-lookup"><span data-stu-id="0431f-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="0431f-120">检测到的问题的类别：</span><span class="sxs-lookup"><span data-stu-id="0431f-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="0431f-121">浏览器 (Edge、Chrome、IE) </span><span class="sxs-lookup"><span data-stu-id="0431f-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="0431f-122">未知 (非 Microsoft 组件) </span><span class="sxs-lookup"><span data-stu-id="0431f-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="0431f-123">驱动程序 (音频、图形或其他驱动程序) </span><span class="sxs-lookup"><span data-stu-id="0431f-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="0431f-124">Slack (、G 套件、Microsoft Office及其加载项或扩展、Teams) </span><span class="sxs-lookup"><span data-stu-id="0431f-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="0431f-125">媒体 (图像、音乐或视频应用</span><span class="sxs-lookup"><span data-stu-id="0431f-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="0431f-126">安全 (Windows安全组件) </span><span class="sxs-lookup"><span data-stu-id="0431f-126">Security (Windows security components)</span></span>
- <span data-ttu-id="0431f-127">当 Operations 调查和Microsoft 托管桌面时的当前状态</span><span class="sxs-lookup"><span data-stu-id="0431f-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

