---
title: 了解建议工作流
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: presharm, jmueller
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: 了解帮助你购买 Microsoft 产品和服务的建议。
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: 0a067049f278daee3c6e55aba00a81dcb2746c3c
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754773"
---
# <a name="understand-the-proposal-workflow"></a>了解建议工作流

建议是 Microsoft 为贵组织购买 Microsoft 产品和服务的正式优惠。 您可以直接与 Microsoft 代表合作，以确定建议的特定产品、服务和条款。

Microsoft 代表起草一个包含您和您的代表讨论的项目的建议。 代表向您发送一封包含指向建议网站的链接的电子邮件。 该网站包含专门为您和您的组织准备的建议。

收到通知电子邮件后，按照指向建议网站的链接操作。 登录网站后，可以启动建议审阅过程。

## <a name="prerequisites-for-buying-items-with-a-proposal"></a>购买具有建议的项目的先决条件

在购买建议项目之前，你必须具有计费帐户和与 Microsoft 的协议。

### <a name="billing-account"></a>计费帐户

使用计费帐户管理帐户设置、发票、计费配置文件以及产品和服务。 如果你还没有计费帐户，Microsoft 代表会创建一个。 否则，他们使用组织的现有计费帐户，只要你有权使用该计费帐户。

计费帐户权限由计费帐户所有者管理。 全局管理员可以将自己分配给计费帐户所有者角色，然后让其他人成为计费帐户所有者。

有关计费帐户详细信息，请参阅 [管理计费帐户](manage-billing-accounts.md)。

### <a name="microsoft-customer-agreement"></a>Microsoft 客户协议

