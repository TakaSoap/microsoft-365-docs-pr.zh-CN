---
title: Mac 上的 Microsoft Defender for Endpoint 的隐私
description: 隐私控制，如何配置影响隐私的策略设置和在 Mac 上的 Microsoft Defender for Endpoint 中收集的诊断数据的信息。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 隐私， 诊断
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
ms.openlocfilehash: 2884ffc695abc1c6b4b5be9bbd7c9ad37ad05439
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651292"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f4261-104">macOS 上适用于终结点的 Microsoft Defender 的隐私</span><span class="sxs-lookup"><span data-stu-id="f4261-104">Privacy for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4261-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f4261-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4261-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4261-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4261-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4261-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4261-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f4261-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4261-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f4261-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="f4261-110">Microsoft 致力于为您提供在 macOS 上使用 Microsoft Defender for Endpoint 时，选择收集和使用数据方式时需要的信息和控件。</span><span class="sxs-lookup"><span data-stu-id="f4261-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="f4261-111">本主题介绍产品内可用的隐私控件、如何使用策略设置管理这些控件，以及所收集的数据事件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4261-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f4261-112">macOS 上适用于终结点的 Microsoft Defender 中的隐私控件概述</span><span class="sxs-lookup"><span data-stu-id="f4261-112">Overview of privacy controls in Microsoft Defender for Endpoint on macOS</span></span>

<span data-ttu-id="f4261-113">本部分介绍由 macOS 上的 Microsoft Defender for Endpoint 收集的不同类型的数据的隐私控制。</span><span class="sxs-lookup"><span data-stu-id="f4261-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="f4261-114">诊断数据</span><span class="sxs-lookup"><span data-stu-id="f4261-114">Diagnostic data</span></span>

<span data-ttu-id="f4261-115">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="f4261-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="f4261-116">某些诊断数据是必需的，而某些诊断数据是可选的。</span><span class="sxs-lookup"><span data-stu-id="f4261-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="f4261-117">我们允许你选择是否通过使用隐私控件（如组织的策略设置）向我们发送必需或可选的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="f4261-118">Microsoft Defender for Endpoint 客户端软件有两个级别的诊断数据可供选择：</span><span class="sxs-lookup"><span data-stu-id="f4261-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="f4261-119">**必需**：帮助确保 Microsoft Defender for Endpoint 安全、最新以及按预期在安装它的设备上按预期运行所需的最低数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="f4261-120">**可选**：帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修正问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="f4261-121">默认情况下，仅向 Microsoft 发送必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="f4261-122">云提供的保护数据</span><span class="sxs-lookup"><span data-stu-id="f4261-122">Cloud delivered protection data</span></span>

<span data-ttu-id="f4261-123">云提供的保护用于通过访问云中的最新保护数据来提供更高和更快的保护。</span><span class="sxs-lookup"><span data-stu-id="f4261-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="f4261-124">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="f4261-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="f4261-125">示例数据</span><span class="sxs-lookup"><span data-stu-id="f4261-125">Sample data</span></span>

<span data-ttu-id="f4261-126">示例数据用于通过发送 Microsoft 可疑示例来改进产品的保护功能，以便可以分析它们。</span><span class="sxs-lookup"><span data-stu-id="f4261-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="f4261-127">启用自动示例提交是可选的。</span><span class="sxs-lookup"><span data-stu-id="f4261-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="f4261-128">启用此功能并且收集的示例可能包含个人信息时，将提示用户征得同意。</span><span class="sxs-lookup"><span data-stu-id="f4261-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="f4261-129">通过策略设置管理隐私控件</span><span class="sxs-lookup"><span data-stu-id="f4261-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="f4261-130">如果您是 IT 管理员，您可能希望在企业级别配置这些控件。</span><span class="sxs-lookup"><span data-stu-id="f4261-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="f4261-131">The privacy controls for the various types of data described in the preceding section are described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="f4261-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="f4261-132">与任何新策略设置一样，应在受限的受控环境中仔细测试它们，以确保在组织中更广泛地实现策略设置之前，所配置的设置具有所需的效果。</span><span class="sxs-lookup"><span data-stu-id="f4261-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="f4261-133">诊断数据事件</span><span class="sxs-lookup"><span data-stu-id="f4261-133">Diagnostic data events</span></span>

