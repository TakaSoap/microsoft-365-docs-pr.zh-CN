---
title: Microsoft Defender ATP for Mac 的隐私
description: 隐私控制，如何配置影响隐私的策略设置和有关在 Microsoft Defender ATP for Mac 中收集的诊断数据的信息。
keywords: microsoft， defender， atp， mac， 隐私， 诊断
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
ms.openlocfilehash: 93715f761beded95cfaa91b4747a2e4b5a3c61c1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689673"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="e2d71-104">macOS 上适用于终结点的 Microsoft Defender 的隐私</span><span class="sxs-lookup"><span data-stu-id="e2d71-104">Privacy for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2d71-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e2d71-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2d71-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e2d71-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e2d71-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2d71-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e2d71-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e2d71-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e2d71-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e2d71-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="e2d71-110">Microsoft 致力于为您提供在 macOS 上使用 Microsoft Defender for Endpoint 时，选择收集和使用数据方式时需要的信息和控件。</span><span class="sxs-lookup"><span data-stu-id="e2d71-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="e2d71-111">本主题介绍产品内可用的隐私控件、如何使用策略设置管理这些控件，以及所收集的数据事件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2d71-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="e2d71-112">macOS 上适用于终结点的 Microsoft Defender 中的隐私控件概述</span><span class="sxs-lookup"><span data-stu-id="e2d71-112">Overview of privacy controls in Microsoft Defender for Endpoint on macOS</span></span>

<span data-ttu-id="e2d71-113">本部分介绍由 macOS 上的 Microsoft Defender for Endpoint 收集的不同类型的数据的隐私控制。</span><span class="sxs-lookup"><span data-stu-id="e2d71-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="e2d71-114">诊断数据</span><span class="sxs-lookup"><span data-stu-id="e2d71-114">Diagnostic data</span></span>

<span data-ttu-id="e2d71-115">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="e2d71-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="e2d71-116">某些诊断数据是必需的，而某些诊断数据是可选的。</span><span class="sxs-lookup"><span data-stu-id="e2d71-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="e2d71-117">我们允许你选择是否通过使用隐私控件（如组织的策略设置）向我们发送必需或可选的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="e2d71-118">Microsoft Defender for Endpoint 客户端软件有两个级别的诊断数据可供选择：</span><span class="sxs-lookup"><span data-stu-id="e2d71-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="e2d71-119">**必需**：帮助确保 Microsoft Defender for Endpoint 安全、最新以及按预期在安装它的设备上按预期运行所需的最低数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="e2d71-120">**可选**：帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修正问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="e2d71-121">默认情况下，仅向 Microsoft 发送必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="e2d71-122">云提供的保护数据</span><span class="sxs-lookup"><span data-stu-id="e2d71-122">Cloud delivered protection data</span></span>

<span data-ttu-id="e2d71-123">云提供的保护用于通过访问云中的最新保护数据来提供更高和更快的保护。</span><span class="sxs-lookup"><span data-stu-id="e2d71-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="e2d71-124">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="e2d71-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="e2d71-125">示例数据</span><span class="sxs-lookup"><span data-stu-id="e2d71-125">Sample data</span></span>

<span data-ttu-id="e2d71-126">示例数据用于通过发送 Microsoft 可疑示例来改进产品的保护功能，以便可以分析它们。</span><span class="sxs-lookup"><span data-stu-id="e2d71-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="e2d71-127">启用自动示例提交是可选的。</span><span class="sxs-lookup"><span data-stu-id="e2d71-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="e2d71-128">启用此功能并且收集的示例可能包含个人信息时，将提示用户征得同意。</span><span class="sxs-lookup"><span data-stu-id="e2d71-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="e2d71-129">通过策略设置管理隐私控件</span><span class="sxs-lookup"><span data-stu-id="e2d71-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="e2d71-130">如果您是 IT 管理员，您可能希望在企业级别配置这些控件。</span><span class="sxs-lookup"><span data-stu-id="e2d71-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="e2d71-131">The privacy controls for the various types of data described in the preceding section are described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="e2d71-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="e2d71-132">与任何新策略设置一样，应在受限的受控环境中仔细测试它们，以确保在组织中更广泛地实现策略设置之前，所配置的设置具有所需的效果。</span><span class="sxs-lookup"><span data-stu-id="e2d71-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="e2d71-133">诊断数据事件</span><span class="sxs-lookup"><span data-stu-id="e2d71-133">Diagnostic data events</span></span>

