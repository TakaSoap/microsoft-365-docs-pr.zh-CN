---
title: 排查问题并查找与 iOS 上的 Microsoft Defender for Endpoint 相关的常见问题解答
description: 疑难解答和常见问题解答 - 适用于 iOS 上的终结点的 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 疑难解答， 如何
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
ms.openlocfilehash: 9245062a0906186ce779383725cecc8209655c6f
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882749"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>排查与 iOS 上的 Microsoft Defender for Endpoint 相关的问题并查找常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本主题提供疑难解答信息，以帮助你解决在 iOS 上使用 Microsoft Defender for Endpoint 时可能出现的问题。



> [!NOTE]
> iOS 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>打开 VPN 后，应用无法工作
某些应用在检测到活动 VPN 时停止运行。 可以在使用此类应用时禁用 VPN。 

默认情况下，iOS 上的 Defender for Endpoint 包括并启用 Web 保护功能。 [Web](web-protection-overview.md) 保护有助于保护设备免受 Web 威胁，并保护用户免受网络钓鱼攻击。 iOS 上的 Defender for Endpoint 使用 VPN 来提供此保护。 请注意，这是本地 VPN，与传统 VPN 不同，网络流量不会发送到设备外部。

虽然默认启用，但在某些情况下可能需要你禁用 VPN。 例如，你想要运行一些在配置 VPN 时不起作用的应用。 在这种情况下，你可以选择直接从 Defender for Endpoint 应用或按照以下步骤禁用 VPN：

1. 在 iOS 设备上，打开 **"设置应用**"，单击 **或点击"** 常规"，然后单击 **"VPN"。**
1. 单击或点击 Microsoft Defender for Endpoint 的"i"按钮。
1. 关闭 **"连接按需"** 以禁用 VPN。

    > [!div class="mx-imgBorder"]
    > ![VPN 配置按需连接。](images/ios-vpn-config.png)

> [!NOTE]
> 禁用 VPN 后，Web 保护将不可用。 若要重新启用 Web 保护，请打开设备上 Microsoft Defender for Endpoint 应用并启用 Web 保护。

## <a name="coexistence-with-multiple-vpn-profiles"></a>与多个 VPN 配置文件共存

Apple iOS 不支持多个 **设备范围的** VPN 同时处于活动状态。 虽然设备上可以存在多个 VPN 配置文件，但一次只能有一个 VPN 处于活动状态。 如果你需要在设备上使用另一个 VPN，可以在使用另一个 VPN 时禁用终结点 VPN 的 Defender。

## <a name="battery-consumption"></a>电池消耗

