---
title: 收集诊断数据Microsoft Defender 防病毒
description: 使用工具来收集数据以排查Microsoft Defender 防病毒
keywords: 疑难解答， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender av， 组策略对象， 设置， 诊断数据
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 73f07a7346edbaebe7e53cd4e17e29a5e6764073
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170514"
---
# <a name="collect-microsoft-defender-antivirus-diagnostic-data"></a>收集Microsoft Defender 防病毒诊断数据

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

本文介绍如何收集诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决在使用 Microsoft Defender 防病毒 时可能遇到的问题。

> [!NOTE]
> 作为调查或响应过程的一部分，你可以从设备收集调查包。 操作说明： [从设备收集调查包](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)。

在至少两个遇到相同问题的设备上，.cab以下步骤获取诊断文件：

1. 打开命令提示符的管理员级别版本，如下所示：

    a. 打开" **开始"** 菜单。

    b. 类型 **cmd**。 右键单击命令 **提示符** ，然后选择以 **管理员角色运行**。

    c. 指定管理员凭据或批准提示。

2. 导航到目录，Microsoft Defender 防病毒。 默认情况下，此操作为 `C:\Program Files\Windows Defender`。

   > [!NOTE]
   > 如果你运行的是更新的 [Microsoft Defender 反恶意软件平台版本](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)，请从 `MpCmdRun` 以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` ：。

3. 键入以下命令，然后按 **Enter**

    ```Dos
    mpcmdrun.exe -GetFiles
    ```

4. 将.cab一个包含各种诊断日志的诊断文件。 将在命令提示符的输出中指定文件的位置。 默认情况下，位置为 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 。

   > [!NOTE]
   > 若要将 cab 文件重定向到其他路径或 UNC 共享，请使用以下命令：
   >
   > `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`
   >
   > 有关详细信息，请参阅将 [诊断数据重定向到 UNC 共享](#redirect-diagnostic-data-to-a-unc-share)。

5. 将.cab文件复制到 Microsoft 支持人员可以访问的位置。 例如，您可以与我们OneDrive受密码保护的文件夹。

> [!NOTE]
> 如果更新合规性有问题，使用 Update <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Compliance</a>支持电子邮件模板发送电子邮件，并填写包含以下信息的模板：
>
> 在更新合规性中使用 Microsoft Defender 防病毒时，我遇到以下问题：
>
> 我至少提供了 2 个支持.cab以下位置的文件：
>
> \<accessible share, including access details such as password\>
>
> 我的 OMS 工作区 ID 为：
>
> 请联系我：

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>将诊断数据重定向到 UNC 共享

若要收集中央存储库上的诊断数据，您可以指定 SupportLogLocation 参数。

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

将诊断数据复制到指定路径。 如果未指定路径，诊断数据将复制到支持日志位置配置中指定的位置。

使用 SupportLogLocation 参数时，将在目标路径中创建如下所示的文件夹结构：

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

<br>

****

|字段|Description|
|---|---|
|path|命令行中指定的路径或从配置中检索的路径|
|MMDD|收集诊断数据的月份和 (例如，0530) |
|hostname|收集诊断数据的设备的主机名|
|HHMM|收集诊断数据的小时数和分钟数 (例如，1422) |
|

> [!NOTE]
> 使用文件共享时，请确保用于收集诊断包的帐户具有对共享的写入访问权限。

## <a name="specify-location-where-diagnostic-data-is-created"></a>指定创建诊断数据的位置

还可以指定使用组策略对象.cab GPO 文件创建诊断 (位置) 。

1. 打开本地组策略编辑器，并找到 SupportLogLocation GPO，位置为： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation` 。

2. 选择 **"定义目录路径"以复制支持日志文件**。

   ![本地组策略编辑器的屏幕截图](images/GPO1-SupportLogLocationDefender.png)

   ![定义日志文件设置路径的屏幕截图](images/GPO2-SupportLogLocationGPPage.png)

    ![本地组策略编辑器的屏幕截图。](images/GPO1-SupportLogLocationDefender.png)  
        
     ![定义日志文件设置路径的屏幕截图。](images/GPO2-SupportLogLocationGPPage.png)  
3. 在策略编辑器内，选择"已启用 **"。**

4. 在"选项"字段中指定要复制支持日志文件的 **目录** 路径。
     ![Enabled 目录路径自定义设置的屏幕截图。](images/GPO3-SupportLogLocationGPPageEnabledExample.png) 
5. 选择 **"确定"** 或"**应用"。**

## <a name="see-also"></a>另请参阅

- [报告Microsoft Defender 防病毒疑难解答](troubleshoot-reporting.md)
