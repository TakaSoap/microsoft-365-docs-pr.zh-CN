---
title: 解决 Microsoft Defender ATP for Mac 的许可证问题
description: 解决 Microsoft Defender ATP for Mac 中的许可证问题。
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689109"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="28aad-104">解决 macOS 上 Microsoft Defender for Endpoint 的许可证问题</span><span class="sxs-lookup"><span data-stu-id="28aad-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="28aad-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28aad-105">**Applies to:**</span></span>

- [<span data-ttu-id="28aad-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28aad-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="28aad-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28aad-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28aad-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28aad-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28aad-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="28aad-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28aad-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28aad-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="28aad-111">当你在 [macOS](microsoft-defender-endpoint-mac.md) 上通过 Microsoft Defender for Endpoint 和 [手动](mac-install-manually.md) 部署测试或概念证明 (PoC) 时，你可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="28aad-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![许可证错误的图像](images/no-license-found.png)

<span data-ttu-id="28aad-113&quot;>**消息：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;28aad-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;28aad-114&quot;>未找到许可证</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;28aad-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;28aad-115&quot;>看起来你的组织没有 Microsoft 365 企业版订阅的许可证。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;28aad-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;28aad-116&quot;>请与管理员联系以寻求帮助。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;28aad-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;28aad-117&quot;>**原因：**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;28aad-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;28aad-118&quot;>你已部署和/或安装了 macOS 程序包上的 Microsoft Defender for Endpoint (&quot;下载安装程序包") 但你可能已运行配置脚本 ("下载载入程序包") 。</span><span class="sxs-lookup"><span data-stu-id="28aad-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="28aad-119">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="28aad-119">**Solution:**</span></span>

<span data-ttu-id="28aad-120">按照以下 MicrosoftDefenderATPOnboardingMacOs.py 说明操作： [客户端配置](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="28aad-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

