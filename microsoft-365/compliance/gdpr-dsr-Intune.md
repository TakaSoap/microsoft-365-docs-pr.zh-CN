---
title: 针对 GDPR 和 CCPA 的 Intune 数据主体请求
description: 指南介绍了如何使用 Microsoft 的产品、服务和管理工具来帮助我们的控制者客户查找和处理个人数据以响应 DSR 和 CCPA 请求。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 4ed49de0254fb834f84816236c2925791076f423
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073339"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>针对 GDPR 和 CCPA 的 Intune 数据主体请求

根据欧盟[一般数据保护条例 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)，用户（在条例中称为“*数据主体*”）有权管理由雇主或其他类型机构或组织（称为“*数据控制者*”或简称为“*控制者*”）收集的个人数据。根据 GDPR，个人数据的定义非常广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据或接收电子格式的个人数据（以便于转移给其他控制者）。数据主体为了对自己的个人数据执行操作而向控制者发出的正式请求，称为“*数据主体请求*”或“DSR”。

同样，加州消费者隐私法案 (CCPA) 规定了加州消费者的隐私权和义务，包括与 GDPR 的数据主体权利类似的权利，例如删除、访问和接收（可移植性）其个人信息的权利。  CCPA 还就某些披露规定了在选择行使权限时防止歧视的保障措施，并就分类为“销售”的特定数据传输提出了“选择退出/选择加入”要求。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

本指南介绍了如何使用 Microsoft 产品、服务和管理工具来帮助我们的控制者客户查找和处理个人数据以响应 DSR。 具体而言，这包括如何查找、访问和处理驻留在 Microsoft 云中的个人数据或个人信息。 以下是本指南中所述的过程的快速概览：

- **发现：** 使用搜索和发现工具更轻松地查找可能是 DSR 主体的客户的数据。 收集了潜在的响应性文档后，你便可以执行下列步骤中所述的一项或多项 DSR 操作来响应请求。 或者，你也可以确定请求是否不符合组织的 DSR 响应指南。
- **访问：** 检索驻留在 Microsoft 云中的个人数据，并根据请求复制个人数据以供数据主体使用。
- **纠正：** 进行更改或者对个人数据实施其他请求的操作（如果适用）。
- **限制：** 通过移除各种 Azure 服务的许可证，或者在可能的情况下关闭所需的服务，限制对个人数据的处理。 此外还可以从 Microsoft 云中删除数据，并将其保留在本地或其他位置。
- **删除：** 永久删除保存在 Microsoft 云中的个人数据。
- **导出/接收（可移植性）：** 向数据主体提供个人数据或个人信息的电子副本（采用机器可读格式）。 根据 CCPA 的定义，个人信息是指与已识别或可识别人员相关的任何信息。 个人的私人、公共或工作角色之间没有任何区别。 所定义的“个人信息”术语与 GDPR 下的“个人信息”大致相同。 但是，CCPA 还包括家人和家庭数据。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

本指南中的每个部分概述了数据控制者组织为响应对 Microsoft 云中个人数据的 DSR 而采取的技术过程。

#### <a name="terminology"></a>术语

下面提供了与本指南相关的术语定义。

- **控制者：** 单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或其提名的具体准则。
- **个人数据和数据主体：** 身份已识别或可识别的自然人（“数据主体”）的任何相关信息；身份可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、联机标识符等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。
- **处理者：** 代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。
- **客户数据：** 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文字、声音、视频或图像文件以及软件。 客户数据包括 (1) 最终用户的身份信息（例如，Azure Active Directory 中的用户名和联系人信息）和客户上传到特定服务或者在特定服务中创建的客户内容（例如，Azure 存储帐户中的客户内容，Azure SQL 数据库的客户内容，或 Azure 虚拟机中的客户虚拟机映像）。
- **系统生成日志：** Microsoft 生成的日志和相关数据，可帮助 Microsoft 向用户提供企业服务。 系统生成日志主要包括化名数据，例如唯一标识符 — 这通常是系统生成的无法单独识别个人但用于向用户提供企业服务的一个数字。 系统生成日志还可能包含最终用户的身份信息，例如用户名。

#### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南由两部分组成：

- **第 1 部分：响应针对客户数据发出的数据主体请求：** 本指南的第 1 部分介绍了如何在你用来创作数据的应用程序中访问、校正、限制、删除和导出数据。 本节详细介绍了如何响应针对客户内容和最终用户的个人身份信息发出的 DSR。
- **第 2 部分：响应针对系统生成日志发出的数据主体请求：** 在你使用 Microsoft 的企业服务时，Microsoft 会生成一些信息（称为“系统生成日志”）来提供服务。 本指南的第 2 部分介绍了如何为 Azure 访问、删除和导出此类信息。

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>了解 Azure Active Directory 和 Microsoft Intune 的 DSR

在考虑提供给企业客户的服务时，必须始终在特定 Azure Active Directory (AAD) 租户环境中执行 DSR。需要注意的是，始终在给定的 AAD 租户内执行 DSR。如果用户参与了多个租户，则务必注意*仅*在收到请求的特定租户内执行给定的 DSR。必须知道的是，这意味着一个企业客户执行 DSR **不会**影响相邻企业客户的数据。

这同样也适用于提供给企业客户的 Microsoft Intune：针对*与 AAD 租户关联*的 Intune 帐户执行 DSR **将仅**与租户内的数据相关。此外，在处理租户内的 Intune 帐户时，请务必了解以下内容：

