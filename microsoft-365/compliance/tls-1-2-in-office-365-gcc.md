---
title: 在 Microsoft 365 GCC High 和 DoD 中禁用 TLS 1.0 和 1.1
description: 讨论 Microsoft 如何在 Microsoft 365 的 GCC High 和 DoD 环境中禁用对 TLS 1.1 和 1.0 的支持。
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: d4da76268791e36bd01b5d6f6140fd52c70b3b4a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454191"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="55f5d-103">在 Microsoft 365 GCC High 和 DoD 中禁用 TLS 1.0 和 1.1</span><span class="sxs-lookup"><span data-stu-id="55f5d-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="55f5d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="55f5d-104">Summary</span></span>

<span data-ttu-id="55f5d-105">为了符合联邦风险和授权管理计划 (FedRAMP) 的最新合规性标准，我们正在 Microsoft 365 GCC High 和 DoD 环境中禁用传输层安全性 (TLS) 版本 1.1 和 1.0。</span><span class="sxs-lookup"><span data-stu-id="55f5d-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="55f5d-106">此更改之前是通过 Microsoft 支持在 Office 365 中准备强制使用 [TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)而宣布的。</span><span class="sxs-lookup"><span data-stu-id="55f5d-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="55f5d-107">数据的安全性非常重要，我们承诺实现可能影响服务使用的更改的透明度。</span><span class="sxs-lookup"><span data-stu-id="55f5d-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="55f5d-108">尽管 [Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) 实现没有已知的安全漏洞，但我们仍致力于遵守 FedRAMP 合规性标准。</span><span class="sxs-lookup"><span data-stu-id="55f5d-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="55f5d-109">因此，我们在 2020 年 1 月 15 日禁用了 Microsoft 365 GCC High 和 DoD 环境中 TLS 1.1 和 1.0。</span><span class="sxs-lookup"><span data-stu-id="55f5d-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="55f5d-110">若要了解如何删除 TLS 1.1 和 1.0 依赖项，请参阅以下白皮书：</span><span class="sxs-lookup"><span data-stu-id="55f5d-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="55f5d-111">解决 TLS 1.0 问题</span><span class="sxs-lookup"><span data-stu-id="55f5d-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="55f5d-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="55f5d-112">More information</span></span>

<span data-ttu-id="55f5d-113">从 2020 年 1 月 15 日开始，GCC 高和 DoD 环境中 Microsoft 365 将禁用 TLS 1.1 和 1.0。</span><span class="sxs-lookup"><span data-stu-id="55f5d-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="55f5d-114">到 2020 年 1 月 15 日，客户端服务器和浏览器服务器的所有组合都应使用 TLS 版本 1.2 (或更高版本) 以确保可以建立所有连接而不会与 Microsoft 365 发生问题。</span><span class="sxs-lookup"><span data-stu-id="55f5d-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="55f5d-115">这可能需要更新客户端服务器和浏览器服务器的某些组合。</span><span class="sxs-lookup"><span data-stu-id="55f5d-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="55f5d-116">对于 SharePoint 和 OneDrive，需要更新和配置 .NET 以支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="55f5d-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="55f5d-117">有关信息，请参阅[如何在客户端上启用 TLS 1.2。](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="55f5d-117">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="55f5d-118">您必须更新客户端计算机，以确保保持对 Office 365 GCC High 和 DoD 的不间断访问。</span><span class="sxs-lookup"><span data-stu-id="55f5d-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="55f5d-119">你需要更新通过 TLS 1.0 或 TLS 1.1 调用 Microsoft 365 API 的应用程序以使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="55f5d-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="55f5d-120">.NET 4.5 默认为 TLS 1.1。</span><span class="sxs-lookup"><span data-stu-id="55f5d-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="55f5d-121">若要更新 .NET 配置，请参阅如何在客户端上启用传输层安全性 (TLS) [1.2。](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="55f5d-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="55f5d-122">有关详细信息，请参阅准备在 Office 365 中强制使用[TLS 1.2。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="55f5d-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="55f5d-123">我们知道以下客户端应用程序无法使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="55f5d-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="55f5d-124">Android 4.3 和更低的版本</span><span class="sxs-lookup"><span data-stu-id="55f5d-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="55f5d-125">Firefox 版本 5.0 及更低版本</span><span class="sxs-lookup"><span data-stu-id="55f5d-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="55f5d-126">Internet Explorer 8 Windows 7 和早期版本上的 Internet Explorer 8–10</span><span class="sxs-lookup"><span data-stu-id="55f5d-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="55f5d-127">Internet Explorer 10 Windows Phone 8.0 上显示</span><span class="sxs-lookup"><span data-stu-id="55f5d-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="55f5d-128">Safari 6.0.4/OS X 10.8.4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="55f5d-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="55f5d-129">尽管当前对 Microsoft Online 服务连接的分析显示，大多数服务和终结点几乎看不到 TLS 1.1 和 1.0 使用情况，但我们提供了此更改的通知，以便你可以在必要时更新任何受影响的客户端或服务器，然后再停止对 TLS 1.1 和 1.0 的支持。</span><span class="sxs-lookup"><span data-stu-id="55f5d-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="55f5d-130">如果要将任何本地基础结构用于混合方案或 Active Directory 联合身份验证服务 (AD FS) ，请确保该基础结构可以同时支持使用 TLS 1.2 (或更高版本) 的入站和出站连接。</span><span class="sxs-lookup"><span data-stu-id="55f5d-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="55f5d-131">除了使用无法使用 TLS 1.2 的列出的客户端时可能会遇到的中断之外，删除 TLS 1.1 和 1.0 将阻止你使用以下 Microsoft 产品：</span><span class="sxs-lookup"><span data-stu-id="55f5d-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="55f5d-132">Lync 电话</span><span class="sxs-lookup"><span data-stu-id="55f5d-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="55f5d-133">参考</span><span class="sxs-lookup"><span data-stu-id="55f5d-133">References</span></span>

<span data-ttu-id="55f5d-134">有关帮助确保客户端使用 TLS 1.2 的指导和参考，请参阅"准备在 Office 365 中强制使用[TLS 1.2"。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="55f5d-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
