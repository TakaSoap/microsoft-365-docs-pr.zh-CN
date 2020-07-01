---
title: Office 365 的 TLS 1.0 和1.1 弃用
description: 介绍了 Office 365 的 TLS 1.0 和1.1 弃用情况。
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937320"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="eebc3-103">Office 365 的 TLS 1.0 和1.1 弃用</span><span class="sxs-lookup"><span data-stu-id="eebc3-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>

<span data-ttu-id="eebc3-104">从2018年10月31日起，Office 365 服务的传输层安全性（TLS）1.0 和1.1 协议已被弃用。</span><span class="sxs-lookup"><span data-stu-id="eebc3-104">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="eebc3-105">最终用户的效果应最小。</span><span class="sxs-lookup"><span data-stu-id="eebc3-105">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="eebc3-106">此更改可在将近两年的时间内公布，在12月2017日宣布推出首次公开通知。</span><span class="sxs-lookup"><span data-stu-id="eebc3-106">This change was publicized for almost two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="eebc3-107">本文仅用于涵盖与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。</span><span class="sxs-lookup"><span data-stu-id="eebc3-107">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="eebc3-108">Office 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="eebc3-108">Office and TLS overview</span></span>

<span data-ttu-id="eebc3-109">Office 客户端依赖于 Windows web 服务（WINHTTP）以通过 TLS 协议发送和接收通信。</span><span class="sxs-lookup"><span data-stu-id="eebc3-109">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="eebc3-110">如果本地计算机的 web 服务可以使用 TLS 1.2，则 Office 客户端可以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="eebc3-110">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="eebc3-111">所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议都是操作系统的一部分，而不是特定于 Office 客户端的。</span><span class="sxs-lookup"><span data-stu-id="eebc3-111">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="eebc3-112">在 Windows 8 和更高版本上</span><span class="sxs-lookup"><span data-stu-id="eebc3-112">On Windows 8 and later versions</span></span>

<span data-ttu-id="eebc3-113">默认情况下，如果没有网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和1.1 协议可用。</span><span class="sxs-lookup"><span data-stu-id="eebc3-113">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="eebc3-114">在 Windows 7 上</span><span class="sxs-lookup"><span data-stu-id="eebc3-114">On Windows 7</span></span>

