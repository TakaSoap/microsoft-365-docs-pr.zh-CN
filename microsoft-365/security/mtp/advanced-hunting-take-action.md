---
title: 对 Microsoft 365 Defender 中的高级搜寻查询结果执行操作
description: 快速解决高级搜寻查询结果中的威胁和受影响资产
keywords: 高级搜索、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、执行操作
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 506af82ec08ad6cd8dbeece5c1c2741e09e4817a
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842460"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="367b0-104">对高级搜寻查询结果执行操作</span><span class="sxs-lookup"><span data-stu-id="367b0-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="367b0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="367b0-105">**Applies to:**</span></span>
- <span data-ttu-id="367b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="367b0-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="367b0-107">您可以使用强大而全面的操作选项快速包含您在 [高级](advanced-hunting-overview.md) 搜索中找到的威胁或地址已泄露资产。</span><span class="sxs-lookup"><span data-stu-id="367b0-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="367b0-108">使用这些选项，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="367b0-108">With these options, you can:</span></span>

- <span data-ttu-id="367b0-109">对设备执行各种操作</span><span class="sxs-lookup"><span data-stu-id="367b0-109">Take various actions on devices</span></span>
- <span data-ttu-id="367b0-110">隔离文件</span><span class="sxs-lookup"><span data-stu-id="367b0-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="367b0-111">所需权限</span><span class="sxs-lookup"><span data-stu-id="367b0-111">Required permissions</span></span>
<span data-ttu-id="367b0-112">若要能够通过高级搜索执行操作，您需要在 Microsoft Defender for Endpoint 中具有一个角色，在 [设备上具有提交修正操作的权限](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)。</span><span class="sxs-lookup"><span data-stu-id="367b0-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="367b0-113">如果无法执行此操作，请联系全局管理员了解获取以下权限：</span><span class="sxs-lookup"><span data-stu-id="367b0-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="367b0-114">*> 威胁和漏洞管理的活动修正操作-修正处理*</span><span class="sxs-lookup"><span data-stu-id="367b0-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="367b0-115">对设备执行各种操作</span><span class="sxs-lookup"><span data-stu-id="367b0-115">Take various actions on devices</span></span>
<span data-ttu-id="367b0-116">您可以对由查询结果中的列标识的设备执行以下操作 `DeviceId` ：</span><span class="sxs-lookup"><span data-stu-id="367b0-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="367b0-117">隔离受影响的设备以包含感染或阻止攻击横向移动</span><span class="sxs-lookup"><span data-stu-id="367b0-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="367b0-118">收集调查包以获取更多的取证信息</span><span class="sxs-lookup"><span data-stu-id="367b0-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="367b0-119">运行防病毒扫描，以使用最新的安全智能更新查找并删除威胁</span><span class="sxs-lookup"><span data-stu-id="367b0-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="367b0-120">启动自动调查以检查和修正设备上可能受影响的其他设备上的威胁</span><span class="sxs-lookup"><span data-stu-id="367b0-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="367b0-121">仅将应用程序执行限制为 Microsoft 签名的可执行文件，从而通过恶意软件或其他不受信任的可执行文件阻止后续威胁活动</span><span class="sxs-lookup"><span data-stu-id="367b0-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="367b0-122">若要了解有关如何通过 Microsoft Defender for Endpoint 执行这些响应操作的详细信息，请 [阅读有关设备的响应操作的信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。</span><span class="sxs-lookup"><span data-stu-id="367b0-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="367b0-123">隔离文件</span><span class="sxs-lookup"><span data-stu-id="367b0-123">Quarantine files</span></span>
<span data-ttu-id="367b0-124">您可以对文件部署 *隔离* 操作，以便在遇到时自动隔离这些文件。</span><span class="sxs-lookup"><span data-stu-id="367b0-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="367b0-125">选择此操作时，可以在下列各列之间进行选择，以确定要隔离的查询结果中的哪些文件：</span><span class="sxs-lookup"><span data-stu-id="367b0-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="367b0-126">`SHA1` —在大多数高级搜寻表中，这是受录制操作影响的文件的 SHA-1。</span><span class="sxs-lookup"><span data-stu-id="367b0-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="367b0-127">例如，如果复制了文件，则该文件是复制的文件。</span><span class="sxs-lookup"><span data-stu-id="367b0-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="367b0-128">`InitiatingProcessSHA1` —在大多数高级搜寻表中，这是负责启动录制的操作的文件。</span><span class="sxs-lookup"><span data-stu-id="367b0-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="367b0-129">例如，如果已启动子进程，则为父进程。</span><span class="sxs-lookup"><span data-stu-id="367b0-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="367b0-130">`SHA256` —这是与列所标识文件的 SHA-256 等效项 `SHA1` 。</span><span class="sxs-lookup"><span data-stu-id="367b0-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="367b0-131">`InitiatingProcessSHA256` —这是与列所标识文件的 SHA-256 等效项 `InitiatingProcessSHA1` 。</span><span class="sxs-lookup"><span data-stu-id="367b0-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="367b0-132">若要了解有关如何执行隔离操作和还原文件的详细信息，请 [阅读有关文件的响应操作的信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)。</span><span class="sxs-lookup"><span data-stu-id="367b0-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="367b0-133">若要查找文件并将其隔离，查询结果还应将 `DeviceId` 值作为设备标识符包括在内。</span><span class="sxs-lookup"><span data-stu-id="367b0-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="367b0-134">执行操作</span><span class="sxs-lookup"><span data-stu-id="367b0-134">Take action</span></span>
<span data-ttu-id="367b0-135">若要执行任何所述的操作，请在查询结果中选择一个或多个记录，然后选择 " **采取操作** "。</span><span class="sxs-lookup"><span data-stu-id="367b0-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="367b0-136">向导将指导您完成选择和提交首选操作的过程。</span><span class="sxs-lookup"><span data-stu-id="367b0-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="367b0-138">查看所执行的操作</span><span class="sxs-lookup"><span data-stu-id="367b0-138">Review actions taken</span></span>
<span data-ttu-id="367b0-139">每个操作都将在操作 [中心](mtp-action-center.md)中单独记录在 " **操作中心**  >  **历史记录** ( [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history) ") "下。</span><span class="sxs-lookup"><span data-stu-id="367b0-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="367b0-140">转到操作中心以检查每个操作的状态。</span><span class="sxs-lookup"><span data-stu-id="367b0-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="367b0-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="367b0-141">Related topics</span></span>
- [<span data-ttu-id="367b0-142">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="367b0-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="367b0-143">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="367b0-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="367b0-144">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="367b0-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="367b0-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="367b0-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="367b0-146">操作中心概述</span><span class="sxs-lookup"><span data-stu-id="367b0-146">Action center overview</span></span>](mtp-action-center.md)
