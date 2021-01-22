---
title: 监视和查看报告 - 安全中心
description: 介绍 Microsoft 365 安全中心如何提供保护和安全状态概览摘要。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视器， 报告， 状态
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930398"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="d0ded-104">在 Microsoft 365 安全中心中监视和查看报告</span><span class="sxs-lookup"><span data-stu-id="d0ded-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="d0ded-105">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="d0ded-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="d0ded-106">可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="d0ded-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="d0ded-107">Microsoft 365 安全中心提供了 Microsoft 365 环境中保护和安全状态的摘要。</span><span class="sxs-lookup"><span data-stu-id="d0ded-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="d0ded-108">安全中心包括一 **个"** 报告"部分，其中包含一系列覆盖各种领域的卡片。</span><span class="sxs-lookup"><span data-stu-id="d0ded-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="d0ded-109">安全分析师和管理员可以在日常操作中跟踪卡片。</span><span class="sxs-lookup"><span data-stu-id="d0ded-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="d0ded-110">在向下钻取时，卡片提供详细的报告，在某些情况下，提供管理选项。</span><span class="sxs-lookup"><span data-stu-id="d0ded-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="d0ded-111">自定义视图</span><span class="sxs-lookup"><span data-stu-id="d0ded-111">Customize views</span></span>

<span data-ttu-id="d0ded-112">默认情况下，卡片分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="d0ded-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="d0ded-113">[标识](monitor-and-report-identities.md) - 用户帐户和凭据</span><span class="sxs-lookup"><span data-stu-id="d0ded-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="d0ded-114">[数据](monitor-data.md) - 电子邮件和文档内容</span><span class="sxs-lookup"><span data-stu-id="d0ded-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="d0ded-115">[设备](monitor-devices.md) - 计算机、移动电话和其他设备</span><span class="sxs-lookup"><span data-stu-id="d0ded-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="d0ded-116">[应用](monitor-apps.md) - 程序和附加的联机服务</span><span class="sxs-lookup"><span data-stu-id="d0ded-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="d0ded-117">按主题 **切换到组**，重新排列卡片，并分组为下列主题：</span><span class="sxs-lookup"><span data-stu-id="d0ded-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="d0ded-118">**风险** - 突出显示可能面临风险的实体（如帐户和设备）的卡片。</span><span class="sxs-lookup"><span data-stu-id="d0ded-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="d0ded-119">这些卡片还突出显示了可能的风险来源，例如新的威胁市场活动和特权云应用</span><span class="sxs-lookup"><span data-stu-id="d0ded-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="d0ded-120">**检测趋势** - 突出显示新威胁检测、异常和策略违反的卡片</span><span class="sxs-lookup"><span data-stu-id="d0ded-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="d0ded-121">**配置和运行状况** - 涵盖安全控件的配置和部署的卡，包括设备载入到管理服务状态</span><span class="sxs-lookup"><span data-stu-id="d0ded-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="d0ded-122">**其他** - 所有其他未在其他主题下分类的卡片</span><span class="sxs-lookup"><span data-stu-id="d0ded-122">**Other** - all other cards not categorized under other topics</span></span>
