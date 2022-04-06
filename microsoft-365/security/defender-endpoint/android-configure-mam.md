---
title: '使用应用保护策略配置 Microsoft Defender for Endpoint 风险信号 (MAM) '
description: 介绍如何使用应用保护策略为终结点风险信号配置 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 配置， MAM， 应用保护ection 策略， 托管应用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: shthota
author: shthota
manager: dansimp
ms.localizationpriority: medium
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5d74fd2af61ee4047dd2728c28e6093efbc58ce9
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471288"
---
# <a name="configure-microsoft-defender-for-endpoint-risk-signals-using-app-protection-policies-mam"></a>使用应用保护策略配置 Microsoft Defender for Endpoint 风险信号 (MAM) 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



Android 版 Microsoft Defender for Endpoint 已在移动设备管理 (MDM) 方案中保护企业用户，现在为未使用 Intune 移动设备管理 (MDM) 注册的设备扩展对移动应用管理 (MAM) 的支持。 它还向使用其他企业移动性管理解决方案的客户扩展了此支持，同时仍使用 Intune 在 MAM (移动应用程序) 。此功能允许您在应用程序中管理和保护组织的数据。

Intune 应用保护策略应用 Android 上的 Microsoft Defender for Endpoint 威胁信息来保护这些应用。 应用保护策略 (APP) 是可确保组织数据在托管应用中保持安全或受到控制的规则。 托管应用程序应用了应用保护策略，并且可通过 Intune 进行管理。  

