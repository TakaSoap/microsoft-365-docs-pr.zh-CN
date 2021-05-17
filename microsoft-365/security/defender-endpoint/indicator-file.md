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
ms.openlocfilehash: 103f5d0ad9d12a37f3a3b8065f39c24d592cc252
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995053"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="e94f0-104">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e94f0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e94f0-105">**Applies to:**</span></span>
- [<span data-ttu-id="e94f0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e94f0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e94f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e94f0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="e94f0-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="e94f0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e94f0-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e94f0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="e94f0-110">通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。</span><span class="sxs-lookup"><span data-stu-id="e94f0-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="e94f0-111">如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。</span><span class="sxs-lookup"><span data-stu-id="e94f0-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="e94f0-112">此操作将阻止在组织的设备上读取、写入或执行该操作。</span><span class="sxs-lookup"><span data-stu-id="e94f0-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="e94f0-113">有三种方法可以创建文件指示器：</span><span class="sxs-lookup"><span data-stu-id="e94f0-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="e94f0-114">通过设置页面创建指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="e94f0-115">通过使用文件详细信息页面中的"添加指示器"按钮创建上下文指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="e94f0-116">通过指示器 [API 创建指示器](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e94f0-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e94f0-117">开始之前</span><span class="sxs-lookup"><span data-stu-id="e94f0-117">Before you begin</span></span>

<span data-ttu-id="e94f0-118">在创建文件指示器之前，了解以下先决条件很重要：</span><span class="sxs-lookup"><span data-stu-id="e94f0-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="e94f0-119">如果你的组织在活动模式下使用 **Microsoft Defender 防病毒 (，) 启用** 基于云的保护，则此功能 **可用**。</span><span class="sxs-lookup"><span data-stu-id="e94f0-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="e94f0-120">有关详细信息，请参阅 [管理基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="e94f0-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="e94f0-121">反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e94f0-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="e94f0-122">请参阅 [每月平台和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="e94f0-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="e94f0-123">在具有 Windows 10 版本 1703 或更高版本、Windows Server 2016 2019 的设备上受支持。</span><span class="sxs-lookup"><span data-stu-id="e94f0-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="e94f0-124">若要开始阻止文件，首先需要打开"阻止或允许 ["设置。](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="e94f0-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="e94f0-125">此功能旨在防止从 web (可疑恶意软件) 潜在恶意文件。</span><span class="sxs-lookup"><span data-stu-id="e94f0-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="e94f0-126">它目前支持可移植的可执行 (PE) 文件，包括.exe和.dll文件。</span><span class="sxs-lookup"><span data-stu-id="e94f0-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="e94f0-127">覆盖范围将随着时间的推移而延长。</span><span class="sxs-lookup"><span data-stu-id="e94f0-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="e94f0-128">从设置页创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="e94f0-129">在导航窗格中，选择 **"设置 >标记"。**</span><span class="sxs-lookup"><span data-stu-id="e94f0-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="e94f0-130">选择" **文件哈希"**   选项卡。</span><span class="sxs-lookup"><span data-stu-id="e94f0-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="e94f0-131">选择 **"添加指示器"。**</span><span class="sxs-lookup"><span data-stu-id="e94f0-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="e94f0-132">指定以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="e94f0-132">Specify the following details:</span></span>
    - <span data-ttu-id="e94f0-133">Indicator - 指定实体详细信息并定义指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="e94f0-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="e94f0-134">操作 - 指定要采取的操作并提供说明。</span><span class="sxs-lookup"><span data-stu-id="e94f0-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="e94f0-135">范围 - 定义设备组的范围。</span><span class="sxs-lookup"><span data-stu-id="e94f0-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="e94f0-136">查看"摘要"选项卡中的详细信息，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="e94f0-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="e94f0-137">从文件详细信息页面创建上下文指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="e94f0-138">对文件执行响应 [操作的选项](respond-file-alerts.md)之一是   添加文件指示器。</span><span class="sxs-lookup"><span data-stu-id="e94f0-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="e94f0-139">为文件添加指示器哈希时，可以选择引发警报，并阻止组织中设备尝试运行该文件。</span><span class="sxs-lookup"><span data-stu-id="e94f0-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="e94f0-140">由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。</span><span class="sxs-lookup"><span data-stu-id="e94f0-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="e94f0-141">通常，文件块将在几分钟内强制执行和删除，但可能需要 30 分钟以上的时间。</span><span class="sxs-lookup"><span data-stu-id="e94f0-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="e94f0-142">如果存在冲突的文件指示器策略，则应用更安全的策略的强制策略。</span><span class="sxs-lookup"><span data-stu-id="e94f0-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="e94f0-143">例如，如果两种哈希类型都定义了相同的文件，则 SHA-256 文件哈希指示器策略优先于 MD5 文件哈希指示器策略。</span><span class="sxs-lookup"><span data-stu-id="e94f0-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="e94f0-144">如果禁用 EnableFileHashComputation 组策略，则文件 IoC 的阻止准确度将降低。</span><span class="sxs-lookup"><span data-stu-id="e94f0-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="e94f0-145">但是，启用 EnableFileHashComputation 可能会影响设备性能。</span><span class="sxs-lookup"><span data-stu-id="e94f0-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="e94f0-146">例如，将大文件从网络共享复制到本地设备（尤其是通过 VPN 连接）可能会影响设备性能。</span><span class="sxs-lookup"><span data-stu-id="e94f0-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="e94f0-147">有关 EnableFileHashComputation 组策略详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="e94f0-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="e94f0-148">策略冲突处理</span><span class="sxs-lookup"><span data-stu-id="e94f0-148">Policy conflict handling</span></span>  

<span data-ttu-id="e94f0-149">证书和文件 IoC 策略处理冲突将遵循以下顺序：</span><span class="sxs-lookup"><span data-stu-id="e94f0-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="e94f0-150">如果应用程序控制和 AppLocker Windows Defender策略不允许该文件，**则阻止**</span><span class="sxs-lookup"><span data-stu-id="e94f0-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="e94f0-151">否则，如果 Defender 防病毒排除允许该文件 **，则允许**</span><span class="sxs-lookup"><span data-stu-id="e94f0-151">Else if the file is allowed by the Defender Anti-Virus Exclusion, then **Allow**</span></span>

- <span data-ttu-id="e94f0-152">否则，如果阻止或警告文件 IoC 阻止或警告文件，则 **阻止/警告**</span><span class="sxs-lookup"><span data-stu-id="e94f0-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="e94f0-153">否则，如果允许文件 IOC 策略允许该文件 **，则允许**</span><span class="sxs-lookup"><span data-stu-id="e94f0-153">Else if the file is allowed by an allow file IOC policy, then **Allow**</span></span>

- <span data-ttu-id="e94f0-154">否则，如果该文件被 ASR 规则、CFA、AV、SmartScreen 阻止，则 **阻止**</span><span class="sxs-lookup"><span data-stu-id="e94f0-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="e94f0-155">Else **Allow** (AppLocker 策略Windows Defender应用程序控制&，任何 IoC 规则都不适用于它) </span><span class="sxs-lookup"><span data-stu-id="e94f0-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="e94f0-156">如果存在具有相同强制类型和目标的冲突文件 IoC 策略，则更安全的文件 ioC 策略 (这意味着将应用) 哈希时间更长。</span><span class="sxs-lookup"><span data-stu-id="e94f0-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="e94f0-157">例如，如果 SHA-256 文件哈希 IoC 策略定义同一个文件，它将在 MD5 文件哈希 IoC 策略中获胜。</span><span class="sxs-lookup"><span data-stu-id="e94f0-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="e94f0-158">请注意，危险和漏洞管理阻止易受攻击的应用程序功能使用文件 IoC 进行强制执行，并且将遵循上述冲突处理顺序。</span><span class="sxs-lookup"><span data-stu-id="e94f0-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="e94f0-159">示例</span><span class="sxs-lookup"><span data-stu-id="e94f0-159">Examples</span></span>

|<span data-ttu-id="e94f0-160">组件</span><span class="sxs-lookup"><span data-stu-id="e94f0-160">Component</span></span> |<span data-ttu-id="e94f0-161">组件强制</span><span class="sxs-lookup"><span data-stu-id="e94f0-161">Component enforcement</span></span> |<span data-ttu-id="e94f0-162">文件指示器操作</span><span class="sxs-lookup"><span data-stu-id="e94f0-162">File indicator Action</span></span> |<span data-ttu-id="e94f0-163">结果</span><span class="sxs-lookup"><span data-stu-id="e94f0-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="e94f0-164">攻击面减少文件路径排除</span><span class="sxs-lookup"><span data-stu-id="e94f0-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="e94f0-165">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-165">Allow</span></span> |<span data-ttu-id="e94f0-166">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-166">Block</span></span> |<span data-ttu-id="e94f0-167">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-167">Block</span></span>
|<span data-ttu-id="e94f0-168">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="e94f0-168">Attack surface reduction rule</span></span> |<span data-ttu-id="e94f0-169">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-169">Block</span></span> |<span data-ttu-id="e94f0-170">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-170">Allow</span></span> |<span data-ttu-id="e94f0-171">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-171">Allow</span></span>
|<span data-ttu-id="e94f0-172">Windows Defender 应用程序控制</span><span class="sxs-lookup"><span data-stu-id="e94f0-172">Windows Defender Application Control</span></span> |<span data-ttu-id="e94f0-173">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-173">Allow</span></span> |<span data-ttu-id="e94f0-174">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-174">Block</span></span> |<span data-ttu-id="e94f0-175">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-175">Allow</span></span> |
|<span data-ttu-id="e94f0-176">Windows Defender 应用程序控制</span><span class="sxs-lookup"><span data-stu-id="e94f0-176">Windows Defender Application Control</span></span> |<span data-ttu-id="e94f0-177">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-177">Block</span></span> |<span data-ttu-id="e94f0-178">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-178">Allow</span></span> |<span data-ttu-id="e94f0-179">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-179">Block</span></span>
|<span data-ttu-id="e94f0-180">Microsoft Defender 防病毒排除</span><span class="sxs-lookup"><span data-stu-id="e94f0-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="e94f0-181">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-181">Allow</span></span> |<span data-ttu-id="e94f0-182">阻止</span><span class="sxs-lookup"><span data-stu-id="e94f0-182">Block</span></span> |<span data-ttu-id="e94f0-183">允许</span><span class="sxs-lookup"><span data-stu-id="e94f0-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="e94f0-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e94f0-184">See also</span></span>

- [<span data-ttu-id="e94f0-185">创建指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="e94f0-186">创建 IP 和 URL/域指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="e94f0-187">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="e94f0-188">管理指示器</span><span class="sxs-lookup"><span data-stu-id="e94f0-188">Manage indicators</span></span>](indicator-manage.md)