<span data-ttu-id="e2d71-134">本节介绍哪些内容被视为必需诊断数据以及哪些内容被视为可选诊断数据，以及所收集的事件和字段的说明。</span><span class="sxs-lookup"><span data-stu-id="e2d71-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="e2d71-135">所有事件常用的数据字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-135">Data fields that are common for all events</span></span>
<span data-ttu-id="e2d71-136">无论类别或数据子类型如何，所有事件都有一些共同的与事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="e2d71-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="e2d71-137">以下字段被视为通用于所有事件：</span><span class="sxs-lookup"><span data-stu-id="e2d71-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="e2d71-138">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-138">Field</span></span>                   | <span data-ttu-id="e2d71-139">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="e2d71-140">平台</span><span class="sxs-lookup"><span data-stu-id="e2d71-140">platform</span></span>                | <span data-ttu-id="e2d71-141">应用运行平台的广泛分类。</span><span class="sxs-lookup"><span data-stu-id="e2d71-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="e2d71-142">允许 Microsoft 确定在哪些平台上可能会发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="e2d71-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="e2d71-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="e2d71-143">machine_guid</span></span>            | <span data-ttu-id="e2d71-144">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="e2d71-145">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="e2d71-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="e2d71-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="e2d71-146">sense_guid</span></span>              | <span data-ttu-id="e2d71-147">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="e2d71-148">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="e2d71-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="e2d71-149">org_id</span><span class="sxs-lookup"><span data-stu-id="e2d71-149">org_id</span></span>                  | <span data-ttu-id="e2d71-150">与设备所属的企业关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="e2d71-151">允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响。</span><span class="sxs-lookup"><span data-stu-id="e2d71-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="e2d71-152">hostname</span><span class="sxs-lookup"><span data-stu-id="e2d71-152">hostname</span></span>                | <span data-ttu-id="e2d71-153">本地设备名称 (DNS 后缀) 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="e2d71-154">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="e2d71-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="e2d71-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="e2d71-155">product_guid</span></span>            | <span data-ttu-id="e2d71-156">产品的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-156">Unique identifier of the product.</span></span> <span data-ttu-id="e2d71-157">允许 Microsoft 区分影响不同产品风格的问题。</span><span class="sxs-lookup"><span data-stu-id="e2d71-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="e2d71-158">app_version</span><span class="sxs-lookup"><span data-stu-id="e2d71-158">app_version</span></span>             | <span data-ttu-id="e2d71-159">macOS 应用程序上的 Microsoft Defender for Endpoint 的版本。</span><span class="sxs-lookup"><span data-stu-id="e2d71-159">Version of the Microsoft Defender for Endpoint on macOS application.</span></span> <span data-ttu-id="e2d71-160">允许 Microsoft 确定哪些版本的产品显示问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="e2d71-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="e2d71-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="e2d71-161">sig_version</span></span>             | <span data-ttu-id="e2d71-162">安全智能数据库的版本。</span><span class="sxs-lookup"><span data-stu-id="e2d71-162">Version of security intelligence database.</span></span> <span data-ttu-id="e2d71-163">允许 Microsoft 标识显示问题的安全智能版本，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="e2d71-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="e2d71-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="e2d71-164">supported_compressions</span></span>  | <span data-ttu-id="e2d71-165">应用程序支持的压缩算法列表，例如 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="e2d71-166">允许 Microsoft 了解在与应用程序通信时可以使用的压缩类型。</span><span class="sxs-lookup"><span data-stu-id="e2d71-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="e2d71-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="e2d71-167">release_ring</span></span>            | <span data-ttu-id="e2d71-168">设备与设备关联的圈， (Insider Fast、Insider Slow、Production) 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="e2d71-169">允许 Microsoft 识别可能在哪个发布环上发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="e2d71-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="e2d71-170">必需诊断数据</span><span class="sxs-lookup"><span data-stu-id="e2d71-170">Required diagnostic data</span></span>

