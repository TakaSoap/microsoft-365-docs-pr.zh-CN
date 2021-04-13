---
title: 收集 Microsoft Defender 防病毒更新合规性Windows Defender诊断数据
description: 使用工具收集数据，解决使用 Microsoft Defender 防病毒评估加载项时的更新合规性问题
keywords: 疑难解答， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3975a18c2986ac7766664194a6d4b80ee1a503b1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689958"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="d9446-104">收集 Microsoft Defender AV 评估的更新合规性诊断数据</span><span class="sxs-lookup"><span data-stu-id="d9446-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9446-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d9446-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9446-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9446-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d9446-107">本文介绍如何收集诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决在使用更新合规性外接程序中的 Microsoft Defender AV 评估部分时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="d9446-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="d9446-108">在尝试此过程之前，请确保你已阅读 Microsoft [Defender 防病毒](troubleshoot-reporting.md)报告疑难解答，满足所有先决条件，并采取了任何其他建议的疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="d9446-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="d9446-109">在至少两台未在更新合规性中报告或显示的设备上，通过执行以下步骤获取 .cab 诊断文件：</span><span class="sxs-lookup"><span data-stu-id="d9446-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="d9446-110">打开命令提示符的管理员级别版本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9446-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="d9446-111">a.</span><span class="sxs-lookup"><span data-stu-id="d9446-111">a.</span></span> <span data-ttu-id="d9446-112">打开" **开始"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="d9446-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="d9446-113">b.</span><span class="sxs-lookup"><span data-stu-id="d9446-113">b.</span></span> <span data-ttu-id="d9446-114">类型 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="d9446-114">Type **cmd**.</span></span> <span data-ttu-id="d9446-115">右键单击命令 **提示符，** 然后单击 **以管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="d9446-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="d9446-116">c.</span><span class="sxs-lookup"><span data-stu-id="d9446-116">c.</span></span> <span data-ttu-id="d9446-117">输入管理员凭据或批准提示。</span><span class="sxs-lookup"><span data-stu-id="d9446-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="d9446-118">导航到Windows Defender目录。</span><span class="sxs-lookup"><span data-stu-id="d9446-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="d9446-119">默认情况下，此操作为 `C:\Program Files\Windows Defender`。</span><span class="sxs-lookup"><span data-stu-id="d9446-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="d9446-120">键入以下命令，然后按 **Enter**</span><span class="sxs-lookup"><span data-stu-id="d9446-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="d9446-121">将生成包含各种诊断日志的 .cab 文件。</span><span class="sxs-lookup"><span data-stu-id="d9446-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="d9446-122">将在命令提示符的输出中指定文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d9446-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="d9446-123">默认情况下，位置为 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="d9446-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="d9446-124">将这些 .cab 文件复制到 Microsoft 支持人员可以访问的位置。</span><span class="sxs-lookup"><span data-stu-id="d9446-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="d9446-125">例如，可以与我们共享受密码保护的 OneDrive 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d9446-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="d9446-126">使用更新一致性支持 <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">电子邮件模板发送电子邮件</a>，并填写包含以下信息的模板：</span><span class="sxs-lookup"><span data-stu-id="d9446-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="d9446-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9446-127">See also</span></span>

- [<span data-ttu-id="d9446-128">Microsoft Windows Defender防病毒报告疑难解答</span><span class="sxs-lookup"><span data-stu-id="d9446-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)