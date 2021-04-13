---
title: 在 Jamf Pro 中设置适用于 macOS 的 Microsoft Defender ATP 策略
description: 了解如何在 Jamf Pro 中设置适用于 macOS 的 Microsoft Defender ATP 策略
keywords: 策略， microsoft， defender， atp， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.technology: mde
ms.openlocfilehash: 9b00d81d3d51c343565ec4eb743181baa2750b01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687729"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="3fb6a-104">在 Jamf Pro 中设置 macOS 上的 Microsoft Defender for Endpoint 策略</span><span class="sxs-lookup"><span data-stu-id="3fb6a-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3fb6a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3fb6a-106">适用于 Mac 的终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="3fb6a-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="3fb6a-107">此页面将指导你完成在 Jamf Pro 中设置 macOS 策略所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="3fb6a-108">需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="3fb6a-109">获取适用于终结点的 Microsoft Defender 载入程序包</span><span class="sxs-lookup"><span data-stu-id="3fb6a-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="3fb6a-110">使用载入程序包在 Jamf Pro 中创建配置文件</span><span class="sxs-lookup"><span data-stu-id="3fb6a-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="3fb6a-111">为终结点设置配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3fb6a-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="3fb6a-112">为终结点通知设置配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3fb6a-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="3fb6a-113">配置 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="3fb6a-114">授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="3fb6a-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="3fb6a-115">批准适用于终结点的 Microsoft Defender 内核扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="3fb6a-116">批准适用于终结点的 Microsoft Defender 的系统扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="3fb6a-117">配置网络扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="3fb6a-118">在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描</span><span class="sxs-lookup"><span data-stu-id="3fb6a-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="3fb6a-119">在 macOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3fb6a-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="3fb6a-120">步骤 1：获取适用于终结点的 Microsoft Defender 载入程序包</span><span class="sxs-lookup"><span data-stu-id="3fb6a-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="3fb6a-121">在 [Microsoft Defender 安全中心](https://securitycenter.microsoft.com )中，导航到">**载入"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="3fb6a-122">选择 macOS 作为操作系统，选择移动设备管理/Microsoft Intune 作为部署方法。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Microsoft Defender 安全中心的图像](images/onboarding-macos.png)

