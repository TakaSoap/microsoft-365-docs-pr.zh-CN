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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564921"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="41dc5-103">启用要由 Microsoft 365 商业高级版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="41dc5-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="41dc5-104">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业高级版设置为保护您的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="41dc5-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="41dc5-105">若要设置此保护，可以实现**混合 AZURE AD 加入的设备**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="41dc5-106">这些设备将加入本地 Active Directory 和 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="41dc5-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="41dc5-107">本视频介绍了有关如何针对最常见方案对此进行设置的步骤，在下面的步骤中也将对此进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="41dc5-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="41dc5-108">在开始之前，请确保完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="41dc5-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="41dc5-109">使用 Azure AD Connect 将用户同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="41dc5-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="41dc5-110">完成 Azure AD Connect 组织单位（OU）同步。</span><span class="sxs-lookup"><span data-stu-id="41dc5-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="41dc5-111">确保您要同步的所有域用户都具有到 Microsoft 365 商业高级版的许可证。</span><span class="sxs-lookup"><span data-stu-id="41dc5-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="41dc5-112">有关步骤，请参阅[将域用户同步到 Microsoft](manage-domain-users.md) 。</span><span class="sxs-lookup"><span data-stu-id="41dc5-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="41dc5-113">1. 在 Intune 中验证 MDM 证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="41dc5-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="41dc5-114">转到 portal.azure.com，并在 Intune 页面的顶部搜索。</span><span class="sxs-lookup"><span data-stu-id="41dc5-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="41dc5-115">在 "Microsoft Intune" 页面上，选择 "**设备注册**"，并在 "**概述**" 页上确保**MDM 颁发机构**是**Intune**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="41dc5-116">如果**mdm 机构**为 "**无**"，请单击**mdm 机构**将其设置为**Intune**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="41dc5-117">如果**mdm 颁发机构**是**Microsoft office 365**，请转到 "**设备**  >  **注册设备**"，并使用右侧的 "**添加 mdm 颁发机构**" 对话框添加**Intune MDM**颁发机构（仅当**MDM 机构**设置为 Microsoft Office 365 时，"**添加 MDM 颁发机构**" 对话框才可用）。</span><span class="sxs-lookup"><span data-stu-id="41dc5-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="41dc5-118">2. 验证 Azure AD 是否已启用加入计算机</span><span class="sxs-lookup"><span data-stu-id="41dc5-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="41dc5-119">转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，在**管理中心**列表中，选择 "azure active Directory （如果 Azure active directory 不可见）" 列表中的 " **azure active directory** "。</span><span class="sxs-lookup"><span data-stu-id="41dc5-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="41dc5-120">在**Azure Active directory 管理中心**中，转到 " **azure active directory** "，选择 "**设备**"，然后选择 "**设备设置**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="41dc5-121">验证**用户是否可以将设备加入 AZURE AD**已启用</span><span class="sxs-lookup"><span data-stu-id="41dc5-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="41dc5-122">若要启用所有用户，请设置为**all**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="41dc5-123">若要启用特定用户，请将设置为 "已**选择**" 以启用特定用户组。</span><span class="sxs-lookup"><span data-stu-id="41dc5-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="41dc5-124">将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="41dc5-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="41dc5-125">选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。</span><span class="sxs-lookup"><span data-stu-id="41dc5-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="41dc5-126">3. 验证 Azure AD 是否已启用 MDM</span><span class="sxs-lookup"><span data-stu-id="41dc5-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="41dc5-127">转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，然后选择 "选择**终结点 Managemen**t" （如果**终结点管理器**不可见，请选择 "**全部显示**"）</span><span class="sxs-lookup"><span data-stu-id="41dc5-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="41dc5-128">在**Microsoft 终结点管理器管理中心**，转到 "**设备**  >  **windows**  >  **windows 注册**  >  **自动注册**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="41dc5-129">验证 MDM 用户作用域是否已启用。</span><span class="sxs-lookup"><span data-stu-id="41dc5-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="41dc5-130">若要注册所有计算机，设置为**all** ，以便在用户向 Windows 添加工作帐户时自动注册加入 Azure AD 和新计算机的所有用户计算机。</span><span class="sxs-lookup"><span data-stu-id="41dc5-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="41dc5-131">设置为**Some**以注册特定用户组的计算机。</span><span class="sxs-lookup"><span data-stu-id="41dc5-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="41dc5-132">将 Azure AD 中同步的所需域用户添加到[安全组](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="41dc5-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="41dc5-133">选择 "**选择组**" 以为该安全组启用 MDM 用户作用域。</span><span class="sxs-lookup"><span data-stu-id="41dc5-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="41dc5-134">4. 设置服务连接点（SCP）</span><span class="sxs-lookup"><span data-stu-id="41dc5-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="41dc5-135">可通过[配置混合 AZURE AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)简化这些步骤。</span><span class="sxs-lookup"><span data-stu-id="41dc5-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="41dc5-136">若要完成使用 Azure AD Connect 和 Microsoft 365 商业高级全局管理员和 Active Directory 管理员密码所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="41dc5-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="41dc5-137">启动 Azure AD Connect，然后选择 "**配置**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="41dc5-138">在 "**其他任务**" 页上，选择 "**配置设备选项**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="41dc5-139">在 "**概述**" 页上，选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="41dc5-140">在 "**连接到 AZURE AD** " 页上，输入 Microsoft 365 商业高级版全局管理员的凭据。</span><span class="sxs-lookup"><span data-stu-id="41dc5-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="41dc5-141">在 "**设备选项**" 页上，选择 "**配置混合 Azure AD 加入**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="41dc5-142">在 " **SCP** " 页面上，对于您希望 Azure AD CONNECT 配置 SCP 的每个林，请完成以下步骤，然后选择 "**下一步**"：</span><span class="sxs-lookup"><span data-stu-id="41dc5-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="41dc5-143">选中林名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="41dc5-143">Check the box beside the forest name.</span></span> <span data-ttu-id="41dc5-144">林应为你的 AD 域名称。</span><span class="sxs-lookup"><span data-stu-id="41dc5-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="41dc5-145">在 "**身份验证服务**" 列下，打开下拉列表并选择匹配的域名（只能有一个选项）。</span><span class="sxs-lookup"><span data-stu-id="41dc5-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="41dc5-146">选择 "**添加**" 以输入域管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="41dc5-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="41dc5-147">在 "**设备操作系统**" 页面上，选择 "Windows 10 或更高版本仅加入域" 设备。</span><span class="sxs-lookup"><span data-stu-id="41dc5-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="41dc5-148">在 "**准备配置**" 页上，选择 "**配置**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="41dc5-149">在 "**配置完成**" 页上，选择 "**退出**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="41dc5-150">5. 为 Intune 注册创建 GPO – ADMX 方法</span><span class="sxs-lookup"><span data-stu-id="41dc5-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="41dc5-151">改用.ADMX 模板文件。</span><span class="sxs-lookup"><span data-stu-id="41dc5-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="41dc5-152">登录到 AD server、搜索和打开**服务器管理器**  >  **工具**  >  **组策略管理**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="41dc5-153">选择 "**域**" 下的域名，然后右键单击 "**组策略对象**" 以选择 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="41dc5-154">为新 GPO 指定名称，例如 "*Cloud_Enrollment*"，然后选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="41dc5-155">右键单击 "**组策略对象**" 下的新 GPO，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="41dc5-156">在**组策略管理编辑器**中，转到 "**计算机配置**  >  **策略**"  >  **管理模板**  >  **Windows 组件**  >  **MDM**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="41dc5-157">右键单击 "**使用默认 Azure AD 凭据启用自动 MDM 注册**"，然后选择 "**启用**  >  **" "确定"**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="41dc5-158">关闭编辑器窗口。</span><span class="sxs-lookup"><span data-stu-id="41dc5-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41dc5-159">如果您没有看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**，请参阅[获取最新的管理模板](#get-the-latest-administrative-templates)。</span><span class="sxs-lookup"><span data-stu-id="41dc5-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="41dc5-160">6. 部署组策略</span><span class="sxs-lookup"><span data-stu-id="41dc5-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="41dc5-161">在服务器管理器的 "**域**> 组策略对象" 下，选择上面步骤3中的 GPO，例如 "Cloud_Enrollment"。</span><span class="sxs-lookup"><span data-stu-id="41dc5-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="41dc5-162">为 GPO 选择 "**作用域**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="41dc5-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="41dc5-163">在 GPO 的 "作用域" 选项卡中，右键单击 "**链接**" 下的域链接。</span><span class="sxs-lookup"><span data-stu-id="41dc5-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="41dc5-164">选择 "**强制**" 以部署 GPO，然后在确认屏幕中单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="41dc5-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="41dc5-165">获取最新的管理模板</span><span class="sxs-lookup"><span data-stu-id="41dc5-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="41dc5-166">如果您没有看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**，可能是因为您没有为 Windows 10 版本1803、版本1809或版本1903安装 ADMX。</span><span class="sxs-lookup"><span data-stu-id="41dc5-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="41dc5-167">若要解决此问题，请执行以下步骤（注意：最新的 MDM 将向后兼容）：</span><span class="sxs-lookup"><span data-stu-id="41dc5-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="41dc5-168">下载：[适用于 Windows 10 的管理模板（admx）可能为2019更新（1903）](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)。</span><span class="sxs-lookup"><span data-stu-id="41dc5-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="41dc5-169">在主域控制器（PDC）上安装程序包。</span><span class="sxs-lookup"><span data-stu-id="41dc5-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="41dc5-170">导航，具体取决于文件夹的版本： **C:\Program Files （x86） \Microsoft Group Policy\Windows 10 5 月 2019 Update （1903） v3**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="41dc5-171">将上述路径中的 "**策略定义**" 文件夹重命名为**PolicyDefinitions**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="41dc5-172">将**PolicyDefinitions**文件夹复制到**C:\Windows\SYSVOL\domain\Policies**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="41dc5-173">如果计划将中央策略存储用于整个域，请在那里添加 PolicyDefinitions 的内容。</span><span class="sxs-lookup"><span data-stu-id="41dc5-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="41dc5-174">重新启动主域控制器，以使策略可用。</span><span class="sxs-lookup"><span data-stu-id="41dc5-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="41dc5-175">此过程也适用于将来的任何版本。</span><span class="sxs-lookup"><span data-stu-id="41dc5-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="41dc5-176">此时，您应该能够看到策略**使用默认的 AZURE AD 凭据启用自动 MDM 注册**。</span><span class="sxs-lookup"><span data-stu-id="41dc5-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

