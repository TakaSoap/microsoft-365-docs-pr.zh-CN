---
title: Microsoft OneDrive
description: Microsoft 托管桌面如何为注册的设备设置 OneDrive
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， 应用， 业务线应用， LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904836"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="55827-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="55827-104">Microsoft OneDrive</span></span>

<span data-ttu-id="55827-105">Microsoft 托管桌面使用 [OneDrive for Business](/onedrive/plan-onedrive-enterprise) 作为所有 Microsoft 托管桌面设备的云存储服务，以确保设备尽可能无状态。</span><span class="sxs-lookup"><span data-stu-id="55827-105">Microsoft Managed Desktop uses [OneDrive for Business](/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="55827-106">无论用户登录哪个设备，用户都将能够找到其文件。</span><span class="sxs-lookup"><span data-stu-id="55827-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="55827-107">例如，如果将 Microsoft 托管桌面设备替换为新设备，文件将自动同步到新设备。</span><span class="sxs-lookup"><span data-stu-id="55827-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="55827-108">默认情况下，我们在 Microsoft 托管设备上自动配置这些设置：</span><span class="sxs-lookup"><span data-stu-id="55827-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="55827-109">OneDrive 使用用户帐户进行无提示配置，并自动登录 (而无需) 登录 Windows 的用户帐户进行用户交互。</span><span class="sxs-lookup"><span data-stu-id="55827-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="55827-110">有关详细信息，请参阅以 [无提示方式配置用户帐户 - OneDrive](/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="55827-110">For more information, see [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="55827-111">启用了按需文件功能，以便用户可以从 OneDrive 中的云存储访问文件，而无需不必要地使用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="55827-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="55827-112">有关详细信息，请参阅使用 [适用于 Windows 10 的 OneDrive 文件随](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)需保存磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="55827-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="55827-113">"已知文件夹移动"功能以静默方式启用，以在云中备份用户数据，从而使用户能够从任何设备访问其文件。</span><span class="sxs-lookup"><span data-stu-id="55827-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="55827-114">有关详细信息，请参阅使用 OneDrive 备份文档、 [图片和桌面文件夹](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)。</span><span class="sxs-lookup"><span data-stu-id="55827-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="55827-115">用户无法禁用已知文件夹移动功能或更改已知文件夹的位置以确保跨 Microsoft 托管桌面设备的一致体验。</span><span class="sxs-lookup"><span data-stu-id="55827-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="55827-116">用户体验</span><span class="sxs-lookup"><span data-stu-id="55827-116">User experience</span></span>

<span data-ttu-id="55827-117">当 Microsoft 托管桌面用户收到新设备时，他们通过设置设备时输入其 Azure 凭据来体验首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="55827-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="55827-118">此过程完成后，他们可以访问其桌面并拥有 OneDrive 体验。</span><span class="sxs-lookup"><span data-stu-id="55827-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="55827-119">系统告知用户 OneDrive 已配置，并且已自动登录到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="55827-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="通知你正在同步 OneDrive，可以在 OneDrive 中编辑文件。单击此处查看文件":::

2. <span data-ttu-id="55827-121">系统告知用户，已针对他们配置了 OneDrive 已知文件夹移动。</span><span class="sxs-lookup"><span data-stu-id="55827-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="阅读你的 IT 部门备份重要文件夹的通知。文件夹现已备份到 OneDrive，并且可从其他设备使用":::

3. <span data-ttu-id="55827-123">为了防止在重置或重新映像设备时在桌面上复制图标，系统会自动从 OneDrive 同步中删除 Microsoft Edge 和 Microsoft Teams 图标，如文件资源管理器中的此视图所示。</span><span class="sxs-lookup"><span data-stu-id="55827-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="文件资源管理器显示 Teams 和 Edge 列表（带清除复选框）和悬停文本（从同步中排除）。":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="55827-125">OneDrive 同步限制</span><span class="sxs-lookup"><span data-stu-id="55827-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="55827-126">如果你需要限制 OneDrive 同步，我们建议你使用 Azure Active Directory 条件访问策略控制访问。</span><span class="sxs-lookup"><span data-stu-id="55827-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="55827-127">有关详细信息，请参阅在 [OneDrive 同步应用中启用条件访问支持](/onedrive/enable-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="55827-127">For more information, see [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="55827-128">如果在你的组织中无法使用 Azure AD 条件访问策略，则 IT 管理员应执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="55827-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="55827-129">如果还不了解，请查找租户 ID，如查找 [Microsoft 365](/onedrive/find-your-office-365-tenant-id)租户 ID 中所述。</span><span class="sxs-lookup"><span data-stu-id="55827-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="55827-130">登录到 OneDrive 管理中心， **然后选择左侧窗格中** 的"同步"。</span><span class="sxs-lookup"><span data-stu-id="55827-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="55827-131">选中 **"仅允许在加入特定** 域的 PC 上同步"复选框，然后将租户 ID 添加到域列表中。</span><span class="sxs-lookup"><span data-stu-id="55827-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="55827-132">有关详细信息，请参阅 Allow [syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains)。</span><span class="sxs-lookup"><span data-stu-id="55827-132">For more information, see [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="55827-133">本指南仅适用于 Microsoft 托管桌面中的租户。</span><span class="sxs-lookup"><span data-stu-id="55827-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="55827-134">本文中未讨论其他使用的设置。</span><span class="sxs-lookup"><span data-stu-id="55827-134">There are other settings in use that aren't discussed in this article.</span></span>