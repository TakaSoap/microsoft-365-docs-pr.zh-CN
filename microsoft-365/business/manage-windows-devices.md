---
title: 允许 Microsoft 365 商业版管理加入域的 Windows 10 设备
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 了解如何通过几个步骤使 Microsoft 365 能够保护加入本地 Active-Directory 的 Windows 10 设备。
ms.openlocfilehash: 82d4ac3f1d6aba9489f9ea153de3a3d2083b47ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913186"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="2c6c9-103">允许 Microsoft 365 商业高级版管理加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="2c6c9-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="2c6c9-104">如果你的组织使用本地 Windows Server Active Directory，你可以设置 Microsoft 365 商业高级版来保护你的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="2c6c9-105">若要设置此保护，你可以实现加入 **混合 Azure AD 的设备**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="2c6c9-106">这些设备已加入本地 Active Directory 和 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="2c6c9-107">本视频介绍了如何针对最常见方案设置此方案的步骤，后续步骤中对此也进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="2c6c9-108">在开始使用之前，请确保完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2c6c9-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="2c6c9-109">使用 Azure AD Connect 将用户同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="2c6c9-110">完成 Azure AD Connect 组织单位 (OU) 同步。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="2c6c9-111">确保你同步的所有域用户都有 Microsoft 365 商业高级版许可证。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="2c6c9-112">有关 [步骤，请参阅将域用户](manage-domain-users.md) 同步到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="2c6c9-113">1. 在 Intune 中验证 MDM 颁发机构</span><span class="sxs-lookup"><span data-stu-id="2c6c9-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="2c6c9-114">转到 [终结点管理器](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)，在 Microsoft Intune 页面上，选择设备注册，然后在概述页面上，确保 **MDM 颁发机构** 是 **Intune**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="2c6c9-115">如果 **MDM 颁发机构** 为 **"无**"，请单击 **MDM 颁发机构** ，以将它设置为 **Intune**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="2c6c9-116">如果 **MDM 颁发** 机构为 Microsoft Office  **365，** 请转到设备注册设备并使用右侧添加 MDM 颁发机构对话框添加 Intune MDM 颁发机构 (只有 MDM 颁发机构设置为 Microsoft Office  >   365 ) 时，"添加 **MDM** 颁发机构"对话框才可用。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="2c6c9-117">2. 验证 Azure AD 是否已启用以加入计算机</span><span class="sxs-lookup"><span data-stu-id="2c6c9-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="2c6c9-118">转到 管理中心 ，然后选择 Azure Active Directory (如果 Azure Active Directory 在管理中心列表中不可见，) <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 全部显示"。 </span><span class="sxs-lookup"><span data-stu-id="2c6c9-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="2c6c9-119">在 **Azure Active Directory 管理中心** 中，转到 **"Azure Active Directory"，** 选择"**设备**"，然后选择"**设备设置"。**</span><span class="sxs-lookup"><span data-stu-id="2c6c9-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="2c6c9-120">验证 **用户是否将设备加入 Azure AD** 已启用</span><span class="sxs-lookup"><span data-stu-id="2c6c9-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="2c6c9-121">若要启用所有用户，请 **设置为全部**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="2c6c9-122">若要启用特定用户，请设置为 **"已选择** "以启用特定的一组用户。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="2c6c9-123">将 Azure AD 中同步的所需域用户添加到 [安全组](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="2c6c9-124">选择 **"选择组** "以启用该安全组的 MDM 用户作用域。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="2c6c9-125">3. 验证 Azure AD 是否已启用 MDM</span><span class="sxs-lookup"><span data-stu-id="2c6c9-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="2c6c9-126">转到管理中心，然后选择终结点管理 (如果终结点管理器在管理中心内不可见，请选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 全部)   </span><span class="sxs-lookup"><span data-stu-id="2c6c9-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="2c6c9-127">在 **Microsoft Endpoint Manager 管理中心中**，**转到设备**  >  **Windows**  >  **Windows 注册**  >  **自动注册**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="2c6c9-128">验证 MDM 用户作用域是否已启用。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="2c6c9-129">若要注册所有计算机，请设置为"全部"，以在用户将工作帐户添加到 Windows 时自动注册已加入 Azure AD 的所有用户计算机和新计算机。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="2c6c9-130">设置为 **"某些** "以注册特定组用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="2c6c9-131">将 Azure AD 中同步的所需域用户添加到 [安全组](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="2c6c9-132">选择 **"选择组** "以启用该安全组的 MDM 用户作用域。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="2c6c9-133">4. 创建所需的资源</span><span class="sxs-lookup"><span data-stu-id="2c6c9-133">4. Create the required resources</span></span> 

<span data-ttu-id="2c6c9-134">使用[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模块中的[Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet 简化了配置混合[Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)加入所需的任务。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="2c6c9-135">调用此 cmdlet 时，它将创建和配置所需的服务连接点和组策略。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="2c6c9-136">可以通过从 PowerShell 实例调用以下内容来安装此模块：</span><span class="sxs-lookup"><span data-stu-id="2c6c9-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="2c6c9-137">建议在运行 Azure AD Connect 的 Windows Server 上安装此模块。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="2c6c9-138">若要创建所需的服务连接点和组策略，将调用  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="2c6c9-139">执行此任务时，你将需要 Microsoft 365 商业高级版全局管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="2c6c9-140">准备好创建资源时，请调用以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c6c9-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="2c6c9-141">第一个命令将建立与 Microsoft 云的连接，当系统提示时，指定 Microsoft 365 商业高级版全局管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="2c6c9-142">5. 链接组策略</span><span class="sxs-lookup"><span data-stu-id="2c6c9-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="2c6c9-143">在组策略管理控制台 (GPMC) 中，右键单击要链接策略的位置，然后从上下文菜单中选择"链接现有 *GPO..."。*</span><span class="sxs-lookup"><span data-stu-id="2c6c9-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="2c6c9-144">选择在以上步骤中创建的策略，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="2c6c9-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="2c6c9-145">获取最新的管理模板</span><span class="sxs-lookup"><span data-stu-id="2c6c9-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="2c6c9-146">如果你看不到使用默认 Azure **AD** 凭据启用自动 MDM 注册的策略，这可能是因为你未为 Windows 10 版本 1803 或更高版本安装 ADMX。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="2c6c9-147">若要解决此问题，请按照以下步骤操作 (注意：最新的 MDM.admx 是向后兼容的) ：</span><span class="sxs-lookup"><span data-stu-id="2c6c9-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="2c6c9-148">下载[：2020 年 10 ( 20H2) Windows 10 管理模板 (.admx) 。 ](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="2c6c9-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="2c6c9-149">在域控制器上安装程序包。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="2c6c9-150">根据管理模板版本导航到文件夹 **：C：\Program Files (x86) \Microsoft Group Policy\Windows 10 2020 年 10 月更新 (20H2)**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="2c6c9-151">将上述 **路径中的"策略** 定义"文件夹重命名为 **PolicyDefinitions**。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="2c6c9-152">将 **PolicyDefinitions** 文件夹复制到 SYSVOL 共享，默认位于 **C：\Windows\SYSVOL\domain\Policies。**</span><span class="sxs-lookup"><span data-stu-id="2c6c9-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="2c6c9-153">如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="2c6c9-154">如果您具有多个域控制器，请等待 SYSVOL 复制，以便策略可用。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="2c6c9-155">此过程还适用于管理模板的任何未来版本。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="2c6c9-156">此时，你应该可以看到"使用默认 **Azure AD** 凭据启用自动 MDM 注册"策略可用。</span><span class="sxs-lookup"><span data-stu-id="2c6c9-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>