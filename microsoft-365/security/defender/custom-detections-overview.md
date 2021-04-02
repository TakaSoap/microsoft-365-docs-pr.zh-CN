---
title: Microsoft 365 Defender 中的自定义检测概述
description: 了解如何使用高级搜寻创建自定义检测和生成警报
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 589a15aa456a96a5eef8042d922d338f056a882d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498834"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="72581-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="72581-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="72581-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="72581-105">**Applies to:**</span></span>
- <span data-ttu-id="72581-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72581-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="72581-107">通过自定义检测，您可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="72581-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="72581-108">这通过可自定义的检测规则实现，这些规则可自动触发警报和响应操作。</span><span class="sxs-lookup"><span data-stu-id="72581-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="72581-109">自定义 [检测与高级](advanced-hunting-overview.md)搜寻一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的广泛事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="72581-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="72581-110">你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="72581-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="72581-111">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="72581-111">Custom detections provide:</span></span>
- <span data-ttu-id="72581-112">针对从高级搜寻查询构建的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="72581-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="72581-113">自动响应操作</span><span class="sxs-lookup"><span data-stu-id="72581-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="72581-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72581-114">See also</span></span>
- [<span data-ttu-id="72581-115">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="72581-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="72581-116">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="72581-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72581-117">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="72581-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
