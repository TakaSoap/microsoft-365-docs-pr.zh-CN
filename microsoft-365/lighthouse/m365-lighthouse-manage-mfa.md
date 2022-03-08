---
title: 管理多重身份验证
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何管理多重身份验证。
ms.openlocfilehash: 5ab430e464fb2d20f9a911818f9fd6cb077d849e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326127"
---
# <a name="manage-multifactor-authentication"></a>管理多重身份验证

Azure Active Directory (Azure AD) MFA (多重身份验证) 保护对数据和应用程序的访问，从而通过使用第二种形式的身份验证提供另一层安全性。 "多重身份验证"选项卡提供有关跨租户的 MFA 启用状态的详细信息。 选择列表中的任意租户以查看该租户的更多详细信息，包括已配置哪些需要 MFA 的条件访问策略，以及哪些用户尚未注册 MFA。

对于中小型商业客户 (SMB) ，Microsoft 建议至少启用安全默认值。[](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 对于更复杂的方案，可以使用条件 [访问](/azure/active-directory/conditional-access/overview) 来配置特定策略。

## <a name="before-you-begin"></a>准备工作

必须先满足以下条件，租户才能显示在列表中：

- 客户租户必须具有每个用户Azure AD Premium许可证。 有关哪些许可证支持 MFA 的信息，请参阅适用于多重Azure AD[身份验证的功能和许可证](/azure/active-directory/authentication/concept-mfa-licensing)。

- 客户租户必须处于活动状态Microsoft 365 Lighthouse。 若要了解如何确定租户是否处于活动状态，请参阅Microsoft 365 Lighthouse[列表概述](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview)。

## <a name="enable-mfa-for-a-tenant"></a>为租户启用 MFA

1. In the left navigation pane in Lighthouse， select **Users**.

2. 选择 **"多重身份验证"** 选项卡。

3. 从租户列表中，选择一个租户以打开详细信息窗格。

4. 在" **MFA 启用"选项卡上的** "具有安全性默认值 **的 MFA"** 下，选择" **启用安全默认值"**。

5. 选择“**保存更改**”。

若要通过条件访问启用 MFA，请参阅教程：使用多重身份验证保护Azure AD[登录事件](/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

## <a name="notify-users-who-arent-registered-for-mfa"></a>通知未注册 MFA 的用户

1. In the left navigation pane in Lighthouse， select **Users**.

2. 选择 **"多重身份验证"** 选项卡。

3. 从租户列表中，选择一个租户以打开详细信息窗格。

4. 在" **未注册 MFA 的用户"选项卡** 上，选择要通知的用户。

5. 选择 **"创建电子邮件"**。

Lighthouse 打开默认电子邮件客户端，并预填充电子邮件，并包含注册 MFA 的说明。 所有选定用户都将包含在"BCC"行中。 如果你希望单独向用户发送电子邮件，可以选择用户名旁边的电子邮件图标。

如果要使用不同的电子邮件帐户，可以将用户列表导出到文件中。 您还可以下载可以使用公司品牌自定义的示例电子邮件模板。

## <a name="next-steps"></a>后续步骤

启用 MFA 后，你可以启用Azure Active Directory (Azure AD) 密码重置。 此功能使用户能够更改或重置其密码，无需管理员或技术支持参与。 有关详细信息，请参阅 [管理自助服务密码重置](m365-lighthouse-manage-sspr.md)。

## <a name="related-content"></a>相关内容

[Plan an Azure Active Directory Multi-Factor Authentication deployment (](/azure/active-directory/authentication/howto-mfa-getstarted) article) \
[什么是安全默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) （文章）\
[什么是条件访问？](/azure/active-directory/conditional-access/overview) （文章）\
[了解如何将用户从每用户 MFA](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) 转换为条件访问 (文章) 
