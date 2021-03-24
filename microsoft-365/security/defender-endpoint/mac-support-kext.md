---
title: 解决 Microsoft Defender ATP for Mac 中的内核扩展问题
description: 解决 Microsoft Defender ATP for Mac 中与内核扩展相关的问题。
keywords: microsoft， defender， atp， mac， 内核， 扩展
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
ms.openlocfilehash: ee6f34a16c4c924bbc73af89029c529dfc766568
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055411"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="51775-104">解决 Microsoft Defender for Endpoint for Mac 中的内核扩展问题</span><span class="sxs-lookup"><span data-stu-id="51775-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="51775-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="51775-105">**Applies to:**</span></span>

- [<span data-ttu-id="51775-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="51775-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="51775-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51775-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="51775-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51775-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="51775-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="51775-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51775-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="51775-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="51775-111">本文提供有关解决作为 Microsoft Defender for Endpoint for Mac 的一部分安装的内核扩展的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="51775-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="51775-112">从 macOS High Sierra (10.13) 开始，macOS 要求在允许所有内核扩展在设备上运行之前得到明确批准。</span><span class="sxs-lookup"><span data-stu-id="51775-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they are allowed to run on the device.</span></span>

<span data-ttu-id="51775-113">如果在部署/安装 Microsoft Defender for Endpoint for Mac 期间未批准内核扩展，则应用程序将显示横幅提示你启用它：</span><span class="sxs-lookup"><span data-stu-id="51775-113">If you did not approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint for Mac, the application displays a banner prompting you to enable it:</span></span>

   ![RTP 已禁用屏幕截图](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-32-main-app-fix)

<span data-ttu-id="51775-115">还可以运行 ```mdatp health``` 。</span><span class="sxs-lookup"><span data-stu-id="51775-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="51775-116">它报告实时保护是否已启用，但不可用。</span><span class="sxs-lookup"><span data-stu-id="51775-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="51775-117">这表示未批准在设备上运行内核扩展。</span><span class="sxs-lookup"><span data-stu-id="51775-117">This indicates that the kernel extension is not approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="51775-118">以下各节提供有关如何解决此问题的指导，具体取决于你用于部署适用于 Mac 的 Microsoft Defender for Endpoint 的方法。</span><span class="sxs-lookup"><span data-stu-id="51775-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint for Mac.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="51775-119">托管部署</span><span class="sxs-lookup"><span data-stu-id="51775-119">Managed deployment</span></span>

<span data-ttu-id="51775-120">请参阅用于部署产品的管理工具对应的说明：</span><span class="sxs-lookup"><span data-stu-id="51775-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="51775-121">基于 JAMF 的部署</span><span class="sxs-lookup"><span data-stu-id="51775-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="51775-122">基于 Microsoft Intune 的部署</span><span class="sxs-lookup"><span data-stu-id="51775-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="51775-123">手动部署</span><span class="sxs-lookup"><span data-stu-id="51775-123">Manual deployment</span></span>

<span data-ttu-id="51775-124">如果安装产品后不到 30 分钟，请导航到"系统首选项安全性 & 隐私"，其中您必须允许开发人员  >  "Microsoft  Corporation"提供系统软件。</span><span class="sxs-lookup"><span data-stu-id="51775-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="51775-125">如果未看到此提示，则意味着 30 分钟或更长的时间已过，并且内核扩展尚未获得批准，无法在你的设备上运行：</span><span class="sxs-lookup"><span data-stu-id="51775-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![提示过期屏幕截图后的安全和隐私窗口](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-33-securityprivacysettings-noprompt)

<span data-ttu-id="51775-127">在这种情况下，您需要执行以下步骤以再次触发审批流程。</span><span class="sxs-lookup"><span data-stu-id="51775-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="51775-128">在终端中，尝试安装驱动程序。</span><span class="sxs-lookup"><span data-stu-id="51775-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="51775-129">以下操作将失败，因为内核扩展未获准在设备上运行。</span><span class="sxs-lookup"><span data-stu-id="51775-129">The following operation will fail, because the kernel extension was not approved to run on the device.</span></span> <span data-ttu-id="51775-130">但是，它将再次触发审批流程。</span><span class="sxs-lookup"><span data-stu-id="51775-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="51775-131">从 **菜单中打开** 系统  >  **首选项&隐私**"。</span><span class="sxs-lookup"><span data-stu-id="51775-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="51775-132"> (，请首先关闭它。) </span><span class="sxs-lookup"><span data-stu-id="51775-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="51775-133">**允许** 来自开发人员"Microsoft Corporation"的系统软件</span><span class="sxs-lookup"><span data-stu-id="51775-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="51775-134">在终端中，再次安装驱动程序。</span><span class="sxs-lookup"><span data-stu-id="51775-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="51775-135">此时操作将成功：</span><span class="sxs-lookup"><span data-stu-id="51775-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="51775-136">横幅应从 Defender 应用程序中消失，现在应报告实时保护已启用 ```mdatp health``` 且可用：</span><span class="sxs-lookup"><span data-stu-id="51775-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
