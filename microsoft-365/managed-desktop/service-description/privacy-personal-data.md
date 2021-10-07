---
title: 隐私和个人数据
description: 详细介绍服务收集、存储和使用的数据
keywords: GDPR， 保留， 删除， 存储， 保留， 处理， 安全性， 审核
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: medium
ms.openlocfilehash: 23f74d8ddab72b08e2106c1b7d3de0a3264b4444
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194257"
---
# <a name="overview"></a>概述

Microsoft 托管桌面 IT 即服务 (ITaaS) 服务，旨在保留员工的 Windows 设备部署和更新。 它还提供 IT 服务管理和操作、监视安全和事件响应以及提供用户支持。 本文档提供有关数据平台和隐私合规性的其他详细信息，Microsoft 托管桌面。

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft 托管桌面数据源和用途

Microsoft 托管桌面向企业客户提供服务，并通过使用来自各种源的数据正确管理客户的注册设备。 这些源（包括 Azure Active Directory、Microsoft Intune、Microsoft Windows 10 和 Microsoft Defender for Endpoint）提供由 Microsoft 托管桌面 管理的设备的全面视图。 该服务还使用这些Microsoft 服务启用Microsoft 托管桌面 ITaaS 功能：

- [Microsoft Windows 10 企业版](/windows/windows-10/)- 用于管理设备设置体验、管理与其他服务的连接以及为 IT 专业人员提供的操作支持。
- [Windows企业更新](/windows/deployment/update/waas-manage-updates-wufb)- Windows 10 企业版诊断数据提供有关更新Windows 10信息。 
- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) – 用于设备管理和确保数据安全。
  - [Microsoft Azure Active Directory](/azure/active-directory/) - 用于身份验证和标识所有用户帐户。 
  - [Microsoft Intune](/mem/intune/) – 用于分发设备配置、设备管理和应用程序管理。
  - [Endpoint Analytics](/mem/analytics/overview) – 用于分析有关设备和应用使用情况的见解。
  - [Windows Autopilot](/microsoft-365/windows/windows-autopilot) – 用于设备预配和部署。
  - [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/) – 提供安全服务，如设备安全监视和安全智能数据。
