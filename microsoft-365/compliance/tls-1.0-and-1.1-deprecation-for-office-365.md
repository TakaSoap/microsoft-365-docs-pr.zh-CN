---
title: Office 365 的 TLS 1.0 和 1.1 停用
description: 介绍 Office 365 的 TLS 1.0 和 1.1 弃用。
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
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777050"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="ed29f-103">Office 365 的 TLS 1.0 和 1.1 停用</span><span class="sxs-lookup"><span data-stu-id="ed29f-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="ed29f-104">由于 COVID-19，我们暂时停止了对商业客户实施 TLS 1.0 和 1.1 的弃用，但由于供应链已进行调整，并且某些国家/地区开始备份，我们将 TLS 实施重新设定为 2020 年 10 月 15 日，并将在随后的几周和几个月内继续推出。</span><span class="sxs-lookup"><span data-stu-id="ed29f-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="ed29f-105">从 2018 年 10 月 31 日起，Office 365 服务已弃用传输层安全性 (TLS) 1.0 和 1.1 协议。</span><span class="sxs-lookup"><span data-stu-id="ed29f-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="ed29f-106">预计对最终用户的影响最小。</span><span class="sxs-lookup"><span data-stu-id="ed29f-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="ed29f-107">此更改已公布两年以上，2017 年 12 月发布第一个公开声明。</span><span class="sxs-lookup"><span data-stu-id="ed29f-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="ed29f-108">本文仅用于介绍与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。</span><span class="sxs-lookup"><span data-stu-id="ed29f-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="ed29f-109">Office 和 TLS 概述</span><span class="sxs-lookup"><span data-stu-id="ed29f-109">Office and TLS overview</span></span>

<span data-ttu-id="ed29f-110">Office 客户端依赖 Windows Web 服务 (WINHTTP) TLS 协议发送和接收流量。</span><span class="sxs-lookup"><span data-stu-id="ed29f-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="ed29f-111">如果本地计算机的 Web 服务可以使用 TLS 1.2，Office 客户端可以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ed29f-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="ed29f-112">所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议是操作系统的一部分，而不是特定于 Office 客户端的。</span><span class="sxs-lookup"><span data-stu-id="ed29f-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="ed29f-113">在 Windows 8 和更高版本上</span><span class="sxs-lookup"><span data-stu-id="ed29f-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="ed29f-114">默认情况下，如果没有将网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和 1.1 协议可用。</span><span class="sxs-lookup"><span data-stu-id="ed29f-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="ed29f-115">在 Windows 7 上</span><span class="sxs-lookup"><span data-stu-id="ed29f-115">On Windows 7</span></span>

