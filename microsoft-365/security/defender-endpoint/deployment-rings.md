---
title: 在环中部署Microsoft Defender for Endpoint
description: 了解如何在环中部署Microsoft Defender for Endpoint
keywords: 部署， 环， 评估， 试点， 内部快速， 内部人员慢， 设置， 载入， 阶段， 部署， 部署， 采用， 配置
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 41f47720582f715e6c5d28276ddd87777e9669d5
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783372"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>在环中部署Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

可以使用基于环的部署方法来部署Microsoft Defender for Endpoint。

可在以下方案中应用部署环：

- [新部署](#new-deployments)
- [现有部署](#existing-deployments)

## <a name="new-deployments"></a>新部署

:::image type="content" source="images/deployment-rings.png" alt-text="部署环" lightbox="images/deployment-rings.png":::

基于环的方法是确定一组要载入的终结点，并验证是否满足某些条件，然后再继续将服务部署到更大的设备集。 你可以为每个环定义退出条件，并确保在转到下一个环之前满足这些条件。

采用基于环的部署有助于减少在推出服务时可能出现的潜在问题。 通过先试用一定数量的设备，可以识别潜在问题并缓解可能出现的潜在风险。

表 1 提供了可能使用的部署环的示例。

**表 1**：

<br>

****

|部署环|说明|
|---|---|
|评估|环 1：确定 50 个用于试点测试的系统|
|试点|环 2：确定生产环境中的下一个 50-100 终结点|
|完全部署|环 3：以较大的增量向其他环境推出服务|
|

### <a name="exit-criteria"></a>退出条件

这些环的退出条件示例集可以包括：

- 设备显示在设备清单列表中
- 警报显示在仪表板中
- [运行检测测试](run-detection-test.md)
- [对设备运行模拟攻击](attack-simulations.md)

### <a name="evaluate"></a>评估

识别环境中要载入到服务的少量测试计算机。 理想情况下，这些计算机将少于 50 个终结点。

### <a name="pilot"></a>试点

Microsoft Defender for Endpoint支持可以载入到服务的各种终结点。 在此环中，根据定义的退出条件，确定要加入的多个设备，并决定继续下一个部署圈。

下表显示了支持的终结点以及可用于将设备载入服务的相应工具。

| 端点     | 部署工具                       |
|--------------|------------------------------------------|
| **Windows**  |  [本地脚本 (多达 10 台设备) ](configure-endpoints-script.md) <br> 注意：如果要在生产环境中部署 10 台以上的设备，请改用组策略方法或下面列出的其他受支持工具。<br>  [组策略](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/移动设备管理器](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 脚本](configure-endpoints-vdi.md) <br> [与 Microsoft Defender for Cloud 集成](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)  |
| **macOS**    | [本地脚本](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [移动设备管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [本地脚本](linux-install-manually.md) <br> [木偶](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft Endpoint Manager](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               |

### <a name="full-deployment"></a>完全部署

在此阶段，可以使用 [计划部署](deployment-strategy.md) 材料来帮助你规划部署。

使用以下材料选择适合组织的Microsoft Defender for Endpoint体系结构。

|**项**|**说明**|
|:-----|:-----|
|[:::image type="content" source="images/mde-deployment-strategy.png" alt-text="部署Microsoft Defender for Endpoint策略" lightbox="images/mde-deployment-strategy.png":::](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) | 体系结构资料有助于规划如下体系结构的部署： <ul><li> 云-本机 </li><li> 协同管理 </li><li> 本地</li><li>评估和本地载入</li></ul>

## <a name="existing-deployments"></a>现有部署

### <a name="windows-endpoints"></a>Windows终结点

对于Windows和/或Windows服务器，请使用 **(SUVP) 的安全更新验证程序**，在周二) 修补程序之前，选择几台计算机 (提前进行测试。

有关详细信息，请参阅：

- [什么是安全更新验证计划](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [软件更新验证计划和Microsoft 恶意软件防护中心建立 - TwC 交互式时间线第 4 部分](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>非Windows终结点

借助 macOS 和 Linux，可以使用多个系统并在 Beta 通道中运行。

> [!NOTE]
> 理想情况下，至少有一个安全管理员和一个开发人员，以便在生成进入当前通道之前，能够找到兼容性、性能和可靠性问题。

通道的选择决定了提供给设备的更新的类型和频率。 Beta 中的设备是第一个接收更新和新功能的设备，其次是预览版，最后是 Current。

:::image type="content" source="images/insider-rings.png" alt-text="内部圈" lightbox="images/insider-rings.png":::


为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用 Beta 或预览版。

> [!WARNING]
> 在初始安装后切换通道需要重新安装产品。 若要切换产品通道：卸载现有包，重新配置设备以使用新通道，并按照本文档中的步骤从新位置安装包。