- [Microsoft 托管桌面](https://endpoint.microsoft.com/#home)– 由客户提供或在服务运行期间由服务生成的数据。
- [Microsoft 365企业应用 –](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1)用于管理Microsoft 365 应用版。

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft 托管桌面数据处理和存储

Microsoft 托管桌面依赖来自多个 Microsoft 产品和服务的数据来为企业客户提供服务。 为实现保护和维护已注册设备的目标，我们将从这些服务中处理数据并复制到Microsoft 托管桌面。  处理数据时，我们将按照联机服务条款和 Microsoft 隐私声明中引用的提供记录[说明操作](https://privacy.microsoft.com/privacystatement)。 [](https://www.microsoft.com/licensing/product-licensing/products) Microsoft 托管桌面处理者的职责包括确保适当的机密性、安全性和复原能力。 Microsoft 托管桌面采取其他隐私和安全措施，以确保正确处理个人身份数据。 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft 托管桌面数据存储和员工位置

Microsoft 托管桌面将数据存储在美国的 Azure 数据中心。 需要由 Microsoft 托管桌面和其他服务获取的个人数据才能使服务正常运行。 如果设备已从 Microsoft 托管桌面 中删除，我们将个人数据最长保留 30 天，但 Microsoft Defender for Endpoint 收集的警报数据除外，出于安全目的，警报数据存储 180 天。 有关数据保留详细信息，请参阅数据保留[、删除和Microsoft 365。](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)

Microsoft 托管桌面工程运营和安全运营团队位于美国和印度。 

### <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10诊断数据

Microsoft 托管桌面使用[Windows 10](/windows/privacy/windows-diagnostic-data)增强诊断数据Windows安全、最新、解决问题以及改进产品。 增强的诊断数据设置包括有关在 Microsoft 托管桌面注册的设备及其设置、功能和设备运行状况的更多详细信息。 选择增强诊断数据后，将收集数据，包括所需的诊断数据。 有关[诊断Windows](/windows/privacy/changes-to-windows-diagnostic-data-collection)设置和数据收集Windows 10，请参阅对诊断数据收集的更改。

诊断数据术语将在未来版本的 Windows。 Microsoft 托管桌面致力于仅处理服务所需的数据。 虽然这意味着诊断级别将更改为 **"** 可选"，Microsoft 托管桌面将实现有限的诊断策略以微调服务所需的诊断数据收集。 有关详细信息，请参阅对诊断[Windows的更改](/windows/privacy/changes-to-windows-diagnostic-data-collection)。

Microsoft 托管桌面仅处理和存储来自Windows 10设备（如应用程序和设备可靠性和性能信息）的可选诊断数据中的系统级别数据。 Microsoft 托管桌面不会处理和存储客户的个人数据，例如聊天和浏览器历史记录、语音、文本或语音数据。 

有关 Microsoft Windows 10诊断数据收集Windows 10请参阅 Microsoft 隐私声明的"我们[](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)存储并处理个人数据的位置"部分。

### <a name="microsoft-windows-update-for-business"></a>适用于Windows Microsoft Windows 更新
适用于Windows Microsoft Windows Update 使用来自诊断的数据来分析更新状态和故障。 Microsoft 托管桌面利用此数据，并使用它来缓解和解决问题，以确保所有注册的设备都基于预定义的更新节奏是最新的。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
标识 Microsoft 托管桌面 使用的数据由 Azure Active Directory (Azure AD) 存储在一个地理位置中，该地理位置基于组织在订阅 Microsoft 联机服务（如 Microsoft Apps 企业版和 Azure）时提供的位置。 标识 Microsoft 托管桌面 使用的数据由 Azure AD 存储在地理位置中，该地理位置基于组织在订阅 Microsoft 联机服务（如 Microsoft Apps for enterprise 和 Azure）时提供的位置。 有关 Azure AD 数据所在的位置详细信息，请参阅Azure Active Directory [- 你的数据位于何处？](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune收集、处理数据并共享数据Microsoft 托管桌面以支持业务运营和服务。 有关 [在 Intune 中](/mem/intune/protect/privacy-data-collect) 收集的数据详细信息，请参阅 Intune 中的数据收集。 

有关数据位置Microsoft Intune，请参阅存储客户Microsoft 365[的位置](/microsoft-365/enterprise/o365-data-locations)。 Intune 遵守管理员为客户数据选择的存储位置。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint
Microsoft Defender for Endpoint 收集并存储设备上注册的设备Microsoft 托管桌面管理、跟踪和报告目的。 收集的信息包括文件数据 (如文件名、大小和哈希) 、进程数据 (正在运行的进程、哈希) 、注册表数据、网络连接数据和设备详细信息 (例如设备标识符、设备名称和操作系统版本) 。 有关 [适用于 Endpoint 的](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) Microsoft Defender 数据收集和存储位置详细信息，请参阅 Microsoft Defender for Endpoint 数据存储和隐私。 

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版 
Microsoft 365 企业应用版与 Microsoft 托管桌面 一起收集和共享数据，以确保这些应用是最新版本，且基于由 Microsoft 托管桌面 管理的预定义更新频道。 有关[你的数据收集和存储位置Microsoft 365 应用版](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)请参阅 Microsoft Defender for Endpoint 数据存储和隐私。

## <a name="major-data-change-notification"></a>主要数据更改通知
Microsoft 托管桌面遵循服务通信框架中概述的变更控制流程。 我们通过邮件Microsoft 365中心Microsoft 托管桌面管理员门户通知客户安全事件和服务的主要更改。 对收集的数据类型和存储位置的更改被视为重大更改。 我们将至少提前 30 天通知此更改，这是针对 Microsoft 365 服务的标准做法。 有关详细信息，请参阅服务 [更改和通信](/microsoft-365/managed-desktop/service-description/servicechanges)。

## <a name="compliance"></a>合规性
Microsoft 托管桌面已经过外部审核，并获得了一套全面的合规性产品/服务。 有关详细信息，请参阅Microsoft 托管桌面[合规性。](/microsoft-365/managed-desktop/intro/compliance) 可在 Microsoft 服务信任门户下载审核[](https://aka.ms/stp)报告，该门户充当 Microsoft Enterprise Online Services 的中央存储库。  (Microsoft 托管桌面列于这些文档中的"监控和管理"类别下。) 

### <a name="data-subject-requests"></a>数据主体请求
Microsoft 托管桌面 GDPR 和 CCPA 隐私条例，为数据主体授予其个人数据的特定权限。 这些权限包括获取个人数据的副本、请求更正、限制对个人数据的处理、删除或以电子格式接收，以便可以将其移动到另一个控制者。 有关数据主体请求 (DSR) ，请参阅数据主体请求以及[GDPR 和 CCPA。](/compliance/regulatory/gdpr-data-subject-requests)

若要对案例管理系统收集的数据执行数据Microsoft 托管桌面请求，请参阅以下内容：

- 来自 Microsoft Defender 终结点警报的数据：你的安全管理员可以请求删除或提取与 Microsoft Defender for Endpoint 警报相关的个人数据，方法为在管理门户 提交报告 [请求](https://aka.ms/memadmin)。 在请求中，选择"请求类型 **""更改请求"、** 类别 **"安全**"和"子类别 **""其他"。** 在请求描述中提供相关设备名称。
- 来自Microsoft 托管桌面请求的数据：你的 IT 管理员可以请求删除或提取与个人数据相关的支持请求，方法为在管理门户 中提交报告[请求](https://aka.ms/memadmin)。 在请求中，选择"请求类型 **""更改请求"、** 类别 **"安全**"和"子类别 **""其他"。** 在请求描述中提供相关的设备名称或用户名。

有关与服务相关的其他产品的 DSR，请参阅以下文章：

- Windows[诊断数据](/compliance/regulatory/gdpr-dsr-windows)
- Microsoft [Intune 数据](/compliance/regulatory/gdpr-dsr-intune)
- Azure Active [Directory 数据](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>法律
**Microsoft** 向组织客户提供的产品的最终用户的隐私声明 - [Microsoft](https://privacy.microsoft.com/privacystatement) 隐私声明通知最终用户使用工作帐户登录 Microsoft 产品时，) 其组织可以控制和管理其帐户 (包括控制隐私相关设置) 以及访问并处理其数据，b) Microsoft 可能会收集和处理数据，以向组织和最终用户提供服务。