<span data-ttu-id="ed29f-116">没有 KB [3140245](https://support.microsoft.com/help/3140245) 更新，TLS 1.1 和 1.2 协议不可用。</span><span class="sxs-lookup"><span data-stu-id="ed29f-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="ed29f-117">更新解决了此问题并添加了以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="ed29f-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="ed29f-118">自 2018 年 10 月 31 日起，没有此更新的 Windows 7 用户会受到影响。</span><span class="sxs-lookup"><span data-stu-id="ed29f-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="ed29f-119">[KB 3140245](https://support.microsoft.com/help/3140245) 详细介绍了如何更改 WINHTTP 设置以启用 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="ed29f-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="ed29f-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="ed29f-120">More information</span></span>

<span data-ttu-id="ed29f-121">知识库文章 **介绍的 DefaultSecureProtocols** 注册表项的值决定了可以使用哪些网络协议：</span><span class="sxs-lookup"><span data-stu-id="ed29f-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="ed29f-122">DefaultSecureProtocols 值</span><span class="sxs-lookup"><span data-stu-id="ed29f-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="ed29f-123">协议已启用</span><span class="sxs-lookup"><span data-stu-id="ed29f-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="ed29f-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="ed29f-124">0x00000008</span></span>|<span data-ttu-id="ed29f-125">默认情况下启用 SSL 2.0</span><span class="sxs-lookup"><span data-stu-id="ed29f-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="ed29f-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="ed29f-126">0x00000020</span></span>|<span data-ttu-id="ed29f-127">默认情况下启用 SSL 3.0</span><span class="sxs-lookup"><span data-stu-id="ed29f-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="ed29f-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="ed29f-128">0x00000080</span></span>|<span data-ttu-id="ed29f-129">默认情况下启用 TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="ed29f-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="ed29f-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="ed29f-130">0x00000200</span></span>|<span data-ttu-id="ed29f-131">默认情况下启用 TLS 1.1</span><span class="sxs-lookup"><span data-stu-id="ed29f-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="ed29f-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="ed29f-132">0x00000800</span></span>|<span data-ttu-id="ed29f-133">默认情况下启用 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="ed29f-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="ed29f-134">Office 客户端和 TLS 注册表项</span><span class="sxs-lookup"><span data-stu-id="ed29f-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="ed29f-135">你可以参考[KB 4057306 准备在 Office 365 中强制使用 TLS 1.2。](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="ed29f-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="ed29f-136">这是一篇供 IT 管理员阅读的常规文章，它是有关 TLS 1.2 更改的官方文档。</span><span class="sxs-lookup"><span data-stu-id="ed29f-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="ed29f-137">下表显示了 2018 年 10 月 31 日之后 Office 365 客户端中相应的注册表项值。</span><span class="sxs-lookup"><span data-stu-id="ed29f-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="ed29f-138">2018 年 10 月 31 日之后为 Office 365 服务启用的协议</span><span class="sxs-lookup"><span data-stu-id="ed29f-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="ed29f-139">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed29f-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="ed29f-140">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ed29f-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="ed29f-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="ed29f-141">0x00000A80</span></span>|
|<span data-ttu-id="ed29f-142">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ed29f-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="ed29f-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="ed29f-143">0x00000A00</span></span>|
|<span data-ttu-id="ed29f-144">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ed29f-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="ed29f-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="ed29f-145">0x00000880</span></span>|
|<span data-ttu-id="ed29f-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="ed29f-146">TLS 1.2</span></span>|<span data-ttu-id="ed29f-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="ed29f-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ed29f-148">我们不建议使用 SSL 2.0 和 3.0 协议，这两种协议也可使用 **DefaultSecureProtocols** 密钥进行设置。</span><span class="sxs-lookup"><span data-stu-id="ed29f-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="ed29f-149">SSL 2.0 和 3.0 被视为已弃用的协议。</span><span class="sxs-lookup"><span data-stu-id="ed29f-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="ed29f-150">最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管最终决定这样做取决于最能满足产品需求的产品。</span><span class="sxs-lookup"><span data-stu-id="ed29f-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="ed29f-151">有关 SSL 3.0 漏洞详细信息，请参阅[KB 3009008。](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="ed29f-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="ed29f-152">可以在编程模式下使用默认的 Windows 计算器来设置相同的引用注册表项值。</span><span class="sxs-lookup"><span data-stu-id="ed29f-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="ed29f-153">有关详细信息，请参阅 [KB 3140245 更新以在 Windows 的 WinHTTP 中启用 TLS 1.1 和 TLS 1.2](https://support.microsoft.com/help/3140245)作为默认安全协议。</span><span class="sxs-lookup"><span data-stu-id="ed29f-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="ed29f-154">无论是否安装 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) ，DefaultSecureProtocols 注册表子项都不存在，必须手动或通过组策略对象 (GPO) 添加。</span><span class="sxs-lookup"><span data-stu-id="ed29f-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="ed29f-155">也就是说，除非必须自定义启用或限制哪些安全协议，否则不需要此密钥。</span><span class="sxs-lookup"><span data-stu-id="ed29f-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="ed29f-156">你只需 Windows 7 SP1 ([KB 3140245) ](https://support.microsoft.com/help/3140245) 更新。</span><span class="sxs-lookup"><span data-stu-id="ed29f-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
