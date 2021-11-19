---
title: 在 Android 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 Android 上配置适用于终结点的 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 配置
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
ms.openlocfilehash: 575df186af15628ec4d7d4162d100ea0d1974146
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111395"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>在 Android 功能上配置适用于终结点的 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>在 Android 上通过 Defender for Endpoint 进行条件访问

Android 上的 Microsoft Defender for Endpoint 以及 Microsoft Intune 和 Azure Active Directory 启用基于设备风险级别的设备合规性和条件访问策略。 Defender for Endpoint 是移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。

若要详细了解如何在 Android 和条件访问上设置适用于终结点的 Defender，请参阅[Defender for Endpoint 和 Intune。](/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>配置自定义指示器

> [!NOTE]
> Android 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。

Android 上的 Defender for Endpoint 使管理员能够配置自定义指示器以支持 Android 设备。 若要详细了解如何配置自定义指示器，请参阅管理 [指示器](manage-indicators.md)。

## <a name="configure-web-protection"></a>配置 Web 保护
Android 上的 Defender for Endpoint 允许 IT 管理员配置 Web 保护功能。 此功能在管理中心Microsoft Endpoint Manager可用。

> [!NOTE]
> Android 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。
> 有关详细信息，请参阅在运行 [Android 的设备上配置 Web 保护](/mem/intune/protect/advanced-threat-protection-manage-android)。


## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>配置 BYOD 设备应用漏洞评估

从 Android 版 Microsoft Defender for Endpoint 的版本 1.0.3425.0303 开始，我们能够对已安装在载入的移动设备上的操作系统和应用运行漏洞评估。

> [!NOTE]
> 漏洞评估是 Microsoft [](next-gen-threat-and-vuln-mgt.md) Defender for Endpoint 中的威胁和漏洞管理的一部分。 在 Android 上，此功能当前处于预览阶段，在商业发行之前可能会进行重大修改。

**有关与来自个人设备的应用相关的隐私注意事项 (BYOD) ：**

- 对于 android Enterprise工作配置文件，仅支持在工作配置文件上安装的应用。
- 对于其他 BYOD 模式，默认情况下，不会启用应用的 **漏洞** 评估。 但是，当设备在管理员模式下时，管理员可以通过 Microsoft Endpoint Manager显式启用此功能，以便获取设备上安装的应用列表。 有关详细信息，请访问文档。

### <a name="configure-privacy-for-device-administrator-mode"></a>为设备管理员模式配置隐私

使用以下步骤为目标用户启用设备管理员模式下的设备应用漏洞评估。  

> [!NOTE]
> 默认情况下，对于使用设备管理模式注册的设备，这将关闭。

1. 在 [Microsoft Endpoint Manager中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到"**设备** 配置文件""创建配置文件"  >    >  并输入以下设置：

   - **平台**：选择 Android 设备管理员
   - **配置文件：** 选择"自定义"，然后单击创建

2. 在 **"基础知识"** 部分，指定配置文件的名称和说明。

3. 在配置 **设置中**，选择添加 **OMA-URI** 设置：

   - **名称**：为此 OMA-URI 设置输入唯一的名称和说明，以便你稍后可以轻松找到它。
   - **OMA-URI：./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - 数据类型：在下拉列表中选择"整数"。
   - 值：输入 0 以禁用隐私 (默认情况下，该值为 1) 

4. 单击 **"** 下一步"，并将此配置文件分配给目标设备/用户。

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>配置 Android Enterprise工作配置文件的隐私

Defender for Endpoint 支持对工作配置文件中的应用进行漏洞评估。 但是，若要为目标用户关闭此功能，可以使用以下步骤：

1. In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** App  >  **configuration policies**  >  **Add**  >  **Managed devices**.
2. 为策略命名;**Android >平台Enterprise;** 选择配置文件类型。
3. 选择 **Microsoft Defender for Endpoint** 作为目标应用。
4. 在设置页面中，选择"使用 **配置** 设计器"，将 **DefenderTVMPrivacyMode** 作为键和值类型添加为 **Integer**
   - 若要在工作配置文件中禁用应用漏洞，请输入值作为 ， `1` 并将此策略分配给用户。 默认情况下，此值设置为 `0` 。
   - 对于密钥设置为 的用户，Defender for Endpoint 将应用列表从工作配置文件发送到 `0` 后端服务进行漏洞评估。
5. 单击 **"** 下一步"，并将此配置文件分配给目标设备/用户。

打开或关闭上述隐私控制不会影响设备合规性检查或条件访问。

## <a name="configure-privacy-for-malware-threat-report"></a>配置恶意软件威胁报告的隐私

> [!NOTE]
> Android 版 Defender for Endpoint 的隐私控件目前处于预览阶段，在商业发行之前可能会进行重大修改。

恶意软件威胁报告的隐私控制可用于禁用从恶意软件威胁报告 (名称和程序包) 应用详细信息的集合。 这使组织能够灵活地选择是否在检测到恶意应用时收集应用名称。 *此功能当前仅适用于在 Android 设备管理员模式下 **注册** 的设备。*

使用以下步骤为目标用户打开它：

1. 在 [Microsoft Endpoint Manager中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到"**设备** 配置文件""创建配置文件"  >    >  并输入以下设置：

   - **平台**：选择 Android 设备管理员
   - **配置文件：** 选择"自定义"，然后单击创建

2. 在 **"基础知识"** 部分，指定配置文件的名称和说明。

3. 在配置 **设置中**，选择添加 **OMA-URI** 设置：

   - **名称**：为此 OMA-URI 设置输入唯一的名称和说明，以便你稍后可以轻松找到它。
   - **OMA-URI：./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - 数据类型：在下拉列表中选择"整数"。
   - 值：输入 1 以启用隐私 (默认情况下，该值为 0) 

4. 单击 **"** 下一步"，并将此配置文件分配给目标设备/用户。

使用此隐私控制不会影响设备合规性检查或条件访问。 例如，具有恶意应用的设备的风险级别始终为"中等"。

## <a name="related-topics"></a>相关主题

- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
