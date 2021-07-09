---
title: 使用本地脚本载入 Windows 10 设备
description: 使用本地脚本在设备上部署配置包，以允许将设备载入服务。
keywords: 使用本地脚本配置设备， 设备管理， 为终结点设备配置 Microsoft Defender
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e15a02753c7a1b346021a4351af24b8fd28315da
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339642"
---
# <a name="onboard-the-windows-10-devices-using-a-local-script"></a>使用Windows 10脚本载入新设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

还可以手动将个别设备载入到 Defender for Endpoint。 在承诺载入网络内的所有设备之前，你可能希望先在测试服务时这样做。

> [!IMPORTANT]
> 此脚本已优化为在最多 10 台设备上使用。
>
> 若要大规模部署，请使用 [其他部署选项](configure-endpoints.md)。 例如，可以使用在使用组策略载入 Windows 10 设备中提供的脚本，将载入脚本部署到生产中的 10[多个设备](configure-endpoints-gp.md)。

## <a name="onboard-devices"></a>载入设备 

[![显示各种部署路径的 PDF 图像](images/onboard-script.png)](images/onboard-script.png#lightbox)


请查看[PDF 或](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)查看部署 Defender for Endpoint 中的各种路径。 


1.  打开 GP 配置包.zip文件 *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从 Defender 门户Microsoft 365[程序包](https://security.microsoft.com/)：

    1. 在导航窗格中，**选择"设置**  >  **终结点**  >  **设备管理**  >  **载入"。**

    1. 选择Windows 10操作系统。

    1. 在"**部署方法"** 字段中，选择"**本地脚本"。**

    1. 单击 **下载程序包** 并保存.zip文件。

  
2.  将配置包的内容解压缩到你想要载入 (的位置，例如桌面) 。 你应该有一个名为 *WindowsDefenderATPLocalOnboardingScript.cmd 的文件*。

3.  在设备上打开提升的命令行提示符并运行脚本：

    1.  转到“**开始**”并键入“**cmd**”。

    1.  右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

        ![指向"开始"菜单以管理员角色运行"的窗口](images/run-as-admin.png)

4.  键入脚本文件的位置。 如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*

5.  按 **Enter 键** 或单击"确定 **"。**

若要了解如何手动验证设备是否合规并正确报告传感器数据，请参阅 Microsoft [Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)。


>[!TIP]
> 载入设备后，你可以选择运行检测测试来验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint 终结点](run-detection-test.md)运行检测测试。

## <a name="configure-sample-collection-settings"></a>配置示例集合设置
对于每个设备，你可以设置一个配置值，以指示当通过 Microsoft 365 Defender 请求提交文件进行深入分析时是否可以从设备收集示例。

可以使用 *regedit* 或创建并运行 *.reg* 文件，在设备上手动配置示例共享设置。  

通过以下注册表项设置配置：

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
其中：<br>
名称类型为 D-WORD。 <br>
可能的值是：
- 0 - 不允许从此设备共享示例
- 1 - 允许从此设备共享所有文件类型

如果注册表项不存在，则默认值为 1。


## <a name="offboard-devices-using-a-local-script"></a>使用本地脚本的载出设备
出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。

1. 从门户获取Microsoft 365 Defender[包](https://security.microsoft.com/)：

    1. 在导航窗格中，**选择"设置**  >    >  **终结点设备管理**  > **""载出"。**

    1. 选择Windows 10操作系统。

    1. 在"**部署方法"** 字段中，选择"**本地脚本"。**

    1. 单击 **下载程序包** 并保存.zip文件。

2. 将文件.zip到设备可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。

3.  在设备上打开提升的命令行提示符并运行脚本：

    1.  转到“**开始**”并键入“**cmd**”。

    1.  右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

        ![指向"开始"菜单以管理员角色运行"的窗口](images/run-as-admin.png)

4.  键入脚本文件的位置。 如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  按 **Enter 键** 或单击"确定 **"。**

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。


## <a name="monitor-device-configuration"></a>监视设备配置
可以按照载入问题疑难解答中的不同[](troubleshoot-onboarding.md)验证步骤验证脚本是否成功完成以及代理是否正在运行。

也可以直接在门户上或使用不同的部署工具进行监视。

### <a name="monitor-devices-using-the-portal"></a>使用门户监视设备
1. 转到Microsoft 365 Defender门户。

2. 单击 **"设备清单"。**

3. 验证设备是否显示。


## <a name="related-topics"></a>相关主题
- [使用Windows 10载入设备](configure-endpoints-gp.md)
- [使用Windows 10载入Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 10 设备](configure-endpoints-mdm.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
- [在新载入的 Microsoft Defender 终结点设备上运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
