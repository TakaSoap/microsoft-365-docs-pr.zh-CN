---
title: macOS 加泰罗尼亚语和较新版本的 macOS 的新配置文件
description: 本主题介绍为了从系统扩展中获益而必须所做的更改，系统扩展是 macOS Catalina 和较新版本 macOS 上内核扩展的替换。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 内核， 系统， 扩展， 加泰罗尼亚语
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 374bd7b6f31cfb555e8f6189a01b4946980c0fc6
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171517"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a>macOS 加泰罗尼亚语和较新版本的 macOS 的新配置文件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

为了与 macOS 发展保持一致，我们正在准备利用系统扩展而非内核扩展的 macOS 更新上的 Microsoft Defender for Endpoint。 此更新仅适用于 macOS 10.15.4 (macOS) macOS 版本。

如果你通过 JAMF、Intune 或其他 MDM 解决方案 (托管环境中在 macOS 上部署了 Microsoft Defender for Endpoint) ，则必须部署新的配置文件。 如果不执行这些步骤，则会导致用户收到运行这些新组件的审批提示。

## <a name="jamf"></a>JAMF

### <a name="jamf-system-extensions-policy"></a>JAMF 系统扩展策略

若要批准系统扩展，请创建以下有效负载：

1. In **Computers > Configuration Profiles** select Options > System **Extensions**.
2. 从 **"系统扩展类型"** 下拉列表 **中选择** "允许的系统扩展"。
3. 将 **UBF8T346G9 用于** 团队 ID。
4. 将以下捆绑包标识符添加到允许 **的系统扩展** 列表中：

    - **com.microsoft.wdav.epsext**
    - **com.microsoft.wdav.netext**

    ![批准的系统扩展屏幕截图。](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a>隐私首选项策略控制

添加以下 JAMF 有效负载以授予对 Microsoft Defender 终结点安全扩展的完全磁盘访问权限。 此策略是在设备上运行扩展的先决条件。

1. 选择 **选项** \> **隐私首选项策略控制**。
2. 用作 `com.microsoft.wdav.epsext` 标识符 **和** `Bundle ID` 捆绑 **包类型**。
3. 将代码要求设置为 `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
4. 将 **应用或服务设置为** **SystemPolicyAllFiles，** 并访问 **允许**。

    ![隐私首选项策略控制。](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a>网络扩展策略

作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft 365 Defender 门户。 以下策略允许网络扩展执行此功能。

> [!NOTE]
> JAMF 没有对内容筛选策略的内置支持，这是启用 MacOS 上的 Microsoft Defender for Endpoint 在设备上安装的网络扩展的先决条件。 此外，JAMF 有时会更改正在部署的策略的内容。
> 因此，以下步骤提供了涉及对配置文件进行签名的解决方法。

1. 将以下内容保存为使用 `com.microsoft.network-extension.mobileconfig` 文本编辑器的设备：

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. 在终端中运行实用工具，确认上述 `plutil` 文件已正确复制：

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    例如，如果文件存储在 Documents 中：

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```

    验证命令是否输出 `OK` 。

    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```

3. 按照此页面上 [的说明，](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) 使用 JAMF 的内置证书颁发机构创建签名证书。

4. 创建证书并安装到设备后，从终端运行以下命令对文件进行签名：

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```

    例如，如果证书名称为 **SigningCertificate，** 并且签名文件将存储在 Documents 中：

    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```

5. 从 JAMF 门户中，导航到 **"配置文件**"，**然后单击"Upload** 按钮。 在 `com.microsoft.network-extension.signed.mobileconfig` 系统提示您输入文件时选择。

## <a name="intune"></a>Intune

### <a name="intune-system-extensions-policy"></a>Intune 系统扩展策略

批准系统扩展：

1. 在 Intune 中，打开 **"管理** \> **设备配置"。** 选择 **"管理** \> **配置文件** \> **""创建配置文件"。**
2. 选择配置文件的名称。 将 **Platform=macOS** 更改为 **Profile type=Extensions**。 选择“**创建**”。
3. 在 `Basics` 选项卡中，为此新配置文件命名。
4. 在 `Configuration settings` 选项卡中，在 部分中添加以下 `Allowed system extensions` 条目：

   <br>

   ****

   |捆绑包标识符|团队标识符|
   |---|---|
   |com.microsoft.wdav.epsext|UBF8T346G9|
   |com.microsoft.wdav.netext|UBF8T346G9|
   |||

   ![系统配置文件屏幕截图。](images/mac-system-extension-intune2.png)

5. 在 `Assignments` 选项卡中，将此配置文件分配给"所有用户 **&所有设备"。**
6. 查看并创建此配置文件。

### <a name="create-and-deploy-the-custom-configuration-profile"></a>创建和部署自定义配置文件

以下配置文件启用网络扩展，并授予对终结点安全系统扩展的完全磁盘访问权限。

将以下内容保存到名为sysext.xml **的文件：**

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

验证上述文件是否复制正确。 从终端运行以下命令并验证它是否输出 `OK` ：

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

部署此自定义配置文件：

1. 在 Intune 中，打开 **"管理** \> **设备配置"。** 选择 **"管理** \> **配置文件** \> **""创建配置文件"。**
2. 选择配置文件的名称。 Change **Platform=macOS** and **Profile type=Custom**. 选择"**配置"。**
3. 打开配置文件， **然后上传** sysext.xml。 此文件是在上一步骤中创建的。
4. 选择“**确定**”。

    ![Intune 中的系统扩展屏幕截图。](images/mac-system-extension-intune.png)

5. 在 `Assignments` 选项卡中，将此配置文件分配给"所有用户 **&所有设备"。**
6. 查看并创建此配置文件。