<span data-ttu-id="f4261-134">本节介绍哪些内容被视为必需诊断数据以及哪些内容被视为可选诊断数据，以及所收集的事件和字段的说明。</span><span class="sxs-lookup"><span data-stu-id="f4261-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="f4261-135">所有事件常用的数据字段</span><span class="sxs-lookup"><span data-stu-id="f4261-135">Data fields that are common for all events</span></span>
<span data-ttu-id="f4261-136">无论类别或数据子类型如何，所有事件都有一些共同的与事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="f4261-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="f4261-137">以下字段被视为通用于所有事件：</span><span class="sxs-lookup"><span data-stu-id="f4261-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="f4261-138">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-138">Field</span></span>                   | <span data-ttu-id="f4261-139">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="f4261-140">平台</span><span class="sxs-lookup"><span data-stu-id="f4261-140">platform</span></span>                | <span data-ttu-id="f4261-141">应用运行平台的广泛分类。</span><span class="sxs-lookup"><span data-stu-id="f4261-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="f4261-142">允许 Microsoft 确定在哪些平台上可能会发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="f4261-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="f4261-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="f4261-143">machine_guid</span></span>            | <span data-ttu-id="f4261-144">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="f4261-145">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="f4261-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="f4261-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="f4261-146">sense_guid</span></span>              | <span data-ttu-id="f4261-147">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="f4261-148">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="f4261-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="f4261-149">org_id</span><span class="sxs-lookup"><span data-stu-id="f4261-149">org_id</span></span>                  | <span data-ttu-id="f4261-150">与设备所属的企业关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="f4261-151">允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响。</span><span class="sxs-lookup"><span data-stu-id="f4261-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="f4261-152">hostname</span><span class="sxs-lookup"><span data-stu-id="f4261-152">hostname</span></span>                | <span data-ttu-id="f4261-153">本地设备名称 (DNS 后缀) 。</span><span class="sxs-lookup"><span data-stu-id="f4261-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="f4261-154">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="f4261-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="f4261-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="f4261-155">product_guid</span></span>            | <span data-ttu-id="f4261-156">产品的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-156">Unique identifier of the product.</span></span> <span data-ttu-id="f4261-157">允许 Microsoft 区分影响不同产品风格的问题。</span><span class="sxs-lookup"><span data-stu-id="f4261-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="f4261-158">app_version</span><span class="sxs-lookup"><span data-stu-id="f4261-158">app_version</span></span>             | <span data-ttu-id="f4261-159">macOS 应用程序上的 Microsoft Defender for Endpoint 的版本。</span><span class="sxs-lookup"><span data-stu-id="f4261-159">Version of the Microsoft Defender for Endpoint on macOS application.</span></span> <span data-ttu-id="f4261-160">允许 Microsoft 确定哪些版本的产品显示问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="f4261-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="f4261-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="f4261-161">sig_version</span></span>             | <span data-ttu-id="f4261-162">安全智能数据库的版本。</span><span class="sxs-lookup"><span data-stu-id="f4261-162">Version of security intelligence database.</span></span> <span data-ttu-id="f4261-163">允许 Microsoft 标识显示问题的安全智能版本，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="f4261-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="f4261-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="f4261-164">supported_compressions</span></span>  | <span data-ttu-id="f4261-165">应用程序支持的压缩算法列表，例如 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="f4261-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="f4261-166">允许 Microsoft 了解在与应用程序通信时可以使用的压缩类型。</span><span class="sxs-lookup"><span data-stu-id="f4261-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="f4261-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="f4261-167">release_ring</span></span>            | <span data-ttu-id="f4261-168">设备与设备关联的圈， (Insider Fast、Insider Slow、Production) 。</span><span class="sxs-lookup"><span data-stu-id="f4261-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="f4261-169">允许 Microsoft 识别可能在哪个发布环上发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="f4261-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="f4261-170">必需诊断数据</span><span class="sxs-lookup"><span data-stu-id="f4261-170">Required diagnostic data</span></span>

