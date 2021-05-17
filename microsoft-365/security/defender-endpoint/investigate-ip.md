---
title: 调查与警报关联的 IP 地址
description: 使用调查选项检查设备和外部 IP 地址之间可能的通信。
keywords: 调查， 调查， IP 地址， 警报， Microsoft Defender for Endpoint， 外部 IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933825"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="cc26a-104">调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cc26a-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cc26a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="cc26a-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc26a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc26a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc26a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc26a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cc26a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="cc26a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc26a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="cc26a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="cc26a-110">检查你的设备和外部 Internet 协议与 IP 地址 () 通信。</span><span class="sxs-lookup"><span data-stu-id="cc26a-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="cc26a-111">标识组织中与可疑或已知的恶意 IP 地址通信的所有设备，如命令和控制 (C2) 服务器，有助于确定潜在的泄露范围、关联文件和受感染的设备。</span><span class="sxs-lookup"><span data-stu-id="cc26a-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="cc26a-112">您可以在 IP 地址视图中的以下部分中查找信息：</span><span class="sxs-lookup"><span data-stu-id="cc26a-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="cc26a-113">全球 IP</span><span class="sxs-lookup"><span data-stu-id="cc26a-113">IP worldwide</span></span>
- <span data-ttu-id="cc26a-114">反向 DNS 名称</span><span class="sxs-lookup"><span data-stu-id="cc26a-114">Reverse DNS names</span></span>
- <span data-ttu-id="cc26a-115">与此 IP 相关的警报</span><span class="sxs-lookup"><span data-stu-id="cc26a-115">Alerts related to this IP</span></span>
- <span data-ttu-id="cc26a-116">组织中 IP</span><span class="sxs-lookup"><span data-stu-id="cc26a-116">IP in organization</span></span>
- <span data-ttu-id="cc26a-117">普遍程度</span><span class="sxs-lookup"><span data-stu-id="cc26a-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="cc26a-118">IP 全球和反向 DNS 名称</span><span class="sxs-lookup"><span data-stu-id="cc26a-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="cc26a-119">"IP 地址详细信息"部分显示 IP 地址的属性，如其 ASN 及其反向 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="cc26a-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="cc26a-120">与此 IP 相关的警报</span><span class="sxs-lookup"><span data-stu-id="cc26a-120">Alerts related to this IP</span></span>

<span data-ttu-id="cc26a-121">" **与此 IP 相关的警报** "部分提供了与该 IP 关联的警报列表。</span><span class="sxs-lookup"><span data-stu-id="cc26a-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="cc26a-122">组织中 IP</span><span class="sxs-lookup"><span data-stu-id="cc26a-122">IP in organization</span></span>

<span data-ttu-id="cc26a-123">" **组织中的 IP"** 部分提供有关组织中 IP 地址的普遍程度的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc26a-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="cc26a-124">普遍程度</span><span class="sxs-lookup"><span data-stu-id="cc26a-124">Prevalence</span></span>

<span data-ttu-id="cc26a-125">" **普遍** 程度"部分显示已连接到此 IP 地址的设备数，以及第一次和最后一次看到 IP 时。</span><span class="sxs-lookup"><span data-stu-id="cc26a-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="cc26a-126">可以按时间段筛选此部分的结果;默认期限为 30 天。</span><span class="sxs-lookup"><span data-stu-id="cc26a-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="cc26a-127">最新观察到的具有 IP 的设备</span><span class="sxs-lookup"><span data-stu-id="cc26a-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="cc26a-128">" **最新观察到** 的具有 IP 的设备"部分提供有关在 IP 地址上观测到的事件和关联警报按时间顺序排列的视图。</span><span class="sxs-lookup"><span data-stu-id="cc26a-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="cc26a-129">**调查外部 IP：**</span><span class="sxs-lookup"><span data-stu-id="cc26a-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="cc26a-130">从搜索栏 **下拉菜单中选择** **IP。**</span><span class="sxs-lookup"><span data-stu-id="cc26a-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="cc26a-131">在"搜索"字段中 **输入** IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cc26a-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="cc26a-132">单击搜索图标或按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="cc26a-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="cc26a-133">将显示有关 IP 地址的详细信息，包括：注册详细信息 (（如果) 可用、反向 IP (例如域) 、在可选择的时间段) 内与此 IP 地址 (通信的组织中设备的普遍程度，以及组织中观测到与此 IP 地址通信的设备。</span><span class="sxs-lookup"><span data-stu-id="cc26a-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="cc26a-134">将仅返回与组织中设备通信时观察到的 IP 地址的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="cc26a-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="cc26a-135">使用搜索筛选器定义搜索条件。</span><span class="sxs-lookup"><span data-stu-id="cc26a-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="cc26a-136">您还可以使用时间线搜索框筛选组织中观测到与 IP 地址通信的所有设备的显示结果、与通信关联的文件和上次观测到的日期。</span><span class="sxs-lookup"><span data-stu-id="cc26a-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="cc26a-137">单击任何设备名称将进入该设备的视图，你可以继续调查报告的警报、行为和事件。</span><span class="sxs-lookup"><span data-stu-id="cc26a-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc26a-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="cc26a-138">Related topics</span></span>

- [<span data-ttu-id="cc26a-139">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="cc26a-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="cc26a-140">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="cc26a-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="cc26a-141">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="cc26a-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="cc26a-142">调查与 Microsoft Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="cc26a-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="cc26a-143">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="cc26a-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="cc26a-144">调查与 Microsoft Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="cc26a-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="cc26a-145">调查 Microsoft Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="cc26a-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
