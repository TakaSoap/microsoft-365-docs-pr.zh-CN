---
title: 常见标识和设备访问策略-Microsoft 365 企业版 |Microsoft 文档
description: 介绍针对有关如何应用标识和设备访问策略以及配置的 Microsoft 建议的策略。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: b6e10757c3a4370c83b6ee0c1fb6c818a13089ea
ms.sourcegitcommit: 7eaecb91c7cb1f8679f99882563f5c1149175992
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "43022917"
---
# <a name="common-identity-and-device-access-policies"></a>常见标识和设备访问策略
本文介绍了用于保护云服务访问的常见建议策略，其中包括使用 Azure AD 应用程序代理发布的本地应用程序。 

本指南讨论如何在新预配的环境中部署建议的策略。 在单独的实验室环境中设置这些策略，可以在将首展转移到预生产和生产环境之前，了解和评估建议的策略。 您的新设置的环境可能是仅云或混合的。  

## <a name="policy-set"></a>策略集 

下图说明了建议的一组策略。 它显示了每个策略应用于哪一层的保护，以及这些策略是应用于 Pc、电话和平板电脑，还是适用于这两种类别的设备。 它还指示这些策略的配置位置。

![用于配置标识和设备访问的常见策略](../media/Identity_device_access_policies_byplan.png)


本文的其余部分介绍了如何配置这些策略。 

建议在将设备注册到 Intune 中之前使用多重身份验证，以确保设备已占有目标用户。 在强制实施设备合规性策略之前，还必须将设备注册到 Intune。

为了让你有时间完成这些任务，我们建议你按照此表中所列的顺序实施基准策略。 但是，敏感和高度管控保护的 MFA 策略可在任何时候实施。


