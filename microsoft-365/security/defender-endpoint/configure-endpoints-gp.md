---
title: 通过Windows策略将设备载入 Microsoft Defender for Endpoint
description: 使用组策略在 Windows部署配置包，以便它们可以载入服务。
keywords: 使用组策略配置设备， 设备管理， 为终结点设备配置 Microsoft Defender， 载入适用于终结点设备的 Microsoft Defender， 组策略
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
ms.date: 09/16/2021
ms.technology: mde
ms.openlocfilehash: 51950846b1e445bf9fecb3111e827e1ca9b6d1e4
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962959"
---
# <a name="onboard-windows-devices-using-group-policy"></a>使用组策略载入 Windows 设备 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**适用于：**

- 组策略
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)。

> [!NOTE]
> 若要使用组策略 (GP) 更新来部署程序包，必须在 Windows Server 2008 R2 或更高版本上。
>
> 对于 Windows Server 2019 和 Windows Server 2022，可能需要将 NT AUTHORITY\Well-Known-System-Account 替换为组策略首选项创建的 XML 文件的 NT AUTHORITY\SYSTEM。

> [!NOTE]
> 如果你对 Windows Server 2012 R2 和 2016 使用新的统一 Microsoft Defender for Endpoint 解决方案，请确保你正在使用中央存储中的最新 ADMX 文件，以访问正确的 Microsoft Defender for Endpoint 策略选项。 请参考 [如何创建](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)和管理集中存储组策略管理模板Windows下载最新文件 **以用于Windows 10**。

