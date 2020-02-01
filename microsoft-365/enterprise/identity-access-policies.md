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
ms.openlocfilehash: dad6c2f8d85c81b67da1aa3425c73e5991b3829b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596949"
---
# <a name="common-identity-and-device-access-policies"></a>常见标识和设备访问策略
本文介绍了用于保护云服务访问的常见建议策略，其中包括使用 Azure AD 应用程序代理发布的本地应用程序。 

本指南讨论如何在新预配的环境中部署建议的策略。 在单独的实验室环境中设置这些策略，可以在将首展转移到预生产和生产环境之前，了解和评估建议的策略。 您的新设置的环境可能是仅云或混合的。  

## <a name="policy-set"></a>策略集 

下图说明了建议的一组策略。 它显示了每个策略应用于哪一层的保护，以及这些策略是应用于 Pc、电话和平板电脑，还是适用于这两种类别的设备。 它还指示这些策略的配置位置。

![用于配置标识和设备访问的常见策略](../images/Identity_device_access_policies_byplan.png)


本文的其余部分介绍了如何配置这些策略。 

建议在将设备注册到 Intune 中之前使用多重身份验证，以确保设备已占有目标用户。 在强制实施设备合规性策略之前，还必须将设备注册到 Intune。

为了让你有时间完成这些任务，我们建议你按照此表中所列的顺序实施基准策略。 但是，敏感和高度管控保护的 MFA 策略可在任何时候实施。