<span data-ttu-id="e2d71-171">**必需诊断** 数据是帮助使 Microsoft Defender for Endpoint 保持安全、最新，并按预期在安装它的设备上执行所需的最少数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="e2d71-172">必需的诊断数据有助于识别与设备或软件配置相关的 Microsoft Defender for Endpoint 问题。</span><span class="sxs-lookup"><span data-stu-id="e2d71-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="e2d71-173">例如，它可以帮助确定 Microsoft Defender for Endpoint 功能在特定操作系统版本上崩溃的频率是否更频繁、是否具有新引入的功能，或者何时禁用某些 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="e2d71-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="e2d71-174">必需的诊断数据可帮助 Microsoft 更快速地检测、诊断和修复这些问题，以便降低对用户或组织的影响。</span><span class="sxs-lookup"><span data-stu-id="e2d71-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="e2d71-175">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="e2d71-175">Software setup and inventory data events</span></span>

<span data-ttu-id="e2d71-176">**Microsoft Defender for Endpoint 安装/卸载**</span><span class="sxs-lookup"><span data-stu-id="e2d71-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="e2d71-177">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-177">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-178">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-178">Field</span></span>            | <span data-ttu-id="e2d71-179">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="e2d71-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="e2d71-180">correlation_id</span></span>   | <span data-ttu-id="e2d71-181">与安装关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="e2d71-182">version</span><span class="sxs-lookup"><span data-stu-id="e2d71-182">version</span></span>          | <span data-ttu-id="e2d71-183">程序包的版本。</span><span class="sxs-lookup"><span data-stu-id="e2d71-183">Version of the package.</span></span> |
| <span data-ttu-id="e2d71-184">severity</span><span class="sxs-lookup"><span data-stu-id="e2d71-184">severity</span></span>         | <span data-ttu-id="e2d71-185">邮件严重性，例如 (信息) 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="e2d71-186">code</span><span class="sxs-lookup"><span data-stu-id="e2d71-186">code</span></span>             | <span data-ttu-id="e2d71-187">描述操作的代码。</span><span class="sxs-lookup"><span data-stu-id="e2d71-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="e2d71-188">text</span><span class="sxs-lookup"><span data-stu-id="e2d71-188">text</span></span>             | <span data-ttu-id="e2d71-189">与产品安装相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e2d71-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="e2d71-190">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="e2d71-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="e2d71-191">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-191">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-192">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-192">Field</span></span>                                               | <span data-ttu-id="e2d71-193">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="e2d71-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="e2d71-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="e2d71-195">是否在设备上启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="e2d71-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="e2d71-196">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="e2d71-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="e2d71-197">是否在设备上启用被动模式。</span><span class="sxs-lookup"><span data-stu-id="e2d71-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="e2d71-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="e2d71-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="e2d71-199">是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="e2d71-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="e2d71-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="e2d71-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="e2d71-201">当应用程序与 Microsoft Defender for Endpoint 云通信时，将退出。</span><span class="sxs-lookup"><span data-stu-id="e2d71-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="e2d71-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="e2d71-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="e2d71-203">产品发送到云的连续检测信号之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="e2d71-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="e2d71-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="e2d71-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="e2d71-205">用于与云通信的 URI。</span><span class="sxs-lookup"><span data-stu-id="e2d71-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="e2d71-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="e2d71-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="e2d71-207">设备诊断级别 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="e2d71-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="e2d71-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="e2d71-209">是否打开自动提交示例。</span><span class="sxs-lookup"><span data-stu-id="e2d71-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="e2d71-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="e2d71-210">edr.early_preview</span></span>                                   | <span data-ttu-id="e2d71-211">设备是否应该运行 EDR 早期预览功能。</span><span class="sxs-lookup"><span data-stu-id="e2d71-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="e2d71-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="e2d71-212">edr.group_id</span></span>                                        | <span data-ttu-id="e2d71-213">检测和响应组件使用的组标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="e2d71-214">edr.tags</span><span class="sxs-lookup"><span data-stu-id="e2d71-214">edr.tags</span></span>                                            | <span data-ttu-id="e2d71-215">用户定义的标记。</span><span class="sxs-lookup"><span data-stu-id="e2d71-215">User-defined tags.</span></span> |
| <span data-ttu-id="e2d71-216">功能。 \[可选功能名称\]</span><span class="sxs-lookup"><span data-stu-id="e2d71-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="e2d71-217">预览功能列表，以及是否已启用。</span><span class="sxs-lookup"><span data-stu-id="e2d71-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="e2d71-218">产品和服务使用情况数据事件</span><span class="sxs-lookup"><span data-stu-id="e2d71-218">Product and service usage data events</span></span>

