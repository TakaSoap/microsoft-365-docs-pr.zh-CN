---
title: 适用于 GDPR 的 Windows DPIA 数据处理者
description: 查找信息以确定在使用 Microsoft Windows 数据处理者服务时是否需要进行数据保护影响评估 (DPIA)。
keywords: DPIA, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
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
ms.openlocfilehash: c594bbca6383874346719a477d3f86f3dac99409
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023592"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-data-processor-service-for-windows"></a>数据保护影响评估：使用 Microsoft Windows 数据处理者服务的数据控制者指南

>[!NOTE]
>本主题面向 Windows 预览程序的数据处理者服务的参与者，并且需要接受特定的使用条款。 若要了解有关计划的详细信息并同意使用条款，请参阅 [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview)。

根据 一般数据保护条例 (GDPR)，数据控制者需要为“可能对自然人的权限和自由造成高风险”的处理操作准备数据保护影响评估(DPIA)。 Windows 本身的数据处理者服务中没有固有的内容，这必然要求使用它的数据控制者创建 DPIA。 无论是否需要 DPIA，都将依赖于数据控制者部署、配置和使用 Windows 数据处理者服务的详细信息和上下文。 

此文档的目的是为数据控制者提供 Windows 数据处理者服务的相关信息，帮助他们确定是否需要 DPIA 以及要包含的详细信息（如果需要）。

>[!Note]
>Microsoft 在此文档中未提供任何法律建议。 本文档仅供参考。 我们鼓励客户与其隐私官和法律顾问合作，以确定与使用 Windows 数据处理者服务或任何其他 Microsoft 联机服务相关的任何 DPIA 的必要性和内容。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 – 确定是否需要 DPIA

GDPR 第 35 条要求数据控制者来创建数据保护影响评估 (DPIA)，“用于在考虑某种处理类型的本质、范围、上下文和目的的情况下评估该处理类型（尤其是使用新技术的处理类型）是否会对自然人的权力和自由产生高风险。” 下表还列出了表明如此高风险的特定因素。 确定是否需要 DPIA 时，数据控制者应根据控制者的特定实现和 Windows 数据处理者服务的使用情况，考虑这些因素以及任何其他相关因素。

## <a name="table-1--data-processor-service-for-windows-dpia-risk-factors"></a>表 1 – Windows DPIA 风险因素数据处理者服务 

|||
|:----|:----|
|**高风险因素**|**关于 Windows 数据处理者服务的相关信息**|
| 基于自动化处理对自然人的私人方面进行系统全面的评估（包括剖析以及会对自然人产生法律效应或显著影响自然人的决策）。 |Windows 数据处理者服务不具有特定的自动数据处理功能。<br><br> 但是，由于其他服务使用 Windows 数据处理者服务作为数据源，因此数据控制者可能会配置那些服务以用于此类处理。 控制者应根据其对 Windows 数据处理者服务所连接服务的使用情况进行确定。|   
| 处理大量特殊类别的数据，如种族或族裔、政治观点、宗教或哲学信仰、工会成员身份、基因数据、用于唯一标识自然人的生物识别数据、关于自然人性生活健康或性取向数据的数据，或与刑事犯罪和违法行为相关的个人数据。 | Windows 数据处理者服务不专用于处理特殊类别的个人数据，并且使用 Windows 数据处理者服务并不会增加控制者处理数据本身所具有的风险。<br><br> 但是，数据控制者可以使用连接到 Windows 数据处理者服务的服务来处理枚举的特殊数据类别。 使用 Windows 数据处理者服务作为数据源的服务可以使客户能够跟踪或以其他方式处理任何类型的数据，包括特殊类别的个人数据。 但作为数据处理者，Microsoft 不对此类使用进行任何控制，且对此类使用鲜有或没有任何见解。 数据控制者有责任确定数据控制者数据的适当用途。 |

## <a name="part-2--contents-of-a-dpia"></a>第 2 部分 - DPIA 的内容 

Article 35(7) mandates that a Data Protection Impact Assessment specify the purposes of processing and a systematic description of the envisioned processing. A systematic description of a comprehensive DPIA might include factors such as the types of data processed, how long data is retained, where the data is located and transferred, and what third parties may have access to the data. In addition, the DPIA must include: 

对与处理操作的目的相关的必要性和合理性的评估； 

对自然人的权力和自由带来的风险的评估；以及 

应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此条例的规定（将数据使用者和其他相关人员的合法权益考虑在内）。 

下表包含与上述每个元素相关的 Windows 数据处理者服务信息。 如第 1 部分中所述，根据控制者的具体实施和 Windows 数据处理者服务的使用情况，数据控制者必须考虑下面提供的详细信息，以及任何其他相关因素。 

## <a name="table-2--data-processor-service-for-windows-dpia-elements"></a>表 2 – Windows DPIA 元素数据处理者服务 

