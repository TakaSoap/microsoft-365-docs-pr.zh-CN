---
title: 使用Windows管理器载入设备
description: 使用 Configuration Manager 在设备上部署配置包，以便设备载入服务。
keywords: 使用 sccm 载入设备， 设备管理， 为终结点设备配置 Microsoft Defender
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/22/2021
ms.technology: mde
ms.openlocfilehash: ff1863a24e352823fce6d1c9e57f228528cda016
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176879"
---
# <a name="onboard-the-windows-devices-using-configuration-manager"></a>使用配置Windows载入新设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Endpoint Configuration Manager当前分支
- System Center 2012 R2 Configuration Manager

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)。

## <a name="supported-client-operating-systems"></a>支持的客户端操作系统

根据正在运行的 Configuration Manager 版本，可以载入以下客户端操作系统：

- **Configuration Manager 版本 1910 及之前版本**：
  - 运行 Windows 10
- **Configuration Manager 版本 2002 及更高版本**：

  从 Configuration Manager 版本 2002 开始，你可以载入以下操作系统：

  - Windows 8.1
  - Windows 10
  - Windows 11
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server 2016版本 1803 或更高版本
  - Windows Server 2019
  - Windows Server 2022

> [!NOTE]
> 若要详细了解如何载入 Windows Server 2012 R2、Windows Server 2016、Windows Server 2019 和 Windows Server 2022，请参阅载入[Windows 服务器](configure-server-endpoints.md)。

### <a name="onboard-devices-using-system-center-configuration-manager"></a>使用移动设备载入System Center Configuration Manager

