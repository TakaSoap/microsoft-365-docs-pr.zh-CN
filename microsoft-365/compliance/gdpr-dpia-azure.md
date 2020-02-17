---
title: 根据 GDPR 对 Azure 进行 DPIA
description: ''
keywords: DPIA, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
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
ms.openlocfilehash: cb2b9251a7b4fdaa987a803075f0040b93b2f59a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073359"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-azure"></a>数据保护影响评估：使用 Microsoft Azure 的数据控制者指南

根据一般数据保护条例 (GDPR)，需要由数据控制者准备数据保护影响评估 (DPIA)，用于处理“可能对自然人的权力和自由产生高风险”的操作。Microsoft Azure 本身并不一定要求由使用它的数据控制者创建 DPIA。更准确地说，是否需要 DPIA 取决于数据控制者部署、配置和使用 Microsoft Azure 的*方式*和背景。

此文档的目的是为数据控制者提供 Microsoft Azure 的相关信息，帮助他们确定是否需要 DPIA 以及要包含的详细信息。

> [!Note]
> Microsoft 在此文档中未提供任何法律建议。 本文档仅供参考。 我们鼓励客户与其隐私官和法律顾问合作，以确定与使用 Microsoft Azure 或任何其他 Microsoft 联机服务相关的任何 DPIA 的必要性和内容。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 – 确定是否需要 DPIA

GDPR 第 35 条要求数据控制者来创建数据保护影响评估 (DPIA)，“用于在考虑某种处理类型的本质、范围、上下文和目的的情况下评估该处理类型（尤其是使用新技术的处理类型）是否会对自然人的权力和自由产生高风险。” 它进一步规定了指示此类高风险的特定因素（将在下表中讨论）。根据控制者的具体实施和 Microsoft Azure 的使用情况，确定是否需要 DPIA 时，数据控制者应考虑以下因素，以及任何其他相关因素。

|||
|:----|:----|
|**高风险因素**|**Microsoft Azure 的相关信息**|
| 基于自动化处理对自然人的私人方面进行系统全面的评估（包括剖析以及会对自然人产生法律效应或显著影响自然人的决策）。| Microsoft Azure 不具有特定的自动数据处理功能。 <br><br> *但是，由于 Azure 是一项高度可定制的服务，数据控制者可对其进行配置，以用于此类处理*。控制者应根据 Azure 的使用情况决定是否对其进行配置。 |
| 处理大量特殊类别的数据，如种族或族裔、政治观点、宗教或哲学信仰、工会成员身份、基因数据、用于唯一标识自然人的生物识别数据、关于自然人性生活健康或性取向数据的数据，或与刑事犯罪和违法行为相关的个人数据。 | Microsoft Azure 不专用于处理特殊类别的个人数据，并且使用 Azure 并不会增加控制者处理数据本身所具有的风险。 <br><br> *不过，数据控制者可使用 Microsoft Azure 处理枚举的特殊类别的数据*。Microsoft Azure 是一项高度可定制的服务，支持客户跟踪或处理任何类型的数据，包括特殊类别的个人数据。但作为数据处理者，Microsoft 不对此类使用进行任何控制，且通常对此类使用鲜有或没有任何见解。数据控制者应确保恰当使用数据控制者的数据。 |
| 大规模系统化监视公开可访问区域  | Microsoft Azure 不专用于进行或帮助此类监视。 <br><br> *不过，数据控制者可使用 Microsoft Azure 处理通过此类监视收集的数据。* Microsoft Azure 是一项高度可定制的服务，支持客户跟踪或处理任何类型的数据，包括监视数据。但作为数据处理者，Microsoft 不对此类使用进行任何控制，且通常对此类使用鲜有或没有任何见解。数据控制者应确保恰当使用数据控制者的数据。 |

## <a name="part-2--contents-of-a-dpia"></a>第 2 部分 — DPIA 的内容

第 35(7) 条规定，数据保护影响评估应指定处理的目的和预期处理的系统化说明。 综合 DPIA 的系统化说明可能包括所处理数据的类型、数据保留时间、数据存储位置和传输位置以及有权访问数据的第三方等因素。 此外，DPIA 还必须包括：

- 对与处理操作的目的相关的必要性和合理性的评估；
- 对自然人的权力和自由带来的风险的评估；以及
- 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此条例的规定（将数据使用者和其他相关人员的合法权益考虑在内）。

下表包含与上述每个元素相关的 Microsoft Azure 信息。如第 1 部分中所述，根据控制者的具体实施和 Microsoft Azure 的使用情况，数据控制者必须考虑下面提供的详细信息，以及任何其他相关因素。

