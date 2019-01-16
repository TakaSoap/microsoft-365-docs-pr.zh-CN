---
title: 设备状态
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: 了解 Microsoft 365 企业版中的设备状态。
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865627"
---
# <a name="device-states"></a><span data-ttu-id="53184-103">设备状态</span><span class="sxs-lookup"><span data-stu-id="53184-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="53184-104">设备状态</span><span class="sxs-lookup"><span data-stu-id="53184-104">Device states</span></span>

<span data-ttu-id="53184-105">" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="53184-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="53184-107">**状态**</span><span class="sxs-lookup"><span data-stu-id="53184-107">**Status**</span></span>|<span data-ttu-id="53184-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="53184-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53184-109">由 Intune 托管</span><span class="sxs-lookup"><span data-stu-id="53184-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="53184-110">由 Microsoft 365 商业版 托管</span><span class="sxs-lookup"><span data-stu-id="53184-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="53184-111">等待停用</span><span class="sxs-lookup"><span data-stu-id="53184-111">Retire pending</span></span>  <br/> |<span data-ttu-id="53184-112">Microsoft 365 商业版 正准备从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="53184-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="53184-113">正在停用</span><span class="sxs-lookup"><span data-stu-id="53184-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="53184-114">Microsoft 365 商业版 当前正在从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="53184-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="53184-115">停用失败</span><span class="sxs-lookup"><span data-stu-id="53184-115">Retire failed</span></span>  <br/> | <span data-ttu-id="53184-116">删除公司数据操作失败。</span><span class="sxs-lookup"><span data-stu-id="53184-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="53184-117">已取消停用</span><span class="sxs-lookup"><span data-stu-id="53184-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="53184-118">已取消"停用"操作。</span><span class="sxs-lookup"><span data-stu-id="53184-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="53184-119">等待擦除</span><span class="sxs-lookup"><span data-stu-id="53184-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="53184-120">正在等待恢复出厂重置。</span><span class="sxs-lookup"><span data-stu-id="53184-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="53184-121">正在擦除</span><span class="sxs-lookup"><span data-stu-id="53184-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="53184-122">已开始恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="53184-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="53184-123">擦除失败</span><span class="sxs-lookup"><span data-stu-id="53184-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="53184-124">无法恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="53184-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="53184-125">已取消擦除</span><span class="sxs-lookup"><span data-stu-id="53184-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="53184-126">已取消工厂擦除。</span><span class="sxs-lookup"><span data-stu-id="53184-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="53184-127">不正常</span><span class="sxs-lookup"><span data-stu-id="53184-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="53184-128">这表明某个操作正在等待执行（或正在执行），但设备未签入时间已超过 30 天。</span><span class="sxs-lookup"><span data-stu-id="53184-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="53184-129">等待删除</span><span class="sxs-lookup"><span data-stu-id="53184-129">Delete pending</span></span>  <br/> |<span data-ttu-id="53184-130">正在等待执行"删除"操作。</span><span class="sxs-lookup"><span data-stu-id="53184-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="53184-131">已发现</span><span class="sxs-lookup"><span data-stu-id="53184-131">Discovered</span></span>  <br/> |<span data-ttu-id="53184-132">Microsoft 365 商业版 已检测到设备。</span><span class="sxs-lookup"><span data-stu-id="53184-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
