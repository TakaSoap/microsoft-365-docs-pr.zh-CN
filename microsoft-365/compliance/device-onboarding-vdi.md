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
description: 在虚拟桌面基础结构 (VDI) 设备上部署配置包，以便将其载入到Microsoft 365终结点数据丢失防护服务。
ms.openlocfilehash: 6bfb0f69198afbcc9d2949d583e151631cc7953b
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760616"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>载入非永久性虚拟桌面基础结构设备

**适用于：**

- [Microsoft 365终结点数据丢失防护 （DLP）](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

- 虚拟桌面基础结构 (VDI) 设备

> [!WARNING]
> Microsoft 365虚拟桌面Windows终结点数据丢失防护支持支持单个会话方案。 目前不支持Windows虚拟桌面上的多会话方案。

## <a name="onboard-vdi-devices"></a>载入 VDI 设备

Microsoft 365支持非永久性虚拟桌面基础结构 (VDI) 会话加入。

> [!NOTE]
> 若要加入非永久性 VDI 会话，VDI 设备必须位于 1809 或更高版本Windows 10。

载入 VDI 时可能会遇到相关挑战。 以下是此方案的典型挑战：

- 即时提前加入短期会话，必须在实际预配之前载入到Microsoft 365。
- 设备名称通常会重复用于新会话。

VDI 设备可以显示在Microsoft 365合规中心中，如下所示：

- 每个设备的单个条目。
请注意，在这种情况下，必须在创建会话时配置 *相同的* 设备名称，例如使用无人参与的应答文件。
- 每个设备的多个条目 - 每个会话一个。

以下步骤将指导你完成 VDI 设备的载入，并突出显示单个和多个条目的步骤。

> [!WARNING]
> 对于资源配置较低的环境，VDI 启动过程可能会降低设备载入过程的速度。

1. 从 [Microsoft 合规中心](https://compliance.microsoft.com)获取 VDI 配置包.zip文件 (*DeviceCompliancePackage.zip*) 。

2. 在导航窗格中，选择 **“设置** > **Device 载入** > **Onboarding**”。

3. 在 **“部署方法** ”字段 **中，为非持久性终结点选择 VDI 载入脚本**。

4. 单击 **“下载”包** 并保存.zip文件。

5. 将从.zip文件中提取的 DeviceCompliancePackage 文件夹中的文件复制到路径`C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`下的`golden`图像中。

6. 如果未为每个设备实现单个条目，请复制 DeviceComplianceOnboardingScript.cmd。

7. 如果为每个设备实现单个条目，请复制 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript.cmd。

    > [!NOTE]
    > 如果看不到该 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 文件夹，则可能会隐藏该文件夹。 需要从文件资源管理器中选择 **“显示隐藏的文件和文件夹**”选项。

8. 打开“本地组策略编辑器”窗口并导航到 **“计算机配置** > **Windows 设置** > **ScriptsStartup** > 。

   > [!NOTE]
   > 域组策略也可用于载入非永久性 VDI 设备。

9. 根据要实现的方法，请执行相应的步骤：

   **对于每个设备的单个条目**

   选择 **“PowerShell 脚本”** 选项卡，然后单击“**添加** (Windows资源管理器将直接在之前复制载入脚本的路径中打开) 。 导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1`。

   **对于每个设备的多个条目**：

   选择 **“脚本”** 选项卡，然后单击“**添加** (Windows资源管理器将直接在之前复制载入脚本的路径中打开) 。 导航到载入 bash 脚本 `DeviceComplianceOnboardingScript.cmd`。

10. 测试解决方案：
    1. 使用一台设备创建池。
    1. 登录到设备。
    1. 从设备注销。
    1. 使用另一个用户登录到设备。
    1. **对于每个设备的单个条目**：在Microsoft Defender 安全中心中只检查一个条目。
       **对于每个设备的多个条目**：检查Microsoft Defender 安全中心中的多个条目。

11. 单击“导航”窗格上的 **“设备”列表** 。

12. 通过输入设备名称并选择 **“设备** ”作为搜索类型来使用搜索函数。

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>更新非永久性虚拟桌面基础结构 (VDI) 映像

最佳做法是，建议使用脱机服务工具修补黄金图像。

例如，在映像保持脱机状态时，可以使用以下命令安装更新：

```DOS
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

有关 DISM 命令和脱机服务的详细信息，请参阅以下文章：

- [使用 DISM 修改Windows映像](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM 映像管理Command-Line选项](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [减小脱机Windows映像中组件存储的大小](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

如果脱机服务不是非永久性 VDI 环境的可行选项，则应采取以下步骤来确保一致性和传感器运行状况：

1. 启动用于联机服务或修补的黄金映像后，运行一个离载脚本以关闭Microsoft 365设备监视传感器。 有关详细信息，请参阅 [使用本地脚本的“载入”设备](device-onboarding-script.md#offboard-devices-using-a-local-script)。

2. 通过在 CMD 窗口中运行以下命令来确保传感器已停止：

   ```DOS
   sc query sense
   ```

3. 根据需要为映像提供服务。

4. 使用可从 https://download.sysinternals.com/files/PSTools.zip) 中下载的PsExec.exe (运行以下命令，以清理自启动以来传感器可能累积的网络文件夹内容：

    ```DOS
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 像平时一样重新封住金像。

## <a name="related-topics"></a>相关主题

- [使用组策略载入Windows 10和Windows 11设备](device-onboarding-gp.md)
- [使用Microsoft Endpoint Configuration Manager载入Windows 10和Windows 11设备](device-onboarding-sccm.md)
- [使用移动设备管理工具载入 Windows 10 和 Windows 11 设备](device-onboarding-mdm.md)
- [使用本地脚本载入 Windows 10 和 Windows 11 设备](device-onboarding-script.md)
- [排查 Microsoft Defender 高级威胁防护载入问题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
