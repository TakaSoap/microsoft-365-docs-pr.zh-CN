---
title: 在 Jamf 中设置 macOS 上的 Microsoft Defender for Endpoint Pro
description: 了解如何在 Jamf Pro 中设置 macOS 上的 Microsoft Defender for Endpoint 策略
keywords: 策略， microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: 577eea6e678b6a5d60e5bb8f2fbaaae25d239577
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230063"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="68150-104">在 Jamf 中设置 macOS 上的 Microsoft Defender for Endpoint Pro</span><span class="sxs-lookup"><span data-stu-id="68150-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="68150-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="68150-105">**Applies to:**</span></span>

- [<span data-ttu-id="68150-106">Mac 上的 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="68150-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="68150-107">此页面将指导你完成在 Jamf Pro 中设置 macOS 策略所需的Pro。</span><span class="sxs-lookup"><span data-stu-id="68150-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="68150-108">需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="68150-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="68150-109">获取适用于终结点的 Microsoft Defender 载入程序包</span><span class="sxs-lookup"><span data-stu-id="68150-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="68150-110">使用载入包在 Jamf Pro创建配置文件</span><span class="sxs-lookup"><span data-stu-id="68150-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="68150-111">为终结点设置配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="68150-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="68150-112">为终结点通知设置配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="68150-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="68150-113">配置 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="68150-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="68150-114">授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="68150-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="68150-115">批准适用于终结点的 Microsoft Defender 内核扩展</span><span class="sxs-lookup"><span data-stu-id="68150-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="68150-116">批准适用于终结点的 Microsoft Defender 的系统扩展</span><span class="sxs-lookup"><span data-stu-id="68150-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="68150-117">配置网络扩展</span><span class="sxs-lookup"><span data-stu-id="68150-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="68150-118">在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描</span><span class="sxs-lookup"><span data-stu-id="68150-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="68150-119">在 macOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="68150-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="68150-120">步骤 1：获取适用于终结点的 Microsoft Defender 载入程序包</span><span class="sxs-lookup"><span data-stu-id="68150-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="68150-121">In [Microsoft Defender 安全中心，](https://securitycenter.microsoft.com)navigate to **设置 > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="68150-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com), navigate to **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="68150-122">选择 macOS 作为操作系统，选择移动设备管理/Microsoft Intune作为部署方法。</span><span class="sxs-lookup"><span data-stu-id="68150-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![图像Microsoft Defender 安全中心](images/onboarding-macos.png)

3. <span data-ttu-id="68150-124">选择 **下载载入程序包 (WindowsDefenderATPOnboardingPackage.zip) 。**</span><span class="sxs-lookup"><span data-stu-id="68150-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="68150-125">提取 `WindowsDefenderATPOnboardingPackage.zip` 。</span><span class="sxs-lookup"><span data-stu-id="68150-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="68150-126">将文件复制到首选位置。</span><span class="sxs-lookup"><span data-stu-id="68150-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="68150-127">例如，`C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。</span><span class="sxs-lookup"><span data-stu-id="68150-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="68150-128">步骤 2：使用载入程序包在 Jamf Pro创建配置文件</span><span class="sxs-lookup"><span data-stu-id="68150-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="68150-129">找到上 `WindowsDefenderATPOnboarding.plist` 一部分中的文件。</span><span class="sxs-lookup"><span data-stu-id="68150-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![WindowsDefenderATPOnboarding 文件的图像](images/plist-onboarding-file.png)


