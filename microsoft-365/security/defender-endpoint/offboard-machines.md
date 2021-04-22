---
title: 从 Microsoft Defender for Endpoint 服务载出设备
description: 从 Microsoft Defender for Endpoint 服务载入 Windows 10 设备、服务器和非 Windows 设备
keywords: offboarding， Microsoft Defender for Endpoint offboarding， offboarding
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934149"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="c179b-104">从 Microsoft Defender for Endpoint 服务载出设备</span><span class="sxs-lookup"><span data-stu-id="c179b-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c179b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c179b-105">**Applies to:**</span></span>
- [<span data-ttu-id="c179b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c179b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c179b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c179b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c179b-108">**平台**</span><span class="sxs-lookup"><span data-stu-id="c179b-108">**Platforms**</span></span>
- <span data-ttu-id="c179b-109">macOS</span><span class="sxs-lookup"><span data-stu-id="c179b-109">macOS</span></span>
- <span data-ttu-id="c179b-110">Linux</span><span class="sxs-lookup"><span data-stu-id="c179b-110">Linux</span></span>
- <span data-ttu-id="c179b-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c179b-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="c179b-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c179b-112">Windows Server 2016</span></span>

><span data-ttu-id="c179b-113">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="c179b-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c179b-114">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c179b-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="c179b-115">按照相应说明进行操作，具体取决于你的首选部署方法。</span><span class="sxs-lookup"><span data-stu-id="c179b-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="c179b-116">在载出 7 天后，设备[](fix-unhealthy-sensors.md#inactive-devices)的状态将切换到非活动状态。</span><span class="sxs-lookup"><span data-stu-id="c179b-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="c179b-117">已载出设备的数据 (时间线、警报、漏洞等) 将保留在门户中，直到配置的保留[期过期。](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="c179b-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="c179b-118">不带数据 (设备配置文件) 将在设备 [列表中](machines-view-overview.md) 保留不超过 180 天。</span><span class="sxs-lookup"><span data-stu-id="c179b-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="c179b-119">此外，过去 30 天内未处于活动状态的设备不会在反映组织的威胁和漏洞管理曝光分数和 Microsoft 设备安全分数的数据中考虑。 [](tvm-exposure-score.md)</span><span class="sxs-lookup"><span data-stu-id="c179b-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="c179b-120">若要仅查看活动设备，可以按运行状况 [状态](machines-view-overview.md#health-state)、 [设备标记](machine-tags.md) 或计算机 [组进行筛选](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="c179b-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="c179b-121">载出 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="c179b-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="c179b-122">使用本地脚本的载出设备</span><span class="sxs-lookup"><span data-stu-id="c179b-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="c179b-123">使用组策略的载出设备</span><span class="sxs-lookup"><span data-stu-id="c179b-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="c179b-124">使用移动设备管理工具的载出设备</span><span class="sxs-lookup"><span data-stu-id="c179b-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="c179b-125">载出服务器</span><span class="sxs-lookup"><span data-stu-id="c179b-125">Offboard Servers</span></span>
- [<span data-ttu-id="c179b-126">载出服务器</span><span class="sxs-lookup"><span data-stu-id="c179b-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="c179b-127">载出非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="c179b-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="c179b-128">载出非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="c179b-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

