---
title: 设备状态
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解 Microsoft 365 商业版中的设备状态。
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276955"
---
# <a name="device-states"></a><span data-ttu-id="ba0e6-103">设备状态</span><span class="sxs-lookup"><span data-stu-id="ba0e6-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="ba0e6-104">设备状态</span><span class="sxs-lookup"><span data-stu-id="ba0e6-104">Device states</span></span>

<span data-ttu-id="ba0e6-105">" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="ba0e6-107">**状态**</span><span class="sxs-lookup"><span data-stu-id="ba0e6-107">**Status**</span></span>|<span data-ttu-id="ba0e6-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ba0e6-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba0e6-109">由 Intune 托管</span><span class="sxs-lookup"><span data-stu-id="ba0e6-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="ba0e6-110">由 Microsoft 365 商业版 托管</span><span class="sxs-lookup"><span data-stu-id="ba0e6-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-111">等待停用</span><span class="sxs-lookup"><span data-stu-id="ba0e6-111">Retire pending</span></span>  <br/> |<span data-ttu-id="ba0e6-112">Microsoft 365 商业版 正准备从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-113">正在停用</span><span class="sxs-lookup"><span data-stu-id="ba0e6-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="ba0e6-114">Microsoft 365 商业版 当前正在从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-115">停用失败</span><span class="sxs-lookup"><span data-stu-id="ba0e6-115">Retire failed</span></span>  <br/> | <span data-ttu-id="ba0e6-116">删除公司数据操作失败。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-117">已取消停用</span><span class="sxs-lookup"><span data-stu-id="ba0e6-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="ba0e6-118">已取消"停用"操作。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-119">等待擦除</span><span class="sxs-lookup"><span data-stu-id="ba0e6-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="ba0e6-120">正在等待恢复出厂重置。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-121">正在擦除</span><span class="sxs-lookup"><span data-stu-id="ba0e6-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="ba0e6-122">已开始恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-123">擦除失败</span><span class="sxs-lookup"><span data-stu-id="ba0e6-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="ba0e6-124">无法恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-125">已取消擦除</span><span class="sxs-lookup"><span data-stu-id="ba0e6-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="ba0e6-126">已取消工厂擦除。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-127">不正常</span><span class="sxs-lookup"><span data-stu-id="ba0e6-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="ba0e6-128">这表明某个操作正在等待执行（或正在执行），但设备未签入时间已超过 30 天。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-129">等待删除</span><span class="sxs-lookup"><span data-stu-id="ba0e6-129">Delete pending</span></span>  <br/> |<span data-ttu-id="ba0e6-130">正在等待执行"删除"操作。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="ba0e6-131">已发现</span><span class="sxs-lookup"><span data-stu-id="ba0e6-131">Discovered</span></span>  <br/> |<span data-ttu-id="ba0e6-132">Microsoft 365 商业版 已检测到设备。</span><span class="sxs-lookup"><span data-stu-id="ba0e6-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