<span data-ttu-id="f4261-171">**必需诊断** 数据是帮助使 Microsoft Defender for Endpoint 保持安全、最新，并按预期在安装它的设备上执行所需的最少数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="f4261-172">必需的诊断数据有助于识别与设备或软件配置相关的 Microsoft Defender for Endpoint 问题。</span><span class="sxs-lookup"><span data-stu-id="f4261-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="f4261-173">例如，它可以帮助确定 Microsoft Defender for Endpoint 功能在特定操作系统版本上崩溃的频率是否更频繁、是否具有新引入的功能，或者何时禁用某些 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="f4261-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="f4261-174">必需的诊断数据可帮助 Microsoft 更快速地检测、诊断和修复这些问题，以便降低对用户或组织的影响。</span><span class="sxs-lookup"><span data-stu-id="f4261-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="f4261-175">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="f4261-175">Software setup and inventory data events</span></span>

<span data-ttu-id="f4261-176">**Microsoft Defender for Endpoint 安装/卸载**</span><span class="sxs-lookup"><span data-stu-id="f4261-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="f4261-177">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-177">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-178">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-178">Field</span></span>            | <span data-ttu-id="f4261-179">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f4261-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="f4261-180">correlation_id</span></span>   | <span data-ttu-id="f4261-181">与安装关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="f4261-182">version</span><span class="sxs-lookup"><span data-stu-id="f4261-182">version</span></span>          | <span data-ttu-id="f4261-183">程序包的版本。</span><span class="sxs-lookup"><span data-stu-id="f4261-183">Version of the package.</span></span> |
| <span data-ttu-id="f4261-184">severity</span><span class="sxs-lookup"><span data-stu-id="f4261-184">severity</span></span>         | <span data-ttu-id="f4261-185">邮件严重性，例如 (信息) 。</span><span class="sxs-lookup"><span data-stu-id="f4261-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="f4261-186">code</span><span class="sxs-lookup"><span data-stu-id="f4261-186">code</span></span>             | <span data-ttu-id="f4261-187">描述操作的代码。</span><span class="sxs-lookup"><span data-stu-id="f4261-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="f4261-188">text</span><span class="sxs-lookup"><span data-stu-id="f4261-188">text</span></span>             | <span data-ttu-id="f4261-189">与产品安装相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f4261-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="f4261-190">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="f4261-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="f4261-191">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-191">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-192">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-192">Field</span></span>                                               | <span data-ttu-id="f4261-193">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="f4261-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="f4261-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="f4261-195">是否在设备上启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="f4261-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="f4261-196">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="f4261-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="f4261-197">是否在设备上启用被动模式。</span><span class="sxs-lookup"><span data-stu-id="f4261-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="f4261-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="f4261-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="f4261-199">是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="f4261-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="f4261-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="f4261-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="f4261-201">当应用程序与 Microsoft Defender for Endpoint 云通信时，将退出。</span><span class="sxs-lookup"><span data-stu-id="f4261-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="f4261-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="f4261-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="f4261-203">产品发送到云的连续检测信号之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="f4261-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="f4261-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="f4261-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="f4261-205">用于与云通信的 URI。</span><span class="sxs-lookup"><span data-stu-id="f4261-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="f4261-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="f4261-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="f4261-207">设备诊断级别 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="f4261-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="f4261-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="f4261-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="f4261-209">是否打开自动提交示例。</span><span class="sxs-lookup"><span data-stu-id="f4261-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="f4261-210">cloud_service.automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="f4261-210">cloud_service.automatic_definition_update_enabled</span></span>   | <span data-ttu-id="f4261-211">是否启用自动定义更新。</span><span class="sxs-lookup"><span data-stu-id="f4261-211">Whether automatic definition update is turned on or not.</span></span> |
| <span data-ttu-id="f4261-212">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="f4261-212">edr.early_preview</span></span>                                   | <span data-ttu-id="f4261-213">设备是否应该运行EDR早期预览功能。</span><span class="sxs-lookup"><span data-stu-id="f4261-213">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="f4261-214">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="f4261-214">edr.group_id</span></span>                                        | <span data-ttu-id="f4261-215">检测和响应组件使用的组标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-215">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="f4261-216">edr.tags</span><span class="sxs-lookup"><span data-stu-id="f4261-216">edr.tags</span></span>                                            | <span data-ttu-id="f4261-217">用户定义的标记。</span><span class="sxs-lookup"><span data-stu-id="f4261-217">User-defined tags.</span></span> |
| <span data-ttu-id="f4261-218">功能。 \[可选功能名称\]</span><span class="sxs-lookup"><span data-stu-id="f4261-218">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="f4261-219">预览功能列表，以及是否已启用。</span><span class="sxs-lookup"><span data-stu-id="f4261-219">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="f4261-220">产品和服务使用情况数据事件</span><span class="sxs-lookup"><span data-stu-id="f4261-220">Product and service usage data events</span></span>