- 如果 Intune 用户创建了 Azure 订阅，订阅将视为 AAD 租户。因此，如上文所述，DSR 的范围仅限于租户。
- 如果删除通过 Intune 帐户创建的 Azure 订阅，**不会影响**实际 Intune 帐户。同样，如上所述，Azure 订阅中执行的 DSR 仅限于租户本身。

在**给定租户外**针对 Intune 帐户本身的 DSR 将通过消费者隐私面板执行。请参考“Windows 数据主体请求指南”了解更多详细信息。

## <a name="part-1-dsr-guide-for-customer-data"></a>第 1 部分：客户数据的 DSR 指南

### <a name="executing-dsrs-against-customer-data"></a>针对客户数据执行 DSR

Microsoft 让你能够通过 Azure 门户访问、删除和导出某些客户数据，也可直接通过特定服务的预先存在的应用程序编程接口 (API) 或用户界面 (UI)（也称为*产品内体验*）。有关此类产品内体验的详细信息，在各个服务的参考文档中进行了介绍。

>[!IMPORTANT]  
>支持产品内 DSR 的服务要求直接使用服务的应用程序编程接口 (API) 或用户界面 (UI)，描述适用的 CRUD（创建、读取、更新、删除）操作。因此，除了在 Azure 门户中内执行 DSR 之外，还必须在给定服务内执行 DSR，以便完成针对给定数据主体的完整请求。请参考特定服务的参考文档以了解更多详细信息。

### <a name="step-1-discover"></a>步骤 1：发现

响应 DSR 的第一步是查找作为请求主体的个人数据。这第一步（查找和审查所涉及的个人数据）将帮助你确定 DSR 是否符合组织有关接受或拒绝 DSR 的要求。例如，在查找并审查所涉及的个人数据后，你可以确定请求不符合组织的要求，因为这样做可能会对他人的权利和自由产生负面影响。

找到数据后，可执行特定操作以满足数据主体的请求。有关详细信息，请参阅以下内容：

- [数据收集](https://docs.microsoft.com/intune/privacy-data-collect)
- [数据存储和处理](https://docs.microsoft.com/intune/privacy-data-store-process)
- [查找个人数据](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>步骤 2：访问

在找到包含潜在响应 DSR 的个人数据的客户数据后，应该由你和你的组织决定将哪些数据提供给数据主体。可以通过实际文档副本、经过适当编校的版本或者你认为适合共享的部分的屏幕截图来提供。对于访问请求的每个响应，需要检索包含响应数据的文档或其他项目的副本。

将副本提供给数据主体时，可能需要删除或修订有关其他数据主体和任何机密信息的个人信息。

下面说明了如何获取数据副本来响应 DSR 访问请求。

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft 提供了门户和产品内体验，让企业客户的租户管理员能够管理 DSR 访问请求。 响应 DSR 访问请求时可以访问用户的个人数据，包括：(a) 最终用户的个人身份信息，以及 (b) 系统生成日志。

#### <a name="service-specific-interfaces"></a>特定于服务的界面

Microsoft Intune 通过用户界面 (UI) 或预先存在的应用程序编程接口 (API) 直接提供[发现客户数据](#step-1-discover)的功能。

### <a name="step-3-rectify"></a>步骤 3：纠正

如果数据主体要求你纠正驻留在你组织数据中的个人数据，你和你的组织需要确定是否接受请求。纠正数据可能包括以下操作：编辑、修订个人数据或从文档或其他项目类型中移除个人数据。

Microsoft 作为数据处理者不提供纠正系统生成的日志的功能，因为它反映真实活动并构成 Microsoft 服务内事件的历史记录。对于 Intune，管理员无法更新特定于设备或应用的信息。如果最终用户想要纠正任何个人数据（例如，设备名称），他们必须直接在其设备上执行此操作。此类更改将在他们下次连接到 Intune 时同步。

### <a name="step-4-restrict"></a>步骤 4：限制

数据主体可能要求限制对其个人数据的处理。 我们同时提供了 Azure 门户和预先存在的应用程序编程接口 (API) 或用户界面 (UI)。 这些体验让企业客户的租户管理员能够通过将数据导出与数据删除相结合来管理此类 DSR。 有关详细信息，请参阅[处理个人数据](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)。

### <a name="step-5-delete"></a>步骤 5：删除

从组织的客户数据中删除个人数据的“清除权限”是 GDPR 中提供的重要保护。删除个人数据包括删除所有个人数据和系统生成的日志（审核日志信息除外）。有关详细信息，请参阅[删除最终用户个人数据](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data)。

## <a name="part-2-system-generated-logs"></a>第 2 部分：系统生成的日志

审核日志向租户管理员提供在 Microsoft Intune 中生成的更改的活动记录。审核日志适用于许多管理活动，通常包括创建、更新（编辑）、删除和分配操作。也可以查看生成审核事件的远程任务。这些审核日志可能包含在 Intune 中注册了设备的用户的个人数据。管理员无法删除审核日志。有关详细信息，请参阅[审核个人数据](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data)。

## <a name="notify-about-exporting-or-deleting-issues"></a>通知导出或删除问题

如果在从 Azure 门户导出或删除数据时遇到问题，请转到 Azure 门户“帮助 + 支持”**** 边栏选项卡，并在“订阅管理 > 其他安全与合规请求 > 隐私”边栏选项卡和“GDPR 请求”**** 下提交新票证。

## <a name="learn-more"></a>了解更多

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
