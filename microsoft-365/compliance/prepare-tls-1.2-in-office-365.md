---
title: 在 Office 365 和 Office 365 GCC 中准备 TLS 1.2
description: 在停止对 TLS 1.0 和 1.1 的支持后，如何让 Office 365 和 Office 365 GCC 中的所有客户端-服务器和浏览器-服务器组合准备好使用 TLS 1.2。
author: kccross
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
- Office 365 Business
ms.openlocfilehash: 708e5dc68b777db42696c6791124b2a8dd1d3b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927948"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a><span data-ttu-id="ee617-103">在 Office 365 和 Office 365 GCC 中准备 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="ee617-103">Preparing for TLS 1.2 in Office 365 and Office 365 GCC</span></span>

## <a name="summary"></a><span data-ttu-id="ee617-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ee617-104">Summary</span></span>

<span data-ttu-id="ee617-105">为了向我们的客户提供一流的加密，Microsoft 计划在 Office 365 和 Office 365 GCC 中弃用传输层安全 (TLS) 版本 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="ee617-105">To provide the best-in-class encryption to our customers, Microsoft plans to deprecate Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span> <span data-ttu-id="ee617-106">我们知道您的数据的安全性非常重要，并且我们承诺对可能影响使用 TLS 服务的更改保持透明公开。</span><span class="sxs-lookup"><span data-stu-id="ee617-106">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span>

<span data-ttu-id="ee617-107">[Microsoft TLS 1.0 实现](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n)没有已知安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="ee617-107">The [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) has no known security vulnerabilities.</span></span> <span data-ttu-id="ee617-108">但是，由于未来的潜在协议降级攻击和其他 TLS 漏洞，我们将停止在 Microsoft Office 365 和 Office 365 GCC 中提供 TLS 1.0 和 1.1 支持。</span><span class="sxs-lookup"><span data-stu-id="ee617-108">But because of the potential for future protocol downgrade attacks and other TLS vulnerabilities, we are discontinuing support for TLS 1.0 and 1.1 in Microsoft Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="ee617-109">有关如何删除 TLS 1.0 和 1.1 依赖项的信息，请参阅以下白皮书：[解决 TLS 1.0 问题](https://www.microsoft.com/download/details.aspx?id=55266)。</span><span class="sxs-lookup"><span data-stu-id="ee617-109">For information about how to remove TLS 1.0 and 1.1 dependencies, see the following white paper: [Solving the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>

## <a name="more-information"></a><span data-ttu-id="ee617-110">更多信息</span><span class="sxs-lookup"><span data-stu-id="ee617-110">More information</span></span>

<span data-ttu-id="ee617-111">自 2020 年 1 月起，我们已经开始弃用 TLS 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="ee617-111">We have already begun deprecation of TLS 1.0 and 1.1 as of January 2020.</span></span> <span data-ttu-id="ee617-112">不支持通过 TLS 1.0 或 1.1 在我们的 DoD 或 GCC High 实例中连接到 Office 365 的任何客户端、设备或服务。</span><span class="sxs-lookup"><span data-stu-id="ee617-112">Any clients, devices, or services that connect to Office 365 through TLS 1.0 or 1.1 in our DoD or GCC High instances are unsupported.</span></span> <span data-ttu-id="ee617-113">对于 Office 365 商业客户，TLS 1.0 和 1.1 的弃用将于 2020 年 10 月 15 日开始，并持续数周和数月推出。</span><span class="sxs-lookup"><span data-stu-id="ee617-113">For our commercial customers of Office 365, deprecation of TLS 1.0 and 1.1 will begin October 15, 2020 and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="ee617-114">我们建议所有客户端-服务器和浏览器-服务器组合使用 TLS1.2（或更高版本）以保持与 Office 365 服务的连接。</span><span class="sxs-lookup"><span data-stu-id="ee617-114">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) in order to maintain connection to Office 365 services.</span></span> <span data-ttu-id="ee617-115">你可能必须更新某些客户端-服务器和浏览器-服务器组合。</span><span class="sxs-lookup"><span data-stu-id="ee617-115">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="ee617-116">你需要更新通过 TLS 1.0 或 TLS 1.1 调用 Microsoft 365 API 的应用程序，以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ee617-116">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="ee617-117">.NET 4.5 默认为 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="ee617-117">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="ee617-118">若要更新 .NET 配置，请参阅如何在客户端上启用传输层安全性[ (TLS) 1.2。](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="ee617-118">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="ee617-119">以下是已知的无法使用 TLS 1.2 的客户端。</span><span class="sxs-lookup"><span data-stu-id="ee617-119">The following clients are known to be unable to use TLS 1.2.</span></span> <span data-ttu-id="ee617-120">更新这些客户端以确保对服务的访问不会间断。</span><span class="sxs-lookup"><span data-stu-id="ee617-120">Update these clients to ensure uninterrupted access to the service.</span></span>

