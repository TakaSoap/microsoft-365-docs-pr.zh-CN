---
title: 设置适用于 Linux 的 Microsoft Defender ATP 的首选项
ms.reviewer: ''
description: 介绍如何在企业中为 Linux 配置 Microsoft Defender ATP。
keywords: microsoft， defender， atp， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8595bae216911350d3f18fcceef729ef020a424
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408161"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a5d28-104">设置适用于 Linux 的 Microsoft Defender 终结点的首选项</span><span class="sxs-lookup"><span data-stu-id="a5d28-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a5d28-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a5d28-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5d28-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5d28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5d28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5d28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5d28-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a5d28-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a5d28-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a5d28-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="a5d28-110">本主题包含有关如何在企业环境中为适用于 Linux 的 Defender 终结点设置首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="a5d28-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="a5d28-111">如果你有兴趣从命令行在设备上配置产品，请参阅 [资源](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="a5d28-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="a5d28-112">在企业环境中，可通过配置文件管理适用于 Linux 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="a5d28-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="a5d28-113">此配置文件从你选择的管理工具部署。</span><span class="sxs-lookup"><span data-stu-id="a5d28-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="a5d28-114">企业管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="a5d28-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="a5d28-115">换句话说，企业中的用户不能更改通过此配置文件设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="a5d28-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="a5d28-116">本文介绍此配置文件 (包括可用于开始使用配置文件的建议) 以及如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="a5d28-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="a5d28-117">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="a5d28-117">Configuration profile structure</span></span>

<span data-ttu-id="a5d28-118">配置文件是一个 .json 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="a5d28-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="a5d28-119">值可以很简单，如数字值，也可以复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="a5d28-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="a5d28-120">通常，你将使用配置管理工具在 位置推送名称 ```mdatp_managed.json``` 为 的文件 ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="a5d28-121">配置文件的顶层包括产品范围的首选项和产品子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="a5d28-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="a5d28-122">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="a5d28-122">Antivirus engine preferences</span></span>

<span data-ttu-id="a5d28-123">配置文件 *的 antivirusEngine* 部分用于管理产品的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="a5d28-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-124">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-124">**Key**</span></span> | <span data-ttu-id="a5d28-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="a5d28-125">antivirusEngine</span></span> |
| <span data-ttu-id="a5d28-126">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-126">**Data type**</span></span> | <span data-ttu-id="a5d28-127">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="a5d28-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a5d28-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-128">**Comments**</span></span> | <span data-ttu-id="a5d28-129">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="a5d28-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="a5d28-130">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="a5d28-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="a5d28-131">确定是否在启用实时 (时扫描) 文件。</span><span class="sxs-lookup"><span data-stu-id="a5d28-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-132">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-132">**Key**</span></span> | <span data-ttu-id="a5d28-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="a5d28-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="a5d28-134">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-134">**Data type**</span></span> | <span data-ttu-id="a5d28-135">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5d28-135">Boolean</span></span> |
| <span data-ttu-id="a5d28-136">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-136">**Possible values**</span></span> | <span data-ttu-id="a5d28-137">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="a5d28-137">true (default)</span></span> <br/> <span data-ttu-id="a5d28-138">false</span><span class="sxs-lookup"><span data-stu-id="a5d28-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="a5d28-139">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="a5d28-139">Enable / disable passive mode</span></span>

<span data-ttu-id="a5d28-140">确定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="a5d28-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="a5d28-141">在被动模式下：</span><span class="sxs-lookup"><span data-stu-id="a5d28-141">In passive mode:</span></span>
- <span data-ttu-id="a5d28-142">实时保护已关闭。</span><span class="sxs-lookup"><span data-stu-id="a5d28-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="a5d28-143">按需扫描已打开。</span><span class="sxs-lookup"><span data-stu-id="a5d28-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="a5d28-144">自动威胁修正已关闭。</span><span class="sxs-lookup"><span data-stu-id="a5d28-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="a5d28-145">安全智能更新已打开。</span><span class="sxs-lookup"><span data-stu-id="a5d28-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="a5d28-146">状态菜单图标处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="a5d28-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-147">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-147">**Key**</span></span> | <span data-ttu-id="a5d28-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="a5d28-148">passiveMode</span></span> |
| <span data-ttu-id="a5d28-149">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-149">**Data type**</span></span> | <span data-ttu-id="a5d28-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5d28-150">Boolean</span></span> |
| <span data-ttu-id="a5d28-151">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-151">**Possible values**</span></span> | <span data-ttu-id="a5d28-152">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="a5d28-152">false (default)</span></span> <br/> <span data-ttu-id="a5d28-153">true</span><span class="sxs-lookup"><span data-stu-id="a5d28-153">true</span></span> |
| <span data-ttu-id="a5d28-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-154">**Comments**</span></span> | <span data-ttu-id="a5d28-155">适用于终结点版本 100.67.60 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5d28-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="a5d28-156">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="a5d28-156">Exclusion merge policy</span></span>

<span data-ttu-id="a5d28-157">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="a5d28-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="a5d28-158">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="a5d28-159">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="a5d28-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-160">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-160">**Key**</span></span> | <span data-ttu-id="a5d28-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="a5d28-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="a5d28-162">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-162">**Data type**</span></span> | <span data-ttu-id="a5d28-163">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-163">String</span></span> |
| <span data-ttu-id="a5d28-164">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-164">**Possible values**</span></span> | <span data-ttu-id="a5d28-165">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="a5d28-165">merge (default)</span></span> <br/> <span data-ttu-id="a5d28-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="a5d28-166">admin_only</span></span> |
| <span data-ttu-id="a5d28-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-167">**Comments**</span></span> | <span data-ttu-id="a5d28-168">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5d28-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="a5d28-169">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="a5d28-169">Scan exclusions</span></span>

<span data-ttu-id="a5d28-170">从扫描中排除的实体。</span><span class="sxs-lookup"><span data-stu-id="a5d28-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="a5d28-171">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="a5d28-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-172">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-172">**Key**</span></span> | <span data-ttu-id="a5d28-173">排除项</span><span class="sxs-lookup"><span data-stu-id="a5d28-173">exclusions</span></span> |
| <span data-ttu-id="a5d28-174">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-174">**Data type**</span></span> | <span data-ttu-id="a5d28-175">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="a5d28-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a5d28-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-176">**Comments**</span></span> | <span data-ttu-id="a5d28-177">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="a5d28-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="a5d28-178">**排除类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-178">**Type of exclusion**</span></span>

<span data-ttu-id="a5d28-179">指定从扫描中排除的内容的类型。</span><span class="sxs-lookup"><span data-stu-id="a5d28-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-180">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-180">**Key**</span></span> | <span data-ttu-id="a5d28-181">$type</span><span class="sxs-lookup"><span data-stu-id="a5d28-181">$type</span></span> |
| <span data-ttu-id="a5d28-182">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-182">**Data type**</span></span> | <span data-ttu-id="a5d28-183">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-183">String</span></span> |
| <span data-ttu-id="a5d28-184">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-184">**Possible values**</span></span> | <span data-ttu-id="a5d28-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="a5d28-185">excludedPath</span></span> <br/> <span data-ttu-id="a5d28-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="a5d28-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="a5d28-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="a5d28-187">excludedFileName</span></span> |
|||

<span data-ttu-id="a5d28-188">**排除内容的路径**</span><span class="sxs-lookup"><span data-stu-id="a5d28-188">**Path to excluded content**</span></span>

<span data-ttu-id="a5d28-189">用于按完整文件路径从扫描中排除内容。</span><span class="sxs-lookup"><span data-stu-id="a5d28-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-190">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-190">**Key**</span></span> | <span data-ttu-id="a5d28-191">path</span><span class="sxs-lookup"><span data-stu-id="a5d28-191">path</span></span> |
| <span data-ttu-id="a5d28-192">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-192">**Data type**</span></span> | <span data-ttu-id="a5d28-193">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-193">String</span></span> |
| <span data-ttu-id="a5d28-194">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-194">**Possible values**</span></span> | <span data-ttu-id="a5d28-195">有效路径</span><span class="sxs-lookup"><span data-stu-id="a5d28-195">valid paths</span></span> |
| <span data-ttu-id="a5d28-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-196">**Comments**</span></span> | <span data-ttu-id="a5d28-197">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="a5d28-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="a5d28-198">**文件 (目录的路径)**</span><span class="sxs-lookup"><span data-stu-id="a5d28-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="a5d28-199">指示 path *属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="a5d28-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="a5d28-200">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-200">**Key**</span></span> | <span data-ttu-id="a5d28-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="a5d28-201">isDirectory</span></span> |
| <span data-ttu-id="a5d28-202">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-202">**Data type**</span></span> | <span data-ttu-id="a5d28-203">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5d28-203">Boolean</span></span> |
| <span data-ttu-id="a5d28-204">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-204">**Possible values**</span></span> | <span data-ttu-id="a5d28-205">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="a5d28-205">false (default)</span></span> <br/> <span data-ttu-id="a5d28-206">true</span><span class="sxs-lookup"><span data-stu-id="a5d28-206">true</span></span> |
| <span data-ttu-id="a5d28-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-207">**Comments**</span></span> | <span data-ttu-id="a5d28-208">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="a5d28-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="a5d28-209">**从扫描中排除的文件扩展名**</span><span class="sxs-lookup"><span data-stu-id="a5d28-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="a5d28-210">用于按文件扩展名从扫描中排除内容。</span><span class="sxs-lookup"><span data-stu-id="a5d28-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-211">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-211">**Key**</span></span> | <span data-ttu-id="a5d28-212">extension</span><span class="sxs-lookup"><span data-stu-id="a5d28-212">extension</span></span> |
| <span data-ttu-id="a5d28-213">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-213">**Data type**</span></span> | <span data-ttu-id="a5d28-214">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-214">String</span></span> |
| <span data-ttu-id="a5d28-215">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-215">**Possible values**</span></span> | <span data-ttu-id="a5d28-216">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="a5d28-216">valid file extensions</span></span> |
| <span data-ttu-id="a5d28-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-217">**Comments**</span></span> | <span data-ttu-id="a5d28-218">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="a5d28-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="a5d28-219">**从扫描中排除的进程**</span><span class="sxs-lookup"><span data-stu-id="a5d28-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="a5d28-220">指定从扫描中排除所有文件活动的进程。</span><span class="sxs-lookup"><span data-stu-id="a5d28-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="a5d28-221">可以通过进程的名称或名称来指定 (例如，) 或完整 (`cat` 例如 `/bin/cat` ，) 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-222">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-222">**Key**</span></span> | <span data-ttu-id="a5d28-223">name</span><span class="sxs-lookup"><span data-stu-id="a5d28-223">name</span></span> |
| <span data-ttu-id="a5d28-224">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-224">**Data type**</span></span> | <span data-ttu-id="a5d28-225">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-225">String</span></span> |
| <span data-ttu-id="a5d28-226">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-226">**Possible values**</span></span> | <span data-ttu-id="a5d28-227">任何字符串</span><span class="sxs-lookup"><span data-stu-id="a5d28-227">any string</span></span> |
| <span data-ttu-id="a5d28-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-228">**Comments**</span></span> | <span data-ttu-id="a5d28-229">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="a5d28-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="a5d28-230">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="a5d28-230">Allowed threats</span></span>

<span data-ttu-id="a5d28-231">威胁列表 (名称) 产品未阻止但允许运行的威胁列表。</span><span class="sxs-lookup"><span data-stu-id="a5d28-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-232">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-232">**Key**</span></span> | <span data-ttu-id="a5d28-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="a5d28-233">allowedThreats</span></span> |
| <span data-ttu-id="a5d28-234">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-234">**Data type**</span></span> | <span data-ttu-id="a5d28-235">字符串数组</span><span class="sxs-lookup"><span data-stu-id="a5d28-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="a5d28-236">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="a5d28-236">Disallowed threat actions</span></span>

<span data-ttu-id="a5d28-237">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="a5d28-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="a5d28-238">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="a5d28-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-239">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-239">**Key**</span></span> | <span data-ttu-id="a5d28-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="a5d28-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="a5d28-241">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-241">**Data type**</span></span> | <span data-ttu-id="a5d28-242">字符串数组</span><span class="sxs-lookup"><span data-stu-id="a5d28-242">Array of strings</span></span> |
| <span data-ttu-id="a5d28-243">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-243">**Possible values**</span></span> | <span data-ttu-id="a5d28-244">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="a5d28-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="a5d28-245">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="a5d28-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="a5d28-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-246">**Comments**</span></span> | <span data-ttu-id="a5d28-247">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5d28-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="a5d28-248">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="a5d28-248">Threat type settings</span></span>

<span data-ttu-id="a5d28-249">防病毒 *引擎中的 threatTypeSettings* 首选项用于控制产品如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="a5d28-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-250">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-250">**Key**</span></span> | <span data-ttu-id="a5d28-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="a5d28-251">threatTypeSettings</span></span> |
| <span data-ttu-id="a5d28-252">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-252">**Data type**</span></span> | <span data-ttu-id="a5d28-253">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="a5d28-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a5d28-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-254">**Comments**</span></span> | <span data-ttu-id="a5d28-255">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="a5d28-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="a5d28-256">**威胁类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-256">**Threat type**</span></span>

<span data-ttu-id="a5d28-257">配置其行为的威胁类型。</span><span class="sxs-lookup"><span data-stu-id="a5d28-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-258">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-258">**Key**</span></span> | <span data-ttu-id="a5d28-259">注册表项</span><span class="sxs-lookup"><span data-stu-id="a5d28-259">key</span></span> |
| <span data-ttu-id="a5d28-260">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-260">**Data type**</span></span> | <span data-ttu-id="a5d28-261">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-261">String</span></span> |
| <span data-ttu-id="a5d28-262">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-262">**Possible values**</span></span> | <span data-ttu-id="a5d28-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="a5d28-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="a5d28-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="a5d28-264">archive_bomb</span></span> |
|||

<span data-ttu-id="a5d28-265">**要采取的措施**</span><span class="sxs-lookup"><span data-stu-id="a5d28-265">**Action to take**</span></span>

<span data-ttu-id="a5d28-266">遇到上一节中指定的类型的威胁时要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="a5d28-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="a5d28-267">可以是：</span><span class="sxs-lookup"><span data-stu-id="a5d28-267">Can be:</span></span>

- <span data-ttu-id="a5d28-268">**审核**：设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="a5d28-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="a5d28-269">**阻止**：设备受到此类型威胁的保护，并且你将在安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="a5d28-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="a5d28-270">**关闭**：设备不受此类型威胁的保护，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="a5d28-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-271">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-271">**Key**</span></span> | <span data-ttu-id="a5d28-272">值</span><span class="sxs-lookup"><span data-stu-id="a5d28-272">value</span></span> |
| <span data-ttu-id="a5d28-273">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-273">**Data type**</span></span> | <span data-ttu-id="a5d28-274">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-274">String</span></span> |
| <span data-ttu-id="a5d28-275">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-275">**Possible values**</span></span> | <span data-ttu-id="a5d28-276">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="a5d28-276">audit (default)</span></span> <br/> <span data-ttu-id="a5d28-277">block</span><span class="sxs-lookup"><span data-stu-id="a5d28-277">block</span></span> <br/> <span data-ttu-id="a5d28-278">off</span><span class="sxs-lookup"><span data-stu-id="a5d28-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="a5d28-279">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="a5d28-279">Threat type settings merge policy</span></span>

<span data-ttu-id="a5d28-280">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="a5d28-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="a5d28-281">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="a5d28-282">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="a5d28-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-283">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-283">**Key**</span></span> | <span data-ttu-id="a5d28-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="a5d28-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="a5d28-285">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-285">**Data type**</span></span> | <span data-ttu-id="a5d28-286">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-286">String</span></span> |
| <span data-ttu-id="a5d28-287">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-287">**Possible values**</span></span> | <span data-ttu-id="a5d28-288">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="a5d28-288">merge (default)</span></span> <br/> <span data-ttu-id="a5d28-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="a5d28-289">admin_only</span></span> |
| <span data-ttu-id="a5d28-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-290">**Comments**</span></span> | <span data-ttu-id="a5d28-291">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5d28-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="a5d28-292">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="a5d28-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="a5d28-293">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="a5d28-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="a5d28-294">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="a5d28-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="a5d28-295">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="a5d28-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-296">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-296">**Key**</span></span> | <span data-ttu-id="a5d28-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="a5d28-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="a5d28-298">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-298">**Data type**</span></span> | <span data-ttu-id="a5d28-299">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-299">String</span></span> |
| <span data-ttu-id="a5d28-300">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-300">**Possible values**</span></span> | <span data-ttu-id="a5d28-301">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-301">90 (default).</span></span> <span data-ttu-id="a5d28-302">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="a5d28-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="a5d28-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-303">**Comments**</span></span> | <span data-ttu-id="a5d28-304">适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5d28-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="a5d28-305">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="a5d28-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="a5d28-306">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="a5d28-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="a5d28-307">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="a5d28-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-308">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-308">**Key**</span></span> | <span data-ttu-id="a5d28-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="a5d28-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="a5d28-310">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-310">**Data type**</span></span> | <span data-ttu-id="a5d28-311">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-311">String</span></span> |
| <span data-ttu-id="a5d28-312">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-312">**Possible values**</span></span> | <span data-ttu-id="a5d28-313">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-313">10000 (default).</span></span> <span data-ttu-id="a5d28-314">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="a5d28-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="a5d28-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-315">**Comments**</span></span> | <span data-ttu-id="a5d28-316">适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5d28-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="a5d28-317">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="a5d28-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="a5d28-318">配置文件 *中的 cloudService* 条目用于配置产品的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="a5d28-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-319">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-319">**Key**</span></span> | <span data-ttu-id="a5d28-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="a5d28-320">cloudService</span></span> |
| <span data-ttu-id="a5d28-321">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-321">**Data type**</span></span> | <span data-ttu-id="a5d28-322">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="a5d28-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a5d28-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a5d28-323">**Comments**</span></span> | <span data-ttu-id="a5d28-324">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="a5d28-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="a5d28-325">启用/禁用云提供的保护</span><span class="sxs-lookup"><span data-stu-id="a5d28-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="a5d28-326">确定是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="a5d28-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="a5d28-327">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="a5d28-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-328">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-328">**Key**</span></span> | <span data-ttu-id="a5d28-329">enabled</span><span class="sxs-lookup"><span data-stu-id="a5d28-329">enabled</span></span> |
| <span data-ttu-id="a5d28-330">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-330">**Data type**</span></span> | <span data-ttu-id="a5d28-331">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5d28-331">Boolean</span></span> |
| <span data-ttu-id="a5d28-332">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-332">**Possible values**</span></span> | <span data-ttu-id="a5d28-333">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="a5d28-333">true (default)</span></span> <br/> <span data-ttu-id="a5d28-334">false</span><span class="sxs-lookup"><span data-stu-id="a5d28-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="a5d28-335">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="a5d28-335">Diagnostic collection level</span></span>

<span data-ttu-id="a5d28-336">诊断数据用于使 Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="a5d28-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="a5d28-337">此设置确定产品发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="a5d28-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-338">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-338">**Key**</span></span> | <span data-ttu-id="a5d28-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="a5d28-339">diagnosticLevel</span></span> |
| <span data-ttu-id="a5d28-340">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-340">**Data type**</span></span> | <span data-ttu-id="a5d28-341">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-341">String</span></span> |
| <span data-ttu-id="a5d28-342">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-342">**Possible values**</span></span> | <span data-ttu-id="a5d28-343">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="a5d28-343">optional (default)</span></span> <br/> <span data-ttu-id="a5d28-344">必需</span><span class="sxs-lookup"><span data-stu-id="a5d28-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="a5d28-345">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="a5d28-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="a5d28-346">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a5d28-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="a5d28-347">有三个级别用于控制示例提交：</span><span class="sxs-lookup"><span data-stu-id="a5d28-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="a5d28-348">**无**：不会向 Microsoft 提交任何可疑样本。</span><span class="sxs-lookup"><span data-stu-id="a5d28-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="a5d28-349">**安全**：仅自动提交不包含个人身份信息 (PII) 的可疑示例。</span><span class="sxs-lookup"><span data-stu-id="a5d28-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="a5d28-350">这是此设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="a5d28-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="a5d28-351">**全部**：所有可疑示例都提交到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a5d28-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-352">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-352">**Key**</span></span> | <span data-ttu-id="a5d28-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="a5d28-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="a5d28-354">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-354">**Data type**</span></span> | <span data-ttu-id="a5d28-355">String</span><span class="sxs-lookup"><span data-stu-id="a5d28-355">String</span></span> |
| <span data-ttu-id="a5d28-356">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-356">**Possible values**</span></span> | <span data-ttu-id="a5d28-357">无</span><span class="sxs-lookup"><span data-stu-id="a5d28-357">none</span></span> <br/> <span data-ttu-id="a5d28-358">安全 (默认) </span><span class="sxs-lookup"><span data-stu-id="a5d28-358">safe (default)</span></span> <br/> <span data-ttu-id="a5d28-359">all</span><span class="sxs-lookup"><span data-stu-id="a5d28-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="a5d28-360">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="a5d28-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="a5d28-361">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="a5d28-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="a5d28-362">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="a5d28-362">**Key**</span></span> | <span data-ttu-id="a5d28-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="a5d28-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="a5d28-364">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a5d28-364">**Data type**</span></span> | <span data-ttu-id="a5d28-365">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5d28-365">Boolean</span></span> |
| <span data-ttu-id="a5d28-366">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a5d28-366">**Possible values**</span></span> | <span data-ttu-id="a5d28-367">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="a5d28-367">true (default)</span></span> <br/> <span data-ttu-id="a5d28-368">false</span><span class="sxs-lookup"><span data-stu-id="a5d28-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="a5d28-369">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="a5d28-369">Recommended configuration profile</span></span>

<span data-ttu-id="a5d28-370">若要开始，我们建议你的企业采用以下配置文件，以利用 Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="a5d28-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="a5d28-371">以下配置文件将：</span><span class="sxs-lookup"><span data-stu-id="a5d28-371">The following configuration profile will:</span></span>

- <span data-ttu-id="a5d28-372">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="a5d28-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="a5d28-373">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="a5d28-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="a5d28-374">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="a5d28-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="a5d28-375">**存档 (** 高压缩率的文件) 审核到产品日志</span><span class="sxs-lookup"><span data-stu-id="a5d28-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="a5d28-376">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="a5d28-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="a5d28-377">启用云保护</span><span class="sxs-lookup"><span data-stu-id="a5d28-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="a5d28-378">启用级别的自动示例 `safe` 提交</span><span class="sxs-lookup"><span data-stu-id="a5d28-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="a5d28-379">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="a5d28-379">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="a5d28-380">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="a5d28-380">Full configuration profile example</span></span>

<span data-ttu-id="a5d28-381">以下配置文件包含本文档中所述的所有设置的条目，可用于更高级的方案，您希望对产品进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="a5d28-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="a5d28-382">完整个人资料</span><span class="sxs-lookup"><span data-stu-id="a5d28-382">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="a5d28-383">配置文件验证</span><span class="sxs-lookup"><span data-stu-id="a5d28-383">Configuration profile validation</span></span>

<span data-ttu-id="a5d28-384">配置文件必须是有效的 JSON 格式文件。</span><span class="sxs-lookup"><span data-stu-id="a5d28-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="a5d28-385">有许多工具可用于验证这一点。</span><span class="sxs-lookup"><span data-stu-id="a5d28-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="a5d28-386">例如，如果你已安装 `python` 在设备上：</span><span class="sxs-lookup"><span data-stu-id="a5d28-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="a5d28-387">如果 JSON 格式良好，则上述命令会输出回终端，并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="a5d28-388">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="a5d28-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="a5d28-389">验证文件mdatp_managed.js是否正常工作</span><span class="sxs-lookup"><span data-stu-id="a5d28-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="a5d28-390">若要验证 /etc/opt/microsoft/mdatp/managed/mdatp_managed.json 是否正常工作，应在这些设置旁边看到"[托管]"：</span><span class="sxs-lookup"><span data-stu-id="a5d28-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="a5d28-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="a5d28-391">cloud_enabled</span></span>
- <span data-ttu-id="a5d28-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="a5d28-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="a5d28-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="a5d28-393">passice_mode_enabled</span></span>
- <span data-ttu-id="a5d28-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="a5d28-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="a5d28-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="a5d28-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="a5d28-396">若要mdatp_managed.js，无需重新启动 wdavdaemon。</span><span class="sxs-lookup"><span data-stu-id="a5d28-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="a5d28-397">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="a5d28-397">Configuration profile deployment</span></span>

<span data-ttu-id="a5d28-398">为企业生成配置文件后，可以通过企业使用的管理工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="a5d28-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="a5d28-399">适用于 Linux 的终结点的 Defender 从 */etc/opt/microsoft/mdatp/managed/mdatp_managed.js文件读取托管* 配置。</span><span class="sxs-lookup"><span data-stu-id="a5d28-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
