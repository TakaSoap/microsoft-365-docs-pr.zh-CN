---
title: Microsoft 威胁防护中的预览功能
description: 了解 Microsoft 365 安全中的新功能
keywords: 预览版、new、m365 security、security、365、功能
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048263"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="f0086-104">Microsoft 威胁防护预览功能</span><span class="sxs-lookup"><span data-stu-id="f0086-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="f0086-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f0086-105">**Applies to:**</span></span>
- <span data-ttu-id="f0086-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f0086-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="f0086-107">Microsoft 威胁防护服务不断更新，以提供新的功能增强功能和功能。</span><span class="sxs-lookup"><span data-stu-id="f0086-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="f0086-108">了解 Microsoft 威胁防护预览版本中的新功能，并通过启用预览体验在首次尝试即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="f0086-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="f0086-109">有关新增功能的详细信息，请参阅 [Microsoft 威胁防护中的新增功能](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="f0086-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="f0086-110">打开预览功能</span><span class="sxs-lookup"><span data-stu-id="f0086-110">Turn on preview features</span></span>
<span data-ttu-id="f0086-111">你将有权访问即将推出的功能，您可以在中提供反馈，以帮助改进功能，使其在功能普遍可用之前获得全面体验。</span><span class="sxs-lookup"><span data-stu-id="f0086-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="f0086-112">打开预览体验设置，使其在第一次尝试即将推出的功能中。</span><span class="sxs-lookup"><span data-stu-id="f0086-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="f0086-113">在导航窗格中，选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="f0086-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="f0086-114">选择 " **Microsoft 威胁防护**"。</span><span class="sxs-lookup"><span data-stu-id="f0086-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="f0086-115">选择 "**预览功能**  >  **" "打开预览功能"**。</span><span class="sxs-lookup"><span data-stu-id="f0086-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="f0086-116">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f0086-116">Select **Save**.</span></span>

<span data-ttu-id="f0086-117">当您看到 "**打开预览功能**" 复选框处于选中状态时，您将知道已经打开了预览功能。</span><span class="sxs-lookup"><span data-stu-id="f0086-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="f0086-118">预览功能</span><span class="sxs-lookup"><span data-stu-id="f0086-118">Preview features</span></span>
<span data-ttu-id="f0086-119">目前，预览中提供了以下功能和增强功能：</span><span class="sxs-lookup"><span data-stu-id="f0086-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="f0086-120">**["门户架构参考"](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** —有关安全中心中直接使用的架构表的信息。</span><span class="sxs-lookup"><span data-stu-id="f0086-120">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — information about schema tables available directly in the security center.</span></span> <span data-ttu-id="f0086-121">除了表和列说明之外，此参考还提供有关受支持的事件类型（ `ActionType` 值）和示例查询的信息。</span><span class="sxs-lookup"><span data-stu-id="f0086-121">In addition to table and column descriptions, this reference provides information about supported event types (`ActionType` values) and sample queries.</span></span>  

- <span data-ttu-id="f0086-122">**[标识和应用程序表](advanced-hunting-schema-tables.md)**—使用高级搜寻架构中的[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表深入了解身份验证事件、Active Directory 查询和与应用程序相关的活动。</span><span class="sxs-lookup"><span data-stu-id="f0086-122">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="f0086-123">**[进入寻找](advanced-hunting-go-hunt.md)**--快速透视，从调查事件到使用基于查询的[高级](advanced-hunting-overview.md)搜索功能检查特定事件、用户、设备或其他实体类型。</span><span class="sxs-lookup"><span data-stu-id="f0086-123">**[Go hunt](advanced-hunting-go-hunt.md)** — quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span>

- <span data-ttu-id="f0086-124">**[FileProfile （）函数](advanced-hunting-fileprofile-function.md)**—在你的[高级搜寻](advanced-hunting-overview.md)查询中使用，以合并全面的文件信息。</span><span class="sxs-lookup"><span data-stu-id="f0086-124">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
