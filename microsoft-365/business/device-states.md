---
title: 设备状态
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解 Microsoft 365 商业版中的设备状态。
ms.openlocfilehash: b55e6a5d538ec28d195225e93797cea27afd2e8b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320200"
---
# <a name="device-states"></a><span data-ttu-id="60e59-103">设备状态</span><span class="sxs-lookup"><span data-stu-id="60e59-103">Device states</span></span>

<span data-ttu-id="60e59-104">" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。</span><span class="sxs-lookup"><span data-stu-id="60e59-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="60e59-106">**状态**</span><span class="sxs-lookup"><span data-stu-id="60e59-106">**Status**</span></span>|<span data-ttu-id="60e59-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="60e59-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60e59-108">由 Intune 托管</span><span class="sxs-lookup"><span data-stu-id="60e59-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="60e59-109">由 Microsoft 365 商业版 托管</span><span class="sxs-lookup"><span data-stu-id="60e59-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="60e59-110">等待停用</span><span class="sxs-lookup"><span data-stu-id="60e59-110">Retire pending</span></span>  <br/> |<span data-ttu-id="60e59-111">Microsoft 365 商业版 正准备从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="60e59-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="60e59-112">正在停用</span><span class="sxs-lookup"><span data-stu-id="60e59-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="60e59-113">Microsoft 365 商业版 当前正在从设备中删除公司数据。</span><span class="sxs-lookup"><span data-stu-id="60e59-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="60e59-114">停用失败</span><span class="sxs-lookup"><span data-stu-id="60e59-114">Retire failed</span></span>  <br/> | <span data-ttu-id="60e59-115">删除公司数据操作失败。</span><span class="sxs-lookup"><span data-stu-id="60e59-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="60e59-116">停用取消</span><span class="sxs-lookup"><span data-stu-id="60e59-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="60e59-117">取消停用操作。</span><span class="sxs-lookup"><span data-stu-id="60e59-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="60e59-118">等待擦除</span><span class="sxs-lookup"><span data-stu-id="60e59-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="60e59-119">正在等待恢复出厂重置。</span><span class="sxs-lookup"><span data-stu-id="60e59-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="60e59-120">正在擦除</span><span class="sxs-lookup"><span data-stu-id="60e59-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="60e59-121">已开始恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="60e59-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="60e59-122">擦除失败</span><span class="sxs-lookup"><span data-stu-id="60e59-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="60e59-123">无法进行恢复出厂设置。</span><span class="sxs-lookup"><span data-stu-id="60e59-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="60e59-124">擦除已取消</span><span class="sxs-lookup"><span data-stu-id="60e59-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="60e59-125">已取消工厂擦除。</span><span class="sxs-lookup"><span data-stu-id="60e59-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="60e59-126">不正常</span><span class="sxs-lookup"><span data-stu-id="60e59-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="60e59-127">某个操作已挂起（或正在进行），但设备尚未签入30天以上的天数。</span><span class="sxs-lookup"><span data-stu-id="60e59-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="60e59-128">等待删除</span><span class="sxs-lookup"><span data-stu-id="60e59-128">Delete pending</span></span>  <br/> |<span data-ttu-id="60e59-129">正在等待执行"删除"操作。</span><span class="sxs-lookup"><span data-stu-id="60e59-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="60e59-130">已发现</span><span class="sxs-lookup"><span data-stu-id="60e59-130">Discovered</span></span>  <br/> |<span data-ttu-id="60e59-131">Microsoft 365 商业版 已检测到设备。</span><span class="sxs-lookup"><span data-stu-id="60e59-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
