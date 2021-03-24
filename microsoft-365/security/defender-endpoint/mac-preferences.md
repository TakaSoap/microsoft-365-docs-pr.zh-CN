---
title: 设置适用于 Mac 的 Microsoft Defender ATP 的首选项
description: 在企业组织中配置适用于 Mac 的 Microsoft Defender ATP。
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056616"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="e259f-104">设置适用于 Mac 的 Microsoft Defender 终结点的首选项</span><span class="sxs-lookup"><span data-stu-id="e259f-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e259f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e259f-105">**Applies to:**</span></span>

- [<span data-ttu-id="e259f-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="e259f-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="e259f-107">本文包含有关如何在企业组织中设置适用于 Mac 的 Microsoft Defender for Endpoint 的首选项的说明。</span><span class="sxs-lookup"><span data-stu-id="e259f-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="e259f-108">若要使用命令行界面配置适用于 Mac 的 Microsoft Defender for Endpoint，请参阅 [资源](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="e259f-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="e259f-109">摘要</span><span class="sxs-lookup"><span data-stu-id="e259f-109">Summary</span></span>

<span data-ttu-id="e259f-110">在企业组织中，可以通过使用多种管理工具之一部署的配置文件管理适用于 Mac 的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="e259f-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="e259f-111">由安全操作团队管理的首选项优先于在设备上本地设置的首选项。</span><span class="sxs-lookup"><span data-stu-id="e259f-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="e259f-112">更改通过配置文件设置的首选项需要提升的权限，并且对于没有管理权限的用户不可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="e259f-113">本文介绍配置文件的结构，包括可用于入门的推荐配置文件，并提供有关如何部署配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="e259f-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="e259f-114">配置文件结构</span><span class="sxs-lookup"><span data-stu-id="e259f-114">Configuration profile structure</span></span>

<span data-ttu-id="e259f-115">配置文件是一个 *.plist* 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。</span><span class="sxs-lookup"><span data-stu-id="e259f-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="e259f-116">值可以是简单的 (，如数值) 或复杂，如嵌套的首选项列表。</span><span class="sxs-lookup"><span data-stu-id="e259f-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="e259f-117">配置文件的布局取决于你使用的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e259f-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="e259f-118">以下各节包含 JAMF 和 Intune 的配置文件示例。</span><span class="sxs-lookup"><span data-stu-id="e259f-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="e259f-119">配置文件的顶级包括产品范围的首选项和 Microsoft Defender for Endpoint 子区域条目，下一节将详细介绍这些首选项和条目。</span><span class="sxs-lookup"><span data-stu-id="e259f-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="e259f-120">防病毒引擎首选项</span><span class="sxs-lookup"><span data-stu-id="e259f-120">Antivirus engine preferences</span></span>

<span data-ttu-id="e259f-121">配置文件 *的 antivirusEngine* 部分用于管理 Microsoft Defender for Endpoint 的防病毒组件的首选项。</span><span class="sxs-lookup"><span data-stu-id="e259f-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-122">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-123">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-123">**Key**</span></span> | <span data-ttu-id="e259f-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="e259f-124">antivirusEngine</span></span> |
| <span data-ttu-id="e259f-125">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-125">**Data type**</span></span> | <span data-ttu-id="e259f-126">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-127">**Comments**</span></span> | <span data-ttu-id="e259f-128">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="e259f-129">启用/禁用实时保护</span><span class="sxs-lookup"><span data-stu-id="e259f-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="e259f-130">指定是否启用实时保护，以在访问文件时对文件进行扫描。</span><span class="sxs-lookup"><span data-stu-id="e259f-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-131">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-132">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-132">**Key**</span></span> | <span data-ttu-id="e259f-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="e259f-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="e259f-134">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-134">**Data type**</span></span> | <span data-ttu-id="e259f-135">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-135">Boolean</span></span> |
| <span data-ttu-id="e259f-136">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-136">**Possible values**</span></span> | <span data-ttu-id="e259f-137">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="e259f-137">true (default)</span></span> <br/> <span data-ttu-id="e259f-138">false</span><span class="sxs-lookup"><span data-stu-id="e259f-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="e259f-139">启用/禁用被动模式</span><span class="sxs-lookup"><span data-stu-id="e259f-139">Enable / disable passive mode</span></span>

<span data-ttu-id="e259f-140">指定防病毒引擎是否在被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="e259f-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="e259f-141">被动模式具有以下含义：</span><span class="sxs-lookup"><span data-stu-id="e259f-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="e259f-142">实时保护已关闭</span><span class="sxs-lookup"><span data-stu-id="e259f-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="e259f-143">按需扫描已打开</span><span class="sxs-lookup"><span data-stu-id="e259f-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="e259f-144">自动威胁修正已关闭</span><span class="sxs-lookup"><span data-stu-id="e259f-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="e259f-145">启用安全智能更新</span><span class="sxs-lookup"><span data-stu-id="e259f-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="e259f-146">状态菜单图标处于隐藏状态</span><span class="sxs-lookup"><span data-stu-id="e259f-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-147">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-148">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-148">**Key**</span></span> | <span data-ttu-id="e259f-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="e259f-149">passiveMode</span></span> |
| <span data-ttu-id="e259f-150">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-150">**Data type**</span></span> | <span data-ttu-id="e259f-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-151">Boolean</span></span> |
| <span data-ttu-id="e259f-152">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-152">**Possible values**</span></span> | <span data-ttu-id="e259f-153">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="e259f-153">false (default)</span></span> <br/> <span data-ttu-id="e259f-154">true</span><span class="sxs-lookup"><span data-stu-id="e259f-154">true</span></span> |
| <span data-ttu-id="e259f-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-155">**Comments**</span></span> | <span data-ttu-id="e259f-156">适用于终结点版本 100.67.60 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="e259f-157">排除合并策略</span><span class="sxs-lookup"><span data-stu-id="e259f-157">Exclusion merge policy</span></span>

<span data-ttu-id="e259f-158">指定排除项的合并策略。</span><span class="sxs-lookup"><span data-stu-id="e259f-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="e259f-159">它可以是管理员定义的排除项和用户定义的排除项 () 管理员定义的排除项 `merge` `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="e259f-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="e259f-160">此设置可用于限制本地用户定义自己的排除项。</span><span class="sxs-lookup"><span data-stu-id="e259f-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-161">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-162">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-162">**Key**</span></span> | <span data-ttu-id="e259f-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="e259f-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="e259f-164">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-164">**Data type**</span></span> | <span data-ttu-id="e259f-165">String</span><span class="sxs-lookup"><span data-stu-id="e259f-165">String</span></span> |
| <span data-ttu-id="e259f-166">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-166">**Possible values**</span></span> | <span data-ttu-id="e259f-167">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="e259f-167">merge (default)</span></span> <br/> <span data-ttu-id="e259f-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="e259f-168">admin_only</span></span> |
| <span data-ttu-id="e259f-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-169">**Comments**</span></span> | <span data-ttu-id="e259f-170">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="e259f-171">扫描排除项</span><span class="sxs-lookup"><span data-stu-id="e259f-171">Scan exclusions</span></span>

<span data-ttu-id="e259f-172">指定被扫描排除的实体。</span><span class="sxs-lookup"><span data-stu-id="e259f-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="e259f-173">排除项可以通过完整路径、扩展名或文件名指定。</span><span class="sxs-lookup"><span data-stu-id="e259f-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-174">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-175">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-175">**Key**</span></span> | <span data-ttu-id="e259f-176">排除项</span><span class="sxs-lookup"><span data-stu-id="e259f-176">exclusions</span></span> |
| <span data-ttu-id="e259f-177">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-177">**Data type**</span></span> | <span data-ttu-id="e259f-178">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-179">**Comments**</span></span> | <span data-ttu-id="e259f-180">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="e259f-181">排除类型</span><span class="sxs-lookup"><span data-stu-id="e259f-181">Type of exclusion</span></span>

<span data-ttu-id="e259f-182">按类型指定被排除的内容。</span><span class="sxs-lookup"><span data-stu-id="e259f-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-183">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-184">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-184">**Key**</span></span> | <span data-ttu-id="e259f-185">$type</span><span class="sxs-lookup"><span data-stu-id="e259f-185">$type</span></span> |
| <span data-ttu-id="e259f-186">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-186">**Data type**</span></span> | <span data-ttu-id="e259f-187">String</span><span class="sxs-lookup"><span data-stu-id="e259f-187">String</span></span> |
| <span data-ttu-id="e259f-188">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-188">**Possible values**</span></span> | <span data-ttu-id="e259f-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="e259f-189">excludedPath</span></span> <br/> <span data-ttu-id="e259f-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="e259f-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="e259f-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="e259f-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="e259f-192">排除内容的路径</span><span class="sxs-lookup"><span data-stu-id="e259f-192">Path to excluded content</span></span>

<span data-ttu-id="e259f-193">指定未由完整文件路径扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="e259f-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-194">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-195">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-195">**Key**</span></span> | <span data-ttu-id="e259f-196">path</span><span class="sxs-lookup"><span data-stu-id="e259f-196">path</span></span> |
| <span data-ttu-id="e259f-197">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-197">**Data type**</span></span> | <span data-ttu-id="e259f-198">String</span><span class="sxs-lookup"><span data-stu-id="e259f-198">String</span></span> |
| <span data-ttu-id="e259f-199">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-199">**Possible values**</span></span> | <span data-ttu-id="e259f-200">有效路径</span><span class="sxs-lookup"><span data-stu-id="e259f-200">valid paths</span></span> |
| <span data-ttu-id="e259f-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-201">**Comments**</span></span> | <span data-ttu-id="e259f-202">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="e259f-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="e259f-203">文件 (目录的路径) </span><span class="sxs-lookup"><span data-stu-id="e259f-203">Path type (file / directory)</span></span>

<span data-ttu-id="e259f-204">指示 *path 属性* 是否引用文件或目录。</span><span class="sxs-lookup"><span data-stu-id="e259f-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="e259f-205">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-206">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-206">**Key**</span></span> | <span data-ttu-id="e259f-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="e259f-207">isDirectory</span></span> |
| <span data-ttu-id="e259f-208">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-208">**Data type**</span></span> | <span data-ttu-id="e259f-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-209">Boolean</span></span> |
| <span data-ttu-id="e259f-210">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-210">**Possible values**</span></span> | <span data-ttu-id="e259f-211">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="e259f-211">false (default)</span></span> <br/> <span data-ttu-id="e259f-212">true</span><span class="sxs-lookup"><span data-stu-id="e259f-212">true</span></span> |
| <span data-ttu-id="e259f-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-213">**Comments**</span></span> | <span data-ttu-id="e259f-214">仅在 *排除$type\*\*时适用*</span><span class="sxs-lookup"><span data-stu-id="e259f-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="e259f-215">从扫描中排除的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="e259f-215">File extension excluded from the scan</span></span>

<span data-ttu-id="e259f-216">指定文件扩展名无法扫描的内容。</span><span class="sxs-lookup"><span data-stu-id="e259f-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-217">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-218">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-218">**Key**</span></span> | <span data-ttu-id="e259f-219">extension</span><span class="sxs-lookup"><span data-stu-id="e259f-219">extension</span></span> |
| <span data-ttu-id="e259f-220">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-220">**Data type**</span></span> | <span data-ttu-id="e259f-221">String</span><span class="sxs-lookup"><span data-stu-id="e259f-221">String</span></span> |
| <span data-ttu-id="e259f-222">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-222">**Possible values**</span></span> | <span data-ttu-id="e259f-223">有效的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="e259f-223">valid file extensions</span></span> |
| <span data-ttu-id="e259f-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-224">**Comments**</span></span> | <span data-ttu-id="e259f-225">仅在 *排除\*\*$type FileExtension 时适用*</span><span class="sxs-lookup"><span data-stu-id="e259f-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="e259f-226">从扫描中排除的进程</span><span class="sxs-lookup"><span data-stu-id="e259f-226">Process excluded from the scan</span></span>

<span data-ttu-id="e259f-227">指定一个进程，所有文件活动都从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="e259f-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="e259f-228">可以通过进程的名称指定进程， (例如) 或完整路径 (`cat` 例如 `/bin/cat`) 。</span><span class="sxs-lookup"><span data-stu-id="e259f-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-229">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-230">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-230">**Key**</span></span> | <span data-ttu-id="e259f-231">name</span><span class="sxs-lookup"><span data-stu-id="e259f-231">name</span></span> |
| <span data-ttu-id="e259f-232">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-232">**Data type**</span></span> | <span data-ttu-id="e259f-233">String</span><span class="sxs-lookup"><span data-stu-id="e259f-233">String</span></span> |
| <span data-ttu-id="e259f-234">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-234">**Possible values**</span></span> | <span data-ttu-id="e259f-235">任何字符串</span><span class="sxs-lookup"><span data-stu-id="e259f-235">any string</span></span> |
| <span data-ttu-id="e259f-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-236">**Comments**</span></span> | <span data-ttu-id="e259f-237">仅在 *排除\*\*$type FileName 时适用*</span><span class="sxs-lookup"><span data-stu-id="e259f-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="e259f-238">允许的威胁</span><span class="sxs-lookup"><span data-stu-id="e259f-238">Allowed threats</span></span>

<span data-ttu-id="e259f-239">按名称指定未由 Defender for Endpoint for Mac 阻止的威胁。</span><span class="sxs-lookup"><span data-stu-id="e259f-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="e259f-240">将允许运行这些威胁。</span><span class="sxs-lookup"><span data-stu-id="e259f-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-241">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-242">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-242">**Key**</span></span> | <span data-ttu-id="e259f-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="e259f-243">allowedThreats</span></span> |
| <span data-ttu-id="e259f-244">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-244">**Data type**</span></span> | <span data-ttu-id="e259f-245">字符串数组</span><span class="sxs-lookup"><span data-stu-id="e259f-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="e259f-246">不允许威胁操作</span><span class="sxs-lookup"><span data-stu-id="e259f-246">Disallowed threat actions</span></span>

<span data-ttu-id="e259f-247">限制设备的本地用户在检测到威胁时可采取的操作。</span><span class="sxs-lookup"><span data-stu-id="e259f-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="e259f-248">此列表中包含的操作不会显示在用户界面中。</span><span class="sxs-lookup"><span data-stu-id="e259f-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-249">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-250">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-250">**Key**</span></span> | <span data-ttu-id="e259f-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="e259f-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="e259f-252">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-252">**Data type**</span></span> | <span data-ttu-id="e259f-253">字符串数组</span><span class="sxs-lookup"><span data-stu-id="e259f-253">Array of strings</span></span> |
| <span data-ttu-id="e259f-254">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-254">**Possible values**</span></span> | <span data-ttu-id="e259f-255">允许 (限制用户允许威胁) </span><span class="sxs-lookup"><span data-stu-id="e259f-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="e259f-256">restore (限制用户从隔离网站还原) </span><span class="sxs-lookup"><span data-stu-id="e259f-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="e259f-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-257">**Comments**</span></span> | <span data-ttu-id="e259f-258">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="e259f-259">威胁类型设置</span><span class="sxs-lookup"><span data-stu-id="e259f-259">Threat type settings</span></span>

<span data-ttu-id="e259f-260">指定 Microsoft Defender for Endpoint for Mac 如何处理某些威胁类型。</span><span class="sxs-lookup"><span data-stu-id="e259f-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-261">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-262">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-262">**Key**</span></span> | <span data-ttu-id="e259f-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="e259f-263">threatTypeSettings</span></span> |
| <span data-ttu-id="e259f-264">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-264">**Data type**</span></span> | <span data-ttu-id="e259f-265">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-266">**Comments**</span></span> | <span data-ttu-id="e259f-267">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="e259f-268">威胁类型</span><span class="sxs-lookup"><span data-stu-id="e259f-268">Threat type</span></span>

<span data-ttu-id="e259f-269">指定威胁类型。</span><span class="sxs-lookup"><span data-stu-id="e259f-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-270">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-271">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-271">**Key**</span></span> | <span data-ttu-id="e259f-272">注册表项</span><span class="sxs-lookup"><span data-stu-id="e259f-272">key</span></span> |
| <span data-ttu-id="e259f-273">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-273">**Data type**</span></span> | <span data-ttu-id="e259f-274">String</span><span class="sxs-lookup"><span data-stu-id="e259f-274">String</span></span> |
| <span data-ttu-id="e259f-275">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-275">**Possible values**</span></span> | <span data-ttu-id="e259f-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="e259f-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="e259f-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="e259f-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="e259f-278">要采取的措施</span><span class="sxs-lookup"><span data-stu-id="e259f-278">Action to take</span></span>

<span data-ttu-id="e259f-279">指定在检测到上一节中指定的类型的威胁时要采取什么操作。</span><span class="sxs-lookup"><span data-stu-id="e259f-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="e259f-280">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="e259f-280">Choose from the following options:</span></span>

- <span data-ttu-id="e259f-281">**审核**：你的设备不受此类型威胁的保护，但会记录关于威胁的条目。</span><span class="sxs-lookup"><span data-stu-id="e259f-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="e259f-282">**阻止**：你的设备受到此类型威胁的保护，并且你将在用户界面和安全控制台中收到通知。</span><span class="sxs-lookup"><span data-stu-id="e259f-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="e259f-283">**关闭**：你的设备不受此类型威胁的防御，并且不会记录任何内容。</span><span class="sxs-lookup"><span data-stu-id="e259f-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-284">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-285">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-285">**Key**</span></span> | <span data-ttu-id="e259f-286">值</span><span class="sxs-lookup"><span data-stu-id="e259f-286">value</span></span> |
| <span data-ttu-id="e259f-287">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-287">**Data type**</span></span> | <span data-ttu-id="e259f-288">String</span><span class="sxs-lookup"><span data-stu-id="e259f-288">String</span></span> |
| <span data-ttu-id="e259f-289">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-289">**Possible values**</span></span> | <span data-ttu-id="e259f-290">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="e259f-290">audit (default)</span></span> <br/> <span data-ttu-id="e259f-291">block</span><span class="sxs-lookup"><span data-stu-id="e259f-291">block</span></span> <br/> <span data-ttu-id="e259f-292">off</span><span class="sxs-lookup"><span data-stu-id="e259f-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="e259f-293">威胁类型设置合并策略</span><span class="sxs-lookup"><span data-stu-id="e259f-293">Threat type settings merge policy</span></span>

<span data-ttu-id="e259f-294">指定威胁类型设置的合并策略。</span><span class="sxs-lookup"><span data-stu-id="e259f-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="e259f-295">这可以是管理员定义的设置和用户定义的设置的组合， () 管理员 `merge` 定义的设置 `admin_only` () 。</span><span class="sxs-lookup"><span data-stu-id="e259f-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="e259f-296">此设置可用于限制本地用户为不同的威胁类型定义自己的设置。</span><span class="sxs-lookup"><span data-stu-id="e259f-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-297">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-298">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-298">**Key**</span></span> | <span data-ttu-id="e259f-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="e259f-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="e259f-300">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-300">**Data type**</span></span> | <span data-ttu-id="e259f-301">String</span><span class="sxs-lookup"><span data-stu-id="e259f-301">String</span></span> |
| <span data-ttu-id="e259f-302">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-302">**Possible values**</span></span> | <span data-ttu-id="e259f-303">合并 (默认) </span><span class="sxs-lookup"><span data-stu-id="e259f-303">merge (default)</span></span> <br/> <span data-ttu-id="e259f-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="e259f-304">admin_only</span></span> |
| <span data-ttu-id="e259f-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-305">**Comments**</span></span> | <span data-ttu-id="e259f-306">适用于终结点版本 100.83.73 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="e259f-307">防病毒扫描历史记录保留 (天数) </span><span class="sxs-lookup"><span data-stu-id="e259f-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="e259f-308">指定结果在设备的扫描历史记录中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="e259f-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="e259f-309">旧扫描结果将从历史记录中删除。</span><span class="sxs-lookup"><span data-stu-id="e259f-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="e259f-310">也从磁盘中删除的旧隔离文件。</span><span class="sxs-lookup"><span data-stu-id="e259f-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-311">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-312">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-312">**Key**</span></span> | <span data-ttu-id="e259f-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="e259f-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="e259f-314">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-314">**Data type**</span></span> | <span data-ttu-id="e259f-315">String</span><span class="sxs-lookup"><span data-stu-id="e259f-315">String</span></span> |
| <span data-ttu-id="e259f-316">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-316">**Possible values**</span></span> | <span data-ttu-id="e259f-317">90 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="e259f-317">90 (default).</span></span> <span data-ttu-id="e259f-318">允许的值从 1 天到 180 天。</span><span class="sxs-lookup"><span data-stu-id="e259f-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="e259f-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-319">**Comments**</span></span> | <span data-ttu-id="e259f-320">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="e259f-321">防病毒扫描历史记录中的最大项目数</span><span class="sxs-lookup"><span data-stu-id="e259f-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="e259f-322">指定在扫描历史记录中保留的最大条目数。</span><span class="sxs-lookup"><span data-stu-id="e259f-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="e259f-323">条目包括过去执行的所有按需扫描以及所有防病毒检测。</span><span class="sxs-lookup"><span data-stu-id="e259f-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-324">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-325">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-325">**Key**</span></span> | <span data-ttu-id="e259f-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="e259f-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="e259f-327">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-327">**Data type**</span></span> | <span data-ttu-id="e259f-328">String</span><span class="sxs-lookup"><span data-stu-id="e259f-328">String</span></span> |
| <span data-ttu-id="e259f-329">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-329">**Possible values**</span></span> | <span data-ttu-id="e259f-330">10000 (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="e259f-330">10000 (default).</span></span> <span data-ttu-id="e259f-331">允许的值从 5000 个项目到 15000 个项目。</span><span class="sxs-lookup"><span data-stu-id="e259f-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="e259f-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-332">**Comments**</span></span> | <span data-ttu-id="e259f-333">适用于终结点版本 101.07.23 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="e259f-334">云提供的保护首选项</span><span class="sxs-lookup"><span data-stu-id="e259f-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="e259f-335">配置 Microsoft Defender for Endpoint for Mac 的云驱动保护功能。</span><span class="sxs-lookup"><span data-stu-id="e259f-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-336">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-337">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-337">**Key**</span></span> | <span data-ttu-id="e259f-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="e259f-338">cloudService</span></span> |
| <span data-ttu-id="e259f-339">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-339">**Data type**</span></span> | <span data-ttu-id="e259f-340">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-341">**Comments**</span></span> | <span data-ttu-id="e259f-342">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="e259f-343">启用/禁用云保护</span><span class="sxs-lookup"><span data-stu-id="e259f-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="e259f-344">指定是否启用云保护设备。</span><span class="sxs-lookup"><span data-stu-id="e259f-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="e259f-345">若要提高服务的安全性，我们建议保持启用此功能。</span><span class="sxs-lookup"><span data-stu-id="e259f-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-346">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-347">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-347">**Key**</span></span> | <span data-ttu-id="e259f-348">enabled</span><span class="sxs-lookup"><span data-stu-id="e259f-348">enabled</span></span> |
| <span data-ttu-id="e259f-349">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-349">**Data type**</span></span> | <span data-ttu-id="e259f-350">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-350">Boolean</span></span> |
| <span data-ttu-id="e259f-351">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-351">**Possible values**</span></span> | <span data-ttu-id="e259f-352">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="e259f-352">true (default)</span></span> <br/> <span data-ttu-id="e259f-353">false</span><span class="sxs-lookup"><span data-stu-id="e259f-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="e259f-354">诊断集合级别</span><span class="sxs-lookup"><span data-stu-id="e259f-354">Diagnostic collection level</span></span>

<span data-ttu-id="e259f-355">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="e259f-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="e259f-356">此设置确定 Microsoft Defender for Endpoint 发送给 Microsoft 的诊断级别。</span><span class="sxs-lookup"><span data-stu-id="e259f-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-357">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-358">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-358">**Key**</span></span> | <span data-ttu-id="e259f-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="e259f-359">diagnosticLevel</span></span> |
| <span data-ttu-id="e259f-360">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-360">**Data type**</span></span> | <span data-ttu-id="e259f-361">String</span><span class="sxs-lookup"><span data-stu-id="e259f-361">String</span></span> |
| <span data-ttu-id="e259f-362">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-362">**Possible values**</span></span> | <span data-ttu-id="e259f-363">可选 (默认) </span><span class="sxs-lookup"><span data-stu-id="e259f-363">optional (default)</span></span> <br/> <span data-ttu-id="e259f-364">必需</span><span class="sxs-lookup"><span data-stu-id="e259f-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="e259f-365">启用/禁用自动示例提交</span><span class="sxs-lookup"><span data-stu-id="e259f-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="e259f-366">确定是否将 (可能包含威胁的可疑) 发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e259f-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="e259f-367">系统将提示你提交的文件是否可能包含个人信息。</span><span class="sxs-lookup"><span data-stu-id="e259f-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-368">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-369">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-369">**Key**</span></span> | <span data-ttu-id="e259f-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="e259f-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="e259f-371">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-371">**Data type**</span></span> | <span data-ttu-id="e259f-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-372">Boolean</span></span> |
| <span data-ttu-id="e259f-373">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-373">**Possible values**</span></span> | <span data-ttu-id="e259f-374">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="e259f-374">true (default)</span></span> <br/> <span data-ttu-id="e259f-375">false</span><span class="sxs-lookup"><span data-stu-id="e259f-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="e259f-376">启用/禁用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="e259f-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="e259f-377">确定是否自动安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="e259f-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-378">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-378">**Key**</span></span> | <span data-ttu-id="e259f-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="e259f-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="e259f-380">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-380">**Data type**</span></span> | <span data-ttu-id="e259f-381">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-381">Boolean</span></span> |
| <span data-ttu-id="e259f-382">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-382">**Possible values**</span></span> | <span data-ttu-id="e259f-383">true (默认值) </span><span class="sxs-lookup"><span data-stu-id="e259f-383">true (default)</span></span> <br/> <span data-ttu-id="e259f-384">false</span><span class="sxs-lookup"><span data-stu-id="e259f-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="e259f-385">用户界面首选项</span><span class="sxs-lookup"><span data-stu-id="e259f-385">User interface preferences</span></span>

<span data-ttu-id="e259f-386">管理 Microsoft Defender for Endpoint for Mac 用户界面的首选项。</span><span class="sxs-lookup"><span data-stu-id="e259f-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-387">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-388">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-388">**Key**</span></span> | <span data-ttu-id="e259f-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="e259f-389">userInterface</span></span> |
| <span data-ttu-id="e259f-390">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-390">**Data type**</span></span> | <span data-ttu-id="e259f-391">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-392">**Comments**</span></span> | <span data-ttu-id="e259f-393">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="e259f-394">显示/隐藏状态菜单图标</span><span class="sxs-lookup"><span data-stu-id="e259f-394">Show / hide status menu icon</span></span>

<span data-ttu-id="e259f-395">指定是显示还是隐藏屏幕右上角的状态菜单图标。</span><span class="sxs-lookup"><span data-stu-id="e259f-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-396">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-397">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-397">**Key**</span></span> | <span data-ttu-id="e259f-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="e259f-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="e259f-399">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-399">**Data type**</span></span> | <span data-ttu-id="e259f-400">Boolean</span><span class="sxs-lookup"><span data-stu-id="e259f-400">Boolean</span></span> |
| <span data-ttu-id="e259f-401">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-401">**Possible values**</span></span> | <span data-ttu-id="e259f-402">false（默认值）</span><span class="sxs-lookup"><span data-stu-id="e259f-402">false (default)</span></span> <br/> <span data-ttu-id="e259f-403">true</span><span class="sxs-lookup"><span data-stu-id="e259f-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="e259f-404">显示/隐藏发送反馈的选项</span><span class="sxs-lookup"><span data-stu-id="e259f-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="e259f-405">指定用户是否可以通过访问 向 Microsoft 提交反馈 `Help`  >  `Send Feedback` 。</span><span class="sxs-lookup"><span data-stu-id="e259f-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-406">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-407">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-407">**Key**</span></span> | <span data-ttu-id="e259f-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="e259f-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="e259f-409">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-409">**Data type**</span></span> | <span data-ttu-id="e259f-410">String</span><span class="sxs-lookup"><span data-stu-id="e259f-410">String</span></span> |
| <span data-ttu-id="e259f-411">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-411">**Possible values**</span></span> | <span data-ttu-id="e259f-412">已启用 (默认) </span><span class="sxs-lookup"><span data-stu-id="e259f-412">enabled (default)</span></span> <br/> <span data-ttu-id="e259f-413">disabled</span><span class="sxs-lookup"><span data-stu-id="e259f-413">disabled</span></span> |
| <span data-ttu-id="e259f-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-414">**Comments**</span></span> | <span data-ttu-id="e259f-415">适用于终结点版本 101.19.61 或更高版本的 Microsoft Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="e259f-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="e259f-416">终结点检测和响应首选项</span><span class="sxs-lookup"><span data-stu-id="e259f-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="e259f-417">管理适用于 Mac 的 Microsoft Defender (EDR) 组件的终结点检测和响应首选项。</span><span class="sxs-lookup"><span data-stu-id="e259f-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-418">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-419">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-419">**Key**</span></span> | <span data-ttu-id="e259f-420">edr</span><span class="sxs-lookup"><span data-stu-id="e259f-420">edr</span></span> |
| <span data-ttu-id="e259f-421">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-421">**Data type**</span></span> | <span data-ttu-id="e259f-422">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-423">**Comments**</span></span> | <span data-ttu-id="e259f-424">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="e259f-425">设备标记</span><span class="sxs-lookup"><span data-stu-id="e259f-425">Device tags</span></span>

<span data-ttu-id="e259f-426">指定标记名称及其值。</span><span class="sxs-lookup"><span data-stu-id="e259f-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="e259f-427">GROUP 标记使用指定值标记设备。</span><span class="sxs-lookup"><span data-stu-id="e259f-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="e259f-428">标记反映在设备页面下的门户中，可用于筛选和分组设备。</span><span class="sxs-lookup"><span data-stu-id="e259f-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-429">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-430">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-430">**Key**</span></span> | <span data-ttu-id="e259f-431">tags</span><span class="sxs-lookup"><span data-stu-id="e259f-431">tags</span></span> |
| <span data-ttu-id="e259f-432">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-432">**Data type**</span></span> | <span data-ttu-id="e259f-433">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="e259f-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e259f-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e259f-434">**Comments**</span></span> | <span data-ttu-id="e259f-435">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="e259f-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="e259f-436">标记类型</span><span class="sxs-lookup"><span data-stu-id="e259f-436">Type of tag</span></span>

<span data-ttu-id="e259f-437">指定标记的类型</span><span class="sxs-lookup"><span data-stu-id="e259f-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-438">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-439">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-439">**Key**</span></span> | <span data-ttu-id="e259f-440">注册表项</span><span class="sxs-lookup"><span data-stu-id="e259f-440">key</span></span> |
| <span data-ttu-id="e259f-441">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-441">**Data type**</span></span> | <span data-ttu-id="e259f-442">String</span><span class="sxs-lookup"><span data-stu-id="e259f-442">String</span></span> |
| <span data-ttu-id="e259f-443">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="e259f-444">tag 的值</span><span class="sxs-lookup"><span data-stu-id="e259f-444">Value of tag</span></span>

<span data-ttu-id="e259f-445">指定 tag 的值</span><span class="sxs-lookup"><span data-stu-id="e259f-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="e259f-446">**域**</span><span class="sxs-lookup"><span data-stu-id="e259f-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e259f-447">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e259f-447">**Key**</span></span> | <span data-ttu-id="e259f-448">值</span><span class="sxs-lookup"><span data-stu-id="e259f-448">value</span></span> |
| <span data-ttu-id="e259f-449">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e259f-449">**Data type**</span></span> | <span data-ttu-id="e259f-450">String</span><span class="sxs-lookup"><span data-stu-id="e259f-450">String</span></span> |
| <span data-ttu-id="e259f-451">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e259f-451">**Possible values**</span></span> | <span data-ttu-id="e259f-452">任何字符串</span><span class="sxs-lookup"><span data-stu-id="e259f-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="e259f-453">每个标记类型只能设置一个值。</span><span class="sxs-lookup"><span data-stu-id="e259f-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="e259f-454">标记类型是唯一的，并且不应在同一配置文件中重复。</span><span class="sxs-lookup"><span data-stu-id="e259f-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="e259f-455">建议的配置文件</span><span class="sxs-lookup"><span data-stu-id="e259f-455">Recommended configuration profile</span></span>

<span data-ttu-id="e259f-456">若要开始，我们建议你的企业采用以下配置，以利用 Microsoft Defender for Endpoint 提供的所有保护功能。</span><span class="sxs-lookup"><span data-stu-id="e259f-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="e259f-457">以下配置文件 (，或者，对于 JAMF，可以上载到自定义设置配置文件中的属性列表) ：</span><span class="sxs-lookup"><span data-stu-id="e259f-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="e259f-458">启用实时保护 (RTP) </span><span class="sxs-lookup"><span data-stu-id="e259f-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="e259f-459">指定如何处理以下威胁类型：</span><span class="sxs-lookup"><span data-stu-id="e259f-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="e259f-460">**阻止 PUA (可能不需要)** 的应用程序</span><span class="sxs-lookup"><span data-stu-id="e259f-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="e259f-461">**使用高** (率存档存档) 将审核到 Microsoft Defender 终结点日志</span><span class="sxs-lookup"><span data-stu-id="e259f-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="e259f-462">启用自动安全智能更新</span><span class="sxs-lookup"><span data-stu-id="e259f-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="e259f-463">启用云保护</span><span class="sxs-lookup"><span data-stu-id="e259f-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="e259f-464">启用自动提交示例</span><span class="sxs-lookup"><span data-stu-id="e259f-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="e259f-465">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="e259f-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="e259f-466">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="e259f-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="e259f-467">完整配置文件示例</span><span class="sxs-lookup"><span data-stu-id="e259f-467">Full configuration profile example</span></span>

<span data-ttu-id="e259f-468">以下模板包含本文档中所述的所有设置的条目，可用于更高级的方案，你想要对 Microsoft Defender for Endpoint for Mac 进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="e259f-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="e259f-469">JAMF 配置文件的属性列表</span><span class="sxs-lookup"><span data-stu-id="e259f-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="e259f-470">Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="e259f-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="e259f-471">属性列表验证</span><span class="sxs-lookup"><span data-stu-id="e259f-471">Property list validation</span></span>

<span data-ttu-id="e259f-472">属性列表必须是有效的 *.plist* 文件。</span><span class="sxs-lookup"><span data-stu-id="e259f-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="e259f-473">可通过执行：</span><span class="sxs-lookup"><span data-stu-id="e259f-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="e259f-474">如果文件格式良好，则上述命令将输出 `OK` 并返回 的退出代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="e259f-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="e259f-475">否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1` 。</span><span class="sxs-lookup"><span data-stu-id="e259f-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="e259f-476">配置文件部署</span><span class="sxs-lookup"><span data-stu-id="e259f-476">Configuration profile deployment</span></span>

<span data-ttu-id="e259f-477">为企业生成配置文件后，可以通过企业使用的管理控制台部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="e259f-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="e259f-478">以下各节提供有关如何使用 JAMF 和 Intune 部署此配置文件的说明。</span><span class="sxs-lookup"><span data-stu-id="e259f-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="e259f-479">JAMF 部署</span><span class="sxs-lookup"><span data-stu-id="e259f-479">JAMF deployment</span></span>

<span data-ttu-id="e259f-480">从 JAMF 控制台中，打开 **"计算机** 配置文件"，导航到你要使用的配置文件，  >  然后选择"自定义 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="e259f-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="e259f-481">使用 创建用作 `com.microsoft.wdav` 首选项域的条目并上载之前生成的 *.plist。*</span><span class="sxs-lookup"><span data-stu-id="e259f-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="e259f-482">必须输入正确的首选项域 `com.microsoft.wdav` () ;否则，Microsoft Defender for Endpoint 无法识别首选项。</span><span class="sxs-lookup"><span data-stu-id="e259f-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="e259f-483">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="e259f-483">Intune deployment</span></span>

1. <span data-ttu-id="e259f-484">打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="e259f-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="e259f-485">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="e259f-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="e259f-486">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e259f-486">Choose a name for the profile.</span></span> <span data-ttu-id="e259f-487">将 **Platform=macOS** 更改为 **配置文件类型=自定义**。</span><span class="sxs-lookup"><span data-stu-id="e259f-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="e259f-488">选择"配置"。</span><span class="sxs-lookup"><span data-stu-id="e259f-488">Select Configure.</span></span>

3. <span data-ttu-id="e259f-489">将之前生成的 .plist 另存为 `com.microsoft.wdav.xml` 。</span><span class="sxs-lookup"><span data-stu-id="e259f-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="e259f-490">输入 `com.microsoft.wdav` 作为 **自定义配置文件名称**。</span><span class="sxs-lookup"><span data-stu-id="e259f-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="e259f-491">打开配置文件并上载 `com.microsoft.wdav.xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="e259f-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="e259f-492"> (此文件是在步骤 3.) </span><span class="sxs-lookup"><span data-stu-id="e259f-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="e259f-493">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e259f-493">Select **OK**.</span></span>

7. <span data-ttu-id="e259f-494">选择 **"管理**  >  **工作分配"。**</span><span class="sxs-lookup"><span data-stu-id="e259f-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="e259f-495">在"**包含"** 选项卡中，**选择"分配给&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="e259f-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="e259f-496">必须输入正确的自定义配置文件名称;否则，Microsoft Defender for Endpoint 无法识别这些首选项。</span><span class="sxs-lookup"><span data-stu-id="e259f-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="e259f-497">资源</span><span class="sxs-lookup"><span data-stu-id="e259f-497">Resources</span></span>

- [<span data-ttu-id="e259f-498">配置文件首选项（Apple 开发人员文档）</span><span class="sxs-lookup"><span data-stu-id="e259f-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
