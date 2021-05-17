---
title: Microsoft Defender 安全中心时区设置
description: 使用此处包含的信息配置Microsoft Defender 安全中心时区设置并查看许可证信息。
keywords: 设置， Microsoft Defender， 网络安全威胁智能， 适用于终结点的 Microsoft Defender， 时区， utc， 本地时间， 许可证
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: df55a1b0e92c24b5f52032330ef95bf19aeb8cb3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932627"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="9f949-104">Microsoft Defender 安全中心时区设置</span><span class="sxs-lookup"><span data-stu-id="9f949-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f949-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9f949-105">**Applies to:**</span></span>
- [<span data-ttu-id="9f949-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9f949-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="9f949-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9f949-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f949-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9f949-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="9f949-109">使用 **时区菜单** ![ 时区设置图标 1 ](images/atp-time-zone.png) 配置时区和查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="9f949-109">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="9f949-110">时区设置</span><span class="sxs-lookup"><span data-stu-id="9f949-110">Time zone settings</span></span>
<span data-ttu-id="9f949-111">时间方面对于评估和分析感知的和实际的网络攻击非常重要。</span><span class="sxs-lookup"><span data-stu-id="9f949-111">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="9f949-112">网络forensic调查通常依赖时间戳来拼贴事件序列。</span><span class="sxs-lookup"><span data-stu-id="9f949-112">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="9f949-113">系统反映正确的时区设置非常重要。</span><span class="sxs-lookup"><span data-stu-id="9f949-113">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="9f949-114">Microsoft Defender for Endpoint 可以显示协调世界时 (UTC) 本地时间。</span><span class="sxs-lookup"><span data-stu-id="9f949-114">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="9f949-115">你的当前时区设置显示在 Microsoft Defender for Endpoint 菜单中。</span><span class="sxs-lookup"><span data-stu-id="9f949-115">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="9f949-116">可以在"时区"菜单中更改显示的 **时区** 。</span><span class="sxs-lookup"><span data-stu-id="9f949-116">You can change the displayed time zone in the **Time zone** menu.</span></span>

![时区设置图标 2](images/atp-time-zone-menu.png)<span data-ttu-id="9f949-118">.</span><span class="sxs-lookup"><span data-stu-id="9f949-118">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="9f949-119">UTC 时区</span><span class="sxs-lookup"><span data-stu-id="9f949-119">UTC time zone</span></span>
<span data-ttu-id="9f949-120">默认情况下，Microsoft Defender for Endpoint 使用 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="9f949-120">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="9f949-121">将 Microsoft Defender for Endpoint 时区设置为 UTC 将显示所有用户的所有 (、事件和其他) UTC 格式的系统时间戳。</span><span class="sxs-lookup"><span data-stu-id="9f949-121">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="9f949-122">这可以帮助在全球不同位置工作的安全分析师在调查事件时使用相同的时间戳。</span><span class="sxs-lookup"><span data-stu-id="9f949-122">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="9f949-123">本地时区</span><span class="sxs-lookup"><span data-stu-id="9f949-123">Local time zone</span></span>
<span data-ttu-id="9f949-124">你可以选择让 Microsoft Defender for Endpoint 使用本地时区设置。</span><span class="sxs-lookup"><span data-stu-id="9f949-124">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="9f949-125">所有警报和事件都将使用本地时区显示。</span><span class="sxs-lookup"><span data-stu-id="9f949-125">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="9f949-126">本地时区取自设备的区域设置。</span><span class="sxs-lookup"><span data-stu-id="9f949-126">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="9f949-127">如果你更改你的区域设置，Microsoft Defender 终结点时区也将更改。</span><span class="sxs-lookup"><span data-stu-id="9f949-127">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="9f949-128">选择此设置意味着 Microsoft Defender for Endpoint 中显示的时间戳将针对所有 Microsoft Defender for Endpoint 用户与本地时间保持一致。</span><span class="sxs-lookup"><span data-stu-id="9f949-128">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="9f949-129">位于不同全球地点的分析师现在将看到 Microsoft Defender for Endpoint 警报，其区域设置也不同。</span><span class="sxs-lookup"><span data-stu-id="9f949-129">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="9f949-130">如果分析师位于单个位置，则选择使用本地时间可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="9f949-130">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="9f949-131">在这种情况下，将事件关联到本地时间可能会更容易，例如，当本地用户单击可疑电子邮件链接时。</span><span class="sxs-lookup"><span data-stu-id="9f949-131">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="9f949-132">设置时区</span><span class="sxs-lookup"><span data-stu-id="9f949-132">Set the time zone</span></span>
<span data-ttu-id="9f949-133">默认情况下，Microsoft Defender for Endpoint 时区设置为 UTC。</span><span class="sxs-lookup"><span data-stu-id="9f949-133">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="9f949-134">设置时区还会更改所有 Microsoft Defender 终结点视图的时间。</span><span class="sxs-lookup"><span data-stu-id="9f949-134">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="9f949-135">设置时区：</span><span class="sxs-lookup"><span data-stu-id="9f949-135">To set the time zone:</span></span>

1. <span data-ttu-id="9f949-136">单击时区 **菜单时区** ![ 设置图标 3 ](images/atp-time-zone.png) 。</span><span class="sxs-lookup"><span data-stu-id="9f949-136">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="9f949-137">选择 **时区 UTC** 指示器。</span><span class="sxs-lookup"><span data-stu-id="9f949-137">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="9f949-138">选择 **时区 UTC** 或本地时区，例如 -7：00。</span><span class="sxs-lookup"><span data-stu-id="9f949-138">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="9f949-139">区域设置</span><span class="sxs-lookup"><span data-stu-id="9f949-139">Regional settings</span></span>
<span data-ttu-id="9f949-140">若要为 Microsoft Defender for Endpoint 应用不同的日期格式，请使用 IE Internet Explorer (区域设置) Microsoft Edge (Edge) 。</span><span class="sxs-lookup"><span data-stu-id="9f949-140">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="9f949-141">如果你使用的是其他浏览器（如 Google Chrome），请按照所需步骤更改该浏览器的时间和日期设置。</span><span class="sxs-lookup"><span data-stu-id="9f949-141">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="9f949-142">**Internet Explorer (IE) 和 Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="9f949-142">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="9f949-143">IE 和 Microsoft Edge使用"控制面板"中"时钟、**语言** 和地区"选项中配置的"区域"设置。</span><span class="sxs-lookup"><span data-stu-id="9f949-143">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="9f949-144">区域格式的已知问题</span><span class="sxs-lookup"><span data-stu-id="9f949-144">Known issues with regional formats</span></span>

<span data-ttu-id="9f949-145">**日期和时间格式**</span><span class="sxs-lookup"><span data-stu-id="9f949-145">**Date and time formats**</span></span><br>
<span data-ttu-id="9f949-146">时间和日期格式存在一些已知问题。</span><span class="sxs-lookup"><span data-stu-id="9f949-146">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="9f949-147">如果将区域设置配置为支持的格式外的其他任何内容，门户可能无法正确反映你的设置。</span><span class="sxs-lookup"><span data-stu-id="9f949-147">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="9f949-148">支持以下日期和时间格式：</span><span class="sxs-lookup"><span data-stu-id="9f949-148">The following date and time formats are supported:</span></span>
- <span data-ttu-id="9f949-149">日期格式 MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="9f949-149">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="9f949-150">日期格式 dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="9f949-150">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="9f949-151">时间格式 hh：mm：ss (12 小时格式) </span><span class="sxs-lookup"><span data-stu-id="9f949-151">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="9f949-152">目前不支持以下日期和时间格式：</span><span class="sxs-lookup"><span data-stu-id="9f949-152">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="9f949-153">日期格式 yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="9f949-153">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="9f949-154">日期格式 dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="9f949-154">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="9f949-155">日期格式 dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="9f949-155">Date format dd/MM/yy</span></span>
- <span data-ttu-id="9f949-156">日期格式 MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="9f949-156">Date format MM/dd/yy</span></span>
- <span data-ttu-id="9f949-157">yy 的日期格式。</span><span class="sxs-lookup"><span data-stu-id="9f949-157">Date format with yy.</span></span> <span data-ttu-id="9f949-158">将只显示 yyyy。</span><span class="sxs-lookup"><span data-stu-id="9f949-158">Will only show yyyy.</span></span>
- <span data-ttu-id="9f949-159">时间格式 HH：mm：ss (24 小时格式) </span><span class="sxs-lookup"><span data-stu-id="9f949-159">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="9f949-160">**数字中使用的小数符号**</span><span class="sxs-lookup"><span data-stu-id="9f949-160">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="9f949-161">使用的小数符号始终是一个点，即使在"区域设置"中的"数字 **"格式** 设置中选择了 **逗号** 。</span><span class="sxs-lookup"><span data-stu-id="9f949-161">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="9f949-162">例如，15，5K 显示为 15.5K。</span><span class="sxs-lookup"><span data-stu-id="9f949-162">For example, 15,5K is displayed as 15.5K.</span></span>


