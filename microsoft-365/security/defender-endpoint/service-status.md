---
title: 检查 Microsoft Defender 终结点服务运行状况
description: 检查 Microsoft Defender 终结点服务运行状况，查看服务是否遇到问题并查看之前已解决的问题。
keywords: 仪表板， 服务， 问题， 服务运行状况， 当前状态， 状态历史记录， 影响摘要， 初步的根本原因， 解决方案， 解决时间， 预计解决时间
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687621"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="93543-104">检查 Microsoft Defender 终结点服务运行状况</span><span class="sxs-lookup"><span data-stu-id="93543-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="93543-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="93543-105">**Applies to:**</span></span>
- [<span data-ttu-id="93543-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="93543-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="93543-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="93543-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93543-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="93543-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="93543-109">**服务运行状况** 提供有关 Defender for Endpoint 服务的当前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="93543-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="93543-110">你将能够验证服务运行状况是否正常或当前是否有问题。</span><span class="sxs-lookup"><span data-stu-id="93543-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="93543-111">如果存在问题，你将看到诸如何时检测到问题、初步确定的根本原因以及预期解决时间等信息。</span><span class="sxs-lookup"><span data-stu-id="93543-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="93543-112">你还将看到已解决的历史问题的信息以及诸如解决问题的日期和时间等详细信息。</span><span class="sxs-lookup"><span data-stu-id="93543-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="93543-113">当服务没有问题时，你将看到正常状态。</span><span class="sxs-lookup"><span data-stu-id="93543-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="93543-114">可以通过单击安全操作仪表板中的磁贴或从导航窗格中选择"**服务** 运行状况"菜单来查看服务运行状况的详细信息。 </span><span class="sxs-lookup"><span data-stu-id="93543-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="93543-115">" **服务运行状况** 详细信息"页包含以下选项卡：</span><span class="sxs-lookup"><span data-stu-id="93543-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="93543-116">**当前状态**</span><span class="sxs-lookup"><span data-stu-id="93543-116">**Current status**</span></span>
- <span data-ttu-id="93543-117">**状态历史记录**</span><span class="sxs-lookup"><span data-stu-id="93543-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="93543-118">当前状态</span><span class="sxs-lookup"><span data-stu-id="93543-118">Current status</span></span>
<span data-ttu-id="93543-119">" **当前状态** "选项卡显示 Defender for Endpoint 服务的当前状态。</span><span class="sxs-lookup"><span data-stu-id="93543-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="93543-120">当服务平稳运行时，将显示正常的服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="93543-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="93543-121">如果发现问题，将显示以下服务详细信息，以帮助您更好地了解该问题：</span><span class="sxs-lookup"><span data-stu-id="93543-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="93543-122">检测到问题的日期和时间</span><span class="sxs-lookup"><span data-stu-id="93543-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="93543-123">问题的简短说明</span><span class="sxs-lookup"><span data-stu-id="93543-123">A short description of the issue</span></span>
- <span data-ttu-id="93543-124">更新时间</span><span class="sxs-lookup"><span data-stu-id="93543-124">Update time</span></span>
- <span data-ttu-id="93543-125">影响摘要</span><span class="sxs-lookup"><span data-stu-id="93543-125">Summary of impact</span></span>
- <span data-ttu-id="93543-126">初步的根本原因</span><span class="sxs-lookup"><span data-stu-id="93543-126">Preliminary root cause</span></span>
- <span data-ttu-id="93543-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="93543-127">Next steps</span></span>
- <span data-ttu-id="93543-128">预期的解决时间</span><span class="sxs-lookup"><span data-stu-id="93543-128">Expected resolution time</span></span>

<span data-ttu-id="93543-129">当问题解决时，页面上将反映问题进度的更新。</span><span class="sxs-lookup"><span data-stu-id="93543-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="93543-130">你将看到有关更新的信息，例如更新的估计解决时间或下一步步骤。</span><span class="sxs-lookup"><span data-stu-id="93543-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="93543-131">当问题解决时，该问题将记录在"状态 **历史记录"** 选项卡中。</span><span class="sxs-lookup"><span data-stu-id="93543-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="93543-132">状态历史记录</span><span class="sxs-lookup"><span data-stu-id="93543-132">Status history</span></span>
<span data-ttu-id="93543-133">" **状态历史记录** "选项卡反映已看到和已解决的所有历史问题。</span><span class="sxs-lookup"><span data-stu-id="93543-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="93543-134">你将看到已解决的问题的详细信息以及解决时包含的其他信息。</span><span class="sxs-lookup"><span data-stu-id="93543-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="93543-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="93543-135">Related topic</span></span>
- [<span data-ttu-id="93543-136">查看安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="93543-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
