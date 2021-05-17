---
title: 反馈循环阻止
description: 反馈循环阻止（也称为快速保护）是 Microsoft Defender for Endpoint 中的行为阻止和包含功能的一部分
keywords: 行为阻止， 快速保护， 反馈阻止， Microsoft Defender for Endpoint
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
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056536"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="aa1c8-104">反馈循环阻止</span><span class="sxs-lookup"><span data-stu-id="aa1c8-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa1c8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aa1c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa1c8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa1c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="aa1c8-107">概述</span><span class="sxs-lookup"><span data-stu-id="aa1c8-107">Overview</span></span>

<span data-ttu-id="aa1c8-108">反馈循环阻止也称为快速保护，是 Microsoft Defender for Endpoint[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)中行为阻止和包含功能的一[个组件](https://docs.microsoft.com/windows/security/threat-protection/)。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span></span> <span data-ttu-id="aa1c8-109">通过反馈循环阻止，可以更好地保护整个组织的设备免受攻击。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="aa1c8-110">反馈循环阻止的工作原理</span><span class="sxs-lookup"><span data-stu-id="aa1c8-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="aa1c8-111">当检测到可疑行为或文件时（如通过[Microsoft Defender 防病毒）时](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)，有关项目的信息将被发送到多个分类器。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="aa1c8-112">快速保护循环引擎检查信息并将信息与其他信号关联，以决定是否阻止文件。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="aa1c8-113">检查和分类项目会快速发生。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="aa1c8-114">它可快速阻止已确认的恶意软件，并驱动整个生态系统的保护。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="aa1c8-115">借助快速保护，攻击可以在设备、组织的其他设备和其他组织中的设备上停止，因为攻击尝试扩大其位置。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="aa1c8-116">配置反馈循环阻止</span><span class="sxs-lookup"><span data-stu-id="aa1c8-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="aa1c8-117">如果你的组织对终结点使用 Defender，则默认启用反馈循环阻止。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="aa1c8-118">但是，通过结合使用 Defender for Endpoint 功能、机器学习保护功能和 Microsoft 安全服务中的信号共享，可以快速提供保护。</span><span class="sxs-lookup"><span data-stu-id="aa1c8-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="aa1c8-119">确保已启用和配置 Defender for Endpoint 的以下特性和功能：</span><span class="sxs-lookup"><span data-stu-id="aa1c8-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="aa1c8-120">适用于终结点的 Microsoft Defender 基线</span><span class="sxs-lookup"><span data-stu-id="aa1c8-120">Microsoft Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="aa1c8-121">载入到 Microsoft Defender for Endpoint 的设备</span><span class="sxs-lookup"><span data-stu-id="aa1c8-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="aa1c8-122">块模式下的 EDR</span><span class="sxs-lookup"><span data-stu-id="aa1c8-122">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="aa1c8-123">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="aa1c8-123">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="aa1c8-124">[下一代保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) </span><span class="sxs-lookup"><span data-stu-id="aa1c8-124">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="aa1c8-125">相关文章</span><span class="sxs-lookup"><span data-stu-id="aa1c8-125">Related articles</span></span>

- [<span data-ttu-id="aa1c8-126">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="aa1c8-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="aa1c8-127"> (博客) 行为阻止和抑制：将光学镜头转换为保护</span><span class="sxs-lookup"><span data-stu-id="aa1c8-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="aa1c8-128">适用于终结点资源的有用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aa1c8-128">Helpful Microsoft Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
