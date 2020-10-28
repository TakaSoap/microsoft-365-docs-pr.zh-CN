---
title: " (VDI) 设备的板载非永久性虚拟桌面基础结构"
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 在虚拟桌面基础结构 (VDI) 设备上部署配置包，以使其载入到 Microsoft 365 终结点数据丢失防护服务。
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769401"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a> (VDI) 设备的板载非永久性虚拟桌面基础结构

**适用于：**
- [Microsoft 365 Endpoint data 丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

-  (VDI) 设备的虚拟桌面基础结构

>[!WARNING]
> Windows 虚拟桌面的 Microsoft 365 终结点数据丢失防护支持支持单个会话方案。 目前，Windows 虚拟桌面上的多会话方案不受支持。

## <a name="onboard-vdi-devices"></a>板载 VDI 设备

Microsoft 365 终结点数据丢失防护支持非永久性 VDI 会话载入。 

>[!Note]
>对于板载非永久性 VDI 会话，VDI 设备必须在 Windows 10 1809 或更高版本上。

在加入 VDIs 时可能会有相关的挑战。 以下是此方案的典型难题：

- 即时启动短期会话的快速加载，在实际设置之前，必须载入到 Microsoft 365 终结点数据丢失。
- 通常为新会话重用设备名称。

VDI 设备可以在 Microsoft 365 合规性中心中显示，就是：

- 每个设备一个条目。  
请注意，在这种情况下，必须在创建会话时配置 *相同* 的设备名称，例如使用无人参与的应答文件。
- 每个设备1个条目-每个会话一个。

以下步骤将指导您完成加入 VDI 设备的步骤，并将突出显示单个和多个条目的步骤。

>[!WARNING]
> 对于资源配置较少的环境，VDI 启动过程可能会降低 Microsoft 365 终结点数据丢失防护的加入速度。 

1.  打开您从 "服务载入" 向导下载 *DeviceCompliancePackage.zip* )  (的 VDI 配置包 .zip 文件。

2.  在导航窗格中，选择 " **设置**  >  **设备** 启动加入"  >  **Onboarding** 。

3. 在 " **部署方法** " 字段中， **为非持久终结点选择 VDI 载入脚本** 。

5. 单击 " **下载包** " 并保存该 .zip 文件。

6. 将从 .zip 文件提取的 DeviceCompliancePackage 文件夹中的文件复制到 `golden/master` 路径下的图像中 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。 

7. 如果不是为每个设备实现单个条目，请复制 DeviceComplianceOnboardingScript。

8. 如果要为每个设备实现单个条目，请复制 Onboard-NonPersistentMachine.ps1 和 DeviceComplianceOnboardingScript。
    
    > [!NOTE]
    > 如果看不到该 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 文件夹，则可能已将其隐藏。 您需要从文件资源管理器中选择 " **显示隐藏文件和文件夹** " 选项。

9. 打开本地组策略编辑器窗口并导航到 " **计算机配置** " "  >  **Windows 设置**  >  **脚本**  >  **启动** "。

   > [!NOTE]
   > 域组策略也可用于加入非永久性 VDI 设备。

4. 根据要实现的方法，请执行相应的步骤：

   **对于每个设备的单个条目**
   
   选择 " **PowerShell 脚本** " 选项卡，然后单击 " **添加** " (Windows 资源管理器将直接在先前复制的载入脚本的路径中打开) 。 导航到 "载入 PowerShell 脚本" `Onboard-NonPersistentMachine.ps1` 。
   
   **对于每个设备的多个条目** ：
   
   选择 " **脚本** " 选项卡，然后单击 " **添加** " (Windows 资源管理器将直接在先前复制的载入脚本的路径中打开) 。 导航到 "载入 bash" 脚本 `DeviceComplianceOnboardingScript.cmd` 。

5. 测试您的解决方案：

   1. 创建一个包含一个设备的池。
      
   1. 登录到设备。
      
   1. 从设备注销。

   1. 使用另一个用户登录到设备。
      
   1. **对于每个设备的单个条目** ：仅检查 Microsoft Defender Security Center 中的一个条目。<br>
      **对于每个设备的多个条目** ：检查 Microsoft Defender 安全中心中的多个条目。

6. 单击导航窗格上的 " **设备列表** "。

7. 通过输入设备名称并选择 " **设备** " 作为搜索类型来使用搜索功能。

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a> (VDI) 映像更新非永久性虚拟桌面基础结构
作为一种最佳做法，我们建议使用脱机服务工具来修补黄金/母版映像。<br>
例如，您可以使用下面的命令在图像保持脱机的情况下安装更新：

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

有关 DISM 命令和离线服务的详细信息，请参阅以下文章：
- [使用 DISM 修改 Windows 映像](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM 图像管理 Command-Line 选项](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [减小脱机 Windows 映像中组件存储的大小](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

如果非持久 VDI 环境中的脱机服务不是可行的选项，则应采取以下步骤来确保一致性和传感器运行状况：

1. 在启动用于联机服务或修补的主映像之后，运行一个脱离脚本来关闭 Microsoft 365 终结点数据丢失防护传感器。 有关详细信息，请参阅 [使用本地脚本的分离设备](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。

2. 通过在 CMD 窗口中运行下面的命令来确保传感器已停止：

   ```console
   sc query sense
   ```

3. 根据需要为图像服务。

4. 使用 PsExec.exe (可从其下载 https://download.sysinternals.com/files/PSTools.zip) 以清理自启动以来，传感器可能已积累的网络文件夹内容的命令运行以下命令：

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 按正常方式重新密封黄金/主映像。

## <a name="related-topics"></a>相关主题
- [使用组策略的板载 Windows 10 设备](dlp-configure-endpoints-gp.md)
- [使用 Microsoft 终结点配置管理器的板载 Windows 10 设备](dlp-configure-endpoints-sccm.md)
- [使用移动设备管理工具的板载 Windows 10 设备](dlp-configure-endpoints-mdm.md)
- [使用本地脚本的板载 Windows 10 设备](dlp-configure-endpoints-script.md)
- [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
