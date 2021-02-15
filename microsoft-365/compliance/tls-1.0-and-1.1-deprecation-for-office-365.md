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
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233094"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="b1b03-103">禁用 Microsoft 365 的 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="b1b03-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1b03-104">由于 COVID-19，我们暂时停止对商业客户禁用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="b1b03-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="b1b03-105">随着供应链进行调整，并且某些国家/地区开放备份，我们在 2020 年 10 月 15 日重新启动了 TLS 1.2 强制推出。</span><span class="sxs-lookup"><span data-stu-id="b1b03-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="b1b03-106">推出将持续几周和几个月。</span><span class="sxs-lookup"><span data-stu-id="b1b03-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="b1b03-107">自 2018 年 10 月 31 日起，Microsoft 365 服务已弃用传输层安全性 (TLS) 1.0 和 1.1 协议。</span><span class="sxs-lookup"><span data-stu-id="b1b03-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="b1b03-108">对最终用户的影响很小。</span><span class="sxs-lookup"><span data-stu-id="b1b03-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="b1b03-109">此更改已公布两年，2017 年 12 月发布第一个公开声明。</span><span class="sxs-lookup"><span data-stu-id="b1b03-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="b1b03-110">本文仅用于介绍与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。</span><span class="sxs-lookup"><span data-stu-id="b1b03-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="b1b03-111">对于 SharePoint 和 OneDrive，需要更新和配置 .NET 以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="b1b03-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="b1b03-112">有关信息，请参阅[如何在客户端上启用 TLS 1.2。](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="b1b03-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="b1b03-113">Office 365 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="b1b03-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="b1b03-114">Office 客户端依赖 Windows Web 服务 (WINHTTP) 通过 TLS 协议发送和接收流量。</span><span class="sxs-lookup"><span data-stu-id="b1b03-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="b1b03-115">如果本地计算机的 Web 服务可以使用 TLS 1.2，Office 客户端可以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="b1b03-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="b1b03-116">所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议是操作系统的一部分，不特定于 Office 客户端。</span><span class="sxs-lookup"><span data-stu-id="b1b03-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="b1b03-117">在 Windows 8 和更高版本上</span><span class="sxs-lookup"><span data-stu-id="b1b03-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="b1b03-118">默认情况下，如果没有将网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和 1.1 协议可用。</span><span class="sxs-lookup"><span data-stu-id="b1b03-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="b1b03-119">在 Windows 7 上</span><span class="sxs-lookup"><span data-stu-id="b1b03-119">On Windows 7</span></span>