<span data-ttu-id="e2d71-219">**安全智能更新报告**</span><span class="sxs-lookup"><span data-stu-id="e2d71-219">**Security intelligence update report**</span></span>

<span data-ttu-id="e2d71-220">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-220">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-221">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-221">Field</span></span>            | <span data-ttu-id="e2d71-222">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="e2d71-223">from_version</span><span class="sxs-lookup"><span data-stu-id="e2d71-223">from_version</span></span>     | <span data-ttu-id="e2d71-224">原始安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="e2d71-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="e2d71-225">to_version</span><span class="sxs-lookup"><span data-stu-id="e2d71-225">to_version</span></span>       | <span data-ttu-id="e2d71-226">新的安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="e2d71-226">New security intelligence version.</span></span> |
| <span data-ttu-id="e2d71-227">状态</span><span class="sxs-lookup"><span data-stu-id="e2d71-227">status</span></span>           | <span data-ttu-id="e2d71-228">指示成功或失败的更新的状态。</span><span class="sxs-lookup"><span data-stu-id="e2d71-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="e2d71-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="e2d71-229">using_proxy</span></span>      | <span data-ttu-id="e2d71-230">更新是否通过代理完成。</span><span class="sxs-lookup"><span data-stu-id="e2d71-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="e2d71-231">error</span><span class="sxs-lookup"><span data-stu-id="e2d71-231">error</span></span>            | <span data-ttu-id="e2d71-232">更新失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="e2d71-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="e2d71-233">reason</span><span class="sxs-lookup"><span data-stu-id="e2d71-233">reason</span></span>           | <span data-ttu-id="e2d71-234">如果更新的存档，则显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="e2d71-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="e2d71-235">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="e2d71-235">Product and service performance data events</span></span>

