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
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928152"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="c14c4-103">从德国 Microsoft 云迁移的其他设备信息</span><span class="sxs-lookup"><span data-stu-id="c14c4-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c14c4-104">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c14c4-104">Frequently asked questions</span></span>

<span data-ttu-id="c14c4-105">**如何判断我的组织是否受到影响？**</span><span class="sxs-lookup"><span data-stu-id="c14c4-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="c14c4-106">管理员应检查 `https://portal.microsoftazure.de` 以确定他们是否有注册的设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="c14c4-107">如果你的组织已注册设备，你将受到影响。</span><span class="sxs-lookup"><span data-stu-id="c14c4-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="c14c4-108">**对用户有什么影响？**</span><span class="sxs-lookup"><span data-stu-id="c14c4-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="c14c4-109">在迁移进入完成 [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段后，已注册设备中的用户将无法再登录。</span><span class="sxs-lookup"><span data-stu-id="c14c4-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="c14c4-110">在组织与德国 Microsoft 云断开连接之前，请确保你的所有设备已注册到全球终结点。</span><span class="sxs-lookup"><span data-stu-id="c14c4-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="c14c4-111">**我的用户何时重新注册其设备？**</span><span class="sxs-lookup"><span data-stu-id="c14c4-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="c14c4-112">在"德国 Microsoft 云分离"迁移阶段，仅注销和重新注册设备对于[成功至关重要。](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="c14c4-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c14c4-113">**如何在迁移后还原设备状态？**</span><span class="sxs-lookup"><span data-stu-id="c14c4-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="c14c4-114">对于在 Azure AD 中注册的已加入 Azure AD 的混合和公司拥有的 Windows 设备，管理员将能够通过远程触发的工作流管理这些设备的迁移，这些工作流将注销旧设备状态。</span><span class="sxs-lookup"><span data-stu-id="c14c4-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="c14c4-115">对于所有其他设备，包括在 Azure AD Windows个人设备，最终用户必须手动执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c14c4-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="c14c4-116">对于加入 Azure AD 的设备，用户需要具有本地管理员帐户才能注销然后重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="c14c4-117">Microsoft 将发布有关如何成功还原设备状态的说明。</span><span class="sxs-lookup"><span data-stu-id="c14c4-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="c14c4-118">**我如何知道我的所有设备都注册到公共云中？**</span><span class="sxs-lookup"><span data-stu-id="c14c4-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="c14c4-119">若要检查你的设备是否已在公有云中注册，你应该将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="c14c4-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="c14c4-120">然后，使用 _registeredTime_ 列 (从 [德国 Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 云迁移) 注册的设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c14c4-121">迁移租户后，设备注册将停用，并且无法启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="c14c4-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="c14c4-122">如果未使用 Intune，请登录到你的订阅并运行此命令以重新激活选项：</span><span class="sxs-lookup"><span data-stu-id="c14c4-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="c14c4-123">混合 Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="c14c4-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="c14c4-124">Windows级别</span><span class="sxs-lookup"><span data-stu-id="c14c4-124">Windows down-level</span></span>

<span data-ttu-id="c14c4-125">_Windows_ 低级别设备是当前运行早期版本的 Windows (（如 Windows 8.1 或 Windows 7) ）或运行 2019 和 2016 之前版本的 Windows Server 的 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="c14c4-126">如果之前已注册此类设备，则需要注销并重新注册这些设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="c14c4-127">若要确定Windows设备先前是否已加入 Azure AD，请对设备使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="c14c4-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="c14c4-128">如果设备之前已加入 Azure AD，并且设备具有到全局 Azure AD 终结点的网络连接，你将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="c14c4-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="c14c4-129">受影响的设备将具有值为"Unknown"的"设备状态"。</span><span class="sxs-lookup"><span data-stu-id="c14c4-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="c14c4-130">如果输出为"Device not joined"或其"Device state"值为"Ok"，请忽略以下指南。</span><span class="sxs-lookup"><span data-stu-id="c14c4-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="c14c4-131">仅对于设备通过 deviceId、指纹等) 且"设备状态"值为"未知"而加入 (的设备，管理员应在此类低级别设备上登录的域用户上下文中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c14c4-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="c14c4-132">在低级别设备上，每个登录域用户只需运行Windows一次。</span><span class="sxs-lookup"><span data-stu-id="c14c4-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="c14c4-133">此命令应在域用户登录的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="c14c4-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="c14c4-134">在用户随后登录时，必须小心不要运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c14c4-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="c14c4-135">当上述命令运行时，它将为登录的用户清除已加入本地混合 Azure AD 的计算机的联接状态。</span><span class="sxs-lookup"><span data-stu-id="c14c4-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="c14c4-136">此外，如果计算机仍配置为已加入租户中的混合 Azure AD，它将尝试在用户重新登录时加入。</span><span class="sxs-lookup"><span data-stu-id="c14c4-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="c14c4-137">WindowsCurrent</span><span class="sxs-lookup"><span data-stu-id="c14c4-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="c14c4-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="c14c4-138">Unjoin</span></span>

<span data-ttu-id="c14c4-139">若要确定Windows 10是否已加入 Azure AD，请对设备运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c14c4-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c14c4-140">如果设备已加入混合 Azure AD，管理员将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="c14c4-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="c14c4-141">如果输出为"AzureAdJoined ： 否"，请忽略以下指南。</span><span class="sxs-lookup"><span data-stu-id="c14c4-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="c14c4-142">仅对于显示设备已加入 Azure AD 的设备，以管理员角色运行以下命令以删除设备的加入状态。</span><span class="sxs-lookup"><span data-stu-id="c14c4-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c14c4-143">上述命令只需在设备上管理上下文中运行一Windows。</span><span class="sxs-lookup"><span data-stu-id="c14c4-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="c14c4-144">混合 AD 加入\重新注册</span><span class="sxs-lookup"><span data-stu-id="c14c4-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="c14c4-145">只要设备具有到全局 Azure AD 终结点的网络连接，设备就会自动加入 Azure AD，无需用户或管理员干预。</span><span class="sxs-lookup"><span data-stu-id="c14c4-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="c14c4-146">加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="c14c4-146">Azure AD Join</span></span>

<span data-ttu-id="c14c4-147">**重要提示：** 商业迁移后将启用 Intune 服务主体，这意味着激活 Azure AD 设备注册。</span><span class="sxs-lookup"><span data-stu-id="c14c4-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="c14c4-148">如果在迁移之前阻止了 Azure AD 设备注册，则必须使用 PowerShell 禁用 Intune 服务主体，以再次禁用 Azure AD 门户的 Azure AD 设备注册。</span><span class="sxs-lookup"><span data-stu-id="c14c4-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="c14c4-149">可以使用 PowerShell for Azure Active Directory 模块中的此命令禁用 Intune Graph主体。</span><span class="sxs-lookup"><span data-stu-id="c14c4-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="c14c4-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="c14c4-150">Unjoin</span></span>

<span data-ttu-id="c14c4-151">若要确定Windows 10是否已加入 Azure AD，用户或管理员可以在设备上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c14c4-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c14c4-152">如果设备已加入 Azure AD，用户或管理员将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="c14c4-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="c14c4-153">如果输出为"AzureAdJoined ： NO"，则忽略以下指南。</span><span class="sxs-lookup"><span data-stu-id="c14c4-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="c14c4-154">用户：如果设备已加入 Azure AD，用户可以从设置中取消加入设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="c14c4-155">在从 Azure AD 中取消加入设备之前，请验证设备上是否有本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="c14c4-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c14c4-156">需要本地管理员帐户才能重新登录设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="c14c4-157">管理员：如果组织的管理员想要取消加入已加入 Azure AD 的用户设备，他们可以使用组策略等机制在每个设备上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c14c4-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="c14c4-158">在从 Azure AD 中取消加入设备之前，管理员必须验证设备上是否有本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="c14c4-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c14c4-159">需要本地管理员帐户才能重新登录设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c14c4-160">上述命令只需在设备上管理上下文中运行一Windows。</span><span class="sxs-lookup"><span data-stu-id="c14c4-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="c14c4-161">Azure AD 加入/重新注册</span><span class="sxs-lookup"><span data-stu-id="c14c4-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="c14c4-162">用户可以从以下设置将设备加入 Azure AD：Windows帐户设置 >访问>访问 **工作或**> 连接。</span><span class="sxs-lookup"><span data-stu-id="c14c4-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="c14c4-163">Azure AD 注册 (公司拥有) </span><span class="sxs-lookup"><span data-stu-id="c14c4-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="c14c4-164">若要确定 Windows 10是否已注册 Azure AD，请对设备运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c14c4-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c14c4-165">如果设备已注册 Azure AD，你将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="c14c4-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="c14c4-166">若要删除设备上现有的 Azure AD 注册帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c14c4-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="c14c4-167">若要删除设备上已注册 Azure AD 的帐户，请使用 CleanupWPJ，可从此处下载的工具[：CleanupWPJ.zip。 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="c14c4-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="c14c4-168">提取 ZIP 文件并运行 **WPJCleanup.cmd**。</span><span class="sxs-lookup"><span data-stu-id="c14c4-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="c14c4-169">此工具将基于设备上文件的版本Windows正确的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="c14c4-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="c14c4-170">通过使用组策略等机制，管理员可以在设备上登录的任何用户的上下文中运行命令。</span><span class="sxs-lookup"><span data-stu-id="c14c4-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="c14c4-171">若要禁用 Web 帐户管理器提示在 Azure AD 中注册设备，请添加以下注册表值：</span><span class="sxs-lookup"><span data-stu-id="c14c4-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="c14c4-172">位置：HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="c14c4-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="c14c4-173">类型：DWORD (32 位) </span><span class="sxs-lookup"><span data-stu-id="c14c4-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="c14c4-174">名称：BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="c14c4-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="c14c4-175">值数据：1</span><span class="sxs-lookup"><span data-stu-id="c14c4-175">Value data: 1</span></span>

<span data-ttu-id="c14c4-176">存在此注册表值应阻止工作区加入，并阻止用户看到加入设备的提示。</span><span class="sxs-lookup"><span data-stu-id="c14c4-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="c14c4-177">Android</span><span class="sxs-lookup"><span data-stu-id="c14c4-177">Android</span></span>

<span data-ttu-id="c14c4-178">对于 Android，用户需要注销并重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="c14c4-179">这可以通过 Microsoft Authenticator 或 公司门户 应用完成。</span><span class="sxs-lookup"><span data-stu-id="c14c4-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="c14c4-180">从Microsoft Authenticator应用，用户可以转到设置 >**注册"。**</span><span class="sxs-lookup"><span data-stu-id="c14c4-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="c14c4-181">在这里，用户可以注销和重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="c14c4-182">从公司门户，用户可以转到"**设备**"选项卡并删除设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="c14c4-183">此后，使用"配置"公司门户。</span><span class="sxs-lookup"><span data-stu-id="c14c4-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="c14c4-184">用户还可以从帐户设置页中删除帐户，然后重新添加工作帐户，从而注销和重新注册。</span><span class="sxs-lookup"><span data-stu-id="c14c4-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="c14c4-185">若要在 Android 上注销和重新注册设备，请运行Microsoft Authenticator应用：</span><span class="sxs-lookup"><span data-stu-id="c14c4-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="c14c4-186">打开 Microsoft Authenticator 应用，**然后转到** 设置 。</span><span class="sxs-lookup"><span data-stu-id="c14c4-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="c14c4-187">选择 **"设备注册"。**</span><span class="sxs-lookup"><span data-stu-id="c14c4-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="c14c4-188">通过选择"注销"取消 **注册设备**。</span><span class="sxs-lookup"><span data-stu-id="c14c4-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="c14c4-189">对于 **设备注册**，请通过键入你的电子邮件地址重新注册设备，**然后选择注册。**</span><span class="sxs-lookup"><span data-stu-id="c14c4-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="c14c4-190">若要注销 Android 设备并重新注册 Android 设置页面：</span><span class="sxs-lookup"><span data-stu-id="c14c4-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="c14c4-191">打开 **设备设置\*\*\*\*转到帐户**。</span><span class="sxs-lookup"><span data-stu-id="c14c4-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="c14c4-192">选择要重新注册的工作帐户，然后选择"删除 **帐户"。**</span><span class="sxs-lookup"><span data-stu-id="c14c4-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="c14c4-193">删除帐户后，从"帐户"**页面** 选择"添加帐户>**工作帐户"。**</span><span class="sxs-lookup"><span data-stu-id="c14c4-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="c14c4-194">对于 **Workplace Join，** 键入你的电子邮件地址，然后选择 **加入** 以完成设备注册。</span><span class="sxs-lookup"><span data-stu-id="c14c4-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="c14c4-195">若要在 Android 上注销并重新注册设备，请公司门户：</span><span class="sxs-lookup"><span data-stu-id="c14c4-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="c14c4-196">启动公司门户并转到 **设备** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c14c4-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="c14c4-197">选择设备以查看设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="c14c4-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="c14c4-198">From theellipses (three dots) menu， select **Remove Device**， and complete the removal by confirming in the dialog.</span><span class="sxs-lookup"><span data-stu-id="c14c4-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="c14c4-199">你现在应该已注销公司门户应用。</span><span class="sxs-lookup"><span data-stu-id="c14c4-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="c14c4-200">选择 **"登录** "以重新注册设备。</span><span class="sxs-lookup"><span data-stu-id="c14c4-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="c14c4-201">有关此工作负载的迁移阶段需要执行的任何操作或对管理或使用情况的影响，请参阅从德国 Microsoft 云迁移的其他[Azure AD](ms-cloud-germany-transition-azure-ad.md)信息中有关 Azure Active Directory (Azure AD) 的信息。</span><span class="sxs-lookup"><span data-stu-id="c14c4-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="c14c4-202">iOS</span><span class="sxs-lookup"><span data-stu-id="c14c4-202">iOS</span></span>

<span data-ttu-id="c14c4-203">在 iOS 设备上，用户需要手动从 Microsoft Authenticator 中删除任何缓存的帐户、注销设备以及从设备上的任何本机应用注销。</span><span class="sxs-lookup"><span data-stu-id="c14c4-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c14c4-204">步骤 1：如果存在，请从应用中删除Microsoft Authenticator帐户</span><span class="sxs-lookup"><span data-stu-id="c14c4-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c14c4-205">点击"管理"应用中Microsoft Authenticator帐户。</span><span class="sxs-lookup"><span data-stu-id="c14c4-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="c14c4-206">点击 **设置** 右上角的"页面"图标。</span><span class="sxs-lookup"><span data-stu-id="c14c4-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="c14c4-207">如果未看到"设置"图标，则可能不会使用最新版本的 Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="c14c4-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="c14c4-208">点击" **删除帐户"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c14c4-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="c14c4-209">点击 **此设备上的所有应用**。</span><span class="sxs-lookup"><span data-stu-id="c14c4-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c14c4-210">步骤 2：从应用注销Microsoft Authenticator设备</span><span class="sxs-lookup"><span data-stu-id="c14c4-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c14c4-211">点击右上角的菜单图标。</span><span class="sxs-lookup"><span data-stu-id="c14c4-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="c14c4-212">依次 **设置"** 设备 **注册"。**</span><span class="sxs-lookup"><span data-stu-id="c14c4-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="c14c4-213">If your account is shown， tap **Unregister device** and **Continue** in the dialog.</span><span class="sxs-lookup"><span data-stu-id="c14c4-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="c14c4-214">此后应该看不到任何帐户。</span><span class="sxs-lookup"><span data-stu-id="c14c4-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="c14c4-215">步骤 3：如有必要从个别应用注销</span><span class="sxs-lookup"><span data-stu-id="c14c4-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="c14c4-216">用户可以转到单个应用，Outlook、Teams和OneDrive，并从这些应用中删除帐户。</span><span class="sxs-lookup"><span data-stu-id="c14c4-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="c14c4-217">详细信息</span><span class="sxs-lookup"><span data-stu-id="c14c4-217">More information</span></span>

<span data-ttu-id="c14c4-218">入门：</span><span class="sxs-lookup"><span data-stu-id="c14c4-218">Getting started:</span></span>

- [<span data-ttu-id="c14c4-219">从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务</span><span class="sxs-lookup"><span data-stu-id="c14c4-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="c14c4-220">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="c14c4-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="c14c4-221">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="c14c4-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="c14c4-222">迁移期间客户体验</span><span class="sxs-lookup"><span data-stu-id="c14c4-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="c14c4-223">在转换过程中移动：</span><span class="sxs-lookup"><span data-stu-id="c14c4-223">Moving through the transition:</span></span>

- [<span data-ttu-id="c14c4-224">迁移阶段操作和影响</span><span class="sxs-lookup"><span data-stu-id="c14c4-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="c14c4-225">其他前期工作</span><span class="sxs-lookup"><span data-stu-id="c14c4-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="c14c4-226">Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="c14c4-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="c14c4-227">云应用：</span><span class="sxs-lookup"><span data-stu-id="c14c4-227">Cloud apps:</span></span>

- [<span data-ttu-id="c14c4-228">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="c14c4-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="c14c4-229">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="c14c4-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="c14c4-230">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="c14c4-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)