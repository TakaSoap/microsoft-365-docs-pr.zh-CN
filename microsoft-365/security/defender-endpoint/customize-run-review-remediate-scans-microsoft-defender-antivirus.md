---
title: 运行和自定义计划扫描和按需扫描
description: 自定义并启动Microsoft Defender 防病毒终结点上的扫描。
keywords: 扫描， 计划， 自定义， 排除， 排除文件， 修正， 扫描结果， 隔离， 删除威胁， 快速扫描， 完全扫描， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 31dbfa2ac6d5537f6d42c0bad612be5ef059368d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275272"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="f5738-104">自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果</span><span class="sxs-lookup"><span data-stu-id="f5738-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f5738-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f5738-105">**Applies to:**</span></span>

- [<span data-ttu-id="f5738-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f5738-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f5738-107">可以使用组策略、PowerShell 和 WMI Windows Management Instrumentation (WMI) 配置Microsoft Defender 防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="f5738-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="f5738-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="f5738-108">In this section</span></span>

<span data-ttu-id="f5738-109">主题</span><span class="sxs-lookup"><span data-stu-id="f5738-109">Topic</span></span> | <span data-ttu-id="f5738-110">说明</span><span class="sxs-lookup"><span data-stu-id="f5738-110">Description</span></span>
---|---
[<span data-ttu-id="f5738-111">配置并验证扫描过程中的文件、文件夹和进程打开Microsoft Defender 防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="f5738-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="f5738-112">你可以排除文件 (包括由指定进程) 修改的文件和文件夹从按需扫描、计划扫描和始终打开实时保护监视和扫描中排除</span><span class="sxs-lookup"><span data-stu-id="f5738-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="f5738-113">配置 Microsoft Defender 防病毒软件扫描选项</span><span class="sxs-lookup"><span data-stu-id="f5738-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="f5738-114">可以将Microsoft Defender 防病毒配置为包括某些类型的电子邮件存储文件、备份或重新分析点以及存档的文件 (如扫描中.zip) 文件。</span><span class="sxs-lookup"><span data-stu-id="f5738-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="f5738-115">还可以启用网络文件扫描</span><span class="sxs-lookup"><span data-stu-id="f5738-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="f5738-116">配置扫描修正</span><span class="sxs-lookup"><span data-stu-id="f5738-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="f5738-117">配置Microsoft Defender 防病毒威胁时应执行哪些操作，以及隔离文件应在隔离文件夹中保留多久</span><span class="sxs-lookup"><span data-stu-id="f5738-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="f5738-118">配置计划扫描</span><span class="sxs-lookup"><span data-stu-id="f5738-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="f5738-119">设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行</span><span class="sxs-lookup"><span data-stu-id="f5738-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="f5738-120">配置并运行扫描</span><span class="sxs-lookup"><span data-stu-id="f5738-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="f5738-121">使用 PowerShell、Windows Management Instrumentation 运行和配置按需扫描，或者使用 Windows 安全中心 应用在终结点上单独运行和配置Windows 安全中心扫描</span><span class="sxs-lookup"><span data-stu-id="f5738-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="f5738-122">查看扫描结果</span><span class="sxs-lookup"><span data-stu-id="f5738-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="f5738-123">使用应用、Microsoft Endpoint Configuration Manager或Microsoft Intune查看Windows 安全中心结果</span><span class="sxs-lookup"><span data-stu-id="f5738-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>