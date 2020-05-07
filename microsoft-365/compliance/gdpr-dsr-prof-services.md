---
title: Microsoft 支持和专业服务与 GDPR 和 CCPA 数据主体请求
description: 了解 Microsoft 支持和专业服务如何处理 GDPR 和 CCPA 数据主体请求。
keywords: 专业服务，Microsoft 365，Microsoft 365 教育版，Microsoft 365 文档，GDPR，CCPA
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
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e8bbdcc6140ffac298942f81899a4c872cc05584
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036307"
---
# <a name="microsoft-support-and-professional-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>Microsoft 支持和专业服务与 GDPR 和 CCPA 数据主体请求

## <a name="introduction-to-microsoft-professional-services"></a>Microsoft 专业服务简介

Microsoft 专业服务包括一个由技术架构师、工程师、顾问和支持专业人员组成的多元化团队，专门负责履行 Microsoft 让客户实现更多收获更多的使命。我们的专业服务团队总共包括 21000 多名顾问、数字顾问、顶级支持、工程师和销售专业人员，他们在 191 个国家/地区工作，支持 46 种不同语言，每个月管理数百万个服务活动，并通过本地、电话、网络、社区和自动化工具与客户和合作伙伴交互。此组织利用将我们与企业客户连接在一起的由合作伙伴、技术社区、工具、诊断以及渠道所构成的广泛网络，汇聚了整个 Microsoft 产品组合的广泛专业知识。

