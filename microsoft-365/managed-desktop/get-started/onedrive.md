---
title: Microsoft OneDrive
description: 如何Microsoft 托管桌面注册OneDrive的设备设置设备配置
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用、业务线应用、LOB 应用
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
---

# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft 托管桌面将 [OneDrive for Business](/onedrive/plan-onedrive-enterprise) 用作所有云设备的云Microsoft 托管桌面服务。 它确保设备尽可能无状态。 无论用户登录哪个设备，用户都将能够找到其文件。 例如，如果你将 Microsoft 托管桌面设备替换为新设备，文件将自动同步到新设备。

默认情况下，我们在 Microsoft 托管设备上自动配置这些设置：

| 功能 | 说明 |
| ------ | ------ |
| 无提示配置 | OneDrive以静默方式使用用户帐户进行配置。 它无需用户交互即可自动登录到用于登录 Windows。 有关详细信息，请参阅以无[提示方式配置用户帐户 - OneDrive](/onedrive/use-silent-account-configuration) |
| 按需文件 | 利用按需文件功能，用户可以从云存储中访问OneDrive而无需不必要地使用磁盘空间。 有关详细信息，请参阅使用文件[按需OneDrive节省磁盘空间Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)。 |
| 已知文件夹移动 | "已知文件夹移动"功能以静默方式启用，以在云中备份用户数据，从而使用户能够从任何设备访问其文件。 有关详细信息，请参阅使用文件夹[备份文档](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)、图片和OneDrive。 <p> 用户无法禁用"已知文件夹移动"功能或更改已知文件夹的位置，以确保跨设备实现Microsoft 托管桌面体验。</p>|

## <a name="user-experience"></a>用户体验

当用户Microsoft 托管桌面设备时，他们通过输入 Azure 凭据在设置设备时经历首次运行体验。 此过程完成后，他们可以访问其桌面并拥有OneDrive体验。

1. 系统告知用户OneDrive已配置用户，并且已自动登录到OneDrive。

:::image type="content" source="media/onedrive-sync.png" alt-text="通知阅读您现在正在同步OneDrive您可以在 OneDrive 中编辑文件。单击此处查看文件。":::

2. 系统告知用户OneDrive已配置已知文件夹移动。

:::image type="content" source="media/onedrive-folders.png" alt-text="阅读你的 IT 部门备份重要文件夹的通知。现在，这些文件夹已备份OneDrive设备提供。":::

3. 为了防止在重置或重新映像设备时在桌面上复制图标，系统会自动从Microsoft Edge中删除Microsoft Teams图标OneDrive 同步。此信息显示在文件资源管理器中。

:::image type="content" source="media/onedrive-teams.png" alt-text="文件资源管理器显示Teams复选框和鼠标悬停文本从同步中排除的边缘列表和边缘列表。":::

## <a name="onedrive-sync-restrictions"></a>OneDrive 同步限制

如果需要限制访问OneDrive 同步，建议您使用条件访问策略Azure Active Directory访问。 有关详细信息，请参阅在应用程序[应用中启用条件OneDrive 同步支持](/onedrive/enable-conditional-access)。

如果在你的组织中不能Azure AD条件访问策略，则 IT 管理员应执行以下步骤：

1. 如果还不了解，请查找租户 ID，如查找租户Microsoft 365 [ID 中所述](/onedrive/find-your-office-365-tenant-id)。
1. 登录到管理OneDrive中心。
1. 在左窗格中，选择"同步 **"**。
1. 选中" **仅在加入到特定域的 PC** 上允许同步"复选框，然后将租户 ID 添加到域列表中。 有关详细信息，请参阅 [只允许在加入特定域的计算机上同步](/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> 本指南仅适用于 Microsoft 托管桌面。 本文中未讨论其他使用的设置。
