---
title: 设备状态
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解适用于企业管理员主页的"设备操作"列表中的Microsoft 365状态。
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578459"
---
# <a name="device-states"></a><span data-ttu-id="18b46-103">设备状态</span><span class="sxs-lookup"><span data-stu-id="18b46-103">Device states</span></span>

<span data-ttu-id="18b46-104">本文适用于Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="18b46-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="18b46-105">" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="18b46-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="18b46-107">**状态**</span><span class="sxs-lookup"><span data-stu-id="18b46-107">**Status**</span></span>|<span data-ttu-id="18b46-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="18b46-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="18b46-109">由 Intune 托管</span><span class="sxs-lookup"><span data-stu-id="18b46-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="18b46-110">由 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="18b46-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="18b46-111">等待停用</span><span class="sxs-lookup"><span data-stu-id="18b46-111">Retire pending</span></span>  <br/> |<span data-ttu-id="18b46-112">Microsoft 365 商业高级版准备好从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="18b46-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="18b46-113">正在停用</span><span class="sxs-lookup"><span data-stu-id="18b46-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="18b46-114">Microsoft 365 商业高级版当前正在从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="18b46-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="18b46-115">停用失败</span><span class="sxs-lookup"><span data-stu-id="18b46-115">Retire failed</span></span>  <br/> | <span data-ttu-id="18b46-116">删除公司数据操作失败。</span><span class="sxs-lookup"><span data-stu-id="18b46-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="18b46-117">已取消停用</span><span class="sxs-lookup"><span data-stu-id="18b46-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="18b46-118">已取消停用操作。</span><span class="sxs-lookup"><span data-stu-id="18b46-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="18b46-119">等待擦除</span><span class="sxs-lookup"><span data-stu-id="18b46-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="18b46-120">正在等待恢复出厂重置。</span><span class="sxs-lookup"><span data-stu-id="18b46-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="18b46-121">正在擦除</span><span class="sxs-lookup"><span data-stu-id="18b46-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="18b46-122">已开始恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="18b46-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="18b46-123">擦除失败</span><span class="sxs-lookup"><span data-stu-id="18b46-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="18b46-124">无法恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="18b46-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="18b46-125">已取消擦除</span><span class="sxs-lookup"><span data-stu-id="18b46-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="18b46-126">已取消出厂擦除。</span><span class="sxs-lookup"><span data-stu-id="18b46-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="18b46-127">不正常</span><span class="sxs-lookup"><span data-stu-id="18b46-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="18b46-128">操作挂起 (或正在进行) ，但设备尚未签入 30 天以上。</span><span class="sxs-lookup"><span data-stu-id="18b46-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="18b46-129">等待删除</span><span class="sxs-lookup"><span data-stu-id="18b46-129">Delete pending</span></span>  <br/> |<span data-ttu-id="18b46-130">正在等待执行"删除"操作。</span><span class="sxs-lookup"><span data-stu-id="18b46-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="18b46-131">已发现</span><span class="sxs-lookup"><span data-stu-id="18b46-131">Discovered</span></span>  <br/> |<span data-ttu-id="18b46-132">Microsoft 365 商业高级版检测到设备。</span><span class="sxs-lookup"><span data-stu-id="18b46-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
