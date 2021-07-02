---
title: 创建文件指示器
ms.reviewer: ''
description: 创建文件哈希的指示器，以定义实体的检测、防范和排除。
keywords: 文件， 哈希， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256911"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="2ca8d-104">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ca8d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ca8d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ca8d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ca8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ca8d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="2ca8d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="2ca8d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ca8d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="2ca8d-110">通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="2ca8d-111">如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="2ca8d-112">此操作将阻止在组织的设备上读取、写入或执行该操作。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="2ca8d-113">有三种方法可以创建文件指示器：</span><span class="sxs-lookup"><span data-stu-id="2ca8d-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="2ca8d-114">通过设置页面创建指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="2ca8d-115">通过使用文件详细信息页面中的"添加指示器"按钮创建上下文指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="2ca8d-116">通过指示器 [API 创建指示器](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="2ca8d-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2ca8d-117">开始之前</span><span class="sxs-lookup"><span data-stu-id="2ca8d-117">Before you begin</span></span>

<span data-ttu-id="2ca8d-118">在创建文件指示器之前，了解以下先决条件很重要：</span><span class="sxs-lookup"><span data-stu-id="2ca8d-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="2ca8d-119">如果你的组织在活动模式下使用 **Microsoft Defender 防病毒 (，) 启用** 基于云的保护，则此功能 **可用**。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="2ca8d-120">有关详细信息，请参阅 [管理基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="2ca8d-121">反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="2ca8d-122">请参阅 [每月平台和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="2ca8d-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="2ca8d-123">在具有 Windows 10 版本 1703 或更高版本、Windows Server 2016 2019 的设备上受支持。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="2ca8d-124">若要开始阻止文件，首先需要打开"阻止或允许 ["设置。](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="2ca8d-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="2ca8d-125">此功能旨在防止从 web (可疑恶意软件) 潜在恶意文件。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="2ca8d-126">它目前支持可移植的可执行 (PE) 文件，包括.exe和.dll文件。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="2ca8d-127">覆盖范围将随着时间的推移而延长。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="2ca8d-128">从设置页创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="2ca8d-129">在导航窗格中，选择 **"设置 >标记"。**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="2ca8d-130">选择" **文件哈希"**   选项卡。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="2ca8d-131">选择 **"添加指示器"。**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="2ca8d-132">指定以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="2ca8d-132">Specify the following details:</span></span>
    - <span data-ttu-id="2ca8d-133">Indicator - 指定实体详细信息并定义指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="2ca8d-134">操作 - 指定要采取的操作并提供说明。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="2ca8d-135">范围 - 定义设备组的范围。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="2ca8d-136">查看"摘要"选项卡中的详细信息，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="2ca8d-137">从文件详细信息页面创建上下文指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="2ca8d-138">对文件执行响应 [操作的选项](respond-file-alerts.md)之一是   添加文件指示器。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="2ca8d-139">为文件添加指示器哈希时，可以选择引发警报，并阻止组织中设备尝试运行该文件。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="2ca8d-140">由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="2ca8d-141">通常，文件块将在几分钟内强制执行和删除，但可能需要 30 分钟以上的时间。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="2ca8d-142">如果存在具有相同强制类型和目标的冲突文件 IoC 策略，将应用更安全哈希的策略。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="2ca8d-143">SHA-256 文件哈希 IoC 策略将超过 SHA-1 文件哈希 IoC 策略，如果哈希类型定义同一个文件，该策略将超过 MD5 文件哈希 IoC 策略。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="2ca8d-144">无论设备组如何，这始终为 true。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="2ca8d-145">在所有其他情况下，如果具有相同强制目标的冲突文件 IoC 策略应用于所有设备和设备组，那么对于设备，设备组的策略将获胜。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="2ca8d-146">如果禁用 EnableFileHashComputation 组策略，则文件 IoC 的阻止准确度将降低。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="2ca8d-147">但是，启用 `EnableFileHashComputation` 可能会影响设备性能。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="2ca8d-148">例如，将大文件从网络共享复制到本地设备（尤其是通过 VPN 连接）可能会影响设备性能。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="2ca8d-149">有关 EnableFileHashComputation 组策略详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="2ca8d-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="2ca8d-150">策略冲突处理</span><span class="sxs-lookup"><span data-stu-id="2ca8d-150">Policy conflict handling</span></span>  

<span data-ttu-id="2ca8d-151">证书和文件 IoC 策略处理冲突将遵循以下顺序：</span><span class="sxs-lookup"><span data-stu-id="2ca8d-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="2ca8d-152">如果应用程序控制和 AppLocker Windows Defender策略不允许该文件，**则阻止**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="2ca8d-153">否则，如果文件被排除Microsoft Defender 防病毒，**则允许**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="2ca8d-154">否则，如果阻止或警告文件 IoC 阻止或警告文件，则 **阻止/警告**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="2ca8d-155">否则，如果允许文件 IoC 策略允许该文件 **，则允许**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="2ca8d-156">否则，如果该文件被 ASR 规则、CFA、AV、SmartScreen 阻止，则 **阻止**</span><span class="sxs-lookup"><span data-stu-id="2ca8d-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="2ca8d-157">Else **Allow** (AppLocker 策略Windows Defender应用程序控制&，任何 IoC 规则都不适用于它) </span><span class="sxs-lookup"><span data-stu-id="2ca8d-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="2ca8d-158">如果存在具有相同强制类型和目标的冲突文件 IoC 策略，则更安全的文件 ioC 策略 (这意味着将应用) 哈希时间更长。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="2ca8d-159">例如，如果 SHA-256 文件哈希 IoC 策略定义同一个文件，则策略将超过 MD5 文件哈希 IoC 策略。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="2ca8d-160">威胁漏洞管理阻止易受攻击的应用程序功能使用文件 IoC 进行强制执行，并遵循上述冲突处理顺序。</span><span class="sxs-lookup"><span data-stu-id="2ca8d-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="2ca8d-161">示例</span><span class="sxs-lookup"><span data-stu-id="2ca8d-161">Examples</span></span>

|<span data-ttu-id="2ca8d-162">组件</span><span class="sxs-lookup"><span data-stu-id="2ca8d-162">Component</span></span> |<span data-ttu-id="2ca8d-163">组件强制</span><span class="sxs-lookup"><span data-stu-id="2ca8d-163">Component enforcement</span></span> |<span data-ttu-id="2ca8d-164">文件指示器操作</span><span class="sxs-lookup"><span data-stu-id="2ca8d-164">File indicator Action</span></span> |<span data-ttu-id="2ca8d-165">结果</span><span class="sxs-lookup"><span data-stu-id="2ca8d-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="2ca8d-166">攻击面减少文件路径排除</span><span class="sxs-lookup"><span data-stu-id="2ca8d-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="2ca8d-167">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-167">Allow</span></span> |<span data-ttu-id="2ca8d-168">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-168">Block</span></span> |<span data-ttu-id="2ca8d-169">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-169">Block</span></span>
|<span data-ttu-id="2ca8d-170">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="2ca8d-170">Attack surface reduction rule</span></span> |<span data-ttu-id="2ca8d-171">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-171">Block</span></span> |<span data-ttu-id="2ca8d-172">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-172">Allow</span></span> |<span data-ttu-id="2ca8d-173">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-173">Allow</span></span>
|<span data-ttu-id="2ca8d-174">Windows Defender 应用程序控制</span><span class="sxs-lookup"><span data-stu-id="2ca8d-174">Windows Defender Application Control</span></span> |<span data-ttu-id="2ca8d-175">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-175">Allow</span></span> |<span data-ttu-id="2ca8d-176">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-176">Block</span></span> |<span data-ttu-id="2ca8d-177">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-177">Allow</span></span> |
|<span data-ttu-id="2ca8d-178">Windows Defender 应用程序控制</span><span class="sxs-lookup"><span data-stu-id="2ca8d-178">Windows Defender Application Control</span></span> |<span data-ttu-id="2ca8d-179">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-179">Block</span></span> |<span data-ttu-id="2ca8d-180">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-180">Allow</span></span> |<span data-ttu-id="2ca8d-181">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-181">Block</span></span>
|<span data-ttu-id="2ca8d-182">Microsoft Defender 防病毒排除</span><span class="sxs-lookup"><span data-stu-id="2ca8d-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="2ca8d-183">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-183">Allow</span></span> |<span data-ttu-id="2ca8d-184">阻止</span><span class="sxs-lookup"><span data-stu-id="2ca8d-184">Block</span></span> |<span data-ttu-id="2ca8d-185">允许</span><span class="sxs-lookup"><span data-stu-id="2ca8d-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="2ca8d-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ca8d-186">See also</span></span>

- [<span data-ttu-id="2ca8d-187">创建指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="2ca8d-188">创建 IP 和 URL/域指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="2ca8d-189">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="2ca8d-190">管理指示器</span><span class="sxs-lookup"><span data-stu-id="2ca8d-190">Manage indicators</span></span>](indicator-manage.md)
