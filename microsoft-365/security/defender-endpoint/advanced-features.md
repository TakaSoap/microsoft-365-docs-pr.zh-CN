---
title: 在 Microsoft Defender for Endpoint 中配置高级功能
description: 启用高级功能，如 Microsoft Defender for Endpoint 中的阻止文件。
keywords: 高级功能， 设置， 阻止文件， 自动调查， 自动解决， skype， microsoft defender for identity， office 365， azure 信息保护， intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bcb96ea29649bf3525b2ffcf6d5cbb5d299bacf3
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418112"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>在 Defender for Endpoint 中配置高级功能

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

根据你使用的 Microsoft 安全产品，某些高级功能可能可供你集成 Defender for Endpoint。

## <a name="enable-advanced-features"></a>启用高级功能

1. 在导航窗格中，选择 **首选项设置**  >  **高级功能**。
2. 选择要配置的高级功能，并切换 **开和****关之间的设置**。
3. 单击 **保存首选项**。

使用以下高级功能可以更好地防范潜在恶意文件，并获取安全调查期间更好的见解。

## <a name="automated-investigation"></a>自动调查

启用此功能以利用服务的自动调查和修正功能。 有关详细信息，请参阅自动 [调查](automated-investigations.md)。

## <a name="live-response"></a>实时响应

启用此功能，以便具有相应权限的用户可以在设备上启动实时响应会话。

有关角色分配详细信息，请参阅创建 [和管理角色](user-roles.md)。

## <a name="live-response-for-servers"></a>服务器实时响应
启用此功能，以便具有适当权限的用户可以启动服务器上实时响应会话。

有关角色分配详细信息，请参阅创建 [和管理角色](user-roles.md)。


## <a name="live-response-unsigned-script-execution"></a>实时响应未签名脚本执行

启用此功能后，您可以在实时响应会话中运行未签名的脚本。


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>限制与作用域内设备组之间的关联
启用此设置后，警报将基于其作用域的设备组关联到单独的事件。 默认情况下，在整个租户范围内发生事件关联。

>[!NOTE]
>更改此设置仅影响未来的警报关联。


## <a name="enable-edr-in-block-mode"></a>在阻止模式下启用 EDR
在阻止模式下 (EDR) 终结点检测和响应功能可提供对恶意项目的保护，即使 Microsoft Defender 防病毒在被动模式下运行。 打开后，阻止模式下的 EDR 将阻止在设备上检测到的恶意项目或行为。 阻止模式下的 EDR 在后台工作，可修正在泄露后检测到的恶意项目。

## <a name="autoresolve-remediated-alerts"></a>Autoresolve 修正警报

对于在 Windows 10 版本 1809 或之后创建的租户，自动调查和修正功能默认配置为解决自动分析结果状态为"未找到威胁"或"已修正"的警报。  如果不希望自动解决警报，需要手动关闭该功能。