请查看[PDF 或](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署 Microsoft Defender for Endpoint 的各种路径。

1. 打开 Configuration Manager 配置.zip文件 *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从应用门户获取[Microsoft 365 Defender包](https://security.microsoft.com/)：
    1. 在导航窗格中，选择 **"设置** \> **终结点** \> **设备管理** \> **载入"。**
    2. 选择Windows 10或Windows 11 作为操作系统。
    3. 在"**部署方法"** 字段中，选择 **"System Center Configuration Manager 2012/2012 R2/1511/1602"。**
    4. 选择 **"下载** 程序包"，然后保存.zip文件。

2. 将 .zip 文件的内容解压缩到将部署包的网络管理员可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATPOnboardingScript.cmd 的文件*。

3. 按照 Package [and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))一文中的步骤部署程序包。

   选择要将程序包部署到的预定义设备集合。

> [!NOTE]
> 在 [OOBE ](https://answers.microsoft.com/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 体验阶段，Defender for Endpoint 不支持 (载入) 加入。 确保用户在运行完安装或升级后Windows OOBE。
>
> 请注意，在 Configuration Manager 应用程序上创建检测规则可以持续检查设备是否已载入。 应用程序是一种与包和程序不同的对象类型。
> 如果由于挂起的 OOBE (或其他任何原因) ，设备尚未载入，Configuration Manager 将重试载入设备，直到规则检测到状态更改。
>
> 通过创建检测规则检查"OnboardingState"注册表值是否为 (= 1，REG_DWORD) 实现此行为。
> 此注册表值位于"HKLM\SOFTWARE\Microsoft\Windows高级威胁防护\状态"下。
有关详细信息，请参阅[Configure Detection Methods in System Center 2012 R2 Configuration Manager。](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>配置示例集合设置

对于每个设备，你可以设置一个配置值，以指示当通过 Microsoft 365 Defender 提交文件进行深入分析时是否可以从设备收集示例。

> [!NOTE]
> 这些配置设置通常通过 Configuration Manager 完成。

可以在 Configuration Manager 中为配置项设置合规性规则，以更改设备上的示例共享设置。

此规则应为修正 *合规性* 规则配置项，用于设置目标设备上注册表项的值以确保它们合规。

通过以下注册表项设置配置：

```text
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

其中 Key 类型为 D-WORD。 可能的值是：

- 0：不允许从此设备进行示例共享
- 1：允许从此设备共享所有文件类型

如果注册表项不存在，则默认值为 1。

有关合规性System Center Configuration Manager，请参阅[System Center 2012 R2 Configuration Manager 中的合规性设置简介](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。

## <a name="other-recommended-configuration-settings"></a>其他建议的配置设置

将设备载入服务后，必须利用包含的威胁防护功能，通过以下建议的配置设置启用这些功能。

### <a name="device-collection-configuration"></a>设备集合配置

如果你使用的是 Endpoint Configuration Manager 版本 2002 或更高版本，可以选择扩大部署范围以包括服务器或低级别客户端。

### <a name="next-generation-protection-configuration"></a>下一代保护配置

建议使用以下配置设置：

#### <a name="scan"></a>扫描

- 扫描可移动存储设备（如 USB 驱动器）：是

#### <a name="real-time-protection"></a>实时保护

- 启用行为监视：是
- 在下载时和安装之前启用对可能不需要的应用程序的保护：是

#### <a name="cloud-protection-service"></a>云保护服务

- 云保护服务成员身份类型：高级成员身份

#### <a name="attack-surface-reduction"></a>攻击面减少

将所有可用规则配置为审核。

> [!NOTE]
> 阻止这些活动可能会中断合法的业务流程。 最佳方法是设置要审核的所有内容，确定哪些内容可安全打开，然后在没有误报检测的终结点上启用这些设置。

#### <a name="network-protection"></a>网络保护

在审核或阻止模式下启用网络保护之前，请确保已安装反恶意软件平台更新，该更新可以从支持 [页面获取](https://support.microsoft.com/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)。

#### <a name="controlled-folder-access"></a>文件夹限制访问

在审核模式下启用该功能至少 30 天。 在此时间段后，检查检测并创建允许写入受保护目录的应用程序列表。

有关详细信息，请参阅评估 [受控文件夹访问权限](evaluate-controlled-folder-access.md)。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。

## <a name="offboard-devices-using-configuration-manager"></a>使用 Configuration Manager 的载出设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，并且该日期也将包含在程序包名称中。

> [!NOTE]
> 载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>使用当前分支Microsoft Endpoint Manager载设备

如果使用 Microsoft Endpoint Manager当前分支，请参阅[创建载出配置文件](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>使用 System Center 2012 R2 Configuration Manager 的载出设备

1. 从门户获取Microsoft 365 Defender[包](https://security.microsoft.com/)：
    1. 在导航窗格中，选择 **"设置** \>  \> **终结点设备管理** \> **""载出"。**  
    1. 选择Windows 10或Windows 11 作为操作系统。
    1. 在"**部署方法"** 字段中，选择 **"System Center Configuration Manager 2012/2012 R2/1511/1602"。**
    1. 选择 **"下载** 程序包"，然后保存.zip文件。

2. 将 .zip 文件的内容解压缩到将部署包的网络管理员可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。

3. 按照 Package [and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))一文中的步骤部署程序包。

   选择要将程序包部署到的预定义设备集合。

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

## <a name="monitor-device-configuration"></a>监视设备配置

如果你使用的是当前分支Microsoft Endpoint Manager，请使用 Configuration Manager 控制台中的内置 Defender for Endpoint 仪表板。 有关详细信息，请参阅 [Defender for Endpoint - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。

如果使用的是 System Center 2012 R2 Configuration Manager，则监控由两部分组成：

1. 确认配置包已正确部署，并且正在 (或已成功) 网络中设备上运行配置包。

2. 检查设备是否符合 Defender for Endpoint 服务 (这可确保设备可以完成载入过程，并可以继续将数据报告给服务) 。

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>确认配置包已正确部署

1. 在 Configuration Manager 控制台中 **，单击导航** 窗格底部的"监视"。

2. 选择 **"概述**"，然后选择"**部署"。**

3. 使用程序包名称选择部署。

4. 查看"完成统计信息"和 **"内容** 状态" **下的状态指示器**。

    如果设备部署失败 (错误、不满足要求或失败状态) ，你可能需要对设备进行故障排除。  有关详细信息，请参阅 Microsoft [Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)。

    ![显示成功部署（无错误）的 Configuration Manager。](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>检查设备是否符合 Microsoft Defender for Endpoint 服务

可以在 2012 R2 Configuration Manager 中为System Center项设置合规性规则，以监视部署。

此规则应为非 *修正* 性合规性规则配置项，用于监视目标设备上注册表项的值。

监视以下注册表项：

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

有关详细信息，请参阅 introduction [to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。

## <a name="related-topics"></a>相关主题

- [使用Windows载入设备](configure-endpoints-gp.md)
- [使用Windows管理工具载入设备](configure-endpoints-mdm.md)
- [使用Windows脚本载入设备](configure-endpoints-script.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
- [在新载入的 Microsoft Defender 终结点设备上运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
