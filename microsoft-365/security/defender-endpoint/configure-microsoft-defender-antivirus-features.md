---
title: 配置 Microsoft Defender 防病毒软件功能
description: 可以使用 Intune、Microsoft Endpoint Configuration Manager、组策略和 PowerShell 配置 Microsoft Defender 防病毒功能。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 配置， 配置， 配置管理器， Microsoft Endpoint Configuration Manager， SCCM， Intune， MDM， 移动设备管理， GP， 组策略， PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765163"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="4f124-104">配置 Microsoft Defender 防病毒软件功能</span><span class="sxs-lookup"><span data-stu-id="4f124-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4f124-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4f124-105">**Applies to:**</span></span>

- [<span data-ttu-id="4f124-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4f124-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4f124-107">可以使用多种工具配置 Microsoft Defender 防病毒，包括：</span><span class="sxs-lookup"><span data-stu-id="4f124-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="4f124-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4f124-108">Microsoft Intune</span></span>
- <span data-ttu-id="4f124-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4f124-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="4f124-110">组策略</span><span class="sxs-lookup"><span data-stu-id="4f124-110">Group Policy</span></span>
- <span data-ttu-id="4f124-111">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f124-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="4f124-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="4f124-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="4f124-113">可以配置以下各种功能：</span><span class="sxs-lookup"><span data-stu-id="4f124-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="4f124-114">云保护</span><span class="sxs-lookup"><span data-stu-id="4f124-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="4f124-115">始终提供实时保护，包括行为、启发式和基于机器学习的保护</span><span class="sxs-lookup"><span data-stu-id="4f124-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="4f124-116">最终用户如何与各个终结点上的客户端交互</span><span class="sxs-lookup"><span data-stu-id="4f124-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="4f124-117">以下文章介绍了配置 Microsoft Defender 防病毒时如何执行关键任务。</span><span class="sxs-lookup"><span data-stu-id="4f124-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="4f124-118">每篇文章都介绍了适用的配置工具 (或) 。</span><span class="sxs-lookup"><span data-stu-id="4f124-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="4f124-119">文章</span><span class="sxs-lookup"><span data-stu-id="4f124-119">Article</span></span>  |<span data-ttu-id="4f124-120">说明</span><span class="sxs-lookup"><span data-stu-id="4f124-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="4f124-121">利用 Microsoft 云提供的 Microsoft Defender 防病毒保护</span><span class="sxs-lookup"><span data-stu-id="4f124-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="4f124-122">使用云提供的保护进行快速可靠的高级防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="4f124-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="4f124-123">配置方案、高要求和实时保护</span><span class="sxs-lookup"><span data-stu-id="4f124-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="4f124-124">启用基于行为的启发式实时防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="4f124-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="4f124-125">配置最终用户与 Microsoft Defender 防病毒的交互</span><span class="sxs-lookup"><span data-stu-id="4f124-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="4f124-126">配置组织中最终用户与 Microsoft Defender 防病毒的交互方式、他们看到的通知，以及他们是否可以覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="4f124-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="4f124-127">还可以查看管理和配置 [工具参考](configuration-management-reference-microsoft-defender-antivirus.md) 主题，了解每个工具的概述以及进一步帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="4f124-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>