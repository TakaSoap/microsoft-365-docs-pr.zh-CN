---
title: Microsoft 托管桌面应用要求
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659710"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="3df5b-103">Microsoft 托管桌面应用要求</span><span class="sxs-lookup"><span data-stu-id="3df5b-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="3df5b-104">Microsoft 托管桌面要求我们使用特定方法管理设备，以确保设备的性能、可靠性和可维护性。</span><span class="sxs-lookup"><span data-stu-id="3df5b-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="3df5b-105">管理区域</span><span class="sxs-lookup"><span data-stu-id="3df5b-105">Management area</span></span>  |<span data-ttu-id="3df5b-106">Microsoft 托管桌面方法</span><span class="sxs-lookup"><span data-stu-id="3df5b-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="3df5b-107">设备配置或策略管理</span><span class="sxs-lookup"><span data-stu-id="3df5b-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="3df5b-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3df5b-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="3df5b-109">应用管理</span><span class="sxs-lookup"><span data-stu-id="3df5b-109">Application management</span></span>     | <span data-ttu-id="3df5b-110">Microsoft Intune 和公司门户</span><span class="sxs-lookup"><span data-stu-id="3df5b-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="3df5b-111">驱动程序部署</span><span class="sxs-lookup"><span data-stu-id="3df5b-111">Driver deployment</span></span>     |  <span data-ttu-id="3df5b-112">设备、Windows 更新或 Intune 中包含的驱动程序</span><span class="sxs-lookup"><span data-stu-id="3df5b-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="3df5b-113">设备安全性</span><span class="sxs-lookup"><span data-stu-id="3df5b-113">Device security</span></span>     | <span data-ttu-id="3df5b-114">请参阅 [设备安全性](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="3df5b-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="3df5b-115">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="3df5b-115">Identity and access management</span></span>     | <span data-ttu-id="3df5b-116">请参阅 [标识和访问管理](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="3df5b-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="3df5b-117">网络安全</span><span class="sxs-lookup"><span data-stu-id="3df5b-117">Network security</span></span>     | <span data-ttu-id="3df5b-118">请参阅 ["网络安全"](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="3df5b-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="3df5b-119">信息安全</span><span class="sxs-lookup"><span data-stu-id="3df5b-119">Information security</span></span>     |  <span data-ttu-id="3df5b-120">请参阅 ["信息安全"](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="3df5b-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="3df5b-121">数据恢复</span><span class="sxs-lookup"><span data-stu-id="3df5b-121">Data recovery</span></span>     | <span data-ttu-id="3df5b-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3df5b-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="3df5b-123">核心工作效率</span><span class="sxs-lookup"><span data-stu-id="3df5b-123">Core productivity</span></span>     | <span data-ttu-id="3df5b-124">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="3df5b-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="3df5b-125">浏览器</span><span class="sxs-lookup"><span data-stu-id="3df5b-125">Browser</span></span>     | <span data-ttu-id="3df5b-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3df5b-126">Microsoft Edge</span></span>        |




<span data-ttu-id="3df5b-127">Microsoft 托管桌面可能会监视在托管设备上运行的其他软件。</span><span class="sxs-lookup"><span data-stu-id="3df5b-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="3df5b-128">如果它对设备管理、设备安全性、性能或可靠性产生负面影响，你可能需要请求服务计划 [例外](customizing.md)。</span><span class="sxs-lookup"><span data-stu-id="3df5b-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
