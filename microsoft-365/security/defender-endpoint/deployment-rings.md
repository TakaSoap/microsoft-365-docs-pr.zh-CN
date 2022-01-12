---
title: 在圈中部署 Microsoft Defender for Endpoint
description: 了解如何在圈中部署 Microsoft Defender for Endpoint
keywords: 部署， 圈， 评估， 试点， 预览体验成员快， 预览体验成员 - 慢， 设置， 载入， 阶段， 部署， 部署， 采用， 配置
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
ms.openlocfilehash: a7a9673591f4d77197390541a58169a58b04fe91
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61872425"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>在圈中部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

可以使用基于圈的部署方法部署 Microsoft Defender for Endpoint。

可以在以下方案中应用部署圈：

- [新部署](#new-deployments)
- [现有部署](#existing-deployments)

## <a name="new-deployments"></a>新部署

![部署圈的图像。](images/deployment-rings.png)

基于圈的方法用于标识要载入的一组终结点，并验证是否满足特定条件，然后再继续将服务部署到更大的设备集。 你可以定义每个圈的退出条件，并确保它们满足，然后再移动到下一个圈。

采用基于圈的部署有助于减少推出服务时可能出现的潜在问题。 通过先试用一定数量的设备，你可以识别潜在问题并减少可能出现的潜在风险。

表 1 提供了您可能使用的部署圈的示例。

**表 1：**

<br>

****

|部署环|说明|
|---|---|
|评估|圈 1：标识 50 个系统用于试点测试|
|试点|圈 2：标识生产环境中的下 50-100 个终结点|
|完全部署|圈 3：以较大增量向其余环境推出服务|
|

### <a name="exit-criteria"></a>退出条件

这些圈的退出条件集示例包括：

- 设备显示在设备清单列表中
- 警报显示在仪表板中
- [运行检测测试](run-detection-test.md)
- [在设备上运行模拟攻击](attack-simulations.md)

### <a name="evaluate"></a>评估

确定环境中要载入服务的少量测试计算机。 理想情况下，这些计算机将少于 50 个终结点。

### <a name="pilot"></a>试点

Microsoft Defender for Endpoint 支持可载入到服务的各种终结点。 在此圈中，确定要载入的几个设备，并基于定义的退出条件，决定继续下一个部署圈。

下表显示了受支持的终结点以及可用于将设备载入服务的相应工具。

| 端点     | 部署工具                       |
|--------------|------------------------------------------|
| **Windows**  |  [本地脚本 (最多 10 台设备) ](configure-endpoints-script.md) <br> 注意：如果要在生产环境中部署 10 台以上设备，请改为使用组策略方法或下面列出的其他支持的工具。<br>  [组策略](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ 移动设备管理器](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 脚本](configure-endpoints-vdi.md) <br> [与 Microsoft Defender for Cloud 集成](configure-server-endpoints.md#integration-with-azure-defender)  |
| **macOS**    | [本地脚本](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [移动设备管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [本地脚本](linux-install-manually.md) <br> [百分百](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft Endpoint Manager](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               |

### <a name="full-deployment"></a>完全部署

在此阶段，可以使用规划 [部署材料来帮助](deployment-strategy.md) 你规划部署。

使用以下材料选择最适合贵组织的适用于终结点的 Microsoft Defender 体系结构。

|**项目**|**说明**|
|:-----|:-----|
|[![适用于终结点部署策略的 Microsoft Defender 缩略图。](images/mde-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) | 体系结构资料有助于规划如下体系结构的部署： <ul><li> 云-本机 </li><li> 协同管理 </li><li> 本地</li><li>评估和本地载入</li></ul>

## <a name="existing-deployments"></a>现有部署

### <a name="windows-endpoints"></a>Windows终结点

对于 Windows 和/或 Windows 服务器，通过使用安全更新验证计划 (**SUVP**) 在修补星期二)  (之前选择多台计算机进行测试。

有关更多信息，请参阅：

- [什么是安全更新验证计划](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [软件更新验证计划与Microsoft 恶意软件防护中心 - TwC 互动时间线第 4 部分](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>非Windows终结点

使用 macOS 和 Linux，可以使用几个系统，在 Beta 渠道中运行。

> [!NOTE]
> 理想情况下，至少一个安全管理员和一个开发人员，以便你能够在生成之前找到兼容性、性能和可靠性问题，然后再进入当前频道。

通道的选择决定了提供给你的设备的更新的类型和频率。 Beta 版设备是接收更新和新功能的第一批设备，随后是预览版，最后是当前设备。

![预览体验成员圈的图像。](images/insider-rings.png)

为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用 Beta 或预览版。

> [!WARNING]
> 在初始安装后切换通道需要重新安装产品。 若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。
