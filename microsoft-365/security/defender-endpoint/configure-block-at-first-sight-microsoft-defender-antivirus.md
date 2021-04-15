---
title: 启用"首次看到时阻止"以在数秒后检测恶意软件
description: 打开"首次看到时阻止"功能，以在数秒钟内检测和阻止恶意软件。
keywords: 扫描， BAFS， 恶意软件， 首次看到， 首次看到， 云， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765751"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="7e2ba-104">在首次看到时打开阻止</span><span class="sxs-lookup"><span data-stu-id="7e2ba-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7e2ba-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-105">**Applies to:**</span></span>

- [<span data-ttu-id="7e2ba-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e2ba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7e2ba-107">"首次看到时阻止"提供了一种在数秒钟内检测和阻止新恶意软件的方法。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="7e2ba-108">当启用某些先决条件设置时，默认情况下会启用此保护。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="7e2ba-109">这些设置包括云保护、指定的示例提交超时 (如 50 秒) ，以及文件阻止级别较高。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="7e2ba-110">在大多数企业组织中，默认情况下会通过 Microsoft Defender 防病毒部署启用这些设置。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="7e2ba-111">你可以 [指定在基于云的](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 保护服务分析文件时阻止文件运行的时间。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="7e2ba-112">此外， [还可以自定义在](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 文件被阻止时显示在用户桌面上的消息。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="7e2ba-113">您可以更改公司名称、联系人信息和邮件 URL。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="7e2ba-114">请访问 Microsoft Defender for Endpoint 演示网站 [，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 以确认这些功能是否正常工作，并查看这些功能如何工作。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="7e2ba-115">运作方式</span><span class="sxs-lookup"><span data-stu-id="7e2ba-115">How it works</span></span>

<span data-ttu-id="7e2ba-116">当 Microsoft Defender 防病毒遇到可疑但未检测到的文件时，它会查询云保护后端。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="7e2ba-117">云后端对文件应用启发式、机器学习和自动分析，以确定文件是否是恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="7e2ba-118">Microsoft Defender 防病毒使用多个检测和防护技术提供准确、智能和实时的保护。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="7e2ba-119">若要了解更多信息，请参阅此博客：了解 Microsoft Defender for Endpoint 下一代保护 [的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="7e2ba-120">![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="7e2ba-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="7e2ba-121">在 Windows 10 版本 1803 或更高版本中，"首次看到时阻止"可以阻止不可移植的可执行文件 (如 JS、VBS 或宏) 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="7e2ba-122">"首次看到时阻止"仅对从 Internet 下载的可执行文件和不可移植的可执行文件或源自 Internet 区域的文件使用云保护后端。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="7e2ba-123">通过云后端检查 .exe 文件的哈希值，以确定该文件以前是否未检测到。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="7e2ba-124">如果云后端无法确定，Microsoft Defender 防病毒将锁定文件，并将其副本上传到云。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="7e2ba-125">云执行其他分析，以在允许文件运行或在将来遇到时阻止它，具体取决于它确定文件是恶意文件还是安全文件。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="7e2ba-126">在许多情况下，此过程可以将新恶意软件的响应时间从几小时缩短到秒。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="7e2ba-127">使用 Microsoft Intune 打开"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="7e2ba-128">Microsoft Intune 现在是 Microsoft Endpoint Manager 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="7e2ba-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) ， navigate to **Devices**  >  **Configuration profiles**.</span><span class="sxs-lookup"><span data-stu-id="7e2ba-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="7e2ba-130">使用设备限制配置文件类型 **选择或创建** 配置文件。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="7e2ba-131">在设备 **限制** 配置文件的配置设置中，在 Microsoft Defender 防病毒下设置或确认 **以下设置**：</span><span class="sxs-lookup"><span data-stu-id="7e2ba-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="7e2ba-132">**云保护：** 已启用</span><span class="sxs-lookup"><span data-stu-id="7e2ba-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="7e2ba-133">**文件阻止级别**：高</span><span class="sxs-lookup"><span data-stu-id="7e2ba-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="7e2ba-134">**云文件扫描的扩展名**：50</span><span class="sxs-lookup"><span data-stu-id="7e2ba-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="7e2ba-135">**在提交示例之前提示用户**：在不提示的情况下发送所有数据</span><span class="sxs-lookup"><span data-stu-id="7e2ba-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="7e2ba-137">保存设置。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="7e2ba-138">将文件阻止级别设置为 **"高** "将应用强级别的检测。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="7e2ba-139">如果文件阻止导致对合法文件进行误报检测的不太可能，可以 [还原隔离的文件](./restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="7e2ba-140">有关在 Intune 中配置 Microsoft Defender 防病毒设备限制的信息，请参阅在 Microsoft Intune 中配置 [设备限制设置](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="7e2ba-141">有关 Intune 中的 Microsoft Defender 防病毒设备限制的列表，请参阅 Intune 中的 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) (和) 设备限制。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="7e2ba-142">使用 Microsoft Endpoint Manager 打开"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="7e2ba-143">如果你正在寻找 Microsoft Endpoint Configuration Manager，它现在是 Microsoft Endpoint Manager 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="7e2ba-144">在 Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，转到 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="7e2ba-145">选择现有策略，或者使用 **Microsoft Defender** 防病毒配置文件类型创建新策略。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="7e2ba-146">设置或确认以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="7e2ba-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="7e2ba-147">**启用云保护：** 是</span><span class="sxs-lookup"><span data-stu-id="7e2ba-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="7e2ba-148">**云提供的保护级别**：高</span><span class="sxs-lookup"><span data-stu-id="7e2ba-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="7e2ba-149">**Defender 云扩展超时（以秒数表示）：50**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="终结点管理器中的&quot;首次看到时阻止&quot;设置":::

4. <span data-ttu-id="7e2ba-151">将 Microsoft Defender 防病毒配置文件应用于组，如所有用户、所有 **设备** 或 **所有用户和设备**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="7e2ba-152">使用组策略启用"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="7e2ba-153">我们建议使用 Intune 或 Microsoft Endpoint Manager 打开"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="7e2ba-154">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="7e2ba-155">使用组 **策略管理编辑器** 转到计算机 **配置** 管理  >  **模板**  >  **Windows 组件** Microsoft Defender  >  **防病毒**  >  **MAPS**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="7e2ba-156">在"MAPS"部分，双击"配置'首次看到时阻止 **'功能**"，将其设置为"已启用"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7e2ba-157">设置为 **始终提示 (0)** 会降低设备的保护状态。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="7e2ba-158">设置为" **从不发送 (2)** 意味着首次看到时阻止将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="7e2ba-159">在 MAPS 部分中，双击"需要进一步 **分析时发送文件示例"，** 并将其设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="7e2ba-160">在 **"需要进一步分析时发送文件示例"下**，选择 **"发送所有示例**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="7e2ba-161">如果更改了任何设置，请在整个网络中重新部署组策略对象，以确保覆盖所有终结点。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="7e2ba-162">确认在个别客户端上启用"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="7e2ba-163">你可以确认使用 Windows 安全设置在个别客户端上启用了"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="7e2ba-164">只要启用了云提供的保护和自动提交示例，就会自动启用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="7e2ba-165">打开 Windows 安全应用。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="7e2ba-166">选择 **病毒&威胁防护**"，然后在"病毒&**威胁防护设置**"下，选择"管理 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 安全应用中的病毒&威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="7e2ba-168">确认 **云提供的保护和\*\*\*\*自动提交** 示例均已打开。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="7e2ba-169">如果使用组策略配置和部署先决条件设置，本部分中所述的设置将灰出，并且无法用于个别终结点。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="7e2ba-170">必须先通过组策略对象所做的更改部署到个别终结点，然后才能在 Windows 设置中更新设置。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="7e2ba-171">验证"首次看到时阻止"是否正常工作</span><span class="sxs-lookup"><span data-stu-id="7e2ba-171">Validate block at first sight is working</span></span>

<span data-ttu-id="7e2ba-172">若要验证该功能是否正常工作，请按照验证网络和云之间的连接[中的指南。](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="7e2ba-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="7e2ba-173">关闭"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="7e2ba-174">关闭"首次看到时阻止"将降低设备 (和) 保护状态。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="7e2ba-175">如果你想要保留先决条件设置而不实际使用"首次看到时阻止"保护，你可以选择禁用"首次看到时阻止"。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="7e2ba-176">如果遇到延迟问题或要测试功能对网络的影响，可能会暂时关闭首次看到时阻止。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="7e2ba-177">但是，建议不要永久禁用首次看到时阻止。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="7e2ba-178">使用 Microsoft Endpoint Manager 关闭"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="7e2ba-179">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="7e2ba-180">转到 **终结点安全**  >  **防病毒**，然后选择你的 Microsoft Defender 防病毒策略。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="7e2ba-181">在 **"管理"** 下，选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="7e2ba-182">在"**配置设置"旁边，** 选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="7e2ba-183">更改以下一个或多个设置：</span><span class="sxs-lookup"><span data-stu-id="7e2ba-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="7e2ba-184">将 **"启用云提供的保护"设置为\*\*\*\*"否**"**或"未配置"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="7e2ba-185">将 **云提供的保护级别设置为\*\*\*\*"未配置"。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="7e2ba-186">清除 **"Defender 云扩展超时（以秒表示）"** 框。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="7e2ba-187">查看并保存设置。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="7e2ba-188">使用组策略关闭"首次看到时阻止"</span><span class="sxs-lookup"><span data-stu-id="7e2ba-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="7e2ba-189">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="7e2ba-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="7e2ba-190">使用组 **策略管理编辑器** 转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="7e2ba-191">通过 Windows组件 Microsoft Defender 防病毒 MAPS  >  **展开**  >  **树**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="7e2ba-192">双击配置 **'首次看到时阻止'功能** ，将选项设置为 **已禁用**。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e2ba-193">禁用"首次看到时阻止"不会禁用或更改先决条件组策略。</span><span class="sxs-lookup"><span data-stu-id="7e2ba-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e2ba-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e2ba-194">See also</span></span>

- [<span data-ttu-id="7e2ba-195">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="7e2ba-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="7e2ba-196">启用云保护</span><span class="sxs-lookup"><span data-stu-id="7e2ba-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)