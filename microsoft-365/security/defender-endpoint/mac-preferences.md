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
ms.openlocfilehash: f13734392e4975738a0d60d38e618595b5175667
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934557"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1ba44-104">在 macOS 上设置适用于终结点的 Microsoft Defender 的首选项</span><span class="sxs-lookup"><span data-stu-id="1ba44-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1ba44-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1ba44-105">**Applies to:**</span></span>

- [<span data-ttu-id="1ba44-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ba44-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="1ba44-107">本文包含有关如何在企业组织中为 macOS 上的 Microsoft Defender for Endpoint 设置首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="1ba44-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="1ba44-108">若要使用命令行界面在 macOS 上配置适用于终结点的 Microsoft Defender，请参阅 [资源](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="1ba44-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="1ba44-109">摘要</span><span class="sxs-lookup"><span data-stu-id="1ba44-109">Summary</span></span>

<span data-ttu-id="1ba44-110">在企业组织中，可以通过使用多种管理工具之一部署的配置文件管理 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="1ba44-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="1ba44-111">由安全操作团队管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="1ba44-112">更改通过配置文件设置的首选项需要提升的权限，并且对于没有管理权限的用户不可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="1ba44-113">本文介绍配置文件的结构，包括可用于入门的推荐配置文件，并提供有关如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="1ba44-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="1ba44-114">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="1ba44-114">Configuration profile structure</span></span>

<span data-ttu-id="1ba44-115">配置文件是一个 *.plist* 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="1ba44-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="1ba44-116">值可以是简单的 (，如数值) 或复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="1ba44-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="1ba44-117">配置文件的布局取决于你使用的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1ba44-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="1ba44-118">以下各节包含 JAMF 和 Intune 的配置文件示例。</span><span class="sxs-lookup"><span data-stu-id="1ba44-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="1ba44-119">配置文件的顶级包括产品范围的首选项和 Microsoft Defender for Endpoint 子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="1ba44-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="1ba44-120">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="1ba44-120">Antivirus engine preferences</span></span>

<span data-ttu-id="1ba44-121">配置文件 *的 antivirusEngine* 部分用于管理 Microsoft Defender for Endpoint 的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="1ba44-122">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-122">Section</span></span>|<span data-ttu-id="1ba44-123">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-124">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-125">**Key**</span></span> | <span data-ttu-id="1ba44-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="1ba44-126">antivirusEngine</span></span> |
| <span data-ttu-id="1ba44-127">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-127">**Data type**</span></span> | <span data-ttu-id="1ba44-128">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-129">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-129">**Comments**</span></span> | <span data-ttu-id="1ba44-130">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="1ba44-131">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="1ba44-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="1ba44-132">指定是否启用实时保护，以在访问文件时对文件进行扫描。</span><span class="sxs-lookup"><span data-stu-id="1ba44-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="1ba44-133">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-133">Section</span></span>|<span data-ttu-id="1ba44-134">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-135">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-136">**Key**</span></span> | <span data-ttu-id="1ba44-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="1ba44-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="1ba44-138">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-138">**Data type**</span></span> | <span data-ttu-id="1ba44-139">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-139">Boolean</span></span> |
| <span data-ttu-id="1ba44-140">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-140">**Possible values**</span></span> | <span data-ttu-id="1ba44-141">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ba44-141">true (default)</span></span> <br/> <span data-ttu-id="1ba44-142">false</span><span class="sxs-lookup"><span data-stu-id="1ba44-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="1ba44-143">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="1ba44-143">Enable / disable passive mode</span></span>

<span data-ttu-id="1ba44-144">指定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="1ba44-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="1ba44-145">被动模式具有以下含义：</span><span class="sxs-lookup"><span data-stu-id="1ba44-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="1ba44-146">实时保护已关闭</span><span class="sxs-lookup"><span data-stu-id="1ba44-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="1ba44-147">按需扫描已打开</span><span class="sxs-lookup"><span data-stu-id="1ba44-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="1ba44-148">自动威胁修正已关闭</span><span class="sxs-lookup"><span data-stu-id="1ba44-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="1ba44-149">启用安全智能更新</span><span class="sxs-lookup"><span data-stu-id="1ba44-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="1ba44-150">状态菜单图标处于隐藏状态</span><span class="sxs-lookup"><span data-stu-id="1ba44-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="1ba44-151">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-151">Section</span></span>|<span data-ttu-id="1ba44-152">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-153">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-154">**Key**</span></span> | <span data-ttu-id="1ba44-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="1ba44-155">passiveMode</span></span> |
| <span data-ttu-id="1ba44-156">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-156">**Data type**</span></span> | <span data-ttu-id="1ba44-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-157">Boolean</span></span> |
| <span data-ttu-id="1ba44-158">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-158">**Possible values**</span></span> | <span data-ttu-id="1ba44-159">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="1ba44-159">false (default)</span></span> <br/> <span data-ttu-id="1ba44-160">true</span><span class="sxs-lookup"><span data-stu-id="1ba44-160">true</span></span> |
| <span data-ttu-id="1ba44-161">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-161">**Comments**</span></span> | <span data-ttu-id="1ba44-162">适用于终结点版本 100.67.60 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="1ba44-163">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="1ba44-163">Exclusion merge policy</span></span>

<span data-ttu-id="1ba44-164">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="1ba44-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="1ba44-165">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="1ba44-166">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="1ba44-167">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-167">Section</span></span>|<span data-ttu-id="1ba44-168">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-169">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-170">**Key**</span></span> | <span data-ttu-id="1ba44-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1ba44-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="1ba44-172">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-172">**Data type**</span></span> | <span data-ttu-id="1ba44-173">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-173">String</span></span> |
| <span data-ttu-id="1ba44-174">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-174">**Possible values**</span></span> | <span data-ttu-id="1ba44-175">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="1ba44-175">merge (default)</span></span> <br/> <span data-ttu-id="1ba44-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="1ba44-176">admin_only</span></span> |
| <span data-ttu-id="1ba44-177">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-177">**Comments**</span></span> | <span data-ttu-id="1ba44-178">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="1ba44-179">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="1ba44-179">Scan exclusions</span></span>

<span data-ttu-id="1ba44-180">指定被扫描排除的实体。</span><span class="sxs-lookup"><span data-stu-id="1ba44-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="1ba44-181">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="1ba44-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="1ba44-182">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-182">Section</span></span>|<span data-ttu-id="1ba44-183">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-184">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-185">**Key**</span></span> | <span data-ttu-id="1ba44-186">排除项</span><span class="sxs-lookup"><span data-stu-id="1ba44-186">exclusions</span></span> |
| <span data-ttu-id="1ba44-187">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-187">**Data type**</span></span> | <span data-ttu-id="1ba44-188">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-189">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-189">**Comments**</span></span> | <span data-ttu-id="1ba44-190">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="1ba44-191">排除类型</span><span class="sxs-lookup"><span data-stu-id="1ba44-191">Type of exclusion</span></span>

<span data-ttu-id="1ba44-192">按类型指定被排除的内容。</span><span class="sxs-lookup"><span data-stu-id="1ba44-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="1ba44-193">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-193">Section</span></span>|<span data-ttu-id="1ba44-194">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-195">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-196">**Key**</span></span> | <span data-ttu-id="1ba44-197">$type</span><span class="sxs-lookup"><span data-stu-id="1ba44-197">$type</span></span> |
| <span data-ttu-id="1ba44-198">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-198">**Data type**</span></span> | <span data-ttu-id="1ba44-199">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-199">String</span></span> |
| <span data-ttu-id="1ba44-200">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-200">**Possible values**</span></span> | <span data-ttu-id="1ba44-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="1ba44-201">excludedPath</span></span> <br/> <span data-ttu-id="1ba44-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="1ba44-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="1ba44-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="1ba44-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="1ba44-204">排除内容的路径</span><span class="sxs-lookup"><span data-stu-id="1ba44-204">Path to excluded content</span></span>

<span data-ttu-id="1ba44-205">指定未由完整文件路径扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="1ba44-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="1ba44-206">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-206">Section</span></span>|<span data-ttu-id="1ba44-207">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-208">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-209">**Key**</span></span> | <span data-ttu-id="1ba44-210">path</span><span class="sxs-lookup"><span data-stu-id="1ba44-210">path</span></span> |
| <span data-ttu-id="1ba44-211">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-211">**Data type**</span></span> | <span data-ttu-id="1ba44-212">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-212">String</span></span> |
| <span data-ttu-id="1ba44-213">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-213">**Possible values**</span></span> | <span data-ttu-id="1ba44-214">有效路径</span><span class="sxs-lookup"><span data-stu-id="1ba44-214">valid paths</span></span> |
| <span data-ttu-id="1ba44-215">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-215">**Comments**</span></span> | <span data-ttu-id="1ba44-216">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="1ba44-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="1ba44-217">文件 (目录的路径) </span><span class="sxs-lookup"><span data-stu-id="1ba44-217">Path type (file / directory)</span></span>

<span data-ttu-id="1ba44-218">指示 *path 属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="1ba44-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="1ba44-219">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-219">Section</span></span>|<span data-ttu-id="1ba44-220">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-221">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-222">**Key**</span></span> | <span data-ttu-id="1ba44-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="1ba44-223">isDirectory</span></span> |
| <span data-ttu-id="1ba44-224">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-224">**Data type**</span></span> | <span data-ttu-id="1ba44-225">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-225">Boolean</span></span> |
| <span data-ttu-id="1ba44-226">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-226">**Possible values**</span></span> | <span data-ttu-id="1ba44-227">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="1ba44-227">false (default)</span></span> <br/> <span data-ttu-id="1ba44-228">true</span><span class="sxs-lookup"><span data-stu-id="1ba44-228">true</span></span> |
| <span data-ttu-id="1ba44-229">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-229">**Comments**</span></span> | <span data-ttu-id="1ba44-230">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="1ba44-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="1ba44-231">从扫描中排除的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="1ba44-231">File extension excluded from the scan</span></span>

<span data-ttu-id="1ba44-232">指定文件扩展名无法扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="1ba44-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="1ba44-233">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-233">Section</span></span>|<span data-ttu-id="1ba44-234">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-235">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-236">**Key**</span></span> | <span data-ttu-id="1ba44-237">extension</span><span class="sxs-lookup"><span data-stu-id="1ba44-237">extension</span></span> |
| <span data-ttu-id="1ba44-238">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-238">**Data type**</span></span> | <span data-ttu-id="1ba44-239">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-239">String</span></span> |
| <span data-ttu-id="1ba44-240">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-240">**Possible values**</span></span> | <span data-ttu-id="1ba44-241">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="1ba44-241">valid file extensions</span></span> |
| <span data-ttu-id="1ba44-242">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-242">**Comments**</span></span> | <span data-ttu-id="1ba44-243">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="1ba44-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="1ba44-244">从扫描中排除的进程</span><span class="sxs-lookup"><span data-stu-id="1ba44-244">Process excluded from the scan</span></span>

<span data-ttu-id="1ba44-245">指定一个进程，所有文件活动都从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="1ba44-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="1ba44-246">可以通过进程的名称指定进程， (例如) 或完整路径 (`cat` 例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="1ba44-247">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-247">Section</span></span>|<span data-ttu-id="1ba44-248">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-249">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-250">**Key**</span></span> | <span data-ttu-id="1ba44-251">name</span><span class="sxs-lookup"><span data-stu-id="1ba44-251">name</span></span> |
| <span data-ttu-id="1ba44-252">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-252">**Data type**</span></span> | <span data-ttu-id="1ba44-253">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-253">String</span></span> |
| <span data-ttu-id="1ba44-254">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-254">**Possible values**</span></span> | <span data-ttu-id="1ba44-255">任何字符串</span><span class="sxs-lookup"><span data-stu-id="1ba44-255">any string</span></span> |
| <span data-ttu-id="1ba44-256">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-256">**Comments**</span></span> | <span data-ttu-id="1ba44-257">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="1ba44-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="1ba44-258">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="1ba44-258">Allowed threats</span></span>

<span data-ttu-id="1ba44-259">按名称指定未由 Mac 上的 Defender for Endpoint 阻止的威胁。</span><span class="sxs-lookup"><span data-stu-id="1ba44-259">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="1ba44-260">将允许运行这些威胁。</span><span class="sxs-lookup"><span data-stu-id="1ba44-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="1ba44-261">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-261">Section</span></span>|<span data-ttu-id="1ba44-262">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-263">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-264">**Key**</span></span> | <span data-ttu-id="1ba44-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="1ba44-265">allowedThreats</span></span> |
| <span data-ttu-id="1ba44-266">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-266">**Data type**</span></span> | <span data-ttu-id="1ba44-267">字符串数组</span><span class="sxs-lookup"><span data-stu-id="1ba44-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="1ba44-268">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="1ba44-268">Disallowed threat actions</span></span>

<span data-ttu-id="1ba44-269">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="1ba44-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="1ba44-270">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="1ba44-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="1ba44-271">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-271">Section</span></span>|<span data-ttu-id="1ba44-272">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-273">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-274">**Key**</span></span> | <span data-ttu-id="1ba44-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="1ba44-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="1ba44-276">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-276">**Data type**</span></span> | <span data-ttu-id="1ba44-277">字符串数组</span><span class="sxs-lookup"><span data-stu-id="1ba44-277">Array of strings</span></span> |
| <span data-ttu-id="1ba44-278">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-278">**Possible values**</span></span> | <span data-ttu-id="1ba44-279">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="1ba44-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="1ba44-280">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="1ba44-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="1ba44-281">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-281">**Comments**</span></span> | <span data-ttu-id="1ba44-282">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="1ba44-283">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="1ba44-283">Threat type settings</span></span>

<span data-ttu-id="1ba44-284">指定 macOS 上的 Microsoft Defender for Endpoint 如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="1ba44-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1ba44-285">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-285">Section</span></span>|<span data-ttu-id="1ba44-286">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-287">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-288">**Key**</span></span> | <span data-ttu-id="1ba44-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="1ba44-289">threatTypeSettings</span></span> |
| <span data-ttu-id="1ba44-290">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-290">**Data type**</span></span> | <span data-ttu-id="1ba44-291">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-292">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-292">**Comments**</span></span> | <span data-ttu-id="1ba44-293">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="1ba44-294">威胁类型</span><span class="sxs-lookup"><span data-stu-id="1ba44-294">Threat type</span></span>

<span data-ttu-id="1ba44-295">指定威胁类型。</span><span class="sxs-lookup"><span data-stu-id="1ba44-295">Specify threat types.</span></span>

|<span data-ttu-id="1ba44-296">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-296">Section</span></span>|<span data-ttu-id="1ba44-297">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-298">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-299">**Key**</span></span> | <span data-ttu-id="1ba44-300">注册表项</span><span class="sxs-lookup"><span data-stu-id="1ba44-300">key</span></span> |
| <span data-ttu-id="1ba44-301">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-301">**Data type**</span></span> | <span data-ttu-id="1ba44-302">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-302">String</span></span> |
| <span data-ttu-id="1ba44-303">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-303">**Possible values**</span></span> | <span data-ttu-id="1ba44-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="1ba44-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="1ba44-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="1ba44-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="1ba44-306">要采取的措施</span><span class="sxs-lookup"><span data-stu-id="1ba44-306">Action to take</span></span>

<span data-ttu-id="1ba44-307">指定在检测到上一节中指定的类型的威胁时要采取什么操作。</span><span class="sxs-lookup"><span data-stu-id="1ba44-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="1ba44-308">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="1ba44-308">Choose from the following options:</span></span>

- <span data-ttu-id="1ba44-309">**审核**：你的设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="1ba44-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="1ba44-310">**阻止**：你的设备受到此类型威胁的保护，并且你将在用户界面和安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="1ba44-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="1ba44-311">**关闭**：你的设备不受此类型威胁的防御，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="1ba44-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="1ba44-312">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-312">Section</span></span>|<span data-ttu-id="1ba44-313">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-314">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-315">**Key**</span></span> | <span data-ttu-id="1ba44-316">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-316">value</span></span> |
| <span data-ttu-id="1ba44-317">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-317">**Data type**</span></span> | <span data-ttu-id="1ba44-318">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-318">String</span></span> |
| <span data-ttu-id="1ba44-319">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-319">**Possible values**</span></span> | <span data-ttu-id="1ba44-320">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="1ba44-320">audit (default)</span></span> <br/> <span data-ttu-id="1ba44-321">block</span><span class="sxs-lookup"><span data-stu-id="1ba44-321">block</span></span> <br/> <span data-ttu-id="1ba44-322">off</span><span class="sxs-lookup"><span data-stu-id="1ba44-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="1ba44-323">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="1ba44-323">Threat type settings merge policy</span></span>

<span data-ttu-id="1ba44-324">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="1ba44-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="1ba44-325">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="1ba44-326">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="1ba44-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="1ba44-327">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-327">Section</span></span>|<span data-ttu-id="1ba44-328">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-329">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-330">**Key**</span></span> | <span data-ttu-id="1ba44-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="1ba44-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="1ba44-332">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-332">**Data type**</span></span> | <span data-ttu-id="1ba44-333">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-333">String</span></span> |
| <span data-ttu-id="1ba44-334">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-334">**Possible values**</span></span> | <span data-ttu-id="1ba44-335">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="1ba44-335">merge (default)</span></span> <br/> <span data-ttu-id="1ba44-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="1ba44-336">admin_only</span></span> |
| <span data-ttu-id="1ba44-337">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-337">**Comments**</span></span> | <span data-ttu-id="1ba44-338">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="1ba44-339">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="1ba44-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="1ba44-340">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="1ba44-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="1ba44-341">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="1ba44-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="1ba44-342">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="1ba44-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="1ba44-343">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-343">Section</span></span>|<span data-ttu-id="1ba44-344">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-345">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-346">**Key**</span></span> | <span data-ttu-id="1ba44-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="1ba44-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="1ba44-348">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-348">**Data type**</span></span> | <span data-ttu-id="1ba44-349">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-349">String</span></span> |
| <span data-ttu-id="1ba44-350">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-350">**Possible values**</span></span> | <span data-ttu-id="1ba44-351">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-351">90 (default).</span></span> <span data-ttu-id="1ba44-352">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="1ba44-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="1ba44-353">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-353">**Comments**</span></span> | <span data-ttu-id="1ba44-354">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="1ba44-355">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="1ba44-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="1ba44-356">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="1ba44-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="1ba44-357">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="1ba44-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="1ba44-358">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-358">Section</span></span>|<span data-ttu-id="1ba44-359">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-360">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-361">**Key**</span></span> | <span data-ttu-id="1ba44-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="1ba44-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="1ba44-363">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-363">**Data type**</span></span> | <span data-ttu-id="1ba44-364">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-364">String</span></span> |
| <span data-ttu-id="1ba44-365">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-365">**Possible values**</span></span> | <span data-ttu-id="1ba44-366">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-366">10000 (default).</span></span> <span data-ttu-id="1ba44-367">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="1ba44-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="1ba44-368">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-368">**Comments**</span></span> | <span data-ttu-id="1ba44-369">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="1ba44-370">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="1ba44-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="1ba44-371">在 macOS 上配置 Microsoft Defender for Endpoint 的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="1ba44-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1ba44-372">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-372">Section</span></span>|<span data-ttu-id="1ba44-373">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-374">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-375">**Key**</span></span> | <span data-ttu-id="1ba44-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="1ba44-376">cloudService</span></span> |
| <span data-ttu-id="1ba44-377">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-377">**Data type**</span></span> | <span data-ttu-id="1ba44-378">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-379">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-379">**Comments**</span></span> | <span data-ttu-id="1ba44-380">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="1ba44-381">启用/禁用云保护</span><span class="sxs-lookup"><span data-stu-id="1ba44-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="1ba44-382">指定是否启用云保护设备。</span><span class="sxs-lookup"><span data-stu-id="1ba44-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="1ba44-383">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="1ba44-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="1ba44-384">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-384">Section</span></span>|<span data-ttu-id="1ba44-385">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-386">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-387">**Key**</span></span> | <span data-ttu-id="1ba44-388">enabled</span><span class="sxs-lookup"><span data-stu-id="1ba44-388">enabled</span></span> |
| <span data-ttu-id="1ba44-389">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-389">**Data type**</span></span> | <span data-ttu-id="1ba44-390">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-390">Boolean</span></span> |
| <span data-ttu-id="1ba44-391">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-391">**Possible values**</span></span> | <span data-ttu-id="1ba44-392">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ba44-392">true (default)</span></span> <br/> <span data-ttu-id="1ba44-393">false</span><span class="sxs-lookup"><span data-stu-id="1ba44-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="1ba44-394">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="1ba44-394">Diagnostic collection level</span></span>

<span data-ttu-id="1ba44-395">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="1ba44-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="1ba44-396">此设置确定 Microsoft Defender for Endpoint 发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="1ba44-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="1ba44-397">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-397">Section</span></span>|<span data-ttu-id="1ba44-398">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-399">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-400">**Key**</span></span> | <span data-ttu-id="1ba44-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="1ba44-401">diagnosticLevel</span></span> |
| <span data-ttu-id="1ba44-402">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-402">**Data type**</span></span> | <span data-ttu-id="1ba44-403">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-403">String</span></span> |
| <span data-ttu-id="1ba44-404">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-404">**Possible values**</span></span> | <span data-ttu-id="1ba44-405">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="1ba44-405">optional (default)</span></span> <br/> <span data-ttu-id="1ba44-406">必需</span><span class="sxs-lookup"><span data-stu-id="1ba44-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="1ba44-407">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="1ba44-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="1ba44-408">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="1ba44-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="1ba44-409">系统将提示你提交的文件是否可能包含个人信息。</span><span class="sxs-lookup"><span data-stu-id="1ba44-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="1ba44-410">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-410">Section</span></span>|<span data-ttu-id="1ba44-411">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-412">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-413">**Key**</span></span> | <span data-ttu-id="1ba44-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="1ba44-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="1ba44-415">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-415">**Data type**</span></span> | <span data-ttu-id="1ba44-416">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-416">Boolean</span></span> |
| <span data-ttu-id="1ba44-417">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-417">**Possible values**</span></span> | <span data-ttu-id="1ba44-418">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ba44-418">true (default)</span></span> <br/> <span data-ttu-id="1ba44-419">false</span><span class="sxs-lookup"><span data-stu-id="1ba44-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="1ba44-420">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="1ba44-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="1ba44-421">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="1ba44-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="1ba44-422">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-422">Section</span></span>|<span data-ttu-id="1ba44-423">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-424">**Key**</span></span> | <span data-ttu-id="1ba44-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="1ba44-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="1ba44-426">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-426">**Data type**</span></span> | <span data-ttu-id="1ba44-427">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-427">Boolean</span></span> |
| <span data-ttu-id="1ba44-428">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-428">**Possible values**</span></span> | <span data-ttu-id="1ba44-429">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ba44-429">true (default)</span></span> <br/> <span data-ttu-id="1ba44-430">false</span><span class="sxs-lookup"><span data-stu-id="1ba44-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="1ba44-431">用户界面首选项</span><span class="sxs-lookup"><span data-stu-id="1ba44-431">User interface preferences</span></span>

<span data-ttu-id="1ba44-432">管理 macOS 上适用于终结点的 Microsoft Defender 用户界面的首选项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1ba44-433">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-433">Section</span></span>|<span data-ttu-id="1ba44-434">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-435">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-436">**Key**</span></span> | <span data-ttu-id="1ba44-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="1ba44-437">userInterface</span></span> |
| <span data-ttu-id="1ba44-438">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-438">**Data type**</span></span> | <span data-ttu-id="1ba44-439">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-440">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-440">**Comments**</span></span> | <span data-ttu-id="1ba44-441">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="1ba44-442">显示/隐藏状态菜单图标</span><span class="sxs-lookup"><span data-stu-id="1ba44-442">Show / hide status menu icon</span></span>

<span data-ttu-id="1ba44-443">指定是显示还是隐藏屏幕右上角的状态菜单图标。</span><span class="sxs-lookup"><span data-stu-id="1ba44-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="1ba44-444">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-444">Section</span></span>|<span data-ttu-id="1ba44-445">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-446">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-447">**Key**</span></span> | <span data-ttu-id="1ba44-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="1ba44-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="1ba44-449">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-449">**Data type**</span></span> | <span data-ttu-id="1ba44-450">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ba44-450">Boolean</span></span> |
| <span data-ttu-id="1ba44-451">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-451">**Possible values**</span></span> | <span data-ttu-id="1ba44-452">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="1ba44-452">false (default)</span></span> <br/> <span data-ttu-id="1ba44-453">true</span><span class="sxs-lookup"><span data-stu-id="1ba44-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="1ba44-454">显示/隐藏发送反馈的选项</span><span class="sxs-lookup"><span data-stu-id="1ba44-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="1ba44-455">指定用户是否可以通过访问 向 Microsoft 提交反馈 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="1ba44-456">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-456">Section</span></span>|<span data-ttu-id="1ba44-457">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-458">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-459">**Key**</span></span> | <span data-ttu-id="1ba44-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="1ba44-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="1ba44-461">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-461">**Data type**</span></span> | <span data-ttu-id="1ba44-462">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-462">String</span></span> |
| <span data-ttu-id="1ba44-463">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-463">**Possible values**</span></span> | <span data-ttu-id="1ba44-464">已启用 (默认) </span><span class="sxs-lookup"><span data-stu-id="1ba44-464">enabled (default)</span></span> <br/> <span data-ttu-id="1ba44-465">disabled</span><span class="sxs-lookup"><span data-stu-id="1ba44-465">disabled</span></span> |
| <span data-ttu-id="1ba44-466">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-466">**Comments**</span></span> | <span data-ttu-id="1ba44-467">适用于终结点版本 101.19.61 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="1ba44-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="1ba44-468">终结点检测和响应首选项</span><span class="sxs-lookup"><span data-stu-id="1ba44-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="1ba44-469">管理 macOS 上 Microsoft Defender for Endpoint (EDR) 组件的终结点检测和响应首选项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="1ba44-470">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-470">Section</span></span>|<span data-ttu-id="1ba44-471">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-472">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-473">**Key**</span></span> | <span data-ttu-id="1ba44-474">edr</span><span class="sxs-lookup"><span data-stu-id="1ba44-474">edr</span></span> |
| <span data-ttu-id="1ba44-475">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-475">**Data type**</span></span> | <span data-ttu-id="1ba44-476">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-477">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-477">**Comments**</span></span> | <span data-ttu-id="1ba44-478">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="1ba44-479">设备标记</span><span class="sxs-lookup"><span data-stu-id="1ba44-479">Device tags</span></span>

<span data-ttu-id="1ba44-480">指定标记名称及其值。</span><span class="sxs-lookup"><span data-stu-id="1ba44-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="1ba44-481">GROUP 标记使用指定值标记设备。</span><span class="sxs-lookup"><span data-stu-id="1ba44-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="1ba44-482">标记反映在设备页面下的门户中，可用于筛选和分组设备。</span><span class="sxs-lookup"><span data-stu-id="1ba44-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="1ba44-483">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-483">Section</span></span>|<span data-ttu-id="1ba44-484">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-485">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-486">**Key**</span></span> | <span data-ttu-id="1ba44-487">tags</span><span class="sxs-lookup"><span data-stu-id="1ba44-487">tags</span></span> |
| <span data-ttu-id="1ba44-488">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-488">**Data type**</span></span> | <span data-ttu-id="1ba44-489">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="1ba44-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="1ba44-490">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ba44-490">**Comments**</span></span> | <span data-ttu-id="1ba44-491">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="1ba44-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="1ba44-492">标记类型</span><span class="sxs-lookup"><span data-stu-id="1ba44-492">Type of tag</span></span>

<span data-ttu-id="1ba44-493">指定标记的类型</span><span class="sxs-lookup"><span data-stu-id="1ba44-493">Specifies the type of tag</span></span>

|<span data-ttu-id="1ba44-494">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-494">Section</span></span>|<span data-ttu-id="1ba44-495">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-496">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-497">**Key**</span></span> | <span data-ttu-id="1ba44-498">注册表项</span><span class="sxs-lookup"><span data-stu-id="1ba44-498">key</span></span> |
| <span data-ttu-id="1ba44-499">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-499">**Data type**</span></span> | <span data-ttu-id="1ba44-500">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-500">String</span></span> |
| <span data-ttu-id="1ba44-501">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="1ba44-502">tag 的值</span><span class="sxs-lookup"><span data-stu-id="1ba44-502">Value of tag</span></span>

<span data-ttu-id="1ba44-503">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="1ba44-503">Specifies the value of tag</span></span>

|<span data-ttu-id="1ba44-504">节</span><span class="sxs-lookup"><span data-stu-id="1ba44-504">Section</span></span>|<span data-ttu-id="1ba44-505">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="1ba44-506">**域**</span><span class="sxs-lookup"><span data-stu-id="1ba44-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="1ba44-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ba44-507">**Key**</span></span> | <span data-ttu-id="1ba44-508">值</span><span class="sxs-lookup"><span data-stu-id="1ba44-508">value</span></span> |
| <span data-ttu-id="1ba44-509">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ba44-509">**Data type**</span></span> | <span data-ttu-id="1ba44-510">String</span><span class="sxs-lookup"><span data-stu-id="1ba44-510">String</span></span> |
| <span data-ttu-id="1ba44-511">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ba44-511">**Possible values**</span></span> | <span data-ttu-id="1ba44-512">任何字符串</span><span class="sxs-lookup"><span data-stu-id="1ba44-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="1ba44-513">每个标记类型只能设置一个值。</span><span class="sxs-lookup"><span data-stu-id="1ba44-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="1ba44-514">标记类型是唯一的，并且不应在同一配置文件中重复。</span><span class="sxs-lookup"><span data-stu-id="1ba44-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="1ba44-515">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba44-515">Recommended configuration profile</span></span>

<span data-ttu-id="1ba44-516">若要开始，我们建议你的企业采用以下配置，以利用 Microsoft Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="1ba44-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="1ba44-517">以下配置文件 (，或者，对于 JAMF，可以上载到自定义设置配置文件中的属性列表) ：</span><span class="sxs-lookup"><span data-stu-id="1ba44-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="1ba44-518">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="1ba44-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="1ba44-519">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="1ba44-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="1ba44-520">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="1ba44-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="1ba44-521">**使用高** (率存档存档) 将审核到 Microsoft Defender 终结点日志</span><span class="sxs-lookup"><span data-stu-id="1ba44-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="1ba44-522">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="1ba44-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="1ba44-523">启用云保护</span><span class="sxs-lookup"><span data-stu-id="1ba44-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="1ba44-524">启用自动提交示例</span><span class="sxs-lookup"><span data-stu-id="1ba44-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1ba44-525">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="1ba44-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="1ba44-526">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba44-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="1ba44-527">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="1ba44-527">Full configuration profile example</span></span>

<span data-ttu-id="1ba44-528">以下模板包含本文档中所述的所有设置的条目，可用于更高级的方案，你想要在 macOS 上对 Microsoft Defender for Endpoint 进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="1ba44-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="1ba44-529">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="1ba44-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="1ba44-530">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="1ba44-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="1ba44-531">属性列表验证</span><span class="sxs-lookup"><span data-stu-id="1ba44-531">Property list validation</span></span>

<span data-ttu-id="1ba44-532">属性列表必须是有效的 *.plist* 文件。</span><span class="sxs-lookup"><span data-stu-id="1ba44-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="1ba44-533">可通过执行：</span><span class="sxs-lookup"><span data-stu-id="1ba44-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="1ba44-534">如果文件格式良好，则上述命令将输出 `OK` 并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="1ba44-535">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="1ba44-536">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="1ba44-536">Configuration profile deployment</span></span>

<span data-ttu-id="1ba44-537">为企业生成配置文件后，可以通过企业使用的管理控制台部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ba44-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="1ba44-538">以下各节提供有关如何使用 JAMF 和 Intune 部署此配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="1ba44-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="1ba44-539">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="1ba44-539">JAMF deployment</span></span>

<span data-ttu-id="1ba44-540">从 JAMF 控制台中，打开 **"计算机** 配置文件"，导航到你要使用的配置文件，  >  然后选择"自定义 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ba44-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="1ba44-541">使用 创建用作 `com.microsoft.wdav` 首选项域的条目并上载之前生成的 *.plist。*</span><span class="sxs-lookup"><span data-stu-id="1ba44-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="1ba44-542">必须输入正确的首选项域 `com.microsoft.wdav` () ;否则，Microsoft Defender for Endpoint 无法识别首选项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="1ba44-543">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="1ba44-543">Intune deployment</span></span>

1. <span data-ttu-id="1ba44-544">打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="1ba44-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="1ba44-545">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="1ba44-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="1ba44-546">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1ba44-546">Choose a name for the profile.</span></span> <span data-ttu-id="1ba44-547">将 **Platform=macOS** 更改为 **配置文件类型=自定义**。</span><span class="sxs-lookup"><span data-stu-id="1ba44-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="1ba44-548">选择"配置"。</span><span class="sxs-lookup"><span data-stu-id="1ba44-548">Select Configure.</span></span>

3. <span data-ttu-id="1ba44-549">将之前生成的 .plist 另存为 `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="1ba44-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="1ba44-550">输入 `com.microsoft.wdav` 作为 **自定义配置文件名称**。</span><span class="sxs-lookup"><span data-stu-id="1ba44-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="1ba44-551">打开配置文件并上载 `com.microsoft.wdav.xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="1ba44-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="1ba44-552"> (此文件是在步骤 3.) </span><span class="sxs-lookup"><span data-stu-id="1ba44-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="1ba44-553">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1ba44-553">Select **OK**.</span></span>

7. <span data-ttu-id="1ba44-554">选择 **"管理**  >  **工作分配"。**</span><span class="sxs-lookup"><span data-stu-id="1ba44-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="1ba44-555">在"**包含"** 选项卡中，**选择"分配给&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="1ba44-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="1ba44-556">必须输入正确的自定义配置文件名称;否则，Microsoft Defender for Endpoint 无法识别这些首选项。</span><span class="sxs-lookup"><span data-stu-id="1ba44-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="1ba44-557">资源</span><span class="sxs-lookup"><span data-stu-id="1ba44-557">Resources</span></span>

- [<span data-ttu-id="1ba44-558">配置文件首选项（Apple 开发人员文档）</span><span class="sxs-lookup"><span data-stu-id="1ba44-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
