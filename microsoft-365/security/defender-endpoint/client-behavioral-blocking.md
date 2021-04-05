---
title: 客户端阻止
description: 客户端行为阻止是 Microsoft Defender for Endpoint 中的行为阻止和包含功能的一部分
keywords: 行为阻止， 快速保护， 客户端行为， Microsoft Defender ATP
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
ms.openlocfilehash: 9fcff96b2583c6ef6bec05429ec50a71f3872e43
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587103"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="1be5a-104">客户端阻止</span><span class="sxs-lookup"><span data-stu-id="1be5a-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1be5a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1be5a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1be5a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1be5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1be5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1be5a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1be5a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="1be5a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1be5a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1be5a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="1be5a-110">概述</span><span class="sxs-lookup"><span data-stu-id="1be5a-110">Overview</span></span>

<span data-ttu-id="1be5a-111">客户端行为阻止是 Defender for Endpoint 中行为阻止 [和](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) 包含功能的一个组件。</span><span class="sxs-lookup"><span data-stu-id="1be5a-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="1be5a-112">由于在设备上检测到可疑行为 (也称为客户端或终结点) ，因此 (或应用程序等项目) 自动阻止、检查和修正。</span><span class="sxs-lookup"><span data-stu-id="1be5a-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="云和客户端保护":::

<span data-ttu-id="1be5a-114">防病毒保护在与云保护配对时效果最佳。</span><span class="sxs-lookup"><span data-stu-id="1be5a-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="1be5a-115">客户端行为阻止的工作原理</span><span class="sxs-lookup"><span data-stu-id="1be5a-115">How client behavioral blocking works</span></span>

