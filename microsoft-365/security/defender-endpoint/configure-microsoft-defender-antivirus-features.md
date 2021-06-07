---
title: 配置 Microsoft Defender 防病毒软件功能
description: 可以使用 Intune Microsoft Defender 防病毒、Microsoft Endpoint Configuration Manager、组策略和 PowerShell 配置这些功能。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 配置， 配置， 配置管理器， Microsoft Endpoint Configuration Manager， SCCM， Intune， MDM， 移动设备管理， GP， 组策略， PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789023"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="2732c-104">配置 Microsoft Defender 防病毒软件功能</span><span class="sxs-lookup"><span data-stu-id="2732c-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2732c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2732c-105">**Applies to:**</span></span>

- [<span data-ttu-id="2732c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2732c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2732c-107">可以使用多种Microsoft Defender 防病毒配置自定义设置，例如：</span><span class="sxs-lookup"><span data-stu-id="2732c-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="2732c-108">Microsoft Endpoint Manager (包括Microsoft Intune和Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="2732c-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="2732c-109">组策略</span><span class="sxs-lookup"><span data-stu-id="2732c-109">Group Policy</span></span>
- <span data-ttu-id="2732c-110">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="2732c-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="2732c-111">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="2732c-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="2732c-112">可以配置以下各种功能：</span><span class="sxs-lookup"><span data-stu-id="2732c-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="2732c-113">云保护。</span><span class="sxs-lookup"><span data-stu-id="2732c-113">Cloud-delivered protection.</span></span> <span data-ttu-id="2732c-114">请参阅[云提供的保护和Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2732c-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="2732c-115">始终提供实时保护，包括行为保护、启发式保护以及基于机器学习的保护。</span><span class="sxs-lookup"><span data-stu-id="2732c-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="2732c-116">请参阅 [配置行为、启发式和实时保护](configure-protection-features-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="2732c-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="2732c-117">最终用户如何与各个终结点上的客户端交互。</span><span class="sxs-lookup"><span data-stu-id="2732c-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="2732c-118">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2732c-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="2732c-119">阻止用户查看或与用户界面Microsoft Defender 防病毒交互</span><span class="sxs-lookup"><span data-stu-id="2732c-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="2732c-120">阻止或允许用户在本地修改Microsoft Defender 防病毒策略设置</span><span class="sxs-lookup"><span data-stu-id="2732c-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="2732c-121">查看 [管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="2732c-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>