---
title: 常见的标识和设备访问策略-Microsoft 365 企业版 |Microsoft 文档
description: 介绍针对有关如何应用标识和设备访问策略以及配置的 Microsoft 建议的策略。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866034"
---
# <a name="common-identity-and-device-access-policies"></a>常见标识和设备访问策略
本文介绍推荐用于保护权云服务的策略的共同包括本地应用程序发布与 Azure AD 应用程序代理。 

本指南讨论了如何部署新设置环境中的建议的策略。在单独的实验室环境中的这些策略设置允许您了解和暂存向您的预生产和生产环境推出之前进行评估的建议的策略。新设置的环境可能仅限于云或混合。  

## <a name="policy-set"></a>策略设置 

下图说明了推荐的策略集。它显示哪一层保护措施适用于每个策略和策略是否适用于 Pc 或电话和平板电脑或设备这两个类别。它还指示配置了这些策略。

![常见配置标识和设备访问的策略](../images/Identity_device_access_policies_byplan.png)


本文的其余部分介绍如何配置这些策略。 

注册到 Intune 的设备的设备包含在预期的用户所拥有的保证之前，建议使用多因素身份验证。此外必须注册到 Intune 强制实施设备合规性策略之前设备。

要授予时间来完成这些任务，我们建议此表中列出的顺序实现基准策略。但是，在任何时候都可以实现敏感和高管控保护的 MFA 策略。


