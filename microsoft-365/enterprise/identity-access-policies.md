---
title: 常见标识和设备访问策略-适用于企业的 Microsoft 365 |Microsoft 文档
description: 描述建议的通用标识和设备访问策略和配置。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: 8c4b136f30da0499b31102683f1a903e71813142
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547214"
---
# <a name="common-identity-and-device-access-policies"></a>常见标识和设备访问策略

本文介绍了用于保护对 Microsoft 365 云服务的访问的常见建议策略，包括使用 Azure Active Directory (Azure AD) 应用程序代理发布的本地应用程序。 

本指南讨论如何在新预配的环境中部署建议的策略。 在单独的实验室环境中设置这些策略，可以在将首展转移到预生产和生产环境之前，了解和评估建议的策略。 您的新设置的环境可以是仅云或混合环境，以反映您的评估需求。  

## <a name="policy-set"></a>策略集 

下图说明了建议的一组策略。 它显示了每个策略应用于哪一层的保护，以及这些策略是应用于 Pc、电话和平板电脑，还是适用于这两种类别的设备。 它还指明了配置这些策略的位置。

[ ![ 用于配置标识和设备访问的常见策略](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [请参阅此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

本文的其余部分介绍了如何配置这些策略。 

>[!Note]
>建议在 Intune 中注册设备之前，要求使用多重身份验证 (MFA) ，以确保设备在拥有预期的用户。 您必须先在 Intune 中注册设备，然后才能强制实施设备合规性策略。
>

为了让你有时间完成这些任务，我们建议你按照此表中所列的顺序实施基准策略。 但是，可随时实施针对敏感和高度受保护的保护级别的 MFA 策略。

|保护级别|策略|更多信息|
|:---------------|:-------|:----------------|
|**Baseline**|[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[阻止不支持新式身份验证的客户端](#block-clients-that-dont-support-modern-authentication)|不使用新式身份验证的客户端可以绕过条件访问策略，因此阻止这些策略是很重要的。|
|        |[高风险用户必须更改密码](#high-risk-users-must-change-password)|如果为其帐户检测到高风险活动，则强制用户在登录时更改其密码。|
|        |[应用应用数据保护策略](#apply-app-data-protection-policies)|每个平台一个 Intune 应用保护策略 (Windows、iOS/iPadOS、Android) 。|
|        |[需要经批准的应用和应用保护](#require-approved-apps-and-app-protection)|使用 iOS、iPadOS 或 Android 为电话和平板电脑强制实施移动应用保护。|
|        |[定义设备合规性策略](#define-device-compliance-policies)|每个平台一个策略。|
|        |[需要兼容电脑](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|使用 Windows 或 MacOS 强制对电脑进行 Intune 管理。|
|**敏感**|[当登录风险为*低*、*中*或*高*时，需要进行 MFA](#require-mfa-based-on-sign-in-risk)| |
|         |[需要符合要求 *的 pc 和* 移动设备](#require-compliant-pcs-and-mobile-devices)|为电脑 (Windows 或 MacOS) 和电话或平板电脑 (iOS、iPadOS 或 Android) 强制执行 Intune 管理。|
|**高度管控**|[*始终* 要求进行 MFA](#require-mfa-based-on-sign-in-risk)|
| | | |

## <a name="assigning-policies-to-groups-and-users"></a>将策略分配给组和用户

在配置策略之前，请确定您对每个保护层使用的 Azure AD 组。 通常情况下，基准保护适用于组织中的每个人。 同时包含在基线和敏感保护中的用户将应用所有基准策略加上敏感策略。 保护是累积的，并且强制实施最严格的策略。 

建议的做法是为条件访问排除创建 Azure AD 组。 在 "**工作分配**" 部分的 "**用户和组**的**排除**值" 设置中，将此组添加到所有条件访问策略。 这为您提供了在对访问问题进行故障排除时提供对用户的访问权限的方法。 建议仅将其作为临时解决方案。 监视此组的更改，并确保仅按预期使用排除组。 

下面的示例展示了需要进行 MFA 的组分配和排除。

![MFA 策略的组分配和排除示例](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

结果如下：

- 如果登录风险为 "中" 或 "高"，则所有用户都需要使用 MFA。

- 当登录风险为低、中或高时，执行人员组的成员需要使用 MFA。

  在这种情况下，执行人员组的成员与比较基准和敏感的条件访问策略相匹配。 这两个策略的访问控制组合在一起，在这种情况下与敏感的条件访问策略是等效的。

- Top Secret 项目 X 组的成员总是需要使用 MFA

  在这种情况下，Top Secret 项目 X 组的成员与比较基准和高度管控的条件访问策略相匹配。 这两个策略的访问控制组合在一起。 由于高管控条件访问策略的访问控制更具限制性，因此使用它。

对组和用户应用更高级别的保护时要小心。 例如，在每次登录时，最高密码项目 X 组的成员将需要使用 MFA，即使他们不负责项目 X 的高管控内容。  

作为这些建议的一部分创建的所有 Azure AD 组都必须创建为 Microsoft 365 组。 在保护 Microsoft 团队和 SharePoint 中的文档时，这一点对敏感度标签的部署非常重要。

![用于创建 Microsoft 365 组的屏幕捕获](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>需要基于登录风险进行 MFA

您应该让用户在需要使用之前注册 MFA。 如果您有 Microsoft 365 E5、Microsoft 365 E3 和 Identity & 威胁防护外接程序、Office 365 with EMS E5 或单独的 Azure AD 高级 P2 许可证，则可以将 MFA 注册策略与 Azure AD Identity Protection 结合使用，以要求用户注册进行 MFA。 [先决条件工作](identity-access-prerequisites.md)包括向具有 MFA 的所有用户注册。

注册用户后，您可以使用新的条件访问策略要求使用 MFA 进行登录。

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。
2. 在 Azure 服务列表中，选择 " **Azure Active Directory**"。
3. 在 " **管理** " 列表中，选择 " **安全性**"，然后选择 " **条件访问**"。
4. 选择 " **新建策略** "，然后键入新策略的名称。

下表介绍了根据登录风险要求进行 MFA 的条件访问策略设置。

在 " **工作分配** " 部分：

|设置|属性|值|注意|
|:---|:---------|:-----|:----|
|用户和组|包括| **选择 "用户和组" > 用户和组**：选择包含目标用户帐户的特定组。 |从包含试点用户帐户的组开始。|
||排除| **用户和组**：选择您的条件访问例外组;)  (应用程序标识的服务帐户。|应在需要的临时基础上修改成员资格。|
|云应用或操作| **包含的云应用 >** | **选择应用**程序：选择要应用此策略的应用程序。 例如，选择 "Exchange Online"。||
|条件| | |配置特定于您的环境和需求的条件。|
||登录风险||请参阅下表中的指南。|
|||||

**登录风险条件设置**

根据目标的保护级别应用风险级别设置。

|保护级别|需要的风险级别值|Action|
|:---------|:-----|:----|
|基线|高、中|检查两者。|
|敏感|高、中、低|检查全部三个。|
|高度管控| |将所有选项保留为未选中状态，以始终强制执行 MFA。|
||||

在 " **访问控制** " 部分：

|设置|属性|值|Action|
|:---|:---------|:-----|:----|
|授予|**Grant access**| | Select |
|||**需要多因素身份验证**| 支票 |
||**需要所有已选控件** ||Select|
|||||

选择 " **选择** " 以保存 **授予** 设置。

最后，选择 **"** **启用策略**"，然后选择 " **创建**"。

此外，请考虑使用 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 工具来测试策略。

## <a name="block-clients-that-dont-support-modern-authentication"></a>阻止不支持新式身份验证的客户端

将这些表中的设置用于条件访问策略，以阻止不支持新式身份验证的客户端。

请参阅 [本文](microsoft-365-client-support-modern-authentication.md) ，获取 suppport 新式验证的 Microsoft 365 中的客户端列表。

在 " **工作分配** " 部分：

|设置|属性|值|注意|
|:---|:---------|:-----|:----|
|用户和组|包括| **选择 "用户和组" > 用户和组**：选择包含目标用户帐户的特定组。 |从包含试点用户帐户的组开始。|
||排除| **用户和组**：选择您的条件访问例外组;)  (应用程序标识的服务帐户。|应在需要的临时基础上修改成员资格。|
|云应用或操作|**包含的云应用 >**| **选择 "应用程序**"：选择与不支持新式身份验证的客户端对应的应用程序。||
|条件| **客户端应用** | 为 **"配置" 选择 "是"** **Configure** <br> 清除**浏览器**和**移动应用程序和桌面客户端**的复选标记 | |
||||

在 " **访问控制** " 部分：

|设置|属性|值|Action|
|:---|:---------|:-----|:----|
|授予|**阻止访问**| | Select |
||**需要所有已选控件** ||Select|
|||||

选择 " **选择** " 以保存 **授予** 设置。

最后，选择 **"** **启用策略**"，然后选择 " **创建**"。

请考虑使用 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 工具来测试策略。

## <a name="high-risk-users-must-change-password"></a>高风险用户必须更改密码

若要确保所有高风险用户的受损帐户强制在登录时执行密码更改，必须应用以下策略。

Log in to the [Microsoft Azure portal (https://portal.azure.com)](https://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.

在 " **工作分配** " 部分：

|类型|属性|值|Action|
|:---|:---------|:-----|:----|
|Users|包括|**所有用户**|Select|
|用户风险| **High**||Select|
|||||

在 "第二个 **工作分配** " 部分：

| 类型 | 属性 | 值                  | Action |
|:-----|:-----------|:------------------------|:------|
| Access | **允许访问** |  | Select  |
|      |     | **需要更改密码** | 支票  |
|||||

选择 " **完成** " 以保存 **访问** 设置。

最后，为 "**强制策略**" 选择 **"启用**"，然后选择 "**保存**"。

请考虑使用 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 工具来测试策略。

将此策略与 " [配置 AZURE AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)" 结合使用，可检测并阻止已知弱密码及其变种以及特定于您的组织的其他薄弱术语。 使用 Azure AD 密码保护可确保更改的密码是强密码。

## <a name="apply-app-data-protection-policies"></a>应用应用数据保护策略

应用程序保护策略 (应用程序) 定义允许哪些应用程序以及可以对组织的数据执行的操作。 应用程序中提供的选项使组织能够根据其特定需求调整保护。 在某些情况下，实现完整方案可能不太清楚需要哪些策略设置。 为了帮助组织确定移动客户端终结点强化的优先级，Microsoft 为 iOS 和 Android 移动应用管理的应用程序数据保护框架引入了分类。 

应用程序数据保护框架分为三个不同的配置级别，每个级别都建立了上一个级别： 

- **企业基本数据保护** (级别 1) 可确保使用 PIN 对应用程序进行保护并进行加密，并执行选择性擦除操作。 对于 Android 设备，此级别验证 Android 设备证明。 这是一种入门级配置，它在 Exchange Online 邮箱策略中提供了类似的数据保护控制，并介绍了它和用户对应用程序的人口。 
- **企业增强的数据保护** (级别 2) 介绍了应用程序数据泄露预防机制和最低操作系统要求。 这是适用于大多数移动用户访问工作或学校数据的配置。 
- **企业高数据保护** (级别 3) 引入了高级数据保护机制、增强的 PIN 配置和应用程序移动威胁防御。 访问高风险数据的用户需要此配置。 

若要查看每个配置级别和必须受保护的最小应用程序的特定建议，请查看 [使用应用保护策略的 Data protection framework](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)。 

使用 [标识和设备访问配置](microsoft-365-policies-configurations.md)中概述的原则，比较基准和敏感保护层与第2级企业增强型数据保护设置密切对应。 高度管控的保护层密切映射到3级企业高数据保护设置。

|保护级别 |应用保护策略  |更多信息  |
|---------|---------|---------|
|基线     | [2级增强数据保护](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | 在级别2中强制实施的策略设置包括为级别1建议的所有策略设置，并且仅添加或更新以下策略设置以实现更多控件和级别1更复杂的配置。         |
|敏感     | [2级增强数据保护](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | 在级别2中强制实施的策略设置包括为级别1建议的所有策略设置，并且仅添加或更新以下策略设置以实现更多控件和级别1更复杂的配置。        |
|高度管控     | [3级企业高数据保护](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | 在级别3中强制实施的策略设置包括为级别1和2建议的所有策略设置，并且仅添加或更新以下策略设置，以实现更多控件和级别2的更复杂的配置。        |

若要使用数据保护框架设置为 Microsoft 终结点管理器中的每个平台 (iOS 和 Android) 创建新的应用保护策略，您可以执行以下操作：

1. 按照 [如何使用 Microsoft Intune 创建和部署应用保护策略](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)中的步骤手动创建策略。 
2. 使用[intune 的 PowerShell 脚本](https://github.com/microsoftgraph/powershell-intune-samples)导入示例[Intune 应用保护策略配置框架 JSON 模板](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies)。

## <a name="require-approved-apps-and-app-protection"></a>需要经批准的应用和应用保护

若要强制实施在 Intune 中应用的应用保护策略，必须创建一个条件访问策略，以要求已批准的客户端应用程序和应用保护策略中设置的条件。 

强制应用保护策略要求中所述的一组策略需要 [具有条件访问权限的云应用访问权限的应用程序保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。 这两个策略都包含在此建议的一组标识和访问配置策略中。

若要创建需要经批准的应用程序和应用程序保护的条件访问策略，请按照 [方案1： microsoft 365 apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)中的 "为 Microsoft 365 配置 Azure AD 条件访问策略" 中的 "应用保护策略"，这将允许 Outlook for IOS 和 Android，但阻止支持 OAuth 的 exchange ActiveSync 客户端连接到 Exchange Online。

   > [!NOTE]
   > 此策略可确保移动用户可以使用适用的应用程序访问所有 Office 终结点。

如果要启用对 Exchange Online 的移动访问，请实施 [阻止 ActiveSync 客户端](secure-email-recommended-policies.md#block-activesync-clients)，这将阻止 exchange activesync 客户端利用基本身份验证连接到 exchange online。 本文顶部的插图中未对此策略进行图示。 在 [保护电子邮件的策略建议中对](secure-email-recommended-policies.md)其进行了描述和图示。

 这些策略利用授予权限控制 [请求批准的客户端应用程序](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) 并 [需要应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)。

最后，为 iOS 和 Android 设备上的其他客户端应用程序阻止旧版身份验证，以确保这些客户端无法绕过条件访问策略。 如果你按照本文中的指导进行，你已配置 [阻止不支持新式身份验证的客户端](#block-clients-that-dont-support-modern-authentication)。

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>定义设备合规性策略

设备合规性策略定义了设备必须满足的要求以确定为合规性。 您可以从 Microsoft 终结点管理器管理中心中创建 Intune 设备合规性策略。

必须为每台电脑、电话或平板电脑平台创建策略：

- Android 设备管理员
- Android 企业版
- iOS/iPadOS
- macOS
- Windows 8.1 及更高版本
- Windows 10 及更高版本

若要创建设备合规性策略，请使用管理员凭据登录[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)，然后导航到 "**设备**  >  **合规性策略**"  >  **策略**。 选择 " **创建策略**"。

对于要部署的设备合规性策略，必须将其分配给用户组。 您在创建并保存策略后分配该策略。 在管理中心中，选择策略，然后选择 " **分配**"。 选择要接收策略的组后，选择 " **保存** " 以保存该组分配并部署该策略。

有关在 Intune 中创建合规性策略的分步指南，请参阅 Intune 文档中的在 [Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) 。

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10 及更高版本的推荐设置

对于运行 Windows 10 及更高版本的电脑，建议在策略创建过程的 " **步骤2：合规性设置**" 中配置以下设置。

有关 **设备运行状况 > Windows 运行状况证明服务评估规则**，请参阅此表。

|属性|值|Action|
|:---------|:-----|:----|
|需要 BitLocker|需要| Select |
|要求在设备上启用安全启动|需要| Select |
|需要代码完整性|需要| Select |
||||

对于 " **设备属性**"，请根据您的 IT 和安全策略为操作系统版本指定适当的值。

若要 **配置管理器合规性**，请选择 " **需要**"。

有关 **系统的安全性**，请参阅此表。

|类型|属性|值|Action|
|:---|:---------|:-----|:----|
|Password|需要密码才能解锁移动设备|需要| Select |
||简单密码|阻止|Select|
||密码类型|设备默认值|Select|
||最短密码长度|6 |类型|
||在需要密码之前不活动的最长分钟数|15 |类型 <br>Android 版本4.0 及更高版本或 KNOX 4.0 及更高版本支持此设置。 对于 iOS 设备，支持 iOS 8.0 和更高版本。|
||密码过期 (天) |41|类型|
||用于防止重复使用的以前密码的数目|5 |类型|
||设备从空闲状态返回时需要密码 (移动和全息) |需要|适用于 Windows 10 及更高版本|
|加密|设备上的数据存储加密|需要|Select|
|设备安全性|Firewall|需要|Select|
||防病毒|需要|Select|
||间谍|需要|Select <br> 此设置需要在 Windows 安全中心中注册的反间谍软件解决方案。|
|Defender|Microsoft Defender 反恶意软件|需要|Select|
||Microsoft Defender 反恶意软件最低版本||类型 <br> 仅支持 Windows 10 桌面版。 Microsoft 建议版本的背后不超过最新版本五个。|
||最新的 Microsoft Defender 反恶意软件签名|需要|Select|
||实时保护|需要|Select <br>仅支持 Windows 10 桌面版|
|||||

**Microsoft Defender ATP**

|类型|属性|值|Action|
|:---|:---------|:-----|:----|
|Microsoft Defender 高级威胁防护规则|要求设备在计算机风险得分|中|Select|
|||||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>要求兼容的电脑 (但不符合合规性的电话和平板电脑) 

在将策略添加到需要兼容的电脑之前，请务必在 Intune 中注册设备进行管理。 建议在将设备注册到 Intune 中之前使用多重身份验证，以确保设备已占有目标用户。 

若要要求合规的电脑：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。
2. 在 Azure 服务列表中，选择 " **Azure Active Directory**"。
3. 在 " **管理** " 列表中，选择 " **安全性**"，然后选择 " **条件访问**"。
4. 选择 " **新建策略** "，然后键入新策略的名称。

5. 在 " **分配**" 下，选择 " **用户和组** "，并包括您希望该策略应用于谁。 此外，还排除您的条件访问排除组。

6. 在 " **分配**" 下，选择 " **云应用或操作**"。

7. 对于 " **包含**"，选择 " **选择应用" > 选择**"，然后从" **云应用** "列表中选择所需的应用。 例如，选择 "Exchange Online"。 完成后选择 " **选择** "。

8. 若要要求兼容的电脑 (但不符合兼容电话和平板电脑) ，请在 " **分配**" 下选择 " **条件 > 设备平台**"。 为 **"配置" 选择 "是"** 。 **Configure** 选择 "  **选择设备平台**"，选择 " **Windows** " 和 " **macOS**"，然后选择 " **完成**"。

9. 在 " **访问控制**" 下，选择 " **授予** "。

10. 选择 " **授予访问权限** "，然后选中 " **要求将设备标记为合规**"。 对于多个控件，选择 **"要求所有选定控件"**。 完成后，选择 " **选择**"。 

10. 为 **"** **启用策略**" 选择 "启用"，然后选择 " **创建**"。

>[!Note]
>启用此策略之前，请确保你的设备兼容。 否则，在将您的用户帐户添加到条件访问排除组之前，您可能会被锁定，并且将无法更改此策略。
>

## <a name="require-compliant-pcs-and-mobile-devices"></a>需要符合要求 *的 pc 和* 移动设备

若要要求所有设备符合性，请执行以下操作：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。
2. 在 Azure 服务列表中，选择 " **Azure Active Directory**"。
3. 在 " **管理** " 列表中，选择 " **安全性**"，然后选择 " **条件访问**"。
4. 选择 " **新建策略** "，然后键入新策略的名称。

5. 在 " **分配**" 下，选择 " **用户和组** "，并包括您希望该策略应用于谁。 此外，还排除您的条件访问排除组。

6. 在 " **分配**" 下，选择 " **云应用或操作**"。

7. 对于 " **包含**"，选择 " **选择应用" > 选择**"，然后从" **云应用** "列表中选择所需的应用。 例如，选择 "Exchange Online"。 完成后选择 " **选择** "。

8. 在 " **访问控制**" 下，选择 " **授予** "。

9. 选择 " **授予访问权限** "，然后选中 " **要求将设备标记为合规**"。 对于多个控件，选择 **"要求所有选定控件"**。 完成后，选择 " **选择**"。 

10. 为 **"** **启用策略**" 选择 "启用"，然后选择 " **创建**"。

>[!Note]
>启用此策略之前，请确保你的设备兼容。 否则，在将您的用户帐户添加到条件访问排除组之前，您可能会被锁定，并且将无法更改此策略。
>

## <a name="next-step"></a>后续步骤

![步骤3：针对来宾和外部用户的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)


[了解来宾和外部用户的策略建议](identity-access-policies-guest-access.md)
