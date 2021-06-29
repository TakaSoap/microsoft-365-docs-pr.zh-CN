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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6d2770dec270e2d1c1b9750387a0f07f82b357f9
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177089"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="5c8ce-104">自定义减少攻击面规则</span><span class="sxs-lookup"><span data-stu-id="5c8ce-104">Customize attack surface reduction rules</span></span>

<span data-ttu-id="5c8ce-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5c8ce-105">**Applies to:**</span></span>

- [<span data-ttu-id="5c8ce-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c8ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c8ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c8ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5c8ce-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="5c8ce-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c8ce-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="5c8ce-110">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5c8ce-111">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5c8ce-112">[攻击面减少规则](enable-attack-surface-reduction.md) 有助于防止经常滥用以损害设备或网络的软件行为。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="5c8ce-113">例如，攻击者可能会尝试从 USB 驱动器运行未签名的脚本，或者让 Office 文档中的宏直接调用 Win32 API。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="5c8ce-114">攻击面减少规则可以限制这些类型的风险行为，并改进组织的防御状态。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="5c8ce-115">了解如何通过排除文件和文件夹或向用户计算机上[](#exclude-files-and-folders)显示的通知警报添加自定义文本[](#customize-the-notification)来自定义攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="5c8ce-116">你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：</span><span class="sxs-lookup"><span data-stu-id="5c8ce-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="5c8ce-117">Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="5c8ce-117">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5c8ce-118">Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本</span><span class="sxs-lookup"><span data-stu-id="5c8ce-118">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="5c8ce-119">Windows服务器版本[1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本</span><span class="sxs-lookup"><span data-stu-id="5c8ce-119">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="5c8ce-120">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5c8ce-120">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="5c8ce-121">可以使用组策略、PowerShell 和移动设备管理 (MDM) CSP (配置) 配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-121">You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

<span data-ttu-id="5c8ce-122">有关 [支持](enable-attack-surface-reduction.md#requirements) 的操作系统和其他要求信息的信息，请参阅"启用攻击面减少规则"文章中的要求。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-122">See [Requirements](enable-attack-surface-reduction.md#requirements) in the "Enable attack surface reduction rules" article for information about supported operating systems and additional requirement information.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="5c8ce-123">排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="5c8ce-123">Exclude files and folders</span></span>

<span data-ttu-id="5c8ce-124">你可以选择从攻击面减少规则评估中排除文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-124">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="5c8ce-125">排除后，即使攻击面减少规则检测到文件包含恶意行为，也不会阻止文件运行。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-125">When excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

<span data-ttu-id="5c8ce-126">例如，请考虑勒索软件规则：</span><span class="sxs-lookup"><span data-stu-id="5c8ce-126">For example, consider the ransomware rule:</span></span>

<span data-ttu-id="5c8ce-127">勒索软件规则旨在帮助企业客户降低勒索软件攻击的风险，同时确保业务连续性。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-127">The ransomware rule is designed to help enterprise customers reduce risks of ransomware attacks while ensuring business continuity.</span></span> <span data-ttu-id="5c8ce-128">默认情况下，勒索软件规则错误应谨慎处理，并防范尚未获得足够信誉和信任的文件。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-128">By default, the ransomware rule errors on the side of caution and protect against files that haven't yet attained sufficient reputation and trust.</span></span> <span data-ttu-id="5c8ce-129">为了重新强调一下，勒索软件规则仅针对未基于数百万客户的使用情况指标获得足够正面信誉和普遍程度的文件触发。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-129">To reemphasize, the ransomware rule only triggers on files that have not gained enough positive reputation and prevalence, based on usage metrics of millions of our customers.</span></span> <span data-ttu-id="5c8ce-130">通常，块是自行解析的，因为每个文件的"信誉和信任"值都会随着无问题使用率的增加而递增升级。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-130">Usually, the blocks are self resolved, because each file's “reputation and trust” values are incrementally upgraded as non-problematic usage increases.</span></span>

<span data-ttu-id="5c8ce-131">如果无法及时解决阻止问题，客户可以自行承担风险，使用自助服务机制或基于IOC (IOC) 的"允许列表"功能来取消阻止文件本身。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-131">In cases in which blocks aren’t self resolved in a timely manner, customers can - _at their own risk_ - make use of either the self-service mechanism or an Indicator of Compromise (IOC)-based "allow list" capability to unblock the files themselves.</span></span>  

> [!WARNING]
> <span data-ttu-id="5c8ce-132">排除或取消阻止文件或文件夹可能会允许不安全的文件运行并感染你的设备。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-132">Excluding or unblocking files or folders could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="5c8ce-133">排除文件或文件夹可以严重削弱攻击面减少规则提供的保护。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-133">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="5c8ce-134">将允许运行规则阻止的文件，并且不会记录任何报告或事件。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-134">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="5c8ce-135">排除应用于允许排除的所有规则。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-135">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="5c8ce-136">您可以为资源指定单个文件、文件夹路径或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-136">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="5c8ce-137">但是，不能将排除限制到特定规则。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-137">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="5c8ce-138">仅在已排除的应用程序或服务启动时应用排除。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-138">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="5c8ce-139">例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-139">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="5c8ce-140">攻击面减少支持环境变量和通配符。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-140">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="5c8ce-141">有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-141">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) .</span></span>
<span data-ttu-id="5c8ce-142">如果在检测你认为不应检测到的文件的规则方面遇到问题，请使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-142">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

| <span data-ttu-id="5c8ce-143">规则说明</span><span class="sxs-lookup"><span data-stu-id="5c8ce-143">Rule description</span></span> | <span data-ttu-id="5c8ce-144">GUID</span><span class="sxs-lookup"><span data-stu-id="5c8ce-144">GUID</span></span> |
|:----|:----|
| <span data-ttu-id="5c8ce-145">阻止滥用被攻击的易受攻击的已签名驱动程序</span><span class="sxs-lookup"><span data-stu-id="5c8ce-145">Block abuse of exploited vulnerable signed drivers</span></span> | `56a863a9-875e-4185-98a7-b882c64b5ce5` |
| <span data-ttu-id="5c8ce-146">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="5c8ce-146">Block Adobe Reader from creating child processes</span></span> | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| <span data-ttu-id="5c8ce-147">阻止所有Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="5c8ce-147">Block all Office applications from creating child processes</span></span> | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| <span data-ttu-id="5c8ce-148">阻止本地安全机构子系统Windows窃取凭据 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="5c8ce-148">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| <span data-ttu-id="5c8ce-149">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="5c8ce-149">Block executable content from email client and webmail</span></span> | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| <span data-ttu-id="5c8ce-150">阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="5c8ce-150">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| <span data-ttu-id="5c8ce-151">阻止执行可能混淆的脚本</span><span class="sxs-lookup"><span data-stu-id="5c8ce-151">Block execution of potentially obfuscated scripts</span></span> | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| <span data-ttu-id="5c8ce-152">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="5c8ce-152">Block JavaScript or VBScript from launching downloaded executable content</span></span> | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| <span data-ttu-id="5c8ce-153">阻止Office应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="5c8ce-153">Block Office applications from creating executable content</span></span> | `3B576869-A4EC-4529-8536-B80A7769E899` |
| <span data-ttu-id="5c8ce-154">阻止Office代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="5c8ce-154">Block Office applications from injecting code into other processes</span></span> | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| <span data-ttu-id="5c8ce-155">阻止Office应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="5c8ce-155">Block Office communication applications from creating child processes</span></span> | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| <span data-ttu-id="5c8ce-156">通过 WMI 事件订阅阻止持久性</span><span class="sxs-lookup"><span data-stu-id="5c8ce-156">Block persistence through WMI event subscription</span></span> | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |
| <span data-ttu-id="5c8ce-157">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="5c8ce-157">Block process creations originating from PSExec and WMI commands</span></span> | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| <span data-ttu-id="5c8ce-158">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="5c8ce-158">Block untrusted and unsigned processes that run from USB</span></span> | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| <span data-ttu-id="5c8ce-159">从宏中阻止 Win32 API Office调用</span><span class="sxs-lookup"><span data-stu-id="5c8ce-159">Block Win32 API calls from Office macro</span></span> | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| <span data-ttu-id="5c8ce-160">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="5c8ce-160">Use advanced protection against ransomware</span></span> | `c1db55ab-c21a-4637-bb3f-a12568109d35` |

<span data-ttu-id="5c8ce-161">有关 [每个规则的详细信息](attack-surface-reduction.md) ，请参阅攻击面减少主题。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-161">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="5c8ce-162">使用组策略排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="5c8ce-162">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="5c8ce-163">在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-163">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="5c8ce-164">在组 **策略管理编辑器中**，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-164">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="5c8ce-165">展开树以 **Windows攻击**  >    >  **Microsoft Defender 防病毒Microsoft Defender 攻击防护**  >  **减少的组件**。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-165">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="5c8ce-166">双击从攻击 **面减少规则中排除** 文件和路径设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-166">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="5c8ce-167">选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-167">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="5c8ce-168">在"值"**列中为** 每个项目输入 **0。**</span><span class="sxs-lookup"><span data-stu-id="5c8ce-168">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="5c8ce-169">请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-169">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="5c8ce-170">使用 PowerShell 排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="5c8ce-170">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="5c8ce-171">在 **"管理"中"开始"菜单 powershell，** 右键单击"Windows PowerShell并选择"以 **管理员角色运行"**</span><span class="sxs-lookup"><span data-stu-id="5c8ce-171">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="5c8ce-172">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5c8ce-172">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="5c8ce-173">继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-173">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c8ce-174">用于 `Add-MpPreference` 向列表中追加或添加应用。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-174">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="5c8ce-175">使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-175">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="5c8ce-176">使用 MDM CSP 排除文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="5c8ce-176">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="5c8ce-177">使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-177">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="5c8ce-178">自定义通知</span><span class="sxs-lookup"><span data-stu-id="5c8ce-178">Customize the notification</span></span>

<span data-ttu-id="5c8ce-179">你可以自定义何时触发规则并阻止应用或文件的通知。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-179">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="5c8ce-180">请参阅[Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。</span><span class="sxs-lookup"><span data-stu-id="5c8ce-180">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c8ce-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="5c8ce-181">Related topics</span></span>

- [<span data-ttu-id="5c8ce-182">使用攻击面减少规则减少攻击面</span><span class="sxs-lookup"><span data-stu-id="5c8ce-182">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
- [<span data-ttu-id="5c8ce-183">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="5c8ce-183">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="5c8ce-184">评估攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="5c8ce-184">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="5c8ce-185">关于攻击面减少的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="5c8ce-185">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
