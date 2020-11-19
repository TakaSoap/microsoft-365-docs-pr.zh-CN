---
title: 监视和查看报告-安全中心
description: 介绍 Microsoft 365 安全中心如何一目了然地概述保护和安全状态。
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、status
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356879"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="2804f-104">在 Microsoft 365 安全中心中监视和查看报告</span><span class="sxs-lookup"><span data-stu-id="2804f-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="2804f-105">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="2804f-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="2804f-106">您可以 [在实验室环境中对其进行评估](https://aka.ms/mtp-trial-lab) ，也可以 [在生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="2804f-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="2804f-107">Microsoft 365 安全中心在 Microsoft 365 环境中提供了保护和安全状态的摘要。</span><span class="sxs-lookup"><span data-stu-id="2804f-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="2804f-108">安全中心包含一个 **报告** 部分，其中提供了一系列涵盖各种区域的卡的主机。</span><span class="sxs-lookup"><span data-stu-id="2804f-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="2804f-109">安全分析员和管理员可以在日常操作中跟踪卡片。</span><span class="sxs-lookup"><span data-stu-id="2804f-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="2804f-110">在向下钻取时，卡片提供了详细报告，在某些情况下，还提供了管理选项。</span><span class="sxs-lookup"><span data-stu-id="2804f-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="2804f-111">自定义视图</span><span class="sxs-lookup"><span data-stu-id="2804f-111">Customize views</span></span>

<span data-ttu-id="2804f-112">默认情况下，卡片分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="2804f-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="2804f-113">[标识](monitor-and-report-identities.md) -用户帐户和凭据</span><span class="sxs-lookup"><span data-stu-id="2804f-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="2804f-114">[Data](monitor-data.md) -电子邮件和文档内容</span><span class="sxs-lookup"><span data-stu-id="2804f-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="2804f-115">[设备](monitor-devices.md) -计算机、移动电话和其他设备</span><span class="sxs-lookup"><span data-stu-id="2804f-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="2804f-116">[应用](monitor-apps.md) 程序-程序和附加的联机服务</span><span class="sxs-lookup"><span data-stu-id="2804f-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="2804f-117">切换到 " **按主题分组**"，重新排列卡片并将其分组到以下主题中：</span><span class="sxs-lookup"><span data-stu-id="2804f-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="2804f-118">**风险** 卡片，突出显示可能存在风险的实体（如帐户和设备）。</span><span class="sxs-lookup"><span data-stu-id="2804f-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="2804f-119">这些卡片还突出显示了可能的风险来源，如新的威胁活动和特权云应用</span><span class="sxs-lookup"><span data-stu-id="2804f-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="2804f-120">**检测趋势** -突出显示新的威胁检测、异常和策略违规的卡片</span><span class="sxs-lookup"><span data-stu-id="2804f-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="2804f-121">**配置和运行状况** ，包括安全控制的配置和部署，包括将设备加入状态到管理服务</span><span class="sxs-lookup"><span data-stu-id="2804f-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="2804f-122">**其他-其他** 所有不按其他主题分类的卡片</span><span class="sxs-lookup"><span data-stu-id="2804f-122">**Other** - all other cards not categorized under other topics</span></span>