> [!TIP]
> 对于在此版本之前创建的租户，你需要从高级功能页面手动 [启用](https://securitycenter.windows.com/preferences2/integration) 此功能。

> [!NOTE]
>
> - 自动解决操作的结果可能会影响基于设备上找到的活动警报的设备风险级别计算。
> - 如果安全操作分析师手动将警报状态设置为"正在进行"或"已解决"，则自动解决功能不会覆盖它。

## <a name="allow-or-block-file"></a>允许或阻止文件

仅在组织满足以下要求时，阻止才可用：

- 使用 Microsoft Defender 防病毒作为活动的反恶意软件解决方案，
- 启用基于云的保护功能

此功能使你能够阻止网络中潜在的恶意文件。 阻止文件将阻止在组织的设备上读取、写入或执行文件。

若要打开 **"允许"或"阻止** 文件"：：

1. 在导航窗格中，选择"**设置**  >  **""高级功能**  >  **""允许或阻止文件"。**

1. 切换开和 **关****之间的设置**。

    ![阻止文件功能的高级设置的图像](images/atp-preferences-setup.png)

1. 选择 **页面底部的** "保存首选项"。

启用此功能后，可以通过文件 [配置文件](respond-file-alerts.md#allow-or-block-file) 页上的 **"添加** 指示器"选项卡阻止文件。

## <a name="custom-network-indicators"></a>自定义网络指示器

启用此功能后，您可以创建 IP 地址、域或 URL 的指示器，这些指示器根据自定义指示器列表确定是否允许或阻止它们。

若要使用此功能，设备必须运行 Windows 10 版本 1709 或更高版本。 它们还应具有阻止模式和反恶意软件平台版本 4.18.1906.3 或更高版本的网络保护，请参阅[KB 4052623。](https://go.microsoft.com/fwlink/?linkid=2099834)

有关详细信息，请参阅管理 [指示器](manage-indicators.md)。

> [!NOTE]
> 网络保护利用信誉服务，在可能超出你为 Defender for Endpoint 数据选择的位置之外的位置处理请求。


## <a name="tamper-protection"></a>防篡改保护
在某些类型的网络攻击期间，不良参与者会尝试在你的计算机上禁用安全功能，如防病毒保护。 不良操作者希望禁用安全功能，以便更轻松地访问数据、安装恶意软件，或者以其他方式利用你的数据、标识和设备。

防篡改保护实质上会锁定 Microsoft Defender 防病毒，并阻止通过应用和方法更改安全设置。

保持防篡改功能打开，以防止对安全解决方案及其基本功能进行不必要的更改。

## <a name="show-user-details"></a>显示用户详细信息

启用此功能，以便你可以看到存储在 Azure Active Directory 中的用户详细信息。 详细信息包括调查用户帐户实体时的用户图片、姓名、职务和部门信息。 您可以在以下视图中找到用户帐户信息：

- 安全操作仪表板
- 警报队列
- 设备详细信息页面

有关详细信息，请参阅 [调查用户帐户](investigate-user.md)。

## <a name="skype-for-business-integration"></a>Skype for Business 集成

启用 Skype for Business 集成后，你能够使用 Skype for Business、电子邮件或电话与用户进行通信。 当你需要与用户通信并降低风险时，这很方便。

> [!NOTE]
> 当设备与网络隔离时，有一个弹出窗口，你可以选择启用 Outlook 和 Skype 通信，这将允许用户在断开与网络的连接时与其通信。 当设备在隔离模式下时，此设置适用于 Skype 和 Outlook 通信。

## <a name="azure-advanced-threat-protection-integration"></a>Azure 高级威胁防护集成

与 Azure 高级威胁防护的集成允许你直接透视另一个 Microsoft Identity 安全产品。 Azure 高级威胁防护通过有关可疑遭到入侵的帐户和相关资源的更多见解来扩大调查。 通过启用此功能，你将通过从标识的角度透视网络来丰富基于设备的调查功能。

> [!NOTE]
> 你需要具有相应的许可证才能启用此功能。

## <a name="office-365-threat-intelligence-connection"></a>Office 365 威胁智能连接

此功能仅在有活动的 Office 365 E5 或威胁智能加载项时可用。 有关详细信息，请参阅 Office 365 企业版 E5 产品页面。

启用此功能后，你将能够将 Office 365 高级威胁防护的数据合并到 Microsoft Defender 安全中心，以跨 Office 365 邮箱和 Windows 设备进行全面的安全调查。

> [!NOTE]
> 你需要具有相应的许可证才能启用此功能。

若要在 Office 365 威胁智能中接收上下文设备集成，你需要在安全与合规中心仪表板中启用适用于终结点& Defender。 有关详细信息，请参阅威胁 [调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

## <a name="microsoft-threat-experts"></a>Microsoft 威胁专家

在两个 Microsoft 威胁专家组件中，目标攻击通知一般可用。 专家按需功能仍处于预览阶段。 只有在应用预览版且应用程序已获得批准后，才能使用专家按需功能。 可以通过适用于终结点门户的 Defender 警报仪表板接收来自 Microsoft 威胁专家的定向攻击通知，如果已配置，可通过电子邮件接收。

> [!NOTE]
> 适用于终结点的 Defender 中的 Microsoft 威胁专家功能随企业移动性 + 安全性 的 E5 许可证 [一起提供](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)。

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

启用此设置将 Defender for Endpoint 信号转发到 Microsoft Cloud App Security，以便更深入地了解云应用程序使用情况。 转发的数据存储和处理位置与 Cloud App Security 数据位于同一位置。

> [!NOTE]
> 此功能将在运行 Windows 10 版本 1709 (OS 内部版本 16299.1085（具有[KB4493441](https://support.microsoft.com/help/4493441)版本）的设备上提供企业移动性[+](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)安全性的 E5) ， Windows 10 版本 1803 (OS 内部版本 17134.704（带[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10 版本 1809 (操作系统版本 17763.379，KB4489899) 或更高版本 Windows 10 版本）。 [](https://support.microsoft.com/help/4489899)

## <a name="azure-information-protection"></a>Azure 信息保护

打开此设置将允许信号转发到 Azure 信息保护。 它使数据所有者和管理员能够查看载入的设备上受保护的数据和设备风险分级。

## <a name="microsoft-secure-score"></a>Microsoft 安全功能分数

将 Microsoft Defender for Endpoint 信号转发到 Microsoft 365 安全中心中的 Microsoft 安全分数。 打开此功能后，Microsoft 安全功能分数可了解设备的安全状态。 转发数据的存储和处理位置与 Microsoft 安全分数数据位于同一位置。

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>从 Microsoft Defender 标识门户启用适用于终结点的 Microsoft Defender 集成

若要在 Microsoft Defender for Identity 中接收上下文设备集成，你还需要在 Microsoft Defender 标识门户中启用该功能。

1. 使用全局管理员或安全管理员角色登录到 [Microsoft Defender for Identity](https://portal.atp.azure.com/) 门户。

2. 单击 **"创建实例"。**

3. 将"集成"设置切换 **为"打开"，** 然后单击"保存 **"。**

在两个门户上完成集成步骤后，你将能够查看设备详细信息或用户详细信息页面中的相关警报。

## <a name="microsoft-intune-connection"></a>Microsoft Intune 连接

Defender for Endpoint 可以与 [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) 集成 [，以启用基于设备风险的条件访问](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。 当你 [启用此功能时](configure-conditional-access.md)，你将能够与 Intune 共享 Defender for Endpoint 设备信息，从而增强策略实施。

> [!IMPORTANT]
> 你需要在 Intune 和 Defender for Endpoint 上启用集成才能使用此功能。 有关特定步骤详细信息，请参阅在 [Defender for Endpoint 中配置条件访问](configure-conditional-access.md)。

此功能仅在具有以下功能时可用：

- 企业移动性 + 安全性 E3、Windows E5 (或 Microsoft 365 企业版 E5) 
- 一个活动的 Microsoft Intune 环境，与加入 Azure AD 的 Intune 托管的 Windows 10 [设备一起](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)。

### <a name="conditional-access-policy"></a>条件访问策略

启用 Intune 集成后，Intune 将自动创建经典条件访问 (CA) 策略。 此经典 CA 策略是设置到 Intune 的状态报告的先决条件。 不应删除它。

> [!NOTE]
> Intune 创建的经典 CA 策略与用于配置[](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)终结点的新式条件访问策略不同。

## <a name="preview-features"></a>预览功能

了解 Defender for Endpoint 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。

你将有权访问即将推出的功能，你可以提供反馈，以帮助在功能全面可用之前改进整体体验。

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>与 Microsoft 合规中心共享终结点警报

将终结点安全警报及其会审状态转发到 Microsoft 合规中心，从而通过警报增强内部风险管理策略，并修正内部风险，然后再造成危害。 转发的数据将处理并存储在与 Office 365 数据相同的位置。

在内部风险管理 [设置中](/microsoft-365/compliance/insider-risk-management-settings#indicators) 配置安全策略违反指示器后，适用于终结点的 Defender 警报将共享与适用用户的内部风险管理。

## <a name="related-topics"></a>相关主题

- [更新数据保留设置](data-retention-settings.md)
- [配置警报通知](configure-email-notifications.md)
