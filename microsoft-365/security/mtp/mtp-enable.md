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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844585"
---
# <a name="turn-on-microsoft-threat-protection"></a>打开 Microsoft 威胁防护

**适用于：**
- Microsoft 威胁防护

[Microsoft 威胁防护](microsoft-threat-protection.md)通过在 Microsoft Defender 高级威胁防护（ATP）、OFFICE 365 ATP、Microsoft 云应用安全性和 Azure atp 之间集成关键功能，统一了你的事件响应流程。 这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。

当具有所需权限的符合条件的客户访问 Microsoft 365 安全中心时，Microsoft 威胁防护将自动启用。 阅读本文以了解各种先决条件以及如何设置 Microsoft 威胁防护。

## <a name="check-license-eligibility-and-required-permissions"></a>检查许可证资格和必需权限
Microsoft 365 安全产品的许可证通常使您能够在 Microsoft 365 安全中心中使用 Microsoft 威胁防护，而无需额外的许可费用。 我们建议获取 Microsoft 365 E5、E5、E5 或 A5 安全许可证或有效的许可证组合，以提供对所有支持的服务的访问权限。

有关许可的详细信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>检查你的角色
您必须是**全局管理员**或 Azure Active Directory 中的**安全管理员**才能打开 Microsoft 威胁防护。 [在 Azure AD 中查看你的角色](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支持的服务
Microsoft 威胁防护可从已部署的各种受支持的服务中聚合数据。 它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。 这样做不会影响与集成服务关联的现有部署、设置或数据。

若要获得最佳保护并优化 Microsoft 威胁防护，建议在网络上部署所有适用的受支持的服务。 有关详细信息，请[参阅部署支持的服务](deploy-supported-services.md)。

## <a name="before-starting-the-service"></a>启动服务之前
在你打开服务之前，Microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）会在你选择 "**事件**"、"**操作中心**" 或 "导航窗格" 中的 "**搜寻**" 时显示 "microsoft 威胁防护设置" 页。 如果你不符合使用 Microsoft 威胁防护的条件，则不会显示这些导航项目。

![显示 microsoft 威胁防护设置页面的图像如果尚未在 microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 安全中心中*打开 microsoft 威胁防护设置的 microsoft 威胁防护

## <a name="starting-the-service"></a>启动服务
若要打开 Microsoft 威胁防护，只需选择 **"启用 Microsoft 威胁防护**" 并应用更改。 您还可以通过在导航窗格中选择 "**设置**" （[security.microsoft.com/settings](https://security.microsoft.com/settings)），然后选择 " **microsoft 威胁防护**" 来访问此选项。

>[!NOTE]
>如果在导航窗格中看不到**设置**或无法访问页面，请检查您的权限和许可证。

### <a name="data-center-location"></a>数据中心位置
Microsoft 威胁防护将在[Microsoft DEFENDER ATP 使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)存储和处理数据。 如果你没有 Microsoft Defender ATP，将根据活动的 Microsoft 365 安全服务的位置自动选择新的数据中心位置。 屏幕上显示了所选的数据中心位置。

>[!NOTE]
>在 Microsoft 365 安全中心中选择 **"需要帮助？** "，以与 microsoft 支持部门联系，了解如何在不同的数据中心位置设置 Microsoft 威胁保护。 

### <a name="confirm-that-the-service-is-on"></a>确认服务已开启
设置服务后，它将添加：

- [事件管理](incidents-overview.md)
- 用于管理[自动调查和响应](mtp-autoir.md)的操作中心
- [高级搜寻](advanced-hunting-overview.md)功能

![Microsoft 365 security center 导航窗格的图像与 Microsoft 威胁防护功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 威胁防护功能*

### <a name="getting-azure-atp-data"></a>获取 Azure ATP 数据
要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。 [了解有关此集成的更多信息](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>关闭 Microsoft 威胁防护
要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。 取消选择 **"打开 Microsoft 威胁防护**" 并应用更改。

将从 Microsoft 365 安全中心删除相应的功能。

## <a name="get-assistance"></a>获取帮助

若要获取有关启用 Microsoft 威胁防护的最常见问题的解答，请[阅读 FAQ](mtp-enable-faq.md)。

Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。 若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。 联系支持时，请提及 Microsoft 威胁防护。

## <a name="related-topics"></a>相关主题

- [常见问题](mtp-enable-faq.md)
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [Microsoft 威胁防护概述](microsoft-threat-protection.md)
- [Microsoft Defender ATP 概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概述](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概述](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概述](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 数据存储](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)