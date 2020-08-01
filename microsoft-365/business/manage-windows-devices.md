---
title: 启用要由 Microsoft 365 for business 管理的加入域的 Windows 10 设备
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
description: 了解如何启用 Microsoft 365 以仅在几个步骤中保护本地的 Active Directory 加入 Windows 10 设备。
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533777"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="61a7b-103">启用要由 Microsoft 365 商业高级版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="61a7b-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="61a7b-104">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业高级版设置为保护您的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="61a7b-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="61a7b-105">若要设置此保护，可以实现**混合 AZURE AD 加入的设备**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="61a7b-106">这些设备将加入本地 Active Directory 和 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="61a7b-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="61a7b-107">本视频介绍了有关如何针对最常见方案对此进行设置的步骤，在下面的步骤中也将对此进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="61a7b-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="61a7b-108">在开始之前，请确保完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="61a7b-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="61a7b-109">使用 Azure AD Connect 将用户同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="61a7b-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="61a7b-110">完成 Azure AD Connect 组织单位（OU）同步。</span><span class="sxs-lookup"><span data-stu-id="61a7b-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="61a7b-111">确保您要同步的所有域用户都具有到 Microsoft 365 商业高级版的许可证。</span><span class="sxs-lookup"><span data-stu-id="61a7b-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="61a7b-112">有关步骤，请参阅[将域用户同步到 Microsoft](manage-domain-users.md) 。</span><span class="sxs-lookup"><span data-stu-id="61a7b-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="61a7b-113">1. 在 Intune 中验证 MDM 证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="61a7b-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="61a7b-114">转到 portal.azure.com，并在 Intune 页面的顶部搜索。</span><span class="sxs-lookup"><span data-stu-id="61a7b-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="61a7b-115">在 "Microsoft Intune" 页面上，选择 "**设备注册**"，并在 "**概述**" 页上确保**MDM 颁发机构**是**Intune**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="61a7b-116">如果**mdm 机构**为 "**无**"，请单击**mdm 机构**将其设置为**Intune**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="61a7b-117">如果**mdm 颁发机构**是**Microsoft office 365**，请转到 "**设备**  >  **注册设备**"，并使用右侧的 "**添加 mdm 颁发机构**" 对话框添加**Intune MDM**颁发机构（仅当**MDM 机构**设置为 Microsoft Office 365 时，"**添加 MDM 颁发机构**" 对话框才可用）。</span><span class="sxs-lookup"><span data-stu-id="61a7b-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="61a7b-118">2. 验证 Azure AD 是否已启用加入计算机</span><span class="sxs-lookup"><span data-stu-id="61a7b-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="61a7b-119">转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，在**管理中心**列表中，选择 "azure active Directory （如果 Azure active directory 不可见）" 列表中的 " **azure active directory** "。</span><span class="sxs-lookup"><span data-stu-id="61a7b-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="61a7b-120">在**Azure Active directory 管理中心**中，转到 " **azure active directory** "，选择 "**设备**"，然后选择 "**设备设置**"。</span><span class="sxs-lookup"><span data-stu-id="61a7b-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="61a7b-121">验证**用户是否可以将设备加入 AZURE AD**已启用</span><span class="sxs-lookup"><span data-stu-id="61a7b-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="61a7b-122">若要启用所有用户，请设置为**all**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="61a7b-123">若要启用特定用户，请将设置为 "已**选择**" 以启用特定用户组。</span><span class="sxs-lookup"><span data-stu-id="61a7b-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="61a7b-124">将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="61a7b-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="61a7b-125">选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。</span><span class="sxs-lookup"><span data-stu-id="61a7b-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="61a7b-126">3. 验证 Azure AD 是否已启用 MDM</span><span class="sxs-lookup"><span data-stu-id="61a7b-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="61a7b-127">转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然后选择 "选择**终结点 Managemen**t" （如果**终结点管理器**不可见，请选择 "**全部显示**"）</span><span class="sxs-lookup"><span data-stu-id="61a7b-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="61a7b-128">在**Microsoft 终结点管理器管理中心**，转到 "**设备**  >  **windows**  >  **windows 注册**  >  **自动注册**"。</span><span class="sxs-lookup"><span data-stu-id="61a7b-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="61a7b-129">验证 MDM 用户作用域是否已启用。</span><span class="sxs-lookup"><span data-stu-id="61a7b-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="61a7b-130">若要注册所有计算机，设置为**all** ，以便在用户向 Windows 添加工作帐户时自动注册加入 Azure AD 和新计算机的所有用户计算机。</span><span class="sxs-lookup"><span data-stu-id="61a7b-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="61a7b-131">设置为**Some**以注册特定用户组的计算机。</span><span class="sxs-lookup"><span data-stu-id="61a7b-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="61a7b-132">将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="61a7b-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="61a7b-133">选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。</span><span class="sxs-lookup"><span data-stu-id="61a7b-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="61a7b-134">4. 创建所需的资源</span><span class="sxs-lookup"><span data-stu-id="61a7b-134">4. Create the required resources</span></span> 

