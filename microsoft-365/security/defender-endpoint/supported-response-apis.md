---
title: 支持的 Microsoft Defender 高级威胁防护响应 API
description: 了解与特定响应相关的 Microsoft Defender 高级威胁防护 API 调用。
keywords: 响应 api， 图形 api， 受支持的 api， 参与者， 警报， 设备， 用户， 域， ip， 文件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185547"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="42795-104">支持的 Microsoft Defender for Endpoint 查询 API</span><span class="sxs-lookup"><span data-stu-id="42795-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="42795-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="42795-105">**Applies to:**</span></span>
- [<span data-ttu-id="42795-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42795-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="42795-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="42795-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="42795-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="42795-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="42795-109">了解可以运行的受支持的与响应相关的 API 调用，以及所需请求标头和来自调用的预期响应等详细信息。</span><span class="sxs-lookup"><span data-stu-id="42795-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="42795-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="42795-110">In this section</span></span>
<span data-ttu-id="42795-111">主题</span><span class="sxs-lookup"><span data-stu-id="42795-111">Topic</span></span> | <span data-ttu-id="42795-112">说明</span><span class="sxs-lookup"><span data-stu-id="42795-112">Description</span></span>
:---|:---
<span data-ttu-id="42795-113">收集调查包</span><span class="sxs-lookup"><span data-stu-id="42795-113">Collect investigation package</span></span> | <span data-ttu-id="42795-114">运行此 API 从设备收集调查包。</span><span class="sxs-lookup"><span data-stu-id="42795-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="42795-115">隔离设备</span><span class="sxs-lookup"><span data-stu-id="42795-115">Isolate device</span></span> | <span data-ttu-id="42795-116">运行此 API 以将设备与网络隔离。</span><span class="sxs-lookup"><span data-stu-id="42795-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="42795-117">Unisolate 设备</span><span class="sxs-lookup"><span data-stu-id="42795-117">Unisolate device</span></span> | <span data-ttu-id="42795-118">从隔离中删除设备。</span><span class="sxs-lookup"><span data-stu-id="42795-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="42795-119">限制代码执行</span><span class="sxs-lookup"><span data-stu-id="42795-119">Restrict code execution</span></span> | <span data-ttu-id="42795-120">通过停止恶意进程运行此 API 以包含攻击。</span><span class="sxs-lookup"><span data-stu-id="42795-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="42795-121">还可以锁定设备并阻止潜在恶意程序的后续尝试运行。</span><span class="sxs-lookup"><span data-stu-id="42795-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="42795-122">无限制代码执行</span><span class="sxs-lookup"><span data-stu-id="42795-122">Unrestrict code execution</span></span> | <span data-ttu-id="42795-123">在验证损坏的设备已修复后，运行此功能以取消应用程序策略的限制。</span><span class="sxs-lookup"><span data-stu-id="42795-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="42795-124">运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="42795-124">Run antivirus scan</span></span> | <span data-ttu-id="42795-125">远程启动防病毒扫描，以帮助识别和修正可能存在于受到威胁的设备的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="42795-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="42795-126">停止和隔离文件</span><span class="sxs-lookup"><span data-stu-id="42795-126">Stop and quarantine file</span></span> |  <span data-ttu-id="42795-127">运行此调用以停止正在运行的进程、隔离文件并删除持久性（如注册表项）。</span><span class="sxs-lookup"><span data-stu-id="42795-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="42795-128">请求示例</span><span class="sxs-lookup"><span data-stu-id="42795-128">Request sample</span></span> | <span data-ttu-id="42795-129">运行此调用，从特定设备请求文件示例。</span><span class="sxs-lookup"><span data-stu-id="42795-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="42795-130">文件会从设备中收集并上载到安全存储。</span><span class="sxs-lookup"><span data-stu-id="42795-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="42795-131">阻止文件</span><span class="sxs-lookup"><span data-stu-id="42795-131">Block file</span></span> | <span data-ttu-id="42795-132">运行此 API，通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。</span><span class="sxs-lookup"><span data-stu-id="42795-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="42795-133">取消阻止文件</span><span class="sxs-lookup"><span data-stu-id="42795-133">Unblock file</span></span> | <span data-ttu-id="42795-134">允许使用 Microsoft Defender 防病毒在组织中运行文件。</span><span class="sxs-lookup"><span data-stu-id="42795-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="42795-135">获取程序包 SAS URI</span><span class="sxs-lookup"><span data-stu-id="42795-135">Get package SAS URI</span></span> | <span data-ttu-id="42795-136">运行此 API 获取允许下载调查包的 URI。</span><span class="sxs-lookup"><span data-stu-id="42795-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="42795-137">获取 MachineAction 对象</span><span class="sxs-lookup"><span data-stu-id="42795-137">Get MachineAction object</span></span> | <span data-ttu-id="42795-138">运行此 API 获取 MachineAction 对象。</span><span class="sxs-lookup"><span data-stu-id="42795-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="42795-139">获取 MachineActions 集合</span><span class="sxs-lookup"><span data-stu-id="42795-139">Get MachineActions collection</span></span> | <span data-ttu-id="42795-140">运行它可获取 MachineAction 集合。</span><span class="sxs-lookup"><span data-stu-id="42795-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="42795-141">获取 FileActions 集合</span><span class="sxs-lookup"><span data-stu-id="42795-141">Get FileActions collection</span></span> | <span data-ttu-id="42795-142">运行此 API 获取 FileActions 集合。</span><span class="sxs-lookup"><span data-stu-id="42795-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="42795-143">获取 FileMachineAction 对象</span><span class="sxs-lookup"><span data-stu-id="42795-143">Get FileMachineAction object</span></span> | <span data-ttu-id="42795-144">运行此 API 获取 FileMachineAction 对象。</span><span class="sxs-lookup"><span data-stu-id="42795-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="42795-145">获取 FileMachineActions 集合</span><span class="sxs-lookup"><span data-stu-id="42795-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="42795-146">运行此 API 获取 FileMachineAction 集合。</span><span class="sxs-lookup"><span data-stu-id="42795-146">Run this API to get FileMachineAction collection.</span></span>
