---
title: 可下载的准备情况评估检查器
description: 检查设备和网络设置，包括所需的终结点
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581030"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="bd87c-104">可下载的准备情况评估检查器</span><span class="sxs-lookup"><span data-stu-id="bd87c-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="bd87c-105">若要很好地使用 Microsoft 托管桌面，设备必须满足硬件和设置的某些要求。</span><span class="sxs-lookup"><span data-stu-id="bd87c-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="bd87c-106">此外，每台设备必须能够到达关键终结点。</span><span class="sxs-lookup"><span data-stu-id="bd87c-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="bd87c-107">下载并运行此工具以获取 HTML 报告、查看结果，然后采取措施。</span><span class="sxs-lookup"><span data-stu-id="bd87c-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="bd87c-108">你需要下载该工具和支持文件，然后在你想要在 Microsoft 托管桌面中注册的每个设备上手动运行它。</span><span class="sxs-lookup"><span data-stu-id="bd87c-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bd87c-109">对于每个检查，该工具将报告三个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="bd87c-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="bd87c-110">结果</span><span class="sxs-lookup"><span data-stu-id="bd87c-110">Result</span></span>  |<span data-ttu-id="bd87c-111">含义</span><span class="sxs-lookup"><span data-stu-id="bd87c-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="bd87c-112">Ready</span><span class="sxs-lookup"><span data-stu-id="bd87c-112">Ready</span></span>     | <span data-ttu-id="bd87c-113">完成注册前无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="bd87c-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="bd87c-114">公告</span><span class="sxs-lookup"><span data-stu-id="bd87c-114">Advisory</span></span>    | <span data-ttu-id="bd87c-115">按照工具中的步骤操作，实现注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="bd87c-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="bd87c-116">*你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。</span><span class="sxs-lookup"><span data-stu-id="bd87c-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="bd87c-117">未就绪</span><span class="sxs-lookup"><span data-stu-id="bd87c-117">Not ready</span></span> | <span data-ttu-id="bd87c-118">*如果不修复* 这些问题，注册将失败。</span><span class="sxs-lookup"><span data-stu-id="bd87c-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="bd87c-119">按照工具中的步骤进行解析。</span><span class="sxs-lookup"><span data-stu-id="bd87c-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="bd87c-120">获取检查器</span><span class="sxs-lookup"><span data-stu-id="bd87c-120">Obtain the checker</span></span>

<span data-ttu-id="bd87c-121">从 下载.zip文件 https://aka.ms/mmddratoolv0 。</span><span class="sxs-lookup"><span data-stu-id="bd87c-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="bd87c-122">运行该工具的用户必须在运行该工具的设备上具有本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bd87c-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="bd87c-123">然后按照以下步骤运行该工具：</span><span class="sxs-lookup"><span data-stu-id="bd87c-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="bd87c-124">将下载.zip文件复制到你想要检查的每个设备。</span><span class="sxs-lookup"><span data-stu-id="bd87c-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="bd87c-125">在压缩的下载中解压缩所有文件。</span><span class="sxs-lookup"><span data-stu-id="bd87c-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="bd87c-126">运行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**。</span><span class="sxs-lookup"><span data-stu-id="bd87c-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="bd87c-127">出现"用户访问控制"提示时，选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="bd87c-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="bd87c-128">该工具将运行，并打开默认浏览器中的报告。</span><span class="sxs-lookup"><span data-stu-id="bd87c-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="bd87c-129">还可以下载并提取.zip存档到共享位置，从 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe访问该** 存档，然后在本地运行它。</span><span class="sxs-lookup"><span data-stu-id="bd87c-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="bd87c-130">检查</span><span class="sxs-lookup"><span data-stu-id="bd87c-130">Checks</span></span>

<span data-ttu-id="bd87c-131">可下载的工具会检查与设备和网络相关的项：</span><span class="sxs-lookup"><span data-stu-id="bd87c-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="bd87c-132">硬件</span><span class="sxs-lookup"><span data-stu-id="bd87c-132">Hardware</span></span>

