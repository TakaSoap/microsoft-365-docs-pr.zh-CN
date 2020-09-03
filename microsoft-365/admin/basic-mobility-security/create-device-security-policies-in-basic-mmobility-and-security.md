---
title: 在基本移动性和安全性中创建设备安全策略
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用基本移动性和安全性来创建保护组织信息的设备策略。
ms.openlocfilehash: 7bbc4a128505ce6e569db4b4d7d98e132c503965
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336760"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>在基本移动性和安全性中创建设备安全策略 

您可以使用基本移动性和安全性来创建设备策略，以帮助保护 Microsoft 365 上的组织信息免遭未经授权的访问。 您可以将策略应用于组织中的任何移动设备，其中设备的用户具有适用的 Microsoft 365 许可证，并已在基本移动和安全性中注册了该设备。

## <a name="before-you-begin"></a>准备工作

>[!IMPORTANT]
>在创建移动设备策略之前，必须激活并设置基本的移动性和安全性。 有关详细信息，请参阅基本移动性和安全性概述。

- 了解基本移动性和安全性所支持的设备、移动设备应用和安全设置。 请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。
- 创建包含要向其部署策略的 Microsoft 365 用户的安全组，以及您可能想要排除其阻止访问 Microsoft 365 的用户的安全组。 我们建议您先向少量用户部署新策略，以此来测试策略，然后再为组织部署此策略。 您可以创建和使用仅包含自己的安全组或可为您测试该策略的少数 Microsoft 365 用户。 若要了解有关安全组的详细信息，请参阅 [创建、编辑或删除安全组](https://go.microsoft.com/fwlink/p/?LinkId=518555)。
- 若要在 Microsoft 365 中创建和部署基本移动性和安全策略，您需要是 Microsoft 365 全局管理员。有关详细信息，请参阅 [安全性 & 合规性中心中的权限](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)。
- 在部署策略之前，让你的组织了解在基本移动性和安全性中注册设备的潜在影响。 根据您设置策略的方式，可以阻止不兼容的设备访问 Microsoft 365 和数据，包括已注册设备上已安装的应用程序、照片和个人信息，以及可以删除的数据。

>[!NOTE]
>在 MDM for Microsoft 365 商业标准中创建的策略和访问规则替代 exchange ActiveSync 移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则。 在 MDM for Microsoft 365 商业标准中注册设备后，应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则都将被忽略。 若要了解有关 Exchange ActiveSync 的详细信息，请参阅 exchange [Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>步骤1：创建设备策略并部署到测试组

在开始之前，请确保已激活并设置基本移动性和安全性。 有关说明，请参阅 [基本移动性和安全性概述](overview-of-basic-mobility-and-security-for-microsoft-365.md)。

1. 在浏览器中键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. 选择 " **创建策略**"。

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本移动性和安全策略设置":::

3. 在 " **策略设置** " 页上，指定要应用于组织中的移动设备的要求。

4. **需要管理电子邮件配置文件**：如果启用此功能，则不会认为没有由基本移动性和安全性管理的电子邮件配置文件的设备不合规。 如果设备的目标不正确，或者用户手动设置了设备上的电子邮件帐户，则该设备不能有托管电子邮件配置文件。 如果 **未启用** (默认) ，则不会对合规性或非合规性评估此设置。 有关选择此选项时用户如何符合标准的说明，请参阅 [找到现有的电子邮件帐户](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。

5. 在 " **是否要立即应用此策略？"** 页面上，选择要应用此策略的组。

6. 选择 " **创建此策略**"。

策略将被推送到每个用户下次使用其移动设备登录 Microsoft 365 时应用该策略的设备。 如果用户之前未将策略应用于其移动设备，则在部署该策略后，他们会在其设备上收到通知，其中包括注册和激活基本移动性和安全性的步骤。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)。 在由 Intune 服务托管的基本移动性和安全性完成注册之前，对电子邮件、OneDrive 和其他服务的访问受到限制。 在完成使用 Intune 公司门户应用的注册后，他们可以使用服务，并将策略应用于其设备。

## <a name="step-2-verify-that-your-policy-works"></a>步骤2：验证策略是否有效

创建设备策略后，请检查策略是否按预期工作，然后再将其部署到组织。

1. 在浏览器中键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 选择 **"查看受管理的设备的列表"**。
3. 检查已应用此策略的用户设备的状态。 您希望管理设备的 **状态** **。**
4. 您还可以在选择设备后，通过单击 "**恢复时恢复**" 或 "从**管理**中**删除公司数据**" 按钮，在设备上执行完全或选择性擦除。 有关说明，请参阅 [擦除 Microsoft 365 中的移动设备。

步骤3：将策略部署到您的组织

在创建设备策略并验证它是否按预期方式工作后，将其部署到您的组织。

1. 从浏览器类型： [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 选择要部署的策略，然后选择 "要**应用的组**" 旁边的 "**编辑**"。
3. 搜索要添加的组，然后单击 " **选择**"。
4. 选择 " **关闭** 并 **更改设置"。**
5. 选择 " **关闭** 并 **编辑策略"。**

将策略推送到每个用户的移动设备，下次从其移动设备登录到 Microsoft 365 时，策略将应用于该用户。 如果用户未将策略应用于其移动设备，则会在其设备上收到通知，其中包含注册和激活基本移动性和安全性的步骤。 完成注册后，策略将应用于其设备。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)。

## <a name="step-4-block-email-access-for-unsupported-devices"></a>步骤4：阻止不受支持的设备的电子邮件访问

为了帮助保护组织信息的安全，应阻止对基本移动性和安全性不受支持的移动设备的应用程序访问 Microsoft 365 电子邮件。 有关受支持设备的列表，请参阅 [支持的设备](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)。 

**阻止应用程序访问：**

1. 在浏览器中键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 选择 " **管理组织范围的设备访问设置**"。
3. 若要阻止不受支持的设备，请在 "**如果 MDM For Microsoft 365 不支持设备**" 下选择 "**阻止**"，然后选择 "**保存**"。

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本移动性和安全块访问选项":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>步骤 5：选择要从条件访问检查中排除的安全组

如果您要从他们的移动设备上的条件访问检查中排除某些人员，并且已为这些人员创建了一个或多个安全组，则在此处添加安全组。 这些组中的人员不会为其受支持的移动设备强制实施任何策略。 如果您不再希望在组织中使用基本移动性和安全性，建议使用此选项。

1. 在浏览器中键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. 选择 " **管理组织范围的设备访问设置**"。

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本移动性和安全性创建策略选项":::

3. 选择 " **添加** " 以添加安全组，其中包含要从阻止访问 Microsoft 365 的用户排除的用户。 当用户已添加到此列表时，他们可以在使用不受支持的设备时访问 Microsoft 365 电子邮件。

4. 在 " **选择组** " 面板中选择要使用的安全组。

5. 选择名称，然后添加 " **Add**  >  **保存**"。

6. 在 " **组织范围的设备访问设置** " 面板中，选择 " **保存**"。

    :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="基本移动和安全允许访问选项":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>安全策略对不同设备类型的影响是什么？

当您将策略应用于用户设备时，对每个设备的影响在不同设备类型中稍有不同。 请查看以下示例表，了解策略对不同设备的影响。

|**安全策略**|**Android 4 及更高版本**|**Samsung KNOX**|**iOS 6 及更高版本**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|需要加密备份|否|是|是|需要 iOS 加密备份。|
|阻止云备份|是|是|是|阻止在 Android 上进行 Google 备份（灰显），阻止在 iOS 上进行云备份。|
|阻止文档同步|否|否|是|iOS：阻止云中的文档。|
|阻止照片同步 |否|否|是|iOS（本机）：阻止照片流。|
|阻止屏幕捕获 |否|是|是|在尝试时被阻止。|
|阻止视频会议 |否|否|是|FaceTime 在 iOS 上阻止，而不是在 Skype 或其他人上阻止。|
|阻止发送诊断数据 |否|是|是|阻止在 Android 上发送 Google 故障报告。|
|阻止对应用商店的访问 |否|是|是|应用商店图标在 Android 主页上缺失，在 Windows 上禁用，在 iOS 上缺失。|
|要求提供应用商店的密码 |否|否|是|iOS：购买 iTunes 所需的密码。|
|阻止连接到可移动存储 |否|是|不适用|Android： SD 卡在 "设置" 中显示为灰色，Windows 通知用户，安装的应用程序不可用|
|阻止蓝牙连接 |查看注释|查看注释|是|无法将蓝牙禁用为 Android 上的设置。 相反，我们禁用了需要蓝牙的所有事务：高级音频分发、音频/视频远程控制、无人参与设备、耳机、电话簿访问和串行端口。 使用以上任一项时，页面底部将显示一个小型 Toast 消息。|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>当您删除策略或从策略中删除用户时，会发生什么情况？

当您删除策略或从已部署该策略的组中删除用户时，策略设置将从用户设备中删除 Microsoft 365 电子邮件配置文件和缓存的电子邮件。 请参阅下表以查看为不同设备类型删除的内容。

|**删除的内容**|**iOS 6 及更高版本**|**Android 4 及更高版本 (包括 Samsung KNOX**|
|:-----|:-----|:----------------------|
|托管电子邮件配置文件<sup>1</sup>|是|否|
|阻止云备份|是|否|
<sup>1</sup>如果在部署策略时选择了 " **电子邮件配置文件** "，则该配置文件中的托管电子邮件配置文件和缓存的电子邮件将从用户设备中删除。

策略将从移动设备中删除。对于每个用户，该策略将应用于下次其设备签入基本移动性和安全性。 如果部署适用于这些用户设备的新策略，系统会提示他们重新注册基本移动性和安全性。

您还可以完全擦除设备，也可以有选择性地擦除设备中的组织信息。 有关详细信息，请参阅 [在基本移动和安全中擦除移动设备](wipe-mobile-device.md)。 

## <a name="related-topics"></a>相关主题

[基本移动性和安全性概述](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)
