---
title: 使用自动调查调查和修正威胁
description: 了解 Microsoft Defender for Endpoint 中的自动调查流程。
keywords: 自动化， 调查， 检测， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: d4b0751938b66cc22dd59e2e7035077c5ef59ff9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274816"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="eb836-104">自动调查概述</span><span class="sxs-lookup"><span data-stu-id="eb836-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eb836-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eb836-105">**Applies to:**</span></span>
- [<span data-ttu-id="eb836-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb836-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eb836-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb836-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="eb836-108">想要了解它的工作原理吗？</span><span class="sxs-lookup"><span data-stu-id="eb836-108">Want to see how it works?</span></span> <span data-ttu-id="eb836-109">观看以下视频：</span><span class="sxs-lookup"><span data-stu-id="eb836-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="eb836-110">自动调查中的技术使用各种检查算法，并且基于安全分析师使用的过程。</span><span class="sxs-lookup"><span data-stu-id="eb836-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="eb836-111">AIR 功能旨在检查警报并立即采取措施来解决违规问题。</span><span class="sxs-lookup"><span data-stu-id="eb836-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="eb836-112">AIR 功能可显著减少警报量，使安全操作专注于更复杂的威胁和其他高价值计划。</span><span class="sxs-lookup"><span data-stu-id="eb836-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="eb836-113">所有修正操作（无论是挂起还是已完成）都跟踪在操作 [中心中](auto-investigation-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eb836-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="eb836-114">在操作中心中，挂起的操作 (或拒绝) ，如果需要，可以撤消已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="eb836-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="eb836-115">本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="eb836-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="eb836-116">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="eb836-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="eb836-117">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="eb836-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="eb836-118">自动调查的启动方式</span><span class="sxs-lookup"><span data-stu-id="eb836-118">How the automated investigation starts</span></span>

<span data-ttu-id="eb836-119">当触发警报或安全操作员启动调查时，可以启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="eb836-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="eb836-120">情况</span><span class="sxs-lookup"><span data-stu-id="eb836-120">Situation</span></span>  |<span data-ttu-id="eb836-121">发生的情况</span><span class="sxs-lookup"><span data-stu-id="eb836-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="eb836-122">触发警报</span><span class="sxs-lookup"><span data-stu-id="eb836-122">An alert is triggered</span></span>     | <span data-ttu-id="eb836-123">通常，自动调查在触发[警报并](review-alerts.md)[创建事件时](view-incidents-queue.md)启动。</span><span class="sxs-lookup"><span data-stu-id="eb836-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="eb836-124">例如，假设恶意文件驻留在设备上。</span><span class="sxs-lookup"><span data-stu-id="eb836-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="eb836-125">检测到该文件时，将触发警报并创建事件。</span><span class="sxs-lookup"><span data-stu-id="eb836-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="eb836-126">自动调查过程在设备上开始。</span><span class="sxs-lookup"><span data-stu-id="eb836-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="eb836-127">由于其他设备上生成了相同的文件，因此其他警报会添加到关联事件和自动调查。</span><span class="sxs-lookup"><span data-stu-id="eb836-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="eb836-128">手动启动调查</span><span class="sxs-lookup"><span data-stu-id="eb836-128">An investigation is started manually</span></span>     | <span data-ttu-id="eb836-129">安全运营团队可以手动启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="eb836-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="eb836-130">例如，假设安全操作员正在查看设备列表，并注意到设备具有高风险级别。</span><span class="sxs-lookup"><span data-stu-id="eb836-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="eb836-131">安全操作员可以选择列表中的设备以打开其飞出内容，然后选择启动 **自动调查**。</span><span class="sxs-lookup"><span data-stu-id="eb836-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="eb836-132">自动调查如何扩展其范围</span><span class="sxs-lookup"><span data-stu-id="eb836-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="eb836-133">当调查正在运行时，从设备生成的其他任何警报将添加到正在进行的自动调查，直到完成该调查。</span><span class="sxs-lookup"><span data-stu-id="eb836-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="eb836-134">此外，如果在其他设备上看到相同的威胁，则这些设备将添加到调查。</span><span class="sxs-lookup"><span data-stu-id="eb836-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="eb836-135">如果在另一台设备上看到一个已注册实体，则自动调查过程会扩展其范围以包括该设备，并且通用安全手册将在该设备上启动。</span><span class="sxs-lookup"><span data-stu-id="eb836-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="eb836-136">如果在此扩展过程中从同一实体找到 10 台或更多的设备，则扩展操作需要获得批准，并且显示在"待定操作" **选项卡上** 。</span><span class="sxs-lookup"><span data-stu-id="eb836-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="eb836-137">如何修正威胁</span><span class="sxs-lookup"><span data-stu-id="eb836-137">How threats are remediated</span></span>

<span data-ttu-id="eb836-138">触发警报并运行自动调查时，将针对调查的每个证据生成裁定。</span><span class="sxs-lookup"><span data-stu-id="eb836-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="eb836-139">裁定可以是</span><span class="sxs-lookup"><span data-stu-id="eb836-139">Verdicts can be</span></span> 
- <span data-ttu-id="eb836-140">*恶意*;</span><span class="sxs-lookup"><span data-stu-id="eb836-140">*Malicious*;</span></span>
- <span data-ttu-id="eb836-141">*可疑*;或</span><span class="sxs-lookup"><span data-stu-id="eb836-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="eb836-142">*未找到威胁*。</span><span class="sxs-lookup"><span data-stu-id="eb836-142">*No threats found*.</span></span> 

<span data-ttu-id="eb836-143">在做出裁定后，自动调查可能会导致一个或多个修正操作。</span><span class="sxs-lookup"><span data-stu-id="eb836-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="eb836-144">修正操作的示例包括将文件发送到隔离区、停止服务、删除计划任务等。</span><span class="sxs-lookup"><span data-stu-id="eb836-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="eb836-145">若要了解更多信息，请参阅 [修正操作](manage-auto-investigation.md#remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="eb836-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="eb836-146">根据为 [组织](automation-levels.md) 设置的自动化级别以及其他安全设置，修正操作可以自动执行，或仅在安全运营团队批准后执行。</span><span class="sxs-lookup"><span data-stu-id="eb836-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="eb836-147">可影响自动修正的其他安全设置包括 [保护来自](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) PUA (可能不需要) 。</span><span class="sxs-lookup"><span data-stu-id="eb836-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="eb836-148">所有修正操作（无论是挂起还是已完成）都跟踪在操作 [中心中](auto-investigation-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eb836-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="eb836-149">如有必要，安全运营团队可以撤消修正操作。</span><span class="sxs-lookup"><span data-stu-id="eb836-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="eb836-150">若要了解更多信息，请参阅 [在自动调查后审阅和批准修正操作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)。</span><span class="sxs-lookup"><span data-stu-id="eb836-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="eb836-151">查看安全中心内新的统一Microsoft 365调查页面。</span><span class="sxs-lookup"><span data-stu-id="eb836-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="eb836-152">若要了解更多信息，请参阅 ([ NEW！) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。</span><span class="sxs-lookup"><span data-stu-id="eb836-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="eb836-153">AIR 的要求</span><span class="sxs-lookup"><span data-stu-id="eb836-153">Requirements for AIR</span></span>

<span data-ttu-id="eb836-154">你的组织必须具有适用于终结点的 Defender (请参阅[Microsoft Defender for Endpoint) 。](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="eb836-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="eb836-155">目前，AIR 仅支持以下操作系统版本：</span><span class="sxs-lookup"><span data-stu-id="eb836-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="eb836-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="eb836-156">Windows Server 2019</span></span>
- <span data-ttu-id="eb836-157">Windows 10版本 1709 (OS 内部版本 16299.1085（包含[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="eb836-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="eb836-158">Windows 10版本 1803 (OS 内部版本 17134.704（包含[KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="eb836-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="eb836-159">Windows 10版本[1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019)或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb836-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb836-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb836-160">Next steps</span></span>

- [<span data-ttu-id="eb836-161">详细了解自动化级别</span><span class="sxs-lookup"><span data-stu-id="eb836-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="eb836-162">请参阅交互式指南：使用 Microsoft Defender for Endpoint 调查和修正威胁</span><span class="sxs-lookup"><span data-stu-id="eb836-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="eb836-163">在 Microsoft Defender for Endpoint 中配置自动调查和修正功能</span><span class="sxs-lookup"><span data-stu-id="eb836-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="eb836-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb836-164">See also</span></span>

- [<span data-ttu-id="eb836-165">PUA 保护</span><span class="sxs-lookup"><span data-stu-id="eb836-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="eb836-166">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="eb836-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="eb836-167">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="eb836-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
