---
title: 适用于移动设备的载入Windows 10工具
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 载入Windows 10设备，以便它们可以将传感器数据发送到 Microsoft 365 合规性解决方案
ms.openlocfilehash: 676fb3a7ffcae8d108fd9b7fabe61bb78b7e1744
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341696"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="7d041-103">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="7d041-103">Onboarding tools and methods for Windows 10 devices</span></span>

<span data-ttu-id="7d041-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7d041-104">**Applies to:**</span></span>
- [<span data-ttu-id="7d041-105">Microsoft 365DLP (终结点数据丢失) </span><span class="sxs-lookup"><span data-stu-id="7d041-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="7d041-106">必须配置组织中设备，以便Microsoft 365终结点数据丢失防护服务可以从这些设备获取传感器数据。</span><span class="sxs-lookup"><span data-stu-id="7d041-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="7d041-107">可以使用多种方法和部署工具来配置贵组织的设备。</span><span class="sxs-lookup"><span data-stu-id="7d041-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="7d041-108">支持以下部署工具和方法：</span><span class="sxs-lookup"><span data-stu-id="7d041-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="7d041-109">组策略</span><span class="sxs-lookup"><span data-stu-id="7d041-109">group policy</span></span>
- <span data-ttu-id="7d041-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7d041-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="7d041-111">移动设备管理 (包括Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="7d041-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="7d041-112">本地脚本</span><span class="sxs-lookup"><span data-stu-id="7d041-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7d041-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="7d041-113">In this section</span></span>
<span data-ttu-id="7d041-114">主题</span><span class="sxs-lookup"><span data-stu-id="7d041-114">Topic</span></span> | <span data-ttu-id="7d041-115">说明</span><span class="sxs-lookup"><span data-stu-id="7d041-115">Description</span></span>
:---|:---
[<span data-ttu-id="7d041-116">使用Windows 10载入设备</span><span class="sxs-lookup"><span data-stu-id="7d041-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="7d041-117">使用组策略在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="7d041-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="7d041-118">使用Windows载入Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7d041-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="7d041-119">可以使用 Microsoft Endpoint Configuration Manager (当前分支) 版本 1606 或 Microsoft Endpoint Configuration Manager (current branch) 版本 1602 或更早版本在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="7d041-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="7d041-120">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="7d041-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="7d041-121">使用移动设备管理工具或Microsoft Intune在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="7d041-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="7d041-122">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="7d041-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="7d041-123">了解如何使用本地脚本在终结点上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="7d041-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="7d041-124">载入非永久虚拟桌面基础结构 （VDI） 设备</span><span class="sxs-lookup"><span data-stu-id="7d041-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="7d041-125">了解如何使用配置包配置 VDI 设备。</span><span class="sxs-lookup"><span data-stu-id="7d041-125">Learn how to use the configuration package to configure VDI devices.</span></span>