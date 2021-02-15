---
title: Microsoft OneDrive
description: Microsoft 托管桌面如何为已注册的设备设置 OneDrive
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， 应用， 业务线应用， LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233891"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft 托管桌面将 [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) 用作所有 Microsoft 托管桌面设备的云存储服务，以确保设备尽可能无状态。 无论用户登录哪个设备，用户都将能够找到其文件。 例如，如果将 Microsoft 托管桌面设备替换为新设备，则文件将自动同步到新设备。

默认情况下，我们在 Microsoft 托管设备上自动配置这些设置：

- OneDrive 以静默方式使用用户帐户进行配置，并自动登录 (无需用户交互) 登录到用于登录 Windows 的用户帐户。 有关详细信息，请参阅以 [静默方式配置用户帐户 - OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- 启用"按需文件"功能，以便用户可以从 OneDrive 中的云存储访问文件，而无需不必要地使用磁盘空间。 有关详细信息，请参阅 [使用适用于 Windows 10 的 OneDrive 文件按需保存磁盘空间](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)。

- "已知文件夹移动"功能以静默方式启用，以在云中备份用户数据，从而使用户能够从任何设备访问其文件。 有关详细信息，请参阅使用 OneDrive 备份文档、 [图片和桌面文件夹](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)。

- 用户无法禁用"已知文件夹移动"功能或更改已知文件夹的位置，以确保跨 Microsoft 托管桌面设备的一致体验。

## <a name="user-experience"></a>用户体验

当 Microsoft 托管桌面用户收到新设备时，他们通过设置设备时输入 Azure 凭据来体验首次运行体验。 完成此过程后，他们可以访问其桌面并拥有 OneDrive 体验。

1. 系统会告知用户 OneDrive 已配置，并且已自动登录到 OneDrive。

:::image type="content" source="media/onedrive-sync.png" alt-text="通知阅读你正在同步 OneDrive，你可以编辑 OneDrive 中的文件。单击此处查看文件":::

2. 系统告知用户已针对他们配置了 OneDrive 已知文件夹移动。

:::image type="content" source="media/onedrive-folders.png" alt-text="读取你的 IT 部门的通知会备份重要文件夹。现在文件夹已备份到 OneDrive，并且可从其他设备使用":::

3. 若要在重置或重新映像设备时防止桌面上出现重复图标，系统会自动从 OneDrive 同步中删除 Microsoft Edge 和 Microsoft Teams 图标，如文件资源管理器中的此视图所示。

:::image type="content" source="media/onedrive-teams.png" alt-text="显示已清除复选框的 Teams 和 Edge 列表的文件资源管理器，并悬停文本（从同步中排除）。":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 同步限制

如果你需要限制 OneDrive 同步，我们建议你使用 Azure Active Directory 条件访问策略控制访问。 有关详细信息，请参阅在 [OneDrive 同步应用中启用条件访问支持](https://docs.microsoft.com/onedrive/enable-conditional-access)。

如果你无法在你的组织中使用 Azure AD 条件访问策略，你的 IT 管理员应遵循以下步骤：

1. 如果还不知道，请查找租户 ID，如"查找 [Microsoft 365 租户 ID"中所述](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)。
2. 登录到 OneDrive 管理中心，然后在左 **窗格中** 选择"同步"。 选中 **"仅允许在** 加入特定域的 PC 上同步"复选框，然后将租户 ID 添加到域列表中。 有关详细信息，请参阅"[仅允许在加入特定域的计算机上同步"。](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> 本指南仅适用于 Microsoft 托管桌面中的租户。 本文中未讨论其他使用的设置。
