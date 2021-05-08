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
ms.openlocfilehash: a3711018034bcabdde10c21b3c968c3e813d0565
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245249"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="23f03-104">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23f03-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23f03-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="23f03-105">**Applies to:**</span></span>
- [<span data-ttu-id="23f03-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23f03-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23f03-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23f03-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="23f03-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="23f03-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23f03-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="23f03-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="23f03-110">本主题介绍在已注册的设备上在 iOS Intune 公司门户 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="23f03-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="23f03-111">有关 Intune 设备注册详细信息，请参阅在 Intune 中注册 [iOS/iPadOS 设备](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="23f03-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="23f03-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="23f03-112">Before you begin</span></span>

- <span data-ttu-id="23f03-113">确保你有权访问 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="23f03-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="23f03-114">确保为用户完成了 iOS 注册。</span><span class="sxs-lookup"><span data-stu-id="23f03-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="23f03-115">用户需要分配有 Defender for Endpoint 许可证才能在 iOS 上使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="23f03-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="23f03-116">有关如何 [分配许可证的说明，](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 请参阅向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="23f03-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="23f03-117">iOS 上的 Microsoft Defender for Endpoint 现已在 [Apple App Store 中提供](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="23f03-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="23f03-118">部署步骤</span><span class="sxs-lookup"><span data-stu-id="23f03-118">Deployment steps</span></span>

<span data-ttu-id="23f03-119">通过 iOS 部署适用于终结点的 defender Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="23f03-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="23f03-120">添加 iOS 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="23f03-120">Add iOS store app</span></span>

1. <span data-ttu-id="23f03-121">在 [Microsoft Endpoint Manager 管理中心，](https://go.microsoft.com/fwlink/?linkid=2109431)转到 **应用**  ->  **iOS/iPadOS**  ->  **添加**  ->  **iOS 应用商店应用**，然后单击选择 。 </span><span class="sxs-lookup"><span data-stu-id="23f03-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-122">![管理Microsoft Endpoint Manager 1 的图像](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="23f03-123">在"添加应用"页上，单击" **搜索应用商店"，** 在 **搜索栏中** 键入 Microsoft Defender 终结点。</span><span class="sxs-lookup"><span data-stu-id="23f03-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="23f03-124">在搜索结果部分中，单击 Microsoft *Defender 终结点* ，然后单击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="23f03-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="23f03-125">选择 **iOS 11.0** 作为最低操作系统。</span><span class="sxs-lookup"><span data-stu-id="23f03-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="23f03-126">查看有关应用的其他信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="23f03-127">在"*分配"* 部分，转到"**必填"部分**，然后选择"**添加组"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="23f03-128">然后，你可以选择你要 (iOS) Defender for Endpoint 的用户组。</span><span class="sxs-lookup"><span data-stu-id="23f03-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="23f03-129">单击 **"选择**"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23f03-130">所选用户组应由 Intune 注册的用户组成。</span><span class="sxs-lookup"><span data-stu-id="23f03-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-131">![管理Microsoft Endpoint Manager 2 的图像](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="23f03-132">在"*审阅 + 创建*"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="23f03-133">片刻后，应成功创建 Defender for Endpoint 应用，并且页面右上角会显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="23f03-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="23f03-134">在显示的"应用信息"页的"监视器"部分，选择"设备安装状态"以验证设备安装是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="23f03-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-135">![管理Microsoft Endpoint Manager 3 的图像](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="23f03-136">VPN 配置文件的自动载入 (简化的载入) </span><span class="sxs-lookup"><span data-stu-id="23f03-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

> [!NOTE]
> <span data-ttu-id="23f03-137">VPN 配置文件的自动载入目前处于预览阶段，在商业发行之前，本部分中提到的步骤可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="23f03-137">Auto-onboarding of VPN profile is currently in preview and the steps mentioned in this section may be substantially modified before it's commercially released.</span></span>

<span data-ttu-id="23f03-138">管理员可以配置 VPN 配置文件的自动设置。</span><span class="sxs-lookup"><span data-stu-id="23f03-138">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="23f03-139">这将自动设置 Defender for Endpoint VPN 配置文件，无需用户在载入时这样做。</span><span class="sxs-lookup"><span data-stu-id="23f03-139">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="23f03-140">请注意，VPN 用于提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="23f03-140">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="23f03-141">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="23f03-141">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="23f03-142">在 [Microsoft Endpoint Manager 管理中心中](https://go.microsoft.com/fwlink/?linkid=2109431)，转到"**设备**  ->  **配置文件""**  ->  **创建**  ->  **iOS 应用商店"应用**，然后单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-142">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create** -> **iOS store app** and click **Select**.</span></span>
1. <span data-ttu-id="23f03-143">选择 **"平台** 为 **iOS/iPadOS"** 和 **"配置文件类型** 为 **VPN"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-143">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="23f03-144">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="23f03-144">Click **Create**.</span></span>
1. <span data-ttu-id="23f03-145">键入配置文件的名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="23f03-145">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="23f03-146">为 **"连接** 类型"选择"自定义 **VPN"，在"基本 VPN"** 部分，输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="23f03-146">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="23f03-147">连接名称 = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23f03-147">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="23f03-148">VPN 服务器地址 = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="23f03-148">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="23f03-149">Auth 方法 = "Username and password"</span><span class="sxs-lookup"><span data-stu-id="23f03-149">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="23f03-150">拆分隧道 = 禁用</span><span class="sxs-lookup"><span data-stu-id="23f03-150">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="23f03-151">VPN 标识符 = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="23f03-151">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="23f03-152">在键值对中，输入键 **AutoOnboard，** 将值设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="23f03-152">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="23f03-153">自动 VPN 的类型 = 按需 VPN</span><span class="sxs-lookup"><span data-stu-id="23f03-153">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="23f03-154">单击 **"** 为 **按需规则添加**"，然后选择"我想执行以下操作 = 建立 **VPN，\*\*\*\*我希望限制为 = 所有域"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-154">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![VPN 配置文件配置的屏幕截图](images/ios-deploy-8.png)

1. <span data-ttu-id="23f03-156">单击"下一步"，并将配置文件分配给目标用户。</span><span class="sxs-lookup"><span data-stu-id="23f03-156">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="23f03-157">在"*审阅 + 创建*"部分，验证输入的所有信息是否正确，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-157">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="23f03-158">完成载入和检查状态</span><span class="sxs-lookup"><span data-stu-id="23f03-158">Complete onboarding and check status</span></span>

1. <span data-ttu-id="23f03-159">在设备上安装 iOS 上的 Defender for Endpoint 后，你将看到应用图标。</span><span class="sxs-lookup"><span data-stu-id="23f03-159">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![自动生成的智能手机说明的屏幕截图](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="23f03-161">点击 Defender for Endpoint 应用图标并按照屏幕上的说明完成载入步骤。</span><span class="sxs-lookup"><span data-stu-id="23f03-161">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="23f03-162">详细信息包括最终用户接受 iOS 上终结点的 Defender 所需的 iOS 权限。</span><span class="sxs-lookup"><span data-stu-id="23f03-162">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="23f03-163">成功载入后，设备将开始显示在设备列表中的Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="23f03-163">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-164">![自动生成的手机描述的屏幕截图](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-164">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="23f03-165">配置适用于监督模式的 Microsoft Defender 终结点</span><span class="sxs-lookup"><span data-stu-id="23f03-165">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="23f03-166">鉴于平台在这些类型的设备上提供的管理功能已增强，iOS 上的 Microsoft Defender for Endpoint 应用在受监督的 iOS/iPadOS 设备上具有专门的功能。</span><span class="sxs-lookup"><span data-stu-id="23f03-166">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="23f03-167">若要充分利用这些功能，适用于终结点的 Defender 应用需要知道设备是否位于监督模式下。</span><span class="sxs-lookup"><span data-stu-id="23f03-167">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="23f03-168">通过 Intune 配置监督模式</span><span class="sxs-lookup"><span data-stu-id="23f03-168">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="23f03-169">Intune 允许你通过应用配置策略配置适用于 iOS 的 Defender 应用。</span><span class="sxs-lookup"><span data-stu-id="23f03-169">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="23f03-170">适用于受监督设备的此应用配置策略仅适用于托管设备，并且作为最佳做法应面向所有托管 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="23f03-170">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="23f03-171">登录到管理 [Microsoft Endpoint Manager，](https://go.microsoft.com/fwlink/?linkid=2109431)然后转到 **应用**  >  **应用配置策略**  >  **添加**。</span><span class="sxs-lookup"><span data-stu-id="23f03-171">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="23f03-172">单击 **托管设备**。</span><span class="sxs-lookup"><span data-stu-id="23f03-172">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-173">![管理Microsoft Endpoint Manager 4 的图像](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-173">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="23f03-174">在 *"创建应用配置策略"* 页中，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="23f03-174">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="23f03-175">Policy Name</span><span class="sxs-lookup"><span data-stu-id="23f03-175">Policy Name</span></span>
    - <span data-ttu-id="23f03-176">平台：选择 iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="23f03-176">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="23f03-177">目标应用：**从Microsoft Defender ATP** 选择目标应用</span><span class="sxs-lookup"><span data-stu-id="23f03-177">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-178">![管理Microsoft Endpoint Manager 5 的图像](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-178">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="23f03-179">下一个屏幕中，选择 **"使用配置设计器** "作为格式。</span><span class="sxs-lookup"><span data-stu-id="23f03-179">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="23f03-180">指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="23f03-180">Specify the following property:</span></span>
    - <span data-ttu-id="23f03-181">配置密钥：issupervised</span><span class="sxs-lookup"><span data-stu-id="23f03-181">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="23f03-182">值类型：String</span><span class="sxs-lookup"><span data-stu-id="23f03-182">Value type: String</span></span>
    - <span data-ttu-id="23f03-183">配置值：{{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="23f03-183">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-184">![管理Microsoft Endpoint Manager中心 6 的图像](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-184">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="23f03-185">单击 **"下** 一步"打开 **"范围标记"** 页。</span><span class="sxs-lookup"><span data-stu-id="23f03-185">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="23f03-186">范围标记是可选的。</span><span class="sxs-lookup"><span data-stu-id="23f03-186">Scope tags are optional.</span></span> <span data-ttu-id="23f03-187">单击“下一步”即可继续。</span><span class="sxs-lookup"><span data-stu-id="23f03-187">Click **Next** to continue.</span></span>

1. <span data-ttu-id="23f03-188">在" **分配** "页上，选择将接收此配置文件的组。</span><span class="sxs-lookup"><span data-stu-id="23f03-188">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="23f03-189">对于此方案，最佳做法是面向 **所有设备**。</span><span class="sxs-lookup"><span data-stu-id="23f03-189">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="23f03-190">有关分配配置文件的信息，请参阅分配 [用户和设备配置文件](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="23f03-190">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="23f03-191">部署到用户组时，用户必须在应用策略之前登录设备。</span><span class="sxs-lookup"><span data-stu-id="23f03-191">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="23f03-192">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="23f03-192">Click **Next**.</span></span>

1. <span data-ttu-id="23f03-193">在"**审阅 + 创建**"页上，完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-193">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="23f03-194">新配置文件显示在配置文件列表中。</span><span class="sxs-lookup"><span data-stu-id="23f03-194">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="23f03-195">接下来，为了增强防钓鱼功能，可以在受监督的 iOS 设备上部署自定义配置文件。</span><span class="sxs-lookup"><span data-stu-id="23f03-195">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="23f03-196">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="23f03-196">Follow the steps below:</span></span>
    - <span data-ttu-id="23f03-197">从下载配置配置文件 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="23f03-197">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="23f03-198">导航到 **设备**  ->  **iOS/iPadOS**  ->  **配置文件**  ->  **创建配置文件**</span><span class="sxs-lookup"><span data-stu-id="23f03-198">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23f03-199">![管理Microsoft Endpoint Manager中心 7 的图像](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="23f03-199">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="23f03-200">提供配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="23f03-200">Provide a name of the profile.</span></span> <span data-ttu-id="23f03-201">当系统提示导入配置文件时，请选择上面下载的文件。</span><span class="sxs-lookup"><span data-stu-id="23f03-201">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="23f03-202">在 **"分配** "部分，选择要应用此配置文件的设备组。</span><span class="sxs-lookup"><span data-stu-id="23f03-202">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="23f03-203">最佳做法是，这应该应用于所有托管的 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="23f03-203">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="23f03-204">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="23f03-204">Click **Next**.</span></span>
    - <span data-ttu-id="23f03-205">在"**审阅 + 创建**"页上，完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="23f03-205">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="23f03-206">新配置文件显示在配置文件列表中。</span><span class="sxs-lookup"><span data-stu-id="23f03-206">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23f03-207">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23f03-207">Next Steps</span></span>

[<span data-ttu-id="23f03-208">在 iOS 功能上为终结点配置 Defender</span><span class="sxs-lookup"><span data-stu-id="23f03-208">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
