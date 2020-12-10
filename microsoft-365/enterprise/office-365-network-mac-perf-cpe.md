---
title: Microsoft 365 通知网络路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 通知网络路由
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611432"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="c32fb-103">Microsoft 365 通知网络路由 (预览) </span><span class="sxs-lookup"><span data-stu-id="c32fb-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="c32fb-104">已通知网络路由是一项功能，可将各种 Microsoft 365 应用程序集成到第三方软件定义的网络 (SD WAN) 解决方案中，以优化和改进与 Microsoft 服务终结点的网络连接。</span><span class="sxs-lookup"><span data-stu-id="c32fb-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="c32fb-105">优化的 SD WAN 连接可能会导致用户体验和性能提高。</span><span class="sxs-lookup"><span data-stu-id="c32fb-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c32fb-106">Microsoft 365 通知网络路由当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="c32fb-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="c32fb-107">有关此预览的详细信息，包括接收帮助的指南，请参阅 [Microsoft 365 通知网络路由公共预览版](https://go.microsoft.com/fwlink/?linkid=2151565)。</span><span class="sxs-lookup"><span data-stu-id="c32fb-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="c32fb-108">概述</span><span class="sxs-lookup"><span data-stu-id="c32fb-108">Overview</span></span>

<span data-ttu-id="c32fb-109">已通知网络路由在 Microsoft 与您的 SD WAN 解决方案之间提供双向数据共享通道。</span><span class="sxs-lookup"><span data-stu-id="c32fb-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="c32fb-110">对于您配置的每个办公室位置和 Internet 电路，Microsoft 会定期与在所选 Microsoft 365 应用程序体验的质量上，与每个特定 Internet 电路相关联的网络流量与 SD WAN 解决方案共享反馈。</span><span class="sxs-lookup"><span data-stu-id="c32fb-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="c32fb-111">通过此反馈，SD WAN 解决方案可以通过使用可替换的可用链接来路由 Microsoft 365 应用程序流量，从而执行智能恢复操作。</span><span class="sxs-lookup"><span data-stu-id="c32fb-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="c32fb-112">特定 Internet 电路（如增加的延迟或高数据包丢失）的路径中的服务质量降低很难连续检测。</span><span class="sxs-lookup"><span data-stu-id="c32fb-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="c32fb-113">这些降低可能会对 Exchange Online、SharePoint、OneDrive 和 Microsoft 团队等应用程序的用户体验产生不利的损害。</span><span class="sxs-lookup"><span data-stu-id="c32fb-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="c32fb-114">常见症状包括对 Exchange 内容的搜索速度较慢、在与 SharePoint 或 OneDrive 文档库交互或 Microsoft 团队中的通话或会议质量较差时的传输时间较高。</span><span class="sxs-lookup"><span data-stu-id="c32fb-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="c32fb-115">网络中的反馈和恢复机制通知路由旨在实时动态检测此类问题，并通知部署的 SD WAN 解决方案执行自动恢复操作。</span><span class="sxs-lookup"><span data-stu-id="c32fb-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="c32fb-116">数据共享通道还可用于定期接收 SD WAN 解决方案中的网络级光学数据，包括与设备和附加电路相关联的配置信息和使用情况统计信息。</span><span class="sxs-lookup"><span data-stu-id="c32fb-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="c32fb-117">不会收集或存储任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="c32fb-117">No personal information is collected or stored.</span></span> <span data-ttu-id="c32fb-118">所有收集的信息都聚合到办公室位置和连接的 Internet 电路中。</span><span class="sxs-lookup"><span data-stu-id="c32fb-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="c32fb-119">此信息可以帮助 Microsoft 更高效地解决使用 Microsoft 365 服务和应用程序时报告的问题。</span><span class="sxs-lookup"><span data-stu-id="c32fb-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="c32fb-120">Microsoft 365 通知网络路由支持 WW 商业云中的租户，但不支持 GCC 中级、GCC 高、DoD、德国或中国云。</span><span class="sxs-lookup"><span data-stu-id="c32fb-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="c32fb-121">Requirements</span><span class="sxs-lookup"><span data-stu-id="c32fb-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="c32fb-122">集成的 SD 广域网解决方案</span><span class="sxs-lookup"><span data-stu-id="c32fb-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="c32fb-123">Microsoft 正在与各种合作伙伴合作，以实现与 Microsoft 365 的网络路由的集成。</span><span class="sxs-lookup"><span data-stu-id="c32fb-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="c32fb-124">当前启用的解决方案包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="c32fb-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="c32fb-125">设备生成器</span><span class="sxs-lookup"><span data-stu-id="c32fb-125">Device Maker</span></span> | <span data-ttu-id="c32fb-126">解决方案名称</span><span class="sxs-lookup"><span data-stu-id="c32fb-126">Solution Name</span></span> | <span data-ttu-id="c32fb-127">最低版本</span><span class="sxs-lookup"><span data-stu-id="c32fb-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c32fb-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="c32fb-128">Cisco</span></span> | [<span data-ttu-id="c32fb-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="c32fb-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="c32fb-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="c32fb-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="c32fb-131">网络拓扑 </span><span class="sxs-lookup"><span data-stu-id="c32fb-131">Network topology</span></span>

<span data-ttu-id="c32fb-132">已通知网络路由当前根据用于向 Microsoft 发送网络流量的公用 IP 地址来标识与特定办公室位置和 Internet 电路相关联的流量。</span><span class="sxs-lookup"><span data-stu-id="c32fb-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="c32fb-133">如果没有至少一条网络电路在分支机构提供直接 Internet 访问，则网络通知路由可能不会提供显著价值。</span><span class="sxs-lookup"><span data-stu-id="c32fb-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="c32fb-134">应用程序使用</span><span class="sxs-lookup"><span data-stu-id="c32fb-134">Application usage</span></span>

<span data-ttu-id="c32fb-135">通过在运行 Windows、团队、SharePoint 和 OneDrive 的设备上使用 Microsoft Outlook，在网络质量指标) 中反映的应用程序体验数据 (。</span><span class="sxs-lookup"><span data-stu-id="c32fb-135">Application experience data (reflected through network quality metrics) is collected through usage of Microsoft Outlook on devices running Windows, Teams, SharePoint, and OneDrive.</span></span> <span data-ttu-id="c32fb-136">评估网络电路的运行状况时不会考虑其他应用程序通信。</span><span class="sxs-lookup"><span data-stu-id="c32fb-136">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="c32fb-137">启用通知的网络路由</span><span class="sxs-lookup"><span data-stu-id="c32fb-137">Enabling informed network routing</span></span>

<span data-ttu-id="c32fb-138">启用通知网络路由需要多个步骤，其中一些步骤将需要在您的 SD WAN 解决方案的配置界面中执行。</span><span class="sxs-lookup"><span data-stu-id="c32fb-138">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="c32fb-139">请咨询您的 SD WAN 解决方案供应商，以获取有关如何启动在 SD WAN 解决方案内启用网络通知路由的过程的指南，然后再继续使用 Microsoft 365 管理中心中的配置。</span><span class="sxs-lookup"><span data-stu-id="c32fb-139">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="c32fb-140">准备好在 Microsoft 365 管理中心中启用已通知的网络路由后，请确保您具有必要的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="c32fb-140">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c32fb-141">为了提供所需的租户级应用程序权限，为所选的 SD WAN 解决方案访问已通知的网络路由数据共享频道，必须以全局管理员身份执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="c32fb-141">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="c32fb-142">步骤1：打开 SD-WAN 解决方案配置选项</span><span class="sxs-lookup"><span data-stu-id="c32fb-142">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="c32fb-143">在 [Microsoft 365 管理中心](https://admin.microsoft.com/)，在左侧导航窗格中选择 " **运行状况 > 网络连接** "。</span><span class="sxs-lookup"><span data-stu-id="c32fb-143">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="c32fb-144">本管理中心的这一部分为您的组织提供聚合网络连接指标，并提供有关如何提高连接性的指导。</span><span class="sxs-lookup"><span data-stu-id="c32fb-144">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="c32fb-145">有关管理员中心中提供的这些功能的其他信息，请参阅 [Microsoft 365 管理中心中的网络连接 (预览) ](office-365-network-mac-perf-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="c32fb-145">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="c32fb-146">选择 " **设置" > "SD WAN 解决方案** " 以打开 "已通知的网络路由配置" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c32fb-146">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="c32fb-147">" **设置** " 下显示的其他选项适用于 "管理中心" 中的常规网络连接指南，无需启用通知网络路由。</span><span class="sxs-lookup"><span data-stu-id="c32fb-147">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="c32fb-148">在 "配置" 窗格中，选择 " **添加您的 SD-WAN 解决方案 (预览)**"。</span><span class="sxs-lookup"><span data-stu-id="c32fb-148">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="c32fb-149">步骤2：选择您的 SD WAN 解决方案和数据存储位置</span><span class="sxs-lookup"><span data-stu-id="c32fb-149">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="c32fb-150">在下拉框中，选择已部署的 SD WAN 解决方案，以及希望将与网络通知路由相关联的数据存储到的位置。</span><span class="sxs-lookup"><span data-stu-id="c32fb-150">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="c32fb-151">有关其他信息，请参阅 " [数据存储](#data-storage) " 部分。</span><span class="sxs-lookup"><span data-stu-id="c32fb-151">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="c32fb-152">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="c32fb-152">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="c32fb-153">步骤3：接受数据共享的条款</span><span class="sxs-lookup"><span data-stu-id="c32fb-153">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="c32fb-154">仔细阅读并确认与在 Microsoft 和所选的 SD WAN 解决方案之间共享数据相关联的提供的术语，然后选择指示的复选框。</span><span class="sxs-lookup"><span data-stu-id="c32fb-154">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="c32fb-155">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="c32fb-155">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="c32fb-156">步骤4：授予对 SD WAN 解决方案的权限</span><span class="sxs-lookup"><span data-stu-id="c32fb-156">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="c32fb-157">此步骤将启动 Azure Active Directory (Azure AD) 的权限授予请求。</span><span class="sxs-lookup"><span data-stu-id="c32fb-157">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c32fb-158">你将被请求授予租户级权限，这些权限允许你所选的 SD WAN 解决方案访问已通知的网络路由数据存储和与你的租户关联的服务运行状况信息。</span><span class="sxs-lookup"><span data-stu-id="c32fb-158">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="c32fb-159">此操作需要全局管理员角色权限。</span><span class="sxs-lookup"><span data-stu-id="c32fb-159">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="c32fb-160">选择 " **授予对此应用程序的权限** " 链接并遵循 Azure AD 请求。</span><span class="sxs-lookup"><span data-stu-id="c32fb-160">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="c32fb-161">完成权限授予后，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c32fb-161">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="c32fb-162">步骤5：确认配置设置</span><span class="sxs-lookup"><span data-stu-id="c32fb-162">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="c32fb-163">为租户启用网络通知的路由的最后一步是显示你提供的设置的确认页。</span><span class="sxs-lookup"><span data-stu-id="c32fb-163">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="c32fb-164">现已为你的租户启用通知网络路由。</span><span class="sxs-lookup"><span data-stu-id="c32fb-164">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="c32fb-165">选择 " **完成** "，然后关闭 "SD-WAN 解决方案配置" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c32fb-165">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="c32fb-166">配置网络通知路由</span><span class="sxs-lookup"><span data-stu-id="c32fb-166">Configuring network informed routing</span></span>

<span data-ttu-id="c32fb-167">您将在您的 SD WAN 解决方案中对已通知的网络路由执行大量配置，例如在正常情况下配置流量应如何路由以及在检测到问题时应使用的备用路径。</span><span class="sxs-lookup"><span data-stu-id="c32fb-167">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="c32fb-168">有关这些配置步骤的详细信息，请参阅 SD WAN 解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="c32fb-168">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="c32fb-169">每个办公室位置必须在 Microsoft 365 管理中心中进行配置，以便有通知的网络路由能够正确识别与网络电路相关联的通信，从而实现这些位置的连接。</span><span class="sxs-lookup"><span data-stu-id="c32fb-169">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="c32fb-170">在 Microsoft 正在进行的网络遥测集合中，可能会自动检测到办公室位置。</span><span class="sxs-lookup"><span data-stu-id="c32fb-170">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="c32fb-171">因此，某些位置可能在你的租户的管理中心内预先填充。</span><span class="sxs-lookup"><span data-stu-id="c32fb-171">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="c32fb-172">如果这些位置是准确的，则只需为每个所需位置启用已通知的网络路由功能，并配置 Internet 线路及其公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c32fb-172">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="c32fb-173">如果自动检测到的位置不准确，或者在租户中没有预先填充的位置，则必须手动添加或编辑位置，以反映组织的准确拓扑。</span><span class="sxs-lookup"><span data-stu-id="c32fb-173">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="c32fb-174">更新位置</span><span class="sxs-lookup"><span data-stu-id="c32fb-174">Updating locations</span></span>

<span data-ttu-id="c32fb-175">可以在 " **位置** " 选项卡下找到租户的位置。位置可以直接在列表中编辑或使用 CSV 文件进行更新。</span><span class="sxs-lookup"><span data-stu-id="c32fb-175">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="c32fb-176">确保在此列表中存在要在其上启用通知网络路由的每个办公室位置。</span><span class="sxs-lookup"><span data-stu-id="c32fb-176">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="c32fb-177">收集的样本和其他与评估相关的信息的 **位置** 列表中的列与通知的网络路由功能无关。</span><span class="sxs-lookup"><span data-stu-id="c32fb-177">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="c32fb-178">为已通知的网络路由启用位置</span><span class="sxs-lookup"><span data-stu-id="c32fb-178">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="c32fb-179">在 " **位置** " 列表中，从 "快速操作" 菜单中选择 " **编辑** " 以打开 "位置配置" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c32fb-179">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="c32fb-180">选择 " **在此位置使用 Microsoft 365 通知网络路由**"。</span><span class="sxs-lookup"><span data-stu-id="c32fb-180">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="c32fb-181">在此 "办公室位置" 部分的 " **传出 IP 地址范围** " 中，添加所有提供到此办公室位置的 Internet 连接的网络电路。</span><span class="sxs-lookup"><span data-stu-id="c32fb-181">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="c32fb-182">确保每个电路都与代表网络流量的唯一公共 IP 地址子网相关联。</span><span class="sxs-lookup"><span data-stu-id="c32fb-182">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="c32fb-183">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c32fb-183">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="c32fb-184">禁用网络通知路由</span><span class="sxs-lookup"><span data-stu-id="c32fb-184">Disabling network informed routing</span></span>

<span data-ttu-id="c32fb-185">通过重置您的 SD-WAN 解决方案设置，可能会对整个租户禁用已通知的网络路由功能。</span><span class="sxs-lookup"><span data-stu-id="c32fb-185">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="c32fb-186">虽然这会在 Microsoft 365 中停止对数据的所有处理，但您还应禁用管理中心内的网络通知路由。</span><span class="sxs-lookup"><span data-stu-id="c32fb-186">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="c32fb-187">步骤1：打开 SD-WAN 解决方案配置选项</span><span class="sxs-lookup"><span data-stu-id="c32fb-187">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="c32fb-188">在 [Microsoft 365 管理中心](https://admin.microsoft.com/) 中，在左侧导航窗格中选择 " **运行状况 > 网络连接** "。</span><span class="sxs-lookup"><span data-stu-id="c32fb-188">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="c32fb-189">选择 " **设置" > "SD WAN 解决方案** " 以打开 "已通知的网络路由配置" 窗格。</span><span class="sxs-lookup"><span data-stu-id="c32fb-189">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="c32fb-190">配置窗格显示当前配置的 SD WAN 解决方案的摘要。</span><span class="sxs-lookup"><span data-stu-id="c32fb-190">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="c32fb-191">步骤2：重置配置</span><span class="sxs-lookup"><span data-stu-id="c32fb-191">Step 2: Reset your configuration</span></span>

<span data-ttu-id="c32fb-192">在 "配置" 窗格中，选择 " **重置您的 SD-WAN 解决方案设置**"。</span><span class="sxs-lookup"><span data-stu-id="c32fb-192">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="c32fb-193">你的设置现在已重置并通知网络路由已禁用。</span><span class="sxs-lookup"><span data-stu-id="c32fb-193">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="c32fb-194">您可以随时重新启用它，方法是按照 [启用通知的网络路由](#enabling-informed-network-routing)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c32fb-194">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="c32fb-195">数据存储</span><span class="sxs-lookup"><span data-stu-id="c32fb-195">Data storage</span></span>

<span data-ttu-id="c32fb-196">在 Microsoft 和 SD WAN 解决方案提供商之间交换的数据存储在最初启用网络通知路由的过程中所选的数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="c32fb-196">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="c32fb-197">数据存储位置选项表示包含存储数据的 Microsoft Azure 区域的地理区域。</span><span class="sxs-lookup"><span data-stu-id="c32fb-197">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="c32fb-198">在预览阶段，仅适用 **于北美的** 数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="c32fb-198">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="c32fb-199">在有通知的网络路由的常规可用性之前，其他数据存储位置将变为可用状态。</span><span class="sxs-lookup"><span data-stu-id="c32fb-199">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="c32fb-200">数据在此位置保留最长30天。</span><span class="sxs-lookup"><span data-stu-id="c32fb-200">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="c32fb-201">在禁用此功能时，将在此30天保留时段内删除所有剩余数据。</span><span class="sxs-lookup"><span data-stu-id="c32fb-201">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c32fb-202">相关主题</span><span class="sxs-lookup"><span data-stu-id="c32fb-202">Related topics</span></span>

[<span data-ttu-id="c32fb-203">Microsoft 365 管理中心中的网络连接 (预览版) </span><span class="sxs-lookup"><span data-stu-id="c32fb-203">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="c32fb-204">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="c32fb-204">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
