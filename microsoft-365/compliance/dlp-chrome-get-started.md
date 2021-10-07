---
title: Microsoft 合规性扩展入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 准备及部署 Microsoft 合规性扩展。
ms.openlocfilehash: acfadd7ad57b12f4dabf2719457f96e96a5c3f69
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175223"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Microsoft 合规性扩展入门

使用这些过程推出 Microsoft 合规性扩展。

## <a name="before-you-begin"></a>开始之前

要使用 Microsoft 合规性扩展，设备必须装载到终结点 DLP中。 如果您是 DLP 或终结点 DLP 的新手，请阅读这些文章

- [了解 Microsoft 合规性扩展](dlp-chrome-learn-about.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [根据模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
- [了解终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
- [Windows 10 设备的装载工具和方法](dlp-configure-endpoints.md)
- [为 Endpoint DLP 配置设备代理和 Internet 连接设置](endpoint-dlp-configure-proxy.md)
- [使用终结点数据丢失防护](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

在开始使用终结点 DLP 之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何加载项。 若要访问和使用终结点 DLP 功能，必须具有这些订阅或加载项中的一个。

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 合规
- Microsoft 365 A5 合规
- Microsoft 365 E5 信息保护和治理
- Microsoft 365 A5 信息保护和治理

有关详细的许可指南，请参阅 [适用于安全性与合规性的 Microsoft 365 许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

- 您的组织必须获得终结点 DLP 的许可
- 您的设备必须运行 Windows 10 x64 内部版本 1809 或更高版本。
- 设备必须具有反恶意软件客户端（版本为 4.18.2101.9 或更高）。 请通过打开“**Windows 安全中心**”应用，选择“**设置**”图标，然后选择“**关于**”来查看当前版本。


### <a name="permissions"></a>权限

可在 [活动资源管理器](data-classification-activity-explorer.md) 中查看终结点 DLP 中的数据。 有七个角色可向活动资源管理器授予权限，用于访问数据的帐户必须是其中任何一个的成员。

- 全局管理员
- 合规性管理员
- 安全管理员
- 合规性数据管理员
- 全局读取者
- 安全读者
- 报表阅读人员

### <a name="overall-installation-workflow"></a>整体安装工作流

部署 Microsoft 合规性扩展是一个多阶段过程。可选择一次在一台计算机上安装，或将 Microsoft Endpoint Manager 或组策略用于组织范围的部署。

1. [准备设备](#prepare-your-devices)。
2. [基本设置单机自托管](#basic-setup-single-machine-selfhost)
3. [使用 Microsoft Endpoint Manager 部署](#deploy-using-microsoft-endpoint-manager)
4. [使用组策略部署](#deploy-using-group-policy)
5. [测试扩展](#test-the-extension)
6. [使用警报管理仪表板查看 Chrome DLP 警报](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [在活动资源管理器中查看 Chrome DLP 数据](#viewing-chrome-dlp-data-in-activity-explorer)

### <a name="prepare-infrastructure"></a>准备基础结构

如果要向所有受监视 Windows 10 设备推出 Microsoft 合规性扩展，应从不允许的应用列表中删除 Google Chrome。 有关详细信息，请参阅 [不允许的浏览器](endpoint-dlp-using.md#unallowed-browsers)。 如果只向少数设备推出，则可在不允许的浏览器列表中保留 Chrome。 对于已安装 Microsoft 合规性扩展的计算机，Microsoft 合规性扩展将绕过不允许应用列表的限制。

### <a name="prepare-your-devices"></a>准备设备

1. 使用这些主题中的过程载入设备：
    1. [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
    1. [Windows 10 设备的装载工具和方法](dlp-configure-endpoints.md)
    1. [为 Endpoint DLP 配置设备代理和 Internet 连接设置](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>基本设置单机自托管

这是推荐采用的方法。

1. 登录到要安装 Microsoft 合规性扩展的 Windows 10 计算机，并以管理员身份运行此 PowerShell 脚本。

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ```

2. 导航到“[Microsoft 合规性扩展 - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)。

3. 按照 Chrome Web Store 页面上的说明安装扩展。

### <a name="deploy-using-microsoft-endpoint-manager"></a>使用 Microsoft Endpoint Manager 进行部署

使用此设置方法进行组织范围的部署

##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>通过 Microsoft Endpoint Manager 启用所需的注册表项

1. 创建具有以下内容的 PowerShell 脚本：

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. 登录 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)。

3. 导航到“**设备**” > “**脚本**”，并选择“**添加**”。

4. 浏览到系统提示时创建的脚本位置。

5. 使用以下设置：
    1. 使用登录凭据运行此脚本：否
    1. 执行脚本签名检查：否
    1. 在 64 位 PowerShell 主机中运行脚本：是

6. 选择适当的设备组并应用该策略。

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Microsoft Endpoint Manager 强制安装步骤

将 Microsoft 合规性扩展添加到强制安装的扩展列表之前，引入 Chrome ADMX 是一个重要过程。 Google 记录了 Microsoft Endpoint Manager 中此过程的步骤：[使用 Microsoft Intune 管理 Chrome 浏览器 - Google Chrome 企业版帮助](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)。

 引入 ADMX 后，可按照以下步骤为此扩展创建配置文件。

1. 登录 Microsoft Endpoint Manager 管理中心 (https://endpoint.microsoft.com)。

2. 导航到配置文件。

3. 选择“**创建配置文件**”。

4. 选择“**Windows 10**”平台。

5. 选择“**自定义**”配置文件类型。

6. 选择“**设置**”选项卡。

7. 选择“**添加**”。

8. 输入以下策略信息。

    OMA-URI： `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    数据类型`String`<br/>
    值：`<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9. 单击“创建”。

### <a name="deploy-using-group-policy"></a>使用组策略部署

如果不想使用 Microsoft Endpoint Manager，可使用组策略在组织中部署 Microsoft 合规性扩展

1. 设备必须可通过组策略进行管理，并且需要将所有 Chrome ADMX 导入组策略中央存储。 有关详细信息，请参阅 [如何在 Windows 中创建和管理组策略管理模板的中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。

2. 使用下面的方法创建 PowerShell 脚本：

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3. 打开“**组策略管理控制台**”并导航到组织单位 (OU)。

4. 右键单击并选择“**在此域中创建 GPO，并在此处链接它**”。 系统提示时，为此组策略对象 (GPO) 分配一个描述性名称，然后完成创建。

5. 右键单击“GPO”，然后选择“**编辑**”。

6. 转到“**计算机配置**” > “**首选项**” > **控制面板设置** > “**已计划任务**”。

7. 通过右键单击，然后选择“**新建任务**” > “**立即任务（至少为 Windows 7）**”来创建新的立即任务。

8. 命名任务并提供说明。

9. 选择相应的帐户以运行立即任务，例如 NT Authority

10. 选择“**以最高权限运行**”。

11. 配置 Windows 10 的策略。

12. 在“**操作**”选项卡中，选择“**启动程序**”。

13. 输入步骤 1 中创建的程序/脚本的路径。

14. 选择“**应用**”。

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>将 Chrome 扩展添加到 ForceInstall 列表

1. 在组策略管理编辑器中，导航到“OU”。

2. 展开以下路径“**计算机/用户配置**” > “**策略**” > “**管理模板**” > “**经典管理模板**” > “**Google**” > “**Google Chrome**” > “**扩展**”。 此路径可能有所不同，具体取决于你的配置。

3. 选择“**配置强制安装的扩展列表**”。

4. 右键单击并选择“**编辑**”。

5. 选择“**已启用**”。

6. 选择“**显示**”。

7. 在“**值**”下添加以下条目：`echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8. 依次选择“**确定**”和“**应用**”。

### <a name="test-the-extension"></a>测试扩展

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>上传到云服务，或通过不允许的浏览器云出口访问

1. 创建或获取敏感项目，并尝试将文件上传到组织受限服务域之一。 敏感数据必须与我们的一个内置 [敏感信息类型](sensitive-information-type-entity-definitions.md) 或组织的敏感信息类型之一相匹配。 应从正在测试的设备上收到 DLP toast 通知，说明当文件打开时不允许此操作。

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>在 Chrome 中测试其他 DLP 方案

因为已从不允许的浏览器/应用列表中删除 Chrome，现可测试以下方案，以确认行为符合组织要求：

- 使用剪贴板将敏感项的数据复制到另一个文档
  - 若要测试，请在 Chrome 浏览器中打开要防止复制到剪贴板操作的文件，然后尝试复制该文件的数据。
  - 预期结果：DLP toast 通知，显示打开文件时不允许此操作。
- 打印文档
  - 若要测试，请在 Chrome 浏览器中打开防止打印操作的文件，然后尝试打印该文件。
  - 预期结果：DLP toast 通知，显示打开文件时不允许此操作。
- 复制到 USB 可移动媒体
  - 若要测试，请尝试将文件保存到可移动媒体存储器。
  - 预期结果：DLP toast 通知，显示打开文件时不允许此操作。
- 复制到网络共享
  - 若要测试，请尝试将文件保存到网络共享。
  - 预期结果：DLP toast 通知，显示打开文件时不允许此操作。

### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>使用警报管理仪表板查看 Chrome DLP 警报

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com) 内打开“**数据丢失防护**”页面，然后选择“**警报**”。

2. 请参阅 [如何配置和查看 DLP 策略警报](dlp-configure-view-alerts-policies.md) 中的过程，以查看你的终结点 DLP 策略警报。

### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>在活动资源管理器中查看 Chrome DLP 数据

1. 在 Microsoft 365 合规中心中打开域的“[数据分类页面](https://compliance.microsoft.com/dataclassification?viewid=overview)”，然后选择“**活动资源管理器**”。

2. 请参考[活动资源管理器入门](data-classification-activity-explorer.md)中的程序，以访问和筛选终结点设备的所有数据。

   > [!div class="mx-imgBorder"]
   > ![终结点设备的活动资源管理器筛选器。](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>已知问题和限制

1. 不支持对云出口执行阻止替代。
2. 不支持并必须禁用 Incognito 模式。

## <a name="next-steps"></a>后续步骤

现在，你已载入设备，并且可以在“活动资源管理器”中查看活动数据，那么就可以继续下一步，在其中创建保护敏感项目的 DLP 策略。

- [使用端点数据丢失防护](endpoint-dlp-using.md)

## <a name="see-also"></a>另请参阅

- [了解终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [使用终结点数据丢失防护](endpoint-dlp-using.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 设备的装载工具和方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [已建立 Azure AD 联接的设备](/azure/active-directory/devices/concept-azure-ad-join)
- [下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
