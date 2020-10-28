---
title: " (预览版的 Windows 10 设备的载入工具和方法) "
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
description: 板载 Windows 10 设备，以便可以将传感器数据发送到 Microsoft 365 合规性解决方案
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769639"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a><span data-ttu-id="602db-103"> (预览版的 Windows 10 设备的载入工具和方法) </span><span class="sxs-lookup"><span data-stu-id="602db-103">Onboarding tools and methods for Windows 10 devices (preview)</span></span>

<span data-ttu-id="602db-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="602db-104">**Applies to:**</span></span>
- [<span data-ttu-id="602db-105">Microsoft 365 Endpoint data 丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="602db-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="602db-106">您的组织中的设备必须配置为 Microsoft 365 终结点数据丢失防护服务可以从这些设备获取传感器数据。</span><span class="sxs-lookup"><span data-stu-id="602db-106">Devices in your organization must be configured so that the Microsoft 365 Endpoint data loss prevention service can get sensor data from them.</span></span> <span data-ttu-id="602db-107">您可以使用多种方法和部署工具来配置组织中的设备。</span><span class="sxs-lookup"><span data-stu-id="602db-107">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="602db-108">支持以下部署工具和方法：</span><span class="sxs-lookup"><span data-stu-id="602db-108">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="602db-109">组策略</span><span class="sxs-lookup"><span data-stu-id="602db-109">group policy</span></span>
- <span data-ttu-id="602db-110">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="602db-110">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="602db-111">移动设备管理 (包括 Microsoft Intune) </span><span class="sxs-lookup"><span data-stu-id="602db-111">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="602db-112">本地脚本</span><span class="sxs-lookup"><span data-stu-id="602db-112">local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="602db-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="602db-113">In this section</span></span>
<span data-ttu-id="602db-114">主题</span><span class="sxs-lookup"><span data-stu-id="602db-114">Topic</span></span> | <span data-ttu-id="602db-115">说明</span><span class="sxs-lookup"><span data-stu-id="602db-115">Description</span></span>
:---|:---
[<span data-ttu-id="602db-116">使用组策略的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="602db-116">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md) | <span data-ttu-id="602db-117">使用组策略在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="602db-117">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="602db-118">使用 Microsoft 终结点配置管理器的板载 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="602db-118">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md) | <span data-ttu-id="602db-119">您可以使用 Microsoft 终结点配置管理器 (当前分支) 版本1606或 Microsoft 终结点配置管理器 (当前分支) 版本1602或更早版本，以在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="602db-119">You can use either use Microsoft Endpoint Configuration Manager (current branch) version 1606 or Microsoft Endpoint Configuration Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="602db-120">使用移动设备管理工具的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="602db-120">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md) | <span data-ttu-id="602db-121">使用移动设备管理工具或 Microsoft Intune 在设备上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="602db-121">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="602db-122">使用本地脚本的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="602db-122">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md) | <span data-ttu-id="602db-123">了解如何使用本地脚本在终结点上部署配置包。</span><span class="sxs-lookup"><span data-stu-id="602db-123">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="602db-124"> (VDI) 设备的板载非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="602db-124">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md) | <span data-ttu-id="602db-125">了解如何使用配置包配置 VDI 设备。</span><span class="sxs-lookup"><span data-stu-id="602db-125">Learn how to use the configuration package to configure VDI devices.</span></span>
