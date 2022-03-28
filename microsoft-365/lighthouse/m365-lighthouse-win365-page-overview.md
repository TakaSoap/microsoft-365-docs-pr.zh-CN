---
title: Microsoft 365 Lighthouse Windows 365 (云电脑) 概述
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 有关托管服务提供商 (使用) 的 MICROSOFT 365 LIGHTHOUSE，请了解 Windows 365 (云) 页面。
ms.openlocfilehash: fa910e3de992aa3f3f76090f76a473a96aebc8fb
ms.sourcegitcommit: 9d563faeaa50b59b0b468dbb373d886e5270f58e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "64387045"
---
# <a name="windows-365-cloud-pcs-page-overview"></a>Windows 365 (云电脑) 概述  
  
Windows 365 是一项基于云的服务，允许 Microsoft Endpoint Manager (MEM) 管理员为拥有 Windows 365 许可证的用户预配和管理云电脑。 Windows 365 与 MEM 完全集成，用于设备管理，Microsoft 365 Lighthouse跨所有客户租户管理云电脑。

有关 365 Windows，请参阅什么是 [Windows 365？](/windows-365/overview) 有关 365 Windows列表，请参阅 [Requirements for Windows 365](/windows-365/enterprise/requirements)。

> [!IMPORTANT]
> 必须先转到 [MEM](https://go.microsoft.com/fwlink/p/?linkid=2150463) 以预配每个客户租户的云电脑，然后才能在 Lighthouse 中管理它们。 你无法从 Lighthouse 中预配。

为客户租户预配云电脑后，Microsoft 365 主页上的 Windows 365 卡会提供有关需要采取措施的云电脑（如无法预配的云电脑数量和 Azure 网络连接故障）的简短警报。 若要获取详细状态，请选择 Windows 365 卡上的按钮 (或在左侧导航窗格) 中选择 **Windows 365** 以打开 Windows 365 页面。 在此页面中，你可以获取分配给客户租户的云电脑的状态概述，查看你管理的所有云电脑及其分配到的租户的列表，并查看客户租户和 Azure Active Directory (Azure AD) 之间的 Azure 网络连接及其状态。

## <a name="overview-tab"></a>"概述"选项卡

在"概述"选项卡上，彩色计数注释栏显示具有以下状态的所有客户租户中的云电脑或 Azure 网络连接总数：网络连接失败、未设置、预配失败和即将取消设置。

可以在批注栏下方的列表中查看每个客户租户的云电脑状态细目。 若要了解哪些租户具有具有特定状态的云电脑，请从计数注释栏中选择该状态以筛选列表。 若要查看一个或多个特定客户租户的云电脑状态，请使用"租户"下拉菜单筛选列表。

若要获取特定客户租户的详细状态信息，请选择该租户的任何状态列下的值。 根据值位于哪一列，**Azure 网络连接** 或"所有云电脑"选项卡将打开，并显示详细信息。

"概述"选项卡还包括以下选项：

- **刷新：** 选择以检索最新的云电脑数据。
- **导出：** 选择将云电脑数据导出到Excel逗号分隔值 (.csv) 文件。
- **搜索：** 输入关键字以在列表中快速找到特定的云电脑。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png" alt-text="&quot;Windows 365 概述&quot;选项卡的屏幕截图。" lightbox="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png":::

## <a name="all-cloud-pcs-tab"></a>"所有云电脑"选项卡

在"所有云电脑"选项卡上，彩色计数注释栏显示具有以下状态的所有客户租户中的云电脑总数：已设置、未设置、预配失败和即将取消预配。

可以在批注栏下方的列表中查看所有云电脑及其预配状态。 提供了以下信息：

- **云电脑名称：** 分配给云电脑的名称。
- **租户：** 预配云电脑的客户租户。
- **设备名称：** Intune 设备名称 - 云电脑的唯一标识符。
- **电脑类型：** 根据标准 SUS 的云电脑类型。
- **状态：** 云电脑的预配状态。
- **用户：** 已预配或尝试预配云电脑的用户。

若要了解哪些租户具有具有特定预配状态的云电脑，请从计数注释栏中选择该状态以筛选列表。 若要查看一个或多个特定客户租户的云电脑预配状态，请使用"租户"下拉菜单筛选列表。

选择列表中的任意云电脑以查看更多详细信息。 如果你需要在云电脑上采取措施，可以使用选项查看云中的租户预配策略和设备Microsoft Endpoint Manager。

"所有云电脑"选项卡还包括以下选项：

- **刷新：** 选择以检索最新的云电脑数据。
- **导出：** 选择将云电脑数据导出到Excel逗号分隔值 (.csv) 文件。
- **搜索：** 输入关键字以在列表中快速找到特定的云电脑。
- **重试预配：** 从列表中选择状态为预配失败的 1 到 20 台云电脑，然后选择此选项以重试这些云电脑的预配。

若要查看云电脑预配状态及其含义的完整列表，请参阅 Windows 365 文档库中[](/windows-365/enterprise/device-management-overview#column-details)的云电脑的设备管理概述。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png" alt-text="&quot;Windows 365 所有云电脑&quot;选项卡的屏幕截图。" lightbox="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png":::

## <a name="azure-network-connections-tab"></a>"Azure 网络连接"选项卡

在"Azure 网络连接"选项卡上，彩色计数注释栏显示具有以下状态的所有客户租户中的 Azure 网络连接总数："成功连接"和"连接失败"。

在计数注释栏下方的列表中，可以查看所有 Azure 网络连接及其连接状态。

To see connections with a specific provisioning status， select that status from the count-annotation bar to filter the list. 若要查看一个或多个特定客户租户的连接状态，请使用"租户"下拉菜单筛选列表。

如果需要对列表中的连接采取操作或排除故障，请选择"查看连接 **详细信息**"Microsoft Endpoint Manager。

"Azure 网络连接"选项卡还包括以下选项：

- **刷新：** 选择以检索最新的连接数据。
- **导出：** 选择以将连接数据导出到Excel逗号分隔值 (.csv) 文件中。
- **搜索：** 输入关键字以快速找到特定连接。

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png" alt-text="&quot;Azure 网络连接&quot;选项卡的屏幕截图。" lightbox="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png":::

## <a name="related-content"></a>相关内容

[什么是 Windows 365？](/windows-365/overview) （文章）\
Windows文章适用于云电脑的 ([365](/windows-365/enterprise/device-management-overview) 设备) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 