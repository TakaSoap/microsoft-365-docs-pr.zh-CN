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
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: cb56872be3cef2e094583e59a702707f79355743
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177617"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="22974-104">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="22974-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="22974-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="22974-105">**Applies to:**</span></span>

- [<span data-ttu-id="22974-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="22974-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22974-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22974-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="22974-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="22974-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="22974-109">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="22974-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="22974-110">[攻击面减少规则](attack-surface-reduction.md) (ASR 规则) 有助于防止恶意软件经常滥用以损害设备和网络的操作。</span><span class="sxs-lookup"><span data-stu-id="22974-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="22974-111">要求</span><span class="sxs-lookup"><span data-stu-id="22974-111">Requirements</span></span>

<span data-ttu-id="22974-112">跨多个版本的攻击Windows功能</span><span class="sxs-lookup"><span data-stu-id="22974-112">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="22974-113">你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：</span><span class="sxs-lookup"><span data-stu-id="22974-113">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="22974-114">Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="22974-114">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="22974-115">Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="22974-115">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="22974-116">Windows服务器版本[1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="22974-116">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="22974-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="22974-117">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="22974-118">若要使用攻击面减少规则的整个功能集，你需要：</span><span class="sxs-lookup"><span data-stu-id="22974-118">To use the entire feature-set of attack surface reduction rules, you need:</span></span>

- <span data-ttu-id="22974-119">Windows Defender 防病毒作为主 AV (实时保护) </span><span class="sxs-lookup"><span data-stu-id="22974-119">Windows Defender Antivirus as primary AV (real-time protection on)</span></span>
- <span data-ttu-id="22974-120">[某些规则](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 要求 (云传递保护) </span><span class="sxs-lookup"><span data-stu-id="22974-120">[Cloud-Delivery Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (some rules require that)</span></span>
- <span data-ttu-id="22974-121">Windows 10 企业版E5 或 E3 许可证或 Microsoft 365 商业版许可证</span><span class="sxs-lookup"><span data-stu-id="22974-121">Windows 10 Enterprise E5 or E3 License or Microsoft 365 Business License</span></span>

<span data-ttu-id="22974-122">尽管攻击面减少规则不需要[Windows E5](/windows/deployment/deploy-enterprise-licenses)许可证，但使用 Windows E5 许可证，你可以获得高级管理功能，包括适用于终结点的 Defender 中提供的监视、分析和工作流，以及 Microsoft 365 安全中心的报告和配置功能。</span><span class="sxs-lookup"><span data-stu-id="22974-122">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), with a Windows E5 license, you get advanced management capabilities including monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="22974-123">这些高级功能不适用于 E3 许可证，但你仍可以使用事件查看器查看攻击面减少规则事件。</span><span class="sxs-lookup"><span data-stu-id="22974-123">These advanced capabilities aren't available with an E3 license, but you can still use Event Viewer to review attack surface reduction rule events.</span></span>

<span data-ttu-id="22974-124">每个 ASR 规则包含四个设置之一：</span><span class="sxs-lookup"><span data-stu-id="22974-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="22974-125">**未配置**：禁用 ASR 规则</span><span class="sxs-lookup"><span data-stu-id="22974-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="22974-126">**阻止**：启用 ASR 规则</span><span class="sxs-lookup"><span data-stu-id="22974-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="22974-127">**审核**：评估 ASR 规则在启用后对组织的影响</span><span class="sxs-lookup"><span data-stu-id="22974-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="22974-128">**警告**：启用 ASR 规则，但允许最终用户绕过阻止</span><span class="sxs-lookup"><span data-stu-id="22974-128">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22974-129">目前，在 MEM 中配置 ASR 规则时，三个 ASR 规则不支持Microsoft Endpoint Manager (模式) 。</span><span class="sxs-lookup"><span data-stu-id="22974-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="22974-130">若要了解更多信息，请参阅 [不支持警告模式的情况](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="22974-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="22974-131">强烈建议将 ASR 规则与 Windows E5 许可证 (或类似的许可 SKU) 一同使用，以利用适用于 Endpoint (Defender for Endpoint) 的[Microsoft Defender](microsoft-defender-endpoint.md)中提供的高级监视和报告功能。</span><span class="sxs-lookup"><span data-stu-id="22974-131">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="22974-132">但是，如果您具有不包含高级监视和报告功能的另一个许可证（如 Windows Professional 或 Windows E3），您可以在触发 ASR 规则时在每个终结点生成的事件（例如，事件转发 () ）上开发自己的监视和报告工具。</span><span class="sxs-lookup"><span data-stu-id="22974-132">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="22974-133">若要了解有关许可Windows，请参阅 Windows 10 [Licensing and](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="22974-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="22974-134">可以使用以下任一方法启用攻击面减少规则：</span><span class="sxs-lookup"><span data-stu-id="22974-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="22974-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="22974-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="22974-136">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="22974-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="22974-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="22974-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="22974-138">组策略</span><span class="sxs-lookup"><span data-stu-id="22974-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="22974-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="22974-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="22974-140">Enterprise Intune 或 Microsoft Endpoint Manager等高级管理。</span><span class="sxs-lookup"><span data-stu-id="22974-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="22974-141">Enterprise级别管理将在启动时覆盖任何冲突的组策略或 PowerShell 设置。</span><span class="sxs-lookup"><span data-stu-id="22974-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="22974-142">从 ASR 规则中排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="22974-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="22974-143">你可以排除大多数攻击面减少规则评估的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="22974-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="22974-144">这意味着，即使 ASR 规则确定文件或文件夹包含恶意行为，它将不会阻止文件运行。</span><span class="sxs-lookup"><span data-stu-id="22974-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="22974-145">这可能会允许不安全的文件运行并感染你的设备。</span><span class="sxs-lookup"><span data-stu-id="22974-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="22974-146">通过允许指定的 Defender for Endpoint 文件和证书指示器，还可以从基于证书和文件哈希触发的 ASR 规则排除。</span><span class="sxs-lookup"><span data-stu-id="22974-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="22974-147"> (请参阅 [管理指示器](manage-indicators.md).) </span><span class="sxs-lookup"><span data-stu-id="22974-147">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22974-148">排除文件或文件夹会大大降低 ASR 规则所提供的保护。</span><span class="sxs-lookup"><span data-stu-id="22974-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="22974-149">将允许运行排除的文件，并且不会记录任何报告或事件。</span><span class="sxs-lookup"><span data-stu-id="22974-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="22974-150">如果 ASR 规则正在检测你认为不应检测的文件，应首先使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="22974-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="22974-151">可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) ，但无法指定排除项应用于的规则。</span><span class="sxs-lookup"><span data-stu-id="22974-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="22974-152">仅在已排除的应用程序或服务启动时应用排除。</span><span class="sxs-lookup"><span data-stu-id="22974-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="22974-153">例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="22974-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="22974-154">ASR 规则支持环境变量和通配符。</span><span class="sxs-lookup"><span data-stu-id="22974-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="22974-155">有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="22974-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="22974-156">以下用于启用 ASR 规则的过程包括有关如何排除文件和文件夹的说明。</span><span class="sxs-lookup"><span data-stu-id="22974-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="22974-157">Intune</span><span class="sxs-lookup"><span data-stu-id="22974-157">Intune</span></span>

1. <span data-ttu-id="22974-158">选择 **设备配置文件**  >  。</span><span class="sxs-lookup"><span data-stu-id="22974-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="22974-159">选择现有的终结点保护配置文件或创建新的终结点保护配置文件。</span><span class="sxs-lookup"><span data-stu-id="22974-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="22974-160">若要创建新的配置文件，请选择" **创建配置文件** "并为此配置文件输入信息。</span><span class="sxs-lookup"><span data-stu-id="22974-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="22974-161">对于 **"配置文件类型"，** 选择"**终结点保护"。**</span><span class="sxs-lookup"><span data-stu-id="22974-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="22974-162">如果已选择现有配置文件，请选择 **"属性**"，然后选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="22974-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="22974-163">在终结点 **保护窗格中**，选择Windows Defender **攻击防护"，** 然后选择攻击 **面减少**。</span><span class="sxs-lookup"><span data-stu-id="22974-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="22974-164">选择每个 ASR 规则所需的设置。</span><span class="sxs-lookup"><span data-stu-id="22974-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="22974-165">在 **"攻击面减少异常"** 下，输入单个文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="22974-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="22974-166">还可以选择导入 **以** 导入 CSV 文件，其中包含要从 ASR 规则中排除的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="22974-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="22974-167">CSV 文件的每一行的格式应如下所示：</span><span class="sxs-lookup"><span data-stu-id="22974-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="22974-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="22974-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="22974-169">在 **三** 个配置窗格中选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="22974-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="22974-170">然后，**如果要** 创建新的终结点保护文件，请选择"创建";如果要编辑现有终结点保护文件，请选择"保存"。</span><span class="sxs-lookup"><span data-stu-id="22974-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="22974-171">MEM</span><span class="sxs-lookup"><span data-stu-id="22974-171">MEM</span></span>

<span data-ttu-id="22974-172">可以使用 OMA-URI Microsoft Endpoint Manager (MEM) 配置自定义 ASR 规则。</span><span class="sxs-lookup"><span data-stu-id="22974-172">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="22974-173">以下过程使用规则 [阻止滥用攻击的易受攻击的已](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) 签名驱动程序作为示例。</span><span class="sxs-lookup"><span data-stu-id="22974-173">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="22974-174">打开管理Microsoft Endpoint Manager (MEM) 管理中心。</span><span class="sxs-lookup"><span data-stu-id="22974-174">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="22974-175">在"**开始"** 菜单中，单击 **"设备"，** 选择 **"配置文件**"，然后单击"**创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="22974-175">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-176">![MEM 创建配置文件](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="22974-176">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="22974-177">在 **"创建配置文件"** 中的以下两个下拉列表中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="22974-177">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="22974-178">在 **"平台**"**中，Windows 10和更高版本"**</span><span class="sxs-lookup"><span data-stu-id="22974-178">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="22974-179">在 **"配置文件类型"** 中， **选择"模板"**</span><span class="sxs-lookup"><span data-stu-id="22974-179">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="22974-180">选择 **"自定义**"，然后单击"**创建"。**</span><span class="sxs-lookup"><span data-stu-id="22974-180">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-181">![MEM 规则配置文件属性](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="22974-181">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="22974-182">自定义模板工具将打开到步骤 **1 基础知识**。</span><span class="sxs-lookup"><span data-stu-id="22974-182">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="22974-183">在 **"1 基础知识**"的 **"名称**"中，键入模板的名称，在"说明"中，可以键入 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="22974-183">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-184">![MEM 基本属性](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="22974-184">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="22974-185">单击 **下一个**。</span><span class="sxs-lookup"><span data-stu-id="22974-185">Click **Next**.</span></span> <span data-ttu-id="22974-186">步骤 **2 将打开配置** 设置。</span><span class="sxs-lookup"><span data-stu-id="22974-186">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="22974-187">对于 OMA-URI 设置，**单击添加**。</span><span class="sxs-lookup"><span data-stu-id="22974-187">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="22974-188">此时将显示两个选项："**添加"和**"**导出"。**</span><span class="sxs-lookup"><span data-stu-id="22974-188">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-189">![MEM 配置设置](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="22974-189">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="22974-190">再次 **单击"添加** "。</span><span class="sxs-lookup"><span data-stu-id="22974-190">Click **Add** again.</span></span> <span data-ttu-id="22974-191">添加 **行 OMA-URI 设置** 打开。</span><span class="sxs-lookup"><span data-stu-id="22974-191">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="22974-192">在 **"添加行"** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22974-192">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="22974-193">在 **"名称**"中，键入规则的名称。</span><span class="sxs-lookup"><span data-stu-id="22974-193">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="22974-194">在 **"说明**"中，键入简要说明。</span><span class="sxs-lookup"><span data-stu-id="22974-194">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="22974-195">在 **OMA-URI** 中，键入或粘贴要添加的规则的特定 OMA-URI 链接。</span><span class="sxs-lookup"><span data-stu-id="22974-195">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="22974-196">在 **"数据类型"中**，选择"**字符串"。**</span><span class="sxs-lookup"><span data-stu-id="22974-196">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="22974-197">在 **"值**"中，键入或粘贴 GUID 值、无空格的符号和 \= State (_GUID=StateValue_) 。</span><span class="sxs-lookup"><span data-stu-id="22974-197">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="22974-198">其中： {0 ： 禁用 (禁用 ASR 规则) }，{1 ： 阻止 (启用 ASR 规则) }，{2 ： 审核 (评估 ASR 规则在启用) } 时对组织的影响，{6 ： 警告 (启用 ASR 规则，但允许最终用户绕过阻止) }</span><span class="sxs-lookup"><span data-stu-id="22974-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-199">![MEM OMA URI 配置](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="22974-199">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="22974-200">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="22974-200">Click **Save**.</span></span> <span data-ttu-id="22974-201">**添加行** 关闭。</span><span class="sxs-lookup"><span data-stu-id="22974-201">**Add Row** closes.</span></span> <span data-ttu-id="22974-202">在 **"自定义"** 中，单击"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="22974-202">In **Custom**, click **Next**.</span></span> <span data-ttu-id="22974-203">在步骤 **3 范围标记中**，范围标记是可选的。</span><span class="sxs-lookup"><span data-stu-id="22974-203">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="22974-204">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="22974-204">Do one of the following:</span></span>

   - <span data-ttu-id="22974-205">单击 **"选择范围标记"，** 选择作用域 (可选) ，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="22974-205">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="22974-206">或单击" **下一步"**</span><span class="sxs-lookup"><span data-stu-id="22974-206">Or click **Next**</span></span>

7. <span data-ttu-id="22974-207">在步骤 **4"分配**"中，在" **包含** 的组 " - 对于您希望应用此规则的组 - 从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="22974-207">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="22974-208">**添加组**</span><span class="sxs-lookup"><span data-stu-id="22974-208">**Add groups**</span></span>
   - <span data-ttu-id="22974-209">**添加所有用户**</span><span class="sxs-lookup"><span data-stu-id="22974-209">**Add all users**</span></span>
   - <span data-ttu-id="22974-210">**添加所有设备**</span><span class="sxs-lookup"><span data-stu-id="22974-210">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-211">![MEM 分配](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="22974-211">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="22974-212">在 **"已排除的** 组"中，选择要从此规则中排除的任何组，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="22974-212">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="22974-213">在步骤 **5 针对** 以下设置的适用性规则中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22974-213">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="22974-214">在 **"规则**"中，选择"如果 **分配配置文件"** 或" **不分配配置文件"（如果为 ）**</span><span class="sxs-lookup"><span data-stu-id="22974-214">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="22974-215">在 **"** 属性"中，选择要应用此规则的属性</span><span class="sxs-lookup"><span data-stu-id="22974-215">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="22974-216">在 **"值**"中，输入适用的值或值范围</span><span class="sxs-lookup"><span data-stu-id="22974-216">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="22974-217">![MEM 适用性规则](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="22974-217">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="22974-218">单击 **下一个**。</span><span class="sxs-lookup"><span data-stu-id="22974-218">Click **Next**.</span></span> <span data-ttu-id="22974-219">在"**步骤 6 查看 + 创建**"中，查看已选择并输入的设置和信息，然后单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="22974-219">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="22974-220">![MEM 审阅和创建](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="22974-220">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="22974-221">规则处于活动状态，且数分钟内有效。</span><span class="sxs-lookup"><span data-stu-id="22974-221">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="22974-222">冲突处理：</span><span class="sxs-lookup"><span data-stu-id="22974-222">Conflict handling:</span></span>
>
> <span data-ttu-id="22974-223">如果为设备分配了两个不同的 ASR 策略，则处理冲突的方式为分配了不同状态的规则，没有实施冲突管理，因此会出现错误。</span><span class="sxs-lookup"><span data-stu-id="22974-223">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="22974-224">非冲突规则不会生成错误，并且规则将正确应用。</span><span class="sxs-lookup"><span data-stu-id="22974-224">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="22974-225">结果是应用第一个规则，后续的非冲突规则将合并到该策略中。</span><span class="sxs-lookup"><span data-stu-id="22974-225">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="22974-226">MDM</span><span class="sxs-lookup"><span data-stu-id="22974-226">MDM</span></span>

<span data-ttu-id="22974-227">使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 配置服务提供程序 (CSP) 单独启用和设置每个规则的模式。</span><span class="sxs-lookup"><span data-stu-id="22974-227">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="22974-228">下面是使用 ASR 规则的 [GUID 值进行引用的示例](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="22974-228">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="22974-229">在审核模式下 (阻止) 、禁用、警告或启用的值为：</span><span class="sxs-lookup"><span data-stu-id="22974-229">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="22974-230">0 ：禁用 (禁用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="22974-230">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="22974-231">1：阻止 (启用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="22974-231">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="22974-232">2：审核 (评估 ASR 规则在启用后对组织) </span><span class="sxs-lookup"><span data-stu-id="22974-232">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="22974-233">6：警告 (启用 ASR 规则，但允许最终用户绕过阻止) 。</span><span class="sxs-lookup"><span data-stu-id="22974-233">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="22974-234">警告模式现在适用于大多数 ASR 规则。</span><span class="sxs-lookup"><span data-stu-id="22974-234">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="22974-235">使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。</span><span class="sxs-lookup"><span data-stu-id="22974-235">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="22974-236">示例：</span><span class="sxs-lookup"><span data-stu-id="22974-236">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="22974-237">请务必输入不带空格的 OMA-URI 值。</span><span class="sxs-lookup"><span data-stu-id="22974-237">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="22974-238">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="22974-238">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="22974-239">In Microsoft Endpoint Configuration Manager， go to **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard**.</span><span class="sxs-lookup"><span data-stu-id="22974-239">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="22974-240">选择 **"主页**  >  **创建攻击防护策略"。**</span><span class="sxs-lookup"><span data-stu-id="22974-240">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="22974-241">输入名称和说明，选择攻击 **面** 减少，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="22974-241">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="22974-242">选择将阻止或审核操作的规则，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="22974-242">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="22974-243">查看设置，然后选择" **下一** 步"以创建策略。</span><span class="sxs-lookup"><span data-stu-id="22974-243">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="22974-244">创建策略后 **，关闭**。</span><span class="sxs-lookup"><span data-stu-id="22974-244">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="22974-245">组策略</span><span class="sxs-lookup"><span data-stu-id="22974-245">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="22974-246">如果使用 Intune、Configuration Manager 或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="22974-246">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="22974-247">在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="22974-247">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="22974-248">在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="22974-248">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="22974-249">展开树以 **Windows攻击**  >    >  **Microsoft Defender 防病毒Microsoft Defender 攻击防护**  >  **减少的组件**。</span><span class="sxs-lookup"><span data-stu-id="22974-249">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="22974-250">选择 **配置攻击面减少规则，** 然后选择 **已启用。**</span><span class="sxs-lookup"><span data-stu-id="22974-250">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="22974-251">然后，您可以为选项部分的每个规则设置单个状态。</span><span class="sxs-lookup"><span data-stu-id="22974-251">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="22974-252">选择 **"显示..."，** 在"值名称"列中输入规则 ID，在"值"列中输入 **所选状态**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22974-252">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="22974-253">0 ：禁用 (禁用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="22974-253">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="22974-254">1：阻止 (启用 ASR 规则) </span><span class="sxs-lookup"><span data-stu-id="22974-254">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="22974-255">2：审核 (评估 ASR 规则在启用后对组织) </span><span class="sxs-lookup"><span data-stu-id="22974-255">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="22974-256">6： (启用 ASR 规则，但允许最终用户绕过阻止) </span><span class="sxs-lookup"><span data-stu-id="22974-256">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="组策略中的 ASR 规则":::

5. <span data-ttu-id="22974-258">若要从 ASR 规则中排除文件和文件夹，请选择"从攻击 **面** 减少规则中排除文件和路径"设置，将选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="22974-258">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="22974-259">选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="22974-259">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="22974-260">在"值"**列中为** 每个项目输入 **0。**</span><span class="sxs-lookup"><span data-stu-id="22974-260">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="22974-261">请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。</span><span class="sxs-lookup"><span data-stu-id="22974-261">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="22974-262">PowerShell</span><span class="sxs-lookup"><span data-stu-id="22974-262">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="22974-263">如果使用 Intune、Configuration Manager 或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的 PowerShell 设置。</span><span class="sxs-lookup"><span data-stu-id="22974-263">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="22974-264">若要允许用户使用 PowerShell 定义值，请使用管理平台中规则的"用户定义"选项。</span><span class="sxs-lookup"><span data-stu-id="22974-264">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="22974-265">在 **"管理"中"开始"菜单 powershell，** 右键 **单击**"Windows PowerShell并选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="22974-265">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="22974-266">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="22974-266">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="22974-267">若要在审核模式下启用 ASR 规则，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="22974-267">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="22974-268">若要在警告模式下启用 ASR 规则，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="22974-268">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="22974-269">若要启用 ASR 阻止滥用被攻击的易受攻击的已签名驱动程序，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="22974-269">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="22974-270">若要关闭 ASR 规则，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="22974-270">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="22974-271">必须单独为每个规则指定状态，但可以在逗号分隔列表中组合规则和状态。</span><span class="sxs-lookup"><span data-stu-id="22974-271">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="22974-272">在下面的示例中，将启用前两个规则，第三个规则将被禁用，第四个规则将在审核模式下启用：</span><span class="sxs-lookup"><span data-stu-id="22974-272">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="22974-273">您还可以使用 `Add-MpPreference` PowerShell 谓词将新规则添加到现有列表中。</span><span class="sxs-lookup"><span data-stu-id="22974-273">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="22974-274">`Set-MpPreference` 将始终覆盖现有的规则集。</span><span class="sxs-lookup"><span data-stu-id="22974-274">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="22974-275">如果要添加到现有集合，请改为 `Add-MpPreference` 使用 。</span><span class="sxs-lookup"><span data-stu-id="22974-275">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="22974-276">可以使用 获取规则列表及其当前状态 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="22974-276">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="22974-277">若要从 ASR 规则中排除文件和文件夹，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="22974-277">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="22974-278">继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="22974-278">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="22974-279">用于 `Add-MpPreference` 向列表中追加或添加应用。</span><span class="sxs-lookup"><span data-stu-id="22974-279">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="22974-280">使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="22974-280">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="22974-281">相关文章</span><span class="sxs-lookup"><span data-stu-id="22974-281">Related articles</span></span>

- [<span data-ttu-id="22974-282">使用攻击面减少规则减少攻击面</span><span class="sxs-lookup"><span data-stu-id="22974-282">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="22974-283">评估攻击面减少</span><span class="sxs-lookup"><span data-stu-id="22974-283">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="22974-284">关于攻击面减少的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="22974-284">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
