---
title: 可靠性见解
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f830e01d54aef9065727971533633f8e63bc1214
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257030"
---
# <a name="reliability-insights"></a><span data-ttu-id="905a5-103">可靠性见解</span><span class="sxs-lookup"><span data-stu-id="905a5-103">Reliability insights</span></span>

<span data-ttu-id="905a5-104">此视图为你提供托管设备的运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="905a5-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="905a5-105">若要查看可靠性数据，请选择 "**可靠性**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="905a5-105">To view reliability data, select the **Reliability** tab.</span></span>


![可靠性窗格](images/insights_reliability.png)

<span data-ttu-id="905a5-107">"**跨设备的可靠性**" 部分通过报告被视为 "正常" 的设备的百分比以及自上次报告失败后观测到的平均时间，在最近14天中提供了部署的快速运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="905a5-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="905a5-108">根据时间，右侧的**可靠性**图表将报告发生严重错误的设备数以及观测到的严重错误总数。</span><span class="sxs-lookup"><span data-stu-id="905a5-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="905a5-109">"**热门问题**" 部分详细介绍了影响至少5% 托管设备的特定检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="905a5-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="905a5-110">报告的详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="905a5-110">Reported details include:</span></span>

- <span data-ttu-id="905a5-111">问题的类型</span><span class="sxs-lookup"><span data-stu-id="905a5-111">The type of issue</span></span>
    - <span data-ttu-id="905a5-112">应用程序崩溃，应用程序在其中停止运行或意外停止</span><span class="sxs-lookup"><span data-stu-id="905a5-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="905a5-113">应用程序挂起，应用程序在其中停止对输入的响应</span><span class="sxs-lookup"><span data-stu-id="905a5-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="905a5-114">严重错误，在 Windows 遇到无法恢复的问题时发生</span><span class="sxs-lookup"><span data-stu-id="905a5-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="905a5-115">受同一问题影响的设备数量</span><span class="sxs-lookup"><span data-stu-id="905a5-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="905a5-116">该数字代表的受管理设备的百分比</span><span class="sxs-lookup"><span data-stu-id="905a5-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="905a5-117">特定问题的总次数</span><span class="sxs-lookup"><span data-stu-id="905a5-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="905a5-118">似乎是问题源的软件组件</span><span class="sxs-lookup"><span data-stu-id="905a5-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="905a5-119">当前状态为 Microsoft 托管桌面操作调查和 remediates 问题</span><span class="sxs-lookup"><span data-stu-id="905a5-119">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

