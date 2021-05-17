---
title: Microsoft 365 Defender 中的自定义检测概述
description: 了解如何使用高级搜寻创建自定义检测和生成警报
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto
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
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952532"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="d9641-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="d9641-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d9641-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d9641-105">**Applies to:**</span></span>
- <span data-ttu-id="d9641-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9641-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d9641-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9641-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d9641-108">通过自定义检测，您可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="d9641-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="d9641-109">这通过可自定义的检测规则实现，这些规则可自动触发警报和响应操作。</span><span class="sxs-lookup"><span data-stu-id="d9641-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="d9641-110">自定义 [检测与高级](advanced-hunting-overview.md)搜寻一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的广泛事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="d9641-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="d9641-111">你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="d9641-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="d9641-112">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="d9641-112">Custom detections provide:</span></span>
- <span data-ttu-id="d9641-113">针对从高级搜寻查询构建的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="d9641-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="d9641-114">自动响应操作</span><span class="sxs-lookup"><span data-stu-id="d9641-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="d9641-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9641-115">See also</span></span>
- [<span data-ttu-id="d9641-116">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="d9641-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="d9641-117">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d9641-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d9641-118">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="d9641-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
