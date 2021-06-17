---
title: 配置攻击面减少功能
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell cmdlet 和组策略配置攻击面减少。
keywords: asr， 攻击面减少， windows defender， microsoft defender， 防病毒， av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984444"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="01329-104">配置攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="01329-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="01329-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="01329-105">**Applies to:**</span></span>

- [<span data-ttu-id="01329-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="01329-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01329-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01329-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="01329-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="01329-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="01329-109">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="01329-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="01329-110">Defender for Endpoint 包括多种攻击面减少功能。</span><span class="sxs-lookup"><span data-stu-id="01329-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="01329-111">若要了解更多信息，请参阅 [攻击面减少功能概述](overview-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="01329-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="01329-112">若要在你的环境中配置攻击面减少，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="01329-112">To configure attack surface reduction in your environment, follow these steps:</span></span>

1. <span data-ttu-id="01329-113">[为 Microsoft Edge 启用基于硬件的隔离](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="01329-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="01329-114">启用应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="01329-114">Enable application control.</span></span>

   1. <span data-ttu-id="01329-115">查看 Windows 中的基本策略。</span><span class="sxs-lookup"><span data-stu-id="01329-115">Review base policies in Windows.</span></span> <span data-ttu-id="01329-116">请参阅 [示例基本策略](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。</span><span class="sxs-lookup"><span data-stu-id="01329-116">See [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="01329-117">请参阅Windows Defender[控件设计指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。</span><span class="sxs-lookup"><span data-stu-id="01329-117">See the [Windows Defender Application Control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="01329-118">请参阅[部署 WDAC Windows Defender应用程序 (策略) 应用程序控制](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="01329-118">Refer to [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="01329-119">[启用受控文件夹访问权限](enable-controlled-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="01329-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="01329-120">[打开网络保护](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="01329-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="01329-121">[启用 Exploit Protection](enable-exploit-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="01329-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="01329-122">[配置攻击面减少规则](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="01329-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="01329-123">设置网络防火墙。</span><span class="sxs-lookup"><span data-stu-id="01329-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="01329-124">获取高级安全[Windows Defender防火墙的概述](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。</span><span class="sxs-lookup"><span data-stu-id="01329-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="01329-125">使用[Windows Defender防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)设计指南决定您希望如何设计防火墙策略。</span><span class="sxs-lookup"><span data-stu-id="01329-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="01329-126">使用[Windows Defender 防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)部署指南设置组织的高级安全防火墙。</span><span class="sxs-lookup"><span data-stu-id="01329-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span>

> [!TIP]
> <span data-ttu-id="01329-127">在大多数情况下，配置攻击面减少功能时，可以从以下几种方法中选择：</span><span class="sxs-lookup"><span data-stu-id="01329-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>

> - <span data-ttu-id="01329-128">Microsoft Endpoint Manager (现在包括Microsoft Intune和Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="01329-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="01329-129">组策略</span><span class="sxs-lookup"><span data-stu-id="01329-129">Group Policy</span></span>
> - <span data-ttu-id="01329-130">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="01329-130">PowerShell cmdlets</span></span>
