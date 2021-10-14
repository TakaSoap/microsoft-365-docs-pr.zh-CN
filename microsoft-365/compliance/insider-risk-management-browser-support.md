---
title: '了解并配置预览版中的内部风险管理 (信号) '
description: 了解企业内部风险管理浏览器信号检测Microsoft 365
keywords: Microsoft 365- 预览体验计划风险管理、风险管理、合规性
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: a89393a2e420948a126ec5503a16ce981ed9652a
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60334492"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection-preview"></a>了解并配置预览版中的内部风险管理 (信号) 

用户通常使用 Web 浏览器访问组织中敏感和非敏感的文件。 通过内部风险管理，你的组织可以检测并处理在 Microsoft Edge 和[Google Chrome](https://www.google.com/chrome)浏览器中查看的所有[非可执行文件的](https://www.microsoft.com/edge)浏览器过滤信号。 借助这些信号，当范围内策略用户在使用这些浏览器执行以下任一活动时，分析员和研究人员可以快速采取行动：

- 复制到个人云存储的文件
- 打印到本地或网络设备的文件
- 传输或复制到网络共享的文件
- 复制到 USB 设备的文件

使用内置浏览器功能Microsoft Edge *Microsoft 预览* 体验成员风险扩展加载项在浏览器中检测到这些事件的信号。 在 Google Chrome 中，客户使用 *Microsoft 合规性扩展* 进行信号检测。

下表汇总了每个浏览器的检测到的活动和扩展支持：

| **检测到的活动**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| 复制到个人云存储的文件         | 本机             | 扩展名         |
| 打印到本地或网络设备的文件      | 本机             | 扩展名         |
| 传输或复制到网络共享的文件 | 扩展名          | 扩展名         |
| 复制到 USB 设备的文件                    | 扩展名          | 扩展名         |

## <a name="common-requirements"></a>常见要求

在安装 Microsoft *Insider Risk Extension* 或 *Microsoft Compliance Extension* 之前，客户需要确保范围内策略用户的设备满足以下要求

- 建议Windows 10 x64 内部版本，Windows 10 x64 版本 1809 的最低版本，以用于信号检测支持。 浏览器信号检测当前在非 Windows设备上不受支持。
- 当前[Microsoft 365](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing)内部风险管理支持的订阅。
- 设备必须[载入到](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices)Microsoft 365 合规性门户。

有关特定浏览器配置要求，请参阅本文Microsoft Edge和 Google Chrome 部分。

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>为浏览器配置浏览器信号检测Microsoft Edge

### <a name="microsoft-edge-browser-requirements"></a>Microsoft Edge浏览器要求

- 满足常见要求
- Microsoft Edge x64、91.0.864.41 或更高版本
- *Microsoft Insider Risk Extension* 加载项版本 1.0.0.44 或更高版本
- Edge.exe未配置为不允许的浏览器

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>选项 1：建议 (边缘服务器进行测试的基本) 

在测试浏览器信号检测时，使用此选项为组织的每台设备配置单台计算机自主机。

对于基本设置选项，请完成以下步骤：

1. 导航到 [Microsoft Insider Risk Extension](https://microsoftedge.microsoft.com/addons/detail/microsoft-insider-risk-ex/lcmcgbabdcbngcbcfabdncmoppkajglo)。
2. 安装扩展。

### <a name="option-2-intune-setup-for-edge"></a>选项 2：Edge 的 Intune 设置

用户此选项使用 Intune 为组织配置扩展和要求。

对于 Intune 设置选项，请完成以下步骤：

1. 使用管理员权限[Microsoft Endpoint Manager](https://endpoint.microsoft.com)登录管理中心。
2. 导航到 **配置文件**。
3. 选择“**创建配置文件**”。
4. 选择 **Windows 10** 作为平台。
5. 选择 **"管理模板"***作为配置文件类型，* 然后选择"创建 **"。**
6. 选择“**设置**”选项卡。
7. 选择 **"边缘版本 77 及更高版本"。**
8. 搜索 **扩展** ，它为你提供所有与扩展相关的设置的概述。
9. 选择设置 **"控制以静默方式安装哪些扩展"。**
10. 选择 **"已启用"。**
11. 当系统提示时添加扩展 *ID：lcmcgbabdcbngcbcfabdncmoppkajglo***。**
12. 选择 **"确定"。**

### <a name="option-3-group-policy-setup-for-edge"></a>选项 3：边缘的组策略设置

使用此选项使用组策略在组织范围内配置扩展和要求。

对于组策略设置选项，请完成以下步骤：

**步骤 1：导入最新的 Microsoft Edge.admx (.admx) 文件。**

设备必须使用组策略进行管理，并且Microsoft Edge[模板](https://www.microsoft.com/edge/business/download)需要导入组策略中央存储中。 有关详细信息，请参阅 [如何在 Windows 中创建和管理组策略管理模板的中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。

**步骤 2：将 *Microsoft Insider Risk Management Extension* 加载项添加到 *强制安装* 列表。**

完成以下步骤以添加扩展：

1. 在组 **策略管理编辑器中**，导航到组织单位 (OU) 。
2. 展开以下路径 **计算机/用户配置** \> **策略** \> **管理模板** \> **经典管理** 模板 \> **Microsoft Edge** \> **扩展**。 此路径可能因组织的配置而异。
3. 选择 **"配置以静默方式安装哪些扩展"。**
4. 右键单击并选择"编辑 **"。**
5. 选中" **已启用"** 单选按钮。
6. 选择“**显示**”。
7. 对于 **Value**，添加以下条目 *：lcmcgbabdcbngcbcfabdncmoppkajglo; https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. 选择 **"确定**"，然后选择"应用 **"。**

## <a name="configure-browser-signal-detection-for-google-chrome"></a>为 Google Chrome 配置浏览器信号检测

通过 Microsoft 合规性扩展启用对 Google Chrome 的内部风险管理浏览器信号检测 *支持*。 此扩展还支持 Chrome 上的 Endpoint DLP。 有关 Endpoint DLP 支持的详细信息，请参阅 Microsoft 合规性扩展 ([预览版) 。 ](/microsoft-365/compliance/dlp-chrome-get-started)

### <a name="google-chrome-browser-requirements"></a>Google Chrome 浏览器要求

- 满足常见要求
- 最新版本的 Google Chrome x64
- *Microsoft 合规性扩展* 版本 2.0.0.183 或更高版本
- Chrome.exe未配置为不允许的浏览器

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>选项 1：建议 (Chrome 应用进行测试的基本) 

在测试浏览器信号检测时，使用此选项为组织的每台设备配置单台计算机自主机。

对于基本设置选项，请完成以下步骤：

**步骤 1：使用 PowerShell 启用必需的注册表项**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>需要这些注册表项来确保扩展的正确功能。 在测试任何信号之前，必须启用这些注册表项。*

**步骤 2：安装 *Microsoft 合规性扩展***

1. 导航到 [Microsoft 合规性扩展](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)。
2. 安装扩展。

### <a name="option-2-intune-setup-for-chrome"></a>选项 2：针对 Chrome 的 Intune 设置

用户此选项使用 Intune 为组织配置扩展和要求。

对于 Intune 设置选项，请完成以下步骤：

**步骤 1：使用 Intune 启用必需的注册表项**

1. 运行以下 PowerShell 脚本：

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. 登录到管理[Microsoft Endpoint Manager中心](https://endpoint.microsoft.com)。
3. 导航到 **"设备** \> **脚本"，** 然后选择" **添加"。**
4. 浏览到系统提示时创建的脚本位置。
5. 使用以下设置：

    - 使用登录凭据运行此脚本： *是*
    - 强制执行脚本签名检查： *否*
    - 在 64 位 PowerShell 主机中运行脚本： *是*

6. 选择相应的设备组并应用策略。

**步骤 2：配置 Intune 强制安装**

在将 Microsoft DLP Chrome 扩展添加到强制安装的扩展列表中之前，必须安装 Chrome 管理模板 (.admx) 文件进行 Intune 管理。 有关分步指南，请参阅使用 Microsoft Intune[管理 Chrome 浏览器](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)。 安装管理模板文件后，完成以下步骤：

1. 登录到管理[Microsoft Endpoint Manager中心](https://endpoint.microsoft.com)。
2. 导航到 **配置文件**。
3. 选择“**创建配置文件**”。
4. 选择 **Windows 10** 作为 *平台*。
5. 选择 **"** 自定义" *作为配置文件* 类型。
6. 选择“**设置**”选项卡。
7. 选择 **"添加"。**
8. 输入以下策略信息：

    - *OMA-URI：./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - 数据类型 *：String*
    - 值： *\<enabled/\>\<data id=”ExtensionInstallForcelistDesc” value=”1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/\>*

9. 选择“**创建**”。

### <a name="option-3-group-policy-setup-for-chrome"></a>选项 3：Chrome 的组策略设置

使用此选项使用组策略在组织范围内配置扩展和要求。

对于组策略设置选项，请完成以下步骤：

**步骤 1：导入 Chrome 管理模板文件**

你的设备必须使用组策略进行管理，并且所有 [Chrome](https://chromeenterprise.google/browser/download/) 管理模板都需要导入组策略中央存储中。 有关详细信息，请参阅 [如何在 Windows 中创建和管理组策略管理模板的中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。

**步骤 2：使用 PowerShell 启用必需的注册表项**

1. 创建具有以下内容的 PowerShell 脚本：

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. 打开“**组策略管理控制台**”并导航到组织单位 (OU)。
3. 右键单击并选择 **"在此域中创建 GPO"，并在此处链接它**。 当系统提示时，向 GPO 中的此组策略对象 (描述) 。 例如 *，DLP Chrome 即时 PowerShell 脚本*。
4. 创建 GPO 后，右键单击并选择"编辑 **"。** 此选择将您带至组策略对象。
5. 导航到 **计算机配置** \> **首选项** \> **控制面板设置** \> **计划任务**。
6. 右键单击"计划任务"下的空白区域，然后选择"新建即时任务" (至少Windows \> **7) 。**
7. 输入任务 *名称和**说明*。
8. 选择相应的帐户以运行即时任务。 例如 *，NT Authority*。
9. 选择“**以最高权限运行**”。
10. 配置 Windows 10 的策略。
11. 在"**操作"** 选项卡上，选择"**启动程序"。**
12. 输入在步骤 1 中创建的程序/ **脚本的路径**。
13. 选择“**应用**”。

**步骤 3：将 Chrome 扩展添加到强制安装列表**

1. 在组 **策略管理编辑器中**，导航到组织单位 (OU) 。
2. 展开以下路径 **计算机/用户配置** \> **策略** \> **管理模板** \> **经典管理模板** \> **Google** \> **Google Chrome** \> **扩展**。 此路径可能因组织的配置而异。
3. 选择 **配置强制安装的扩展的列表**。
4. 右键单击并选择"编辑 **"。**
5. 选择" **已启用"** 单选按钮。
6. 选择“**显示**”。
7. 对于 **Value**，添加以下条目 *：echcggldkblhodogklpincgchnpgcdco; https://clients2.google.com/service/update2/crx*
8. 选择 **"确定**"，然后选择"应用 **"。**

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>测试和验证内部风险管理浏览器信号检测

1. 创建已启用设备指示器的内部风险管理策略。
2. 若要测试复制到个人云存储的文件的信号检测，请从受支持的设备中完成Windows步骤：

    - 打开文件共享网站 (Microsoft OneDrive、Google 云端硬盘等) 配置用于信号检测的浏览器类型。
    - 通过浏览器，将非可执行文件上载到网站。
3. 若要测试信号检测到本地或网络设备的文件、传输或复制到网络共享的文件以及复制到 USB 设备的文件，请从受支持的 Windows 设备完成以下步骤：

    - 直接在浏览器中打开非可执行文件。 必须直接通过文件资源管理器打开文件，或在新的浏览器选项卡（而不是网页）中打开文件。
    - 打印文件。
    - 将文件保存到 USB 设备。
    - 将文件保存到网络驱动器。
  
4. 创建首个内部风险管理策略后，你将在大约 24 小时后开始从活动指示器接收警报。 查看 [警报仪表板，](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) 了解测试活动的内部风险管理警报。
