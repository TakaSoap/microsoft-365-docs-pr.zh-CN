---
title: 使用 Jamf 部署在 macOS 上部署 Microsoft Defender for Endpoint Pro
description: 使用 Jamf 部署在 macOS 上部署 Microsoft Defender for Endpoint Pro
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: b41c5ec827e110e0101c50ce7babeb6442096edb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842886"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="99303-104">使用 Jamf 部署在 macOS 上部署 Microsoft Defender for Endpoint Pro</span><span class="sxs-lookup"><span data-stu-id="99303-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99303-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="99303-105">**Applies to:**</span></span>
- [<span data-ttu-id="99303-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99303-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99303-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="99303-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="99303-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="99303-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="99303-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="99303-110">了解如何使用 Jamf 部署在 macOS 上部署 Microsoft Defender for Endpoint Pro。</span><span class="sxs-lookup"><span data-stu-id="99303-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="99303-111">如果你使用的是 macOS Catalina (10.15.4) 或较新版本的 macOS，请参阅 [macOS Catalina](/microsoft-365/security/defender-endpoint/mac-sysext-policies)的新配置文件和较新版本的 macOS。</span><span class="sxs-lookup"><span data-stu-id="99303-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="99303-112">这是一个多步骤过程。</span><span class="sxs-lookup"><span data-stu-id="99303-112">This is a multi step process.</span></span> <span data-ttu-id="99303-113">你将需要完成以下所有步骤：</span><span class="sxs-lookup"><span data-stu-id="99303-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="99303-114">登录到 Jamf 门户</span><span class="sxs-lookup"><span data-stu-id="99303-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="99303-115">在 Jamf 中设置 macOS 设备组的 Microsoft Defender for Endpoint Pro</span><span class="sxs-lookup"><span data-stu-id="99303-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="99303-116">在 Jamf 中设置 macOS 策略上的 Microsoft Defender for Endpoint Pro</span><span class="sxs-lookup"><span data-stu-id="99303-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="99303-117">在 macOS 设备上将 Microsoft Defender for Endpoint 注册到 Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99303-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




