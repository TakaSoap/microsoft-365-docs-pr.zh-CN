---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
description: 在虚拟桌面基础结构 (VDI) 设备上部署配置包，以便将其载入到Microsoft Defender for Endpoint服务。
keywords: 配置虚拟桌面基础结构 (VDI) 设备、vdi、设备管理、配置 Microsoft Defender for Endpoint、终结点
search.product: eADQiWindows 10XVcnh
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
ms.date: 02/14/2022
ms.technology: mde
ms.openlocfilehash: fe86b09588f08a05183de146092b50b5cb530d0e
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64825005"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>载入非永久性虚拟桌面基础结构 (VDI) 设备Microsoft 365 Defender

虚拟桌面基础结构 (VDI) 是一个 IT 基础结构概念，允许最终用户从几乎任何设备 (（如个人计算机、智能手机或平板电脑) ）访问企业虚拟桌面实例，从而无需组织向用户提供物理计算机。 使用 VDI 设备可降低成本，因为 IT 部门不再负责管理、修复和替换物理终结点。 授权用户可以通过安全桌面客户端或浏览器从任何已批准的设备访问相同的公司服务器、文件、应用和服务。

与 IT 环境中的任何其他系统一样，这些系统也应该具有终结点检测和响应 (EDR) 和防病毒解决方案，以防止高级威胁和攻击。


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 虚拟桌面基础结构 (VDI) 设备
- Windows 10、Windows 11、Windows Server 2019、Windows Server 2022、Windows Server 2008R2/2012R2/2016

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)。

 > [!NOTE]
  > **持久性 VDI** - [将持久性 VDI 计算机载](configure-endpoints.md)入Microsoft Defender for Endpoint的处理方式与载入物理计算机（如台式机或笔记本电脑）的方式相同。 组策略、Microsoft Endpoint Manager和其他方法可用于载入永久性计算机。 在Microsoft 365 Defender门户中， (https://security.microsoft.com)载入，选择首选的载入方法，并按照该类型的说明操作。 

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>载入非永久性虚拟桌面基础结构 (VDI) 设备

Defender for Endpoint 支持非永久性 VDI 会话载入。

载入 VDI 实例时，可能会遇到相关挑战。 以下是此方案的典型挑战：

- 即时提前加入短期会话，该会话必须在实际预配之前载入 Defender for Endpoint。
- 设备名称通常会重复用于新会话。

在 VDI 环境中，VDI 实例可以具有较短的生存期。 VDI 设备可以显示在 Defender for Endpoint 门户中，如下所示：


- 每个 VDI 实例的单个门户条目。 如果 VDI 实例已载入到Microsoft Defender for Endpoint并在某些时候删除，然后使用相同的主机名重新创建，则不会在门户中创建表示此 VDI 实例的新对象。 


  > [!NOTE]
  > 在这种情况下，必须在创建会话时配置 *相同的* 设备名称，例如使用无人参与的应答文件。

- 每个设备的多个条目 - 每个 VDI 实例一个。

以下步骤将指导你完成 VDI 设备的载入，并突出显示单个和多个条目的步骤。

> [!WARNING]
> 对于资源配置较低的环境，VDI 启动过程可能会减慢 Defender for Endpoint 传感器的载入速度。

### <a name="for-windows-10-or-windows-11-or-windows-server-2012-r2-and-later"></a>对于Windows 10、Windows 11或Windows Server 2012 R2 及更高版本

> [!NOTE]
> Windows Server 2016和Windows Server 2012 R2 需要先使用载[入Windows服务器](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2012-r2-and-windows-server-2016)中的说明应用安装包，才能使此功能正常工作。

1.  打开从服务载入向导下载的WindowsDefenderATPOnboardingPackage.zip)  (VDI 配置 *包.zip文件* 。 还可以从<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>获取包：

    1. 在导航窗格中，选择 **设置** > **EndpointsDevice** >  **managementOnboarding** > 。

    1. 选择操作系统。

    1.  在 **“部署方法** ”字段 **中，为非持久性终结点选择 VDI 载入脚本**。

    1. 单击 **“下载”包** 并保存.zip文件。

2. 将从.zip文件中提取的 WindowsDefenderATPOnboardingPackage 文件夹中的文件复制到路径 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`下的黄金/母版映像中。
    1. 如果为每个设备实现多个条目 - 每个会话一个，请复制 WindowsDefenderATPOnboardingScript.cmd。
    2. 如果为每个设备实现单个条目，请复制 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript.cmd。

    > [!NOTE]
    > 如果看不到该 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 文件夹，则可能会隐藏该文件夹。 需要从文件资源管理器中选择 **“显示隐藏的文件和文件夹**”选项。

3. 打开“本地组策略编辑器”窗口，导航到 **“计算机配置** \> **”Windows 设置** \> **“脚本** \> **启动**”。

   > [!NOTE]
   > 域组策略也可用于载入非永久性 VDI 设备。

4. 根据要实现的方法，请执行相应的步骤：
    - 对于每个设备的单个条目：

         选择 **“PowerShell 脚本”** 选项卡，然后单击“**添加** (Windows资源管理器将直接在之前复制载入脚本的路径中打开) 。 导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1`。 无需指定另一个文件，因为它会自动触发。

    - 对于每个设备的多个条目：

         选择 **“脚本”** 选项卡，然后单击“**添加** (Windows资源管理器将直接在之前复制载入脚本的路径中打开) 。 导航到载入 bash 脚本 `WindowsDefenderATPOnboardingScript.cmd`。

5. 测试解决方案：
   1. 使用一台设备创建池。
   2. 登录到设备。
   3. 从设备注销。
   4. 使用另一个用户登录到设备。
   5. 根据要实现的方法，请执行相应的步骤：
      - 对于每个设备的单个条目：在Microsoft 365 Defender门户中只检查一个条目。
      - 对于每个设备的多个条目：请在Microsoft 365 Defender门户中检查多个条目。

6. 单击“导航”窗格上的 **“设备”列表** 。

7. 通过输入设备名称并选择 **“设备** ”作为搜索类型来使用搜索函数。

## <a name="for-downlevel-skus-windows-server-2008-r2"></a>对于下层 SKU (Windows Server 2008 R2) 

> [!NOTE]
> 如果为需要 MMA 的 Windows Server 2016 和 Windows Server 2012 R2 运行上一个Microsoft Defender for Endpoint，则这些有关其他Windows服务器版本的说明也适用。 Microsoft Defender for Endpoint[中的服务器迁移方案中](/microsoft-365/security/defender-endpoint/server-migration)介绍了迁移到新的统一解决方案的说明。

> [!NOTE]
> 只有当目标是实现“每个设备的单个条目”时，以下注册表才相关。

1. 将注册表值设置为：

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    或使用命令行：

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. 按照 [服务器载入过程进行操作](configure-server-endpoints.md)。 

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>更新非永久性虚拟桌面基础结构 (VDI) 映像

为了轻松地将更新部署到 VDI 中运行的 VM，我们缩短了本指南，重点介绍如何快速轻松地在计算机上获取更新。 不再需要定期创建和密封黄金映像，因为更新将扩展到主机服务器上的组件位，然后在启用时直接下载到 VM。

有关详细信息，请遵循虚拟[桌面基础结构 (VDI) 环境中Microsoft Defender 防病毒的部署指南](/security/defender-endpoint/deployment-vdi-microsoft-defender-antivirus)。


## <a name="related-topics"></a>相关主题
- [使用组策略载入 Windows 设备](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 设备](configure-endpoints-mdm.md)
- [使用本地脚本载入 Windows 设备](configure-endpoints-script.md)
- [排查Microsoft Defender for Endpoint载入问题](troubleshoot-onboarding.md)