<span data-ttu-id="b1b03-120">没有 [KB 3140245 更新，TLS 1.1 和 1.2](https://support.microsoft.com/help/3140245) 协议不可用。</span><span class="sxs-lookup"><span data-stu-id="b1b03-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="b1b03-121">更新可解决此问题并添加以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="b1b03-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="b1b03-122">自 2018 年 10 月 31 日起，没有此更新的 Windows 7 用户会受到影响。</span><span class="sxs-lookup"><span data-stu-id="b1b03-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="b1b03-123">[KB 3140245](https://support.microsoft.com/help/3140245) 详细介绍了如何更改 WINHTTP 设置以启用 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="b1b03-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="b1b03-124">更多信息</span><span class="sxs-lookup"><span data-stu-id="b1b03-124">More information</span></span>

<span data-ttu-id="b1b03-125">KB 文章 **介绍的 DefaultSecureProtocols** 注册表项的值决定了可以使用哪些网络协议：</span><span class="sxs-lookup"><span data-stu-id="b1b03-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="b1b03-126">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="b1b03-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="b1b03-127">协议已启用</span><span class="sxs-lookup"><span data-stu-id="b1b03-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="b1b03-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="b1b03-128">0x00000008</span></span>|<span data-ttu-id="b1b03-129">默认情况下启用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="b1b03-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="b1b03-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="b1b03-130">0x00000020</span></span>|<span data-ttu-id="b1b03-131">默认情况下启用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="b1b03-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="b1b03-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="b1b03-132">0x00000080</span></span>|<span data-ttu-id="b1b03-133">默认情况下启用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="b1b03-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="b1b03-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="b1b03-134">0x00000200</span></span>|<span data-ttu-id="b1b03-135">默认情况下启用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="b1b03-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="b1b03-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="b1b03-136">0x00000800</span></span>|<span data-ttu-id="b1b03-137">默认情况下启用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b1b03-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="b1b03-138">Office 客户端和 TLS 注册表项</span><span class="sxs-lookup"><span data-stu-id="b1b03-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="b1b03-139">你可以参考[KB 4057306 准备在 Office 365 中强制使用 TLS 1.2。](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="b1b03-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="b1b03-140">这是一篇适用于 IT 管理员的常规文章，它是有关 TLS 1.2 更改的官方文档。</span><span class="sxs-lookup"><span data-stu-id="b1b03-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="b1b03-141">下表显示了 2018 年 10 月 31 日之后 Office 365 客户端中的相应注册表项值。</span><span class="sxs-lookup"><span data-stu-id="b1b03-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="b1b03-142">2018 年 10 月 31 日之后为 Office 365 服务启用的协议</span><span class="sxs-lookup"><span data-stu-id="b1b03-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="b1b03-143">十六进制值</span><span class="sxs-lookup"><span data-stu-id="b1b03-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="b1b03-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="b1b03-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="b1b03-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="b1b03-145">0x00000A80</span></span>|
|<span data-ttu-id="b1b03-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="b1b03-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="b1b03-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="b1b03-147">0x00000A00</span></span>|
|<span data-ttu-id="b1b03-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="b1b03-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="b1b03-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="b1b03-149">0x00000880</span></span>|
|<span data-ttu-id="b1b03-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b1b03-150">TLS 1.2</span></span>|<span data-ttu-id="b1b03-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="b1b03-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="b1b03-152">请勿使用 SSL 2.0 和 3.0 协议，这两种协议也可使用 **DefaultSecureProtocols** 密钥进行设置。</span><span class="sxs-lookup"><span data-stu-id="b1b03-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="b1b03-153">SSL 2.0 和 3.0 被视为过时的不安全协议。</span><span class="sxs-lookup"><span data-stu-id="b1b03-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="b1b03-154">最佳做法是结束 SSL 2.0 和 SSL 3.0 的使用，尽管最终决定这样做取决于最能满足产品需求的产品。</span><span class="sxs-lookup"><span data-stu-id="b1b03-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="b1b03-155">有关 SSL 3.0 漏洞详细信息，请参阅 [KB 3009008](https://support.microsoft.com/help/3009008)。</span><span class="sxs-lookup"><span data-stu-id="b1b03-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="b1b03-156">可以在编程模式下使用默认的 Windows 计算器来设置相同的引用注册表项值。</span><span class="sxs-lookup"><span data-stu-id="b1b03-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="b1b03-157">有关详细信息，请参阅 [KB 3140245 更新以在 Windows 的 WinHTTP 中启用 TLS 1.1 和 TLS 1.2](https://support.microsoft.com/help/3140245)作为默认安全协议。</span><span class="sxs-lookup"><span data-stu-id="b1b03-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="b1b03-158">无论是否安装了 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) ，DefaultSecureProtocols 注册表子项都不存在，必须手动或通过组策略对象 (GPO) 添加。</span><span class="sxs-lookup"><span data-stu-id="b1b03-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="b1b03-159">也就是说，除非必须自定义启用或限制哪些安全协议，否则不需要此密钥。</span><span class="sxs-lookup"><span data-stu-id="b1b03-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="b1b03-160">你只需 Windows 7 SP1 ([KB 3140245) ](https://support.microsoft.com/help/3140245) 更新。</span><span class="sxs-lookup"><span data-stu-id="b1b03-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="b1b03-161">更新和配置 .NET Framework 以支持 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b1b03-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="b1b03-162">你需要更新通过 TLS 1.0 或 TLS 1.1 调用 Microsoft 365 API 的应用程序以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="b1b03-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="b1b03-163">.NET 4.5 默认为 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="b1b03-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="b1b03-164">若要更新 .NET 配置，请参阅如何在客户端上启用传输层安全性 (TLS) [1.2。](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="b1b03-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="b1b03-165">更多信息</span><span class="sxs-lookup"><span data-stu-id="b1b03-165">More information</span></span>

<span data-ttu-id="b1b03-166">有关详细信息，请参阅准备在 Office 365 中强制使用[TLS 1.2。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="b1b03-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
