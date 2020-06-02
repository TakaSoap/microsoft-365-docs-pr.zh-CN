---
title: 设备状态
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 了解 Microsoft 365 for business 中的 "管理员主页" 中的 "设备操作" 列表中的各种设备状态。
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471171"
---
# <a name="device-states"></a><span data-ttu-id="e7197-103">设备状态</span><span class="sxs-lookup"><span data-stu-id="e7197-103">Device states</span></span>

<span data-ttu-id="e7197-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="e7197-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="e7197-105">" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="e7197-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="e7197-107">**状态**</span><span class="sxs-lookup"><span data-stu-id="e7197-107">**Status**</span></span>|<span data-ttu-id="e7197-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7197-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e7197-109">由 Intune 托管</span><span class="sxs-lookup"><span data-stu-id="e7197-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="e7197-110">由 Microsoft 365 商业高级版管理。</span><span class="sxs-lookup"><span data-stu-id="e7197-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="e7197-111">等待停用</span><span class="sxs-lookup"><span data-stu-id="e7197-111">Retire pending</span></span>  <br/> |<span data-ttu-id="e7197-112">Microsoft 365 商业高级版准备从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="e7197-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e7197-113">正在停用</span><span class="sxs-lookup"><span data-stu-id="e7197-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="e7197-114">Microsoft 365 商业高级版当前正在从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="e7197-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e7197-115">停用失败</span><span class="sxs-lookup"><span data-stu-id="e7197-115">Retire failed</span></span>  <br/> | <span data-ttu-id="e7197-116">删除公司数据操作失败。</span><span class="sxs-lookup"><span data-stu-id="e7197-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="e7197-117">停用取消</span><span class="sxs-lookup"><span data-stu-id="e7197-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="e7197-118">取消停用操作。</span><span class="sxs-lookup"><span data-stu-id="e7197-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="e7197-119">等待擦除</span><span class="sxs-lookup"><span data-stu-id="e7197-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="e7197-120">正在等待恢复出厂重置。</span><span class="sxs-lookup"><span data-stu-id="e7197-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="e7197-121">正在擦除</span><span class="sxs-lookup"><span data-stu-id="e7197-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="e7197-122">已开始恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="e7197-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="e7197-123">擦除失败</span><span class="sxs-lookup"><span data-stu-id="e7197-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="e7197-124">无法进行恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="e7197-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="e7197-125">擦除已取消</span><span class="sxs-lookup"><span data-stu-id="e7197-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="e7197-126">已取消工厂擦除。</span><span class="sxs-lookup"><span data-stu-id="e7197-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="e7197-127">不正常</span><span class="sxs-lookup"><span data-stu-id="e7197-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="e7197-128">某个操作已挂起（或正在进行），但设备尚未签入30天以上的天数。</span><span class="sxs-lookup"><span data-stu-id="e7197-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="e7197-129">等待删除</span><span class="sxs-lookup"><span data-stu-id="e7197-129">Delete pending</span></span>  <br/> |<span data-ttu-id="e7197-130">正在等待执行"删除"操作。</span><span class="sxs-lookup"><span data-stu-id="e7197-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="e7197-131">已发现</span><span class="sxs-lookup"><span data-stu-id="e7197-131">Discovered</span></span>  <br/> |<span data-ttu-id="e7197-132">Microsoft 365 商业高级版已检测到设备。</span><span class="sxs-lookup"><span data-stu-id="e7197-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