<span data-ttu-id="e2d71-236">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="e2d71-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="e2d71-237">在应用程序意外退出时收集系统信息和应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="e2d71-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="e2d71-238">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-238">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-239">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-239">Field</span></span>                          | <span data-ttu-id="e2d71-240">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="e2d71-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="e2d71-241">v1_crash_count</span></span>                 | <span data-ttu-id="e2d71-242">每小时 V1 引擎进程在客户端计算机上崩溃次数</span><span class="sxs-lookup"><span data-stu-id="e2d71-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="e2d71-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="e2d71-243">v2_crash_count</span></span>                 | <span data-ttu-id="e2d71-244">每小时 V2 引擎进程在客户端计算机上崩溃次数</span><span class="sxs-lookup"><span data-stu-id="e2d71-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="e2d71-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="e2d71-245">EDR_crash_count</span></span>                | <span data-ttu-id="e2d71-246">每小时在客户端计算机上 EDR 进程崩溃次数</span><span class="sxs-lookup"><span data-stu-id="e2d71-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="e2d71-247">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="e2d71-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="e2d71-248">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-248">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-249">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-249">Field</span></span>            | <span data-ttu-id="e2d71-250">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="e2d71-251">version</span><span class="sxs-lookup"><span data-stu-id="e2d71-251">version</span></span>          | <span data-ttu-id="e2d71-252">macOS 上终结点的 Microsoft Defender 版本。</span><span class="sxs-lookup"><span data-stu-id="e2d71-252">Version of Microsoft Defender for Endpoint on macOS.</span></span> |
| <span data-ttu-id="e2d71-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="e2d71-253">instance_id</span></span>      | <span data-ttu-id="e2d71-254">内核扩展启动时生成的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="e2d71-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="e2d71-255">trace_level</span></span>      | <span data-ttu-id="e2d71-256">内核扩展的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="e2d71-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="e2d71-257">subsystem</span><span class="sxs-lookup"><span data-stu-id="e2d71-257">subsystem</span></span>        | <span data-ttu-id="e2d71-258">用于实时保护的基础子系统。</span><span class="sxs-lookup"><span data-stu-id="e2d71-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="e2d71-259">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="e2d71-259">ipc.connects</span></span>     | <span data-ttu-id="e2d71-260">内核扩展接收的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="e2d71-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="e2d71-261">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="e2d71-261">ipc.rejects</span></span>      | <span data-ttu-id="e2d71-262">内核扩展拒绝的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="e2d71-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="e2d71-263">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="e2d71-263">ipc.connected</span></span>    | <span data-ttu-id="e2d71-264">是否有到内核扩展的活动连接。</span><span class="sxs-lookup"><span data-stu-id="e2d71-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="e2d71-265">支持数据</span><span class="sxs-lookup"><span data-stu-id="e2d71-265">Support data</span></span>

<span data-ttu-id="e2d71-266">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="e2d71-266">**Diagnostic logs**</span></span>

<span data-ttu-id="e2d71-267">仅在用户同意的情况下收集诊断日志作为反馈提交功能一部分。</span><span class="sxs-lookup"><span data-stu-id="e2d71-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="e2d71-268">将收集以下文件作为支持日志的一部分：</span><span class="sxs-lookup"><span data-stu-id="e2d71-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="e2d71-269">*/Library/Logs/Microsoft/mdatp/ 下的所有文件*</span><span class="sxs-lookup"><span data-stu-id="e2d71-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="e2d71-270">macOS 上的 Microsoft Defender for Endpoint 创建和使用的 */Library/Application Support/Microsoft/Defender/* 下的文件子集</span><span class="sxs-lookup"><span data-stu-id="e2d71-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="e2d71-271">macOS 上的 Microsoft Defender for Endpoint 使用的 */Library/Managed Preferences* 下的文件子集</span><span class="sxs-lookup"><span data-stu-id="e2d71-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="e2d71-272">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="e2d71-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="e2d71-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="e2d71-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="e2d71-274">可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="e2d71-274">Optional diagnostic data</span></span>

<span data-ttu-id="e2d71-275">**可选诊断** 数据是可帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修复问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="e2d71-276">如果你选择向我们发送可选诊断数据，则还需要包括必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="e2d71-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="e2d71-277">可选诊断数据的示例包括 Microsoft 收集有关产品配置 (例如设备) 上设置的排除数的数据 (以及有关产品) 组件性能的聚合度量。</span><span class="sxs-lookup"><span data-stu-id="e2d71-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="e2d71-278">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="e2d71-278">Software setup and inventory data events</span></span>

