---
title: Microsoft 威胁防护中的自定义检测概述
description: 了解如何使用高级搜寻来创建自定义检测并生成警报
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、microsoft 365、Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498347"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="c7bdd-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="c7bdd-104">Custom detections overview</span></span>

<span data-ttu-id="c7bdd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c7bdd-105">**Applies to:**</span></span>
- <span data-ttu-id="c7bdd-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c7bdd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c7bdd-107">使用自定义检测，可以主动监视和响应各种事件和系统状态，包括可疑的入侵活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="c7bdd-108">这可通过可自定义的检测规则（自动触发警报和响应操作）实现。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="c7bdd-109">自定义检测适用于[高级搜寻](advanced-hunting-overview.md)，它提供一种功能强大的灵活的查询语言，可覆盖网络中的一组大量事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="c7bdd-110">您可以将其设置为定期运行，并在存在匹配项时生成警报和采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="c7bdd-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="c7bdd-111">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="c7bdd-111">Custom detections provide:</span></span>
- <span data-ttu-id="c7bdd-112">从高级搜寻查询生成的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="c7bdd-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="c7bdd-113">自动响应操作</span><span class="sxs-lookup"><span data-stu-id="c7bdd-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="c7bdd-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="c7bdd-114">Related topic</span></span>
- [<span data-ttu-id="c7bdd-115">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="c7bdd-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="c7bdd-116">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="c7bdd-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)