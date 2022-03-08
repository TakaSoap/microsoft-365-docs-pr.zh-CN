---
title: 在 Microsoft Defender for Endpoint 中配置高级功能
description: 打开 Microsoft Defender for Endpoint 中的阻止文件等高级功能。
keywords: 高级功能， 设置， 阻止文件， 自动调查， 自动解决， skype， microsoft defender for identity， office 365， azure 信息保护， intune
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56a836e14051e3f621fb42fd518fb2cf5efe8bed
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327695"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>在 Defender for Endpoint 中配置高级功能

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedfeats-abovefoldlink)。

根据你使用的 Microsoft 安全产品，某些高级功能可能可供你集成 Defender for Endpoint。

## <a name="enable-advanced-features"></a>启用高级功能

1. 在导航窗格中，选择"**设置** \> **终结点** \> **高级功能"**。
2. 选择要配置的高级功能，并切换开和 **关****之间的设置**。
3. 单击 **"保存首选项"**。

使用以下高级功能可以更好地防范潜在恶意文件，并获取安全调查期间更好的见解。

## <a name="automated-investigation"></a>自动调查

启用此功能以利用服务的自动调查和修正功能。 有关详细信息，请参阅自动 [调查](automated-investigations.md)。

## <a name="live-response"></a>实时响应

> [!NOTE]
> 实时响应 **需要启用** 自动调查，然后才能在 Microsoft Defender for Endpoint 门户的高级设置部分中启用它。

启用此功能，以便具有相应权限的用户可以在设备上启动实时响应会话。

有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。

## <a name="live-response-for-servers"></a>服务器实时响应

启用此功能，以便具有适当权限的用户可以启动服务器上实时响应会话。

有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。

## <a name="live-response-unsigned-script-execution"></a>实时响应未签名脚本执行

启用此功能后，您可以在实时响应会话中运行未签名的脚本。

## <a name="always-remediate-pua"></a>始终修正 PUA

PUA (可能不需要) 是一类软件，可能会导致你的计算机运行缓慢、显示意外广告或在最差时安装其他软件（可能是意外的或不需要的）。

启用此功能，以便 (PUA) ，即使未在设备上配置 PUA 保护，在租户的所有设备上也进行修正。 这有助于防止用户无意中在设备上安装不需要的应用程序。 关闭后，修正取决于设备配置。

## <a name="restrict-correlation-to-within-scoped-device-groups"></a>限制与作用域内设备组之间的关联

此配置可用于本地 SOC 操作希望仅将警报关联限制为可以访问的设备组的方案。 打开此设置后，由跨设备组的警报组成的事件将不再被视为单个事件。 然后，本地 SOC 可以针对事件采取措施，因为他们可以访问涉及的设备组之一。 但是，全局 SOC 将按设备组而不是一个事件查看多个不同的事件。 建议不要启用此设置，除非这样做超出了整个组织中事件相关性的好处。

> [!NOTE]
> 更改此设置仅影响未来的警报关联。

## <a name="enable-edr-in-block-mode"></a>启用EDR阻止模式

终结点检测和响应 (EDR) 在阻止模式下提供对恶意项目的保护，即使 Microsoft Defender 防病毒处于被动模式时。 打开后，EDR模式阻止在设备上检测到的恶意项目或行为。 EDR阻止模式在后台工作，以修正在泄露后检测到的恶意项目。

## <a name="autoresolve-remediated-alerts"></a>Autoresolve 修正警报

对于在 Windows 10 版本 1809 或之后创建的租户，自动调查和修正功能默认配置为解决自动分析结果状态为"未找到威胁"或"已修正"的警报。 如果不希望自动解决警报，需要手动关闭该功能。

