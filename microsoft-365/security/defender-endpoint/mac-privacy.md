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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1386809778edeb92521a8656e9ece78591a682a4
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382897"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="02f60-104">适用于 Mac 的 Microsoft Defender 终结点的隐私</span><span class="sxs-lookup"><span data-stu-id="02f60-104">Privacy for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02f60-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="02f60-105">**Applies to:**</span></span>
- [<span data-ttu-id="02f60-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02f60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02f60-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02f60-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="02f60-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="02f60-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="02f60-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="02f60-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="02f60-110">Microsoft 致力于提供你在使用适用于 Mac 的 Microsoft Defender for Endpoint 时选择收集和使用数据方式时需要的信息和控件。</span><span class="sxs-lookup"><span data-stu-id="02f60-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="02f60-111">本主题介绍产品内可用的隐私控件、如何使用策略设置管理这些控件，以及所收集的数据事件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="02f60-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="02f60-112">Microsoft Defender for Endpoint for Mac 中的隐私控件概述</span><span class="sxs-lookup"><span data-stu-id="02f60-112">Overview of privacy controls in Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="02f60-113">本部分介绍 Microsoft Defender for Endpoint for Mac 收集的不同类型的数据的隐私控制。</span><span class="sxs-lookup"><span data-stu-id="02f60-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="02f60-114">诊断数据</span><span class="sxs-lookup"><span data-stu-id="02f60-114">Diagnostic data</span></span>

<span data-ttu-id="02f60-115">诊断数据用于使 Microsoft Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="02f60-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="02f60-116">某些诊断数据是必需的，而某些诊断数据是可选的。</span><span class="sxs-lookup"><span data-stu-id="02f60-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="02f60-117">我们允许你选择是否通过使用隐私控件（如组织的策略设置）向我们发送必需或可选的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="02f60-118">Microsoft Defender for Endpoint 客户端软件有两个级别的诊断数据可供选择：</span><span class="sxs-lookup"><span data-stu-id="02f60-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="02f60-119">**必需**：帮助确保 Microsoft Defender for Endpoint 安全、最新以及按预期在安装它的设备上按预期运行所需的最低数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="02f60-120">**可选**：帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修正问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="02f60-121">默认情况下，仅向 Microsoft 发送必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="02f60-122">云提供的保护数据</span><span class="sxs-lookup"><span data-stu-id="02f60-122">Cloud delivered protection data</span></span>

<span data-ttu-id="02f60-123">云提供的保护用于通过访问云中的最新保护数据来提供更高和更快的保护。</span><span class="sxs-lookup"><span data-stu-id="02f60-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="02f60-124">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="02f60-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="02f60-125">示例数据</span><span class="sxs-lookup"><span data-stu-id="02f60-125">Sample data</span></span>

<span data-ttu-id="02f60-126">示例数据用于通过发送 Microsoft 可疑示例来改进产品的保护功能，以便可以分析它们。</span><span class="sxs-lookup"><span data-stu-id="02f60-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="02f60-127">启用自动示例提交是可选的。</span><span class="sxs-lookup"><span data-stu-id="02f60-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="02f60-128">启用此功能并且收集的示例可能包含个人信息时，将提示用户征得同意。</span><span class="sxs-lookup"><span data-stu-id="02f60-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="02f60-129">通过策略设置管理隐私控件</span><span class="sxs-lookup"><span data-stu-id="02f60-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="02f60-130">如果您是 IT 管理员，您可能希望在企业级别配置这些控件。</span><span class="sxs-lookup"><span data-stu-id="02f60-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="02f60-131">The privacy controls for the various types of data described in the preceding section are described in [Set preferences for Microsoft Defender for Endpoint for Mac .](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="02f60-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="02f60-132">与任何新策略设置一样，应在受限的受控环境中仔细测试它们，以确保在组织中更广泛地实现策略设置之前，所配置的设置具有所需的效果。</span><span class="sxs-lookup"><span data-stu-id="02f60-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="02f60-133">诊断数据事件</span><span class="sxs-lookup"><span data-stu-id="02f60-133">Diagnostic data events</span></span>

<span data-ttu-id="02f60-134">本节介绍哪些内容被视为必需诊断数据以及哪些内容被视为可选诊断数据，以及所收集的事件和字段的说明。</span><span class="sxs-lookup"><span data-stu-id="02f60-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="02f60-135">所有事件常用的数据字段</span><span class="sxs-lookup"><span data-stu-id="02f60-135">Data fields that are common for all events</span></span>
<span data-ttu-id="02f60-136">无论类别或数据子类型如何，所有事件都有一些共同的与事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="02f60-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="02f60-137">以下字段被视为通用于所有事件：</span><span class="sxs-lookup"><span data-stu-id="02f60-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="02f60-138">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-138">Field</span></span>                   | <span data-ttu-id="02f60-139">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="02f60-140">平台</span><span class="sxs-lookup"><span data-stu-id="02f60-140">platform</span></span>                | <span data-ttu-id="02f60-141">应用运行平台的广泛分类。</span><span class="sxs-lookup"><span data-stu-id="02f60-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="02f60-142">允许 Microsoft 确定在哪些平台上可能会发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="02f60-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="02f60-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="02f60-143">machine_guid</span></span>            | <span data-ttu-id="02f60-144">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="02f60-145">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="02f60-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="02f60-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="02f60-146">sense_guid</span></span>              | <span data-ttu-id="02f60-147">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="02f60-148">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="02f60-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="02f60-149">org_id</span><span class="sxs-lookup"><span data-stu-id="02f60-149">org_id</span></span>                  | <span data-ttu-id="02f60-150">与设备所属的企业关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="02f60-151">允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响。</span><span class="sxs-lookup"><span data-stu-id="02f60-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="02f60-152">hostname</span><span class="sxs-lookup"><span data-stu-id="02f60-152">hostname</span></span>                | <span data-ttu-id="02f60-153">本地设备名称 (DNS 后缀) 。</span><span class="sxs-lookup"><span data-stu-id="02f60-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="02f60-154">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="02f60-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="02f60-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="02f60-155">product_guid</span></span>            | <span data-ttu-id="02f60-156">产品的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-156">Unique identifier of the product.</span></span> <span data-ttu-id="02f60-157">允许 Microsoft 区分影响不同产品风格的问题。</span><span class="sxs-lookup"><span data-stu-id="02f60-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="02f60-158">app_version</span><span class="sxs-lookup"><span data-stu-id="02f60-158">app_version</span></span>             | <span data-ttu-id="02f60-159">适用于 Mac 应用程序的 Microsoft Defender for Endpoint 的版本。</span><span class="sxs-lookup"><span data-stu-id="02f60-159">Version of the Microsoft Defender for Endpoint for Mac application.</span></span> <span data-ttu-id="02f60-160">允许 Microsoft 确定哪些版本的产品显示问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="02f60-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="02f60-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="02f60-161">sig_version</span></span>             | <span data-ttu-id="02f60-162">安全智能数据库的版本。</span><span class="sxs-lookup"><span data-stu-id="02f60-162">Version of security intelligence database.</span></span> <span data-ttu-id="02f60-163">允许 Microsoft 标识显示问题的安全智能版本，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="02f60-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="02f60-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="02f60-164">supported_compressions</span></span>  | <span data-ttu-id="02f60-165">应用程序支持的压缩算法列表，例如 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="02f60-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="02f60-166">允许 Microsoft 了解在与应用程序通信时可以使用的压缩类型。</span><span class="sxs-lookup"><span data-stu-id="02f60-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="02f60-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="02f60-167">release_ring</span></span>            | <span data-ttu-id="02f60-168">设备与设备关联的圈， (Insider Fast、Insider Slow、Production) 。</span><span class="sxs-lookup"><span data-stu-id="02f60-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="02f60-169">允许 Microsoft 识别可能在哪个发布环上发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="02f60-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="02f60-170">必需诊断数据</span><span class="sxs-lookup"><span data-stu-id="02f60-170">Required diagnostic data</span></span>

<span data-ttu-id="02f60-171">**必需诊断** 数据是帮助使 Microsoft Defender for Endpoint 保持安全、最新，并按预期在安装它的设备上执行所需的最少数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="02f60-172">必需的诊断数据有助于识别与设备或软件配置相关的 Microsoft Defender for Endpoint 问题。</span><span class="sxs-lookup"><span data-stu-id="02f60-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="02f60-173">例如，它可以帮助确定 Microsoft Defender for Endpoint 功能在特定操作系统版本上崩溃的频率是否更频繁、是否具有新引入的功能，或者何时禁用某些 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="02f60-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="02f60-174">必需的诊断数据可帮助 Microsoft 更快速地检测、诊断和修复这些问题，以便降低对用户或组织的影响。</span><span class="sxs-lookup"><span data-stu-id="02f60-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="02f60-175">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="02f60-175">Software setup and inventory data events</span></span>

<span data-ttu-id="02f60-176">**Microsoft Defender for Endpoint 安装/卸载**</span><span class="sxs-lookup"><span data-stu-id="02f60-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="02f60-177">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-177">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-178">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-178">Field</span></span>            | <span data-ttu-id="02f60-179">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="02f60-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="02f60-180">correlation_id</span></span>   | <span data-ttu-id="02f60-181">与安装关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="02f60-182">version</span><span class="sxs-lookup"><span data-stu-id="02f60-182">version</span></span>          | <span data-ttu-id="02f60-183">程序包的版本。</span><span class="sxs-lookup"><span data-stu-id="02f60-183">Version of the package.</span></span> |
| <span data-ttu-id="02f60-184">severity</span><span class="sxs-lookup"><span data-stu-id="02f60-184">severity</span></span>         | <span data-ttu-id="02f60-185">邮件严重性，例如 (信息) 。</span><span class="sxs-lookup"><span data-stu-id="02f60-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="02f60-186">code</span><span class="sxs-lookup"><span data-stu-id="02f60-186">code</span></span>             | <span data-ttu-id="02f60-187">描述操作的代码。</span><span class="sxs-lookup"><span data-stu-id="02f60-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="02f60-188">text</span><span class="sxs-lookup"><span data-stu-id="02f60-188">text</span></span>             | <span data-ttu-id="02f60-189">与产品安装相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="02f60-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="02f60-190">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="02f60-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="02f60-191">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-191">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-192">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-192">Field</span></span>                                               | <span data-ttu-id="02f60-193">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="02f60-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="02f60-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="02f60-195">是否在设备上启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="02f60-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="02f60-196">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="02f60-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="02f60-197">是否在设备上启用被动模式。</span><span class="sxs-lookup"><span data-stu-id="02f60-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="02f60-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="02f60-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="02f60-199">是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="02f60-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="02f60-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="02f60-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="02f60-201">当应用程序与 Microsoft Defender for Endpoint 云通信时，将退出。</span><span class="sxs-lookup"><span data-stu-id="02f60-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="02f60-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="02f60-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="02f60-203">产品发送到云的连续检测信号之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="02f60-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="02f60-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="02f60-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="02f60-205">用于与云通信的 URI。</span><span class="sxs-lookup"><span data-stu-id="02f60-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="02f60-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="02f60-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="02f60-207">设备诊断级别 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="02f60-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="02f60-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="02f60-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="02f60-209">是否打开自动提交示例。</span><span class="sxs-lookup"><span data-stu-id="02f60-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="02f60-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="02f60-210">edr.early_preview</span></span>                                   | <span data-ttu-id="02f60-211">设备是否应该运行 EDR 早期预览功能。</span><span class="sxs-lookup"><span data-stu-id="02f60-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="02f60-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="02f60-212">edr.group_id</span></span>                                        | <span data-ttu-id="02f60-213">检测和响应组件使用的组标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="02f60-214">edr.tags</span><span class="sxs-lookup"><span data-stu-id="02f60-214">edr.tags</span></span>                                            | <span data-ttu-id="02f60-215">用户定义的标记。</span><span class="sxs-lookup"><span data-stu-id="02f60-215">User-defined tags.</span></span> |
| <span data-ttu-id="02f60-216">功能。 \[可选功能名称\]</span><span class="sxs-lookup"><span data-stu-id="02f60-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="02f60-217">预览功能列表，以及是否已启用。</span><span class="sxs-lookup"><span data-stu-id="02f60-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="02f60-218">产品和服务使用情况数据事件</span><span class="sxs-lookup"><span data-stu-id="02f60-218">Product and service usage data events</span></span>

<span data-ttu-id="02f60-219">**安全智能更新报告**</span><span class="sxs-lookup"><span data-stu-id="02f60-219">**Security intelligence update report**</span></span>

<span data-ttu-id="02f60-220">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-220">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-221">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-221">Field</span></span>            | <span data-ttu-id="02f60-222">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="02f60-223">from_version</span><span class="sxs-lookup"><span data-stu-id="02f60-223">from_version</span></span>     | <span data-ttu-id="02f60-224">原始安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="02f60-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="02f60-225">to_version</span><span class="sxs-lookup"><span data-stu-id="02f60-225">to_version</span></span>       | <span data-ttu-id="02f60-226">新的安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="02f60-226">New security intelligence version.</span></span> |
| <span data-ttu-id="02f60-227">状态</span><span class="sxs-lookup"><span data-stu-id="02f60-227">status</span></span>           | <span data-ttu-id="02f60-228">指示成功或失败的更新的状态。</span><span class="sxs-lookup"><span data-stu-id="02f60-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="02f60-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="02f60-229">using_proxy</span></span>      | <span data-ttu-id="02f60-230">更新是否通过代理完成。</span><span class="sxs-lookup"><span data-stu-id="02f60-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="02f60-231">error</span><span class="sxs-lookup"><span data-stu-id="02f60-231">error</span></span>            | <span data-ttu-id="02f60-232">更新失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="02f60-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="02f60-233">reason</span><span class="sxs-lookup"><span data-stu-id="02f60-233">reason</span></span>           | <span data-ttu-id="02f60-234">如果更新的存档，则显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="02f60-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="02f60-235">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="02f60-235">Product and service performance data events</span></span>

<span data-ttu-id="02f60-236">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="02f60-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="02f60-237">在应用程序意外退出时收集系统信息和应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="02f60-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="02f60-238">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-238">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-239">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-239">Field</span></span>                          | <span data-ttu-id="02f60-240">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="02f60-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="02f60-241">v1_crash_count</span></span>                 | <span data-ttu-id="02f60-242">每小时 V1 引擎进程在客户端计算机上崩溃次数</span><span class="sxs-lookup"><span data-stu-id="02f60-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="02f60-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="02f60-243">v2_crash_count</span></span>                 | <span data-ttu-id="02f60-244">每小时 V2 引擎进程在客户端计算机上崩溃次数</span><span class="sxs-lookup"><span data-stu-id="02f60-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="02f60-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="02f60-245">EDR_crash_count</span></span>                | <span data-ttu-id="02f60-246">每小时在客户端计算机上 EDR 进程崩溃次数</span><span class="sxs-lookup"><span data-stu-id="02f60-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="02f60-247">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="02f60-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="02f60-248">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-248">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-249">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-249">Field</span></span>            | <span data-ttu-id="02f60-250">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="02f60-251">version</span><span class="sxs-lookup"><span data-stu-id="02f60-251">version</span></span>          | <span data-ttu-id="02f60-252">适用于 Mac 的 Microsoft Defender for Endpoint 的版本。</span><span class="sxs-lookup"><span data-stu-id="02f60-252">Version of Microsoft Defender for Endpoint for Mac.</span></span> |
| <span data-ttu-id="02f60-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="02f60-253">instance_id</span></span>      | <span data-ttu-id="02f60-254">内核扩展启动时生成的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="02f60-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="02f60-255">trace_level</span></span>      | <span data-ttu-id="02f60-256">内核扩展的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="02f60-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="02f60-257">subsystem</span><span class="sxs-lookup"><span data-stu-id="02f60-257">subsystem</span></span>        | <span data-ttu-id="02f60-258">用于实时保护的基础子系统。</span><span class="sxs-lookup"><span data-stu-id="02f60-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="02f60-259">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="02f60-259">ipc.connects</span></span>     | <span data-ttu-id="02f60-260">内核扩展接收的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="02f60-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="02f60-261">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="02f60-261">ipc.rejects</span></span>      | <span data-ttu-id="02f60-262">内核扩展拒绝的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="02f60-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="02f60-263">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="02f60-263">ipc.connected</span></span>    | <span data-ttu-id="02f60-264">是否有到内核扩展的活动连接。</span><span class="sxs-lookup"><span data-stu-id="02f60-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="02f60-265">支持数据</span><span class="sxs-lookup"><span data-stu-id="02f60-265">Support data</span></span>

<span data-ttu-id="02f60-266">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="02f60-266">**Diagnostic logs**</span></span>

<span data-ttu-id="02f60-267">仅在用户同意的情况下收集诊断日志作为反馈提交功能一部分。</span><span class="sxs-lookup"><span data-stu-id="02f60-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="02f60-268">将收集以下文件作为支持日志的一部分：</span><span class="sxs-lookup"><span data-stu-id="02f60-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="02f60-269">*/Library/Logs/Microsoft/mdatp/ 下的所有文件*</span><span class="sxs-lookup"><span data-stu-id="02f60-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="02f60-270">Microsoft Defender for Endpoint for Mac 创建和使用的 */Library/Application Support/Microsoft/Defender/* 下的文件子集</span><span class="sxs-lookup"><span data-stu-id="02f60-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="02f60-271">Microsoft Defender for Endpoint for Mac 使用的 */Library/Managed Preferences* 下的文件子集</span><span class="sxs-lookup"><span data-stu-id="02f60-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="02f60-272">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="02f60-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="02f60-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="02f60-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="02f60-274">可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="02f60-274">Optional diagnostic data</span></span>

<span data-ttu-id="02f60-275">**可选诊断** 数据是可帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修复问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="02f60-276">如果你选择向我们发送可选诊断数据，则还需要包括必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="02f60-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="02f60-277">可选诊断数据的示例包括 Microsoft 收集有关产品配置 (例如设备) 上设置的排除数的数据 (以及有关产品) 组件性能的聚合度量。</span><span class="sxs-lookup"><span data-stu-id="02f60-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="02f60-278">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="02f60-278">Software setup and inventory data events</span></span>

<span data-ttu-id="02f60-279">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="02f60-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="02f60-280">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-280">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-281">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-281">Field</span></span>                                              | <span data-ttu-id="02f60-282">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="02f60-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="02f60-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="02f60-284">与云通信时，连接重试次数将退出。</span><span class="sxs-lookup"><span data-stu-id="02f60-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="02f60-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="02f60-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="02f60-286">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="02f60-286">Size of the product cache.</span></span> |
| <span data-ttu-id="02f60-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="02f60-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="02f60-288">每日上载的崩溃日志的限制。</span><span class="sxs-lookup"><span data-stu-id="02f60-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="02f60-289">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="02f60-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="02f60-290">扫描排除项是否是目录。</span><span class="sxs-lookup"><span data-stu-id="02f60-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="02f60-291">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="02f60-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="02f60-292">从扫描中排除的路径。</span><span class="sxs-lookup"><span data-stu-id="02f60-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="02f60-293">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="02f60-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="02f60-294">从扫描中排除的扩展。</span><span class="sxs-lookup"><span data-stu-id="02f60-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="02f60-295">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="02f60-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="02f60-296">从扫描中排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="02f60-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="02f60-297">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="02f60-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="02f60-298">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="02f60-298">Size of the product cache.</span></span> |
| <span data-ttu-id="02f60-299">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="02f60-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="02f60-300">用于扫描的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="02f60-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="02f60-301">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="02f60-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="02f60-302">从隔离区还原的文件可以再次检测到之前，该时间已过。</span><span class="sxs-lookup"><span data-stu-id="02f60-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="02f60-303">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="02f60-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="02f60-304">完全扫描目录。</span><span class="sxs-lookup"><span data-stu-id="02f60-304">Full scan directory.</span></span> |
| <span data-ttu-id="02f60-305">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="02f60-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="02f60-306">快速扫描中使用的目录列表。</span><span class="sxs-lookup"><span data-stu-id="02f60-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="02f60-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="02f60-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="02f60-308">检测和响应组件使用的延迟模式。</span><span class="sxs-lookup"><span data-stu-id="02f60-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="02f60-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="02f60-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="02f60-310">检测和响应组件使用的代理地址。</span><span class="sxs-lookup"><span data-stu-id="02f60-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="02f60-311">**Microsoft 自动更新配置**</span><span class="sxs-lookup"><span data-stu-id="02f60-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="02f60-312">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-312">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-313">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-313">Field</span></span>                       | <span data-ttu-id="02f60-314">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="02f60-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="02f60-315">how_to_check</span></span>                | <span data-ttu-id="02f60-316">确定如何检查产品更新 (例如自动或手动) 。</span><span class="sxs-lookup"><span data-stu-id="02f60-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="02f60-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="02f60-317">channel_name</span></span>                | <span data-ttu-id="02f60-318">更新与设备关联的通道。</span><span class="sxs-lookup"><span data-stu-id="02f60-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="02f60-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="02f60-319">manifest_server</span></span>             | <span data-ttu-id="02f60-320">用于下载更新的服务器。</span><span class="sxs-lookup"><span data-stu-id="02f60-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="02f60-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="02f60-321">update_cache</span></span>                | <span data-ttu-id="02f60-322">用于存储更新的缓存的位置。</span><span class="sxs-lookup"><span data-stu-id="02f60-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="02f60-323">产品和服务使用情况</span><span class="sxs-lookup"><span data-stu-id="02f60-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="02f60-324">诊断日志上载开始报告</span><span class="sxs-lookup"><span data-stu-id="02f60-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="02f60-325">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-325">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-326">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-326">Field</span></span>            | <span data-ttu-id="02f60-327">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="02f60-328">sha256</span><span class="sxs-lookup"><span data-stu-id="02f60-328">sha256</span></span>           | <span data-ttu-id="02f60-329">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="02f60-330">size</span><span class="sxs-lookup"><span data-stu-id="02f60-330">size</span></span>             | <span data-ttu-id="02f60-331">支持日志的大小。</span><span class="sxs-lookup"><span data-stu-id="02f60-331">Size of the support log.</span></span> |
| <span data-ttu-id="02f60-332">original_path</span><span class="sxs-lookup"><span data-stu-id="02f60-332">original_path</span></span>    | <span data-ttu-id="02f60-333">始终在 */library/ (/Microsoft/Defender/wdavdiag/ 下* 的支持日志) 。</span><span class="sxs-lookup"><span data-stu-id="02f60-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="02f60-334">format</span><span class="sxs-lookup"><span data-stu-id="02f60-334">format</span></span>           | <span data-ttu-id="02f60-335">支持日志的格式。</span><span class="sxs-lookup"><span data-stu-id="02f60-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="02f60-336">诊断日志上载已完成报告</span><span class="sxs-lookup"><span data-stu-id="02f60-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="02f60-337">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-337">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-338">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-338">Field</span></span>            | <span data-ttu-id="02f60-339">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="02f60-340">request_id</span><span class="sxs-lookup"><span data-stu-id="02f60-340">request_id</span></span>       | <span data-ttu-id="02f60-341">支持日志上载请求的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="02f60-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="02f60-342">sha256</span><span class="sxs-lookup"><span data-stu-id="02f60-342">sha256</span></span>           | <span data-ttu-id="02f60-343">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="02f60-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="02f60-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="02f60-344">blob_sas_uri</span></span>     | <span data-ttu-id="02f60-345">应用程序用于上载支持日志的 URI。</span><span class="sxs-lookup"><span data-stu-id="02f60-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="02f60-346">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="02f60-346">Product and service performance data events</span></span>

<span data-ttu-id="02f60-347">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="02f60-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="02f60-348">应用程序意外退出以及发生这种情况时的应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="02f60-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="02f60-349">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="02f60-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="02f60-350">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="02f60-350">The following fields are collected:</span></span>

| <span data-ttu-id="02f60-351">字段</span><span class="sxs-lookup"><span data-stu-id="02f60-351">Field</span></span>                          | <span data-ttu-id="02f60-352">说明</span><span class="sxs-lookup"><span data-stu-id="02f60-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="02f60-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="02f60-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="02f60-354">以下属性是聚合的数值，表示自内核扩展启动后发生的事件数。</span><span class="sxs-lookup"><span data-stu-id="02f60-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="02f60-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="02f60-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="02f60-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="02f60-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="02f60-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="02f60-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="02f60-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="02f60-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="02f60-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="02f60-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="02f60-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="02f60-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="02f60-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="02f60-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="02f60-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="02f60-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="02f60-363">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="02f60-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="02f60-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="02f60-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="02f60-365">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="02f60-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="02f60-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="02f60-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="02f60-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="02f60-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="02f60-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="02f60-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="02f60-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="02f60-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="02f60-370">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="02f60-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="02f60-371">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="02f60-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="02f60-372">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="02f60-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="02f60-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="02f60-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="02f60-374">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="02f60-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="02f60-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="02f60-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="02f60-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="02f60-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="02f60-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="02f60-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="02f60-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="02f60-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="02f60-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="02f60-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="02f60-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="02f60-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="02f60-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="02f60-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="02f60-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="02f60-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="02f60-383">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="02f60-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="02f60-384">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="02f60-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="02f60-385">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="02f60-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="02f60-386">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="02f60-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="02f60-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="02f60-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="02f60-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="02f60-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="02f60-389">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="02f60-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="02f60-390">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="02f60-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="02f60-391">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="02f60-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="02f60-392">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="02f60-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="02f60-393">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="02f60-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="02f60-394">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="02f60-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="02f60-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="02f60-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="02f60-396">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="02f60-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="02f60-397">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="02f60-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="02f60-398">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="02f60-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="02f60-399">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="02f60-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="02f60-400">资源</span><span class="sxs-lookup"><span data-stu-id="02f60-400">Resources</span></span>

- [<span data-ttu-id="02f60-401">Microsoft 隐私</span><span class="sxs-lookup"><span data-stu-id="02f60-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
