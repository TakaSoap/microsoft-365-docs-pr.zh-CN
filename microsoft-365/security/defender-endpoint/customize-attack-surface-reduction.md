---
title: 自定义减少攻击面规则
description: 在审核、阻止或禁用模式中单独设置规则，并添加应从攻击面减少规则中排除的文件和文件夹
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 自定义， 配置， 排除
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570347"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="0e01d-104">自定义减少攻击面规则</span><span class="sxs-lookup"><span data-stu-id="0e01d-104">Customize attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e01d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0e01d-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e01d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0e01d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e01d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e01d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0e01d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="0e01d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e01d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0e01d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="0e01d-110">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="0e01d-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0e01d-111">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="0e01d-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="0e01d-112">[攻击面减少规则](enable-attack-surface-reduction.md) 有助于防止经常滥用以损害设备或网络的软件行为。</span><span class="sxs-lookup"><span data-stu-id="0e01d-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="0e01d-113">例如，攻击者可能会尝试从 USB 驱动器运行未签名的脚本，或者让 Office 文档中的宏直接调用 Win32 API。</span><span class="sxs-lookup"><span data-stu-id="0e01d-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="0e01d-114">攻击面减少规则可以限制这些类型的风险行为，并改进组织的防御状态。</span><span class="sxs-lookup"><span data-stu-id="0e01d-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="0e01d-115">了解如何通过排除文件和文件夹或向用户计算机上[](#exclude-files-and-folders)显示的通知警报添加自定义文本[](#customize-the-notification)来自定义攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="0e01d-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="0e01d-116">你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：</span><span class="sxs-lookup"><span data-stu-id="0e01d-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="0e01d-117">Windows 10 专业版版本[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="0e01d-117">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0e01d-118">Windows 10 企业版版本[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="0e01d-118">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="0e01d-119">Windows服务器版本[1803 (半年频道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="0e01d-119">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="0e01d-120">[Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)可以使用组策略、PowerShell 和移动设备管理 (MDM) CSP (配置) 配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="0e01d-120">[Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="0e01d-121">排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="0e01d-121">Exclude files and folders</span></span>

<span data-ttu-id="0e01d-122">你可以选择从攻击面减少规则评估中排除文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e01d-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="0e01d-123">排除后，即使攻击面减少规则检测到文件包含恶意行为，也不会阻止文件运行。</span><span class="sxs-lookup"><span data-stu-id="0e01d-123">Once excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

> [!WARNING]
> <span data-ttu-id="0e01d-124">这可能会允许不安全的文件运行并感染你的设备。</span><span class="sxs-lookup"><span data-stu-id="0e01d-124">This could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="0e01d-125">排除文件或文件夹会大大降低攻击面减少规则所提供的保护。</span><span class="sxs-lookup"><span data-stu-id="0e01d-125">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="0e01d-126">将允许运行规则阻止的文件，并且不会记录任何报告或事件。</span><span class="sxs-lookup"><span data-stu-id="0e01d-126">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="0e01d-127">排除适用于允许排除的所有规则。</span><span class="sxs-lookup"><span data-stu-id="0e01d-127">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="0e01d-128">您可以为资源指定单个文件、文件夹路径或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="0e01d-128">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="0e01d-129">但是，不能将排除限制到特定规则。</span><span class="sxs-lookup"><span data-stu-id="0e01d-129">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="0e01d-130">仅在已排除的应用程序或服务启动时应用排除。</span><span class="sxs-lookup"><span data-stu-id="0e01d-130">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="0e01d-131">例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="0e01d-131">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="0e01d-132">攻击面减少支持环境变量和通配符。</span><span class="sxs-lookup"><span data-stu-id="0e01d-132">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="0e01d-133">有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="0e01d-133">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>
<span data-ttu-id="0e01d-134">如果在检测你认为不应检测到的文件的规则方面遇到问题，请使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="0e01d-134">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="0e01d-135">规则说明</span><span class="sxs-lookup"><span data-stu-id="0e01d-135">Rule description</span></span> | <span data-ttu-id="0e01d-136">GUID</span><span class="sxs-lookup"><span data-stu-id="0e01d-136">GUID</span></span>
-|-|-
<span data-ttu-id="0e01d-137">阻止所有Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="0e01d-137">Block all Office applications from creating child processes</span></span> | <span data-ttu-id="0e01d-138">D4F940AB-401B-4EFC-AADC-AD5F3C50688A</span><span class="sxs-lookup"><span data-stu-id="0e01d-138">D4F940AB-401B-4EFC-AADC-AD5F3C50688A</span></span>
<span data-ttu-id="0e01d-139">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="0e01d-139">Block execution of potentially obfuscated scripts</span></span> | <span data-ttu-id="0e01d-140">5BEB7EFE-FD9A-4556-801D-275E5FFC04CC</span><span class="sxs-lookup"><span data-stu-id="0e01d-140">5BEB7EFE-FD9A-4556-801D-275E5FFC04CC</span></span>
<span data-ttu-id="0e01d-141">从宏中阻止 Win32 API Office调用</span><span class="sxs-lookup"><span data-stu-id="0e01d-141">Block Win32 API calls from Office macro</span></span> | <span data-ttu-id="0e01d-142">92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B</span><span class="sxs-lookup"><span data-stu-id="0e01d-142">92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B</span></span>
<span data-ttu-id="0e01d-143">阻止Office应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="0e01d-143">Block Office applications from creating executable content</span></span> | <span data-ttu-id="0e01d-144">3B576869-A4EC-4529-8536-B80A7769E899</span><span class="sxs-lookup"><span data-stu-id="0e01d-144">3B576869-A4EC-4529-8536-B80A7769E899</span></span>
<span data-ttu-id="0e01d-145">阻止Office代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="0e01d-145">Block Office applications from injecting code into other processes</span></span> | <span data-ttu-id="0e01d-146">75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84</span><span class="sxs-lookup"><span data-stu-id="0e01d-146">75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84</span></span>
<span data-ttu-id="0e01d-147">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="0e01d-147">Block JavaScript or VBScript from launching downloaded executable content</span></span> | <span data-ttu-id="0e01d-148">D3E037E1-3EB8-44C8-A917-57927947596D</span><span class="sxs-lookup"><span data-stu-id="0e01d-148">D3E037E1-3EB8-44C8-A917-57927947596D</span></span>
<span data-ttu-id="0e01d-149">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="0e01d-149">Block executable content from email client and webmail</span></span> | <span data-ttu-id="0e01d-150">BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550</span><span class="sxs-lookup"><span data-stu-id="0e01d-150">BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550</span></span>
<span data-ttu-id="0e01d-151">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="0e01d-151">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | <span data-ttu-id="0e01d-152">01443614-cd74-433a-b99e-2ecdc07bfc25</span><span class="sxs-lookup"><span data-stu-id="0e01d-152">01443614-cd74-433a-b99e-2ecdc07bfc25</span></span>
<span data-ttu-id="0e01d-153">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="0e01d-153">Use advanced protection against ransomware</span></span> | <span data-ttu-id="0e01d-154">c1db55ab-c21a-4637-bb3f-a12568109d35</span><span class="sxs-lookup"><span data-stu-id="0e01d-154">c1db55ab-c21a-4637-bb3f-a12568109d35</span></span>
<span data-ttu-id="0e01d-155">阻止本地安全机构子系统Windows窃取凭据 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="0e01d-155">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | <span data-ttu-id="0e01d-156">9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2</span><span class="sxs-lookup"><span data-stu-id="0e01d-156">9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2</span></span>
<span data-ttu-id="0e01d-157">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="0e01d-157">Block process creations originating from PSExec and WMI commands</span></span> | <span data-ttu-id="0e01d-158">d1e49aac-8f56-4280-b9ba-993a6d77406c</span><span class="sxs-lookup"><span data-stu-id="0e01d-158">d1e49aac-8f56-4280-b9ba-993a6d77406c</span></span>
<span data-ttu-id="0e01d-159">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="0e01d-159">Block untrusted and unsigned processes that run from USB</span></span> | <span data-ttu-id="0e01d-160">b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4</span><span class="sxs-lookup"><span data-stu-id="0e01d-160">b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4</span></span>
<span data-ttu-id="0e01d-161">阻止Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="0e01d-161">Block Office communication applications from creating child processes</span></span> | <span data-ttu-id="0e01d-162">26190899-1602-49e8-8b27-eb1d0a1ce869</span><span class="sxs-lookup"><span data-stu-id="0e01d-162">26190899-1602-49e8-8b27-eb1d0a1ce869</span></span>
<span data-ttu-id="0e01d-163">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="0e01d-163">Block Adobe Reader from creating child processes</span></span> | <span data-ttu-id="0e01d-164">7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c</span><span class="sxs-lookup"><span data-stu-id="0e01d-164">7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c</span></span>
<span data-ttu-id="0e01d-165">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="0e01d-165">Block persistence through WMI event subscription</span></span> | <span data-ttu-id="0e01d-166">e6db77e5-3df2-4cf1-b95a-636979351e5b</span><span class="sxs-lookup"><span data-stu-id="0e01d-166">e6db77e5-3df2-4cf1-b95a-636979351e5b</span></span>

<span data-ttu-id="0e01d-167">有关 [每个规则的详细信息](attack-surface-reduction.md) ，请参阅攻击面减少主题。</span><span class="sxs-lookup"><span data-stu-id="0e01d-167">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="0e01d-168">使用组策略排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="0e01d-168">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="0e01d-169">在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="0e01d-169">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="0e01d-170">在组 **策略管理编辑器中**，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="0e01d-170">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="0e01d-171">展开树以 **Windows攻击**  >  **Microsoft Defender 防病毒Windows Defender**  >  **攻击**  >  **面减少的组件**。</span><span class="sxs-lookup"><span data-stu-id="0e01d-171">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="0e01d-172">双击从攻击 **面减少规则中排除** 文件和路径设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0e01d-172">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="0e01d-173">选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e01d-173">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="0e01d-174">在"值"**列中为** 每个项目输入 **0。**</span><span class="sxs-lookup"><span data-stu-id="0e01d-174">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="0e01d-175">请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。</span><span class="sxs-lookup"><span data-stu-id="0e01d-175">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="0e01d-176">使用 PowerShell 排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="0e01d-176">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="0e01d-177">在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"**</span><span class="sxs-lookup"><span data-stu-id="0e01d-177">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="0e01d-178">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0e01d-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="0e01d-179">继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e01d-179">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e01d-180">用于 `Add-MpPreference` 向列表中追加或添加应用。</span><span class="sxs-lookup"><span data-stu-id="0e01d-180">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="0e01d-181">使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="0e01d-181">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="0e01d-182">使用 MDM CSP 排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="0e01d-182">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="0e01d-183">使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。</span><span class="sxs-lookup"><span data-stu-id="0e01d-183">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="0e01d-184">自定义通知</span><span class="sxs-lookup"><span data-stu-id="0e01d-184">Customize the notification</span></span>

<span data-ttu-id="0e01d-185">你可以自定义何时触发规则并阻止应用或文件的通知。</span><span class="sxs-lookup"><span data-stu-id="0e01d-185">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="0e01d-186">请参阅[Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。</span><span class="sxs-lookup"><span data-stu-id="0e01d-186">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e01d-187">相关主题</span><span class="sxs-lookup"><span data-stu-id="0e01d-187">Related topics</span></span>

* [<span data-ttu-id="0e01d-188">使用攻击面减少规则减少攻击面</span><span class="sxs-lookup"><span data-stu-id="0e01d-188">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="0e01d-189">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="0e01d-189">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="0e01d-190">评估减少攻击面规则</span><span class="sxs-lookup"><span data-stu-id="0e01d-190">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="0e01d-191">关于减少攻击面的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0e01d-191">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
