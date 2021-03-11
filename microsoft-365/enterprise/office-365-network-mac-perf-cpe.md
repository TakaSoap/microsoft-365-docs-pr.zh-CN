---
title: Microsoft 365 通知网络路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
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
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717596"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="a0a6c-103">Microsoft 365 通知网络路由 (预览) </span><span class="sxs-lookup"><span data-stu-id="a0a6c-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="a0a6c-104">通知网络路由是一项功能，可以将各种 Microsoft 365 应用程序与第三方软件定义的网络 (SD-WAN) 解决方案集成，以优化和改进与 Microsoft 服务终结点的网络连接。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="a0a6c-105">优化的 SD-WAN 连接可能会改善用户体验和性能。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a0a6c-106">Microsoft 365 通知网络路由当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="a0a6c-107">有关此预览的详细信息，包括接收协助的指导，请参阅 [Microsoft 365 通知网络路由公共预览版](https://go.microsoft.com/fwlink/?linkid=2151565)。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="a0a6c-108">概述</span><span class="sxs-lookup"><span data-stu-id="a0a6c-108">Overview</span></span>

<span data-ttu-id="a0a6c-109">通知网络路由在 Microsoft 和 SD-WAN 解决方案之间提供双向数据共享通道。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="a0a6c-110">对于您配置的每个办公室位置和 Internet 线路，Microsoft 会定期与 SD-WAN 解决方案共享有关与每个特定 Internet 电路关联的网络流量的选定 Microsoft 365 应用程序体验质量的反馈。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="a0a6c-111">使用此反馈，SD-WAN 解决方案随后可以通过通过备用可用链接路由 Microsoft 365 应用程序流量来采取智能恢复操作。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="a0a6c-112">很难持续检测特定 Internet 电路路径中的服务质量下降，例如延迟增加或数据包丢失率高。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="a0a6c-113">这些降级可能会对 Exchange Online、SharePoint、OneDrive 和 Microsoft Teams 等应用程序的用户体验产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="a0a6c-114">常见症状包括 Exchange 内容搜索缓慢、与 SharePoint 或 OneDrive 文档库交互时传输时间长，或者 Microsoft Teams 中的通话或会议质量差。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="a0a6c-115">网络通知路由中的反馈和恢复机制旨在以近实时方式动态检测此类问题，并通知部署的 SD-WAN 解决方案采取自动恢复操作。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="a0a6c-116">数据共享通道还用于定期从 SD-WAN 解决方案接收网络级别的光学数据，包括与设备和连接电路关联的配置信息和使用情况统计信息。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="a0a6c-117">不收集或存储任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-117">No personal information is collected or stored.</span></span> <span data-ttu-id="a0a6c-118">所有收集的信息将聚合到办公室位置和连接的 Internet 电路。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="a0a6c-119">此信息可帮助 Microsoft 更有效地解决使用 Microsoft 365 服务和应用程序时报告的问题。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="a0a6c-120">Microsoft 365 通知网络路由支持 WW 商业云中的租户，但不支持 GCC 中等、GCC 高、DoD、Germany 或中国云中的租户。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0a6c-121">要求</span><span class="sxs-lookup"><span data-stu-id="a0a6c-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="a0a6c-122">集成的 SD-WAN 解决方案</span><span class="sxs-lookup"><span data-stu-id="a0a6c-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="a0a6c-123">Microsoft 正在与各种合作伙伴合作，以实现与 Microsoft 365 通知网络路由的集成。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="a0a6c-124">当前启用的解决方案包括：</span><span class="sxs-lookup"><span data-stu-id="a0a6c-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="a0a6c-125">Device Maker</span><span class="sxs-lookup"><span data-stu-id="a0a6c-125">Device Maker</span></span> | <span data-ttu-id="a0a6c-126">解决方案名称</span><span class="sxs-lookup"><span data-stu-id="a0a6c-126">Solution Name</span></span> | <span data-ttu-id="a0a6c-127">最低版本</span><span class="sxs-lookup"><span data-stu-id="a0a6c-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a0a6c-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="a0a6c-128">Cisco</span></span> | [<span data-ttu-id="a0a6c-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="a0a6c-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="a0a6c-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="a0a6c-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="a0a6c-131">网络拓扑 </span><span class="sxs-lookup"><span data-stu-id="a0a6c-131">Network topology</span></span>

<span data-ttu-id="a0a6c-132">通知网络路由当前根据用于向 Microsoft 发送网络流量的公共 IP 地址标识与特定办公室位置和 Internet 电路关联的流量。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="a0a6c-133">如果分支位置没有至少一个提供直接 Internet 访问的网络电路，则网络通知路由可能不会提供显著价值。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="a0a6c-134">应用程序使用情况</span><span class="sxs-lookup"><span data-stu-id="a0a6c-134">Application usage</span></span>

<span data-ttu-id="a0a6c-135">应用程序体验 (通过网络质量指标) 通过特定 Microsoft 客户端应用程序收集。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-135">Application experience data (reflected through network quality metrics) is collected through usage of specific Microsoft client applications.</span></span> <span data-ttu-id="a0a6c-136">Exchange 指标反映 Outlook 客户端的使用情况以及一些Outlook Web App使用情况。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-136">Exchange metrics reflect usage of the Outlook client as well as some Outlook Web App usage.</span></span> <span data-ttu-id="a0a6c-137">SharePoint 和 OneDrive 指标反映特定于租户的 SharePoint 终结点的使用情况，而不考虑客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-137">SharePoint and OneDrive metrics reflect usage of the tenant-specific SharePoint endpoints, regardless of client application.</span></span> <span data-ttu-id="a0a6c-138">Teams 指标反映 Teams 桌面客户端的使用情况。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-138">Teams metrics reflect usage of the Teams desktop client.</span></span> <span data-ttu-id="a0a6c-139">在评估网络电路的运行状况时，不会考虑其他应用程序流量。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-139">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="a0a6c-140">启用通知网络路由</span><span class="sxs-lookup"><span data-stu-id="a0a6c-140">Enabling informed network routing</span></span>

<span data-ttu-id="a0a6c-141">启用智能网络路由需要多个步骤，其中一些步骤需要在 SD-WAN 解决方案的配置接口内执行。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-141">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="a0a6c-142">有关如何启动在 SD-WAN 解决方案中启用网络通知路由过程的指导，请咨询 SD-WAN 解决方案供应商，然后再在 Microsoft 365 管理中心继续配置。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-142">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="a0a6c-143">准备好在 Microsoft 365 管理中心启用通知网络路由后，请确保你拥有必要的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-143">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a0a6c-144">为了向选定的 SD-WAN 解决方案提供必要的租户级应用程序权限同意，以访问通知的网络路由数据共享通道，必须以全局管理员角色执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-144">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="a0a6c-145">步骤 1：打开 SD-WAN 解决方案配置选项</span><span class="sxs-lookup"><span data-stu-id="a0a6c-145">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="a0a6c-146">在 [Microsoft 365 管理中心](https://admin.microsoft.com/)， **选择>导航** 窗格中的"运行状况"和"网络连接"。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-146">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="a0a6c-147">管理中心的这一部分为组织提供聚合的网络连接指标，以及如何改进连接的指导。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-147">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="a0a6c-148">请参阅 [Microsoft 365 ](office-365-network-mac-perf-overview.md) 管理中心 (预览) 中的网络连接，了解管理中心内提供的这些功能的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-148">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="a0a6c-149">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span><span class="sxs-lookup"><span data-stu-id="a0a6c-149">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="a0a6c-150">"设置"下显示的其他选项适用于管理中心中的一般网络连接指南，不需要启用通知网络路由。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-150">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="a0a6c-151">在配置窗格中，选择"将 **SD-WAN 解决方案 (预览) 。**</span><span class="sxs-lookup"><span data-stu-id="a0a6c-151">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="a0a6c-152">步骤 2：选择 SD-WAN 解决方案和数据存储位置</span><span class="sxs-lookup"><span data-stu-id="a0a6c-152">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="a0a6c-153">在下拉列表中，选择已部署的 SD-WAN 解决方案以及要存储与网络通知路由关联的数据的位置。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-153">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="a0a6c-154">有关 [其他信息，](#data-storage) 请参阅数据存储部分。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-154">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="a0a6c-155">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-155">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="a0a6c-156">步骤 3：接受数据共享条款</span><span class="sxs-lookup"><span data-stu-id="a0a6c-156">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="a0a6c-157">仔细阅读并确认提供的与 Microsoft 和所选 SD-WAN 解决方案之间共享数据相关的条款，然后选择指示的复选框。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-157">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="a0a6c-158">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-158">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="a0a6c-159">步骤 4：向 SD-WAN 解决方案授予权限</span><span class="sxs-lookup"><span data-stu-id="a0a6c-159">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="a0a6c-160">此步骤将启动 Azure Active Directory 和 Azure AD (的权限) 。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-160">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a0a6c-161">将请求授予租户级别权限，以允许所选 SD-WAN 解决方案访问与租户关联的通知网络路由数据存储和服务运行状况信息。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-161">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="a0a6c-162">此操作需要全局管理员角色权限。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-162">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="a0a6c-163">选择 **此应用程序链接的"授予** 权限"，然后遵循 Azure AD 请求。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-163">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="a0a6c-164">完成权限授予后，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a0a6c-164">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="a0a6c-165">步骤 5：确认配置设置</span><span class="sxs-lookup"><span data-stu-id="a0a6c-165">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="a0a6c-166">为租户启用网络通知路由的最后一步是显示你提供的设置的确认页面。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-166">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="a0a6c-167">现在为租户启用了通知网络路由。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-167">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="a0a6c-168">选择 **"** 完成"，然后关闭 SD-WAN 解决方案配置窗格。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-168">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="a0a6c-169">配置网络通知路由</span><span class="sxs-lookup"><span data-stu-id="a0a6c-169">Configuring network informed routing</span></span>

<span data-ttu-id="a0a6c-170">您将在 SD-WAN 解决方案中为通知网络路由执行大部分配置，例如配置在正常情况下应该如何路由流量，以及检测到问题时应该使用的备用路径。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-170">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="a0a6c-171">有关这些配置步骤的详细信息，请咨询您的 SD-WAN 解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-171">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="a0a6c-172">必须在 Microsoft 365 管理中心中配置每个办公室位置，以便智能网络路由可以正确标识与提供这些位置连接的网络电路相关的流量。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-172">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="a0a6c-173">Office 位置可能会自动检测为 Microsoft 正在进行的网络遥测集合的一部分。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-173">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="a0a6c-174">因此，某些位置可能会预先填充在租户的管理中心中。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-174">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="a0a6c-175">如果这些位置准确，则只需为每个所需位置启用通知网络路由功能，并配置 Internet 线路及其公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-175">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="a0a6c-176">如果自动检测的位置不准确，或者租户中没有预填充的位置，您必须手动添加或编辑位置以反映组织的准确拓扑。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-176">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="a0a6c-177">更新位置</span><span class="sxs-lookup"><span data-stu-id="a0a6c-177">Updating locations</span></span>

<span data-ttu-id="a0a6c-178">可以在"位置"选项卡下找到 **租户的位置。** 可以直接在列表中编辑位置，或者使用 CSV 文件更新位置。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-178">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="a0a6c-179">确保要启用通知网络路由的每个办公室位置都位于此列表中。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-179">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="a0a6c-180">收集的示例 **和其他** 评估相关信息的位置列表中的列与通知网络路由功能不相关。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-180">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="a0a6c-181">为智能网络路由启用位置</span><span class="sxs-lookup"><span data-stu-id="a0a6c-181">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="a0a6c-182">在 **"位置"** 列表中，从快速操作菜单中选择"编辑"以打开位置配置窗格。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-182">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="a0a6c-183">选择 **在此位置使用 Microsoft 365 通知网络路由**。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-183">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="a0a6c-184">在此办公室位置部分"出口 IP 地址范围"中添加提供 Internet 连接的所有网络电路到此 **办公室** 位置。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-184">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="a0a6c-185">确保每个电路与表示网络流量的唯一公用 IP 地址子网关联。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-185">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="a0a6c-186">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-186">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="a0a6c-187">禁用网络通知路由</span><span class="sxs-lookup"><span data-stu-id="a0a6c-187">Disabling network informed routing</span></span>

<span data-ttu-id="a0a6c-188">通过重置 SD-WAN 解决方案设置，可能会为整个租户禁用通知网络路由功能。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-188">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="a0a6c-189">虽然这将停止 Microsoft 365 内的所有数据处理，但还应在管理中心内禁用网络通知路由。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-189">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="a0a6c-190">步骤 1：打开 SD-WAN 解决方案配置选项</span><span class="sxs-lookup"><span data-stu-id="a0a6c-190">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="a0a6c-191">在 [Microsoft 365 管理](https://admin.microsoft.com/) 中心，> **导航** 窗格中选择"运行状况"和"网络连接"。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-191">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="a0a6c-192">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span><span class="sxs-lookup"><span data-stu-id="a0a6c-192">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="a0a6c-193">配置窗格显示当前配置的 SD-WAN 解决方案的摘要。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-193">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="a0a6c-194">步骤 2：重置配置</span><span class="sxs-lookup"><span data-stu-id="a0a6c-194">Step 2: Reset your configuration</span></span>

<span data-ttu-id="a0a6c-195">在配置窗格中，选择"**重置 SD-WAN 解决方案设置"。**</span><span class="sxs-lookup"><span data-stu-id="a0a6c-195">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="a0a6c-196">现在，已重置设置，并且已禁用通知网络路由。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-196">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="a0a6c-197">可以通过按照启用通知网络路由 [中的步骤随时重新启用它](#enabling-informed-network-routing)。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-197">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="a0a6c-198">数据存储</span><span class="sxs-lookup"><span data-stu-id="a0a6c-198">Data storage</span></span>

<span data-ttu-id="a0a6c-199">Microsoft 与 SD-WAN 解决方案提供商之间交换的数据存储在初始启用网络通知路由期间所选的数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-199">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="a0a6c-200">数据存储位置选项表示包含存储数据的 Microsoft Azure 区域的地理区域。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-200">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="a0a6c-201">在预览阶段，唯一可用的数据存储位置是 **北美**。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-201">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="a0a6c-202">在通知网络路由的一般可用之前，其他数据存储位置将变为可用位置。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-202">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="a0a6c-203">数据将在此位置保留最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-203">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="a0a6c-204">禁用后，将在此 30 天保留时段内删除所有剩余数据。</span><span class="sxs-lookup"><span data-stu-id="a0a6c-204">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0a6c-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0a6c-205">Related topics</span></span>

[<span data-ttu-id="a0a6c-206">Microsoft 365 管理中心中的网络连接 (预览) </span><span class="sxs-lookup"><span data-stu-id="a0a6c-206">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="a0a6c-207">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="a0a6c-207">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
