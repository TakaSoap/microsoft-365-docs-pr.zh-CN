---
title: 管理支付方式
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: 了解如何在 Microsoft 365 管理中心中管理你的支付方式。
ms.openlocfilehash: c1679b8f525712681aaaad20334840da5e625ad6
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213064"
---
# <a name="manage-payment-methods"></a>管理支付方式

当您从 Microsoft 购买业务产品或服务时，您可以使用现有的付款方式，也可以添加一个新的付款方式。 您可以使用信用卡或借记卡或银行帐户支付购买的物品。

如果您的企业帐户有一个记帐配置文件，并且您是帐单档案文件所有者或帐单个人资料参与者，则可以使用信用卡或发票付款支持的计费配置文件来进行购买或支付帐单。 如果您是帐单发票管理者，则只能使用计费配置文件来支付帐单。 若要了解有关计费配置文件和角色的详细信息，请参阅[管理计费配置文件](manage-billing-profiles.md)。

如果你的企业帐户没有记帐配置文件，则任何全局或帐单管理员都可以管理和使用添加到企业帐户的任何银行帐户。 但是，您只能管理或使用您添加的信用卡。

> [!NOTE]
> 在某些国家或地区不提供用银行帐户付款的选项。
>
> 您必须使用与您的租户从同一国家/地区颁发的付款方式。

## <a name="add-a-payment-method"></a>添加付款方式

