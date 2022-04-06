---
title: 设置适用于终结点的 Microsoft Defender 部署
description: 了解如何设置 Microsoft Defender for Endpoint 的部署
keywords: 部署， 设置， 许可验证， 租户配置， 网络配置
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
ms.openlocfilehash: 8e905db8ba5e868a9913c785bd7f9bc0cc67b39a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472674"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>设置适用于终结点的 Microsoft Defender 部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

部署适用于终结点的 Defender 的过程分三个阶段：

|[![部署阶段 - 准备。](images/phase-diagrams/prepare.png#lightbox)](prepare-deployment.md)<br>[阶段 1：准备](prepare-deployment.md) | ![部署阶段 - 设置](images/phase-diagrams/setup.png#lightbox)<br>阶段 2：设置 | [![部署阶段 - 载入](images/phase-diagrams/onboard.png#lightbox)](onboarding.md)<br>[阶段 3：开始使用](onboarding.md)|
|---|---|---|
||*你在这里！*||

您当前处于设置阶段。

在此部署方案中，将指导你完成以下步骤：

- 许可验证
- 租户配置
- 网络配置

> [!NOTE]
> 为了引导您完成典型部署，此方案将仅涉及 Microsoft Endpoint Configuration Manager。 Defender for Endpoint 支持使用其他载入工具，但不在部署指南中介绍这些方案。 有关详细信息，请参阅 [将设备载入到 Microsoft Defender for Endpoint](onboard-configure.md)。

## <a name="check-license-state"></a>检查许可证状态

可通过管理中心或管理门户检查许可证状态及其是否Microsoft Azure **设置**。

1. 若要查看许可证，请转到 Microsoft Azure **门户** 并导航到"Microsoft Azure [门户许可证"部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   :::image type="content" source="images/atp-licensing-azure-portal.png" alt-text="Azure 许可页面" lightbox="images/atp-licensing-azure-portal.png":::

1. 或者，在管理中心中，导航到" **帐单"** \> **"订阅"**。

    在屏幕上，你将看到所有预配的许可证及其当前 **状态**。

    :::image type="content" source="images/atp-billing-subscriptions.png" alt-text="帐单许可证页面" lightbox="images/atp-billing-subscriptions.png":::

## <a name="cloud-service-provider-validation"></a>云服务提供商验证

若要获取向公司预配哪些许可证的访问权限，并检查许可证的状态，请转到管理中心。

1. 从合作伙伴 **门户中，** 选择"**管理服务> Office 365**"。

2. 单击"**合作伙伴门户**"链接将打开"代表管理员"选项，并授予你客户管理中心的访问权限。

   :::image type="content" source="images/atp-O365-admin-portal-customer.png" alt-text="管理Office 365门户" lightbox="images/atp-O365-admin-portal-customer.png":::

## <a name="tenant-configuration"></a>租户配置

载入 Microsoft Defender for Endpoint 非常简单。 从导航菜单中，选择终结点部分下的任何项目，或任何 Microsoft 365 Defender 功能（如事件、搜寻、操作中心或威胁分析）以启动载入过程。

从 Web 浏览器中，导航到Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>。

## <a name="data-center-location"></a>数据中心位置
Microsoft Defender for Endpoint 将在用户所使用的相同位置存储和处理[Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)。 如果Microsoft 365 Defender尚未打开，则载入 Microsoft Defender for Endpoint 也将打开 Microsoft 365 Defender 并且根据活动 Microsoft 365 安全服务的位置自动选择新的数据中心位置。 所选的数据中心位置会显示在屏幕上。

## <a name="network-configuration"></a>网络配置

如果组织不要求终结点使用代理访问 Internet，请跳过此部分。

Microsoft Defender for Endpoint 感官方案需要 Microsoft Windows HTTP （WinHTTP） 报告感官数据，并与 Microsoft Defender for Endpoint 服务进行通信。 嵌入的 Microsoft Defender for Endpoint 传感器使用 LocalSystem 帐户在系统上下文中运行。 该感官服务使用 Microsoft Windows HTTP Services （WinHTTP） 与 Microsoft Defender for Endpoint 云服务启用通信。 WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用下列发现方法发现代理服务器：

- **自动发现方法**：
  - 透明代理
  - Web 代理自动发现协议 (WPAD)

  如果在网络拓扑中实施了透明代理或 WPAD，则不需要特殊的配置设置。 有关代理中用于终结点 URL 排除的 Microsoft Defender 详细信息，请参阅本文档中的代理服务 [URL](production-deployment.md#proxy-service-urls) 部分，了解 URL 允许列表或配置设备代理和 [Internet 连接设置](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

- **手动静态代理配置**：
  - 基于注册表的配置
  - 使用 netsh 命令配置的 WinHTTP

    仅适用于稳定拓扑结构中的桌面 (例如：企业网络中同一代理服务器后面的桌面) 。

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基于注册表的静态代理手动配置代理服务器

配置基于注册表的静态代理，以允许仅 Microsoft Defender for Endpoint 传感器报告诊断数据，并与 Microsoft Defender for Endpoint 服务进行通信（如果不允许计算机连接到 Internet）。 静态代理可以通过组策略 (GP) 配置。 可以在以下位置找到组策略：

- 管理模板\>Windows组件 \> 数据收集和预览版本\>配置连接的用户体验和遥测服务的已验证代理使用情况
- 将其设置为" **已启用"，** 然后选择 **"禁用经过身份验证的代理用法"**

1. 打开组策略管理控制台。
2. 根据组织实践创建策略或编辑现有策略。
3. 编辑组策略并 **\>导航到"管理模板"Windows组件\>数据收集\>** 和预览版配置连接的用户体验和遥测服务的已验证代理用法。

   :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="与配置使用策略相关的选项" lightbox="images/atp-gpo-proxy1.png":::

4. 选择“**已启用**”。
5. 选择 **"禁用经过身份验证的代理用法"**。
6. 导航到 **管理模板\>Windows组件 \> 数据收集和预览版本 \> 配置连接的用户体验和遥测**。

   :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="与连接用户体验和遥测的配置相关的选项" lightbox="images/atp-gpo-proxy2.png":::

7. 选择“**已启用**”。
8. 输入 **代理服务器名称**。

策略将注册表项 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的两个注册表值 `TelemetryProxyServer` 设置为 REG\u SZ，`DisableEnterpriseAuthProxy` 设置为 REG\u DWORD。

注册表值采用 `TelemetryProxyServer` 以下字符串格式：

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
> - 更改拓扑结构（例如 (：从办公室到家庭) netsh 将发生故障。 使用基于注册表的静态代理配置。

1. 打开提升的命令行:
    1. 转到“**开始**”并键入“**cmd**”。
    1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，再按 **Enter**：

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例如：netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>低级别设备的代理配置

Down-Level包括 Windows 7 SP1 和 Windows 8.1 工作站以及 Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2 以及 Windows Server 2016 之前的 Windows 服务器 CB 1803。 这些操作系统将代理配置为 Microsoft 管理代理的一部分，以处理从终结点到 Azure 的通信。 请参阅 Microsoft 管理代理快速部署指南，了解如何在这些设备上配置代理。

### <a name="proxy-service-urls"></a>代理服务 URL

仅在你拥有 Windows 10 版本 1803 或 Windows 11 URL。 例如，`us-v20.events.data.microsoft.com`仅在设备位于 Windows 10 1803 或 Windows 11。

如果代理或防火墙阻止匿名流量，因为 Microsoft Defender for Endpoint 传感器从系统上下文连接，请确保允许列出的 URL 中的匿名流量。

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。

<br>

****


|域列表的电子表格| 说明|
|---|---|
|:::image type="content" source="images/mdatp-urls.png" alt-text="Microsoft Defender for Endpoint URL 电子表格" lightbox="images/mdatp-urls.png":::|服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)|
|

## <a name="next-step"></a>后续步骤

[![**阶段 3：载入**。](images/onboard.png#lightbox)] <br> [阶段 3：](onboarding.md)载入：将设备载入服务，以便 Microsoft Defender for Endpoint 服务可以从它们获取传感器数据。
