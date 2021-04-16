---
title: 使用 Jamf Pro 部署适用于 macOS 的 Microsoft Defender for Endpoint
description: 使用 Jamf Pro 部署适用于 macOS 的 Microsoft Defender for Endpoint
keywords: microsoft， defender， atp， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: e49a56b138e792f06229345d19a5867c9f6438af
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862255"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="6c2d4-104">使用 Jamf Pro 在 macOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c2d4-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c2d4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c2d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c2d4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c2d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c2d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c2d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6c2d4-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6c2d4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6c2d4-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6c2d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6c2d4-110">了解如何使用 Jamf Pro 在 macOS 上部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="6c2d4-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="6c2d4-111">如果你使用的是 macOS Catalina (10.15.4) 或较新版本的 macOS，请参阅 [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)的新配置文件和较新版本的 macOS。</span><span class="sxs-lookup"><span data-stu-id="6c2d4-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="6c2d4-112">这是一个多步骤过程。</span><span class="sxs-lookup"><span data-stu-id="6c2d4-112">This is a multi step process.</span></span> <span data-ttu-id="6c2d4-113">你将需要完成以下所有步骤：</span><span class="sxs-lookup"><span data-stu-id="6c2d4-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="6c2d4-114">登录到 Jamf 门户</span><span class="sxs-lookup"><span data-stu-id="6c2d4-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="6c2d4-115">在 Jamf Pro 中的 macOS 设备组上设置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c2d4-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="6c2d4-116">在 Jamf Pro 中的 macOS 策略上设置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c2d4-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="6c2d4-117">在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="6c2d4-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




