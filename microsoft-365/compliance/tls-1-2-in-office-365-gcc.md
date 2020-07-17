---
title: Office 中的弃用 TLS 1.0 和 1.1 365 GCC High and DoD
description: 讨论了 Microsoft 如何在 Office 365 和准备好使用 TLS 1.2 的情况下，在 GCC 的高和 DoD 环境中停止支持 TLS 1.1 和1.0。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158877"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="c5cc7-103">Office 中的弃用 TLS 1.0 和 1.1 365 GCC High and DoD</span><span class="sxs-lookup"><span data-stu-id="c5cc7-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="c5cc7-104">总结</span><span class="sxs-lookup"><span data-stu-id="c5cc7-104">Summary</span></span>

<span data-ttu-id="c5cc7-105">为符合联邦风险和授权管理程序（FedRAMP）的最新合规性标准，我们在 Microsoft Office 365 for GCC High and DoD 环境中弃用了传输层安全性（TLS）版本1.1 和1.0。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="c5cc7-106">此更改之前已通过 Microsoft 支持部门宣布，以 [准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="c5cc7-107">您的数据的安全是非常重要的，我们承诺对可能影响您的服务使用的更改的透明性。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="c5cc7-108">尽管[MICROSOFT TLS 1.0 实现](https://support.microsoft.com/help/3117336)没有已知的安全漏洞，但我们仍将致力于 FedRAMP 合规性标准。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="c5cc7-109">因此，在从2020年1月15日起，在 GCC 高和 DoD 环境中，我们将弃用 TLS 1.1 和 365 1.0。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="c5cc7-110">有关如何删除 TLS 1.1 和1.0 依赖项的信息，请参阅以下白皮书：</span><span class="sxs-lookup"><span data-stu-id="c5cc7-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="c5cc7-111">解决 TLS 1.0 问题</span><span class="sxs-lookup"><span data-stu-id="c5cc7-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="c5cc7-112">在为 TLS 1.1 和1.0 的此更改做准备时，建议改用 TLS 版本1.2。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="c5cc7-113">有关详细信息，请参阅[在 Office 365 中强制使用 TLS 1.2 的准备工作](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="c5cc7-114">更多信息</span><span class="sxs-lookup"><span data-stu-id="c5cc7-114">More information</span></span>

<span data-ttu-id="c5cc7-115">从2020年1月15日开始，在 GCC 高和 DoD 环境中的 Office 365 将弃用 TLS 1.1 和1.0。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="c5cc7-116">在2020年1月15日，客户端服务器和浏览器服务器的所有组合都应使用 TLS 版本1.2 （或更高版本），以确保所有连接都可以在不向 Office 365 服务发出问题的情况下进行。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="c5cc7-117">这可能需要对客户端服务器和浏览器服务器的某些组合进行更新。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="c5cc7-118">如果您未在2020更新到 TLS 1.2 （或更高版本），则在尝试连接到 Office 365 时，将会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="c5cc7-119">此外，还需要更新到 TLS 1.2 （或更高版本）作为解决方法的一部分。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="c5cc7-120">我们知道以下客户端无法使用 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="c5cc7-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="c5cc7-121">Android 4.3 和更低的版本</span><span class="sxs-lookup"><span data-stu-id="c5cc7-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="c5cc7-122">Firefox 版本 5.0 及更低版本</span><span class="sxs-lookup"><span data-stu-id="c5cc7-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="c5cc7-123">Windows 7 和更早版本上的 Internet Explorer 8 –10</span><span class="sxs-lookup"><span data-stu-id="c5cc7-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="c5cc7-124">Windows Phone 8.0 上的 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="c5cc7-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="c5cc7-125">Safari 6.0.4/OS X 10.8.4 和早期版本</span><span class="sxs-lookup"><span data-stu-id="c5cc7-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="c5cc7-126">我们建议您更新客户端以确保您保持对 Office 365 GCC 高和 DoD 的无中断访问。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="c5cc7-127">尽管当前对 Microsoft Online services 连接的分析表明，大多数服务和终结点都看到的不只是 TLS 1.1 和1.0 使用，但我们正在提供此更改的通知，以便您可以在支持 TLS 1.1 和1.0 结尾之前，根据需要更新任何受影响的客户端或服务器。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="c5cc7-128">如果要对混合方案或 Active Directory 联合身份验证服务（AD FS）使用任何内部部署基础结构，请确保基础结构可以同时支持使用 TLS 1.2 （或更高版本）的入站和出站连接。</span><span class="sxs-lookup"><span data-stu-id="c5cc7-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="c5cc7-129">除了在使用列出的不能使用 TLS 1.2 的客户端时可能会遇到的故障之外，删除 TLS 1.1 和1.0 将使您无法使用以下 Microsoft 产品：</span><span class="sxs-lookup"><span data-stu-id="c5cc7-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="c5cc7-130">Lync 电话</span><span class="sxs-lookup"><span data-stu-id="c5cc7-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="c5cc7-131">参考</span><span class="sxs-lookup"><span data-stu-id="c5cc7-131">References</span></span>

<span data-ttu-id="c5cc7-132">以下支持文章介绍了有助于确保客户端使用 TLS 1.2 的指南和参考：</span><span class="sxs-lookup"><span data-stu-id="c5cc7-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="c5cc7-133">准备在 Office 365 中使用 TLS 1.2 的必备</span><span class="sxs-lookup"><span data-stu-id="c5cc7-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
