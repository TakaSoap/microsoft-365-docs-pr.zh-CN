---
title: 在 Jamf 中设置 macOS 上的 Microsoft Defender for Endpoint Pro
description: 了解如何在 Jamf Pro macOS 策略上设置 Microsoft Defender for Endpoint
keywords: 策略， microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ae3745840d8160aa896accf97540dc79194326d3
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941908"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>在 Jamf 中设置 macOS 上的 Microsoft Defender for Endpoint Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Mac 上的 Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

此页面将指导你完成在 Jamf 中设置 macOS 策略所需的Pro。

需要执行以下步骤：

1. [获取适用于终结点的 Microsoft Defender 载入程序包](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)
2. [使用载入包在 Jamf Pro创建配置文件](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)
3. [为终结点设置配置 Microsoft Defender](#step-3-configure-microsoft-defender-for-endpoint-settings)
4. [为终结点通知设置配置 Microsoft Defender](#step-4-configure-notifications-settings)
5. [配置 Microsoft AutoUpdate (MAU) ](#step-5-configure-microsoft-autoupdate-mau)
6. [授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)
7. [批准适用于终结点的 Microsoft Defender 内核扩展](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)
8. [批准适用于终结点的 Microsoft Defender 的系统扩展](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)
9. [配置网络扩展](#step-9-configure-network-extension)
10. [在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)
11. [在 macOS 上部署 Microsoft Defender for Endpoint](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)

## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>步骤 1：获取适用于终结点的 Microsoft Defender 载入程序包

1. 在 [Microsoft 365 Defender](https://security.microsoft.com)中，导航到 **设置 >载入"。**

2. 选择 macOS 作为操作系统，选择移动设备管理/Microsoft Intune作为部署方法。

    ![图像Microsoft Defender 安全中心。](images/onboarding-macos.png)

3. 选择 **下载载入程序包** (WindowsDefenderATPOnboardingPackage.zip) 。

4. 提取 `WindowsDefenderATPOnboardingPackage.zip` 。

5. 将文件复制到首选位置。 例如，`C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。

## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>步骤 2：使用载入包在 Jamf Pro创建配置文件

1. 找到上 `WindowsDefenderATPOnboarding.plist` 一部分中的文件。

   ![WindowsDefenderATPOnboarding 文件的图像。](images/plist-onboarding-file.png)

2. Sign in to Jamf Pro， navigate to **Computers**  >  **Configuration Profiles**， and select **New**.

    ![创建新 Jamf 仪表板Pro的图像。](images/jamf-pro-configure-profile.png)

3. 输入以下详细信息：

   常规：

   - 名称：macOS 的 MDATP 载入
   - 说明：mDATP EDR macOS 的载入
   - 类别：无
   - 分发方法：自动安装
   - 级别：计算机级别

4.  导航到"**自定义&应用程序设置，** 然后选择 **"Upload**  >  **添加"。**

    ![配置应用和自定义设置的图像。](images/jamfpro-mac-profile.png)

5. Select **Upload File (PLIST file)** then in Preference **Domain** enter： `com.microsoft.wdav.atp` .

    ![jamfpro plist 上载文件的图像。](images/jamfpro-plist-upload.png)

    ![上载文件属性列表文件的图像。](images/jamfpro-plist-file.png)

6. 选择 **"** 打开"并选择载入文件。

    ![载入文件的图像。](images/jamfpro-plist-file-onboard.png)

7. 选择 **"Upload"。**

    ![上传 plist 文件的图像。](images/jamfpro-upload-plist.png)

8. 选择" **范围"** 选项卡。

    ![范围选项卡的图像。](images/jamfpro-scope-tab.png)

9. 选择目标计算机。

    ![目标计算机的图像。](images/jamfpro-target-computer.png)

    ![目标的图像。](images/jamfpro-targets.png)

10. 选择“**保存**”。

    ![部署目标计算机的图像。](images/jamfpro-deployment-target.png)

    ![选择的目标计算机的图像。](images/jamfpro-target-selected.png)

11. 选择“**完成**”。

    ![目标组计算机的图像。](images/jamfpro-target-group.png)

    ![配置文件列表。](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>步骤 3：为终结点设置配置 Microsoft Defender

可以使用 JAMF Pro GUI 编辑 Microsoft Defender for Endpoint 配置的个人设置，或使用旧方法，方法是在文本编辑器中创建配置 Plist，并将其上载到 JAMF Pro。

请注意，你必须使用精确 `com.microsoft.wdav` 作为 **首选项域**，Microsoft Defender for Endpoint 仅使用此名称并 `com.microsoft.wdav.ext` 加载其托管设置！

 (当您更喜欢使用 GUI 方法，但还需要配置尚未添加到架构的设置时，版本可能在极少数情况下 `com.microsoft.wdav.ext` 使用。) 

### <a name="gui-method"></a>GUI 方法

1. 从 Defender 的 GitHub[下载](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema)schema.json 文件，并将其保存到本地文件：

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. 在"计算机 ->配置文件"下创建新的配置文件，在"常规"选项卡上输入 **以下** 详细信息：

    ![新配置文件。](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - 名称：MDATP MDAV 配置设置
    - 说明：\<blank\>
    - 类别：默认 (无) 
    - 级别：计算机级别 (默认) 
    - 分发方法：使用默认 (自动) 

3. 向下滚动到"应用程序&自定义设置"选项卡，选择 **"外部** 应用程序"，单击 **"** 添加"，然后使用"自定义架构作为源"以用于首选项域。

    ![添加自定义架构。](images/4137189bc3204bb09eed3aabc41afd78.png)

4. 输入 `com.microsoft.wdav` 作为首选项域，单击添加架构Upload步骤1 上下载的 schema.json 文件。 单击“保存”。

    ![Upload架构。](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. 可以在下面的首选项域属性下看到所有受支持的 Microsoft Defender for Endpoint **配置设置**。 单击 **"添加/删除** 属性"以选择要管理的设置，然后单击 **"确定"** 保存更改。  (设置未选择将不包含在托管配置中，最终用户将能够配置其计算机中的这些设置。) 

    ![选择托管设置。](images/817b3b760d11467abe9bdd519513f54f.png)

6. 将设置的值更改为所需值。 可以单击 **"详细信息"** 获取特定设置的文档。  (可以单击 **"Plist 预览** "检查 plist 的配置外观。 单击 **"表单编辑器** "返回到可视编辑器。) 

    ![更改设置值。](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. 选择" **范围"** 选项卡。

    ![配置文件作用域。](images/9fc17529e5577eefd773c658ec576a7d.png)

8. 选择 **Contoso 的机器组**。

9. 选择 **"添加"，** 然后选择"**保存"。**

    ![配置设置 - 添加。](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置设置 - 保存。](images/6f093e42856753a3955cab7ee14f12d9.png)

10. 选择“**完成**”。 你将看到新的 **配置配置文件**。

    ![配置设置 - 已完成。](images/dd55405106da0dfc2f50f8d4525b01c8.png)

Microsoft Defender for Endpoint 会随着时间的推移添加新设置。 这些新设置将添加到架构中，并且新版本将发布到 Github。
只需下载更新的架构、编辑现有配置文件和编辑"自定义"选项卡上的"应用程序&**编辑** 设置架构。

### <a name="legacy-method"></a>旧方法

1. 使用以下 Microsoft Defender for Endpoint 配置设置：

    - enableRealTimeProtection
    - passiveMode

    > [!NOTE]
    > 默认情况下未打开，如果计划运行适用于 macOS 的第三方 AV，请将其设置为 `true` 。

    - 排除项
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats

    > [!NOTE]
    > EICAR 位于示例中，如果你要通过概念证明，请删除它，尤其是在你测试 EICAR 时。

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - 标记
    - hideStatusMenuIcon

     有关信息，请参阅 [JAMF 完整配置文件 的属性列表](mac-preferences.md#property-list-for-jamf-full-configuration-profile)。

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

2. 将文件另存为 `MDATP_MDAV_configuration_settings.plist` 。

3. In the Jamf Pro dashboard， open **Computers**， and there **Configuration Profiles**. 单击**新建 (* 并切换到 **常规** 选项卡。

    ![新配置文件。](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV 配置设置
    - 说明：\<blank\>
    - 类别：默认 (无) 
    - 分发方法：使用默认 (自动) 
    - 级别：计算机 (默认) 

    ![MDATP MDAV 配置设置的图像。](images/3160906404bc5a2edf84d1d015894e3b.png)

5. 在 **"应用程序&自定义设置** 选择"**配置"。**

    ![应用和自定义设置的图像。](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Select **Upload File (PLIST file)**.

    ![配置设置 plist 文件的图像。](images/6f85269276b2278eca4bce84f935f87b.png)

7. 在 **首选项域中，** 输入 `com.microsoft.wdav` ，然后选择Upload **PLIST 文件"**。

    ![配置设置首选项域的图像。](images/db15f147dd959e872a044184711d7d46.png)

8. 选择 **"选择文件"。**

    ![配置设置的图像选择文件。](images/526e978761fc571cca06907da7b01fd6.png)

9. 选择 **"MDATP_MDAV_configuration_settings.plist"，** 然后选择"打开 **"。**

    ![mdatpmdav 配置设置的图像。](images/98acea3750113b8dbab334296e833003.png)

10. 选择 **"Upload"。**

    ![配置设置上载的图像。](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![配置设置上载图像的图像。](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    > [!NOTE]
    > 如果你发生上载 Intune 文件的情况，你将看到以下错误：
    >
    >![配置设置 intune 文件上载的图像。](images/8e69f867664668796a3b2904896f0436.png)

11. 选择“**保存**”。

    ![配置设置的图像 保存映像。](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. 文件已上载。

    ![配置文件上载图像的图像。](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![已上载的配置设置文件的图像。](images/a422e57fe8d45689227e784443e51bd1.png)

13. 选择" **范围"** 选项卡。

    ![配置设置作用域的图像。](images/9fc17529e5577eefd773c658ec576a7d.png)

14. 选择 **Contoso 的机器组**。

15. 选择 **"添加"，** 然后选择"**保存"。**

    ![配置设置的图像 addsav。](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置设置保存添加的图像。](images/6f093e42856753a3955cab7ee14f12d9.png)

16. 选择“**完成**”。 你将看到新的 **配置配置文件**。

    ![配置设置配置文件映像的图像。](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a>步骤 4：配置通知设置

这些步骤适用于 macOS 10.15 (卡) 或更高版本。

1. 在 Jamf Pro仪表板中，选择 **"计算机**"，然后选择"**配置文件"。**

2. 单击 **"新建**"，然后为"选项"输入以下 **详细信息**：

    - 常规 **选项卡**：
        - **名称**：MDATP MDAV 通知设置
        - **说明**：macOS 10.15 (加泰罗尼亚语) 或更高版本
        - **类别**： *默认 (无)*
        - **分发方法**：使用默认 *(自动)*
        - **级别**：计算机级别 *(默认)*

        ![新 macOS 配置文件屏幕的图像。](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - Tab **Notifications**， click **Add**， and enter the following values：
        - **捆绑包 ID**： `com.microsoft.wdav.tray`
        - **严重警报：单击**" **禁用"**
        - **通知**：单击" **启用"**
        - **横幅警报类型**：选择 **"包含**"*和"临时 (默认)*
        - **锁屏界面上的通知：** 单击" **隐藏"**
        - **通知中心中的通知**：单击显示
        - **锁屏提醒应用图标**：单击 **显示**

        ![配置设置 mdatpmdav 通知托盘的图像。](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - 选项卡 **通知**，单击 **"再** 添加一次"，向下滚动到"新建通知 **设置**
        - **捆绑包 ID**： `com.microsoft.autoupdate2`
        - 将其余设置配置为与上述值相同的值

        ![配置设置 mdatpmdav 通知 mau 的图像。](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        请注意，现在你有两个包含通知配置的"表"，一个针对捆绑包 **ID：com.microsoft.wdav.tray，** 另一个针对捆绑包 **ID：com.microsoft.autoupdate2**。 尽管你可以根据你的要求配置警报设置，但是捆绑包的 ID 必须和之前描述的完全相同，并且 **Include** 开关必须为 **通知的打开**。

3. 选择"**范围"** 选项卡，然后选择"添加 **"。**

    ![配置设置范围添加的图像。](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. 选择 **Contoso 的机器组**。

5. 选择 **"添加"，** 然后选择"**保存"。**

    ![配置设置 contoso 计算机 grp 保存的图像。](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![配置设置添加保存的图像。](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. 选择“**完成**”。 你将看到新的 **配置配置文件**。

    ![配置设置完成 img 的图像。](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>步骤 5：配置 Microsoft AutoUpdate (MAU) 

1. 使用以下 Microsoft Defender for Endpoint 配置设置：

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

2. 将其另存为 `MDATP_MDAV_MAU_settings.plist` 。

3. 在 Jamf Pro仪表板中，选择"**常规"。**

    ![配置设置常规映像的图像。](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV MAU 设置
    - 说明：适用于 macOS 的 MDATP 的 Microsoft AutoUpdate 设置
    - 类别：默认 (无) 
    - 分发方法：使用默认 (自动) 
    - 级别：计算机 (默认) 

5. 在 **"应用程序&自定义设置** 选择"**配置"。**

    ![配置设置应用和自定义设置的图像。](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Select **Upload File (PLIST file)**.

    ![配置设置 plist 的图像。](images/1213872db5833aa8be535da57653219f.png)

7. 在 **"首选项域**"中输入 `com.microsoft.autoupdate2` ：，然后选择 **"Upload PLIST 文件"。**

    ![配置设置 pref 域的图像。](images/1213872db5833aa8be535da57653219f.png)

8. 选择 **"选择文件"。**

    ![配置设置 choosefile 的图像。](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. 选择 **"MDATP_MDAV_MAU_settings.plist"。**

    ![配置设置 mdatpmdavmau 设置的图像。](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. 选择 **"Upload"。**
    ![配置设置设置的图像。](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![配置设置设置的图像。](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. 选择“**保存**”。

    ![配置设置 saveimg 的图像。](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. 选择" **范围"** 选项卡。

     ![配置设置作用域tab的图像。](images/10ab98358b2d602f3f67618735fa82fb.png)

13. 选择“**添加**”。

    ![配置设置 addimg1 的图像。](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![配置设置 addimg2 的图像。](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![配置设置 addimg3 的图像。](images/321ba245f14743c1d5d51c15e99deecc.png)

14. 选择“**完成**”。

    ![配置设置 doneimage 的图像。](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>步骤 6：向 Microsoft Defender for Endpoint 授予完全磁盘访问权限

1. 在 Jamf Pro仪表板中，选择 **"配置文件"。**

    ![配置设置配置文件的图像。](images/264493cd01e62c7085659d6fdc26dc91.png)

2. 选择 **+ 新建**。

3. 输入以下详细信息：

    **常规**
    - 名称：MDATP MDAV - 授予对 EDR 和 AV 的完全磁盘访问权限
    - 说明：在 macOS 加泰罗尼亚语或更高版本上，新的隐私首选项策略控制
    - 类别：无
    - 分发方法：自动安装
    - 级别：计算机级别

    ![配置设置常规的图像。](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. 在 **"配置隐私首选项策略控制"中，选择**"**配置"。**

    ![配置隐私策略控制的图像。](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. 在 **"隐私首选项策略控制"中**，输入以下详细信息：

    - 标识符： `com.microsoft.wdav`
    - 标识符类型：捆绑包 ID
    - 代码要求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

    ![配置设置隐私首选项策略控制详细信息的图像。](images/22cb439de958101c0a12f3038f905b27.png)

6. 选择“+ 添加”。

    ![配置设置的图像添加系统策略所有文件。](images/bd93e78b74c2660a0541af4690dd9485.png)

    - 在"应用或服务：设置为 **SystemPolicyAllFiles" 下**

    - 在"访问"下：设置为 **"允许"**

7. 选择 **" ("，** 而不是右下角) 。

    ![配置设置的图像保存图像。](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. 单击 `+` "应用访问" **旁边的** 符号添加新条目。

    ![配置设置应用访问权限的图像。](images/tcc-add-entry.png)

9. 输入以下详细信息：

    - 标识符： `com.microsoft.wdav.epsext`
    - 标识符类型：捆绑包 ID
    - 代码要求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. 选择“+ 添加”。

    ![配置设置 tcc epsext 条目的图像。](images/tcc-epsext-entry.png)

    - 在"应用或服务：设置为 **SystemPolicyAllFiles" 下**

    - 在"访问"下：设置为 **"允许"**

11. 选择 **" ("，** 而不是右下角) 。

    ![配置设置 tcc epsext image2 的图像。](images/tcc-epsext-entry2.png)

12. 选择" **范围"** 选项卡。

    ![配置设置作用域的图像。](images/2c49b16cd112729b3719724f581e6882.png)

13. 选择“+ 添加”。

    ![配置设置 addimage 的图像。](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Select **Computer Groups** > under Group Name **>** select **Contoso's MachineGroup**.

    ![配置设置 contoso machinegrp 的图像。](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. 选择“**添加**”。

16. 选择“**保存**”。

17. 选择“**完成**”。

    ![配置设置 donimg 的图像。](images/809cef630281b64b8f07f20913b0039b.png)

    ![配置设置 donimg2 的图像。](images/6c8b406ee224335a8c65d06953dc756e.png)

或者，你可以下载[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)并将其上载到 JAMF 配置文件，如使用 Jamf 部署自定义[配置文件Pro|方法 2：Upload配置文件为 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>步骤 7：批准适用于终结点的 Microsoft Defender 内核扩展

> [!CAUTION]
> Apple 芯片 (M1) 设备不支持 KEXT。 在这些设备上安装包含 KEXT 策略的配置文件将失败。

1. 在"**配置文件"中**，选择 **"+ 新建"。**

    ![自动生成说明的社交媒体文章屏幕截图。](images/6c8b406ee224335a8c65d06953dc756e.png)

2. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV 内核扩展
    - 说明：kext (MDATP 内核) 
    - 类别：无
    - 分发方法：自动安装
    - 级别：计算机级别

    ![配置设置 mdatpmdav 内核的图像。](images/24e290f5fc309932cf41f3a280d22c14.png)

3. 在 **"配置批准的内核扩展"中，选择**"**配置"。**

    ![批准的内核扩展的配置设置的图像。](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

4. 在 **"已批准内核扩展"** 中 输入以下详细信息：

    - 显示名称：Microsoft Corp.
    - 团队 ID：UBF8T346G9

    ![配置设置应用程序内核扩展的图像。](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. 选择" **范围"** 选项卡。

    ![配置设置范围选项卡 img 的图像。](images/0df36fc308ba569db204ee32db3fb40a.png)

6. 选择“+ 添加”。

7. Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.

8. 选择“+ 添加”。

    ![配置设置的图像添加映像。](images/0dde8a4c41110dbc398c485433a81359.png)

9. 选择“**保存**”。

    ![配置设置保存映像的图像。](images/0add8019b85a453b47fa5c402c72761b.png)

10. 选择“**完成**”。

    ![配置设置完成映像的图像。](images/1c9bd3f68db20b80193dac18f33c22d0.png)

或者，你可以下载[kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig)并将其上载到 JAMF 配置文件，如使用 Jamf 配置文件部署自定义[配置文件Pro|方法 2：Upload配置文件为 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>步骤 8：批准适用于终结点的 Microsoft Defender 的系统扩展

1. 在"**配置文件"中**，选择 **"+ 新建"。**

    ![自动生成说明的社交媒体文章屏幕截图。](images/6c8b406ee224335a8c65d06953dc756e.png)

2. 输入以下详细信息：

    **常规**

    - 名称：MDATP MDAV 系统扩展
    - 说明：MDATP 系统扩展
    - 类别：无
    - 分发方法：自动安装
    - 级别：计算机级别

    ![配置设置的图像 sysext new prof.](images/sysext-new-profile.png)

3. 在 **"系统扩展"中，** 选择"**配置"。**

   ![配置设置 sysext 配置的图像。](images/sysext-configure.png)

4. 在 **"系统扩展"** 中，输入以下详细信息：

   - 显示名称：Microsoft Corp. 系统扩展
   - 系统扩展类型：允许的系统扩展
   - 团队标识符：UBF8T346G9
   - 允许的系统扩展：
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![配置设置 sysextconfig2 的图像。](images/sysext-configure2.png)

5. 选择" **范围"** 选项卡。

    ![配置设置作用域映像的图像。](images/0df36fc308ba569db204ee32db3fb40a.png)

6. 选择“+ 添加”。

7. Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.

8. 选择“+ 添加”。

   ![配置设置 addima 的图像。](images/0dde8a4c41110dbc398c485433a81359.png)

9. 选择“**保存**”。

   ![配置设置 sysext 作用域的图像。](images/sysext-scope.png)

10. 选择“**完成**”。

    ![配置设置 sysext-final 的图像。](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>步骤 9：配置网络扩展

作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft 365 Defender 门户。 以下策略允许网络扩展执行此功能。

这些步骤适用于 macOS 10.15 (加泰罗尼亚) 或更高版本。

1. 在 Jamf Pro仪表板中，选择 **"计算机**"，然后选择"**配置文件"。**

2. 单击 **"新建**"，然后为"选项"输入以下 **详细信息**：

    - 常规 **选项卡**：
        - **名称**：Microsoft Defender ATP 网络扩展
        - **说明**：macOS 10.15 (加泰罗尼亚语) 或更高版本
        - **类别**： *默认 (无)*
        - **分发方法**：使用默认 *(自动)*
        - **级别**：计算机级别 *(默认)*

    - 选项卡 **内容筛选器**：
        - **筛选器名称**：Microsoft Defender ATP 内容筛选器
        - **标识符**： `com.microsoft.wdav`
        - 将 **服务地址****、组织、****用户名**、**密码**、**证书** 留空 (**包括***未* 选中) 
        - **筛选顺序**：检查器
        - **套接字筛选器**： `com.microsoft.wdav.netext`
        - **套接字筛选器指定要求**： `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - 如果 **"包含"** 未 **(，***则"网络筛选器"字段* 留空) 

        请注意，**上述标识符****、套接字** 筛选器 **和套接字筛选器指定要求** 的确切值。

        ![配置设置 mdatpmdav 的图像。](images/netext-create-profile.png)
        
 > [!NOTE]
 > Jamf 支持可直接通过界面设置的内置内容筛选器设置。

3. 选择" **范围"** 选项卡。

   ![配置设置选项卡的图像。](images/0df36fc308ba569db204ee32db3fb40a.png)

4. 选择“+ 添加”。

5. Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.

6. 选择“+ 添加”。

    ![配置设置 adim 的图像。](images/0dde8a4c41110dbc398c485433a81359.png)

7. 选择“**保存**”。

    ![配置设置 savimg netextscop 的图像。](images/netext-scope.png)

8. 选择“**完成**”。

    ![配置设置图像 netextfinal。](images/netext-final.png)

或者，你可以下载[netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)并将其上载到 JAMF 配置文件，如使用 Jamf 配置部署自定义[配置文件Pro|方法 2：Upload配置文件为 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>步骤 10：在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描

按照在 [macOS 上使用 Microsoft Defender for Endpoint 计划扫描的说明进行操作](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>步骤 11：在 macOS 上部署 Microsoft Defender for Endpoint

1. 导航到保存的位置 `wdav.pkg` 。

    ![文件资源管理器 wdav pkg 的图像。](images/8dde76b5463047423f8637c86b05c29d.png)

2. 将其重命名为 `wdav_MDM_Contoso_200329.pkg` 。

    ![文件资源管理器 1 wdavmdmpkg 的图像。](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. 打开 Jamf Pro仪表板。

    ![配置设置 jamfpro 的图像。](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. 选择您的计算机，然后单击顶部的齿轮图标，然后选择计算机 **管理**。

    ![配置设置 compmgmt 的图像。](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. 在 **"程序包"** 中，选择 **"+ 新建"。**
    ![包含鸟描述的图片自动生成程序包新建。](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. 在 **"新建程序包"** 中 输入以下详细信息：

    **"常规"选项卡**
    - 显示名称：现在保留为空。 因为它将在你选择 pkg 时重置。
    - 类别：默认 (无) 
    - 文件名：选择"文件"

    ![配置设置常规选项卡的图像。](images/21de3658bf58b1b767a17358a3f06341.png)

    打开 文件，并指向 `wdav.pkg` 或 `wdav_MDM_Contoso_200329.pkg` 。

    ![自动生成的计算机屏幕描述的屏幕截图。](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. 选择 **“打开”**。 将显示 **名称设置为** **Microsoft Defender 高级威胁防护Microsoft Defender 防病毒。**

    **清单文件** 不是必需的。 Microsoft Defender for Endpoint 在无清单文件的情况下工作。

    **"选项"** 选项卡：保留默认值。

    **"限制"选项卡**：保留默认值。

     ![配置设置限制选项卡的图像。](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. 选择“**保存**”。 程序包将上载到 Jamf Pro。

   ![配置设置包 upl jamf pro 的图像。](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   可能需要几分钟时间，程序包才能可用于部署。

   ![配置设置包 upl 的图像。](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. 导航到" **策略"** 页。

    ![配置设置的图像。](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. 选择 **+ 新建** 以创建新策略。

    ![配置设置新策略的图像。](images/847b70e54ed04787e415f5180414b310.png)


11. 在 **"常规** "中 输入以下详细信息：

    - 显示名称：MDATP 载入 Contoso 200329 v100.86.92 或更高版本

    ![配置设置mdatponboard的图像。](images/625ba6d19e8597f05e4907298a454d28.png)

12. 选择 **"定期签入"。**

    ![配置设置重复签入的图像。](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

13. 选择“**保存**”。

14. 选择 **">配置"。**

    ![配置设置包配置的图像。](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. 选择 **Microsoft** Defender 高级威胁防护旁边的添加按钮 **Microsoft Defender 防病毒。**

    ![配置设置 MDATP 和 MDA 添加的图像。](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. 选择“**保存**”。

    ![配置设置的图像avimg。](images/9d6e5386e652e00715ff348af72671c6.png)

17. 选择" **范围"** 选项卡。

    ![配置设置 scptab 的图像。](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. 选择目标计算机。

    ![配置设置 tgtcomp 的图像。](images/6eda18a64a660fa149575454e54e7156.png)

    **Scope**

    选择“**添加**”。

    ![配置设置 ad1img 的图像。](images/1c08d097829863778d562c10c5f92b67.png)

    ![配置设置 ad2img 的图像。](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **自助服务**

    ![配置设置自服务的图像。](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. 选择“**完成**”。

    ![配置设置的图像 do1img。](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![配置设置 do2img 的图像。](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)
