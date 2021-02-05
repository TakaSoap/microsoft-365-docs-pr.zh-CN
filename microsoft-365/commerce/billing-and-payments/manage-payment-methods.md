---
title: 管理支付方式
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 管理中心管理付款方式。
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114845"
---
# <a name="manage-payment-methods"></a>管理支付方式

::: moniker range="o365-21vianet"
> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。
::: moniker-end

当你从 Microsoft 购买业务产品或服务时，可以使用现有的付款方式，或添加新的付款方式。 可以使用信用卡或借记卡或银行帐户支付所购买内容。

如果你的业务帐户具有计费配置文件，并且你是计费配置文件所有者或帐单配置文件参与者，可以使用信用卡或发票付款支持的计费配置文件进行购买或支付帐单。 如果你是帐单发票管理员，则只能使用计费配置文件支付帐单。 若要了解有关计费配置文件和角色的信息，请参阅["管理计费配置文件"。](manage-billing-profiles.md)

如果你的业务帐户没有帐单配置文件，任何全局管理员或帐单管理员可以管理和使用添加到业务帐户的任何银行帐户。 但是，只能管理或使用添加的信用卡。

> [!NOTE]
> 使用银行帐户付款的选项在一些国家和地区不可用。
>
> 必须使用从与租户相同的国家/地区颁发的付款方式。

## <a name="before-you-begin"></a>准备工作

你必须是全局管理员或帐单管理员才能执行本文中的任务。 有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="add-a-payment-method"></a>添加付款方式

