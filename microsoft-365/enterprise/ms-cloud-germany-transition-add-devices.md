---
title: 从 Microsoft 云德国迁移的其他设备信息
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
description: 摘要：在 (Microsoft 云德国中移动时服务的其他设备信息。) 到新的德国数据中心区域中的 Office 365 服务。
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551949"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="9700d-103">从 Microsoft 云德国迁移的其他设备信息</span><span class="sxs-lookup"><span data-stu-id="9700d-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9700d-104">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="9700d-104">Frequently asked questions</span></span>

<span data-ttu-id="9700d-105">**如何判断我的组织是否受到影响？**</span><span class="sxs-lookup"><span data-stu-id="9700d-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="9700d-106">管理员应 `https://portal.microsoftazure.de` 进行检查以确定他们是否有任何已注册的设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="9700d-107">如果你的组织已注册设备，则会受到影响。</span><span class="sxs-lookup"><span data-stu-id="9700d-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="9700d-108">**对我的用户有什么影响？**</span><span class="sxs-lookup"><span data-stu-id="9700d-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="9700d-109">迁移进入 [Finalize AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段后，已注册设备的用户将无法再登录。</span><span class="sxs-lookup"><span data-stu-id="9700d-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="9700d-110">确保在您的组织从 Microsoft 云德国断开连接之前，向全球终结点注册所有设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="9700d-111">**我的用户何时重新注册其设备？**</span><span class="sxs-lookup"><span data-stu-id="9700d-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="9700d-112">您的成功只是在 [独立 Microsoft 云德国](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段注销和重新注册设备，这一点非常关键。</span><span class="sxs-lookup"><span data-stu-id="9700d-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="9700d-113">**如何在迁移后还原设备状态？**</span><span class="sxs-lookup"><span data-stu-id="9700d-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="9700d-114">对于使用 Azure AD 注册的混合 Azure AD （已加入和公司拥有的 Windows 设备），管理员将能够通过将注销旧设备状态的远程触发工作流来管理这些设备的迁移。</span><span class="sxs-lookup"><span data-stu-id="9700d-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="9700d-115">对于所有其他设备（包括在 Azure AD 中注册的个人 Windows 设备），最终用户必须手动执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="9700d-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="9700d-116">对于已加入 Azure AD 的设备，用户需要具有本地管理员帐户，才能注销并重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="9700d-117">Microsoft 将发布有关如何成功还原设备状态的说明。</span><span class="sxs-lookup"><span data-stu-id="9700d-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="9700d-118">**我如何知道我的所有设备都已在公共云中注册？**</span><span class="sxs-lookup"><span data-stu-id="9700d-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="9700d-119">若要检查你的设备在公共云中是否已注册，应将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="9700d-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="9700d-120">然后，在 [独立于 Microsoft 云德国](ms-cloud-germany-transition.md#how-is-the-migration-organized)迁移阶段之后，使用 _registeredTime_ 列) 对注册 (的设备进行筛选。</span><span class="sxs-lookup"><span data-stu-id="9700d-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="9700d-121">在迁移租户后，设备注册将停用，并且不能启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="9700d-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="9700d-122">如果未使用 Intune，请登录订阅并运行以下命令以重新激活该选项：</span><span class="sxs-lookup"><span data-stu-id="9700d-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="9700d-123">Windows 混合 Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="9700d-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="9700d-124">Windows 低级别</span><span class="sxs-lookup"><span data-stu-id="9700d-124">Windows down-level</span></span>

<span data-ttu-id="9700d-125">_Windows 下层设备_ 是当前运行 windows 的早期版本的 windows 设备 (如 windows 8.1 或 windows 7) ，或者运行低于2019和2016的 windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="9700d-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="9700d-126">如果在之前注册了此类设备，则需要注销并重新注册这些设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="9700d-127">若要确定 Windows 下层设备以前是否已加入到 Azure AD，请在设备上使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="9700d-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="9700d-128">如果设备以前已加入 Azure AD，并且该设备具有与全局 Azure AD 终结点的网络连接，则会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="9700d-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="9700d-129">受影响的设备将具有值为 "Unknown" 的 "设备状态"。</span><span class="sxs-lookup"><span data-stu-id="9700d-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="9700d-130">如果输出为 "设备未联接" 或 "设备状态" 值为 "正常"，请忽略以下指南。</span><span class="sxs-lookup"><span data-stu-id="9700d-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="9700d-131">仅对于显示该设备通过 deviceId、指纹等) 进行联接 (的设备，并且其 "设备状态" 值为 "Unknown" 时，管理员应在此类下层设备上的域用户登录上下文中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9700d-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="9700d-132">上述命令只需要在每个域用户在 Windows 下层设备上登录时运行一次。</span><span class="sxs-lookup"><span data-stu-id="9700d-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="9700d-133">应在域用户登录的上下文中运行此命令。</span><span class="sxs-lookup"><span data-stu-id="9700d-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="9700d-134">若要在用户随后登录时不运行此命令，则必须执行足够的小心。</span><span class="sxs-lookup"><span data-stu-id="9700d-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="9700d-135">运行上述命令时，它将清除登录的用户的本地混合 Azure AD –加入的计算机的加入状态。</span><span class="sxs-lookup"><span data-stu-id="9700d-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="9700d-136">此外，如果计算机仍配置为在租户中加入混合 Azure AD，它将在用户再次登录时尝试加入。</span><span class="sxs-lookup"><span data-stu-id="9700d-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="9700d-137">Windows 当前</span><span class="sxs-lookup"><span data-stu-id="9700d-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="9700d-138">脱离</span><span class="sxs-lookup"><span data-stu-id="9700d-138">Unjoin</span></span>

<span data-ttu-id="9700d-139">若要确定 Windows 10 设备之前是否已加入 Azure AD，请在设备上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9700d-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="9700d-140">如果设备是混合 Azure AD –已加入，则管理员将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="9700d-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="9700d-141">如果输出是 "AzureAdJoined： No"，请忽略以下指南。</span><span class="sxs-lookup"><span data-stu-id="9700d-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="9700d-142">仅对于显示设备已加入 Azure AD 的设备，以管理员身份运行以下命令以删除设备的加入状态。</span><span class="sxs-lookup"><span data-stu-id="9700d-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="9700d-143">上面的命令只需在 Windows 设备的管理上下文中运行一次。</span><span class="sxs-lookup"><span data-stu-id="9700d-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="9700d-144">混合 AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="9700d-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="9700d-145">只要设备具有到全局 Azure AD 终结点的网络连接，该设备就会自动加入 Azure AD，而无需用户或管理员干预。</span><span class="sxs-lookup"><span data-stu-id="9700d-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="9700d-146">Windows Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="9700d-146">Windows Azure AD Join</span></span>

### <a name="unjoin"></a><span data-ttu-id="9700d-147">脱离</span><span class="sxs-lookup"><span data-stu-id="9700d-147">Unjoin</span></span>

<span data-ttu-id="9700d-148">若要确定 Windows 10 设备之前是否已加入 Azure AD，用户或管理员可以在设备上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9700d-148">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="9700d-149">如果设备已加入 Azure AD，则用户或管理员将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="9700d-149">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="9700d-150">如果输出是 "AzureAdJoined： NO"，请忽略以下指南。</span><span class="sxs-lookup"><span data-stu-id="9700d-150">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="9700d-151">用户：如果设备已加入 Azure AD，则用户可以从设置中脱离设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-151">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="9700d-152">在从 Azure AD unjoining 设备之前，请确认设备上是否有本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="9700d-152">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="9700d-153">登录回设备需要本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="9700d-153">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="9700d-154">管理员：如果组织的管理员想要脱离已加入 Azure AD 的用户设备，则可以通过使用组策略等机制在每个设备上运行以下命令来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9700d-154">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="9700d-155">管理员必须先验证设备上是否有本地管理员帐户，然后再 unjoining Azure AD 中的设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-155">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="9700d-156">登录回设备需要本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="9700d-156">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="9700d-157">上面的命令只需在 Windows 设备的管理上下文中运行一次。</span><span class="sxs-lookup"><span data-stu-id="9700d-157">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="9700d-158">Azure AD 加入/重新注册</span><span class="sxs-lookup"><span data-stu-id="9700d-158">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="9700d-159">用户可以从 Windows 设置中将设备加入 Azure AD： **settings > 帐户 > 访问工作或学校 > 连接**。</span><span class="sxs-lookup"><span data-stu-id="9700d-159">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="9700d-160">Windows Azure AD 注册 (公司拥有) </span><span class="sxs-lookup"><span data-stu-id="9700d-160">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="9700d-161">若要确定 Windows 10 设备是否已注册为 Azure AD，请在设备上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9700d-161">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="9700d-162">如果设备已注册 Azure AD，则会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="9700d-162">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="9700d-163">若要删除设备上现有的 Azure AD 注册帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9700d-163">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="9700d-164">若要删除设备上的 Azure AD 注册帐户，请使用 CleanupWPJ，可从此处下载的工具： [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。</span><span class="sxs-lookup"><span data-stu-id="9700d-164">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="9700d-165">解压缩 ZIP 文件并运行 **WPJCleanup**。</span><span class="sxs-lookup"><span data-stu-id="9700d-165">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="9700d-166">此工具将根据设备上的 Windows 版本启动正确的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="9700d-166">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="9700d-167">通过使用像组策略这样的机制，管理员可以在设备上的任何登录的用户上下文中运行此命令。</span><span class="sxs-lookup"><span data-stu-id="9700d-167">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="9700d-168">若要禁用 Web 帐户管理器提示以在 Azure AD 中注册设备，请添加以下注册表值：</span><span class="sxs-lookup"><span data-stu-id="9700d-168">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="9700d-169">位置： HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="9700d-169">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="9700d-170">类型： DWORD (32 位) </span><span class="sxs-lookup"><span data-stu-id="9700d-170">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="9700d-171">名称： BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="9700d-171">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="9700d-172">值数据：1</span><span class="sxs-lookup"><span data-stu-id="9700d-172">Value data: 1</span></span>

<span data-ttu-id="9700d-173">此注册表值的存在应阻止 workplace join，并防止用户看到加入设备的提示。</span><span class="sxs-lookup"><span data-stu-id="9700d-173">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="9700d-174">Android</span><span class="sxs-lookup"><span data-stu-id="9700d-174">Android</span></span>

<span data-ttu-id="9700d-175">对于 Android，用户将需要注销并重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-175">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="9700d-176">可以通过 Microsoft 验证器应用或公司门户应用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="9700d-176">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="9700d-177">在 Microsoft 身份验证器应用中，用户可以转到 " **设备注册" >** 的 "设置"。</span><span class="sxs-lookup"><span data-stu-id="9700d-177">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="9700d-178">用户可以从此处注销和重新注册其设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-178">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="9700d-179">在公司门户中，用户可以转到 " **设备** " 选项卡并删除该设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-179">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="9700d-180">然后，使用公司门户重新注册该设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-180">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="9700d-181">用户还可以通过从 "帐户设置" 页删除帐户，然后重新添加工作帐户来取消注册和重新注册。</span><span class="sxs-lookup"><span data-stu-id="9700d-181">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="9700d-182">若要使用 Microsoft 验证器应用在 Android 上注销并重新注册设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9700d-182">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="9700d-183">打开 Microsoft 身份验证器应用，然后转到 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="9700d-183">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="9700d-184">选择 " **设备注册**"。</span><span class="sxs-lookup"><span data-stu-id="9700d-184">Select **Device registration**.</span></span>
3.  <span data-ttu-id="9700d-185">通过选择 " **注销**" 注销设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-185">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="9700d-186">对于 **设备注册**，请通过键入电子邮件地址重新注册该设备，然后选择 " **注册**"。</span><span class="sxs-lookup"><span data-stu-id="9700d-186">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="9700d-187">若要使用 Android 设置页面注销和重新注册 Android 设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9700d-187">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="9700d-188">打开 " **设备设置** "，然后转到 " **帐户**"。</span><span class="sxs-lookup"><span data-stu-id="9700d-188">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="9700d-189">选择要重新注册的工作帐户，然后选择 " **删除帐户**"。</span><span class="sxs-lookup"><span data-stu-id="9700d-189">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="9700d-190">删除帐户后，从 " **帐户** " 页中，选择 " **添加帐户" > 工作帐户**。</span><span class="sxs-lookup"><span data-stu-id="9700d-190">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="9700d-191">对于 " **Workplace Join**"，键入您的电子邮件地址，然后选择 " **加入** " 以完成设备注册。</span><span class="sxs-lookup"><span data-stu-id="9700d-191">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="9700d-192">若要从公司门户注销并重新注册 Android 上的设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9700d-192">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="9700d-193">启动 "公司门户" 并转到 " **设备** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9700d-193">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="9700d-194">选择设备以查看设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="9700d-194">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="9700d-195">从省略号 (三个点) "菜单中，选择" **删除设备**"，然后通过在对话框中确认来完成删除操作。</span><span class="sxs-lookup"><span data-stu-id="9700d-195">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="9700d-196">现在应注销公司门户应用程序。</span><span class="sxs-lookup"><span data-stu-id="9700d-196">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="9700d-197">选择 **"登录"** 以重新注册设备。</span><span class="sxs-lookup"><span data-stu-id="9700d-197">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="9700d-198">有关在此工作负荷的迁移阶段中所需的任何操作或对管理或使用的影响的详细信息，请查看有关 [从 Microsoft 云德国迁移的其他一般信息](ms-cloud-germany-transition-add-general.md#azure-active-directory)中的 Azure Active Directory 的信息。</span><span class="sxs-lookup"><span data-stu-id="9700d-198">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="9700d-199">iOS</span><span class="sxs-lookup"><span data-stu-id="9700d-199">iOS</span></span>

<span data-ttu-id="9700d-200">在 iOS 设备上，用户需要手动从 Microsoft 身份验证器中删除任何缓存帐户，注销该设备，然后从设备上的任何本机应用注销。</span><span class="sxs-lookup"><span data-stu-id="9700d-200">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="9700d-201">步骤1：如果存在，请从 Microsoft 身份验证器应用中删除帐户</span><span class="sxs-lookup"><span data-stu-id="9700d-201">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="9700d-202">在 Microsoft 身份验证应用程序中点击该帐户。</span><span class="sxs-lookup"><span data-stu-id="9700d-202">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="9700d-203">在右上角点击 " **设置** " 图标。</span><span class="sxs-lookup"><span data-stu-id="9700d-203">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="9700d-204">如果看不到 " **设置** " 图标，则可能是因为没有使用 Microsoft 身份验证器的最新版本。</span><span class="sxs-lookup"><span data-stu-id="9700d-204">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="9700d-205">点击 " **删除帐户** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="9700d-205">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="9700d-206">点击 **此设备上的所有应用**。</span><span class="sxs-lookup"><span data-stu-id="9700d-206">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="9700d-207">步骤2：从 Microsoft 身份验证器应用注销设备</span><span class="sxs-lookup"><span data-stu-id="9700d-207">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="9700d-208">点击右上角的 "菜单" 图标。</span><span class="sxs-lookup"><span data-stu-id="9700d-208">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="9700d-209">点击 " **设置** "，然后单击 " **设备注册**"。</span><span class="sxs-lookup"><span data-stu-id="9700d-209">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="9700d-210">如果显示了你的帐户，请点击 " **取消注册设备** 并 **继续** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="9700d-210">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="9700d-211">之后，您将不会看到任何帐户。</span><span class="sxs-lookup"><span data-stu-id="9700d-211">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="9700d-212">步骤3：在必要时注销单个应用</span><span class="sxs-lookup"><span data-stu-id="9700d-212">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="9700d-213">用户可以转到 Outlook、团队和 OneDrive 等各个应用，并从这些应用中删除帐户。</span><span class="sxs-lookup"><span data-stu-id="9700d-213">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="9700d-214">详细信息</span><span class="sxs-lookup"><span data-stu-id="9700d-214">More information</span></span>

<span data-ttu-id="9700d-215">入门：</span><span class="sxs-lookup"><span data-stu-id="9700d-215">Getting started:</span></span>

- [<span data-ttu-id="9700d-216">从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="9700d-216">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="9700d-217">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="9700d-217">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="9700d-218">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="9700d-218">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="9700d-219">迁移过程中的客户体验</span><span class="sxs-lookup"><span data-stu-id="9700d-219">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="9700d-220">在转换中移动：</span><span class="sxs-lookup"><span data-stu-id="9700d-220">Moving through the transition:</span></span>

- [<span data-ttu-id="9700d-221">迁移阶段的操作和影响</span><span class="sxs-lookup"><span data-stu-id="9700d-221">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="9700d-222">其他预备工作</span><span class="sxs-lookup"><span data-stu-id="9700d-222">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="9700d-223">[服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9700d-223">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="9700d-224">云应用：</span><span class="sxs-lookup"><span data-stu-id="9700d-224">Cloud apps:</span></span>

- [<span data-ttu-id="9700d-225">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="9700d-225">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="9700d-226">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="9700d-226">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="9700d-227">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="9700d-227">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
