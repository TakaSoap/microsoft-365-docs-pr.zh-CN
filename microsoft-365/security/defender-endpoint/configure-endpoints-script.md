---
title: 使用本地脚本载入 Windows 设备
description: 使用本地脚本在设备上部署配置包，以允许将设备载入服务。
keywords: 使用本地脚本配置设备， 设备管理， 为终结点设备配置 Microsoft Defender
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
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dc7f3a88f26ae738f3de718bd590933f44ed4906
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167186"
---
# <a name="onboard-windows-devices-using-a-local-script"></a>使用本地脚本载入 Windows 设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)。

还可以手动将个别设备载入到 Defender for Endpoint。 在承诺载入网络内的所有设备之前，你可能希望先在测试服务时这样做。

> [!IMPORTANT]
> 此脚本已优化为在最多 10 台设备上使用。
>
> 若要大规模部署，请使用 [其他部署选项](configure-endpoints.md)。 例如，可以使用使用组策略 载入 Windows 设备中提供的脚本，将载入脚本部署到生产中的 10[多个设备](configure-endpoints-gp.md)。

请查看[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)或[Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)查看部署 Defender for Endpoint 的各种路径。 

## <a name="onboard-devices"></a>载入设备 

1.  打开 GP 配置包.zip文件 *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从门户获取Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">包</a>：

    1. 在导航窗格中，**选择"设置**  >  **终结点**  >  **设备管理**  >  **载入"。**


请查看[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)或[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署 Defender for Endpoint 的各种路径。

1. 打开 GP 配置包.zip文件 *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从门户获取Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">包</a>：
    1. 在导航窗格中，选择 **"设置** \>  \> **终结点设备管理** \> **载入"。**
    2. 选择Windows 10或Windows 11操作系统。
    3. 在"**部署方法"** 字段中，选择"**本地脚本"。**
    4. 单击 **下载程序包** 并保存.zip文件。

2. 将配置包的内容解压缩到你想要载入 (的位置，例如桌面) 。 你应该有一个名为 *WindowsDefenderATPLocalOnboardingScript.cmd 的文件*。

3. 在设备上打开提升的命令行提示符并运行脚本：
   1. 转到“**开始**”并键入“**cmd**”。
   2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

    ![指向"开始"菜单以管理员角色运行"的窗口。](images/run-as-admin.png)

4.  键入脚本文件的位置。 如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  按 **Enter 键** 或单击"确定 **"。**

若要了解如何手动验证设备是否合规并正确报告传感器数据，请参阅 Microsoft [Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)。

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint 终结点](run-detection-test.md)运行检测测试。

## <a name="configure-sample-collection-settings"></a>配置示例集合设置

对于每个设备，你可以设置一个配置值，以指示当通过 Microsoft 365 Defender 提交文件进行深入分析时是否可以从设备收集示例。

可以通过使用 *regedit* 或创建并运行 .reg 文件，在设备上手动配置 *示例共享* 设置。

通过以下注册表项设置配置：

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

其中，Name 类型是 D-WORD。 可能的值是：

- 0 - 不允许从此设备共享示例
- 1 - 允许从此设备共享所有文件类型

如果注册表项不存在，则默认值为 1。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。

## <a name="offboard-devices-using-a-local-script"></a>使用本地脚本的载出设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从门户获取Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">包</a>：
    1. 在导航窗格中，选择 **"设置** \>  \> **终结点设备管理** \> **""载出"。**
    2. 选择Windows 10或Windows 11操作系统。
    3. 在"**部署方法"** 字段中，选择"**本地脚本"。**
    4. 单击 **下载程序包** 并保存.zip文件。

2. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。

3. 在设备上打开提升的命令行提示符并运行脚本：
   1. 转到“**开始**”并键入“**cmd**”。
   2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

        ![指向"开始"菜单以管理员角色运行"的窗口。](images/run-as-admin.png)

4. 键入脚本文件的位置。 如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5. 按 **Enter 键** 或单击"确定 **"。**

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

## <a name="monitor-device-configuration"></a>监视设备配置

可以按照载入问题疑难解答中的不同[](troubleshoot-onboarding.md)验证步骤验证脚本是否成功完成以及代理是否正在运行。

也可以直接在门户上或使用不同的部署工具进行监视。

### <a name="monitor-devices-using-the-portal"></a>使用门户监视设备

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>。
2. 单击 **"设备清单"。**
3. 验证设备是否显示。

## <a name="related-topics"></a>相关主题
- [使用组策略载入 Windows 设备](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 设备](configure-endpoints-mdm.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
- [在新载入的 Microsoft Defender 终结点设备上运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
