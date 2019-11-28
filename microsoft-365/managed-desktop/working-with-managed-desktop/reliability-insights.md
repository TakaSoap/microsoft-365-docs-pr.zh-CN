---
title: 可靠性见解
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634029"
---
# <a name="reliability-insights"></a><span data-ttu-id="ce7a2-103">可靠性见解</span><span class="sxs-lookup"><span data-stu-id="ce7a2-103">Reliability insights</span></span>

<span data-ttu-id="ce7a2-104">此视图为你提供托管设备的运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="ce7a2-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="ce7a2-105">若要查看可靠性数据，请选择 "**可靠性**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ce7a2-105">To view reliability data, select the **Reliability** tab.</span></span>


![可靠性窗格](images/insights_reliability.png)

<span data-ttu-id="ce7a2-107">"**跨设备的可靠性**" 部分通过报告被视为 "正常" 的设备的百分比以及自上次报告失败后观测到的平均时间，在最近14天中提供了部署的快速运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="ce7a2-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="ce7a2-108">根据时间，右侧的**可靠性**图表将报告发生严重错误的设备数以及观测到的严重错误总数。</span><span class="sxs-lookup"><span data-stu-id="ce7a2-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="ce7a2-109">"**热门问题**" 部分详细介绍了影响至少5% 托管设备的特定检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="ce7a2-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="ce7a2-110">报告的详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="ce7a2-110">Reported details include:</span></span>

- <span data-ttu-id="ce7a2-111">问题的类型</span><span class="sxs-lookup"><span data-stu-id="ce7a2-111">The type of issue</span></span>
    - <span data-ttu-id="ce7a2-112">应用程序崩溃，应用程序在其中停止运行或意外停止</span><span class="sxs-lookup"><span data-stu-id="ce7a2-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="ce7a2-113">应用程序挂起，应用程序在其中停止对输入的响应</span><span class="sxs-lookup"><span data-stu-id="ce7a2-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="ce7a2-114">严重错误，在 Windows 遇到无法恢复的问题时发生</span><span class="sxs-lookup"><span data-stu-id="ce7a2-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="ce7a2-115">受同一问题影响的设备数量</span><span class="sxs-lookup"><span data-stu-id="ce7a2-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="ce7a2-116">该数字代表的受管理设备的百分比</span><span class="sxs-lookup"><span data-stu-id="ce7a2-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="ce7a2-117">特定问题的总次数</span><span class="sxs-lookup"><span data-stu-id="ce7a2-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="ce7a2-118">似乎是问题源的软件组件</span><span class="sxs-lookup"><span data-stu-id="ce7a2-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="ce7a2-119">检测到的问题的类别：</span><span class="sxs-lookup"><span data-stu-id="ce7a2-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="ce7a2-120">浏览器（边缘、Chrome、IE）</span><span class="sxs-lookup"><span data-stu-id="ce7a2-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="ce7a2-121">未知（非 Microsoft 组件）</span><span class="sxs-lookup"><span data-stu-id="ce7a2-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="ce7a2-122">驱动程序（音频、图形或其他驱动程序）</span><span class="sxs-lookup"><span data-stu-id="ce7a2-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="ce7a2-123">生产率（可宽延时间、G 套件、Microsoft Office 及其加载项或扩展、团队）</span><span class="sxs-lookup"><span data-stu-id="ce7a2-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="ce7a2-124">媒体（图像、音乐或视频应用程序</span><span class="sxs-lookup"><span data-stu-id="ce7a2-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="ce7a2-125">安全性（Windows 安全组件）</span><span class="sxs-lookup"><span data-stu-id="ce7a2-125">Security (Windows security components)</span></span>
- <span data-ttu-id="ce7a2-126">当前状态为 Microsoft 托管桌面操作调查和 remediates 问题</span><span class="sxs-lookup"><span data-stu-id="ce7a2-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