<span data-ttu-id="e2d71-279">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="e2d71-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="e2d71-280">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-280">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-281">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-281">Field</span></span>                                              | <span data-ttu-id="e2d71-282">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="e2d71-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="e2d71-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="e2d71-284">与云通信时，连接重试次数将退出。</span><span class="sxs-lookup"><span data-stu-id="e2d71-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="e2d71-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="e2d71-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="e2d71-286">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="e2d71-286">Size of the product cache.</span></span> |
| <span data-ttu-id="e2d71-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="e2d71-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="e2d71-288">每日上载的崩溃日志的限制。</span><span class="sxs-lookup"><span data-stu-id="e2d71-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="e2d71-289">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="e2d71-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="e2d71-290">扫描排除项是否是目录。</span><span class="sxs-lookup"><span data-stu-id="e2d71-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="e2d71-291">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="e2d71-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="e2d71-292">从扫描中排除的路径。</span><span class="sxs-lookup"><span data-stu-id="e2d71-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="e2d71-293">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="e2d71-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="e2d71-294">从扫描中排除的扩展。</span><span class="sxs-lookup"><span data-stu-id="e2d71-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="e2d71-295">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="e2d71-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="e2d71-296">从扫描中排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e2d71-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="e2d71-297">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="e2d71-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="e2d71-298">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="e2d71-298">Size of the product cache.</span></span> |
| <span data-ttu-id="e2d71-299">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="e2d71-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="e2d71-300">用于扫描的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="e2d71-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="e2d71-301">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="e2d71-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="e2d71-302">从隔离区还原的文件可以再次检测到之前，该时间已过。</span><span class="sxs-lookup"><span data-stu-id="e2d71-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="e2d71-303">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="e2d71-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="e2d71-304">完全扫描目录。</span><span class="sxs-lookup"><span data-stu-id="e2d71-304">Full scan directory.</span></span> |
| <span data-ttu-id="e2d71-305">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="e2d71-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="e2d71-306">快速扫描中使用的目录列表。</span><span class="sxs-lookup"><span data-stu-id="e2d71-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="e2d71-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="e2d71-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="e2d71-308">检测和响应组件使用的延迟模式。</span><span class="sxs-lookup"><span data-stu-id="e2d71-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="e2d71-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="e2d71-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="e2d71-310">检测和响应组件使用的代理地址。</span><span class="sxs-lookup"><span data-stu-id="e2d71-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="e2d71-311">**Microsoft 自动更新配置**</span><span class="sxs-lookup"><span data-stu-id="e2d71-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="e2d71-312">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-312">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-313">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-313">Field</span></span>                       | <span data-ttu-id="e2d71-314">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="e2d71-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="e2d71-315">how_to_check</span></span>                | <span data-ttu-id="e2d71-316">确定如何检查产品更新 (例如自动或手动) 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="e2d71-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="e2d71-317">channel_name</span></span>                | <span data-ttu-id="e2d71-318">更新与设备关联的通道。</span><span class="sxs-lookup"><span data-stu-id="e2d71-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="e2d71-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="e2d71-319">manifest_server</span></span>             | <span data-ttu-id="e2d71-320">用于下载更新的服务器。</span><span class="sxs-lookup"><span data-stu-id="e2d71-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="e2d71-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="e2d71-321">update_cache</span></span>                | <span data-ttu-id="e2d71-322">用于存储更新的缓存的位置。</span><span class="sxs-lookup"><span data-stu-id="e2d71-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="e2d71-323">产品和服务使用情况</span><span class="sxs-lookup"><span data-stu-id="e2d71-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="e2d71-324">诊断日志上载开始报告</span><span class="sxs-lookup"><span data-stu-id="e2d71-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="e2d71-325">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-325">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-326">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-326">Field</span></span>            | <span data-ttu-id="e2d71-327">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="e2d71-328">sha256</span><span class="sxs-lookup"><span data-stu-id="e2d71-328">sha256</span></span>           | <span data-ttu-id="e2d71-329">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="e2d71-330">size</span><span class="sxs-lookup"><span data-stu-id="e2d71-330">size</span></span>             | <span data-ttu-id="e2d71-331">支持日志的大小。</span><span class="sxs-lookup"><span data-stu-id="e2d71-331">Size of the support log.</span></span> |
| <span data-ttu-id="e2d71-332">original_path</span><span class="sxs-lookup"><span data-stu-id="e2d71-332">original_path</span></span>    | <span data-ttu-id="e2d71-333">始终在 */library/ (/Microsoft/Defender/wdavdiag/ 下* 的支持日志) 。</span><span class="sxs-lookup"><span data-stu-id="e2d71-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="e2d71-334">format</span><span class="sxs-lookup"><span data-stu-id="e2d71-334">format</span></span>           | <span data-ttu-id="e2d71-335">支持日志的格式。</span><span class="sxs-lookup"><span data-stu-id="e2d71-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="e2d71-336">诊断日志上载已完成报告</span><span class="sxs-lookup"><span data-stu-id="e2d71-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="e2d71-337">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-337">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-338">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-338">Field</span></span>            | <span data-ttu-id="e2d71-339">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="e2d71-340">request_id</span><span class="sxs-lookup"><span data-stu-id="e2d71-340">request_id</span></span>       | <span data-ttu-id="e2d71-341">支持日志上载请求的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="e2d71-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="e2d71-342">sha256</span><span class="sxs-lookup"><span data-stu-id="e2d71-342">sha256</span></span>           | <span data-ttu-id="e2d71-343">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="e2d71-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="e2d71-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="e2d71-344">blob_sas_uri</span></span>     | <span data-ttu-id="e2d71-345">应用程序用于上载支持日志的 URI。</span><span class="sxs-lookup"><span data-stu-id="e2d71-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="e2d71-346">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="e2d71-346">Product and service performance data events</span></span>

