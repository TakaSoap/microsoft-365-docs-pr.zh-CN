---
title: 禁用 Microsoft 365 的 TLS 1.0 和 1.1
description: 介绍 Microsoft 365 的 TLS 1.0 和 1.1 弃用和禁用。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332674"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="6214f-103">禁用 Microsoft 365 的 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="6214f-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6214f-104">由于 COVID-19，我们暂时停止对商业客户禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="6214f-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="6214f-105">由于供应链已进行调整，并且某些国家/地区开始备份，我们在 2020 年 10 月 15 日重新启动了 TLS 1.2 强制推出。</span><span class="sxs-lookup"><span data-stu-id="6214f-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="6214f-106">部署将持续几周和几个月。</span><span class="sxs-lookup"><span data-stu-id="6214f-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="6214f-107">自 2018 年 10 月 31 日起，Microsoft 365 服务已弃用传输层安全性 (TLS) 1.0 和 1.1 协议。</span><span class="sxs-lookup"><span data-stu-id="6214f-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="6214f-108">对最终用户的影响很小。</span><span class="sxs-lookup"><span data-stu-id="6214f-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="6214f-109">此更改已公布两年以上，2017 年 12 月发布第一个公开通知。</span><span class="sxs-lookup"><span data-stu-id="6214f-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="6214f-110">本文仅用于介绍与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。</span><span class="sxs-lookup"><span data-stu-id="6214f-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="6214f-111">对于 SharePoint 和 OneDrive，需要更新和配置 .NET 以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="6214f-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="6214f-112">有关信息，请参阅[如何在客户端上启用 TLS 1.2。](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="6214f-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="6214f-113">Office 365 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="6214f-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="6214f-114">Office 客户端依赖 Windows Web 服务 (WINHTTP) TLS 协议发送和接收流量。</span><span class="sxs-lookup"><span data-stu-id="6214f-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="6214f-115">如果本地计算机的 Web 服务可以使用 TLS 1.2，Office 客户端可以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="6214f-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="6214f-116">所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议是操作系统的一部分，并不特定于 Office 客户端。</span><span class="sxs-lookup"><span data-stu-id="6214f-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="6214f-117">在 Windows 8 和更高版本上</span><span class="sxs-lookup"><span data-stu-id="6214f-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="6214f-118">默认情况下，如果没有将网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和 1.1 协议可用。</span><span class="sxs-lookup"><span data-stu-id="6214f-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="6214f-119">在 Windows 7 上</span><span class="sxs-lookup"><span data-stu-id="6214f-119">On Windows 7</span></span>