<span data-ttu-id="eebc3-115">如果没有[KB 3140245](https://support.microsoft.com/help/3140245)更新，TLS 1.1 和1.2 协议将不可用。</span><span class="sxs-lookup"><span data-stu-id="eebc3-115">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="eebc3-116">更新解决了此问题，并添加了以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="eebc3-116">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="eebc3-117">在2018年10月31日之前，不具有此更新的 Windows 7 用户将受到影响。</span><span class="sxs-lookup"><span data-stu-id="eebc3-117">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="eebc3-118">[KB 3140245](https://support.microsoft.com/help/3140245)包含有关如何更改 WINHTTP 设置以启用 TLS 协议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eebc3-118">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="eebc3-119">更多信息</span><span class="sxs-lookup"><span data-stu-id="eebc3-119">More information</span></span>

<span data-ttu-id="eebc3-120">知识库文章描述的**DefaultSecureProtocols**注册表项的值决定了可以使用的网络协议：</span><span class="sxs-lookup"><span data-stu-id="eebc3-120">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="eebc3-121">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="eebc3-121">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="eebc3-122">启用协议</span><span class="sxs-lookup"><span data-stu-id="eebc3-122">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="eebc3-123">0x00000008</span><span class="sxs-lookup"><span data-stu-id="eebc3-123">0x00000008</span></span>|<span data-ttu-id="eebc3-124">默认情况下启用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="eebc3-124">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="eebc3-125">0x00000020</span><span class="sxs-lookup"><span data-stu-id="eebc3-125">0x00000020</span></span>|<span data-ttu-id="eebc3-126">默认情况下启用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="eebc3-126">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="eebc3-127">0x00000080</span><span class="sxs-lookup"><span data-stu-id="eebc3-127">0x00000080</span></span>|<span data-ttu-id="eebc3-128">默认情况下启用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="eebc3-128">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="eebc3-129">0x00000200</span><span class="sxs-lookup"><span data-stu-id="eebc3-129">0x00000200</span></span>|<span data-ttu-id="eebc3-130">默认情况下启用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="eebc3-130">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="eebc3-131">0x00000800</span><span class="sxs-lookup"><span data-stu-id="eebc3-131">0x00000800</span></span>|<span data-ttu-id="eebc3-132">默认情况下启用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="eebc3-132">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="eebc3-133">Office 客户端和 TLS 注册表项</span><span class="sxs-lookup"><span data-stu-id="eebc3-133">Office clients and TLS registry keys</span></span>

<span data-ttu-id="eebc3-134">您可以参考[KB 4057306，准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306)。</span><span class="sxs-lookup"><span data-stu-id="eebc3-134">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="eebc3-135">这是针对 IT 管理员的一般性文章，它是有关 TLS 1.2 更改的正式文档。</span><span class="sxs-lookup"><span data-stu-id="eebc3-135">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="eebc3-136">下表显示了在2018年10月31日之后 Office 365 客户端中相应的注册表项值。</span><span class="sxs-lookup"><span data-stu-id="eebc3-136">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="eebc3-137">在2018年10月31日之后启用了 Office 365 服务协议</span><span class="sxs-lookup"><span data-stu-id="eebc3-137">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="eebc3-138">十六进制值</span><span class="sxs-lookup"><span data-stu-id="eebc3-138">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="eebc3-139">TLS 1.0 + 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="eebc3-139">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="eebc3-140">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="eebc3-140">0x00000A80</span></span>|
|<span data-ttu-id="eebc3-141">TLS 1.1 + 1。2</span><span class="sxs-lookup"><span data-stu-id="eebc3-141">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="eebc3-142">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="eebc3-142">0x00000A00</span></span>|
|<span data-ttu-id="eebc3-143">TLS 1.0 + 1。2</span><span class="sxs-lookup"><span data-stu-id="eebc3-143">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="eebc3-144">0x00000880</span><span class="sxs-lookup"><span data-stu-id="eebc3-144">0x00000880</span></span>|
|<span data-ttu-id="eebc3-145">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="eebc3-145">TLS 1.2</span></span>|<span data-ttu-id="eebc3-146">0x00000800</span><span class="sxs-lookup"><span data-stu-id="eebc3-146">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="eebc3-147">我们建议您不要使用 SSL 2.0 和3.0 协议，也可以使用**DefaultSecureProtocols**项进行设置。</span><span class="sxs-lookup"><span data-stu-id="eebc3-147">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="eebc3-148">SSL 2.0 和3.0 被视为已弃用的协议。</span><span class="sxs-lookup"><span data-stu-id="eebc3-148">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="eebc3-149">最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管执行此操作的决策最终取决于最符合您的产品需求的决策。</span><span class="sxs-lookup"><span data-stu-id="eebc3-149">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="eebc3-150">有关 SSL 3.0 漏洞的详细信息，请参阅[KB 3009008](https://support.microsoft.com/help/3009008)。</span><span class="sxs-lookup"><span data-stu-id="eebc3-150">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="eebc3-151">您可以使用程序员模式下的默认 Windows 计算器设置相同的引用注册表项值。</span><span class="sxs-lookup"><span data-stu-id="eebc3-151">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="eebc3-152">有关详细信息，请参阅[KB 3140245 更新以将 tls 1.1 和 tls 1.2 启用为 Windows 中 WinHTTP 中的默认安全协议](https://support.microsoft.com/help/3140245)。</span><span class="sxs-lookup"><span data-stu-id="eebc3-152">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="eebc3-153">无论是否安装了 Windows 7 更新（[KB 3140245](https://support.microsoft.com/help/3140245)），DefaultSecureProtocols 注册表子项都不存在，必须手动添加或通过组策略对象（GPO）添加。</span><span class="sxs-lookup"><span data-stu-id="eebc3-153">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="eebc3-154">也就是说，除非您必须自定义启用或限制的安全协议，否则此键不是必需的。</span><span class="sxs-lookup"><span data-stu-id="eebc3-154">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="eebc3-155">您只需要 Windows 7 SP1 （[KB 3140245](https://support.microsoft.com/help/3140245)）更新。</span><span class="sxs-lookup"><span data-stu-id="eebc3-155">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
