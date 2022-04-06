---
title: 在 Android 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 Android 上配置Microsoft Defender for Endpoint
keywords: microsoft、defender、Microsoft Defender for Endpoint、mde、android、configuration
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0e0a8a99444f09d58a43502edd1c94e4cce52301
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664669"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>在 Android 功能上配置 Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>使用 Android 上的 Defender for Endpoint 进行条件访问

在 Android 上Microsoft Defender for Endpoint以及Microsoft Intune和Azure Active Directory可根据设备风险级别强制实施设备符合性和条件访问策略。 Defender for Endpoint 是一种移动威胁防御 (MTD) 解决方案，你可以部署该解决方案，以便通过Intune利用此功能。

有关如何在 Android 和条件访问上设置 Defender for Endpoint 的详细信息，请参阅 [Defender for Endpoint 和 Intune](/mem/intune/protect/advanced-threat-protection)。

## <a name="configure-custom-indicators"></a>配置自定义指示器

> [!NOTE]
> Android 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。

Android 上的 Defender for Endpoint 使管理员能够配置自定义指示器以支持 Android 设备。 有关如何配置自定义指示器的详细信息，请参阅 ["管理指示器](manage-indicators.md)"。

## <a name="configure-web-protection"></a>配置 Web 保护
Android 上的 Defender for Endpoint 允许 IT 管理员配置 Web 保护功能。 此功能在Microsoft Endpoint Manager管理中心内可用。

> [!NOTE]
> Android 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，是本地/自循环 VPN，不会将流量移到设备外部。
> 有关详细信息，请参阅在 [运行 Android 的设备上配置 Web 保护](/mem/intune/protect/advanced-threat-protection-manage-android)。

## <a name="privacy-controls"></a>隐私控制

> [!IMPORTANT]
> Android 上Microsoft Defender for Endpoint隐私控制处于预览状态。 以下信息与预发行产品有关，这些产品在商业发布之前可能会进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

以下隐私控制可用于配置 Defender for Endpoint 从 Android 设备发送的数据：

|威胁报告     |详细信息      |
|--------------------|-------------|
|恶意软件报表 |管理员可以为恶意软件报告设置隐私控制 - 如果启用了隐私，则 Defender for Endpoint 不会将恶意软件应用名称和其他应用详细信息作为恶意软件警报报告的一部分发送 |
|网络钓鱼报表 |管理员可以为网络钓鱼报告设置隐私控制 - 如果启用了隐私，则 Defender for Endpoint 不会将不安全网站的域名和详细信息作为网络钓鱼警报报告的一部分发送 |
|仅限 Android (应用的漏洞评估)  |默认情况下，仅发送有关工作配置文件中安装的应用的信息以进行漏洞评估。 管理员可以禁用隐私以包括个人应用|

## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>为 BYOD 设备配置应用的漏洞评估

从 Android 上Microsoft Defender for Endpoint版本 1.0.3425.0303 开始，你将能够对已载入移动设备上安装的 OS 和应用运行漏洞评估。

> [!NOTE]
> 漏洞评估是Microsoft Defender for Endpoint[中威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)的一部分。 

**有关与个人设备 (BYOD) 相关应用的隐私的说明：**

- 对于具有工作配置文件的 Android Enterprise，仅支持在工作配置文件上安装的应用。
- 对于其他 BYOD 模式，默认 **情况下，不会** 启用对应用的漏洞评估。 但是，当设备处于管理员模式时，管理员可以通过Microsoft Endpoint Manager显式启用此功能，以获取设备上安装的应用列表。 有关详细信息，请参阅下面的详细信息。

### <a name="configure-privacy-for-device-administrator-mode"></a>为设备管理员模式配置隐私

使用以下步骤为目标用户启用设备 **管理员** 模式下设备应用的 **漏洞评估**。 

> [!NOTE]
> 默认情况下，对于使用设备管理模式注册的设备，此操作会关闭。

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **DevicesConfiguration** >  **profilesCreate** >  配置文件并输入以下设置：

   - **平台**：选择 Android 设备管理员
   - **配置文件**：选择"自定义"，然后单击"创建"

2. 在 **"基本信息** "部分中，指定配置文件的名称和说明。

3. 在 **配置设置中**，选择"添加 **OMA-URI** "设置：

   - **名称**：输入此 OMA-URI 设置的唯一名称和说明，以便稍后可以轻松找到它。
   - OMA-URI： **./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - 数据类型：从下拉列表选择“整数”。
   - 值：输入 0 以禁用隐私设置 (默认情况下，值为 1) 

4. 单击 **"下一步** "并将此配置文件分配给目标设备/用户。

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>为 Android Enterprise工作配置文件配置隐私

Defender for Endpoint 支持对工作配置文件中的应用进行漏洞评估。 但是，如果要为目标用户关闭此功能，可以使用以下步骤：

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **AppsApp** >  **配置策略** > **AddManaged** >  设备。
2. 为策略命名;**平台> Android Enterprise**;选择配置文件类型。
3. 选择 **Microsoft Defender for Endpoint** 作为目标应用。
4. 在设置页中，选择 **"使用配置设计** 器"并添加 **DefenderTVMPrivacyMode** 作为键，将值类型添加为 **整数**
   - 若要禁用工作配置文件中应用的漏洞，请输入值并 `1` 将其分配给用户。 默认情况下，此值设置为 `0`。
   - 对于设置为 `0`Key 的用户，Defender for Endpoint 会将工作配置文件中的应用列表发送到后端服务以进行漏洞评估。
5. 单击 **"下一步** "并将此配置文件分配给目标设备/用户。

打开或关闭上述隐私控制不会影响设备符合性检查或条件访问。

## <a name="configure-privacy-for-phishing-alert-report"></a>为网络钓鱼警报报告配置隐私

网络钓鱼报告的隐私控制可用于禁用网络钓鱼威胁报告中域名或网站信息的收集。 这使组织能够灵活地选择在 Defender for Endpoint 检测和阻止恶意网站或网络钓鱼网站时是否要收集域名。

### <a name="configure-privacy-for-phishing-alert-report-on-android-device-administrator-enrolled-devices"></a>在 Android 设备管理员注册的设备上配置网络钓鱼警报报告的隐私：

使用以下步骤为目标用户启用它：

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **DevicesConfiguration** >  **profilesCreate** >  配置文件并输入以下设置：

   - **平台**：选择 Android 设备管理员。
   - **配置文件**：选择"自定义"，然后单击 **"创建**"。

2. 在 **"基本信息** "部分中，指定配置文件的名称和说明。

3. 在 **配置设置中**，选择"添加 **OMA-URI** "设置：

   - **名称**：输入此 OMA-URI 设置的唯一名称和说明，以便稍后可以轻松找到它。
   - OMA-URI： **./Vendor/MSFT/DefenderATP/DefenderExcludeURLInReport**
   - 数据类型：从下拉列表选择“整数”。
   - 值：输入 1 以启用隐私设置。 默认值为 0。

4. 单击 **"下一步** "并将此配置文件分配给目标设备/用户。

使用此隐私控制不会影响设备符合性检查或条件访问。

### <a name="configure-privacy-for-phishing-alert-report-on-android-enterprise-work-profile"></a>在 Android Enterprise工作配置文件上配置网络钓鱼警报报告的隐私

使用以下步骤为工作配置文件中的目标用户启用隐私：

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **AppsApp** >  **配置策略** > **AddManaged** >  设备。
2. 为策略命名"**平台> Android Enterprise**"，选择配置文件类型。
3. 选择 **Microsoft Defender for Endpoint** 作为目标应用。
4. 在设置页中，选择 **"使用配置设计器**"并添加 **DefenderExcludeURLInReport** 作为键，将值类型添加为 **整数**。
   - 输入 **1 以启用隐私**。 默认值为 0。
5. 单击 **"下一步** "并将此配置文件分配给目标设备/用户。

打开或关闭上述隐私控制不会影响设备符合性检查或条件访问。

## <a name="configure-privacy-for-malware-threat-report"></a>为恶意软件威胁报告配置隐私

恶意软件威胁报告的隐私控制可用于禁用从恶意软件威胁报告)  (名称和包信息的应用详细信息集合。 这使组织能够灵活地选择在检测到恶意应用时是否要收集应用名称。

### <a name="configure-privacy-for-malware-alert-report-on-android-device-administrator-enrolled-devices"></a>在 Android 设备管理员注册的设备上为恶意软件警报报告配置隐私：

使用以下步骤为目标用户启用它：

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **DevicesConfiguration** >  **profilesCreate** >  配置文件并输入以下设置：

   - **平台**：选择 Android 设备管理员。
   - **配置文件**：选择"自定义"，然后单击 **"创建**"。

2. 在 **"基本信息** "部分中，指定配置文件的名称和说明。

3. 在 **配置设置中**，选择"添加 **OMA-URI** "设置：

   - **名称**：输入此 OMA-URI 设置的唯一名称和说明，以便稍后可以轻松找到它。
   - OMA-URI： **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - 数据类型：从下拉列表选择“整数”。
   - 值：输入 1 以启用隐私设置。 默认值为 0。

4. 单击 **"下一步** "并将此配置文件分配给目标设备/用户。

使用此隐私控制不会影响设备符合性检查或条件访问。 例如，具有恶意应用的设备始终具有"中等"的风险级别。

### <a name="configure-privacy-for-malware-alert-report-on-android-enterprise-work-profile"></a>在 Android Enterprise工作配置文件上配置恶意软件警报报告的隐私

使用以下步骤为工作配置文件中的目标用户启用隐私：

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **AppsApp** >  **配置策略** > **AddManaged** >  设备。
2. 为策略命名"**平台> Android Enterprise**"，选择配置文件类型。
3. 选择 **Microsoft Defender for Endpoint** 作为目标应用。
4. 在设置页中，选择 **"使用配置设计** 器"并将 **DefenderExcludeAppInReport** 作为键和值类型添加为 **整数**
   - 输入 **1 以启用隐私**。 默认值为 0。
5. 单击 **"下一步** "并将此配置文件分配给目标设备/用户。

使用此隐私控制不会影响设备符合性检查或条件访问。 例如，具有恶意应用的设备始终具有"中等"的风险级别。

## <a name="related-topics"></a>相关主题

- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
