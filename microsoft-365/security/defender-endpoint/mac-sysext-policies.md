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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 28a332cec68521741bdda62aeecd25440552344a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932735"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a><span data-ttu-id="c0d1e-104">macOS 加泰罗尼亚语和较新版本的 macOS 的新配置文件</span><span class="sxs-lookup"><span data-stu-id="c0d1e-104">New configuration profiles for macOS Catalina and newer versions of macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0d1e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0d1e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0d1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c0d1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0d1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c0d1e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c0d1e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0d1e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c0d1e-110">为了与 macOS 发展保持一致，我们正在准备利用系统扩展而非内核扩展的 macOS 更新上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-110">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on macOS update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="c0d1e-111">此更新仅适用于 macOS Catalina (10.15.4) 更高版本的 macOS。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-111">This update will only be applicable to macOS Catalina (10.15.4) and newer versions of macOS.</span></span>

<span data-ttu-id="c0d1e-112">如果你通过 JAMF、Intune 或其他 MDM 解决方案 (托管环境中在 macOS 上部署了 Microsoft Defender for Endpoint) ，则必须部署新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-112">If you have deployed Microsoft Defender for Endpoint on macOS in a managed environment (through JAMF, Intune, or another MDM solution), you must deploy new configuration profiles.</span></span> <span data-ttu-id="c0d1e-113">如果不执行这些步骤，将导致用户收到运行这些新组件的审批提示。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-113">Failure to do these steps will result in users getting approval prompts to run these new components.</span></span>

## <a name="jamf"></a><span data-ttu-id="c0d1e-114">JAMF</span><span class="sxs-lookup"><span data-stu-id="c0d1e-114">JAMF</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="c0d1e-115">系统扩展策略</span><span class="sxs-lookup"><span data-stu-id="c0d1e-115">System Extensions Policy</span></span>

<span data-ttu-id="c0d1e-116">若要批准系统扩展，请创建以下有效负载：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-116">To approve the system extensions, create the following payload:</span></span>

