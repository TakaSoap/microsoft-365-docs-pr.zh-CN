---
title: Windows 10 设备的装载工具和方法
description: 载入 Windows 10 设备，以便它们可以将传感器数据发送到 Microsoft Defender ATP 传感器
keywords: 载入 Windows 10 设备， 组策略， 终结点配置管理器， 移动设备管理， 本地脚本， gp， sccm， mdm， intune
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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165533"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="1fb2c-104">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="1fb2c-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1fb2c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1fb2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="1fb2c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1fb2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1fb2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fb2c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="1fb2c-108">Microsoft 365 终结点数据丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="1fb2c-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="1fb2c-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="1fb2c-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1fb2c-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1fb2c-111">必须配置组织中设备，以便 Defender for Endpoint 服务可以从这些设备获取传感器数据。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="1fb2c-112">可以使用多种方法和部署工具来配置贵组织的设备。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="1fb2c-113">支持以下部署工具和方法：</span><span class="sxs-lookup"><span data-stu-id="1fb2c-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="1fb2c-114">组策略</span><span class="sxs-lookup"><span data-stu-id="1fb2c-114">Group Policy</span></span>
- <span data-ttu-id="1fb2c-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fb2c-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="1fb2c-116">移动设备管理 (包括 Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="1fb2c-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="1fb2c-117">本地脚本</span><span class="sxs-lookup"><span data-stu-id="1fb2c-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1fb2c-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="1fb2c-118">In this section</span></span>
<span data-ttu-id="1fb2c-119">主题</span><span class="sxs-lookup"><span data-stu-id="1fb2c-119">Topic</span></span> | <span data-ttu-id="1fb2c-120">说明</span><span class="sxs-lookup"><span data-stu-id="1fb2c-120">Description</span></span>
:---|:---
[<span data-ttu-id="1fb2c-121">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="1fb2c-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="1fb2c-122">使用组策略在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="1fb2c-123">使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="1fb2c-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="1fb2c-124">可以使用 Microsoft Endpoint Manager (current branch) version 1606 或 Microsoft Endpoint Manager (current branch) version 1602 或更早版本在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="1fb2c-125">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="1fb2c-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="1fb2c-126">使用移动设备管理工具或 Microsoft Intune 在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="1fb2c-127">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="1fb2c-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="1fb2c-128">了解如何使用本地脚本在终结点上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="1fb2c-129">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="1fb2c-130">了解如何使用配置包配置 VDI 设备。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="1fb2c-131">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="1fb2c-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1fb2c-132">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1fb2c-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
