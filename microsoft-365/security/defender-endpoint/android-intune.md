---
title: 使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint
description: 介绍如何使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint
keywords: microsoft， defender， atp， mde， android， 安装， 部署， 卸载，
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 350345acbaadcdd6bc8ef901f03c419a7f8decff
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687717"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="51404-104">使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51404-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51404-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="51404-105">**Applies to:**</span></span>
- [<span data-ttu-id="51404-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51404-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51404-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51404-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="51404-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="51404-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51404-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="51404-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="51404-110">了解如何在 Intune 公司门户注册的设备上部署适用于 Android 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="51404-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="51404-111">有关 Intune 设备注册详细信息，请参阅  [注册设备](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="51404-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="51404-112">**适用于 Android 的 Defender for Endpoint 现已在 [Google Play 上可用](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="51404-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="51404-113">你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android 企业版注册模式部署 Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="51404-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="51404-114">通过 Google Play 自动更新应用。</span><span class="sxs-lookup"><span data-stu-id="51404-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="51404-115">在设备管理员注册的设备上部署</span><span class="sxs-lookup"><span data-stu-id="51404-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="51404-116">**在 Intune 公司门户上部署适用于 Android 的 Defender for Endpoint - 设备管理员注册的设备**</span><span class="sxs-lookup"><span data-stu-id="51404-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="51404-117">了解如何在 Intune 公司门户上部署适用于 Android 的 Defender for Endpoint - 设备管理员注册的设备。</span><span class="sxs-lookup"><span data-stu-id="51404-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="51404-118">添加为 Android 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="51404-118">Add as Android store app</span></span>

1. <span data-ttu-id="51404-119">在 [Microsoft Endpoint Manager 管理中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **"应用""Android** \> **应用** \> **""添加 \> Android 应用商店"应用**，然后选择"**选择"。**</span><span class="sxs-lookup"><span data-stu-id="51404-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Microsoft Endpoint Manager 管理中心添加 android 应用商店应用程序的图像](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="51404-121">在" **添加应用程序"页** 的"应用程序信息"部分 *，输入* ：</span><span class="sxs-lookup"><span data-stu-id="51404-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="51404-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="51404-122">**Name**</span></span> 
   - <span data-ttu-id="51404-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="51404-123">**Description**</span></span>
   - <span data-ttu-id="51404-124">**作为** Microsoft 发布服务器。</span><span class="sxs-lookup"><span data-stu-id="51404-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="51404-125">**作为 Defender** for https://play.google.com/store/apps/details?id=com.microsoft.scmx Endpoint (的应用商店 URL Google Play 应用商店 URL) </span><span class="sxs-lookup"><span data-stu-id="51404-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="51404-126">其他字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="51404-126">Other fields are optional.</span></span> <span data-ttu-id="51404-127">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="51404-127">Select **Next**.</span></span>

   ![Microsoft Endpoint Manager 管理中心添加应用信息的图像](images/mda-addappinfo.png)

3. <span data-ttu-id="51404-129">在" *分配"* 部分，转到" **必需"** 部分并选择" **添加组"。**</span><span class="sxs-lookup"><span data-stu-id="51404-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="51404-130">然后，你可以选择要面向适用于 Android (Defender) 的用户组策略。</span><span class="sxs-lookup"><span data-stu-id="51404-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="51404-131">选择 **"选择**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="51404-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="51404-132">所选用户组应由 Intune 注册的用户组成。</span><span class="sxs-lookup"><span data-stu-id="51404-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Microsoft Endpoint Manager 管理中心选定用户组的图像](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="51404-134">在"**审阅+创建**"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="51404-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="51404-135">片刻后，将成功创建 Defender for Endpoint 应用，页面右上角将显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="51404-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Defender 终结点应用的 Microsoft Endpoint Manager 管理中心通知的图像](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="51404-137">在显示的"应用信息"页的"监视器"部分，选择"设备安装状态"以验证设备安装是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="51404-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-138">![Microsoft Endpoint Manager 管理中心设备安装的图像](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="51404-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="51404-139">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="51404-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="51404-140">在设备上安装适用于 Android 的 Defender for Endpoint 后，你将看到应用图标。</span><span class="sxs-lookup"><span data-stu-id="51404-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![移动设备上的图标](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="51404-142">点击 Microsoft Defender ATP 应用图标并按照屏幕上的说明完成应用载入。</span><span class="sxs-lookup"><span data-stu-id="51404-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="51404-143">详细信息包括最终用户接受 Defender for Endpoint for Android 所需的 Android 权限。</span><span class="sxs-lookup"><span data-stu-id="51404-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="51404-144">成功载入后，设备将开始显示在 Microsoft Defender 安全中心的"设备"列表上。</span><span class="sxs-lookup"><span data-stu-id="51404-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Defender for Endpoint 门户中的设备图像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="51404-146">在 Android 企业版注册的设备上部署</span><span class="sxs-lookup"><span data-stu-id="51404-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="51404-147">适用于 Android 的 Defender for Endpoint 支持 Android 企业版注册的设备。</span><span class="sxs-lookup"><span data-stu-id="51404-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="51404-148">有关 Intune 支持的注册选项的详细信息，请参阅 [注册选项](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)。</span><span class="sxs-lookup"><span data-stu-id="51404-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="51404-149">**目前，支持部署具有工作配置文件和公司所有完全托管用户设备注册的个人拥有设备。**</span><span class="sxs-lookup"><span data-stu-id="51404-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="51404-150">将 Android 上的 Microsoft Defender for Endpoint 添加为托管 Google Play 应用</span><span class="sxs-lookup"><span data-stu-id="51404-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="51404-151">按照以下步骤将 Microsoft Defender for Endpoint 应用添加到托管 Google Play。</span><span class="sxs-lookup"><span data-stu-id="51404-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="51404-152">在 [Microsoft Endpoint Manager 管理中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **"应用""Android** \> **应用** \> **""添加**"，然后选择 **"托管 Google Play 应用"。**</span><span class="sxs-lookup"><span data-stu-id="51404-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-153">![Microsoft Endpoint Manager 管理中心托管 google play 的图像](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="51404-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="51404-154">在随后加载的托管 Google Play 页面上，转到搜索框并查找 **Microsoft Defender。**</span><span class="sxs-lookup"><span data-stu-id="51404-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="51404-155">你的搜索应在托管 Google Play 中显示 Microsoft Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="51404-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="51404-156">从应用搜索结果中单击 Microsoft Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="51404-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Microsoft Endpoint Manager 管理中心应用搜索的图像](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="51404-158">在接下来启动的应用描述页面中，你应该能够看到 Defender for Endpoint 上的应用详细信息。</span><span class="sxs-lookup"><span data-stu-id="51404-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="51404-159">查看页面上的信息，然后选择"批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="51404-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-160">![托管 Google Play 的屏幕截图](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="51404-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="51404-161">你将看到 Defender for Endpoint 为它工作获取的权限。</span><span class="sxs-lookup"><span data-stu-id="51404-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="51404-162">查看它们，然后选择"批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="51404-162">Review them and then select **Approve**.</span></span>

    ![适用于终结点预览应用审批的 Defender 屏幕截图](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="51404-164">You'll be presented with the Approval settings page.</span><span class="sxs-lookup"><span data-stu-id="51404-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="51404-165">此页面确认你优先处理 Defender for Endpoint for Android 可能要求的新应用权限。</span><span class="sxs-lookup"><span data-stu-id="51404-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="51404-166">查看选项并选择首选选项。</span><span class="sxs-lookup"><span data-stu-id="51404-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="51404-167">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="51404-167">Select **Done**.</span></span>

    <span data-ttu-id="51404-168">默认情况下，托管 Google Play 在应用请求新权限时 *选择"保持已批准"*</span><span class="sxs-lookup"><span data-stu-id="51404-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-169">![通知选项卡的图像](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="51404-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="51404-170">完成权限处理选择后，选择" **同步** "以将 Microsoft Defender for Endpoint 同步到应用列表。</span><span class="sxs-lookup"><span data-stu-id="51404-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-171">![同步页面图像](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="51404-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="51404-172">同步将在几分钟后完成。</span><span class="sxs-lookup"><span data-stu-id="51404-172">The sync will complete in a few minutes.</span></span>

    ![Android 应用的图像](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="51404-174">选择 **Android 应用** 屏幕中的"刷新"按钮，"应用"列表中应显示 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="51404-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-175">![Android 应用列表的图像](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="51404-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="51404-176">Defender for Endpoint 通过 Intune 支持托管设备的应用配置策略。</span><span class="sxs-lookup"><span data-stu-id="51404-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="51404-177">此功能可用于自动授予适用的 Android () ，因此最终用户无需接受这些 (权限) 。</span><span class="sxs-lookup"><span data-stu-id="51404-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="51404-178">在应用 **页面中** ，转到策略 **>应用配置策略>添加>托管设备**。</span><span class="sxs-lookup"><span data-stu-id="51404-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Microsoft Endpoint Manager 管理中心 android 托管设备的图像](images/android-mem.png)

    1. <span data-ttu-id="51404-180">在" **创建应用配置策略"** 页中，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="51404-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="51404-181">名称：Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="51404-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="51404-182">选择 **"Android 企业** 版"作为平台。</span><span class="sxs-lookup"><span data-stu-id="51404-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="51404-183">选择 **"仅作为配置文件类型** 的工作配置文件"。</span><span class="sxs-lookup"><span data-stu-id="51404-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="51404-184">单击 **"选择应用"，** 选择 **"Microsoft Defender ATP"，** 选择 **"确定**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="51404-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="51404-185">![创建应用配置策略页的图像](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="51404-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="51404-186">在" **设置** "页中，转到"权限"部分，单击"添加"以查看支持的权限列表。</span><span class="sxs-lookup"><span data-stu-id="51404-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="51404-187">在"添加权限"部分，选择以下权限：</span><span class="sxs-lookup"><span data-stu-id="51404-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="51404-188">外部存储 (读取) </span><span class="sxs-lookup"><span data-stu-id="51404-188">External storage (read)</span></span>
       - <span data-ttu-id="51404-189">外部存储 (写入) </span><span class="sxs-lookup"><span data-stu-id="51404-189">External storage (write)</span></span>

       <span data-ttu-id="51404-190">然后，选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="51404-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="51404-191">![Android 创建应用配置策略的图像](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="51404-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="51404-192">现在应该可以看到列出的权限，现在可以通过在"权限状态"下拉列表中选择"自动授予"，然后选择"下一步"来自动 **授予这两种权限**。</span><span class="sxs-lookup"><span data-stu-id="51404-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="51404-193">![Android 自动授予创建应用配置策略的图像](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="51404-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="51404-194">在 **"分配** "页中，选择此应用配置策略将分配到的用户组。</span><span class="sxs-lookup"><span data-stu-id="51404-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="51404-195">单击 **"选择要包含的组"** 并选择适用的组，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="51404-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="51404-196">在此处选择的组通常是你将 Microsoft Defender for Endpoint Android 应用分配到的同一个组。</span><span class="sxs-lookup"><span data-stu-id="51404-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="51404-197">![创建应用配置策略的图像](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="51404-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="51404-198">In the **Review + Create** page that comes up next， review all the information and then select **Create**.</span><span class="sxs-lookup"><span data-stu-id="51404-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="51404-199">Defender for Endpoint 的应用配置策略（自动授予存储权限）现在分配给所选用户组。</span><span class="sxs-lookup"><span data-stu-id="51404-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="51404-200">![Android 评价创建应用配置策略的图像](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="51404-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="51404-201">在 **"属性分配编辑"列表中选择"Microsoft Defender ATP** \>  \>  \> **应用"。**</span><span class="sxs-lookup"><span data-stu-id="51404-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![应用列表的图像](images/mda-properties.png)


11. <span data-ttu-id="51404-203">将应用分配为 *用户组所需的* 应用。</span><span class="sxs-lookup"><span data-stu-id="51404-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="51404-204">它通过公司门户 *应用* 在设备下次同步期间自动安装在工作配置文件中。</span><span class="sxs-lookup"><span data-stu-id="51404-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="51404-205">此分配可通过导航到"必需"部分"添加组"，选择用户组并单击" \> 选择 **"完成**。</span><span class="sxs-lookup"><span data-stu-id="51404-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-206">![编辑应用程序页的图像](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="51404-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="51404-207">在" **编辑应用程序"** 页中，查看上面输入的所有信息。</span><span class="sxs-lookup"><span data-stu-id="51404-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="51404-208">然后选择" **审阅 + 保存** "，然后 **再次"保存** "以开始工作分配。</span><span class="sxs-lookup"><span data-stu-id="51404-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="51404-209">自动设置始终打开 VPN</span><span class="sxs-lookup"><span data-stu-id="51404-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="51404-210">Defender for Endpoint 通过 Intune 支持托管设备的设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="51404-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="51404-211">此功能可用于在 Android 企业版注册设备上自动设置始终打开 **VPN，** 因此最终用户无需在载入时设置 VPN 服务。</span><span class="sxs-lookup"><span data-stu-id="51404-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="51404-212">在 **"设备"上**，根据设备注册类型，选择"配置文件  >  **""** 创建配置文件平台  >    >  **""Android 企业** 版"，选择以下其中一项下的设备限制</span><span class="sxs-lookup"><span data-stu-id="51404-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="51404-213">**完全托管、专用Corporate-Owned工作配置文件**</span><span class="sxs-lookup"><span data-stu-id="51404-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="51404-214">**个人拥有的工作配置文件**</span><span class="sxs-lookup"><span data-stu-id="51404-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="51404-215">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="51404-215">Select **Create**.</span></span>
 
   > ![创建设备配置文件的图像](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="51404-217">**配置设置** 提供 **用于唯** 一 **标识** 配置文件的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="51404-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![设备配置文件名称和说明的图像](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="51404-219">选择 **连接** 并配置 VPN：</span><span class="sxs-lookup"><span data-stu-id="51404-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="51404-220">启用 **始终启用 VPN** 在工作配置文件中设置 VPN 客户端，尽可能自动连接和重新连接到 VPN。</span><span class="sxs-lookup"><span data-stu-id="51404-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="51404-221">在给定设备上只能为始终打开的 VPN 配置一个 VPN 客户端，因此请确保将始终打开的 VPN 策略部署到单个设备不超过一个。</span><span class="sxs-lookup"><span data-stu-id="51404-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="51404-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span><span class="sxs-lookup"><span data-stu-id="51404-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="51404-223">Microsoft Defender ATP 应用必须安装在用户设备上，才能自动设置此 VPN。</span><span class="sxs-lookup"><span data-stu-id="51404-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="51404-224">在 **Google** Play 应用商店中输入 Microsoft Defender ATP 应用的程序包 ID。</span><span class="sxs-lookup"><span data-stu-id="51404-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="51404-225">对于 Defender 应用 https://play.google.com/store/apps/details?id=com.microsoft.scmx URL，程序包 ID 为 **com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="51404-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="51404-226">**锁定模式** 未配置 (默认) </span><span class="sxs-lookup"><span data-stu-id="51404-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![设备配置文件图像启用始终启用 VPN](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="51404-228">**工作分配** 在  **"分配**   "页中，选择此应用配置策略将分配到的用户组。</span><span class="sxs-lookup"><span data-stu-id="51404-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="51404-229">单击 **"选择要包含** 的组"并选择适用的组，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="51404-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="51404-230">在此处选择的组通常是你将 Microsoft Defender for Endpoint Android 应用分配到的同一个组。</span><span class="sxs-lookup"><span data-stu-id="51404-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![设备配置文件分配的图像](images/4autosetupofvpn.png)

5. <span data-ttu-id="51404-232">In the **Review + Create** page that comes up next， review all the information and then select **Create**.</span><span class="sxs-lookup"><span data-stu-id="51404-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="51404-233">现在，设备配置文件已分配给选定的用户组。</span><span class="sxs-lookup"><span data-stu-id="51404-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![设备配置文件的图像 查看和创建](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="51404-235">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="51404-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="51404-236">通过单击"设备安装状态"确认 Android 上的 Microsoft Defender for Endpoint **的安装状态**。</span><span class="sxs-lookup"><span data-stu-id="51404-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="51404-237">验证设备是否在此处显示。</span><span class="sxs-lookup"><span data-stu-id="51404-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51404-238">![设备安装状态的图像](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="51404-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="51404-239">在设备上，可以通过进入工作配置文件来验证载入 **状态**。</span><span class="sxs-lookup"><span data-stu-id="51404-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="51404-240">确认适用于终结点的 Defender 可用，并且你已使用工作配置文件 注册到个人 **拥有的设备**。</span><span class="sxs-lookup"><span data-stu-id="51404-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="51404-241">如果你注册了企业拥有、完全 **托管的用户设备**，你将在设备上拥有一个配置文件，你可以确认 Defender for Endpoint 可用。</span><span class="sxs-lookup"><span data-stu-id="51404-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![移动设备上应用的图像](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="51404-243">安装应用后，打开应用并接受权限，然后载入应该会成功。</span><span class="sxs-lookup"><span data-stu-id="51404-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![使用 Microsoft Defender for Endpoint 应用的移动设备的图像](images/mda-devicesafe.png)

4. <span data-ttu-id="51404-245">在此阶段，设备已成功载入到适用于 Android 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="51404-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="51404-246">你可以导航到设备页面，在 [Microsoft Defender 安全](https://securitycenter.microsoft.com)**中心验证这一** 点。</span><span class="sxs-lookup"><span data-stu-id="51404-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![适用于终结点的 Microsoft Defender 门户的图像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="51404-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="51404-248">Related topics</span></span>
- [<span data-ttu-id="51404-249">Android 上的 Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="51404-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="51404-250">在 Android 功能上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51404-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