<span data-ttu-id="f4261-221">**安全智能更新报告**</span><span class="sxs-lookup"><span data-stu-id="f4261-221">**Security intelligence update report**</span></span>

<span data-ttu-id="f4261-222">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-222">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-223">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-223">Field</span></span>            | <span data-ttu-id="f4261-224">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-224">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f4261-225">from_version</span><span class="sxs-lookup"><span data-stu-id="f4261-225">from_version</span></span>     | <span data-ttu-id="f4261-226">原始安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="f4261-226">Original security intelligence version.</span></span> |
| <span data-ttu-id="f4261-227">to_version</span><span class="sxs-lookup"><span data-stu-id="f4261-227">to_version</span></span>       | <span data-ttu-id="f4261-228">新的安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="f4261-228">New security intelligence version.</span></span> |
| <span data-ttu-id="f4261-229">状态</span><span class="sxs-lookup"><span data-stu-id="f4261-229">status</span></span>           | <span data-ttu-id="f4261-230">指示成功或失败的更新的状态。</span><span class="sxs-lookup"><span data-stu-id="f4261-230">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="f4261-231">using_proxy</span><span class="sxs-lookup"><span data-stu-id="f4261-231">using_proxy</span></span>      | <span data-ttu-id="f4261-232">更新是否通过代理完成。</span><span class="sxs-lookup"><span data-stu-id="f4261-232">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="f4261-233">error</span><span class="sxs-lookup"><span data-stu-id="f4261-233">error</span></span>            | <span data-ttu-id="f4261-234">更新失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="f4261-234">Error code if the update failed.</span></span> |
| <span data-ttu-id="f4261-235">reason</span><span class="sxs-lookup"><span data-stu-id="f4261-235">reason</span></span>           | <span data-ttu-id="f4261-236">如果更新的存档，则显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="f4261-236">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="f4261-237">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="f4261-237">Product and service performance data events</span></span>

<span data-ttu-id="f4261-238">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="f4261-238">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="f4261-239">在应用程序意外退出时收集系统信息和应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="f4261-239">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="f4261-240">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-240">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-241">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-241">Field</span></span>                          | <span data-ttu-id="f4261-242">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-242">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="f4261-243">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="f4261-243">v1_crash_count</span></span>                 | <span data-ttu-id="f4261-244">每小时 V1 引擎进程在客户端计算机上崩溃次数</span><span class="sxs-lookup"><span data-stu-id="f4261-244">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="f4261-245">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="f4261-245">v2_crash_count</span></span>                 | <span data-ttu-id="f4261-246">每小时 V2 引擎进程在客户端计算机上崩溃次数</span><span class="sxs-lookup"><span data-stu-id="f4261-246">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="f4261-247">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="f4261-247">EDR_crash_count</span></span>                | <span data-ttu-id="f4261-248">客户端计算机上EDR进程每小时崩溃次数</span><span class="sxs-lookup"><span data-stu-id="f4261-248">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="f4261-249">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="f4261-249">**Kernel extension statistics**</span></span>

