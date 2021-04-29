---
title: 启用"首次看到时阻止"以在数秒后检测恶意软件
description: 打开"首次看到时阻止"功能，以在数秒钟内检测和阻止恶意软件。
keywords: 扫描， 首次看到时阻止， 恶意软件， 首次看到， 云， defender， 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079199"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="226f9-104">在首次看到时打开阻止</span><span class="sxs-lookup"><span data-stu-id="226f9-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="226f9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="226f9-105">**Applies to:**</span></span>

- [<span data-ttu-id="226f9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="226f9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="226f9-107">本文介绍称为"首次看到时阻止"的防病毒/反恶意软件功能，并介绍如何为组织启用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="226f9-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="226f9-108">本文面向管理组织安全设置的企业管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="226f9-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="226f9-109">如果你不是企业管理员或 IT 专业人员，但对首次看到时阻止有疑问，请参阅不是企业管理员[或 IT 专业人员？。](#not-an-enterprise-admin-or-it-pro)</span><span class="sxs-lookup"><span data-stu-id="226f9-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="226f9-110">什么是"首次看到时阻止"？</span><span class="sxs-lookup"><span data-stu-id="226f9-110">What is "block at first sight"?</span></span>

<span data-ttu-id="226f9-111">"首次看到时阻止"是下一代保护的威胁防护功能，可检测新恶意软件，并会在数秒钟内阻止它。</span><span class="sxs-lookup"><span data-stu-id="226f9-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="226f9-112">启用某些安全设置后，将启用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="226f9-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="226f9-113">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="226f9-113">These settings include:</span></span>

- <span data-ttu-id="226f9-114">云保护;</span><span class="sxs-lookup"><span data-stu-id="226f9-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="226f9-115">指定的示例提交超时 (如 50 秒) ;和</span><span class="sxs-lookup"><span data-stu-id="226f9-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="226f9-116">文件阻止级别较高。</span><span class="sxs-lookup"><span data-stu-id="226f9-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="226f9-117">在大多数企业组织中，启用"首次看到时阻止"所需的设置都使用 Microsoft Defender 防病毒部署进行配置。</span><span class="sxs-lookup"><span data-stu-id="226f9-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="226f9-118">运作方式</span><span class="sxs-lookup"><span data-stu-id="226f9-118">How it works</span></span>

<span data-ttu-id="226f9-119">当 Microsoft Defender 防病毒遇到可疑但未检测到的文件时，它会查询云保护后端。</span><span class="sxs-lookup"><span data-stu-id="226f9-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="226f9-120">云后端对文件应用启发式、机器学习和自动分析，以确定文件是否是恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="226f9-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="226f9-121">Microsoft Defender 防病毒使用多个检测和防护技术提供准确、智能和实时的保护。</span><span class="sxs-lookup"><span data-stu-id="226f9-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="226f9-123">若要了解更多信息，请参阅此博客：了解 Microsoft Defender for Endpoint 下一代保护 [的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="226f9-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="226f9-124">有关首次看到时阻止的一些了解内容</span><span class="sxs-lookup"><span data-stu-id="226f9-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="226f9-125">在 Windows 10 版本 1803 或更高版本中，"首次看到时阻止"可以阻止不可移植的可执行文件 (如 JS、VBS 或宏) 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="226f9-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="226f9-126">"首次看到时阻止"仅对从 Internet 下载的可执行文件和不可移植的可执行文件或源自 Internet 区域的文件使用云保护后端。</span><span class="sxs-lookup"><span data-stu-id="226f9-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="226f9-127">通过云后端检查 .exe 文件的哈希值，以确定该文件以前是否未检测到。</span><span class="sxs-lookup"><span data-stu-id="226f9-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="226f9-128">如果云后端无法确定，Microsoft Defender 防病毒将锁定文件，并将其副本上传到云。</span><span class="sxs-lookup"><span data-stu-id="226f9-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="226f9-129">云会执行更多分析，以在它允许文件运行或在将来遇到时阻止它，具体取决于它是否确定文件是恶意文件或不是威胁文件。</span><span class="sxs-lookup"><span data-stu-id="226f9-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="226f9-130">在许多情况下，此过程可以将新恶意软件的响应时间从几小时缩短到秒。</span><span class="sxs-lookup"><span data-stu-id="226f9-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="226f9-131">你可以 [指定在基于云的](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 保护服务分析文件时阻止文件运行的时间。</span><span class="sxs-lookup"><span data-stu-id="226f9-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="226f9-132">此外， [还可以自定义在](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 文件被阻止时显示在用户桌面上的消息。</span><span class="sxs-lookup"><span data-stu-id="226f9-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="226f9-133">您可以更改公司名称、联系人信息和邮件 URL。</span><span class="sxs-lookup"><span data-stu-id="226f9-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="226f9-134">使用 Microsoft Intune 打开"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="226f9-135">Microsoft Intune 现在是 Microsoft Endpoint Manager 的一部分。</span><span class="sxs-lookup"><span data-stu-id="226f9-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="226f9-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) ， navigate to **Devices**  >  **Configuration profiles**.</span><span class="sxs-lookup"><span data-stu-id="226f9-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="226f9-137">使用设备限制配置文件类型 **选择或创建** 配置文件。</span><span class="sxs-lookup"><span data-stu-id="226f9-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="226f9-138">在设备 **限制** 配置文件的配置设置中，在 Microsoft Defender 防病毒下设置或确认 **以下设置**：</span><span class="sxs-lookup"><span data-stu-id="226f9-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="226f9-139">**云保护：** 已启用</span><span class="sxs-lookup"><span data-stu-id="226f9-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="226f9-140">**文件阻止级别**：高</span><span class="sxs-lookup"><span data-stu-id="226f9-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="226f9-141">**云文件扫描的扩展名**：50</span><span class="sxs-lookup"><span data-stu-id="226f9-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="226f9-142">**在提交示例之前提示用户**：在不提示的情况下发送所有数据</span><span class="sxs-lookup"><span data-stu-id="226f9-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="226f9-144">保存设置。</span><span class="sxs-lookup"><span data-stu-id="226f9-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="226f9-145">将文件阻止级别设置为 **"高** "将应用强级别的检测。</span><span class="sxs-lookup"><span data-stu-id="226f9-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="226f9-146">如果文件阻止导致对合法文件进行误报检测，安全运营团队可以 [还原隔离的文件](./restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="226f9-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="226f9-147">有关在 Intune 中配置 Microsoft Defender 防病毒设备限制的信息，请参阅在 Microsoft Intune 中配置 [设备限制设置](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="226f9-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="226f9-148">有关 Intune 中的 Microsoft Defender 防病毒设备限制的列表，请参阅 Intune 中的 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) (和) 设备限制。</span><span class="sxs-lookup"><span data-stu-id="226f9-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="226f9-149">使用 Microsoft Endpoint Manager 打开"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="226f9-150">如果你正在寻找 Microsoft Endpoint Configuration Manager，它现在是 Microsoft Endpoint Manager 的一部分。</span><span class="sxs-lookup"><span data-stu-id="226f9-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="226f9-151">在 Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，转到 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="226f9-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="226f9-152">选择现有策略，或者使用 **Microsoft Defender** 防病毒配置文件类型创建新策略。</span><span class="sxs-lookup"><span data-stu-id="226f9-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="226f9-153">设置或确认以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="226f9-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="226f9-154">**启用云保护：** 是</span><span class="sxs-lookup"><span data-stu-id="226f9-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="226f9-155">**云提供的保护级别**：高</span><span class="sxs-lookup"><span data-stu-id="226f9-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="226f9-156">**Defender 云扩展超时（以秒数表示）：50**</span><span class="sxs-lookup"><span data-stu-id="226f9-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="终结点管理器中的&quot;首次看到时阻止&quot;设置":::

4. <span data-ttu-id="226f9-158">将 Microsoft Defender 防病毒配置文件应用于组，如所有用户、所有 **设备** 或 **所有用户和设备**。</span><span class="sxs-lookup"><span data-stu-id="226f9-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="226f9-159">使用组策略启用"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="226f9-160">我们建议使用 Intune 或 Microsoft Endpoint Manager 打开"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="226f9-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="226f9-161">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="226f9-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="226f9-162">使用组 **策略管理编辑器** 转到计算机 **配置** 管理  >  **模板**  >  **Windows 组件** Microsoft Defender  >  **防病毒**  >  **MAPS**。</span><span class="sxs-lookup"><span data-stu-id="226f9-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="226f9-163">在"MAPS"部分，双击"配置'首次看到时阻止 **'功能**"，将其设置为"已启用"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="226f9-164">设置为 **始终提示 (0)** 会降低设备的保护状态。</span><span class="sxs-lookup"><span data-stu-id="226f9-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="226f9-165">设置为" **从不发送 (2)** 意味着首次看到时阻止将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="226f9-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="226f9-166">在 MAPS 部分中，双击"需要进一步 **分析时发送文件示例"，** 并将其设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="226f9-167">在 **"需要进一步分析时发送文件示例"下**，选择 **"发送所有示例**"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="226f9-168">像通常一样在整个网络中重新部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="226f9-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="226f9-169">确认在个别客户端设备上启用"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="226f9-170">你可以确认使用 Windows 安全应用在个别客户端设备上启用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="226f9-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="226f9-171">只要启用了云提供的保护和自动提交示例，就会自动启用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="226f9-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="226f9-172">打开 Windows 安全应用。</span><span class="sxs-lookup"><span data-stu-id="226f9-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="226f9-173">选择 **病毒&威胁防护**"，然后在"病毒&**威胁防护设置**"下，选择"管理 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 安全应用中的病毒&威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="226f9-175">确认 **云提供的保护和\*\*\*\*自动提交** 示例均已打开。</span><span class="sxs-lookup"><span data-stu-id="226f9-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="226f9-176">如果使用组策略配置和部署先决条件设置，本部分中所述的设置将灰出，并且无法用于个别终结点。</span><span class="sxs-lookup"><span data-stu-id="226f9-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="226f9-177">必须先通过组策略对象所做的更改部署到个别终结点，然后才能在 Windows 设置中更新设置。</span><span class="sxs-lookup"><span data-stu-id="226f9-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="226f9-178">验证"首次看到时阻止"是否正常工作</span><span class="sxs-lookup"><span data-stu-id="226f9-178">Validate block at first sight is working</span></span>

<span data-ttu-id="226f9-179">若要验证该功能是否正常工作，请按照验证网络和云之间的连接[中的指南。](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="226f9-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="226f9-180">关闭"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="226f9-181">关闭"首次看到时阻止"将降低设备 (和) 保护状态。</span><span class="sxs-lookup"><span data-stu-id="226f9-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="226f9-182">如果你想要保留先决条件设置而不实际使用"首次看到时阻止"保护，你可以选择禁用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="226f9-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="226f9-183">你可以暂时关闭"首次看到时阻止"以查看此功能对网络有何影响。</span><span class="sxs-lookup"><span data-stu-id="226f9-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="226f9-184">但是，建议不要永久禁用首次看到时阻止。</span><span class="sxs-lookup"><span data-stu-id="226f9-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="226f9-185">使用 Microsoft Endpoint Manager 关闭"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="226f9-186">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="226f9-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="226f9-187">转到 **终结点安全**  >  **防病毒**，然后选择你的 Microsoft Defender 防病毒策略。</span><span class="sxs-lookup"><span data-stu-id="226f9-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="226f9-188">在 **"管理"** 下，选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="226f9-189">在"**配置设置"旁边，** 选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="226f9-190">更改以下一个或多个设置：</span><span class="sxs-lookup"><span data-stu-id="226f9-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="226f9-191">将 **"启用云提供的保护"设置为\*\*\*\*"否**"**或"未配置"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="226f9-192">将 **云提供的保护级别设置为\*\*\*\*"未配置"。**</span><span class="sxs-lookup"><span data-stu-id="226f9-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="226f9-193">清除 Defender 云扩展 **超时（以秒数表示）的复选框**。</span><span class="sxs-lookup"><span data-stu-id="226f9-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="226f9-194">查看并保存设置。</span><span class="sxs-lookup"><span data-stu-id="226f9-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="226f9-195">使用组策略关闭"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="226f9-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="226f9-196">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="226f9-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="226f9-197">使用组 **策略管理编辑器** 转到计算机 **配置，** 然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="226f9-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="226f9-198">通过 Windows组件 Microsoft Defender 防病毒 MAPS  >  **展开**  >  **树**。</span><span class="sxs-lookup"><span data-stu-id="226f9-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="226f9-199">双击配置 **'首次看到时阻止'功能** ，将选项设置为 **已禁用**。</span><span class="sxs-lookup"><span data-stu-id="226f9-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="226f9-200">禁用"首次看到时阻止"不会禁用或更改先决条件组策略。</span><span class="sxs-lookup"><span data-stu-id="226f9-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="226f9-201">不是企业管理员或 IT 专业人员？</span><span class="sxs-lookup"><span data-stu-id="226f9-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="226f9-202">如果你不是企业管理员或 IT 专业人员，但对首次看到时阻止有疑问，本部分适合你。</span><span class="sxs-lookup"><span data-stu-id="226f9-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="226f9-203">"首次看到时阻止"是一项威胁防护功能，可检测和阻止数秒钟内的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="226f9-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="226f9-204">尽管不存在名为"首次看到时阻止"的特定设置，但是当设备上配置某些设置时，会启用该功能。</span><span class="sxs-lookup"><span data-stu-id="226f9-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="226f9-205">如何在你自己的设备上管理首次看到时阻止</span><span class="sxs-lookup"><span data-stu-id="226f9-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="226f9-206">如果你有一个不由组织管理的个人设备，你可能想知道如何打开或关闭首次看到时阻止。</span><span class="sxs-lookup"><span data-stu-id="226f9-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="226f9-207">可以使用 Windows 安全应用管理首次看到时阻止。</span><span class="sxs-lookup"><span data-stu-id="226f9-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="226f9-208">在 Windows 10 计算机上，打开 Windows 安全应用。</span><span class="sxs-lookup"><span data-stu-id="226f9-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="226f9-209">选择 **病毒&威胁防护**。</span><span class="sxs-lookup"><span data-stu-id="226f9-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="226f9-210">在 **病毒&威胁防护设置下，** 选择管理 **设置**。</span><span class="sxs-lookup"><span data-stu-id="226f9-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="226f9-211">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="226f9-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="226f9-212">若要启用"首次看到时阻止"，请确保云提供的保护和自动示例提交都处于打开模式。</span><span class="sxs-lookup"><span data-stu-id="226f9-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="226f9-213">若要禁用"首次看到时阻止"，请关闭 **云保护** 或 **自动提交示例**。</span><span class="sxs-lookup"><span data-stu-id="226f9-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="226f9-214">关闭"首次看到时阻止"会降低设备的保护级别。</span><span class="sxs-lookup"><span data-stu-id="226f9-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="226f9-215">建议不要永久禁用首次看到时阻止。</span><span class="sxs-lookup"><span data-stu-id="226f9-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="226f9-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="226f9-216">See also</span></span>

- [<span data-ttu-id="226f9-217">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="226f9-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="226f9-218">启用云保护</span><span class="sxs-lookup"><span data-stu-id="226f9-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="226f9-219">使用 Windows 安全性保持受保护</span><span class="sxs-lookup"><span data-stu-id="226f9-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)