---
title: 设置Microsoft Defender for Endpoint部署
description: 了解如何为Microsoft Defender for Endpoint设置部署
keywords: 部署、安装、许可验证、租户配置、网络配置
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
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bae66223494d8de98737516cef1a2c407d7d1a6a
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783513"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>设置Microsoft Defender for Endpoint部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

部署 Defender for Endpoint 是一个三阶段过程：

|[![部署阶段 - 准备。](images/phase-diagrams/prepare.png#lightbox)](prepare-deployment.md)<br>[阶段 1：准备](prepare-deployment.md) | ![部署阶段 - 设置](images/phase-diagrams/setup.png#lightbox)<br>阶段 2：设置 | [![部署阶段 - 载入](images/phase-diagrams/onboard.png#lightbox)](onboarding.md)<br>[阶段 3：开始使用](onboarding.md)|
|---|---|---|
||*你在这里！*||

你目前处于设置阶段。

在此部署方案中，你将指导完成以下步骤：

- 许可验证
- 租户配置
- 网络配置

> [!NOTE]
> 为了指导你完成典型部署，此方案仅涵盖Microsoft Endpoint Configuration Manager的使用。 Defender for Endpoint 支持使用其他载入工具，但不会在部署指南中介绍这些方案。 有关详细信息，请参阅[要Microsoft Defender for Endpoint的载入设备](onboard-configure.md)。

## <a name="check-license-state"></a>检查许可证状态

检查许可证状态以及是否已正确预配，可通过管理中心或 **通过Microsoft Azure门户** 完成。

1. 若要查看许可证，请转到 **Microsoft Azure门户** 并导航到 [Microsoft Azure门户许可证部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   :::image type="content" source="images/atp-licensing-azure-portal.png" alt-text="“Azure 许可”页" lightbox="images/atp-licensing-azure-portal.png":::

1. 或者，在管理中心，导航到 **计**\>费 **订阅**。

    在屏幕上，你将看到所有预配的许可证及其当前 **状态**。

    :::image type="content" source="images/atp-billing-subscriptions.png" alt-text="“计费许可证”页" lightbox="images/atp-billing-subscriptions.png":::

## <a name="cloud-service-provider-validation"></a>云服务提供商验证

若要获取向公司预配许可证的访问权限，以及要检查许可证的状态，请转到管理中心。

1. 在 **合作伙伴门户** 中，选择 **“管理服务”> Office 365**。

2. 单击 **合作伙伴门户** 链接将 **代表** 管理员打开选项，并允许你访问客户管理中心。

   :::image type="content" source="images/atp-O365-admin-portal-customer.png" alt-text="Office 365管理门户" lightbox="images/atp-O365-admin-portal-customer.png":::

## <a name="tenant-configuration"></a>租户配置

加入Microsoft Defender for Endpoint很容易。 在导航菜单中，选择“终结点”部分下的任何项，或任何Microsoft 365 Defender功能（如事件、搜寻、操作中心或威胁分析）以启动载入过程。

在 Web 浏览器中，导航到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>。

## <a name="data-center-location"></a>数据中心位置
Microsoft Defender for Endpoint将数据存储和处理与[Microsoft 365 Defender使用的相同位置](/microsoft-365/security/defender/m365d-enable)。 如果尚未打开Microsoft 365 Defender，则载入到Microsoft Defender for Endpoint也将启用Microsoft 365 Defender，并根据活动位置自动选择新的数据中心位置Microsoft 365 安全服务。 屏幕上显示了所选的数据中心位置。

## <a name="network-configuration"></a>网络配置

如果组织不需要终结点使用代理访问 Internet，请跳过此部分。

Microsoft Defender for Endpoint 感官方案需要 Microsoft Windows HTTP （WinHTTP） 报告感官数据，并与 Microsoft Defender for Endpoint 服务进行通信。 嵌入Microsoft Defender for Endpoint传感器使用 LocalSystem 帐户在系统上下文中运行。 该感官服务使用 Microsoft Windows HTTP Services （WinHTTP） 与 Microsoft Defender for Endpoint 云服务启用通信。 WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用以下发现方法发现代理服务器：

- **自动发现方法**：
  - 透明代理
  - Web 代理自动发现协议 (WPAD)

  如果已在网络拓扑中实现透明代理或 WPAD，则无需使用特殊配置设置。 有关代理中Microsoft Defender for Endpoint URL 排除的详细信息，请参阅本文档中的[代理服务 URL](production-deployment.md#proxy-service-urls) 部分，了解 URL 允许列表或[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

- **手动静态代理配置**：
  - 基于注册表的配置
  - 使用 netsh 命令配置的 WinHTTP

    仅适用于稳定拓扑 (中的桌面，例如：同一代理) 背后的公司网络中的桌面。

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基于注册表的静态代理手动配置代理服务器

配置基于注册表的静态代理，以便仅允许Microsoft Defender for Endpoint传感器报告诊断数据，并在不允许计算机连接到 Internet 时与Microsoft Defender for Endpoint服务通信。 静态代理可以通过组策略 (GP) 配置。 可以在以下位置找到组策略：

- 管理模板\>Windows组件\>数据收集和预览版本\>配置已连接用户体验和遥测服务的身份验证代理使用情况
- 将其设置为 **“已启用**”，然后选择 **“禁用经过身份验证的代理使用情况**”

1. 打开组策略管理控制台。
2. 根据组织做法创建策略或编辑现有策略。
3. 编辑组策略并导航到 **管理模板\>Windows组件\>数据收集和预览版本\>配置已连接用户体验和遥测服务的身份验证代理使用情况**。

   :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="与使用策略配置相关的选项" lightbox="images/atp-gpo-proxy1.png":::

4. 选择“**已启用**”。
5. 选择 **“禁用经过身份验证的代理使用”。**
6. 导航到 **管理模板\>Windows组件\>数据收集和预览版本配置连接的\>用户体验和遥测**。

   :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="与配置连接的用户体验和遥测相关的选项" lightbox="images/atp-gpo-proxy2.png":::

7. 选择“**已启用**”。
8. 输入 **代理服务器名称**。

策略将注册表项 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的两个注册表值 `TelemetryProxyServer` 设置为 REG\u SZ，`DisableEnterpriseAuthProxy` 设置为 REG\u DWORD。

注册表值 `TelemetryProxyServer` 采用以下字符串格式：

```text
<server name or ip>:<port>
```

例如：10.0.0.6:8080

此注册表值 `DisableEnterpriseAuthProxy` 应当设置为 1。

### <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用 netsh 命令手动配置代理服务器

使用 netsh 配置系统范围的静态代理。

> [!NOTE]
>
> - 这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。
> - 例如，正在更改拓扑的笔记本电脑 (：从办公室到家庭) 将因 netsh 而发生故障。 使用基于注册表的静态代理配置。

1. 打开提升的命令行:
    1. 转到“**开始**”并键入“**cmd**”。
    1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，再按 **Enter**：

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例如：netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>下层设备的代理配置

Down-Level设备包括 Windows 7 SP1 和 Windows 8.1 工作站以及 Windows Server 2008 R2，以及以前使用Microsoft Monitoring Agent载入的其他服务器操作系统。 这些操作系统将将代理配置为 Microsoft 管理代理的一部分，以处理从终结点到 Azure 的通信。 有关如何在这些设备上配置代理的信息，请参阅 Microsoft 管理代理快速部署指南。

### <a name="proxy-service-urls"></a>代理服务 URL

仅当有Windows 10、版本 1803 或Windows 11设备时，才需要包含 v20 的 URL。 例如，`us-v20.events.data.microsoft.com`仅当设备处于Windows 10版本 1803 或Windows 11时才需要。

如果代理或防火墙阻止匿名流量，因为Microsoft Defender for Endpoint传感器正在从系统上下文进行连接，请确保在列出的 URL 中允许匿名流量。

以下可下载电子表格列出了网络必须能够连接到的服务及其关联 URL。 确保没有防火墙或网络筛选规则会拒绝对这些 URL 的访问，或者可能需要专门为它们创建 *允许* 规则。

<br>

****


|域列表的电子表格| 说明|
|---|---|
|商业客户Microsoft Defender for Endpoint URL 列表| 针对商业客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint Gov/GCC/DoD 的 URL 列表 | 适用于 Gov/GCC/DoD 客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

## <a name="next-step"></a>后续步骤

[![**阶段 3：载入**。](images/onboard.png#lightbox)] <br> [阶段 3：载入](onboarding.md)：将设备载入服务，以便Microsoft Defender for Endpoint服务可以从中获取传感器数据。
