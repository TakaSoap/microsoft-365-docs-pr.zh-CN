---
title: 隐私和个人数据
description: 详细介绍了服务所收集、存储和使用的数据
keywords: GDPR、保留、删除、存储、保留、处理、安全性、审核
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: e1b0c856a3bfb886521ee2c1a2115e4c29504862
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47363250"
---
# <a name="privacy-and-personal-data"></a>隐私和个人数据

用户可以在由 Microsoft 托管桌面管理的设备上接收、传输和存储数据。 他们相信数据的隐私受到保护，并且只能以符合其预期的方式使用。 本文介绍 Microsoft 托管桌面如何收集、存储、保留、处理、保护、共享、审核和导出个人数据。 您还将了解管理员如何查看、更正和删除个人数据。

Microsoft 托管桌面不使用作为配置、广告或市场营销目的提供服务的一部分收集的任何个人数据。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft 托管桌面的数据集合

当用户在 Microsoft 托管桌面中注册企业设备时，将通过使用 Windows 和 Microsoft Intune 来处理数据收集（在技术层中）。 这些源收集有关用户设备的个人数据，例如 Microsoft 托管桌面的设备名称，以便能够识别要管理的设备并与 Microsoft 托管桌面体验一起提供。

Microsoft 托管桌面不会单独收集数据以提供其服务 (，但 [IT 管理员联系信息](#it-admin-contact-information)除外。 相反，Microsoft 托管桌面将重用其他源（如 Windows 和 Microsoft Intune）已收集的数据。 Microsoft 托管桌面使用这些服务从已注册的设备中收集的数据：

- 来自 Microsoft 托管桌面管理的设备的 Windows 诊断数据将被发送到 Microsoft 的 Windows 诊断数据存储。
- Microsoft 托管桌面使用 [新式管理](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) 来管理注册的设备。 作为此项的一部分，设备必须在租户的 Azure Active Directory 中注册。
- 为了将其高度优化和安全的配置分发到注册的设备，Microsoft 托管桌面使用 Microsoft Intune。
- Microsoft 托管桌面对使用此服务的客户使用 Microsoft Defender 高级线程防护中的安全智能数据。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的数据存储和源

在 Microsoft 托管桌面获取数据之后，它需要提供该数据的服务、存储和处理过程，如下所示：

### <a name="storing-data-storage-location-and-data-retention"></a>存储数据、存储位置和数据保留

Microsoft 托管桌面将其数据存储在以下一个或多个 Microsoft 存储服务中：

- Azure SQL
- Azure 存储

Microsoft 托管桌面将其数据存储在美国。 Microsoft 托管桌面保留的个人数据最多为30天。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft 托管桌面的数据使用情况

Microsoft 托管桌面使用以下数据：


| 数据源 |与 Microsoft 托管桌面配合使用  |
|---------|---------|
|Azure Active Directory 数据     | 在为租户管理员创建的报告中使用，这些报告在 Microsoft 托管桌面管理门户中提供。        |
|Intune 数据     | 在为租户管理员创建的报告中使用，这些报告在 Microsoft 托管桌面管理门户中提供。        |
|Microsoft Defender 高级威胁防护 (ATP)     |  用于解决 Microsoft 托管桌面安全操作中心在已注册设备上检测到的安全威胁， (SOC) 。  |
|Windows 诊断数据     |用于确定托管设备的更新状态，以及提供和改进 Microsoft 托管桌面的 IT 即用 (ITaaS) 服务。         |
|管理员联系人数据     | 由 Microsoft 托管桌面用于与租户管理员通信。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft 托管桌面处理的实体

Microsoft 托管桌面将处理这些实体以提供服务：

- 设备数据
- 设备安全设置
- 设备操作系统和硬件
- 有关设备运行状况的聚合信息
- 设备诊断信息
- 租户数据
- Azure Active Directory 资源
- 策略和配置数据
- Microsoft Defender ATP 元数据
- Windows 诊断数据
- 产品和服务使用情况数据

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft 托管桌面使用的标识数据由 Azure Active Directory 存储在地理位置中，在订阅 Microsoft online 服务（如 Office 365 或 Azure）时，将根据组织提供的地址存储在地理位置。 请参阅 [Microsoft Azure —哪里是我的客户数据？](http://azuredatacentermap.azurewebsites.net/) 有关显示 Azure Active Directory 的数据中心的地图的信息。

有关 Azure 用于数据存储的区域的详细信息，请参阅 [Azure Active Directory –你的数据位于何处](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune 数据可以存储在几个不同的区域中，例如欧洲北部 (爱尔兰) 和欧洲西部 (荷兰) 。 你的 IT 管理员创建租户帐户，并选择在最初在 Intune 服务中注册数据时将存储数据的国家/地区。 有关 Intune 使用的数据中心位置的列表，请参阅 [Microsoft Intune-我的客户数据在什么位置？](http://intunedatacentermap.azurewebsites.net/)。 有关 Intune 的数据存储和使用的详细信息，请参阅 [Intune 中的数据收集](https://docs.microsoft.com/intune/privacy-data-collect)。

### <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender 高级威胁防护

Microsoft Defender 高级威胁防护 (ATP) 数据可以存储在几个不同的区域中。 因此，Microsoft Defender ATP 在欧洲联合、英国和美国的 Microsoft Azure 数据中心中运行，如 [Microsoft DEFENDER ATP —数据存储位置](http://intunedatacentermap.azurewebsites.net/)中所述。 有关数据存储和 Microsoft Defender ATP 使用的详细信息，请参阅 [Microsoft DEFENDER atp 收集哪些数据？](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

如 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)中所述，"microsoft 收集的个人数据可能会在你的地区、美国和在 microsoft 或其子公司、子公司或服务提供商运营设施的任何其他国家/地区进行存储和处理。 [...]通常情况下，主存储位置在客户的区域中或在美国，通常会将备份到另一个区域中的数据中心。 将选择存储位置 (s) 以高效运行，提高性能，并创建冗余，以便在出现中断或其他问题时保护数据。 我们采取措施，以确保按照本声明的规定以及适用法律在数据所在的任何位置的要求来处理我们在此隐私声明下收集的数据。

有关 Windows 10 的诊断数据集合的详细信息，请参阅 Microsoft 隐私声明的 ["我们存储和处理个人数据的位置"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) 部分。

## <a name="data-access-protection"></a>数据访问保护

可通过以下几种方式限制直接访问 Microsoft 托管桌面的内部数据存储：

- 它需要工程组长级别的批准。
- 审核和时间有限。
- 它需要使用高度安全和受限制的工作站。
- 在存储所有数据时对其进行加密。
- 没有任何位置的访问权限。
- 对 Microsoft 托管桌面的内部管理门户的访问需要高度安全且受限制的工作站。

## <a name="processing-personal-data-in-a-compliant-manner"></a>以符合的方式处理个人数据
Microsoft 托管桌面使用 ISO 认证的系统处理个人数据。 有关详细信息，请参阅 [合规性](../intro/compliance.md)。

## <a name="profiling-and-marketing"></a>配置文件和市场营销

Microsoft 托管桌面不使用作为配置、广告或市场营销目的提供服务的一部分收集的任何个人数据。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>针对 GDPR 和 CCPA 的数据主体请求

欧盟 [通用数据保护法规 (GDPR) ](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 授予对在法规中 (已知的用户的权限，如数据主体) ，以管理由雇主或其他类型的代理或组织（称为数据控制器或仅控制器 (）收集的个人数据。 根据 GDPR，个人数据的定义非常宽泛，即指与已识别或可识别的自然人相关的任何数据。 GDPR 赋予数据主体对其个人数据的特定权利；这些权利包括，获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据，或接收能转移给另一个控制者的电子格式个人数据。 数据主体向控制者发出的对其个人数据执行操作的正式请求，称为数据主体请求 (DSR)。

同样，加利福尼亚州消费者隐私法案 (CCPA) 为加利福尼亚消费者提供隐私权利和义务，包括与 GDPR 的数据主体权限类似的权限，如删除、访问和接收 (可移植性) 个人信息的权限。 CCPA 还提供特定的披露，针对某些数据传输（属于 "销售"）的 "退出/选择" 要求来防范歧视。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide)和[加州消费者隐私法案常见问题解答](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)。

下面一节讨论 Microsoft 托管桌面如何帮助控制器查找、访问和操作 Microsoft 托管桌面使用的个人数据或个人信息。

> [!NOTE]
> 如果你正在寻找有关 GDPR 的一般信息，请参阅服务信任门户的 [GDPR 部分](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 。

### <a name="it-admin-contact-information"></a>IT 管理员联系信息

租户管理员可以直接在 Microsoft 托管桌面门户的 "管理员联系人" 部分中查看、更正和删除个人数据。

### <a name="user-related-personal-data"></a>与用户相关的个人数据

除此之外，Microsoft 托管桌面不会自行收集个人数据。 相反，它依赖和使用收集的其他 Microsoft 企业 Online Services 的个人数据。 IT 管理员希望对他们的用户请求进行查看、更正和删除个人数据的请求，可以使用 Microsoft 托管桌面所依赖的基础服务的各自功能。 如果你有兴趣查看或删除这些服务使用的个人数据，请先参阅 [针对 GDPR 的 Azure 数据主体请求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) 一文。

此外，请使用以下指南来为 Microsoft 托管桌面的服务执行 Dsr，具体取决于个人数据的集合：

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender ATP](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
