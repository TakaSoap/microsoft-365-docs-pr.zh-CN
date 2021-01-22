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
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928804"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="e54ce-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="e54ce-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e54ce-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e54ce-105">**Applies to:**</span></span>
- <span data-ttu-id="e54ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e54ce-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e54ce-107">通过自定义检测，您可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="e54ce-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="e54ce-108">这通过可自动触发警报和响应操作可自定义的检测规则实现。</span><span class="sxs-lookup"><span data-stu-id="e54ce-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="e54ce-109">自定义检测 [与高级搜寻](advanced-hunting-overview.md)一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的一组广泛的事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="e54ce-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="e54ce-110">你可以将它们设置为定期运行，生成警报，并随时执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="e54ce-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="e54ce-111">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="e54ce-111">Custom detections provide:</span></span>
- <span data-ttu-id="e54ce-112">针对从高级搜寻查询构建的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="e54ce-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="e54ce-113">自动响应操作</span><span class="sxs-lookup"><span data-stu-id="e54ce-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="e54ce-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="e54ce-114">Related topic</span></span>
- [<span data-ttu-id="e54ce-115">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="e54ce-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="e54ce-116">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="e54ce-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
