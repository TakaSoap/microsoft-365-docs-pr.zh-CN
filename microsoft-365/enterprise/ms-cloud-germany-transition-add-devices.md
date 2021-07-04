---
title: 从德国 Microsoft 云迁移的其他设备信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云迁移到新的德国数据中心 (Microsoft 云) Office 365服务时有关服务的其他设备信息。
ms.openlocfilehash: 684af01b2d90f44b2cda1cf050d1e4db70f92915
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289435"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="e2bf8-103">从德国 Microsoft 云迁移的其他设备信息</span><span class="sxs-lookup"><span data-stu-id="e2bf8-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="e2bf8-104">连接到德国 Microsoft 云的已加入和注册的 Azure AD 设备必须在第 9 阶段之后和阶段 10 之前进行迁移。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="e2bf8-105">设备的迁移取决于设备类型、操作系统和 Azure AD 关系。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span>

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="e2bf8-106">加入 Azure AD Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="e2bf8-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="e2bf8-107">如果Windows 10已加入 Azure AD，则它必须与 Azure AD 断开连接，并且必须再次连接。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span>

<span data-ttu-id="e2bf8-108">[![Azure AD 设备Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e2bf8-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="e2bf8-109">如果用户是设备管理员，Windows 10 Azure AD 取消注册设备，然后通过三个步骤重新加入该设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="e2bf8-110">步骤 1：确定设备是否加入 Azure ID</span><span class="sxs-lookup"><span data-stu-id="e2bf8-110">Step 1: Determine if the device is Azure ID joined</span></span>

1. <span data-ttu-id="e2bf8-111">使用你的工作帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-111">Sign in with your work account.</span></span>
2. <span data-ttu-id="e2bf8-112">转到帐户 **设置**  >    >  **访问工作或学校**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="e2bf8-113">在列表中查找连接到 **[...]的帐户s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="e2bf8-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span>
4. <span data-ttu-id="e2bf8-114">如果存在已连接的帐户，请继续执行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-114">If a connected account exists, proceed with Step 2.</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="e2bf8-115">步骤 2：断开设备与 Azure AD 连接</span><span class="sxs-lookup"><span data-stu-id="e2bf8-115">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="e2bf8-116">单击 **已连接** 的工作或学校帐户上的"断开连接"。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-116">Click **Disconnect** on the connected work or School Account.</span></span>
2. <span data-ttu-id="e2bf8-117">确认断开连接两次。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-117">Confirm the disconnect twice.</span></span>
3. <span data-ttu-id="e2bf8-118">输入本地管理员用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="e2bf8-119">设备已断开连接。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-119">The device is disconnected.</span></span>
4. <span data-ttu-id="e2bf8-120">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-120">Restart the device.</span></span>

### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="e2bf8-121">步骤 3：将设备加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="e2bf8-121">Step 3: Join the device to Azure AD</span></span>

1. <span data-ttu-id="e2bf8-122">使用本地管理员的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-122">Sign in with the credentials of the local administrator.</span></span>
2. <span data-ttu-id="e2bf8-123">转到帐户 **设置**  >    >  **访问工作或学校**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="e2bf8-124">单击“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-124">Click **Connect**.</span></span>
4. <span data-ttu-id="e2bf8-125">**重要** 提示：单击 **加入 Azure AD**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5. <span data-ttu-id="e2bf8-126">输入工作帐户的电子邮件地址和密码。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="e2bf8-127">设备已连接。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-127">The device is connected.</span></span>
6. <span data-ttu-id="e2bf8-128">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-128">Restart the device.</span></span>
7. <span data-ttu-id="e2bf8-129">使用你的工作帐户的电子邮件地址和密码登录。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="e2bf8-130">如果用户不是设备的管理员，Azure AD 全局管理员可以按照此配置路径在设备上创建本地管理员帐户，并取消加入设备：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="e2bf8-131">*设置 >帐户>其他帐户>凭据未知> Microsoft 帐户添加用户*</span><span class="sxs-lookup"><span data-stu-id="e2bf8-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="e2bf8-132">对于重新加入，此步骤中可以使用来自组织的任何工作帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span>

<span data-ttu-id="e2bf8-133">请考虑用于加入设备的工作帐户将自动提升为设备的管理员。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="e2bf8-134">组织中的其他任何工作帐户都可以登录到设备，但没有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="e2bf8-135">Azure AD 注册 (工作区) Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="e2bf8-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>

<span data-ttu-id="e2bf8-136">如果Windows 10已注册 Azure AD，需要从 Azure AD 断开连接，然后重新连接。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="e2bf8-137">[![Azure AD 设备Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e2bf8-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="e2bf8-138">步骤 1：确定设备是否注册了 Azure ID</span><span class="sxs-lookup"><span data-stu-id="e2bf8-138">Step 1: Determine if the device is Azure ID registered</span></span>

1. <span data-ttu-id="e2bf8-139">使用你的用户登录。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-139">Sign in with your user.</span></span>
2. <span data-ttu-id="e2bf8-140">转到帐户 **设置**  >    >  **访问工作或学校**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="e2bf8-141">在列表中发现你的工作帐户并检查它是否 **连接到 [...]'s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="e2bf8-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="e2bf8-142">如果你的工作帐户在列表中，但没有连接到 Azure AD，请继续执行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="e2bf8-143">否则，你的设备是加入 Azure AD 的设备，你必须参考加入[Azure AD Windows 10设备](#azure-ad-joined-windows-10-devices)。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="e2bf8-144">步骤 2：断开设备与 Azure AD 连接</span><span class="sxs-lookup"><span data-stu-id="e2bf8-144">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="e2bf8-145">单击你的工作帐户。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-145">Click on your work account.</span></span> <span data-ttu-id="e2bf8-146">将显示" *信息"* 和" *断开连接"* 按钮。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-146">The buttons *Info* and *Disconnect* appear.</span></span>
2. <span data-ttu-id="e2bf8-147">单击 **断开连接**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-147">Click **Disconnect**.</span></span>
3. <span data-ttu-id="e2bf8-148">通过单击"是"确认从设备删除 **帐户**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-148">Confirm account removal from the device by clicking **Yes**.</span></span>

### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="e2bf8-149">步骤 3：连接设备连接到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="e2bf8-149">Step 3: Connect the device to Azure AD</span></span>

1. <span data-ttu-id="e2bf8-150">单击“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-150">Click **Connect**.</span></span>
2. <span data-ttu-id="e2bf8-151">输入你的工作帐户的电子邮件地址，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-151">Enter the email address of your work account and click **Next**.</span></span>
3. <span data-ttu-id="e2bf8-152">输入工作帐户的密码，然后单击"**登录"。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-152">Enter the password of your work account and click **Sign in**.</span></span>
4. <span data-ttu-id="e2bf8-153">通过单击"完成 **"确认**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="e2bf8-154">你的工作帐户将再次列出。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="e2bf8-155">Android</span><span class="sxs-lookup"><span data-stu-id="e2bf8-155">Android</span></span>

<span data-ttu-id="e2bf8-156">对于 Android，用户需要注销并重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="e2bf8-157">这可以通过 Microsoft Authenticator 或 公司门户 应用完成。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span>

- <span data-ttu-id="e2bf8-158">从Microsoft Authenticator应用，用户可以转到设置 >**注册"。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="e2bf8-159">在这里，用户可以注销和重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-159">From there users can unregister and re-register their device.</span></span>

- <span data-ttu-id="e2bf8-160">从公司门户，用户可以转到"**设备**"选项卡并删除设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="e2bf8-161">此后，使用"配置"公司门户。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-161">After that, re-enroll the device by using Company Portal.</span></span>

- <span data-ttu-id="e2bf8-162">用户还可以从帐户设置页中删除帐户，然后重新添加工作帐户，从而注销和重新注册。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="e2bf8-163">若要在 Android 上注销和重新注册设备，请运行Microsoft Authenticator应用：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1. <span data-ttu-id="e2bf8-164">打开 Microsoft Authenticator 应用，**然后转到** 设置 。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2. <span data-ttu-id="e2bf8-165">选择 **"设备注册"。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-165">Select **Device registration**.</span></span>
3. <span data-ttu-id="e2bf8-166">通过选择"注销"取消 **注册设备**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-166">Unregister the device by selecting **Unregister**.</span></span>
4. <span data-ttu-id="e2bf8-167">对于 **设备注册**，请通过键入你的电子邮件地址重新注册设备，**然后选择注册。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="e2bf8-168">若要注销 Android 设备并重新注册 Android 设置页面：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1. <span data-ttu-id="e2bf8-169">打开 **设备设置\*\*\*\*转到帐户**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-169">Open **Device Settings** and go to **Accounts**.</span></span>
2. <span data-ttu-id="e2bf8-170">选择要重新注册的工作帐户，然后选择"删除 **帐户"。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3. <span data-ttu-id="e2bf8-171">删除帐户后，从"帐户"**页面** 选择"添加帐户>**工作帐户"。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4. <span data-ttu-id="e2bf8-172">对于 **Workplace Join，** 键入你的电子邮件地址，然后选择 **加入** 以完成设备注册。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="e2bf8-173">若要在 Android 上注销并重新注册设备，请公司门户：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1. <span data-ttu-id="e2bf8-174">启动公司门户并转到 **设备** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-174">Launch Company Portal and go to **Devices** tab.</span></span>
2. <span data-ttu-id="e2bf8-175">选择设备以查看设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-175">Select the device to see the device details.</span></span>
3. <span data-ttu-id="e2bf8-176">From theellipses (three dots) menu， select **Remove Device**， and complete the removal by confirming in the dialog.</span><span class="sxs-lookup"><span data-stu-id="e2bf8-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4. <span data-ttu-id="e2bf8-177">你现在应该已注销公司门户应用。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="e2bf8-178">选择 **"登录** "以重新注册设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="e2bf8-179">有关此工作负载的迁移阶段需要执行的任何操作或对管理或使用情况的影响，请参阅从德国 Microsoft 云迁移的其他[Azure AD](ms-cloud-germany-transition-azure-ad.md)信息中有关 Azure Active Directory (Azure AD) 的信息。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="e2bf8-180">iOS</span><span class="sxs-lookup"><span data-stu-id="e2bf8-180">iOS</span></span>

<span data-ttu-id="e2bf8-181">在 iOS 设备上，用户需要手动从 Microsoft Authenticator 中删除任何缓存的帐户、注销设备以及从设备上的任何本机应用注销。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="e2bf8-182">步骤 1：如果存在，请从应用中删除Microsoft Authenticator帐户</span><span class="sxs-lookup"><span data-stu-id="e2bf8-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="e2bf8-183">点击"管理"应用中Microsoft Authenticator帐户。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="e2bf8-184">点击 **设置** 右上角的"页面"图标。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="e2bf8-185">如果未看到"设置"图标，则可能不会使用最新版本的 Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="e2bf8-186">点击" **删除帐户"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="e2bf8-187">点击 **此设备上的所有应用**。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-187">Tap **All apps on this device**.</span></span>

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="e2bf8-188">步骤 2：从应用注销Microsoft Authenticator设备</span><span class="sxs-lookup"><span data-stu-id="e2bf8-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="e2bf8-189">点击右上角的菜单图标。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="e2bf8-190">依次 **设置"** 设备 **注册"。**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-190">Tap **Settings** and then **Device Registration**.</span></span>
3. <span data-ttu-id="e2bf8-191">If your account is shown， tap **Unregister device** and **Continue** in the dialog.</span><span class="sxs-lookup"><span data-stu-id="e2bf8-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="e2bf8-192">此后应该看不到任何帐户。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-192">You should see no account after that.</span></span>

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="e2bf8-193">步骤 3：如有必要从个别应用注销</span><span class="sxs-lookup"><span data-stu-id="e2bf8-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="e2bf8-194">用户可以转到单个应用，Outlook、Teams和OneDrive，并从这些应用中删除帐户。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e2bf8-195">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="e2bf8-195">Frequently asked questions</span></span>

<span data-ttu-id="e2bf8-196">**如何判断我的组织是否受到影响？**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="e2bf8-197">管理员应检查 `https://portal.microsoftazure.de` 以确定他们是否有已注册 Azure AD 或加入 Azure AD 的设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="e2bf8-198">如果你的组织已注册 Azure AD 或加入 Azure AD 的设备，则你的组织必须遵循此页面上的说明。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="e2bf8-199">**我的用户何时重新注册其设备？**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="e2bf8-200">阶段 [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 完成后仅注销和重新注册设备，这一点对于成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="e2bf8-201">你必须在阶段 10 启动之前完成重新注册，否则你可能会失去对设备的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="e2bf8-202">**我如何知道我的所有设备都注册到公共云中？**</span><span class="sxs-lookup"><span data-stu-id="e2bf8-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="e2bf8-203">若要检查你的设备是否已在公有云中注册，你应该将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="e2bf8-204">然后，使用 _registeredTime_ 列 (在组织通过迁移过程的第 [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)阶段) 注册的设备。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="e2bf8-205">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="e2bf8-205">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2bf8-206">Intune 服务主体将在迁移过程的第 [3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)阶段之后启用，这意味着将激活 Azure AD 设备注册。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-206">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="e2bf8-207">如果在迁移之前阻止了 Azure AD 设备注册，则必须使用 PowerShell 禁用 Intune 服务主体，以再次禁用 Azure AD 门户的 Azure AD 设备注册。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-207">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="e2bf8-208">可以使用 PowerShell for Azure Active Directory 模块中的此命令禁用 Intune Graph主体。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-208">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="e2bf8-209">更多信息</span><span class="sxs-lookup"><span data-stu-id="e2bf8-209">More information</span></span>

<span data-ttu-id="e2bf8-210">入门：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-210">Getting started:</span></span>

- [<span data-ttu-id="e2bf8-211">从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务</span><span class="sxs-lookup"><span data-stu-id="e2bf8-211">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="e2bf8-212">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="e2bf8-212">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="e2bf8-213">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="e2bf8-213">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="e2bf8-214">迁移期间客户体验</span><span class="sxs-lookup"><span data-stu-id="e2bf8-214">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="e2bf8-215">在转换过程中移动：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-215">Moving through the transition:</span></span>

- [<span data-ttu-id="e2bf8-216">迁移阶段操作和影响</span><span class="sxs-lookup"><span data-stu-id="e2bf8-216">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="e2bf8-217">其他前期工作</span><span class="sxs-lookup"><span data-stu-id="e2bf8-217">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="e2bf8-218">Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="e2bf8-218">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="e2bf8-219">云应用：</span><span class="sxs-lookup"><span data-stu-id="e2bf8-219">Cloud apps:</span></span>

- [<span data-ttu-id="e2bf8-220">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="e2bf8-220">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="e2bf8-221">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="e2bf8-221">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="e2bf8-222">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="e2bf8-222">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
