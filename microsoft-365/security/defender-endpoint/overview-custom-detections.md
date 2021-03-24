---
title: Microsoft Defender ATP 中的自定义检测概述
ms.reviewer: ''
description: 了解如何使用高级搜寻创建自定义检测和生成警报
keywords: 自定义检测， 警报， 检测规则， 高级搜寻， 智能寻线， 查询， 响应操作， 间隔， mdatp， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054632"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="3527e-104">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="3527e-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3527e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3527e-105">**Applies to:**</span></span>
- [<span data-ttu-id="3527e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3527e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3527e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3527e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3527e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3527e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3527e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3527e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="3527e-110">通过自定义检测，你可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的设备。</span><span class="sxs-lookup"><span data-stu-id="3527e-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="3527e-111">为此，可以使用可自动触发警报和响应操作且可自定义的检测规则。</span><span class="sxs-lookup"><span data-stu-id="3527e-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="3527e-112">自定义 [检测与高级](advanced-hunting-overview.md)搜寻一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的广泛事件和系统信息。</span><span class="sxs-lookup"><span data-stu-id="3527e-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="3527e-113">你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="3527e-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="3527e-114">自定义检测提供：</span><span class="sxs-lookup"><span data-stu-id="3527e-114">Custom detections provide:</span></span>
- <span data-ttu-id="3527e-115">针对从高级搜寻查询构建的基于规则的检测的警报</span><span class="sxs-lookup"><span data-stu-id="3527e-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="3527e-116">适用于文件和设备的自动响应操作</span><span class="sxs-lookup"><span data-stu-id="3527e-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="3527e-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="3527e-117">Related topics</span></span>
- [<span data-ttu-id="3527e-118">创建检测规则</span><span class="sxs-lookup"><span data-stu-id="3527e-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="3527e-119">查看和管理检测规则</span><span class="sxs-lookup"><span data-stu-id="3527e-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="3527e-120">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="3527e-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
