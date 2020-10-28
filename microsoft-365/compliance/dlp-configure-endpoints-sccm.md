---
title: 使用配置管理器的板载 Windows 10 设备
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
description: 使用 Configuration Manager 在设备上部署配置包，以使其载入服务。
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769407"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>使用配置管理器的板载 Windows 10 设备

**适用于：**

- [Microsoft 365 Endpoint data 丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)
- 系统中心 2012 R2 配置管理器

### <a name="onboard-devices-using-system-center-configuration-manager"></a>使用 System Center Configuration Manager 的板载设备

1. 打开您从 "服务载入" 向导下载 *DeviceComplianceOnboardingPackage.zip* )  (的 configuration Manager 配置包 .zip 文件。 你也可以从 [Microsoft 合规性中心](https://compliance.microsoft.com/)获取该包。

2. 在导航窗格中，选择 " **设置**  >  **设备** 启动加入"  >  **Onboarding** 。

3. 在 " **部署方法** " 字段中，选择 " **Microsoft 终结点配置管理器 2012/2012 R2/1511/1602** "。
 
4. 选择 " **下载包** "，并保存 .zip 文件。

5. 将 .zip 文件的内容提取到一个共享的只读位置，该位置可供将部署该包的网络管理员访问。 您应该具有一个名为 *DeviceComplianceOnboardingScript* 的文件。

6. 按照 [System Center 2012 R2 Configuration Manager 一文中的程序包和程序](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 中的步骤部署程序包。

7. 选择要将程序包部署到的预定义设备集合。

> [!NOTE]
> Microsoft 365 终结点数据丢失防护不支持在 [OOBE) 阶段 (的开箱 ](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 即用期间的载入。 确保在运行 Windows 安装或升级后，用户完成了 OOBE。

>[!TIP]
> 在载入设备后，您可以选择运行检测测试来验证设备是否已正确载入服务。 有关详细信息，请参阅 [在新载入上运行检测测试 Microsoft DEFENDER ATP 设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)。
>
> 请注意，可以在 Configuration Manager 应用程序上创建一个检测规则，以连续检查设备是否已载入。 应用程序是与包和程序不同的对象类型。
> 如果设备尚未载入 (由于挂起的 OOBE 完成或任何其他原因) ，配置管理器将重试设备板载，直到规则检测到状态更改。
> 
> 如果 "OnboardingState" 注册表值 (的类型 REG_DWORD) = 1，则可以通过创建检测规则检查来实现此行为。
> 此注册表值位于 "HKLM\SOFTWARE\Microsoft\Windows 高级威胁 Protection\Status" 下。
有关详细信息，请参阅 [在 System Center 2012 R2 配置管理器中配置检测方法](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)。

### <a name="configure-sample-collection-settings"></a>配置示例集合设置

对于每个设备，您可以设置一个配置值以表明通过 Microsoft Defender 安全中心发出请求以提交文件进行深入分析时，能否从设备收集示例。

>[!NOTE]
>这些配置设置通常通过配置管理器完成。 

您可以为 Configuration Manager 中的配置项目设置符合性规则，以更改设备上的示例共享设置。

此规则应为 *补救* 合规性规则配置项，它在目标设备上设置注册表项的值，以确保它们是投诉。

通过以下注册表项设置配置：

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
其中：<br>
键类型为 D-字。 <br>
可能的值是：
- 0-不允许从此设备共享示例
- 1-允许共享此设备的所有文件类型

如果注册表项不存在，则默认值为1。

有关 System Center Configuration Manager 合规性的详细信息，请参阅 [System center 2012 R2 Configuration Manager 中的合规性设置简介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。


## <a name="other-recommended-configuration-settings"></a>其他建议的配置设置
在将设备载入服务后，请务必充分利用包含的威胁防护功能，方法是使用以下建议的配置设置来启用这些功能。

### <a name="device-collection-configuration"></a>设备集合配置
如果使用的是终结点配置管理器，版本2002或更高版本，则可以选择扩大部署以包含服务器或下层客户端。


### <a name="next-generation-protection-configuration"></a>下一代保护配置

建议使用以下配置设置：

**扫描**

- 扫描可移动存储设备（如 USB 驱动器）：是

**实时保护**

- 启用行为监视：是
- 在下载和安装之前针对可能不需要的应用程序启用保护：是

**云保护服务**

- 云保护服务成员身份类型：高级成员身份

**攻击面减少** 将所有可用的规则配置为 "审核"。

>[!NOTE]
> 阻止这些活动可能会中断合法业务流程。 最佳方法是设置要审核的所有内容，确定哪些内容是安全的，然后在不具有误报检测的终结点上启用这些设置。

**网络保护**

在 "审核" 或 "阻止" 模式下启用网络保护之前，请确保已安装反恶意软件平台更新（可从 " [支持" 页面](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)获取）。


**受控文件夹访问**

在审核模式下启用至少30天的功能。 在此时间段后，检查检测项并创建允许写入受保护目录的应用程序列表。

有关详细信息，请参阅 [评估受控文件夹访问权限](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)。


## <a name="offboard-devices-using-configuration-manager"></a>使用配置管理器的分离设备

出于安全考虑，用于分离设备的包将在下载后的30天后过期。 发送到设备的已过期的脱离程序包将被拒绝。 下载一个脱离程序包时，系统会通知你数据包到期日期，并且它也将包含在程序包名称中。

> [!NOTE]
> 无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>使用 Microsoft 终结点配置管理器的分离设备当前分支

如果使用 Microsoft 终结点配置管理器的当前分支，请参阅 [创建脱离配置文件](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>使用 System Center 2012 R2 配置管理器的分离设备

1. 从 [Microsoft 合规性中心](https://compliance.microsoft.com/)获取脱离包：

2. 在导航窗格中，选择 " **设置**  >   **设备加入** >  **脱离** "。

3. 选择 Windows 10 作为操作系统。

4. 在 " **部署方法** " 字段中，选择 " **Microsoft 终结点配置管理器 2012/2012 R2/1511/1602** "。
    
5. 选择 " **下载包** "，并保存 .zip 文件。

6. 将 .zip 文件的内容提取到一个共享的只读位置，该位置可供将部署该包的网络管理员访问。 您应具有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的文件。

7. 按照 [System Center 2012 R2 Configuration Manager 一文中的程序包和程序](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 中的步骤部署程序包。

8. 选择要将程序包部署到的预定义设备集合。

> [!IMPORTANT]
> 脱离将导致设备停止向门户发送传感器数据，但设备中的数据（包括对其已有的任何警报的引用）将保留最长6个月。


## <a name="monitor-device-configuration"></a>监视设备配置

如果使用的是 Microsoft 终结点配置管理器的当前分支，请使用 Configuration Manager 控制台中的内置 Microsoft Defender ATP 仪表板。 有关详细信息，请参阅 [Microsoft Defender 高级威胁防护-Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。

如果您使用的是 System Center 2012 R2 配置管理器，则监控由以下两部分组成：

1. 确认配置包已正确部署，并且正在运行 (或已在网络中的设备上成功运行) 。

2. 检查设备是否符合 Microsoft 365 终结点数据丢失防护服务 (这可确保设备能够完成载入过程，并可继续向服务) 报告数据。

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>确认配置包已正确部署

1. 在 Configuration Manager 控制台中，单击导航窗格底部的 " **监视** "。

2. 依次选择 " **概述** " 和 " **部署** "。

3. 在部署中选择包名称。

4. 查看 " **完成统计信息** " 和 " **内容状态** " 下的状态指示器。

    如果有失败的部署 (设备出现 **错误** 、 **未满足要求** 或 **故障状态** ) ，则可能需要对设备进行故障排除。 有关详细信息，请参阅 [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。

    ![显示无任何错误的成功部署的配置管理器](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>检查设备是否符合 Microsoft 365 终结点数据丢失防护服务

您可以为 System Center 2012 R2 配置管理器中的配置项目设置符合性规则，以监视您的部署。

> [!NOTE]
> 此过程和注册表项适用于终结点 DLP 以及高级威胁防护。

此规则应 *是非补救* 性规则配置项目，用于监视目标设备上的注册表项的值。

监视以下注册表项项：
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
有关详细信息，请参阅 [System Center 2012 R2 Configuration Manager 中的合规性设置简介](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。

## <a name="related-topics"></a>相关主题
- [使用组策略的板载 Windows 10 设备](dlp-configure-endpoints-gp.md)
- [使用移动设备管理工具的板载 Windows 10 设备](dlp-configure-endpoints-mdm.md)
- [使用本地脚本的板载 Windows 10 设备](dlp-configure-endpoints-script.md)
- [ (VDI) 设备的板载非永久性虚拟桌面基础结构](dlp-configure-endpoints-vdi.md)
- [在新载入上运行检测测试 Microsoft Defender ATP 设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
