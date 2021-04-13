---
title: Mac 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 了解如何在 Mac 上安装、配置、更新和使用 Microsoft Defender for Endpoint。
keywords: microsoft， defender， atp， mac， 安装， 部署， 卸载， intune， jamf， macos， big sur， catalina， mojave， mde for mac
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
ms.openlocfilehash: 406a0e699ea563670f41355d122aa54ba8667a0e
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687741"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="f84ce-104">Mac 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f84ce-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f84ce-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f84ce-105">**Applies to:**</span></span>
- [<span data-ttu-id="f84ce-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f84ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f84ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f84ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f84ce-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f84ce-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f84ce-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f84ce-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f84ce-110">本主题介绍如何在 Mac 上安装、配置、更新和使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f84ce-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="f84ce-111">在 Mac 上的 Microsoft Defender for Endpoint 旁边运行其他第三方终结点保护产品可能会导致性能问题和不可预知的副作用。</span><span class="sxs-lookup"><span data-stu-id="f84ce-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="f84ce-112">如果非 Microsoft 终结点保护在你的环境中是绝对要求，在将防病毒功能配置为在被动模式下运行后，你仍然可以安全地利用 Mac EDR 上的 Defender for Endpoint [功能](mac-preferences.md#enable--disable-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="f84ce-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="f84ce-113">最新版本的新增功能</span><span class="sxs-lookup"><span data-stu-id="f84ce-113">What’s new in the latest release</span></span>

[<span data-ttu-id="f84ce-114">Microsoft Defender for Endpoint 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="f84ce-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="f84ce-115">Mac 上的 Microsoft Defender for Endpoint 的新增功能</span><span class="sxs-lookup"><span data-stu-id="f84ce-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="f84ce-116">如果你有任何要共享的反馈，请通过在你的设备上打开 Mac 上的 Microsoft Defender for Endpoint 并导航到"帮助发送反馈"来  >  **提交它**。</span><span class="sxs-lookup"><span data-stu-id="f84ce-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="f84ce-117">若要获取最新功能（包括预览功能 (如适用于 Mac 设备的终结点检测和响应) ，请配置运行 Microsoft Defender for Endpoint 的 macOS 设备作为"预览体验成员"设备。</span><span class="sxs-lookup"><span data-stu-id="f84ce-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="f84ce-118">如何在 Mac 上安装 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f84ce-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f84ce-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="f84ce-119">Prerequisites</span></span>

- <span data-ttu-id="f84ce-120">适用于终结点的 Defender 订阅和 Microsoft Defender 安全中心门户的访问权限</span><span class="sxs-lookup"><span data-stu-id="f84ce-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="f84ce-121">macOS 和 BASH 脚本的初学者级体验</span><span class="sxs-lookup"><span data-stu-id="f84ce-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="f84ce-122">手动部署时，设备上 (管理权限) </span><span class="sxs-lookup"><span data-stu-id="f84ce-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="f84ce-123">安装说明</span><span class="sxs-lookup"><span data-stu-id="f84ce-123">Installation instructions</span></span>

<span data-ttu-id="f84ce-124">可以使用多种方法和部署工具在 Mac 上安装和配置 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f84ce-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="f84ce-125">第三方管理工具：</span><span class="sxs-lookup"><span data-stu-id="f84ce-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="f84ce-126">基于 Microsoft Intune 的部署</span><span class="sxs-lookup"><span data-stu-id="f84ce-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="f84ce-127">基于 JAMF 的部署</span><span class="sxs-lookup"><span data-stu-id="f84ce-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="f84ce-128">其他 MDM 产品</span><span class="sxs-lookup"><span data-stu-id="f84ce-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="f84ce-129">命令行工具：</span><span class="sxs-lookup"><span data-stu-id="f84ce-129">Command-line tool:</span></span>
    - [<span data-ttu-id="f84ce-130">手动部署</span><span class="sxs-lookup"><span data-stu-id="f84ce-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="f84ce-131">系统要求</span><span class="sxs-lookup"><span data-stu-id="f84ce-131">System requirements</span></span>

<span data-ttu-id="f84ce-132">支持 macOS 的三个最新主要版本。</span><span class="sxs-lookup"><span data-stu-id="f84ce-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f84ce-133">在 macOS 11 (Sur) 上，Microsoft Defender for Endpoint 需要额外的配置文件。</span><span class="sxs-lookup"><span data-stu-id="f84ce-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="f84ce-134">如果你是从 macOS 早期版本升级的现有客户，请确保部署 [macOS Catalina](mac-sysext-policies.md)的新配置文件和较新版本的 macOS 中列出的其他配置文件。</span><span class="sxs-lookup"><span data-stu-id="f84ce-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f84ce-135">截至 2021 年 2 月 15 (对) MacOS 10.13) 的支持已终止。</span><span class="sxs-lookup"><span data-stu-id="f84ce-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="f84ce-136">11 (大) ，10.15 (加泰罗尼亚语) ，10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="f84ce-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="f84ce-137">磁盘空间：1GB</span><span class="sxs-lookup"><span data-stu-id="f84ce-137">Disk space: 1GB</span></span>

<span data-ttu-id="f84ce-138">不支持 macOS 的 Beta 版本。</span><span class="sxs-lookup"><span data-stu-id="f84ce-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="f84ce-139">启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。</span><span class="sxs-lookup"><span data-stu-id="f84ce-139">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="f84ce-140">许可要求</span><span class="sxs-lookup"><span data-stu-id="f84ce-140">Licensing requirements</span></span>

<span data-ttu-id="f84ce-141">Mac 上的 Microsoft Defender for Endpoint 需要以下 Microsoft 批量许可产品/服务之一：</span><span class="sxs-lookup"><span data-stu-id="f84ce-141">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="f84ce-142">Microsoft 365 E5 (M365 E5) </span><span class="sxs-lookup"><span data-stu-id="f84ce-142">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="f84ce-143">Microsoft 365 E5 安全版</span><span class="sxs-lookup"><span data-stu-id="f84ce-143">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="f84ce-144">Microsoft 365 A5 (M365 A5) </span><span class="sxs-lookup"><span data-stu-id="f84ce-144">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="f84ce-145">符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f84ce-145">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="f84ce-146">Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (云解决方案提供商) 。</span><span class="sxs-lookup"><span data-stu-id="f84ce-146">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="f84ce-147">通过云解决方案提供商购买时，不需要列出 Microsoft 批量许可产品/服务。</span><span class="sxs-lookup"><span data-stu-id="f84ce-147">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="f84ce-148">网络连接</span><span class="sxs-lookup"><span data-stu-id="f84ce-148">Network connections</span></span>

<span data-ttu-id="f84ce-149">以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。</span><span class="sxs-lookup"><span data-stu-id="f84ce-149">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="f84ce-150">应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。 </span><span class="sxs-lookup"><span data-stu-id="f84ce-150">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="f84ce-151">**域列表电子表格**</span><span class="sxs-lookup"><span data-stu-id="f84ce-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="f84ce-152">**Description**</span><span class="sxs-lookup"><span data-stu-id="f84ce-152">**Description**</span></span>|
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | <span data-ttu-id="f84ce-154">服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。</span><span class="sxs-lookup"><span data-stu-id="f84ce-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="f84ce-155">在此处下载[电子表格：mdatp-urls.xlsx。 ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="f84ce-155">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="f84ce-156">Microsoft Defender for Endpoint 可以通过以下发现方法发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="f84ce-156">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="f84ce-157">PAC (代理) </span><span class="sxs-lookup"><span data-stu-id="f84ce-157">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="f84ce-158">Web 代理自动发现协议 (WPAD) </span><span class="sxs-lookup"><span data-stu-id="f84ce-158">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="f84ce-159">手动静态代理配置</span><span class="sxs-lookup"><span data-stu-id="f84ce-159">Manual static proxy configuration</span></span>

<span data-ttu-id="f84ce-160">如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="f84ce-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="f84ce-161">不支持经过身份验证的代理。</span><span class="sxs-lookup"><span data-stu-id="f84ce-161">Authenticated proxies are not supported.</span></span> <span data-ttu-id="f84ce-162">确保仅使用 PAC、WPAD 或静态代理。</span><span class="sxs-lookup"><span data-stu-id="f84ce-162">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="f84ce-163">出于安全考虑，也不支持 SSL 检查和截获代理。</span><span class="sxs-lookup"><span data-stu-id="f84ce-163">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="f84ce-164">为 SSL 检查和代理服务器配置例外，以将数据从 macOS 上的 Microsoft Defender for Endpoint 直接传递到相关 URL，而不会拦截。</span><span class="sxs-lookup"><span data-stu-id="f84ce-164">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="f84ce-165">将拦截证书添加到全局存储将不允许拦截。</span><span class="sxs-lookup"><span data-stu-id="f84ce-165">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="f84ce-166">若要测试连接是否未阻止，请打开 [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) ，在浏览器中打开。</span><span class="sxs-lookup"><span data-stu-id="f84ce-166">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="f84ce-167">如果您更喜欢命令行，还可以在终端中运行以下命令来检查连接：</span><span class="sxs-lookup"><span data-stu-id="f84ce-167">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="f84ce-168">此命令的输出应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="f84ce-168">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="f84ce-169">建议在客户端设备上保持 [启用 (](https://support.apple.com/en-us/HT204899) SIP) 系统完整性保护。</span><span class="sxs-lookup"><span data-stu-id="f84ce-169">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="f84ce-170">SIP 是内置的 macOS 安全功能，可防止对操作系统进行低级篡改，并且默认启用。</span><span class="sxs-lookup"><span data-stu-id="f84ce-170">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="f84ce-171">安装 Microsoft Defender for Endpoint 后，可通过在终端中运行以下命令来验证连接性：</span><span class="sxs-lookup"><span data-stu-id="f84ce-171">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="f84ce-172">如何在 Mac 上更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f84ce-172">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="f84ce-173">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="f84ce-173">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="f84ce-174">若要更新 Mac 上的 Microsoft Defender for Endpoint，使用名为 Microsoft AutoUpdate (MAU) 程序。</span><span class="sxs-lookup"><span data-stu-id="f84ce-174">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="f84ce-175">若要了解更多信息，请参阅 [在 Mac](mac-updates.md)上部署 Microsoft Defender for Endpoint 更新。</span><span class="sxs-lookup"><span data-stu-id="f84ce-175">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="f84ce-176">如何在 Mac 上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f84ce-176">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="f84ce-177">有关如何在企业环境中配置产品的指南可在在 Mac 上设置 [Microsoft Defender for Endpoint 的首选项中提供](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="f84ce-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="f84ce-178">macOS 内核和系统扩展</span><span class="sxs-lookup"><span data-stu-id="f84ce-178">macOS kernel and system extensions</span></span>

<span data-ttu-id="f84ce-179">为了与 macOS 演变保持一致，我们正在准备利用系统扩展而非内核扩展的 Mac 上的 Microsoft Defender for Endpoint 更新。</span><span class="sxs-lookup"><span data-stu-id="f84ce-179">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="f84ce-180">有关相关详细信息，请参阅 Mac 上的 [Microsoft Defender for Endpoint 中的新增功能](mac-whatsnew.md)。</span><span class="sxs-lookup"><span data-stu-id="f84ce-180">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="f84ce-181">资源</span><span class="sxs-lookup"><span data-stu-id="f84ce-181">Resources</span></span>

- <span data-ttu-id="f84ce-182">有关日志记录、卸载或其他主题的信息，请参阅 Mac 上的 [Microsoft Defender for Endpoint 的资源](mac-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="f84ce-182">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="f84ce-183">[Mac 上的 Microsoft Defender for Endpoint 的隐私](mac-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="f84ce-183">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