- <span data-ttu-id="ee617-121">Android 4.3 和更低的版本</span><span class="sxs-lookup"><span data-stu-id="ee617-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="ee617-122">Firefox 版本 5.0 及更低版本</span><span class="sxs-lookup"><span data-stu-id="ee617-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="ee617-123">Windows 7 上的 Internet Explorer 8-10 及更早版本</span><span class="sxs-lookup"><span data-stu-id="ee617-123">Internet Explorer 8-10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="ee617-124">Windows Phone 8 上的 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="ee617-124">Internet Explorer 10 on Windows Phone 8</span></span>
- <span data-ttu-id="ee617-125">Safari 6.0.4/OS X10.8.4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="ee617-125">Safari 6.0.4/OS X10.8.4 and earlier versions</span></span>

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="ee617-126">适用于 Microsoft Teams Rooms 和 Surface Hub 的 TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="ee617-126">TLS 1.2 for Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="ee617-127">自 2018 年 12 月以来，Microsoft Teams Room（以前称为 Skype Room System V2 SRS V2）就一直支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ee617-127">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) have supported TLS 1.2 since December 2018.</span></span> <span data-ttu-id="ee617-128">我们建议 Room 设备安装 Microsoft Teams Rooms 应用版本 4.0.64.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee617-128">We recommend that Rooms devices have Microsoft Teams Rooms app version 4.0.64.0 or later installed.</span></span> <span data-ttu-id="ee617-129">有关更多信息，请参阅[发行说明](/microsoftteams/room-systems/srs2-release-note)。</span><span class="sxs-lookup"><span data-stu-id="ee617-129">For more information, see the [Release notes](/microsoftteams/room-systems/srs2-release-note).</span></span> <span data-ttu-id="ee617-130">更改是向后和向前兼容的。</span><span class="sxs-lookup"><span data-stu-id="ee617-130">The changes are backward and forward compatible.</span></span>

<span data-ttu-id="ee617-131">2019 年 5 月，Surface Hub 发布了 TLS 1.2 支持。</span><span class="sxs-lookup"><span data-stu-id="ee617-131">Surface Hub released TLS 1.2 support in May 2019.</span></span>

<span data-ttu-id="ee617-132">对 Microsoft Teams Rooms 和 Surface Hub 产品的 TLS 1.2 支持还要求更改以下服务器端代码：</span><span class="sxs-lookup"><span data-stu-id="ee617-132">TLS 1.2 support for Microsoft Teams Rooms and Surface Hub products also requires the following server-side code changes:</span></span>

- <span data-ttu-id="ee617-133">Skype for Business Online 服务器更改已于 2019 年 4 月上线。</span><span class="sxs-lookup"><span data-stu-id="ee617-133">Skype for Business Online server changes were made live in April 2019.</span></span> <span data-ttu-id="ee617-134">现在，Skype for Business Online 支持使用 TLS 1.2 连接 Microsoft Teams Room 和 Surface Hub 设备。</span><span class="sxs-lookup"><span data-stu-id="ee617-134">Now, Skype for Business Online supports connecting Microsoft Teams Rooms and Surface Hub devices by using TLS 1.2.</span></span>
- <span data-ttu-id="ee617-135">Skype for Business Server 客户必须安装累积更新 (CU) 才能对 Teams Rooms Systems 和 Surface Hub 使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ee617-135">Skype for Business Server customers must install a cumulative update (CU) to use TLS 1.2 for Teams Rooms Systems and Surface Hub.</span></span>

  - <span data-ttu-id="ee617-136">对于 Skype for Business Server 2015，CU9 已于 2019 年 5 月发布。</span><span class="sxs-lookup"><span data-stu-id="ee617-136">For Skype for Business Server 2015, CU9 is already released in May 2019.</span></span>
  - <span data-ttu-id="ee617-137">对于 Skype for Business Server 2019，CU1 先前计划于 2019 年 4 月发布，但推迟到 2019 年 6 月。</span><span class="sxs-lookup"><span data-stu-id="ee617-137">For Skype for Business Server 2019, CU1 was previously planned for April 2019 but is delayed to June 2019.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ee617-138">在为 Skype for Business Server 安装特定的 CU 之前，Skype for Business 本地客户不应禁用 TLS 1.0 / 1.1。</span><span class="sxs-lookup"><span data-stu-id="ee617-138">Skype for Business on-premises customers should not disable TLS 1.0/1.1 before installing specific CUs for Skype for Business Server.</span></span>

