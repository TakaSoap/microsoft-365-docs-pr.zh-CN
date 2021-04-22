---
title: 在 Jamf Pro 中设置设备组
description: 了解如何在 macOS 上的适用于 Microsoft Defender for Endpoint 的 Jamf Pro 中设置设备组
keywords: device， group， microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933801"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="3b98d-104">在 Jamf Pro 中的 macOS 设备组上设置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b98d-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b98d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3b98d-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b98d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b98d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b98d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b98d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b98d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="3b98d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b98d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3b98d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="3b98d-110">将设备组设置为类似于组策略组织 (OUS) 、Microsoft Endpoint Configuration Manager 的设备集合和 Intune 的设备组。</span><span class="sxs-lookup"><span data-stu-id="3b98d-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="3b98d-111">导航到 **静态计算机组**。</span><span class="sxs-lookup"><span data-stu-id="3b98d-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="3b98d-112">选择"**新建"。**</span><span class="sxs-lookup"><span data-stu-id="3b98d-112">Select **New**.</span></span> 

    ![Jamf Pro1 的图像](images/jamf-pro-static-group.png)

3. <span data-ttu-id="3b98d-114">提供显示名称， **然后选择保存**。</span><span class="sxs-lookup"><span data-stu-id="3b98d-114">Provide a display name and select **Save**.</span></span>

    ![Jamf Pro2 的图像](images/jamfpro-machine-group.png)

4. <span data-ttu-id="3b98d-116">现在，你将在静态 **计算机组下看到 Contoso** **的计算机组**。</span><span class="sxs-lookup"><span data-stu-id="3b98d-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Jamf Pro3 的图像](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="3b98d-118">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b98d-118">Next step</span></span>
- [<span data-ttu-id="3b98d-119">在 Jamf Pro 中的 macOS 策略上设置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b98d-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
