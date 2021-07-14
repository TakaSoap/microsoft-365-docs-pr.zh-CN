---
title: 管理Windows Defender中的业务
description: 了解如何使用组策略、Configuration Manager、PowerShell、WMI、Intune 和命令行管理 Microsoft Defender AV
keywords: 组策略， gpo， config manager， sccm， scep， powershell， wmi， intune， defender， 防病毒， 反恶意软件， 安全性， 保护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415553"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="d1eda-104">管理Microsoft Defender 防病毒中的业务</span><span class="sxs-lookup"><span data-stu-id="d1eda-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d1eda-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d1eda-105">**Applies to:**</span></span>

- [<span data-ttu-id="d1eda-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d1eda-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="d1eda-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d1eda-107">Microsoft Defender Antivirus</span></span>](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

<span data-ttu-id="d1eda-108">可以使用以下工具Microsoft Defender 防病毒和配置自定义设置：</span><span class="sxs-lookup"><span data-stu-id="d1eda-108">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="d1eda-109">[Microsoft Intune (](/mem/intune/protect/endpoint-security-antivirus-policy)部分Microsoft Endpoint Manager) </span><span class="sxs-lookup"><span data-stu-id="d1eda-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="d1eda-110">[Microsoft Endpoint Configuration Manager (](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)现在属于Microsoft Endpoint Manager) </span><span class="sxs-lookup"><span data-stu-id="d1eda-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="d1eda-111">组策略</span><span class="sxs-lookup"><span data-stu-id="d1eda-111">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d1eda-112">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d1eda-112">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d1eda-113">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="d1eda-113">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="d1eda-114">[Microsoft 恶意软件保护命令行](./command-line-arguments-microsoft-defender-antivirus.md)实用程序 (称为"mpcmdrun.exe *实用工具*</span><span class="sxs-lookup"><span data-stu-id="d1eda-114">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="d1eda-115">以下文章提供了使用这些工具管理和配置 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="d1eda-115">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="d1eda-116">文章</span><span class="sxs-lookup"><span data-stu-id="d1eda-116">Article</span></span> | <span data-ttu-id="d1eda-117">说明</span><span class="sxs-lookup"><span data-stu-id="d1eda-117">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="d1eda-118">使用Microsoft Defender 防病毒和Microsoft Intune管理Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d1eda-118">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="d1eda-119">有关使用 Intune 和 Configuration Manager 部署、管理、报表和配置Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d1eda-119">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="d1eda-120">使用Microsoft Defender 防病毒策略设置管理策略</span><span class="sxs-lookup"><span data-stu-id="d1eda-120">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="d1eda-121">ADMX 模板中所有组策略设置的列表</span><span class="sxs-lookup"><span data-stu-id="d1eda-121">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="d1eda-122">使用 PowerShell cmdlet Microsoft Defender 防病毒管理配置</span><span class="sxs-lookup"><span data-stu-id="d1eda-122">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="d1eda-123">有关使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒的说明，以及指向所有 cmdlet 和允许的参数的文档的链接</span><span class="sxs-lookup"><span data-stu-id="d1eda-123">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="d1eda-124">使用 Microsoft Defender 防病毒 Management Instrumentation Windows WMI (管理) </span><span class="sxs-lookup"><span data-stu-id="d1eda-124">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="d1eda-125">有关使用 WMI 管理 Microsoft Defender 防病毒的说明，以及指向 WMIv2 API 文档的链接 (包括所有类、方法和属性) </span><span class="sxs-lookup"><span data-stu-id="d1eda-125">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="d1eda-126">使用 Microsoft Defender 防病毒命令行MpCmdRun.exe管理代码</span><span class="sxs-lookup"><span data-stu-id="d1eda-126">Manage Microsoft Defender Antivirus with the MpCmdRun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)| <span data-ttu-id="d1eda-127">有关使用专用命令行工具来管理和使用 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d1eda-127">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |
