---
title: 在 iOS 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 iOS 功能上部署 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 配置， 功能， ios
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
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2e53eca402b549fcf5ac2ff250ee33e8dac0be48
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110735"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>在 iOS 功能上配置 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

> [!NOTE]
> iOS 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>在 iOS 上通过 Defender for Endpoint 进行条件访问

iOS 上的 Microsoft Defender for Endpoint 以及 Microsoft Intune 和 Azure Active Directory 支持根据设备风险评分强制实施设备合规性和条件访问策略。 Defender for Endpoint 是一种移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。

若要详细了解如何使用 iOS 上的 Defender for Endpoint 设置条件访问，请参阅[Defender for Endpoint 和 Intune。](/mem/intune/protect/advanced-threat-protection)

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 的越狱检测

Microsoft Defender for Endpoint 能够检测已越狱的非托管和托管设备。 如果检测到设备已越狱，则高风险警报将报告给 Microsoft 365 Defender 门户，如果根据设备风险评分设置条件访问，则设备将阻止其访问公司数据。

## <a name="web-protection-and-vpn"></a>Web 保护和 VPN

默认情况下，iOS 上的 Defender for Endpoint 包括并启用 Web 保护功能。 [Web](web-protection-overview.md) 保护有助于保护设备免受 Web 威胁，并保护用户免受网络钓鱼攻击。 iOS 上的 Defender for Endpoint 使用 VPN 来提供此保护。 请注意，这是本地 VPN，与传统 VPN 不同，网络流量不会在设备外部发送。

虽然默认启用，但在某些情况下可能需要你禁用 VPN。 例如，你想要运行一些在配置 VPN 时不起作用的应用。 在这种情况下，你可以选择按照以下步骤在设备上禁用应用中的 VPN：

1. 在 iOS 设备上，打开 **"设置应用**"，单击 **或点击"** 常规"，然后单击 **"VPN"。**
1. 单击或点击 Microsoft Defender for Endpoint 的"i"按钮。
1. 关闭 **"连接按需"** 以禁用 VPN。

    > [!div class="mx-imgBorder"]
    > ![VPN 配置按需连接。](images/ios-vpn-config.png)

> [!NOTE]
> 禁用 VPN 后，Web 保护将不可用。 若要重新启用 Web 保护，请在设备上打开 Microsoft Defender for Endpoint 应用，然后单击或点击"启动 **VPN"。**

## <a name="co-existence-of-multiple-vpn-profiles"></a>多个 VPN 配置文件共存

Apple iOS 不支持多个设备范围的 VPN 同时处于活动状态。 虽然设备上可以存在多个 VPN 配置文件，但一次只能有一个 VPN 处于活动状态。

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>在 MAM 应用保护策略中配置 Microsoft Defender (终结点) 

Microsoft Defender for Endpoint 可以配置为发送要用于应用保护策略 (APP（也称为 iOS/iPadOS 上的 MAM) MAM） 中的威胁信号。 借助此功能，也可使用 Microsoft Defender for Endpoint 保护从注销的设备访问公司数据。

使用 Microsoft Defender for Endpoint 设置应用保护策略的步骤如下所示：

1. 设置从你的 Microsoft Endpoint Manager 租户到 Microsoft Defender for Endpoint 的连接。 在 [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 中，转到"设置) "下的"跨平台) 或终结点安全 Microsoft Defender \>  \> **for**  \> **Endpoint** ("下的"适用于终结点的 Microsoft Defender (租户管理连接器和令牌"，然后打开适用于 **iOS** 的应用保护策略 设置 下的切换。
1. 选择“保存”。 应看到"**连接状态**"现在设置为"**已启用"。**
1. 创建应用保护策略：完成 Microsoft Defender for Endpoint 连接器设置后，导航到"策略 (下的应用应用保护策略) 以创建新策略或 \> 更新现有策略。
1. 选择组织为策略 **所需的** 平台、应用、数据保护、访问要求设置。
1. 在 **"条件启动** \> **设备条件**"下，你将找到设置 **"允许的最大设备威胁级别"。** 这将需要配置为低、中、高或安全。 可用操作为"阻止 **访问"或**"**擦除数据"。** 在此设置生效之前，你可能会看到一个信息对话框，确保你已设置连接器。 如果连接器已设置，可以忽略此对话框。
1. 完成分配并保存策略。

有关 MAM 或应用保护策略的更多详细信息，请参阅 [iOS 应用保护策略设置](/mem/intune/apps/app-protection-policy-settings-ios)。

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>为 MAM 或注销的设备上部署 Microsoft Defender for Endpoint

iOS 上的 Microsoft Defender for Endpoint 支持应用保护策略方案，并且适用于 Apple 应用商店。

最终用户应直接从 Apple 应用商店安装应用的最新版本。

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>针对越狱设备配置合规性策略

若要防止在已越狱的 iOS 设备上访问公司数据，我们建议在 Intune 上设置以下合规性策略。

> [!NOTE]
> 越狱检测是 Microsoft Defender for Endpoint 在 iOS 上提供的一项功能。 但是，我们建议你设置此策略作为抵御越狱情形的额外防御层。

按照以下步骤创建针对已越狱设备的合规性策略。

1. In [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431)go to **Devices**  ->  **Compliance policies** Create  ->  **Policy**. 选择"iOS/iPadOS"作为平台，然后单击"创建 **"。**

    > [!div class="mx-imgBorder"]
    > ![创建策略。](images/ios-jb-policy.png)

2. 指定策略的名称，例如"越狱合规性策略"。
3. 在合规性设置页中，单击以展开 **"设备运行状况"** 部分，**然后单击"阻止****越狱设备"** 字段。

    > [!div class="mx-imgBorder"]
    > ![策略设置。](images/ios-jb-settings.png)

4. 在"**针对不相容性** 的操作"部分，根据你的要求选择操作，然后选择"下一 **步"。**

    > [!div class="mx-imgBorder"]
    > ![策略操作。](images/ios-jb-actions.png)

5. 在 **"分配**"部分，选择要为此策略包含的用户组，然后选择"下一步 **"。**
6. 在"**审阅+创建**"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**

## <a name="configure-custom-indicators"></a>配置自定义指示器

通过 iOS 上的 Defender for Endpoint，管理员还可以在 iOS 设备上配置自定义指示器。 若要详细了解如何配置自定义指示器，请参阅管理 [指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。

> [!NOTE]
> iOS 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。

## <a name="report-unsafe-site"></a>报告不安全网站

网络钓鱼网站会模拟可信赖的网站，以获取你的个人或财务信息。 如果要 [报告可能是网络钓鱼](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 网站的网站，请访问提供有关网络保护的反馈页面。
