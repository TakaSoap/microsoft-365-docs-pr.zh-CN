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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289483"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="25a73-104">在 Linux 上设置适用于终结点的 Microsoft Defender 的首选项</span><span class="sxs-lookup"><span data-stu-id="25a73-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25a73-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="25a73-105">**Applies to:**</span></span>
- [<span data-ttu-id="25a73-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="25a73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25a73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25a73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="25a73-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="25a73-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25a73-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="25a73-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="25a73-110">本主题包含有关如何在企业环境中为 Linux 上的 Defender for Endpoint 设置首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="25a73-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="25a73-111">如果你有兴趣从命令行在设备上配置产品，请参阅 [资源](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="25a73-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="25a73-112">在企业环境中，Linux 上的 Defender for Endpoint 可通过配置文件进行管理。</span><span class="sxs-lookup"><span data-stu-id="25a73-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="25a73-113">此配置文件从你选择的管理工具部署。</span><span class="sxs-lookup"><span data-stu-id="25a73-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="25a73-114">企业管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="25a73-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="25a73-115">换句话说，企业中的用户不能更改通过此配置文件设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="25a73-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="25a73-116">本文介绍此配置文件 (包括可用于开始使用配置文件的建议) 以及如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="25a73-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="25a73-117">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="25a73-117">Configuration profile structure</span></span>

<span data-ttu-id="25a73-118">配置文件是一个 .json 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="25a73-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="25a73-119">值可以很简单，如数字值，也可以复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="25a73-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="25a73-120">通常，你将使用配置管理工具在 位置推送名称 ```mdatp_managed.json``` 为 的文件 ```/etc/opt/microsoft/mdatp/managed/``` 。</span><span class="sxs-lookup"><span data-stu-id="25a73-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="25a73-121">配置文件的顶层包括产品范围的首选项和产品子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="25a73-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="25a73-122">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="25a73-122">Antivirus engine preferences</span></span>

<span data-ttu-id="25a73-123">配置文件 *的 antivirusEngine* 部分用于管理产品的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="25a73-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="25a73-124">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-124">Description</span></span>|<span data-ttu-id="25a73-125">值</span><span class="sxs-lookup"><span data-stu-id="25a73-125">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-126">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-126">**Key**</span></span>|<span data-ttu-id="25a73-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="25a73-127">antivirusEngine</span></span>|
|<span data-ttu-id="25a73-128">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-128">**Data type**</span></span>|<span data-ttu-id="25a73-129">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="25a73-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="25a73-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-130">**Comments**</span></span>|<span data-ttu-id="25a73-131">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="25a73-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="25a73-132">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="25a73-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="25a73-133">确定是否在启用实时 (时扫描) 文件。</span><span class="sxs-lookup"><span data-stu-id="25a73-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="25a73-134">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-134">Description</span></span>|<span data-ttu-id="25a73-135">值</span><span class="sxs-lookup"><span data-stu-id="25a73-135">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-136">**Key**</span></span>|<span data-ttu-id="25a73-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="25a73-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="25a73-138">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-138">**Data type**</span></span>|<span data-ttu-id="25a73-139">Boolean</span><span class="sxs-lookup"><span data-stu-id="25a73-139">Boolean</span></span>|
|<span data-ttu-id="25a73-140">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-140">**Possible values**</span></span>|<span data-ttu-id="25a73-141">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="25a73-141">true (default)</span></span> <p> <span data-ttu-id="25a73-142">false</span><span class="sxs-lookup"><span data-stu-id="25a73-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="25a73-143">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="25a73-143">Enable / disable passive mode</span></span>

<span data-ttu-id="25a73-144">确定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="25a73-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="25a73-145">在被动模式下：</span><span class="sxs-lookup"><span data-stu-id="25a73-145">In passive mode:</span></span>

- <span data-ttu-id="25a73-146">实时保护已关闭。</span><span class="sxs-lookup"><span data-stu-id="25a73-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="25a73-147">按需扫描已打开。</span><span class="sxs-lookup"><span data-stu-id="25a73-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="25a73-148">自动威胁修正已关闭。</span><span class="sxs-lookup"><span data-stu-id="25a73-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="25a73-149">安全智能更新已打开。</span><span class="sxs-lookup"><span data-stu-id="25a73-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="25a73-150">状态菜单图标处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="25a73-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="25a73-151">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-151">Description</span></span>|<span data-ttu-id="25a73-152">值</span><span class="sxs-lookup"><span data-stu-id="25a73-152">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-153">**Key**</span></span>|<span data-ttu-id="25a73-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="25a73-154">passiveMode</span></span>|
|<span data-ttu-id="25a73-155">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-155">**Data type**</span></span>|<span data-ttu-id="25a73-156">Boolean</span><span class="sxs-lookup"><span data-stu-id="25a73-156">Boolean</span></span>|
|<span data-ttu-id="25a73-157">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-157">**Possible values**</span></span>|<span data-ttu-id="25a73-158">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="25a73-158">false (default)</span></span> <p> <span data-ttu-id="25a73-159">true</span><span class="sxs-lookup"><span data-stu-id="25a73-159">true</span></span>|
|<span data-ttu-id="25a73-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-160">**Comments**</span></span>|<span data-ttu-id="25a73-161">适用于终结点版本 100.67.60 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="25a73-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="25a73-162">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="25a73-162">Exclusion merge policy</span></span>

<span data-ttu-id="25a73-163">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="25a73-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="25a73-164">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="25a73-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="25a73-165">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="25a73-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="25a73-166">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-166">Description</span></span>|<span data-ttu-id="25a73-167">值</span><span class="sxs-lookup"><span data-stu-id="25a73-167">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-168">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-168">**Key**</span></span>|<span data-ttu-id="25a73-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="25a73-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="25a73-170">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-170">**Data type**</span></span>|<span data-ttu-id="25a73-171">String</span><span class="sxs-lookup"><span data-stu-id="25a73-171">String</span></span>|
|<span data-ttu-id="25a73-172">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-172">**Possible values**</span></span>|<span data-ttu-id="25a73-173">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="25a73-173">merge (default)</span></span> <p> <span data-ttu-id="25a73-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="25a73-174">admin_only</span></span>|
|<span data-ttu-id="25a73-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-175">**Comments**</span></span>|<span data-ttu-id="25a73-176">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="25a73-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="25a73-177">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="25a73-177">Scan exclusions</span></span>

<span data-ttu-id="25a73-178">从扫描中排除的实体。</span><span class="sxs-lookup"><span data-stu-id="25a73-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="25a73-179">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="25a73-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="25a73-180"> (排除项指定为项目数组，则管理员可以按任意顺序指定所需数量的元素) </span><span class="sxs-lookup"><span data-stu-id="25a73-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="25a73-181">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-181">Description</span></span>|<span data-ttu-id="25a73-182">值</span><span class="sxs-lookup"><span data-stu-id="25a73-182">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-183">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-183">**Key**</span></span>|<span data-ttu-id="25a73-184">排除项</span><span class="sxs-lookup"><span data-stu-id="25a73-184">exclusions</span></span>|
|<span data-ttu-id="25a73-185">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-185">**Data type**</span></span>|<span data-ttu-id="25a73-186">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="25a73-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="25a73-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-187">**Comments**</span></span>|<span data-ttu-id="25a73-188">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="25a73-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="25a73-189">排除类型</span><span class="sxs-lookup"><span data-stu-id="25a73-189">Type of exclusion</span></span>

<span data-ttu-id="25a73-190">指定从扫描中排除的内容的类型。</span><span class="sxs-lookup"><span data-stu-id="25a73-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="25a73-191">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-191">Description</span></span>|<span data-ttu-id="25a73-192">值</span><span class="sxs-lookup"><span data-stu-id="25a73-192">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-193">**Key**</span></span>|<span data-ttu-id="25a73-194">$type</span><span class="sxs-lookup"><span data-stu-id="25a73-194">$type</span></span>|
|<span data-ttu-id="25a73-195">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-195">**Data type**</span></span>|<span data-ttu-id="25a73-196">String</span><span class="sxs-lookup"><span data-stu-id="25a73-196">String</span></span>|
|<span data-ttu-id="25a73-197">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-197">**Possible values**</span></span>|<span data-ttu-id="25a73-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="25a73-198">excludedPath</span></span> <p> <span data-ttu-id="25a73-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="25a73-199">excludedFileExtension</span></span> <p> <span data-ttu-id="25a73-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="25a73-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="25a73-201">排除内容的路径</span><span class="sxs-lookup"><span data-stu-id="25a73-201">Path to excluded content</span></span>

<span data-ttu-id="25a73-202">用于按完整文件路径从扫描中排除内容。</span><span class="sxs-lookup"><span data-stu-id="25a73-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="25a73-203">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-203">Description</span></span>|<span data-ttu-id="25a73-204">值</span><span class="sxs-lookup"><span data-stu-id="25a73-204">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-205">**Key**</span></span>|<span data-ttu-id="25a73-206">path</span><span class="sxs-lookup"><span data-stu-id="25a73-206">path</span></span>|
|<span data-ttu-id="25a73-207">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-207">**Data type**</span></span>|<span data-ttu-id="25a73-208">String</span><span class="sxs-lookup"><span data-stu-id="25a73-208">String</span></span>|
|<span data-ttu-id="25a73-209">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-209">**Possible values**</span></span>|<span data-ttu-id="25a73-210">有效路径</span><span class="sxs-lookup"><span data-stu-id="25a73-210">valid paths</span></span>|
|<span data-ttu-id="25a73-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-211">**Comments**</span></span>|<span data-ttu-id="25a73-212">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="25a73-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="25a73-213">文件 (目录的路径) </span><span class="sxs-lookup"><span data-stu-id="25a73-213">Path type (file / directory)</span></span>

<span data-ttu-id="25a73-214">指示 path *属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="25a73-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="25a73-215">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-215">Description</span></span>|<span data-ttu-id="25a73-216">值</span><span class="sxs-lookup"><span data-stu-id="25a73-216">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-217">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-217">**Key**</span></span>|<span data-ttu-id="25a73-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="25a73-218">isDirectory</span></span>|
|<span data-ttu-id="25a73-219">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-219">**Data type**</span></span>|<span data-ttu-id="25a73-220">Boolean</span><span class="sxs-lookup"><span data-stu-id="25a73-220">Boolean</span></span>|
|<span data-ttu-id="25a73-221">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-221">**Possible values**</span></span>|<span data-ttu-id="25a73-222">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="25a73-222">false (default)</span></span> <p> <span data-ttu-id="25a73-223">true</span><span class="sxs-lookup"><span data-stu-id="25a73-223">true</span></span>|
|<span data-ttu-id="25a73-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-224">**Comments**</span></span>|<span data-ttu-id="25a73-225">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="25a73-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="25a73-226">从扫描中排除的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="25a73-226">File extension excluded from the scan</span></span>

<span data-ttu-id="25a73-227">用于按文件扩展名从扫描中排除内容。</span><span class="sxs-lookup"><span data-stu-id="25a73-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="25a73-228">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-228">Description</span></span>|<span data-ttu-id="25a73-229">值</span><span class="sxs-lookup"><span data-stu-id="25a73-229">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-230">**Key**</span></span>|<span data-ttu-id="25a73-231">extension</span><span class="sxs-lookup"><span data-stu-id="25a73-231">extension</span></span>|
|<span data-ttu-id="25a73-232">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-232">**Data type**</span></span>|<span data-ttu-id="25a73-233">String</span><span class="sxs-lookup"><span data-stu-id="25a73-233">String</span></span>|
|<span data-ttu-id="25a73-234">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-234">**Possible values**</span></span>|<span data-ttu-id="25a73-235">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="25a73-235">valid file extensions</span></span>|
|<span data-ttu-id="25a73-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-236">**Comments**</span></span>|<span data-ttu-id="25a73-237">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="25a73-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="25a73-238">从扫描中排除的进程\*</span><span class="sxs-lookup"><span data-stu-id="25a73-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="25a73-239">指定从扫描中排除所有文件活动的进程。</span><span class="sxs-lookup"><span data-stu-id="25a73-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="25a73-240">可以通过进程的名称或名称来指定 (例如，) 或完整 (`cat` 例如 `/bin/cat` ，) 。</span><span class="sxs-lookup"><span data-stu-id="25a73-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="25a73-241">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-241">Description</span></span>|<span data-ttu-id="25a73-242">值</span><span class="sxs-lookup"><span data-stu-id="25a73-242">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-243">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-243">**Key**</span></span>|<span data-ttu-id="25a73-244">name</span><span class="sxs-lookup"><span data-stu-id="25a73-244">name</span></span>|
|<span data-ttu-id="25a73-245">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-245">**Data type**</span></span>|<span data-ttu-id="25a73-246">String</span><span class="sxs-lookup"><span data-stu-id="25a73-246">String</span></span>|
|<span data-ttu-id="25a73-247">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-247">**Possible values**</span></span>|<span data-ttu-id="25a73-248">任何字符串</span><span class="sxs-lookup"><span data-stu-id="25a73-248">any string</span></span>|
|<span data-ttu-id="25a73-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-249">**Comments**</span></span>|<span data-ttu-id="25a73-250">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="25a73-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="25a73-251">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="25a73-251">Allowed threats</span></span>

<span data-ttu-id="25a73-252">威胁列表 (名称) 产品未阻止但允许运行的威胁列表。</span><span class="sxs-lookup"><span data-stu-id="25a73-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="25a73-253">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-253">Description</span></span>|<span data-ttu-id="25a73-254">值</span><span class="sxs-lookup"><span data-stu-id="25a73-254">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-255">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-255">**Key**</span></span>|<span data-ttu-id="25a73-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="25a73-256">allowedThreats</span></span>|
|<span data-ttu-id="25a73-257">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-257">**Data type**</span></span>|<span data-ttu-id="25a73-258">字符串数组</span><span class="sxs-lookup"><span data-stu-id="25a73-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="25a73-259">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="25a73-259">Disallowed threat actions</span></span>

<span data-ttu-id="25a73-260">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="25a73-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="25a73-261">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="25a73-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="25a73-262">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-262">Description</span></span>|<span data-ttu-id="25a73-263">值</span><span class="sxs-lookup"><span data-stu-id="25a73-263">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-264">**Key**</span></span>|<span data-ttu-id="25a73-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="25a73-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="25a73-266">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-266">**Data type**</span></span>|<span data-ttu-id="25a73-267">字符串数组</span><span class="sxs-lookup"><span data-stu-id="25a73-267">Array of strings</span></span>|
|<span data-ttu-id="25a73-268">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-268">**Possible values**</span></span>|<span data-ttu-id="25a73-269">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="25a73-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="25a73-270">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="25a73-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="25a73-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-271">**Comments**</span></span>|<span data-ttu-id="25a73-272">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="25a73-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="25a73-273">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="25a73-273">Threat type settings</span></span>

<span data-ttu-id="25a73-274">防病毒 *引擎中的 threatTypeSettings* 首选项用于控制产品如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="25a73-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="25a73-275">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-275">Description</span></span>|<span data-ttu-id="25a73-276">值</span><span class="sxs-lookup"><span data-stu-id="25a73-276">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-277">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-277">**Key**</span></span>|<span data-ttu-id="25a73-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="25a73-278">threatTypeSettings</span></span>|
|<span data-ttu-id="25a73-279">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-279">**Data type**</span></span>|<span data-ttu-id="25a73-280">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="25a73-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="25a73-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-281">**Comments**</span></span>|<span data-ttu-id="25a73-282">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="25a73-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="25a73-283">威胁类型</span><span class="sxs-lookup"><span data-stu-id="25a73-283">Threat type</span></span>

<span data-ttu-id="25a73-284">配置其行为的威胁类型。</span><span class="sxs-lookup"><span data-stu-id="25a73-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="25a73-285">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-285">Description</span></span>|<span data-ttu-id="25a73-286">值</span><span class="sxs-lookup"><span data-stu-id="25a73-286">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-287">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-287">**Key**</span></span>|<span data-ttu-id="25a73-288">注册表项</span><span class="sxs-lookup"><span data-stu-id="25a73-288">key</span></span>|
|<span data-ttu-id="25a73-289">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-289">**Data type**</span></span>|<span data-ttu-id="25a73-290">String</span><span class="sxs-lookup"><span data-stu-id="25a73-290">String</span></span>|
|<span data-ttu-id="25a73-291">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-291">**Possible values**</span></span>|<span data-ttu-id="25a73-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="25a73-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="25a73-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="25a73-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="25a73-294">要采取的措施</span><span class="sxs-lookup"><span data-stu-id="25a73-294">Action to take</span></span>

<span data-ttu-id="25a73-295">遇到上一节中指定的类型的威胁时要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="25a73-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="25a73-296">可以是：</span><span class="sxs-lookup"><span data-stu-id="25a73-296">Can be:</span></span>

- <span data-ttu-id="25a73-297">**审核**：设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="25a73-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="25a73-298">**阻止**：设备受到此类型威胁的保护，并且你将在安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="25a73-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="25a73-299">**关闭**：设备不受此类型威胁的保护，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="25a73-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="25a73-300">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-300">Description</span></span>|<span data-ttu-id="25a73-301">值</span><span class="sxs-lookup"><span data-stu-id="25a73-301">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-302">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-302">**Key**</span></span>|<span data-ttu-id="25a73-303">值</span><span class="sxs-lookup"><span data-stu-id="25a73-303">value</span></span>|
|<span data-ttu-id="25a73-304">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-304">**Data type**</span></span>|<span data-ttu-id="25a73-305">String</span><span class="sxs-lookup"><span data-stu-id="25a73-305">String</span></span>|
|<span data-ttu-id="25a73-306">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-306">**Possible values**</span></span>|<span data-ttu-id="25a73-307">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="25a73-307">audit (default)</span></span> <p> <span data-ttu-id="25a73-308">block</span><span class="sxs-lookup"><span data-stu-id="25a73-308">block</span></span> <p> <span data-ttu-id="25a73-309">off</span><span class="sxs-lookup"><span data-stu-id="25a73-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="25a73-310">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="25a73-310">Threat type settings merge policy</span></span>

<span data-ttu-id="25a73-311">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="25a73-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="25a73-312">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="25a73-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="25a73-313">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="25a73-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="25a73-314">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-314">Description</span></span>|<span data-ttu-id="25a73-315">值</span><span class="sxs-lookup"><span data-stu-id="25a73-315">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-316">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-316">**Key**</span></span>|<span data-ttu-id="25a73-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="25a73-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="25a73-318">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-318">**Data type**</span></span>|<span data-ttu-id="25a73-319">String</span><span class="sxs-lookup"><span data-stu-id="25a73-319">String</span></span>|
|<span data-ttu-id="25a73-320">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-320">**Possible values**</span></span>|<span data-ttu-id="25a73-321">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="25a73-321">merge (default)</span></span> <p> <span data-ttu-id="25a73-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="25a73-322">admin_only</span></span>|
|<span data-ttu-id="25a73-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-323">**Comments**</span></span>|<span data-ttu-id="25a73-324">适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="25a73-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="25a73-325">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="25a73-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="25a73-326">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="25a73-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="25a73-327">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="25a73-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="25a73-328">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="25a73-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="25a73-329">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-329">Description</span></span>|<span data-ttu-id="25a73-330">值</span><span class="sxs-lookup"><span data-stu-id="25a73-330">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-331">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-331">**Key**</span></span>|<span data-ttu-id="25a73-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="25a73-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="25a73-333">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-333">**Data type**</span></span>|<span data-ttu-id="25a73-334">String</span><span class="sxs-lookup"><span data-stu-id="25a73-334">String</span></span>|
|<span data-ttu-id="25a73-335">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-335">**Possible values**</span></span>|<span data-ttu-id="25a73-336">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="25a73-336">90 (default).</span></span> <span data-ttu-id="25a73-337">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="25a73-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="25a73-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-338">**Comments**</span></span>|<span data-ttu-id="25a73-339">适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="25a73-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="25a73-340">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="25a73-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="25a73-341">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="25a73-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="25a73-342">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="25a73-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="25a73-343">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-343">Description</span></span>|<span data-ttu-id="25a73-344">值</span><span class="sxs-lookup"><span data-stu-id="25a73-344">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-345">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-345">**Key**</span></span>|<span data-ttu-id="25a73-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="25a73-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="25a73-347">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-347">**Data type**</span></span>|<span data-ttu-id="25a73-348">String</span><span class="sxs-lookup"><span data-stu-id="25a73-348">String</span></span>|
|<span data-ttu-id="25a73-349">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-349">**Possible values**</span></span>|<span data-ttu-id="25a73-350">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="25a73-350">10000 (default).</span></span> <span data-ttu-id="25a73-351">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="25a73-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="25a73-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-352">**Comments**</span></span>|<span data-ttu-id="25a73-353">适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="25a73-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="25a73-354">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="25a73-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="25a73-355">配置文件 *中的 cloudService* 条目用于配置产品的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="25a73-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="25a73-356">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-356">Description</span></span>|<span data-ttu-id="25a73-357">值</span><span class="sxs-lookup"><span data-stu-id="25a73-357">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-358">**Key**</span></span>|<span data-ttu-id="25a73-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="25a73-359">cloudService</span></span>|
|<span data-ttu-id="25a73-360">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-360">**Data type**</span></span>|<span data-ttu-id="25a73-361">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="25a73-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="25a73-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="25a73-362">**Comments**</span></span>|<span data-ttu-id="25a73-363">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="25a73-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="25a73-364">启用/禁用云提供的保护</span><span class="sxs-lookup"><span data-stu-id="25a73-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="25a73-365">确定是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="25a73-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="25a73-366">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="25a73-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="25a73-367">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-367">Description</span></span>|<span data-ttu-id="25a73-368">值</span><span class="sxs-lookup"><span data-stu-id="25a73-368">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-369">**Key**</span></span>|<span data-ttu-id="25a73-370">enabled</span><span class="sxs-lookup"><span data-stu-id="25a73-370">enabled</span></span>|
|<span data-ttu-id="25a73-371">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-371">**Data type**</span></span>|<span data-ttu-id="25a73-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="25a73-372">Boolean</span></span>|
|<span data-ttu-id="25a73-373">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-373">**Possible values**</span></span>|<span data-ttu-id="25a73-374">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="25a73-374">true (default)</span></span> <p> <span data-ttu-id="25a73-375">false</span><span class="sxs-lookup"><span data-stu-id="25a73-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="25a73-376">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="25a73-376">Diagnostic collection level</span></span>

<span data-ttu-id="25a73-377">诊断数据用于使 Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="25a73-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="25a73-378">此设置确定产品发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="25a73-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="25a73-379">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-379">Description</span></span>|<span data-ttu-id="25a73-380">值</span><span class="sxs-lookup"><span data-stu-id="25a73-380">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-381">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-381">**Key**</span></span>|<span data-ttu-id="25a73-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="25a73-382">diagnosticLevel</span></span>|
|<span data-ttu-id="25a73-383">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-383">**Data type**</span></span>|<span data-ttu-id="25a73-384">String</span><span class="sxs-lookup"><span data-stu-id="25a73-384">String</span></span>|
|<span data-ttu-id="25a73-385">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-385">**Possible values**</span></span>|<span data-ttu-id="25a73-386">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="25a73-386">optional (default)</span></span> <p> <span data-ttu-id="25a73-387">必需</span><span class="sxs-lookup"><span data-stu-id="25a73-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="25a73-388">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="25a73-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="25a73-389">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="25a73-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="25a73-390">有三个级别用于控制示例提交：</span><span class="sxs-lookup"><span data-stu-id="25a73-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="25a73-391">**无**：不会向 Microsoft 提交任何可疑样本。</span><span class="sxs-lookup"><span data-stu-id="25a73-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="25a73-392">**保险箱：** 只有不包含个人身份信息的可疑样本 (个人身份) 自动提交。</span><span class="sxs-lookup"><span data-stu-id="25a73-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="25a73-393">这是此设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="25a73-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="25a73-394">**全部**：所有可疑示例都提交到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="25a73-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="25a73-395">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-395">Description</span></span>|<span data-ttu-id="25a73-396">值</span><span class="sxs-lookup"><span data-stu-id="25a73-396">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-397">**Key**</span></span>|<span data-ttu-id="25a73-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="25a73-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="25a73-399">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-399">**Data type**</span></span>|<span data-ttu-id="25a73-400">String</span><span class="sxs-lookup"><span data-stu-id="25a73-400">String</span></span>|
|<span data-ttu-id="25a73-401">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-401">**Possible values**</span></span>|<span data-ttu-id="25a73-402">无</span><span class="sxs-lookup"><span data-stu-id="25a73-402">none</span></span> <p> <span data-ttu-id="25a73-403">安全 (默认) </span><span class="sxs-lookup"><span data-stu-id="25a73-403">safe (default)</span></span> <p> <span data-ttu-id="25a73-404">all</span><span class="sxs-lookup"><span data-stu-id="25a73-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="25a73-405">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="25a73-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="25a73-406">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="25a73-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="25a73-407">说明</span><span class="sxs-lookup"><span data-stu-id="25a73-407">Description</span></span>|<span data-ttu-id="25a73-408">值</span><span class="sxs-lookup"><span data-stu-id="25a73-408">Value</span></span>|
|---|---|
|<span data-ttu-id="25a73-409">**Key**</span><span class="sxs-lookup"><span data-stu-id="25a73-409">**Key**</span></span>|<span data-ttu-id="25a73-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="25a73-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="25a73-411">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="25a73-411">**Data type**</span></span>|<span data-ttu-id="25a73-412">Boolean</span><span class="sxs-lookup"><span data-stu-id="25a73-412">Boolean</span></span>|
|<span data-ttu-id="25a73-413">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="25a73-413">**Possible values**</span></span>|<span data-ttu-id="25a73-414">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="25a73-414">true (default)</span></span> <p> <span data-ttu-id="25a73-415">false</span><span class="sxs-lookup"><span data-stu-id="25a73-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="25a73-416">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="25a73-416">Recommended configuration profile</span></span>

<span data-ttu-id="25a73-417">若要开始，我们建议你的企业采用以下配置文件，以利用 Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="25a73-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="25a73-418">以下配置文件将：</span><span class="sxs-lookup"><span data-stu-id="25a73-418">The following configuration profile will:</span></span>

- <span data-ttu-id="25a73-419">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="25a73-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="25a73-420">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="25a73-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="25a73-421">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="25a73-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="25a73-422">**存档 (** 高压缩率的文件) 审核到产品日志</span><span class="sxs-lookup"><span data-stu-id="25a73-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="25a73-423">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="25a73-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="25a73-424">启用云保护</span><span class="sxs-lookup"><span data-stu-id="25a73-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="25a73-425">启用级别的自动示例 `safe` 提交</span><span class="sxs-lookup"><span data-stu-id="25a73-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="25a73-426">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="25a73-426">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="25a73-427">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="25a73-427">Full configuration profile example</span></span>

<span data-ttu-id="25a73-428">以下配置文件包含本文档中所述的所有设置的条目，可用于更高级的方案，您希望对产品进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="25a73-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="25a73-429">完整个人资料</span><span class="sxs-lookup"><span data-stu-id="25a73-429">Full profile</span></span>

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

## <a name="configuration-profile-validation"></a><span data-ttu-id="25a73-430">配置文件验证</span><span class="sxs-lookup"><span data-stu-id="25a73-430">Configuration profile validation</span></span>

<span data-ttu-id="25a73-431">配置文件必须是有效的 JSON 格式文件。</span><span class="sxs-lookup"><span data-stu-id="25a73-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="25a73-432">有许多工具可用于验证这一点。</span><span class="sxs-lookup"><span data-stu-id="25a73-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="25a73-433">例如，如果你已安装 `python` 在设备上：</span><span class="sxs-lookup"><span data-stu-id="25a73-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="25a73-434">如果 JSON 格式良好，则上述命令会输出回终端，并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="25a73-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="25a73-435">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="25a73-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="25a73-436">验证文件mdatp_managed.js是否正常工作</span><span class="sxs-lookup"><span data-stu-id="25a73-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="25a73-437">若要验证 /etc/opt/microsoft/mdatp/managed/mdatp_managed.json 是否正常工作，应在这些设置旁边看到"[托管]"：</span><span class="sxs-lookup"><span data-stu-id="25a73-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="25a73-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="25a73-438">cloud_enabled</span></span>
- <span data-ttu-id="25a73-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="25a73-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="25a73-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="25a73-440">passive_mode_enabled</span></span>
- <span data-ttu-id="25a73-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="25a73-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="25a73-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="25a73-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="25a73-443">若要mdatp_managed.js，无需重新启动 wdavdaemon。</span><span class="sxs-lookup"><span data-stu-id="25a73-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="25a73-444">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="25a73-444">Configuration profile deployment</span></span>

<span data-ttu-id="25a73-445">为企业生成配置文件后，可以通过企业使用的管理工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="25a73-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="25a73-446">Linux 上的 Defender for Endpoint 从 */etc/opt/microsoft/mdatp/managed/mdatp_managed.json 文件中读取托管* 配置。</span><span class="sxs-lookup"><span data-stu-id="25a73-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