为了提供对基于 Web 的威胁的一切保护，Microsoft Defender for Endpoint 需要一切都在后台运行。 这可能会导致设备的总电池消耗轻微增加。 如果你看到电池严重消耗，请 [向我们发送反馈](ios-troubleshoot.md#send-in-app-feedback) ，我们将进行调查。

此外，在设置应用中，iOS 仅显示特定时间内对用户可见的应用的电池使用情况。 屏幕上显示的应用的电池使用量仅在该持续时间内，由 iOS 根据大量因素（包括 CPU 和网络使用情况）计算。 Microsoft Defender for Endpoint 在后台使用本地/环回 VPN 来检查任何恶意网站或连接的 Web 流量。 来自任何应用的网络数据包都经过此检查，这会导致 Microsoft Defender for Endpoint 的电池使用情况计算不准确。 Microsoft Defender for Endpoint 的实际电池消耗低于设备上"电池设置页面上显示的内容。

请注意，使用的 VPN 是本地 VPN，不同于传统 VPN，网络流量不会发送到设备外部。

## <a name="data-usage"></a>数据使用情况

Microsoft Defender for Endpoint 使用本地/环回 VPN 检查任何恶意网站或连接的 Web 流量。 由于此原因，Microsoft Defender 终结点数据使用情况可能不准确。 我们还观察到，如果设备仅在移动电话网络上，服务提供商报告的数据使用量将非常接近实际使用量，而在 设置 应用中，Apple 显示的实际使用量大约是实际使用量的 1.5 倍到 2 倍。

我们还与其他 VPN 服务有类似的观察结果，并且已经向 Apple 报告了这一点。

此外，使用后端服务更新 Microsoft Defender for Endpoint 以提供更好的保护至关重要。

## <a name="report-unsafe-site"></a>报告不安全网站

网络钓鱼网站会模拟可信赖的网站来获取你的个人或财务信息。 访问 ["提供有关网络保护的反馈"页](https://www.microsoft.com/wdsi/support/report-unsafe-site) ，以报告可能是网络钓鱼网站的网站。

## <a name="malicious-site-detected"></a>检测到恶意站点

Microsoft Defender for Endpoint 可保护你免受网络钓鱼或其他基于 Web 的攻击。 如果检测到恶意站点，连接将被阻止，并且会向组织的安全中心门户发送警报。 警报包括连接的域名、远程 IP 地址和设备详细信息。

此外，iOS 设备上还显示通知。 点击通知将打开以下屏幕，供用户查看详细信息。

> [!div class="mx-imgBorder"]
> ![报告为不安全通知的网站的图像。](images/ios-phish-alert.png)

## <a name="device-not-seen-on-the-defender-for-endpoint-console-after-onboarding"></a>载入后，在 Defender for Endpoint 控制台上未看到设备。

载入后，设备需要几个小时才能显示在 Defender for Endpoint 安全控制台的设备清单中。 此外，请确保设备已正确注册Azure Active Directory并且设备具有 Internet 连接。 若要成功载入，设备必须通过 Microsoft Authenticator 或 Intune 公司门户 并且用户需要使用设备在 Azure AD 中注册的同一帐户登录。

> [!NOTE]
> 有时，设备名称与 Intune Microsoft Endpoint Manager (控制台中的设备) 一致。 Defender for Endpoint 控制台中的设备名称采用 <username_iPhone/iPad 模式>。 还可使用 Azure AD ID 在 Defender for Endpoint 控制台中标识设备。

## <a name="data-and-privacy"></a>数据和隐私

有关收集的数据和隐私的详细信息，请参阅 [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md)。

## <a name="issues-on-supervised-devices-with-content-filter-profile-installed"></a>安装了内容筛选器配置文件的受监督设备的问题

在安装了 Defender for Endpoint 内容筛选器的受监督设备上存在问题。 如果发现此类设备的 Internet 连接速度变慢或延迟，请卸载或删除设备中的内容筛选器配置文件。 我们正在努力解决此问题，并且将在我们解决后更新此位置。 

## <a name="issues-during-app-updates-from-the-app-store"></a>从应用商店更新应用期间的问题

如果在通过应用商店更新应用时发现 (自动更新或手动更新) ，你可能需要重新启动设备。 如果无法解决问题，你可以禁用 Defender VPN 并执行应用更新。 还可以提供应用内反馈来报告此问题。

## <a name="send-in-app-feedback"></a>发送应用内反馈

如果用户面临以上部分中尚未解决的问题，或者无法使用列出的步骤解决问题，则用户可以提供应用内反馈和诊断数据。 然后，我们团队将调查日志以提供正确的解决方案。 用户可以使用以下步骤发送反馈：

  - 在 iOS/iPadOS 设备上打开 MSDefender 应用。
  - 点击左上角 (菜单) 配置文件图标。
  - 点击 **"发送反馈"。**
  - 从给定选项中进行选择。 若要报告问题，请选择 **"我不喜欢某些内容"。**
  - 提供你所面临的问题的详细信息，并检查发送 **诊断数据**。 我们建议你包含你的电子邮件地址，以便团队可以联系你以寻求解决方案或跟进。
  - 点击 **提交** 以成功发送反馈。



