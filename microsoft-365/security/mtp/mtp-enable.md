---
title: 在 Microsoft 365 安全中心中打开 Microsoft 威胁防护
description: 了解如何启用 Microsoft 威胁防护并开始集成安全事件和响应。
keywords: 入门、启用 MTP、Microsoft 威胁防护、M365、security、data location、必需权限、许可证资格、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209243"
---
# <a name="turn-on-microsoft-threat-protection"></a>打开 Microsoft 威胁防护

**适用于：**
- Microsoft 威胁防护

Microsoft 威胁防护通过集成 Microsoft Defender 高级威胁防护 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的关键功能来统一事件响应流程。 这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。

若要获得最佳保护并优化 Microsoft 威胁防护，建议在网络上部署所有适用的受支持的服务。 有关详细信息，请[参阅部署支持的服务](deploy-supported-services.md)。

## <a name="check-license-eligibility-and-required-permissions"></a>检查许可证资格和必需权限
Microsoft 365 E5、E5 Security、A5 或 A5 安全许可证或有效的许可证组合提供了对受支持服务的访问权限，并允许您使用 microsoft 365 安全中心中的 Microsoft 威胁防护，而无需额外的许可费用。

有关许可的详细信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>检查你的角色
您必须是**全局管理员**或 Azure Active Directory 中的**安全管理员**才能打开 Microsoft 威胁防护。 [在 Azure AD 中查看你的角色](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>开始使用服务

>[!IMPORTANT]
>从2020年5月12日开始，Microsoft 将逐步推出有关[许可要求](prerequisites.md#licensing-requirements)的新的优化体验，并启用 Microsoft 威胁防护。 在此期间的几周内，一些客户将开始查看对其门户体验所做的更改。 有关新体验的信息已在本文中标记为 "**新体验**"。

Microsoft 威胁防护从各种集成服务中聚合数据。 它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。 这样做不会影响与集成服务关联的现有部署、设置或数据。

在你打开服务之前，Microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）会在你选择 "**事件**"、"**操作中心**" 或 "导航窗格" 中的 "**搜寻**" 时显示 microsoft 威胁防护欢迎页面。 如果你不符合使用 Microsoft 威胁防护的条件，则不会显示这些导航选项。

![Microsoft ](../../media/mtp-welcome.png)
 *365 安全中心中*未打开 microsoft 威胁防护欢迎页面时显示的 microsoft 威胁防护欢迎页面的图像

若要打开 Microsoft 威胁防护，只需从欢迎页面完成此过程即可。 您还可以通过在导航窗格中访问**设置**（[security.microsoft.com/settings](https://security.microsoft.com/settings)）并选择 " **microsoft 威胁防护**" 来打开 microsoft 威胁防护。

>[!NOTE]
>如果在导航窗格中看不到**设置**或无法访问页面，请检查您的权限和许可证。

### <a name="select-data-center-location"></a>选择数据中心位置
如果已为组织设置了 Microsoft Defender ATP，则数据将在为 [Microsoft Defender ATP 数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)选择的同一数据中心位置进行存储和处理。 如果你没有 Microsoft Defender ATP，系统将要求你选择一个专门用于 Microsoft 威胁防护的新数据中心位置。 
 
您需要先提供许可，然后才能在服务和聚合之间共享数据。

**全新体验：** 从2020年5月12日开始，客户将逐渐收到此体验的更改。 对于具有全新体验的用户，服务将根据您现有的 Microsoft 365 安全服务自动为聚合数据选择最佳数据中心位置。 屏幕上显示了所选的数据中心位置。

### <a name="confirm-that-the-service-is-on"></a>确认服务已开启
设置服务后，它将添加：

- [事件管理](incidents-overview.md)
- 用于管理[自动调查和响应](mtp-autoir.md)的操作中心
- [高级搜寻](advanced-hunting-overview.md)功能

![Microsoft 365 security center 导航窗格的图像与 Microsoft 威胁防护功能 ](../../media/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 威胁防护功能*

### <a name="getting-azure-atp-data"></a>获取 Azure ATP 数据
要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。 [了解有关此集成的更多信息](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>关闭 Microsoft 威胁防护
要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。 取消选择**打开 Microsoft 威胁防护**并保存更改。

将从 Microsoft 365 安全中心删除相应的功能。

## <a name="get-assistance"></a>获取帮助

Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。 若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。 联系支持时，请提及 Microsoft 威胁防护。

## <a name="related-topics"></a>相关主题

- [Microsoft 威胁防护概述](microsoft-threat-protection.md)
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [Microsoft Defender ATP 概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概述](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概述](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概述](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 数据存储](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)