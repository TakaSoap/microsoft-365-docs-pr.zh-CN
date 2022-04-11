---
title: 了解并配置预览体验成员风险管理浏览器信号检测
description: 了解 Microsoft 365 中的预览体验成员风险管理浏览器信号检测
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
ms.openlocfilehash: e904c4576081cd459ca905a56e3dd6cec5b1af31
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758720"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection"></a>了解并配置预览体验成员风险管理浏览器信号检测

用户通常使用 Web 浏览器访问组织中的敏感文件和非敏感文件。 预览体验成员风险管理允许组织检测和处理在 [Microsoft Edge](https://www.microsoft.com/edge) 和 [Google Chrome](https://www.google.com/chrome) 浏览器中查看的所有不可执行文件的浏览器外泄信号。 借助这些信号，分析师和调查员可以在使用以下浏览器时，范围内策略用户执行以下任何活动时快速采取行动：

- 复制到个人云存储的文件
- 打印到本地或网络设备的文件
- 传输或复制到网络共享的文件
- 复制到 USB 设备的文件

在使用内置浏览器功能和使用 *Microsoft 合规性扩展* 加载项的Microsoft Edge中检测到这些事件的信号。 在 Google Chrome 中，客户使用 *Microsoft 合规性扩展* 进行信号检测。

下表汇总了每个浏览器检测到的活动和扩展支持：

| **检测到的活动**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| 复制到个人云存储的文件         | 本机             | 扩展名         |
| 打印到本地或网络设备的文件      | 本机             | 扩展名         |
| 传输或复制到网络共享的文件 | 扩展名          | 扩展名         |
| 复制到 USB 设备的文件                    | 扩展名          | 扩展名         |

## <a name="common-requirements"></a>常见要求

在安装Microsoft Edge加载项或 Google Chrome 扩展之前，客户需要确保范围内策略用户的设备满足以下要求：

- 建议使用最新Windows 10 x64 版本，最小Windows 10 x64 内部版本 1809 以获得信号检测支持。 非Windows设备目前不支持浏览器信号检测。
- 具有内部风险管理支持的当前[Microsoft 365订阅](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing)。
- 设备必须[载](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices)入到Microsoft 365合规性门户。

有关特定浏览器配置要求，请参阅本文后面的Microsoft Edge和 Google Chrome 部分。

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>为Microsoft Edge配置浏览器信号检测

### <a name="microsoft-edge-browser-requirements"></a>Microsoft Edge浏览器要求

- 满足常见要求
- Microsoft Edge x64、91.0.864.41 或更高版本
- *Microsoft 合规性扩展* 加载项版本 1.0.0.44 或更高版本
- Edge.exe未配置为未添加的浏览器

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>选项 1：建议使用 Edge) 进行测试的基本设置 (

使用此选项可在测试浏览器信号检测时为组织中的每个设备配置单个计算机自承载。

对于基本设置选项，请完成以下步骤：

1. 导航到 [Microsoft 合规性扩展](https://microsoftedge.microsoft.com/addons/detail/microsoft-compliance-exte/lcmcgbabdcbngcbcfabdncmoppkajglo)。
2. 安装扩展。

### <a name="option-2-intune-setup-for-edge"></a>选项 2：Intune Edge 设置

使用此选项可使用Intune配置组织的扩展和要求。

对于Intune设置选项，请完成以下步骤：

1. 使用管理员权限登录[到Microsoft Endpoint Manager管理中心](https://endpoint.microsoft.com)。
2. 导航到 **配置文件**。
3. 选择“**创建配置文件**”。
4. 选择 **Windows 10** 作为平台。
5. 选择 **“管理模板** ”作为 *配置文件类型* ，然后选择 **“创建”。**
6. 选择“**设置**”选项卡。
7. 选择 **Edge 版本 77 及更高版本。**
8. 搜索 **扩展** ，以便概述所有与扩展相关的设置。
9. 选择设置 **控制以无提示方式安装的扩展。**
10. 选择 **“已启用”。**
11. 出现提示时添加扩展 ID： *lcmcgbabdcbngcbcfabdncmoppkajglo***。**
12. 选择 **“确定”。**

### <a name="option-3-group-policy-setup-for-edge"></a>选项 3：组策略 Edge 设置

使用此选项可使用组策略在组织范围内配置扩展和要求。

对于组策略设置选项，请完成以下步骤：

**步骤 1：导入最新的Microsoft Edge管理模板 (.admx) 文件。**

设备必须可以使用组策略进行管理，所有[Microsoft Edge管理模板](https://www.microsoft.com/edge/business/download)都需要导入到 组策略 Central Store 中。 有关详细信息，请参阅 [如何在 Windows 中创建和管理组策略管理模板的中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。

**步骤 2：将 *Microsoft 合规性扩展* 加载项添加到 *“强制安装* ”列表。**

完成以下步骤以添加扩展：

1. 在 **组策略管理编辑器** 中，导航到组织单位 (OU) 。
2. 展开以下路径 **计算机/用户配置** \> **策略** \> **管理模板** \> **经典管理模板** \> **Microsoft Edge** \> **扩展**。 此路径可能因组织的配置而异。
3. 选择 **“配置以无提示方式安装的扩展”。**
4. 右键单击并选择 **“编辑**”。
5. 检查 **“启用** 的单选”按钮。
6. 选择“**显示**”。
7. 对于 **Value**，请添加以下条目： *lcmcgbabdcbngcbcfabdncmoppkajglo;https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. 选择 **“确定** ”，然后选择“ **应用**”。

## <a name="configure-browser-signal-detection-for-google-chrome"></a>为 Google Chrome 配置浏览器信号检测

通过 *Microsoft 合规性扩展* 启用 Google Chrome 的预览体验成员风险管理浏览器信号检测支持。 此扩展还支持 Chrome 上的 Endpoint DLP。 有关 Endpoint DLP 支持的详细信息，请参阅 [Microsoft 合规性扩展 (预览版) 开始](/microsoft-365/compliance/dlp-chrome-get-started)。

### <a name="google-chrome-browser-requirements"></a>Google Chrome 浏览器要求

- 满足常见要求
- 最新版本的 Google Chrome x64
- *Microsoft 合规性扩展* 版本 2.0.0.183 或更高版本
- Chrome.exe未配置为未添加的浏览器

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>选项 1：建议使用 Chrome) 进行测试的基本设置 (

使用此选项可在测试浏览器信号检测时为组织中的每个设备配置单个计算机自承载。

对于基本设置选项，请完成以下步骤：

**步骤 1：使用 PowerShell 启用所需的注册表项**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>这些注册表项是必需的，以确保扩展的适当功能。 在测试任何信号之前，必须启用这些注册表项。*

**步骤 2：安装 *Microsoft 合规性扩展***

1. 导航到 [Microsoft 合规性扩展](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)。
2. 安装扩展。

### <a name="option-2-intune-setup-for-chrome"></a>选项 2：Intune Chrome 设置

使用此选项可使用Intune配置组织的扩展和要求。

对于Intune设置选项，请完成以下步骤：

**步骤 1：使用Intune启用所需的注册表项**

1. 运行以下 PowerShell 脚本：

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. 登录到 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)。
3. 导航到 **“设备** \> **脚本”** ，然后选择 **“添加”。**
4. 浏览到系统提示时创建的脚本位置。
5. 使用以下设置：

    - 使用登录凭据运行此脚本： *是*
    - 强制执行脚本签名检查： *否*
    - 在 64 位 PowerShell 主机中运行脚本： *是*

6. 选择相应的设备组并应用策略。

**步骤 2：配置Intune强制安装**

在将 Microsoft DLP Chrome 扩展添加到已安装的强制扩展列表之前，必须安装 Chrome 管理模板 (.admx) 文件以进行Intune管理。 有关分步指南，请参阅使用[Microsoft Intune管理 Chrome 浏览器](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)。 安装管理模板文件后，完成以下步骤：

1. 登录到 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)。
2. 导航到 **配置文件**。
3. 选择“**创建配置文件**”。
4. 选择 **Windows 10** 作为 *平台*。
5. 选择 **“自定义** ”作为 *配置文件* 类型。
6. 选择“**设置**”选项卡。
7. 选择 **“添加”。**
8. 输入以下策略信息：

    - OMA-URI： *./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - 数据类型： *字符串*
    - 价值： *\<enabled/\>\<data id="ExtensionInstallForcelistDesc" value="1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/\>*

9. 选择“**创建**”。

### <a name="option-3-group-policy-setup-for-chrome"></a>选项 3：组策略 Chrome 设置

使用此选项可使用组策略在组织范围内配置扩展和要求。

对于组策略设置选项，请完成以下步骤：

**步骤 1：导入 Chrome 管理模板文件**

设备必须可以使用组策略进行管理，所有 [Chrome 管理模板](https://chromeenterprise.google/browser/download/)都需要导入到 组策略 Central Store。 有关详细信息，请参阅 [如何在 Windows 中创建和管理组策略管理模板的中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。

**步骤 2：使用 PowerShell 启用所需的注册表项**

1. 创建具有以下内容的 PowerShell 脚本：

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. 打开“**组策略管理控制台**”并导航到组织单位 (OU)。
3. 右键单击并选择 **“在此域中创建 GPO”，并将其链接到此处**。 出现提示时，请将描述性名称分配给此组策略对象 (GPO) 。 例如， *DLP Chrome 即时 PowerShell 脚本*。
4. 创建 GPO 后，右键单击并选择 **“编辑**”。 此选择将转到组策略对象。
5. 导航到 **计算机配置** \> **首选项** \> **控制面板设置** \> **计划的任务**。
6. 右键单击 **“计划任务**”下的空白区域，并选择“**新建** \> **即时任务” (至少Windows 7) 。**
7. 输入任务 *名称* 和 *说明*。
8. 选择相应的帐户以运行即时任务。 例如 *，NT 颁发机构*。
9. 选择“**以最高权限运行**”。
10. 配置 Windows 10 的策略。
11. 在 **“操作”** 选项卡上，选择 **“启动程序**”。
12. 输入步骤 **1** 中创建的程序/脚本的路径。
13. 选择“**应用**”。

**步骤 3：将 Chrome 扩展添加到“强制安装”列表**

1. 在 **组策略管理编辑器** 中，导航到组织单位 (OU) 。
2. 展开以下路径 **计算机/用户配置** \> **策略** \> **管理模板** \> **经典管理模板** \> **Google Google** \> **Chrome** \> **扩展**。 此路径可能因组织的配置而异。
3. 选择 **“配置已安装的强制扩展的列表**”。
4. 右键单击并选择 **“编辑**”。
5. 选择 **“启用** 的单选”按钮。
6. 选择“**显示**”。
7. 对于 **Value**，请添加以下条目： *echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx*
8. 选择 **“确定** ”，然后选择“ **应用**”。

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>测试和验证内部风险管理浏览器信号检测

1. 创建启用了设备指示器的内部风险管理策略。
2. 若要测试复制到个人云存储的文件的信号检测，请从受支持的Windows设备完成以下步骤：

    - 使用已配置为信号检测的浏览器类型打开文件共享网站 (Microsoft OneDrive、Google 云端硬盘等) 。
    - 使用浏览器，将不可执行文件上传到网站。
3. 若要测试打印到本地或网络设备的文件、传输或复制到网络共享的文件以及复制到 USB 设备的文件的信号检测，请从受支持的Windows设备完成以下步骤：

    - 直接在浏览器中打开不可执行文件。 该文件必须直接通过文件资源管理器打开，或在新的浏览器选项卡中打开以供查看，而不是网页。
    - 打印文件。
    - 将文件保存到 USB 设备。
    - 将文件保存到网络驱动器。
  
4. 创建第一个内部风险管理策略后，大约 24 小时后，你将开始收到来自活动指示器的警报。 检查 [警报仪表板](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) ，了解已测试活动的预览体验成员风险管理警报。
