---
title: 在 iOS 功能上部署 Microsoft Defender for Endpoint
description: 介绍如何在注销的 iOS 设备上部署适用于终结点的 Microsoft Defender。
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 配置， 功能， ios
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b1945059147f87499d131d241c74aaca749fb6e7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474104"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>在注销的 iOS 设备上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

> [!NOTE]
> iOS 上的 Defender for Endpoint 使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>在 MAM 应用保护策略中配置 Microsoft Defender (终结点) 

iOS 上的 Microsoft Defender for Endpoint 已在移动设备管理 (MDM) 方案中保护企业用户，现在针对未使用 Intune 移动设备管理 (MDM) 注册的设备，将支持扩展到移动应用管理 (MAM) 。 它还向使用其他企业移动性管理解决方案的客户扩展了此支持，同时仍使用 Intune 在 MAM (移动应用程序) 。此功能允许您在应用程序中管理和保护组织的数据。

Intune 应用保护策略利用 iOS 上的 Microsoft Defender for Endpoint 威胁信息来保护这些应用。 应用保护策略 (APP) 是可确保组织数据在托管应用中保持安全或受到控制的规则。 托管应用程序应用了应用保护策略，并且可通过 Intune 进行管理。  

iOS 上的 Microsoft Defender for Endpoint 支持 MAM 的两种配置
- **Intune MDM + MAM**：IT 管理员只能在使用 Intune 移动设备管理和 MDM) 注册的设备上使用应用保护策略管理 (应用。
- **未注册设备的 MAM**：未注册设备的 MAM 或 MAM-WE 允许 IT 管理员在未注册 Intune MDM 的 [](/mem/intune/app/app-protection-policy)设备上使用应用保护策略管理应用。 这意味着可以在已注册到第三方 EMM 提供商的设备上通过 Intune 来管理应用。 若要在以上两种配置中管理应用，客户应在管理中心Microsoft Endpoint Manager [Intune](https://go.microsoft.com/fwlink/?linkid=2109431)

若要启用此功能，管理员需要配置 Microsoft Defender for Endpoint 和 Intune 之间的连接、创建应用保护策略，以及将策略应用于目标设备和应用程序。 
 
最终用户还需要采取措施，在设备上安装 Microsoft Defender for Endpoint 并激活载入流程。

### <a name="pre-requisites"></a>先决条件

1. **验证连接器是否已启用**。 <br> 在统 [一安全控制台上](https://security.microsoft.com)， > 转到 设置 **EndpointsAdvanced** >  **功能**，并确保启用 **Microsoft Intune连接。**

  :::image type="content" source="images/enable-intune-connection.png" alt-text="Defender for Endpoint - Intune 连接器" lightbox="images/enable-intune-connection.png":::

  
2. **验证连接器是否已启用 Intune 门户**。 <br> 在 [Microsoft Endpoint Manager 管理中心，](https://go.microsoft.com/fwlink/?linkid=2109431)转到 Endpoint **SecurityMicrosoft**  >  Defender for Endpoint 并确保连接状态已启用。

  :::image type="content" source="images/app-settings.png" alt-text="应用程序设置" lightbox="images/app-settings.png":::

### <a name="create-an-app-protection-policy"></a>创建应用保护策略
 
通过创建应用保护策略，基于 Microsoft Defender for Endpoint 风险信号阻止访问或擦除托管应用的数据。
Microsoft Defender for Endpoint 可以配置为发送要用于应用保护策略 (应用（也称为 MAM) ）。 借助此功能，可以使用 Microsoft Defender for Endpoint 保护托管应用。

1. 创建策略 <br>
应用保护策略 (APP) 是可确保组织数据在托管应用中保持安全或受到控制的规则。 策略可以是在用户尝试访问或移动“公司”数据时强制执行的规则，或在用户位于应用内时受到禁止或监视的一组操作。 

:::image type="content" source="images/create-policy.png" alt-text="&quot;应用保护策略&quot;菜单项上的&quot;创建策略&quot;选项卡" lightbox="images/create-policy.png":::

2. 添加应用 <br>
    a. 选择要如何将此策略应用到不同设备上的应用。 然后至少添加一个应用。 <br>
    使用此选项指定此策略是否适用于非托管设备。 还可以选择将策略定向到任何管理状态设备上的应用。
由于移动应用管理不需要设备管理，因此可在受管理和不受管理设备上保护公司数据。 管理以用户标识为中心，因而不再需要设备管理。 公司可以同时使用具有或不使用 MDM 的应用保护策略。 例如这样一种情况：员工同时使用公司电话和其个人平板电脑。 公司手机在 MDM 中注册，并受应用保护策略保护，而个人设备仅受应用保护策略保护。

    b. 选择应用<br>
    受管理应用是一种自身执行应用保护策略的应用，可由 Intune 管理。 已与 [Intune SDK](/mem/intune/developer/app-sdk) 集成或由 [Intune](/mem/intune/developer/apps-prepare-mobile-application-management) App Wrapping Tool包装的任何应用都可以使用 Intune 应用保护策略进行管理。 请参阅使用以下工具构建并可供公众使用的 [Microsoft Intune 保护的应用](/mem/intune/apps/apps-supported-intune-apps)的官方列表。

    *示例：Outlook托管应用*

     :::image type="content" source="images/managed-app.png" alt-text="Microsoft Outlook左侧导航窗格上的菜单项" lightbox="images/managed-app.png":::
  

 3. 设置保护策略的登录安全要求。 <br>
在 **">条件"中选择** "设置允许的最大设备 **威胁级别"** ，然后输入一个值。 然后选择"  **操作："阻止访问"**。 iOS 上的 Microsoft Defender for Endpoint 共享此设备威胁级别。

    
   :::image type="content" source="images/conditional-launch.png" alt-text="&quot;设备条件&quot;窗格" lightbox="images/conditional-launch.png":::

4. 分配需要为其应用策略的用户组。<br>
  选择 **"包含的组"**。 然后添加相关组。 


有关 MAM 或应用保护策略详细信息，请参阅 [iOS 应用保护策略设置](/mem/intune/apps/app-protection-policy-settings-ios)。

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>为 MAM 或注销的设备上部署 Microsoft Defender for Endpoint

iOS 上的 Microsoft Defender for Endpoint 支持应用保护策略方案，并且适用于 Apple 应用商店。

当为应用配置应用保护策略以包含来自 Microsoft Defender for Endpoint 的设备风险信号时，将在使用此类应用时重定向用户以安装 Microsoft Defender for Endpoint。 或者，用户还可以直接从 Apple 应用商店安装应用的最新版本。
