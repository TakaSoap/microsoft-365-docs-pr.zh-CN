---
title: 排查 Android 上Microsoft Defender for Endpoint的问题
description: 排查 Android 上Microsoft Defender for Endpoint的问题
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 云， 连接， 通信
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3103ab5332045da58609b048d637da30d287ed10
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666561"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>排查 Android 上 Microsoft Defender for Endpoint 的问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

载入设备时，可能会在安装应用后看到登录问题。

在载入过程中，在设备上安装应用后，可能会遇到登录问题。

本文提供有助于解决登录问题的解决方案。

## <a name="sign-in-failed---unexpected-error"></a>登录失败 - 意外错误

**登录失败：***意外错误，请稍后尝试*

:::image type="content" source="images/f9c3bad127d636c1f150d79814f35d4c.png" alt-text="Microsoft Defender 365 门户的登录页中出现登录失败错误&quot;意外&quot;错误。" lightbox="images/f9c3bad127d636c1f150d79814f35d4c.png":::

**消息：**

意外错误，请稍后尝试

**原因：**

设备上安装了较旧版本的"Microsoft Authenticator"应用。

**解决 方案：**

从 Google Play Store 安装最新版本和[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)，然后重试。

## <a name="sign-in-failed---invalid-license"></a>登录失败 - 许可证无效

**登录失败：***许可证无效，请与管理员联系*

:::image type="content" source="images/920e433f440fa1d3d298e6a2a43d4811.png" alt-text="Microsoft Defender 365 门户登录页中的指令联系人详细信息" lightbox="images/920e433f440fa1d3d298e6a2a43d4811.png":::

**消息：***许可证无效，请与管理员联系*

**原因：**

你没有分配Microsoft 365许可证，或者你的组织没有Microsoft 365 企业版订阅的许可证。

**解决 方案：**

请与管理员联系以获取帮助。

## <a name="report-unsafe-site"></a>报告不安全的站点

网络钓鱼网站模拟值得信赖的网站，以获取个人或财务信息。 若要报告可能是网络钓鱼网站的网站，请访问 ["提供有关网络保护"页面的反馈](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 。

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>某些 OEM 设备上不会阻止网络钓鱼页面

**适用于：** 仅限特定 OEM

- **小米**

某些小米设备上不会阻止 Defender for Endpoint for Android 检测到的网络钓鱼和有害 Web 威胁。 以下功能在这些设备上不起作用。

:::image type="content" source="images/0c04975c74746a5cdb085e1d9386e713.png" alt-text="站点不安全的通知消息" lightbox="images/0c04975c74746a5cdb085e1d9386e713.png":::

**原因：**

小米设备包括新的权限模型。 这可防止 Defender for Endpoint for Android 在后台运行时显示弹出窗口。

小米设备权限："在后台运行时显示弹出窗口。

:::image type="content" source="images/6e48e7b29daf50afddcc6c8c7d59fd64.png" alt-text="Microsoft Defender 365 门户中的弹出式设置窗格" lightbox="images/6e48e7b29daf50afddcc6c8c7d59fd64.png":::

**解决 方案：**

在小米设备上启用所需的权限。

- 在后台运行时显示弹出窗口。

## <a name="unable-to-allow-permission-for-permanent-protection-during-onboarding-on-some-oem-devices"></a>在某些 OEM 设备上加入过程中无法允许"永久保护"权限

**适用于：** 仅限特定的 OEM 设备。

- **使用 Android 11 的小米**

作为应用载入的一部分，Defender 应用要求对设备授予电池优化/永久保护权限，选择 **"允许** "将返回无法设置权限的错误。 它只影响名为"永久保护"的最后一个权限。 

**原因：**

小米在 Android 11 中更改了电池优化权限。 不允许 Defender for Endpoint 将此设置配置为忽略电池优化。

**解决 方案：**

我们正在与 OEM 合作，以查找一个解决方案，以从应用载入屏幕启用此权限。 解决此问题时，我们将更新文档。
用户可以按照以下步骤从设备设置启用相同的权限： 

1. 转到设备上的 **设置**。

2. 搜索并选择 **"电池优化**"。

   :::image type="content" source="images/search-battery-optimisation.png" alt-text="可在其中搜索并选择&quot;电池优化&quot;的页面" lightbox="images/search-battery-optimisation.png":::

3. 在 **特殊应用访问中**，选择 **"电池优化**"。

   :::image type="content" source="images/special-app-access.png" alt-text="可从中选择&quot;电池优化&quot;的特殊应用访问窗格" lightbox="images/special-app-access.png":::

4. 更改下拉列表以显示 **所有应用**。

   :::image type="content" source="images/show-all-apps-2.png" alt-text="可在&quot;电池优化&quot;窗格下将值更改为&quot;所有应用&quot;的下拉列表" lightbox="images/show-all-apps-2.png":::

   :::image type="content" source="images/show-all-apps-1.png" alt-text="在&quot;电池优化&quot;窗格下显示&quot;所有应用&quot;选项的下拉列表" lightbox="images/show-all-apps-1.png":::

5. 找到"Microsoft Defender for Endpoint"，然后选择 **"不优化**"。

   :::image type="content" source="images/select-dont-optimise.png" alt-text="启用选项位置的页面Microsoft Defender for Endpoint和选择&quot;不优化&quot;" lightbox="images/select-dont-optimise.png":::

返回到Microsoft Defender for Endpoint载入屏幕，选择 **"允许**"，将重定向到仪表板屏幕。

## <a name="send-in-app-feedback"></a>发送应用内反馈

如果用户面临的问题尚未在上述部分中解决，或者无法使用列出的步骤解决，则用户可以提供 **应用内反馈** 以及 **诊断数据**。 然后，我们的团队可以调查日志，以提供正确的解决方案。 用户可以按照以下步骤执行相同的操作：

1.  在设备上打开 **MDE 应用程序** ，然后单击左上角的 **配置文件图标** 。

    :::image type="content" source="images/select-profile-icon-1.jpg" alt-text="Microsoft Defender for Endpoint门户中的配置文件图标" lightbox="images/select-profile-icon-1.jpg":::

2.  选择"帮助&反馈"。

    :::image type="content" source="images/selecthelpandfeedback2.png" alt-text="可在Microsoft Defender for Endpoint门户中选择的&quot;帮助&反馈&quot;选项" lightbox="images/selecthelpandfeedback2.png":::

3.  选择"向 Microsoft 发送反馈"。

    :::image type="content" alt-text="选择向 Microsoft 发送反馈" source="images/send-feedback-to-microsoft-3.jpg":::

4.  从给定选项中进行选择。 若要报告问题，请选择"我想报告问题"。

    :::image type="content" source="images/report-issue-4.jpg" alt-text="&quot;我想报告问题&quot;选项" lightbox="images/report-issue-4.jpg":::

5.  提供你面临的问题的详细信息，并检查"发送诊断数据"。 建议检查"包括电子邮件地址"，以便团队可以使用解决方案或后续操作联系你。

    :::image type="content" source="images/finalsubmit5.png" alt-text="可以添加详细信息并附加诊断数据的窗格" lightbox="images/finalsubmit5.png":::

6.  单击"提交"以成功发送反馈。
