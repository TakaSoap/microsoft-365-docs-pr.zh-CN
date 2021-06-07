---
title: 客户端阻止
description: 客户端行为阻止是 Microsoft Defender for Endpoint 中的行为阻止和包含功能的一部分
keywords: 行为阻止， 快速保护， 客户端行为， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795954"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="54e17-104">客户端阻止</span><span class="sxs-lookup"><span data-stu-id="54e17-104">Client behavioral blocking</span></span>

<span data-ttu-id="54e17-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="54e17-105">**Applies to:**</span></span>
- [<span data-ttu-id="54e17-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54e17-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54e17-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54e17-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="54e17-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="54e17-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54e17-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="54e17-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="54e17-110">概述</span><span class="sxs-lookup"><span data-stu-id="54e17-110">Overview</span></span>

<span data-ttu-id="54e17-111">客户端行为阻止是 Defender for Endpoint 中行为阻止 [和](behavioral-blocking-containment.md) 包含功能的一个组件。</span><span class="sxs-lookup"><span data-stu-id="54e17-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="54e17-112">由于在设备上检测到可疑行为 (也称为客户端或终结点) ，因此 (或应用程序等项目) 自动阻止、检查和修正。</span><span class="sxs-lookup"><span data-stu-id="54e17-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="云和客户端保护":::

<span data-ttu-id="54e17-114">防病毒保护在与云保护配对时效果最佳。</span><span class="sxs-lookup"><span data-stu-id="54e17-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="54e17-115">客户端行为阻止的工作原理</span><span class="sxs-lookup"><span data-stu-id="54e17-115">How client behavioral blocking works</span></span>

<span data-ttu-id="54e17-116">[Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)检测设备上可疑行为、恶意代码、无文件攻击和内存中攻击等。</span><span class="sxs-lookup"><span data-stu-id="54e17-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="54e17-117">当检测到可疑行为时，Microsoft Defender 防病毒监控这些可疑行为并将其进程树发送到云保护服务。</span><span class="sxs-lookup"><span data-stu-id="54e17-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="54e17-118">机器学习在毫秒内区分恶意应用程序和良好行为，并分类每个项目。</span><span class="sxs-lookup"><span data-stu-id="54e17-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="54e17-119">在几乎实时中，只要发现项目是恶意项目，就会在设备上被阻止。</span><span class="sxs-lookup"><span data-stu-id="54e17-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="54e17-120">只要检测到可疑行为，就会生成[警报](alerts-queue.md)，并且该警报 [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 安全中心 () 。</span><span class="sxs-lookup"><span data-stu-id="54e17-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="54e17-121">客户端行为阻止非常有效，因为它不仅有助于防止攻击启动，还有助于阻止已开始执行的攻击。</span><span class="sxs-lookup"><span data-stu-id="54e17-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="54e17-122">此外， [通过反馈循环](feedback-loop-blocking.md) (行为阻止和) 功能，可以阻止组织中其他设备的攻击。</span><span class="sxs-lookup"><span data-stu-id="54e17-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="54e17-123">基于行为的检测</span><span class="sxs-lookup"><span data-stu-id="54e17-123">Behavior-based detections</span></span>

<span data-ttu-id="54e17-124">基于行为的检测根据[MITRE ATT&CK 矩阵进行命名Enterprise。](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="54e17-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="54e17-125">命名约定有助于识别观测到恶意行为的攻击阶段：</span><span class="sxs-lookup"><span data-stu-id="54e17-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="54e17-126">策略</span><span class="sxs-lookup"><span data-stu-id="54e17-126">Tactic</span></span> |   <span data-ttu-id="54e17-127">检测威胁名称</span><span class="sxs-lookup"><span data-stu-id="54e17-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="54e17-128">初始访问</span><span class="sxs-lookup"><span data-stu-id="54e17-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="54e17-129">执行</span><span class="sxs-lookup"><span data-stu-id="54e17-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="54e17-130">持久性</span><span class="sxs-lookup"><span data-stu-id="54e17-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="54e17-131">特权提升</span><span class="sxs-lookup"><span data-stu-id="54e17-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="54e17-132">防御者</span><span class="sxs-lookup"><span data-stu-id="54e17-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="54e17-133">凭据访问</span><span class="sxs-lookup"><span data-stu-id="54e17-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="54e17-134">发现</span><span class="sxs-lookup"><span data-stu-id="54e17-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="54e17-135">横向移动</span><span class="sxs-lookup"><span data-stu-id="54e17-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="54e17-136">集合</span><span class="sxs-lookup"><span data-stu-id="54e17-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="54e17-137">命令和控件</span><span class="sxs-lookup"><span data-stu-id="54e17-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="54e17-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="54e17-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="54e17-139">影响</span><span class="sxs-lookup"><span data-stu-id="54e17-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="54e17-140">未分类</span><span class="sxs-lookup"><span data-stu-id="54e17-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="54e17-141">若要了解有关特定威胁的信息，请参阅最近的 **[全球威胁活动](https://www.microsoft.com/wdsi/threats)**。</span><span class="sxs-lookup"><span data-stu-id="54e17-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="54e17-142">配置客户端行为阻止</span><span class="sxs-lookup"><span data-stu-id="54e17-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="54e17-143">如果你的组织对 Endpoint 使用 Defender，则默认情况下会启用客户端行为阻止。</span><span class="sxs-lookup"><span data-stu-id="54e17-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="54e17-144">但是，若要从所有 Defender for Endpoint 功能[](behavioral-blocking-containment.md)（包括行为阻止和抑制）中获益，请确保已启用并配置了 Defender for Endpoint 的以下特性和功能：</span><span class="sxs-lookup"><span data-stu-id="54e17-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="54e17-145">Defender for Endpoint 基线</span><span class="sxs-lookup"><span data-stu-id="54e17-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="54e17-146">载入到适用于终结点的 Defender 的设备</span><span class="sxs-lookup"><span data-stu-id="54e17-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="54e17-147">块模式下的 EDR</span><span class="sxs-lookup"><span data-stu-id="54e17-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="54e17-148">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="54e17-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="54e17-149">[下一代 (](configure-microsoft-defender-antivirus-features.md) 防病毒、反恶意软件和其他威胁防护功能) </span><span class="sxs-lookup"><span data-stu-id="54e17-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

