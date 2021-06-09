---
title: 了解设备配置文件
description: 管理员可以分配给设备的各种配置文件
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841998"
---
# <a name="device-profiles"></a><span data-ttu-id="44c00-104">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="44c00-104">Device profiles</span></span>

<span data-ttu-id="44c00-105">你可以为设备分配不同的 ("设备配置文件) 配置，每个配置都针对特定类型的用户的需求进行了优化。</span><span class="sxs-lookup"><span data-stu-id="44c00-105">You can assign different pre-set configurations ("device profiles") to devices, each optimized for the needs of specific types of users.</span></span> <span data-ttu-id="44c00-106">有三个设备配置文件可用：</span><span class="sxs-lookup"><span data-stu-id="44c00-106">Three device profiles are available:</span></span>

- <span data-ttu-id="44c00-107">标准</span><span class="sxs-lookup"><span data-stu-id="44c00-107">Standard</span></span>
- <span data-ttu-id="44c00-108">敏感数据</span><span class="sxs-lookup"><span data-stu-id="44c00-108">Sensitive Data</span></span>
- <span data-ttu-id="44c00-109">Power user</span><span class="sxs-lookup"><span data-stu-id="44c00-109">Power user</span></span>

<span data-ttu-id="44c00-110">你可以将设备配置文件视为设备配置选项层次结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="44c00-110">You can think of device profiles as being part of a hierarchy of device configuration options.</span></span>

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="显示为棱锥的设备配置。说明如下":::

<span data-ttu-id="44c00-112">从根本上说，Microsoft 托管桌面设备的基础包括标准安全基线、合规性策略、Windows更新设置和组。</span><span class="sxs-lookup"><span data-stu-id="44c00-112">Fundamentally, every Microsoft Managed Desktop device has a foundation that includes a standard security baseline, compliance policies, Windows Update settings, and groups.</span></span> <span data-ttu-id="44c00-113">若要使用Microsoft 托管桌面，每个设备必须包含所有这些元素，管理员未经请求才能更改Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="44c00-113">To work with Microsoft Managed Desktop, every device must include all of these elements, which can't be changed by admins without a request to Microsoft Managed Desktop.</span></span>

<span data-ttu-id="44c00-114">设备配置文件显示在下一个较高级别。</span><span class="sxs-lookup"><span data-stu-id="44c00-114">Device profiles appear at the next higher level.</span></span> <span data-ttu-id="44c00-115">每个Microsoft 托管桌面设备必须分配一 (一个) 配置文件。</span><span class="sxs-lookup"><span data-stu-id="44c00-115">Every Microsoft Managed Desktop device must have one (and only one) profile assigned.</span></span> <span data-ttu-id="44c00-116">管理员可以选择已分配设备的配置文件。</span><span class="sxs-lookup"><span data-stu-id="44c00-116">Admins can choose which profile a device is assigned.</span></span>

<span data-ttu-id="44c00-117">更高级别的是其他 [自定义](customizing.md)项。</span><span class="sxs-lookup"><span data-stu-id="44c00-117">At a still higher level are additional [customizations](customizing.md).</span></span> <span data-ttu-id="44c00-118">每台设备可以具有一个或多个自定义 (或) 自定义。</span><span class="sxs-lookup"><span data-stu-id="44c00-118">Each device can have one or more (or no) customizations.</span></span> <span data-ttu-id="44c00-119">它们可以修改设备配置文件中的 (层或基础配置) ，或者作为一个全新请求，在标准配置的基础上分层。</span><span class="sxs-lookup"><span data-stu-id="44c00-119">They can either modify a lower-level layer (Device profiles or the foundational configuration),  or be an entirely new request that’s layered on top of the standard configuration.</span></span>

<span data-ttu-id="44c00-120">最上面是你自己的修改，如网络详细信息或应用程序。</span><span class="sxs-lookup"><span data-stu-id="44c00-120">At the top are your own modifications, such as network details or applications.</span></span> <span data-ttu-id="44c00-121">设备可以有任意数目的修改，这些修改不会由设备管理或Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="44c00-121">A device can have any number of these modifications, which aren't managed or blocked by Microsoft Managed Desktop.</span></span>


## <a name="device-profile-details"></a><span data-ttu-id="44c00-122">设备配置文件详细信息</span><span class="sxs-lookup"><span data-stu-id="44c00-122">Device profile details</span></span>

<span data-ttu-id="44c00-123">下表总结了设备配置文件配置的每个设置的设置及其默认值。</span><span class="sxs-lookup"><span data-stu-id="44c00-123">The following table summarizes the settings and their default values for each setting configured by device profiles.</span></span> <span data-ttu-id="44c00-124"> (在后台，这些设置使用 OMA-URIs.Microsoft Endpoint Manager.) </span><span class="sxs-lookup"><span data-stu-id="44c00-124">(Behind the scenes, these settings are configured with OMA-URIs by using Custom Configuration Profiles in Microsoft Endpoint Manager.)</span></span>

<br>

****

|<span data-ttu-id="44c00-125">功能</span><span class="sxs-lookup"><span data-stu-id="44c00-125">Feature</span></span>|<span data-ttu-id="44c00-126">敏感数据</span><span class="sxs-lookup"><span data-stu-id="44c00-126">Sensitive Data</span></span>|<span data-ttu-id="44c00-127">Power User</span><span class="sxs-lookup"><span data-stu-id="44c00-127">Power User</span></span>|<span data-ttu-id="44c00-128">标准</span><span class="sxs-lookup"><span data-stu-id="44c00-128">Standard</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="44c00-129">**阻止外部存储**</span><span class="sxs-lookup"><span data-stu-id="44c00-129">**Block External Storage**</span></span>|<span data-ttu-id="44c00-130">是</span><span class="sxs-lookup"><span data-stu-id="44c00-130">Yes</span></span>|<span data-ttu-id="44c00-131">是</span><span class="sxs-lookup"><span data-stu-id="44c00-131">Yes</span></span>|<span data-ttu-id="44c00-132">否</span><span class="sxs-lookup"><span data-stu-id="44c00-132">No</span></span>|
|<span data-ttu-id="44c00-133">**[云块级别](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span><span class="sxs-lookup"><span data-stu-id="44c00-133">**[Cloud Block Level](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span></span>|<span data-ttu-id="44c00-134">高</span><span class="sxs-lookup"><span data-stu-id="44c00-134">High</span></span>|<span data-ttu-id="44c00-135">高</span><span class="sxs-lookup"><span data-stu-id="44c00-135">High</span></span>|<span data-ttu-id="44c00-136">高</span><span class="sxs-lookup"><span data-stu-id="44c00-136">High</span></span>|
|<span data-ttu-id="44c00-137">**禁用 Microsoft 帐户**</span><span class="sxs-lookup"><span data-stu-id="44c00-137">**Disable Microsoft Accounts**</span></span>|<span data-ttu-id="44c00-138">是</span><span class="sxs-lookup"><span data-stu-id="44c00-138">Yes</span></span>|<span data-ttu-id="44c00-139">是</span><span class="sxs-lookup"><span data-stu-id="44c00-139">Yes</span></span>|<span data-ttu-id="44c00-140">否</span><span class="sxs-lookup"><span data-stu-id="44c00-140">No</span></span>|
|<span data-ttu-id="44c00-141">**禁用个人OneDrive**</span><span class="sxs-lookup"><span data-stu-id="44c00-141">**Disable personal OneDrive**</span></span>|<span data-ttu-id="44c00-142">是</span><span class="sxs-lookup"><span data-stu-id="44c00-142">Yes</span></span>|<span data-ttu-id="44c00-143">是</span><span class="sxs-lookup"><span data-stu-id="44c00-143">Yes</span></span>|<span data-ttu-id="44c00-144">否</span><span class="sxs-lookup"><span data-stu-id="44c00-144">No</span></span>|
|<span data-ttu-id="44c00-145">**切换到安全桌面进行提升**</span><span class="sxs-lookup"><span data-stu-id="44c00-145">**Switch to secure desktop for elevation**</span></span>|<span data-ttu-id="44c00-146">否</span><span class="sxs-lookup"><span data-stu-id="44c00-146">No</span></span>|<span data-ttu-id="44c00-147">是</span><span class="sxs-lookup"><span data-stu-id="44c00-147">Yes</span></span>|<span data-ttu-id="44c00-148">否</span><span class="sxs-lookup"><span data-stu-id="44c00-148">No</span></span>|
|<span data-ttu-id="44c00-149">**适用于终结点设备标记的 Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="44c00-149">**Microsoft Defender for Endpoint Device Tag**</span></span>|<span data-ttu-id="44c00-150">M365Managed-SensitiveData</span><span class="sxs-lookup"><span data-stu-id="44c00-150">M365Managed-SensitiveData</span></span>|<span data-ttu-id="44c00-151">M365Managed-PowerUser</span><span class="sxs-lookup"><span data-stu-id="44c00-151">M365Managed-PowerUser</span></span>|<span data-ttu-id="44c00-152">M365Managed-Standard</span><span class="sxs-lookup"><span data-stu-id="44c00-152">M365Managed-Standard</span></span>|
|<span data-ttu-id="44c00-153">**设备上管理员？**</span><span class="sxs-lookup"><span data-stu-id="44c00-153">**Admin on the device?**</span></span>|<span data-ttu-id="44c00-154">否</span><span class="sxs-lookup"><span data-stu-id="44c00-154">No</span></span>|<span data-ttu-id="44c00-155">是</span><span class="sxs-lookup"><span data-stu-id="44c00-155">Yes</span></span>|<span data-ttu-id="44c00-156">否</span><span class="sxs-lookup"><span data-stu-id="44c00-156">No</span></span>|
|<span data-ttu-id="44c00-157">**Autopilot 配置文件**</span><span class="sxs-lookup"><span data-stu-id="44c00-157">**Autopilot Profile**</span></span>|<span data-ttu-id="44c00-158">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="44c00-158">MMD Standard</span></span>|<span data-ttu-id="44c00-159">MMD Power User</span><span class="sxs-lookup"><span data-stu-id="44c00-159">MMD Power User</span></span>|<span data-ttu-id="44c00-160">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="44c00-160">MMD Standard</span></span>|
|<span data-ttu-id="44c00-161">**AppLocker**</span><span class="sxs-lookup"><span data-stu-id="44c00-161">**AppLocker**</span></span>|<span data-ttu-id="44c00-162">是</span><span class="sxs-lookup"><span data-stu-id="44c00-162">Yes</span></span>|<span data-ttu-id="44c00-163">否</span><span class="sxs-lookup"><span data-stu-id="44c00-163">No</span></span>|<span data-ttu-id="44c00-164">否</span><span class="sxs-lookup"><span data-stu-id="44c00-164">No</span></span>|
|<span data-ttu-id="44c00-165">**阻止公共存储**</span><span class="sxs-lookup"><span data-stu-id="44c00-165">**Block Public Store**</span></span>|<span data-ttu-id="44c00-166">是</span><span class="sxs-lookup"><span data-stu-id="44c00-166">Yes</span></span>|<span data-ttu-id="44c00-167">是</span><span class="sxs-lookup"><span data-stu-id="44c00-167">Yes</span></span>|<span data-ttu-id="44c00-168">否</span><span class="sxs-lookup"><span data-stu-id="44c00-168">No</span></span>|
|

<span data-ttu-id="44c00-169">每个设备配置文件也涉及以下项：</span><span class="sxs-lookup"><span data-stu-id="44c00-169">Each device profile also involves these items:</span></span>

- <span data-ttu-id="44c00-170">AAD Azure Active Directory (设备) 动态成员身份</span><span class="sxs-lookup"><span data-stu-id="44c00-170">A dynamic membership Azure Active Directory (AAD) device group</span></span>
- <span data-ttu-id="44c00-171">静态成员资格 AAD 设备组</span><span class="sxs-lookup"><span data-stu-id="44c00-171">A static membership AAD device group</span></span>
- <span data-ttu-id="44c00-172">配置Microsoft Endpoint Manager配置文件</span><span class="sxs-lookup"><span data-stu-id="44c00-172">A Microsoft Endpoint Manager Configuration profile</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44c00-173">不要直接修改这些组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="44c00-173">Don’t modify the membership of these groups directly.</span></span> <span data-ttu-id="44c00-174">使用重新分配配置文件 [中所述的接口](../working-with-managed-desktop/change-device-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="44c00-174">Use the interface as described in [Reassign profiles](../working-with-managed-desktop/change-device-profile.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="44c00-175">限制</span><span class="sxs-lookup"><span data-stu-id="44c00-175">Limitations</span></span>

<span data-ttu-id="44c00-176">你可以像对任何其他策略一样请求设备配置文件及其详细信息的例外。</span><span class="sxs-lookup"><span data-stu-id="44c00-176">You can request exceptions to the device profiles and their details as you would with any other policy.</span></span> <span data-ttu-id="44c00-177">请记住，你的组织只能有一个设备配置文件Azure Active Directory"租户 (租户) 。</span><span class="sxs-lookup"><span data-stu-id="44c00-177">Keep in mind that you can only have one of each device profile in your Azure Active Directory organization ("tenant").</span></span> <span data-ttu-id="44c00-178">例如，你无法请求敏感数据设备配置文件仅对部分用户禁用 AppLocker。</span><span class="sxs-lookup"><span data-stu-id="44c00-178">For example, you can't request that the Sensitive data device profile disables AppLocker for only some of your users.</span></span> <span data-ttu-id="44c00-179">所有具有敏感数据配置文件的设备都必须具有相同的配置。</span><span class="sxs-lookup"><span data-stu-id="44c00-179">All devices with the Sensitive data profile must have the same configuration.</span></span>

<span data-ttu-id="44c00-180">每台设备只能有一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="44c00-180">Each device can only have one profile.</span></span> <span data-ttu-id="44c00-181">如果给定设备由多个用户使用，则该设备上的所有用户都将具有相同的配置。</span><span class="sxs-lookup"><span data-stu-id="44c00-181">If a given device is used by more than one user, all users on that device will have the same configuration.</span></span>