1. <span data-ttu-id="c0d1e-117">In **Computers > Configuration Profiles** select Options > System **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="c0d1e-117">In **Computers > Configuration Profiles** select **Options > System Extensions**.</span></span>
2. <span data-ttu-id="c0d1e-118">从 **"系统扩展类型"** 下拉列表 **中选择** "允许的系统扩展"。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-118">Select **Allowed System Extensions** from the **System Extension Types** drop-down list.</span></span>
3. <span data-ttu-id="c0d1e-119">将 **UBF8T346G9 用于** 团队 ID。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-119">Use **UBF8T346G9** for Team Id.</span></span>
4. <span data-ttu-id="c0d1e-120">将以下捆绑包标识符添加到允许 **的系统扩展** 列表中：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-120">Add the following bundle identifiers to the **Allowed System Extensions** list:</span></span>

    - <span data-ttu-id="c0d1e-121">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-121">**com.microsoft.wdav.epsext**</span></span>
    - <span data-ttu-id="c0d1e-122">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-122">**com.microsoft.wdav.netext**</span></span>

    ![批准的系统扩展屏幕截图](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a><span data-ttu-id="c0d1e-124">隐私首选项策略控制</span><span class="sxs-lookup"><span data-stu-id="c0d1e-124">Privacy Preferences Policy Control</span></span>

<span data-ttu-id="c0d1e-125">添加以下 JAMF 有效负载以授予对 Microsoft Defender 终结点安全扩展的完全磁盘访问权限。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-125">Add the following JAMF payload to grant Full Disk Access to the Microsoft Defender for Endpoint Endpoint Security Extension.</span></span> <span data-ttu-id="c0d1e-126">此策略是在设备上运行扩展的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-126">This policy is a pre-requisite for running the extension on your device.</span></span>

1. <span data-ttu-id="c0d1e-127">选择 **选项**  >  **隐私首选项策略控制**。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-127">Select **Options** > **Privacy Preferences Policy Control**.</span></span>
2. <span data-ttu-id="c0d1e-128">用作 `com.microsoft.wdav.epsext` 标识符 **和** `Bundle ID` 捆绑 **包类型**。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-128">Use `com.microsoft.wdav.epsext` as the **Identifier** and `Bundle ID` as **Bundle type**.</span></span>
3. <span data-ttu-id="c0d1e-129">将代码要求设置为 `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="c0d1e-129">Set Code Requirement to `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
4. <span data-ttu-id="c0d1e-130">将 **应用或服务设置为** **SystemPolicyAllFiles，** 并访问 **允许**。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-130">Set **App or service** to **SystemPolicyAllFiles** and access to **Allow**.</span></span>

    ![隐私首选项策略控制](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a><span data-ttu-id="c0d1e-132">网络扩展策略</span><span class="sxs-lookup"><span data-stu-id="c0d1e-132">Network Extension Policy</span></span>

<span data-ttu-id="c0d1e-133">作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心 门户。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-133">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="c0d1e-134">以下策略允许网络扩展执行此功能。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-134">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="c0d1e-135">JAMF 没有对内容筛选策略的内置支持，这是启用 MacOS 上的 Microsoft Defender for Endpoint 在设备上安装的网络扩展的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-135">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint on macOS installs on the device.</span></span> <span data-ttu-id="c0d1e-136">此外，JAMF 有时会更改正在部署的策略的内容。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-136">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="c0d1e-137">因此，以下步骤提供了涉及对配置文件进行签名的解决方法。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-137">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="c0d1e-138">将以下内容保存为使用 `com.microsoft.network-extension.mobileconfig` 文本编辑器的设备：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-138">Save the following content to your device as `com.microsoft.network-extension.mobileconfig` using a text editor:</span></span>

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

2. <span data-ttu-id="c0d1e-139">在终端中运行实用工具，确认上述 `plutil` 文件已正确复制：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-139">Verify that the above file was copied correctly by running the `plutil` utility in the Terminal:</span></span>

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    <span data-ttu-id="c0d1e-140">例如，如果文件存储在 Documents 中：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-140">For example, if the file was stored in Documents:</span></span>

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    <span data-ttu-id="c0d1e-141">验证命令是否输出 `OK` 。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-141">Verify that the command outputs `OK`.</span></span>
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. <span data-ttu-id="c0d1e-142">按照此页面上 [的说明，](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) 使用 JAMF 的内置证书颁发机构创建签名证书。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-142">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority.</span></span>

4. <span data-ttu-id="c0d1e-143">创建证书并安装到设备后，从终端运行以下命令对文件进行签名：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-143">After the certificate is created and installed to your device, run the following command from the Terminal to sign the file:</span></span>

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    <span data-ttu-id="c0d1e-144">例如，如果证书名称为 **SigningCertificate，** 并且签名文件将存储在 Documents 中：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-144">For example, if the certificate name is **SigningCertificate** and the signed file is going to be stored in Documents:</span></span>
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. <span data-ttu-id="c0d1e-145">从 JAMF 门户中，导航到 **"配置文件**"，**然后单击"Upload** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-145">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> <span data-ttu-id="c0d1e-146">在 `com.microsoft.network-extension.signed.mobileconfig` 系统提示您输入文件时选择。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-146">Select `com.microsoft.network-extension.signed.mobileconfig` when prompted for the file.</span></span>

## <a name="intune"></a><span data-ttu-id="c0d1e-147">Intune</span><span class="sxs-lookup"><span data-stu-id="c0d1e-147">Intune</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="c0d1e-148">系统扩展策略</span><span class="sxs-lookup"><span data-stu-id="c0d1e-148">System Extensions Policy</span></span>

<span data-ttu-id="c0d1e-149">批准系统扩展：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-149">To approve the system extensions:</span></span>

1. <span data-ttu-id="c0d1e-150">在 Intune 中，打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-150">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="c0d1e-151">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-151">Select **Manage** > **Profiles** > **Create Profile**.</span></span>
2. <span data-ttu-id="c0d1e-152">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-152">Choose a name for the profile.</span></span> <span data-ttu-id="c0d1e-153">将 **Platform=macOS** 更改为 **Profile type=Extensions**。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-153">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="c0d1e-154">选择 **创建**。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-154">Select **Create**.</span></span>
3. <span data-ttu-id="c0d1e-155">在 `Basics` 选项卡中，为此新配置文件命名。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-155">In the `Basics` tab, give a name to this new profile.</span></span>
4. <span data-ttu-id="c0d1e-156">在 `Configuration settings` 选项卡中，在 部分中添加以下 `Allowed system extensions` 条目：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-156">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="c0d1e-157">捆绑包标识符</span><span class="sxs-lookup"><span data-stu-id="c0d1e-157">Bundle identifier</span></span>         | <span data-ttu-id="c0d1e-158">团队标识符</span><span class="sxs-lookup"><span data-stu-id="c0d1e-158">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="c0d1e-159">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="c0d1e-159">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="c0d1e-160">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="c0d1e-160">UBF8T346G9</span></span>
    <span data-ttu-id="c0d1e-161">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="c0d1e-161">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="c0d1e-162">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="c0d1e-162">UBF8T346G9</span></span>

    ![系统配置文件屏幕截图](images/mac-system-extension-intune2.png)

5. <span data-ttu-id="c0d1e-164">在 `Assignments` 选项卡中，将此配置文件分配给"所有用户 **&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-164">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="c0d1e-165">查看并创建此配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-165">Review and create this configuration profile.</span></span>

### <a name="create-and-deploy-the-custom-configuration-profile"></a><span data-ttu-id="c0d1e-166">创建和部署自定义配置文件</span><span class="sxs-lookup"><span data-stu-id="c0d1e-166">Create and deploy the Custom Configuration Profile</span></span>

<span data-ttu-id="c0d1e-167">以下配置文件启用网络扩展，并授予对终结点安全系统扩展的完全磁盘访问权限。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-167">The following configuration profile enables the network extension and grants Full Disk Access to the Endpoint Security system extension.</span></span> 

<span data-ttu-id="c0d1e-168">将以下内容保存到名为 **sysext.xml：**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-168">Save the following content to a file named **sysext.xml**:</span></span>

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

<span data-ttu-id="c0d1e-169">验证上述文件是否复制正确。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-169">Verify that the above file was copied correctly.</span></span> <span data-ttu-id="c0d1e-170">从终端运行以下命令并验证它是否输出 `OK` ：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-170">From the Terminal, run the following command and verify that it outputs `OK`:</span></span>

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

<span data-ttu-id="c0d1e-171">部署此自定义配置文件：</span><span class="sxs-lookup"><span data-stu-id="c0d1e-171">To deploy this custom configuration profile:</span></span>

1.  <span data-ttu-id="c0d1e-172">在 Intune 中，打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-172">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="c0d1e-173">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-173">Select **Manage** > **Profiles** > **Create profile**.</span></span>
2. <span data-ttu-id="c0d1e-174">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-174">Choose a name for the profile.</span></span> <span data-ttu-id="c0d1e-175">Change **Platform=macOS** and **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="c0d1e-175">Change **Platform=macOS** and **Profile type=Custom**.</span></span> <span data-ttu-id="c0d1e-176">选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-176">Select **Configure**.</span></span>
3.  <span data-ttu-id="c0d1e-177">打开配置文件， **然后上传** sysext.xml。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-177">Open the configuration profile and upload **sysext.xml**.</span></span> <span data-ttu-id="c0d1e-178">此文件是在上一步骤中创建的。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-178">This file was created in the preceding step.</span></span>
4.  <span data-ttu-id="c0d1e-179">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-179">Select **OK**.</span></span>

    ![Intune 中的系统扩展屏幕截图](images/mac-system-extension-intune.png)

5. <span data-ttu-id="c0d1e-181">在 `Assignments` 选项卡中，将此配置文件分配给"所有用户 **&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="c0d1e-181">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="c0d1e-182">查看并创建此配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0d1e-182">Review and create this configuration profile.</span></span>
