---
title: 设置适用于 Mac 的 Microsoft Defender 终结点的首选项
description: 在企业组织中配置适用于 Mac 的 Microsoft Defender for Endpoint。
keywords: microsoft， defender， atp， mac， 管理， 首选项， 企业， intune， jamf， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860915"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="235bb-104">在 macOS 上设置适用于终结点的 Microsoft Defender 的首选项</span><span class="sxs-lookup"><span data-stu-id="235bb-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="235bb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="235bb-105">**Applies to:**</span></span>

- [<span data-ttu-id="235bb-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="235bb-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="235bb-107">本文包含有关如何在企业组织中为 macOS 上的 Microsoft Defender for Endpoint 设置首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="235bb-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="235bb-108">若要使用命令行界面在 macOS 上配置适用于终结点的 Microsoft Defender，请参阅 [资源](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="235bb-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="235bb-109">摘要</span><span class="sxs-lookup"><span data-stu-id="235bb-109">Summary</span></span>

<span data-ttu-id="235bb-110">在企业组织中，可以通过使用多种管理工具之一部署的配置文件管理 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="235bb-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="235bb-111">由安全操作团队管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="235bb-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="235bb-112">更改通过配置文件设置的首选项需要提升的权限，并且对于没有管理权限的用户不可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="235bb-113">本文介绍配置文件的结构，包括可用于入门的推荐配置文件，并提供有关如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="235bb-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="235bb-114">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="235bb-114">Configuration profile structure</span></span>

<span data-ttu-id="235bb-115">配置文件是一个 *.plist* 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="235bb-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="235bb-116">值可以是简单的 (，如数值) 或复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="235bb-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="235bb-117">配置文件的布局取决于你使用的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="235bb-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="235bb-118">以下各节包含 JAMF 和 Intune 的配置文件示例。</span><span class="sxs-lookup"><span data-stu-id="235bb-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="235bb-119">配置文件的顶级包括产品范围的首选项和 Microsoft Defender for Endpoint 子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="235bb-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="235bb-120">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="235bb-120">Antivirus engine preferences</span></span>

<span data-ttu-id="235bb-121">配置文件 *的 antivirusEngine* 部分用于管理 Microsoft Defender for Endpoint 的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="235bb-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="235bb-122">节</span><span class="sxs-lookup"><span data-stu-id="235bb-122">Section</span></span>|<span data-ttu-id="235bb-123">值</span><span class="sxs-lookup"><span data-stu-id="235bb-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-124">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-125">**Key**</span></span> | <span data-ttu-id="235bb-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="235bb-126">antivirusEngine</span></span> |
| <span data-ttu-id="235bb-127">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-127">**Data type**</span></span> | <span data-ttu-id="235bb-128">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-129">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-129">**Comments**</span></span> | <span data-ttu-id="235bb-130">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="235bb-131">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="235bb-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="235bb-132">指定是否启用实时保护，以在访问文件时对文件进行扫描。</span><span class="sxs-lookup"><span data-stu-id="235bb-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="235bb-133">节</span><span class="sxs-lookup"><span data-stu-id="235bb-133">Section</span></span>|<span data-ttu-id="235bb-134">值</span><span class="sxs-lookup"><span data-stu-id="235bb-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-135">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-136">**Key**</span></span> | <span data-ttu-id="235bb-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="235bb-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="235bb-138">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-138">**Data type**</span></span> | <span data-ttu-id="235bb-139">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-139">Boolean</span></span> |
| <span data-ttu-id="235bb-140">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-140">**Possible values**</span></span> | <span data-ttu-id="235bb-141">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="235bb-141">true (default)</span></span> <br/> <span data-ttu-id="235bb-142">false</span><span class="sxs-lookup"><span data-stu-id="235bb-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="235bb-143">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="235bb-143">Enable / disable passive mode</span></span>

<span data-ttu-id="235bb-144">指定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="235bb-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="235bb-145">被动模式具有以下含义：</span><span class="sxs-lookup"><span data-stu-id="235bb-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="235bb-146">实时保护已关闭</span><span class="sxs-lookup"><span data-stu-id="235bb-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="235bb-147">按需扫描已打开</span><span class="sxs-lookup"><span data-stu-id="235bb-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="235bb-148">自动威胁修正已关闭</span><span class="sxs-lookup"><span data-stu-id="235bb-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="235bb-149">启用安全智能更新</span><span class="sxs-lookup"><span data-stu-id="235bb-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="235bb-150">状态菜单图标处于隐藏状态</span><span class="sxs-lookup"><span data-stu-id="235bb-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="235bb-151">节</span><span class="sxs-lookup"><span data-stu-id="235bb-151">Section</span></span>|<span data-ttu-id="235bb-152">值</span><span class="sxs-lookup"><span data-stu-id="235bb-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-153">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-154">**Key**</span></span> | <span data-ttu-id="235bb-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="235bb-155">passiveMode</span></span> |
| <span data-ttu-id="235bb-156">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-156">**Data type**</span></span> | <span data-ttu-id="235bb-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-157">Boolean</span></span> |
| <span data-ttu-id="235bb-158">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-158">**Possible values**</span></span> | <span data-ttu-id="235bb-159">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="235bb-159">false (default)</span></span> <br/> <span data-ttu-id="235bb-160">true</span><span class="sxs-lookup"><span data-stu-id="235bb-160">true</span></span> |
| <span data-ttu-id="235bb-161">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-161">**Comments**</span></span> | <span data-ttu-id="235bb-162">适用于终结点版本 100.67.60 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="235bb-163">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="235bb-163">Exclusion merge policy</span></span>

<span data-ttu-id="235bb-164">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="235bb-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="235bb-165">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="235bb-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="235bb-166">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="235bb-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="235bb-167">节</span><span class="sxs-lookup"><span data-stu-id="235bb-167">Section</span></span>|<span data-ttu-id="235bb-168">值</span><span class="sxs-lookup"><span data-stu-id="235bb-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-169">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-170">**Key**</span></span> | <span data-ttu-id="235bb-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="235bb-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="235bb-172">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-172">**Data type**</span></span> | <span data-ttu-id="235bb-173">String</span><span class="sxs-lookup"><span data-stu-id="235bb-173">String</span></span> |
| <span data-ttu-id="235bb-174">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-174">**Possible values**</span></span> | <span data-ttu-id="235bb-175">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="235bb-175">merge (default)</span></span> <br/> <span data-ttu-id="235bb-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="235bb-176">admin_only</span></span> |
| <span data-ttu-id="235bb-177">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-177">**Comments**</span></span> | <span data-ttu-id="235bb-178">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="235bb-179">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="235bb-179">Scan exclusions</span></span>

<span data-ttu-id="235bb-180">指定被扫描排除的实体。</span><span class="sxs-lookup"><span data-stu-id="235bb-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="235bb-181">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="235bb-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="235bb-182">节</span><span class="sxs-lookup"><span data-stu-id="235bb-182">Section</span></span>|<span data-ttu-id="235bb-183">值</span><span class="sxs-lookup"><span data-stu-id="235bb-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-184">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-185">**Key**</span></span> | <span data-ttu-id="235bb-186">排除项</span><span class="sxs-lookup"><span data-stu-id="235bb-186">exclusions</span></span> |
| <span data-ttu-id="235bb-187">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-187">**Data type**</span></span> | <span data-ttu-id="235bb-188">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-189">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-189">**Comments**</span></span> | <span data-ttu-id="235bb-190">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="235bb-191">排除类型</span><span class="sxs-lookup"><span data-stu-id="235bb-191">Type of exclusion</span></span>

<span data-ttu-id="235bb-192">按类型指定被排除的内容。</span><span class="sxs-lookup"><span data-stu-id="235bb-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="235bb-193">节</span><span class="sxs-lookup"><span data-stu-id="235bb-193">Section</span></span>|<span data-ttu-id="235bb-194">值</span><span class="sxs-lookup"><span data-stu-id="235bb-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-195">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-196">**Key**</span></span> | <span data-ttu-id="235bb-197">$type</span><span class="sxs-lookup"><span data-stu-id="235bb-197">$type</span></span> |
| <span data-ttu-id="235bb-198">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-198">**Data type**</span></span> | <span data-ttu-id="235bb-199">String</span><span class="sxs-lookup"><span data-stu-id="235bb-199">String</span></span> |
| <span data-ttu-id="235bb-200">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-200">**Possible values**</span></span> | <span data-ttu-id="235bb-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="235bb-201">excludedPath</span></span> <br/> <span data-ttu-id="235bb-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="235bb-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="235bb-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="235bb-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="235bb-204">排除内容的路径</span><span class="sxs-lookup"><span data-stu-id="235bb-204">Path to excluded content</span></span>

<span data-ttu-id="235bb-205">指定未由完整文件路径扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="235bb-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="235bb-206">节</span><span class="sxs-lookup"><span data-stu-id="235bb-206">Section</span></span>|<span data-ttu-id="235bb-207">值</span><span class="sxs-lookup"><span data-stu-id="235bb-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-208">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-209">**Key**</span></span> | <span data-ttu-id="235bb-210">path</span><span class="sxs-lookup"><span data-stu-id="235bb-210">path</span></span> |
| <span data-ttu-id="235bb-211">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-211">**Data type**</span></span> | <span data-ttu-id="235bb-212">String</span><span class="sxs-lookup"><span data-stu-id="235bb-212">String</span></span> |
| <span data-ttu-id="235bb-213">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-213">**Possible values**</span></span> | <span data-ttu-id="235bb-214">有效路径</span><span class="sxs-lookup"><span data-stu-id="235bb-214">valid paths</span></span> |
| <span data-ttu-id="235bb-215">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-215">**Comments**</span></span> | <span data-ttu-id="235bb-216">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="235bb-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="235bb-217">文件 (目录的路径) </span><span class="sxs-lookup"><span data-stu-id="235bb-217">Path type (file / directory)</span></span>

<span data-ttu-id="235bb-218">指示 *path 属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="235bb-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="235bb-219">节</span><span class="sxs-lookup"><span data-stu-id="235bb-219">Section</span></span>|<span data-ttu-id="235bb-220">值</span><span class="sxs-lookup"><span data-stu-id="235bb-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-221">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-222">**Key**</span></span> | <span data-ttu-id="235bb-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="235bb-223">isDirectory</span></span> |
| <span data-ttu-id="235bb-224">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-224">**Data type**</span></span> | <span data-ttu-id="235bb-225">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-225">Boolean</span></span> |
| <span data-ttu-id="235bb-226">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-226">**Possible values**</span></span> | <span data-ttu-id="235bb-227">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="235bb-227">false (default)</span></span> <br/> <span data-ttu-id="235bb-228">true</span><span class="sxs-lookup"><span data-stu-id="235bb-228">true</span></span> |
| <span data-ttu-id="235bb-229">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-229">**Comments**</span></span> | <span data-ttu-id="235bb-230">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="235bb-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="235bb-231">从扫描中排除的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="235bb-231">File extension excluded from the scan</span></span>

<span data-ttu-id="235bb-232">指定文件扩展名无法扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="235bb-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="235bb-233">节</span><span class="sxs-lookup"><span data-stu-id="235bb-233">Section</span></span>|<span data-ttu-id="235bb-234">值</span><span class="sxs-lookup"><span data-stu-id="235bb-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-235">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-236">**Key**</span></span> | <span data-ttu-id="235bb-237">extension</span><span class="sxs-lookup"><span data-stu-id="235bb-237">extension</span></span> |
| <span data-ttu-id="235bb-238">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-238">**Data type**</span></span> | <span data-ttu-id="235bb-239">String</span><span class="sxs-lookup"><span data-stu-id="235bb-239">String</span></span> |
| <span data-ttu-id="235bb-240">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-240">**Possible values**</span></span> | <span data-ttu-id="235bb-241">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="235bb-241">valid file extensions</span></span> |
| <span data-ttu-id="235bb-242">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-242">**Comments**</span></span> | <span data-ttu-id="235bb-243">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="235bb-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="235bb-244">从扫描中排除的进程</span><span class="sxs-lookup"><span data-stu-id="235bb-244">Process excluded from the scan</span></span>

<span data-ttu-id="235bb-245">指定一个进程，所有文件活动都从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="235bb-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="235bb-246">可以通过进程的名称指定进程， (例如) 或完整路径 (`cat` 例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="235bb-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="235bb-247">节</span><span class="sxs-lookup"><span data-stu-id="235bb-247">Section</span></span>|<span data-ttu-id="235bb-248">值</span><span class="sxs-lookup"><span data-stu-id="235bb-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-249">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-250">**Key**</span></span> | <span data-ttu-id="235bb-251">name</span><span class="sxs-lookup"><span data-stu-id="235bb-251">name</span></span> |
| <span data-ttu-id="235bb-252">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-252">**Data type**</span></span> | <span data-ttu-id="235bb-253">String</span><span class="sxs-lookup"><span data-stu-id="235bb-253">String</span></span> |
| <span data-ttu-id="235bb-254">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-254">**Possible values**</span></span> | <span data-ttu-id="235bb-255">任何字符串</span><span class="sxs-lookup"><span data-stu-id="235bb-255">any string</span></span> |
| <span data-ttu-id="235bb-256">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-256">**Comments**</span></span> | <span data-ttu-id="235bb-257">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="235bb-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="235bb-258">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="235bb-258">Allowed threats</span></span>

<span data-ttu-id="235bb-259">按名称指定未由 Defender for Endpoint for Mac 阻止的威胁。</span><span class="sxs-lookup"><span data-stu-id="235bb-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="235bb-260">将允许运行这些威胁。</span><span class="sxs-lookup"><span data-stu-id="235bb-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="235bb-261">节</span><span class="sxs-lookup"><span data-stu-id="235bb-261">Section</span></span>|<span data-ttu-id="235bb-262">值</span><span class="sxs-lookup"><span data-stu-id="235bb-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-263">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-264">**Key**</span></span> | <span data-ttu-id="235bb-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="235bb-265">allowedThreats</span></span> |
| <span data-ttu-id="235bb-266">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-266">**Data type**</span></span> | <span data-ttu-id="235bb-267">字符串数组</span><span class="sxs-lookup"><span data-stu-id="235bb-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="235bb-268">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="235bb-268">Disallowed threat actions</span></span>

<span data-ttu-id="235bb-269">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="235bb-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="235bb-270">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="235bb-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="235bb-271">节</span><span class="sxs-lookup"><span data-stu-id="235bb-271">Section</span></span>|<span data-ttu-id="235bb-272">值</span><span class="sxs-lookup"><span data-stu-id="235bb-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-273">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-274">**Key**</span></span> | <span data-ttu-id="235bb-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="235bb-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="235bb-276">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-276">**Data type**</span></span> | <span data-ttu-id="235bb-277">字符串数组</span><span class="sxs-lookup"><span data-stu-id="235bb-277">Array of strings</span></span> |
| <span data-ttu-id="235bb-278">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-278">**Possible values**</span></span> | <span data-ttu-id="235bb-279">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="235bb-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="235bb-280">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="235bb-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="235bb-281">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-281">**Comments**</span></span> | <span data-ttu-id="235bb-282">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="235bb-283">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="235bb-283">Threat type settings</span></span>

<span data-ttu-id="235bb-284">指定 macOS 上的 Microsoft Defender for Endpoint 如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="235bb-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="235bb-285">节</span><span class="sxs-lookup"><span data-stu-id="235bb-285">Section</span></span>|<span data-ttu-id="235bb-286">值</span><span class="sxs-lookup"><span data-stu-id="235bb-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-287">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-288">**Key**</span></span> | <span data-ttu-id="235bb-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="235bb-289">threatTypeSettings</span></span> |
| <span data-ttu-id="235bb-290">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-290">**Data type**</span></span> | <span data-ttu-id="235bb-291">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-292">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-292">**Comments**</span></span> | <span data-ttu-id="235bb-293">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="235bb-294">威胁类型</span><span class="sxs-lookup"><span data-stu-id="235bb-294">Threat type</span></span>

<span data-ttu-id="235bb-295">指定威胁类型。</span><span class="sxs-lookup"><span data-stu-id="235bb-295">Specify threat types.</span></span>

|<span data-ttu-id="235bb-296">节</span><span class="sxs-lookup"><span data-stu-id="235bb-296">Section</span></span>|<span data-ttu-id="235bb-297">值</span><span class="sxs-lookup"><span data-stu-id="235bb-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-298">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-299">**Key**</span></span> | <span data-ttu-id="235bb-300">注册表项</span><span class="sxs-lookup"><span data-stu-id="235bb-300">key</span></span> |
| <span data-ttu-id="235bb-301">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-301">**Data type**</span></span> | <span data-ttu-id="235bb-302">String</span><span class="sxs-lookup"><span data-stu-id="235bb-302">String</span></span> |
| <span data-ttu-id="235bb-303">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-303">**Possible values**</span></span> | <span data-ttu-id="235bb-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="235bb-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="235bb-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="235bb-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="235bb-306">要采取的措施</span><span class="sxs-lookup"><span data-stu-id="235bb-306">Action to take</span></span>

<span data-ttu-id="235bb-307">指定在检测到上一节中指定的类型的威胁时要采取什么操作。</span><span class="sxs-lookup"><span data-stu-id="235bb-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="235bb-308">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="235bb-308">Choose from the following options:</span></span>

- <span data-ttu-id="235bb-309">**审核**：你的设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="235bb-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="235bb-310">**阻止**：你的设备受到此类型威胁的保护，并且你将在用户界面和安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="235bb-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="235bb-311">**关闭**：你的设备不受此类型威胁的防御，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="235bb-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="235bb-312">节</span><span class="sxs-lookup"><span data-stu-id="235bb-312">Section</span></span>|<span data-ttu-id="235bb-313">值</span><span class="sxs-lookup"><span data-stu-id="235bb-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-314">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-315">**Key**</span></span> | <span data-ttu-id="235bb-316">值</span><span class="sxs-lookup"><span data-stu-id="235bb-316">value</span></span> |
| <span data-ttu-id="235bb-317">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-317">**Data type**</span></span> | <span data-ttu-id="235bb-318">String</span><span class="sxs-lookup"><span data-stu-id="235bb-318">String</span></span> |
| <span data-ttu-id="235bb-319">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-319">**Possible values**</span></span> | <span data-ttu-id="235bb-320">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="235bb-320">audit (default)</span></span> <br/> <span data-ttu-id="235bb-321">block</span><span class="sxs-lookup"><span data-stu-id="235bb-321">block</span></span> <br/> <span data-ttu-id="235bb-322">off</span><span class="sxs-lookup"><span data-stu-id="235bb-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="235bb-323">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="235bb-323">Threat type settings merge policy</span></span>

<span data-ttu-id="235bb-324">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="235bb-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="235bb-325">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="235bb-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="235bb-326">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="235bb-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="235bb-327">节</span><span class="sxs-lookup"><span data-stu-id="235bb-327">Section</span></span>|<span data-ttu-id="235bb-328">值</span><span class="sxs-lookup"><span data-stu-id="235bb-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-329">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-330">**Key**</span></span> | <span data-ttu-id="235bb-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="235bb-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="235bb-332">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-332">**Data type**</span></span> | <span data-ttu-id="235bb-333">String</span><span class="sxs-lookup"><span data-stu-id="235bb-333">String</span></span> |
| <span data-ttu-id="235bb-334">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-334">**Possible values**</span></span> | <span data-ttu-id="235bb-335">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="235bb-335">merge (default)</span></span> <br/> <span data-ttu-id="235bb-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="235bb-336">admin_only</span></span> |
| <span data-ttu-id="235bb-337">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-337">**Comments**</span></span> | <span data-ttu-id="235bb-338">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="235bb-339">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="235bb-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="235bb-340">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="235bb-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="235bb-341">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="235bb-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="235bb-342">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="235bb-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="235bb-343">节</span><span class="sxs-lookup"><span data-stu-id="235bb-343">Section</span></span>|<span data-ttu-id="235bb-344">值</span><span class="sxs-lookup"><span data-stu-id="235bb-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-345">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-346">**Key**</span></span> | <span data-ttu-id="235bb-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="235bb-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="235bb-348">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-348">**Data type**</span></span> | <span data-ttu-id="235bb-349">String</span><span class="sxs-lookup"><span data-stu-id="235bb-349">String</span></span> |
| <span data-ttu-id="235bb-350">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-350">**Possible values**</span></span> | <span data-ttu-id="235bb-351">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="235bb-351">90 (default).</span></span> <span data-ttu-id="235bb-352">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="235bb-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="235bb-353">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-353">**Comments**</span></span> | <span data-ttu-id="235bb-354">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="235bb-355">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="235bb-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="235bb-356">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="235bb-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="235bb-357">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="235bb-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="235bb-358">节</span><span class="sxs-lookup"><span data-stu-id="235bb-358">Section</span></span>|<span data-ttu-id="235bb-359">值</span><span class="sxs-lookup"><span data-stu-id="235bb-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-360">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-361">**Key**</span></span> | <span data-ttu-id="235bb-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="235bb-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="235bb-363">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-363">**Data type**</span></span> | <span data-ttu-id="235bb-364">String</span><span class="sxs-lookup"><span data-stu-id="235bb-364">String</span></span> |
| <span data-ttu-id="235bb-365">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-365">**Possible values**</span></span> | <span data-ttu-id="235bb-366">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="235bb-366">10000 (default).</span></span> <span data-ttu-id="235bb-367">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="235bb-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="235bb-368">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-368">**Comments**</span></span> | <span data-ttu-id="235bb-369">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="235bb-370">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="235bb-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="235bb-371">在 macOS 上配置 Microsoft Defender for Endpoint 的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="235bb-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="235bb-372">节</span><span class="sxs-lookup"><span data-stu-id="235bb-372">Section</span></span>|<span data-ttu-id="235bb-373">值</span><span class="sxs-lookup"><span data-stu-id="235bb-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-374">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-375">**Key**</span></span> | <span data-ttu-id="235bb-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="235bb-376">cloudService</span></span> |
| <span data-ttu-id="235bb-377">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-377">**Data type**</span></span> | <span data-ttu-id="235bb-378">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-379">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-379">**Comments**</span></span> | <span data-ttu-id="235bb-380">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="235bb-381">启用/禁用云保护</span><span class="sxs-lookup"><span data-stu-id="235bb-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="235bb-382">指定是否启用云保护设备。</span><span class="sxs-lookup"><span data-stu-id="235bb-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="235bb-383">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="235bb-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="235bb-384">节</span><span class="sxs-lookup"><span data-stu-id="235bb-384">Section</span></span>|<span data-ttu-id="235bb-385">值</span><span class="sxs-lookup"><span data-stu-id="235bb-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-386">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-387">**Key**</span></span> | <span data-ttu-id="235bb-388">enabled</span><span class="sxs-lookup"><span data-stu-id="235bb-388">enabled</span></span> |
| <span data-ttu-id="235bb-389">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-389">**Data type**</span></span> | <span data-ttu-id="235bb-390">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-390">Boolean</span></span> |
| <span data-ttu-id="235bb-391">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-391">**Possible values**</span></span> | <span data-ttu-id="235bb-392">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="235bb-392">true (default)</span></span> <br/> <span data-ttu-id="235bb-393">false</span><span class="sxs-lookup"><span data-stu-id="235bb-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="235bb-394">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="235bb-394">Diagnostic collection level</span></span>

<span data-ttu-id="235bb-395">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="235bb-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="235bb-396">此设置确定 Microsoft Defender for Endpoint 发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="235bb-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="235bb-397">节</span><span class="sxs-lookup"><span data-stu-id="235bb-397">Section</span></span>|<span data-ttu-id="235bb-398">值</span><span class="sxs-lookup"><span data-stu-id="235bb-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-399">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-400">**Key**</span></span> | <span data-ttu-id="235bb-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="235bb-401">diagnosticLevel</span></span> |
| <span data-ttu-id="235bb-402">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-402">**Data type**</span></span> | <span data-ttu-id="235bb-403">String</span><span class="sxs-lookup"><span data-stu-id="235bb-403">String</span></span> |
| <span data-ttu-id="235bb-404">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-404">**Possible values**</span></span> | <span data-ttu-id="235bb-405">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="235bb-405">optional (default)</span></span> <br/> <span data-ttu-id="235bb-406">必需</span><span class="sxs-lookup"><span data-stu-id="235bb-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="235bb-407">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="235bb-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="235bb-408">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="235bb-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="235bb-409">系统将提示你提交的文件是否可能包含个人信息。</span><span class="sxs-lookup"><span data-stu-id="235bb-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="235bb-410">节</span><span class="sxs-lookup"><span data-stu-id="235bb-410">Section</span></span>|<span data-ttu-id="235bb-411">值</span><span class="sxs-lookup"><span data-stu-id="235bb-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-412">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-413">**Key**</span></span> | <span data-ttu-id="235bb-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="235bb-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="235bb-415">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-415">**Data type**</span></span> | <span data-ttu-id="235bb-416">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-416">Boolean</span></span> |
| <span data-ttu-id="235bb-417">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-417">**Possible values**</span></span> | <span data-ttu-id="235bb-418">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="235bb-418">true (default)</span></span> <br/> <span data-ttu-id="235bb-419">false</span><span class="sxs-lookup"><span data-stu-id="235bb-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="235bb-420">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="235bb-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="235bb-421">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="235bb-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="235bb-422">节</span><span class="sxs-lookup"><span data-stu-id="235bb-422">Section</span></span>|<span data-ttu-id="235bb-423">值</span><span class="sxs-lookup"><span data-stu-id="235bb-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-424">**Key**</span></span> | <span data-ttu-id="235bb-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="235bb-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="235bb-426">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-426">**Data type**</span></span> | <span data-ttu-id="235bb-427">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-427">Boolean</span></span> |
| <span data-ttu-id="235bb-428">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-428">**Possible values**</span></span> | <span data-ttu-id="235bb-429">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="235bb-429">true (default)</span></span> <br/> <span data-ttu-id="235bb-430">false</span><span class="sxs-lookup"><span data-stu-id="235bb-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="235bb-431">用户界面首选项</span><span class="sxs-lookup"><span data-stu-id="235bb-431">User interface preferences</span></span>

<span data-ttu-id="235bb-432">管理 macOS 上适用于终结点的 Microsoft Defender 用户界面的首选项。</span><span class="sxs-lookup"><span data-stu-id="235bb-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="235bb-433">节</span><span class="sxs-lookup"><span data-stu-id="235bb-433">Section</span></span>|<span data-ttu-id="235bb-434">值</span><span class="sxs-lookup"><span data-stu-id="235bb-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-435">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-436">**Key**</span></span> | <span data-ttu-id="235bb-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="235bb-437">userInterface</span></span> |
| <span data-ttu-id="235bb-438">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-438">**Data type**</span></span> | <span data-ttu-id="235bb-439">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-440">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-440">**Comments**</span></span> | <span data-ttu-id="235bb-441">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="235bb-442">显示/隐藏状态菜单图标</span><span class="sxs-lookup"><span data-stu-id="235bb-442">Show / hide status menu icon</span></span>

<span data-ttu-id="235bb-443">指定是显示还是隐藏屏幕右上角的状态菜单图标。</span><span class="sxs-lookup"><span data-stu-id="235bb-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="235bb-444">节</span><span class="sxs-lookup"><span data-stu-id="235bb-444">Section</span></span>|<span data-ttu-id="235bb-445">值</span><span class="sxs-lookup"><span data-stu-id="235bb-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-446">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-447">**Key**</span></span> | <span data-ttu-id="235bb-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="235bb-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="235bb-449">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-449">**Data type**</span></span> | <span data-ttu-id="235bb-450">Boolean</span><span class="sxs-lookup"><span data-stu-id="235bb-450">Boolean</span></span> |
| <span data-ttu-id="235bb-451">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-451">**Possible values**</span></span> | <span data-ttu-id="235bb-452">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="235bb-452">false (default)</span></span> <br/> <span data-ttu-id="235bb-453">true</span><span class="sxs-lookup"><span data-stu-id="235bb-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="235bb-454">显示/隐藏发送反馈的选项</span><span class="sxs-lookup"><span data-stu-id="235bb-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="235bb-455">指定用户是否可以通过访问 向 Microsoft 提交反馈 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="235bb-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="235bb-456">节</span><span class="sxs-lookup"><span data-stu-id="235bb-456">Section</span></span>|<span data-ttu-id="235bb-457">值</span><span class="sxs-lookup"><span data-stu-id="235bb-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-458">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-459">**Key**</span></span> | <span data-ttu-id="235bb-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="235bb-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="235bb-461">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-461">**Data type**</span></span> | <span data-ttu-id="235bb-462">String</span><span class="sxs-lookup"><span data-stu-id="235bb-462">String</span></span> |
| <span data-ttu-id="235bb-463">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-463">**Possible values**</span></span> | <span data-ttu-id="235bb-464">已启用 (默认) </span><span class="sxs-lookup"><span data-stu-id="235bb-464">enabled (default)</span></span> <br/> <span data-ttu-id="235bb-465">disabled</span><span class="sxs-lookup"><span data-stu-id="235bb-465">disabled</span></span> |
| <span data-ttu-id="235bb-466">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-466">**Comments**</span></span> | <span data-ttu-id="235bb-467">适用于终结点版本 101.19.61 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="235bb-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="235bb-468">终结点检测和响应首选项</span><span class="sxs-lookup"><span data-stu-id="235bb-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="235bb-469">管理 macOS 上 Microsoft Defender for Endpoint (EDR) 组件的终结点检测和响应首选项。</span><span class="sxs-lookup"><span data-stu-id="235bb-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="235bb-470">节</span><span class="sxs-lookup"><span data-stu-id="235bb-470">Section</span></span>|<span data-ttu-id="235bb-471">值</span><span class="sxs-lookup"><span data-stu-id="235bb-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-472">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-473">**Key**</span></span> | <span data-ttu-id="235bb-474">edr</span><span class="sxs-lookup"><span data-stu-id="235bb-474">edr</span></span> |
| <span data-ttu-id="235bb-475">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-475">**Data type**</span></span> | <span data-ttu-id="235bb-476">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-477">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-477">**Comments**</span></span> | <span data-ttu-id="235bb-478">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="235bb-479">设备标记</span><span class="sxs-lookup"><span data-stu-id="235bb-479">Device tags</span></span>

<span data-ttu-id="235bb-480">指定标记名称及其值。</span><span class="sxs-lookup"><span data-stu-id="235bb-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="235bb-481">GROUP 标记使用指定值标记设备。</span><span class="sxs-lookup"><span data-stu-id="235bb-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="235bb-482">标记反映在设备页面下的门户中，可用于筛选和分组设备。</span><span class="sxs-lookup"><span data-stu-id="235bb-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="235bb-483">节</span><span class="sxs-lookup"><span data-stu-id="235bb-483">Section</span></span>|<span data-ttu-id="235bb-484">值</span><span class="sxs-lookup"><span data-stu-id="235bb-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-485">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-486">**Key**</span></span> | <span data-ttu-id="235bb-487">tags</span><span class="sxs-lookup"><span data-stu-id="235bb-487">tags</span></span> |
| <span data-ttu-id="235bb-488">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-488">**Data type**</span></span> | <span data-ttu-id="235bb-489">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="235bb-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="235bb-490">**备注**</span><span class="sxs-lookup"><span data-stu-id="235bb-490">**Comments**</span></span> | <span data-ttu-id="235bb-491">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="235bb-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="235bb-492">标记类型</span><span class="sxs-lookup"><span data-stu-id="235bb-492">Type of tag</span></span>

<span data-ttu-id="235bb-493">指定标记的类型</span><span class="sxs-lookup"><span data-stu-id="235bb-493">Specifies the type of tag</span></span>

|<span data-ttu-id="235bb-494">节</span><span class="sxs-lookup"><span data-stu-id="235bb-494">Section</span></span>|<span data-ttu-id="235bb-495">值</span><span class="sxs-lookup"><span data-stu-id="235bb-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-496">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-497">**Key**</span></span> | <span data-ttu-id="235bb-498">注册表项</span><span class="sxs-lookup"><span data-stu-id="235bb-498">key</span></span> |
| <span data-ttu-id="235bb-499">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-499">**Data type**</span></span> | <span data-ttu-id="235bb-500">String</span><span class="sxs-lookup"><span data-stu-id="235bb-500">String</span></span> |
| <span data-ttu-id="235bb-501">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="235bb-502">tag 的值</span><span class="sxs-lookup"><span data-stu-id="235bb-502">Value of tag</span></span>

<span data-ttu-id="235bb-503">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="235bb-503">Specifies the value of tag</span></span>

|<span data-ttu-id="235bb-504">节</span><span class="sxs-lookup"><span data-stu-id="235bb-504">Section</span></span>|<span data-ttu-id="235bb-505">值</span><span class="sxs-lookup"><span data-stu-id="235bb-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="235bb-506">**域**</span><span class="sxs-lookup"><span data-stu-id="235bb-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="235bb-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="235bb-507">**Key**</span></span> | <span data-ttu-id="235bb-508">值</span><span class="sxs-lookup"><span data-stu-id="235bb-508">value</span></span> |
| <span data-ttu-id="235bb-509">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="235bb-509">**Data type**</span></span> | <span data-ttu-id="235bb-510">String</span><span class="sxs-lookup"><span data-stu-id="235bb-510">String</span></span> |
| <span data-ttu-id="235bb-511">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="235bb-511">**Possible values**</span></span> | <span data-ttu-id="235bb-512">任何字符串</span><span class="sxs-lookup"><span data-stu-id="235bb-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="235bb-513">每个标记类型只能设置一个值。</span><span class="sxs-lookup"><span data-stu-id="235bb-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="235bb-514">标记类型是唯一的，并且不应在同一配置文件中重复。</span><span class="sxs-lookup"><span data-stu-id="235bb-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="235bb-515">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="235bb-515">Recommended configuration profile</span></span>

<span data-ttu-id="235bb-516">若要开始，我们建议你的企业采用以下配置，以利用 Microsoft Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="235bb-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="235bb-517">以下配置文件 (，或者，对于 JAMF，可以上载到自定义设置配置文件中的属性列表) ：</span><span class="sxs-lookup"><span data-stu-id="235bb-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="235bb-518">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="235bb-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="235bb-519">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="235bb-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="235bb-520">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="235bb-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="235bb-521">**使用高** (率存档存档) 将审核到 Microsoft Defender 终结点日志</span><span class="sxs-lookup"><span data-stu-id="235bb-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="235bb-522">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="235bb-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="235bb-523">启用云保护</span><span class="sxs-lookup"><span data-stu-id="235bb-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="235bb-524">启用自动提交示例</span><span class="sxs-lookup"><span data-stu-id="235bb-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="235bb-525">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="235bb-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="235bb-526">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="235bb-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="235bb-527">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="235bb-527">Full configuration profile example</span></span>

<span data-ttu-id="235bb-528">以下模板包含本文档中所述的所有设置的条目，可用于更高级的方案，你想要在 macOS 上对 Microsoft Defender for Endpoint 进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="235bb-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="235bb-529">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="235bb-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="235bb-530">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="235bb-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="235bb-531">属性列表验证</span><span class="sxs-lookup"><span data-stu-id="235bb-531">Property list validation</span></span>

<span data-ttu-id="235bb-532">属性列表必须是有效的 *.plist* 文件。</span><span class="sxs-lookup"><span data-stu-id="235bb-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="235bb-533">可通过执行：</span><span class="sxs-lookup"><span data-stu-id="235bb-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="235bb-534">如果文件格式良好，则上述命令将输出 `OK` 并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="235bb-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="235bb-535">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="235bb-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="235bb-536">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="235bb-536">Configuration profile deployment</span></span>

<span data-ttu-id="235bb-537">为企业生成配置文件后，可以通过企业使用的管理控制台部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="235bb-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="235bb-538">以下各节提供有关如何使用 JAMF 和 Intune 部署此配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="235bb-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="235bb-539">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="235bb-539">JAMF deployment</span></span>

<span data-ttu-id="235bb-540">从 JAMF 控制台中，打开 **"计算机** 配置文件"，导航到你要使用的配置文件，  >  然后选择"自定义 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="235bb-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="235bb-541">使用 创建用作 `com.microsoft.wdav` 首选项域的条目并上载之前生成的 *.plist。*</span><span class="sxs-lookup"><span data-stu-id="235bb-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="235bb-542">必须输入正确的首选项域 `com.microsoft.wdav` () ;否则，Microsoft Defender for Endpoint 无法识别首选项。</span><span class="sxs-lookup"><span data-stu-id="235bb-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="235bb-543">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="235bb-543">Intune deployment</span></span>

1. <span data-ttu-id="235bb-544">打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="235bb-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="235bb-545">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="235bb-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="235bb-546">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="235bb-546">Choose a name for the profile.</span></span> <span data-ttu-id="235bb-547">将 **Platform=macOS** 更改为 **配置文件类型=自定义**。</span><span class="sxs-lookup"><span data-stu-id="235bb-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="235bb-548">选择"配置"。</span><span class="sxs-lookup"><span data-stu-id="235bb-548">Select Configure.</span></span>

3. <span data-ttu-id="235bb-549">将之前生成的 .plist 另存为 `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="235bb-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="235bb-550">输入 `com.microsoft.wdav` 作为 **自定义配置文件名称**。</span><span class="sxs-lookup"><span data-stu-id="235bb-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="235bb-551">打开配置文件并上载 `com.microsoft.wdav.xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="235bb-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="235bb-552"> (此文件是在步骤 3.) </span><span class="sxs-lookup"><span data-stu-id="235bb-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="235bb-553">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="235bb-553">Select **OK**.</span></span>

7. <span data-ttu-id="235bb-554">选择 **"管理**  >  **工作分配"。**</span><span class="sxs-lookup"><span data-stu-id="235bb-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="235bb-555">在"**包含"** 选项卡中，**选择"分配给&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="235bb-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="235bb-556">必须输入正确的自定义配置文件名称;否则，Microsoft Defender for Endpoint 无法识别这些首选项。</span><span class="sxs-lookup"><span data-stu-id="235bb-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="235bb-557">资源</span><span class="sxs-lookup"><span data-stu-id="235bb-557">Resources</span></span>

- [<span data-ttu-id="235bb-558">配置文件首选项（Apple 开发人员文档）</span><span class="sxs-lookup"><span data-stu-id="235bb-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
