---
title: 在 Mac 上设置 Microsoft Defender for Endpoint 的首选项
description: 在企业组织中为 Mac 上的终结点配置 MMicrosoft Defender。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 管理， 首选项， 企业， intune， jamf， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346398"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="9cd87-104">在 macOS 上设置适用于终结点的 Microsoft Defender 的首选项</span><span class="sxs-lookup"><span data-stu-id="9cd87-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9cd87-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9cd87-105">**Applies to:**</span></span>

- [<span data-ttu-id="9cd87-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9cd87-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="9cd87-107">本文包含有关如何在企业组织中为 macOS 上的 Microsoft Defender for Endpoint 设置首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="9cd87-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="9cd87-108">若要使用命令行界面在 macOS 上配置适用于终结点的 Microsoft Defender，请参阅 [资源](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="9cd87-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="9cd87-109">摘要</span><span class="sxs-lookup"><span data-stu-id="9cd87-109">Summary</span></span>

<span data-ttu-id="9cd87-110">在企业组织中，可以通过使用多种管理工具之一部署的配置文件管理 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="9cd87-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="9cd87-111">由安全操作团队管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="9cd87-112">更改通过配置文件设置的首选项需要提升的权限，并且对于没有管理权限的用户不可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="9cd87-113">本文介绍配置文件的结构，包括可用于入门的推荐配置文件，并提供有关如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="9cd87-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="9cd87-114">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="9cd87-114">Configuration profile structure</span></span>

<span data-ttu-id="9cd87-115">配置文件是一个 *.plist* 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="9cd87-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="9cd87-116">值可以是简单的 (，如数值) 或复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="9cd87-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="9cd87-117">配置文件的布局取决于你使用的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9cd87-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="9cd87-118">以下各节包含 JAMF 和 Intune 的配置文件示例。</span><span class="sxs-lookup"><span data-stu-id="9cd87-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="9cd87-119">配置文件的顶级包括产品范围的首选项和 Microsoft Defender for Endpoint 子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="9cd87-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="9cd87-120">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="9cd87-120">Antivirus engine preferences</span></span>

<span data-ttu-id="9cd87-121">配置文件 *的 antivirusEngine* 部分用于管理 Microsoft Defender for Endpoint 的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="9cd87-122">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-122">Section</span></span>|<span data-ttu-id="9cd87-123">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-124">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-125">**Key**</span></span> | <span data-ttu-id="9cd87-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="9cd87-126">antivirusEngine</span></span> |
| <span data-ttu-id="9cd87-127">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-127">**Data type**</span></span> | <span data-ttu-id="9cd87-128">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-129">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-129">**Comments**</span></span> | <span data-ttu-id="9cd87-130">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="9cd87-131">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="9cd87-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="9cd87-132">指定是否启用实时保护，以在访问文件时对文件进行扫描。</span><span class="sxs-lookup"><span data-stu-id="9cd87-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="9cd87-133">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-133">Section</span></span>|<span data-ttu-id="9cd87-134">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-135">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-136">**Key**</span></span> | <span data-ttu-id="9cd87-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="9cd87-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="9cd87-138">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-138">**Data type**</span></span> | <span data-ttu-id="9cd87-139">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-139">Boolean</span></span> |
| <span data-ttu-id="9cd87-140">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-140">**Possible values**</span></span> | <span data-ttu-id="9cd87-141">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="9cd87-141">true (default)</span></span> <br/> <span data-ttu-id="9cd87-142">false</span><span class="sxs-lookup"><span data-stu-id="9cd87-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="9cd87-143">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="9cd87-143">Enable / disable passive mode</span></span>

<span data-ttu-id="9cd87-144">指定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="9cd87-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="9cd87-145">被动模式具有以下含义：</span><span class="sxs-lookup"><span data-stu-id="9cd87-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="9cd87-146">实时保护已关闭</span><span class="sxs-lookup"><span data-stu-id="9cd87-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="9cd87-147">按需扫描已打开</span><span class="sxs-lookup"><span data-stu-id="9cd87-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="9cd87-148">自动威胁修正已关闭</span><span class="sxs-lookup"><span data-stu-id="9cd87-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="9cd87-149">启用安全智能更新</span><span class="sxs-lookup"><span data-stu-id="9cd87-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="9cd87-150">状态菜单图标处于隐藏状态</span><span class="sxs-lookup"><span data-stu-id="9cd87-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="9cd87-151">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-151">Section</span></span>|<span data-ttu-id="9cd87-152">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-153">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-154">**Key**</span></span> | <span data-ttu-id="9cd87-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="9cd87-155">passiveMode</span></span> |
| <span data-ttu-id="9cd87-156">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-156">**Data type**</span></span> | <span data-ttu-id="9cd87-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-157">Boolean</span></span> |
| <span data-ttu-id="9cd87-158">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-158">**Possible values**</span></span> | <span data-ttu-id="9cd87-159">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="9cd87-159">false (default)</span></span> <br/> <span data-ttu-id="9cd87-160">true</span><span class="sxs-lookup"><span data-stu-id="9cd87-160">true</span></span> |
| <span data-ttu-id="9cd87-161">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-161">**Comments**</span></span> | <span data-ttu-id="9cd87-162">适用于终结点版本 100.67.60 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="9cd87-163">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="9cd87-163">Exclusion merge policy</span></span>

<span data-ttu-id="9cd87-164">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="9cd87-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="9cd87-165">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="9cd87-166">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="9cd87-167">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-167">Section</span></span>|<span data-ttu-id="9cd87-168">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-169">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-170">**Key**</span></span> | <span data-ttu-id="9cd87-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9cd87-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="9cd87-172">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-172">**Data type**</span></span> | <span data-ttu-id="9cd87-173">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-173">String</span></span> |
| <span data-ttu-id="9cd87-174">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-174">**Possible values**</span></span> | <span data-ttu-id="9cd87-175">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="9cd87-175">merge (default)</span></span> <br/> <span data-ttu-id="9cd87-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="9cd87-176">admin_only</span></span> |
| <span data-ttu-id="9cd87-177">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-177">**Comments**</span></span> | <span data-ttu-id="9cd87-178">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="9cd87-179">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="9cd87-179">Scan exclusions</span></span>

<span data-ttu-id="9cd87-180">指定被扫描排除的实体。</span><span class="sxs-lookup"><span data-stu-id="9cd87-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="9cd87-181">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="9cd87-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="9cd87-182"> (排除项指定为项目数组，则管理员可以按任意顺序指定所需数量的元素) </span><span class="sxs-lookup"><span data-stu-id="9cd87-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="9cd87-183">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-183">Section</span></span>|<span data-ttu-id="9cd87-184">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-185">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-186">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-186">**Key**</span></span> | <span data-ttu-id="9cd87-187">排除项</span><span class="sxs-lookup"><span data-stu-id="9cd87-187">exclusions</span></span> |
| <span data-ttu-id="9cd87-188">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-188">**Data type**</span></span> | <span data-ttu-id="9cd87-189">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-190">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-190">**Comments**</span></span> | <span data-ttu-id="9cd87-191">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="9cd87-192">排除类型</span><span class="sxs-lookup"><span data-stu-id="9cd87-192">Type of exclusion</span></span>

<span data-ttu-id="9cd87-193">按类型指定被排除的内容。</span><span class="sxs-lookup"><span data-stu-id="9cd87-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="9cd87-194">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-194">Section</span></span>|<span data-ttu-id="9cd87-195">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-196">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-197">**Key**</span></span> | <span data-ttu-id="9cd87-198">$type</span><span class="sxs-lookup"><span data-stu-id="9cd87-198">$type</span></span> |
| <span data-ttu-id="9cd87-199">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-199">**Data type**</span></span> | <span data-ttu-id="9cd87-200">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-200">String</span></span> |
| <span data-ttu-id="9cd87-201">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-201">**Possible values**</span></span> | <span data-ttu-id="9cd87-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="9cd87-202">excludedPath</span></span> <br/> <span data-ttu-id="9cd87-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="9cd87-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="9cd87-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="9cd87-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="9cd87-205">排除内容的路径</span><span class="sxs-lookup"><span data-stu-id="9cd87-205">Path to excluded content</span></span>

<span data-ttu-id="9cd87-206">指定未由完整文件路径扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="9cd87-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="9cd87-207">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-207">Section</span></span>|<span data-ttu-id="9cd87-208">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-209">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-210">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-210">**Key**</span></span> | <span data-ttu-id="9cd87-211">path</span><span class="sxs-lookup"><span data-stu-id="9cd87-211">path</span></span> |
| <span data-ttu-id="9cd87-212">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-212">**Data type**</span></span> | <span data-ttu-id="9cd87-213">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-213">String</span></span> |
| <span data-ttu-id="9cd87-214">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-214">**Possible values**</span></span> | <span data-ttu-id="9cd87-215">有效路径</span><span class="sxs-lookup"><span data-stu-id="9cd87-215">valid paths</span></span> |
| <span data-ttu-id="9cd87-216">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-216">**Comments**</span></span> | <span data-ttu-id="9cd87-217">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="9cd87-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="9cd87-218">支持的排除类型</span><span class="sxs-lookup"><span data-stu-id="9cd87-218">Supported exclusion types</span></span>

<span data-ttu-id="9cd87-219">下表显示了 Mac 上的 Defender for Endpoint 支持的排除类型。</span><span class="sxs-lookup"><span data-stu-id="9cd87-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="9cd87-220">排除</span><span class="sxs-lookup"><span data-stu-id="9cd87-220">Exclusion</span></span> | <span data-ttu-id="9cd87-221">定义</span><span class="sxs-lookup"><span data-stu-id="9cd87-221">Definition</span></span> | <span data-ttu-id="9cd87-222">示例</span><span class="sxs-lookup"><span data-stu-id="9cd87-222">Examples</span></span>
---|---|---
<span data-ttu-id="9cd87-223">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="9cd87-223">File extension</span></span> | <span data-ttu-id="9cd87-224">扩展名位于设备上任意位置的所有文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="9cd87-225">文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-225">File</span></span> | <span data-ttu-id="9cd87-226">由完整路径标识的特定文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="9cd87-227">文件夹</span><span class="sxs-lookup"><span data-stu-id="9cd87-227">Folder</span></span> | <span data-ttu-id="9cd87-228">指定文件夹下的所有 (以递归) </span><span class="sxs-lookup"><span data-stu-id="9cd87-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="9cd87-229">流程</span><span class="sxs-lookup"><span data-stu-id="9cd87-229">Process</span></span> | <span data-ttu-id="9cd87-230">特定进程 (的完整路径或文件名指定，) 它打开的所有文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="9cd87-231">上述路径必须是硬链接，而不是符号链接，才能成功排除。</span><span class="sxs-lookup"><span data-stu-id="9cd87-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="9cd87-232">可以通过运行 来检查路径是否为符号链接 `file <path-name>` 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="9cd87-233">文件、文件夹和进程排除项支持以下通配符：</span><span class="sxs-lookup"><span data-stu-id="9cd87-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="9cd87-234">通配符</span><span class="sxs-lookup"><span data-stu-id="9cd87-234">Wildcard</span></span> | <span data-ttu-id="9cd87-235">说明</span><span class="sxs-lookup"><span data-stu-id="9cd87-235">Description</span></span> | <span data-ttu-id="9cd87-236">示例</span><span class="sxs-lookup"><span data-stu-id="9cd87-236">Example</span></span> | <span data-ttu-id="9cd87-237">匹配</span><span class="sxs-lookup"><span data-stu-id="9cd87-237">Matches</span></span> | <span data-ttu-id="9cd87-238">不匹配</span><span class="sxs-lookup"><span data-stu-id="9cd87-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="9cd87-239">匹配任意数目的任何字符，包括无 (请注意，当在路径内使用此通配符时，它将仅替换一个) </span><span class="sxs-lookup"><span data-stu-id="9cd87-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="9cd87-240">?</span><span class="sxs-lookup"><span data-stu-id="9cd87-240">?</span></span> | <span data-ttu-id="9cd87-241">匹配任何单个字符</span><span class="sxs-lookup"><span data-stu-id="9cd87-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="9cd87-242">文件 (目录的路径) </span><span class="sxs-lookup"><span data-stu-id="9cd87-242">Path type (file / directory)</span></span>

<span data-ttu-id="9cd87-243">指示 *path 属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="9cd87-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="9cd87-244">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-244">Section</span></span>|<span data-ttu-id="9cd87-245">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-246">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-247">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-247">**Key**</span></span> | <span data-ttu-id="9cd87-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="9cd87-248">isDirectory</span></span> |
| <span data-ttu-id="9cd87-249">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-249">**Data type**</span></span> | <span data-ttu-id="9cd87-250">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-250">Boolean</span></span> |
| <span data-ttu-id="9cd87-251">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-251">**Possible values**</span></span> | <span data-ttu-id="9cd87-252">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="9cd87-252">false (default)</span></span> <br/> <span data-ttu-id="9cd87-253">true</span><span class="sxs-lookup"><span data-stu-id="9cd87-253">true</span></span> |
| <span data-ttu-id="9cd87-254">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-254">**Comments**</span></span> | <span data-ttu-id="9cd87-255">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="9cd87-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="9cd87-256">从扫描中排除的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="9cd87-256">File extension excluded from the scan</span></span>

<span data-ttu-id="9cd87-257">指定文件扩展名无法扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="9cd87-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="9cd87-258">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-258">Section</span></span>|<span data-ttu-id="9cd87-259">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-260">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-261">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-261">**Key**</span></span> | <span data-ttu-id="9cd87-262">extension</span><span class="sxs-lookup"><span data-stu-id="9cd87-262">extension</span></span> |
| <span data-ttu-id="9cd87-263">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-263">**Data type**</span></span> | <span data-ttu-id="9cd87-264">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-264">String</span></span> |
| <span data-ttu-id="9cd87-265">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-265">**Possible values**</span></span> | <span data-ttu-id="9cd87-266">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="9cd87-266">valid file extensions</span></span> |
| <span data-ttu-id="9cd87-267">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-267">**Comments**</span></span> | <span data-ttu-id="9cd87-268">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="9cd87-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="9cd87-269">从扫描中排除的进程</span><span class="sxs-lookup"><span data-stu-id="9cd87-269">Process excluded from the scan</span></span>

<span data-ttu-id="9cd87-270">指定一个进程，所有文件活动都从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="9cd87-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="9cd87-271">可以通过进程的名称指定进程， (例如) 或完整路径 (`cat` 例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="9cd87-272">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-272">Section</span></span>|<span data-ttu-id="9cd87-273">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-274">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-275">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-275">**Key**</span></span> | <span data-ttu-id="9cd87-276">name</span><span class="sxs-lookup"><span data-stu-id="9cd87-276">name</span></span> |
| <span data-ttu-id="9cd87-277">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-277">**Data type**</span></span> | <span data-ttu-id="9cd87-278">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-278">String</span></span> |
| <span data-ttu-id="9cd87-279">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-279">**Possible values**</span></span> | <span data-ttu-id="9cd87-280">任何字符串</span><span class="sxs-lookup"><span data-stu-id="9cd87-280">any string</span></span> |
| <span data-ttu-id="9cd87-281">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-281">**Comments**</span></span> | <span data-ttu-id="9cd87-282">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="9cd87-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="9cd87-283">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="9cd87-283">Allowed threats</span></span>

<span data-ttu-id="9cd87-284">按名称指定未由 Mac 上的 Defender for Endpoint 阻止的威胁。</span><span class="sxs-lookup"><span data-stu-id="9cd87-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="9cd87-285">将允许运行这些威胁。</span><span class="sxs-lookup"><span data-stu-id="9cd87-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="9cd87-286">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-286">Section</span></span>|<span data-ttu-id="9cd87-287">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-288">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-289">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-289">**Key**</span></span> | <span data-ttu-id="9cd87-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="9cd87-290">allowedThreats</span></span> |
| <span data-ttu-id="9cd87-291">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-291">**Data type**</span></span> | <span data-ttu-id="9cd87-292">字符串数组</span><span class="sxs-lookup"><span data-stu-id="9cd87-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="9cd87-293">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="9cd87-293">Disallowed threat actions</span></span>

<span data-ttu-id="9cd87-294">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="9cd87-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="9cd87-295">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="9cd87-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="9cd87-296">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-296">Section</span></span>|<span data-ttu-id="9cd87-297">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-298">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-299">**Key**</span></span> | <span data-ttu-id="9cd87-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="9cd87-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="9cd87-301">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-301">**Data type**</span></span> | <span data-ttu-id="9cd87-302">字符串数组</span><span class="sxs-lookup"><span data-stu-id="9cd87-302">Array of strings</span></span> |
| <span data-ttu-id="9cd87-303">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-303">**Possible values**</span></span> | <span data-ttu-id="9cd87-304">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="9cd87-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="9cd87-305">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="9cd87-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="9cd87-306">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-306">**Comments**</span></span> | <span data-ttu-id="9cd87-307">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="9cd87-308">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="9cd87-308">Threat type settings</span></span>

<span data-ttu-id="9cd87-309">指定 macOS 上的 Microsoft Defender for Endpoint 如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="9cd87-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9cd87-310">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-310">Section</span></span>|<span data-ttu-id="9cd87-311">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-312">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-313">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-313">**Key**</span></span> | <span data-ttu-id="9cd87-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="9cd87-314">threatTypeSettings</span></span> |
| <span data-ttu-id="9cd87-315">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-315">**Data type**</span></span> | <span data-ttu-id="9cd87-316">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-317">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-317">**Comments**</span></span> | <span data-ttu-id="9cd87-318">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="9cd87-319">威胁类型</span><span class="sxs-lookup"><span data-stu-id="9cd87-319">Threat type</span></span>

<span data-ttu-id="9cd87-320">指定威胁类型。</span><span class="sxs-lookup"><span data-stu-id="9cd87-320">Specify threat types.</span></span>

|<span data-ttu-id="9cd87-321">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-321">Section</span></span>|<span data-ttu-id="9cd87-322">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-323">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-324">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-324">**Key**</span></span> | <span data-ttu-id="9cd87-325">注册表项</span><span class="sxs-lookup"><span data-stu-id="9cd87-325">key</span></span> |
| <span data-ttu-id="9cd87-326">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-326">**Data type**</span></span> | <span data-ttu-id="9cd87-327">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-327">String</span></span> |
| <span data-ttu-id="9cd87-328">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-328">**Possible values**</span></span> | <span data-ttu-id="9cd87-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="9cd87-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="9cd87-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="9cd87-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="9cd87-331">要采取的措施</span><span class="sxs-lookup"><span data-stu-id="9cd87-331">Action to take</span></span>

<span data-ttu-id="9cd87-332">指定在检测到上一节中指定的类型的威胁时要采取什么操作。</span><span class="sxs-lookup"><span data-stu-id="9cd87-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="9cd87-333">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="9cd87-333">Choose from the following options:</span></span>

- <span data-ttu-id="9cd87-334">**审核**：你的设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="9cd87-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="9cd87-335">**阻止**：你的设备受到此类型威胁的保护，并且你将在用户界面和安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="9cd87-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="9cd87-336">**关闭**：你的设备不受此类型威胁的防御，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="9cd87-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="9cd87-337">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-337">Section</span></span>|<span data-ttu-id="9cd87-338">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-339">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-340">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-340">**Key**</span></span> | <span data-ttu-id="9cd87-341">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-341">value</span></span> |
| <span data-ttu-id="9cd87-342">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-342">**Data type**</span></span> | <span data-ttu-id="9cd87-343">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-343">String</span></span> |
| <span data-ttu-id="9cd87-344">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-344">**Possible values**</span></span> | <span data-ttu-id="9cd87-345">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="9cd87-345">audit (default)</span></span> <br/> <span data-ttu-id="9cd87-346">block</span><span class="sxs-lookup"><span data-stu-id="9cd87-346">block</span></span> <br/> <span data-ttu-id="9cd87-347">off</span><span class="sxs-lookup"><span data-stu-id="9cd87-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="9cd87-348">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="9cd87-348">Threat type settings merge policy</span></span>

<span data-ttu-id="9cd87-349">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="9cd87-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="9cd87-350">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="9cd87-351">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="9cd87-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="9cd87-352">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-352">Section</span></span>|<span data-ttu-id="9cd87-353">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-354">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-355">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-355">**Key**</span></span> | <span data-ttu-id="9cd87-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9cd87-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="9cd87-357">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-357">**Data type**</span></span> | <span data-ttu-id="9cd87-358">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-358">String</span></span> |
| <span data-ttu-id="9cd87-359">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-359">**Possible values**</span></span> | <span data-ttu-id="9cd87-360">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="9cd87-360">merge (default)</span></span> <br/> <span data-ttu-id="9cd87-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="9cd87-361">admin_only</span></span> |
| <span data-ttu-id="9cd87-362">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-362">**Comments**</span></span> | <span data-ttu-id="9cd87-363">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="9cd87-364">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="9cd87-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="9cd87-365">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="9cd87-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="9cd87-366">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="9cd87-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="9cd87-367">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="9cd87-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="9cd87-368">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-368">Section</span></span>|<span data-ttu-id="9cd87-369">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-370">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-371">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-371">**Key**</span></span> | <span data-ttu-id="9cd87-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="9cd87-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="9cd87-373">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-373">**Data type**</span></span> | <span data-ttu-id="9cd87-374">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-374">String</span></span> |
| <span data-ttu-id="9cd87-375">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-375">**Possible values**</span></span> | <span data-ttu-id="9cd87-376">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-376">90 (default).</span></span> <span data-ttu-id="9cd87-377">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="9cd87-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="9cd87-378">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-378">**Comments**</span></span> | <span data-ttu-id="9cd87-379">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="9cd87-380">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="9cd87-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="9cd87-381">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="9cd87-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="9cd87-382">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="9cd87-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="9cd87-383">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-383">Section</span></span>|<span data-ttu-id="9cd87-384">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-385">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-386">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-386">**Key**</span></span> | <span data-ttu-id="9cd87-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="9cd87-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="9cd87-388">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-388">**Data type**</span></span> | <span data-ttu-id="9cd87-389">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-389">String</span></span> |
| <span data-ttu-id="9cd87-390">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-390">**Possible values**</span></span> | <span data-ttu-id="9cd87-391">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-391">10000 (default).</span></span> <span data-ttu-id="9cd87-392">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="9cd87-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="9cd87-393">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-393">**Comments**</span></span> | <span data-ttu-id="9cd87-394">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="9cd87-395">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="9cd87-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="9cd87-396">在 macOS 上配置 Microsoft Defender for Endpoint 的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="9cd87-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9cd87-397">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-397">Section</span></span>|<span data-ttu-id="9cd87-398">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-399">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-400">**Key**</span></span> | <span data-ttu-id="9cd87-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="9cd87-401">cloudService</span></span> |
| <span data-ttu-id="9cd87-402">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-402">**Data type**</span></span> | <span data-ttu-id="9cd87-403">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-404">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-404">**Comments**</span></span> | <span data-ttu-id="9cd87-405">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="9cd87-406">启用/禁用云保护</span><span class="sxs-lookup"><span data-stu-id="9cd87-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="9cd87-407">指定是否启用云保护设备。</span><span class="sxs-lookup"><span data-stu-id="9cd87-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="9cd87-408">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="9cd87-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="9cd87-409">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-409">Section</span></span>|<span data-ttu-id="9cd87-410">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-411">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-412">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-412">**Key**</span></span> | <span data-ttu-id="9cd87-413">enabled</span><span class="sxs-lookup"><span data-stu-id="9cd87-413">enabled</span></span> |
| <span data-ttu-id="9cd87-414">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-414">**Data type**</span></span> | <span data-ttu-id="9cd87-415">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-415">Boolean</span></span> |
| <span data-ttu-id="9cd87-416">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-416">**Possible values**</span></span> | <span data-ttu-id="9cd87-417">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="9cd87-417">true (default)</span></span> <br/> <span data-ttu-id="9cd87-418">false</span><span class="sxs-lookup"><span data-stu-id="9cd87-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="9cd87-419">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="9cd87-419">Diagnostic collection level</span></span>

<span data-ttu-id="9cd87-420">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="9cd87-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="9cd87-421">此设置确定 Microsoft Defender for Endpoint 发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="9cd87-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="9cd87-422">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-422">Section</span></span>|<span data-ttu-id="9cd87-423">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-424">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-425">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-425">**Key**</span></span> | <span data-ttu-id="9cd87-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="9cd87-426">diagnosticLevel</span></span> |
| <span data-ttu-id="9cd87-427">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-427">**Data type**</span></span> | <span data-ttu-id="9cd87-428">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-428">String</span></span> |
| <span data-ttu-id="9cd87-429">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-429">**Possible values**</span></span> | <span data-ttu-id="9cd87-430">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="9cd87-430">optional (default)</span></span> <br/> <span data-ttu-id="9cd87-431">必需</span><span class="sxs-lookup"><span data-stu-id="9cd87-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="9cd87-432">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="9cd87-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="9cd87-433">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9cd87-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="9cd87-434">系统将提示你提交的文件是否可能包含个人信息。</span><span class="sxs-lookup"><span data-stu-id="9cd87-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="9cd87-435">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-435">Section</span></span>|<span data-ttu-id="9cd87-436">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-437">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-438">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-438">**Key**</span></span> | <span data-ttu-id="9cd87-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="9cd87-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="9cd87-440">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-440">**Data type**</span></span> | <span data-ttu-id="9cd87-441">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-441">Boolean</span></span> |
| <span data-ttu-id="9cd87-442">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-442">**Possible values**</span></span> | <span data-ttu-id="9cd87-443">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="9cd87-443">true (default)</span></span> <br/> <span data-ttu-id="9cd87-444">false</span><span class="sxs-lookup"><span data-stu-id="9cd87-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="9cd87-445">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="9cd87-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="9cd87-446">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="9cd87-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="9cd87-447">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-447">Section</span></span>|<span data-ttu-id="9cd87-448">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-449">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-449">**Key**</span></span> | <span data-ttu-id="9cd87-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="9cd87-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="9cd87-451">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-451">**Data type**</span></span> | <span data-ttu-id="9cd87-452">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-452">Boolean</span></span> |
| <span data-ttu-id="9cd87-453">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-453">**Possible values**</span></span> | <span data-ttu-id="9cd87-454">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="9cd87-454">true (default)</span></span> <br/> <span data-ttu-id="9cd87-455">false</span><span class="sxs-lookup"><span data-stu-id="9cd87-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="9cd87-456">用户界面首选项</span><span class="sxs-lookup"><span data-stu-id="9cd87-456">User interface preferences</span></span>

<span data-ttu-id="9cd87-457">管理 macOS 上适用于终结点的 Microsoft Defender 用户界面的首选项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9cd87-458">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-458">Section</span></span>|<span data-ttu-id="9cd87-459">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-460">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-461">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-461">**Key**</span></span> | <span data-ttu-id="9cd87-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="9cd87-462">userInterface</span></span> |
| <span data-ttu-id="9cd87-463">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-463">**Data type**</span></span> | <span data-ttu-id="9cd87-464">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-465">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-465">**Comments**</span></span> | <span data-ttu-id="9cd87-466">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="9cd87-467">显示/隐藏状态菜单图标</span><span class="sxs-lookup"><span data-stu-id="9cd87-467">Show / hide status menu icon</span></span>

<span data-ttu-id="9cd87-468">指定是显示还是隐藏屏幕右上角的状态菜单图标。</span><span class="sxs-lookup"><span data-stu-id="9cd87-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="9cd87-469">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-469">Section</span></span>|<span data-ttu-id="9cd87-470">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-471">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-472">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-472">**Key**</span></span> | <span data-ttu-id="9cd87-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="9cd87-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="9cd87-474">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-474">**Data type**</span></span> | <span data-ttu-id="9cd87-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="9cd87-475">Boolean</span></span> |
| <span data-ttu-id="9cd87-476">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-476">**Possible values**</span></span> | <span data-ttu-id="9cd87-477">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="9cd87-477">false (default)</span></span> <br/> <span data-ttu-id="9cd87-478">true</span><span class="sxs-lookup"><span data-stu-id="9cd87-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="9cd87-479">显示/隐藏发送反馈的选项</span><span class="sxs-lookup"><span data-stu-id="9cd87-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="9cd87-480">指定用户是否可以通过访问 向 Microsoft 提交反馈 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="9cd87-481">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-481">Section</span></span>|<span data-ttu-id="9cd87-482">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-483">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-484">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-484">**Key**</span></span> | <span data-ttu-id="9cd87-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="9cd87-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="9cd87-486">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-486">**Data type**</span></span> | <span data-ttu-id="9cd87-487">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-487">String</span></span> |
| <span data-ttu-id="9cd87-488">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-488">**Possible values**</span></span> | <span data-ttu-id="9cd87-489">已启用 (默认) </span><span class="sxs-lookup"><span data-stu-id="9cd87-489">enabled (default)</span></span> <br/> <span data-ttu-id="9cd87-490">disabled</span><span class="sxs-lookup"><span data-stu-id="9cd87-490">disabled</span></span> |
| <span data-ttu-id="9cd87-491">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-491">**Comments**</span></span> | <span data-ttu-id="9cd87-492">适用于终结点版本 101.19.61 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="9cd87-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="9cd87-493">终结点检测和响应首选项</span><span class="sxs-lookup"><span data-stu-id="9cd87-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="9cd87-494">管理 macOS 上 Microsoft Defender for Endpoint (EDR) 的终结点检测和响应的首选项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="9cd87-495">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-495">Section</span></span>|<span data-ttu-id="9cd87-496">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-497">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-498">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-498">**Key**</span></span> | <span data-ttu-id="9cd87-499">edr</span><span class="sxs-lookup"><span data-stu-id="9cd87-499">edr</span></span> |
| <span data-ttu-id="9cd87-500">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-500">**Data type**</span></span> | <span data-ttu-id="9cd87-501">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-502">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-502">**Comments**</span></span> | <span data-ttu-id="9cd87-503">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="9cd87-504">设备标记</span><span class="sxs-lookup"><span data-stu-id="9cd87-504">Device tags</span></span>

<span data-ttu-id="9cd87-505">指定标记名称及其值。</span><span class="sxs-lookup"><span data-stu-id="9cd87-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="9cd87-506">GROUP 标记使用指定值标记设备。</span><span class="sxs-lookup"><span data-stu-id="9cd87-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="9cd87-507">标记反映在设备页面下的门户中，可用于筛选和分组设备。</span><span class="sxs-lookup"><span data-stu-id="9cd87-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="9cd87-508">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-508">Section</span></span>|<span data-ttu-id="9cd87-509">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-510">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-511">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-511">**Key**</span></span> | <span data-ttu-id="9cd87-512">tags</span><span class="sxs-lookup"><span data-stu-id="9cd87-512">tags</span></span> |
| <span data-ttu-id="9cd87-513">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-513">**Data type**</span></span> | <span data-ttu-id="9cd87-514">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="9cd87-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9cd87-515">**备注**</span><span class="sxs-lookup"><span data-stu-id="9cd87-515">**Comments**</span></span> | <span data-ttu-id="9cd87-516">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="9cd87-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="9cd87-517">标记类型</span><span class="sxs-lookup"><span data-stu-id="9cd87-517">Type of tag</span></span>

<span data-ttu-id="9cd87-518">指定标记的类型</span><span class="sxs-lookup"><span data-stu-id="9cd87-518">Specifies the type of tag</span></span>

|<span data-ttu-id="9cd87-519">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-519">Section</span></span>|<span data-ttu-id="9cd87-520">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-521">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-522">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-522">**Key**</span></span> | <span data-ttu-id="9cd87-523">注册表项</span><span class="sxs-lookup"><span data-stu-id="9cd87-523">key</span></span> |
| <span data-ttu-id="9cd87-524">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-524">**Data type**</span></span> | <span data-ttu-id="9cd87-525">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-525">String</span></span> |
| <span data-ttu-id="9cd87-526">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="9cd87-527">tag 的值</span><span class="sxs-lookup"><span data-stu-id="9cd87-527">Value of tag</span></span>

<span data-ttu-id="9cd87-528">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="9cd87-528">Specifies the value of tag</span></span>

|<span data-ttu-id="9cd87-529">节</span><span class="sxs-lookup"><span data-stu-id="9cd87-529">Section</span></span>|<span data-ttu-id="9cd87-530">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9cd87-531">**域**</span><span class="sxs-lookup"><span data-stu-id="9cd87-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9cd87-532">**Key**</span><span class="sxs-lookup"><span data-stu-id="9cd87-532">**Key**</span></span> | <span data-ttu-id="9cd87-533">值</span><span class="sxs-lookup"><span data-stu-id="9cd87-533">value</span></span> |
| <span data-ttu-id="9cd87-534">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd87-534">**Data type**</span></span> | <span data-ttu-id="9cd87-535">String</span><span class="sxs-lookup"><span data-stu-id="9cd87-535">String</span></span> |
| <span data-ttu-id="9cd87-536">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cd87-536">**Possible values**</span></span> | <span data-ttu-id="9cd87-537">任何字符串</span><span class="sxs-lookup"><span data-stu-id="9cd87-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="9cd87-538">每个标记类型只能设置一个值。</span><span class="sxs-lookup"><span data-stu-id="9cd87-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="9cd87-539">标记类型是唯一的，并且不应在同一配置文件中重复。</span><span class="sxs-lookup"><span data-stu-id="9cd87-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="9cd87-540">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-540">Recommended configuration profile</span></span>

<span data-ttu-id="9cd87-541">若要开始，我们建议你的企业采用以下配置，以利用 Microsoft Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="9cd87-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="9cd87-542">以下配置文件 (，或者，对于 JAMF，可以上载到自定义设置配置文件中的属性列表) ：</span><span class="sxs-lookup"><span data-stu-id="9cd87-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="9cd87-543">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="9cd87-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="9cd87-544">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="9cd87-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="9cd87-545">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="9cd87-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="9cd87-546">**使用高** (率存档存档) 将审核到 Microsoft Defender 终结点日志</span><span class="sxs-lookup"><span data-stu-id="9cd87-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="9cd87-547">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="9cd87-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="9cd87-548">启用云保护</span><span class="sxs-lookup"><span data-stu-id="9cd87-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="9cd87-549">启用自动提交示例</span><span class="sxs-lookup"><span data-stu-id="9cd87-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9cd87-550">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="9cd87-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="9cd87-551">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="9cd87-552">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="9cd87-552">Full configuration profile example</span></span>

<span data-ttu-id="9cd87-553">以下模板包含本文档中所述的所有设置的条目，可用于更高级的方案，你想要在 macOS 上对 Microsoft Defender for Endpoint 进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="9cd87-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9cd87-554">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="9cd87-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="9cd87-555">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="9cd87-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="9cd87-556">属性列表验证</span><span class="sxs-lookup"><span data-stu-id="9cd87-556">Property list validation</span></span>

<span data-ttu-id="9cd87-557">属性列表必须是有效的 *.plist* 文件。</span><span class="sxs-lookup"><span data-stu-id="9cd87-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="9cd87-558">可通过执行：</span><span class="sxs-lookup"><span data-stu-id="9cd87-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="9cd87-559">如果文件格式良好，则上述命令将输出 `OK` 并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="9cd87-560">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="9cd87-561">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="9cd87-561">Configuration profile deployment</span></span>

<span data-ttu-id="9cd87-562">为企业生成配置文件后，可以通过企业使用的管理控制台部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="9cd87-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="9cd87-563">以下各节提供有关如何使用 JAMF 和 Intune 部署此配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="9cd87-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="9cd87-564">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="9cd87-564">JAMF deployment</span></span>

<span data-ttu-id="9cd87-565">从 JAMF 控制台中，打开 **计算机** 配置文件，导航到你要使用的配置文件，  >  然后选择自定义设置。 </span><span class="sxs-lookup"><span data-stu-id="9cd87-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="9cd87-566">使用 创建用作 `com.microsoft.wdav` 首选项域的条目并上载之前生成的 *.plist。*</span><span class="sxs-lookup"><span data-stu-id="9cd87-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="9cd87-567">必须输入正确的首选项域 `com.microsoft.wdav` () ;否则，Microsoft Defender for Endpoint 无法识别首选项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="9cd87-568">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="9cd87-568">Intune deployment</span></span>

1. <span data-ttu-id="9cd87-569">打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="9cd87-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="9cd87-570">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="9cd87-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="9cd87-571">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9cd87-571">Choose a name for the profile.</span></span> <span data-ttu-id="9cd87-572">将 **Platform=macOS** 更改为 **配置文件类型=自定义**。</span><span class="sxs-lookup"><span data-stu-id="9cd87-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="9cd87-573">选择"配置"。</span><span class="sxs-lookup"><span data-stu-id="9cd87-573">Select Configure.</span></span>

3. <span data-ttu-id="9cd87-574">将之前生成的 .plist 另存为 `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="9cd87-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="9cd87-575">输入 `com.microsoft.wdav` 作为 **自定义配置文件名称**。</span><span class="sxs-lookup"><span data-stu-id="9cd87-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="9cd87-576">打开配置文件并上载 `com.microsoft.wdav.xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="9cd87-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="9cd87-577"> (此文件是在步骤 3.) </span><span class="sxs-lookup"><span data-stu-id="9cd87-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="9cd87-578">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9cd87-578">Select **OK**.</span></span>

7. <span data-ttu-id="9cd87-579">选择 **"管理**  >  **工作分配"。**</span><span class="sxs-lookup"><span data-stu-id="9cd87-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="9cd87-580">在"**包含"** 选项卡中，**选择"分配给&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="9cd87-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="9cd87-581">必须输入正确的自定义配置文件名称;否则，Microsoft Defender for Endpoint 无法识别这些首选项。</span><span class="sxs-lookup"><span data-stu-id="9cd87-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="9cd87-582">资源</span><span class="sxs-lookup"><span data-stu-id="9cd87-582">Resources</span></span>

- [<span data-ttu-id="9cd87-583">配置文件首选项（Apple 开发人员文档）</span><span class="sxs-lookup"><span data-stu-id="9cd87-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
