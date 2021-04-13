---
title: 解决 Microsoft Defender ATP for Linux 的性能问题
description: 解决 Microsoft Defender ATP for Linux 中的性能问题。
keywords: microsoft， defender， atp， linux， 性能
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8865da0c8080213f6a2b82f78a6b31983c50409
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688617"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7380e-104">解决 Linux 上的 Microsoft Defender for Endpoint 的性能问题</span><span class="sxs-lookup"><span data-stu-id="7380e-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7380e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7380e-105">**Applies to:**</span></span>
- [<span data-ttu-id="7380e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7380e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7380e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7380e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="7380e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="7380e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7380e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7380e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="7380e-110">本文提供了一些常规步骤，可用于缩小与 Defender for Endpoint for Linux 相关的性能问题。</span><span class="sxs-lookup"><span data-stu-id="7380e-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="7380e-111">RTP (RTP) 是适用于 Linux 的 Defender for Endpoint 的一项功能，可持续监视和保护设备免受威胁。</span><span class="sxs-lookup"><span data-stu-id="7380e-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="7380e-112">它包含文件和进程监视以及其他启发。</span><span class="sxs-lookup"><span data-stu-id="7380e-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="7380e-113">根据你正在运行的应用程序和设备特征，在运行适用于 Linux 的 Defender for Endpoint 时可能会遇到性能不优化的问题。</span><span class="sxs-lookup"><span data-stu-id="7380e-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="7380e-114">特别是，在短时间内访问许多资源的应用程序或系统进程可能会导致 Defender for Endpoint for Linux 中的性能问题。</span><span class="sxs-lookup"><span data-stu-id="7380e-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="7380e-115">在启动 **之前，请确保其他安全产品当前未在设备上运行**。</span><span class="sxs-lookup"><span data-stu-id="7380e-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="7380e-116">多个安全产品可能会发生冲突并影响主机性能。</span><span class="sxs-lookup"><span data-stu-id="7380e-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="7380e-117">以下步骤可用于排查并缓解这些问题：</span><span class="sxs-lookup"><span data-stu-id="7380e-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="7380e-118">使用下列方法之一禁用实时保护并观察性能是否提高。</span><span class="sxs-lookup"><span data-stu-id="7380e-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="7380e-119">此方法有助于缩小 Defender for Endpoint for Linux 是否导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="7380e-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="7380e-120">如果你的设备不是由组织管理的，可以通过命令行禁用实时保护：</span><span class="sxs-lookup"><span data-stu-id="7380e-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="7380e-121">如果你的设备由你的组织管理，则管理员可以使用设置适用于 Linux 的 [Defender 终结点的](linux-preferences.md)首选项中的说明禁用实时保护。</span><span class="sxs-lookup"><span data-stu-id="7380e-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="7380e-122">如果实时保护关闭时性能问题仍然存在，则问题的原因可能是终结点检测和响应组件。</span><span class="sxs-lookup"><span data-stu-id="7380e-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="7380e-123">在这种情况下，请联系客户支持部门，了解进一步说明和缓解措施。</span><span class="sxs-lookup"><span data-stu-id="7380e-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="7380e-124">若要查找触发最多扫描的应用程序，可以使用 Defender for Endpoint for Linux 收集实时统计信息。</span><span class="sxs-lookup"><span data-stu-id="7380e-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7380e-125">此功能在版本 100.90.70 或更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="7380e-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="7380e-126">默认情况下，在 和 频道上 `Dogfood` 启用 `InsiderFast` 此功能。</span><span class="sxs-lookup"><span data-stu-id="7380e-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="7380e-127">如果使用的是其他更新通道，可以通过命令行启用此功能：</span><span class="sxs-lookup"><span data-stu-id="7380e-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="7380e-128">此功能需要启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="7380e-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="7380e-129">若要检查实时保护的状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7380e-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="7380e-130">验证条目 `real_time_protection_enabled` 是 `true` 。</span><span class="sxs-lookup"><span data-stu-id="7380e-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="7380e-131">否则，请运行以下命令以启用它：</span><span class="sxs-lookup"><span data-stu-id="7380e-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="7380e-132">若要收集当前统计信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="7380e-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="7380e-133">使用 ```--output json``` (请注意双) 短划线可确保输出格式已准备好进行分析。</span><span class="sxs-lookup"><span data-stu-id="7380e-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="7380e-134">此命令的输出将显示所有进程及其关联的扫描活动。</span><span class="sxs-lookup"><span data-stu-id="7380e-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="7380e-135">在 Linux 系统中，使用 命令下载 **python high_cpu_parser.py** 示例：</span><span class="sxs-lookup"><span data-stu-id="7380e-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="7380e-136">此命令的输出应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="7380e-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="7380e-137">接下来，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7380e-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="7380e-138">以上输出是性能问题的主要参与者的列表。</span><span class="sxs-lookup"><span data-stu-id="7380e-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="7380e-139">第一列是 PID (的进程标识符) ，第二列是 te 进程名称，最后一列是扫描的文件数，按影响排序。</span><span class="sxs-lookup"><span data-stu-id="7380e-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="7380e-140">例如，该命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="7380e-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    <span data-ttu-id="7380e-141">若要提高 Defender for Endpoint for Linux 的性能，请在行下找到编号最高的一个， `Total files scanned` 并添加排除项。</span><span class="sxs-lookup"><span data-stu-id="7380e-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="7380e-142">有关详细信息，请参阅为 Linux 的 Defender for Endpoint 配置和 [验证排除项](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="7380e-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="7380e-143">应用程序将统计信息存储在内存中，并仅跟踪自文件启动和启用实时保护以来的文件活动。</span><span class="sxs-lookup"><span data-stu-id="7380e-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="7380e-144">在实时保护关闭之前或期间启动的进程不计入在内。</span><span class="sxs-lookup"><span data-stu-id="7380e-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="7380e-145">此外，仅计算触发扫描的事件。</span><span class="sxs-lookup"><span data-stu-id="7380e-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="7380e-146">为 Linux 配置 Microsoft Defender ATP，排除导致性能问题的进程或磁盘位置，并重新启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="7380e-146">Configure Microsoft Defender ATP for Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="7380e-147">有关详细信息，请参阅为适用于 Linux 的 Microsoft Defender ATP 配置和 [验证排除项](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="7380e-147">For more information, see [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span></span>