请查看[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)或[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署 Defender for Endpoint 中的各种路径。

1. 打开 GP 配置文件 () `WindowsDefenderATPOnboardingPackage.zip` 从服务载入向导下载的文件。 还可以从应用门户获取<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender包</a>：

    1. 在导航窗格中，选择 **"设置**  >  **终结点**  >  **设备管理**   >  **载入"。**

    1. 选择操作系统。

    1. 在"**部署方法"** 字段中，选择"**组策略"。**

    1. 单击 **下载程序包** 并保存.zip文件。

2. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个称为 *OptionalParamsPolicy* 的文件夹和 *文件 WindowsDefenderATPOnboardingScript.cmd*。

3. 若要创建新的 GPO，请打开组策略管理控制台 [ (](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC) ，右键单击要配置的组策略对象，**然后单击新建。** 在显示的对话框中输入新 GPO 的名称，然后单击"确定 **"。**

4. 打开组 [策略](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

5. 在组 **策略管理编辑器中**，转到"**计算机配置**"，然后转到"**首选项**"，然后转到"**控制面板设置"。**

6. 右键单击 **计划任务**，指向新建 **，然后单击** 立即任务 (**至少Windows 7)**。

7. 在打开 **的任务** 窗口中，转到常规 **选项卡**。在 **"安全选项"** 下，单击 **"更改用户或组**"，然后键入"系统"，然后单击"**检查名称**"，然后单击"确定 **"。** NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。

8. Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box.

9. 在"名称"字段中，键入计划任务策略的适当名称 (例如，Defender for Endpoint Deployment) 。

10. 转到操作 **选项卡，** 然后选择新建 **...** 确保在 **"操作"** 字段中选择了"启动 **程序** "。 使用共享 *WindowsDefenderATPOnboardingScript.cmd* 文件的文件服务器的完全限定域名 (FQDN) 输入 UNC 路径。

11. 选择 **"确定** "并关闭任何打开的 GPMC 窗口。

12. 若要将 GPO 链接到组织单位 (OU) ，请右键单击并选择"链接现有 **GPO"。** 在显示的对话框中，选择要链接的组策略对象。 单击“确定”。

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的适用于终结点 [设备的 Defender](run-detection-test.md)运行检测测试。

## <a name="additional-defender-for-endpoint-configuration-settings"></a>其他 Defender for Endpoint 配置设置

对于每个设备，你可以说明当通过请求提交文件进行深入分析Microsoft 365 Defender是否可以从设备收集示例。

可以使用组策略 (GP) 配置设置，例如深入分析功能中使用的示例共享的设置。

### <a name="configure-sample-collection-settings"></a>配置示例集合设置

1. 在 GP 管理设备上，从配置包复制以下文件：

    - 将 _AtpConfiguration.admx_ 复制到 _\\ C：Windows \\ PolicyDefinitions_

    - 将 _AtpConfiguration.adml_ 复制到 _\\ C：Windows \\ PolicyDefinitions \\ en-US_

    如果对组策略管理模板使用中央存储 [，](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)请从配置包中复制以下文件：

    - 将 _AtpConfiguration.admx_ 复制到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 策略 \\ 策略Definitions_

    - 将 _AtpConfiguration.adml_ 复制到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 策略 \\ 策略Definitions \\ en-US_

2. 打开组 [策略管理控制台，](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)右键单击要配置的 GPO，**然后单击编辑。**

3. 在组 **策略管理编辑器中**，转到计算机 **配置**。

4. 单击 **"策略**"，然后单击 **"管理模板"。**

5. 单击 **Windows组件**"，然后单击 **Windows Defender ATP"。**

6. 选择从设备启用或禁用示例共享。

> [!NOTE]
> 如果未设置值，则默认值为启用示例集合。

## <a name="other-recommended-configuration-settings"></a>其他建议的配置设置

### <a name="update-endpoint-protection-configuration"></a>更新终结点保护配置

配置载入脚本后，继续编辑相同的组策略以添加终结点保护配置。 从运行 Windows 10 或 Server 2019、Windows 11 或 Windows Server 2022 的系统执行组策略编辑，以确保具有所有必需的 Microsoft Defender 防病毒 功能。 你可能需要关闭并重新打开组策略对象以注册 Defender ATP 配置设置。

所有策略都位于 下 `Computer Configuration\Policies\Administrative Templates` 。

**策略位置：\Windows** Components\Windows Defender ATP

Policy|Setting
---|---
Enable\Disable Sample 集合|已启用 - 选中"启用计算机上的示例集合"

<br>

**策略位置：\Windows** Components\Microsoft Defender 防病毒

Policy|Setting
---|---
配置对可能不需要的应用程序的检测|已启用、阻止

<br>

**策略位置：\Windows** Components\Microsoft Defender 防病毒\MAPS

Policy|Setting
---|---
加入 Microsoft MAPS|已启用、高级 MAPS
需要进一步分析时发送文件示例 | 已启用，发送安全示例

<br>

**策略位置：\Windows** Components\Microsoft Defender 防病毒\Real-time Protection

Policy|Setting
---|---
关闭实时保护|已禁用
打开行为监视|已启用
扫描所有下载的文件和附件|已启用
监视您的计算机上的文件和程序活动|已启用

<br>

**策略位置：\Windows** Components\Microsoft Defender 防病毒\Scan

这些设置配置终结点的定期扫描。 建议在性能允许的情况下执行每周快速扫描。

Policy|Setting
---|---
在运行计划扫描之前检查最新的病毒和间谍软件安全智能 |已启用

<br>

**策略位置：\Windows** Components\Microsoft Defender 防病毒\Microsoft Defender 攻击防护\Attack Surface Reduction

从自定义攻击面减少规则获取攻击面减少 GUID [的当前列表](customize-attack-surface-reduction.md)

1. 打开配置 **攻击面减少** 策略。

1. 选择“**已启用**”。

1. 选择" **显示"** 按钮。

1. 在"值名称"字段中 **添加** 值为 2 的每个 GUID。

   这将仅为审核设置每个设置。

   ![攻击面减少配置的图像。](images/asr-guid.png)

Policy|Setting
---|---
配置受控文件夹访问权限| 已启用，审核模式

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。

## <a name="offboard-devices-using-group-policy"></a>使用组策略的载出设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从应用程序门户获取Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">包</a>：

    1. 在导航窗格中，**选择"设置**  >  **终结点**  >  **设备管理**  >  **""载出"。**

    1. 选择操作系统。
    
    1. 在"**部署方法"** 字段中，选择"**组策略"。**

    1. 单击 **下载程序包** 并保存.zip文件。

2. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。

3. 打开组 [策略](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

4. 在组 **策略管理编辑器中**，转到"**计算机配置"，然后** 转到"**首选项**"，然后转到"**控制面板设置"。**

5. 右键单击 **"计划任务"，** 指向 **"新建"，** 然后单击"**立即任务"。**

6. 在打开 **的任务** 窗口中，转到常规 **选项卡** 。在"安全选项"下 ("BUILTIN\SYSTEM) **本地系统用户帐户**。

7. Select **Run whether user is logged on or not and** check the Run with highest **privileges** check-box.

8. 在"名称"字段中，键入计划任务策略的适当名称 (例如，Defender for Endpoint Deployment) 。

9. 转到"操作 **"** 选项卡，然后选择"新建 **..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。 使用共享 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* 文件的文件服务器的完全限定域名 (FQDN) 输入 UNC 路径。

10. 选择 **"确定** "并关闭任何打开的 GPMC 窗口。

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

## <a name="monitor-device-configuration"></a>监视设备配置

借助组策略，无法监视设备上策略的部署。 可以直接在门户上或使用不同的部署工具进行监视。

## <a name="monitor-devices-using-the-portal"></a>使用门户监视设备

1. 转到"Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户"。</a>
2. 单击 **"设备清单"。**
3. 验证设备是否显示。

> [!NOTE]
> 设备可能需要几天时间才能开始在 **"设备"列表上显示**。 这包括将策略分发到设备所花的时间、用户登录之前所花的时间以及终结点开始报告所花的时间。

## <a name="setup-defender-av-policies"></a>设置 Defender AV 策略

创建新的组策略，或将这些设置与其他策略分组。 这依赖于客户环境，以及他们希望如何通过面向不同组织单位和 OUS 来 (服务) 。

1. 选择 GP 或新建 GP 后，编辑 GP。

2. 浏览到 **计算机配置**  >  **策略**  >  **管理模板**  >  **Windows组件Microsoft Defender 防病毒**  >    >  **实时保护**。

    :::image type="content" source="images/realtime-protect.png" alt-text="实时保护。":::

1. 在"隔离"文件夹中，配置从"隔离"文件夹中删除项目。

    :::image type="content" source="images/removal-items-quarantine1.png" alt-text="删除项目隔离文件夹。":::

    :::image type="content" source="images/config-removal-items-quarantine2.png" alt-text="配置删除隔离。":::

4. 在"扫描"文件夹中，配置扫描设置。

    :::image type="content" source="images/gpo-scans.png" alt-text="gpo 扫描。":::

### <a name="monitor-all-files-in-real-time-protection"></a>监视实时保护中的所有文件

浏览到 **计算机配置** \> **策略** \> **管理模板** \> **Windows组件Microsoft Defender 防病毒** \>  \> **实时保护**。

:::image type="content" source="images/config-monitor-incoming-outgoing-file-act.png" alt-text="配置对传入传出文件活动的监视。":::

### <a name="configure-windows-defender-smartscreen-settings"></a>配置Windows Defender SmartScreen 设置

1. 浏览到 \>  \> SmartScreen 资源管理器 **中的** 计算机 \> **Windows配置** Windows Defender \> **模板** \> 。

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="配置 Windows Defender 智能屏幕资源管理器。":::
 
2. 浏览到 **计算机配置**  >  **策略**  >  **SmartScreen**  >  **Windows组件**  >  **Windows Defender管理**  >  **Microsoft Edge。**

    :::image type="content" source="images/config-windows-def-smartscr-explorer.png" alt-text="配置 Windows Defender 智能屏幕边缘。":::

### <a name="configure-potentially-unwanted-applications"></a>配置可能不需要的应用程序

浏览到 **计算机配置** \> **策略** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒。**

:::image type="content" source="images/config-potential-unwanted-apps.png" alt-text="配置可能不需要的应用。":::

:::image type="content" source="images/config-potential-unwanted-apps2.png" alt-text="配置可能。":::

### <a name="configure-cloud-deliver-protection-and-send-samples-automatically"></a>配置云提供保护并自动发送示例

浏览到 **计算机配置** \> **策略** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒** \> **MAPS**。

:::image type="content" source="images/gpo-maps1.png" alt-text="maps。":::

:::image type="content" source="images/gpo-maps-block-atfirst-sight.png" alt-text="阻止首次看到。":::

:::image type="content" source="images/gpo-maps-join-ms-maps.png" alt-text="加入 Microsoft 地图。":::

:::image type="content" source="images/send-file-sample-further-analysis-require.png" alt-text="需要进一步分析时发送文件示例。":::

### <a name="check-for-signature-update"></a>检查签名更新

浏览到 **计算机配置** \> **策略** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒** \> **签名更新**

:::image type="content" source="images/signature-update-1.png" alt-text="签名更新。":::

:::image type="content" source="images/signature-update-2.png" alt-text="签名定义更新。":::

### <a name="configure-cloud-deliver-timeout-and-protection-level"></a>配置云提供超时和保护级别

浏览到 **计算机配置** \> **策略** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒** \> **MpEngine**。
将云保护级别策略配置为默认Microsoft Defender 防病毒 **阻止策略时**，将禁用该策略。 这是将保护级别设置为 Windows 默认值所需的操作。

:::image type="content" source="images/config-extended-cloud-check.png" alt-text="配置扩展云检查。":::

:::image type="content" source="images/cloud-protection-level.png" alt-text="配置云保护级别。":::

## <a name="related-topics"></a>相关主题
- [使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 设备](configure-endpoints-mdm.md)
- [使用本地脚本载入 Windows 设备](configure-endpoints-script.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
- [对新载入的适用于终结点的 Microsoft Defender 设备运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