有关 Microsoft 专业服务的详细信息，请访问 [Microsoft 专业服务安全文档网页](https://www.microsoft.com/zh-CN/professionalservices/overview)。 Microsoft 专业服务非常重视《一般数据保护条例》(GDPR) 规定的义务。 本文档中的信息旨在回答客户有关 Microsoft 的支持和咨询服务如何响应和协助客户响应 GDPR 规定的数据主体请求 (DSR) 义务的问题。

### <a name="introduction-to-dsrs"></a>DSR 简介 

根据 GDPR，用户（在条例中称为“*数据主体*”）有权管理由雇主或其他类型的机构或组织（称为“*数据控制者*”或简称为“*控制者*”）收集的个人数据。根据 GDPR，个人数据的定义非常广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更正个人数据、限制个人数据处理和删除个人数据。数据主体为了对自己的个人数据执行操作而向控制者发出的正式请求，称为“*数据主体请求*”或“DSR”。此外，还规定代表控制者（称为“*数据处理者*”或简称为“*处理者*”）的公司有义务合理协助控制者履行 DSR。

同样，加州消费者隐私法案 (CCPA) 规定了加州消费者的隐私权和义务，包括与 GDPR 的数据主体权利类似的权利，例如删除、访问和接收（可移植性）其个人信息的权利。  CCPA 还就某些披露规定了在选择行使权限时防止歧视的保障措施，并就分类为“销售”的特定数据传输提出了“选择退出/选择加入”要求。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

本指南讨论如何查找、访问和操作驻留在 Microsoft IT 系统中的个人数据，收集这些数据可能是为了提供支持和其他专业服务。

在开发 DSR 响应的过程中，请务必让 Microsoft 客户了解支持和咨询数据是与 Online Services 中的客户数据或者他们或其他数据主体可能提供给 Microsoft 的其他数据分开的。为 Online Services、Microsoft 隐私面板或用于响应 DSR 的其他 Microsoft 系统提供的工具和流程不能用于响应由 Microsoft 支持或其他专业服务保留的个人数据的 DSR。

如下文所述，所有请求都必须通过支持代表提出。当前，没有自助服务工具能够让客户访问专业服务组织内的个人数据。

#### <a name="overview-of-the-processes-outlined-in-this-guide"></a>本指南中所述流程的概览

- **发现：** 使用搜索和发现工具更轻松地查找可能是 DSR 主体的客户的数据。 收集了潜在的响应性文档后，你便可以执行下列步骤中所述的一项或多项 DSR 操作来响应请求。 或者，你也可以确定请求是否不符合组织的 DSR 响应指南。
- **访问：** 检索驻留在 Microsoft 云中的个人数据，如果提出请求，还制作可供数据主体使用的个人数据副本。
- **纠正：** 进行更改或者对个人数据实施其他请求的操作（如果适用）。
- **限制：** 通过移除各种 Azure 服务的许可证，或者在可能的情况下关闭所需的服务，限制对个人数据的处理。 此外还可以从 Microsoft 云中删除数据，并将其保留在本地或其他位置。
- **删除：** 永久删除保存在 Microsoft 云中的个人数据。
- **导出/接收（可移植性）：** 向数据主体提供个人数据或个人信息的电子副本（采用机器可读格式）。 根据 CCPA 的定义，个人信息是指与已识别或可识别人员相关的任何信息。 个人的私人、公共或工作角色之间没有任何区别。 所定义的“个人信息”术语与 GDPR 下的“个人信息”大致相同。 但是，CCPA 还包括家人和家庭数据。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

### <a name="terminology"></a>术语

下面是本指南中 GDPR 术语的相关定义：

- **控制者：** 单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或具体提名条件。
- **个人数据和数据主体：** 身份已识别或可识别的自然人（“数据主体”）的任何相关信息；身份可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、联机标识符等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。
- **处理者：** 代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。

#### <a name="additional-terms-and-definitions-that-may-be-helpful-in-understanding-this-guide"></a>可能有助于了解本指南的其他术语和定义

- **支持和咨询数据：** 客户或代表客户在与 Microsoft 打交道期间向 Microsoft 提供的（或客户授权 Microsoft 从 Online Service 获取的）所有数据，包括所有文本、声音、视频、图像文件或软件，以获取支持或专业服务。 说明一下，这不包括 Microsoft 是数据控制者时收集的数据，包括客户联系人数据。
- **客户联系人：** 可能属于你与 Microsoft 业务关系一部分的个人数据，例如你的客户联系人信息内的个人数据。 这可能包括顶级合同服务经理 (CSM)、Online Service 的全局或 IT 管理员或类似角色的姓名、电子邮件或电话号码。
- **化名数据：** 当你为 Microsoft 的企业产品和服务使用 Microsoft 支持时，Microsoft 会生成一些链接到 Microsoft 数字标识符的信息，以提供支持。 这通常称为“化名数据”。虽然在不使用其他信息的情况下，此数据无法归于特定数据主体，但根据 GDPR 有关个人数据的广泛定义，其中一些数据可视为个人数据。 在专业服务内，履行或协助履行 DSR 的请求将始终自动包括处理化名数据。

### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南介绍了客户在使用 Microsoft 专业服务时可能遇到的 4 种应用场景。

- **针对与 Microsoft 打交道的客户联系人的 DSR：** 解释 Microsoft 如何响应来自客户联系人或 IT 管理员的行使其数据主体权利的请求。
- **针对与 Microsoft 打交道的最终用户的 DSR：** 解释 Microsoft 如何响应来自客户的员工或其他数据主体的行使其权利的请求。
- **针对客户提供数据的 DSR：商业支持：** 解释当客户收到来自其员工或其他数据主体的行使其权利的请求时如何从 Microsoft 获得帮助，并且数据主体的个人数据是在支持服务期间由 Microsoft 支持收集的。
- **针对客户提供数据的 DSR：包括 FastTrack 迁移服务在内的咨询服务：** 解释当客户收到来自其员工或其他数据主体的行使其权利的请求时如何从 Microsoft 获得帮助，并且数据主体的个人数据是在咨询服务期间由 Microsoft 收集的。

## <a name="dsr-for-a-customer-contact-engaging-microsoft"></a>针对与 Microsoft 打交道的客户联系人的 DSR

*Microsoft 如何响应来自客户联系人或 IT 管理员的行使其数据主体权利的请求。*

当客户与 Microsoft 合作以获得支持或咨询服务时，Microsoft 支持会自动收集或从帐户记录中检索客户联系人（例如顶级 CSM、全局管理员、IT 管理员）的个人数据。 这可能包括寻求支持或咨询服务的个人的姓名、电子邮件、电话和其他个人数据。

客户联系人的个人数据是 Microsoft 与客户的业务关系的一部分，且 Microsoft 是数据控制者。Microsoft 将响应来自客户联系人的有关其个人数据的 DSR，无论他们是否仍在组织内。

客户应了解 DSR 仅涵盖客户联系人的个人数据，而不会对服务过程中提交的任何客户数据（例如文字稿、案例描述、文件、工作成果）进行更改或删除，因为 Microsoft 是数据处理者。 此外，为了维护服务活动的历史记录，不会对已关闭的服务活动进行任何更改，包括是谁打开的服务活动的记录。

从客户联系人收到有关 DSR 的查询后，Microsoft 工作人员会将客户联系人转到[隐私响应中心](https://go.microsoft.com/fwlink/?LinkId=321116)。这是 Microsoft 处理隐私查询和投诉的主要输入机制。在收到查询后，隐私响应中心将确定这是商业客户还是组织帐户的一部分，并相应地做出响应。

为了保持客户的业务连续性，在确认替换联系人之前，Microsoft 也不会处理与服务活动相关联的 DSR。在确认新联系人后，Microsoft 将在打开的服务活动中将旧联系人换成新联系人。

客户可选择独立于此 DSR，对专业服务期间通过正常支持或咨询渠道收集的数据进行更改。例如，Microsoft 可以根据请求协助去除支持服务活动（请参考下文的 *“客户提供数据的 DSR 指南”* 部分）。

***仅用于说明目的的示例***

John 是一家 O365 企业客户的 IT 管理员，有一个打开的支持服务活动和两个已关闭的服务活动。现在，John 从公司离职，想要删除其个人数据。John 联系了隐私响应中心，确定他是 IT 管理员。John 得到通知，无法将他的姓名从以前（已关闭）的服务活动或从打开的服务活动内的任何数据中删除。但是，如果他确定了替换联系人，隐私响应中心将替换当前打开的票证上作为联系人的 John。John 告知 Microsoft，Jane 将替换他成为联系人，Microsoft 将在所有支持系统中做出更改。

## <a name="dsr-for-an-end-user-engaging-microsoft"></a>针对与 Microsoft 打交道的最终用户的 DSR

*Microsoft 如何响应来自客户的员工或其他数据主体的行使其权利的请求。*

如果客户的员工或其他数据主体联系 Microsoft，要对 Microsoft 作为数据处理者收集的数据行使其权利，则该数据主体将收到通知，他们需要联系作为数据控制者的 Microsoft 客户来行使这些权利。Microsoft 不会再执行进一步操作。

如果数据主体还联系 Microsoft，要针对 Microsoft 作为数据控制者的情况下（例如消费者支持、商业客户联系人）收集的数据行使权利，则 Microsoft 将单独响应个人针对该个人数据的数据主体权利请求。

***仅用于说明目的的示例***

Jane 是企业客户 Contoso 的一名员工，公司为其提供了 Dynamics 365 帐户。 她联系 Microsoft 要求删除她的所有数据，并被转到了隐私响应中心。 Jane 填写了请求表单。 隐私响应中心将她识别为企业最终用户，告诉她需要通过 Contoso 删除其企业数据。 他们还将她标识为 Microsoft X-Box 用户，并将其数据从其 Microsoft 消费者帐户删除。

## <a name="dsr-for-customer-provided-data-commercial-support"></a>针对客户提供数据的 DSR：商业支持

*当客户收到来自其员工或其他数据主体的行使其权限的请求时如何从 Microsoft 获得帮助，并且数据主体的个人数据是在支持服务期间由 Microsoft 支持收集的。*

当客户与 Microsoft 支持打交道时，Microsoft 从客户那里收集支持数据，用于解决任何需要支持服务活动的问题。 此支持数据包括 Microsoft 与客户的互动（例如聊天、电话、电子邮件、网络提交），以及客户发送给 Microsoft 或 Microsoft 经客户许可后从客户的 IT 环境或 Online Services 租户提取的用于解决支持问题的任何内容文件。 如果是顶级支持，还包括我们为了主动防止将来的问题而从你那里收集的任何数据。 但是，不包括客户联系人信息或 Microsoft 与客户之间业务关系的其他信息（例如帐单记录）。

对于所有支持数据，Microsoft 是数据处理者。因此，Microsoft 不会响应来自数据主体的针对他们与 Microsoft 商业客户联系时所提供的支持数据的直接请求。Microsoft 将与客户一起，通过正常支持渠道协助客户响应 DSR。

## <a name="step-1-discover"></a>步骤 1：发现

要在响应 DSR 时获得 Microsoft 的协助，第一步是查找作为 DSR 主体的个人数据。 这第一步 — 查找和检查所涉及的个人数据 — 将帮助客户确定 DSR 是否符合组织有关接受数据主体请求的策略。

客户找到数据后，客户可以执行特定操作以满足数据主体的请求。根据客户尝试执行的操作，将决定客户需要参与的发现级别。

在 Microsoft 协助客户解决 DSR 的情况下，这是一项业务功能，将通过你的常规支持渠道提出请求，而不是向隐私响应中心提出请求。

在发现相关数据和获取 Microsoft 协助的过程中，客户可使用若干选项来处理 DSR：

*选项 A – 跨 Microsoft 支持的客户 DSR*。在整个 Microsoft 的支持环境中将 DSR 应用于客户的所有支持数据。为此，客户只需要求 Microsoft 将 DSR 应用于收集的所有支持数据。

*选项 B — 特定客户服务活动。* 使用联机系统查看票证，然后识别包含相关个人数据的特定服务活动并报告给 Microsoft。 如果客户无法在所有服务活动（票证）之间进行搜索，Microsoft 会尝试提供协助以执行搜索。

***一旦识别到服务活动，可请求将 DSR 应用到记录的特定部分或 Microsoft 中与该服务活动相关的任何内容。***

若要识别特定服务活动，客户需在其所有服务活动中进行搜索。对于顶级客户，客户的合同服务经理（简称“CSM”）能够查看在合同日程安排下创建的所有支持请求 (SR)。对于非顶级客户，也有同等的支持服务活动门户，如通过 Online Services 支持区域。

![在 SMC 中搜索](../media/Prof-Serv-DSR-Doc-Final_image3.png)CSM 可以转到在 Support.Microsoft.Com（[https://support.microsoft.com/\<local语言代码\>/premier](https://support.microsoft.com/%3clocal%20language%20code%3e/premier)）（简称“SMC”）上的门户，选择并查看“支持请求”。 （请注意：在 URL 中，请替换为你的本地语言代码）。

>[!IMPORTANT]
>除了 SMC 中的案例历史记录之外，客户还在 Microsoft 在支持服务活动期间收集的文件中包含最终用户的个人数据（或者，在客户的许可下从 Online Service 中移除）。 相关示例包括，客户的 Exchange 邮箱、Azure 虚拟机或数据库的副本。 此个人数据可能有也可能没有在特定服务活动（即票证）的案例历史记录中提及。 若要查看该数据，客户联系人必须是特定的经过身份验证（通过 AAD 或 MSA）的支持请求联系人，并且已收到 Microsoft 支持数据传输和管理工具 (DTM) 中工作区的 URL。 客户联系人将有权访问这些文件，但不能进行全局查看，且 SMC 不会指出文件是否存在。

一旦客户在所选支持票证中识别出所有相关数据，客户可以决定是要请求删除与票证相关的所有内容，还是选择性地将 DSR 应用到个别个人数据实例。

## <a name="step-2-access"></a>步骤 2：访问

客户找到包含潜在响应 DSR 的个人数据的支持数据后，由客户决定在响应中包含哪些个人数据。例如，客户可以选择移除有关其他数据主体的个人数据和任何机密信息。

对 DSR 的响应可能包括实际文档、经过适当修订的版本或者客户认为适合共享的部分的屏幕截图的副本。对于这些对访问请求的每个响应，客户都需要检索包含响应数据的文档或其他项目的副本。

对最终用户的个人数据的访问可能在各种类型的内容文档中有提及和标记。 由于客户可能会访问服务活动票证和内容，因此他们无需 Microsoft 的进一步帮助即可提供个人数据摘要。

在极少数情况下，客户可能需要获得 Microsoft 代表与客户代表之间的支持互动数据（例如电子邮件、电话录音文字稿；聊天文字稿）的副本。 在要求的范围内，Microsoft 可能会根据需要、敏感度和难度，提供这些文字稿的副本。

## <a name="step-3-rectify"></a>步骤 3：纠正

如果数据主体要求客户纠正驻留在其组织的支持数据中的个人数据，客户需要确定是否可以接受请求。如果客户选择接受请求，则客户会请求 Microsoft 进行更改。Microsoft 可能会纠正数据，或者将客户数据从支持系统中删除并请求客户以更正后的格式重新提交到 Microsoft。

## <a name="step-4-restrict"></a>步骤 4：限制

客户可随时关闭服务活动，或联系 Microsoft 并请求关闭服务活动。 服务活动关闭后，将无法再执行任何操作。

为了提供额外的保证，客户可以联系 Microsoft 并请求在服务活动票证系统放置备注，指出未经客户许可，不得因任何原因重新打开该案例。

注意：还会基于数据、服务和系统的敏感度，根据保留和删除日程表删除服务活动（票证）。 如果客户请求数据副本，他们应确保在删除之前已先提取数据。

## <a name="step-5-delete"></a>步骤 5：删除

从组织的支持数据移除个人数据的“擦除权限”是 GDPR 中的一项关键保护措施。 移除个人数据包括删除整个服务活动、文档或文件，或删除服务活动、文档或文件中的特定数据。

在客户调查或准备删除个人数据以响应 DSR 时，需要了解以下有关 Microsoft 支持如何进行删除的一些重要事项。

在 Microsoft 的所有数据都必须应用保留和删除策略，因风险和其他因素不同而有所不同。

如果客户请求在所有支持系统中普遍删除数据主体的个人数据，则可通过你的 TAM 或通过在 SMC 或同等系统中填写支持申请 (SR) 来完成。你*必须*指出该请求是根据 GDPR 来协助处理 DSR。

*选项 A - 跨 Microsoft 支持的客户 DSR*。 对于跨系统的 DSR，客户必须提供 Microsoft 识别所需数据需要的个人数据（例如电子邮件地址、电话号码）。 Microsoft 不会关联或研究记录，而是仅根据客户提供的标识符直接进行搜索。 找到数据后，Microsoft 将删除所有服务活动和所有关联数据。

> 重要说明：这可能会导致对客户组织非常重要的历史记录发生丢失。

*选项 B — 特定客户服务活动*。 对于客户已识别并且想要删除的特定服务活动，不要从 SMC 删除票证。 这会导致个人数据遗留在日志和下游系统中，从而可能无法在所需时间范围内删除。 转为识别票证或必须删除的票证中的个人资料，并联系 Microsoft 支持协助你删除该数据。

### <a name="microsoft-support-data-transfer-and-management-tool-dtm-instructions"></a>Microsoft 支持数据传输和管理工具 (DTM) 说明

对于所有这些搜索，由于文件内容的潜在敏感性，Microsoft 不会在整个 DTM 中进行搜索。但是，如果客户希望这么做，Microsoft 将删除包含在 DTM 中的与客户帐户相关联的所有文件。由于可能会对客户产生严重影响，因此 Microsoft 要求客户单独提出申请，指定删除 DTM 文件。

- 对于打开的案例，客户联系人可以转到 DTM，然后删除文件。
- 对于关闭少于 90 天的案例，必须向 TAM 或者在 SR 中提出请求，要求删除文件。
- 对于关闭超过 90 天的案例，文件已被自动删除。
- 即使个人数据仅位于已删除的文件内，客户仍然必须让 Microsoft 在所有系统中检查是否存在该个人数据，因为有些数据可能已在提供支持期间从 DTM 中移除。

## <a name="step-6-export"></a>步骤 6：导出

“数据移植权限”允许数据主体请求电子格式的个人数据副本，并请求你的组织将其传送给另一个控制者。对于支持数据，Microsoft 所拥有的任何有用数据都可能采用服务活动信息或文件的形式，以便返回给你进行再次通信或上传给另一个控制者。

注意：导出的数据不能包括 Microsoft 的知识产权或任何可能会危及服务安全性或稳定性的数据。

***仅用于说明目的的示例***

John 是企业客户 Contoso 的一名顶级 CSM，该客户为其员工电子邮件使用 O365，并使用 Azure 托管 Contoso SQL 数据库。Contoso 有多个打开和已关闭的票证。最近，Microsoft 支持在 Contoso 的许可下将 SQL 数据库的副本移到了 DTM 中，以进行支持和疑难解答。

John 从 Jane 那里收到了一个 DSR，要求删除她的所有数据。John 进入 SMC，并在所有服务活动中进行搜索以识别 Jane 有电子邮件帐户问题，因此在两个票证中按姓名和电子邮件地址进行了引用。他联系了 TAM，向 TAM 提供了 Jane 的姓名和电子邮件地址作为标识符，并请求删除这两个票证，以及从这两个票证生成的所有下游数据。

他还怀疑自己在与支持人员的聊天对话中提到了 Jane，所以他请求删除该聊天日志。

他还知道 Jane 的个人数据位于 SQL 数据库中。由于 SQL 虚拟机移到 DTM 的时间少于 90 天，因此他单独要求其 TAM 协助他将数据库立即从 DTM 中删除。

最后，由于他知道数据可能已在提供支持时从 DTM 文件中删除，因此他要求 Microsoft 在所有 IT 系统中执行检查，查看 SQL 数据库中是否存在 Jane 的个人数据。

Microsoft 支持将执行所有这些删除操作，基于客户请求，TAM 还提供已删除所需数据的鉴证声明。

## <a name="dsr-guide-for-customer-provided-data-in-consulting-services-including-migration-services"></a>咨询服务（包括迁移服务在内）中针对客户提供数据的 DSR 指南

*当客户收到来自其员工或其他数据主体的行使其权利的请求时如何从 Microsoft 获得帮助，并且数据主体的个人数据是在咨询服务期间由 Microsoft 收集的。*

## <a name="microsoft-consulting-services"></a>Microsoft 咨询服务

针对适用 Microsoft 专业版服务数据保护附录 (<https://aka.ms/professionalservicesdpa>) 的、已订立合同的 Microsoft 咨询服务的服务活动。

Microsoft 是与服务活动团队合作的客户联系人的数据控制者。这些人应联系[隐私响应中心](https://go.microsoft.com/fwlink/?LinkId=321116)以行使数据主体权利。

Microsoft 是位于咨询服务活动期间提供的数据内的 DSR 的数据处理者。客户应联系服务活动经理制定计划，以基于收集的数据和所提供的具体咨询服务类型协助响应 DSR。根据你的请求在 Microsoft 咨询服务活动中所构成的典型努力程度，可能还会需要额外的工作订单。此外，根据咨询服务活动的类型，将在每个咨询服务活动之后，在规定的时间范围内删除个人数据。客户可以请求尽快删除数据，并请求提供删除鉴证。

## <a name="microsoft-fasttrack-services"></a>Microsoft FastTrack 服务

[Microsoft FastTrack](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Ffasttrack.microsoft.com%2Fabout&data=02%7C01%7C%7Cd0521d8739c841df674508d596834585%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636580412901207944&sdata=PO5eh56pm9IYk5Y%2Ff%2F31e%2BRVPmrC2Qi%2FCsw1NphR8gY%3D&reserved=0) 为组织提供 IT 咨询服务，以帮助他们载入并使用 Microsoft 365、Azure 和 Dynamics 365 等 Microsoft 云服务。

Microsoft 是与 FastTrack 团队合作的客户联系人的数据控制者。如果客户联系人希望访问、修改联系人信息或将其从 Microsoft FastTrack 记录中删除，客户可以让数据主体将请求直接发送到 Office 365 FastTrack GDPR 请求收件箱 \<<o365ftgdpr@microsoft.com>\>。

对于 FastTrack 迁移服务，Microsoft 是数据处理者。根据我们的 FastTrack 附加隐私披露声明，迁移过程中的所有数据都被视为“迁移数据”。如果需要在组织参与 FastTrack 迁移项目时执行 DSR，则需要特别注意。
  
如果需要在用户数据正通过 FastTrack 迁移系统进行处理时处理任何访问、纠正或导出 DSR 请求，客户需自行通过存储用户数据的现有源系统来完成此 DSR。 用户迁移完成且数据已迁移到目标 Microsoft 云服务后，即可应用由 Microsoft 提供的有关客户如何使用 Microsoft 产品、服务和管理工具来查找个人数据并对其执行操作以响应数据主体请求的指南。 若要查看此指南，请参阅[针对 GDPR 的数据主体请求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests)。 

如果需要在组织参与正在进行的 FastTrack 迁移项目时响应 DSR 删除请求删除用户帐户，则应注意，迁移系统可能会在用户迁移完成后的一段时间内保留用户迁移数据的副本，且删除用户帐户的操作将不会自动删除存储在 FastTrack 迁移系统中的此类用户迁移数据。如果希望 Microsoft FastTrack 团队删除用户迁移数据，可以[提交请求](https://go.microsoft.com/fwlink/?linkid=874544)。在正常的业务过程中，Microsoft FastTrack 在组织迁移完成后即会删除所有数据副本。

## <a name="other-consulting-services"></a>其他咨询服务

通过 Microsoft 收到其他专业服务的客户应通过服务活动团队来履行所有 GDPR 要求。如果服务活动团队无法提供有关 GDPR DSR 履行的明确指导，客户可联系[隐私响应中心](https://go.microsoft.com/fwlink/?LinkId=321116)寻求帮助。