<span data-ttu-id="1be5a-116">[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 可以在设备上检测可疑行为、恶意代码、无文件攻击和内存中攻击等。</span><span class="sxs-lookup"><span data-stu-id="1be5a-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="1be5a-117">当检测到可疑行为时，Microsoft Defender 防病毒将监视这些可疑行为及其进程树并将其发送到云保护服务。</span><span class="sxs-lookup"><span data-stu-id="1be5a-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="1be5a-118">机器学习在毫秒内区分恶意应用程序和良好行为，并分类每个项目。</span><span class="sxs-lookup"><span data-stu-id="1be5a-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="1be5a-119">在几乎实时中，只要发现项目是恶意项目，就会在设备上被阻止。</span><span class="sxs-lookup"><span data-stu-id="1be5a-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="1be5a-120">只要检测到可疑行为，就会生成 [警报](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) ，并且该警报在 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 。</span><span class="sxs-lookup"><span data-stu-id="1be5a-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="1be5a-121">客户端行为阻止非常有效，因为它不仅有助于防止攻击启动，还有助于阻止已开始执行的攻击。</span><span class="sxs-lookup"><span data-stu-id="1be5a-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="1be5a-122">此外， [通过反馈循环](feedback-loop-blocking.md) (行为阻止和) 功能，可以阻止组织中其他设备的攻击。</span><span class="sxs-lookup"><span data-stu-id="1be5a-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="1be5a-123">基于行为的检测</span><span class="sxs-lookup"><span data-stu-id="1be5a-123">Behavior-based detections</span></span>

<span data-ttu-id="1be5a-124">基于行为的检测根据 [MITRE ATT&CK Matrix for Enterprise 进行命名](https://attack.mitre.org/matrices/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="1be5a-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="1be5a-125">命名约定有助于识别观测到恶意行为的攻击阶段：</span><span class="sxs-lookup"><span data-stu-id="1be5a-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="1be5a-126">策略</span><span class="sxs-lookup"><span data-stu-id="1be5a-126">Tactic</span></span> |   <span data-ttu-id="1be5a-127">检测威胁名称</span><span class="sxs-lookup"><span data-stu-id="1be5a-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="1be5a-128">初始访问</span><span class="sxs-lookup"><span data-stu-id="1be5a-128">Initial Access</span></span> | <span data-ttu-id="1be5a-129">Behavior：Win32/InitialAccess.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="1be5a-130">执行</span><span class="sxs-lookup"><span data-stu-id="1be5a-130">Execution</span></span>  | <span data-ttu-id="1be5a-131">Behavior：Win32/Execution.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="1be5a-132">持久性</span><span class="sxs-lookup"><span data-stu-id="1be5a-132">Persistence</span></span>    | <span data-ttu-id="1be5a-133">Behavior：Win32/Persistence.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="1be5a-134">特权提升</span><span class="sxs-lookup"><span data-stu-id="1be5a-134">Privilege Escalation</span></span>   | <span data-ttu-id="1be5a-135">Behavior：Win32/PrivilegeEscalation.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="1be5a-136">防御者</span><span class="sxs-lookup"><span data-stu-id="1be5a-136">Defense Evasion</span></span>    | <span data-ttu-id="1be5a-137">Behavior：Win32/DefenseEvasion.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="1be5a-138">凭据访问</span><span class="sxs-lookup"><span data-stu-id="1be5a-138">Credential Access</span></span>  | <span data-ttu-id="1be5a-139">Behavior：Win32/CredentialAccess.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="1be5a-140">发现</span><span class="sxs-lookup"><span data-stu-id="1be5a-140">Discovery</span></span>  | <span data-ttu-id="1be5a-141">Behavior：Win32/Discovery.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="1be5a-142">横向移动</span><span class="sxs-lookup"><span data-stu-id="1be5a-142">Lateral Movement</span></span> | <span data-ttu-id="1be5a-143">Behavior：Win32/LateralMovement.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="1be5a-144">集合</span><span class="sxs-lookup"><span data-stu-id="1be5a-144">Collection</span></span> |   <span data-ttu-id="1be5a-145">Behavior：Win32/Collection.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="1be5a-146">命令和控件</span><span class="sxs-lookup"><span data-stu-id="1be5a-146">Command and Control</span></span> | <span data-ttu-id="1be5a-147">Behavior：Win32/CommandAndControl.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="1be5a-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="1be5a-148">Exfiltration</span></span>   | <span data-ttu-id="1be5a-149">Behavior：Win32/Exfiltration.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="1be5a-150">影响</span><span class="sxs-lookup"><span data-stu-id="1be5a-150">Impact</span></span> | <span data-ttu-id="1be5a-151">Behavior：Win32/Impact.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="1be5a-152">未分类</span><span class="sxs-lookup"><span data-stu-id="1be5a-152">Uncategorized</span></span>  | <span data-ttu-id="1be5a-153">Behavior：Win32/Generic.\*！ml</span><span class="sxs-lookup"><span data-stu-id="1be5a-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="1be5a-154">若要了解有关特定威胁的信息，请参阅最近的 **[全球威胁活动](https://www.microsoft.com/wdsi/threats)**。</span><span class="sxs-lookup"><span data-stu-id="1be5a-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="1be5a-155">配置客户端行为阻止</span><span class="sxs-lookup"><span data-stu-id="1be5a-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="1be5a-156">如果你的组织对 Endpoint 使用 Defender，则默认情况下会启用客户端行为阻止。</span><span class="sxs-lookup"><span data-stu-id="1be5a-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="1be5a-157">但是，若要从所有 Defender for Endpoint 功能[](behavioral-blocking-containment.md)（包括行为阻止和抑制）中获益，请确保已启用并配置了 Defender for Endpoint 的以下特性和功能：</span><span class="sxs-lookup"><span data-stu-id="1be5a-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="1be5a-158">Defender for Endpoint 基线</span><span class="sxs-lookup"><span data-stu-id="1be5a-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="1be5a-159">载入到适用于终结点的 Defender 的设备</span><span class="sxs-lookup"><span data-stu-id="1be5a-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="1be5a-160">块模式下的 EDR</span><span class="sxs-lookup"><span data-stu-id="1be5a-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="1be5a-161">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="1be5a-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="1be5a-162">[下一代保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) </span><span class="sxs-lookup"><span data-stu-id="1be5a-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="1be5a-163">相关文章</span><span class="sxs-lookup"><span data-stu-id="1be5a-163">Related articles</span></span>

- [<span data-ttu-id="1be5a-164">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="1be5a-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="1be5a-165">反馈循环阻止</span><span class="sxs-lookup"><span data-stu-id="1be5a-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="1be5a-166"> (博客) 行为阻止和抑制：将光学镜头转换为保护</span><span class="sxs-lookup"><span data-stu-id="1be5a-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="1be5a-167">适用于终结点资源的有用 Defender</span><span class="sxs-lookup"><span data-stu-id="1be5a-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