<span data-ttu-id="ee617-139">如果您正在使用混合式场景的本地基础架构或 Active Directory 联合身份验证服务，确保该基础架构同时支持使用 TLS 1.2 的进站和出站连接。</span><span class="sxs-lookup"><span data-stu-id="ee617-139">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services, make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2.</span></span>

## <a name="references"></a><span data-ttu-id="ee617-140">参考</span><span class="sxs-lookup"><span data-stu-id="ee617-140">References</span></span>

<span data-ttu-id="ee617-141">以下资源提供帮助确保客户端正在使用 TLS 1.2 或更高版本及禁用 TLS 1.0 和 1.1 的指导。</span><span class="sxs-lookup"><span data-stu-id="ee617-141">The following resources provide guidance to help make sure that your clients are using TLS 1.2 or a later version and to disable TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="ee617-142">对于连接到 Office 365 的 Windows 7 客户端，请确保 TLS 1.2 是 Windows WinHTTP 中的默认安全协议。</span><span class="sxs-lookup"><span data-stu-id="ee617-142">For Windows 7 clients that connect to Office 365, make sure that TLS 1.2 is the default secure protocol in WinHTTP in Windows.</span></span> <span data-ttu-id="ee617-143">有关更多信息，请参阅 [KB 3140245 - 更新以在 Windows 的 WinHTTP 中启用 TLS 1.1 和 TLS 1.2 作为默认安全协议](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)。</span><span class="sxs-lookup"><span data-stu-id="ee617-143">For more information see [KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).</span></span>
- <span data-ttu-id="ee617-144">要通过删除 TLS 1.0 和 1.1 依赖项解决 TLS 使用弱点问题，请参阅 [Microsoft TLS 1.2 支持](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。</span><span class="sxs-lookup"><span data-stu-id="ee617-144">To start addressing weak TLS use by removing TLS 1.0 and 1.1 dependencies, see [TLS 1.2 support at Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).</span></span>
- <span data-ttu-id="ee617-145">[新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)可更加方便地在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上查找通过使用弱安全协议连接服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="ee617-145">[New IIS functionality](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) makes it easier to find clients on [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) and [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) that connect to the service by using weak security protocols.</span></span>
- <span data-ttu-id="ee617-146">获取有关如何解决 [TLS 1.0 问题的信息](https://www.microsoft.com/download/details.aspx?id=55266)。</span><span class="sxs-lookup"><span data-stu-id="ee617-146">Get more information about how to [solve the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).</span></span>
- <span data-ttu-id="ee617-147">有关安全性方法的一般信息，请转到[Office 365 信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。</span><span class="sxs-lookup"><span data-stu-id="ee617-147">For general information about our approach to security, go to the [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).</span></span>
- [<span data-ttu-id="ee617-148">准备 TLS 1.0/1.1 弃用 - Office 365 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ee617-148">Preparing for TLS 1.0/1.1 Deprecation - Office 365 Skype for Business</span></span>](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [<span data-ttu-id="ee617-149">Exchange Server TLS 指南，第 1 部分：为 TLS 1.2 做好准备</span><span class="sxs-lookup"><span data-stu-id="ee617-149">Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [<span data-ttu-id="ee617-150">Exchange Server TLS 指南，第 2 部分：启用 TLS 1.2 并识别不使用它的客户端</span><span class="sxs-lookup"><span data-stu-id="ee617-150">Exchange Server TLS guidance Part 2: Enabling TLS 1.2 and Identifying Clients Not Using It</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [<span data-ttu-id="ee617-151">Exchange Server TLS 指南，第 3 部分：关闭 TLS 1.0/1.1</span><span class="sxs-lookup"><span data-stu-id="ee617-151">Exchange Server TLS guidance Part 3: Turning Off TLS 1.0/1.1</span></span>](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [<span data-ttu-id="ee617-152">在 Office Online Server 中启用 TLS 1.1 和 TLS 1.2 支持</span><span class="sxs-lookup"><span data-stu-id="ee617-152">Enable TLS 1.1 and TLS 1.2 support in Office Online Server</span></span>](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)