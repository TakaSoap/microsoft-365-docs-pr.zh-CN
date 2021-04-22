---
title: 在 Microsoft 365 Defender 中对高级搜寻查询结果采取措施
description: 在高级搜寻查询结果中快速解决威胁和受影响的资产
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 采取行动
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0c088375cd784b411fdce417d77b1ea176bcee26
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932901"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="22b05-104">对高级搜寻查询结果采取措施</span><span class="sxs-lookup"><span data-stu-id="22b05-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="22b05-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="22b05-105">**Applies to:**</span></span>
- <span data-ttu-id="22b05-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22b05-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="22b05-107">使用强大而全面的操作选项，可以快速包含威胁或解决在高级[](advanced-hunting-overview.md)搜寻中发现的威胁资产。</span><span class="sxs-lookup"><span data-stu-id="22b05-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="22b05-108">通过这些选项，您可以：</span><span class="sxs-lookup"><span data-stu-id="22b05-108">With these options, you can:</span></span>

- <span data-ttu-id="22b05-109">在设备上执行各种操作</span><span class="sxs-lookup"><span data-stu-id="22b05-109">Take various actions on devices</span></span>
- <span data-ttu-id="22b05-110">隔离文件</span><span class="sxs-lookup"><span data-stu-id="22b05-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="22b05-111">所需权限</span><span class="sxs-lookup"><span data-stu-id="22b05-111">Required permissions</span></span>
<span data-ttu-id="22b05-112">若要能够通过高级搜寻采取行动，你需要具有在设备上提交修正操作的权限的 Microsoft Defender for Endpoint [角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="22b05-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="22b05-113">如果无法采取措施，请与全局管理员联系，获取以下权限：</span><span class="sxs-lookup"><span data-stu-id="22b05-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="22b05-114">*威胁和>管理的活动修正操作 - 修正处理*</span><span class="sxs-lookup"><span data-stu-id="22b05-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="22b05-115">在设备上执行各种操作</span><span class="sxs-lookup"><span data-stu-id="22b05-115">Take various actions on devices</span></span>
<span data-ttu-id="22b05-116">可以在查询结果中的列标识的 `DeviceId` 设备上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22b05-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="22b05-117">隔离受影响的设备以包含感染或阻止攻击以稍后移动</span><span class="sxs-lookup"><span data-stu-id="22b05-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="22b05-118">收集调查包以获取更多取证信息</span><span class="sxs-lookup"><span data-stu-id="22b05-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="22b05-119">运行防病毒扫描以使用最新的安全智能更新查找和删除威胁</span><span class="sxs-lookup"><span data-stu-id="22b05-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="22b05-120">启动自动调查，以检查和修正设备上以及可能受影响的其他设备上的威胁</span><span class="sxs-lookup"><span data-stu-id="22b05-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="22b05-121">将应用执行限制为仅 Microsoft 签名的可执行文件，阻止通过恶意软件或其他不受信任的可执行文件进行后续威胁活动</span><span class="sxs-lookup"><span data-stu-id="22b05-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="22b05-122">若要了解有关如何通过 Microsoft Defender for Endpoint 执行这些响应操作的信息， [请阅读有关设备的响应操作](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。</span><span class="sxs-lookup"><span data-stu-id="22b05-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="22b05-123">隔离文件</span><span class="sxs-lookup"><span data-stu-id="22b05-123">Quarantine files</span></span>
<span data-ttu-id="22b05-124">您可以对 *文件部署* 隔离操作，以便遇到文件时自动隔离它们。</span><span class="sxs-lookup"><span data-stu-id="22b05-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="22b05-125">选择此操作时，可以选择以下各列以标识查询结果中要隔离的文件：</span><span class="sxs-lookup"><span data-stu-id="22b05-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="22b05-126">`SHA1` — 在大多数高级搜寻表中，这是受录制操作影响的文件的 SHA-1。</span><span class="sxs-lookup"><span data-stu-id="22b05-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="22b05-127">例如，如果复制了文件，则这是复制的文件。</span><span class="sxs-lookup"><span data-stu-id="22b05-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="22b05-128">`InitiatingProcessSHA1` — 在大部分高级搜寻表中，这是负责启动录制的操作的文件。</span><span class="sxs-lookup"><span data-stu-id="22b05-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="22b05-129">例如，如果启动子进程，这将是父进程。</span><span class="sxs-lookup"><span data-stu-id="22b05-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="22b05-130">`SHA256` — 这是由列标识的文件的 SHA-256 `SHA1` 等效项。</span><span class="sxs-lookup"><span data-stu-id="22b05-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="22b05-131">`InitiatingProcessSHA256` — 这是由列标识的文件的 SHA-256 `InitiatingProcessSHA1` 等效项。</span><span class="sxs-lookup"><span data-stu-id="22b05-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="22b05-132">若要详细了解如何执行隔离操作以及如何还原文件，请阅读 [有关文件的响应操作](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。</span><span class="sxs-lookup"><span data-stu-id="22b05-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="22b05-133">若要查找并隔离文件，查询结果还应包括作为 `DeviceId` 设备标识符的值。</span><span class="sxs-lookup"><span data-stu-id="22b05-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="22b05-134">采取操作</span><span class="sxs-lookup"><span data-stu-id="22b05-134">Take action</span></span>
<span data-ttu-id="22b05-135">若要执行任何描述的操作，请在查询结果中选择一个或多个记录，然后选择"**采取操作"。**</span><span class="sxs-lookup"><span data-stu-id="22b05-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="22b05-136">向导将指导你完成选择并提交首选操作的过程。</span><span class="sxs-lookup"><span data-stu-id="22b05-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="22b05-138">查看已采取的操作</span><span class="sxs-lookup"><span data-stu-id="22b05-138">Review actions taken</span></span>
<span data-ttu-id="22b05-139">每个操作都单独记录在操作中心的"[](m365d-action-center.md)操作中心历史记录  >  " (security.microsoft.com/action-center/history) 。 [](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="22b05-139">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="22b05-140">转到操作中心以检查每个操作的状态。</span><span class="sxs-lookup"><span data-stu-id="22b05-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="22b05-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="22b05-141">Related topics</span></span>
- [<span data-ttu-id="22b05-142">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="22b05-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="22b05-143">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="22b05-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="22b05-144">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="22b05-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="22b05-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="22b05-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="22b05-146">操作中心概述</span><span class="sxs-lookup"><span data-stu-id="22b05-146">Action center overview</span></span>](m365d-action-center.md)
