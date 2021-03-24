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
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054742"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="5ec97-104">Microsoft Defender for Endpoint 的最低要求</span><span class="sxs-lookup"><span data-stu-id="5ec97-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ec97-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5ec97-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ec97-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ec97-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="5ec97-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ec97-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ec97-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5ec97-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ec97-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5ec97-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="5ec97-110">将设备载入到服务有一些最低要求。</span><span class="sxs-lookup"><span data-stu-id="5ec97-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="5ec97-111">了解许可、硬件和软件要求以及其他配置设置，以将设备载入服务。</span><span class="sxs-lookup"><span data-stu-id="5ec97-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="5ec97-112">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5ec97-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="5ec97-113">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="5ec97-114">了解 Defender for Endpoint： Defender [for Endpoint 技术社区中的最新增强功能](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="5ec97-115">Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。</span><span class="sxs-lookup"><span data-stu-id="5ec97-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="5ec97-116">阅读 [：MITRE ATT 中的见解&基于 CK 的评估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5ec97-117">许可要求</span><span class="sxs-lookup"><span data-stu-id="5ec97-117">Licensing requirements</span></span>
<span data-ttu-id="5ec97-118">Microsoft Defender for Endpoint 需要以下 Microsoft 批量许可优惠之一：</span><span class="sxs-lookup"><span data-stu-id="5ec97-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="5ec97-119">Windows 10 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="5ec97-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="5ec97-120">Windows 10 教育版 A5</span><span class="sxs-lookup"><span data-stu-id="5ec97-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="5ec97-121">Microsoft 365 E5 (M365 E5) 包括 Windows 10 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="5ec97-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="5ec97-122">Microsoft 365 A5 (M365 A5) </span><span class="sxs-lookup"><span data-stu-id="5ec97-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="5ec97-123">Microsoft 365 E5 安全版</span><span class="sxs-lookup"><span data-stu-id="5ec97-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="5ec97-124">Microsoft 365 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="5ec97-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="5ec97-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ec97-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-126">符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="5ec97-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="5ec97-127">Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (云解决方案提供商) 。</span><span class="sxs-lookup"><span data-stu-id="5ec97-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="5ec97-128">适用于服务器的 Microsoft Defender for Endpoint 需要以下许可选项之一：</span><span class="sxs-lookup"><span data-stu-id="5ec97-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="5ec97-129">启用 Azure Defender 的 Azure 安全中心</span><span class="sxs-lookup"><span data-stu-id="5ec97-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="5ec97-130">Microsoft Defender for Endpoint for Server (覆盖的服务器服务器一) </span><span class="sxs-lookup"><span data-stu-id="5ec97-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-131">如果 (对于以下一个或多个用户许可证，客户至少可以获取 50 个许可证，每个覆盖的服务器操作系统环境 (OSE) ) （适用于服务器的 Microsoft Defender）每覆盖一个许可证：</span><span class="sxs-lookup"><span data-stu-id="5ec97-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="5ec97-132">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ec97-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="5ec97-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="5ec97-133">Windows E5/A5</span></span>
> * <span data-ttu-id="5ec97-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="5ec97-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="5ec97-135">Microsoft 365 E5/A5 安全</span><span class="sxs-lookup"><span data-stu-id="5ec97-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="5ec97-136">有关许可的详细信息，请参阅产品 [条款网站](https://www.microsoft.com/licensing/terms/) ，并与你的帐户团队一起了解有关条款和条件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5ec97-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="5ec97-137">有关 Windows 10 版本中的功能数组详细信息，请参阅 [比较 Windows 10 版本](https://www.microsoft.com/windowsforbusiness/compare)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="5ec97-138">有关 Windows 10 商业版比较的详细比较表，请参阅[比较 PDF。](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="5ec97-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="5ec97-139">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="5ec97-139">Browser requirements</span></span>
<span data-ttu-id="5ec97-140">通过浏览器（支持以下浏览器）访问 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="5ec97-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="5ec97-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5ec97-141">Microsoft Edge</span></span>
- <span data-ttu-id="5ec97-142">Internet Explorer版本 11</span><span class="sxs-lookup"><span data-stu-id="5ec97-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="5ec97-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="5ec97-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-144">虽然其他浏览器可能正常工作，但所提及的浏览器是受支持的浏览器。</span><span class="sxs-lookup"><span data-stu-id="5ec97-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="5ec97-145">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="5ec97-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="5ec97-146">受支持的 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="5ec97-146">Supported Windows versions</span></span>
- <span data-ttu-id="5ec97-147">Windows 7 SP1 企业 ([需要 ESU 以支持](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) </span><span class="sxs-lookup"><span data-stu-id="5ec97-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="5ec97-148">Windows 7 SP1 专业 ([需要 ESU 以支持](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) </span><span class="sxs-lookup"><span data-stu-id="5ec97-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="5ec97-149">Windows 8.1 企业版</span><span class="sxs-lookup"><span data-stu-id="5ec97-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="5ec97-150">Windows 8.1 专业版</span><span class="sxs-lookup"><span data-stu-id="5ec97-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="5ec97-151">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="5ec97-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="5ec97-152">Windows 10 企业版 LTSC</span><span class="sxs-lookup"><span data-stu-id="5ec97-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="5ec97-153">Windows 10 教育版</span><span class="sxs-lookup"><span data-stu-id="5ec97-153">Windows 10 Education</span></span>
- <span data-ttu-id="5ec97-154">Windows 10 专业版</span><span class="sxs-lookup"><span data-stu-id="5ec97-154">Windows 10 Pro</span></span>
- <span data-ttu-id="5ec97-155">Windows 10 专业教育版</span><span class="sxs-lookup"><span data-stu-id="5ec97-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="5ec97-156">Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="5ec97-156">Windows server</span></span>
  - <span data-ttu-id="5ec97-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="5ec97-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="5ec97-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5ec97-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="5ec97-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5ec97-159">Windows Server 2016</span></span>
  - <span data-ttu-id="5ec97-160">Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ec97-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="5ec97-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5ec97-161">Windows Server 2019</span></span>
- <span data-ttu-id="5ec97-162">Windows 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="5ec97-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="5ec97-163">你的网络上设备必须运行这些版本之一。</span><span class="sxs-lookup"><span data-stu-id="5ec97-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="5ec97-164">对于受支持的版本，设备上 Defender for Endpoint 的硬件要求相同。</span><span class="sxs-lookup"><span data-stu-id="5ec97-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-165">不支持运行移动版本的 Windows (（如 Windows CE 和 Windows 10 移动) 的计算机。</span><span class="sxs-lookup"><span data-stu-id="5ec97-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="5ec97-166">如果运行 Windows 10 企业版 2016 LTSB 的虚拟机在非 Microsoft 虚拟化平台上运行，则可能会遇到性能问题。</span><span class="sxs-lookup"><span data-stu-id="5ec97-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="5ec97-167">对于虚拟环境，我们建议使用 Windows 10 企业版 LTSC 2019 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5ec97-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="5ec97-168">其他支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="5ec97-168">Other supported operating systems</span></span>
- <span data-ttu-id="5ec97-169">Android</span><span class="sxs-lookup"><span data-stu-id="5ec97-169">Android</span></span>
- <span data-ttu-id="5ec97-170">Linux</span><span class="sxs-lookup"><span data-stu-id="5ec97-170">Linux</span></span>
- <span data-ttu-id="5ec97-171">macOS</span><span class="sxs-lookup"><span data-stu-id="5ec97-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-172">你需要了解与 Defender for Endpoint 兼容的 Android 和 macOS 的确切 Linux 分发和版本，集成工作。</span><span class="sxs-lookup"><span data-stu-id="5ec97-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="5ec97-173">网络和数据存储以及配置要求</span><span class="sxs-lookup"><span data-stu-id="5ec97-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="5ec97-174">首次运行载入向导时，必须选择 Microsoft Defender 终结点相关信息的存储位置：欧盟、英国或美国数据中心。</span><span class="sxs-lookup"><span data-stu-id="5ec97-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="5ec97-175">首次设置后，无法更改数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="5ec97-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="5ec97-176">查看 [适用于终结点](data-storage-privacy.md) 的 Microsoft Defender 数据存储和隐私，详细了解 Microsoft 存储你的数据的位置和方法。</span><span class="sxs-lookup"><span data-stu-id="5ec97-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="5ec97-177">诊断数据设置</span><span class="sxs-lookup"><span data-stu-id="5ec97-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-178">Microsoft Defender for Endpoint 不需要任何特定的诊断级别，只要它已启用。</span><span class="sxs-lookup"><span data-stu-id="5ec97-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="5ec97-179">确保在你的组织的所有设备上启用了诊断数据服务。</span><span class="sxs-lookup"><span data-stu-id="5ec97-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="5ec97-180">默认情况下，此服务已启用。</span><span class="sxs-lookup"><span data-stu-id="5ec97-180">By default, this service is enabled.</span></span> <span data-ttu-id="5ec97-181">最佳做法是检查以确保从它们获取传感器数据。</span><span class="sxs-lookup"><span data-stu-id="5ec97-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="5ec97-182">**使用命令行检查 Windows 10 诊断数据服务启动类型**：</span><span class="sxs-lookup"><span data-stu-id="5ec97-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="5ec97-183">在设备上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="5ec97-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="5ec97-184">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="5ec97-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="5ec97-185">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="5ec97-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="5ec97-186">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="5ec97-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="5ec97-187">如果服务已启用，则结果应如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="5ec97-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack 的 sc 查询命令的结果](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="5ec97-189">如果服务未设置为 START_TYPE，则需要将服务设置为自动 **AUTO_START。** </span><span class="sxs-lookup"><span data-stu-id="5ec97-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="5ec97-190">**使用命令行将 Windows 10 诊断数据服务设置为自动启动：**</span><span class="sxs-lookup"><span data-stu-id="5ec97-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="5ec97-191">在终结点上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="5ec97-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="5ec97-192">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="5ec97-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="5ec97-193">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="5ec97-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="5ec97-194">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="5ec97-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="5ec97-195">将显示成功消息。</span><span class="sxs-lookup"><span data-stu-id="5ec97-195">A success message is displayed.</span></span> <span data-ttu-id="5ec97-196">通过输入以下命令验证更改，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="5ec97-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="5ec97-197">Internet 连接</span><span class="sxs-lookup"><span data-stu-id="5ec97-197">Internet connectivity</span></span>
<span data-ttu-id="5ec97-198">可直接或通过代理在设备上建立 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="5ec97-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="5ec97-199">Defender for Endpoint 传感器可以利用每日平均带宽 5 MB 与 Defender for Endpoint 云服务进行通信并报告网络数据。</span><span class="sxs-lookup"><span data-stu-id="5ec97-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="5ec97-200">此每日平均带宽中不包含文件上载和调查包收集等一次活动。</span><span class="sxs-lookup"><span data-stu-id="5ec97-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="5ec97-201">有关其他代理配置设置的信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="5ec97-202">在载入设备之前，必须启用诊断数据服务。</span><span class="sxs-lookup"><span data-stu-id="5ec97-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="5ec97-203">该服务在 Windows 10 中默认启用。</span><span class="sxs-lookup"><span data-stu-id="5ec97-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="5ec97-204">Microsoft Defender 防病毒配置要求</span><span class="sxs-lookup"><span data-stu-id="5ec97-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="5ec97-205">Defender for Endpoint 代理依赖于 Microsoft Defender 防病毒扫描文件并提供有关文件的信息的能力。</span><span class="sxs-lookup"><span data-stu-id="5ec97-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="5ec97-206">在 Defender for Endpoint 设备上配置安全智能更新，无论 Microsoft Defender 防病毒是否是活动的反恶意软件。</span><span class="sxs-lookup"><span data-stu-id="5ec97-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="5ec97-207">有关详细信息，请参阅管理 [Microsoft Defender 防病毒更新和应用基线](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="5ec97-208">当 Microsoft Defender 防病毒在你的组织中不是主动反恶意软件，并且你使用 Defender for Endpoint 服务时，Microsoft Defender 防病毒将进入被动模式。</span><span class="sxs-lookup"><span data-stu-id="5ec97-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="5ec97-209">如果你的组织已通过组策略或其他方法关闭 Microsoft Defender 防病毒，则必须从该组策略中排除已载入的设备。</span><span class="sxs-lookup"><span data-stu-id="5ec97-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="5ec97-210">如果你正在载入服务器，并且 Microsoft Defender 防病毒不是你的服务器上活动的反恶意软件，则需要将 Microsoft Defender 防病毒配置为进入被动模式或卸载。</span><span class="sxs-lookup"><span data-stu-id="5ec97-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="5ec97-211">配置取决于服务器版本。</span><span class="sxs-lookup"><span data-stu-id="5ec97-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="5ec97-212">有关详细信息，请参阅 [Microsoft Defender 防病毒兼容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec97-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5ec97-213">常规组策略不适用于防篡改保护，当启用防篡改保护时，将忽略对 Microsoft Defender 防病毒设置所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5ec97-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="5ec97-214">已启用 Microsoft Defender 防病毒提前启动反恶意软件 (ELAM) 已启用</span><span class="sxs-lookup"><span data-stu-id="5ec97-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="5ec97-215">如果你正在设备上将 Microsoft Defender 防病毒作为主要的反恶意软件产品运行，则 Defender for Endpoint 代理将成功载入。</span><span class="sxs-lookup"><span data-stu-id="5ec97-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="5ec97-216">如果正在运行第三方反恶意软件客户端并使用移动设备管理解决方案或 Microsoft Endpoint Manager (current branch) ，则需要确保已启用 Microsoft Defender 防病毒 ELAM 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="5ec97-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="5ec97-217">有关详细信息，请参阅 [确保策略](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)未禁用 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="5ec97-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="5ec97-218">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ec97-218">Related topics</span></span>
- [<span data-ttu-id="5ec97-219">设置 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="5ec97-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="5ec97-220">载入设备</span><span class="sxs-lookup"><span data-stu-id="5ec97-220">Onboard devices</span></span>](onboard-configure.md)