3. <span data-ttu-id="3fb6a-124">选择 **下载载入程序包 (WindowsDefenderATPOnboardingPackage.zip) 。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="3fb6a-125">提取 `WindowsDefenderATPOnboardingPackage.zip` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="3fb6a-126">将文件复制到首选位置。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="3fb6a-127">例如，`C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="3fb6a-128">步骤 2：使用载入程序包在 Jamf Pro 中创建配置文件</span><span class="sxs-lookup"><span data-stu-id="3fb6a-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="3fb6a-129">找到上 `WindowsDefenderATPOnboarding.plist` 一部分中的文件。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![WindowsDefenderATPOnboarding 文件的图像](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="3fb6a-131">在 Jamf Pro 仪表板中，选择"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![创建新的 Jamf Pro 仪表板的图像](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="3fb6a-133">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-133">Enter the following details:</span></span>

   <span data-ttu-id="3fb6a-134">**常规**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-134">**General**</span></span>
   - <span data-ttu-id="3fb6a-135">名称：macOS 的 MDATP 载入</span><span class="sxs-lookup"><span data-stu-id="3fb6a-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="3fb6a-136">说明：适用于 macOS 的 MDATP EDR 载入</span><span class="sxs-lookup"><span data-stu-id="3fb6a-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="3fb6a-137">类别：无</span><span class="sxs-lookup"><span data-stu-id="3fb6a-137">Category: None</span></span>
   - <span data-ttu-id="3fb6a-138">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="3fb6a-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="3fb6a-139">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="3fb6a-139">Level: Computer Level</span></span>

4. <span data-ttu-id="3fb6a-140">在 **"应用程序&自定义设置"中选择**"配置 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![配置应用和自定义设置的图像](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="3fb6a-142">选择 **"将文件 (PLIST 文件**) ，然后在首选项 **域中输入** `com.microsoft.wdav.atp` ：。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![jamfpro plist 上载文件的图像](images/jamfpro-plist-upload.png)

    ![上载文件属性列表文件的图像](images/jamfpro-plist-file.png)

7. <span data-ttu-id="3fb6a-145">选择 **"** 打开"并选择载入文件。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-145">Select **Open** and select the onboarding file.</span></span>

    ![载入文件的图像](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="3fb6a-147">选择 **"上载"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-147">Select **Upload**.</span></span> 

    ![上传 plist 文件的图像](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="3fb6a-149">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-149">Select the **Scope** tab.</span></span>

    ![范围选项卡的图像](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="3fb6a-151">选择目标计算机。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-151">Select the target computers.</span></span>

    ![目标计算机的图像](images/jamfpro-target-computer.png)

    ![目标图像](images/jamfpro-targets.png) 

11. <span data-ttu-id="3fb6a-154">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-154">Select **Save**.</span></span>

    ![部署目标计算机的图像](images/jamfpro-deployment-target.png)

    ![选择的目标计算机的图像](images/jamfpro-target-selected.png)

12. <span data-ttu-id="3fb6a-157">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-157">Select **Done**.</span></span>

    ![目标组计算机的图像](images/jamfpro-target-group.png)

    ![配置文件列表](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="3fb6a-160">步骤 3：为终结点设置配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3fb6a-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="3fb6a-161">使用以下 Microsoft Defender for Endpoint 配置设置：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="3fb6a-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="3fb6a-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="3fb6a-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="3fb6a-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="3fb6a-164">默认情况下未打开，如果计划运行适用于 macOS 的第三方 AV，请将其设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="3fb6a-165">排除项</span><span class="sxs-lookup"><span data-stu-id="3fb6a-165">exclusions</span></span>
    - <span data-ttu-id="3fb6a-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="3fb6a-166">excludedPath</span></span>
    - <span data-ttu-id="3fb6a-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="3fb6a-167">excludedFileExtension</span></span>
    - <span data-ttu-id="3fb6a-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="3fb6a-168">excludedFileName</span></span>
    - <span data-ttu-id="3fb6a-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="3fb6a-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="3fb6a-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="3fb6a-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="3fb6a-171">EICAR 位于示例中，如果你要通过概念证明，请删除它，尤其是在你测试 EICAR 时。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="3fb6a-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="3fb6a-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="3fb6a-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="3fb6a-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="3fb6a-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="3fb6a-174">archive_bomb</span></span>
    - <span data-ttu-id="3fb6a-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="3fb6a-175">cloudService</span></span>
    - <span data-ttu-id="3fb6a-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="3fb6a-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="3fb6a-177">tags</span><span class="sxs-lookup"><span data-stu-id="3fb6a-177">tags</span></span>
    - <span data-ttu-id="3fb6a-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="3fb6a-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="3fb6a-179">有关信息，请参阅 [Jamf 配置文件的属性列表](mac-preferences.md#property-list-for-jamf-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="3fb6a-180">将文件另存为 `MDATP_MDAV_configuration_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="3fb6a-181">在 Jamf Pro 仪表板中，选择"常规 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![新 Jamf Pro 仪表板的图像](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="3fb6a-183">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-183">Enter the following details:</span></span>

    <span data-ttu-id="3fb6a-184">**常规**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-184">**General**</span></span>
    
    - <span data-ttu-id="3fb6a-185">名称：MDATP MDAV 配置设置</span><span class="sxs-lookup"><span data-stu-id="3fb6a-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="3fb6a-186">说明：\<blank\></span><span class="sxs-lookup"><span data-stu-id="3fb6a-186">Description:\<blank\></span></span>
    - <span data-ttu-id="3fb6a-187">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-187">Category: None (default)</span></span>
    - <span data-ttu-id="3fb6a-188">分发方法：使用默认 (自动) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="3fb6a-189">级别：计算机级别 (默认) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-189">Level: Computer Level(default)</span></span>

    ![MDATP MDAV 配置设置的图像](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="3fb6a-191">在 **"应用程序&自定义设置"中选择**"配置 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![应用和自定义设置的图像](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="3fb6a-193">选择 **"将文件 (PLIST 文件) "。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-193">Select **Upload File (PLIST file)**.</span></span>

    ![配置设置 plist 文件的图像](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="3fb6a-195">在 **首选项域中，** 输入 `com.microsoft.wdav` ，然后选择上载  **PLIST 文件**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![配置设置首选项域的图像](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="3fb6a-197">选择 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-197">Select **Choose File**.</span></span>

    ![配置设置选择文件的图像](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="3fb6a-199">选择 **"MDATP_MDAV_configuration_settings.plist"，** 然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![mdatpmdav 配置设置的图像](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="3fb6a-201">选择 **"上载"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-201">Select **Upload**.</span></span>

    ![配置设置上载的图像](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![配置设置上载图像的图像](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="3fb6a-204">如果你发生上载 Intune 文件的情况，你将看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="3fb6a-205">![配置设置 intune 文件上载的图像](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="3fb6a-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="3fb6a-206">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-206">Select **Save**.</span></span> 

    ![配置设置的图像 保存映像](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="3fb6a-208">文件已上载。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-208">The file is uploaded.</span></span>

    ![配置文件上载图像的图像](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![已上载的配置设置文件的图像](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="3fb6a-211">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-211">Select the **Scope** tab.</span></span>

    ![配置设置作用域的图像](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="3fb6a-213">选择 **Contoso 的机器组**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="3fb6a-214">选择 **"添加"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-214">Select **Add**, then select **Save**.</span></span>

    ![配置设置的图像 addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置设置保存添加的图像](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="3fb6a-217">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-217">Select **Done**.</span></span> <span data-ttu-id="3fb6a-218">你将看到新的 **配置配置文件**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-218">You'll see the new **Configuration profile**.</span></span>

    ![配置设置配置配置文件映像的图像](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="3fb6a-220">步骤 4：配置通知设置</span><span class="sxs-lookup"><span data-stu-id="3fb6a-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="3fb6a-221">这些步骤适用于加泰罗尼亚语或 (macOS 10.15) macOS 10.15。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="3fb6a-222">在 Jamf Pro 仪表板中，选择"**计算机"，** 然后选择"**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="3fb6a-223">单击 **"新建**"，然后为"选项"输入以下 **详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="3fb6a-224">常规 **选项卡**：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-224">Tab **General**:</span></span> 
        - <span data-ttu-id="3fb6a-225">**名称**：MDATP MDAV 通知设置</span><span class="sxs-lookup"><span data-stu-id="3fb6a-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="3fb6a-226">**说明**：macOS 10.15 (加泰罗尼亚语) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fb6a-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="3fb6a-227">**类别**： *默认 (无)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="3fb6a-228">**分发方法**：使用默认 *(自动)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="3fb6a-229">**级别**：计算机级别 *(默认)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-229">**Level**: Computer Level *(default)*</span></span>

        ![配置文件设置 mdatpmdav 的图像](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="3fb6a-231">Tab **Notifications**， click **Add**， and enter the following values：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="3fb6a-232">**捆绑包 ID**： `com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="3fb6a-233">**严重警报：单击**" **禁用"**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="3fb6a-234">**通知**：单击" **启用"**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="3fb6a-235">**横幅警报类型**：选择 **"包含**"*和"临时 (默认)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="3fb6a-236">**锁屏界面上的通知：** 单击" **隐藏"**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="3fb6a-237">**通知中心中的通知**： **单击显示**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="3fb6a-238">**锁屏提醒应用图标**：单击 **显示**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-238">**Badge app icon**: Click **Display**</span></span>

        ![配置设置 mdatpmdav 通知托盘的图像](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="3fb6a-240">选项卡 **通知**，单击 **"再** 添加一次"，向下滚动到" **新建通知设置"**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="3fb6a-241">**捆绑包 ID**： `com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="3fb6a-242">将其余设置配置为与上述值相同的值</span><span class="sxs-lookup"><span data-stu-id="3fb6a-242">Configure the rest of the settings to the same values as above</span></span>

        ![配置设置 mdatpmdav 通知 mau 的图像](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="3fb6a-244">请注意，现在你有两个包含通知配置的"表"，一个针对捆绑包 **ID：com.microsoft.wdav.tray，** 另一个针对捆绑包 **ID：com.microsoft.autoupdate2**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="3fb6a-245">尽管你可以根据你的要求配置警报设置，但是捆绑包的 ID 必须和之前描述的完全相同，并且 **Include** 开关必须为 **通知的打开**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="3fb6a-246">选择"**范围"** 选项卡，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![配置设置范围添加的图像](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="3fb6a-248">选择 **Contoso 的机器组**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="3fb6a-249">选择 **"添加"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-249">Select **Add**, then select **Save**.</span></span>
    
    ![配置设置的图像 contoso 计算机 grp 保存](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![配置设置添加保存的图像](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="3fb6a-252">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-252">Select **Done**.</span></span> <span data-ttu-id="3fb6a-253">你将看到新的 **配置配置文件**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="3fb6a-254">![配置设置完成 img 的图像](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="3fb6a-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="3fb6a-255">步骤 5：配置 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="3fb6a-256">使用以下 Microsoft Defender for Endpoint 配置设置：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="3fb6a-257">将其另存为 `MDATP_MDAV_MAU_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="3fb6a-258">在 Jamf Pro 仪表板中，选择"常规 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![配置设置常规映像的图像](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="3fb6a-260">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-260">Enter the following details:</span></span>

    <span data-ttu-id="3fb6a-261">**常规**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-261">**General**</span></span> 
    
    - <span data-ttu-id="3fb6a-262">名称：MDATP MDAV MAU 设置</span><span class="sxs-lookup"><span data-stu-id="3fb6a-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="3fb6a-263">说明：适用于 macOS 的 MDATP 的 Microsoft AutoUpdate 设置</span><span class="sxs-lookup"><span data-stu-id="3fb6a-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="3fb6a-264">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-264">Category: None (default)</span></span>
    - <span data-ttu-id="3fb6a-265">分发方法：使用默认 (自动) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="3fb6a-266">级别：计算机级别 (默认) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="3fb6a-267">在 **"应用程序&自定义设置"中选择**"配置 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![配置设置应用和自定义设置的图像](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="3fb6a-269">选择 **"将文件 (PLIST 文件) "。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-269">Select **Upload File (PLIST file)**.</span></span>

    ![配置设置 plist 的图像](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="3fb6a-271">In **Preference Domain** enter： ， then select Upload `com.microsoft.autoupdate2` **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![配置设置 pref 域的图像](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="3fb6a-273">选择 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-273">Select **Choose File**.</span></span>

    ![配置设置 choosefile 的图像](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="3fb6a-275">选择 **"MDATP_MDAV_MAU_settings.plist"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![配置设置 mdatpmdavmau 设置的图像](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="3fb6a-277">选择 **"上载"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-277">Select **Upload**.</span></span>
    <span data-ttu-id="3fb6a-278">![配置设置设置的图像](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="3fb6a-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![配置设置设置的图像](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="3fb6a-280">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-280">Select **Save**.</span></span>

    ![配置设置 saveimg 的图像](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="3fb6a-282">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-282">Select the **Scope** tab.</span></span>
   
     ![配置设置作用域tab的图像](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="3fb6a-284">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-284">Select **Add**.</span></span>
    
    ![配置设置 addimg1 的图像](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![配置设置 addimg2 的图像](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![配置设置 addimg3 的图像](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="3fb6a-288">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-288">Select **Done**.</span></span>
    
    ![配置设置完成映像的图像](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="3fb6a-290">步骤 6：向 Microsoft Defender for Endpoint 授予完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="3fb6a-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3fb6a-291">在 Jamf Pro 仪表板中，选择 **"配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![配置设置配置文件的图像](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="3fb6a-293">选择 **+ 新建**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="3fb6a-294">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-294">Enter the following details:</span></span>

    <span data-ttu-id="3fb6a-295">**常规**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-295">**General**</span></span> 
    - <span data-ttu-id="3fb6a-296">名称：MDATP MDAV - 授予对 EDR 和 AV 的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="3fb6a-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="3fb6a-297">说明：在 macOS 加泰罗尼亚语或更高版本上，新的隐私首选项策略控制</span><span class="sxs-lookup"><span data-stu-id="3fb6a-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="3fb6a-298">类别：无</span><span class="sxs-lookup"><span data-stu-id="3fb6a-298">Category: None</span></span>
    - <span data-ttu-id="3fb6a-299">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="3fb6a-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="3fb6a-300">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="3fb6a-300">Level: Computer level</span></span>


    ![配置设置常规的图像](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="3fb6a-302">在 **"配置隐私首选项策略控制"中，选择**"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![配置隐私策略控制的图像](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="3fb6a-304">在 **"隐私首选项策略控制"中**，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="3fb6a-305">标识符： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="3fb6a-306">标识符类型：捆绑包 ID</span><span class="sxs-lookup"><span data-stu-id="3fb6a-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="3fb6a-307">代码要求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![配置设置隐私首选项策略控制详细信息的图像](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="3fb6a-309">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-309">Select **+ Add**.</span></span>

    ![配置设置的图像添加系统策略所有文件](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="3fb6a-311">在"应用或服务：设置为 **SystemPolicyAllFiles" 下**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="3fb6a-312">在"访问"下：设置为 **"允许"**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="3fb6a-313">选择 **" (** 不是右下角的) 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-313">Select **Save** (not the one at the bottom right).</span></span>

    ![配置设置保存图像的图像](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="3fb6a-315">单击 `+` "应用访问" **旁边的** 符号添加新条目。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![配置设置应用访问的图像](images/tcc-add-entry.png)

9. <span data-ttu-id="3fb6a-317">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-317">Enter the following details:</span></span>

    - <span data-ttu-id="3fb6a-318">标识符： `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="3fb6a-319">标识符类型：捆绑包 ID</span><span class="sxs-lookup"><span data-stu-id="3fb6a-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="3fb6a-320">代码要求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="3fb6a-321">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-321">Select **+ Add**.</span></span>

    ![配置设置 tcc epsext 条目的图像](images/tcc-epsext-entry.png)

    - <span data-ttu-id="3fb6a-323">在"应用或服务：设置为 **SystemPolicyAllFiles" 下**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="3fb6a-324">在"访问"下：设置为 **"允许"**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="3fb6a-325">选择 **" (** 不是右下角的) 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-325">Select **Save** (not the one at the bottom right).</span></span>

    ![配置设置 tcc epsext 图像 2 的图像](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="3fb6a-327">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-327">Select the **Scope** tab.</span></span>

    ![配置设置作用域的图像](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="3fb6a-329">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-329">Select **+ Add**.</span></span>

    ![配置设置 addimage 的图像](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="3fb6a-331">Select **Computer Groups** > under Group Name **>** select **Contoso's MachineGroup**.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![配置设置 contoso machinegrp 的图像](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="3fb6a-333">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-333">Select **Add**.</span></span> 

16. <span data-ttu-id="3fb6a-334">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="3fb6a-335">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-335">Select **Done**.</span></span>
    
    ![配置设置的图像](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![配置设置 donimg2 的图像](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="3fb6a-338">或者，你可以下载 [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) 并将其上载到 JAMF 配置文件，如使用 Jamf Pro 部署自定义配置文件中所述 [|方法 2：将配置文件上载到 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3fb6a-339">步骤 7：批准适用于终结点的 Microsoft Defender 内核扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="3fb6a-340">Apple 芯片 (M1) 设备不支持 KEXT。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="3fb6a-341">在这些设备上安装包含 KEXT 策略的配置文件将失败。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="3fb6a-342">在"**配置文件"中**，选择 **"+ 新建"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自动生成的社交媒体文章描述的屏幕截图](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="3fb6a-344">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-344">Enter the following details:</span></span>

    <span data-ttu-id="3fb6a-345">**常规**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-345">**General**</span></span> 
    
    - <span data-ttu-id="3fb6a-346">名称：MDATP MDAV 内核扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="3fb6a-347">说明：kext (MDATP 内核) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="3fb6a-348">类别：无</span><span class="sxs-lookup"><span data-stu-id="3fb6a-348">Category: None</span></span>
    - <span data-ttu-id="3fb6a-349">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="3fb6a-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="3fb6a-350">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="3fb6a-350">Level: Computer Level</span></span>

    ![配置设置 mdatpmdav 内核的图像](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="3fb6a-352">在 **"配置批准的内核扩展"中，选择**"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![批准的内核扩展的配置设置的图像](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="3fb6a-354">在 **"已批准内核扩展"** 中 输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="3fb6a-355">显示名称：Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="3fb6a-356">团队 ID：UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3fb6a-356">Team ID: UBF8T346G9</span></span>

    ![配置设置应用程序内核扩展的图像](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="3fb6a-358">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-358">Select the **Scope** tab.</span></span>

    ![配置设置范围选项卡 img 的图像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="3fb6a-360">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="3fb6a-361">Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="3fb6a-362">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-362">Select **+ Add**.</span></span>

    ![配置设置添加映像的图像](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="3fb6a-364">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-364">Select **Save**.</span></span>

    ![配置设置保存映像](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="3fb6a-366">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-366">Select **Done**.</span></span>

    ![配置设置完成映像的图像](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="3fb6a-368">或者，你可以下载 [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) 并将其上载到 JAMF 配置文件，如使用 Jamf Pro 部署自定义配置文件中所述 [|方法 2：将配置文件上载到 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3fb6a-369">步骤 8：批准适用于终结点的 Microsoft Defender 的系统扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3fb6a-370">在"**配置文件"中**，选择 **"+ 新建"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自动生成的社交媒体文章描述的屏幕截图](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="3fb6a-372">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-372">Enter the following details:</span></span>

    <span data-ttu-id="3fb6a-373">**常规**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-373">**General**</span></span>
    
    - <span data-ttu-id="3fb6a-374">名称：MDATP MDAV 系统扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="3fb6a-375">说明：MDATP 系统扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="3fb6a-376">类别：无</span><span class="sxs-lookup"><span data-stu-id="3fb6a-376">Category: None</span></span>
    - <span data-ttu-id="3fb6a-377">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="3fb6a-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="3fb6a-378">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="3fb6a-378">Level: Computer Level</span></span>

    ![配置设置的图像 sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="3fb6a-380">在 **"系统扩展"中，** 选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-380">In **System Extensions** select **Configure**.</span></span>

   ![配置设置 sysext 配置的图像](images/sysext-configure.png)

4. <span data-ttu-id="3fb6a-382">在 **"系统扩展"** 中，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="3fb6a-383">显示名称：Microsoft Corp. 系统扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="3fb6a-384">系统扩展类型：允许的系统扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="3fb6a-385">团队标识符：UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="3fb6a-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="3fb6a-386">允许的系统扩展：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="3fb6a-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="3fb6a-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-388">**com.microsoft.wdav.netext**</span></span>

    ![配置设置的图像 sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="3fb6a-390">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-390">Select the **Scope** tab.</span></span>

    ![配置设置作用域映像的图像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="3fb6a-392">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="3fb6a-393">Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="3fb6a-394">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-394">Select **+ Add**.</span></span>

   ![配置设置 addima 的图像](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="3fb6a-396">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-396">Select **Save**.</span></span>

   ![配置设置 sysext 作用域的图像](images/sysext-scope.png)

10. <span data-ttu-id="3fb6a-398">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-398">Select **Done**.</span></span>

    ![配置设置的图像 sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="3fb6a-400">步骤 9：配置网络扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="3fb6a-401">作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="3fb6a-402">以下策略允许网络扩展执行此功能。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="3fb6a-403">这些步骤适用于加泰罗尼亚语或 (macOS 10.15) macOS 10.15。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="3fb6a-404">在 Jamf Pro 仪表板中，选择"**计算机"，** 然后选择"**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="3fb6a-405">单击 **"新建**"，然后为"选项"输入以下 **详细信息**：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="3fb6a-406">常规 **选项卡**：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-406">Tab **General**:</span></span> 
        - <span data-ttu-id="3fb6a-407">**名称**：Microsoft Defender ATP 网络扩展</span><span class="sxs-lookup"><span data-stu-id="3fb6a-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="3fb6a-408">**说明**：macOS 10.15 (加泰罗尼亚语) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fb6a-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="3fb6a-409">**类别**： *默认 (无)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="3fb6a-410">**分发方法**：使用默认 *(自动)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="3fb6a-411">**级别**：计算机级别 *(默认)*</span><span class="sxs-lookup"><span data-stu-id="3fb6a-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="3fb6a-412">选项卡 **内容筛选器**：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="3fb6a-413">**筛选器名称**：Microsoft Defender ATP 内容筛选器</span><span class="sxs-lookup"><span data-stu-id="3fb6a-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="3fb6a-414">**标识符**： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="3fb6a-415">将 **服务地址\*\*\*\*、组织、\*\*\*\*用户名**、**密码**、**证书** 留空 (\**包括\*\*\*未* 选中) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="3fb6a-416">**筛选顺序**：检查器</span><span class="sxs-lookup"><span data-stu-id="3fb6a-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="3fb6a-417">**套接字筛选器**： `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="3fb6a-418">**套接字筛选器指定要求**： `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="3fb6a-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="3fb6a-419">如果 **"包含"** 未 **(，则"** 网络筛选器 *"* 字段留空) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="3fb6a-420">请注意，**上述标识符\*\*\*\*、套接字** 筛选器 **和套接字筛选器指定要求** 的确切值。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![配置设置 mdatpmdav 的图像](images/netext-create-profile.png)

3. <span data-ttu-id="3fb6a-422">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-422">Select the **Scope** tab.</span></span>

   ![配置设置标签页的图像](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="3fb6a-424">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="3fb6a-425">Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="3fb6a-426">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-426">Select **+ Add**.</span></span>

    ![配置设置 adim 的图像](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="3fb6a-428">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-428">Select **Save**.</span></span>

    ![配置设置 savimg netextscop 的图像](images/netext-scope.png)

8. <span data-ttu-id="3fb6a-430">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-430">Select **Done**.</span></span>

    ![配置设置图像 netextfinal](images/netext-final.png)

<span data-ttu-id="3fb6a-432">或者，你可以下载 [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) 并将其上载到 JAMF 配置文件，如使用 Jamf Pro 部署自定义配置文件中所述 [|方法 2：将配置文件上载到 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3fb6a-433">步骤 10：在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描</span><span class="sxs-lookup"><span data-stu-id="3fb6a-433">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="3fb6a-434">按照在 [macOS 上使用 Microsoft Defender for Endpoint 计划扫描的说明操作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3fb6a-435">步骤 11：在 macOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3fb6a-435">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="3fb6a-436">导航到保存的位置 `wdav.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![文件资源管理器 wdav pkg 的图像](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="3fb6a-438">将其重命名为 `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![文件资源管理器1 wdavmdmpkg 的图像](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="3fb6a-440">打开 Jamf Pro 仪表板。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-440">Open the Jamf Pro dashboard.</span></span>

    ![配置设置 jamfpro 的图像](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="3fb6a-442">选择您的计算机，然后单击顶部的齿轮图标，然后选择计算机 **管理**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![配置设置 compmgmt 的图像](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="3fb6a-444">在 **"程序包"** 中，选择 **"+ 新建"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="3fb6a-445">![包含鸟描述的图片自动生成程序包新建](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="3fb6a-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="3fb6a-446">在 **"新建程序包"** 中 输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="3fb6a-447">**"常规"选项卡**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-447">**General tab**</span></span>
    - <span data-ttu-id="3fb6a-448">显示名称：现在保留为空。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="3fb6a-449">因为它将在你选择 pkg 时重置。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="3fb6a-450">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="3fb6a-450">Category: None (default)</span></span>
    - <span data-ttu-id="3fb6a-451">文件名：选择"文件"</span><span class="sxs-lookup"><span data-stu-id="3fb6a-451">Filename: Choose File</span></span>

    ![配置设置常规选项卡的图像](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="3fb6a-453">打开 文件，并指向 `wdav.pkg` 或 `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![自动生成的计算机屏幕描述的屏幕截图](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="3fb6a-455">选择 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-455">Select **Open**.</span></span> <span data-ttu-id="3fb6a-456">将显示 **名称设置为** **Microsoft Defender 高级威胁防护和 Microsoft Defender 防病毒**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="3fb6a-457">**清单文件** 不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-457">**Manifest File** is not required.</span></span> <span data-ttu-id="3fb6a-458">Microsoft Defender 高级威胁防护在没有清单文件的情况下工作。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-458">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="3fb6a-459">**选项选项卡**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-459">**Options tab**</span></span><br> <span data-ttu-id="3fb6a-460">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-460">Keep default values.</span></span>

    <span data-ttu-id="3fb6a-461">**"限制"选项卡**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-461">**Limitations tab**</span></span><br> <span data-ttu-id="3fb6a-462">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-462">Keep default values.</span></span>
    
     ![配置设置限制选项卡的图像](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="3fb6a-464">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-464">Select **Save**.</span></span> <span data-ttu-id="3fb6a-465">该程序包将上载到 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-465">The package is uploaded to Jamf Pro.</span></span> 

   ![配置设置包 upl jamf pro 的图像](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="3fb6a-467">可能需要几分钟时间，程序包才能可用于部署。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![配置设置包 upl 的图像](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="3fb6a-469">导航到" **策略"** 页。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-469">Navigate to the **Policies** page.</span></span>

    ![配置设置要求的图像](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="3fb6a-471">选择 **+ 新建** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-471">Select **+ New** to create a new policy.</span></span>

    ![配置设置新策略的图像](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="3fb6a-473">在 **"常规** "中 输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fb6a-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="3fb6a-474">显示名称：MDATP 载入 Contoso 200329 v100.86.92 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fb6a-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="3fb6a-475">配置设置mdatponboard的图像</span><span class="sxs-lookup"><span data-stu-id="3fb6a-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="3fb6a-476">选择 **"定期签入"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-476">Select **Recurring Check-in**.</span></span> 
    
    ![配置设置重复签入的图像](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="3fb6a-478">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="3fb6a-479">选择 **">配置"。**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-479">Select **Packages > Configure**.</span></span>
 
    ![配置设置包配置的图像](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="3fb6a-481">选择 Microsoft Defender **高级** 威胁防护和 Microsoft Defender 防病毒 旁边的 **"添加"按钮**。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![配置设置 MDATP 和 MDA 添加的图像](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="3fb6a-483">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-483">Select **Save**.</span></span>

    ![配置设置的图像avimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="3fb6a-485">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-485">Select the **Scope** tab.</span></span>  

    ![配置设置 scptab 的图像](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="3fb6a-487">选择目标计算机。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-487">Select the target computers.</span></span>

    ![配置设置 tgtcomp 的图像](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="3fb6a-489">**Scope**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-489">**Scope**</span></span>
    
    <span data-ttu-id="3fb6a-490">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-490">Select **Add**.</span></span>
    
    ![配置设置 ad1img 的图像](images/1c08d097829863778d562c10c5f92b67.png)

    ![配置设置 ad2img 的图像](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="3fb6a-493">**自助服务**</span><span class="sxs-lookup"><span data-stu-id="3fb6a-493">**Self-Service**</span></span>
    
    ![配置设置自服务的图像](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="3fb6a-495">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3fb6a-495">Select **Done**.</span></span> 

    ![配置设置 do1img 的图像](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![配置设置 do2img 的图像](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




