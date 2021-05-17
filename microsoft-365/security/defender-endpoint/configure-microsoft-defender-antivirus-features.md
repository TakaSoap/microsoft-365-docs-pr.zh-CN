---
title: 配置 Microsoft Defender 防病毒软件功能
description: 可以使用 Intune Microsoft Defender 防病毒、Microsoft Endpoint Configuration Manager、组策略和 PowerShell 配置这些功能。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 配置， 配置， 配置管理器， Microsoft Endpoint Configuration Manager， SCCM， Intune， MDM， 移动设备管理， GP， 组策略， PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275104"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="21e09-104">配置 Microsoft Defender 防病毒软件功能</span><span class="sxs-lookup"><span data-stu-id="21e09-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="21e09-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="21e09-105">**Applies to:**</span></span>

- [<span data-ttu-id="21e09-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="21e09-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="21e09-107">可以使用多种Microsoft Defender 防病毒配置配置策略，包括：</span><span class="sxs-lookup"><span data-stu-id="21e09-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="21e09-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="21e09-108">Microsoft Intune</span></span>
- <span data-ttu-id="21e09-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="21e09-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="21e09-110">组策略</span><span class="sxs-lookup"><span data-stu-id="21e09-110">Group Policy</span></span>
- <span data-ttu-id="21e09-111">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="21e09-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="21e09-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="21e09-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="21e09-113">可以配置以下各种功能：</span><span class="sxs-lookup"><span data-stu-id="21e09-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="21e09-114">云端保护</span><span class="sxs-lookup"><span data-stu-id="21e09-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="21e09-115">始终提供实时保护，包括行为、启发式和基于机器学习的保护</span><span class="sxs-lookup"><span data-stu-id="21e09-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="21e09-116">最终用户如何与各个终结点上的客户端交互</span><span class="sxs-lookup"><span data-stu-id="21e09-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="21e09-117">以下文章介绍如何在配置任务时执行Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="21e09-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="21e09-118">每篇文章都介绍了适用的配置工具 (或) 。</span><span class="sxs-lookup"><span data-stu-id="21e09-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="21e09-119">文章</span><span class="sxs-lookup"><span data-stu-id="21e09-119">Article</span></span>  |<span data-ttu-id="21e09-120">说明</span><span class="sxs-lookup"><span data-stu-id="21e09-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="21e09-121">利用 Microsoft 云提供的Microsoft Defender 防病毒保护</span><span class="sxs-lookup"><span data-stu-id="21e09-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="21e09-122">使用云提供的保护进行快速可靠的高级防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="21e09-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="21e09-123">配置方案、高要求和实时保护</span><span class="sxs-lookup"><span data-stu-id="21e09-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="21e09-124">启用基于行为的启发式实时防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="21e09-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="21e09-125">配置最终用户与最终用户的Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="21e09-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="21e09-126">配置组织中最终用户与用户交互的方式Microsoft Defender 防病毒他们看到的通知，以及他们是否可以覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="21e09-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="21e09-127">还可以查看管理和配置 [工具参考](configuration-management-reference-microsoft-defender-antivirus.md) 主题，了解每个工具的概述以及进一步帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="21e09-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>