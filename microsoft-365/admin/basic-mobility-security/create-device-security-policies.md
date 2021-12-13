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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- MET150
description: 使用基本移动性和安全性创建保护组织信息的设备策略。
ms.openlocfilehash: c0fa9cec0b9029d2cd55aace0c758e6c81e265b0
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421830"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>在基本移动性和安全性中创建设备安全策略

可以使用基本移动性和安全性创建设备策略，帮助保护组织信息Microsoft 365未经授权的访问。 你可以将策略应用于组织中设备用户拥有适用的 Microsoft 365 许可证并且已注册基本移动性和安全性设备的任何移动设备。

## <a name="before-you-begin"></a>准备工作

> [!IMPORTANT]
> 必须先激活和设置基本移动性和安全性，然后才能创建移动设备策略。 有关详细信息，请参阅 Overview of Basic Mobility and Security。

- 了解基本移动性和安全性支持的设备、移动设备应用和安全设置。 请参阅[Capabilities of Basic Mobility and Security。](capabilities.md)
- 创建安全组，Microsoft 365要部署策略的用户以及您可能要阻止其访问策略的用户Microsoft 365。 我们建议您先向少量用户部署新策略，以此来测试策略，然后再为组织部署此策略。 可以创建和使用仅包含你自己的安全组，也可以为Microsoft 365测试策略的少量用户创建和使用安全组。 若要详细了解安全组，请参阅创建、 [编辑或删除安全组](../email/create-edit-or-delete-a-security-group.md)。
- 若要在安全中心创建和部署基本移动Microsoft 365，你需要是全局Microsoft 365管理员。有关详细信息，请参阅[安全与合规中心&权限](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。
- 在部署策略之前，请让组织了解在基本移动性和安全性中注册设备的潜在影响。 根据策略设置方式，可能会阻止不相容的设备访问 Microsoft 365 和数据，包括注册的设备上已安装的应用程序、照片和个人信息，并且可删除数据。

> [!NOTE]
> 在基本移动性和安全性 for Microsoft 365 商业标准版 中创建的策略和访问规则Exchange ActiveSync在 Exchange 管理中心中创建的移动设备邮箱策略和设备访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">规则</a>。 为设备注册基本移动性和安全性 for Microsoft 365 商业标准版后，Exchange ActiveSync应用于该设备的任何移动设备邮箱策略或设备访问规则将被忽略。 若要详细了解Exchange ActiveSync，请参阅 Exchange ActiveSync[中的Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>步骤 1：创建设备策略并部署到测试组

在启动之前，请确保已激活并设置基本移动性和安全性。 有关说明，请参阅[Overview of Basic Mobility and Security。](overview.md)

1. 在浏览器中，键入 <https://protection.office.com/devicev2> 。

2. 选择“**创建策略**”。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本移动和安全策略设置。":::

3. 在 **"策略设置** "页上，指定要应用于组织中移动设备的要求。

4. **需要管理电子邮件配置文件**：启用后，没有由基本移动性和安全性管理的电子邮件配置文件的设备被视为不兼容。 如果设备未正确设定目标，或者用户手动在设备上设置电子邮件帐户，则设备不能拥有托管电子邮件配置文件。 如果您 **将"未** 启用" (默认) ，则不评估此设置的合规性或非合规性。 有关在选择此选项时用户如何获得遵从性的说明，请参阅已找到现有 [电子邮件帐户](/intune-user-help/existing-company-email-account-found)。

5. 在 **"现在是否要应用此策略？"** 页上，选择要应用此策略的组。

6. 选择 **"创建此策略"。**

该策略将推送到每个用户的设备，该策略将应用于他们下一次使用Microsoft 365登录时。 如果用户之前没有将策略应用于其移动设备，在部署策略后，他们会在设备上收到一条通知，其中包括注册和激活基本移动性和安全性的步骤。 有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。 在 Intune 服务托管的基本移动性和安全性中完成注册之前，对电子邮件、OneDrive和其他服务的访问权限将受到限制。 使用 Intune 公司门户 应用完成注册后，他们可以使用服务，并且策略将应用于其设备。

## <a name="step-2-verify-that-your-policy-works"></a>步骤 2：验证策略是否正常工作

创建设备策略后，在将策略部署到组织之前，检查该策略是否正常工作。

1. 在浏览器中，键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 选择 **"查看托管设备的列表"。**
3. 检查已应用此策略的用户设备的状态。 希望 **设备** 的状态为"托管 **"。**
4. 选择设备后，还可以单击"恢复出厂设置"或"从管理中删除公司数据"按钮，在设备上执行完全或选择性擦除。  有关说明，请参阅 [擦除设备中的Microsoft 365。

## <a name="step-3-deploy-a-policy-to-your-organization"></a>步骤 3：将策略部署到组织

创建设备策略并验证其是否正常工作后，将其部署到组织。

1. 从浏览器类型 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ：。
2. 选择要部署的策略，然后选择 **"应用于的** 组 **"旁边的"编辑"。**
3. 搜索要添加的组， **然后单击选择**。
4. 选择 **"关闭** 并 **更改设置"。**
5. 选择 **"关闭****和编辑策略"。**

该策略将推送到每个用户的移动设备，该策略将应用于他们下次从Microsoft 365登录时。 如果用户尚未将策略应用于其移动设备，则用户会通过注册和激活基本移动性和安全性的步骤在设备上收到通知。 完成注册后，策略将应用于其设备。 有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。

## <a name="step-4-block-email-access-for-unsupported-devices"></a>步骤 4：阻止不受支持的设备的电子邮件访问

为了帮助保护组织信息的安全，应阻止应用访问Microsoft 365移动性和安全性不支持的移动设备的电子邮件。 有关受支持的设备的列表，请参阅受支持的 [设备](../../admin/basic-mobility-security/capabilities.md)。

**若要阻止应用访问，**

1. 在浏览器中，键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. 选择 **"管理组织范围的设备访问设置"。**
3. 若要阻止不受支持的设备，请选择"如果设备不受基本移动性和安全性支持，Microsoft 365"下选择"**阻止"，** 然后选择"保存 **"。**

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本移动性和安全性阻止访问选项。":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>步骤 5：选择要从条件访问检查中排除的安全组

如果您要从他们的移动设备上的条件访问检查中排除某些人员，并且已为这些人员创建了一个或多个安全组，则在此处添加安全组。 这些组中人员不会为受支持的移动设备强制执行任何策略。 如果不再需要在组织中使用基本移动性和安全性，则推荐使用此选项。

1. 在浏览器中，键入 [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. 选择 **"管理组织范围的设备访问设置"。**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本移动性和安全性创建策略选项。":::

3. 选择 **"** 添加"，添加具有要排除的用户的安全组，阻止其访问Microsoft 365。 将用户添加到此列表后，他们可以使用不受支持的Microsoft 365访问电子邮件。

4. 在"选择组"面板中选择 **想要使用的安全** 组。

5. 选择名称，然后添加 **"保存**  >  **"。**

6. 在"**组织范围的设备访问设置"面板** 上，选择"保存 **"。**

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="基本移动性和安全性允许访问选项。":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>安全策略对不同设备类型的影响是什么？

将策略应用于用户设备时，对每台设备的影响因设备类型而异。 请查看以下示例表，了解策略对不同设备的影响。

|**安全策略**|**Android 4 及更高版本**|**Samsung KNOX**|**iOS 6 及更高版本**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|需要加密备份|否|是|是|需要 iOS 加密备份。|
|阻止云备份|是|是|是|阻止在 Android 上进行 Google 备份（灰显），阻止在 iOS 上进行云备份。|
|阻止文档同步|否|否|是|iOS：阻止云中的文档。|
|阻止照片同步 |否|否|是|iOS（本机）：阻止照片流。|
|阻止屏幕捕获 |否|是|是|在尝试时被阻止。|
|阻止视频会议 |否|否|是|FaceTime 在 iOS 上被阻止，在 Skype或其他上被阻止。|
|阻止发送诊断数据 |否|是|是|阻止在 Android 上发送 Google 故障报告。|
|阻止对应用商店的访问 |否|是|是|应用商店图标在 Android 主页上缺失，在 Windows 上禁用，在 iOS 上缺失。|
|要求提供应用商店的密码 |否|否|是|iOS：购买 iTunes 所需的密码。|
|阻止连接到可移动存储 |否|是|不适用|Android：SD 卡在设置中灰显Windows通知用户，安装的应用不可用|
|阻止蓝牙连接 |请参阅备注|请参阅备注|是|无法将蓝牙禁用为 Android 上的设置。 相反，我们禁用需要蓝牙的所有事务：高级音频分发、音频/视频远程控制、免手设备、耳机、电话书籍访问和串行端口。 使用以上任一项时，页面底部将显示一个小型 Toast 消息。|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>当您删除策略或从策略中删除用户时，会发生什么情况？

删除策略或删除策略部署到的组的用户时，策略设置、Microsoft 365电子邮件配置文件和缓存的电子邮件可能会从用户设备中删除。 请参阅下表，了解为不同设备类型删除的项。

|**删除的内容**|**iOS 6 及更高版本**|**Android 4 及更高版本 (Samsung KNOX**|
|:-----|:-----|:-----|
|托管电子邮件配置文件<sup>1</sup>|是|否|
|阻止云备份|是|否|

<sup>1</sup>如果部署策略时选择了"管理电子邮件配置文件"选项，则从用户设备中删除该配置文件中的托管电子邮件配置文件和缓存电子邮件。

将从移动设备中删除每个用户的策略，该策略将应用于其设备下次使用基本移动性和安全性进行登录。 如果部署适用于这些用户设备的新策略，系统会提示他们在基本移动性和安全性中重新注册。

还可以完全擦除设备，或选择性地擦除设备中的组织信息。 有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。

## <a name="related-content"></a>相关内容

[Overview of Basic Mobility and Security](overview.md) (article) \
[基本移动性和安全性](capabilities.md) 功能 (文章) 