2. <span data-ttu-id="68150-131">在 Jamf Pro仪表板中，选择"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="68150-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![创建新 Jamf 仪表板Pro的图像](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="68150-133">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-133">Enter the following details:</span></span>

   <span data-ttu-id="68150-134">**常规**</span><span class="sxs-lookup"><span data-stu-id="68150-134">**General**</span></span>
   - <span data-ttu-id="68150-135">名称：macOS 的 MDATP 载入</span><span class="sxs-lookup"><span data-stu-id="68150-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="68150-136">说明：mDATP EDR macOS 的载入</span><span class="sxs-lookup"><span data-stu-id="68150-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="68150-137">类别：无</span><span class="sxs-lookup"><span data-stu-id="68150-137">Category: None</span></span>
   - <span data-ttu-id="68150-138">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="68150-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="68150-139">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="68150-139">Level: Computer Level</span></span>

4. <span data-ttu-id="68150-140">在 **"应用程序&自定义设置** 选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![配置应用和自定义设置的图像](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="68150-142">Select **Upload File (PLIST file)** then in Preference **Domain** enter： `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="68150-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span>

    ![jamfpro plist 上载文件的图像](images/jamfpro-plist-upload.png)

    ![上载文件属性列表文件的图像](images/jamfpro-plist-file.png)

6. <span data-ttu-id="68150-145">选择 **"** 打开"并选择载入文件。</span><span class="sxs-lookup"><span data-stu-id="68150-145">Select **Open** and select the onboarding file.</span></span>

    ![载入文件的图像](images/jamfpro-plist-file-onboard.png)

7. <span data-ttu-id="68150-147">选择 **"Upload"。**</span><span class="sxs-lookup"><span data-stu-id="68150-147">Select **Upload**.</span></span>

    ![上传 plist 文件的图像](images/jamfpro-upload-plist.png)

8. <span data-ttu-id="68150-149">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-149">Select the **Scope** tab.</span></span>

    ![范围选项卡的图像](images/jamfpro-scope-tab.png)

9. <span data-ttu-id="68150-151">选择目标计算机。</span><span class="sxs-lookup"><span data-stu-id="68150-151">Select the target computers.</span></span>

    ![目标计算机的图像](images/jamfpro-target-computer.png)

    ![目标图像](images/jamfpro-targets.png)

10. <span data-ttu-id="68150-154">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-154">Select **Save**.</span></span>

    ![部署目标计算机的图像](images/jamfpro-deployment-target.png)

    ![选择的目标计算机的图像](images/jamfpro-target-selected.png)

11. <span data-ttu-id="68150-157">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-157">Select **Done**.</span></span>

    ![目标组计算机的图像](images/jamfpro-target-group.png)

    ![配置文件列表](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="68150-160">步骤 3：为终结点设置配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="68150-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

<span data-ttu-id="68150-161">可以使用 JAMF Pro GUI 编辑 Microsoft Defender 配置的个人设置，或使用旧方法，方法是在文本编辑器中创建配置 Plist，并将其上载到 JAMF Pro。</span><span class="sxs-lookup"><span data-stu-id="68150-161">You can either use JAMF Pro GUI to edit individual settings of the Microsoft Defender configuration, or use the legacy method by creating a configuration Plist in a text editor, and uploading it to JAMF Pro.</span></span>

<span data-ttu-id="68150-162">请注意，你必须使用精确 `com.microsoft.wdav` 作为 **首选项域**，Microsoft Defender 仅使用此名称并 `com.microsoft.wdav.ext` 加载其托管设置！</span><span class="sxs-lookup"><span data-stu-id="68150-162">Note that you must use exact `com.microsoft.wdav` as the **Preference Domain**, Microsoft Defender uses only this name and `com.microsoft.wdav.ext` to load its managed settings!</span></span>

<span data-ttu-id="68150-163"> (您喜欢使用 GUI 方法，但也需要配置尚未添加到架构的设置时，版本可能在极少数情况下 `com.microsoft.wdav.ext` 使用。) </span><span class="sxs-lookup"><span data-stu-id="68150-163">(The `com.microsoft.wdav.ext` version may be used in rare cases when you prefer to use GUI method, but also need to configure a setting that has not been added to the schema yet.)</span></span>

### <a name="gui-method"></a><span data-ttu-id="68150-164">GUI 方法</span><span class="sxs-lookup"><span data-stu-id="68150-164">GUI method</span></span>

1. <span data-ttu-id="68150-165">从 defender schema.js存储库下载GitHub[文件，](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema)并将其保存到本地文件：</span><span class="sxs-lookup"><span data-stu-id="68150-165">Download schema.json file from [Defender's GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) and save it to a local file:</span></span>

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. <span data-ttu-id="68150-166">在"计算机 ->配置文件"下创建新的配置文件，在"常规"选项卡上输入 **以下** 详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-166">Create a new Configuration Profile under Computers -> Configuration Profiles, enter the following details on the **General** tab:</span></span>

    ![新配置文件](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - <span data-ttu-id="68150-168">名称：MDATP MDAV 配置设置</span><span class="sxs-lookup"><span data-stu-id="68150-168">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="68150-169">说明：\<blank\></span><span class="sxs-lookup"><span data-stu-id="68150-169">Description:\<blank\></span></span>
    - <span data-ttu-id="68150-170">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="68150-170">Category: None (default)</span></span>
    - <span data-ttu-id="68150-171">级别：计算机级别 (默认) </span><span class="sxs-lookup"><span data-stu-id="68150-171">Level: Computer Level (default)</span></span>
    - <span data-ttu-id="68150-172">分发方法：使用默认 (自动) </span><span class="sxs-lookup"><span data-stu-id="68150-172">Distribution Method: Install Automatically (default)</span></span>

3. <span data-ttu-id="68150-173">向下滚动到"&自定义设置"选项卡，选择 **"外部** 应用程序"，单击"添加"，并使用"自定义架构作为源"以用于首选项域。 </span><span class="sxs-lookup"><span data-stu-id="68150-173">Scroll down to the **Application & Custom Settings** tab, select **External Applications**, click **Add** and use **Custom Schema** as Source to use for the preference domain.</span></span>

    ![添加自定义架构](images/4137189bc3204bb09eed3aabc41afd78.png)

4. <span data-ttu-id="68150-175">输入 `com.microsoft.wdav` 作为首选项域，单击"添加架构 **"Uploadschema.js** 步骤 1 上下载的文件上的"添加架构"。</span><span class="sxs-lookup"><span data-stu-id="68150-175">Enter `com.microsoft.wdav` as the Preference Domain, click on **Add Schema** and **Upload** the schema.json file downloaded on Step 1.</span></span> <span data-ttu-id="68150-176">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-176">Click **Save**.</span></span>

    ![Upload架构](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. <span data-ttu-id="68150-178">可以在下面的首选项域属性下看到所有受支持的 Microsoft Defender **配置设置**。</span><span class="sxs-lookup"><span data-stu-id="68150-178">You can see all supported Microsoft Defender configuration settings below, under **Preference Domain Properties**.</span></span> <span data-ttu-id="68150-179">单击 **"添加/删除** 属性"以选择要管理的设置，然后单击 **"确定"** 保存更改。</span><span class="sxs-lookup"><span data-stu-id="68150-179">Click **Add/Remove properties** to select the settings that you want to be managed, and click **Ok** to save your changes.</span></span> <span data-ttu-id="68150-180"> (设置未选择的用户不会包含在托管配置中，最终用户将能够配置其计算机中的这些设置。) </span><span class="sxs-lookup"><span data-stu-id="68150-180">(Settings left unselected will not be included into the managed configuration, an end user will be able to configure those settings on their machines.)</span></span>

    ![选择托管设置](images/817b3b760d11467abe9bdd519513f54f.png)

6. <span data-ttu-id="68150-182">将设置的值更改为所需值。</span><span class="sxs-lookup"><span data-stu-id="68150-182">Change values of the settings to desired values.</span></span> <span data-ttu-id="68150-183">可以单击 **"详细信息"** 获取特定设置的文档。</span><span class="sxs-lookup"><span data-stu-id="68150-183">You can click **More information** to get documentation for a particular setting.</span></span> <span data-ttu-id="68150-184"> (可以单击 **"Plist 预览** "检查 plist 的配置外观。</span><span class="sxs-lookup"><span data-stu-id="68150-184">(You may click **Plist preview** to inspect what the configuration plist will look like.</span></span> <span data-ttu-id="68150-185">单击 **"表单编辑器** "返回到可视编辑器。) </span><span class="sxs-lookup"><span data-stu-id="68150-185">Click **Form editor** to return to the visual editor.)</span></span>

    ![更改设置值](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. <span data-ttu-id="68150-187">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-187">Select the **Scope** tab.</span></span>

    ![配置文件作用域](images/9fc17529e5577eefd773c658ec576a7d.png)

8. <span data-ttu-id="68150-189">选择 **Contoso 的机器组**。</span><span class="sxs-lookup"><span data-stu-id="68150-189">Select **Contoso's Machine Group**.</span></span>

9. <span data-ttu-id="68150-190">选择 **"添加"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="68150-190">Select **Add**, then select **Save**.</span></span>

    ![配置设置 - 添加](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置设置 - 保存](images/6f093e42856753a3955cab7ee14f12d9.png)

10. <span data-ttu-id="68150-193">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-193">Select **Done**.</span></span> <span data-ttu-id="68150-194">你将看到新的 **配置配置文件**。</span><span class="sxs-lookup"><span data-stu-id="68150-194">You'll see the new **Configuration profile**.</span></span>

    ![配置设置 - 完成](images/dd55405106da0dfc2f50f8d4525b01c8.png)

<span data-ttu-id="68150-196">Microsoft Defender 会随着时间的推移添加新设置。</span><span class="sxs-lookup"><span data-stu-id="68150-196">Microsoft Defender adds new settings over time.</span></span> <span data-ttu-id="68150-197">这些新设置将添加到架构中，并且新版本将发布到 Github。</span><span class="sxs-lookup"><span data-stu-id="68150-197">These new settings will be added to the schema, and a new version will be published to Github.</span></span>
<span data-ttu-id="68150-198">只需下载更新的架构、编辑现有配置文件和编辑"自定义 **&"** 选项卡上的"编辑设置架构。 </span><span class="sxs-lookup"><span data-stu-id="68150-198">All you need to do to have updates is to download an updated schema, edit existing configuration profile, and **Edit schema** at the **Application & Custom Settings** tab.</span></span>

### <a name="legacy-method"></a><span data-ttu-id="68150-199">旧方法</span><span class="sxs-lookup"><span data-stu-id="68150-199">Legacy method</span></span>

1. <span data-ttu-id="68150-200">使用以下 Microsoft Defender for Endpoint 配置设置：</span><span class="sxs-lookup"><span data-stu-id="68150-200">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="68150-201">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="68150-201">enableRealTimeProtection</span></span>
    - <span data-ttu-id="68150-202">passiveMode</span><span class="sxs-lookup"><span data-stu-id="68150-202">passiveMode</span></span>

    >[!NOTE]
    ><span data-ttu-id="68150-203">默认情况下未打开，如果计划运行适用于 macOS 的第三方 AV，请将其设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="68150-203">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="68150-204">排除项</span><span class="sxs-lookup"><span data-stu-id="68150-204">exclusions</span></span>
    - <span data-ttu-id="68150-205">excludedPath</span><span class="sxs-lookup"><span data-stu-id="68150-205">excludedPath</span></span>
    - <span data-ttu-id="68150-206">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="68150-206">excludedFileExtension</span></span>
    - <span data-ttu-id="68150-207">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="68150-207">excludedFileName</span></span>
    - <span data-ttu-id="68150-208">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="68150-208">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="68150-209">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="68150-209">allowedThreats</span></span>

    >[!NOTE]
    ><span data-ttu-id="68150-210">EICAR 位于示例中，如果你要通过概念证明，请删除它，尤其是在你测试 EICAR 时。</span><span class="sxs-lookup"><span data-stu-id="68150-210">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>

    - <span data-ttu-id="68150-211">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="68150-211">disallowedThreatActions</span></span>
    - <span data-ttu-id="68150-212">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="68150-212">potentially_unwanted_application</span></span>
    - <span data-ttu-id="68150-213">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="68150-213">archive_bomb</span></span>
    - <span data-ttu-id="68150-214">cloudService</span><span class="sxs-lookup"><span data-stu-id="68150-214">cloudService</span></span>
    - <span data-ttu-id="68150-215">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="68150-215">automaticSampleSubmission</span></span>
    - <span data-ttu-id="68150-216">标记</span><span class="sxs-lookup"><span data-stu-id="68150-216">tags</span></span>
    - <span data-ttu-id="68150-217">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="68150-217">hideStatusMenuIcon</span></span>

     <span data-ttu-id="68150-218">有关信息，请参阅 [Jamf 配置文件的属性列表](mac-preferences.md#property-list-for-jamf-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="68150-218">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="68150-219">将文件另存为 `MDATP_MDAV_configuration_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="68150-219">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>

3. <span data-ttu-id="68150-220">在 Jamf Pro仪表板中，打开 **"计算机**"，然后打开 **"配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-220">In the Jamf Pro dashboard, open **Computers**, and there **Configuration Profiles**.</span></span> <span data-ttu-id="68150-221">单击\**新建 (* 并 **切换到常规选项卡** 。</span><span class="sxs-lookup"><span data-stu-id="68150-221">Click \**New(* and switch to the **General** tab.</span></span>

    ![新配置文件](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="68150-223">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-223">Enter the following details:</span></span>

    <span data-ttu-id="68150-224">**常规**</span><span class="sxs-lookup"><span data-stu-id="68150-224">**General**</span></span>

    - <span data-ttu-id="68150-225">名称：MDATP MDAV 配置设置</span><span class="sxs-lookup"><span data-stu-id="68150-225">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="68150-226">说明：\<blank\></span><span class="sxs-lookup"><span data-stu-id="68150-226">Description:\<blank\></span></span>
    - <span data-ttu-id="68150-227">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="68150-227">Category: None (default)</span></span>
    - <span data-ttu-id="68150-228">分发方法：使用默认 (自动) </span><span class="sxs-lookup"><span data-stu-id="68150-228">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="68150-229">级别：计算机级别 (默认) </span><span class="sxs-lookup"><span data-stu-id="68150-229">Level: Computer Level(default)</span></span>

    ![MDATP MDAV 配置设置的图像](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="68150-231">在 **"应用程序&自定义设置** 选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-231">In **Application & Custom Settings** select **Configure**.</span></span>

    ![应用和自定义设置的图像](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="68150-233">Select **Upload File (PLIST file)**.</span><span class="sxs-lookup"><span data-stu-id="68150-233">Select **Upload File (PLIST file)**.</span></span>

    ![配置设置 plist 文件的图像](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="68150-235">在 **首选项域中，** 输入 `com.microsoft.wdav` ，然后选择Upload **PLIST 文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-235">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![配置设置首选项域的图像](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="68150-237">选择 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-237">Select **Choose File**.</span></span>

    ![配置设置选择文件的图像](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="68150-239">选择 **"MDATP_MDAV_configuration_settings.plist"，** 然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="68150-239">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![mdatpmdav 配置设置的图像](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="68150-241">选择 **"Upload"。**</span><span class="sxs-lookup"><span data-stu-id="68150-241">Select **Upload**.</span></span>

    ![配置设置上载的图像](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![配置设置上载图像的图像](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="68150-244">如果你发生上载 Intune 文件的情况，你将看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="68150-244">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="68150-245">![配置设置 intune 文件上载的图像](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="68150-245">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="68150-246">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-246">Select **Save**.</span></span>

    ![配置设置的图像 保存映像](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="68150-248">文件已上载。</span><span class="sxs-lookup"><span data-stu-id="68150-248">The file is uploaded.</span></span>

    ![配置文件上载图像的图像](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![已上载的配置设置文件的图像](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="68150-251">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-251">Select the **Scope** tab.</span></span>

    ![配置设置作用域的图像](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="68150-253">选择 **Contoso 的机器组**。</span><span class="sxs-lookup"><span data-stu-id="68150-253">Select **Contoso's Machine Group**.</span></span>

15. <span data-ttu-id="68150-254">选择 **"添加"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="68150-254">Select **Add**, then select **Save**.</span></span>

    ![配置设置的图像 addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置设置保存添加的图像](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="68150-257">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-257">Select **Done**.</span></span> <span data-ttu-id="68150-258">你将看到新的 **配置配置文件**。</span><span class="sxs-lookup"><span data-stu-id="68150-258">You'll see the new **Configuration profile**.</span></span>

    ![配置设置配置配置文件映像的图像](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="68150-260">步骤 4：配置通知设置</span><span class="sxs-lookup"><span data-stu-id="68150-260">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="68150-261">这些步骤适用于加泰罗尼亚语或 (macOS 10.15) macOS 10.15。</span><span class="sxs-lookup"><span data-stu-id="68150-261">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="68150-262">在 Jamf Pro仪表板中，选择 **"计算机**"，然后选择"**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-262">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="68150-263">单击 **"新建**"，然后为"选项"输入以下 **详细信息**：</span><span class="sxs-lookup"><span data-stu-id="68150-263">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="68150-264">常规 **选项卡**：</span><span class="sxs-lookup"><span data-stu-id="68150-264">Tab **General**:</span></span>
        - <span data-ttu-id="68150-265">**名称**：MDATP MDAV 通知设置</span><span class="sxs-lookup"><span data-stu-id="68150-265">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="68150-266">**说明**：macOS 10.15 (加泰罗尼亚语) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="68150-266">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="68150-267">**类别**： *默认 (无)*</span><span class="sxs-lookup"><span data-stu-id="68150-267">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="68150-268">**分发方法**：使用默认 *(自动)*</span><span class="sxs-lookup"><span data-stu-id="68150-268">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="68150-269">**级别**：计算机级别 *(默认)*</span><span class="sxs-lookup"><span data-stu-id="68150-269">**Level**: Computer Level *(default)*</span></span>

        ![新 macOS 配置文件屏幕的图像](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="68150-271">Tab **Notifications**， click **Add**， and enter the following values：</span><span class="sxs-lookup"><span data-stu-id="68150-271">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="68150-272">**捆绑包 ID**： `com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="68150-272">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="68150-273">**严重警报：单击**" **禁用"**</span><span class="sxs-lookup"><span data-stu-id="68150-273">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="68150-274">**通知**：单击" **启用"**</span><span class="sxs-lookup"><span data-stu-id="68150-274">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="68150-275">**横幅警报类型**：选择 **"包含**"*和"临时 (默认)*</span><span class="sxs-lookup"><span data-stu-id="68150-275">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="68150-276">**锁屏界面上的通知：** 单击" **隐藏"**</span><span class="sxs-lookup"><span data-stu-id="68150-276">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="68150-277">**通知中心中的通知**： **单击显示**</span><span class="sxs-lookup"><span data-stu-id="68150-277">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="68150-278">**锁屏提醒应用图标**：单击 **显示**</span><span class="sxs-lookup"><span data-stu-id="68150-278">**Badge app icon**: Click **Display**</span></span>

        ![配置设置 mdatpmdav 通知托盘的图像](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="68150-280">Tab **Notifications**， click **Add** one more time， scroll down to New **Notifications 设置**</span><span class="sxs-lookup"><span data-stu-id="68150-280">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="68150-281">**捆绑包 ID**： `com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="68150-281">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="68150-282">将其余设置配置为与上述值相同的值</span><span class="sxs-lookup"><span data-stu-id="68150-282">Configure the rest of the settings to the same values as above</span></span>

        ![配置设置 mdatpmdav 通知 mau 的图像](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="68150-284">请注意，现在你有两个包含通知配置的"表"，一个针对捆绑包 **ID：com.microsoft.wdav.tray，** 另一个针对捆绑包 **ID：com.microsoft.autoupdate2**。</span><span class="sxs-lookup"><span data-stu-id="68150-284">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="68150-285">尽管你可以根据你的要求配置警报设置，但是捆绑包的 ID 必须和之前描述的完全相同，并且 **Include** 开关必须为 **通知的打开**。</span><span class="sxs-lookup"><span data-stu-id="68150-285">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="68150-286">选择"**范围"** 选项卡，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="68150-286">Select the **Scope** tab, then select **Add**.</span></span>

    ![配置设置范围添加的图像](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="68150-288">选择 **Contoso 的机器组**。</span><span class="sxs-lookup"><span data-stu-id="68150-288">Select **Contoso's Machine Group**.</span></span>

5. <span data-ttu-id="68150-289">选择 **"添加"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="68150-289">Select **Add**, then select **Save**.</span></span>

    ![配置设置的图像 contoso 计算机 grp 保存](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![配置设置添加保存的图像](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="68150-292">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-292">Select **Done**.</span></span> <span data-ttu-id="68150-293">你将看到新的 **配置配置文件**。</span><span class="sxs-lookup"><span data-stu-id="68150-293">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="68150-294">![配置设置完成 img 的图像](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="68150-294">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="68150-295">步骤 5：配置 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="68150-295">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="68150-296">使用以下 Microsoft Defender for Endpoint 配置设置：</span><span class="sxs-lookup"><span data-stu-id="68150-296">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="68150-297">将其另存为 `MDATP_MDAV_MAU_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="68150-297">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="68150-298">在 Jamf Pro仪表板中，选择"**常规"。**</span><span class="sxs-lookup"><span data-stu-id="68150-298">In the Jamf Pro dashboard, select **General**.</span></span>

    ![配置设置常规映像的图像](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="68150-300">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-300">Enter the following details:</span></span>

    <span data-ttu-id="68150-301">**常规**</span><span class="sxs-lookup"><span data-stu-id="68150-301">**General**</span></span>

    - <span data-ttu-id="68150-302">名称：MDATP MDAV MAU 设置</span><span class="sxs-lookup"><span data-stu-id="68150-302">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="68150-303">说明：适用于 macOS 的 MDATP 的 Microsoft AutoUpdate 设置</span><span class="sxs-lookup"><span data-stu-id="68150-303">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="68150-304">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="68150-304">Category: None (default)</span></span>
    - <span data-ttu-id="68150-305">分发方法：使用默认 (自动) </span><span class="sxs-lookup"><span data-stu-id="68150-305">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="68150-306">级别：计算机级别 (默认) </span><span class="sxs-lookup"><span data-stu-id="68150-306">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="68150-307">在 **"应用程序&自定义设置** 选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-307">In **Application & Custom Settings** select **Configure**.</span></span>

    ![配置设置应用和自定义设置的图像](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="68150-309">Select **Upload File (PLIST file)**.</span><span class="sxs-lookup"><span data-stu-id="68150-309">Select **Upload File (PLIST file)**.</span></span>

    ![配置设置 plist 的图像](images/1213872db5833aa8be535da57653219f.png)

7. <span data-ttu-id="68150-311">在 **"首选项域**"中输入 `com.microsoft.autoupdate2` ：，然后选择 **"Upload PLIST 文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-311">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![配置设置 pref 域的图像](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="68150-313">选择 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-313">Select **Choose File**.</span></span>

    ![配置设置 choosefile 的图像](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="68150-315">选择 **"MDATP_MDAV_MAU_settings.plist"。**</span><span class="sxs-lookup"><span data-stu-id="68150-315">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![配置设置 mdatpmdavmau 设置的图像](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="68150-317">选择 **"Upload"。**</span><span class="sxs-lookup"><span data-stu-id="68150-317">Select **Upload**.</span></span>
    <span data-ttu-id="68150-318">![配置设置设置的图像](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="68150-318">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![配置设置设置的图像](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="68150-320">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-320">Select **Save**.</span></span>

    ![配置设置 saveimg 的图像](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="68150-322">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-322">Select the **Scope** tab.</span></span>

     ![配置设置作用域tab的图像](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="68150-324">选择“添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-324">Select **Add**.</span></span>

    ![配置设置 addimg1 的图像](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![配置设置 addimg2 的图像](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![配置设置 addimg3 的图像](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="68150-328">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-328">Select **Done**.</span></span>

    ![配置设置完成映像的图像](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="68150-330">步骤 6：向 Microsoft Defender for Endpoint 授予完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="68150-330">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="68150-331">在 Jamf Pro仪表板中，选择 **"配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-331">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![配置设置配置文件的图像](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="68150-333">选择 **+ 新建**。</span><span class="sxs-lookup"><span data-stu-id="68150-333">Select **+ New**.</span></span>

3. <span data-ttu-id="68150-334">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-334">Enter the following details:</span></span>

    <span data-ttu-id="68150-335">**常规**</span><span class="sxs-lookup"><span data-stu-id="68150-335">**General**</span></span>
    - <span data-ttu-id="68150-336">名称：MDATP MDAV - 授予对 EDR 和 AV 的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="68150-336">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="68150-337">说明：在 macOS 加泰罗尼亚语或更高版本上，新的隐私首选项策略控制</span><span class="sxs-lookup"><span data-stu-id="68150-337">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="68150-338">类别：无</span><span class="sxs-lookup"><span data-stu-id="68150-338">Category: None</span></span>
    - <span data-ttu-id="68150-339">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="68150-339">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="68150-340">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="68150-340">Level: Computer level</span></span>


    ![配置设置常规的图像](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="68150-342">在 **"配置隐私首选项策略控制"中，选择**"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-342">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![配置隐私策略控制的图像](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="68150-344">在 **"隐私首选项策略控制"中**，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-344">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="68150-345">标识符： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="68150-345">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="68150-346">标识符类型：捆绑包 ID</span><span class="sxs-lookup"><span data-stu-id="68150-346">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="68150-347">代码要求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="68150-347">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![配置设置隐私首选项策略控制详细信息的图像](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="68150-349">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-349">Select **+ Add**.</span></span>

    ![配置设置的图像添加系统策略所有文件](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="68150-351">在"应用或服务：设置为 **SystemPolicyAllFiles" 下**</span><span class="sxs-lookup"><span data-stu-id="68150-351">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="68150-352">在"访问"下：设置为 **"允许"**</span><span class="sxs-lookup"><span data-stu-id="68150-352">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="68150-353">选择 **" (** 不是右下角的) 。</span><span class="sxs-lookup"><span data-stu-id="68150-353">Select **Save** (not the one at the bottom right).</span></span>

    ![配置设置保存图像的图像](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="68150-355">单击 `+` "应用访问" **旁边的** 符号添加新条目。</span><span class="sxs-lookup"><span data-stu-id="68150-355">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![配置设置应用访问的图像](images/tcc-add-entry.png)

9. <span data-ttu-id="68150-357">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-357">Enter the following details:</span></span>

    - <span data-ttu-id="68150-358">标识符： `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="68150-358">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="68150-359">标识符类型：捆绑包 ID</span><span class="sxs-lookup"><span data-stu-id="68150-359">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="68150-360">代码要求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="68150-360">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="68150-361">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-361">Select **+ Add**.</span></span>

    ![配置设置 tcc epsext 条目的图像](images/tcc-epsext-entry.png)

    - <span data-ttu-id="68150-363">在"应用或服务：设置为 **SystemPolicyAllFiles" 下**</span><span class="sxs-lookup"><span data-stu-id="68150-363">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="68150-364">在"访问"下：设置为 **"允许"**</span><span class="sxs-lookup"><span data-stu-id="68150-364">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="68150-365">选择 **" (** 不是右下角的) 。</span><span class="sxs-lookup"><span data-stu-id="68150-365">Select **Save** (not the one at the bottom right).</span></span>

    ![配置设置 tcc epsext 图像 2 的图像](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="68150-367">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-367">Select the **Scope** tab.</span></span>

    ![配置设置作用域的图像](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="68150-369">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-369">Select **+ Add**.</span></span>

    ![配置设置 addimage 的图像](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="68150-371">Select **Computer Groups** > under Group Name **>** select **Contoso's MachineGroup**.</span><span class="sxs-lookup"><span data-stu-id="68150-371">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span>

    ![配置设置 contoso machinegrp 的图像](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="68150-373">选择“添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-373">Select **Add**.</span></span>

16. <span data-ttu-id="68150-374">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-374">Select **Save**.</span></span>

17. <span data-ttu-id="68150-375">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-375">Select **Done**.</span></span>

    ![配置设置的图像](images/809cef630281b64b8f07f20913b0039b.png)

    ![配置设置 donimg2 的图像](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="68150-378">或者，你可以下载[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)并将其上载到 JAMF 配置文件，如使用 Jamf 配置部署自定义[配置文件Pro|方法 2：Upload配置文件为 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="68150-378">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="68150-379">步骤 7：批准适用于终结点的 Microsoft Defender 内核扩展</span><span class="sxs-lookup"><span data-stu-id="68150-379">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="68150-380">Apple 芯片 (M1) 设备不支持 KEXT。</span><span class="sxs-lookup"><span data-stu-id="68150-380">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="68150-381">在这些设备上安装包含 KEXT 策略的配置文件将失败。</span><span class="sxs-lookup"><span data-stu-id="68150-381">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="68150-382">在"**配置文件"中**，选择 **"+ 新建"。**</span><span class="sxs-lookup"><span data-stu-id="68150-382">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自动生成的社交媒体文章描述的屏幕截图](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="68150-384">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-384">Enter the following details:</span></span>

    <span data-ttu-id="68150-385">**常规**</span><span class="sxs-lookup"><span data-stu-id="68150-385">**General**</span></span>

    - <span data-ttu-id="68150-386">名称：MDATP MDAV 内核扩展</span><span class="sxs-lookup"><span data-stu-id="68150-386">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="68150-387">说明：kext (MDATP 内核) </span><span class="sxs-lookup"><span data-stu-id="68150-387">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="68150-388">类别：无</span><span class="sxs-lookup"><span data-stu-id="68150-388">Category: None</span></span>
    - <span data-ttu-id="68150-389">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="68150-389">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="68150-390">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="68150-390">Level: Computer Level</span></span>

    ![配置设置 mdatpmdav 内核的图像](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="68150-392">在 **"配置批准的内核扩展"中，选择**"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-392">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![批准的内核扩展的配置设置的图像](images/30be88b63abc5e8dde11b73f1b1ade6a.png)


4. <span data-ttu-id="68150-394">在 **"已批准内核扩展"** 中 输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-394">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="68150-395">显示名称：Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="68150-395">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="68150-396">团队 ID：UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="68150-396">Team ID: UBF8T346G9</span></span>

    ![配置设置应用程序内核扩展的图像](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="68150-398">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-398">Select the **Scope** tab.</span></span>

    ![配置设置范围选项卡 img 的图像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="68150-400">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-400">Select **+ Add**.</span></span>

7. <span data-ttu-id="68150-401">Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.</span><span class="sxs-lookup"><span data-stu-id="68150-401">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="68150-402">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-402">Select **+ Add**.</span></span>

    ![配置设置添加映像的图像](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="68150-404">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-404">Select **Save**.</span></span>

    ![配置设置保存映像](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="68150-406">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-406">Select **Done**.</span></span>

    ![配置设置完成映像的图像](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="68150-408">或者，你可以下载[kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig)并将其上载到 JAMF 配置文件，如使用 Jamf 配置部署自定义[配置文件Pro|方法 2：Upload配置文件为 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="68150-408">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="68150-409">步骤 8：批准适用于终结点的 Microsoft Defender 的系统扩展</span><span class="sxs-lookup"><span data-stu-id="68150-409">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="68150-410">在"**配置文件"中**，选择 **"+ 新建"。**</span><span class="sxs-lookup"><span data-stu-id="68150-410">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自动生成的社交媒体文章描述的屏幕截图](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="68150-412">输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-412">Enter the following details:</span></span>

    <span data-ttu-id="68150-413">**常规**</span><span class="sxs-lookup"><span data-stu-id="68150-413">**General**</span></span>

    - <span data-ttu-id="68150-414">名称：MDATP MDAV 系统扩展</span><span class="sxs-lookup"><span data-stu-id="68150-414">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="68150-415">说明：MDATP 系统扩展</span><span class="sxs-lookup"><span data-stu-id="68150-415">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="68150-416">类别：无</span><span class="sxs-lookup"><span data-stu-id="68150-416">Category: None</span></span>
    - <span data-ttu-id="68150-417">分发方法：自动安装</span><span class="sxs-lookup"><span data-stu-id="68150-417">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="68150-418">级别：计算机级别</span><span class="sxs-lookup"><span data-stu-id="68150-418">Level: Computer Level</span></span>

    ![配置设置的图像 sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="68150-420">在 **"系统扩展"中，** 选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-420">In **System Extensions** select **Configure**.</span></span>

   ![配置设置 sysext 配置的图像](images/sysext-configure.png)

4. <span data-ttu-id="68150-422">在 **"系统扩展"** 中，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-422">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="68150-423">显示名称：Microsoft Corp. 系统扩展</span><span class="sxs-lookup"><span data-stu-id="68150-423">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="68150-424">系统扩展类型：允许的系统扩展</span><span class="sxs-lookup"><span data-stu-id="68150-424">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="68150-425">团队标识符：UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="68150-425">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="68150-426">允许的系统扩展：</span><span class="sxs-lookup"><span data-stu-id="68150-426">Allowed System Extensions:</span></span>
     - <span data-ttu-id="68150-427">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="68150-427">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="68150-428">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="68150-428">**com.microsoft.wdav.netext**</span></span>

    ![配置设置的图像 sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="68150-430">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-430">Select the **Scope** tab.</span></span>

    ![配置设置作用域映像的图像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="68150-432">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-432">Select **+ Add**.</span></span>

7. <span data-ttu-id="68150-433">Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.</span><span class="sxs-lookup"><span data-stu-id="68150-433">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="68150-434">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-434">Select **+ Add**.</span></span>

   ![配置设置 addima 的图像](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="68150-436">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-436">Select **Save**.</span></span>

   ![配置设置 sysext 作用域的图像](images/sysext-scope.png)

10. <span data-ttu-id="68150-438">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-438">Select **Done**.</span></span>

    ![配置设置的图像 sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="68150-440">步骤 9：配置网络扩展</span><span class="sxs-lookup"><span data-stu-id="68150-440">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="68150-441">作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心 门户。</span><span class="sxs-lookup"><span data-stu-id="68150-441">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="68150-442">以下策略允许网络扩展执行此功能。</span><span class="sxs-lookup"><span data-stu-id="68150-442">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="68150-443">这些步骤适用于加泰罗尼亚语或 (macOS 10.15) macOS 10.15。</span><span class="sxs-lookup"><span data-stu-id="68150-443">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="68150-444">在 Jamf Pro仪表板中，选择 **"计算机**"，然后选择"**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="68150-444">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="68150-445">单击 **"新建**"，然后为"选项"输入以下 **详细信息**：</span><span class="sxs-lookup"><span data-stu-id="68150-445">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="68150-446">常规 **选项卡**：</span><span class="sxs-lookup"><span data-stu-id="68150-446">Tab **General**:</span></span>
        - <span data-ttu-id="68150-447">**名称**：Microsoft Defender ATP 网络扩展</span><span class="sxs-lookup"><span data-stu-id="68150-447">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="68150-448">**说明**：macOS 10.15 (加泰罗尼亚语) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="68150-448">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="68150-449">**类别**： *默认 (无)*</span><span class="sxs-lookup"><span data-stu-id="68150-449">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="68150-450">**分发方法**：使用默认 *(自动)*</span><span class="sxs-lookup"><span data-stu-id="68150-450">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="68150-451">**级别**：计算机级别 *(默认)*</span><span class="sxs-lookup"><span data-stu-id="68150-451">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="68150-452">选项卡 **内容筛选器**：</span><span class="sxs-lookup"><span data-stu-id="68150-452">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="68150-453">**筛选器名称**：Microsoft Defender ATP 内容筛选器</span><span class="sxs-lookup"><span data-stu-id="68150-453">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="68150-454">**标识符**： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="68150-454">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="68150-455">将 **服务地址\*\*\*\*、组织、\*\*\*\*用户名**、**密码**、**证书** 留空 (\**包括\*\*\*未* 选中) </span><span class="sxs-lookup"><span data-stu-id="68150-455">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="68150-456">**筛选顺序**：检查器</span><span class="sxs-lookup"><span data-stu-id="68150-456">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="68150-457">**套接字筛选器**： `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="68150-457">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="68150-458">**套接字筛选器指定要求**： `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="68150-458">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="68150-459">如果 **"包含"** 未 **(，则"** 网络筛选器 *"* 字段留空) </span><span class="sxs-lookup"><span data-stu-id="68150-459">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="68150-460">请注意，**上述标识符\*\*\*\*、套接字** 筛选器 **和套接字筛选器指定要求** 的确切值。</span><span class="sxs-lookup"><span data-stu-id="68150-460">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![配置设置 mdatpmdav 的图像](images/netext-create-profile.png)

3. <span data-ttu-id="68150-462">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-462">Select the **Scope** tab.</span></span>

   ![配置设置标签页的图像](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="68150-464">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-464">Select **+ Add**.</span></span>

5. <span data-ttu-id="68150-465">Select **Computer Groups** > under Group Name **>** select **Contoso's Machine Group**.</span><span class="sxs-lookup"><span data-stu-id="68150-465">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="68150-466">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-466">Select **+ Add**.</span></span>

    ![配置设置 adim 的图像](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="68150-468">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-468">Select **Save**.</span></span>

    ![配置设置 savimg netextscop 的图像](images/netext-scope.png)

8. <span data-ttu-id="68150-470">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-470">Select **Done**.</span></span>

    ![配置设置图像 netextfinal](images/netext-final.png)

<span data-ttu-id="68150-472">或者，你可以下载[netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)并将其上载到 JAMF 配置文件，如使用 Jamf 配置部署自定义[配置文件Pro|方法 2：Upload配置文件为 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。</span><span class="sxs-lookup"><span data-stu-id="68150-472">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="68150-473">步骤 10：在 macOS 上使用 Microsoft Defender for Endpoint 计划扫描</span><span class="sxs-lookup"><span data-stu-id="68150-473">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="68150-474">按照在 [macOS 上使用 Microsoft Defender for Endpoint 计划扫描的说明操作](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)。</span><span class="sxs-lookup"><span data-stu-id="68150-474">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="68150-475">步骤 11：在 macOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="68150-475">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="68150-476">导航到保存的位置 `wdav.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="68150-476">Navigate to where you saved `wdav.pkg`.</span></span>

    ![文件资源管理器 wdav pkg 的图像](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="68150-478">将其重命名为 `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="68150-478">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![文件资源管理器1 wdavmdmpkg 的图像](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="68150-480">打开 Jamf Pro仪表板。</span><span class="sxs-lookup"><span data-stu-id="68150-480">Open the Jamf Pro dashboard.</span></span>

    ![配置设置 jamfpro 的图像](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="68150-482">选择您的计算机，然后单击顶部的齿轮图标，然后选择计算机 **管理**。</span><span class="sxs-lookup"><span data-stu-id="68150-482">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![配置设置 compmgmt 的图像](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="68150-484">在 **"程序包"** 中，选择 **"+ 新建"。**</span><span class="sxs-lookup"><span data-stu-id="68150-484">In **Packages**, select **+ New**.</span></span>
    <span data-ttu-id="68150-485">![包含鸟描述的图片自动生成程序包新建](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="68150-485">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="68150-486">在 **"新建程序包"** 中 输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-486">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="68150-487">**"常规"选项卡**</span><span class="sxs-lookup"><span data-stu-id="68150-487">**General tab**</span></span>
    - <span data-ttu-id="68150-488">显示名称：现在保留为空。</span><span class="sxs-lookup"><span data-stu-id="68150-488">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="68150-489">因为它将在你选择 pkg 时重置。</span><span class="sxs-lookup"><span data-stu-id="68150-489">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="68150-490">类别：默认 (无) </span><span class="sxs-lookup"><span data-stu-id="68150-490">Category: None (default)</span></span>
    - <span data-ttu-id="68150-491">文件名：选择"文件"</span><span class="sxs-lookup"><span data-stu-id="68150-491">Filename: Choose File</span></span>

    ![配置设置常规选项卡的图像](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="68150-493">打开 文件，并指向 `wdav.pkg` 或 `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="68150-493">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![自动生成的计算机屏幕描述的屏幕截图](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="68150-495">选择 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="68150-495">Select **Open**.</span></span> <span data-ttu-id="68150-496">将显示 **名称设置为** **Microsoft Defender 高级威胁防护，Microsoft Defender 防病毒。**</span><span class="sxs-lookup"><span data-stu-id="68150-496">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="68150-497">**清单文件** 不是必需的。</span><span class="sxs-lookup"><span data-stu-id="68150-497">**Manifest File** is not required.</span></span> <span data-ttu-id="68150-498">Microsoft Defender for Endpoint 在无清单文件的情况下工作。</span><span class="sxs-lookup"><span data-stu-id="68150-498">Microsoft Defender for Endpoint works without Manifest File.</span></span>

    <span data-ttu-id="68150-499">**选项选项卡**</span><span class="sxs-lookup"><span data-stu-id="68150-499">**Options tab**</span></span><br> <span data-ttu-id="68150-500">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="68150-500">Keep default values.</span></span>

    <span data-ttu-id="68150-501">**"限制"选项卡**</span><span class="sxs-lookup"><span data-stu-id="68150-501">**Limitations tab**</span></span><br> <span data-ttu-id="68150-502">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="68150-502">Keep default values.</span></span>

     ![配置设置限制选项卡的图像](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. <span data-ttu-id="68150-504">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-504">Select **Save**.</span></span> <span data-ttu-id="68150-505">程序包将上载到 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="68150-505">The package is uploaded to Jamf Pro.</span></span>

   ![配置设置包 upl jamf pro 的图像](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="68150-507">可能需要几分钟时间，程序包才能可用于部署。</span><span class="sxs-lookup"><span data-stu-id="68150-507">It can take a few minutes for the package to be available for deployment.</span></span>

   ![配置设置包 upl 的图像](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="68150-509">导航到" **策略"** 页。</span><span class="sxs-lookup"><span data-stu-id="68150-509">Navigate to the **Policies** page.</span></span>

    ![配置设置要求的图像](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="68150-511">选择 **+ 新建** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="68150-511">Select **+ New** to create a new policy.</span></span>

    ![配置设置新策略的图像](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="68150-513">在 **"常规** "中 输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="68150-513">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="68150-514">显示名称：MDATP 载入 Contoso 200329 v100.86.92 或更高版本</span><span class="sxs-lookup"><span data-stu-id="68150-514">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![配置设置mdatponboard的图像](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="68150-516">选择 **"定期签入"。**</span><span class="sxs-lookup"><span data-stu-id="68150-516">Select **Recurring Check-in**.</span></span>

    ![配置设置重复签入的图像](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)


13. <span data-ttu-id="68150-518">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-518">Select **Save**.</span></span>

14. <span data-ttu-id="68150-519">选择 **">配置"。**</span><span class="sxs-lookup"><span data-stu-id="68150-519">Select **Packages > Configure**.</span></span>

    ![配置设置包配置的图像](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="68150-521">选择 **Microsoft** Defender 高级威胁防护旁边的添加按钮 **Microsoft Defender 防病毒。**</span><span class="sxs-lookup"><span data-stu-id="68150-521">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![配置设置 MDATP 和 MDA 添加的图像](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="68150-523">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="68150-523">Select **Save**.</span></span>

    ![配置设置的图像avimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="68150-525">选择" **范围"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68150-525">Select the **Scope** tab.</span></span>

    ![配置设置 scptab 的图像](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="68150-527">选择目标计算机。</span><span class="sxs-lookup"><span data-stu-id="68150-527">Select the target computers.</span></span>

    ![配置设置 tgtcomp 的图像](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="68150-529">**Scope**</span><span class="sxs-lookup"><span data-stu-id="68150-529">**Scope**</span></span>

    <span data-ttu-id="68150-530">选择“添加”。</span><span class="sxs-lookup"><span data-stu-id="68150-530">Select **Add**.</span></span>

    ![配置设置 ad1img 的图像](images/1c08d097829863778d562c10c5f92b67.png)

    ![配置设置 ad2img 的图像](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="68150-533">**自助服务**</span><span class="sxs-lookup"><span data-stu-id="68150-533">**Self-Service**</span></span>

    ![配置设置自服务的图像](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="68150-535">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="68150-535">Select **Done**.</span></span>

    ![配置设置 do1img 的图像](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![配置设置 do2img 的图像](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