<span data-ttu-id="6214f-120">没有 [KB 3140245 更新，TLS 1.1 和 1.2 协议不可用](https://support.microsoft.com/help/3140245) 。</span><span class="sxs-lookup"><span data-stu-id="6214f-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="6214f-121">更新可解决此问题并添加以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="6214f-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="6214f-122">自 2018 年 10 月 31 日起，没有此更新的 Windows 7 用户会受到影响。</span><span class="sxs-lookup"><span data-stu-id="6214f-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="6214f-123">[KB 3140245](https://support.microsoft.com/help/3140245) 详细介绍了如何更改 WINHTTP 设置以启用 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="6214f-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="6214f-124">更多信息</span><span class="sxs-lookup"><span data-stu-id="6214f-124">More information</span></span>

<span data-ttu-id="6214f-125">KB 文章介绍 **的 DefaultSecureProtocols** 注册表项的值决定了可以使用哪些网络协议：</span><span class="sxs-lookup"><span data-stu-id="6214f-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="6214f-126">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="6214f-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="6214f-127">协议已启用</span><span class="sxs-lookup"><span data-stu-id="6214f-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="6214f-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="6214f-128">0x00000008</span></span>|<span data-ttu-id="6214f-129">默认情况下启用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="6214f-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="6214f-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="6214f-130">0x00000020</span></span>|<span data-ttu-id="6214f-131">默认情况下启用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="6214f-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="6214f-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="6214f-132">0x00000080</span></span>|<span data-ttu-id="6214f-133">默认情况下启用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="6214f-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="6214f-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="6214f-134">0x00000200</span></span>|<span data-ttu-id="6214f-135">默认情况下启用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="6214f-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="6214f-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="6214f-136">0x00000800</span></span>|<span data-ttu-id="6214f-137">默认情况下启用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="6214f-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="6214f-138">Office 客户端和 TLS 注册表项</span><span class="sxs-lookup"><span data-stu-id="6214f-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="6214f-139">你可以参考[KB 4057306 准备在 Office 365 中强制使用 TLS 1.2。](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="6214f-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="6214f-140">这是一篇适用于 IT 管理员的常规文章，也是有关 TLS 1.2 更改的官方文档。</span><span class="sxs-lookup"><span data-stu-id="6214f-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="6214f-141">下表显示了 2018 年 10 月 31 日之后 Office 365 客户端中的相应注册表项值。</span><span class="sxs-lookup"><span data-stu-id="6214f-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="6214f-142">2018 年 10 月 31 日之后为 Office 365 服务启用的协议</span><span class="sxs-lookup"><span data-stu-id="6214f-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="6214f-143">十六进制值</span><span class="sxs-lookup"><span data-stu-id="6214f-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="6214f-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="6214f-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="6214f-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="6214f-145">0x00000A80</span></span>|
|<span data-ttu-id="6214f-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="6214f-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="6214f-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="6214f-147">0x00000A00</span></span>|
|<span data-ttu-id="6214f-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="6214f-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="6214f-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="6214f-149">0x00000880</span></span>|
|<span data-ttu-id="6214f-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="6214f-150">TLS 1.2</span></span>|<span data-ttu-id="6214f-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="6214f-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="6214f-152">请勿使用 SSL 2.0 和 3.0 协议，这两种协议也可使用 **DefaultSecureProtocols** 密钥进行设置。</span><span class="sxs-lookup"><span data-stu-id="6214f-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="6214f-153">SSL 2.0 和 3.0 被视为过时的不安全协议。</span><span class="sxs-lookup"><span data-stu-id="6214f-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="6214f-154">最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管最终决定使用哪一项最能满足你的产品需求。</span><span class="sxs-lookup"><span data-stu-id="6214f-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="6214f-155">有关 SSL 3.0 漏洞详细信息，请参阅[KB 3009008。](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="6214f-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="6214f-156">可以在程序员模式下使用默认的 Windows 计算器来设置相同的引用注册表项值。</span><span class="sxs-lookup"><span data-stu-id="6214f-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="6214f-157">有关详细信息，请参阅 [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245)。</span><span class="sxs-lookup"><span data-stu-id="6214f-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="6214f-158">无论是否安装了 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) ，DefaultSecureProtocols 注册表子项不存在，必须手动添加，或者必须通过组策略对象 (GPO) 添加。</span><span class="sxs-lookup"><span data-stu-id="6214f-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="6214f-159">也就是说，除非您必须自定义启用或限制哪些安全协议，否则不需要此密钥。</span><span class="sxs-lookup"><span data-stu-id="6214f-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="6214f-160">只需 Windows 7 SP1 ([KB 3140245) ](https://support.microsoft.com/help/3140245) 更新。</span><span class="sxs-lookup"><span data-stu-id="6214f-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="6214f-161">更新和配置.NET Framework TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="6214f-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="6214f-162">你需要通过 TLS 1.0 或 TLS 1.1 更新调用 Microsoft 365 API 的应用程序以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="6214f-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="6214f-163">.NET 4.5 默认为 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="6214f-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="6214f-164">若要更新 .NET 配置，请参阅如何在客户端上启用传输层安全性[ (TLS) 1.2。](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="6214f-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="6214f-165">更多信息</span><span class="sxs-lookup"><span data-stu-id="6214f-165">More information</span></span>

<span data-ttu-id="6214f-166">有关详细信息，请参阅准备在 Office 365 中强制使用[TLS 1.2。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6214f-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="references"></a><span data-ttu-id="6214f-167">参考</span><span class="sxs-lookup"><span data-stu-id="6214f-167">References</span></span>

<span data-ttu-id="6214f-168">以下资源提供指导，以帮助确保客户端使用的是 TLS 1.2 或更高版本，并禁用 TLS 1.0 和 1.1：</span><span class="sxs-lookup"><span data-stu-id="6214f-168">The following resources provide guidance to help make sure that your clients are using TLS 1.2 or a later version and to disable TLS 1.0 and 1.1:</span></span>

- <span data-ttu-id="6214f-169">对于连接到 Office 365 的 Windows 7 客户端，请确保 TLS 1.2 是 Windows WinHTTP 中的默认安全协议。</span><span class="sxs-lookup"><span data-stu-id="6214f-169">For Windows 7 clients that connect to Office 365, make sure that TLS 1.2 is the default secure protocol in WinHTTP in Windows.</span></span> <span data-ttu-id="6214f-170">有关详细信息，请参阅 [KB 3140245 - 更新以在 Windows 的 WinHTTP 中启用 TLS 1.1 和 TLS 1.2](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)作为默认安全协议。</span><span class="sxs-lookup"><span data-stu-id="6214f-170">For more information, see [KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).</span></span>
- <span data-ttu-id="6214f-171">若要通过删除 TLS 1.0 和 1.1 依赖项来解决弱 TLS 使用情况，请参阅 Microsoft 上的 [TLS 1.2 支持](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。</span><span class="sxs-lookup"><span data-stu-id="6214f-171">To address weak TLS usage by removing TLS 1.0 and 1.1 dependencies, see [TLS 1.2 support at Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).</span></span>
- <span data-ttu-id="6214f-172">[新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)可更加方便地在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上查找通过使用弱安全协议连接服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="6214f-172">[New IIS functionality](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) makes it easier to find clients on [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) and [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) that connect to the service by using weak security protocols.</span></span>
- <span data-ttu-id="6214f-173">获取有关如何解决 [TLS 1.0 问题的信息](https://www.microsoft.com/download/details.aspx?id=55266)。</span><span class="sxs-lookup"><span data-stu-id="6214f-173">Get more information about how to [solve the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>
- <span data-ttu-id="6214f-174">有关安全性方法的一般信息，请转到[Office 365 信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。</span><span class="sxs-lookup"><span data-stu-id="6214f-174">For general information about our approach to security, go to the [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).</span></span>
- [<span data-ttu-id="6214f-175">准备 TLS 1.0/1.1 弃用 - Office 365 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6214f-175">Preparing for TLS 1.0/1.1 Deprecation - Office 365 Skype for Business</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [<span data-ttu-id="6214f-176">Exchange Server TLS 指南，第 1 部分：为 TLS 1.2 做好准备</span><span class="sxs-lookup"><span data-stu-id="6214f-176">Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [<span data-ttu-id="6214f-177">Exchange Server TLS 指南，第 2 部分：启用 TLS 1.2 并识别不使用它的客户端</span><span class="sxs-lookup"><span data-stu-id="6214f-177">Exchange Server TLS guidance Part 2: Enabling TLS 1.2 and Identifying Clients Not Using It</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [<span data-ttu-id="6214f-178">Exchange Server TLS 指南，第 3 部分：关闭 TLS 1.0/1.1</span><span class="sxs-lookup"><span data-stu-id="6214f-178">Exchange Server TLS guidance Part 3: Turning Off TLS 1.0/1.1</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [<span data-ttu-id="6214f-179">在 Office Online Server 中启用 TLS 1.1 和 TLS 1.2 支持</span><span class="sxs-lookup"><span data-stu-id="6214f-179">Enable TLS 1.1 and TLS 1.2 support in Office Online Server</span></span>](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

