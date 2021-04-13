---
title: 适用于 iOS 的 Microsoft Defender ATP 的基于应用的部署
ms.reviewer: ''
description: 介绍如何使用应用部署适用于 iOS 的 Microsoft Defender ATP
keywords: microsoft， defender， atp， ios， 应用， 安装， 部署， 卸载， intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6cfd2953e752ed9c96f7f16a3ec7ea1fd8862ab2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689733"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="fee8a-104">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fee8a-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fee8a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fee8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="fee8a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fee8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fee8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fee8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fee8a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="fee8a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fee8a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="fee8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fee8a-110">本主题介绍在 Intune 公司门户注册设备上部署适用于 iOS 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="fee8a-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="fee8a-111">有关 Intune 设备注册详细信息，请参阅在 Intune 中注册 [iOS/iPadOS 设备](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="fee8a-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fee8a-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="fee8a-112">Before you begin</span></span>

- <span data-ttu-id="fee8a-113">确保你有权访问 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="fee8a-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="fee8a-114">确保为用户完成了 iOS 注册。</span><span class="sxs-lookup"><span data-stu-id="fee8a-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="fee8a-115">用户需要分配有 Defender for Endpoint 许可证才能使用适用于 iOS 的终结点的 Defender。</span><span class="sxs-lookup"><span data-stu-id="fee8a-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="fee8a-116">有关如何 [分配许可证的说明，](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 请参阅向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="fee8a-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="fee8a-117">Microsoft Defender ATP (适用于适用于 iOS) 的 Microsoft Defender ATP 现已在 [Apple App Store 中提供](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="fee8a-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="fee8a-118">部署步骤</span><span class="sxs-lookup"><span data-stu-id="fee8a-118">Deployment steps</span></span>

<span data-ttu-id="fee8a-119">通过 Intune 公司门户部署适用于 iOS 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="fee8a-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="fee8a-120">添加 iOS 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="fee8a-120">Add iOS store app</span></span>

1. <span data-ttu-id="fee8a-121">在 [Microsoft Endpoint Manager 管理中心，](https://go.microsoft.com/fwlink/?linkid=2109431)转到 **应用**  ->  **iOS/iPadOS**  ->  **添加**  ->  **iOS 应用商店应用**，然后单击选择 。 </span><span class="sxs-lookup"><span data-stu-id="fee8a-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-122">![Microsoft Endpoint Manager 管理中心的图像1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="fee8a-123">在"添加应用"页上，单击" **搜索应用商店"，** 在 **搜索栏中** 键入 Microsoft Defender 终结点。</span><span class="sxs-lookup"><span data-stu-id="fee8a-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="fee8a-124">在搜索结果部分中，单击 Microsoft *Defender 终结点* ，然后单击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="fee8a-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="fee8a-125">选择 **iOS 11.0** 作为最低操作系统。</span><span class="sxs-lookup"><span data-stu-id="fee8a-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="fee8a-126">查看有关应用的其他信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fee8a-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="fee8a-127">在"*分配"* 部分，转到"**必填"部分**，然后选择"**添加组"。**</span><span class="sxs-lookup"><span data-stu-id="fee8a-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="fee8a-128">然后，你可以选择要面向适用于 iOS (Defender) 的用户组。</span><span class="sxs-lookup"><span data-stu-id="fee8a-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="fee8a-129">单击 **"选择**"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="fee8a-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fee8a-130">所选用户组应由 Intune 注册的用户组成。</span><span class="sxs-lookup"><span data-stu-id="fee8a-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-131">![Microsoft Endpoint Manager 管理中心 2 的图像](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="fee8a-132">在"*审阅 + 创建*"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fee8a-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="fee8a-133">片刻后，应成功创建 Defender for Endpoint 应用，并且页面右上角会显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="fee8a-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="fee8a-134">在显示的"应用信息"页的"监视器"部分，选择"设备安装状态"以验证设备安装是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="fee8a-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-135">![Microsoft Endpoint Manager 管理中心的图像3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="fee8a-136">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="fee8a-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="fee8a-137">在设备上安装适用于 iOS 的 Defender for Endpoint 后，你将看到应用图标。</span><span class="sxs-lookup"><span data-stu-id="fee8a-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![自动生成的智能手机说明的屏幕截图](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="fee8a-139">点击 Defender for Endpoint 应用图标并按照屏幕上的说明完成载入步骤。</span><span class="sxs-lookup"><span data-stu-id="fee8a-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="fee8a-140">详细信息包括最终用户接受 Defender for Endpoint for iOS 所需的 iOS 权限。</span><span class="sxs-lookup"><span data-stu-id="fee8a-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="fee8a-141">成功载入后，设备将开始显示在 Microsoft Defender 安全中心的"设备"列表上。</span><span class="sxs-lookup"><span data-stu-id="fee8a-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-142">![自动生成的手机描述的屏幕截图](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="fee8a-143">配置适用于监督模式的 Microsoft Defender 终结点</span><span class="sxs-lookup"><span data-stu-id="fee8a-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="fee8a-144">鉴于平台在这些类型的设备上提供的管理功能已增强，iOS 上的 Microsoft Defender for Endpoint 应用在受监督的 iOS/iPadOS 设备上具有专门的功能。</span><span class="sxs-lookup"><span data-stu-id="fee8a-144">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="fee8a-145">若要充分利用这些功能，适用于终结点的 Defender 应用需要知道设备是否位于监督模式下。</span><span class="sxs-lookup"><span data-stu-id="fee8a-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="fee8a-146">通过 Intune 配置监督模式</span><span class="sxs-lookup"><span data-stu-id="fee8a-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="fee8a-147">Intune 允许你通过应用配置策略配置适用于 iOS 的 Defender 应用。</span><span class="sxs-lookup"><span data-stu-id="fee8a-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fee8a-148">适用于受监督设备的此应用配置策略仅适用于托管设备，并且作为最佳做法应面向所有托管 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="fee8a-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="fee8a-149">登录到 Microsoft [Endpoint Manager 管理中心，](https://go.microsoft.com/fwlink/?linkid=2109431)然后转到 **应用**  >  **应用配置策略**  >  **添加**。</span><span class="sxs-lookup"><span data-stu-id="fee8a-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="fee8a-150">单击 **托管设备**。</span><span class="sxs-lookup"><span data-stu-id="fee8a-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-151">![Microsoft Endpoint Manager 管理中心的图像4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="fee8a-152">在 *"创建应用配置策略"* 页中，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="fee8a-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="fee8a-153">Policy Name</span><span class="sxs-lookup"><span data-stu-id="fee8a-153">Policy Name</span></span>
    - <span data-ttu-id="fee8a-154">平台：选择 iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="fee8a-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="fee8a-155">目标应用：从 **列表中选择 Microsoft Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="fee8a-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-156">![Microsoft Endpoint Manager 管理中心的图像5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="fee8a-157">下一个屏幕中，选择 **"使用配置设计器** "作为格式。</span><span class="sxs-lookup"><span data-stu-id="fee8a-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="fee8a-158">指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="fee8a-158">Specify the following property:</span></span>
    - <span data-ttu-id="fee8a-159">配置密钥：issupervised</span><span class="sxs-lookup"><span data-stu-id="fee8a-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="fee8a-160">值类型：String</span><span class="sxs-lookup"><span data-stu-id="fee8a-160">Value type: String</span></span>
    - <span data-ttu-id="fee8a-161">配置值：{{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="fee8a-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-162">![Microsoft Endpoint Manager 管理中心的图像6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="fee8a-163">单击 **"下** 一步"打开 **"范围标记"** 页。</span><span class="sxs-lookup"><span data-stu-id="fee8a-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="fee8a-164">范围标记是可选的。</span><span class="sxs-lookup"><span data-stu-id="fee8a-164">Scope tags are optional.</span></span> <span data-ttu-id="fee8a-165">单击“下一步”即可继续。</span><span class="sxs-lookup"><span data-stu-id="fee8a-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="fee8a-166">在" **分配** "页上，选择将接收此配置文件的组。</span><span class="sxs-lookup"><span data-stu-id="fee8a-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="fee8a-167">对于此方案，最佳做法是面向 **所有设备**。</span><span class="sxs-lookup"><span data-stu-id="fee8a-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="fee8a-168">有关分配配置文件的信息，请参阅分配 [用户和设备配置文件](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="fee8a-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="fee8a-169">部署到用户组时，用户必须在应用策略之前登录设备。</span><span class="sxs-lookup"><span data-stu-id="fee8a-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="fee8a-170">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="fee8a-170">Click **Next**.</span></span>

1. <span data-ttu-id="fee8a-171">在"**审阅 + 创建**"页上，完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fee8a-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="fee8a-172">新配置文件显示在配置文件列表中。</span><span class="sxs-lookup"><span data-stu-id="fee8a-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="fee8a-173">接下来，为了增强防钓鱼功能，可以在受监督的 iOS 设备上部署自定义配置文件。</span><span class="sxs-lookup"><span data-stu-id="fee8a-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="fee8a-174">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fee8a-174">Follow the steps below:</span></span>
    - <span data-ttu-id="fee8a-175">从下载配置配置文件 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="fee8a-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="fee8a-176">导航到 **设备**  ->  **iOS/iPadOS**  ->  **配置文件**  ->  **创建配置文件**</span><span class="sxs-lookup"><span data-stu-id="fee8a-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fee8a-177">![Microsoft Endpoint Manager 管理中心的图像7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="fee8a-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="fee8a-178">提供配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fee8a-178">Provide a name of the profile.</span></span> <span data-ttu-id="fee8a-179">当系统提示导入配置文件时，请选择上面下载的文件。</span><span class="sxs-lookup"><span data-stu-id="fee8a-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="fee8a-180">在 **"分配** "部分，选择要应用此配置文件的设备组。</span><span class="sxs-lookup"><span data-stu-id="fee8a-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="fee8a-181">最佳做法是，这应该应用于所有托管的 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="fee8a-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="fee8a-182">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="fee8a-182">Click **Next**.</span></span>
    - <span data-ttu-id="fee8a-183">在"**审阅 + 创建**"页上，完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fee8a-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="fee8a-184">新配置文件显示在配置文件列表中。</span><span class="sxs-lookup"><span data-stu-id="fee8a-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fee8a-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fee8a-185">Next Steps</span></span>

[<span data-ttu-id="fee8a-186">为适用于 iOS 功能的终结点配置 Defender</span><span class="sxs-lookup"><span data-stu-id="fee8a-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
