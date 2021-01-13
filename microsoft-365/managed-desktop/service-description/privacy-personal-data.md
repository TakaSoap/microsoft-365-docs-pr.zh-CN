---
title: 隐私和个人数据
description: 详细说明服务收集、存储和使用的数据
keywords: GDPR， 保留， 删除， 存储， 保留， 处理， 安全性， 审核
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7005e09d5a3df158569e132d2954f3b9a0ebf371
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840477"
---
# <a name="privacy-and-personal-data"></a>隐私和个人数据

用户可以在由 Microsoft 托管桌面管理的设备上接收、传输和存储数据。 他们信任数据隐私受到保护，并且仅按照符合其预期的方式使用。 本文介绍了 Microsoft 托管桌面如何收集、存储、保留、处理、保护、共享、审核和导出个人数据。 你还将了解管理员如何查看、更正和删除个人数据。

Microsoft 托管桌面不会将收集的任何个人数据用作提供服务以用于分析、广告或市场营销目的。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft 托管桌面的数据收集

当用户将公司设备注册到 Microsoft 托管桌面时，使用 Windows 和 Microsoft Intune 在技术层处理数据收集。 这些源收集有关用户设备的个人数据，例如 Microsoft 托管桌面的设备名称，以便识别要管理和提供 Microsoft 托管桌面体验的设备。

