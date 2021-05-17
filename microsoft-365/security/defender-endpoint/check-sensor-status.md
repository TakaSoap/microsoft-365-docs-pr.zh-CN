---
title: 在 Microsoft Defender for Endpoint 中检查传感器的运行状况
description: 检查设备的传感器运行状况，以确定哪些设备配置不正确、处于非活动状态或未报告传感器数据。
keywords: 传感器， 传感器运行状况， 错误配置， 非活动， 无传感器数据， 传感器数据， 通信受损， 通信
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904160"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="37580-104">检查 Microsoft Defender for Endpoint 中的传感器运行状况</span><span class="sxs-lookup"><span data-stu-id="37580-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37580-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="37580-105">**Applies to:**</span></span>
- [<span data-ttu-id="37580-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37580-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37580-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37580-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="37580-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="37580-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37580-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="37580-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="37580-110">" **具有传感器问题的设备"** 磁贴位于安全操作仪表板上。</span><span class="sxs-lookup"><span data-stu-id="37580-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="37580-111">此磁贴提供有关单个设备提供传感器数据并与 Defender for Endpoint 服务通信的能力的信息。</span><span class="sxs-lookup"><span data-stu-id="37580-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="37580-112">它报告需要关注的设备数，并帮助你识别有问题的设备并采取措施纠正已知问题。</span><span class="sxs-lookup"><span data-stu-id="37580-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="37580-113">磁贴上有两个状态指示器，它们提供有关未正确报告给服务的设备数量的信息：</span><span class="sxs-lookup"><span data-stu-id="37580-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="37580-114">**配置错误** - 这些设备可能部分向 Defender for Endpoint 服务报告传感器数据，并且可能有需要更正的配置错误。</span><span class="sxs-lookup"><span data-stu-id="37580-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="37580-115">**非** 活动 - 在过去一个月内停止向 Defender for Endpoint 服务报告超过七天的设备。</span><span class="sxs-lookup"><span data-stu-id="37580-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="37580-116">单击任何组将你引导到 **设备列表**，该列表根据你的选择进行筛选。</span><span class="sxs-lookup"><span data-stu-id="37580-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![具有传感器问题的设备的屏幕截图磁贴](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="37580-118">在 **"设备"** 列表上，可以按以下状态筛选运行状况列表：</span><span class="sxs-lookup"><span data-stu-id="37580-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="37580-119">**Active** - 主动向 Defender for Endpoint 服务报告的设备。</span><span class="sxs-lookup"><span data-stu-id="37580-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="37580-120">**错误配置** - 这些设备可能部分向 Defender for Endpoint 服务报告传感器数据，但具有需要更正的配置错误。</span><span class="sxs-lookup"><span data-stu-id="37580-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="37580-121">配置错误的设备可能具有以下一个问题或以下问题的组合：</span><span class="sxs-lookup"><span data-stu-id="37580-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="37580-122">**无传感器数据** - 设备已停止发送传感器数据。</span><span class="sxs-lookup"><span data-stu-id="37580-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="37580-123">可以从设备触发有限警报。</span><span class="sxs-lookup"><span data-stu-id="37580-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="37580-124">**通信受损** - 与设备通信的能力受损。</span><span class="sxs-lookup"><span data-stu-id="37580-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="37580-125">发送文件进行深入分析、阻止文件、将设备与网络隔离以及需要与设备通信的其他操作可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="37580-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="37580-126">**非** 活动 - 停止向 Defender for Endpoint 服务报告的设备。</span><span class="sxs-lookup"><span data-stu-id="37580-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="37580-127">您还可以使用导出功能以 CSV 格式下载 **整个** 列表。</span><span class="sxs-lookup"><span data-stu-id="37580-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="37580-128">有关筛选器的信息，请参阅 [查看和组织设备列表](machines-view-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="37580-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="37580-129">导出 CSV 格式的列表以显示未筛选的数据。</span><span class="sxs-lookup"><span data-stu-id="37580-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="37580-130">CSV 文件将包含组织的所有设备，而不考虑视图本身应用的任何筛选，并且可能需要大量时间来下载，具体取决于你的组织规模。</span><span class="sxs-lookup"><span data-stu-id="37580-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![设备列表页面的屏幕截图](images/atp-devices-list-page.png)

<span data-ttu-id="37580-132">单击错误配置或不活动的设备时，可以查看设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="37580-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="37580-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="37580-133">Related topic</span></span>
- [<span data-ttu-id="37580-134">修复 Defender for Endpoint 中的不正常传感器</span><span class="sxs-lookup"><span data-stu-id="37580-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
