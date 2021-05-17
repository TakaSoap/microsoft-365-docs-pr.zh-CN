---
title: '基于硬件的隔离 (Windows 10) '
ms.reviewer: ''
description: 了解软件中基于硬件的隔离Windows 10恶意软件的防护。
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
ms.openlocfilehash: 82841ccdb2a6ad09f43d0bf8d12cb54fe44d6dfe
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186901"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="dd127-103">Windows 10 中基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="dd127-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd127-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dd127-104">**Applies to:**</span></span>
- [<span data-ttu-id="dd127-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dd127-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd127-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd127-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dd127-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="dd127-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd127-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="dd127-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="dd127-109">基于硬件的隔离可帮助保护 Windows 10系统完整性，并且与 Microsoft Defender for Endpoint 集成。</span><span class="sxs-lookup"><span data-stu-id="dd127-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="dd127-110">功能</span><span class="sxs-lookup"><span data-stu-id="dd127-110">Feature</span></span> | <span data-ttu-id="dd127-111">说明</span><span class="sxs-lookup"><span data-stu-id="dd127-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="dd127-112">Windows Defender 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="dd127-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="dd127-113">应用程序防护可保护你的设备免受高级攻击，同时保持你的工作效率。</span><span class="sxs-lookup"><span data-stu-id="dd127-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="dd127-114">使用基于硬件的独特隔离方法，目标是将不受信任的网站和 PDF 文档隔离在轻型容器内，该容器通过本机虚拟机监控程序与操作系统Windows隔离。</span><span class="sxs-lookup"><span data-stu-id="dd127-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="dd127-115">如果不受信任的站点或 PDF 文档是恶意的，它仍包含在应用程序防护的安全容器中，使桌面电脑受到保护，并且攻击者不会访问企业数据。</span><span class="sxs-lookup"><span data-stu-id="dd127-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="dd127-116">Windows DefenderSystem Guard</span><span class="sxs-lookup"><span data-stu-id="dd127-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="dd127-117">System Guard 在系统启动时和运行后保护和维护系统的完整性，并且使用证明验证系统完整性。</span><span class="sxs-lookup"><span data-stu-id="dd127-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

