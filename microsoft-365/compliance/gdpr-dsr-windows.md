---
title: 符合 GDPR 和 CCPA 的适用于 Windows 数据主体请求的数据处理者服务
description: 了解如何使用 Microsoft 产品、服务和管理工具来查找和处理个人数据以响应 DSR。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 525b8b0783886a7449be72c89a2aa624afda9929
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023588"
---
# <a name="data-processor-service-for-windows-data-subject-requests-for-the-gdpr-and-ccpa"></a>符合 GDPR 和 CCPA 的适用于 Windows 数据主体请求的数据处理者服务 

>[!NOTE]
>本主题面向 Windows 预览程序的数据处理者服务的参与者，并且需要接受特定的使用条款。 若要了解有关计划的详细信息并同意使用条款，请参阅 [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview)。

## <a name="introduction-to-data-subject-requests-dsrs"></a>数据主体请求 (DSR) 简介 
一般数据保护条例 (GDPR) 赋予民众（在条例中称为_数据主体_）权利，即管理已由雇主或其他类型机构或组织（称为_数据控制者_或简称为_控制者_）收集的个人数据。 根据 GDPR，个人数据的定义非常宽泛，即指与已识别或可识别的自然人相关的任何数据。 GDPR 赋予数据主体对其个人数据的特定权利；这些权利包括，获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据，或接收能转移给另一个控制者的电子格式个人数据。 数据主体向控制者发出的对其个人数据执行操作的正式请求，称为_数据主体请求_ (DSR)。 

同样，加州消费者隐私法案 (CCPA) 规定了加州消费者的隐私权和义务，其中包括与 GDPR 的数据主体权利类似的权利，例如删除、访问和接收（可移植性）其个人信息的权利。 CCPA 还就某些披露规定了在选择行使权限时防止歧视的保障措施，并就分类为“销售”的特定数据传输提出了“选择退出/选择加入”要求。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa)和[加州消费者隐私法案常见问题解答](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq)。

本指南讨论了如何使用 Microsoft 产品、服务和管理工具以帮助我们的控制者客户查找和操作个人数据以响应 DSR。具体而言，这包括如何查找、访问和操作驻留在 Microsoft 云中的个人数据。下面是本指南中所列流程的快速概述： 

1. **访问** - 检索驻留在 Microsoft 云中的个人数据，如果提出请求，还制作可供数据主体使用的个人数据副本。 
2. **删除** - 永久删除驻留在 Microsoft 云中的个人数据。 
3. **导出** - 向数据主体提供个人数据的电子副本（采用机器可读格式）。 根据 CCPA 的定义，个人信息是指与已识别或可识别人员相关的任何信息。

根据 CCPA 的定义，个人信息是指与已识别或可识别人员相关的任何信息。 个人的私人、公共或工作角色之间没有任何区别。 所定义的“个人信息”术语与 GDPR 下的“个人信息”大致相同。 但是，CCPA 还包括家人和家庭数据。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa)和[加州消费者隐私法案常见问题解答](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq)。

本指南中的每个部分概述了数据控制者组织为响应对 Microsoft 云中个人数据的 DSR 而采取的技术过程。 

## <a name="terminology"></a>术语 
下面提供了与本指南相关的术语定义。 

* _控制者_ - 单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或具体提名条件。 

* _个人数据和数据主体_ - 身份已识别或可识别的自然人（“数据主体”）的任何相关信息；身份可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、联机标识等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。 

* _处理者_ - 代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。 

* _客户数据_ — 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文字、声音、视频或图像文件以及软件。 

* _Windows 诊断数据_ — Windows 设备中有关设备以及 Windows 和相关软件如何执行的非常重要的技术数据。 它用于保持 Windows 处于最新状态、安全、可靠、高性能，并通过对 Windows 使用情况的综合分析来改进 Windows。 Windows 诊断数据的一些示例包括正在使用的硬件类型、在其各自使用时安装的应用程序以及设备驱动程序的可靠性信息。 某些 Windows 组件和应用会直接连接到 Microsoft 服务，但它们交换的数据不是 Windows 诊断数据。 例如，将用户的位置交换为当地天气或新闻不是 Windows 诊断数据的示例。 

