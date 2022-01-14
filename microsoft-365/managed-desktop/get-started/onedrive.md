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
ms.openlocfilehash: 8b5725de70446ee69452fabd02702e587ff13fa2
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035024"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft 托管桌面将[OneDrive for Business](/onedrive/plan-onedrive-enterprise)用作所有 Microsoft 托管桌面 设备的云存储服务，以确保设备尽可能无状态。 无论用户登录哪个设备，用户都将能够找到其文件。 例如，如果你将Microsoft 托管桌面设备替换为新设备，文件将自动同步到新设备。

默认情况下，我们在 Microsoft 托管设备上自动配置这些设置：

- OneDrive以静默方式使用用户帐户进行配置，并自动登录 (而无需用户) 登录到用于登录 Windows 的用户帐户。 有关详细信息，请参阅以无[提示方式配置用户帐户 - OneDrive](/onedrive/use-silent-account-configuration)

- 启用了"按需文件"功能，以便用户可以从云存储中访问OneDrive而无需不必要地使用磁盘空间。 有关详细信息，请参阅使用文件随OneDrive保存磁盘空间[，Windows 10。](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- "已知文件夹移动"功能以静默方式启用，以在云中备份用户数据，从而使用户能够从任何设备访问其文件。 有关详细信息，请参阅使用"文档、图片["和"](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)桌面"OneDrive。

- 用户无法禁用已知文件夹移动功能或更改已知文件夹的位置，以确保跨设备实现一Microsoft 托管桌面体验。

## <a name="user-experience"></a>用户体验

当用户Microsoft 托管桌面新设备时，他们可以通过在设置设备时输入其 Azure 凭据来体验首次运行体验。 此过程完成后，他们可以访问其桌面，并拥有OneDrive体验。

1. 系统告知用户OneDrive已配置，并且已自动登录到OneDrive。

:::image type="content" source="media/onedrive-sync.png" alt-text="通知阅读您现在正在同步OneDrive您可以在 OneDrive 中编辑文件。单击此处查看文件。":::

2. 系统告知用户OneDrive已配置已知文件夹移动。

:::image type="content" source="media/onedrive-folders.png" alt-text="阅读你的 IT 部门备份重要文件夹的通知。现在，这些文件夹已备份OneDrive，并且可从其他设备使用。":::

3. 为了防止在重置或重置设备时在桌面上复制图标，系统会自动从 OneDrive 同步 中删除 Microsoft Edge 和 Microsoft Teams 图标，如文件资源管理器中的此视图所示。

:::image type="content" source="media/onedrive-teams.png" alt-text="显示已清除Teams列表和 Edge 列表的文件资源管理器，并悬停文本阅读从同步中排除。":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 同步限制

如果需要限制访问OneDrive 同步，建议您使用条件访问策略Azure Active Directory访问。 有关详细信息，请参阅在应用[应用中启用条件OneDrive 同步支持](/onedrive/enable-conditional-access)。

如果在你的组织中无法Azure AD条件访问策略，则 IT 管理员应执行以下步骤：

1. 如果还不知道，请查找租户 ID，如查找租户Microsoft 365 [ID 中所述](/onedrive/find-your-office-365-tenant-id)。
2. 登录到管理OneDrive，**然后选择左侧窗格中** 的"同步"。 选中 **"仅允许在加入特定** 域的 PC 上同步"复选框，然后将租户 ID 添加到域列表中。 有关详细信息，请参阅 Allow [syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> 本指南仅适用于 Microsoft 托管桌面。 本文中未讨论其他使用的设置。