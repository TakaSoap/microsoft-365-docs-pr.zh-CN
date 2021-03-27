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
ms.openlocfilehash: 87190d9e0bb62d42642374bd7c9f6f3acad3c80a
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379379"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="f2303-104">解决 Microsoft Defender for Endpoint for Mac 的性能问题</span><span class="sxs-lookup"><span data-stu-id="f2303-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2303-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f2303-105">**Applies to:**</span></span>

- [<span data-ttu-id="f2303-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="f2303-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="f2303-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2303-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2303-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2303-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2303-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f2303-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2303-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f2303-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f2303-111">本主题提供了一些常规步骤，可用于缩小与 Microsoft Defender for Endpoint for Mac 相关的性能问题。</span><span class="sxs-lookup"><span data-stu-id="f2303-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="f2303-112">RTP (实时) 是适用于 Mac 的 Microsoft Defender for Endpoint 的一项功能，可持续监视你的设备并保护设备免受威胁。</span><span class="sxs-lookup"><span data-stu-id="f2303-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="f2303-113">它包含文件和进程监视以及其他启发。</span><span class="sxs-lookup"><span data-stu-id="f2303-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="f2303-114">根据你正在运行的应用程序和设备特征，在运行适用于 Mac 的 Microsoft Defender for Endpoint 时可能会遇到性能不优化的问题。</span><span class="sxs-lookup"><span data-stu-id="f2303-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="f2303-115">特别是，在短时间内访问许多资源的应用程序或系统进程可能会导致 Microsoft Defender for Endpoint for Mac 中的性能问题。</span><span class="sxs-lookup"><span data-stu-id="f2303-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="f2303-116">以下步骤可用于排查并缓解这些问题：</span><span class="sxs-lookup"><span data-stu-id="f2303-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="f2303-117">使用下列方法之一禁用实时保护并观察性能是否提高。</span><span class="sxs-lookup"><span data-stu-id="f2303-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="f2303-118">此方法有助于缩小 Microsoft Defender for Endpoint for Mac 是否导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="f2303-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="f2303-119">如果你的设备不是由你的组织管理的，可以使用以下选项之一禁用实时保护：</span><span class="sxs-lookup"><span data-stu-id="f2303-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="f2303-120">从用户界面。</span><span class="sxs-lookup"><span data-stu-id="f2303-120">From the user interface.</span></span> <span data-ttu-id="f2303-121">打开 Microsoft Defender for Endpoint for Mac 并导航到"**管理设置"。**</span><span class="sxs-lookup"><span data-stu-id="f2303-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![管理实时保护屏幕截图](images/mdatp-36-rtp.png)

    - <span data-ttu-id="f2303-123">从终端。</span><span class="sxs-lookup"><span data-stu-id="f2303-123">From the Terminal.</span></span> <span data-ttu-id="f2303-124">出于安全目的，此操作需要提升权限。</span><span class="sxs-lookup"><span data-stu-id="f2303-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="f2303-125">如果你的设备由你的组织管理，则管理员可以使用设置适用于 Mac 的 Microsoft Defender for Endpoint 的首选项中的说明禁用 [实时保护](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="f2303-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="f2303-126">打开 Finder 并导航到 **应用程序**  >  **实用程序**。</span><span class="sxs-lookup"><span data-stu-id="f2303-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="f2303-127">打开 **活动监视器** 并分析哪些应用程序正在使用您系统上的资源。</span><span class="sxs-lookup"><span data-stu-id="f2303-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="f2303-128">典型示例包括软件更新和编译器。</span><span class="sxs-lookup"><span data-stu-id="f2303-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="f2303-129">将 Microsoft Defender for Endpoint for Mac 配置为排除导致性能问题的进程或磁盘位置，并重新启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="f2303-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="f2303-130">有关详细信息 [，请参阅配置和验证适用于 Mac](mac-exclusions.md) 的 Microsoft Defender 终结点的排除项。</span><span class="sxs-lookup"><span data-stu-id="f2303-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
