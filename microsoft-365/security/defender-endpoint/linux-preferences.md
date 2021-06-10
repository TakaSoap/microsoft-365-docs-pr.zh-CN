---
title: 在 Linux 上设置适用于终结点的 Microsoft Defender 的首选项
ms.reviewer: ''
description: 介绍如何在企业版 Linux 上为终结点配置 Microsoft Defender。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 00f6bdac66ae286bf55a875599f7097b14b06cb3
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861547"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="95167-104">在 Linux 上设置适用于终结点的 Microsoft Defender 的首选项</span><span class="sxs-lookup"><span data-stu-id="95167-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95167-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="95167-105">**Applies to:**</span></span>
- [<span data-ttu-id="95167-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95167-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95167-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95167-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95167-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="95167-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="95167-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="95167-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="95167-110">本主题包含有关如何在企业环境中为 Linux 上的 Defender for Endpoint 设置首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="95167-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="95167-111">如果你有兴趣从命令行在设备上配置产品，请参阅 [资源](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="95167-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="95167-112">在企业环境中，Linux 上的 Defender for Endpoint 可通过配置文件进行管理。</span><span class="sxs-lookup"><span data-stu-id="95167-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="95167-113">此配置文件从你选择的管理工具部署。</span><span class="sxs-lookup"><span data-stu-id="95167-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="95167-114">企业管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="95167-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="95167-115">换句话说，企业中的用户不能更改通过此配置文件设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="95167-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="95167-116">本文介绍此配置文件 (包括可用于开始使用配置文件的建议) 以及如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="95167-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="95167-117">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="95167-117">Configuration profile structure</span></span>

<span data-ttu-id="95167-118">配置文件是一个 .json 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="95167-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="95167-119">值可以很简单，如数字值，也可以复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="95167-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="95167-120">通常，你将使用配置管理工具在 位置推送名称 ```mdatp_managed.json``` 为 的文件 ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="95167-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="95167-121">配置文件的顶层包括产品范围的首选项和产品子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="95167-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="95167-122">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="95167-122">Antivirus engine preferences</span></span>

<span data-ttu-id="95167-123">配置文件 *的 antivirusEngine* 部分用于管理产品的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="95167-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-124">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-124">**Key**</span></span> | <span data-ttu-id="95167-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="95167-125">antivirusEngine</span></span> |
| <span data-ttu-id="95167-126">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-126">**Data type**</span></span> | <span data-ttu-id="95167-127">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="95167-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="95167-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-128">**Comments**</span></span> | <span data-ttu-id="95167-129">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="95167-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="95167-130">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="95167-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="95167-131">确定是否在启用实时 (时扫描) 文件。</span><span class="sxs-lookup"><span data-stu-id="95167-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-132">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-132">**Key**</span></span> | <span data-ttu-id="95167-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="95167-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="95167-134">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-134">**Data type**</span></span> | <span data-ttu-id="95167-135">Boolean</span><span class="sxs-lookup"><span data-stu-id="95167-135">Boolean</span></span> |
| <span data-ttu-id="95167-136">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-136">**Possible values**</span></span> | <span data-ttu-id="95167-137">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="95167-137">true (default)</span></span> <br/> <span data-ttu-id="95167-138">false</span><span class="sxs-lookup"><span data-stu-id="95167-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="95167-139">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="95167-139">Enable / disable passive mode</span></span>

<span data-ttu-id="95167-140">确定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="95167-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="95167-141">在被动模式下：</span><span class="sxs-lookup"><span data-stu-id="95167-141">In passive mode:</span></span>
- <span data-ttu-id="95167-142">实时保护已关闭。</span><span class="sxs-lookup"><span data-stu-id="95167-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="95167-143">按需扫描已打开。</span><span class="sxs-lookup"><span data-stu-id="95167-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="95167-144">自动威胁修正已关闭。</span><span class="sxs-lookup"><span data-stu-id="95167-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="95167-145">安全智能更新已打开。</span><span class="sxs-lookup"><span data-stu-id="95167-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="95167-146">状态菜单图标处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="95167-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-147">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-147">**Key**</span></span> | <span data-ttu-id="95167-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="95167-148">passiveMode</span></span> |
| <span data-ttu-id="95167-149">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-149">**Data type**</span></span> | <span data-ttu-id="95167-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="95167-150">Boolean</span></span> |
| <span data-ttu-id="95167-151">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-151">**Possible values**</span></span> | <span data-ttu-id="95167-152">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="95167-152">false (default)</span></span> <br/> <span data-ttu-id="95167-153">true</span><span class="sxs-lookup"><span data-stu-id="95167-153">true</span></span> |
| <span data-ttu-id="95167-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-154">**Comments**</span></span> | <span data-ttu-id="95167-155">适用于终结点版本 100.67.60 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="95167-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="95167-156">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="95167-156">Exclusion merge policy</span></span>

<span data-ttu-id="95167-157">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="95167-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="95167-158">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="95167-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="95167-159">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="95167-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-160">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-160">**Key**</span></span> | <span data-ttu-id="95167-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="95167-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="95167-162">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-162">**Data type**</span></span> | <span data-ttu-id="95167-163">String</span><span class="sxs-lookup"><span data-stu-id="95167-163">String</span></span> |
| <span data-ttu-id="95167-164">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-164">**Possible values**</span></span> | <span data-ttu-id="95167-165">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="95167-165">merge (default)</span></span> <br/> <span data-ttu-id="95167-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="95167-166">admin_only</span></span> |
| <span data-ttu-id="95167-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-167">**Comments**</span></span> | <span data-ttu-id="95167-168">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="95167-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="95167-169">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="95167-169">Scan exclusions</span></span>

<span data-ttu-id="95167-170">从扫描中排除的实体。</span><span class="sxs-lookup"><span data-stu-id="95167-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="95167-171">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="95167-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="95167-172"> (排除项指定为项目数组，则管理员可以按任意顺序指定所需数量的元素) </span><span class="sxs-lookup"><span data-stu-id="95167-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-173">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-173">**Key**</span></span> | <span data-ttu-id="95167-174">排除项</span><span class="sxs-lookup"><span data-stu-id="95167-174">exclusions</span></span> |
| <span data-ttu-id="95167-175">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-175">**Data type**</span></span> | <span data-ttu-id="95167-176">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="95167-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="95167-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-177">**Comments**</span></span> | <span data-ttu-id="95167-178">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="95167-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="95167-179">**排除类型**</span><span class="sxs-lookup"><span data-stu-id="95167-179">**Type of exclusion**</span></span>

<span data-ttu-id="95167-180">指定从扫描中排除的内容的类型。</span><span class="sxs-lookup"><span data-stu-id="95167-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-181">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-181">**Key**</span></span> | <span data-ttu-id="95167-182">$type</span><span class="sxs-lookup"><span data-stu-id="95167-182">$type</span></span> |
| <span data-ttu-id="95167-183">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-183">**Data type**</span></span> | <span data-ttu-id="95167-184">String</span><span class="sxs-lookup"><span data-stu-id="95167-184">String</span></span> |
| <span data-ttu-id="95167-185">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-185">**Possible values**</span></span> | <span data-ttu-id="95167-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="95167-186">excludedPath</span></span> <br/> <span data-ttu-id="95167-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="95167-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="95167-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="95167-188">excludedFileName</span></span> |
|||

<span data-ttu-id="95167-189">**排除内容的路径**</span><span class="sxs-lookup"><span data-stu-id="95167-189">**Path to excluded content**</span></span>

<span data-ttu-id="95167-190">用于按完整文件路径从扫描中排除内容。</span><span class="sxs-lookup"><span data-stu-id="95167-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-191">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-191">**Key**</span></span> | <span data-ttu-id="95167-192">path</span><span class="sxs-lookup"><span data-stu-id="95167-192">path</span></span> |
| <span data-ttu-id="95167-193">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-193">**Data type**</span></span> | <span data-ttu-id="95167-194">String</span><span class="sxs-lookup"><span data-stu-id="95167-194">String</span></span> |
| <span data-ttu-id="95167-195">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-195">**Possible values**</span></span> | <span data-ttu-id="95167-196">有效路径</span><span class="sxs-lookup"><span data-stu-id="95167-196">valid paths</span></span> |
| <span data-ttu-id="95167-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-197">**Comments**</span></span> | <span data-ttu-id="95167-198">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="95167-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="95167-199">**文件 (目录的路径)**</span><span class="sxs-lookup"><span data-stu-id="95167-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="95167-200">指示 path *属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="95167-200">Indicates if the *path* property refers to a file or directory.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-201">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-201">**Key**</span></span> | <span data-ttu-id="95167-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="95167-202">isDirectory</span></span> |
| <span data-ttu-id="95167-203">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-203">**Data type**</span></span> | <span data-ttu-id="95167-204">Boolean</span><span class="sxs-lookup"><span data-stu-id="95167-204">Boolean</span></span> |
| <span data-ttu-id="95167-205">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-205">**Possible values**</span></span> | <span data-ttu-id="95167-206">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="95167-206">false (default)</span></span> <br/> <span data-ttu-id="95167-207">true</span><span class="sxs-lookup"><span data-stu-id="95167-207">true</span></span> |
| <span data-ttu-id="95167-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-208">**Comments**</span></span> | <span data-ttu-id="95167-209">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="95167-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="95167-210">**从扫描中排除的文件扩展名**</span><span class="sxs-lookup"><span data-stu-id="95167-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="95167-211">用于按文件扩展名从扫描中排除内容。</span><span class="sxs-lookup"><span data-stu-id="95167-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-212">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-212">**Key**</span></span> | <span data-ttu-id="95167-213">extension</span><span class="sxs-lookup"><span data-stu-id="95167-213">extension</span></span> |
| <span data-ttu-id="95167-214">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-214">**Data type**</span></span> | <span data-ttu-id="95167-215">String</span><span class="sxs-lookup"><span data-stu-id="95167-215">String</span></span> |
| <span data-ttu-id="95167-216">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-216">**Possible values**</span></span> | <span data-ttu-id="95167-217">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="95167-217">valid file extensions</span></span> |
| <span data-ttu-id="95167-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-218">**Comments**</span></span> | <span data-ttu-id="95167-219">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="95167-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="95167-220">**从扫描中排除的进程**</span><span class="sxs-lookup"><span data-stu-id="95167-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="95167-221">指定从扫描中排除所有文件活动的进程。</span><span class="sxs-lookup"><span data-stu-id="95167-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="95167-222">可以通过进程的名称或名称来指定 (例如，) 或完整 (`cat` 例如 `/bin/cat` ，) 。</span><span class="sxs-lookup"><span data-stu-id="95167-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-223">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-223">**Key**</span></span> | <span data-ttu-id="95167-224">name</span><span class="sxs-lookup"><span data-stu-id="95167-224">name</span></span> |
| <span data-ttu-id="95167-225">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-225">**Data type**</span></span> | <span data-ttu-id="95167-226">String</span><span class="sxs-lookup"><span data-stu-id="95167-226">String</span></span> |
| <span data-ttu-id="95167-227">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-227">**Possible values**</span></span> | <span data-ttu-id="95167-228">任何字符串</span><span class="sxs-lookup"><span data-stu-id="95167-228">any string</span></span> |
| <span data-ttu-id="95167-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-229">**Comments**</span></span> | <span data-ttu-id="95167-230">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="95167-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="95167-231">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="95167-231">Allowed threats</span></span>

<span data-ttu-id="95167-232">威胁列表 (名称) 产品未阻止但允许运行的威胁列表。</span><span class="sxs-lookup"><span data-stu-id="95167-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-233">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-233">**Key**</span></span> | <span data-ttu-id="95167-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="95167-234">allowedThreats</span></span> |
| <span data-ttu-id="95167-235">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-235">**Data type**</span></span> | <span data-ttu-id="95167-236">字符串数组</span><span class="sxs-lookup"><span data-stu-id="95167-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="95167-237">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="95167-237">Disallowed threat actions</span></span>

<span data-ttu-id="95167-238">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="95167-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="95167-239">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="95167-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-240">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-240">**Key**</span></span> | <span data-ttu-id="95167-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="95167-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="95167-242">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-242">**Data type**</span></span> | <span data-ttu-id="95167-243">字符串数组</span><span class="sxs-lookup"><span data-stu-id="95167-243">Array of strings</span></span> |
| <span data-ttu-id="95167-244">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-244">**Possible values**</span></span> | <span data-ttu-id="95167-245">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="95167-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="95167-246">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="95167-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="95167-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-247">**Comments**</span></span> | <span data-ttu-id="95167-248">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="95167-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="95167-249">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="95167-249">Threat type settings</span></span>

<span data-ttu-id="95167-250">防病毒 *引擎中的 threatTypeSettings* 首选项用于控制产品如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="95167-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-251">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-251">**Key**</span></span> | <span data-ttu-id="95167-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="95167-252">threatTypeSettings</span></span> |
| <span data-ttu-id="95167-253">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-253">**Data type**</span></span> | <span data-ttu-id="95167-254">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="95167-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="95167-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-255">**Comments**</span></span> | <span data-ttu-id="95167-256">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="95167-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="95167-257">**威胁类型**</span><span class="sxs-lookup"><span data-stu-id="95167-257">**Threat type**</span></span>

<span data-ttu-id="95167-258">配置其行为的威胁类型。</span><span class="sxs-lookup"><span data-stu-id="95167-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-259">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-259">**Key**</span></span> | <span data-ttu-id="95167-260">注册表项</span><span class="sxs-lookup"><span data-stu-id="95167-260">key</span></span> |
| <span data-ttu-id="95167-261">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-261">**Data type**</span></span> | <span data-ttu-id="95167-262">String</span><span class="sxs-lookup"><span data-stu-id="95167-262">String</span></span> |
| <span data-ttu-id="95167-263">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-263">**Possible values**</span></span> | <span data-ttu-id="95167-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="95167-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="95167-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="95167-265">archive_bomb</span></span> |
|||

<span data-ttu-id="95167-266">**要采取的措施**</span><span class="sxs-lookup"><span data-stu-id="95167-266">**Action to take**</span></span>

<span data-ttu-id="95167-267">遇到上一节中指定的类型的威胁时要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="95167-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="95167-268">可以是：</span><span class="sxs-lookup"><span data-stu-id="95167-268">Can be:</span></span>

- <span data-ttu-id="95167-269">**审核**：设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="95167-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="95167-270">**阻止**：设备受到此类型威胁的保护，并且你将在安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="95167-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="95167-271">**关闭**：设备不受此类型威胁的保护，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="95167-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-272">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-272">**Key**</span></span> | <span data-ttu-id="95167-273">值</span><span class="sxs-lookup"><span data-stu-id="95167-273">value</span></span> |
| <span data-ttu-id="95167-274">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-274">**Data type**</span></span> | <span data-ttu-id="95167-275">String</span><span class="sxs-lookup"><span data-stu-id="95167-275">String</span></span> |
| <span data-ttu-id="95167-276">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-276">**Possible values**</span></span> | <span data-ttu-id="95167-277">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="95167-277">audit (default)</span></span> <br/> <span data-ttu-id="95167-278">block</span><span class="sxs-lookup"><span data-stu-id="95167-278">block</span></span> <br/> <span data-ttu-id="95167-279">off</span><span class="sxs-lookup"><span data-stu-id="95167-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="95167-280">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="95167-280">Threat type settings merge policy</span></span>

<span data-ttu-id="95167-281">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="95167-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="95167-282">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="95167-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="95167-283">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="95167-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-284">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-284">**Key**</span></span> | <span data-ttu-id="95167-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="95167-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="95167-286">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-286">**Data type**</span></span> | <span data-ttu-id="95167-287">String</span><span class="sxs-lookup"><span data-stu-id="95167-287">String</span></span> |
| <span data-ttu-id="95167-288">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-288">**Possible values**</span></span> | <span data-ttu-id="95167-289">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="95167-289">merge (default)</span></span> <br/> <span data-ttu-id="95167-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="95167-290">admin_only</span></span> |
| <span data-ttu-id="95167-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-291">**Comments**</span></span> | <span data-ttu-id="95167-292">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="95167-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="95167-293">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="95167-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="95167-294">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="95167-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="95167-295">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="95167-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="95167-296">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="95167-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-297">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-297">**Key**</span></span> | <span data-ttu-id="95167-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="95167-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="95167-299">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-299">**Data type**</span></span> | <span data-ttu-id="95167-300">String</span><span class="sxs-lookup"><span data-stu-id="95167-300">String</span></span> |
| <span data-ttu-id="95167-301">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-301">**Possible values**</span></span> | <span data-ttu-id="95167-302">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="95167-302">90 (default).</span></span> <span data-ttu-id="95167-303">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="95167-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="95167-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-304">**Comments**</span></span> | <span data-ttu-id="95167-305">适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="95167-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="95167-306">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="95167-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="95167-307">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="95167-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="95167-308">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="95167-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-309">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-309">**Key**</span></span> | <span data-ttu-id="95167-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="95167-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="95167-311">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-311">**Data type**</span></span> | <span data-ttu-id="95167-312">String</span><span class="sxs-lookup"><span data-stu-id="95167-312">String</span></span> |
| <span data-ttu-id="95167-313">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-313">**Possible values**</span></span> | <span data-ttu-id="95167-314">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="95167-314">10000 (default).</span></span> <span data-ttu-id="95167-315">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="95167-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="95167-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-316">**Comments**</span></span> | <span data-ttu-id="95167-317">适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="95167-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="95167-318">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="95167-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="95167-319">配置文件 *中的 cloudService* 条目用于配置产品的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="95167-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-320">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-320">**Key**</span></span> | <span data-ttu-id="95167-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="95167-321">cloudService</span></span> |
| <span data-ttu-id="95167-322">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-322">**Data type**</span></span> | <span data-ttu-id="95167-323">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="95167-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="95167-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="95167-324">**Comments**</span></span> | <span data-ttu-id="95167-325">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="95167-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="95167-326">启用/禁用云提供的保护</span><span class="sxs-lookup"><span data-stu-id="95167-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="95167-327">确定是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="95167-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="95167-328">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="95167-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-329">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-329">**Key**</span></span> | <span data-ttu-id="95167-330">enabled</span><span class="sxs-lookup"><span data-stu-id="95167-330">enabled</span></span> |
| <span data-ttu-id="95167-331">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-331">**Data type**</span></span> | <span data-ttu-id="95167-332">Boolean</span><span class="sxs-lookup"><span data-stu-id="95167-332">Boolean</span></span> |
| <span data-ttu-id="95167-333">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-333">**Possible values**</span></span> | <span data-ttu-id="95167-334">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="95167-334">true (default)</span></span> <br/> <span data-ttu-id="95167-335">false</span><span class="sxs-lookup"><span data-stu-id="95167-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="95167-336">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="95167-336">Diagnostic collection level</span></span>

<span data-ttu-id="95167-337">诊断数据用于使 Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="95167-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="95167-338">此设置确定产品发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="95167-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-339">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-339">**Key**</span></span> | <span data-ttu-id="95167-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="95167-340">diagnosticLevel</span></span> |
| <span data-ttu-id="95167-341">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-341">**Data type**</span></span> | <span data-ttu-id="95167-342">String</span><span class="sxs-lookup"><span data-stu-id="95167-342">String</span></span> |
| <span data-ttu-id="95167-343">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-343">**Possible values**</span></span> | <span data-ttu-id="95167-344">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="95167-344">optional (default)</span></span> <br/> <span data-ttu-id="95167-345">必需</span><span class="sxs-lookup"><span data-stu-id="95167-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="95167-346">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="95167-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="95167-347">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="95167-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="95167-348">有三个级别用于控制示例提交：</span><span class="sxs-lookup"><span data-stu-id="95167-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="95167-349">**无**：不会向 Microsoft 提交任何可疑样本。</span><span class="sxs-lookup"><span data-stu-id="95167-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="95167-350">**保险箱：** 只有不包含个人身份信息的可疑样本 (个人身份) 自动提交。</span><span class="sxs-lookup"><span data-stu-id="95167-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="95167-351">这是此设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="95167-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="95167-352">**全部**：所有可疑示例都提交到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="95167-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-353">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-353">**Key**</span></span> | <span data-ttu-id="95167-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="95167-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="95167-355">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-355">**Data type**</span></span> | <span data-ttu-id="95167-356">String</span><span class="sxs-lookup"><span data-stu-id="95167-356">String</span></span> |
| <span data-ttu-id="95167-357">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-357">**Possible values**</span></span> | <span data-ttu-id="95167-358">无</span><span class="sxs-lookup"><span data-stu-id="95167-358">none</span></span> <br/> <span data-ttu-id="95167-359">安全 (默认) </span><span class="sxs-lookup"><span data-stu-id="95167-359">safe (default)</span></span> <br/> <span data-ttu-id="95167-360">all</span><span class="sxs-lookup"><span data-stu-id="95167-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="95167-361">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="95167-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="95167-362">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="95167-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="95167-363">**键**</span><span class="sxs-lookup"><span data-stu-id="95167-363">**Key**</span></span> | <span data-ttu-id="95167-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="95167-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="95167-365">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95167-365">**Data type**</span></span> | <span data-ttu-id="95167-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="95167-366">Boolean</span></span> |
| <span data-ttu-id="95167-367">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95167-367">**Possible values**</span></span> | <span data-ttu-id="95167-368">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="95167-368">true (default)</span></span> <br/> <span data-ttu-id="95167-369">false</span><span class="sxs-lookup"><span data-stu-id="95167-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="95167-370">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="95167-370">Recommended configuration profile</span></span>

<span data-ttu-id="95167-371">若要开始，我们建议你的企业采用以下配置文件，以利用 Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="95167-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="95167-372">以下配置文件将：</span><span class="sxs-lookup"><span data-stu-id="95167-372">The following configuration profile will:</span></span>

- <span data-ttu-id="95167-373">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="95167-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="95167-374">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="95167-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="95167-375">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="95167-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="95167-376">**存档 (** 高压缩率的文件) 审核到产品日志</span><span class="sxs-lookup"><span data-stu-id="95167-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="95167-377">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="95167-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="95167-378">启用云保护</span><span class="sxs-lookup"><span data-stu-id="95167-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="95167-379">启用级别的自动示例 `safe` 提交</span><span class="sxs-lookup"><span data-stu-id="95167-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="95167-380">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="95167-380">Sample profile</span></span>

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
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="95167-381">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="95167-381">Full configuration profile example</span></span>

<span data-ttu-id="95167-382">以下配置文件包含本文档中所述的所有设置的条目，可用于更高级的方案，您希望对产品进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="95167-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="95167-383">完整个人资料</span><span class="sxs-lookup"><span data-stu-id="95167-383">Full profile</span></span>

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
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
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
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="95167-384">配置文件验证</span><span class="sxs-lookup"><span data-stu-id="95167-384">Configuration profile validation</span></span>

<span data-ttu-id="95167-385">配置文件必须是有效的 JSON 格式文件。</span><span class="sxs-lookup"><span data-stu-id="95167-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="95167-386">有许多工具可用于验证这一点。</span><span class="sxs-lookup"><span data-stu-id="95167-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="95167-387">例如，如果你已安装 `python` 在设备上：</span><span class="sxs-lookup"><span data-stu-id="95167-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="95167-388">如果 JSON 格式良好，则上述命令会输出回终端，并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="95167-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="95167-389">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="95167-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="95167-390">验证文件mdatp_managed.js是否正常工作</span><span class="sxs-lookup"><span data-stu-id="95167-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="95167-391">若要验证 /etc/opt/microsoft/mdatp/managed/mdatp_managed.json 是否正常工作，应在这些设置旁边看到"[托管]"：</span><span class="sxs-lookup"><span data-stu-id="95167-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>
- <span data-ttu-id="95167-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="95167-392">cloud_enabled</span></span>
- <span data-ttu-id="95167-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="95167-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="95167-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="95167-394">passice_mode_enabled</span></span>
- <span data-ttu-id="95167-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="95167-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="95167-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="95167-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="95167-397">若要mdatp_managed.js，无需重新启动 wdavdaemon。</span><span class="sxs-lookup"><span data-stu-id="95167-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="95167-398">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="95167-398">Configuration profile deployment</span></span>

<span data-ttu-id="95167-399">为企业生成配置文件后，可以通过企业使用的管理工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="95167-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="95167-400">Linux 上的 Defender for Endpoint 从 */etc/opt/microsoft/mdatp/managed/mdatp_managed.json 文件中读取托管* 配置。</span><span class="sxs-lookup"><span data-stu-id="95167-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
