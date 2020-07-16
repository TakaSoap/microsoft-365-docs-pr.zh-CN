---
title: Office 365 的 TLS 1.0 和 1.1 停用
description: 介绍了 Office 365 的 TLS 1.0 和1.1 弃用情况。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 270d04974cec9c36fa31a77bda401375fdac0471
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148144"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="b9d2b-103">Office 365 的 TLS 1.0 和 1.1 停用</span><span class="sxs-lookup"><span data-stu-id="b9d2b-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="b9d2b-104">由于 covid-19，我们暂时停止了针对商业客户的过时强制执行的 TLS 1.0 和1.1，但由于提供链已调整，而某些国家/地区已重新打开，我们正在将 TLS 强制重置为开始 Oct 15、2020。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to covid-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to start Oct 15, 2020.</span></span> 

<span data-ttu-id="b9d2b-105">从2018年10月31日起，Office 365 服务的传输层安全性（TLS）1.0 和1.1 协议已被弃用。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="b9d2b-106">最终用户的效果应最小。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="b9d2b-107">此更改已在两年的时间内公布，第一次公开发布在12月2017。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="b9d2b-108">本文仅用于涵盖与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="b9d2b-109">Office 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="b9d2b-109">Office and TLS overview</span></span>

<span data-ttu-id="b9d2b-110">Office 客户端依赖于 Windows web 服务（WINHTTP）以通过 TLS 协议发送和接收通信。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="b9d2b-111">如果本地计算机的 web 服务可以使用 TLS 1.2，则 Office 客户端可以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="b9d2b-112">所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议都是操作系统的一部分，而不是特定于 Office 客户端的。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="b9d2b-113">在 Windows 8 和更高版本上</span><span class="sxs-lookup"><span data-stu-id="b9d2b-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="b9d2b-114">默认情况下，如果没有网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和1.1 协议可用。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="b9d2b-115">在 Windows 7 上</span><span class="sxs-lookup"><span data-stu-id="b9d2b-115">On Windows 7</span></span>

<span data-ttu-id="b9d2b-116">如果没有[KB 3140245](https://support.microsoft.com/help/3140245)更新，TLS 1.1 和1.2 协议将不可用。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="b9d2b-117">更新解决了此问题，并添加了以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="b9d2b-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="b9d2b-118">在2018年10月31日之前，不具有此更新的 Windows 7 用户将受到影响。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="b9d2b-119">[KB 3140245](https://support.microsoft.com/help/3140245)包含有关如何更改 WINHTTP 设置以启用 TLS 协议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="b9d2b-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="b9d2b-120">More information</span></span>

<span data-ttu-id="b9d2b-121">知识库文章描述的**DefaultSecureProtocols**注册表项的值决定了可以使用的网络协议：</span><span class="sxs-lookup"><span data-stu-id="b9d2b-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="b9d2b-122">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="b9d2b-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="b9d2b-123">启用协议</span><span class="sxs-lookup"><span data-stu-id="b9d2b-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="b9d2b-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="b9d2b-124">0x00000008</span></span>|<span data-ttu-id="b9d2b-125">默认情况下启用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="b9d2b-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="b9d2b-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="b9d2b-126">0x00000020</span></span>|<span data-ttu-id="b9d2b-127">默认情况下启用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="b9d2b-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="b9d2b-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="b9d2b-128">0x00000080</span></span>|<span data-ttu-id="b9d2b-129">默认情况下启用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="b9d2b-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="b9d2b-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="b9d2b-130">0x00000200</span></span>|<span data-ttu-id="b9d2b-131">默认情况下启用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="b9d2b-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="b9d2b-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="b9d2b-132">0x00000800</span></span>|<span data-ttu-id="b9d2b-133">默认情况下启用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b9d2b-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="b9d2b-134">Office 客户端和 TLS 注册表项</span><span class="sxs-lookup"><span data-stu-id="b9d2b-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="b9d2b-135">您可以参考[KB 4057306，准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306)。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="b9d2b-136">这是针对 IT 管理员的一般性文章，它是有关 TLS 1.2 更改的正式文档。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="b9d2b-137">下表显示了在2018年10月31日之后 Office 365 客户端中相应的注册表项值。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="b9d2b-138">在2018年10月31日之后启用了 Office 365 服务协议</span><span class="sxs-lookup"><span data-stu-id="b9d2b-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="b9d2b-139">十六进制值</span><span class="sxs-lookup"><span data-stu-id="b9d2b-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="b9d2b-140">TLS 1.0 + 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="b9d2b-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="b9d2b-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="b9d2b-141">0x00000A80</span></span>|
|<span data-ttu-id="b9d2b-142">TLS 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="b9d2b-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="b9d2b-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="b9d2b-143">0x00000A00</span></span>|
|<span data-ttu-id="b9d2b-144">TLS 1.0 + 1。2</span><span class="sxs-lookup"><span data-stu-id="b9d2b-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="b9d2b-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="b9d2b-145">0x00000880</span></span>|
|<span data-ttu-id="b9d2b-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b9d2b-146">TLS 1.2</span></span>|<span data-ttu-id="b9d2b-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="b9d2b-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="b9d2b-148">我们建议您不要使用 SSL 2.0 和3.0 协议，也可以使用**DefaultSecureProtocols**项进行设置。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="b9d2b-149">SSL 2.0 和3.0 被视为已弃用的协议。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="b9d2b-150">最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管执行此操作的决策最终取决于最符合您的产品需求的决策。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="b9d2b-151">有关 SSL 3.0 漏洞的详细信息，请参阅[KB 3009008](https://support.microsoft.com/help/3009008)。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="b9d2b-152">您可以使用程序员模式下的默认 Windows 计算器设置相同的引用注册表项值。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="b9d2b-153">有关详细信息，请参阅[KB 3140245 更新以将 tls 1.1 和 tls 1.2 启用为 Windows 中 WinHTTP 中的默认安全协议](https://support.microsoft.com/help/3140245)。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="b9d2b-154">无论是否安装了 Windows 7 更新（[KB 3140245](https://support.microsoft.com/help/3140245)），DefaultSecureProtocols 注册表子项都不存在，必须手动添加或通过组策略对象（GPO）添加。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="b9d2b-155">也就是说，除非您必须自定义启用或限制的安全协议，否则此键不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="b9d2b-156">您只需要 Windows 7 SP1 （[KB 3140245](https://support.microsoft.com/help/3140245)）更新。</span><span class="sxs-lookup"><span data-stu-id="b9d2b-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