<span data-ttu-id="e2d71-347">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="e2d71-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="e2d71-348">应用程序意外退出以及发生这种情况时的应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="e2d71-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="e2d71-349">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="e2d71-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="e2d71-350">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="e2d71-350">The following fields are collected:</span></span>

| <span data-ttu-id="e2d71-351">字段</span><span class="sxs-lookup"><span data-stu-id="e2d71-351">Field</span></span>                          | <span data-ttu-id="e2d71-352">说明</span><span class="sxs-lookup"><span data-stu-id="e2d71-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="e2d71-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="e2d71-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="e2d71-354">以下属性是聚合的数值，表示自内核扩展启动后发生的事件数。</span><span class="sxs-lookup"><span data-stu-id="e2d71-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="e2d71-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="e2d71-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="e2d71-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="e2d71-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="e2d71-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="e2d71-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="e2d71-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="e2d71-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="e2d71-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="e2d71-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="e2d71-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="e2d71-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="e2d71-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="e2d71-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="e2d71-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="e2d71-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="e2d71-363">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="e2d71-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="e2d71-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="e2d71-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="e2d71-365">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="e2d71-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="e2d71-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="e2d71-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="e2d71-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="e2d71-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="e2d71-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="e2d71-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="e2d71-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="e2d71-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="e2d71-370">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="e2d71-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="e2d71-371">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="e2d71-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="e2d71-372">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="e2d71-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="e2d71-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="e2d71-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="e2d71-374">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="e2d71-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="e2d71-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="e2d71-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="e2d71-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="e2d71-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="e2d71-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="e2d71-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="e2d71-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="e2d71-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="e2d71-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="e2d71-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="e2d71-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="e2d71-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="e2d71-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="e2d71-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="e2d71-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="e2d71-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="e2d71-383">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="e2d71-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="e2d71-384">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="e2d71-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="e2d71-385">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="e2d71-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="e2d71-386">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="e2d71-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="e2d71-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="e2d71-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="e2d71-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="e2d71-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="e2d71-389">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="e2d71-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="e2d71-390">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="e2d71-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="e2d71-391">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="e2d71-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="e2d71-392">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="e2d71-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="e2d71-393">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="e2d71-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="e2d71-394">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="e2d71-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="e2d71-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="e2d71-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="e2d71-396">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="e2d71-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="e2d71-397">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="e2d71-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="e2d71-398">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="e2d71-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="e2d71-399">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="e2d71-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="e2d71-400">资源</span><span class="sxs-lookup"><span data-stu-id="e2d71-400">Resources</span></span>

- [<span data-ttu-id="e2d71-401">Microsoft 隐私</span><span class="sxs-lookup"><span data-stu-id="e2d71-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