> [!TIP]
> 对于在此版本之前创建的租户，你需要从高级功能页面手动 [启用](https://security.microsoft.com//preferences2/integration) 此功能。

> [!NOTE]
>
> - 自动解决操作的结果可能会影响基于在设备上找到的活动警报的设备风险级别计算。
> - 如果安全操作分析师手动将警报状态设置为"正在进行"或"已解决"，则自动解决功能不会覆盖它。

## <a name="allow-or-block-file"></a>允许或阻止文件

仅在组织满足以下要求时，阻止才可用：

- 使用 Microsoft Defender 防病毒 作为活动的反恶意软件解决方案，
- 启用基于云的保护功能

此功能使你能够阻止网络中潜在的恶意文件。 阻止文件将阻止在组织的设备上读取、写入或执行文件。

若要打开 **"允许"或"阻止** 文件"：：

1. 在导航窗格中，**选择"**\>设置 **终结点""** \>  \>常规 **高级功能** \> **""允许或阻止文件"**。

1. 在"开"和" **关"** 之间 **切换设置**。
 
    :::image type="content" source="../../media/alloworblockfile.png" alt-text="阻止文件功能的高级设置的图像。":::

1. 选择 **页面底部的** "保存首选项"。

启用此功能后，可以通过文件 [配置文件](respond-file-alerts.md#allow-or-block-file) 页上的 **"添加** 指示器"选项卡阻止文件。

## <a name="custom-network-indicators"></a>自定义网络指示器

启用此功能后，您可以创建 IP 地址、域或 URL 的指示器，这些指示器根据自定义指示器列表确定是否允许或阻止它们。

若要使用此功能，设备必须运行Windows 10版本 1709 或更高版本，Windows 11。 它们还应具有阻止模式和反恶意软件平台版本 4.18.1906.3 或更高版本的网络保护 [，请参阅 KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)。

有关详细信息，请参阅管理 [指示器](manage-indicators.md)。

> [!NOTE]
> 网络保护利用信誉服务，在可能超出你为 Defender for Endpoint 数据选择的位置之外的位置处理请求。

## <a name="tamper-protection"></a>防篡改保护
在某些类型的网络攻击期间，不良参与者会尝试在你的计算机上禁用安全功能，如防病毒保护。 不良操作者希望禁用安全功能，以便更轻松地访问数据、安装恶意软件或以其他方式利用你的数据、标识和设备。

防篡改保护实质上Microsoft Defender 防病毒并阻止通过应用和方法更改安全设置。

如果你的组织使用基于云的保护Microsoft Defender 防病毒则此功能可用。 有关详细信息，请参阅通过云保护[在 Microsoft Defender 防病毒中使用下一代技术](cloud-protection-microsoft-defender-antivirus.md)。

保持防篡改功能打开，以防止对安全解决方案及其基本功能进行不必要的更改。

## <a name="show-user-details"></a>显示用户详细信息

启用此功能，以便你可以查看存储在Azure Active Directory。 详细信息包括调查用户帐户实体时的用户图片、姓名、职务和部门信息。 您可以在以下视图中找到用户帐户信息：

- 安全操作仪表板
- 警报队列
- 设备详细信息页面

有关详细信息，请参阅 [调查用户帐户](investigate-user.md)。

## <a name="skype-for-business-integration"></a>Skype for Business 集成

通过启用Skype for Business集成，可以使用电子邮件、电子邮件或Skype for Business与用户进行通信。 当你需要与用户通信并降低风险时，这很方便。

> [!NOTE]
> 当设备与网络隔离时，有一个弹出窗口，你可以选择启用 Outlook 和 Skype 通信，这将允许用户在断开与网络的连接时与其通信。 此设置适用于设备在Skype Outlook时的通信和通信。

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender for Identity 集成

与 Microsoft Defender for Identity 的集成允许你直接透视另一个 Microsoft Identity 安全产品。 Microsoft Defender for Identity 通过有关可疑遭到入侵的帐户和相关资源的更多见解来扩大调查。 通过启用此功能，你将通过从标识的角度透视网络来丰富基于设备的调查功能。

> [!NOTE]
> 你需要具有相应的许可证才能启用此功能。

## <a name="office-365-threat-intelligence-connection"></a>Office 365威胁智能连接

此功能仅在你拥有活动加载项或威胁Office 365 E5可用。 有关详细信息，请参阅 Office 365 企业版 E5 产品页。

启用此功能后，你将能够将 Microsoft Defender for Office 365 数据合并到 Microsoft 365 Defender 中，以便跨 Office 365 邮箱和 Windows 设备进行全面安全调查。

> [!NOTE]
> 你需要具有相应的许可证才能启用此功能。

若要在威胁情报中Office 365上下文设备集成，你需要在安全与合规中心仪表板中启用 Defender for Endpoint &设置。 有关详细信息，请参阅威胁 [调查和响应](/microsoft-365/security/office-365-security/office-365-ti)。

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft 威胁专家 - 目标攻击通知

在两个 Microsoft 威胁专家组件中，目标攻击通知一般可用。 专家按需功能仍处于预览阶段。 如果你已申请预览，并且你的应用程序已获得批准，你只能使用专家按需功能。 可以通过 Defender for Endpoint 门户的警报仪表板接收来自 Microsoft 威胁专家 的定向攻击通知，如果已配置，可以通过电子邮件接收。

> [!NOTE]
> Defender Microsoft 威胁专家 终结点中的 Microsoft 威胁专家 功能随适用于 企业移动性 + 安全性 的 E5 [许可证一企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)。

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

启用此设置将 Defender for Endpoint 信号转发到 Microsoft Defender for Cloud Apps，以便更深入地了解云应用程序使用情况。 转发的数据存储和处理位置与 Defender for Cloud Apps 数据位于同一位置。

> [!NOTE]
> 此功能将随 E5 许可证一起提供，[企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)设备上运行Windows 10。 版本 1709 (OS 内部版本 16299.1085（带 [KB4493441](https://support.microsoft.com/help/4493441)) ，Windows 10，版本 1803 (OS 内部版本 17134.704，具有 [KB4493464](https://support.microsoft.com/help/4493464)) ，Windows 10 版本 1809 (OS 内部版本 17763.379[KB4489899](https://support.microsoft.com/help/4489899)) 、Windows 10版本或 Windows 11。

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>从 Microsoft Defender 标识门户启用适用于终结点的 Microsoft Defender 集成

若要在 Microsoft Defender for Identity 中接收上下文设备集成，你还需要在 Microsoft Defender 标识门户中启用该功能。

1. 使用全局管理员或安全管理员角色登录到 [Microsoft Defender for Identity](https://portal.atp.azure.com/) 门户。

2. 单击 **"创建实例"**。

3. 将"集成"设置切换 **为"打开"** ，然后单击"保存 **"**。

在两个门户上完成集成步骤后，你将能够查看设备详细信息或用户详细信息页面中的相关警报。

## <a name="web-content-filtering"></a>Web 内容筛选

阻止访问包含不需要的内容的网站，并跟踪所有域中的 Web 活动。 若要指定要阻止的 Web 内容类别，请创建 [Web 内容筛选策略](https://security.microsoft.com/preferences2/web_content_filtering_policy)。 部署 Microsoft Defender for Endpoint 安全基线时，请确保网络保护在 [阻止模式下](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)。

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>与 Microsoft 合规中心共享终结点警报

将终结点安全警报及其会审状态转发到 Microsoft 合规中心，从而通过警报增强内部风险管理策略，并修正内部风险，然后再造成危害。 转发的数据将处理并存储在与传输数据相同的Office 365位置。

在内部风险管理 [设置中](/microsoft-365/compliance/insider-risk-management-settings#indicators) 配置安全策略违反指示器后，适用于终结点的 Defender 警报将共享与适用用户的内部风险管理。

## <a name="microsoft-intune-connection"></a>Microsoft Intune连接

Defender for Endpoint 可以与 Microsoft Intune[集成，以启用基于设备风险的条件访问](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。[](/intune/what-is-intune) 启用 [此功能后](configure-conditional-access.md)，你将能够与 Intune 共享 Defender for Endpoint 设备信息，从而增强策略实施。

> [!IMPORTANT]
> 你需要在 Intune 和 Defender for Endpoint 上启用集成才能使用此功能。 有关特定步骤详细信息，请参阅在 [Defender for Endpoint 中配置条件访问](configure-conditional-access.md)。

此功能仅在具有以下功能时可用：

- 适用于 E5 企业移动性 + 安全性 E3或 Windows E5 (或 Microsoft 365 企业版 的许可租户) 
- Active Microsoft Intune环境，已加入 Intune Windows设备[Azure AD设备](/azure/active-directory/devices/concept-azure-ad-join/)。

### <a name="conditional-access-policy"></a>条件访问策略

启用 Intune 集成后，Intune 将自动创建经典条件访问 (CA) 策略。 此经典 CA 策略是设置到 Intune 的状态报告的先决条件。 不应将其删除。

> [!NOTE]
> Intune 创建的经典 CA 策略与用于配置终结点的新式[](/azure/active-directory/conditional-access/overview/)条件访问策略不同。

## <a name="device-discovery"></a>设备发现

帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的流程更改。 使用载入的设备，可以在网络中查找非托管设备，并评估漏洞和风险。 有关详细信息，请参阅设备 [发现](device-discovery.md)。

> [!NOTE]
> 你始终可以应用筛选器以从设备清单列表中排除非托管设备。 您还可以使用 API 查询上的载入状态列筛选出非托管设备。

## <a name="preview-features"></a>预览功能

了解 Defender for Endpoint 预览版中的新功能。 通过打开预览体验来尝试即将推出的功能。

你将有权访问即将推出的功能，你可以提供反馈，以帮助在功能全面可用之前改进整体体验。

## <a name="download-quarantined-files"></a>下载隔离文件

在安全合规的位置备份隔离文件，以便可以直接从隔离区下载这些文件。 " **下载文件** "按钮将始终在文件页面中可用。 默认情况下，此设置为打开状态。 [详细了解要求](respond-file-alerts.md#download-quarantined-files)

## <a name="related-topics"></a>相关主题

- [更新数据保留设置](data-retention-settings.md)
- [配置警报通知](configure-email-notifications.md)