Microsoft 托管桌面不会自行收集数据以提供其服务 ([IT 管理员联系信息除外](#it-admin-contact-information)。 相反，Microsoft 托管桌面会重用其他源（如 Windows 和 Microsoft Intune）已收集的数据。 Microsoft 托管桌面使用这些服务从注册设备收集的数据：

- 来自由 Microsoft 托管桌面管理的设备的 Windows 诊断数据将发送到 Microsoft 的 Windows 诊断数据存储。
- Microsoft 托管桌面 [使用新式管理](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) 来管理已注册的设备。 作为"新式管理"的一部分，设备必须在租户的 Azure Active Directory 中注册。
- 为了将高度优化和安全的配置分发到已注册的设备，Microsoft 托管桌面使用 Microsoft Intune。
- Microsoft 托管桌面为使用 Microsoft Defender 高级线程保护的客户使用 Microsoft Defender 高级线程保护中的安全智能数据。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的数据存储和源

在 Microsoft 托管桌面获取数据后，它需要提供其服务、存储和数据处理，如下所示：

### <a name="storing-data-storage-location-and-data-retention"></a>存储数据、存储位置和数据保留

Microsoft 托管桌面将数据存储在下列一个或多个 Microsoft 存储服务中：

- Azure SQL
- Azure 存储

Microsoft 托管桌面将数据存储在美国。 个人数据由 Microsoft 托管桌面最长保留 30 天。

### <a name="staff-location"></a>员工位置

MMD 操作和 MMD 安全运营团队位于美国和印度。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft 托管桌面的数据使用情况

Microsoft 托管桌面使用此数据：


| 数据源 |与 Microsoft 托管桌面一起使用  |
|---------|---------|
|Azure Active Directory 数据     | 用于为租户管理员创建的报表，这些报告在 Microsoft 托管桌面管理门户中提供。        |
|Intune 数据     | 用于为租户管理员创建的报表，这些报告在 Microsoft 托管桌面管理门户中提供。        |
|Microsoft Defender for Endpoint     |  用于解决由 Microsoft 托管桌面的安全运营中心或 SOC 组织在已注册 (检测到) 。  |
|Windows 诊断数据     |用于确定托管设备的更新状态，并提供和改进 Microsoft 托管桌面的 IT 即服务 (ITaaS) 产品。         |
|管理员联系人数据     | 由 Microsoft 托管桌面用于与租户管理员通信。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft 托管桌面处理的实体

Microsoft 托管桌面处理这些实体以提供服务：

- 设备数据
- 设备安全设置
- 设备操作系统和硬件
- 有关设备运行状况的聚合信息
- 设备诊断信息
- 租户数据
- Azure Active Directory 资源
- 策略和配置数据
- Microsoft Defender for Endpoint 元数据
- Windows 诊断数据
- 产品和服务使用情况数据

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft 托管桌面使用的标识数据由 Azure Active Directory 存储在基于组织在订阅 Microsoft 联机服务（如 Office 365 或 Azure）时所提供的地址的地理位置。 有关显示 Azure Active Directory 数据中心的地图，请参阅 [Microsoft Azure—我的](http://azuredatacentermap.azurewebsites.net/) 客户数据在哪里？

有关 Azure 用于数据存储的区域详细信息，请参阅 Azure [Active Directory–你的数据所在的位置](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune 数据存储在一些不同的区域，如欧洲北部 (爱尔兰) 以及 (荷兰) 。 IT 管理员创建租户帐户，并选择最初在 Intune 服务中注册时存储数据的国家/地区。 有关 Intune 使用的数据中心位置的列表，请参阅[Microsoft Intune—我的客户数据在哪里？](http://intunedatacentermap.azurewebsites.net/) 有关数据存储和 Intune 使用的信息，请参阅 [Intune 中的数据收集](https://docs.microsoft.com/intune/privacy-data-collect)。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Microsoft Defender for Endpoint 数据存储在几个不同的区域。 因此，Defender for Endpoint 在欧盟、英国和美国的 Microsoft Azure 数据中心中运行，如 [Microsoft Defender for Endpoint 数据存储](http://intunedatacentermap.azurewebsites.net/)位置所规定。 有关数据存储和 Defender for Endpoint 使用的信息，请参阅 Microsoft Defender for Endpoint 收集 [哪些数据？](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

如 Microsoft 隐私声明所规定 [，"Microsoft](https://privacy.microsoft.com/privacystatement)收集的个人数据可以在你地区的美国以及 Microsoft 或其关联公司、子公司或服务提供商运营设施的任何其他国家/地区进行存储和处理。 [...]通常，主存储位置位于客户区域或美国，通常具有对另一个地区的数据中心的备份。 选择 (存储位置) ，以便高效操作、提高性能以及创建冗余，以在出现中断或其他问题时保护数据。 我们采取措施，确保根据本声明的规定以及无论数据位于何处的适用法律的要求，处理我们在此隐私声明下收集的数据。"

有关 Windows 10 诊断数据收集详细信息，请参阅 Microsoft[](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)隐私声明的"我们存储并处理个人数据的位置"部分。

## <a name="data-access-protection"></a>数据访问保护

通过多种方式限制直接访问 Microsoft 托管桌面的内部数据存储：

- 它需要工程领导级审批。
- 它同时受审核和时间限制。
- 它需要使用高度安全和受限的工作站。
- 所有数据在存储时都经过加密。
- 没有长期访问权限。
- 访问 Microsoft 托管桌面的内部管理门户需要高度安全且受限制的工作站。

## <a name="processing-personal-data-in-a-compliant-manner"></a>以合规方式处理个人数据
Microsoft 托管桌面使用 ISO 认证的系统处理个人数据。 有关详细信息，[请参阅合规性。](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>分析和营销

Microsoft 托管桌面不会将收集的任何个人数据用作提供服务以用于分析、广告或市场营销目的。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>针对 GDPR 和 CCPA 的数据主体请求

欧盟一般数据保护条例 [ (GDPR) ](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) (赋予在法规中称为数据主体) 的人) 管理由雇主或其他类型机构或组织收集的个人数据 (称为数据控制者或仅控制者) 。 根据 GDPR，个人数据的定义非常宽泛，即指与已识别或可识别的自然人相关的任何数据。 GDPR 赋予数据主体对其个人数据的特定权利；这些权利包括，获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据，或接收能转移给另一个控制者的电子格式个人数据。 数据主体向控制者发出的对其个人数据执行操作的正式请求，称为数据主体请求 (DSR)。

同样，加州消费者隐私法案 (CCPA) 规定了加州消费者的隐私权利与义务，包括与 GDPR 的数据主体权利类似的权利，例如删除、访问和接收 (可移植性) 个人信息的权利。 CCPA 还提供了某些披露、选择行使权利时防止泄露的保护措施，以及某些分类为"销售"的数据传输的"选择退出/选择加入"要求。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide)和[加州消费者隐私法案常见问题解答](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)。

以下部分讨论 Microsoft 托管桌面如何帮助控制者查找、访问和操作 Microsoft 托管桌面使用的个人数据或个人信息。

> [!NOTE]
> 如果要查找有关 GDPR 的常规信息，请参阅服务信任门户 [的 GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 部分。

### <a name="it-admin-contact-information"></a>IT 管理员联系信息

租户管理员可以直接在 Microsoft 托管桌面门户的"管理员 ("部分查看、更正和删除自己的个人数据) 例如自己的联系信息。

### <a name="user-related-personal-data"></a>与用户相关的个人数据

除此之外，Microsoft 托管桌面不会自行收集个人数据。 相反，它依赖于并使用其他 Microsoft Enterprise Online Services 收集的个人数据。 希望响应其用户查看、更正和删除其个人数据请求的 IT 管理员可以使用 Microsoft 托管桌面所依赖的基础服务各自的功能。 如果你有兴趣查看或删除这些服务使用的个人数据，请首先参阅 [适用于 GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) 的 Azure 数据主体请求文章。

此外，使用以下指南为 Microsoft 托管桌面收集个人数据所依赖的服务练习 DSR：

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender for Endpoint](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
