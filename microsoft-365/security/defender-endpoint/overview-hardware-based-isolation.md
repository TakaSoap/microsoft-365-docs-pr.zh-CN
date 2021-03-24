---
title: 'Windows 10 (基于硬件的) '
ms.reviewer: ''
description: 了解 Windows 10 中基于硬件的隔离如何有助于防御恶意软件。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054642"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="7d5e9-103">Windows 10 中基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="7d5e9-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d5e9-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7d5e9-104">**Applies to:**</span></span>
- [<span data-ttu-id="7d5e9-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d5e9-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7d5e9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d5e9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7d5e9-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="7d5e9-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d5e9-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7d5e9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7d5e9-109">基于硬件的隔离可帮助保护 Windows 10 中的系统完整性，并且与 Microsoft Defender for Endpoint 集成。</span><span class="sxs-lookup"><span data-stu-id="7d5e9-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="7d5e9-110">功能</span><span class="sxs-lookup"><span data-stu-id="7d5e9-110">Feature</span></span> | <span data-ttu-id="7d5e9-111">说明</span><span class="sxs-lookup"><span data-stu-id="7d5e9-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="7d5e9-112">Windows Defender 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="7d5e9-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="7d5e9-113">应用程序防护可保护你的设备免受高级攻击，同时保持你的工作效率。</span><span class="sxs-lookup"><span data-stu-id="7d5e9-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="7d5e9-114">使用基于硬件的独特隔离方法，目标是将不受信任的网站和 PDF 文档隔离在通过本机 Windows 虚拟机监控程序与操作系统分离的轻型容器内。</span><span class="sxs-lookup"><span data-stu-id="7d5e9-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="7d5e9-115">如果不受信任的站点或 PDF 文档是恶意的，它仍包含在应用程序防护的安全容器中，使桌面电脑受到保护，并且攻击者不会访问企业数据。</span><span class="sxs-lookup"><span data-stu-id="7d5e9-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="7d5e9-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="7d5e9-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="7d5e9-117">System Guard 在系统启动时和运行后保护和维护系统的完整性，并且使用证明验证系统完整性。</span><span class="sxs-lookup"><span data-stu-id="7d5e9-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

