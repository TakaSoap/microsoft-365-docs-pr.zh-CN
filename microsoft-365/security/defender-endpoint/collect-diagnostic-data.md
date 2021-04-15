---
title: 收集 Microsoft Defender 防病毒的诊断数据
description: 使用工具收集数据以排除 Microsoft Defender 防病毒故障
keywords: 疑难解答， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender av， 组策略对象， 设置， 诊断数据
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d74a8921af677f6ed66580bd00830440d59cf1aa
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764719"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="52ce3-104">收集 Microsoft Defender AV 诊断数据</span><span class="sxs-lookup"><span data-stu-id="52ce3-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="52ce3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="52ce3-105">**Applies to:**</span></span>

- [<span data-ttu-id="52ce3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="52ce3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="52ce3-107">本文介绍如何收集诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决在使用 Microsoft Defender AV 时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="52ce3-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="52ce3-108">作为调查或响应过程的一部分，你可以从设备收集调查包。</span><span class="sxs-lookup"><span data-stu-id="52ce3-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="52ce3-109">操作说明： [从设备收集调查包](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)。</span><span class="sxs-lookup"><span data-stu-id="52ce3-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="52ce3-110">在至少两个遇到相同问题的设备上，通过执行以下步骤获取 .cab 诊断文件：</span><span class="sxs-lookup"><span data-stu-id="52ce3-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="52ce3-111">打开命令提示符的管理员级别版本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52ce3-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="52ce3-112">a.</span><span class="sxs-lookup"><span data-stu-id="52ce3-112">a.</span></span> <span data-ttu-id="52ce3-113">打开" **开始"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="52ce3-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="52ce3-114">b.</span><span class="sxs-lookup"><span data-stu-id="52ce3-114">b.</span></span> <span data-ttu-id="52ce3-115">类型 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="52ce3-115">Type **cmd**.</span></span> <span data-ttu-id="52ce3-116">右键单击命令 **提示符，** 然后单击 **以管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="52ce3-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="52ce3-117">c.</span><span class="sxs-lookup"><span data-stu-id="52ce3-117">c.</span></span> <span data-ttu-id="52ce3-118">输入管理员凭据或批准提示。</span><span class="sxs-lookup"><span data-stu-id="52ce3-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="52ce3-119">导航到 Microsoft Defender 目录。</span><span class="sxs-lookup"><span data-stu-id="52ce3-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="52ce3-120">默认情况下，此操作为 `C:\Program Files\Windows Defender`。</span><span class="sxs-lookup"><span data-stu-id="52ce3-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="52ce3-121">如果你运行的是更新的 [Microsoft Defender 平台版本](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)，请 `MpCmdRun` 从以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` ：。</span><span class="sxs-lookup"><span data-stu-id="52ce3-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="52ce3-122">键入以下命令，然后按 **Enter**</span><span class="sxs-lookup"><span data-stu-id="52ce3-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="52ce3-123">将生成包含各种诊断日志的 .cab 文件。</span><span class="sxs-lookup"><span data-stu-id="52ce3-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="52ce3-124">将在命令提示符的输出中指定文件的位置。</span><span class="sxs-lookup"><span data-stu-id="52ce3-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="52ce3-125">默认情况下，位置为 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="52ce3-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="52ce3-126">若要将 cab 文件重定向到其他路径或 UNC 共享，请使用以下命令： `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="52ce3-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="52ce3-127">有关详细信息，请参阅将 [诊断数据重定向到 UNC 共享](#redirect-diagnostic-data-to-a-unc-share)。</span><span class="sxs-lookup"><span data-stu-id="52ce3-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="52ce3-128">将这些 .cab 文件复制到 Microsoft 支持人员可以访问的位置。</span><span class="sxs-lookup"><span data-stu-id="52ce3-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="52ce3-129">例如，可以与我们共享受密码保护的 OneDrive 文件夹。</span><span class="sxs-lookup"><span data-stu-id="52ce3-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="52ce3-130">如果更新合规性有问题，使用 Update <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Compliance</a>支持电子邮件模板发送电子邮件，并填写包含以下信息的模板：</span><span class="sxs-lookup"><span data-stu-id="52ce3-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="52ce3-131">将诊断数据重定向到 UNC 共享</span><span class="sxs-lookup"><span data-stu-id="52ce3-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="52ce3-132">若要收集中央存储库上的诊断数据，您可以指定 SupportLogLocation 参数。</span><span class="sxs-lookup"><span data-stu-id="52ce3-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="52ce3-133">将诊断数据复制到指定路径。</span><span class="sxs-lookup"><span data-stu-id="52ce3-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="52ce3-134">如果未指定路径，诊断数据将复制到支持日志位置配置中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="52ce3-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="52ce3-135">使用 SupportLogLocation 参数时，将在目标路径中创建如下所示的文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="52ce3-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="52ce3-136">字段</span><span class="sxs-lookup"><span data-stu-id="52ce3-136">field</span></span>  | <span data-ttu-id="52ce3-137">说明</span><span class="sxs-lookup"><span data-stu-id="52ce3-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="52ce3-138">path</span><span class="sxs-lookup"><span data-stu-id="52ce3-138">path</span></span> | <span data-ttu-id="52ce3-139">命令行中指定的路径或从配置中检索的路径</span><span class="sxs-lookup"><span data-stu-id="52ce3-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="52ce3-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="52ce3-140">MMDD</span></span> | <span data-ttu-id="52ce3-141">收集诊断数据的月份和 (例如，0530) </span><span class="sxs-lookup"><span data-stu-id="52ce3-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="52ce3-142">hostname</span><span class="sxs-lookup"><span data-stu-id="52ce3-142">hostname</span></span> | <span data-ttu-id="52ce3-143">收集诊断数据的设备的主机名</span><span class="sxs-lookup"><span data-stu-id="52ce3-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="52ce3-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="52ce3-144">HHMM</span></span> | <span data-ttu-id="52ce3-145">收集诊断数据的小时数和分钟数 (例如，1422) </span><span class="sxs-lookup"><span data-stu-id="52ce3-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="52ce3-146">使用文件共享时，请确保用于收集诊断包的帐户对共享具有写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="52ce3-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="52ce3-147">指定创建诊断数据的位置</span><span class="sxs-lookup"><span data-stu-id="52ce3-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="52ce3-148">还可以指定使用组策略对象创建诊断 .cab 文件的位置 (GPO) 。</span><span class="sxs-lookup"><span data-stu-id="52ce3-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="52ce3-149">打开本地组策略编辑器，并找到 SupportLogLocation GPO，位置为： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="52ce3-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="52ce3-150">选择 **"定义目录路径"以复制支持日志文件**。</span><span class="sxs-lookup"><span data-stu-id="52ce3-150">Select **Define the directory path to copy support log files**.</span></span>

    ![本地组策略编辑器的屏幕截图](images/GPO1-SupportLogLocationDefender.png)  
        
     ![定义日志文件设置路径的屏幕截图](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="52ce3-153">在策略编辑器内，选择"已启用 **"。**</span><span class="sxs-lookup"><span data-stu-id="52ce3-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="52ce3-154">在"选项"字段中指定要复制支持日志文件的 **目录** 路径。</span><span class="sxs-lookup"><span data-stu-id="52ce3-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="52ce3-155">![已启用目录路径自定义设置的屏幕截图](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="52ce3-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="52ce3-156">选择 **"确定"** 或"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="52ce3-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="52ce3-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52ce3-157">See also</span></span>

- [<span data-ttu-id="52ce3-158">Microsoft Defender 防病毒报告疑难解答</span><span class="sxs-lookup"><span data-stu-id="52ce3-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)