添加付款方法不会将任何订阅关联。 若要将单个订阅分配给付款方法，请参阅[更改单个订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。 若要将使用其他付款方式的所有订阅替换为新的，请参阅[替换付款方法](#replace-a-payment-method)。

1. 在 "管理中心" 中，转到 "**计费**  >  **帐单 & 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。
2. 选择“**添加付款方式**”。
3. 在“**付款方式**”页面上，从下拉菜单中选择一种付款方式。
4. 输入新卡或银行帐户的信息，然后选择 "**添加**"。

## <a name="update-payment-method-details"></a>更新付款方式详细信息

您可以更改现有付款方式的信用卡或借记卡、帐单地址或到期日期的名称。 但是，不能更改卡片或帐号。 如果帐户号码已更改，请将[其替换为其他付款方式](#replace-a-payment-method)，然后[删除旧的](#delete-a-payment-method)付款方式。

1. 在 "管理中心" 中，转到 "**计费**  >  **帐单 & 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。
2. 选择要更新的付款方式的行。 在右侧窗格中，选择 "**编辑**"。
3. 更新付款方式信息，包括信用卡或借记卡上的姓名、帐单地址或到期日期，然后选择 "**保存**"。

## <a name="replace-a-payment-method"></a>替换付款方法

当您替换付款方式时，会将其替换为使用相同付款方式的所有订阅和计费配置文件。 替换支付方式不会删除现有的付款方式。 您仍可以选择和使用其他订阅和计费配置文件。

若要更改单个订阅的付款方式，请参阅[更改单个订阅的支付方式](#change-a-payment-method-for-a-single-subscription)。

1. 在 "管理中心" 中，转到 "**计费**  >  **帐单 & 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。
2. 选择要替换的付款方法的行。 右侧窗格列出了所有帐单配置文件和使用所选付款方式的各个订阅。
3. 在右侧窗格中，选择 "**替换所有项目的付款方式**"。
4. 若要使用现有的付款方式，请从下拉列表中选择一个，然后选择 "**替换**"。
    > [!NOTE]
    > 如果你有与帐单配置文件关联的订阅，则只能使用信用卡或借记卡支付。 如果您在 "**付款方式**" 页上列出了银行帐户，则不能在下拉列表中进行选择。
5. 若要添加新的付款方式，请选择 "**添加支付方式**"。
6. 在 "**添加付款方法**" 窗格中，输入帐户信息，然后选择 "**保存**"。 您必须使用与您的租户来自同一国家/地区的付款方式。
7. 已在下拉列表中选择新的付款方式。 选择“**替换**”。

## <a name="change-a-payment-method-for-a-single-subscription"></a>更改单个订阅的付款方式

您可以更改用于支付单个订阅的付款方式。

1. 在管理中心中，转到 "**付费**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品</a>" 页面。
2. 在 "**订阅**" 选项卡上，选择要使用备用付款方式支付的订阅。 
3. 在 "**帐单**" 下，选择 "付款方法" 旁边的 "**编辑**"。
4. 在现有付款方法旁边，选择 "**更改**"。
5. 从下拉列表中，选择另一种付款方式，或选择添加付款方法。
6. 如果添加付款方法，请输入信用卡或帐户详细信息，然后选择 "**保存**"。
7. 确认所选的支付方式正确，然后选择 "**保存**"。

## <a name="delete-a-payment-method"></a>删除付款方法

您只能删除未附加到订阅或帐单配置文件的付款方式。 这适用于所有订阅（无论其状态如何）。

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>删除没有订阅或附加的计费配置文件的付款方式

如果付款方法不与任何订阅或计费配置文件关联，则可以立即将其删除。

1. 在 "管理中心" 中，转到 "**计费**  >  **帐单 & 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。
2. 找到要删除的付款方法，选择三个点，然后选择 "**删除**"。
3. 在右侧窗格的底部，选择 "**删除**"。

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>删除带有订阅或附加的计费配置文件的付款方式

如果向任何订阅或计费配置文件附加了付款方式，请首先将其替换为现有付款方式，或添加新的付款方式，然后删除旧的付款方式。

1. 在 "管理中心" 中，转到 "**计费**  >  **帐单 & 付款**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。
2. 选择要删除的付款方法所在的行。 右侧窗格中列出了使用该付款方式的现有订阅。
3. 在右侧窗格中，选择 "**删除**"。
4. 若要使用现有的付款方式，请从下拉列表中选择一个，然后选择 "**下一步**"，然后选择 "**删除**"。
    > [!NOTE]
    > 如果你有与付费配置文件关联的订阅，则只能使用信用卡支付。 如果您在 "**付款方式**" 页上列出了银行帐户，则不能在下拉列表中进行选择。
5. 若要添加新的付款方式，请选择 "**添加支付方式**"。
6. 选择要添加的付款方式类型，输入帐户信息，然后选择 "**保存**"。
7. 已在下拉列表中选择新的付款方式。 选择“**下一步**”。
8. 选择“删除”****。

## <a name="troubleshoot-payment-methods"></a>付款方式疑难解答

|**问题**|**疑难解答步骤**|
|:----------|:-----|
|**我收到一条错误消息，显示 "浏览器当前设置为阻止 cookie"。** |将浏览器设置为允许第三方 Cookie，然后重试。 |
|**已拒绝信用卡或借出卡。** |如果通过信用卡或借记卡付款，并且您的卡被拒绝，您会收到一封电子邮件，指出 Microsoft 无法处理付款。 请仔细检查卡片的详细信息 &mdash; 卡号、到期日期、卡片上的名称以及地址（包括城市、省/市/自治区和邮政编码） &mdash; 是否与在卡片和语句上显示的相同。 您可以使用 "订阅详细信息" 页的 "**计费**" 部分中的 "**结算余额**" 链接更新您的卡片信息并立即提交付款。 有关详细信息，请参阅[如果我的信用卡被拒绝且付款过期，该怎么办？](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  如果仍然看到"拒绝"消息，请联系你的银行。 您的卡可能不是活动的。 如果你最近在邮件中接收到包含更新到期日期的卡，请确保其已激活。 您的银行还可以告诉您您的卡片是否未被批准为在线、国际或重复事务。 |
|**我想要更新一个或多个银行帐号。** |您不能在现有的付款方式上更改卡号或帐号。 如果您的卡或帐号已更改，请[使用不同的付款方式替换它](#replace-a-payment-method)，将所有活动的订阅从付款方式移到新的付款方式，然后[删除旧的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。 |
|**我的帐户上仅有一个卡或银行帐户，我想将其删除。** |如果只有一种付款方式，则必须[将其替换为新的付款方式](#replace-a-payment-method)，然后才能将其删除。 |
|**我无法添加我的卡或银行帐户。**  |您必须使用与您的租户从同一国家/地区颁发的付款方式。 如果您在输入卡或银行帐户信息时遇到问题，可以[联系支持人员](../../admin/contact-support-for-business-products.md)。 |

## <a name="related-articles"></a>相关文章

[为你的业务订阅付费](pay-for-your-subscription.md)

[管理计费对象信息](manage-billing-profiles.md)

[更改付款频率](change-payment-frequency.md)