|保护级别|Policies|更多信息|
|:---------------|:-------|:----------------|
|**基线**|[*中等*或*高*风险登录时需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|        |[阻止客户端不支持现代身份验证](#block-clients-that-dont-support-modern-authentication)|因此，很重要阻止这些，不使用现代的身份验证的客户端可以跳过条件访问规则，|
|        |[高风险用户必须更改密码](#high-risk-users-must-change-password)|强制用户如果高风险活动检测到其帐户在登录后更改其密码|
|        |[定义应用程序保护策略](#define-app-protection-policies)|每个平台 (iOS，Android、 Windows) 的一个策略。|
|        |[需要已批准应用程序](#require-approved-apps)|强制移动应用程序保护手机和平板电脑|
|        |[定义设备合规性策略](#define-device-compliance-policies)|每个平台的的一个策略|
|        |[需要符合标准的 Pc](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|强制实施 Pc Intune 的管理|
|**敏感**|[*低*、*中*或*高*风险登录时需要 MFA](#require-mfa-based-on-sign-in-risk)| |
|         |[需要符合标准的 Pc*和*移动设备](#require-compliant-pcs-and-mobile-devices)|强制实施 Pc 和平板电脑电话/Intune 的管理|
|**高度管控**|[*始终*需要 MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>向用户分配策略
配置策略之前，确定要用于保护每一层的 Azure AD 组。通常，比较基准保护适用于组织中的每个人。包含的比较基准和敏感的保护功能的用户将必须应用的比较基准策略以及敏感的策略。保护累积以及实施最严格策略。 

建议的做法是创建 Azure AD 组条件访问排除。将该组添加到所有条件访问规则"排除"下。这样，您可以向用户提供访问，而您解决访问问题的方法。这被建议为临时解决方案。监视更改此组，并确保仅适用于正在使用排除组。 

下图提供了用户分配和排除的示例。

![示例用户分配和排除 MFA 规则条件](../images/identity-access-policies-assignment.png)

在图 MFA*始终*需要一个条件的访问策略分配"顶部机密项目 X 团队"。应用于用户的更高级别的保护时应谨慎。此项目工作组成员需要提供两种形式的身份验证，每次登录，即使它们不查看高度规范化的内容。  

创建这些建议的一部分的所有 Azure AD 组必须创建为 Office 365 组。保护 SharePoint Online 中的文档时，这是特别重要部署 Azure 信息保护 (AIP)。

![创建 Office 365 组的屏幕截图](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>需要 MFA 根据登录风险
需要 MFA 之前, 先使用 Identity 保护 MFA 注册策略注册 MFA 用户。注册用户后，可以强制 MFA 登录。[必备工作](identity-access-prerequisites.md)包括 MFA 中注册的所有用户。

创建新的条件访问策略： 

1. 转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

![基线 CA 策略](./media/secure-email/CA-EXO-policy-1.png)

 下表介绍实现此策略的条件的访问策略设置。

分配

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始|
||排除|例外安全组；服务帐户(应用标识)|根据需要临时每个修改的成员身份|
|云应用|包括|选择您希望此规则应用于的应用程序。例如，选择 Office 365 Exchange Online||
|条件|已配置|是|根据自身环境和需求进行配置|
|登录风险|风险级别||请参阅下表中的指南|

**登录风险**

应用基于您的目标的保护级别的设置。

|属性|保护级别|值|注释|
|:---|:---------|:-----|:----|
|风险级别|基线|高、中|两项全选|
| |敏感|高、 中、 低|三项全选|
| |高度管控| |保留所有选项保持为不选中始终强制实施 MFA|

访问控制

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|授予|授予访问权限|True|已选择|
||需要进行 MFA|True|Check|
||需要标记为兼容的设备|False||
||需要混合 Azure AD 加入设备|False||
||需要批准的客户端应用程序|False||
||需要所有已选控件|True|已选择|

> [!NOTE]
> 请务必通过选择**在**启用此策略。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略。



## <a name="block-clients-that-dont-support-modern-authentication"></a>阻止客户端不支持现代身份验证
1. 转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

下表介绍实现此策略的条件的访问策略设置。

分配

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|用户和组|包括|选择用户和组 - 选择包含目标用户的特定安全组|从包含试点用户的安全组开始|
||排除|例外安全组；服务帐户(应用标识)|按需临时修改的成员身份|
|云应用|包括|选择您希望此规则应用于的应用程序。例如，选择 Office 365 Exchange Online||
|条件|已配置|是|配置客户端应用程序|
|客户端应用程序|已配置|是|移动应用程序和桌面客户端，其他客户端 （选择两者）|

访问控制

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|授予|阻止访问|True|已选择|
||需要进行 MFA|False||
||需要标记为兼容的设备|False||
||需要混合 Azure AD 加入设备|False||
||需要批准的客户端应用程序|False||
||需要所有已选控件|True|已选择|

> [!NOTE]
> 请务必通过选择**在**启用此策略。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略。



## <a name="high-risk-users-must-change-password"></a>高风险用户必须更改密码
若要确保所有高风险用户受到攻击的帐户强制执行密码更改时签名中，您必须应用以下策略。

登录到[Microsoft Azure 门户 (http://portal.azure.com)](http://portal.azure.com/)使用管理员凭据，然后导航到**Azure AD 身份防护 > 用户风险策略**。

分配

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|Users|包括|所有用户|已选择|
||排除|无||
|条件|用户风险|高|已选择|

控制

| 类型 | 属性 | 值                  | 注释 |
|:-----|:-----------|:------------------------|:------|
|      | 访问     | 允许访问            | True  |
|      | 访问     | 需要更改密码 | True  |

**审阅：** 不适用

> [!NOTE]
> 请务必通过选择**在**启用此策略。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略

## <a name="define-app-protection-policies"></a>定义应用程序保护策略
应用程序保护策略定义允许的应用程序并他们与您组织的数据可以执行的操作。创建 Intune 应用程序中的 Azure 门户从保护策略。 

创建每个平台的策略：
- iOS
- Android
- Windows 10

若要创建新的应用程序保护策略，登录到您的管理凭据的 Microsoft Azure 门户，然后导航到**移动应用程序 > 应用程序保护策略**。选择**添加策略**。

有微小的差异的应用程序保护 iOS 和 Android 之间的策略选项。以下策略是专用于 Android。使用此指南作为在其他策略。

推荐的应用程序列表包括以下组件：
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

下表介绍建议的设置：

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|数据重定位|阻止 Android 备份|是|在 iOS 上，这会专门调用 iTunes 和 iCloud|
||允许应用向其他应用传送数据|策略托管应用||
||允许应用从其他应用接收数据|策略托管应用||
||防止“另存为”|是||
||选择企业数据可保存到其中的存储服务|OneDrive for Business，SharePoint||
||限制使用其他应用剪切、复制和粘贴|与粘贴中的策略托管应用程序||
||限制显示在托管浏览器内的 Web 内容|否||
||加密应用数据|是|在 iOS 上，选择选项：“锁定设备时”|
||启用设备时禁用应用程序加密|是|禁用此设置，以避免双加密|
||禁用联系人同步|否||
||禁用打印|否||
|访问|访问需要 PIN|是||
||选择类型|数字||
||允许使用简单 PIN|否||
||PIN 长度|6||
||允许使用指纹而不是 PIN|是||
||管理设备 PIN 时禁用应用程序 PIN|是||
||需要访问企业凭据|否||
||在一定时间后重新检查访问要求(分钟)|30||
||阻止屏幕捕获和 Android 助手|否|在 iOS 上，此选项不可用|
|登录安全要求|最大 PIN 尝试|5|重置 Pin|
||离线宽限期|720|阻止访问|
||擦除应用数据之前的脱机间隔时间（天）|90|擦除数据|
||根 Jailbroken/设备| |擦除数据|

完成后，请务必选中"创建"。重复上述步骤，并将替换为 iOS 的选定的平台 （下拉）。这将创建两个应用程序策略，因此后创建策略，然后将组分配给策略并将其部署。

若要编辑策略并将这些策略分配给用户，请参阅[如何创建和分配应用程序保护策略](https://docs.microsoft.com/intune/app-protection-policies)。 

## <a name="require-approved-apps"></a>需要已批准应用程序
若要要求已批准应用程序：

1. 转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。选择**选择**并**完成**。

8. 从“访问控制”部分选择“授予”。

9. 选择**授予访问**，选择**需要批准客户端应用程序**。为多个控件中，选择**需要选定的控件**，然后选择**选择**。 

10. 选择" **创建**"。

## <a name="define-device-compliance-policies"></a>定义设备合规性策略

设备合规性策略定义的设备必须遵守才能被标记为兼容的要求。创建 Intune 设备从 Azure 门户中的合规性策略。 

创建每个平台的策略：
- Android
- Android 企业
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1 及更高版本
- Windows 10 及更高版本

若要创建设备合规性策略，登录到您的管理凭据的 Microsoft Azure 门户，然后导航到**Intune > 设备合规性**。选择**创建策略**。

为 Windows 10 建议使用下列设置。

**设备运行状况： Windows 运行状况审计服务求值规则**

|属性|值|注释|
|:---------|:-----|:----|
|需要 BitLocker|需要||
|需要安全引导设备上启用|需要||
|需要代码完整性|需要||


设备属性

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|操作系统版本|全部|未配置||

对于所有上述策略视为部署，它们必须针对用户组。您可以执行此操作通过创建策略 （保存） 或更高版本，通过选择在**策略**部分 （相同级别添加） 的**管理部署**。

系统安全

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|密码|需要密码以解锁移动设备|需要||
||简单密码|阻止||
||密码类型|默认设备||
||最短密码长度|6||
||最大分钟无活动需要密码之前|15 |此设置支持 Android 版本 4.0 和上方或 KNOX 4.0 及以上。对于 iOS 设备，它支持针对 iOS 8.0 和上方|
||密码过期(天)|41||
||以前的密码，以防止重复使用的数量|5||
||从空闲状态 （Mobile 和全息） 返回设备时需要密码|需要|适用于 Windows 10 及更高版本|
|加密|在设备上的数据存储的加密|需要||
|设备安全|防火墙|需要||
||防病毒|需要||
||反间谍软件|需要|此设置，需要使用 Windows 安全中心注册反间谍软件解决方案|
|Defender|Windows Defender 反恶意软件|需要||
||Windows Defender 反恶意软件的最低版本||仅支持 Windows 10 桌面。Microsoft 建议版本不超过 5 后面从最新版本|
||最新的 Windows Defender 反恶意软件签名|需要||
||“实时保护”|需要|仅支持 Windows 10 桌面支持|

**Windows Defender ATP**

|类型|属性|值|注释|
|:---|:---------|:-----|:----|
|Windows Defender 高级威胁保护规则|需要为在或下的计算机风险分数的设备|中等||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>需要符合 Pc （但不是符合标准的电话和平板电脑）
添加之前需要符合 Pc 的策略，请务必注册到 Intune 的管理设备。注册到 Intune 的设备的设备包含在预期的用户所拥有的保证之前，建议使用多因素身份验证。 

需要符合 Pc:

1. 转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。选择**选择**并**完成**。

8. 如果需要符合 Pc，但不是符合手机和平板电脑，请选择**条件**和**设备平台**。选择**选择设备平台**，并选择**Windows**和**macOS**。

9. 从“访问控制”部分选择“授予”。

10. 选择**授予访问**，选择**需要标记为兼容的设备**。为多个控件中，选择**需要所有选定的控件**，然后选择**选择**。 

11. 选择" **创建**"。

如果您的目标是需要兼容的 Pc*和*移动设备，则不要选择平台。这将强制所有设备法规遵从性。 

## <a name="require-compliant-pcs-and-mobile-devices"></a>需要符合标准的 Pc*和*移动设备

若要为所有设备要求合规性：

1. 转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。

2. 从左侧菜单中选择“Azure Active Directory”。

3. 在“安全”部分之下，选择“条件访问”。

4. 选择“新策略”。

5. 输入策略名称，然后选择要应用策略的“用户和组”。

6. 选择“云应用”。

7. 选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。选择**选择**并**完成**。

8. 从“访问控制”部分选择“授予”。

9. 选择**授予访问**，选择**需要标记为兼容的设备**。为多个控件中，选择**需要所有选定的控件**，然后选择**选择**。 

10. 选择" **创建**"。

在创建此策略时，不要选中平台。这将强制兼容的设备。




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>后续步骤

[了解有关用于保护电子邮件的策略建议](secure-email-recommended-policies.md)
