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
ms.openlocfilehash: 8f966060ebc9a30166647b397b93f2b45356df74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083715"
---
# <a name="turn-on-microsoft-threat-protection"></a>打开 Microsoft 威胁防护

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft 威胁防护通过集成 Microsoft Defender 高级威胁防护 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的关键功能来统一事件响应流程。 这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。

## <a name="check-license-eligibility-and-required-permissions"></a>检查许可证资格和必需权限
Microsoft 365 E5、Microsoft 365 E5 安全或等效的许可证组合的客户可以使用 Microsoft 威胁防护。 有关更多信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。

您必须是**全局管理员**或[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的**安全管理员**才能打开 Microsoft 威胁防护。

## <a name="start-using-the-service"></a>开始使用服务
Microsoft 威胁防护从各种集成服务中聚合数据。 它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。

在你打开服务之前，Microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）不会在导航窗格中显示**事件**和**操作中心**选项。

![未安装 microsoft 威胁防护功能](../../media/mtp-off.png)
的 microsoft 365 安全中心导航窗格的图像关闭 microsoft*365 安全中心，并关闭 microsoft 威胁防护*

若要打开 Microsoft 威胁防护，请在导航窗格中选择 "**设置**"。 在 "**[设置" 页](https://security.microsoft.com/settings)** 中，转到 " **Microsoft 威胁防护** > **" 自愿加入/自愿退出**。

>[!NOTE]
>如果在导航窗格中看不到**设置**或无法访问页面，请检查您的权限和许可证。

### <a name="select-data-center-location"></a>选择数据中心位置
如果已为组织设置了 Microsoft Defender ATP，则数据将在为 [Microsoft Defender ATP 数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)选择的同一数据中心位置进行存储和处理。 如果你没有 Microsoft Defender ATP，系统将要求你选择一个专门用于 Microsoft 威胁防护的新数据中心位置。 

您需要先提供许可，然后才能在服务和聚合之间共享数据。

### <a name="confirm-that-the-service-is-on"></a>确认服务已开启
设置服务后，它将添加：

- [事件管理](incidents-overview.md)
- 用于管理[自动调查和响应](mtp-autoir.md)的操作中心
- [高级搜寻](advanced-hunting-overview.md)功能（添加到现有**搜寻**页面）

![Microsoft 365 security center 导航窗格的图像与 microsoft 威胁防护功能](../../media/mtp-on.png)
*microsoft 365 security center with 事件管理和其他 Microsoft 威胁防护功能*

### <a name="getting-azure-atp-data"></a>获取 Azure ATP 数据
要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。 [了解有关此集成的更多信息](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>关闭 Microsoft 威胁防护
要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。 取消选择**打开 Microsoft 威胁防护**并保存更改。

将永久删除数据，并将从 Microsoft 365 安全中心删除相应的功能。

## <a name="get-assistance"></a>获取帮助

Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。 若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。 联系支持时，请提及 Microsoft 威胁防护。

## <a name="related-topics"></a>相关主题

- [Microsoft 威胁防护概述](microsoft-threat-protection.md)
- [许可要求和其他先决条件](prerequisites.md)
- [Microsoft Defender ATP 概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概述](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概述](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概述](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 数据存储](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
