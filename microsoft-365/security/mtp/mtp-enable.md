---
title: 在 Microsoft 365 安全中心打开 Microsoft 365 Defender
description: 了解如何启用 Microsoft 365 Defender 并开始集成安全事件和响应。
keywords: 入门， 启用 MTP， Microsoft 威胁防护， M365， 安全性， 数据位置， 所需权限， 许可证资格， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930218"
---
# <a name="turn-on-microsoft-365-defender"></a>打开 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) 通过集成 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的关键功能来统一事件响应流程。 这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。

当具有所需权限的合格客户访问 Microsoft 365 安全中心时，Microsoft 365 Defender 将自动打开。 阅读本文以了解各种先决条件以及如何预配 Microsoft 365 Defender。

## <a name="check-license-eligibility-and-required-permissions"></a>检查许可证资格和所需权限

Microsoft 365 安全产品的许可证通常授权你在 Microsoft 365 安全中心使用 Microsoft 365 Defender，而无需额外的许可费用。 我们建议获取 Microsoft 365 E5、E5 安全、A5 或 A5 安全许可证或提供所有支持服务访问权限的有效许可证组合。

有关详细的许可信息， [请阅读许可要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>检查角色

你必须是 **Azure** Active Directory 中的全局管理员或安全管理员才能启用 Microsoft 365 Defender。  [在 Azure AD 中查看角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支持的服务

Microsoft 365 Defender 聚合已部署的各种受支持服务的数据。 它将集中处理和存储数据，以确定新的见解，并可能实现集中响应工作流。 这样做不会影响现有部署、设置或与集成服务关联的数据。

为了获得最佳保护并优化 Microsoft 365 Defender，我们建议在你的网络上部署所有适用的受支持服务。 有关详细信息，请阅读 [有关部署受支持的服务的信息](deploy-supported-services.md)。

## <a name="before-starting-the-service"></a>启动服务之前

在打开该服务之前，当你从导航窗格中选择事件、操作中心或搜寻时，Microsoft 365 安全中心 ([security.microsoft.com](https://security.microsoft.com)) 会显示 Microsoft 365 Defender 设置页。  如果你不符合使用 Microsoft 365 Defender 条件，将不会显示这些导航项。

![如果 Microsoft 365 Defender 尚未在 Microsoft 365 安全中心中打开 ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender 设置，则显示 Microsoft 365 Defender 设置页面的图像*

## <a name="starting-the-service"></a>启动服务

若要打开 Microsoft 365 Defender，只需选择" **打开 Microsoft 365 Defender"** 并应用更改。 您还可以通过在导航窗格中选择"设置 (security.microsoft.com/settings) ，然后选择 **Microsoft 365 Defender。**  [](https://security.microsoft.com/settings)

> [!NOTE]
> 如果在 **导航窗格中看不到** "设置"或无法访问页面，请检查您的权限和许可证。

### <a name="data-center-location"></a>数据中心位置

Microsoft 365 Defender 将在 Microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)使用的相同位置存储和处理数据。 如果你没有 Microsoft Defender for Endpoint，则根据活动的 Microsoft 365 安全服务的位置自动选择新的数据中心位置。 所选数据中心位置将显示在屏幕中。

选择 **"需要帮助"？** 在 Microsoft 365 安全中心中，联系 Microsoft 支持人员，以在不同数据中心位置预配 Microsoft 365 Defender。

> [!NOTE]
> Microsoft Defender for Endpoint 在通过 Azure Defender 打开 (欧盟) 中自动设置。 Microsoft 365 Defender 将自动在相同的欧盟数据中心中为已为此终结点预配 Defender 的客户进行预配。

### <a name="confirm-that-the-service-is-on"></a>确认服务已开启

设置服务后，它将添加：

- [事件管理](incidents-overview.md)
- 用于管理[自动调查和响应](mtp-autoir.md)的操作中心
- [高级搜寻](advanced-hunting-overview.md) 功能

![包含 Microsoft 365 Defender 的 Microsoft 365 安全中心导航窗格的图像，其中 Microsoft 365 安全中心具有事件管理和其他 ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender 功能*

### <a name="getting-microsoft-defender-for-identity-data"></a>获取 Microsoft Defender for Identity 数据

若要与 Microsoft 365 Defender 共享 Microsoft Defender 的标识数据，请确保 Microsoft Cloud App Security 和 Microsoft Defender for Identity 集成已打开。 [详细了解此集成](https://docs.microsoft.com/cloud-app-security/mdi-integration)。

## <a name="get-assistance"></a>获取帮助

若要获取有关打开 Microsoft 365 Defender 的最常见问题的答案，请阅读 [常见问题解答](mtp-enable-faq.md)。

Microsoft 支持人员可帮助预配或取消设置租户上的服务和相关资源。 有关帮助 **，请在** Microsoft 365 安全中心中选择"需要帮助？"。 联系支持人员时，请提及 Microsoft 365 Defender。

## <a name="related-topics"></a>相关主题

- [常见问题](mtp-enable-faq.md)
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [Microsoft 365 Defender 概述](microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint 概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Defender for Office 365 概述](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概述](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 概述](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [适用于终结点数据存储的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
