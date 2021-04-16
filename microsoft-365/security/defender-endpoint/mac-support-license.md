---
title: 解决 Microsoft Defender for Endpoint for Mac 的许可证问题
description: 解决 Microsoft Defender for Endpoint for Mac 中的许可证问题。
keywords: microsoft， defender， atp， mac， 性能
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
ms.openlocfilehash: 3fb351d9ce8e9beef812e6aaa7d463161a6af8df
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862183"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="8f730-104">解决 macOS 上 Microsoft Defender for Endpoint 的许可证问题</span><span class="sxs-lookup"><span data-stu-id="8f730-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8f730-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8f730-105">**Applies to:**</span></span>

- [<span data-ttu-id="8f730-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8f730-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="8f730-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8f730-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f730-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f730-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8f730-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8f730-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8f730-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8f730-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8f730-111">当你在 [macOS](microsoft-defender-endpoint-mac.md) 上通过 Microsoft Defender for Endpoint 和 [手动](mac-install-manually.md) 部署测试或概念证明 (PoC) 时，你可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="8f730-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![许可证错误的图像](images/no-license-found.png)

<span data-ttu-id="8f730-113&quot;>**消息：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f730-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;8f730-114&quot;>未找到许可证</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f730-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;8f730-115&quot;>看起来你的组织没有 Microsoft 365 企业版订阅的许可证。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f730-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;8f730-116&quot;>请与管理员联系以寻求帮助。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f730-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;8f730-117&quot;>**原因：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f730-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;8f730-118&quot;>你已部署和/或安装了 macOS 程序包上的 Microsoft Defender for Endpoint (&quot;下载安装程序包") 但你可能已运行配置脚本 ("下载载入程序包") 。</span><span class="sxs-lookup"><span data-stu-id="8f730-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="8f730-119">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="8f730-119">**Solution:**</span></span>

<span data-ttu-id="8f730-120">按照以下 MicrosoftDefenderATPOnboardingMacOs.py 说明操作： [客户端配置](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="8f730-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