<span data-ttu-id="f4261-250">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-250">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-251">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-251">Field</span></span>            | <span data-ttu-id="f4261-252">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-252">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f4261-253">version</span><span class="sxs-lookup"><span data-stu-id="f4261-253">version</span></span>          | <span data-ttu-id="f4261-254">macOS 上终结点的 Microsoft Defender 版本。</span><span class="sxs-lookup"><span data-stu-id="f4261-254">Version of Microsoft Defender for Endpoint on macOS.</span></span> |
| <span data-ttu-id="f4261-255">instance_id</span><span class="sxs-lookup"><span data-stu-id="f4261-255">instance_id</span></span>      | <span data-ttu-id="f4261-256">内核扩展启动时生成的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-256">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="f4261-257">trace_level</span><span class="sxs-lookup"><span data-stu-id="f4261-257">trace_level</span></span>      | <span data-ttu-id="f4261-258">内核扩展的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="f4261-258">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="f4261-259">subsystem</span><span class="sxs-lookup"><span data-stu-id="f4261-259">subsystem</span></span>        | <span data-ttu-id="f4261-260">用于实时保护的基础子系统。</span><span class="sxs-lookup"><span data-stu-id="f4261-260">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="f4261-261">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="f4261-261">ipc.connects</span></span>     | <span data-ttu-id="f4261-262">内核扩展接收的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="f4261-262">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="f4261-263">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="f4261-263">ipc.rejects</span></span>      | <span data-ttu-id="f4261-264">内核扩展拒绝的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="f4261-264">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="f4261-265">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="f4261-265">ipc.connected</span></span>    | <span data-ttu-id="f4261-266">是否有到内核扩展的活动连接。</span><span class="sxs-lookup"><span data-stu-id="f4261-266">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="f4261-267">支持数据</span><span class="sxs-lookup"><span data-stu-id="f4261-267">Support data</span></span>

<span data-ttu-id="f4261-268">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="f4261-268">**Diagnostic logs**</span></span>

<span data-ttu-id="f4261-269">仅在用户同意的情况下收集诊断日志作为反馈提交功能一部分。</span><span class="sxs-lookup"><span data-stu-id="f4261-269">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="f4261-270">将收集以下文件作为支持日志的一部分：</span><span class="sxs-lookup"><span data-stu-id="f4261-270">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="f4261-271">*/Library/Logs/Microsoft/mdatp/ 下的所有文件*</span><span class="sxs-lookup"><span data-stu-id="f4261-271">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="f4261-272">macOS 上的 Microsoft Defender for Endpoint 创建和使用的 */Library/Application Support/Microsoft/Defender/* 下的文件子集</span><span class="sxs-lookup"><span data-stu-id="f4261-272">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="f4261-273">macOS 上的 Microsoft Defender for Endpoint 使用的 */Library/Managed Preferences* 下的文件子集</span><span class="sxs-lookup"><span data-stu-id="f4261-273">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="f4261-274">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="f4261-274">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="f4261-275">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="f4261-275">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="f4261-276">可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="f4261-276">Optional diagnostic data</span></span>

<span data-ttu-id="f4261-277">**可选诊断** 数据是可帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修复问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-277">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="f4261-278">如果你选择向我们发送可选诊断数据，则还需要包括必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="f4261-278">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="f4261-279">可选诊断数据的示例包括 Microsoft 收集有关产品配置 (例如设备) 上设置的排除数的数据 (以及有关产品) 组件性能的聚合度量。</span><span class="sxs-lookup"><span data-stu-id="f4261-279">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="f4261-280">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="f4261-280">Software setup and inventory data events</span></span>