|保护级别|策略|更多信息|
|:---------------|:-------|:----------------|
|**Baseline**|[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[阻止不支持新式身份验证的客户端](#block-clients-that-dont-support-modern-authentication)|不使用新式身份验证的客户端可以绕过条件访问规则，因此，请务必阻止这些|
|        |[高风险用户必须更改密码](#high-risk-users-must-change-password)|如果为帐户检测到高风险活动，则强制用户在登录时更改其密码|
|        |[定义应用保护策略](#define-app-protection-policies)|每个平台（iOS、Android、Windows）一个策略。|
|        |[需要支持 Intune 应用保护策略的应用程序](#require-apps-that-support-intune-app-protection-policies)|为电话和平板电脑强制实施移动应用保护|
|        |[定义设备合规性策略](#define-device-compliance-policies)|每个平台一个策略|
|        |[需要兼容电脑](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|强制对电脑进行 Intune 管理|
|**敏感**|[当登录风险为*低*、*中*或*高*时，需要进行 MFA](#require-mfa-based-on-sign-in-risk)| |
|         |[需要符合要求*的 pc 和*移动设备](#require-compliant-pcs-and-mobile-devices)|对电脑和电话/平板电脑强制 Intune 管理|
|**高度管控**|[*始终*要求进行 MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>向用户分配策略
在配置策略之前，请确定您对每个保护层使用的 Azure AD 组。 通常情况下，基准保护适用于组织中的每个人。 同时包含在基线和敏感保护中的用户将应用所有基准策略加上敏感策略。 保护是累积的，并且强制实施最严格的策略。 

建议的做法是为条件访问排除创建 Azure AD 组。 将此组添加到 "Exclude" 下的所有条件访问规则。 这为您提供了在对访问问题进行故障排除时提供对用户的访问权限的方法。 建议仅将其作为临时解决方案。 监视此组的更改，并确保仅按预期使用排除组。 

下图提供了用户分配和排除的示例。

![用于 MFA 规则的用户分配和排除示例](../media/identity-access-policies-assignment.png)

在图中，"Top secret project X team" 分配了一个需要*始终*进行 MFA 的条件访问策略。 对用户应用更高级别的保护时要合理。 此项目团队的成员将需要在每次登录时提供两种形式的身份验证，即使他们没有查看高度管控的内容也是如此。  

作为这些建议的一部分创建的所有 Azure AD 组都必须创建为 Office 365 组。 在 SharePoint Online 中保护文档时，这一点对于部署 Azure 信息保护 (AIP) 尤为重要。

![用于创建 Office 365 组的屏幕捕获](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>需要基于登录风险进行 MFA
在要求进行 MFA 之前，首先使用标识保护 MFA 注册策略为用户注册 MFA。 注册用户后，可以强制进行 MFA 以进行登录。 [先决条件工作](identity-access-prerequisites.md)包括向具有 MFA 的所有用户注册。

创建新的条件访问策略： 

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，您将看到 "Azure 仪表板"。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

![基线 CA 策略](../media/secure-email/CA-EXO-policy-1.png)

 下表介绍了要为此策略实现的条件访问策略设置。

**作业**

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始|
||排除|例外安全组；服务帐户(应用标识)|根据需要在临时基础上修改的成员身份|
|云应用|包括|选择要应用此规则的应用程序。 例如，选择 "Office 365 Exchange Online"||
|条件|已配置|是|根据自身环境和需求进行配置|
|登录风险|风险级别||请参阅下表中的指南|

**登录风险**

根据目标的保护级别应用设置。

|属性|保护级别|值|注意|
|:---|:---------|:-----|:----|
|风险级别|基线|高、中|两项全选|
| |敏感|高、中、低|三项全选|
| |高度管控| |将所有选项保留为未选中状态以始终强制执行 MFA|

访问控制

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|授予|授予访问权限|True|已选定|
||需要进行 MFA|True|Check|
||要求将设备标记为合规|False||
||要求混合 Azure AD 加入设备|False||
||需要经批准的客户端应用程序|False||
||需要所有已选控件|True|已选定|

> [!NOTE]
> 请务必启用此策略，方法是选择 **"打开"**。 此外，请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略。



## <a name="block-clients-that-dont-support-modern-authentication"></a>阻止不支持新式身份验证的客户端
1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，您将看到 "Azure 仪表板"。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

下表介绍了要为此策略实现的条件访问策略设置。

**作业**

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始|
||排除|例外安全组；服务帐户(应用标识)|按需临时修改的成员身份|
|云应用|包括|选择要应用此规则的应用程序。 例如，选择 "Office 365 Exchange Online"||
|条件|已配置|是|配置客户端应用程序|
|客户端应用|已配置|是|移动应用和桌面客户端，其他客户端（选择两者）|

访问控制

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|授予|阻止访问|True|已选定|
||需要进行 MFA|False||
||要求将设备标记为合规|False||
||要求混合 Azure AD 加入设备|False||
||需要经批准的客户端应用程序|False||
||需要所有已选控件|True|已选定|

> [!NOTE]
> 请务必启用此策略，方法是选择 **"打开"**。 此外，请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略。



## <a name="high-risk-users-must-change-password"></a>高风险用户必须更改密码
若要确保所有高风险用户的受损帐户强制在登录时执行密码更改，必须应用以下策略。

Log in to the [Microsoft Azure portal (https://portal.azure.com)](https://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.

**作业**

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|Users|包括|所有用户|已选择|
||排除|无||
|条件|用户风险|高|已选择|

控制

| 类型 | 属性 | 值                  | 注意 |
|:-----|:-----------|:------------------------|:------|
|      | Access     | 允许访问            | True  |
|      | 访问     | 需要更改密码 | True  |

**审阅：** 不适用

> [!NOTE]
> 请务必启用此策略，方法是选择 **"打开"**。 此外，请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略

## <a name="define-app-protection-policies"></a>定义应用保护策略
应用程序保护策略（应用）定义允许哪些应用，以及可以对组织的数据执行的操作。 应用程序中提供的选项使组织能够根据其特定需求调整保护。 在某些情况下，实现完整方案可能不太清楚需要哪些策略设置。 为了帮助组织确定移动客户端终结点强化的优先级，Microsoft 为 iOS 和 Android 移动应用管理的应用程序数据保护框架引入了分类。 

应用程序数据保护框架分为三个不同的配置级别，每个级别都建立了上一个级别： 

- 企业基本数据保护确保应用程序受到 PIN 保护并进行加密，并执行选择性擦除操作。 对于 Android 设备，此级别验证 Android 设备证明。 这是一种入门级配置，它在 Exchange Online 邮箱策略中提供了类似的数据保护控制，并介绍了它和用户对应用程序的人口。 
- 企业增强型数据保护引入了应用程序数据泄露预防机制和最低操作系统要求。 这是适用于大多数移动用户访问工作或学校数据的配置。 
- 企业高数据保护引入了高级数据保护机制、增强的 PIN 配置和应用程序移动威胁防御。 访问高风险数据的用户需要此配置。 

若要查看每个配置级别和必须受保护的最小应用程序的特定建议，请查看[使用应用保护策略的 Data protection framework](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)。 

使用[标识和设备访问配置](microsoft-365-policies-configurations.md)中概述的原则，比较基准和敏感保护层与第2级企业增强型数据保护设置密切对应。 高度管控的保护层密切映射到3级企业高数据保护设置。

|保护级别 |应用保护策略  |更多信息  |
|---------|---------|---------|
|基线     | [2级增强数据保护](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | 在级别2中强制实施的策略设置包括为级别1建议的所有策略设置，并且仅添加或更新以下策略设置以实现更多控件和级别1更复杂的配置。         |
|敏感     | [2级增强数据保护](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | 在级别2中强制实施的策略设置包括为级别1建议的所有策略设置，并且仅添加或更新以下策略设置以实现更多控件和级别1更复杂的配置。        |
|高度管控     | [3级企业高数据保护](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | 在级别3中强制实施的策略设置包括为级别1和2建议的所有策略设置，并且仅添加或更新以下策略设置，以实现更多控件和级别2的更复杂的配置。        |

若要使用数据保护框架设置为 Microsoft 终结点管理器中的每个平台（iOS 和 Android）创建新的应用保护策略，管理员可以执行以下操作：
1. 按照[如何使用 Microsoft Intune 创建和部署应用保护策略](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)中的步骤手动创建策略。
2. 使用[intune 的 PowerShell 脚本](https://github.com/microsoftgraph/powershell-intune-samples)导入示例[Intune 应用保护策略配置框架 JSON 模板](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies)。

## <a name="require-apps-that-support-intune-app-protection-policies"></a>需要支持 Intune 应用保护策略的应用程序
通过条件访问，组织可以限制对已批准（支持新式身份验证）的 iOS 和 Android 客户端应用的访问（Intune 应用保护策略应用于这些应用）。 需要多个条件访问策略，每个策略面向所有潜在的用户。 有关创建这些策略的详细信息，请参阅[需要使用条件访问的云应用访问的应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。

1. 在[方案1： office 365 应用程序需要批准的应用](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)程序中的 "步骤1：为 Office 365 配置 Azure AD 条件访问策略" 中，这将允许 Outlook for IOS 和 Android，但阻止支持 OAuth 的 exchange ActiveSync 客户端连接到 Exchange Online。

   > [!NOTE]
   > 此策略可确保移动用户可以使用适用的应用程序访问所有 Office 终结点。

2. 如果启用对 Exchange Online 的移动访问，请实施[阻止 ActiveSync 客户端](secure-email-recommended-policies.md#block-activesync-clients)，这将阻止 exchange activesync 客户端利用基本身份验证连接到 exchange online。

   上面的策略利用了授予权限控制[请求批准的客户端应用程序](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app)并[需要应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)。

3. 为 iOS 和 Android 设备上的其他客户端应用禁用旧版身份验证。 有关详细信息，请参阅[阻止不支持新式身份验证的客户端](#block-clients-that-dont-support-modern-authentication)。

## <a name="define-device-compliance-policies"></a>定义设备合规性策略

设备合规性策略定义设备必须遵循的要求才能标记为合规。 从 Microsoft 终结点管理器管理中心中创建 Intune 设备合规性策略。

为每个平台创建一个策略：
- Android 设备管理员
- Android 企业版
- iOS/iPadOS
- macOS
- 此设置在以下类型的设备上可用：
- Windows 8.1 及更高版本
- Windows 10 及更高版本

若要创建设备合规性策略，请使用你的管理凭据登录[Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然后导航到 "**设备** > **合规性策略** > "**策略**。 选择 "**创建策略**"。

对于要部署的设备合规性策略，必须将其分配给用户组。 您在创建并保存策略后分配该策略。 在管理中心中，选择策略，然后选择 "**分配**"。 选择要接收策略的组后，选择 "**保存**" 以保存该组分配并部署该策略。

有关在 Intune 中创建合规性策略的分步指南，请参阅 Intune 文档中的在[Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。

建议将以下设置用于 Windows 10。

**设备运行状况： Windows 运行状况证明服务评估规则**

|属性|值|注意|
|:---------|:-----|:----|
|需要 BitLocker|需要||
|要求在设备上启用安全启动|需要||
|需要代码完整性|需要||


设备属性

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|操作系统版本|全部|未配置||

系统安全

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|Password|需要密码才能解锁移动设备|需要||
||简单密码|阻止||
||密码类型|设备默认值||
||最短密码长度|6 ||
||在需要密码之前不活动的最长分钟数|15 |Android 版本4.0 及更高版本或 KNOX 4.0 及更高版本支持此设置。 对于 iOS 设备，支持 iOS 8.0 和更高版本|
||密码过期（天）|41||
||用于防止重复使用的以前密码的数目|5 ||
||当设备从空闲状态（移动和全息）返回时需要密码|需要|适用于 Windows 10 及更高版本|
|加密|设备上的数据存储加密|需要||
|设备安全性|Firewall|需要||
||防病毒|需要||
||间谍|需要|此设置需要在 Windows 安全中心中注册的反间谍软件解决方案|
|Defender|Microsoft Defender 反恶意软件|需要||
||Microsoft Defender 反恶意软件最低版本||仅支持 Windows 10 桌面版。 Microsoft 建议版本的背后不超过最新版本五个|
||最新的 Microsoft Defender 反恶意软件签名|需要||
||实时保护|需要|仅支持 Windows 10 桌面版|

**Microsoft Defender ATP**

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|Microsoft Defender 高级威胁防护规则|要求设备在计算机风险得分|中等||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>需要符合要求的电脑（但不符合兼容电话和平板电脑）
在将策略添加到需要兼容的电脑之前，请务必在 Intune 中注册设备进行管理。 建议在将设备注册到 Intune 中之前使用多重身份验证，以确保设备已占有目标用户。 

若要要求合规的电脑：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，您将看到 "Azure 仪表板"。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择 "**选择应用**"，从 "**云应用**" 列表中选择所需的应用。 例如，选择 "Office 365 Exchange Online"。 选择 "**选择**并**完成**"。

8. 若要要求兼容的电脑，但不符合兼容电话和平板电脑，请选择 "**条件**" 和 "**设备平台**"。 选择 "**选择设备平台**" 并选择 " **Windows**和**macOS**"。

9. 从“访问控制”部分选择“授予”。

10. 选择 "**授予访问权限**"，选择 "**要求设备被标记为合规**"。 对于多个控件，选择 **"要求所有选定控件**"，然后选择 "**选择**"。 

11. 选择“**创建**”。

如果您的目标是要求符合合规性的 Pc*和*移动设备，请不要选择 "平台"。 这将强制实施所有设备的符合性。 

## <a name="require-compliant-pcs-and-mobile-devices"></a>需要符合要求*的 pc 和*移动设备

若要要求所有设备符合性，请执行以下操作：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，您将看到 "Azure 仪表板"。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择 "**选择应用**"，从 "**云应用**" 列表中选择所需的应用。 例如，选择 "Office 365 Exchange Online"。 选择 "**选择**并**完成**"。

8. 从“访问控制”部分选择“授予”。

9. 选择 "**授予访问权限**"，选择 "**要求设备被标记为合规**"。 对于多个控件，选择 **"要求所有选定控件**"，然后选择 "**选择**"。 

10. 选择“**创建**”。

创建此策略时，请不要选择平台。 这将强制实施符合性的设备。


## <a name="next-steps"></a>后续步骤

[了解有关用于保护电子邮件的策略建议](secure-email-recommended-policies.md)
