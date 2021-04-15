---
title: 使用适用于 Mac 的 Microsoft Defender ATP (MDM) 不同的移动设备管理部署
description: 在其他管理解决方案上安装 Microsoft Defender ATP for Mac。
keywords: microsoft， defender， atp， mac， 安装， 部署， macos， 加泰罗尼亚语， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3343eb433a6ae5c708651abf298bd4f061817543
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764129"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ef17d-104">在 macOS 上使用不同的移动设备管理 (MDM) 系统部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ef17d-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ef17d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ef17d-105">**Applies to:**</span></span>
- [<span data-ttu-id="ef17d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ef17d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ef17d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef17d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ef17d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ef17d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ef17d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ef17d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="ef17d-110">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="ef17d-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="ef17d-111">在开始使用之前，请参阅 [macOS](microsoft-defender-endpoint-mac.md) 上的 Microsoft Defender for Endpoint 主页，了解当前软件版本的先决条件和系统要求说明。</span><span class="sxs-lookup"><span data-stu-id="ef17d-111">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="approach"></a><span data-ttu-id="ef17d-112">方法</span><span class="sxs-lookup"><span data-stu-id="ef17d-112">Approach</span></span>

> [!CAUTION]

> <span data-ttu-id="ef17d-113">目前，Microsoft 正式仅支持 Intune 和 JAMF 在 macOS 上部署和管理 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="ef17d-113">Currently, Microsoft officially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="ef17d-114">Microsoft 对下面提供的信息不做出明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="ef17d-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="ef17d-115">如果你的组织使用未正式支持的移动设备管理 (MDM) 解决方案，这并不意味着无法在 macOS 上部署或运行 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="ef17d-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="ef17d-116">macOS 上的 Microsoft Defender for Endpoint 不依赖于任何特定于供应商的功能。</span><span class="sxs-lookup"><span data-stu-id="ef17d-116">Microsoft Defender for Endpoint on macOS does not depend on any vendor-specific features.</span></span> <span data-ttu-id="ef17d-117">它可以与支持以下功能的任何 MDM 解决方案一同使用：</span><span class="sxs-lookup"><span data-stu-id="ef17d-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="ef17d-118">将 macOS .pkg 部署到托管设备。</span><span class="sxs-lookup"><span data-stu-id="ef17d-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="ef17d-119">将 macOS 系统配置文件部署到托管设备。</span><span class="sxs-lookup"><span data-stu-id="ef17d-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="ef17d-120">在托管设备上运行任意管理员配置的工具/脚本。</span><span class="sxs-lookup"><span data-stu-id="ef17d-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="ef17d-121">大多数现代 MDM 解决方案都包括这些功能，但是，它们调用它们的方式可能不同。</span><span class="sxs-lookup"><span data-stu-id="ef17d-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="ef17d-122">但是，你可以部署 Defender，无需上述列表中的最后一项要求：</span><span class="sxs-lookup"><span data-stu-id="ef17d-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="ef17d-123">无法集中收集状态</span><span class="sxs-lookup"><span data-stu-id="ef17d-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="ef17d-124">如果你决定卸载 Defender，你将需要以管理员角色在本地登录到客户端设备</span><span class="sxs-lookup"><span data-stu-id="ef17d-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="ef17d-125">部署</span><span class="sxs-lookup"><span data-stu-id="ef17d-125">Deployment</span></span>

<span data-ttu-id="ef17d-126">大多数 MDM 解决方案都使用相同的模型来管理 macOS 设备，使用类似的术语。</span><span class="sxs-lookup"><span data-stu-id="ef17d-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="ef17d-127">将 [基于 JAMF 的部署](mac-install-with-jamf.md) 用作模板。</span><span class="sxs-lookup"><span data-stu-id="ef17d-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="ef17d-128">程序包</span><span class="sxs-lookup"><span data-stu-id="ef17d-128">Package</span></span>

<span data-ttu-id="ef17d-129">配置所需应用程序 [包](mac-install-with-jamf.md)的部署，安装程序包 (wdav.pkg) [从 Microsoft Defender 安全中心下载](mac-install-with-jamf.md)。</span><span class="sxs-lookup"><span data-stu-id="ef17d-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="ef17d-130">若要将程序包部署到企业，请使用与 MDM 解决方案关联的说明。</span><span class="sxs-lookup"><span data-stu-id="ef17d-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="ef17d-131">许可证设置</span><span class="sxs-lookup"><span data-stu-id="ef17d-131">License settings</span></span>

<span data-ttu-id="ef17d-132">设置 [系统配置文件](mac-install-with-jamf.md)。</span><span class="sxs-lookup"><span data-stu-id="ef17d-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> 

<span data-ttu-id="ef17d-133">MDM 解决方案可能称其为"自定义设置配置文件"，因为 macOS 上的 Microsoft Defender for Endpoint 不是 macOS 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ef17d-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint on macOS is not part of macOS.</span></span>

<span data-ttu-id="ef17d-134">使用属性列表 jamf/WindowsDefenderATPOnboarding.plist，可从从 Microsoft Defender 安全中心下载的载入 [包中提取](mac-install-with-jamf.md)。</span><span class="sxs-lookup"><span data-stu-id="ef17d-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="ef17d-135">您的系统可能支持 XML 格式的任意属性列表。</span><span class="sxs-lookup"><span data-stu-id="ef17d-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="ef17d-136">在这种情况下，你可以像现在一样上传 jamf/WindowsDefenderATPOnboarding.plist 文件。</span><span class="sxs-lookup"><span data-stu-id="ef17d-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="ef17d-137">或者，可能需要先将属性列表转换为其他格式。</span><span class="sxs-lookup"><span data-stu-id="ef17d-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="ef17d-138">通常，自定义配置文件具有 ID、名称或域属性。</span><span class="sxs-lookup"><span data-stu-id="ef17d-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="ef17d-139">必须完全使用"com.microsoft.wdav.atp"作为此值。</span><span class="sxs-lookup"><span data-stu-id="ef17d-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="ef17d-140">MDM 使用它将设置文件部署到客户端设备的 **/Library/Managed Preferences/com.microsoft.wdav.atp.plist，Defender** 使用此文件加载载入信息。</span><span class="sxs-lookup"><span data-stu-id="ef17d-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="ef17d-141">内核扩展策略</span><span class="sxs-lookup"><span data-stu-id="ef17d-141">Kernel extension policy</span></span>

<span data-ttu-id="ef17d-142">设置 KEXT 或内核扩展策略。</span><span class="sxs-lookup"><span data-stu-id="ef17d-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="ef17d-143">使用团队标识符 **UBF8T346G9** 允许 Microsoft 提供的内核扩展。</span><span class="sxs-lookup"><span data-stu-id="ef17d-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

> [!CAUTION]
> <span data-ttu-id="ef17d-144">如果您的环境由 Apple 芯片 (M1) ，则这些计算机不应接收包含 KEXT 策略的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ef17d-144">If your environment consists of Apple Silicon (M1) devices, these machines should not receive configuration profiles with KEXT policies.</span></span>
> <span data-ttu-id="ef17d-145">Apple 在这些计算机上不支持 KEXT，在 M1 计算机上部署此类配置文件将失败。</span><span class="sxs-lookup"><span data-stu-id="ef17d-145">Apple does not support KEXT on these machines, deployment of such profile would fail on M1 machines.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="ef17d-146">系统扩展策略</span><span class="sxs-lookup"><span data-stu-id="ef17d-146">System extension policy</span></span>

<span data-ttu-id="ef17d-147">设置系统扩展策略。</span><span class="sxs-lookup"><span data-stu-id="ef17d-147">Set up a system extension policy.</span></span> <span data-ttu-id="ef17d-148">使用团队标识符 **UBF8T346G9** 并批准以下捆绑包标识符：</span><span class="sxs-lookup"><span data-stu-id="ef17d-148">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="ef17d-149">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="ef17d-149">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="ef17d-150">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="ef17d-150">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="ef17d-151">完全磁盘访问策略</span><span class="sxs-lookup"><span data-stu-id="ef17d-151">Full disk access policy</span></span>

<span data-ttu-id="ef17d-152">授予对以下组件的完全磁盘访问权限：</span><span class="sxs-lookup"><span data-stu-id="ef17d-152">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="ef17d-153">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ef17d-153">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="ef17d-154">标识符： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="ef17d-154">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="ef17d-155">标识符类型：捆绑包 ID</span><span class="sxs-lookup"><span data-stu-id="ef17d-155">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="ef17d-156">代码要求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="ef17d-156">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="ef17d-157">Microsoft Defender for Endpoint Security Extension</span><span class="sxs-lookup"><span data-stu-id="ef17d-157">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="ef17d-158">标识符： `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="ef17d-158">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="ef17d-159">标识符类型：捆绑包 ID</span><span class="sxs-lookup"><span data-stu-id="ef17d-159">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="ef17d-160">代码要求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="ef17d-160">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="ef17d-161">网络扩展策略</span><span class="sxs-lookup"><span data-stu-id="ef17d-161">Network extension policy</span></span>

<span data-ttu-id="ef17d-162">作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="ef17d-162">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="ef17d-163">以下策略允许网络扩展执行此功能。</span><span class="sxs-lookup"><span data-stu-id="ef17d-163">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="ef17d-164">筛选器类型：插件</span><span class="sxs-lookup"><span data-stu-id="ef17d-164">Filter type: Plugin</span></span>
- <span data-ttu-id="ef17d-165">插件捆绑包标识符： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="ef17d-165">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="ef17d-166">筛选数据提供程序捆绑包标识符： `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="ef17d-166">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="ef17d-167">筛选数据提供程序指定的要求： `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="ef17d-167">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="ef17d-168">筛选器套接字： `true`</span><span class="sxs-lookup"><span data-stu-id="ef17d-168">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="ef17d-169">检查安装状态</span><span class="sxs-lookup"><span data-stu-id="ef17d-169">Check installation status</span></span>

<span data-ttu-id="ef17d-170">在 [客户端设备上运行 Microsoft Defender for Endpoint](mac-install-with-jamf.md) 以检查载入状态。</span><span class="sxs-lookup"><span data-stu-id="ef17d-170">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