||||
|:---|:---|:--|
|**DPIA 的元素**|**Microsoft Azure 的相关信息**| |
| 处理目的 | 使用 Microsoft Azure 处理数据的目的由实施、配置和使用它的控制者确定。 <br><br> 正如[联机服务条款 (OST)](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 中所规定，作为数据处理者，Microsoft 处理客户数据只是为了向客户（即数据控制者）提供所请求的服务。Microsoft 不会将客户数据或相关信息用于任何广告或类似商业目的。 |   |
| 处理的个人数据类别  | *客户数据* — 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文本、声音、视频或图像文件以及软件。  客户数据包括 (1) 最终用户的身份信息（例如，Azure Active Directory 中的用户名和联系人信息）和客户上传到特定服务或者在特定服务中创建的客户内容（例如，Azure 存储帐户中的客户内容，Azure SQL 数据库的客户内容，或 Azure 虚拟机中的客户虚拟机映像）。<br><br> *系统生成日志* — Microsoft 生成的日志和相关数据，可帮助 Microsoft 向用户提供企业服务。 系统生成日志主要包括化名数据，例如唯一标识符（它由系统生成，无法单独识别个人，但可用于向用户提供企业服务）。  系统生成日志还可能包含最终用户的身份信息，例如用户名。 <br><br> *支持数据* — 客户或代表客户通过与 Microsoft 签订协定以获取联机服务技术支持而提供给 Microsoft 的数据（或客户授权 Microsoft 从联机服务获取的数据）。 <br><br> 有关 Azure 所处理数据的其他详细信息，请参阅[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和 [Microsoft 信任中心](https://www.microsoft.com/trustcenter)。</p> |   |
| 数据保留 | Microsoft 将在客户有权使用该联机服务期间保留和处理客户数据，直到客户检索所有客户数据或根据 OST 的条款删除所有客户数据。  在客户订阅期内，客户可随时访问和提取每个联机服务中存储的客户数据。 除免费试用版和领英服务外，如果客户订阅到期或终止，帐户功能将受到限制，Microsoft 会将该帐户存储在该联机服务中的客户数据保留 90 天，便于客户提取数据。 90 天保留期结束后，Microsoft 将禁用客户帐户并删除客户数据。 客户可使用 [Azure 数据使用者请求 GDPR 文档](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)中介绍的功能根据数据使用者请求删除个人数据。 |   |
| 个人数据的位置和传输 | 客户能够在指定的[地理区域](https://azure.microsoft.com/global-infrastructure/)中预配静态的客户数据，但 OST 中规定了一些例外情况。有关服务部署和数据驻留的其他详细信息，请参阅 [Azure 全球基础结构](https://azuredatacentermap.azurewebsites.net/)网页。<br><br>对于来自欧洲经济区和瑞士的个人数据，Microsoft 将确保在向第三方国家/地区或国际组织传输的个人数据时实施 GDPR 第 46 条中规定的相应安全措施。除 Microsoft 根据处理者标准合同条款和其他模板合同所做的承诺外，Microsoft 还获得了欧盟-美国和瑞士-美国隐私防护框架认证并践行其承诺。 |   |
| 与第三方分享的数据 | Microsoft 会与充当下级处理者（即处理个人数据的分包商）角色的第三方分享数据，以实现客户和技术支持、服务维护和其他操作。 Microsoft 将向其传输客户数据或支持数据的任何分包商都会与 Microsoft 签订书面协议，该协议的效力不低于[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中的数据保护条款。 与其分享客户数据或支持数据的所有第三方分包商都包括在[分包商列表](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors)中（参阅“分包商列表”）。 <br><br> 《联机服务条款》中还规定了 Microsoft 如何回应执法机构和第三方请求客户数据和支持数据的情况。 Microsoft 会尝试将执法机构或第三方的请求直接转达客户，除非法律禁止。 |   |
| 数据使用者权力 | 作为数据处理者，Microsoft 会向客户（即数据控制者）提供其数据使用者的个人数据，并赋予客户在数据使用者依据 GDPR 行使权力时满足其请求的能力。Microsoft 以符合产品功能和其数据处理者角色的方式实现此目标。如果 Microsoft 收到来自客户数据使用者的请求（请求依据 GDPR 行使其一项或多项权力），会将请求转发给数据控制者。<br><br>[Azure 数据使用者请求 GDPR 文档](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)介绍如何使用 Azure 中的功能支持数据使用者权力。 |   |
| 对与处理操作的目的相关的必要性和合理性的评估 | 这种评估将取决于数据控制者的处理需求和目的。<br><br>为了向数据控制者提供服务，Microsoft 需要进行某些处理，此类是必要且合理的。Microsoft 在 OST 中作此承诺。 | |
| 对数据使用者的权力和自由带来的风险的评估 | 使用 Microsoft Azure 对数据使用者的权力和自由带来的关键风险取决于数据控制者实施、配置和使用 Microsoft Azure 的方式和背景。<br><br> 然而，与其他所有服务一样，该服务中保存的个人数据可能存在未经授权的访问或意外泄漏的风险。OST 中说明了 Microsoft 用于应对此类风险的措施，下文将进一步详细讨论。 | |
| 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此 GDPR 的规定（将数据使用者和其他相关人员的合法权益考虑在内）。 | Microsoft 致力于帮助保护客户数据的安全。OST 中详细说明了 Microsoft 采取的安全措施。 <br><br> Microsoft 遵守严格的安全标准和行业领先的数据保护方法。Microsoft 不断改进其体系，以应对新威胁。有关云治理和隐私条例的详细信息，请参阅[信任中心的云治理和隐私](https://www.microsoft.com/trustcenter/guidance/ensure-compliance)页。 <br><br> Microsoft 采取合理且适当的技术和组织措施来保护其处理的个人数据。这些措施包括但不限于，内部隐私策略和条例、合同承诺以及国际和地区标准认证。有关详细信息，请参阅[信任中心的隐私标准页](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)。 <br><br> Microsoft 向客户提供重要、透明的安全和隐私材料，帮助 Microsoft 解释对个人数据的使用和处理。客户如有疑问，尽可联系 Microsoft。 <br><br> 此外，Microsoft 履行 GDPR 规定的适用于数据处理者的所有其他义务，包括但不限于数据保护影响评估和记录保存。 |  |

## <a name="learn-more"></a>了解详细信息

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
