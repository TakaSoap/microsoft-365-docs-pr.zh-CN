---
title: 使用 PowerShell cmdlet 配置和运行 Microsoft Defender AV
description: 在 Windows 10 中，可以使用 PowerShell cmdlet 运行扫描、更新安全智能以及更改 Microsoft Defender 防病毒中的设置。
keywords: 扫描， 命令行， mpcmdrun， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 0fd1e6b2eec1be722af58e0753e158c050b56c6b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749870"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="d3ae5-104">使用 PowerShell cmdlet 配置和管理 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d3ae5-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d3ae5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d3ae5-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3ae5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3ae5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d3ae5-107">可以使用 PowerShell 在 Windows Defender 中执行各种Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="d3ae5-108">与命令提示符或命令行类似，PowerShell 是基于任务的命令行 shell 和脚本语言，专为系统管理设计。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="d3ae5-109">可以在 MSDN 上的 [PowerShell 中心中阅读有关它的更多信息](/previous-versions/msdn10/mt173057(v=msdn.10))。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="d3ae5-110">有关 cmdlet 及其函数和可用参数的列表，请参阅 [Defender cmdlet 主题](/powershell/module/defender) 。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="d3ae5-111">PowerShell cmdlet 在 Windows Server 环境中最有用，这些环境不依赖图形用户界面 (GUI) 配置软件。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="d3ae5-112">PowerShell cmdlet 不应用作完整网络策略管理基础结构（如 Microsoft Endpoint Configuration [Manager、](/configmgr)组策略管理[](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))控制台或 Microsoft Defender 防病毒组策略[ADMX](https://www.microsoft.com/download/101445)模板）的替换。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="d3ae5-113">使用 PowerShell 所做的更改将影响部署或进行更改的终结点上的本地设置。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="d3ae5-114">这意味着使用组策略、Microsoft Endpoint Configuration Manager 或 Microsoft Intune 部署策略可能会覆盖使用 PowerShell 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="d3ae5-115">你可以 [配置哪些设置可以使用本地策略覆盖在本地覆盖](configure-local-policy-overrides-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d3ae5-116">PowerShell 通常安装在 文件夹 下 `%SystemRoot%\system32\WindowsPowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="d3ae5-117">使用 Microsoft Defender 防病毒 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d3ae5-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="d3ae5-118">在 Windows 搜索栏中，键入 **powershell**。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="d3ae5-119">Select **Windows PowerShell** from the results to open the interface.</span><span class="sxs-lookup"><span data-stu-id="d3ae5-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="d3ae5-120">输入 PowerShell 命令和任何参数。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="d3ae5-121">您可能需要在管理员模式下打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="d3ae5-122">右键单击"开始"菜单中的项，单击"以管理员角色运行 **"，** 在权限提示符下单击"是"。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="d3ae5-123">若要打开任何 cmdlet 的联机帮助，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d3ae5-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="d3ae5-124">省略 `-online` 参数可获取本地缓存的帮助。</span><span class="sxs-lookup"><span data-stu-id="d3ae5-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3ae5-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3ae5-125">Related topics</span></span>

- [<span data-ttu-id="d3ae5-126">有关管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="d3ae5-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d3ae5-127">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d3ae5-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d3ae5-128">Microsoft Defender 防病毒 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d3ae5-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)