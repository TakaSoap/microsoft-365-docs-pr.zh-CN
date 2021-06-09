---
title: 在 Microsoft Defender for Endpoint 中配置条件访问
description: 了解在 Intune、Microsoft Defender 安全中心 和 Azure 中实现条件访问需要执行的步骤
keywords: 条件访问， 条件， 访问， 设备风险， 风险级别， 集成， intune 集成
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ceb69d59dc5208c0908e33d0880d9352562ec140
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843970"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b528c-104">在 Microsoft Defender for Endpoint 中配置条件访问</span><span class="sxs-lookup"><span data-stu-id="b528c-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b528c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b528c-105">**Applies to:**</span></span>
- [<span data-ttu-id="b528c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b528c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b528c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b528c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b528c-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b528c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b528c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b528c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b528c-110">本节指导您完成正确实现条件访问需要执行的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="b528c-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="b528c-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="b528c-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="b528c-112">需要注意的是，此方案不支持已注册 Azure AD 的设备。</span><span class="sxs-lookup"><span data-stu-id="b528c-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="b528c-113">仅支持 Intune 注册的设备。</span><span class="sxs-lookup"><span data-stu-id="b528c-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="b528c-114">你需要确保你的所有设备都注册到 Intune 中。</span><span class="sxs-lookup"><span data-stu-id="b528c-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="b528c-115">可以使用以下任一选项在 Intune 中注册设备：</span><span class="sxs-lookup"><span data-stu-id="b528c-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="b528c-116">IT 管理员：若要详细了解如何启用自动注册，请参阅Windows[注册](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="b528c-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="b528c-117">最终用户：若要详细了解如何在 Intune 中注册 Windows 10 设备，请参阅在[Intune 中Windows 10设备](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="b528c-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="b528c-118">最终用户替代：若要详细了解如何加入 Azure AD 域，请参阅如何：规划 [Azure AD 加入实现](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="b528c-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="b528c-119">在应用、Intune 门户和 Azure AD Microsoft Defender 安全中心需要执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="b528c-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="b528c-120">请注意访问这些门户和实现条件访问所需的角色：</span><span class="sxs-lookup"><span data-stu-id="b528c-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="b528c-121">**Microsoft Defender 安全中心**- 你需要使用一个帐户登录门户全局管理员角色启用集成。</span><span class="sxs-lookup"><span data-stu-id="b528c-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="b528c-122">**Intune** - 你需要使用具有管理权限的安全管理员权限登录门户。</span><span class="sxs-lookup"><span data-stu-id="b528c-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="b528c-123">**Azure AD 门户** - 你需要以全局管理员、安全管理员或条件访问管理员登录。</span><span class="sxs-lookup"><span data-stu-id="b528c-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="b528c-124">你将需要一个Microsoft Intune环境，并且 Intune 托管和 Azure AD 已加入Windows 10设备。</span><span class="sxs-lookup"><span data-stu-id="b528c-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="b528c-125">执行以下步骤以启用条件访问：</span><span class="sxs-lookup"><span data-stu-id="b528c-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="b528c-126">步骤 1：打开Microsoft Intune连接Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="b528c-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="b528c-127">步骤 2：在 Intune 中打开 Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="b528c-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="b528c-128">步骤 3：在 Intune 中创建合规性策略</span><span class="sxs-lookup"><span data-stu-id="b528c-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="b528c-129">步骤 4：分配策略</span><span class="sxs-lookup"><span data-stu-id="b528c-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="b528c-130">步骤 5：创建 Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="b528c-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="b528c-131">步骤 1：打开Microsoft Intune连接</span><span class="sxs-lookup"><span data-stu-id="b528c-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="b528c-132">在导航窗格中，**选择"设置**  >  **高级Microsoft Intune**  >  **连接"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="b528c-133">将"Microsoft Intune"设置为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="b528c-134">单击 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="b528c-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="b528c-135">步骤 2：在 Intune 中打开 Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="b528c-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="b528c-136">登录到 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="b528c-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b528c-137">选择 **设备合规性**  >  **Microsoft Defender ATP。**</span><span class="sxs-lookup"><span data-stu-id="b528c-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="b528c-138">将 **连接 Windows 10.0.15063+** 设备Microsoft Defender 高级威胁防护设置为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="b528c-139">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b528c-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="b528c-140">步骤 3：在 Intune 中创建合规性策略</span><span class="sxs-lookup"><span data-stu-id="b528c-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="b528c-141">在 [Azure 门户中](https://portal.azure.com)，选择 **"所有服务"，** 筛选 **Intune，** 然后选择"Microsoft Intune"。 </span><span class="sxs-lookup"><span data-stu-id="b528c-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="b528c-142">选择 **"设备合规性**  >  **策略**  >  **""创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="b528c-143">输入"**名称"** 和"**说明"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="b528c-144">在 **平台** 中，选择 **Windows 10和更高版本。**</span><span class="sxs-lookup"><span data-stu-id="b528c-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="b528c-145">在 **"设备运行状况** "设置中，将"要求设备位于设备威胁级别或以下设备威胁级别 **"设置为首选** 级别：</span><span class="sxs-lookup"><span data-stu-id="b528c-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="b528c-146">**Secured：** 此级别是最安全级别。</span><span class="sxs-lookup"><span data-stu-id="b528c-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="b528c-147">设备无法具有任何现有威胁，并且仍访问公司资源。</span><span class="sxs-lookup"><span data-stu-id="b528c-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="b528c-148">如果发现任何威胁，则评估设备不相容。</span><span class="sxs-lookup"><span data-stu-id="b528c-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="b528c-149">**低**：如果仅存在低级别威胁，则设备合规。</span><span class="sxs-lookup"><span data-stu-id="b528c-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="b528c-150">具有中等或高威胁级别的设备不兼容。</span><span class="sxs-lookup"><span data-stu-id="b528c-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="b528c-151">**中**：如果设备上发现的威胁较低或中等，则设备符合要求。</span><span class="sxs-lookup"><span data-stu-id="b528c-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="b528c-152">如果检测到高级威胁，则设备被确定为不符合要求。</span><span class="sxs-lookup"><span data-stu-id="b528c-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="b528c-153">**高**：此级别最不安全，允许所有威胁级别。</span><span class="sxs-lookup"><span data-stu-id="b528c-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="b528c-154">因此，具有高、中或低威胁级别的设备被视为兼容设备。</span><span class="sxs-lookup"><span data-stu-id="b528c-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="b528c-155">选择 **"确定\*\*\*\*"，** 然后选择"创建"保存 (并创建策略) 。</span><span class="sxs-lookup"><span data-stu-id="b528c-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="b528c-156">步骤 4：分配策略</span><span class="sxs-lookup"><span data-stu-id="b528c-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="b528c-157">在 [Azure 门户中](https://portal.azure.com)，选择 **"所有服务"，** 筛选 **Intune，** 然后选择"Microsoft Intune"。 </span><span class="sxs-lookup"><span data-stu-id="b528c-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="b528c-158">选择 **设备合规性**  >  **策略**>选择适用于终结点的 Microsoft Defender 合规性策略。</span><span class="sxs-lookup"><span data-stu-id="b528c-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="b528c-159">选择“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="b528c-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="b528c-160">包括或排除 Azure AD 组，以为其分配策略。</span><span class="sxs-lookup"><span data-stu-id="b528c-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="b528c-161">若要将策略部署到组，请选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="b528c-162">针对策略的目标用户设备进行评估是否符合合规性。</span><span class="sxs-lookup"><span data-stu-id="b528c-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="b528c-163">步骤 5：创建 Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="b528c-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="b528c-164">在 [Azure 门户中，](https://portal.azure.com)打开 **Azure Active Directory**  >  **条件访问**  >  **新策略"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="b528c-165">输入策略"**名称"，** 然后选择"**用户和组"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="b528c-166">使用包含或排除选项为策略添加组，**然后选择完成。**</span><span class="sxs-lookup"><span data-stu-id="b528c-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="b528c-167">选择 **"云** 应用"，然后选择要保护的应用。</span><span class="sxs-lookup"><span data-stu-id="b528c-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="b528c-168">例如，选择"**选择应用"，** 然后选择 **"Office 365 SharePoint Online"** 和 **"Office 365 Exchange Online"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="b528c-169">选择“**完成**”以保存更改。</span><span class="sxs-lookup"><span data-stu-id="b528c-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="b528c-170">选择  >  **条件 客户端应用**，将策略应用于应用和浏览器。</span><span class="sxs-lookup"><span data-stu-id="b528c-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="b528c-171">例如，选择"**是"，** 然后启用 **"浏览器** 和 **移动应用和桌面客户端"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="b528c-172">选择“**完成**”以保存更改。</span><span class="sxs-lookup"><span data-stu-id="b528c-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="b528c-173">选择 **"授予** "以基于设备合规性应用条件访问。</span><span class="sxs-lookup"><span data-stu-id="b528c-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="b528c-174">例如，选择"**授予访问权限**  >  **要求设备标记为合规"。**</span><span class="sxs-lookup"><span data-stu-id="b528c-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="b528c-175">选择 **"选择** "保存更改。</span><span class="sxs-lookup"><span data-stu-id="b528c-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="b528c-176">选择 **"启用策略**"，然后选择" **创建** "保存更改。</span><span class="sxs-lookup"><span data-stu-id="b528c-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="b528c-177">有关详细信息，请参阅在 [Intune](/intune/advanced-threat-protection)中通过条件访问强制 Microsoft Defender for Endpoint 的合规性。</span><span class="sxs-lookup"><span data-stu-id="b528c-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="b528c-178">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b528c-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b528c-179">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b528c-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
