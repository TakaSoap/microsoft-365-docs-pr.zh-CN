---
title: 在 Jamf Pro中设置 macOS 策略的Microsoft Defender for Endpoint
description: 了解如何在 Jamf Pro中设置 macOS 策略上的Microsoft Defender for Endpoint
keywords: policies， microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8d248eef175da6de3e329b4ec9b75b1111c668a6
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824709"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>在 Jamf Pro中设置 macOS 策略的Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Mac 上的 Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

本页将指导你完成在 Jamf Pro 中设置 macOS 策略所需的步骤。

需要执行以下步骤：

1. [获取Microsoft Defender for Endpoint载入包](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)
2. [使用载入包在 Jamf Pro中创建配置文件](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)
3. [配置Microsoft Defender for Endpoint设置](#step-3-configure-microsoft-defender-for-endpoint-settings)
4. [配置Microsoft Defender for Endpoint通知设置](#step-4-configure-notifications-settings)
5. [配置 Microsoft AutoUpdate (MAU) ](#step-5-configure-microsoft-autoupdate-mau)
6. [授予对Microsoft Defender for Endpoint的完全磁盘访问权限](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)
7. [批准Microsoft Defender for Endpoint的内核扩展](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)
8. [批准Microsoft Defender for Endpoint的系统扩展](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)
9. [配置网络扩展](#step-9-configure-network-extension)
10. [在 macOS 上使用Microsoft Defender for Endpoint计划扫描](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)
11. [在 macOS 上部署Microsoft Defender for Endpoint](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)

## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>步骤 1：获取Microsoft Defender for Endpoint载入包

1. 在 [Microsoft 365 Defender](https://security.microsoft.com)中，导航到 **>载入设置 >终结点**。

2. 选择 macOS 作为操作系统，选择移动设备管理/Microsoft Intune作为部署方法。

   :::image type="content" source="images/onboarding-macos.png" alt-text="Microsoft Defender 安全中心的设置页" lightbox="images/onboarding-macos.png":::

3. 选择 **“下载载入”包** (WindowsDefenderATPOnboardingPackage.zip) 。

4. 提取 `WindowsDefenderATPOnboardingPackage.zip`。

5. 将文件复制到首选位置。 例如，`C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。

## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>步骤 2：使用载入包在 Jamf Pro中创建配置文件

1. 找到上一部分中的文件 `WindowsDefenderATPOnboarding.plist` 。

   :::image type="content" source="images/plist-onboarding-file.png" alt-text="Windows Defender ATP 载入文件" lightbox="images/plist-onboarding-file.png":::

2. 登录到 Jamf Pro，导航到 **ComputersConfiguration** >  配置文件，然后选择 **“新建**”。

   :::image type="content" source="images/jamf-pro-configure-profile.png" alt-text="在其中创建新 Jamf Pro仪表板的页面" lightbox="images/jamf-pro-configure-profile.png":::

3. 输入以下详细信息：

   常规：

   - 名称：适用于 macOS 的 MDE 载入
   - 说明：适用于 macOS 的 MDE EDR载入
   - 类别：无
   - 分发方法：自动安装
   - 级别：计算机级别

4.  导航到“**应用程序&自定义设置**”页，然后选择 **“Upload** >  **Add**”。

   :::image type="content" source="images/jamfpro-mac-profile.png" alt-text="配置应用和自定义设置" lightbox="images/jamfpro-mac-profile.png":::

5. 选择 **Upload文件 (PLIST 文件)** 然后在 **首选项域** 中输入： `com.microsoft.wdav.atp`

   :::image type="content" source="images/jamfpro-plist-upload.png" alt-text="jamfpro plist 上传文件" lightbox="images/jamfpro-plist-upload.png":::

   :::image type="content" source="images/jamfpro-plist-file.png" alt-text="上传文件属性列表文件" lightbox="images/jamfpro-plist-file.png":::

6. 选择 **“打开** ”并选择载入文件。

   :::image type="content" source="images/jamfpro-plist-file-onboard.png" alt-text="载入文件" lightbox="images/jamfpro-plist-file-onboard.png":::

7. 选择“**上传**”。

   :::image type="content" source="images/jamfpro-upload-plist.png" alt-text="上传的 plist 文件" lightbox="images/jamfpro-upload-plist.png":::

8. 选择“ **作用域** ”选项卡。

   :::image type="content" source="images/jamfpro-scope-tab.png" alt-text="“作用域”选项卡" lightbox="images/jamfpro-scope-tab.png":::

9. 选择目标计算机。

   :::image type="content" source="images/jamfpro-target-computer.png" alt-text="目标计算机" lightbox="images/jamfpro-target-computer.png":::

   :::image type="content" source="images/jamfpro-targets.png" alt-text="目标" lightbox="images/jamfpro-targets.png":::

10. 选择“**保存**”。

   :::image type="content" source="images/jamfpro-deployment-target.png" alt-text="目标计算机的部署" lightbox="images/jamfpro-deployment-target.png":::

   :::image type="content" source="images/jamfpro-target-selected.png" alt-text="选择目标计算机" lightbox="images/jamfpro-target-selected.png":::

11. 选择“**完成**”。

    :::image type="content" source="images/jamfpro-target-group.png" alt-text="目标组的计算机" lightbox="images/jamfpro-target-group.png":::

    :::image type="content" source="images/jamfpro-configuration-policies.png" alt-text="配置文件列表" lightbox="images/jamfpro-configuration-policies.png":::

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>步骤 3：配置Microsoft Defender for Endpoint设置

可以使用 JAMF Pro GUI 编辑Microsoft Defender for Endpoint配置的各个设置，也可以通过在文本编辑器中创建配置 Plist 并将其上传到 JAMF Pro 来使用旧方法。

请注意，必须完全`com.microsoft.wdav`用作 **首选项域**，Microsoft Defender for Endpoint仅使用此名称并`com.microsoft.wdav.ext`加载其托管设置！

`com.microsoft.wdav.ext` (在极少数情况下，如果希望使用 GUI 方法，但还需要配置尚未添加到架构的设置，则可以使用该版本。) 

### <a name="gui-method"></a>GUI 方法

1. 从 [Defender 的 GitHub 存储库](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema)下载 schema.json 文件并将其保存到本地文件：

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. 在“计算机->配置文件”下创建新的配置文件，在“ **常规** ”选项卡上输入以下详细信息：

   :::image type="content" source="images/644e0f3af40c29e80ca1443535b2fe32.png" alt-text="新配置文件" lightbox="images/644e0f3af40c29e80ca1443535b2fe32.png":::

    - 名称：MDATP MDAV 配置设置
    - 描述：\<blank\>
    - 类别：无 (默认) 
    - 级别：计算机级别 (默认) 
    - 分发方法：自动安装 (默认) 

3. 向下滚动到“**应用程序&自定义设置**”选项卡，选择 **“外部应用程序**”，单击 **“添加**”并使用 **自定义架构** 作为源以用于首选项域。

   :::image type="content" source="images/4137189bc3204bb09eed3aabc41afd78.png" alt-text="添加自定义架构" lightbox="images/4137189bc3204bb09eed3aabc41afd78.png":::

4. 输入`com.microsoft.wdav`为首选项域，单击 **“添加架构****”并Upload** 步骤 1 上下载的 schema.json 文件。 单击 **“保存”**。

   :::image type="content" source="images/a6f9f556037c42fabcfdcb1b697244cf.png" alt-text="Upload架构" lightbox="images/a6f9f556037c42fabcfdcb1b697244cf.png":::

5. 可以在“**首选项域属性**”下查看下面所有受支持的Microsoft Defender for Endpoint配置设置。 单击 **“添加/删除属性** ”以选择要管理的设置，然后单击 **“确定** ”保存所做的更改。  (设置未选中内容将不包括在托管配置中，最终用户将能够在其计算机上配置这些设置。) 

   :::image type="content" source="images/817b3b760d11467abe9bdd519513f54f.png" alt-text="所选的托管设置" lightbox="images/817b3b760d11467abe9bdd519513f54f.png":::

6. 将设置的值更改为所需的值。 可以单击 **“详细信息** ”以获取特定设置的文档。  (可以单击 **Plist 预览** 来检查配置 plist 的外观。 单击 **窗体编辑器** 返回到视觉编辑器。) 

   :::image type="content" source="images/a14a79efd5c041bb8974cb5b12b3a9b6.png" alt-text="更改设置值的页面" lightbox="images/a14a79efd5c041bb8974cb5b12b3a9b6.png":::

7. 选择“ **作用域** ”选项卡。

   :::image type="content" source="images/9fc17529e5577eefd773c658ec576a7d.png" alt-text="配置文件范围" lightbox="images/9fc17529e5577eefd773c658ec576a7d.png":::

8. 选择 **Contoso 的计算机组**。

9. 选择 **“添加**”，然后选择 **“保存**”。

   :::image type="content" source="images/cf30438b5512ac89af1d11cbf35219a6.png" alt-text="可在其中添加配置设置的页面" lightbox="images/cf30438b5512ac89af1d11cbf35219a6.png":::

   :::image type="content" source="images/6f093e42856753a3955cab7ee14f12d9.png" alt-text="可在其中保存配置设置的页面" lightbox="images/6f093e42856753a3955cab7ee14f12d9.png":::

10. 选择“**完成**”。 你将看到新的 **配置文件**。

    :::image type="content" source="images/dd55405106da0dfc2f50f8d4525b01c8.png" alt-text="完成配置设置的页面" lightbox="images/dd55405106da0dfc2f50f8d4525b01c8.png":::

Microsoft Defender for Endpoint随时间推移添加新设置。 这些新设置将添加到架构中，新版本将发布到 Github。
若要进行更新，只需在“应用程序 **”&“自定义设置**”选项卡上下载更新的架构、编辑现有配置文件和 **编辑架构**。

### <a name="legacy-method"></a>旧方法

1. 使用以下Microsoft Defender for Endpoint配置设置：

    - enableRealTimeProtection
    - passiveMode

    > [!NOTE]
    > 默认情况下未打开，如果计划为 macOS 运行第三方 AV，请将其 `true`设置为。

    - 排除
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats

    > [!NOTE]
    > EICAR 位于示例中，如果要进行概念证明，请将其删除，尤其是在测试 EICAR 时。

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon

     有关信息，请参阅 [JAMF 完整配置文件的属性列表](mac-preferences.md#property-list-for-jamf-full-configuration-profile)。

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. 将文件另存为 `MDATP_MDAV_configuration_settings.plist`.

3. 在 Jamf Pro仪表板中，打开 **计算机** 及其 **配置文件**。 单击 **“新建** ”并切换到“ **常规** ”选项卡。

   :::image type="content" source="images/644e0f3af40c29e80ca1443535b2fe32.png" alt-text="显示新配置文件的页面" lightbox="images/644e0f3af40c29e80ca1443535b2fe32.png":::

4. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV 配置设置
    - 描述：\<blank\>
    - 类别：无 (默认) 
    - 分发方法：自动安装 (默认) 
    - 级别：计算机级别 (默认) 

    :::image type="content" source="images/3160906404bc5a2edf84d1d015894e3b.png" alt-text="MDATP MDAV 配置设置" lightbox="images/3160906404bc5a2edf84d1d015894e3b.png":::

5. 在 **应用程序&自定义设置** 选择 **“配置**”。

   :::image type="content" source="images/e1cc1e48ec9d5d688087b4d771e668d2.png" alt-text="应用程序和自定义设置" lightbox="images/e1cc1e48ec9d5d688087b4d771e668d2.png":::

6. 选择 **Upload文件 (PLIST 文件)**。

   :::image type="content" source="images/6f85269276b2278eca4bce84f935f87b.png" alt-text="配置设置 plist 文件" lightbox="images/6f85269276b2278eca4bce84f935f87b.png":::

7. 在 **首选项域中**，输入`com.microsoft.wdav`，然后选择 **Upload PLIST 文件**。

   :::image type="content" source="images/db15f147dd959e872a044184711d7d46.png" alt-text="配置设置首选项域" lightbox="images/db15f147dd959e872a044184711d7d46.png":::

8. 选择 **“选择文件**”。

    :::image type="content" source="images/526e978761fc571cca06907da7b01fd6.png" alt-text="选择 plist 文件的提示" lightbox="images/526e978761fc571cca06907da7b01fd6.png":::

9. 选择 **MDATP_MDAV_configuration_settings.plist**，然后选择 **“打开**”。

   :::image type="content" source="images/98acea3750113b8dbab334296e833003.png" alt-text="mdatpmdav 配置设置" lightbox="images/98acea3750113b8dbab334296e833003.png":::

10. 选择“**上传**”。

    :::image type="content" source="images/0adb21c13206861ba9b30a879ade93d3.png" alt-text="配置设置上传" lightbox="images/0adb21c13206861ba9b30a879ade93d3.png":::

    :::image type="content" source="images/f624de59b3cc86e3e2d32ae5de093e02.png" alt-text="上传与配置设置相关的映像的提示" lightbox="images/f624de59b3cc86e3e2d32ae5de093e02.png":::

    > [!NOTE]
    > 如果碰巧上传Intune文件，则会收到以下错误：
    >
    > :::image type="content" source="images/8e69f867664668796a3b2904896f0436.png" alt-text="上传与配置设置相关的 intune 文件的提示" lightbox="images/8e69f867664668796a3b2904896f0436.png":::

11. 选择“**保存**”。

    :::image type="content" source="images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png" alt-text="用于保存与配置设置相关的映像的选项" lightbox="images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png":::

12. 文件已上传。

    :::image type="content" source="images/33e2b2a1611fdddf6b5b79e54496e3bb.png" alt-text="与配置设置相关的上传文件" lightbox="images/33e2b2a1611fdddf6b5b79e54496e3bb.png":::

    :::image type="content" source="images/a422e57fe8d45689227e784443e51bd1.png" alt-text="“配置设置”页" lightbox="images/a422e57fe8d45689227e784443e51bd1.png":::

13. 选择“ **作用域** ”选项卡。

    :::image type="content" source="images/9fc17529e5577eefd773c658ec576a7d.png" alt-text="配置设置的范围" lightbox="images/9fc17529e5577eefd773c658ec576a7d.png":::

14. 选择 **Contoso 的计算机组**。

15. 选择 **“添加**”，然后选择 **“保存**”。

    :::image type="content" source="images/cf30438b5512ac89af1d11cbf35219a6.png" alt-text="配置设置 addsav" lightbox="images/cf30438b5512ac89af1d11cbf35219a6.png":::

    :::image type="content" source="images/6f093e42856753a3955cab7ee14f12d9.png" alt-text="配置设置的通知" lightbox="images/6f093e42856753a3955cab7ee14f12d9.png":::

16. 选择“**完成**”。 你将看到新的 **配置文件**。

    ![配置设置配置配置文件映像的图像。](images/dd55405106da0dfc2f50f8d4525b01c8.png)
    :::image type="content" source="images/dd55405106da0dfc2f50f8d4525b01c8.png" alt-text="配置文件的设置" lightbox="images/dd55405106da0dfc2f50f8d4525b01c8.png":::

## <a name="step-4-configure-notifications-settings"></a>步骤 4：配置通知设置

这些步骤适用于 macOS 10.15 (Catalina) 或更高版本。

1. 在 Jamf Pro 仪表板中，选择 **“计算机**”，然后选择 **“配置文件**”。

2. 单击 **“新建**”，并输入以下“ **选项**”详细信息：

    - Tab **General**：
        - **名称**：MDATP MDAV 通知设置
        - **说明**：macOS 10.15 (Catalina) 或更高版本
        - **类别**：无 *(默认)*
        - **分发方法**：自动安装 *(默认)*
        - **级别**：计算机级别 *(默认)*

        :::image type="content" source="images/c9820a5ff84aaf21635c04a23a97ca93.png" alt-text="新的 macOS 配置文件页" lightbox="images/c9820a5ff84aaf21635c04a23a97ca93.png":::

    - 选项卡 **通知**，单击 **“添加**”，然后输入以下值：
        - **捆绑 ID**： `com.microsoft.wdav.tray`
        - **严重警报**：单击 **“禁用”**
        - **通知**：单击 **“启用”**
        - **横幅警报类型**：选择 **“包含** ”和 **“临时** *(默认)*
        - **锁屏上的通知**：单击 **“隐藏”**
        - **通知中心中的通知**：单击 **“显示”**
        - **锁屏提醒应用图标**：单击 **“显示”**

        :::image type="content" source="images/7f9138053dbcbf928e5182ee7b295ebe.png" alt-text="配置设置 mdatpmdav 通知托盘" lightbox="images/7f9138053dbcbf928e5182ee7b295ebe.png":::

    - 选项卡 **通知**，再单击 **“添加** 一次”，向下滚动到 **“新建通知”设置**
        - **捆绑 ID**： `com.microsoft.autoupdate.fba`
        - 将其余设置配置为与上面相同的值

        :::image type="content" source="images/4bac6ce277aedfb4a674f2d9fcb2599a.png" alt-text="配置设置 mdatpmdav notifications mau" lightbox="images/4bac6ce277aedfb4a674f2d9fcb2599a.png":::

        请注意，现在你有两个包含通知配置的“表”，一个用于 **捆绑 ID：com.microsoft.wdav.tray**，另一个用于 **捆绑 ID：com.microsoft.autoupdate.fba**。 虽然可以根据要求配置警报设置，但捆绑 ID 必须与之前所述完全相同，并且“**包含**”**开关必须为****通知** 打开。

3. 选择“ **作用域** ”选项卡，然后选择 **“添加**”。

   :::image type="content" source="images/441aa2ecd36abadcdd8aed03556080b5.png" alt-text="可在其中添加配置设置值的页面" lightbox="images/441aa2ecd36abadcdd8aed03556080b5.png":::

4. 选择 **Contoso 的计算机组**。

5. 选择 **“添加**”，然后选择 **“保存**”。

   :::image type="content" source="images/09a275e321268e5e3ac0c0865d3e2db5.png" alt-text="可在其中保存配置设置 contoso 计算机组值的页面" lightbox="images/09a275e321268e5e3ac0c0865d3e2db5.png":::

   :::image type="content" source="images/4d2d1d4ee13d3f840f425924c3df0d51.png" alt-text="显示配置设置的完成通知的页面" lightbox="images/4d2d1d4ee13d3f840f425924c3df0d51.png":::

6. 选择“**完成**”。 你将看到新的 **配置文件**。

   :::image type="content" source="images/633ad26b8bf24ec683c98b2feb884bdf.png" alt-text="已完成的配置设置" lightbox="images/633ad26b8bf24ec683c98b2feb884bdf.png":::

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>步骤 5：配置 Microsoft AutoUpdate (MAU) 

1. 使用以下Microsoft Defender for Endpoint配置设置：

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. 另存为 `MDATP_MDAV_MAU_settings.plist`.

3. 在 Jamf Pro 仪表板中，选择 **“常规**”。

   :::image type="content" source="images/eaba2a23dd34f73bf59e826217ba6f15.png" alt-text="配置设置" lightbox="images/eaba2a23dd34f73bf59e826217ba6f15.png":::

4. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV MAU 设置
    - 说明：适用于 macOS 的 MDATP 的 Microsoft AutoUpdate 设置
    - 类别：无 (默认) 
    - 分发方法：自动安装 (默认) 
    - 级别：计算机级别 (默认) 

5. 在 **应用程序&自定义设置** 选择 **“配置**”。

   :::image type="content" source="images/1f72e9c15eaafcabf1504397e99be311.png" alt-text="配置设置应用程序和自定义设置" lightbox="images/1f72e9c15eaafcabf1504397e99be311.png":::

6. 选择 **Upload文件 (PLIST 文件)**。

7. 在 **首选项域** 中输入：`com.microsoft.autoupdate2`然后选择 **Upload PLIST 文件**。

   :::image type="content" source="images/1213872db5833aa8be535da57653219f.png" alt-text="配置设置首选项域" lightbox="images/1213872db5833aa8be535da57653219f.png":::
    

8. 选择 **“选择文件**”。

   :::image type="content" source="images/335aff58950ce62d1dabc289ecdce9ed.png" alt-text="有关配置设置选择文件的提示" lightbox="images/335aff58950ce62d1dabc289ecdce9ed.png":::

9. 选择 **MDATP_MDAV_MAU_settings.plist**。

   :::image type="content" source="images/a26bd4967cd54bb113a2c8d32894c3de.png" alt-text="mdatpmdavmau 设置" lightbox="images/a26bd4967cd54bb113a2c8d32894c3de.png":::

10. 选择“**上传**”。
    :::image type="content" source="images/4239ca0528efb0734e4ca0b490bfb22d.png" alt-text="有关配置设置的文件的上传" lightbox="images/4239ca0528efb0734e4ca0b490bfb22d.png":::

    :::image type="content" source="images/4ec20e72c8aed9a4c16912e01692436a.png" alt-text="显示有关配置设置的文件的上传选项的页面" lightbox="images/4ec20e72c8aed9a4c16912e01692436a.png":::

11. 选择“**保存**”。

    :::image type="content" source="images/253274b33e74f3f5b8d475cf8692ce4e.png" alt-text="显示有关配置设置的文件的保存选项的页面" lightbox="images/253274b33e74f3f5b8d475cf8692ce4e.png":::

12. 选择“ **作用域** ”选项卡。

    :::image type="content" source="images/10ab98358b2d602f3f67618735fa82fb.png" alt-text="配置设置的“范围”选项卡" lightbox="images/10ab98358b2d602f3f67618735fa82fb.png":::

13. 选择“**添加**”。

    :::image type="content" source="images/56e6f6259b9ce3c1706ed8d666ae4947.png" alt-text="添加部署目标的选项" lightbox="images/56e6f6259b9ce3c1706ed8d666ae4947.png":::

    :::image type="content" source="images/38c67ee1905c4747c3b26c8eba57726b.png" alt-text="在其中向配置设置添加更多值的页面" lightbox="images/38c67ee1905c4747c3b26c8eba57726b.png":::

    :::image type="content" source="images/321ba245f14743c1d5d51c15e99deecc.png" alt-text="可在其中向配置设置添加更多值的页面" lightbox="images/321ba245f14743c1d5d51c15e99deecc.png":::

14. 选择“**完成**”。

    :::image type="content" source="images/ba44cdb77e4781aa8b940fb83e3c21f7.png" alt-text="有关配置设置的完成通知" lightbox="images/ba44cdb77e4781aa8b940fb83e3c21f7.png":::

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>步骤 6：授予对Microsoft Defender for Endpoint的完全磁盘访问权限

1. 在 Jamf Pro 仪表板中，选择 **“配置文件**”。

   :::image type="content" source="images/264493cd01e62c7085659d6fdc26dc91.png" alt-text="要为其配置设置的配置文件" lightbox="images/264493cd01e62c7085659d6fdc26dc91.png":::

2. 选择 **+新建**。

3. 输入以下详细信息：

    **常规**
    - 名称：MDATP MDAV - 授予对EDR和 AV 的完全磁盘访问权限
    - 说明：在 macOS Catalina 或更高版本上，新的隐私首选项策略控制
    - 类别：无
    - 分发方法：自动安装
    - 级别：计算机级别

    :::image type="content" source="images/ba3d40399e1a6d09214ecbb2b341923f.png" alt-text="一般情况下的配置设置" lightbox="images/ba3d40399e1a6d09214ecbb2b341923f.png":::
    

4. 在 **“配置隐私首选项策略控制** ”中，选择 **“配置**”。

   :::image type="content" source="images/715ae7ec8d6a262c489f94d14e1e51bb.png" alt-text="配置隐私策略控制" lightbox="images/715ae7ec8d6a262c489f94d14e1e51bb.png":::

5. 在 **隐私首选项策略控制** 中，输入以下详细信息：

    - 标识符： `com.microsoft.wdav`
    - 标识符类型：捆绑 ID
    - 代码要求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

    :::image type="content" source="images/22cb439de958101c0a12f3038f905b27.png" alt-text="配置设置隐私首选项策略控制详细信息" lightbox="images/22cb439de958101c0a12f3038f905b27.png":::

6. 选择“+ 添加”。

   :::image type="content" source="images/bd93e78b74c2660a0541af4690dd9485.png" alt-text="配置设置添加系统策略所有文件选项" lightbox="images/bd93e78b74c2660a0541af4690dd9485.png":::

    - 在应用或服务下：设置为 **SystemPolicyAllFiles**

    - 在“访问”下：设置为 **“允许**”

7. 选择 **“保存** (而不是右下角的保存) 。

   :::image type="content" source="images/6de50b4a897408ddc6ded56a09c09fe2.png" alt-text="配置设置的保存操作" lightbox="images/6de50b4a897408ddc6ded56a09c09fe2.png":::

8. `+`单击 **应用访问** 旁边的符号以添加新条目。

   :::image type="content" source="images/tcc-add-entry.png" alt-text="与配置设置相关的保存操作" lightbox="images/tcc-add-entry.png":::

9. 输入以下详细信息：

    - 标识符： `com.microsoft.wdav.epsext`
    - 标识符类型：捆绑 ID
    - 代码要求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. 选择“+ 添加”。

    :::image type="content" source="images/tcc-epsext-entry.png" alt-text="配置设置 tcc epsext 条目" lightbox="images/tcc-epsext-entry.png":::

    - 在应用或服务下：设置为 **SystemPolicyAllFiles**

    - 在“访问”下：设置为 **“允许**”

11. 选择 **“保存** (而不是右下角的保存) 。

    :::image type="content" source="images/tcc-epsext-entry2.png" alt-text="配置设置 tcc epsext 的另一个实例" lightbox="images/tcc-epsext-entry2.png":::

12. 选择“ **作用域** ”选项卡。

    :::image type="content" source="images/2c49b16cd112729b3719724f581e6882.png" alt-text="描述配置设置的范围的页面" lightbox="images/2c49b16cd112729b3719724f581e6882.png":::

13. 选择“+ 添加”。

    :::image type="content" source="images/57cef926d1b9260fb74a5f460cee887a.png" alt-text="描述配置设置的页面" lightbox="images/57cef926d1b9260fb74a5f460cee887a.png":::

14. 选择“**组名称**”下的 **“计算机组**>>选择 **Contoso 的 MachineGroup**。

    :::image type="content" source="images/368d35b3d6179af92ffdbfd93b226b69.png" alt-text="配置设置 contoso 计算机组" lightbox="images/368d35b3d6179af92ffdbfd93b226b69.png":::

15. 选择“**添加**”。

16. 选择“**保存**”。

17. 选择“**完成**”。

    :::image type="content" source="images/809cef630281b64b8f07f20913b0039b.png" alt-text="配置设置 contoso machine-group" lightbox="images/809cef630281b64b8f07f20913b0039b.png":::

    :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="配置设置图示" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

或者，可以下载 [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) 并将其上传到 JAMF 配置文件，如[使用 Jamf Pro|部署自定义配置文件中所述方法 2：将配置文件Upload到 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>步骤 7：批准Microsoft Defender for Endpoint的内核扩展

> [!CAUTION]
> Apple 硅 (M1) 设备不支持 KEXT。 在这些设备上安装包含 KEXT 策略的配置文件将失败。

1. 在 **配置文件中**，选择 **“+ 新建**”。

   :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="自动生成社交媒体文章说明" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

2. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV 内核扩展
    - 说明：MDATP 内核扩展 (kext) 
    - 类别：无
    - 分发方法：自动安装
    - 级别：计算机级别

    :::image type="content" source="images/24e290f5fc309932cf41f3a280d22c14.png" alt-text="配置设置 mdatpmdav 内核" lightbox="images/24e290f5fc309932cf41f3a280d22c14.png":::

3. 在 **“配置已批准的内核扩展”中** ，选择 **“配置**”。

   :::image type="content" source="images/30be88b63abc5e8dde11b73f1b1ade6a.png" alt-text="显示已批准的内核扩展的配置设置的页面" lightbox="images/30be88b63abc5e8dde11b73f1b1ade6a.png":::

4. 在 **“已批准的内核扩展”** 中，输入以下详细信息：

    - 显示名称：Microsoft Corp。
    - 团队 ID：UBF8T346G9

    :::image type="content" source="images/39cf120d3ac3652292d8d1b6d057bd60.png" alt-text="“已批准的内核扩展”窗格" lightbox="images/39cf120d3ac3652292d8d1b6d057bd60.png":::

5. 选择“ **作用域** ”选项卡。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="配置的“范围”选项卡" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

6. 选择“+ 添加”。

7. 选择“**组名称**”下的 **“计算机组**>>选择 **Contoso 的计算机组**。

8. 选择“+ 添加”。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="为配置设置定义其他值的页面" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

9. 选择“**保存**”。

   :::image type="content" source="images/0add8019b85a453b47fa5c402c72761b.png" alt-text="MDATP MDAV 内核扩展" lightbox="images/0add8019b85a453b47fa5c402c72761b.png":::

10. 选择“**完成**”。

    :::image type="content" source="images/1c9bd3f68db20b80193dac18f33c22d0.png" alt-text="“配置文件详细信息”页" lightbox="images/1c9bd3f68db20b80193dac18f33c22d0.png":::

或者，可以下载 [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) 并将其上传到 JAMF 配置文件，如[使用 Jamf Pro|部署自定义配置文件中所述方法 2：将配置文件Upload到 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>步骤 8：批准Microsoft Defender for Endpoint的系统扩展

1. 在 **配置文件中**，选择 **“+ 新建**”。

   :::image type="content" source="images/6c8b406ee224335a8c65d06953dc756e.png" alt-text="自动生成的社交媒体帖子的说明" lightbox="images/6c8b406ee224335a8c65d06953dc756e.png":::

2. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV 系统扩展
    - 说明：MDATP 系统扩展
    - 类别：无
    - 分发方法：自动安装
    - 级别：计算机级别

    :::image type="content" source="images/sysext-new-profile.png" alt-text="配置设置 sysext 新配置文件" lightbox="images/sysext-new-profile.png":::

3. 在 **系统扩展中** 选择 **“配置**”。

   :::image type="content" source="images/sysext-configure.png" alt-text="包含系统扩展的“配置”选项的窗格" lightbox="images/sysext-configure.png":::

4. 在 **系统扩展中** 输入以下详细信息：

   - 显示名称：Microsoft Corp. 系统扩展
   - 系统扩展类型：允许的系统扩展
   - 团队标识符：UBF8T346G9
   - 允许的系统扩展：
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    :::image type="content" source="images/sysext-configure2.png" alt-text="MDATP MDAV 系统扩展窗格" lightbox="images/sysext-configure2.png":::

5. 选择“ **作用域** ”选项卡。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="“目标计算机”选择窗格" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

6. 选择“+ 添加”。

7. 选择“**组名称**”下的 **“计算机组**>>选择 **Contoso 的计算机组**。

8. 选择“+ 添加”。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="“新建 macOS 配置文件”窗格" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

9. 选择“**保存**”。

   :::image type="content" source="images/sysext-scope.png" alt-text="显示有关 MDATP MDAV 系统扩展的选项" lightbox="images/sysext-scope.png":::

10. 选择“**完成**”。

    :::image type="content" source="images/sysext-final.png" alt-text="配置设置 sysext - final" lightbox="images/sysext-final.png":::

## <a name="step-9-configure-network-extension"></a>步骤 9：配置网络扩展

作为终结点检测和响应功能的一部分，macOS 上的Microsoft Defender for Endpoint会检查套接字流量，并将此信息报告给Microsoft 365 Defender门户。 以下策略允许网络扩展执行此功能。

这些步骤适用于 macOS 10.15 (Catalina) 或更高版本。

1. 在 Jamf Pro 仪表板中，选择 **“计算机**”，然后选择 **“配置文件**”。

2. 单击 **“新建**”，并输入以下“ **选项**”详细信息：

    - Tab **General**：
        - **名称**：Microsoft Defender 网络扩展
        - **说明**：macOS 10.15 (Catalina) 或更高版本
        - **类别**：无 *(默认)*
        - **分发方法**：自动安装 *(默认)*
        - **级别**：计算机级别 *(默认)*

    - 选项卡 **内容筛选器**：
        - **筛选器名称**：Microsoft Defender 内容筛选器
        - **标识符**： `com.microsoft.wdav`
        - *未* 选择“保留 **服务地址**”、“**组织**”、“**用户名**”、“**密码**”、“**证书** 空白 (**包括**) 
        - **筛选器顺序**：检查器
        - **套接字筛选器**： `com.microsoft.wdav.netext`
        - **套接字筛选器指定要求**： `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - 将 **网络筛选器** 字段留空 (*未* 选择 **“包括**”) 

        请注意，如上所述 **，标识符**、 **套接字筛选器** 和 **套接字筛选器指定要求** 的确切值。

        :::image type="content" source="images/netext-create-profile.png" alt-text="mdatpmdav 配置设置" lightbox="images/netext-create-profile.png":::

3. 选择“ **作用域** ”选项卡。

   :::image type="content" source="images/0df36fc308ba569db204ee32db3fb40a.png" alt-text="“配置设置范围”选项卡" lightbox="images/0df36fc308ba569db204ee32db3fb40a.png":::

4. 选择“+ 添加”。

5. 选择“**组名称**”下的 **“计算机组**>>选择 **Contoso 的计算机组**。

6. 选择“+ 添加”。

   :::image type="content" source="images/0dde8a4c41110dbc398c485433a81359.png" alt-text="配置设置 adim" lightbox="images/0dde8a4c41110dbc398c485433a81359.png":::

7. 选择“**保存**”。

   :::image type="content" source="images/netext-scope.png" alt-text="“内容筛选器”窗格" lightbox="images/netext-scope.png":::

8. 选择“**完成**”。

   :::image type="content" source="images/netext-final.png" alt-text="配置设置 netext - final" lightbox="images/netext-final.png":::

或者，可以下载 [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) 并将其上传到 JAMF 配置文件，如[使用 Jamf Pro|部署自定义配置文件中所述方法 2：将配置文件Upload到 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>步骤 10：在 macOS 上使用Microsoft Defender for Endpoint计划扫描

使用 [macOS 上的Microsoft Defender for Endpoint按计划扫描的说明操作](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>步骤 11：在 macOS 上部署Microsoft Defender for Endpoint

1. 导航到保存 `wdav.pkg`的位置。

   :::image type="content" source="images/8dde76b5463047423f8637c86b05c29d.png" alt-text="文件资源管理器 wdav 包" lightbox="images/8dde76b5463047423f8637c86b05c29d.png":::

2. 将其重命名为 `wdav_MDM_Contoso_200329.pkg`.

   :::image type="content" source="images/fb2220fed3a530f4b3ef36f600da0c27.png" alt-text="文件资源管理器 1 wdavmdm 包" lightbox="images/fb2220fed3a530f4b3ef36f600da0c27.png":::

3. 打开 Jamf Pro仪表板。

   :::image type="content" source="images/990742cd9a15ca9fdd37c9f695d1b9f4.png" alt-text="jamfpro 的配置设置" lightbox="images/990742cd9a15ca9fdd37c9f695d1b9f4.png":::

4. 选择计算机，然后单击顶部的齿轮图标，然后选择 **“计算机管理**”。

   :::image type="content" source="images/b6d671b2f18b89d96c1c8e2ea1991242.png" alt-text="配置设置 - 计算机管理" lightbox="images/b6d671b2f18b89d96c1c8e2ea1991242.png":::

5. 在 **“包**”中，选择 **“+ 新建**”。
   :::image type="content" source="images/57aa4d21e2ccc65466bf284701d4e961.png" alt-text="自动生成的包的鸟描述" lightbox="images/57aa4d21e2ccc65466bf284701d4e961.png":::

6. 在新 **包** 中输入以下详细信息：

    **“常规”选项卡**
    - 显示名称：立即将其留空。 因为在选择 pkg 时会重置它。
    - 类别：无 (默认) 
    - 文件名：选择文件

    :::image type="content" source="images/21de3658bf58b1b767a17358a3f06341.png" alt-text="配置设置的“常规”选项卡" lightbox="images/21de3658bf58b1b767a17358a3f06341.png":::

    打开该文件并将其指向 `wdav.pkg` 或 `wdav_MDM_Contoso_200329.pkg`指向该文件。

    :::image type="content" source="images/1aa5aaa0a387f4e16ce55b66facc77d1.png" alt-text="显示自动生成的包的说明的计算机屏幕" lightbox="images/1aa5aaa0a387f4e16ce55b66facc77d1.png":::

7. 选择 **“打开”**。 将 **显示名称** 设置为 **Microsoft Defender 高级威胁防护和Microsoft Defender 防病毒**。

    **不需要清单文件** 。 Microsoft Defender for Endpoint不使用清单文件。

    **“选项”选项卡**：保留默认值。

    **限制选项卡**：保留默认值。

    :::image type="content" source="images/56dac54634d13b2d3948ab50e8d3ef21.png" alt-text="配置设置的限制选项卡" lightbox="images/56dac54634d13b2d3948ab50e8d3ef21.png":::

8. 选择“**保存**”。 包将上传到 Jamf Pro。

   :::image type="content" source="images/33f1ecdc7d4872555418bbc3efe4b7a3.png" alt-text="与配置设置相关的包的配置设置包上传过程" lightbox="images/33f1ecdc7d4872555418bbc3efe4b7a3.png":::

   可能需要几分钟时间才能将包用于部署。

   :::image type="content" source="images/1626d138e6309c6e87bfaab64f5ccf7b.png" alt-text="上传用于配置设置的包的实例" lightbox="images/1626d138e6309c6e87bfaab64f5ccf7b.png":::

9. 导航到“ **策略** ”页。

   :::image type="content" source="images/f878f8efa5ebc92d069f4b8f79f62c7f.png" alt-text="配置设置策略" lightbox="images/f878f8efa5ebc92d069f4b8f79f62c7f.png":::

10. 选择 **“+ 新建** ”以创建新策略。

    :::image type="content" source="images/847b70e54ed04787e415f5180414b310.png" alt-text="配置设置新策略" lightbox="images/847b70e54ed04787e415f5180414b310.png":::


11. 在 **“常规** ”中，输入以下详细信息：

    - 显示名称：MDATP 载入 Contoso 200329 v100.86.92 或更高版本

      :::image type="content" source="images/625ba6d19e8597f05e4907298a454d28.png" alt-text="配置设置 - 加入 MDATP" lightbox="images/625ba6d19e8597f05e4907298a454d28.png":::

12. 选择 **定期签入**。

    :::image type="content" source="images/68bdbc5754dfc80aa1a024dde0fce7b0.png" alt-text="配置设置的定期签入" lightbox="images/68bdbc5754dfc80aa1a024dde0fce7b0.png":::

13. 选择“**保存**”。

14. 选择 **包>配置**。

    :::image type="content" source="images/8fb4cc03721e1efb4a15867d5241ebfb.png" alt-text="用于配置包的选项" lightbox="images/8fb4cc03721e1efb4a15867d5241ebfb.png":::

15. 选择 **Microsoft Defender 高级威胁防护** 旁边的 **“添加**”按钮并Microsoft Defender 防病毒。

    :::image type="content" source="images/526b83fbdbb31265b3d0c1e5fbbdc33a.png" alt-text="向 MDATP MDA 添加更多设置的选项" lightbox="images/526b83fbdbb31265b3d0c1e5fbbdc33a.png":::

16. 选择“**保存**”。

    :::image type="content" source="images/9d6e5386e652e00715ff348af72671c6.png" alt-text="配置设置的保存选项" lightbox="images/9d6e5386e652e00715ff348af72671c6.png":::

17. 选择“ **作用域** ”选项卡。

    :::image type="content" source="images/8d80fe378a31143db9be0bacf7ddc5a3.png" alt-text="与配置设置相关的“作用域”选项卡" lightbox="images/8d80fe378a31143db9be0bacf7ddc5a3.png":::

18. 选择目标计算机。

    :::image type="content" source="images/6eda18a64a660fa149575454e54e7156.png" alt-text="添加计算机组的选项" lightbox="images/6eda18a64a660fa149575454e54e7156.png":::

    **Scope**

    选择“**添加**”。

    :::image type="content" source="images/1c08d097829863778d562c10c5f92b67.png" alt-text="配置设置 - ad1" lightbox="images/1c08d097829863778d562c10c5f92b67.png":::

    :::image type="content" source="images/216253cbfb6ae738b9f13496b9c799fd.png" alt-text="配置设置 - ad2" lightbox="images/216253cbfb6ae738b9f13496b9c799fd.png":::

    **自助服务**

    :::image type="content" source="images/c9f85bba3e96d627fe00fc5a8363b83a.png" alt-text="配置设置的自助服务选项卡" lightbox="images/c9f85bba3e96d627fe00fc5a8363b83a.png":::

19. 选择“**完成**”。

    :::image type="content" source="images/99679a7835b0d27d0a222bc3fdaf7f3b.png" alt-text="具有用于完成它的选项的 Contoso 载入状态" lightbox="images/99679a7835b0d27d0a222bc3fdaf7f3b.png":::

    :::image type="content" source="images/632aaab79ae18d0d2b8e0c16b6ba39e2.png" alt-text="“策略”页" lightbox="images/632aaab79ae18d0d2b8e0c16b6ba39e2.png":::