<span data-ttu-id="bd87c-133">设备必须满足特定的硬件要求，以使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="bd87c-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="bd87c-134">目前，仅 [允许注册特定](../service-description/device-list.md) 批准的设备。</span><span class="sxs-lookup"><span data-stu-id="bd87c-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="bd87c-135">如果你的设备未通过任何检查，它将与 Microsoft 托管桌面不兼容。</span><span class="sxs-lookup"><span data-stu-id="bd87c-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="bd87c-136">网络终结点</span><span class="sxs-lookup"><span data-stu-id="bd87c-136">Network endpoints</span></span>

<span data-ttu-id="bd87c-137">设备能够访问多个关键 [终结点](network.md) ，以使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="bd87c-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bd87c-138">如果工具报告 **"未准备好"** 结果，请参阅详细报告，了解哪些终结点不可访问。</span><span class="sxs-lookup"><span data-stu-id="bd87c-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="bd87c-139">然后调整防火墙或其他网络设置，以确保可以到达这些终结点。</span><span class="sxs-lookup"><span data-stu-id="bd87c-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="bd87c-140">其他设置</span><span class="sxs-lookup"><span data-stu-id="bd87c-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="bd87c-141">企业 WI-fi 配置文件</span><span class="sxs-lookup"><span data-stu-id="bd87c-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="bd87c-142">公告 **结果** 意味着你正在使用某些需要证书和配置文件正常运行的 WLAN 配置文件。</span><span class="sxs-lookup"><span data-stu-id="bd87c-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="bd87c-143">有关详细信息，请参阅 [部署证书和 WI-Fi/VPN 配置文件](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。</span><span class="sxs-lookup"><span data-stu-id="bd87c-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="bd87c-144">LAN 配置文件</span><span class="sxs-lookup"><span data-stu-id="bd87c-144">LAN profiles</span></span>

<span data-ttu-id="bd87c-145">公告 **结果** 意味着你拥有需要证书和配置文件来正常工作的 LAN。</span><span class="sxs-lookup"><span data-stu-id="bd87c-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="bd87c-146">有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="bd87c-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="bd87c-147">VPN 配置文件</span><span class="sxs-lookup"><span data-stu-id="bd87c-147">VPN profiles</span></span>

<span data-ttu-id="bd87c-148">公告 **结果** 意味着你正在使用虚拟专用网络 (VPN) 。</span><span class="sxs-lookup"><span data-stu-id="bd87c-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="bd87c-149">创建部署与 Microsoft Intune 集成的证书的 VPN 配置文件。</span><span class="sxs-lookup"><span data-stu-id="bd87c-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="bd87c-150">有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="bd87c-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="bd87c-151">映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="bd87c-151">Mapped drives</span></span>

<span data-ttu-id="bd87c-152">公告 **结果** 意味着你有一些映射的驱动器，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="bd87c-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="bd87c-153">有关详细信息，请参阅准备 Microsoft 托管 [桌面的映射驱动器](mapped-drives.md)。</span><span class="sxs-lookup"><span data-stu-id="bd87c-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="bd87c-154">打印队列</span><span class="sxs-lookup"><span data-stu-id="bd87c-154">Print queues</span></span>

<span data-ttu-id="bd87c-155">公告 **结果** 意味着有一些未完成的打印队列，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="bd87c-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="bd87c-156">一个解决方案是使用云打印。</span><span class="sxs-lookup"><span data-stu-id="bd87c-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="bd87c-157">有关详细信息，请参阅准备 [Microsoft 托管桌面的打印资源](printing.md)。</span><span class="sxs-lookup"><span data-stu-id="bd87c-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="bd87c-158">代理</span><span class="sxs-lookup"><span data-stu-id="bd87c-158">Proxies</span></span>

<span data-ttu-id="bd87c-159">公告 **结果** 意味着您使用了代理服务器。</span><span class="sxs-lookup"><span data-stu-id="bd87c-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="bd87c-160">有关详细信息，请参阅 [Microsoft 托管桌面的网络配置](network.md)。</span><span class="sxs-lookup"><span data-stu-id="bd87c-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

