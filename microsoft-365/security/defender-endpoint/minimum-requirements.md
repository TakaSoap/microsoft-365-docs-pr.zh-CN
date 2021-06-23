---
title: Microsoft Defender for Endpoint 的最低要求
description: 了解将设备载入到服务的许可要求
keywords: 最低要求， 许可， 比较表
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52fa73774933ba90e8ca92dd1b337f983f5446c5
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082908"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="8d20a-104">Microsoft Defender for Endpoint 的最低要求</span><span class="sxs-lookup"><span data-stu-id="8d20a-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8d20a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8d20a-105">**Applies to:**</span></span>

- [<span data-ttu-id="8d20a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8d20a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d20a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d20a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8d20a-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8d20a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8d20a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8d20a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="8d20a-110">将设备载入到服务有一些最低要求。</span><span class="sxs-lookup"><span data-stu-id="8d20a-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="8d20a-111">了解许可、硬件和软件要求以及其他配置设置，以将设备载入服务。</span><span class="sxs-lookup"><span data-stu-id="8d20a-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="8d20a-112">了解 Defender for Endpoint： Defender [for Endpoint Tech](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)Community 中的最新增强功能。</span><span class="sxs-lookup"><span data-stu-id="8d20a-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="8d20a-113">Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。</span><span class="sxs-lookup"><span data-stu-id="8d20a-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="8d20a-114">阅读[：Insights MITRE ATT&基于 CK 的评估。](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="8d20a-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="8d20a-115">许可要求</span><span class="sxs-lookup"><span data-stu-id="8d20a-115">Licensing requirements</span></span>

<span data-ttu-id="8d20a-116">Microsoft Defender for Endpoint 需要以下 Microsoft 批量许可优惠之一：</span><span class="sxs-lookup"><span data-stu-id="8d20a-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="8d20a-117">Windows 10 企业版E5</span><span class="sxs-lookup"><span data-stu-id="8d20a-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="8d20a-118">Windows 10 教育版 A5</span><span class="sxs-lookup"><span data-stu-id="8d20a-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="8d20a-119">Microsoft 365 E5 (M365 E5) 包括 Windows 10 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="8d20a-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="8d20a-120">Microsoft 365 A5 (M365 A5) </span><span class="sxs-lookup"><span data-stu-id="8d20a-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="8d20a-121">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="8d20a-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="8d20a-122">Microsoft 365 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="8d20a-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="8d20a-123">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8d20a-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="8d20a-124">符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8d20a-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="8d20a-125">Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (购买) 。</span><span class="sxs-lookup"><span data-stu-id="8d20a-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="8d20a-126">RDSH VM 不需要单独的 Defender for Endpoint 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d20a-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="8d20a-127">适用于服务器的 Microsoft Defender for Endpoint 需要以下许可选项之一：</span><span class="sxs-lookup"><span data-stu-id="8d20a-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="8d20a-128">启用 Azure Defender 的 Azure 安全中心</span><span class="sxs-lookup"><span data-stu-id="8d20a-128">Azure Security Center with Azure Defender enabled</span></span>](/azure/security-center/security-center-pricing)
- <span data-ttu-id="8d20a-129">Microsoft Defender for Endpoint for Server (覆盖的服务器服务器一) </span><span class="sxs-lookup"><span data-stu-id="8d20a-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="8d20a-130">如果 (对于以下一个或多个用户许可证，客户至少可以获取 50 个许可证，每个覆盖的服务器操作系统环境 (OSE) ) （适用于服务器的 Microsoft Defender）每覆盖一个许可证：</span><span class="sxs-lookup"><span data-stu-id="8d20a-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="8d20a-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8d20a-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="8d20a-132">WindowsE5/A5</span><span class="sxs-lookup"><span data-stu-id="8d20a-132">Windows E5/A5</span></span>
> * <span data-ttu-id="8d20a-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="8d20a-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="8d20a-134">Microsoft 365 E5/A5 安全性</span><span class="sxs-lookup"><span data-stu-id="8d20a-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="8d20a-135">有关许可的详细信息，请参阅产品 [条款网站](https://www.microsoft.com/licensing/terms/) ，并与你的帐户团队一起了解有关条款和条件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8d20a-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="8d20a-136">有关不同版本中功能数组Windows 10，请参阅[比较Windows 10版本](https://www.microsoft.com/windowsforbusiness/compare)。</span><span class="sxs-lookup"><span data-stu-id="8d20a-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="8d20a-137">有关商业版比较Windows 10比较表，请参阅[比较 PDF。](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="8d20a-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="8d20a-138">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="8d20a-138">Browser requirements</span></span>

<span data-ttu-id="8d20a-139">通过浏览器（支持以下浏览器）访问 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="8d20a-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="8d20a-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8d20a-140">Microsoft Edge</span></span>
- <span data-ttu-id="8d20a-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="8d20a-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="8d20a-142">虽然其他浏览器可能正常工作，但所提及的浏览器是受支持的浏览器。</span><span class="sxs-lookup"><span data-stu-id="8d20a-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="8d20a-143">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="8d20a-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="8d20a-144">支持Windows版本</span><span class="sxs-lookup"><span data-stu-id="8d20a-144">Supported Windows versions</span></span>

- <span data-ttu-id="8d20a-145">Windows 7 SP1 Enterprise ([需要 ESU 以支持](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) </span><span class="sxs-lookup"><span data-stu-id="8d20a-145">Windows 7 SP1 Enterprise ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="8d20a-146">Windows 7 SP1 Pro (需要[ESU 以支持](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) </span><span class="sxs-lookup"><span data-stu-id="8d20a-146">Windows 7 SP1 Pro ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="8d20a-147">Windows 8.1 企业版</span><span class="sxs-lookup"><span data-stu-id="8d20a-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="8d20a-148">Windows 8.1 专业版</span><span class="sxs-lookup"><span data-stu-id="8d20a-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="8d20a-149">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="8d20a-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="8d20a-150">Windows 10 企业版LTSC 2016 (或更高版本) </span><span class="sxs-lookup"><span data-stu-id="8d20a-150">Windows 10 Enterprise LTSC 2016 (or later)</span></span>](/windows/whats-new/ltsc/)
- <span data-ttu-id="8d20a-151">Windows 10 教育版</span><span class="sxs-lookup"><span data-stu-id="8d20a-151">Windows 10 Education</span></span>
- <span data-ttu-id="8d20a-152">Windows 10 专业版</span><span class="sxs-lookup"><span data-stu-id="8d20a-152">Windows 10 Pro</span></span>
- <span data-ttu-id="8d20a-153">Windows 10 专业教育版</span><span class="sxs-lookup"><span data-stu-id="8d20a-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="8d20a-154">Windows服务器</span><span class="sxs-lookup"><span data-stu-id="8d20a-154">Windows server</span></span>
  - <span data-ttu-id="8d20a-155">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="8d20a-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="8d20a-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8d20a-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="8d20a-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8d20a-157">Windows Server 2016</span></span>
  - <span data-ttu-id="8d20a-158">Windows服务器版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8d20a-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="8d20a-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8d20a-159">Windows Server 2019</span></span>
- <span data-ttu-id="8d20a-160">Windows 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="8d20a-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="8d20a-161">你的网络上设备必须运行这些版本之一。</span><span class="sxs-lookup"><span data-stu-id="8d20a-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="8d20a-162">对于受支持的版本，设备上 Defender for Endpoint 的硬件要求相同。</span><span class="sxs-lookup"><span data-stu-id="8d20a-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="8d20a-163">不支持运行移动版本的 Windows (（如 Windows CE 和 Windows 10 移动版) ）。</span><span class="sxs-lookup"><span data-stu-id="8d20a-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="8d20a-164">如果运行Windows 10 企业版 2016 长期服务版非 Microsoft 虚拟化平台上运行，则运行该虚拟机的虚拟机可能会遇到性能问题。</span><span class="sxs-lookup"><span data-stu-id="8d20a-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="8d20a-165">对于虚拟环境，建议使用 Windows 10 企业版 LTSC 2019 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8d20a-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="8d20a-166">其他支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="8d20a-166">Other supported operating systems</span></span>

- [<span data-ttu-id="8d20a-167">Android</span><span class="sxs-lookup"><span data-stu-id="8d20a-167">Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="8d20a-168">iOS</span><span class="sxs-lookup"><span data-stu-id="8d20a-168">iOS</span></span>](microsoft-defender-endpoint-ios.md)
- [<span data-ttu-id="8d20a-169">Linux</span><span class="sxs-lookup"><span data-stu-id="8d20a-169">Linux</span></span>](microsoft-defender-endpoint-linux.md)
- [<span data-ttu-id="8d20a-170">macOS</span><span class="sxs-lookup"><span data-stu-id="8d20a-170">macOS</span></span>](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> <span data-ttu-id="8d20a-171">你需要确认 Android、iOS 和 macOS 的 Linux 分发和版本与 Defender for Endpoint 兼容，集成工作。</span><span class="sxs-lookup"><span data-stu-id="8d20a-171">You'll need to confirm the Linux distributions and versions of Android, iOS, and macOS are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="8d20a-172">网络和数据存储以及配置要求</span><span class="sxs-lookup"><span data-stu-id="8d20a-172">Network and data storage and configuration requirements</span></span>

<span data-ttu-id="8d20a-173">首次运行载入向导时，必须选择 Microsoft Defender 终结点相关信息的存储位置：欧盟、英国或美国数据中心。</span><span class="sxs-lookup"><span data-stu-id="8d20a-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="8d20a-174">首次设置后，无法更改数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="8d20a-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="8d20a-175">查看 [适用于终结点](data-storage-privacy.md) 的 Microsoft Defender 数据存储和隐私，详细了解 Microsoft 存储你的数据的位置和方法。</span><span class="sxs-lookup"><span data-stu-id="8d20a-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="8d20a-176">诊断数据设置</span><span class="sxs-lookup"><span data-stu-id="8d20a-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="8d20a-177">Microsoft Defender for Endpoint 不需要任何特定的诊断级别，只要它已启用。</span><span class="sxs-lookup"><span data-stu-id="8d20a-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="8d20a-178">确保在你的组织的所有设备上启用了诊断数据服务。</span><span class="sxs-lookup"><span data-stu-id="8d20a-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="8d20a-179">默认情况下，此服务已启用。</span><span class="sxs-lookup"><span data-stu-id="8d20a-179">By default, this service is enabled.</span></span> <span data-ttu-id="8d20a-180">最佳做法是检查以确保从它们获取传感器数据。</span><span class="sxs-lookup"><span data-stu-id="8d20a-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="8d20a-181">**使用命令行检查诊断Windows 10服务启动类型**：</span><span class="sxs-lookup"><span data-stu-id="8d20a-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="8d20a-182">在设备上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="8d20a-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="8d20a-183">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="8d20a-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="8d20a-184">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="8d20a-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="8d20a-185">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="8d20a-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="8d20a-186">如果服务已启用，则结果应如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="8d20a-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack 的 sc 查询命令的结果](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="8d20a-188">如果服务未设置为 START_TYPE，则需要将服务设置为自动 **AUTO_START。** </span><span class="sxs-lookup"><span data-stu-id="8d20a-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="8d20a-189">**使用命令行将 Windows 10数据服务设置为自动启动：**</span><span class="sxs-lookup"><span data-stu-id="8d20a-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="8d20a-190">在终结点上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="8d20a-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="8d20a-191">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="8d20a-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="8d20a-192">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="8d20a-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="8d20a-193">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="8d20a-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="8d20a-194">将显示成功消息。</span><span class="sxs-lookup"><span data-stu-id="8d20a-194">A success message is displayed.</span></span> <span data-ttu-id="8d20a-195">通过输入以下命令验证更改，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="8d20a-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="8d20a-196">Internet 连接</span><span class="sxs-lookup"><span data-stu-id="8d20a-196">Internet connectivity</span></span>

<span data-ttu-id="8d20a-197">可直接或通过代理在设备上建立 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="8d20a-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="8d20a-198">Defender for Endpoint 传感器可以使用每日平均带宽 5 MB 与 Defender for Endpoint 云服务进行通信并报告网络数据。</span><span class="sxs-lookup"><span data-stu-id="8d20a-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="8d20a-199">此每日平均带宽中不包含文件上载和调查包收集等一次活动。</span><span class="sxs-lookup"><span data-stu-id="8d20a-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="8d20a-200">有关其他代理配置设置的信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="8d20a-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="8d20a-201">在载入设备之前，必须启用诊断数据服务。</span><span class="sxs-lookup"><span data-stu-id="8d20a-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="8d20a-202">默认情况下，该服务在 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="8d20a-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="8d20a-203">Microsoft Defender 防病毒配置要求</span><span class="sxs-lookup"><span data-stu-id="8d20a-203">Microsoft Defender Antivirus configuration requirement</span></span>

<span data-ttu-id="8d20a-204">Defender for Endpoint 代理依赖于Microsoft Defender 防病毒扫描文件并提供有关文件的信息的能力。</span><span class="sxs-lookup"><span data-stu-id="8d20a-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="8d20a-205">在 Defender for Endpoint 设备上配置安全智能更新，Microsoft Defender 防病毒反恶意软件是否有效。</span><span class="sxs-lookup"><span data-stu-id="8d20a-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="8d20a-206">有关详细信息，请参阅管理更新[Microsoft Defender 防病毒应用基线](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="8d20a-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="8d20a-207">如果Microsoft Defender 防病毒在你的组织中不是主动反恶意软件，并且你使用 Defender for Endpoint 服务，Microsoft Defender 防病毒被动模式。</span><span class="sxs-lookup"><span data-stu-id="8d20a-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="8d20a-208">如果你的组织通过组策略Microsoft Defender 防病毒方法关闭已载入的设备，则必须从该组策略中排除已载入的设备。</span><span class="sxs-lookup"><span data-stu-id="8d20a-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="8d20a-209">如果你正在载入服务器，Microsoft Defender 防病毒服务器上不是主动反恶意软件，Microsoft Defender 防病毒需要配置为进入被动模式或卸载。</span><span class="sxs-lookup"><span data-stu-id="8d20a-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="8d20a-210">配置取决于服务器版本。</span><span class="sxs-lookup"><span data-stu-id="8d20a-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="8d20a-211">有关详细信息，请参阅兼容性[Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="8d20a-211">For more information, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8d20a-212">常规组策略不适用于防篡改保护，当防篡改保护打开Microsoft Defender 防病毒将忽略对组设置所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8d20a-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="8d20a-213">Microsoft Defender 防病毒启用早期启动反恶意软件 (ELAM) 已启用</span><span class="sxs-lookup"><span data-stu-id="8d20a-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>

<span data-ttu-id="8d20a-214">如果你正在设备上Microsoft Defender 防病毒作为主要的反恶意软件产品，则 Defender for Endpoint 代理将成功载入。</span><span class="sxs-lookup"><span data-stu-id="8d20a-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="8d20a-215">如果正在运行第三方反恶意软件客户端并使用移动设备管理解决方案或 Microsoft Endpoint Manager (current branch) ，则需要确保 Microsoft Defender 防病毒 ELAM 驱动程序已启用。</span><span class="sxs-lookup"><span data-stu-id="8d20a-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="8d20a-216">有关详细信息，请参阅[确保策略Microsoft Defender 防病毒禁用策略](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="8d20a-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="8d20a-217">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d20a-217">Related topics</span></span>

- [<span data-ttu-id="8d20a-218">设置 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="8d20a-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="8d20a-219">载入设备</span><span class="sxs-lookup"><span data-stu-id="8d20a-219">Onboard devices</span></span>](onboard-configure.md)
