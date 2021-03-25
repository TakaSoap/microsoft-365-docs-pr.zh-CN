---
title: 配置攻击面减少
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell cmdlet 和组策略配置攻击面减少。
keywords: asr， 攻击面减少， windows defender， microsoft defender， 防病毒， av
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166157"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="9281d-104">配置攻击面减少</span><span class="sxs-lookup"><span data-stu-id="9281d-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9281d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9281d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9281d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9281d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9281d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9281d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9281d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9281d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9281d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9281d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="9281d-110">可以使用多种工具配置攻击面减少，包括：</span><span class="sxs-lookup"><span data-stu-id="9281d-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="9281d-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9281d-111">Microsoft Intune</span></span>
* <span data-ttu-id="9281d-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9281d-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="9281d-113">组策略</span><span class="sxs-lookup"><span data-stu-id="9281d-113">Group Policy</span></span>
* <span data-ttu-id="9281d-114">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="9281d-114">PowerShell cmdlets</span></span>

<span data-ttu-id="9281d-115">文章</span><span class="sxs-lookup"><span data-stu-id="9281d-115">Article</span></span> | <span data-ttu-id="9281d-116">说明</span><span class="sxs-lookup"><span data-stu-id="9281d-116">Description</span></span>
-|-
[<span data-ttu-id="9281d-117">为 Microsoft Edge 启用基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="9281d-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="9281d-118">如何准备和安装应用程序防护，包括硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="9281d-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="9281d-119">启用应用程序控制</span><span class="sxs-lookup"><span data-stu-id="9281d-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="9281d-120">如何控制用户运行的应用程序和保护内核模式进程</span><span class="sxs-lookup"><span data-stu-id="9281d-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="9281d-121">Exploit Protection</span><span class="sxs-lookup"><span data-stu-id="9281d-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="9281d-122">如何在操作系统进程和个别应用上自动应用攻击缓解技术</span><span class="sxs-lookup"><span data-stu-id="9281d-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="9281d-123">网络保护</span><span class="sxs-lookup"><span data-stu-id="9281d-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="9281d-124">如何阻止用户使用任何应用访问危险域</span><span class="sxs-lookup"><span data-stu-id="9281d-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="9281d-125">受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="9281d-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="9281d-126">如何保护有价值的数据免受恶意应用的攻击</span><span class="sxs-lookup"><span data-stu-id="9281d-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="9281d-127">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="9281d-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="9281d-128">如何防止寻找漏洞的恶意软件通常使用的操作和应用</span><span class="sxs-lookup"><span data-stu-id="9281d-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="9281d-129">网络防火墙</span><span class="sxs-lookup"><span data-stu-id="9281d-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="9281d-130">如何跨网络保护设备和数据</span><span class="sxs-lookup"><span data-stu-id="9281d-130">How to protect devices and data across a network</span></span>

