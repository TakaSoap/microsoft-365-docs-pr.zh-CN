---
title: 使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint
description: 介绍如何使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 安装， 部署， 卸载，
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
ms.openlocfilehash: c44993337a6b14dc2fa131de906c5fc6bde28fac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289039"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="0c546-104">使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c546-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c546-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0c546-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c546-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c546-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0c546-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c546-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0c546-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0c546-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c546-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0c546-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0c546-110">了解如何在已注册的设备上在 Android Intune 公司门户 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="0c546-110">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="0c546-111">有关 Intune 设备注册详细信息，请参阅  [注册设备](/mem/intune/user-help/enroll-device-android-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="0c546-111">For more information about Intune device enrollment, see  [Enroll your device](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="0c546-112">**Android 上的 Defender for Endpoint 现已在 [Google Play 上可用](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="0c546-112">**Defender for Endpoint on Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span>
>
> <span data-ttu-id="0c546-113">你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android Enterprise部署 Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="0c546-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise enrollment modes.</span></span>
>
> <span data-ttu-id="0c546-114">通过 Google Play 自动更新应用。</span><span class="sxs-lookup"><span data-stu-id="0c546-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="0c546-115">在设备管理员注册的设备上部署</span><span class="sxs-lookup"><span data-stu-id="0c546-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="0c546-116">**在 Android 设备上部署 Defender for Endpoint Intune 公司门户 - 设备管理员注册的设备**</span><span class="sxs-lookup"><span data-stu-id="0c546-116">**Deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="0c546-117">了解如何在 Android 设备上部署 Defender for Endpoint Intune 公司门户 - 设备管理员注册的设备。</span><span class="sxs-lookup"><span data-stu-id="0c546-117">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices.</span></span>

### <a name="add-as-android-store-app"></a><span data-ttu-id="0c546-118">添加为 Android 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="0c546-118">Add as Android store app</span></span>

1. <span data-ttu-id="0c546-119">In [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431) go to **Apps** \> **Android Apps** Add Android store \> **\> app** and choose **Select**.</span><span class="sxs-lookup"><span data-stu-id="0c546-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![管理中心Microsoft Endpoint Manager android 应用商店应用程序的图像](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="0c546-121">在" **添加应用程序"页** 的"应用程序信息"部分 *，输入* ：</span><span class="sxs-lookup"><span data-stu-id="0c546-121">On the **Add app** page and in the *App Information* section enter:</span></span>

   - <span data-ttu-id="0c546-122">**名称**</span><span class="sxs-lookup"><span data-stu-id="0c546-122">**Name**</span></span>
   - <span data-ttu-id="0c546-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c546-123">**Description**</span></span>
   - <span data-ttu-id="0c546-124">**Publisher** Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0c546-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="0c546-125">**作为 Defender** for https://play.google.com/store/apps/details?id=com.microsoft.scmx Endpoint (的应用商店 URL Google Play 应用商店 URL) </span><span class="sxs-lookup"><span data-stu-id="0c546-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span>

   <span data-ttu-id="0c546-126">其他字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="0c546-126">Other fields are optional.</span></span> <span data-ttu-id="0c546-127">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0c546-127">Select **Next**.</span></span>

   ![管理中心Microsoft Endpoint Manager应用信息的图像](images/mda-addappinfo.png)

3. <span data-ttu-id="0c546-129">在" *分配"* 部分，转到" **必需"** 部分并选择" **添加组"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="0c546-130">然后，你可以选择要 (Android) Defender for Endpoint 的用户组。</span><span class="sxs-lookup"><span data-stu-id="0c546-130">You can then choose the user group(s) that you would like to target Defender for Endpoint on Android app.</span></span> <span data-ttu-id="0c546-131">选择 **"选择**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-131">Choose **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c546-132">所选用户组应由 Intune 注册的用户组成。</span><span class="sxs-lookup"><span data-stu-id="0c546-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![管理中心Microsoft Endpoint Manager用户组的图像](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="0c546-134">在"**审阅+创建**"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="0c546-135">片刻后，将成功创建 Defender for Endpoint 应用，页面右上角将显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="0c546-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Defender Microsoft Endpoint Manager应用管理员中心通知的图像](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="0c546-137">在显示的"应用信息"页的"监视器"部分，选择"设备安装状态"以验证设备安装是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="0c546-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-138">![管理Microsoft Endpoint Manager安装的图像](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0c546-139">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="0c546-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0c546-140">在设备上安装 Android 上的 Defender for Endpoint 后，你将看到应用图标。</span><span class="sxs-lookup"><span data-stu-id="0c546-140">Once Defender for Endpoint on Android has been installed on the device, you'll see the app icon.</span></span>

    ![移动设备上的图标](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="0c546-142">点击 Microsoft Defender for Endpoint 应用图标并按照屏幕上的说明完成应用载入。</span><span class="sxs-lookup"><span data-stu-id="0c546-142">Tap the Microsoft Defender for Endpoint app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="0c546-143">详细信息包括最终用户接受 Android 上的 Defender for Endpoint 所需的 Android 权限。</span><span class="sxs-lookup"><span data-stu-id="0c546-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint on Android.</span></span>

3. <span data-ttu-id="0c546-144">成功载入后，设备将开始显示在设备列表中的Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="0c546-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Defender for Endpoint 门户中的设备图像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="0c546-146">在 Android Enterprise注册的设备上部署</span><span class="sxs-lookup"><span data-stu-id="0c546-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="0c546-147">Android 上的 Defender for Endpoint 支持 Android Enterprise注册的设备。</span><span class="sxs-lookup"><span data-stu-id="0c546-147">Defender for Endpoint on Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="0c546-148">有关 Intune 支持的注册选项的详细信息，请参阅 [注册选项](/mem/intune/enrollment/android-enroll)。</span><span class="sxs-lookup"><span data-stu-id="0c546-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="0c546-149">**目前，支持部署具有工作配置文件和公司所有完全托管用户设备注册的个人拥有设备。**</span><span class="sxs-lookup"><span data-stu-id="0c546-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="0c546-150">将 Android 上的 Microsoft Defender for Endpoint 添加为托管 Google Play 应用</span><span class="sxs-lookup"><span data-stu-id="0c546-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="0c546-151">按照以下步骤将 Microsoft Defender for Endpoint 应用添加到托管 Google Play。</span><span class="sxs-lookup"><span data-stu-id="0c546-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="0c546-152">In [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431) go to **Apps** \> **Android Apps** \> **Add** and select Managed Google **Play app**.</span><span class="sxs-lookup"><span data-stu-id="0c546-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-153">![管理中心Microsoft Endpoint Manager google play 的图像](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="0c546-154">在随后加载的托管 Google Play 页面上，转到搜索框并查找 **Microsoft Defender。**</span><span class="sxs-lookup"><span data-stu-id="0c546-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="0c546-155">你的搜索应在托管 Google Play 中显示 Microsoft Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="0c546-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="0c546-156">从应用搜索结果中单击 Microsoft Defender for Endpoint 应用。</span><span class="sxs-lookup"><span data-stu-id="0c546-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![管理Microsoft Endpoint Manager应用搜索的图像](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="0c546-158">在接下来启动的应用描述页面中，你应该能够看到 Defender for Endpoint 上的应用详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c546-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="0c546-159">查看页面上的信息，然后选择"批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-160">![托管 Google Play 的屏幕截图](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="0c546-161">你将看到 Defender for Endpoint 为它工作获取的权限。</span><span class="sxs-lookup"><span data-stu-id="0c546-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="0c546-162">查看它们，然后选择"批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-162">Review them and then select **Approve**.</span></span>

    ![适用于终结点预览应用审批的 Defender 屏幕截图](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="0c546-164">You'll be presented with the Approval settings page.</span><span class="sxs-lookup"><span data-stu-id="0c546-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="0c546-165">此页面确认你优先处理 Android 上的 Defender for Endpoint 可能请求的新应用权限。</span><span class="sxs-lookup"><span data-stu-id="0c546-165">The page confirms your preference to handle new app permissions that Defender for Endpoint on Android might ask.</span></span> <span data-ttu-id="0c546-166">查看选项并选择首选选项。</span><span class="sxs-lookup"><span data-stu-id="0c546-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="0c546-167">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="0c546-167">Select **Done**.</span></span>

    <span data-ttu-id="0c546-168">默认情况下，托管 Google Play 在应用请求新权限时 *选择"保持已批准"*</span><span class="sxs-lookup"><span data-stu-id="0c546-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-169">![通知选项卡的图像](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="0c546-170">完成权限处理选择后，选择" **同步** "以将 Microsoft Defender for Endpoint 同步到应用列表。</span><span class="sxs-lookup"><span data-stu-id="0c546-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-171">![同步页面图像](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="0c546-172">同步将在几分钟后完成。</span><span class="sxs-lookup"><span data-stu-id="0c546-172">The sync will complete in a few minutes.</span></span>

    ![Android 应用的图像](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="0c546-174">选择 Android **应用** 屏幕中的"刷新"按钮，Microsoft Defender for Endpoint 应在应用列表中可见。</span><span class="sxs-lookup"><span data-stu-id="0c546-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender for Endpoint should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-175">![Android 应用列表的图像](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="0c546-176">Defender for Endpoint 通过 Intune 支持托管设备的应用配置策略。</span><span class="sxs-lookup"><span data-stu-id="0c546-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="0c546-177">此功能可用于自动授予适用的 Android () ，因此最终用户无需接受这些 (权限) 。</span><span class="sxs-lookup"><span data-stu-id="0c546-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="0c546-178">在应用 **页面中** ，转到策略 **>应用配置策略>添加>托管设备**。</span><span class="sxs-lookup"><span data-stu-id="0c546-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![android Microsoft Endpoint Manager管理中心托管设备的图像](images/android-mem.png)

    1. <span data-ttu-id="0c546-180">在" **创建应用配置策略"** 页中，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="0c546-180">In the **Create app configuration policy** page, enter the following details:</span></span>

        - <span data-ttu-id="0c546-181">名称：Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="0c546-181">Name: Microsoft Defender for Endpoint.</span></span>
        - <span data-ttu-id="0c546-182">选择 **Android Enterprise** 作为平台。</span><span class="sxs-lookup"><span data-stu-id="0c546-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="0c546-183">选择 **"仅作为配置文件类型** 的工作配置文件"。</span><span class="sxs-lookup"><span data-stu-id="0c546-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="0c546-184">单击 **"选择应用"，** 选择 **"Microsoft Defender ATP"，** 选择 **"确定**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0c546-185">![创建应用配置策略页的图像](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="0c546-186">In the **设置** page， go to the Permissions section click on Add to view the list of supported permissions.</span><span class="sxs-lookup"><span data-stu-id="0c546-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="0c546-187">在"添加权限"部分，选择以下权限：</span><span class="sxs-lookup"><span data-stu-id="0c546-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="0c546-188">外部存储 (读取) </span><span class="sxs-lookup"><span data-stu-id="0c546-188">External storage (read)</span></span>
       - <span data-ttu-id="0c546-189">外部存储 (写入) </span><span class="sxs-lookup"><span data-stu-id="0c546-189">External storage (write)</span></span>

       <span data-ttu-id="0c546-190">然后，选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0c546-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="0c546-191">![Android 创建应用配置策略的图像](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="0c546-192">现在应该可以看到列出的权限，现在可以通过在"权限状态"下拉列表中选择"自动授予"，然后选择"下一步"来自动 **授予这两种权限**。</span><span class="sxs-lookup"><span data-stu-id="0c546-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0c546-193">![Android 自动授予创建应用配置策略的图像](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="0c546-194">在 **"分配** "页中，选择此应用配置策略将分配到的用户组。</span><span class="sxs-lookup"><span data-stu-id="0c546-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="0c546-195">单击 **"选择要包含的组"** 并选择适用的组，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="0c546-196">在此处选择的组通常是你将 Microsoft Defender for Endpoint Android 应用分配到的同一个组。</span><span class="sxs-lookup"><span data-stu-id="0c546-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0c546-197">![创建应用配置策略的图像](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>

    1. <span data-ttu-id="0c546-198">In the **Review + Create** page that comes up next， review all the information and then select **Create**.</span><span class="sxs-lookup"><span data-stu-id="0c546-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>

        <span data-ttu-id="0c546-199">Defender for Endpoint 的应用配置策略（自动授予存储权限）现在分配给所选用户组。</span><span class="sxs-lookup"><span data-stu-id="0c546-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0c546-200">![Android 评价创建应用配置策略的图像](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>

10. <span data-ttu-id="0c546-201">在 **"属性分配编辑"列表中选择"Microsoft Defender ATP** \>  \>  \> **应用"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![应用列表的图像](images/mda-properties.png)

11. <span data-ttu-id="0c546-203">将应用分配为 *用户组所需的* 应用。</span><span class="sxs-lookup"><span data-stu-id="0c546-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="0c546-204">在设备下一次 *同步* 期间，它会自动安装在工作配置文件中，公司门户应用。</span><span class="sxs-lookup"><span data-stu-id="0c546-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="0c546-205">此分配可通过导航到"必需"部分"添加组"，选择用户组并单击" \> 选择 **"完成**。</span><span class="sxs-lookup"><span data-stu-id="0c546-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-206">![编辑应用程序页的图像](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>

12. <span data-ttu-id="0c546-207">在" **编辑应用程序"** 页中，查看上面输入的所有信息。</span><span class="sxs-lookup"><span data-stu-id="0c546-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="0c546-208">然后选择" **审阅 + 保存** "，然后 **再次"保存** "以开始工作分配。</span><span class="sxs-lookup"><span data-stu-id="0c546-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="0c546-209">自动设置始终打开 VPN</span><span class="sxs-lookup"><span data-stu-id="0c546-209">Auto Setup of Always-on VPN</span></span>

<span data-ttu-id="0c546-210">Defender for Endpoint 通过 Intune 支持托管设备的设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="0c546-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="0c546-211">此功能可用于在 Android Enterprise设备上自动设置始终打开 **VPN，** 因此最终用户无需在载入时设置 VPN 服务。</span><span class="sxs-lookup"><span data-stu-id="0c546-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>

1. <span data-ttu-id="0c546-212">在 **设备上，** 选择 **配置文件 创建**  >  **配置文件**  >  **平台**  >  **Android Enterprise**</span><span class="sxs-lookup"><span data-stu-id="0c546-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise**</span></span>

   <span data-ttu-id="0c546-213">根据 **你的设备注册** 类型，在下列选项之一下选择设备限制：</span><span class="sxs-lookup"><span data-stu-id="0c546-213">Select **Device restrictions** under one of the following, based on your device enrollment type:</span></span>
   - <span data-ttu-id="0c546-214">**完全托管、专用Corporate-Owned工作配置文件**</span><span class="sxs-lookup"><span data-stu-id="0c546-214">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
   - <span data-ttu-id="0c546-215">**个人拥有的工作配置文件**</span><span class="sxs-lookup"><span data-stu-id="0c546-215">**Personally owned Work Profile**</span></span>

   <span data-ttu-id="0c546-216">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="0c546-216">Select **Create**.</span></span>

   > ![创建设备配置文件的图像](images/1autosetupofvpn.png)

2. <span data-ttu-id="0c546-218">**配置设置** 提供 **用于唯** 一 **标识** 配置文件的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="0c546-218">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span>

   > ![设备配置文件名称和说明的图像](images/2autosetupofvpn.png)

3. <span data-ttu-id="0c546-220">选择 **连接** 并配置 VPN：</span><span class="sxs-lookup"><span data-stu-id="0c546-220">Select **Connectivity** and configure VPN:</span></span>
   - <span data-ttu-id="0c546-221">启用 **始终启用 VPN**</span><span class="sxs-lookup"><span data-stu-id="0c546-221">Enable **Always-on VPN**</span></span>

   <span data-ttu-id="0c546-222">在工作配置文件中设置 VPN 客户端，尽可能自动连接和重新连接到 VPN。</span><span class="sxs-lookup"><span data-stu-id="0c546-222">Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="0c546-223">在给定设备上只能为始终打开的 VPN 配置一个 VPN 客户端，因此请确保将始终打开的 VPN 策略部署到单个设备不超过一个。</span><span class="sxs-lookup"><span data-stu-id="0c546-223">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span>

   - <span data-ttu-id="0c546-224">选择"VPN 客户端中的自定义"下拉列表</span><span class="sxs-lookup"><span data-stu-id="0c546-224">Select **Custom** in VPN client dropdown list</span></span>

   <span data-ttu-id="0c546-225">在这种情况下，自定义 VPN 是 Defender for Endpoint VPN，用于提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="0c546-225">Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0c546-226">必须在用户设备上安装 Microsoft Defender for Endpoint 应用，才能自动设置此 VPN。</span><span class="sxs-lookup"><span data-stu-id="0c546-226">Microsoft Defender for Endpoint app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

   - <span data-ttu-id="0c546-227">在 **Google** Play 应用商店中输入 Microsoft Defender for Endpoint 应用的程序包 ID。</span><span class="sxs-lookup"><span data-stu-id="0c546-227">Enter **Package ID** of the Microsoft Defender for Endpoint app in Google Play store.</span></span> <span data-ttu-id="0c546-228">对于 Defender 应用 <https://play.google.com/store/apps/details?id=com.microsoft.scmx> URL，程序包 ID 为 **com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="0c546-228">For the Defender app URL <https://play.google.com/store/apps/details?id=com.microsoft.scmx>, Package ID is **com.microsoft.scmx**</span></span>
   - <span data-ttu-id="0c546-229">**锁定模式** 未配置 (默认) </span><span class="sxs-lookup"><span data-stu-id="0c546-229">**Lockdown mode** Not configured (Default)</span></span>

     ![设备配置文件图像启用始终启用 VPN](images/3autosetupofvpn.png)

4. <span data-ttu-id="0c546-231">**Assignment**</span><span class="sxs-lookup"><span data-stu-id="0c546-231">**Assignment**</span></span>

   <span data-ttu-id="0c546-232">在 **"分配**   "页中，选择此应用配置策略将分配到的用户组。</span><span class="sxs-lookup"><span data-stu-id="0c546-232">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="0c546-233">单击 **"选择要包含** 的组"并选择适用的组，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0c546-233">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="0c546-234">在此处选择的组通常是你将 Microsoft Defender for Endpoint Android 应用分配到的同一个组。</span><span class="sxs-lookup"><span data-stu-id="0c546-234">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span>

     ![设备配置文件分配的图像](images/4autosetupofvpn.png)

5. <span data-ttu-id="0c546-236">In the **Review + Create** page that comes up next， review all the information and then select **Create**.</span><span class="sxs-lookup"><span data-stu-id="0c546-236">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span>
<span data-ttu-id="0c546-237">现在，设备配置文件已分配给选定的用户组。</span><span class="sxs-lookup"><span data-stu-id="0c546-237">The device configuration profile is now assigned to the selected user group.</span></span>

    ![设备配置文件的图像 查看和创建](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0c546-239">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="0c546-239">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0c546-240">通过单击"设备安装状态"确认 Android 上的 Microsoft Defender for Endpoint **的安装状态**。</span><span class="sxs-lookup"><span data-stu-id="0c546-240">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="0c546-241">验证设备是否在此处显示。</span><span class="sxs-lookup"><span data-stu-id="0c546-241">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0c546-242">![设备安装状态的图像](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="0c546-242">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>

2. <span data-ttu-id="0c546-243">在设备上，可以通过进入工作配置文件来验证载入 **状态**。</span><span class="sxs-lookup"><span data-stu-id="0c546-243">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="0c546-244">确认适用于终结点的 Defender 可用，并且你已使用工作配置文件 注册到个人 **拥有的设备**。</span><span class="sxs-lookup"><span data-stu-id="0c546-244">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="0c546-245">如果你注册了企业拥有、完全 **托管的用户设备**，你将在设备上拥有一个配置文件，你可以确认 Defender for Endpoint 可用。</span><span class="sxs-lookup"><span data-stu-id="0c546-245">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![移动设备上应用的图像](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="0c546-247">安装应用后，打开应用并接受权限，然后载入应该会成功。</span><span class="sxs-lookup"><span data-stu-id="0c546-247">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![使用 Microsoft Defender for Endpoint 应用的移动设备的图像](images/mda-devicesafe.png)

4. <span data-ttu-id="0c546-249">在此阶段，设备已成功载入 Android 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="0c546-249">At this stage the device is successfully onboarded onto Defender for Endpoint on Android.</span></span> <span data-ttu-id="0c546-250">可以通过导航到"设备 ["Microsoft Defender 安全中心](https://securitycenter.microsoft.com)在设备上 **验证这一** 点。</span><span class="sxs-lookup"><span data-stu-id="0c546-250">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![适用于终结点的 Microsoft Defender 门户的图像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="related-topics"></a><span data-ttu-id="0c546-252">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c546-252">Related topics</span></span>

- [<span data-ttu-id="0c546-253">Android 上的 Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="0c546-253">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="0c546-254">在 Android 功能上配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c546-254">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
