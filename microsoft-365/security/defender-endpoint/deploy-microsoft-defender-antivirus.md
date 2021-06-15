---
title: 部署和启用 Microsoft Defender 防病毒软件
description: 使用 Microsoft Defender 防病毒、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或 WMI 部署 Microsoft Intune，以保护终结点。
keywords: 部署、启用、Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925739"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="9bbc9-104">部署和启用 Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="9bbc9-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9bbc9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9bbc9-105">**Applies to:**</span></span>

- [<span data-ttu-id="9bbc9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9bbc9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9bbc9-107">根据你使用的管理工具，你可能需要专门启用或配置Microsoft Defender 防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="9bbc9-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="9bbc9-108">有关如何使用[Microsoft Intune、Microsoft Endpoint Configuration Manager、](deploy-manage-report-microsoft-defender-antivirus.md#ref2)组策略、Active Directory、Microsoft Azure、PowerShell cmdlet 和 Windows Management Instruction (WMI) 启用保护的说明，请参阅 Microsoft Defender 防病毒 上的表。</span><span class="sxs-lookup"><span data-stu-id="9bbc9-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="9bbc9-109">一些方案需要有关如何成功部署或配置 Microsoft Defender 防病毒 保护的更多指南，例如虚拟桌面基础结构 (VDI) 环境。</span><span class="sxs-lookup"><span data-stu-id="9bbc9-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="9bbc9-110">本节中的其余文章提供有关在 VDI 或远程桌面服务[ (RDS) ](deployment-vdi-microsoft-defender-antivirus.md)环境中在虚拟机 (VM) 上设置 Microsoft Defender 防病毒 的端到端建议和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9bbc9-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9bbc9-111">相关文章</span><span class="sxs-lookup"><span data-stu-id="9bbc9-111">Related articles</span></span>

- [<span data-ttu-id="9bbc9-112">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="9bbc9-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9bbc9-113">部署、管理更新并报告Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="9bbc9-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9bbc9-114">虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南</span><span class="sxs-lookup"><span data-stu-id="9bbc9-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)