## <a name="how-to-use-this-guide"></a>如何使用本指南 

在对 Windows 注册设备使用数据处理者服务时，Windows 会生成一些信息（称为 Windows 诊断数据），以提供该服务。

## <a name="windows-diagnostic-data"></a>Windows 诊断数据 

Microsoft 为你提供了访问、删除和导出与用户使用 Windows 数据处理者服务相关的 Windows 诊断数据的功能。

>[!IMPORTANT]
>不支持修正 Windows 诊断数据的功能。 Windows 诊断数据构成 Windows 内执行的实际操作，对此类数据的修改将会损坏操作的历史记录，增加安全风险并危害可靠性。 文档中涵盖的所有数据都被视为 Windows 诊断数据。 

## <a name="executing-dsrs-against-windows-diagnostic-data"></a>针对 Windows 诊断数据执行 DSR 

Microsoft 让你能够通过 Azure 门户访问、删除和导出某些 Windows 诊断数据，也可直接通过预先存在的应用程序编程接口 (API) 执行此类操作。

### <a name="step-1-access"></a>步骤 1：访问 

租户管理员是组织中唯一可以访问特定 Windows 诊断数据（与特定用户对适用于 Windows 注册设备的数据处理者服务的使用有关）的人员。 为访问请求检索到的数据将通过导出方式，以机器可读格式提供，并在允许用户知道数据与哪些设备和服务关联的文件中提供。 如上所述，检索到的数据不包括可能会危及 Windows 设备安全性或稳定性的数据。 

Microsoft 提供了门户体验，让企业客户的租户管理员能够管理 DSR 访问请求。 [Azure DSR，第 2 部分，步骤 3：导出](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export)介绍如何通过 Azure 门户以导出方式执行 DSR 访问请求。

### <a name="step-2-delete"></a>步骤 2：删除 

Microsoft 提供了基于特定用户的 Azure Active Directory 对象执行基于用户的 DSR 删除请求的方法。

对于基于用户的删除请求，Microsoft 提供了门户体验，让企业客户的租户管理员能够管理 DSR 删除请求。 [Azure DSR，第 1 部分，步骤 5：删除](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-5-delete)介绍如何通过 Azure 门户执行 DSR 删除请求。 

Microsoft 提供通过预先存在的应用程序编程接口 (API) 直接删除用户（进而删除客户数据）的功能。 有关详细信息，请参阅 [API 参考文档](https://docs.microsoft.com/graph/api/directory-deleteditems-delete?view=graph-rest-beta)。 

>[!IMPORTANT]  
>删除收集的数据不会停止进一步收集。 若要关闭数据收集，请按照[各个服务的参考文档](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)中所述的步骤进行操作。
 
 此外，基于用户的删除请求需要删除用户帐户本身。 

### <a name="step-3-export"></a>步骤 3：导出 

租户管理员是组织中唯一可以访问特定 Windows 诊断数据（与特定用户对适用于 Windows 注册设备的数据处理者服务的使用有关）的人员。 为导出请求检索到的数据将以机器可读格式提供，并在允许用户知道数据与哪些设备和服务关联的文件中提供。 如上所述，检索到的数据不包括可能会危及 Windows 设备安全性或稳定性的数据。 [Azure DSR，第 2 部分，步骤 3：导出](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export)介绍如何通过 Azure 门户执行 DSR 导出请求。 

Microsoft 提供通过预先存在的应用程序编程接口 (API) 直接导出客户数据的功能。 有关详细信息，请参阅 [API 参考文档](https://docs.microsoft.com/graph/api/user-exportpersonaldata?view=graph-rest-1.0)。

## <a name="notify-about-exporting-or-deleting-issues"></a>通知导出或删除问题 

如果在从 Azure 门户导出或删除数据时遇到问题，请转到 Azure 门户“帮助 + 支持”**** 边栏选项卡，并在“订阅管理 > 其他安全与合规请求 > 隐私”边栏选项卡和“GDPR 请求”**** 下提交新票证。 
