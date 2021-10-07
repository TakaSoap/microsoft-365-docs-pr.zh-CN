---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 在 VDI (虚拟桌面基础结构) 包，以便它们可以载入到 Microsoft 365 终结点数据丢失防护服务。
ms.openlocfilehash: 9b61ee4095065010a7924031493e2810e624e1a7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204355"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>载入非永久性虚拟桌面基础结构设备

**适用于：**
- [Microsoft 365DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)

- 虚拟桌面基础结构 (VDI) 设备

> [!WARNING]
> Microsoft 365虚拟桌面的终结点数据丢失防护Windows支持单个会话方案。 当前不支持Windows桌面上的多会话方案。

## <a name="onboard-vdi-devices"></a>载入 VDI 设备

Microsoft 365终结点数据丢失防护支持非永久性虚拟桌面基础结构 (VDI) 会话载入。

> [!NOTE]
> 若要载入非永久性 VDI 会话，VDI 设备必须位于 Windows 10 1809 或更高版本上。

载入 VDIS 时可能存在相关挑战。 以下是此方案的典型挑战：

- 即时提前载入短期会话，在实际预配之前，必须Microsoft 365终结点数据丢失防护。
- 设备名称通常重新用于新会话。

VDI 设备可以在合规性Microsoft 365显示为：

- 每台设备的单个条目。
请注意，在这种情况下，创建会话时必须配置相同的设备名称，例如使用无人参与应答文件。
- 每个设备有多个条目 - 每个会话一个条目。

以下步骤将指导你完成载入 VDI 设备，并重点介绍单项和多条目的步骤。

> [!WARNING]
> 对于资源配置较低的环境，VDI 启动过程可能会Microsoft 365终结点数据丢失防护载入。

1. 打开 VDI 配置包.zip文件 *(DeviceCompliancePackage.zip)* 从服务载入向导下载的内容。

2. 在导航窗格中，选择 **"设置**  >  **载入**  >  **"。**

3. 在 **"部署方法"** 字段中，选择 **"非永久性终结点的 VDI 载入脚本"。**

4. 单击 **下载程序包** 并保存.zip文件。

5. 将文件从 DeviceCompliancePackage 文件夹中从 .zip 文件复制到路径 `golden/master` 下的映像 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 中。

6. 如果未针对每台设备实现单个条目，请复制 DeviceComplianceOnboardingScript.cmd。

7. 如果要针对每台设备实现单个条目，请同时复制 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript.cmd。

    > [!NOTE]
    > 如果看不到该文件夹 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ，它可能处于隐藏状态。 你需要从文件资源管理器中选择显示隐藏 **文件和** 文件夹选项。

8. 打开本地组策略编辑器窗口并 **导航到计算机** 配置  >  **Windows 设置**  >  **脚本**  >  **启动**。

   > [!NOTE]
   > 域组策略还可用于载入非永久性 VDI 设备。

9. 根据你要实现的方法，请按照相应步骤操作：

   **对于每台设备的单个条目**

   选择 **"PowerShell 脚本**"选项卡，然后单击"添加 (Windows资源管理器将在你之前复制载入脚本的路径中直接) 。 导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1` 。

   **对于每台设备的多个条目**：

   选择"**脚本**"选项卡，然后单击 **"添加** (Windows资源管理器将在你之前复制载入脚本的路径中直接) 。 导航到载入 Bash 脚本 `DeviceComplianceOnboardingScript.cmd` 。

10. 测试解决方案：
    1. 创建具有一台设备的池。
    1. 登录到设备。
    1. 从设备注销。
    1. 使用其他用户登录到设备。
    1. **For single entry for each device**： Check only one entry in Microsoft Defender 安全中心.
       **For multiple entries for each device**： Check multiple entries in Microsoft Defender 安全中心.

11. 单击 **导航窗格上的** "设备列表"。

12. 通过输入设备名称并选择设备作为搜索类型 **来** 使用搜索函数。

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>使用 VDI 映像更新非永久性 () 基础结构

作为最佳实践，我们建议使用脱机维护工具修补黄金/主映像。

例如，可以使用以下命令在映像保持脱机时安装更新：

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

有关 DISM 命令和脱机服务的详细信息，请参阅以下文章：

- [使用 DISM Windows映像](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM 映像管理Command-Line选项](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [减小脱机映像中组件存储Windows大小](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

如果脱机服务不是非永久性 VDI 环境的可行选项，应执行以下步骤以确保一致性和传感器运行状况：

1. 启动主映像进行联机维护或修补后，运行一个 offboarding脚本来Microsoft 365终结点数据丢失防护传感器。 有关详细信息，请参阅使用本地 [脚本的载出设备](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。

2. 在 CMD 窗口中运行以下命令，确保传感器已停止：

   ```console
   sc query sense
   ```

3. 根据需要为映像提供服务。

4. 使用可下载的 PsExec.exe (运行以下命令，以清理传感器自启动后可能 https://download.sysinternals.com/files/PSTools.zip) 累积的网络文件夹内容：

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 像平常一样重新密封黄金/主图像。

## <a name="related-topics"></a>相关主题

- [使用Windows 10载入设备](dlp-configure-endpoints-gp.md)
- [使用Windows 10设备载入Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 10 设备](dlp-configure-endpoints-mdm.md)
- [使用本地脚本载入 Windows 10 设备](dlp-configure-endpoints-script.md)
- [Microsoft Defender 高级威胁防护载入问题疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