添加付款方式不会关联任何订阅。 若要将单个订阅分配给付款方式，请参阅更改单个 [订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。 若要将使用另一种付款方式的所有订阅替换为新付款方式，请参阅["替换付款方式"。](#replace-a-payment-method)

1. 在管理中心，转到“**账单**” > “**账单与付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。
2. 选择“**添加付款方式**”。
3. 在“**付款方式**”页面上，从下拉菜单中选择一种付款方式。
4. 输入新卡或新银行帐户的信息，然后选择"添加 **"。**

## <a name="update-payment-method-details"></a>更新付款方式详细信息

您可以更改现有付款方式的信用卡或借记卡名称、帐单地址或到期日期。 但是，你无法更改卡号或帐号。 如果帐号已更改， [请将其](#replace-a-payment-method)替换为其他付款方式，然后 [删除旧付款方式](#delete-a-payment-method)。

1. 在管理中心，转到“**账单**” > “**账单与付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。
2. 选择要更新的付款方式行。 在右窗格中，选择“**编辑**”。
3. 更新付款方式信息，包括信用卡或借记卡上的姓名、帐单邮寄地址或到期日期，然后选择“**保存**”。

## <a name="replace-a-payment-method"></a>替换付款方式

替换付款方式时，可将其替换为使用相同付款方式的所有订阅和计费配置文件。 替换付款方式不会删除现有的付款方式。 它仍然可供你选择并用于其他订阅和计费配置文件。

若要更改单个订阅的付款方式，请参阅更改单个 [订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。

1. 在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。
2. 选择要替换的付款方式行。 右窗格列出了使用所选付款方式的所有计费对象信息和单个订阅。
3. 在右窗格中，选择“**所有商品的替换付款方式**”。
4. 若要使用现有付款方式，请从下拉列表中选择一个，然后选择“**替换**”。
    > [!NOTE]
    > 如果你有与计费对象信息相关联的订阅，则只能使用信用卡或借记卡支付。 如果“**付款方式**”页面上列出了银行帐户，则不能在下拉列表中选择它们。
5. 若要添加新的付款方式，请选择“**添加付款方式**”。
6. 在“**添加付款方式**”窗格中，输入帐户信息，然后选择“**保存**”。 你必须使用租户所在国家/地区的付款方式。
7. 已在下拉列表中选择新的付款方式。 选择“**替换**”。

## <a name="change-a-payment-method-for-a-single-subscription"></a>更改单个订阅的付款方式

你可以更改用于支付单个订阅的付款方式。

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在 **"产品** "选项卡上，找到想要通过备用付款方式付费的订阅。
3. 选择 **三个点 (** 操作) ，然后选择 **"替换付款方式"。**
4. 在 **"替换付款方式"** 窗格中，从下拉列表中选择备用付款方式，或选择添加付款方式。
5. 如果添加付款方式，请输入卡或帐户详细信息，然后选择"**保存"。**
6. 验证所选付款方式是否正确，然后选择"替换 **"。**

## <a name="delete-a-payment-method"></a>删除付款方式

只能删除未附加到订阅或计费配置文件的付款方式。 这适用于所有订阅，无论其状态如何。

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>删除未附加订阅或计费配置文件的付款方式

如果付款方式未与任何订阅或计费配置文件关联，您可以立即将其删除。

1. 在管理中心，转到“**账单**” > “**账单与付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。
2. 找到要删除的付款方式，选择三个点，然后选择"删除 **"。**
3. 在右窗格的底部，选择"删除 **"。**

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>删除附加了订阅或计费配置文件的付款方式

如果付款方式附加到任何订阅或计费配置文件，请首先将其替换为现有付款方式，或添加新付款方式，然后删除旧的付款方式。

1. 在管理中心，转到“**账单**” > “**账单与付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。
2. 选择要删除的付款方式的行。 右窗格列出了使用该付款方式的现有订阅。
3. 在右侧窗格中，选择"删除 **"。**
4. 若要使用现有付款方式，请从下拉列表中选择一种付款方式，选择"下一步"，然后选择"**删除"。**
    > [!NOTE]
    > 如果你有与计费配置文件相关联的订阅，则只能使用信用卡支付这些订阅。 如果在"付款方式"页上列出了银行帐户，则它们不能从下拉列表中选择。
5. 若要添加新的付款方式，请选择“**添加付款方式**”。
6. 选择要添加的付款方式的类型，输入帐户信息，然后选择"保存 **"。**
7. 已在下拉列表中选择新的付款方式。 选择 **下一步**。
8. 选择“删除”。

## <a name="troubleshoot-payment-methods"></a>付款方式疑难解答

| 问题 | 故障排除步骤 |
|:----------|:-----|
|**我收到一条错误消息，指出"浏览器当前已设置为阻止 Cookie"。** |将浏览器设置为允许第三方 Cookie，然后重试。 |
|**我的信用卡或借记卡被拒绝。** |如果你通过信用卡或借记卡付款，而你的卡被拒绝，你将收到一封电子邮件，指出 Microsoft 无法处理该付款。 仔细检查卡片详细信息卡号、到期日期、卡上的名称和地址（包括城市、省/市/市/县和邮政编码）是否与卡片和您的语句上完全相同 &mdash; &mdash; 。 可以使用订阅详细信息页面的"计费"部分中的"结算余额"链接更新卡信息并立即提交付款。 有关详细信息，请参阅如果我有未结 [余额，如何？](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  如果仍然看到"拒绝"消息，请联系你的银行。 你的卡片可能未处于活动状态。 如果最近在邮件中收到过期日期更新的卡片，请确保已激活。 你的银行还可以告知你你的卡是否未获准进行联机、国际或定期交易。 |
|**我想要更新卡号或银行帐号。** |不能更改现有付款方式上的卡号或帐号。 如果你的卡号或帐号已更改，请[](#replace-a-payment-method)将其替换为其他付款方式，该方法会将所有活动订阅从付款方式移动到新付款方式，然后删除[旧的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。 |
|**我的帐户上只有一个卡或银行帐户，我想删除它。** |如果您只有一种付款方式，则必须 [将其](#replace-a-payment-method) 替换为新的付款方式，然后才能将其删除。 |
|**我无法添加我的卡或银行帐户。**  |必须使用从与租户相同的国家/地区颁发的付款方式。 如果你在输入卡或银行帐户信息时遇到问题，可以 [联系支持人员](../../admin/contact-support-for-business-products.md)。 |

## <a name="related-content"></a>相关内容

[支付你的商业订阅 (](pay-for-your-subscription.md) 文章) \
[管理帐单配置文件 (](manage-billing-profiles.md) 文章) \
[更改你的计费频率 (](change-payment-frequency.md) 文章) 
