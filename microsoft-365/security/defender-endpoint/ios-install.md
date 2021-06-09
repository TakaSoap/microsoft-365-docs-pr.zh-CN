---
title: 适用于 iOS 上的终结点的 Microsoft Defender 基于应用的部署
ms.reviewer: ''
description: 介绍如何使用应用在 iOS 上部署 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 应用， 安装， 部署， 卸载， intune
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
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842278"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="b7563-104">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7563-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7563-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b7563-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7563-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7563-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7563-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7563-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b7563-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b7563-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b7563-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b7563-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b7563-110">本主题介绍在已注册的设备上在 iOS Intune 公司门户 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="b7563-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="b7563-111">有关 Intune 设备注册详细信息，请参阅在 Intune 中注册 [iOS/iPadOS 设备](/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="b7563-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b7563-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="b7563-112">Before you begin</span></span>

- <span data-ttu-id="b7563-113">确保你有权访问 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="b7563-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="b7563-114">确保为用户完成了 iOS 注册。</span><span class="sxs-lookup"><span data-stu-id="b7563-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="b7563-115">用户需要分配有 Defender for Endpoint 许可证才能在 iOS 上使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="b7563-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="b7563-116">有关如何 [分配许可证的说明，](/azure/active-directory/users-groups-roles/licensing-groups-assign) 请参阅向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="b7563-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="b7563-117">iOS 上的 Microsoft Defender for Endpoint 在 [Apple App Store 中提供](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="b7563-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="b7563-118">部署步骤</span><span class="sxs-lookup"><span data-stu-id="b7563-118">Deployment steps</span></span>

<span data-ttu-id="b7563-119">通过 iOS 部署适用于终结点的 defender Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="b7563-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="b7563-120">添加 iOS 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="b7563-120">Add iOS store app</span></span>

1. <span data-ttu-id="b7563-121">在 [Microsoft Endpoint Manager 管理中心，](https://go.microsoft.com/fwlink/?linkid=2109431)转到 **应用**  ->  **iOS/iPadOS**  ->  **添加**  ->  **iOS 应用商店应用**，然后单击选择 。 </span><span class="sxs-lookup"><span data-stu-id="b7563-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-122">![管理Microsoft Endpoint Manager 1 的图像](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="b7563-123">在"添加应用"页上，单击" **搜索应用商店"，** 在 **搜索栏中** 键入 Microsoft Defender 终结点。</span><span class="sxs-lookup"><span data-stu-id="b7563-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="b7563-124">在搜索结果部分中，单击 Microsoft *Defender 终结点* ，然后单击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="b7563-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="b7563-125">选择 **iOS 11.0** 作为最低操作系统。</span><span class="sxs-lookup"><span data-stu-id="b7563-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="b7563-126">查看有关应用的其他信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="b7563-127">在"*分配"* 部分，转到"**必填"部分**，然后选择"**添加组"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="b7563-128">然后，你可以选择你要 (iOS) Defender for Endpoint 的用户组。</span><span class="sxs-lookup"><span data-stu-id="b7563-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="b7563-129">单击 **"选择**"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7563-130">所选用户组应由 Intune 注册的用户组成。</span><span class="sxs-lookup"><span data-stu-id="b7563-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-131">![管理Microsoft Endpoint Manager 2 的图像](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="b7563-132">在"*审阅 + 创建*"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="b7563-133">片刻后，应成功创建 Defender for Endpoint 应用，并且页面右上角会显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="b7563-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="b7563-134">在显示的"应用信息"页的"监视器"部分，选择"设备安装状态"以验证设备安装是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="b7563-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-135">![管理Microsoft Endpoint Manager 3 的图像](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="b7563-136">VPN 配置文件的自动载入 (简化的载入) </span><span class="sxs-lookup"><span data-stu-id="b7563-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="b7563-137">管理员可以配置 VPN 配置文件的自动设置。</span><span class="sxs-lookup"><span data-stu-id="b7563-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="b7563-138">这将自动设置 Defender for Endpoint VPN 配置文件，无需用户在载入时这样做。</span><span class="sxs-lookup"><span data-stu-id="b7563-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="b7563-139">请注意，VPN 用于提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="b7563-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b7563-140">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="b7563-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="b7563-141">在 [Microsoft Endpoint Manager 管理中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **"设备**  ->  **配置文件""**  ->  **创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="b7563-142">选择 **"平台** 为 **iOS/iPadOS"** 和 **"配置文件类型** 为 **VPN"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="b7563-143">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="b7563-143">Click **Create**.</span></span>
1. <span data-ttu-id="b7563-144">键入配置文件的名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="b7563-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="b7563-145">为 **"连接** 类型"选择"自定义 **VPN"，在"基本 VPN"** 部分，输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="b7563-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="b7563-146">连接名称 = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7563-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="b7563-147">VPN 服务器地址 = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="b7563-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="b7563-148">Auth 方法 = "Username and password"</span><span class="sxs-lookup"><span data-stu-id="b7563-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="b7563-149">拆分隧道 = 禁用</span><span class="sxs-lookup"><span data-stu-id="b7563-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="b7563-150">VPN 标识符 = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="b7563-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="b7563-151">在键值对中，输入键 **AutoOnboard，** 将值设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="b7563-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="b7563-152">自动 VPN 的类型 = 按需 VPN</span><span class="sxs-lookup"><span data-stu-id="b7563-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="b7563-153">单击 **"** 为 **按需规则添加**"，然后选择"我想执行以下操作 = 建立 **VPN，\*\*\*\*我希望限制为 = 所有域"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![VPN 配置文件配置的屏幕截图](images/ios-deploy-8.png)

1. <span data-ttu-id="b7563-155">单击"下一步"，并将配置文件分配给目标用户。</span><span class="sxs-lookup"><span data-stu-id="b7563-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="b7563-156">在"*审阅 + 创建*"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="b7563-157">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="b7563-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="b7563-158">在设备上安装 iOS 上的 Defender for Endpoint 后，你将看到应用图标。</span><span class="sxs-lookup"><span data-stu-id="b7563-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![自动生成的智能手机说明的屏幕截图](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="b7563-160">点击 MSDefender (Defender for Endpoint 应用) 并按照屏幕上的说明完成载入步骤。</span><span class="sxs-lookup"><span data-stu-id="b7563-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="b7563-161">详细信息包括最终用户接受 iOS 上终结点的 Defender 所需的 iOS 权限。</span><span class="sxs-lookup"><span data-stu-id="b7563-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="b7563-162">成功载入后，设备将开始显示在设备列表中的Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b7563-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-163">![自动生成的手机描述的屏幕截图](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="b7563-164">配置适用于监督模式的 Microsoft Defender 终结点</span><span class="sxs-lookup"><span data-stu-id="b7563-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="b7563-165">鉴于平台在这些类型的设备上提供的管理功能已增强，iOS 上的 Microsoft Defender for Endpoint 应用在受监督的 iOS/iPadOS 设备上具有专门的功能。</span><span class="sxs-lookup"><span data-stu-id="b7563-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="b7563-166">若要充分利用这些功能，适用于终结点的 Defender 应用需要知道设备是否位于监督模式下。</span><span class="sxs-lookup"><span data-stu-id="b7563-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="b7563-167">通过 Intune 配置监督模式</span><span class="sxs-lookup"><span data-stu-id="b7563-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="b7563-168">Intune 允许你通过应用配置策略配置适用于 iOS 的 Defender 应用。</span><span class="sxs-lookup"><span data-stu-id="b7563-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b7563-169">适用于受监督设备的此应用配置策略仅适用于托管设备，并且作为最佳做法应面向所有托管 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="b7563-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="b7563-170">登录到管理 [Microsoft Endpoint Manager，](https://go.microsoft.com/fwlink/?linkid=2109431)然后转到 **应用**  >  **应用配置策略**  >  **添加**。</span><span class="sxs-lookup"><span data-stu-id="b7563-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="b7563-171">单击 **托管设备**。</span><span class="sxs-lookup"><span data-stu-id="b7563-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-172">![管理Microsoft Endpoint Manager 4 的图像](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="b7563-173">在 *"创建应用配置策略"* 页中，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="b7563-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="b7563-174">Policy Name</span><span class="sxs-lookup"><span data-stu-id="b7563-174">Policy Name</span></span>
    - <span data-ttu-id="b7563-175">平台：选择 iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="b7563-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="b7563-176">目标应用：从 **列表中选择 Microsoft Defender** 终结点</span><span class="sxs-lookup"><span data-stu-id="b7563-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-177">![管理Microsoft Endpoint Manager 5 的图像](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="b7563-178">下一个屏幕中，选择 **"使用配置设计器** "作为格式。</span><span class="sxs-lookup"><span data-stu-id="b7563-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="b7563-179">指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="b7563-179">Specify the following property:</span></span>
    - <span data-ttu-id="b7563-180">配置密钥：issupervised</span><span class="sxs-lookup"><span data-stu-id="b7563-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="b7563-181">值类型：String</span><span class="sxs-lookup"><span data-stu-id="b7563-181">Value type: String</span></span>
    - <span data-ttu-id="b7563-182">配置值：{{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="b7563-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-183">![管理Microsoft Endpoint Manager中心 6 的图像](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="b7563-184">单击 **"下** 一步"打开 **"范围标记"** 页。</span><span class="sxs-lookup"><span data-stu-id="b7563-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="b7563-185">范围标记是可选的。</span><span class="sxs-lookup"><span data-stu-id="b7563-185">Scope tags are optional.</span></span> <span data-ttu-id="b7563-186">单击“下一步”即可继续。</span><span class="sxs-lookup"><span data-stu-id="b7563-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="b7563-187">在" **分配** "页上，选择将接收此配置文件的组。</span><span class="sxs-lookup"><span data-stu-id="b7563-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="b7563-188">对于此方案，最佳做法是面向 **所有设备**。</span><span class="sxs-lookup"><span data-stu-id="b7563-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="b7563-189">有关分配配置文件的信息，请参阅分配 [用户和设备配置文件](/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="b7563-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="b7563-190">部署到用户组时，用户必须在应用策略之前登录设备。</span><span class="sxs-lookup"><span data-stu-id="b7563-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="b7563-191">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b7563-191">Click **Next**.</span></span>

1. <span data-ttu-id="b7563-192">在"**审阅 + 创建**"页上，完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="b7563-193">新配置文件显示在配置文件列表中。</span><span class="sxs-lookup"><span data-stu-id="b7563-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="b7563-194">接下来，为了增强防钓鱼功能，可以在受监督的 iOS 设备上部署自定义配置文件。</span><span class="sxs-lookup"><span data-stu-id="b7563-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="b7563-195">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b7563-195">Follow the steps below:</span></span>
    - <span data-ttu-id="b7563-196">从下载配置配置文件 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="b7563-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="b7563-197">导航到 **设备**  ->  **iOS/iPadOS**  ->  **配置文件**  ->  **创建配置文件**</span><span class="sxs-lookup"><span data-stu-id="b7563-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b7563-198">![管理Microsoft Endpoint Manager中心 7 的图像](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="b7563-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="b7563-199">提供配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b7563-199">Provide a name of the profile.</span></span> <span data-ttu-id="b7563-200">当系统提示导入配置文件时，请选择上面下载的文件。</span><span class="sxs-lookup"><span data-stu-id="b7563-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="b7563-201">在 **"分配** "部分，选择要应用此配置文件的设备组。</span><span class="sxs-lookup"><span data-stu-id="b7563-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="b7563-202">最佳做法是，这应该应用于所有托管的 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="b7563-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="b7563-203">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b7563-203">Click **Next**.</span></span>
    - <span data-ttu-id="b7563-204">在"**审阅 + 创建**"页上，完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="b7563-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="b7563-205">新配置文件显示在配置文件列表中。</span><span class="sxs-lookup"><span data-stu-id="b7563-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7563-206">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b7563-206">Next Steps</span></span>

[<span data-ttu-id="b7563-207">在 iOS 功能上为终结点配置 Defender</span><span class="sxs-lookup"><span data-stu-id="b7563-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