<span data-ttu-id="f4261-281">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="f4261-281">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="f4261-282">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-282">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-283">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-283">Field</span></span>                                              | <span data-ttu-id="f4261-284">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-284">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="f4261-285">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="f4261-285">connection_retry_timeout</span></span>                           | <span data-ttu-id="f4261-286">与云通信时，连接重试次数将退出。</span><span class="sxs-lookup"><span data-stu-id="f4261-286">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="f4261-287">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="f4261-287">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="f4261-288">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="f4261-288">Size of the product cache.</span></span> |
| <span data-ttu-id="f4261-289">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="f4261-289">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="f4261-290">每日上载的崩溃日志的限制。</span><span class="sxs-lookup"><span data-stu-id="f4261-290">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="f4261-291">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="f4261-291">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="f4261-292">扫描排除项是否是目录。</span><span class="sxs-lookup"><span data-stu-id="f4261-292">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="f4261-293">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="f4261-293">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="f4261-294">从扫描中排除的路径。</span><span class="sxs-lookup"><span data-stu-id="f4261-294">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="f4261-295">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="f4261-295">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="f4261-296">从扫描中排除的扩展。</span><span class="sxs-lookup"><span data-stu-id="f4261-296">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="f4261-297">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="f4261-297">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="f4261-298">从扫描中排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f4261-298">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="f4261-299">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="f4261-299">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="f4261-300">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="f4261-300">Size of the product cache.</span></span> |
| <span data-ttu-id="f4261-301">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="f4261-301">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="f4261-302">用于扫描的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="f4261-302">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="f4261-303">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="f4261-303">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="f4261-304">从隔离区还原的文件可以再次检测到之前，该时间已过。</span><span class="sxs-lookup"><span data-stu-id="f4261-304">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="f4261-305">antivirus_engine.threat_type_settings</span><span class="sxs-lookup"><span data-stu-id="f4261-305">antivirus_engine.threat_type_settings</span></span>              | <span data-ttu-id="f4261-306">产品如何处理不同威胁类型的配置。</span><span class="sxs-lookup"><span data-stu-id="f4261-306">Configuration for how different threat types are handled by the product.</span></span> |
| <span data-ttu-id="f4261-307">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="f4261-307">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="f4261-308">完全扫描目录。</span><span class="sxs-lookup"><span data-stu-id="f4261-308">Full scan directory.</span></span> |
| <span data-ttu-id="f4261-309">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="f4261-309">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="f4261-310">快速扫描中使用的目录列表。</span><span class="sxs-lookup"><span data-stu-id="f4261-310">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="f4261-311">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="f4261-311">edr.latency_mode</span></span>                                   | <span data-ttu-id="f4261-312">检测和响应组件使用的延迟模式。</span><span class="sxs-lookup"><span data-stu-id="f4261-312">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="f4261-313">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="f4261-313">edr.proxy_address</span></span>                                  | <span data-ttu-id="f4261-314">检测和响应组件使用的代理地址。</span><span class="sxs-lookup"><span data-stu-id="f4261-314">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="f4261-315">**Microsoft 自动更新配置**</span><span class="sxs-lookup"><span data-stu-id="f4261-315">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="f4261-316">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-316">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-317">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-317">Field</span></span>                       | <span data-ttu-id="f4261-318">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-318">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="f4261-319">how_to_check</span><span class="sxs-lookup"><span data-stu-id="f4261-319">how_to_check</span></span>                | <span data-ttu-id="f4261-320">确定如何检查产品更新 (例如自动或手动) 。</span><span class="sxs-lookup"><span data-stu-id="f4261-320">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="f4261-321">channel_name</span><span class="sxs-lookup"><span data-stu-id="f4261-321">channel_name</span></span>                | <span data-ttu-id="f4261-322">更新与设备关联的通道。</span><span class="sxs-lookup"><span data-stu-id="f4261-322">Update channel associated with the device.</span></span> |
| <span data-ttu-id="f4261-323">manifest_server</span><span class="sxs-lookup"><span data-stu-id="f4261-323">manifest_server</span></span>             | <span data-ttu-id="f4261-324">用于下载更新的服务器。</span><span class="sxs-lookup"><span data-stu-id="f4261-324">Server used for downloading updates.</span></span> |
| <span data-ttu-id="f4261-325">update_cache</span><span class="sxs-lookup"><span data-stu-id="f4261-325">update_cache</span></span>                | <span data-ttu-id="f4261-326">用于存储更新的缓存的位置。</span><span class="sxs-lookup"><span data-stu-id="f4261-326">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="f4261-327">产品和服务使用情况</span><span class="sxs-lookup"><span data-stu-id="f4261-327">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="f4261-328">诊断日志上载开始报告</span><span class="sxs-lookup"><span data-stu-id="f4261-328">Diagnostic log upload started report</span></span>

<span data-ttu-id="f4261-329">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-329">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-330">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-330">Field</span></span>            | <span data-ttu-id="f4261-331">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-331">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f4261-332">sha256</span><span class="sxs-lookup"><span data-stu-id="f4261-332">sha256</span></span>           | <span data-ttu-id="f4261-333">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-333">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="f4261-334">大小</span><span class="sxs-lookup"><span data-stu-id="f4261-334">size</span></span>             | <span data-ttu-id="f4261-335">支持日志的大小。</span><span class="sxs-lookup"><span data-stu-id="f4261-335">Size of the support log.</span></span> |
| <span data-ttu-id="f4261-336">original_path</span><span class="sxs-lookup"><span data-stu-id="f4261-336">original_path</span></span>    | <span data-ttu-id="f4261-337">始终在 */library/ (/Microsoft/Defender/wdavdiag/ 下* 的支持日志) 。</span><span class="sxs-lookup"><span data-stu-id="f4261-337">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="f4261-338">format</span><span class="sxs-lookup"><span data-stu-id="f4261-338">format</span></span>           | <span data-ttu-id="f4261-339">支持日志的格式。</span><span class="sxs-lookup"><span data-stu-id="f4261-339">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="f4261-340">诊断日志上载已完成报告</span><span class="sxs-lookup"><span data-stu-id="f4261-340">Diagnostic log upload completed report</span></span>

