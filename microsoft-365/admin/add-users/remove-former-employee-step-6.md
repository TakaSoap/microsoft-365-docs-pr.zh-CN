---
title: 步骤 6 - 从以前的员工删除和删除 Microsoft 365 许可证
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 按照以下步骤从以前的员工删除 Microsoft 365 许可证。
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244164"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>步骤 6 - 从以前的员工删除 Microsoft 365 许可证

如果某人离开组织后不想支付许可证费用，则需要删除其 Microsoft 365 许可证，然后从订阅中删除它。 如果不删除许可证，可以将许可证分配给其他用户。
  
删除许可证后，该用户的所有数据将保留 30 天。 可[访问](get-access-to-and-back-up-a-former-user-s-data.md)该数据，或在用户返回时[还原](restore-user.md)该帐户。 30 天后，用户的所有数据 (存储在 SharePoint Online) 上的文档除外）将从 Microsoft 365 中永久删除，并且无法恢复。

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要阻止的员工的姓名，然后选择"许可证 **和应用"** 选项卡。
3. 清除要删除 (许可证) 复选框，然后选择"保存 **更改"。**

**若要在聘用** 其他人之前减少你支付的许可证数量，请执行以下步骤：

1. 在管理中心，转到" **帐单** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">""产品"页面</a> ，然后选择" **产品"** 选项卡。
2. 选择要从中删除许可证的订阅。
3. 在详细信息页面上，选择删除 **许可证**。
4. 在"**删除许可证"** 窗格中的"新数量"下的"许可证总数"框中，输入此订阅的许可证总数。 例如，如果你有 25 个许可证，并且想要删除其中一个许可证，请输入 24。
5. 选择“**保存**”。

向 [企业添加其他人](add-users.md) 时，系统会提示你同时购买许可证，只需一个步骤！

有关管理 Microsoft 365 商业版用户许可证的信息，请参阅在 [Microsoft 365](../manage/assign-licenses-to-users.md)商业版 中向用户分配许可证和取消分配 [Microsoft 365](../manage/remove-licenses-from-users.md)商业版中的用户许可证。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已删除的员工帐户如何影响 Skype for Business

从 Office 365 删除用户许可证时，与该用户相关联的 PSTN 呼叫号码将被释放。可将其分配给其他用户。
  
如果用户属于队列组，则他不再是呼叫队列代理的可行目标。因此，我们还建议将该用户从与呼叫队列相关联的组中删除。

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>设置呼叫转发给组织人员

如果需要为离职员工的电话号码设置呼叫转发，呼叫策略下的呼叫转发设置可以设置转发，其中传入呼叫可以转发给其他用户，也可以同时呼叫其他人。 有关详细信息，请参阅 [Microsoft Teams 中的通话策略](/microsoftteams/teams-calling-policy)。
