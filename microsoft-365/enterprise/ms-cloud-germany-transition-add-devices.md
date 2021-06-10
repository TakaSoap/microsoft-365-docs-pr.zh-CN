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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861296"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="8ea73-103">从德国 Microsoft 云迁移的其他设备信息</span><span class="sxs-lookup"><span data-stu-id="8ea73-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="8ea73-104">连接到德国 Microsoft 云的已加入和注册的 Azure AD 设备必须在第 9 阶段之后和阶段 10 之前进行迁移。</span><span class="sxs-lookup"><span data-stu-id="8ea73-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="8ea73-105">设备的迁移取决于设备类型、操作系统和 AAD 关系。</span><span class="sxs-lookup"><span data-stu-id="8ea73-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="8ea73-106">常见问题</span><span class="sxs-lookup"><span data-stu-id="8ea73-106">Frequently asked questions</span></span>

<span data-ttu-id="8ea73-107">**如何判断我的组织是否受到影响？**</span><span class="sxs-lookup"><span data-stu-id="8ea73-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="8ea73-108">管理员应检查 `https://portal.microsoftazure.de` 以确定他们是否有已注册或已加入 Azure AD 的设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="8ea73-109">如果你的组织已注册设备，你将受到影响。</span><span class="sxs-lookup"><span data-stu-id="8ea73-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="8ea73-110">**对用户有什么影响？**</span><span class="sxs-lookup"><span data-stu-id="8ea73-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="8ea73-111">完成迁移阶段 [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 且 Microsoft 云德国终结点已禁用后，已注册设备的用户将无法再登录。</span><span class="sxs-lookup"><span data-stu-id="8ea73-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="8ea73-112">在组织与德国 Microsoft 云断开连接之前，请确保你的所有设备已注册到全球终结点。</span><span class="sxs-lookup"><span data-stu-id="8ea73-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="8ea73-113">**我的用户何时重新注册其设备？**</span><span class="sxs-lookup"><span data-stu-id="8ea73-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="8ea73-114">阶段 [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 完成后仅注销和重新注册设备，这一点对于成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="8ea73-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="8ea73-115">你必须在阶段 10 启动之前完成重新注册，否则你可能会失去对设备的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ea73-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="8ea73-116">**如何在迁移后还原设备状态？**</span><span class="sxs-lookup"><span data-stu-id="8ea73-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="8ea73-117">对于在 Azure AD Windows公司拥有的设备，管理员将能够通过远程触发的工作流管理这些设备的迁移，这些工作流将取消注册旧设备状态。</span><span class="sxs-lookup"><span data-stu-id="8ea73-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="8ea73-118">对于所有其他设备，包括在 Azure AD Windows个人设备，最终用户必须手动执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="8ea73-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="8ea73-119">对于加入 Azure AD 的设备，用户需要具有本地管理员帐户才能注销然后重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="8ea73-120">请参阅下面的有关如何成功还原设备状态的详细说明。</span><span class="sxs-lookup"><span data-stu-id="8ea73-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="8ea73-121">**我如何知道我的所有设备都注册到公共云中？**</span><span class="sxs-lookup"><span data-stu-id="8ea73-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="8ea73-122">若要检查你的设备是否已在公有云中注册，你应该将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="8ea73-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="8ea73-123">然后，使用 _registeredTime_ 列 (从 [德国 Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 云迁移) 注册的设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="8ea73-124">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="8ea73-124">Additional considerations</span></span>
<span data-ttu-id="8ea73-125">迁移租户后，设备注册将停用，并且无法启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="8ea73-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="8ea73-126">如果未使用 Intune，请登录到你的订阅并运行此命令以重新激活选项：</span><span class="sxs-lookup"><span data-stu-id="8ea73-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="8ea73-127">**重要提示：** 商业迁移后将启用 Intune 服务主体，这意味着激活 Azure AD 设备注册。</span><span class="sxs-lookup"><span data-stu-id="8ea73-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="8ea73-128">如果在迁移之前阻止了 Azure AD 设备注册，则必须使用 PowerShell 禁用 Intune 服务主体，以再次禁用 Azure AD 门户的 Azure AD 设备注册。</span><span class="sxs-lookup"><span data-stu-id="8ea73-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="8ea73-129">可以使用 PowerShell for Azure Active Directory 模块中的此命令禁用 Intune Graph主体。</span><span class="sxs-lookup"><span data-stu-id="8ea73-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="8ea73-130">加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ea73-130">Azure AD Join</span></span>
<span data-ttu-id="8ea73-131">这适用于Windows 10设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="8ea73-132">如果设备已加入 Azure AD，则必须从 Azure AD 断开连接，然后重新连接。</span><span class="sxs-lookup"><span data-stu-id="8ea73-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="8ea73-133">[![Azure AD 设备Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8ea73-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="8ea73-134">如果用户是设备管理员，Windows 10 Azure AD 取消注册设备，然后重新加入该设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="8ea73-135">如果没有管理员权限，则用户需要此计算机上本地管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="8ea73-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="8ea73-136">管理员可以按照以下配置路径在设备上创建本地管理员帐户：</span><span class="sxs-lookup"><span data-stu-id="8ea73-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="8ea73-137">*设置 >帐户>其他帐户>凭据未知> Microsoft 帐户添加用户*</span><span class="sxs-lookup"><span data-stu-id="8ea73-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="8ea73-138">步骤 1：确定设备是否加入 Azure ID</span><span class="sxs-lookup"><span data-stu-id="8ea73-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="8ea73-139">使用用户电子邮件和密码登录。</span><span class="sxs-lookup"><span data-stu-id="8ea73-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="8ea73-140">转到"设置 >访问>或学校帐户"。</span><span class="sxs-lookup"><span data-stu-id="8ea73-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="8ea73-141">在列表中查找已连接到 **的用户...的 Azure AD**。</span><span class="sxs-lookup"><span data-stu-id="8ea73-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="8ea73-142">如果已连接的用户存在，请继续执行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="8ea73-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="8ea73-143">如果没有，则无需执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="8ea73-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="8ea73-144">步骤 2：断开设备与 Azure AD 连接</span><span class="sxs-lookup"><span data-stu-id="8ea73-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="8ea73-145">点击 **已连接** 的工作或学校帐户上的"断开连接"。</span><span class="sxs-lookup"><span data-stu-id="8ea73-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="8ea73-146">确认断开连接两次。</span><span class="sxs-lookup"><span data-stu-id="8ea73-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="8ea73-147">输入本地管理员用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8ea73-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="8ea73-148">设备已断开连接。</span><span class="sxs-lookup"><span data-stu-id="8ea73-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="8ea73-149">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="8ea73-150">步骤 3：将设备加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ea73-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="8ea73-151">用户使用本地管理员的凭据登录</span><span class="sxs-lookup"><span data-stu-id="8ea73-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="8ea73-152">转到 **"设置"，** 然后转到 **"帐户"，\*\*\*\*然后访问工作或学校**</span><span class="sxs-lookup"><span data-stu-id="8ea73-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="8ea73-153">点击 **连接**</span><span class="sxs-lookup"><span data-stu-id="8ea73-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="8ea73-154">**重要** 提示：点击 **加入 Azure AD**</span><span class="sxs-lookup"><span data-stu-id="8ea73-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="8ea73-155">输入用户的电子邮件地址和密码。</span><span class="sxs-lookup"><span data-stu-id="8ea73-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="8ea73-156">设备已连接</span><span class="sxs-lookup"><span data-stu-id="8ea73-156">The device is connected</span></span>
6.  <span data-ttu-id="8ea73-157">重新启动设备</span><span class="sxs-lookup"><span data-stu-id="8ea73-157">Restart the device</span></span> 
7.  <span data-ttu-id="8ea73-158">使用电子邮件地址和密码进行签名</span><span class="sxs-lookup"><span data-stu-id="8ea73-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="8ea73-159">Azure AD 注册 (公司拥有) </span><span class="sxs-lookup"><span data-stu-id="8ea73-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="8ea73-160">若要确定 Windows 10是否已注册 Azure AD，请对设备运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8ea73-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="8ea73-161">如果设备已注册 Azure AD，你将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="8ea73-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="8ea73-162">若要删除设备上现有的 Azure AD 注册帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8ea73-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="8ea73-163">若要删除设备上已注册 Azure AD 的帐户，请使用 CleanupWPJ，可从此处下载的工具[：CleanupWPJ.zip。 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="8ea73-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="8ea73-164">提取 ZIP 文件并运行 **WPJCleanup.cmd**。</span><span class="sxs-lookup"><span data-stu-id="8ea73-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="8ea73-165">此工具将基于设备上文件的版本Windows正确的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="8ea73-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="8ea73-166">通过使用组策略等机制，管理员可以在设备上登录的任何用户的上下文中运行命令。</span><span class="sxs-lookup"><span data-stu-id="8ea73-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="8ea73-167">若要禁用 Web 帐户管理器提示在 Azure AD 中注册设备，请添加以下注册表值：</span><span class="sxs-lookup"><span data-stu-id="8ea73-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="8ea73-168">位置：HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="8ea73-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="8ea73-169">类型：DWORD (32 位) </span><span class="sxs-lookup"><span data-stu-id="8ea73-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="8ea73-170">名称：BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="8ea73-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="8ea73-171">值数据：1</span><span class="sxs-lookup"><span data-stu-id="8ea73-171">Value data: 1</span></span>

<span data-ttu-id="8ea73-172">存在此注册表值应阻止工作区加入，并阻止用户看到加入设备的提示。</span><span class="sxs-lookup"><span data-stu-id="8ea73-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="8ea73-173">Android</span><span class="sxs-lookup"><span data-stu-id="8ea73-173">Android</span></span>

<span data-ttu-id="8ea73-174">对于 Android，用户需要注销并重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="8ea73-175">这可以通过 Microsoft Authenticator 或 公司门户 应用完成。</span><span class="sxs-lookup"><span data-stu-id="8ea73-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="8ea73-176">从Microsoft Authenticator应用，用户可以转到设置 >**注册"。**</span><span class="sxs-lookup"><span data-stu-id="8ea73-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="8ea73-177">在这里，用户可以注销和重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="8ea73-178">从公司门户，用户可以转到"**设备**"选项卡并删除设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="8ea73-179">此后，使用"配置"公司门户。</span><span class="sxs-lookup"><span data-stu-id="8ea73-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="8ea73-180">用户还可以从帐户设置页中删除帐户，然后重新添加工作帐户，从而注销和重新注册。</span><span class="sxs-lookup"><span data-stu-id="8ea73-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="8ea73-181">若要在 Android 上注销和重新注册设备，请运行Microsoft Authenticator应用：</span><span class="sxs-lookup"><span data-stu-id="8ea73-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="8ea73-182">打开 Microsoft Authenticator 应用，**然后转到** 设置 。</span><span class="sxs-lookup"><span data-stu-id="8ea73-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="8ea73-183">选择 **"设备注册"。**</span><span class="sxs-lookup"><span data-stu-id="8ea73-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="8ea73-184">通过选择"注销"取消 **注册设备**。</span><span class="sxs-lookup"><span data-stu-id="8ea73-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="8ea73-185">对于 **设备注册**，请通过键入你的电子邮件地址重新注册设备，**然后选择注册。**</span><span class="sxs-lookup"><span data-stu-id="8ea73-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="8ea73-186">若要注销 Android 设备并重新注册 Android 设置页面：</span><span class="sxs-lookup"><span data-stu-id="8ea73-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="8ea73-187">打开 **设备设置\*\*\*\*转到帐户**。</span><span class="sxs-lookup"><span data-stu-id="8ea73-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="8ea73-188">选择要重新注册的工作帐户，然后选择"删除 **帐户"。**</span><span class="sxs-lookup"><span data-stu-id="8ea73-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="8ea73-189">删除帐户后，从"帐户"**页面** 选择"添加帐户>**工作帐户"。**</span><span class="sxs-lookup"><span data-stu-id="8ea73-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="8ea73-190">对于 **Workplace Join，** 键入你的电子邮件地址，然后选择 **加入** 以完成设备注册。</span><span class="sxs-lookup"><span data-stu-id="8ea73-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="8ea73-191">若要在 Android 上注销并重新注册设备，请公司门户：</span><span class="sxs-lookup"><span data-stu-id="8ea73-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="8ea73-192">启动公司门户并转到 **设备** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8ea73-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="8ea73-193">选择设备以查看设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ea73-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="8ea73-194">From theellipses (three dots) menu， select **Remove Device**， and complete the removal by confirming in the dialog.</span><span class="sxs-lookup"><span data-stu-id="8ea73-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="8ea73-195">你现在应该已注销公司门户应用。</span><span class="sxs-lookup"><span data-stu-id="8ea73-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="8ea73-196">选择 **"登录** "以重新注册设备。</span><span class="sxs-lookup"><span data-stu-id="8ea73-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="8ea73-197">有关此工作负载的迁移阶段需要执行的任何操作或对管理或使用情况的影响，请参阅从德国 Microsoft 云迁移的其他[Azure AD](ms-cloud-germany-transition-azure-ad.md)信息中有关 Azure Active Directory (Azure AD) 的信息。</span><span class="sxs-lookup"><span data-stu-id="8ea73-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="8ea73-198">iOS</span><span class="sxs-lookup"><span data-stu-id="8ea73-198">iOS</span></span>

<span data-ttu-id="8ea73-199">在 iOS 设备上，用户需要手动从 Microsoft Authenticator 中删除任何缓存的帐户、注销设备以及从设备上的任何本机应用注销。</span><span class="sxs-lookup"><span data-stu-id="8ea73-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="8ea73-200">步骤 1：如果存在，请从应用中删除Microsoft Authenticator帐户</span><span class="sxs-lookup"><span data-stu-id="8ea73-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="8ea73-201">点击"管理"应用中Microsoft Authenticator帐户。</span><span class="sxs-lookup"><span data-stu-id="8ea73-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="8ea73-202">点击 **设置** 右上角的"页面"图标。</span><span class="sxs-lookup"><span data-stu-id="8ea73-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="8ea73-203">如果未看到"设置"图标，则可能不会使用最新版本的 Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="8ea73-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="8ea73-204">点击" **删除帐户"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="8ea73-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="8ea73-205">点击 **此设备上的所有应用**。</span><span class="sxs-lookup"><span data-stu-id="8ea73-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="8ea73-206">步骤 2：从应用注销Microsoft Authenticator设备</span><span class="sxs-lookup"><span data-stu-id="8ea73-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="8ea73-207">点击右上角的菜单图标。</span><span class="sxs-lookup"><span data-stu-id="8ea73-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="8ea73-208">依次 **设置"** 设备 **注册"。**</span><span class="sxs-lookup"><span data-stu-id="8ea73-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="8ea73-209">If your account is shown， tap **Unregister device** and **Continue** in the dialog.</span><span class="sxs-lookup"><span data-stu-id="8ea73-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="8ea73-210">此后应该看不到任何帐户。</span><span class="sxs-lookup"><span data-stu-id="8ea73-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="8ea73-211">步骤 3：如有必要从个别应用注销</span><span class="sxs-lookup"><span data-stu-id="8ea73-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="8ea73-212">用户可以转到单个应用，Outlook、Teams和OneDrive，并从这些应用中删除帐户。</span><span class="sxs-lookup"><span data-stu-id="8ea73-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="8ea73-213">详细信息</span><span class="sxs-lookup"><span data-stu-id="8ea73-213">More information</span></span>

<span data-ttu-id="8ea73-214">入门：</span><span class="sxs-lookup"><span data-stu-id="8ea73-214">Getting started:</span></span>

- [<span data-ttu-id="8ea73-215">从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务</span><span class="sxs-lookup"><span data-stu-id="8ea73-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="8ea73-216">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="8ea73-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="8ea73-217">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="8ea73-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="8ea73-218">迁移期间客户体验</span><span class="sxs-lookup"><span data-stu-id="8ea73-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="8ea73-219">在转换过程中移动：</span><span class="sxs-lookup"><span data-stu-id="8ea73-219">Moving through the transition:</span></span>

- [<span data-ttu-id="8ea73-220">迁移阶段操作和影响</span><span class="sxs-lookup"><span data-stu-id="8ea73-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="8ea73-221">其他前期工作</span><span class="sxs-lookup"><span data-stu-id="8ea73-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="8ea73-222">Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="8ea73-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="8ea73-223">云应用：</span><span class="sxs-lookup"><span data-stu-id="8ea73-223">Cloud apps:</span></span>

- [<span data-ttu-id="8ea73-224">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="8ea73-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="8ea73-225">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="8ea73-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="8ea73-226">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="8ea73-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)