Microsoft 客户协议 (MCA) 允许组织购买 Microsoft 产品和服务。 有关详细信息，请参阅 [Microsoft 客户协议](https://www.microsoft.com/en-us/Licensing/how-to-buy/microsoft-customer-agreement)。

## <a name="permissions-needed-to-sign-an-agreement-or-pay-for-items"></a>签署协议或支付项目费用所需的权限

如果在计费帐户中没有分配的角色，则当您查看建议时，会分配有基本读者角色。 此角色允许您查看建议，但不对建议执行任何操作。 必须先分配有计费帐户所有者或计费帐户参与者角色，然后才能签署协议或购买产品和服务。 你的计费帐户所有者可以将此角色分配给你。

有关计费帐户角色详细信息，请参阅 [了解对计费帐户的访问权限](manage-billing-accounts.md#understand-access-to-billing-accounts)。

如果这是一个新的计费帐户，并且没有人接受协议，则会自动成为计费帐户所有者，但你必须：

- 是建议中指定的人员， **还是**
- 已是[Azure Active Directory全局](/azure/active-directory/roles/permissions-reference#global-administrator)管理员

## <a name="what-is-the-overall-workflow"></a>什么是总体工作流？

总体建议工作流如下所示：

- 你的 Microsoft 代表创建一个建议，并通过电子邮件向您发送一个链接。
- 您可以使用链接转到建议登录页。
- 查看组织的信息。
- 您查看建议、根据需要接受 MCA 并完成签出过程。
  > [!IMPORTANT]
  > 你必须有权代表你的组织对 MCA 进行签名。 如果您没有该权限，则执行该步骤的人必须执行此步骤。
- 签出完成后，会提供其他链接来设置产品和服务。

## <a name="proposal-terms"></a>建议术语

下表包含您的建议和建议网站上出现的术语和定义。

| **术语** | **定义** |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 计费帐户 | 用于管理帐户设置、发票、付款方式和产品的帐户。 |
| 计费配置文件 | 有关你的组织的信息，可让你自定义发票中包含哪些项目，以及如何支付发票费用。 计费配置文件包括计费帐户名称、用于特定计费配置文件的付款方式、联系人信息、发票设置以及允许更改计费配置文件、支付帐单以及购买产品和服务的权限。 |
| 现有协议 | 组织已与 Microsoft 签订的任何协议。 其中可能包括（但不限于）企业协议 Microsoft 产品&服务协议或 Microsoft 客户协议。 |
| Microsoft 客户协议 (MCA)  | 概述组织与 Microsoft 之间的帐户的条款和条件的协议。 |
| Microsoft 代表 | 为你和组织准备建议的授权 Microsoft 代表。 |
| 组织 | 使用 Microsoft 产品、技术或服务的法律实体。 |
| 准备者 | 准备建议的 Microsoft 代表的电子邮件地址。 |
| 补充条款 | MCA 的修正，其中包含特定于您的组织的术语。 若要接受补充条款，必须使用 DocuSign 记录电子签名。 |

## <a name="step-1-review-organization-information"></a>步骤 1：查看组织信息

登录后，首先要查看组织的信息。

### <a name="your-organization"></a>你的组织

" **你的组织** "部分显示与之关联的计费帐户。 计费帐户信息从现有计费帐户提取，或由 Microsoft 代表创建。 如果您的组织是另一个组织的关联，则还会看到包含该组织的名称和地址的潜在客户组织部分。

如果这是你的组织第一次与 Microsoft 建立商业关系，并且你尚未签署 MCA，如果贵组织或潜在客户组织下的信息不正确，请联系代表来进行更改。 接受 MCA 后，可以在"帐单"页面上查看和更改组织的地址和联系人信息，Microsoft 365 管理中心。 [](https://go.microsoft.com/fwlink/p/?linkid=2084771) 如果组织名称发生更改，请打开服务请求以进行更新。 [了解如何打开服务请求。](../business-video/get-help-support.md)

### <a name="your-information"></a>你的信息

如果你是新客户，请在"你的信息"下输入你的姓名、电子邮件地址和电话号码，然后选择"保存 **"。** 如果你是现有客户，请验证你的信息是否正确。 若要进行任何更正，请选择"**编辑"，** 进行必要的更改，然后选择"保存 **"。**

准备就绪后，选择" **继续"** 以移动到下一步。

## <a name="step-2-review-proposal"></a>步骤 2：审阅建议

该建议包含您与 Microsoft 代表讨论的项目的详细信息。 你可以转发包含建议链接的电子邮件，以与组织的其他利益干系人共享它。 使用该链接的其他人对建议具有只读视图。

如果要在审阅后对建议做出任何更改，请与 Microsoft 代表联系。

### <a name="proposal-contents"></a>建议内容

建议包含以下信息：

| 节 | 说明 |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 组织名称 | 已准备建议的组织的名称。 |
| 有效到日期 | 建议产品/服务到期的日期。 如果错过此到期日期，请与 Microsoft 代表联系，让他们知道您仍对建议感兴趣。 |
| 货币 | 用于计算建议中项目成本的货币。 |
| 准备 | 请求建议的人的帐单帐户名称、地址、联系人电子邮件地址和电话号码。 |
| 准备者 | 准备建议的 Microsoft 代表的电子邮件地址。 |
| 摘要 | 显示与建议关联的小计。 如有必要，还将显示用于计算 (的) 汇率的汇率。 |
| 建议行项目 | 本节包含建议中包含的所有项目的数量、单价和小计。 |
| 后续步骤 | 本节指示必须执行的必要操作。 |

若要对 MCA 进行签名，请选择"下一步 **"下的按钮**。 如果必须签署补充条款，一个链接将你指向 DocuSign 站点，你将在这里按照步骤对文档进行签名。

在签署任何必要的协议或补充条款后，选择 **"转到"以签出**。

## <a name="step-3-checkout"></a>步骤 3：签出

签出页面包含以下部分：

### <a name="sold-to"></a>售达地址

此部分显示用于建议的计费帐户。 如果需要更改任何信息，请选择"编辑 **"** 链接。 您还可以使用"编辑 **"** 链接添加组织的税务 ID。 税务 ID 必须与"售达"部分中列出的 **国家/地区** 相关。 如果你有免税，则必须打开支持票证以请求免税状态。

若要了解有关税单以及如何申请免税身份的信息，请参阅税务 [信息](billing-and-payments/tax-information.md)。

### <a name="billed-to"></a>计费到

此部分显示用于确定发票中包含哪些项目的计费配置文件，以及如何支付发票。 每个计费周期，你将收到每个计费配置文件的单独发票。 使用支票或数据传输或 Azure 预付款支付发票费用。 如果你还没有计费配置文件，Microsoft 代表会创建一个。 在结帐期间，可以选择其他计费配置文件（如果有）、更改计费配置文件的名称或添加 P.O。 number。 还可以创建新的计费配置文件。

有关计费配置文件的信息，请参阅管理 [计费配置文件](billing-and-payments/manage-billing-profiles.md)。

### <a name="proposal-items-in-this-order"></a>按此顺序的建议项

本节显示建议中包含的所有项目的列表。 该列表可以包括以下一个或多个类别：

- **补充条款** MCA 的任何修正列表，其中包含组织的条款。 例如，此列表可能包括 HIPAA 或 GDPR 条款。
- **现在购买** 在建议接受工作流结束时签出期间支付的项目列表。
- **应用于 (费用折扣)** 作为建议一部分收到的折扣列表。
- **包含** 包含在建议包中的项目列表，无需额外付费。 这些项目中的某些项目将来可能具有与其相关的成本。

### <a name="summary"></a>摘要

此部分显示要支付的项数、小计、估计税款和订单总额。

若要下订单，请选择下 **订单** 或 **接受协议 &amp; 下订单**。

下订单后，您将收到一条确认消息，确认将采取下一步操作。 如果你购买了 Azure 计划，下一步是在 Azure 门户中设置计费帐户。

## <a name="step-4-set-up-your-new-billing-account-azure-customers-only"></a>步骤 4：仅向 Azure (设置新的) 

如果你是一名新客户，并且已购买 Azure 产品作为建议的一部分，下一步是设置新的计费帐户。 若要了解如何，请参阅 [为 Microsoft 客户协议设置计费帐户](/azure/cost-management-billing/manage/mca-setup-account)。

如果你是具有 企业协议 的现有 Azure 客户，并且你是第一次对 MCA 进行签名，下一步是了解协议之间的更改，以及如何使用新的计费帐户完成任务。 若要了解更多信息，请参阅[完成企业协议客户协议的计费帐户中的任务](/azure/cost-management-billing/manage/mca-enterprise-operations)。

## <a name="understand-invoicing"></a>了解发票

签出并完成订单后，初始发票在 24-48 小时内发送。 此后，你将在每月的 5 号左右收到发票。 每月发票包含上个月的费用。 如果你的帐户有任何信用额度，将从你的计费配置文件的货币信用中减去这些信用，并应用于你的发票余额。 应用信用后的剩余余额是余额到期。 你有 30 天从计费日期开始支付发票。

发票的 PDF 副本中包含用于在何处发送支票或数据传输的付款说明。 若要查看或下载发票，请参阅 [查看帐单或发票](billing-and-payments/view-your-bill-or-invoice.md)。
