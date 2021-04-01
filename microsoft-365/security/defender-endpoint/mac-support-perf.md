---
title: 解决 Microsoft Defender for Endpoint for Mac 的性能问题
description: 解决 Microsoft Defender for Endpoint for Mac 中的性能问题。
keywords: microsoft， defender， atp， mac， 性能
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
ms.openlocfilehash: 6ff93b44627cf876384522f0c4f25d22347c8661
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476251"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="1feff-104">解决 Microsoft Defender for Endpoint for Mac 的性能问题</span><span class="sxs-lookup"><span data-stu-id="1feff-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1feff-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1feff-105">**Applies to:**</span></span>

- [<span data-ttu-id="1feff-106">适用于 Mac 的终结点的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1feff-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="1feff-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1feff-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1feff-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1feff-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1feff-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1feff-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1feff-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1feff-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1feff-111">本主题提供了一些常规步骤，可用于缩小与 Microsoft Defender for Endpoint for Mac 相关的性能问题。</span><span class="sxs-lookup"><span data-stu-id="1feff-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="1feff-112">RTP (实时) 是适用于 Mac 的 Microsoft Defender for Endpoint 的一项功能，可持续监视你的设备并保护设备免受威胁。</span><span class="sxs-lookup"><span data-stu-id="1feff-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="1feff-113">它包含文件和进程监视以及其他启发。</span><span class="sxs-lookup"><span data-stu-id="1feff-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="1feff-114">根据你正在运行的应用程序和设备特征，在运行适用于 Mac 的 Microsoft Defender for Endpoint 时可能会遇到性能不优化的问题。</span><span class="sxs-lookup"><span data-stu-id="1feff-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="1feff-115">特别是，在短时间内访问许多资源的应用程序或系统进程可能会导致 Microsoft Defender for Endpoint for Mac 中的性能问题。</span><span class="sxs-lookup"><span data-stu-id="1feff-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="1feff-116">以下步骤可用于排查并缓解这些问题：</span><span class="sxs-lookup"><span data-stu-id="1feff-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="1feff-117">使用下列方法之一禁用实时保护并观察性能是否提高。</span><span class="sxs-lookup"><span data-stu-id="1feff-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="1feff-118">此方法有助于缩小 Microsoft Defender for Endpoint for Mac 是否导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="1feff-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

      <span data-ttu-id="1feff-119">如果你的设备不是由你的组织管理的，可以使用以下选项之一禁用实时保护：</span><span class="sxs-lookup"><span data-stu-id="1feff-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="1feff-120">从用户界面。</span><span class="sxs-lookup"><span data-stu-id="1feff-120">From the user interface.</span></span> <span data-ttu-id="1feff-121">打开 Microsoft Defender for Endpoint for Mac 并导航到"**管理设置"。**</span><span class="sxs-lookup"><span data-stu-id="1feff-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![管理实时保护屏幕截图](images/mdatp-36-rtp.png)

    - <span data-ttu-id="1feff-123">从终端。</span><span class="sxs-lookup"><span data-stu-id="1feff-123">From the Terminal.</span></span> <span data-ttu-id="1feff-124">出于安全目的，此操作需要提升权限。</span><span class="sxs-lookup"><span data-stu-id="1feff-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="1feff-125">如果你的设备由你的组织管理，则管理员可以使用设置适用于 Mac 的 Microsoft Defender for Endpoint 的首选项中的说明禁用 [实时保护](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="1feff-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>
      
      <span data-ttu-id="1feff-126">如果实时保护关闭时性能问题仍然存在，则问题的原因可能是终结点检测和响应组件。</span><span class="sxs-lookup"><span data-stu-id="1feff-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="1feff-127">在这种情况下，请联系客户支持部门，了解进一步说明和缓解措施。</span><span class="sxs-lookup"><span data-stu-id="1feff-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="1feff-128">打开 Finder 并导航到 **应用程序**  >  **实用程序**。</span><span class="sxs-lookup"><span data-stu-id="1feff-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="1feff-129">打开 **活动监视器** 并分析哪些应用程序正在使用您系统上的资源。</span><span class="sxs-lookup"><span data-stu-id="1feff-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="1feff-130">典型示例包括软件更新和编译器。</span><span class="sxs-lookup"><span data-stu-id="1feff-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="1feff-131">若要查找触发最多扫描的应用程序，可以使用 Defender for Endpoint for Mac 收集实时统计信息。</span><span class="sxs-lookup"><span data-stu-id="1feff-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1feff-132">此功能在版本 100.90.70 或更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="1feff-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="1feff-133">默认情况下，在 **Dogfood** 和 **InsiderFast** 频道上启用此功能。</span><span class="sxs-lookup"><span data-stu-id="1feff-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="1feff-134">如果使用的是其他更新通道，可以通过命令行启用此功能：</span><span class="sxs-lookup"><span data-stu-id="1feff-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="1feff-135">此功能需要启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="1feff-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="1feff-136">若要检查实时保护的状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1feff-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="1feff-137">确认 **real_time_protection_enabled条目** 为 true。</span><span class="sxs-lookup"><span data-stu-id="1feff-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="1feff-138">否则，请运行以下命令以启用它：</span><span class="sxs-lookup"><span data-stu-id="1feff-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="1feff-139">若要收集当前统计信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="1feff-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > <span data-ttu-id="1feff-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span><span class="sxs-lookup"><span data-stu-id="1feff-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="1feff-141">此命令的输出将显示所有进程及其关联的扫描活动。</span><span class="sxs-lookup"><span data-stu-id="1feff-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="1feff-142">在 Mac 系统上，使用 命令下载 python high_cpu_parser.py 示例：</span><span class="sxs-lookup"><span data-stu-id="1feff-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="1feff-143">此命令的输出应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="1feff-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="1feff-144">接下来，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="1feff-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="1feff-145">以上输出是性能问题的主要参与者的列表。</span><span class="sxs-lookup"><span data-stu-id="1feff-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="1feff-146">第一列是 PID (的进程标识符) ，第二列是 te 进程名称，最后一列是扫描的文件数，按影响排序。</span><span class="sxs-lookup"><span data-stu-id="1feff-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="1feff-147">例如，该命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="1feff-147">For example, the output of the command will be something like the below:</span></span>

      ```output
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

      <span data-ttu-id="1feff-148">若要提高 Defender for Endpoint for Mac 的性能，请在"扫描的文件总数"行下找到编号最高的一个，并添加排除项。</span><span class="sxs-lookup"><span data-stu-id="1feff-148">To improve the performance of Defender for Endpoint for Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="1feff-149">有关详细信息，请参阅为 Linux 的 Defender for Endpoint 配置和 [验证排除项](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="1feff-149">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="1feff-150">应用程序将统计信息存储在内存中，并仅跟踪自文件启动和启用实时保护以来的文件活动。</span><span class="sxs-lookup"><span data-stu-id="1feff-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="1feff-151">在实时保护关闭之前或期间启动的进程不计入在内。</span><span class="sxs-lookup"><span data-stu-id="1feff-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="1feff-152">此外，仅计算触发扫描的事件。</span><span class="sxs-lookup"><span data-stu-id="1feff-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="1feff-153">将 Microsoft Defender for Endpoint for Mac 配置为排除导致性能问题的进程或磁盘位置，并重新启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="1feff-153">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="1feff-154">有关详细信息 [，请参阅配置和验证适用于 Mac](mac-exclusions.md) 的 Microsoft Defender 终结点的排除项。</span><span class="sxs-lookup"><span data-stu-id="1feff-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