<span data-ttu-id="61a7b-135">通过使用在[SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell 模块中找到的[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet，执行[配置混合 Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)所需的任务已得到简化。</span><span class="sxs-lookup"><span data-stu-id="61a7b-135">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="61a7b-136">调用此 cmdlet 时，它将创建并配置所需的服务连接点和组策略。</span><span class="sxs-lookup"><span data-stu-id="61a7b-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="61a7b-137">您可以通过从 PowerShell 实例中调用以下命令来安装此模块：</span><span class="sxs-lookup"><span data-stu-id="61a7b-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="61a7b-138">建议在运行 Azure AD Connect 的 Windows 服务器上安装此模块。</span><span class="sxs-lookup"><span data-stu-id="61a7b-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="61a7b-139">若要创建所需的服务连接点和组策略，您将调用[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61a7b-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="61a7b-140">执行此任务时，将需要 Microsoft 365 商业高级全局管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="61a7b-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="61a7b-141">准备好创建资源时，请调用以下命令：</span><span class="sxs-lookup"><span data-stu-id="61a7b-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="61a7b-142">第一个命令将与 Microsoft 云建立连接，当系统提示时，请指定 Microsoft 365 Business Premium 全局管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="61a7b-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="61a7b-143">5. 链接组策略</span><span class="sxs-lookup"><span data-stu-id="61a7b-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="61a7b-144">在组策略管理控制台（GPMC）中，右键单击要将策略链接到的位置，然后从上下文菜单中选择 "*链接现有 GPO ...* "。</span><span class="sxs-lookup"><span data-stu-id="61a7b-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="61a7b-145">选择在上述步骤中创建的策略，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="61a7b-146">获取最新的管理模板</span><span class="sxs-lookup"><span data-stu-id="61a7b-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="61a7b-147">如果您没有看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**，可能是因为您没有为 Windows 10 版本1803、版本1809或版本1903安装 ADMX。</span><span class="sxs-lookup"><span data-stu-id="61a7b-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="61a7b-148">若要解决此问题，请执行以下步骤（注意：最新的 MDM 将向后兼容）：</span><span class="sxs-lookup"><span data-stu-id="61a7b-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="61a7b-149">下载：[适用于 Windows 10 的管理模板（admx）可能为2019更新（1903）](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。</span><span class="sxs-lookup"><span data-stu-id="61a7b-149">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="61a7b-150">在主域控制器（PDC）上安装程序包。</span><span class="sxs-lookup"><span data-stu-id="61a7b-150">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="61a7b-151">导航，具体取决于文件夹的版本： **C:\Program Files （x86） \Microsoft Group Policy\Windows 10 5 月 2019 Update （1903） v3**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-151">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="61a7b-152">将上述路径中的 "**策略定义**" 文件夹重命名为**PolicyDefinitions**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="61a7b-153">将**PolicyDefinitions**文件夹复制到**C:\Windows\SYSVOL\domain\Policies**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-153">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="61a7b-154">如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。</span><span class="sxs-lookup"><span data-stu-id="61a7b-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="61a7b-155">重新启动主域控制器，以使策略可用。</span><span class="sxs-lookup"><span data-stu-id="61a7b-155">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="61a7b-156">此过程也适用于将来的任何版本。</span><span class="sxs-lookup"><span data-stu-id="61a7b-156">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="61a7b-157">此时，您应该能够看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**。</span><span class="sxs-lookup"><span data-stu-id="61a7b-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