|保护级别|策略|更多信息|
|:---------------|:-------|:----------------|
|**Baseline**|[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[阻止不支持新式身份验证的客户端](#block-clients-that-dont-support-modern-authentication)|不使用新式身份验证的客户端可以绕过条件访问规则，因此，请务必阻止这些|
|        |[高风险用户必须更改密码](#high-risk-users-must-change-password)|如果为帐户检测到高风险活动，则强制用户在登录时更改其密码|
|        |[定义应用保护策略](#define-app-protection-policies)|每个平台（iOS、Android、Windows）一个策略。|
|        |[需要批准的应用程序](#require-approved-apps)|为电话和平板电脑强制实施移动应用保护|
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

![用于 MFA 规则的用户分配和排除示例](../images/identity-access-policies-assignment.png)

在图中，"Top secret project X team" 分配了一个需要*始终*进行 MFA 的条件访问策略。 对用户应用更高级别的保护时要合理。 此项目团队的成员将需要在每次登录时提供两种形式的身份验证，即使他们没有查看高度管控的内容也是如此。  

作为这些建议的一部分创建的所有 Azure AD 组都必须创建为 Office 365 组。 在 SharePoint Online 中保护文档时，这一点对于部署 Azure 信息保护 (AIP) 尤为重要。

![用于创建 Office 365 组的屏幕捕获](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>需要基于登录风险进行 MFA
在要求进行 MFA 之前，首先使用标识保护 MFA 注册策略为用户注册 MFA。 注册用户后，可以强制进行 MFA 以进行登录。 [先决条件工作](identity-access-prerequisites.md)包括向具有 MFA 的所有用户注册。

创建新的条件访问策略： 

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，您将看到 "Azure 仪表板"。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

![基线 CA 策略](./media/secure-email/CA-EXO-policy-1.png)

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
|      | Access     | 需要更改密码 | True  |

**审阅：** 不适用

> [!NOTE]
> 请务必启用此策略，方法是选择 **"打开"**。 此外，请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略

## <a name="define-app-protection-policies"></a>定义应用保护策略
应用保护策略定义哪些应用程序是允许的，以及可以对组织的数据执行的操作。 从 Azure 门户中创建 Intune 应用保护策略。 

为每个平台创建一个策略：
- iOS
- Android
- Windows 10

若要创建新的应用保护策略，请使用管理员凭据登录到 Microsoft Azure 门户，然后导航到**客户端应用** > **应用程序保护策略**。 选择 "**创建策略**"。

iOS 和 Android 的应用保护策略选项略有不同。 以下策略专用于 Android。 将本指南用作其他策略的指南。

推荐的应用程序列表包括以下内容：
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

下表介绍了推荐的设置：

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|数据重定位|阻止 Android 备份|是|在 iOS 上，这会专门调用 iTunes 和 iCloud|
||允许应用向其他应用传送数据|策略托管应用||
||允许应用从其他应用接收数据|策略托管应用||
||防止“另存为”|是||
||选择企业数据可保存到其中的存储服务|OneDrive for Business、SharePoint||
||限制使用其他应用剪切、复制和粘贴|使用 "粘贴到" 的策略托管应用||
||限制显示在托管浏览器内的 Web 内容|否||
||加密应用数据|是|在 iOS 上，选择选项：“锁定设备时”|
||启用设备时禁用应用程序加密|是|禁用此设置可避免双重加密|
||禁用联系人同步|否||
||禁用打印|否||
|访问|访问需要 PIN|是||
||选择类型|数值||
||允许使用简单 PIN|否||
||PIN 长度|6 ||
||允许使用指纹而不是 PIN|是||
||在管理设备 PIN 时禁用应用 PIN|是||
||需要公司凭据才能访问|否||
||在一定时间后重新检查访问要求(分钟)|30||
||阻止屏幕捕获和 Android 助手|否|在 iOS 上，此选项不可用|
|登录安全要求|最大 PIN 尝试次数|5 |重置 Pin|
||离线宽限期|720|阻止访问|
||擦除应用数据之前的脱机间隔时间（天）|90|擦除数据|
||已越狱/取得根的设备| |擦除数据|

完成后，请记住选择 "创建"。 重复上述步骤，并将所选平台（下拉列表）替换为 iOS。 这可创建两个应用策略，因此请在创建策略后将组分配到策略，并进行部署。

若要编辑策略并将这些策略分配给用户，请参阅[如何创建和分配应用保护策略](https://docs.microsoft.com/intune/app-protection-policies)。 

## <a name="require-approved-apps"></a>需要批准的应用程序
若要要求获得批准的应用：

1. 转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，您将看到 "Azure 仪表板"。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择 "**选择应用**"，从 "**云应用**" 列表中选择所需的应用。 例如，选择 "Office 365 Exchange Online"。 选择 "**选择**并**完成**"。

8. 选择 "**条件**"，选择 "**设备平台**"，然后选择 "**配置**"

9. 在 "**包含**" 下，选择 "**选择设备平台**"，选择 " **Android**和**iOS**"。 单击 "**完成**" 并再次**执行**

10. 从“访问控制”部分选择“授予”。

11. 选择 "**授予访问权限**"，选择 "**需要批准的客户端应用**"。 对于多个控件，选择 "**需要选定的控件**"，然后选择 "**选择**"。 

12. 选择“**创建**”。

## <a name="define-device-compliance-policies"></a>定义设备合规性策略

设备合规性策略定义设备必须遵循的要求才能标记为合规。 从 Azure 门户中创建 Intune 设备合规性策略。 

为每个平台创建一个策略：
- Android
- Android 企业版
- iOS
- macOS
- 此设置在以下类型的设备上可用：
- Windows 8.1 及更高版本
- Windows 10 及更高版本

若要创建设备合规性策略，请使用你的管理凭据登录到 Microsoft Azure 门户，然后导航到**Intune > 设备合规性**。 选择“**创建策略**”。

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

要将上述所有策略视为已部署，这些策略必须面向用户组。 为此，可以通过在 "**策略**" 部分中选择 "**管理部署**" （与 "添加" 相同级别）来创建策略（在保存时）或更高版本。

系统安全

|类型|属性|值|注意|
|:---|:---------|:-----|:----|
|密码|需要密码才能解锁移动设备|需要||
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
|Defender|Windows Defender 反恶意软件|需要||
||Windows Defender 反恶意软件最低版本||仅支持 Windows 10 桌面版。 Microsoft 建议版本的背后不超过最新版本五个|
||最新的 Windows Defender 反恶意软件签名|需要||
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
