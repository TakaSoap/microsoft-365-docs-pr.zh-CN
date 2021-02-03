---
title: Microsoft 365 Defender 中的自定义检测概述
description: 了解如何使用高级搜寻创建自定义检测并生成警报
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: de9fb28f09b88cf1730f3bb3539234f6a03ec2e3
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080709"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="da79f-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="da79f-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="da79f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="da79f-105">**Applies to:**</span></span>
- <span data-ttu-id="da79f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da79f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="da79f-107">通过自定义检测，您可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="da79f-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="da79f-108">这通过可自动触发警报和响应操作可自定义的检测规则实现。</span><span class="sxs-lookup"><span data-stu-id="da79f-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="da79f-109">自定义检测 [与高级搜寻](advanced-hunting-overview.md)一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的一组广泛的事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="da79f-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="da79f-110">你可以将它们设置为定期运行，生成警报，并随时执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="da79f-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="da79f-111">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="da79f-111">Custom detections provide:</span></span>
- <span data-ttu-id="da79f-112">针对从高级搜寻查询构建的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="da79f-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="da79f-113">自动响应操作</span><span class="sxs-lookup"><span data-stu-id="da79f-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="da79f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da79f-114">See also</span></span>
- [<span data-ttu-id="da79f-115">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="da79f-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="da79f-116">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="da79f-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="da79f-117">从 Microsoft Defender for Endpoint 迁移高级搜寻查询</span><span class="sxs-lookup"><span data-stu-id="da79f-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