<span data-ttu-id="f4261-341">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-341">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-342">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-342">Field</span></span>            | <span data-ttu-id="f4261-343">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-343">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="f4261-344">request_id</span><span class="sxs-lookup"><span data-stu-id="f4261-344">request_id</span></span>       | <span data-ttu-id="f4261-345">支持日志上载请求的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="f4261-345">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="f4261-346">sha256</span><span class="sxs-lookup"><span data-stu-id="f4261-346">sha256</span></span>           | <span data-ttu-id="f4261-347">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="f4261-347">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="f4261-348">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="f4261-348">blob_sas_uri</span></span>     | <span data-ttu-id="f4261-349">应用程序用于上载支持日志的 URI。</span><span class="sxs-lookup"><span data-stu-id="f4261-349">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="f4261-350">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="f4261-350">Product and service performance data events</span></span>

<span data-ttu-id="f4261-351">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="f4261-351">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="f4261-352">应用程序意外退出以及发生这种情况时的应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="f4261-352">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="f4261-353">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="f4261-353">**Kernel extension statistics**</span></span>

<span data-ttu-id="f4261-354">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="f4261-354">The following fields are collected:</span></span>

| <span data-ttu-id="f4261-355">字段</span><span class="sxs-lookup"><span data-stu-id="f4261-355">Field</span></span>                          | <span data-ttu-id="f4261-356">说明</span><span class="sxs-lookup"><span data-stu-id="f4261-356">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="f4261-357">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="f4261-357">pkt_ack_timeout</span></span>                | <span data-ttu-id="f4261-358">以下属性是聚合的数值，表示自内核扩展启动后发生的事件数。</span><span class="sxs-lookup"><span data-stu-id="f4261-358">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="f4261-359">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="f4261-359">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="f4261-360">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="f4261-360">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="f4261-361">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="f4261-361">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="f4261-362">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="f4261-362">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="f4261-363">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="f4261-363">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="f4261-364">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="f4261-364">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="f4261-365">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="f4261-365">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="f4261-366">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="f4261-366">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="f4261-367">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="f4261-367">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="f4261-368">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="f4261-368">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="f4261-369">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="f4261-369">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="f4261-370">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="f4261-370">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="f4261-371">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="f4261-371">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="f4261-372">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="f4261-372">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="f4261-373">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="f4261-373">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="f4261-374">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="f4261-374">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="f4261-375">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="f4261-375">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="f4261-376">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="f4261-376">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="f4261-377">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="f4261-377">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="f4261-378">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="f4261-378">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="f4261-379">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="f4261-379">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="f4261-380">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="f4261-380">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="f4261-381">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="f4261-381">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="f4261-382">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="f4261-382">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="f4261-383">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="f4261-383">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="f4261-384">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="f4261-384">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="f4261-385">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="f4261-385">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="f4261-386">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="f4261-386">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="f4261-387">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="f4261-387">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="f4261-388">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="f4261-388">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="f4261-389">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="f4261-389">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="f4261-390">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="f4261-390">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="f4261-391">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="f4261-391">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="f4261-392">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="f4261-392">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="f4261-393">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="f4261-393">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="f4261-394">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="f4261-394">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="f4261-395">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="f4261-395">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="f4261-396">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="f4261-396">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="f4261-397">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="f4261-397">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="f4261-398">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="f4261-398">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="f4261-399">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="f4261-399">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="f4261-400">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="f4261-400">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="f4261-401">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="f4261-401">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="f4261-402">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="f4261-402">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="f4261-403">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="f4261-403">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="f4261-404">资源</span><span class="sxs-lookup"><span data-stu-id="f4261-404">Resources</span></span>

- [<span data-ttu-id="f4261-405">Microsoft 隐私</span><span class="sxs-lookup"><span data-stu-id="f4261-405">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
