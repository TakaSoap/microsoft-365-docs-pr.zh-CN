---
title: CPU 回归分析
description: 了解 CPU 消耗的回归结果和指标
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322504"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="ed89f-103">智能 CPU 回归分析</span><span class="sxs-lookup"><span data-stu-id="ed89f-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="ed89f-104">CPU 使用率可以指示应用程序是否受操作系统更新的影响。</span><span class="sxs-lookup"><span data-stu-id="ed89f-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="ed89f-105">Microsoft 365 测试基础为软件开发人员提供了 CPU 性能回归的见解，当其应用程序在即将推出的 Windows 操作系统 (操作系统更新的不同版本上运行时) 回归。</span><span class="sxs-lookup"><span data-stu-id="ed89f-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="ed89f-106">这些 CPU 回归使开发人员 (在广泛部署操作系统更新) 并解决应用程序问题，从而防止最终用户遇到不良体验。</span><span class="sxs-lookup"><span data-stu-id="ed89f-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="ed89f-107">CPU 回归分析的工作原理</span><span class="sxs-lookup"><span data-stu-id="ed89f-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="ed89f-108">作为测试基础用户，你可以将应用程序的二进制文件 (上载到单个 .zip 文件) 以及关联的测试脚本，并选择你要在 Azure 上的测试基础门户上测试应用程序的 Windows 操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="ed89f-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="ed89f-109">然后，测试基础服务运行测试脚本并执行 CPU **回归分析**。</span><span class="sxs-lookup"><span data-stu-id="ed89f-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="ed89f-110">该服务将检查目标操作系统更新的预发布版本上的应用程序的 CPU 使用率是否与已发布版本的操作系统的 CPU 使用率一起。</span><span class="sxs-lookup"><span data-stu-id="ed89f-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="ed89f-111">CPU 使用率不是 100% 的类似比较，因为操作系统的两个版本上运行的进程可能完全匹配，也可能不完全匹配，因为操作系统版本不同;但是，测试基础执行的分析可以显示您的应用程序的 CPU 使用率是否受即将推出的操作系统更新的影响，特别是哪些进程已从以前的测试运行中进行了回归。</span><span class="sxs-lookup"><span data-stu-id="ed89f-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="ed89f-112">在下面的快照中，将针对同一应用程序比较两个操作系统版本 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="ed89f-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="ed89f-113">"CPU 使用率"选项卡分别显示两个发行版的使用率的上限和下限（分别为第 90 个和 10 个百分点）。</span><span class="sxs-lookup"><span data-stu-id="ed89f-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="ed89f-114">图中显示了 CPU 使用率的时间系列以及平均使用率。</span><span class="sxs-lookup"><span data-stu-id="ed89f-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="ed89f-115">客户现在可以使用该功能来确定其应用程序的 CPU 使用率是否受操作系统更新的影响，特别是哪些进程已从以前的执行中回归。</span><span class="sxs-lookup"><span data-stu-id="ed89f-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![CPU 回归分析](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="ed89f-117">相关流程标识</span><span class="sxs-lookup"><span data-stu-id="ed89f-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="ed89f-118">下面我们将讨论如何在应用程序中标识已回归进程。</span><span class="sxs-lookup"><span data-stu-id="ed89f-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="ed89f-119">分析性能回归需要跟踪测试运行期间在虚拟机上运行的每种进程不同类型的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="ed89f-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="ed89f-120">此类分析为给定应用程序的很多过程捕获大量变量。</span><span class="sxs-lookup"><span data-stu-id="ed89f-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="ed89f-121">并非所有进程都与一个运行或应用程序关联。</span><span class="sxs-lookup"><span data-stu-id="ed89f-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="ed89f-122">为了应对这一挑战，应用了一种使用概率和信息理论上的相互信息排名算法，以找出与给定应用程序最相关的过程。</span><span class="sxs-lookup"><span data-stu-id="ed89f-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="ed89f-123">当进程被视为另一种离散随机变量时，应用程序可被视为一种类型的离散随机变量。</span><span class="sxs-lookup"><span data-stu-id="ed89f-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="ed89f-124">使用相关性的条件概率测量两个随机变量的关联。</span><span class="sxs-lookup"><span data-stu-id="ed89f-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="ed89f-125">然后，进程将按每个应用程序的相关性顺序显示。</span><span class="sxs-lookup"><span data-stu-id="ed89f-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="ed89f-126">还可以收藏默认情况下可监视的一部分进程，以及用于 CPU 回归分析的相关进程。</span><span class="sxs-lookup"><span data-stu-id="ed89f-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="ed89f-127">一旦检测到回归分析器，就可以下载Windows分析器工具包并分析 CPU 性能回归的原因。</span><span class="sxs-lookup"><span data-stu-id="ed89f-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="ed89f-128">Windows Performance Analyzer 将事件跟踪日志 (ETL) 作为输入，这些 .etl 文件在日志文件中可用，可在门户上运行测试时下载。</span><span class="sxs-lookup"><span data-stu-id="ed89f-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="ed89f-129">如果您想了解有关调试 CPU 性能的更多信息，请参阅 Windows Performance Analyzer 文档。</span><span class="sxs-lookup"><span data-stu-id="ed89f-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

