---
title: 适用于 Linux 的 Microsoft Defender ATP 的隐私
description: 隐私控制，如何配置影响隐私的策略设置和有关在 Microsoft Defender ATP for Linux 中收集的诊断数据的信息。
keywords: microsoft， defender， atp， linux， 隐私， 诊断
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34a06a964baa475c5dedd019e40a6e31e44c0dd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055826"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="d64c2-104">适用于 Linux 的 Microsoft Defender 终结点的隐私</span><span class="sxs-lookup"><span data-stu-id="d64c2-104">Privacy for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d64c2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d64c2-105">**Applies to:**</span></span>
- [<span data-ttu-id="d64c2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d64c2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d64c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d64c2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d64c2-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="d64c2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d64c2-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d64c2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d64c2-110">Microsoft 致力于提供你在使用适用于 Linux 的 Defender for Endpoint 时选择收集和使用数据方式时需要的信息和控件。</span><span class="sxs-lookup"><span data-stu-id="d64c2-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="d64c2-111">本主题介绍产品内可用的隐私控件、如何使用策略设置管理这些控件，以及所收集的数据事件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="d64c2-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="d64c2-112">Microsoft Defender for Endpoint for Linux 中的隐私控件概述</span><span class="sxs-lookup"><span data-stu-id="d64c2-112">Overview of privacy controls in Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="d64c2-113">本部分介绍 Defender for Endpoint for Linux 收集的不同类型的数据的隐私控制。</span><span class="sxs-lookup"><span data-stu-id="d64c2-113">This section describes the privacy controls for the different types of data collected by Defender for Endpoint for Linux.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="d64c2-114">诊断数据</span><span class="sxs-lookup"><span data-stu-id="d64c2-114">Diagnostic data</span></span>

<span data-ttu-id="d64c2-115">诊断数据用于使 Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。</span><span class="sxs-lookup"><span data-stu-id="d64c2-115">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="d64c2-116">某些诊断数据是必需的，而某些诊断数据是可选的。</span><span class="sxs-lookup"><span data-stu-id="d64c2-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="d64c2-117">我们允许你选择是否通过使用隐私控件（如组织的策略设置）向我们发送必需或可选的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="d64c2-118">对于 Defender for Endpoint 客户端软件，有两个级别的诊断数据可供选择：</span><span class="sxs-lookup"><span data-stu-id="d64c2-118">There are two levels of diagnostic data for Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="d64c2-119">**必需**：帮助使 Defender for Endpoint 保持安全、最新以及按预期在安装了终结点的设备上按预期运行所需的最低数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-119">**Required**: The minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="d64c2-120">**可选**：帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修正问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="d64c2-121">默认情况下，仅向 Microsoft 发送必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="d64c2-122">云提供的保护数据</span><span class="sxs-lookup"><span data-stu-id="d64c2-122">Cloud delivered protection data</span></span>

<span data-ttu-id="d64c2-123">云提供的保护用于通过访问云中的最新保护数据来提供更高和更快的保护。</span><span class="sxs-lookup"><span data-stu-id="d64c2-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="d64c2-124">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="d64c2-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="d64c2-125">示例数据</span><span class="sxs-lookup"><span data-stu-id="d64c2-125">Sample data</span></span>

<span data-ttu-id="d64c2-126">示例数据用于通过发送 Microsoft 可疑示例来改进产品的保护功能，以便可以分析它们。</span><span class="sxs-lookup"><span data-stu-id="d64c2-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="d64c2-127">启用自动示例提交是可选的。</span><span class="sxs-lookup"><span data-stu-id="d64c2-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="d64c2-128">有三个级别用于控制示例提交：</span><span class="sxs-lookup"><span data-stu-id="d64c2-128">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="d64c2-129">**无**：不会向 Microsoft 提交任何可疑样本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-129">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="d64c2-130">**安全**：仅自动提交不包含个人身份信息 (PII) 的可疑示例。</span><span class="sxs-lookup"><span data-stu-id="d64c2-130">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="d64c2-131">这是此设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="d64c2-131">This is the default value for this setting.</span></span>
- <span data-ttu-id="d64c2-132">**全部**：所有可疑示例都提交到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d64c2-132">**All**: all suspicious samples are submitted to Microsoft.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="d64c2-133">通过策略设置管理隐私控件</span><span class="sxs-lookup"><span data-stu-id="d64c2-133">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="d64c2-134">如果您是 IT 管理员，您可能希望在企业级别配置这些控件。</span><span class="sxs-lookup"><span data-stu-id="d64c2-134">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="d64c2-135">The privacy controls for the various types of data described in the preceding section are described in [Set preferences for Defender for Endpoint for Linux .](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="d64c2-135">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

<span data-ttu-id="d64c2-136">与任何新策略设置一样，应在受限的受控环境中仔细测试它们，以确保在组织中更广泛地实现策略设置之前，所配置的设置具有所需的效果。</span><span class="sxs-lookup"><span data-stu-id="d64c2-136">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="d64c2-137">诊断数据事件</span><span class="sxs-lookup"><span data-stu-id="d64c2-137">Diagnostic data events</span></span>

<span data-ttu-id="d64c2-138">本节介绍哪些内容被视为必需诊断数据以及哪些内容被视为可选诊断数据，以及所收集的事件和字段的说明。</span><span class="sxs-lookup"><span data-stu-id="d64c2-138">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="d64c2-139">所有事件常用的数据字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-139">Data fields that are common for all events</span></span>
<span data-ttu-id="d64c2-140">无论类别或数据子类型如何，所有事件都有一些共同的与事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="d64c2-140">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="d64c2-141">以下字段被视为通用于所有事件：</span><span class="sxs-lookup"><span data-stu-id="d64c2-141">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="d64c2-142">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-142">Field</span></span>                   | <span data-ttu-id="d64c2-143">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-143">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="d64c2-144">平台</span><span class="sxs-lookup"><span data-stu-id="d64c2-144">platform</span></span>                | <span data-ttu-id="d64c2-145">应用运行平台的广泛分类。</span><span class="sxs-lookup"><span data-stu-id="d64c2-145">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="d64c2-146">允许 Microsoft 确定在哪些平台上可能会发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="d64c2-146">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="d64c2-147">machine_guid</span><span class="sxs-lookup"><span data-stu-id="d64c2-147">machine_guid</span></span>            | <span data-ttu-id="d64c2-148">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-148">Unique identifier associated with the device.</span></span> <span data-ttu-id="d64c2-149">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="d64c2-149">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="d64c2-150">sense_guid</span><span class="sxs-lookup"><span data-stu-id="d64c2-150">sense_guid</span></span>              | <span data-ttu-id="d64c2-151">与设备关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-151">Unique identifier associated with the device.</span></span> <span data-ttu-id="d64c2-152">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="d64c2-152">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="d64c2-153">org_id</span><span class="sxs-lookup"><span data-stu-id="d64c2-153">org_id</span></span>                  | <span data-ttu-id="d64c2-154">与设备所属的企业关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-154">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="d64c2-155">允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响。</span><span class="sxs-lookup"><span data-stu-id="d64c2-155">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="d64c2-156">hostname</span><span class="sxs-lookup"><span data-stu-id="d64c2-156">hostname</span></span>                | <span data-ttu-id="d64c2-157">本地设备名称 (DNS 后缀) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-157">Local device name (without DNS suffix).</span></span> <span data-ttu-id="d64c2-158">允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。</span><span class="sxs-lookup"><span data-stu-id="d64c2-158">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="d64c2-159">product_guid</span><span class="sxs-lookup"><span data-stu-id="d64c2-159">product_guid</span></span>            | <span data-ttu-id="d64c2-160">产品的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-160">Unique identifier of the product.</span></span> <span data-ttu-id="d64c2-161">允许 Microsoft 区分影响不同产品风格的问题。</span><span class="sxs-lookup"><span data-stu-id="d64c2-161">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="d64c2-162">app_version</span><span class="sxs-lookup"><span data-stu-id="d64c2-162">app_version</span></span>             | <span data-ttu-id="d64c2-163">适用于 Linux 应用程序的 Defender for Endpoint 的版本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-163">Version of the Defender for Endpoint for Linux application.</span></span> <span data-ttu-id="d64c2-164">允许 Microsoft 确定哪些版本的产品显示问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="d64c2-164">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="d64c2-165">sig_version</span><span class="sxs-lookup"><span data-stu-id="d64c2-165">sig_version</span></span>             | <span data-ttu-id="d64c2-166">安全智能数据库的版本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-166">Version of security intelligence database.</span></span> <span data-ttu-id="d64c2-167">允许 Microsoft 标识显示问题的安全智能版本，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="d64c2-167">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="d64c2-168">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="d64c2-168">supported_compressions</span></span>  | <span data-ttu-id="d64c2-169">应用程序支持的压缩算法列表，例如 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-169">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="d64c2-170">允许 Microsoft 了解在与应用程序通信时可以使用的压缩类型。</span><span class="sxs-lookup"><span data-stu-id="d64c2-170">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="d64c2-171">release_ring</span><span class="sxs-lookup"><span data-stu-id="d64c2-171">release_ring</span></span>            | <span data-ttu-id="d64c2-172">设备与设备关联的圈， (Insider Fast、Insider Slow、Production) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-172">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="d64c2-173">允许 Microsoft 识别可能在哪个发布环上发生问题，以便可以正确地确定问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="d64c2-173">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |

### <a name="required-diagnostic-data"></a><span data-ttu-id="d64c2-174">必需诊断数据</span><span class="sxs-lookup"><span data-stu-id="d64c2-174">Required diagnostic data</span></span>

<span data-ttu-id="d64c2-175">**必需诊断** 数据是帮助使 Defender for Endpoint 保持安全、最新，并按预期在安装它的设备上执行所需的最少数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-175">**Required diagnostic data** is the minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="d64c2-176">必需的诊断数据有助于识别与设备或软件配置相关的 Microsoft Defender for Endpoint 问题。</span><span class="sxs-lookup"><span data-stu-id="d64c2-176">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="d64c2-177">例如，它可以帮助确定 Defender for Endpoint 功能在特定操作系统版本、新引入的功能上崩溃的频率是否更频繁，或者何时禁用某些 Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="d64c2-177">For example, it can help determine if a Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="d64c2-178">必需的诊断数据可帮助 Microsoft 更快速地检测、诊断和修复这些问题，以便降低对用户或组织的影响。</span><span class="sxs-lookup"><span data-stu-id="d64c2-178">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="d64c2-179">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="d64c2-179">Software setup and inventory data events</span></span>

<span data-ttu-id="d64c2-180">**Microsoft Defender for Endpoint 安装/卸载**</span><span class="sxs-lookup"><span data-stu-id="d64c2-180">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="d64c2-181">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-181">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-182">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-182">Field</span></span>            | <span data-ttu-id="d64c2-183">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-183">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="d64c2-184">correlation_id</span><span class="sxs-lookup"><span data-stu-id="d64c2-184">correlation_id</span></span>   | <span data-ttu-id="d64c2-185">与安装关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-185">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="d64c2-186">version</span><span class="sxs-lookup"><span data-stu-id="d64c2-186">version</span></span>          | <span data-ttu-id="d64c2-187">程序包的版本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-187">Version of the package.</span></span> |
| <span data-ttu-id="d64c2-188">severity</span><span class="sxs-lookup"><span data-stu-id="d64c2-188">severity</span></span>         | <span data-ttu-id="d64c2-189">邮件严重性，例如 (信息) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-189">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="d64c2-190">code</span><span class="sxs-lookup"><span data-stu-id="d64c2-190">code</span></span>             | <span data-ttu-id="d64c2-191">描述操作的代码。</span><span class="sxs-lookup"><span data-stu-id="d64c2-191">Code that describes the operation.</span></span> |
| <span data-ttu-id="d64c2-192">text</span><span class="sxs-lookup"><span data-stu-id="d64c2-192">text</span></span>             | <span data-ttu-id="d64c2-193">与产品安装相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="d64c2-193">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="d64c2-194">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="d64c2-194">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="d64c2-195">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-195">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-196">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-196">Field</span></span>                                               | <span data-ttu-id="d64c2-197">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-197">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="d64c2-198">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="d64c2-198">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="d64c2-199">是否在设备上启用实时保护。</span><span class="sxs-lookup"><span data-stu-id="d64c2-199">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="d64c2-200">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="d64c2-200">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="d64c2-201">是否在设备上启用被动模式。</span><span class="sxs-lookup"><span data-stu-id="d64c2-201">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="d64c2-202">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="d64c2-202">cloud_service.enabled</span></span>                               | <span data-ttu-id="d64c2-203">是否在设备上启用云保护。</span><span class="sxs-lookup"><span data-stu-id="d64c2-203">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="d64c2-204">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="d64c2-204">cloud_service.timeout</span></span>                               | <span data-ttu-id="d64c2-205">当应用程序与 Defender for Endpoint 云通信时，将退出。</span><span class="sxs-lookup"><span data-stu-id="d64c2-205">Time out when the application communicates with the Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="d64c2-206">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="d64c2-206">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="d64c2-207">产品发送到云的连续检测信号之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="d64c2-207">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="d64c2-208">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="d64c2-208">cloud_service.service_uri</span></span>                           | <span data-ttu-id="d64c2-209">用于与云通信的 URI。</span><span class="sxs-lookup"><span data-stu-id="d64c2-209">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="d64c2-210">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="d64c2-210">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="d64c2-211">设备诊断级别 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-211">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="d64c2-212">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="d64c2-212">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="d64c2-213">设备的自动示例提交级别 (无、安全、) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-213">Automatic sample submission level of the device (none, safe, all).</span></span> |
| <span data-ttu-id="d64c2-214">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="d64c2-214">edr.early_preview</span></span>                                   | <span data-ttu-id="d64c2-215">设备是否应该运行 EDR 早期预览功能。</span><span class="sxs-lookup"><span data-stu-id="d64c2-215">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="d64c2-216">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="d64c2-216">edr.group_id</span></span>                                        | <span data-ttu-id="d64c2-217">检测和响应组件使用的组标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-217">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="d64c2-218">edr.tags</span><span class="sxs-lookup"><span data-stu-id="d64c2-218">edr.tags</span></span>                                            | <span data-ttu-id="d64c2-219">用户定义的标记。</span><span class="sxs-lookup"><span data-stu-id="d64c2-219">User-defined tags.</span></span> |
| <span data-ttu-id="d64c2-220">功能。 \[可选功能名称\]</span><span class="sxs-lookup"><span data-stu-id="d64c2-220">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="d64c2-221">预览功能列表，以及是否已启用。</span><span class="sxs-lookup"><span data-stu-id="d64c2-221">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="d64c2-222">产品和服务使用情况数据事件</span><span class="sxs-lookup"><span data-stu-id="d64c2-222">Product and service usage data events</span></span>

<span data-ttu-id="d64c2-223">**安全智能更新报告**</span><span class="sxs-lookup"><span data-stu-id="d64c2-223">**Security intelligence update report**</span></span>

<span data-ttu-id="d64c2-224">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-224">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-225">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-225">Field</span></span>            | <span data-ttu-id="d64c2-226">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-226">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="d64c2-227">from_version</span><span class="sxs-lookup"><span data-stu-id="d64c2-227">from_version</span></span>     | <span data-ttu-id="d64c2-228">原始安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-228">Original security intelligence version.</span></span> |
| <span data-ttu-id="d64c2-229">to_version</span><span class="sxs-lookup"><span data-stu-id="d64c2-229">to_version</span></span>       | <span data-ttu-id="d64c2-230">新的安全智能版本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-230">New security intelligence version.</span></span> |
| <span data-ttu-id="d64c2-231">状态</span><span class="sxs-lookup"><span data-stu-id="d64c2-231">status</span></span>           | <span data-ttu-id="d64c2-232">指示成功或失败的更新的状态。</span><span class="sxs-lookup"><span data-stu-id="d64c2-232">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="d64c2-233">using_proxy</span><span class="sxs-lookup"><span data-stu-id="d64c2-233">using_proxy</span></span>      | <span data-ttu-id="d64c2-234">更新是否通过代理完成。</span><span class="sxs-lookup"><span data-stu-id="d64c2-234">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="d64c2-235">error</span><span class="sxs-lookup"><span data-stu-id="d64c2-235">error</span></span>            | <span data-ttu-id="d64c2-236">更新失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="d64c2-236">Error code if the update failed.</span></span> |
| <span data-ttu-id="d64c2-237">reason</span><span class="sxs-lookup"><span data-stu-id="d64c2-237">reason</span></span>           | <span data-ttu-id="d64c2-238">更新失败时出现错误消息。</span><span class="sxs-lookup"><span data-stu-id="d64c2-238">Error message if the update failed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="d64c2-239">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="d64c2-239">Product and service performance data events</span></span>

<span data-ttu-id="d64c2-240">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="d64c2-240">**Kernel extension statistics**</span></span>

<span data-ttu-id="d64c2-241">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-241">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-242">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-242">Field</span></span>            | <span data-ttu-id="d64c2-243">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-243">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="d64c2-244">version</span><span class="sxs-lookup"><span data-stu-id="d64c2-244">version</span></span>          | <span data-ttu-id="d64c2-245">适用于 Linux 的终结点的 Defender 版本。</span><span class="sxs-lookup"><span data-stu-id="d64c2-245">Version of Defender for Endpoint for Linux.</span></span> |
| <span data-ttu-id="d64c2-246">instance_id</span><span class="sxs-lookup"><span data-stu-id="d64c2-246">instance_id</span></span>      | <span data-ttu-id="d64c2-247">内核扩展启动时生成的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-247">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="d64c2-248">trace_level</span><span class="sxs-lookup"><span data-stu-id="d64c2-248">trace_level</span></span>      | <span data-ttu-id="d64c2-249">内核扩展的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="d64c2-249">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="d64c2-250">subsystem</span><span class="sxs-lookup"><span data-stu-id="d64c2-250">subsystem</span></span>        | <span data-ttu-id="d64c2-251">用于实时保护的基础子系统。</span><span class="sxs-lookup"><span data-stu-id="d64c2-251">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="d64c2-252">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="d64c2-252">ipc.connects</span></span>     | <span data-ttu-id="d64c2-253">内核扩展接收的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="d64c2-253">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="d64c2-254">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="d64c2-254">ipc.rejects</span></span>      | <span data-ttu-id="d64c2-255">内核扩展拒绝的连接请求数。</span><span class="sxs-lookup"><span data-stu-id="d64c2-255">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="d64c2-256">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="d64c2-256">ipc.connected</span></span>    | <span data-ttu-id="d64c2-257">是否有到内核扩展的活动连接。</span><span class="sxs-lookup"><span data-stu-id="d64c2-257">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="d64c2-258">支持数据</span><span class="sxs-lookup"><span data-stu-id="d64c2-258">Support data</span></span>

<span data-ttu-id="d64c2-259">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="d64c2-259">**Diagnostic logs**</span></span>

<span data-ttu-id="d64c2-260">仅在用户同意的情况下收集诊断日志作为反馈提交功能一部分。</span><span class="sxs-lookup"><span data-stu-id="d64c2-260">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="d64c2-261">将收集以下文件作为支持日志的一部分：</span><span class="sxs-lookup"><span data-stu-id="d64c2-261">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="d64c2-262">*/var/log/microsoft/mdatp 下的所有文件*</span><span class="sxs-lookup"><span data-stu-id="d64c2-262">All files under */var/log/microsoft/mdatp*</span></span>
- <span data-ttu-id="d64c2-263">*/etc/opt/microsoft/mdatp* 下由 Defender for Endpoint for Linux 创建和使用的文件的子集</span><span class="sxs-lookup"><span data-stu-id="d64c2-263">Subset of files under */etc/opt/microsoft/mdatp* that are created and used by Defender for Endpoint for Linux</span></span>
- <span data-ttu-id="d64c2-264">*/var/log/microsoft_mdatp_ \* .log 下的产品安装和卸载日志*</span><span class="sxs-lookup"><span data-stu-id="d64c2-264">Product installation and uninstallation logs under */var/log/microsoft_mdatp_\*.log*</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="d64c2-265">可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="d64c2-265">Optional diagnostic data</span></span>

<span data-ttu-id="d64c2-266">**可选诊断** 数据是可帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修复问题的其他数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-266">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="d64c2-267">如果你选择向我们发送可选诊断数据，则还需要包括必需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="d64c2-267">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="d64c2-268">可选诊断数据的示例包括 Microsoft 收集有关产品配置 (例如设备) 上设置的排除数的数据 (以及有关产品) 组件性能的聚合度量。</span><span class="sxs-lookup"><span data-stu-id="d64c2-268">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="d64c2-269">软件安装和清单数据事件</span><span class="sxs-lookup"><span data-stu-id="d64c2-269">Software setup and inventory data events</span></span>

<span data-ttu-id="d64c2-270">**Microsoft Defender for Endpoint 配置**</span><span class="sxs-lookup"><span data-stu-id="d64c2-270">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="d64c2-271">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-271">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-272">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-272">Field</span></span>                                              | <span data-ttu-id="d64c2-273">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-273">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="d64c2-274">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="d64c2-274">connection_retry_timeout</span></span>                           | <span data-ttu-id="d64c2-275">与云通信时的连接重试时间。</span><span class="sxs-lookup"><span data-stu-id="d64c2-275">Connection retry time-out when communication with the cloud.</span></span> |
| <span data-ttu-id="d64c2-276">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="d64c2-276">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="d64c2-277">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="d64c2-277">Size of the product cache.</span></span> |
| <span data-ttu-id="d64c2-278">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="d64c2-278">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="d64c2-279">每日上载的崩溃日志的限制。</span><span class="sxs-lookup"><span data-stu-id="d64c2-279">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="d64c2-280">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="d64c2-280">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="d64c2-281">扫描排除项是否是目录。</span><span class="sxs-lookup"><span data-stu-id="d64c2-281">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="d64c2-282">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="d64c2-282">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="d64c2-283">从扫描中排除的路径。</span><span class="sxs-lookup"><span data-stu-id="d64c2-283">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="d64c2-284">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="d64c2-284">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="d64c2-285">从扫描中排除的扩展。</span><span class="sxs-lookup"><span data-stu-id="d64c2-285">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="d64c2-286">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="d64c2-286">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="d64c2-287">从扫描中排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d64c2-287">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="d64c2-288">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="d64c2-288">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="d64c2-289">产品缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="d64c2-289">Size of the product cache.</span></span> |
| <span data-ttu-id="d64c2-290">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="d64c2-290">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="d64c2-291">用于扫描的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="d64c2-291">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="d64c2-292">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="d64c2-292">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="d64c2-293">从隔离区还原的文件可以再次检测到之前，该时间已过。</span><span class="sxs-lookup"><span data-stu-id="d64c2-293">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="d64c2-294">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="d64c2-294">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="d64c2-295">完全扫描目录。</span><span class="sxs-lookup"><span data-stu-id="d64c2-295">Full scan directory.</span></span> |
| <span data-ttu-id="d64c2-296">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="d64c2-296">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="d64c2-297">快速扫描中使用的目录列表。</span><span class="sxs-lookup"><span data-stu-id="d64c2-297">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="d64c2-298">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="d64c2-298">edr.latency_mode</span></span>                                   | <span data-ttu-id="d64c2-299">检测和响应组件使用的延迟模式。</span><span class="sxs-lookup"><span data-stu-id="d64c2-299">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="d64c2-300">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="d64c2-300">edr.proxy_address</span></span>                                  | <span data-ttu-id="d64c2-301">检测和响应组件使用的代理地址。</span><span class="sxs-lookup"><span data-stu-id="d64c2-301">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="d64c2-302">**Microsoft 自动更新配置**</span><span class="sxs-lookup"><span data-stu-id="d64c2-302">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="d64c2-303">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-303">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-304">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-304">Field</span></span>                       | <span data-ttu-id="d64c2-305">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-305">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="d64c2-306">how_to_check</span><span class="sxs-lookup"><span data-stu-id="d64c2-306">how_to_check</span></span>                | <span data-ttu-id="d64c2-307">确定如何检查产品更新 (例如自动或手动) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-307">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="d64c2-308">channel_name</span><span class="sxs-lookup"><span data-stu-id="d64c2-308">channel_name</span></span>                | <span data-ttu-id="d64c2-309">更新与设备关联的通道。</span><span class="sxs-lookup"><span data-stu-id="d64c2-309">Update channel associated with the device.</span></span> |
| <span data-ttu-id="d64c2-310">manifest_server</span><span class="sxs-lookup"><span data-stu-id="d64c2-310">manifest_server</span></span>             | <span data-ttu-id="d64c2-311">用于下载更新的服务器。</span><span class="sxs-lookup"><span data-stu-id="d64c2-311">Server used for downloading updates.</span></span> |
| <span data-ttu-id="d64c2-312">update_cache</span><span class="sxs-lookup"><span data-stu-id="d64c2-312">update_cache</span></span>                | <span data-ttu-id="d64c2-313">用于存储更新的缓存的位置。</span><span class="sxs-lookup"><span data-stu-id="d64c2-313">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="d64c2-314">产品和服务使用情况</span><span class="sxs-lookup"><span data-stu-id="d64c2-314">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="d64c2-315">诊断日志上载开始报告</span><span class="sxs-lookup"><span data-stu-id="d64c2-315">Diagnostic log upload started report</span></span>

<span data-ttu-id="d64c2-316">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-316">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-317">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-317">Field</span></span>            | <span data-ttu-id="d64c2-318">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-318">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="d64c2-319">sha256</span><span class="sxs-lookup"><span data-stu-id="d64c2-319">sha256</span></span>           | <span data-ttu-id="d64c2-320">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-320">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="d64c2-321">size</span><span class="sxs-lookup"><span data-stu-id="d64c2-321">size</span></span>             | <span data-ttu-id="d64c2-322">支持日志的大小。</span><span class="sxs-lookup"><span data-stu-id="d64c2-322">Size of the support log.</span></span> |
| <span data-ttu-id="d64c2-323">original_path</span><span class="sxs-lookup"><span data-stu-id="d64c2-323">original_path</span></span>    | <span data-ttu-id="d64c2-324">始终在 */var/opt/microsoft/mdatp/wdavdiag/ (下* 的支持日志) 。</span><span class="sxs-lookup"><span data-stu-id="d64c2-324">Path to the support log (always under */var/opt/microsoft/mdatp/wdavdiag/*).</span></span> |
| <span data-ttu-id="d64c2-325">format</span><span class="sxs-lookup"><span data-stu-id="d64c2-325">format</span></span>           | <span data-ttu-id="d64c2-326">支持日志的格式。</span><span class="sxs-lookup"><span data-stu-id="d64c2-326">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="d64c2-327">诊断日志上载已完成报告</span><span class="sxs-lookup"><span data-stu-id="d64c2-327">Diagnostic log upload completed report</span></span>

<span data-ttu-id="d64c2-328">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-328">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-329">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-329">Field</span></span>            | <span data-ttu-id="d64c2-330">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-330">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="d64c2-331">request_id</span><span class="sxs-lookup"><span data-stu-id="d64c2-331">request_id</span></span>       | <span data-ttu-id="d64c2-332">支持日志上载请求的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="d64c2-332">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="d64c2-333">sha256</span><span class="sxs-lookup"><span data-stu-id="d64c2-333">sha256</span></span>           | <span data-ttu-id="d64c2-334">支持日志的 SHA256 标识符。</span><span class="sxs-lookup"><span data-stu-id="d64c2-334">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="d64c2-335">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="d64c2-335">blob_sas_uri</span></span>     | <span data-ttu-id="d64c2-336">应用程序用于上载支持日志的 URI。</span><span class="sxs-lookup"><span data-stu-id="d64c2-336">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="d64c2-337">产品和服务性能事件</span><span class="sxs-lookup"><span data-stu-id="d64c2-337">Product and service performance data events</span></span>

<span data-ttu-id="d64c2-338">**应用程序意外退出（崩溃）**</span><span class="sxs-lookup"><span data-stu-id="d64c2-338">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="d64c2-339">应用程序意外退出以及发生这种情况时的应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="d64c2-339">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="d64c2-340">**内核扩展统计信息**</span><span class="sxs-lookup"><span data-stu-id="d64c2-340">**Kernel extension statistics**</span></span>

<span data-ttu-id="d64c2-341">将会收集以下字段：</span><span class="sxs-lookup"><span data-stu-id="d64c2-341">The following fields are collected:</span></span>

| <span data-ttu-id="d64c2-342">字段</span><span class="sxs-lookup"><span data-stu-id="d64c2-342">Field</span></span>                          | <span data-ttu-id="d64c2-343">说明</span><span class="sxs-lookup"><span data-stu-id="d64c2-343">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="d64c2-344">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="d64c2-344">pkt_ack_timeout</span></span>                | <span data-ttu-id="d64c2-345">以下属性是聚合的数值，表示自内核扩展启动后发生的事件数。</span><span class="sxs-lookup"><span data-stu-id="d64c2-345">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="d64c2-346">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="d64c2-346">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="d64c2-347">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="d64c2-347">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="d64c2-348">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="d64c2-348">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="d64c2-349">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="d64c2-349">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="d64c2-350">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="d64c2-350">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="d64c2-351">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="d64c2-351">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="d64c2-352">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="d64c2-352">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="d64c2-353">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="d64c2-353">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="d64c2-354">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="d64c2-354">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="d64c2-355">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="d64c2-355">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="d64c2-356">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="d64c2-356">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="d64c2-357">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="d64c2-357">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="d64c2-358">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="d64c2-358">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="d64c2-359">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="d64c2-359">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="d64c2-360">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="d64c2-360">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="d64c2-361">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="d64c2-361">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="d64c2-362">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="d64c2-362">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="d64c2-363">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="d64c2-363">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="d64c2-364">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="d64c2-364">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="d64c2-365">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="d64c2-365">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="d64c2-366">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="d64c2-366">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="d64c2-367">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="d64c2-367">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="d64c2-368">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="d64c2-368">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="d64c2-369">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="d64c2-369">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="d64c2-370">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="d64c2-370">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="d64c2-371">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="d64c2-371">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="d64c2-372">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="d64c2-372">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="d64c2-373">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="d64c2-373">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="d64c2-374">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="d64c2-374">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="d64c2-375">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="d64c2-375">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="d64c2-376">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="d64c2-376">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="d64c2-377">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="d64c2-377">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="d64c2-378">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="d64c2-378">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="d64c2-379">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="d64c2-379">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="d64c2-380">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="d64c2-380">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="d64c2-381">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="d64c2-381">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="d64c2-382">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="d64c2-382">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="d64c2-383">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="d64c2-383">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="d64c2-384">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="d64c2-384">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="d64c2-385">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="d64c2-385">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="d64c2-386">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="d64c2-386">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="d64c2-387">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="d64c2-387">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="d64c2-388">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="d64c2-388">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="d64c2-389">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="d64c2-389">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="d64c2-390">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="d64c2-390">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="d64c2-391">资源</span><span class="sxs-lookup"><span data-stu-id="d64c2-391">Resources</span></span>

- [<span data-ttu-id="d64c2-392">Microsoft 隐私</span><span class="sxs-lookup"><span data-stu-id="d64c2-392">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