||||
|:---|:---|:--|
|**DPIA 的元素**|**关于 Windows 数据处理者服务的相关信息**| |
| 处理目的 | 使用 Windows 数据处理者服务诊断数据的目的由实现、配置和使用其的控制者决定。 <br><br> 正如[联机服务条款 (OST) ](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中所规定，作为数据处理者，Microsoft 处理客户数据只是为了向客户（即数据控制者）提供所请求的服务。 Microsoft 不会将因此获得的客户数据或信息用于任何广告或类似商业目的。 |
| 处理的个人数据类别 | **客户数据** - 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文字、声音、视频或图像文件以及软件。 客户数据包括最终用户的可识别信息（例如 Azure Active Directory 中的用户名和联系信息或 Windows 诊断数据中的设备信息）。 <br><br> **系统生成数据：** Microsoft 生成的数据，可帮助 Microsoft 向用户提供企业服务。 系统生成数据主要包括化名数据，例如唯一标识符（它由系统生成，无法单独识别个人，但可用于向用户提供企业服务）。 系统生成数据还可能包含有关最终用户的身份信息，例如用户名。 <br><br> **支持数据** - 客户或代表客户通过与 Microsoft 签订协定以获取联机服务技术支持而提供给 Microsoft 的数据（或客户授权 Microsoft 从联机服务获取的数据）。 <br><br> 有关 Windows 数据处理者服务所处理数据的其他详细信息，请参阅[联机服务条款](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和 [Microsoft 信任中心](https://www.microsoft.com/trustcenter)。 |
| 数据保留 | Microsoft 将在客户有权使用该联机服务期间保留和处理客户数据，直到客户检索所有客户数据或根据 OST 的条款删除所有客户数据。 在客户订阅期间的任何时候，客户都可以导出存储在 Windows 数据处理者服务中的客户数据。 客户可使用 [Windows 数据处理者服务数据使用者数据主体请求文档](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)中介绍的功能根据数据使用者请求删除个人数据。
| 个人数据的位置和传输 | Windows 数据处理者服务客户数据驻留在美国的 Microsoft 数据中心。 |
| 与第三方分享的数据 | Microsoft shares data with third parties acting as our subprocessors (i.e., subcontractors which process personal data) to support functions such as customer and technical support, service maintenance, and other operations. Any subcontractors to which Microsoft transfers Customer Data or Support Data will have entered into written agreements with Microsoft that are no less protective than the Data Protection Terms of the [Online Services Terms](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). All third-party subcontractors with which Customer Data or Support Data is shared are included in the [Lists of subcontractors](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors) (see “We limit access by subprocessors”). <br><br> Information regarding Microsoft’s response to law enforcement and third party requests for Customer Data and Support Data is located in the Online Services Terms. Unless Microsoft is legally prohibited from doing so, Microsoft will attempt to redirect the law enforcement agency or third party directly to the Customer. |
| 数据主体权利 | 当以处理者的身份操作时，Microsoft 向客户（即控制者）提供其数据使用者的个人数据以及依据 GDPR 行使权力时满足数据使用者请求的能力。 Microsoft 以与产品功能和作为数据处理者的角色一致的方式完成此操作。如果 Microsof 收到来自客户数据使用者的请求，请求依据 GDPR 行使其一项或多项权力，则该请求将重定向到数据控制者。 <br><br> [Windows 数据处理者服务数据使用者数据主体请求文档](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)介绍如何使用 Windows 数据处理者中的功能支持数据使用者权力。 |
| 对与处理操作的目的相关的必要性和合理性的评估 | 这种评估将取决于数据控制者的处理需求和目的。 <br><br> With regard to the processing carried out by Microsoft, such processing is necessary and proportional for the purpose of providing the services to the data controller. Microsoft makes this commitment in the OST. |
| 对数据使用者的权力和自由带来的风险的评估 | 使用 Windows 数据处理者服务对数据使用者的权力和自由带来的关键风险取决于数据控制者实施、配置和使用 Windows 数据处理者服务的方式和背景。 <br><br> However, as with any service, personal data held in the service may be at risk of unauthorized access or inadvertent disclosure. Measures Microsoft takes to address such risks are discussed in the OST, as further detailed below. |
| 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此 GDPR 的规定（将数据使用者和其他相关人员的合法权益考虑在内）。 | Microsoft is committed to helping protect the security of Customer Data. The security measures Microsoft takes are described in detail in the OST. <br><br> Microsoft 采取合理和适当的技术和组织措施来保护其处理的个人数据。 这些措施包括但不限于内部隐私政策和惯例，合同承诺以及国际和区域标准认证。 有关更多信息，请访问[信任中心隐私标准页面](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)。 <br><br> Microsoft provides significant, transparent customer facing security and privacy materials to help explain Microsoft’s use and processing of personal data. Customers are encouraged to contact Microsoft with questions. <br><br> 此外，Microsoft 履行 GDPR 规定的适用于数据处理者的所有其他义务，包括但不限于数据保护影响评估和记录保存。| 
