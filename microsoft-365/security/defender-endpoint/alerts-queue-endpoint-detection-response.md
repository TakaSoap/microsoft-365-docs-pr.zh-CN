---
title: 警报队列中Microsoft 365 Defender
ms.reviewer: ''
description: 查看和管理警报中Microsoft 365 Defender
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: ed65c836e74d5394d3b291ca3ebb5e781e37afa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339558"
---
# <a name="alerts-queue-in-microsoft-365-defender"></a><span data-ttu-id="33f58-103">警报队列中Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33f58-103">Alerts queue in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33f58-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="33f58-104">**Applies to:**</span></span>
- [<span data-ttu-id="33f58-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="33f58-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="33f58-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="33f58-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33f58-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="33f58-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="33f58-108">了解如何查看和管理队列，以便有效地调查在实体（如设备、文件或用户帐户）上看到的威胁。</span><span class="sxs-lookup"><span data-stu-id="33f58-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="33f58-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="33f58-109">In this section</span></span>
<span data-ttu-id="33f58-110">主题</span><span class="sxs-lookup"><span data-stu-id="33f58-110">Topic</span></span> | <span data-ttu-id="33f58-111">说明</span><span class="sxs-lookup"><span data-stu-id="33f58-111">Description</span></span> 
:---|:---
[<span data-ttu-id="33f58-112">查看和组织警报队列</span><span class="sxs-lookup"><span data-stu-id="33f58-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="33f58-113">显示网络中标记的警报列表。</span><span class="sxs-lookup"><span data-stu-id="33f58-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="33f58-114">管理警报</span><span class="sxs-lookup"><span data-stu-id="33f58-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="33f58-115">了解如何管理警报（如更改其状态、将其分配给安全操作成员）以及查看警报历史记录。</span><span class="sxs-lookup"><span data-stu-id="33f58-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="33f58-116">调查警报</span><span class="sxs-lookup"><span data-stu-id="33f58-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="33f58-117">调查影响网络的警报，了解它们的含义以及如何解决它们。</span><span class="sxs-lookup"><span data-stu-id="33f58-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="33f58-118">调查文件</span><span class="sxs-lookup"><span data-stu-id="33f58-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="33f58-119">调查与特定警报、行为或事件关联的文件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="33f58-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="33f58-120">调查设备</span><span class="sxs-lookup"><span data-stu-id="33f58-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="33f58-121">调查与特定警报、行为或事件关联的设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="33f58-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="33f58-122">调查 IP 地址</span><span class="sxs-lookup"><span data-stu-id="33f58-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="33f58-123">检查网络中设备与外部 Internet 协议与 IP 地址 () 通信。</span><span class="sxs-lookup"><span data-stu-id="33f58-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="33f58-124">调查域</span><span class="sxs-lookup"><span data-stu-id="33f58-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="33f58-125">调查域以查看网络中设备和服务器是否一直与已知的恶意域通信。</span><span class="sxs-lookup"><span data-stu-id="33f58-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="33f58-126">调查用户帐户</span><span class="sxs-lookup"><span data-stu-id="33f58-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="33f58-127">识别具有最活跃警报的用户帐户，并调查凭据可能遭到入侵的情况。</span><span class="sxs-lookup"><span data-stu-id="33f58-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


