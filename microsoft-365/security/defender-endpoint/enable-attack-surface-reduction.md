---
title: 启用攻击面减少规则
description: 启用攻击面 (ASR) 规则，以保护你的设备免受使用宏、脚本和常见注入技术的攻击。
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 启用， 打开
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 7aeda679d5ce350ef64a2758359390adc4a280f0
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939238"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="16f65-104">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="16f65-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16f65-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="16f65-105">**Applies to:**</span></span>
- [<span data-ttu-id="16f65-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="16f65-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16f65-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16f65-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="16f65-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="16f65-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16f65-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="16f65-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="16f65-110">[攻击面减少规则](attack-surface-reduction.md) (ASR 规则) 有助于防止恶意软件经常滥用以损害设备和网络的操作。</span><span class="sxs-lookup"><span data-stu-id="16f65-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="16f65-111">你可以为运行以下任一版本的 Windows 的设备设置 ASR 规则：</span><span class="sxs-lookup"><span data-stu-id="16f65-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="16f65-112">Windows 10 专业 [版版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16f65-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="16f65-113">Windows 10 企业版 [版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16f65-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="16f65-114">Windows Server [版本 1803 (半年 ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 频道) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16f65-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="16f65-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="16f65-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="16f65-116">**要求** 你可以为运行以下任一版本的 Windows 的设备设置攻击面减少规则：</span><span class="sxs-lookup"><span data-stu-id="16f65-116">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="16f65-117">Windows 10 专业版版本 1709 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16f65-117">Windows 10 Pro, version 1709 or later</span></span>
- <span data-ttu-id="16f65-118">Windows 10 企业版版本 1709 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16f65-118">Windows 10 Enterprise, version 1709 or later</span></span>
- <span data-ttu-id="16f65-119">Windows Server 版本 1803 (半年频道) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16f65-119">Windows Server, version 1803 (Semi-Annual Channel) or later</span></span>
- <span data-ttu-id="16f65-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="16f65-120">Windows Server 2019</span></span>

<span data-ttu-id="16f65-121">尽管攻击面减少规则不需要 Windows E5 许可证，但如果拥有 Windows E5，则获得高级管理功能。</span><span class="sxs-lookup"><span data-stu-id="16f65-121">Although attack surface reduction rules don't require a Windows E5 license, if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="16f65-122">这些功能仅在 Windows E5 中可用，包括 Defender for Endpoint 中提供的监视、分析和工作流，以及 Microsoft 365 安全中心中的报告和配置功能。</span><span class="sxs-lookup"><span data-stu-id="16f65-122">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="16f65-123">这些高级功能不适用于 Windows Professional 或 Windows E3 许可证;但是，如果你有这些许可证，可以使用事件查看器和 Microsoft Defender 防病毒日志查看攻击面减少规则事件。</span><span class="sxs-lookup"><span data-stu-id="16f65-123">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="16f65-124">每个 ASR 规则包含四个设置之一：</span><span class="sxs-lookup"><span data-stu-id="16f65-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="16f65-125">**未配置**：禁用 ASR 规则</span><span class="sxs-lookup"><span data-stu-id="16f65-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="16f65-126">**阻止**：启用 ASR 规则</span><span class="sxs-lookup"><span data-stu-id="16f65-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="16f65-127">**审核**：评估 ASR 规则在启用后对组织的影响</span><span class="sxs-lookup"><span data-stu-id="16f65-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="16f65-128">**警告**：启用 ASR 规则，但允许最终用户绕过阻止</span><span class="sxs-lookup"><span data-stu-id="16f65-128">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16f65-129">目前，在 Microsoft Endpoint Manager 和 MEM 管理器中配置 ASR 规则时，三个 ASR 规则不支持 (模式) 。</span><span class="sxs-lookup"><span data-stu-id="16f65-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="16f65-130">若要了解更多信息，请参阅 [不支持警告模式的情况](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="16f65-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="16f65-131">强烈建议你将 ASR 规则与 Windows E5 许可证 (或类似的许可 SKU) 一同使用，以利用适用于 Endpoint (Defender for Endpoint) 的 [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) 中提供的高级监视和报告功能。</span><span class="sxs-lookup"><span data-stu-id="16f65-131">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="16f65-132">但是，对于无法访问高级监视和报告功能的其他许可证（如 Windows Professional 或 E3），可以在触发 AS (R 规则时在每个终结点生成的事件（如事件转发) ）上开发自己的监视和报告工具。</span><span class="sxs-lookup"><span data-stu-id="16f65-132">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="16f65-133">若要了解有关 Windows 许可的更多信息，请参阅 [Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 许可并获取 [适用于 Windows 10 的批量许可指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="16f65-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="16f65-134">可以使用以下任一方法启用攻击面减少规则：</span><span class="sxs-lookup"><span data-stu-id="16f65-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="16f65-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="16f65-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="16f65-136">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="16f65-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="16f65-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="16f65-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="16f65-138">组策略</span><span class="sxs-lookup"><span data-stu-id="16f65-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="16f65-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="16f65-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="16f65-140">建议使用企业级管理，如 Intune 或 Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="16f65-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="16f65-141">启动时，企业级管理将覆盖任何冲突的组策略或 PowerShell 设置。</span><span class="sxs-lookup"><span data-stu-id="16f65-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="16f65-142">从 ASR 规则中排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="16f65-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="16f65-143">你可以排除大多数攻击面减少规则评估的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="16f65-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="16f65-144">这意味着，即使 ASR 规则确定文件或文件夹包含恶意行为，它将不会阻止文件运行。</span><span class="sxs-lookup"><span data-stu-id="16f65-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="16f65-145">这可能会允许不安全的文件运行并感染你的设备。</span><span class="sxs-lookup"><span data-stu-id="16f65-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="16f65-146">通过允许指定的 Defender for Endpoint 文件和证书指示器，还可以从基于证书和文件哈希触发的 ASR 规则排除。</span><span class="sxs-lookup"><span data-stu-id="16f65-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="16f65-147"> (请参阅 [管理指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).) </span><span class="sxs-lookup"><span data-stu-id="16f65-147">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16f65-148">排除文件或文件夹会大大降低 ASR 规则所提供的保护。</span><span class="sxs-lookup"><span data-stu-id="16f65-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="16f65-149">将允许运行排除的文件，并且不会记录任何报告或事件。</span><span class="sxs-lookup"><span data-stu-id="16f65-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="16f65-150">如果 ASR 规则正在检测你认为不应检测的文件，应首先使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="16f65-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="16f65-151">可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) ，但无法指定排除项应用于的规则。</span><span class="sxs-lookup"><span data-stu-id="16f65-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="16f65-152">仅在已排除的应用程序或服务启动时应用排除。</span><span class="sxs-lookup"><span data-stu-id="16f65-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="16f65-153">例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="16f65-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="16f65-154">ASR 规则支持环境变量和通配符。</span><span class="sxs-lookup"><span data-stu-id="16f65-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="16f65-155">有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="16f65-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="16f65-156">以下用于启用 ASR 规则的过程包括有关如何排除文件和文件夹的说明。</span><span class="sxs-lookup"><span data-stu-id="16f65-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="16f65-157">Intune</span><span class="sxs-lookup"><span data-stu-id="16f65-157">Intune</span></span>

1. <span data-ttu-id="16f65-158">选择 **设备配置文件**  >  。</span><span class="sxs-lookup"><span data-stu-id="16f65-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="16f65-159">选择现有的终结点保护配置文件或创建新的终结点保护配置文件。</span><span class="sxs-lookup"><span data-stu-id="16f65-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="16f65-160">若要创建新的配置文件，请选择" **创建配置文件** "并为此配置文件输入信息。</span><span class="sxs-lookup"><span data-stu-id="16f65-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="16f65-161">对于 **"配置文件类型"，** 选择"**终结点保护"。**</span><span class="sxs-lookup"><span data-stu-id="16f65-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="16f65-162">如果已选择现有配置文件，请选择"**属性"，** 然后选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="16f65-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="16f65-163">在终结点 **保护窗格中，** 选择Windows Defender **攻击防护"，** 然后选择攻击 **面减少**。</span><span class="sxs-lookup"><span data-stu-id="16f65-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="16f65-164">选择每个 ASR 规则所需的设置。</span><span class="sxs-lookup"><span data-stu-id="16f65-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="16f65-165">在 **"攻击面减少异常"** 下，输入单个文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="16f65-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="16f65-166">还可以选择导入 **以** 导入 CSV 文件，其中包含要从 ASR 规则中排除的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="16f65-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="16f65-167">CSV 文件的每一行的格式应如下所示：</span><span class="sxs-lookup"><span data-stu-id="16f65-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="16f65-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="16f65-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="16f65-169">在 **三** 个配置窗格中选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="16f65-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="16f65-170">然后，**如果要** 创建新的终结点保护文件，请选择"创建";如果要编辑现有终结点保护文件，请选择"保存"。</span><span class="sxs-lookup"><span data-stu-id="16f65-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="16f65-171">MDM</span><span class="sxs-lookup"><span data-stu-id="16f65-171">MDM</span></span>

<span data-ttu-id="16f65-172">使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 配置服务提供程序 (CSP) 单独启用和设置每个规则的模式。</span><span class="sxs-lookup"><span data-stu-id="16f65-172">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="16f65-173">下面是使用 ASR 规则的 [GUID 值进行引用的示例](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="16f65-173">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="16f65-174">在审核模式下 (阻止) 、禁用、警告或启用的值为：</span><span class="sxs-lookup"><span data-stu-id="16f65-174">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="16f65-175">0 ：禁用 (禁用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="16f65-175">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="16f65-176">1：阻止 (启用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="16f65-176">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="16f65-177">2：审核 (评估 ASR 规则在启用后对组织) </span><span class="sxs-lookup"><span data-stu-id="16f65-177">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="16f65-178">6：警告 (启用 ASR 规则，但允许最终用户绕过阻止) 。</span><span class="sxs-lookup"><span data-stu-id="16f65-178">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="16f65-179">警告模式现在适用于大多数 ASR 规则。</span><span class="sxs-lookup"><span data-stu-id="16f65-179">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="16f65-180">使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。</span><span class="sxs-lookup"><span data-stu-id="16f65-180">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="16f65-181">示例：</span><span class="sxs-lookup"><span data-stu-id="16f65-181">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="16f65-182">请务必输入不带空格的 OMA-URI 值。</span><span class="sxs-lookup"><span data-stu-id="16f65-182">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="16f65-183">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="16f65-183">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="16f65-184">在 Microsoft Endpoint Configuration Manager 中，转到 **"资产和** 合规性  >  **Endpoint Protection**  >  **Windows Defender攻击防护"。**</span><span class="sxs-lookup"><span data-stu-id="16f65-184">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="16f65-185">选择 **"主页**  >  **创建攻击防护策略"。**</span><span class="sxs-lookup"><span data-stu-id="16f65-185">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="16f65-186">输入名称和说明，选择攻击 **面** 减少，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="16f65-186">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="16f65-187">选择将阻止或审核操作的规则，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="16f65-187">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="16f65-188">查看设置，然后选择" **下一** 步"以创建策略。</span><span class="sxs-lookup"><span data-stu-id="16f65-188">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="16f65-189">创建策略后 **，关闭**。</span><span class="sxs-lookup"><span data-stu-id="16f65-189">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="16f65-190">组策略</span><span class="sxs-lookup"><span data-stu-id="16f65-190">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="16f65-191">如果使用 Intune、Configuration Manager 或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="16f65-191">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="16f65-192">在组策略管理计算机上，打开组 [策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="16f65-192">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="16f65-193">在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="16f65-193">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="16f65-194">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒** Microsoft Defender  >  **攻击防护**  >  **攻击面减少**。</span><span class="sxs-lookup"><span data-stu-id="16f65-194">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="16f65-195">选择 **配置攻击面减少规则，** 然后选择 **已启用。**</span><span class="sxs-lookup"><span data-stu-id="16f65-195">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="16f65-196">然后，您可以为选项部分的每个规则设置单个状态。</span><span class="sxs-lookup"><span data-stu-id="16f65-196">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="16f65-197">选择 **"显示..."，** 在"值名称"列中输入规则 ID，在"值"列中输入 **所选状态**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="16f65-197">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="16f65-198">0 ：禁用 (禁用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="16f65-198">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="16f65-199">1：阻止 (启用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="16f65-199">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="16f65-200">2：审核 (评估 ASR 规则在启用后对组织) </span><span class="sxs-lookup"><span data-stu-id="16f65-200">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="16f65-201">6： (启用 ASR 规则，但允许最终用户绕过阻止) </span><span class="sxs-lookup"><span data-stu-id="16f65-201">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="组策略中的 ASR 规则":::

5. <span data-ttu-id="16f65-203">若要从 ASR 规则中排除文件和文件夹，请选择"从攻击 **面** 减少规则中排除文件和路径"设置，将选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="16f65-203">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="16f65-204">选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="16f65-204">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="16f65-205">在"值"**列中为** 每个项目输入 **0。**</span><span class="sxs-lookup"><span data-stu-id="16f65-205">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="16f65-206">请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。</span><span class="sxs-lookup"><span data-stu-id="16f65-206">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="16f65-207">PowerShell</span><span class="sxs-lookup"><span data-stu-id="16f65-207">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="16f65-208">如果使用 Intune、Configuration Manager 或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的 PowerShell 设置。</span><span class="sxs-lookup"><span data-stu-id="16f65-208">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="16f65-209">若要允许用户使用 PowerShell 定义值，请使用管理平台中规则的"用户定义"选项。</span><span class="sxs-lookup"><span data-stu-id="16f65-209">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="16f65-210">在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="16f65-210">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="16f65-211">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="16f65-211">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="16f65-212">若要在审核模式下启用 ASR 规则，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="16f65-212">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="16f65-213">若要在警告模式下启用 ASR 规则，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="16f65-213">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="16f65-214">若要关闭 ASR 规则，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="16f65-214">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="16f65-215">必须单独为每个规则指定状态，但可以在逗号分隔列表中组合规则和状态。</span><span class="sxs-lookup"><span data-stu-id="16f65-215">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="16f65-216">在下面的示例中，将启用前两个规则，第三个规则将被禁用，第四个规则将在审核模式下启用：</span><span class="sxs-lookup"><span data-stu-id="16f65-216">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="16f65-217">您还可以使用 `Add-MpPreference` PowerShell 谓词将新规则添加到现有列表中。</span><span class="sxs-lookup"><span data-stu-id="16f65-217">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="16f65-218">`Set-MpPreference` 将始终覆盖现有的规则集。</span><span class="sxs-lookup"><span data-stu-id="16f65-218">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="16f65-219">如果要添加到现有集合，请改为 `Add-MpPreference` 使用 。</span><span class="sxs-lookup"><span data-stu-id="16f65-219">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="16f65-220">可以使用 获取规则列表及其当前状态 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="16f65-220">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="16f65-221">若要从 ASR 规则中排除文件和文件夹，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="16f65-221">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="16f65-222">继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="16f65-222">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="16f65-223">用于 `Add-MpPreference` 向列表中追加或添加应用。</span><span class="sxs-lookup"><span data-stu-id="16f65-223">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="16f65-224">使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="16f65-224">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="16f65-225">相关文章</span><span class="sxs-lookup"><span data-stu-id="16f65-225">Related articles</span></span>

- [<span data-ttu-id="16f65-226">使用攻击面减少规则减少攻击面</span><span class="sxs-lookup"><span data-stu-id="16f65-226">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="16f65-227">评估攻击面减少</span><span class="sxs-lookup"><span data-stu-id="16f65-227">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="16f65-228">关于减少攻击面的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="16f65-228">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
