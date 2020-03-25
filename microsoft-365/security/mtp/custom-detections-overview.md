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
ms.openlocfilehash: a9ba61650b69e3c42506735c90ae05b917a53209
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931719"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="0c6ff-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="0c6ff-104">Custom detections overview</span></span>

<span data-ttu-id="0c6ff-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0c6ff-105">**Applies to:**</span></span>
- <span data-ttu-id="0c6ff-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="0c6ff-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0c6ff-107">使用自定义检测，可以主动监视和响应各种事件和系统状态，包括可疑的入侵活动和错误配置的终结点。</span><span class="sxs-lookup"><span data-stu-id="0c6ff-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="0c6ff-108">这可通过可自定义的检测规则（自动触发警报和响应操作）实现。</span><span class="sxs-lookup"><span data-stu-id="0c6ff-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="0c6ff-109">自定义检测适用于[高级搜寻](advanced-hunting-overview.md)，它提供一种功能强大的灵活的查询语言，可覆盖网络中的一组大量事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="0c6ff-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="0c6ff-110">您可以将其设置为定期运行，并在存在匹配项时生成警报和采取响应操作。</span><span class="sxs-lookup"><span data-stu-id="0c6ff-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="0c6ff-111">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="0c6ff-111">Custom detections provide:</span></span>
- <span data-ttu-id="0c6ff-112">从高级搜寻查询生成的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="0c6ff-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="0c6ff-113">自动响应操作</span><span class="sxs-lookup"><span data-stu-id="0c6ff-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="0c6ff-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c6ff-114">Related topic</span></span>
- [<span data-ttu-id="0c6ff-115">创建和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="0c6ff-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="0c6ff-116">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0c6ff-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)