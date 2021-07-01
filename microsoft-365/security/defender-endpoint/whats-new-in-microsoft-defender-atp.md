---
title: Microsoft Defender for Endpoint 中的新增功能
description: 请参阅最新版本的 Microsoft Defender for Endpoint (GA) 中通常提供哪些功能，以及 Windows 10 和 Windows Server 中的安全功能。
keywords: 适用于终结点的 Microsoft Defender 中的新增功能， ga， 通用， 功能， 可用， 新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c200d4ac81f12e46b085261c5ece279839255f4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228383"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="32c32-104">Microsoft Defender for Endpoint 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="32c32-104">What's new in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="32c32-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="32c32-105">**Applies to:**</span></span>
- [<span data-ttu-id="32c32-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32c32-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="32c32-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32c32-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="32c32-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="32c32-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="32c32-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="32c32-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink)

<span data-ttu-id="32c32-110">在最新版本的 Microsoft Defender for Endpoint 中 (GA) 中通常提供以下功能，以及 Windows 10 和 Windows Server 中的安全功能。</span><span class="sxs-lookup"><span data-stu-id="32c32-110">The following features are generally available (GA) in the latest release of Microsoft Defender for Endpoint as well as security features in Windows 10 and Windows Server.</span></span>

<span data-ttu-id="32c32-111">有关预览功能的详细信息，请参阅预览 [功能](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="32c32-111">For more information on preview features, see [Preview features](preview.md).</span></span>


> [!TIP]
> <span data-ttu-id="32c32-112">RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：</span><span class="sxs-lookup"><span data-stu-id="32c32-112">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```https
> /api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

## <a name="june-2021"></a><span data-ttu-id="32c32-113">2021 年 6 月</span><span class="sxs-lookup"><span data-stu-id="32c32-113">June 2021</span></span>

- [<span data-ttu-id="32c32-114">设备发现</span><span class="sxs-lookup"><span data-stu-id="32c32-114">Device discovery</span></span>](device-discovery.md) <br> <span data-ttu-id="32c32-115">帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的流程更改。</span><span class="sxs-lookup"><span data-stu-id="32c32-115">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="32c32-116">使用载入的设备，可以在网络中查找非托管设备，并评估漏洞和风险。</span><span class="sxs-lookup"><span data-stu-id="32c32-116">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="32c32-117">然后，你可以载入发现的设备，以减少与网络中具有非托管终结点相关的风险。</span><span class="sxs-lookup"><span data-stu-id="32c32-117">You can then onboard discovered devices to reduce risks associated with having unmanaged endpoints in your network.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="32c32-118">从 2021 年 7 月 19 日开始，标准发现将成为所有客户的默认模式。</span><span class="sxs-lookup"><span data-stu-id="32c32-118">Standard discovery will be the default mode for all customers starting July 19, 2021.</span></span> <span data-ttu-id="32c32-119">你可以选择通过设置页保留基本模式。</span><span class="sxs-lookup"><span data-stu-id="32c32-119">You can choose to retain the basic mode through the settings page.</span></span>


- <span data-ttu-id="32c32-120">[现在，设备](/microsoft-365/security/defender-endpoint/machine-groups) 组定义可以包括每个条件的多个值。</span><span class="sxs-lookup"><span data-stu-id="32c32-120">[Device group definitions](/microsoft-365/security/defender-endpoint/machine-groups) can now include multiple values for each condition.</span></span> <span data-ttu-id="32c32-121">你可以将多个标记、设备名称和域设置为单个设备组的定义。</span><span class="sxs-lookup"><span data-stu-id="32c32-121">You can set multiple tags, device names, and domains to the definition of a single device group.</span></span>

## <a name="march-2021"></a><span data-ttu-id="32c32-122">2021 年 3 月</span><span class="sxs-lookup"><span data-stu-id="32c32-122">March 2021</span></span>
- [<span data-ttu-id="32c32-123">使用管理程序管理防Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="32c32-123">Manage tamper protection using the Microsoft Defender Security Center</span></span>](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) <br> <span data-ttu-id="32c32-124">您可以使用称为租户附加 Windows 10 Windows Server 2016 Windows Server 2019 上管理防 *篡改保护设置*。</span><span class="sxs-lookup"><span data-stu-id="32c32-124">You can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span>

## <a name="january-2021"></a><span data-ttu-id="32c32-125">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="32c32-125">January 2021</span></span>

- [<span data-ttu-id="32c32-126">Windows 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="32c32-126">Windows Virtual Desktop</span></span>](https://azure.microsoft.com/services/virtual-desktop/) <br> <span data-ttu-id="32c32-127">Microsoft Defender for Endpoint 现在添加了对虚拟Windows支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-127">Microsoft Defender for Endpoint now adds support for Windows Virtual Desktop.</span></span>

## <a name="december-2020"></a><span data-ttu-id="32c32-128">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="32c32-128">December 2020</span></span>
- [<span data-ttu-id="32c32-129">iOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32c32-129">Microsoft Defender for Endpoint on iOS</span></span>](microsoft-defender-endpoint-ios.md) <br> <span data-ttu-id="32c32-130">Microsoft Defender for Endpoint 现在增加了对 iOS 的支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-130">Microsoft Defender for Endpoint now adds support for iOS.</span></span> <span data-ttu-id="32c32-131">了解如何在 iOS 上安装、配置、更新和使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="32c32-131">Learn how to install, configure, update, and use Microsoft Defender for Endpoint on iOS.</span></span>

## <a name="september-2020"></a><span data-ttu-id="32c32-132">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="32c32-132">September 2020</span></span>
- [<span data-ttu-id="32c32-133">Android 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32c32-133">Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md) <br> <span data-ttu-id="32c32-134">Microsoft Defender for Endpoint 现在增加了对 Android 的支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-134">Microsoft Defender for Endpoint now adds support for Android.</span></span> <span data-ttu-id="32c32-135">了解如何在 Android 上安装、配置、更新和使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="32c32-135">Learn how to install, configure, update, and use Microsoft Defender for Endpoint on Android.</span></span>
- [<span data-ttu-id="32c32-136">威胁和漏洞管理 macOS 支持</span><span class="sxs-lookup"><span data-stu-id="32c32-136">Threat and vulnerability management macOS support</span></span>](tvm-supported-os.md)<br> <span data-ttu-id="32c32-137">适用于 macOS 的威胁漏洞管理现在公开预览版，它将持续检测 macOS 设备上存在漏洞，以帮助你通过关注风险确定修复优先级。</span><span class="sxs-lookup"><span data-stu-id="32c32-137">Threat and vulnerability management for macOS is now in public preview, and will continuously detect vulnerabilities on your macOS devices to help you prioritize remediation by focusing on risk.</span></span> <span data-ttu-id="32c32-138">有关详细信息，请从[Microsoft Tech Community博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-adds-depth-and-breadth-to-threat/ba-p/1695824)。</span><span class="sxs-lookup"><span data-stu-id="32c32-138">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-adds-depth-and-breadth-to-threat/ba-p/1695824).</span></span>


## <a name="august-2020"></a><span data-ttu-id="32c32-139">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="32c32-139">August 2020</span></span>
- [<span data-ttu-id="32c32-140">Android 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32c32-140">Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md) <br> <span data-ttu-id="32c32-141">Microsoft Defender for Endpoint 现在增加了对 Android 的支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-141">Microsoft Defender for Endpoint now adds support for Android.</span></span> <span data-ttu-id="32c32-142">了解如何在 Android 上安装、配置和使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="32c32-142">Learn how to install, configure, and use Microsoft Defender for Endpoint on Android.</span></span>


## <a name="july-2020"></a><span data-ttu-id="32c32-143">2020 年 7 月</span><span class="sxs-lookup"><span data-stu-id="32c32-143">July 2020</span></span>
- [<span data-ttu-id="32c32-144">创建证书指示器</span><span class="sxs-lookup"><span data-stu-id="32c32-144">Create indicators for certificates</span></span>](manage-indicators.md) <br> <span data-ttu-id="32c32-145">创建指示器以允许或阻止证书。</span><span class="sxs-lookup"><span data-stu-id="32c32-145">Create indicators to allow or block certificates.</span></span>

## <a name="june-2020"></a><span data-ttu-id="32c32-146">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="32c32-146">June 2020</span></span>
- [<span data-ttu-id="32c32-147">Microsoft Defender for Endpoint on Linux</span><span class="sxs-lookup"><span data-stu-id="32c32-147">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md) <br> <span data-ttu-id="32c32-148">Microsoft Defender for Endpoint 现在增加了对 Linux 的支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-148">Microsoft Defender for Endpoint now adds support for Linux.</span></span> <span data-ttu-id="32c32-149">了解如何在 Linux 上安装、配置、更新和使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="32c32-149">Learn how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

- [<span data-ttu-id="32c32-150">评估实验室中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="32c32-150">Attack simulators in the evaluation lab</span></span>](evaluation-lab.md#threat-simulator-scenarios) <br> <span data-ttu-id="32c32-151">Microsoft Defender for Endpoint 已与各种威胁模拟平台合作，让你可以方便地从门户内测试平台的功能。</span><span class="sxs-lookup"><span data-stu-id="32c32-151">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span>


## <a name="april-2020"></a><span data-ttu-id="32c32-152">2020 年 4 月</span><span class="sxs-lookup"><span data-stu-id="32c32-152">April 2020</span></span>

- [<span data-ttu-id="32c32-153">威胁&漏洞管理 API 支持</span><span class="sxs-lookup"><span data-stu-id="32c32-153">Threat & Vulnerability Management API support</span></span>](exposed-apis-list.md) <BR><span data-ttu-id="32c32-154">运行威胁&漏洞管理相关的 API 调用，例如获取组织的威胁暴露分数或设备安全分数、软件和设备漏洞清单、软件版本分布、设备漏洞信息、安全建议信息。</span><span class="sxs-lookup"><span data-stu-id="32c32-154">Run Threat & Vulnerability Management-related API calls such as get your organization's threat exposure score or device secure score, software and device vulnerability inventory, software version distribution, device vulnerability information, security recommendation information.</span></span> <span data-ttu-id="32c32-155">有关详细信息，请从[Microsoft Tech Community博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。</span><span class="sxs-lookup"><span data-stu-id="32c32-155">Learn more from this [Microsoft Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).</span></span>

## <a name="november-december-2019"></a><span data-ttu-id="32c32-156">November-December 2019 年</span><span class="sxs-lookup"><span data-stu-id="32c32-156">November-December 2019</span></span>

- [<span data-ttu-id="32c32-157">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32c32-157">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md) <BR> <span data-ttu-id="32c32-158">macOS 上的 Microsoft Defender for Endpoint 为 Mac 设备带来了下一代保护。</span><span class="sxs-lookup"><span data-stu-id="32c32-158">Microsoft Defender for Endpoint on macOS brings the next-generation protection to Mac devices.</span></span> <span data-ttu-id="32c32-159">统一终结点安全平台的核心组件现在可用于 Mac 设备，包括 [终结点检测和响应](microsoft-defender-endpoint-mac.md)。</span><span class="sxs-lookup"><span data-stu-id="32c32-159">Core components of the unified endpoint security platform will now be available for Mac devices, including [endpoint detection and response](microsoft-defender-endpoint-mac.md).</span></span>

- [<span data-ttu-id="32c32-160">威胁&漏洞管理应用程序和应用程序版本生命周期结束信息</span><span class="sxs-lookup"><span data-stu-id="32c32-160">Threat & Vulnerability Management application and application version end-of-life information</span></span>](tvm-security-recommendation.md) <BR><span data-ttu-id="32c32-161">已进入生命周期结束的应用程序和应用程序版本会进行标记或标记，以便你了解它们将不再受支持，并且可以采取措施卸载或替换它们。</span><span class="sxs-lookup"><span data-stu-id="32c32-161">Applications and application versions which have reached their end-of-life are tagged or labeled as such so you are aware that they will no longer be supported, and can take action to either uninstall or replace.</span></span> <span data-ttu-id="32c32-162">这样做有助于降低因应用程序未修补导致的各种漏洞暴露的风险。</span><span class="sxs-lookup"><span data-stu-id="32c32-162">Doing so will help lessen the risks related to various vulnerability exposures due to unpatched applications.</span></span>

- [<span data-ttu-id="32c32-163">威胁&漏洞管理高级搜寻架构</span><span class="sxs-lookup"><span data-stu-id="32c32-163">Threat & Vulnerability Management Advanced Hunting Schemas</span></span>](advanced-hunting-schema-reference.md) <BR><span data-ttu-id="32c32-164">使用高级&中的威胁和漏洞管理表查询软件清单、漏洞知识库、安全配置评估和安全配置知识库。</span><span class="sxs-lookup"><span data-stu-id="32c32-164">Use the Threat & Vulnerability Management tables in the Advanced hunting schema to query about software inventory, vulnerability knowledgebase, security configuration assessment, and security configuration knowledgebase.</span></span>

 - [<span data-ttu-id="32c32-165">威胁&漏洞管理基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="32c32-165">Threat & Vulnerability Management role-based access controls</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) <BR><span data-ttu-id="32c32-166">使用新权限可允许最大灵活性创建面向 SecOps 的角色、面向威胁 & 漏洞管理的角色或混合角色，以便仅授权用户访问特定数据以执行任务。</span><span class="sxs-lookup"><span data-stu-id="32c32-166">Use the new permissions to allow maximum flexibility to create SecOps-oriented roles, Threat & Vulnerability Management-oriented roles, or hybrid roles so only authorized users are accessing specific data to do their task.</span></span> <span data-ttu-id="32c32-167">您还可以通过指定威胁和漏洞&管理角色是只能查看与漏洞相关的数据，还是可以创建和管理修正和异常，以进一步实现粒度。</span><span class="sxs-lookup"><span data-stu-id="32c32-167">You can also achieve even further granularity by specifying whether a Threat & Vulnerability Management role can only view vulnerability-related data, or can create and manage remediation and exceptions.</span></span>

- [<span data-ttu-id="32c32-168">设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="32c32-168">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="32c32-169">设备运行状况和合规性报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="32c32-169">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

## <a name="october-2019"></a><span data-ttu-id="32c32-170">2019 年 10 月</span><span class="sxs-lookup"><span data-stu-id="32c32-170">October 2019</span></span>

- [<span data-ttu-id="32c32-171">IP 地址、URL/域指示器</span><span class="sxs-lookup"><span data-stu-id="32c32-171">Indicators for IP addresses, URLs/Domains</span></span>](manage-indicators.md) <BR> <span data-ttu-id="32c32-172">你现在可以使用自己的威胁情报允许或阻止 URL/域。</span><span class="sxs-lookup"><span data-stu-id="32c32-172">You can now allow or block URLs/domains using your own threat intelligence.</span></span>


- [<span data-ttu-id="32c32-173">Microsoft 威胁专家 - 专家按需</span><span class="sxs-lookup"><span data-stu-id="32c32-173">Microsoft Threat Experts - Experts on Demand</span></span>](microsoft-threat-experts.md) <BR> <span data-ttu-id="32c32-174">现在，您可以选择从门户Microsoft 威胁专家咨询相关内容，以帮助你在调查上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="32c32-174">You now have the option to consult with Microsoft Threat Experts from several places in the portal to help you in the context of your investigation.</span></span>

- [<span data-ttu-id="32c32-175">连接的 Azure AD 应用程序</span><span class="sxs-lookup"><span data-stu-id="32c32-175">Connected Azure AD applications</span></span>](connected-applications.md)<br> <span data-ttu-id="32c32-176">"已连接应用程序"页提供有关连接到组织中 Microsoft Defender for Endpoint 的 Azure AD 应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="32c32-176">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span>

- [<span data-ttu-id="32c32-177">API 资源管理器</span><span class="sxs-lookup"><span data-stu-id="32c32-177">API Explorer</span></span>](api-explorer.md)<br> <span data-ttu-id="32c32-178">通过 API 资源管理器，可以轻松构造和执行 API 查询、测试和发送任何可用 Microsoft Defender 终结点 API 终结点的请求。</span><span class="sxs-lookup"><span data-stu-id="32c32-178">The API explorer makes it easy to construct and perform API queries, test and send requests for any available Microsoft Defender for Endpoint API endpoint.</span></span>


## <a name="september-2019"></a><span data-ttu-id="32c32-179">2019 年 9 月</span><span class="sxs-lookup"><span data-stu-id="32c32-179">September 2019</span></span>

- [<span data-ttu-id="32c32-180">使用 Intune 的防篡改保护设置</span><span class="sxs-lookup"><span data-stu-id="32c32-180">Tamper Protection settings using Intune</span></span>](prevent-changes-to-security-settings-with-tamper-protection.md)<br/><span data-ttu-id="32c32-181">现在，你可以打开或 (Intune) Intune Microsoft 365 Device Management Portal 中的组织 (防篡改) 。</span><span class="sxs-lookup"><span data-stu-id="32c32-181">You can now turn Tamper Protection on (or off) for your organization in the Microsoft 365 Device Management Portal (Intune).</span></span>

- [<span data-ttu-id="32c32-182">实时响应</span><span class="sxs-lookup"><span data-stu-id="32c32-182">Live response</span></span>](live-response.md)<BR> <span data-ttu-id="32c32-183">使用远程 Shell 连接即时访问设备。</span><span class="sxs-lookup"><span data-stu-id="32c32-183">Get instantaneous access to a device using a remote shell connection.</span></span> <span data-ttu-id="32c32-184">开展深入调查工作，并立即采取响应操作，以立即包含识别的威胁- 实时。</span><span class="sxs-lookup"><span data-stu-id="32c32-184">Do in-depth investigative work and take immediate response actions to promptly contain identified threats - real-time.</span></span>

- [<span data-ttu-id="32c32-185">评估实验室</span><span class="sxs-lookup"><span data-stu-id="32c32-185">Evaluation lab</span></span>](evaluation-lab.md) <BR> <span data-ttu-id="32c32-186">Microsoft Defender for Endpoint 评估实验室旨在消除设备和环境配置的复杂性，以便你可以专注于评估平台的功能、运行模拟，并查看防护、检测和修正功能的操作。</span><span class="sxs-lookup"><span data-stu-id="32c32-186">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

- [<span data-ttu-id="32c32-187">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="32c32-187">Windows Server 2008 R2 SP1</span></span>](configure-server-endpoints.md) <BR> <span data-ttu-id="32c32-188">现在可以载入 Windows Server 2008 R2 SP1。</span><span class="sxs-lookup"><span data-stu-id="32c32-188">You can now onboard Windows Server 2008 R2 SP1.</span></span>


## <a name="june-2019"></a><span data-ttu-id="32c32-189">2019 年 6 月</span><span class="sxs-lookup"><span data-stu-id="32c32-189">June 2019</span></span>

- [<span data-ttu-id="32c32-190">威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="32c32-190">Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md) <BR> <span data-ttu-id="32c32-191">一种新的内置功能，使用基于风险的方法发现、优先顺序和修复终结点漏洞和错误配置。</span><span class="sxs-lookup"><span data-stu-id="32c32-191">A new built-in capability that uses a risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- <span data-ttu-id="32c32-192">[设备运行状况和合规性报告](machine-reports.md)  设备运行状况和合规性报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="32c32-192">[Device health and compliance report](machine-reports.md)  The device health and compliance report provides high-level information about the devices in your organization.</span></span>

## <a name="may-2019"></a><span data-ttu-id="32c32-193">2019 年 5 月</span><span class="sxs-lookup"><span data-stu-id="32c32-193">May 2019</span></span>

- [<span data-ttu-id="32c32-194">威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="32c32-194">Threat protection reports</span></span>](threat-protection-reports.md)<BR><span data-ttu-id="32c32-195">威胁防护报告提供有关在组织中生成的警报的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="32c32-195">The threat protection report provides high-level information about alerts generated in your organization.</span></span>


- [<span data-ttu-id="32c32-196">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="32c32-196">Microsoft Threat Experts</span></span>](microsoft-threat-experts.md)<BR> <span data-ttu-id="32c32-197">Microsoft 威胁专家是 Microsoft Defender for Endpoint 中新增的托管威胁搜寻服务，可提供主动搜寻、优先顺序和其他上下文和见解，进一步使安全运营中心 (SOC) 可以快速准确地识别和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="32c32-197">Microsoft Threat Experts is the new managed threat hunting service in Microsoft Defender for Endpoint that provides proactive hunting, prioritization, and additional context and insights that further empower security operations centers (SOCs) to identify and respond to threats quickly and accurately.</span></span> <span data-ttu-id="32c32-198">它提供了 Microsoft 客户可以利用的其他专业技能和光学系统层来增强安全操作功能，这是 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="32c32-198">It provides additional layer of expertise and optics that Microsoft customers can utilize to augment security operation capabilities as part of Microsoft 365.</span></span>

- [<span data-ttu-id="32c32-199">指示器</span><span class="sxs-lookup"><span data-stu-id="32c32-199">Indicators</span></span>](ti-indicator.md) <BR> <span data-ttu-id="32c32-200">指示器的 API 现已普遍可用。</span><span class="sxs-lookup"><span data-stu-id="32c32-200">APIs for indicators are now generally available.</span></span>


- [<span data-ttu-id="32c32-201">互操作性</span><span class="sxs-lookup"><span data-stu-id="32c32-201">Interoperability</span></span>](partner-applications.md) <BR> <span data-ttu-id="32c32-202">Microsoft Defender for Endpoint 支持第三方应用程序，以帮助增强平台的检测、调查和威胁智能功能。</span><span class="sxs-lookup"><span data-stu-id="32c32-202">Microsoft Defender for Endpoint supports third-party applications to help enhance the detection, investigation, and threat intelligence capabilities of the platform.</span></span>


## <a name="april-2019"></a><span data-ttu-id="32c32-203">2019 年 4 月</span><span class="sxs-lookup"><span data-stu-id="32c32-203">April 2019</span></span>
- [<span data-ttu-id="32c32-204">Microsoft 威胁专家目标攻击通知功能</span><span class="sxs-lookup"><span data-stu-id="32c32-204">Microsoft Threat Experts Targeted Attack Notification capability</span></span>](microsoft-threat-experts.md) <BR> <span data-ttu-id="32c32-205">Microsoft 威胁专家目标攻击通知警报专为组织定制，可提供尽可能多的信息，从而引起人们注意其网络中的关键威胁，包括时间线、入侵范围和入侵方法。</span><span class="sxs-lookup"><span data-stu-id="32c32-205">Microsoft Threat Experts' Targeted Attack Notification alerts are tailored to organizations to provide as much information as can be quickly delivered thus bringing attention to critical threats in their network, including the timeline, scope of breach, and the methods of intrusion.</span></span>

- [<span data-ttu-id="32c32-206">Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="32c32-206">Microsoft Defender for Endpoint API</span></span>](apis-intro.md) <BR> <span data-ttu-id="32c32-207">Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="32c32-207">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="32c32-208">这些 API 将使您能够基于 Microsoft Defender for Endpoint 功能自动执行工作流创新。</span><span class="sxs-lookup"><span data-stu-id="32c32-208">Those APIs will enable you to automate workflows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span>



## <a name="february-2019"></a><span data-ttu-id="32c32-209">2019 年 2 月</span><span class="sxs-lookup"><span data-stu-id="32c32-209">February 2019</span></span>
- [<span data-ttu-id="32c32-210">事件</span><span class="sxs-lookup"><span data-stu-id="32c32-210">Incidents</span></span>](view-incidents-queue.md) <BR> <span data-ttu-id="32c32-211">事件是 Microsoft Defender for Endpoint 中的一个新实体，将所有相关警报和相关实体汇集在一起，以讲述更广泛的攻击案例，使分析人员可以更好地了解复杂威胁的可能性。</span><span class="sxs-lookup"><span data-stu-id="32c32-211">Incident is a new entity in Microsoft Defender for Endpoint that brings together all relevant alerts and related entities to narrate the broader attack story, giving analysts better perspective on the purview of complex threats.</span></span>

- [<span data-ttu-id="32c32-212">载入以前版本的 Windows</span><span class="sxs-lookup"><span data-stu-id="32c32-212">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)<BR> <span data-ttu-id="32c32-213">载入支持的设备Windows，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器。</span><span class="sxs-lookup"><span data-stu-id="32c32-213">Onboard supported versions of Windows devices so that they can send sensor data to the Microsoft Defender for Endpoint sensor.</span></span>


## <a name="october-2018"></a><span data-ttu-id="32c32-214">2018 年 10 月</span><span class="sxs-lookup"><span data-stu-id="32c32-214">October 2018</span></span>
- [<span data-ttu-id="32c32-215">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="32c32-215">Attack surface reduction rules</span></span>](attack-surface-reduction.md)<BR><span data-ttu-id="32c32-216">所有攻击面减少规则现在在 Windows Server 2019 上受支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-216">All Attack surface reduction rules are now supported on Windows Server 2019.</span></span>

- [<span data-ttu-id="32c32-217">受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="32c32-217">Controlled folder access</span></span>](enable-controlled-folders.md)<BR> <span data-ttu-id="32c32-218">现在，Windows Server 2019 支持受控文件夹访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c32-218">Controlled folder access is now supported on Windows Server 2019.</span></span>

- [<span data-ttu-id="32c32-219">自定义检测</span><span class="sxs-lookup"><span data-stu-id="32c32-219">Custom detection</span></span>](manage-indicators.md)<BR><span data-ttu-id="32c32-220">通过自定义检测，你可以创建自定义查询来监视任何类型的行为（如可疑或新出现的威胁）的事件。</span><span class="sxs-lookup"><span data-stu-id="32c32-220">With custom detections, you can create custom queries to monitor events for any kind of behavior such as suspicious or emerging threats.</span></span> <span data-ttu-id="32c32-221">这可以通过创建自定义检测规则来利用高级搜寻功能实现。</span><span class="sxs-lookup"><span data-stu-id="32c32-221">This can be done by leveraging the power of advanced hunting through the creation of custom detection rules.</span></span>

- [<span data-ttu-id="32c32-222">与 Azure Defender 集成</span><span class="sxs-lookup"><span data-stu-id="32c32-222">Integration with Azure Defender</span></span>](configure-server-endpoints.md)<BR> <span data-ttu-id="32c32-223">Microsoft Defender for Endpoint 与 Azure Defender 集成，以提供全面的服务器保护解决方案。</span><span class="sxs-lookup"><span data-stu-id="32c32-223">Microsoft Defender for Endpoint integrates with Azure Defender to provide a comprehensive server protection solution.</span></span> <span data-ttu-id="32c32-224">借助此集成，Azure Defender 可以利用 Microsoft Defender for Endpoint 功能，为 Windows 服务器提供改进的威胁检测。</span><span class="sxs-lookup"><span data-stu-id="32c32-224">With this integration Azure Defender can leverage the power of Microsoft Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

- [<span data-ttu-id="32c32-225">托管安全服务提供程序 (MSSP) 支持</span><span class="sxs-lookup"><span data-stu-id="32c32-225">Managed security service provider (MSSP) support</span></span>](mssp-support.md)<BR> <span data-ttu-id="32c32-226">Microsoft Defender for Endpoint 通过提供 MSSP 集成添加了对此方案的支持。</span><span class="sxs-lookup"><span data-stu-id="32c32-226">Microsoft Defender for Endpoint adds support for this scenario by providing MSSP integration.</span></span> <span data-ttu-id="32c32-227">通过集成，MSSP 可以执行以下操作：获取对 MSSP 客户的 Microsoft Defender 安全中心 门户的访问权限、获取电子邮件通知，以及使用 SIEM) 工具通过安全信息和事件管理获取 (警报。</span><span class="sxs-lookup"><span data-stu-id="32c32-227">The integration will allow MSSPs to take the following actions: Get access to MSSP customer's Microsoft Defender Security Center portal, fetch email notifications, and fetch alerts through security information and event management (SIEM) tools.</span></span>

- [<span data-ttu-id="32c32-228">可移动设备控件</span><span class="sxs-lookup"><span data-stu-id="32c32-228">Removable device control</span></span>](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)<BR><span data-ttu-id="32c32-229">Microsoft Defender for Endpoint 提供了多个监视和控制功能，以帮助防止来自可移动设备的威胁，包括允许或阻止特定硬件 ID 的新设置。</span><span class="sxs-lookup"><span data-stu-id="32c32-229">Microsoft Defender for Endpoint provides multiple monitoring and control features to help prevent threats from removable devices, including new settings to allow or block specific hardware IDs.</span></span>

- [<span data-ttu-id="32c32-230">支持 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="32c32-230">Support for iOS and Android devices</span></span>](configure-endpoints-non-windows.md)<BR> <span data-ttu-id="32c32-231">iOS 和 Android 设备现在受支持，可以载入到服务。</span><span class="sxs-lookup"><span data-stu-id="32c32-231">iOS and Android devices are now supported and can be onboarded to the service.</span></span>

- [<span data-ttu-id="32c32-232">威胁分析</span><span class="sxs-lookup"><span data-stu-id="32c32-232">Threat analytics</span></span>](threat-analytics.md)<BR>
<span data-ttu-id="32c32-233">威胁分析是 Microsoft Defender for Endpoint 研究团队在发现新出现的威胁和爆发后尽快发布的一组交互式报告。</span><span class="sxs-lookup"><span data-stu-id="32c32-233">Threat Analytics is a set of interactive reports published by the Microsoft Defender for Endpoint research team as soon as emerging threats and outbreaks are identified.</span></span> <span data-ttu-id="32c32-234">这些报告可帮助安全运营团队评估对环境的影响，并提供包含、提高组织恢复能力并防止特定威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="32c32-234">The reports help security operations teams assess impact on their environment and provides recommended actions to contain, increase organizational resilience, and prevent specific threats.</span></span>

- <span data-ttu-id="32c32-235">版本 1809 Windows 10中的新增功能，有两个新的攻击面减少规则：</span><span class="sxs-lookup"><span data-stu-id="32c32-235">New in Windows 10 version 1809, there are two new attack surface reduction rules:</span></span>
  - <span data-ttu-id="32c32-236">阻止 Adobe Reader 创建子进程</span><span class="sxs-lookup"><span data-stu-id="32c32-236">Block Adobe Reader from creating child processes</span></span>
  - <span data-ttu-id="32c32-237">阻止Office应用程序创建子进程。</span><span class="sxs-lookup"><span data-stu-id="32c32-237">Block Office communication application from creating child processes.</span></span>

- [<span data-ttu-id="32c32-238">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="32c32-238">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)
  - <span data-ttu-id="32c32-239">反恶意软件扫描接口 (AMSI) 扩展为覆盖Office VBA 宏。</span><span class="sxs-lookup"><span data-stu-id="32c32-239">Antimalware Scan Interface (AMSI) was extended to cover Office VBA macros as well.</span></span> <span data-ttu-id="32c32-240">[Office VBA + AMSI：将恶意宏上的宏分在一起](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/)。</span><span class="sxs-lookup"><span data-stu-id="32c32-240">[Office VBA + AMSI: Parting the veil on malicious macros](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/).</span></span>
  - <span data-ttu-id="32c32-241">Microsoft Defender 防病毒版本 1809 中新增Windows 10，现在可以在沙盒 (预览[](https://www.microsoft.com/security/blog/2018/10/26/windows-defender-antivirus-can-now-run-in-a-sandbox)) 运行，从而提升其安全性。</span><span class="sxs-lookup"><span data-stu-id="32c32-241">Microsoft Defender Antivirus, new in Windows 10 version 1809, can now [run within a sandbox](https://www.microsoft.com/security/blog/2018/10/26/windows-defender-antivirus-can-now-run-in-a-sandbox) (preview), increasing its security.</span></span>
  - <span data-ttu-id="32c32-242">[配置用于扫描的 CPU](configure-advanced-scan-types-microsoft-defender-antivirus.md) Microsoft Defender 防病毒设置。</span><span class="sxs-lookup"><span data-stu-id="32c32-242">[Configure CPU priority settings](configure-advanced-scan-types-microsoft-defender-antivirus.md) for Microsoft Defender Antivirus scans.</span></span>

## <a name="march-2018"></a><span data-ttu-id="32c32-243">2018 年 3 月</span><span class="sxs-lookup"><span data-stu-id="32c32-243">March 2018</span></span>

- [<span data-ttu-id="32c32-244">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="32c32-244">Advanced Hunting</span></span>](advanced-hunting-overview.md)

   <span data-ttu-id="32c32-245">在 Microsoft Defender for Endpoint 中使用高级搜寻查询数据。</span><span class="sxs-lookup"><span data-stu-id="32c32-245">Query data using advanced hunting in Microsoft Defender for Endpoint.</span></span>

- [<span data-ttu-id="32c32-246">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="32c32-246">Attack surface reduction rules</span></span>](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)

  <span data-ttu-id="32c32-247">新的攻击面减少规则：</span><span class="sxs-lookup"><span data-stu-id="32c32-247">New attack surface reduction rules:</span></span>

  - <span data-ttu-id="32c32-248">使用高级防护抵御勒索软件</span><span class="sxs-lookup"><span data-stu-id="32c32-248">Use advanced protection against ransomware</span></span>
  - <span data-ttu-id="32c32-249">阻止本地安全机构子系统Windows窃取凭据 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="32c32-249">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
  - <span data-ttu-id="32c32-250">阻止源自 PSExec 和 WMI 命令的进程创建</span><span class="sxs-lookup"><span data-stu-id="32c32-250">Block process creations originating from PSExec and WMI commands</span></span>
  - <span data-ttu-id="32c32-251">阻止从 USB 运行的不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="32c32-251">Block untrusted and unsigned processes that run from USB</span></span>
  - <span data-ttu-id="32c32-252">阻止来自电子邮件客户端和 Webmail 的可执行内容</span><span class="sxs-lookup"><span data-stu-id="32c32-252">Block executable content from email client and webmail</span></span>

- [<span data-ttu-id="32c32-253">自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="32c32-253">Automated investigation and remediation</span></span>](automated-investigations.md)<BR> <span data-ttu-id="32c32-254">使用自动调查来调查和修正威胁。</span><span class="sxs-lookup"><span data-stu-id="32c32-254">Use Automated investigations to investigate and remediate threats.</span></span>

    > [!NOTE]
    > <span data-ttu-id="32c32-255">可从 Windows 10 版本 1803 或更高版本获得。</span><span class="sxs-lookup"><span data-stu-id="32c32-255">Available from Windows 10, version 1803 or later.</span></span>

- [<span data-ttu-id="32c32-256">条件访问</span><span class="sxs-lookup"><span data-stu-id="32c32-256">Conditional Access</span></span>](conditional-access.md) <br> <span data-ttu-id="32c32-257">启用条件访问以更好地保护用户、设备和数据。</span><span class="sxs-lookup"><span data-stu-id="32c32-257">Enable conditional access to better protect users, devices, and data.</span></span>

- [<span data-ttu-id="32c32-258">Microsoft Defender for Endpoint Community 中心</span><span class="sxs-lookup"><span data-stu-id="32c32-258">Microsoft Defender for Endpoint Community center</span></span>](community.md)<BR>
    <span data-ttu-id="32c32-259">Microsoft Defender for Endpoint Community 中心是社区成员可以学习、协作和共享产品体验的地方。</span><span class="sxs-lookup"><span data-stu-id="32c32-259">The Microsoft Defender for Endpoint Community Center is a place where community members can learn, collaborate, and share experiences about the product.</span></span>

- [<span data-ttu-id="32c32-260">受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="32c32-260">Controlled folder access</span></span>](enable-controlled-folders.md)<BR>
<span data-ttu-id="32c32-261">你现在可以使用受控文件夹访问权限阻止不受信任的进程写入磁盘扇区。</span><span class="sxs-lookup"><span data-stu-id="32c32-261">You can now block untrusted processes from writing to disk sectors using Controlled Folder Access.</span></span>

- [<span data-ttu-id="32c32-262">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="32c32-262">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)<BR>
    <span data-ttu-id="32c32-263">Microsoft Defender for Endpoint 为用户和非 Windows平台提供了集中式安全Windows体验。</span><span class="sxs-lookup"><span data-stu-id="32c32-263">Microsoft Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="32c32-264">你将能够查看来自各种支持的操作系统和操作系统警报 (操作系统) Microsoft Defender 安全中心更好地保护组织的网络。</span><span class="sxs-lookup"><span data-stu-id="32c32-264">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span>

- [<span data-ttu-id="32c32-265">基于角色的访问控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="32c32-265">Role-based access control (RBAC)</span></span>](rbac.md)<BR>
    <span data-ttu-id="32c32-266">使用基于角色的访问控制 (RBAC) ，可以在安全操作团队内创建角色和组，以授予对门户的适当访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c32-266">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the portal.</span></span>


- [<span data-ttu-id="32c32-267">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="32c32-267">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)<BR>
<span data-ttu-id="32c32-268">Microsoft Defender 防病毒服务之间共享检测状态Microsoft 365与 Microsoft Defender for Endpoint 进行互操作。</span><span class="sxs-lookup"><span data-stu-id="32c32-268">Microsoft Defender Antivirus now shares detection status between Microsoft 365 services and interoperates with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="32c32-269">有关详细信息，请参阅通过云保护在 Microsoft Defender 防病毒[中使用下一代技术](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="32c32-269">For more information, see [Use next-gen technologies in Microsoft Defender Antivirus through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).</span></span>

    <span data-ttu-id="32c32-270">"首次看到时阻止"现在可以阻止不可移植的可执行 (，例如 JS、VBS 或宏) 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="32c32-270">Block at first sight can now block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span> <span data-ttu-id="32c32-271">有关详细信息，请参阅启用 [首次看到时阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="32c32-271">For more information, see [Enable block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md).</span></span>