Android 上的 Microsoft Defender for Endpoint 支持 MAM 的两种配置
- **Intune MDM + MAM**：IT 管理员只能在使用 Intune 移动设备管理和 MDM) 注册的设备上使用应用保护策略管理 (应用。
- **未注册设备的 MAM**：未注册设备的 MAM 或 MAM-WE 允许 IT 管理员在未注册 Intune MDM 的 [](/mem/intune/app/app-protection-policy)设备上使用应用保护策略管理应用。 此预配意味着应用可以在注册到第三方 EMM 提供程序的设备上由 Intune 管理。 若要在以上两种配置中管理应用，客户应在管理中心Microsoft Endpoint Manager [Intune](https://go.microsoft.com/fwlink/?linkid=2109431)

若要启用此功能，管理员需要配置 Microsoft Defender for Endpoint 和 Intune 之间的连接、创建应用保护策略，以及将策略应用于目标设备和应用程序。 
 
最终用户还需要采取措施，在设备上安装 Microsoft Defender for Endpoint 并激活载入流程。


## <a name="admin-prerequisites"></a>管理员先决条件

- **验证 Microsoft Defender for Endpoint-Intune连接器是否已启用**

  a. 转到 security.microsoft.com。 

  b. 选择 **设置 >">"> Microsoft Intune"** 连接"时选择"终结点"。

  c. 如果连接未打开，请选择该开关将其打开，然后选择"保存 **首选项"**。

  :::image type="content" source="images/enable-intune-connection.png" alt-text="Microsoft 365 Defender门户中的&quot;高级功能&quot;部分" lightbox="images/enable-intune-connection.png":::

  d. 转到"**Microsoft Endpoint Manager (Intune**) 并验证 Microsoft Defender for Endpoint-Intune 连接器是否已启用。

  :::image type="content" source="images/validate-intune-connector.png" alt-text="应用程序门户中的 intune 连接器Microsoft 365 Defender窗格" lightbox="images/validate-intune-connector.png":::

- **在 Android 连接器上为应用保护策略启用 Microsoft Defender for Endpoint (APP)**
  
  配置 Intune 上的连接器Microsoft Endpoint Manager应用保护策略：

  a. 转到 Microsoft **Defender >终结点的租户>和令牌**。

  b. 打开 Android 应用保护策略的 (如以下屏幕截图中所示) 。

  c. 选择“**保存**”。

  :::image type="content" source="images/app-settings.png" alt-text="应用程序门户中的应用程序Microsoft 365 Defender窗格" lightbox="images/app-settings.png":::

- **创建应用保护策略** 
 
通过创建应用保护策略，基于 Microsoft Defender for Endpoint 风险信号阻止访问或擦除托管应用的数据。
Microsoft Defender for Endpoint 可以配置为发送要用于应用保护策略 (应用（也称为 MAM) ）。 借助此功能，可以使用 Microsoft Defender for Endpoint 保护托管应用。

1. 创建策略 <br>
应用保护策略 (APP) 是可确保组织数据在托管应用中保持安全或受到控制的规则。 策略可以是在用户尝试访问或移动“公司”数据时强制执行的规则，或在用户位于应用内时受到禁止或监视的一组操作。 

:::image type="content" source="images/create-policy.png" alt-text="应用门户的应用保护策略页中的&quot;创建策略&quot;Microsoft 365 Defender选项卡" lightbox="images/create-policy.png":::

2. 添加应用 <br>
    a. 选择要如何将此策略应用到不同设备上的应用。 然后至少添加一个应用。 <br>
    使用此选项指定此策略是否适用于非托管设备。 在 Android 中，你可以指定适用于 Android Enterprise、设备管理员或非托管设备的策略。 还可以选择将策略定向到任何管理状态设备上的应用。
由于移动应用管理不需要设备管理，因此可在受管理和不受管理设备上保护公司数据。 管理以用户标识为中心，因而不再需要设备管理。 公司可以同时使用具有或不使用 MDM 的应用保护策略。 例如这样一种情况：员工同时使用公司电话和其个人平板电脑。 公司手机在 MDM 中注册，并受应用保护策略保护，而个人设备仅受应用保护策略保护。

    b. 选择应用<br>
    受管理应用是一种自身执行应用保护策略的应用，可由 Intune 管理。 已与 [Intune SDK](/mem/intune/developer/app-sdk) 集成或由 [Intune](/mem/intune/developer/apps-prepare-mobile-application-management) App Wrapping Tool包装的任何应用都可以使用 Intune 应用保护策略进行管理。 请参阅使用以下工具构建并可供公众使用的 [Microsoft Intune 保护的应用](/mem/intune/apps/apps-supported-intune-apps)的官方列表。

    *示例：Outlook托管应用*

  :::image type="content" source="images/managed-app.png" alt-text="应用程序门户中的&quot;公共Microsoft 365 Defender窗格" lightbox="images/managed-app.png":::


 3. 设置保护策略的登录安全要求。 <br>
在 **">条件"中选择** "设置允许的最大设备 **威胁级别"** ，然后输入一个值。 然后选择"  **操作："阻止访问"**。 Android 上的 Microsoft Defender for Endpoint 共享此设备威胁级别。

  :::image type="content" source="images/conditional-launch.png" alt-text="Microsoft 365 Defender门户中的&quot;设备Microsoft 365 Defender窗格" lightbox="images/conditional-launch.png":::
  
- **分配需要为其应用策略的用户组。**<br>
  选择 **"包含的组"**。 然后添加相关组。 

    :::image type="content" source="images/assignment.png" alt-text="应用程序门户中的&quot;包含Microsoft 365 Defender窗格" lightbox="images/assignment.png":::


## <a name="end-user-prerequisites"></a>最终用户先决条件
- 必须安装代理应用
    - Intune 公司门户
    
- 用户具有托管应用所需的许可证，并且安装了该应用

### <a name="end-user-onboarding"></a>最终用户载入 

1. 登录到托管应用程序，例如Outlook。 设备已注册，并且应用程序保护策略已同步到设备。 应用程序保护策略可识别设备的运行状况。  

2. 选择 **继续**。 显示一个屏幕，建议在 Android 应用上下载和设置 Microsoft Defender for Endpoint。

3. 选择“下载”。 你将重定向到 Google play (应用商店) 。 

4.  安装 Microsoft Defender for Endpoint (Mobile) 应用并启动"托管应用载入"屏幕。

  :::image type="content" source="images/download-mde.png" alt-text="说明性页面，包含下载 MDE 和启动应用载入屏幕的过程" lightbox="images/download-mde.png":::
  

5.  单击 **"继续>启动"**。 Microsoft Defender for Endpoint 应用载入/激活流已启动。 按照步骤完成载入。 将自动重定向回托管应用载入屏幕，现在指示设备运行正常。

6. 选择 **"** 继续"以登录到托管应用程序。 



## <a name="related-topics"></a>相关主题

- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
