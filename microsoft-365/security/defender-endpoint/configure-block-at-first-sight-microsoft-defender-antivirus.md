---
title: 启用“首次看到时阻止”来在几秒内检测恶意软件
description: 打开“首次看到时阻止”功能来在几秒内检测和阻止恶意软件。
keywords: 扫描，首次看到时阻止，恶意软件，首次看到，云，Defender，防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ba0f2184ced21aea60b172d44936e3e2d36e5270
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274948"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="33d56-104">打开“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="33d56-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="33d56-105">**Applies to:**</span></span>

- [<span data-ttu-id="33d56-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="33d56-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="33d56-107">此文章解释了名为“首次看到时阻止”的防病毒/防恶意软件功能，并介绍了如何为组织启用“首次看到时阻止”功能。</span><span class="sxs-lookup"><span data-stu-id="33d56-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="33d56-108">此文章适合的读者为管理组织安全设置的企业管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="33d56-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="33d56-109">如果你不是企业管理员或 IT 专业人员，但你对“首次看到时阻止”有疑问的话，请参阅[不是企业管理员或 IT 专业人员？](#not-an-enterprise-admin-or-it-pro)。</span><span class="sxs-lookup"><span data-stu-id="33d56-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="33d56-110">什么是“首次看到时阻止”？</span><span class="sxs-lookup"><span data-stu-id="33d56-110">What is "block at first sight"?</span></span>

<span data-ttu-id="33d56-111">“首次看到时阻止”是下一代保护的一种威胁保护功能，它能够在几秒内检测新的恶意软件并将其阻止。</span><span class="sxs-lookup"><span data-stu-id="33d56-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="33d56-112">“首次看到时阻止”的启用方式是启用某些特定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="33d56-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="33d56-113">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="33d56-113">These settings include:</span></span>

- <span data-ttu-id="33d56-114">云端保护；</span><span class="sxs-lookup"><span data-stu-id="33d56-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="33d56-115">指定的示例提交超时（比如 50 秒）；以及</span><span class="sxs-lookup"><span data-stu-id="33d56-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="33d56-116">高文件阻止级别。</span><span class="sxs-lookup"><span data-stu-id="33d56-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="33d56-117">在大多数企业组织中，需要启用“首次看到时阻止”的设置都已在部署 Microsoft Defender 防病毒时配置了。</span><span class="sxs-lookup"><span data-stu-id="33d56-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="33d56-118">运作方式</span><span class="sxs-lookup"><span data-stu-id="33d56-118">How it works</span></span>

<span data-ttu-id="33d56-119">当 Microsoft Defender 防病毒软件遇到未检测到的可疑文件时，它会查询云保护后端。</span><span class="sxs-lookup"><span data-stu-id="33d56-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="33d56-120">云后端将应用启发式、机器学习以及自动文件分析，以确定文件是恶意文件还是非威胁文件。</span><span class="sxs-lookup"><span data-stu-id="33d56-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="33d56-121">Microsoft Defender 防病毒使用多种检测和防护技术来提供准确、智能、实时的保护。</span><span class="sxs-lookup"><span data-stu-id="33d56-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="33d56-123">若要了解更多，请参阅此博客：[了解 Microsoft Defender for Endpoint 下一代保护的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="33d56-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="33d56-124">关于“首次看到时阻止”的一些须知</span><span class="sxs-lookup"><span data-stu-id="33d56-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="33d56-125">在 Windows 10 1803 版本或更高版本中，“首次看到时阻止”现在可以阻止不可移植的可执行文件（如 JS、VBS 或宏）和可执行文件。</span><span class="sxs-lookup"><span data-stu-id="33d56-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="33d56-126">“首次看到时阻止”仅对从 Internet 下载或者源自 Internet 区域的可执行文件和不可移植的可执行文件使用云保护后端。</span><span class="sxs-lookup"><span data-stu-id="33d56-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="33d56-127">通过云后端检查 .exe 文件的哈希值，确定之前是否未检测过此文件。</span><span class="sxs-lookup"><span data-stu-id="33d56-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="33d56-128">如果云后端无法做出决定，Microsoft Defender 防病毒会锁定该文件，同时将副本上传到云。</span><span class="sxs-lookup"><span data-stu-id="33d56-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="33d56-129">云将执行更多分析以得出结论：以后遇到该文件，是允许运行还是阻止（具体取决于它确定文件是恶意文件还是非威胁文件）。</span><span class="sxs-lookup"><span data-stu-id="33d56-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="33d56-130">在许多情况下，此过程可将对新恶意软件的响应时间从几小时减少到几秒。</span><span class="sxs-lookup"><span data-stu-id="33d56-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="33d56-131">你可以[指定当基于云的保护服务在分析文件时，过多久后阻止文件运行](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="33d56-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="33d56-132">另外，当文件被阻止时，你可以[自定义用户桌面上显示的消息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)。</span><span class="sxs-lookup"><span data-stu-id="33d56-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="33d56-133">可更改公司名称、联系信息、消息 URL。</span><span class="sxs-lookup"><span data-stu-id="33d56-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="33d56-134">用 Microsoft Intune 打开“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="33d56-135">Microsoft Intune 现属于 Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="33d56-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="33d56-136">在 Microsoft Endpoint Manager 管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))，导航到“**设备**” > “**配置用户配置**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="33d56-137">使用“**设备限制**”用户配置类型选择或创建用户配置。</span><span class="sxs-lookup"><span data-stu-id="33d56-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="33d56-138">在设备限制用户配置的“**配置设置**”中，在“**Microsoft Defender 防病毒**”下设置或确认以下设置：</span><span class="sxs-lookup"><span data-stu-id="33d56-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="33d56-139">**云端保护**：启用</span><span class="sxs-lookup"><span data-stu-id="33d56-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="33d56-140">**文件阻止级别**：高</span><span class="sxs-lookup"><span data-stu-id="33d56-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="33d56-141">**云扫描文件的时长拓展**：50</span><span class="sxs-lookup"><span data-stu-id="33d56-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="33d56-142">**在提交示例之前提示用户**：在不提示的情况下发送所有数据</span><span class="sxs-lookup"><span data-stu-id="33d56-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="33d56-144">保存设置。</span><span class="sxs-lookup"><span data-stu-id="33d56-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="33d56-145">将文件阻止级别设置为 **高** 将应用高强度检测级别。</span><span class="sxs-lookup"><span data-stu-id="33d56-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="33d56-146">如果发生了意外情况，导致对合法文件做出了误报检测，你的安全操作团队可以[还原隔离的文件](./restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="33d56-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="33d56-147">有关在 Intune 中配置 Microsoft Defender 防病毒设备限制的详细信息，请参阅[在 Microsoft Intune 中配置设备限制设置](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="33d56-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="33d56-148">有关 Intune 中的 Microsoft Defender 防病毒设备限制的列表，请参阅 [Intune 中 Windows 10（和更高版本）设置的设备限制](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="33d56-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="33d56-149">用 Microsoft Endpoint Manager 打开“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="33d56-150">如果你在找 Microsoft Endpoint Configuration Manager，它现在属于 Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="33d56-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="33d56-151">在 Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 中，转到 **Endpoint 安全性** > **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="33d56-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="33d56-152">选择现有策略，或使用 **Microsoft Defender 防病毒** 用户配置类型创建新策略。</span><span class="sxs-lookup"><span data-stu-id="33d56-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="33d56-153">设置或确认以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="33d56-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="33d56-154">**打开云端保护**：是</span><span class="sxs-lookup"><span data-stu-id="33d56-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="33d56-155">**云端保护等级**：高</span><span class="sxs-lookup"><span data-stu-id="33d56-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="33d56-156">**Defender 云扩展超时（秒）**：50</span><span class="sxs-lookup"><span data-stu-id="33d56-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Endpoint Manager 中的“首次看到时阻止”":::

4. <span data-ttu-id="33d56-158">应用 Windows Defender 防病毒的用户配置到组，例如“**所有用户**”、“**所有设备**”或“**所有用户和设备**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="33d56-159">使用组策略打开“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="33d56-160">我们建议使用 Intune 或 Microsoft Endpoint Manager 来打开“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="33d56-161">在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="33d56-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="33d56-162">使用“**组策略管理编辑器**”转到“**计算机配置**” > “**管理模板**” > “**Windows 组件**” > “**Microsoft Defender 防病毒**” > “**MAPS**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="33d56-163">在“MAPS”节中，双击“**配置“首次看到时阻止”功能**”，将其设为“**启用**”，然后选择“**OK**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="33d56-164">设为 **始终提示 (0)** 会降低设备的保护状态。</span><span class="sxs-lookup"><span data-stu-id="33d56-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="33d56-165">设为始 **终不发送 (2)** 意味着“首次看到时阻止”将不起作用。</span><span class="sxs-lookup"><span data-stu-id="33d56-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="33d56-166">在“MAPS”节中，双击“**需要进一步分析时发送文件样本**”，将其设为“**启用**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="33d56-167">在“**需要进一步分析时发送文件样本**”下，选择“**发送所有样本**”，然后选择“**OK**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="33d56-168">如往常一样在网络上中心部署你的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="33d56-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="33d56-169">在客户端上确认“首次看到时阻止”是否已启用</span><span class="sxs-lookup"><span data-stu-id="33d56-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="33d56-170">可以使用 Windows 安全应用来确认“首次看到时阻止”功能是否已在某个客户端设备上启用。</span><span class="sxs-lookup"><span data-stu-id="33d56-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="33d56-171">只要同时启用了 **云端保护** 和 **自动提交样本**，就会自动启用“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="33d56-172">打开 Windows 安全应用。</span><span class="sxs-lookup"><span data-stu-id="33d56-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="33d56-173">选择“**病毒和威胁防护**”，然后在“**病毒和威胁防护设置**”下选择“**管理设置**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 安全应用中病毒和威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="33d56-175">确认 **云端保护** 和 **自动提交样本** 已开启。</span><span class="sxs-lookup"><span data-stu-id="33d56-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="33d56-176">如果已使用组策略配置并部署了先决条件设置，本部分所述的设置将灰显，并且在个别终结点上不可用。</span><span class="sxs-lookup"><span data-stu-id="33d56-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="33d56-177">通过组策略对象进行的更改必须先部署到个别终结点，然后 Windows 设置中的相关设置才会更新。</span><span class="sxs-lookup"><span data-stu-id="33d56-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="33d56-178">验证“首次看到时阻止”是否正常工作</span><span class="sxs-lookup"><span data-stu-id="33d56-178">Validate block at first sight is working</span></span>

<span data-ttu-id="33d56-179">你可以按照[验证网络和云之间的连接](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)中所述的步骤来验证该功能是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="33d56-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="33d56-180">关闭“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="33d56-181">关闭“首次看到时阻止”会降低设备和网络的保护状态。</span><span class="sxs-lookup"><span data-stu-id="33d56-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="33d56-182">如果希望保留先决条件设置，而不使用“首次看到时阻止”保护，则可以选择禁用“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="33d56-183">你可以暂时关闭“首次看到时阻止”来看看这对你的网络有什么影响。</span><span class="sxs-lookup"><span data-stu-id="33d56-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="33d56-184">但是，我们不建议长期禁用“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="33d56-185">用 Microsoft Endpoint Manager 关闭“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="33d56-186">转到 Microsoft Endpoint Manager 管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="33d56-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="33d56-187">转到“**终结点安全**” > “**防病毒**”，然后选择你的 Microsoft Defender 防病毒策略。</span><span class="sxs-lookup"><span data-stu-id="33d56-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="33d56-188">在“**管理**”下，选择“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="33d56-189">选择“**配置设置**”旁的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="33d56-190">请执行下列一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="33d56-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="33d56-191">将“**打开云端保护**”设为“**不**”或“**未配置**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="33d56-192">将“**云端保护级别**”设为“**未配置**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="33d56-193">清空 **Defender 云扩展超时（秒）** 复选框。</span><span class="sxs-lookup"><span data-stu-id="33d56-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="33d56-194">检查并保存你的设置。</span><span class="sxs-lookup"><span data-stu-id="33d56-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="33d56-195">使用组策略关闭“首次看到时阻止”</span><span class="sxs-lookup"><span data-stu-id="33d56-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="33d56-196">在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="33d56-197">在 **策略管理编辑器** 中， 转到“**计算机配置**”并选择“**管理模板**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="33d56-198">将树展开到“**Windows 组件**” > “**Windows Defender 防病毒**” > “**MAPS**。</span><span class="sxs-lookup"><span data-stu-id="33d56-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="33d56-199">双击“**配置“首次看到时阻止”功能**”，并将该选项设置为“**禁用**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33d56-200">禁用“首次看到时阻止”不会禁用或更改先决条件组策略。</span><span class="sxs-lookup"><span data-stu-id="33d56-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="33d56-201">不是企业管理员或 IT 专业人士？</span><span class="sxs-lookup"><span data-stu-id="33d56-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="33d56-202">如果你不是企业管理员或 IT 专业人员，但你对“首次看到时阻止”有疑问的话，请阅读此节。</span><span class="sxs-lookup"><span data-stu-id="33d56-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="33d56-203">“首次看到时阻止”是一种威胁保护功能，它能够在几秒内检测和阻止恶意软件。</span><span class="sxs-lookup"><span data-stu-id="33d56-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="33d56-204">其实没有某个设置叫“首次看到时阻止”，此功能的启用是通过配置设备上的某些设置来实现的。</span><span class="sxs-lookup"><span data-stu-id="33d56-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="33d56-205">如果在自己的设备上管理“首次看到时阻止”的开启与关闭</span><span class="sxs-lookup"><span data-stu-id="33d56-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="33d56-206">如果你的个人设备不受组织管理，你可能想知道如何开启或关闭“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="33d56-207">你可以使用 Windows 安全应用来管理“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="33d56-208">在你的 Windows 10 电脑上，打开 Windows 安全应用。</span><span class="sxs-lookup"><span data-stu-id="33d56-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="33d56-209">选择“**病毒和威胁防护**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="33d56-210">在“**病毒和威胁防护设置**”下选择“**管理设置**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="33d56-211">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="33d56-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="33d56-212">若要启用“首次看到时阻止”，请确保同时启用了“**云端保护**”和“**自动提交样本**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="33d56-213">若要禁用启用“首次看到时阻止”，请禁用“**云端保护**”或“**自动提交样本**”。</span><span class="sxs-lookup"><span data-stu-id="33d56-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="33d56-214">关闭“首次看到时阻止”会降低设备的保护级别。</span><span class="sxs-lookup"><span data-stu-id="33d56-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="33d56-215">我们不建议长期禁用“首次看到时阻止”。</span><span class="sxs-lookup"><span data-stu-id="33d56-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="33d56-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33d56-216">See also</span></span>

- [<span data-ttu-id="33d56-217">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="33d56-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="33d56-218">启用云保护</span><span class="sxs-lookup"><span data-stu-id="33d56-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="33d56-219">通过 Windows 安全持续受到保护</span><span class="sxs-lookup"><span data-stu-id="33d56-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)