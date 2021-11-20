---
title: 管理自助服务密码重置
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
description: 对于 Managed Service Providers (MSP) using Microsoft 365 Lighthouse，了解如何管理自助服务密码重置。
ms.openlocfilehash: b8367d2ed2c088d56425b08c6da5dfd55fcd84b8
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2021
ms.locfileid: "61128600"
---
# <a name="manage-self-service-password-reset"></a>管理自助服务密码重置

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。 如果你的组织没有Microsoft 365 Lighthouse，请参阅注册[Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse使合作伙伴Azure Active Directory (Azure AD) SSPR (自助服务密码重置) 。 SSPR 使用户能够更改或重置其密码，无需管理员或技术支持参与。 如果用户的帐户被锁定或忘记密码，他们可以按照提示自行取消阻止并恢复工作。 当用户无法登录到其设备或应用程序时，此功能可减少技术支持呼叫并降低工作效率。

## <a name="before-you-begin"></a>准备工作

必须先满足以下条件，租户才能显示在列表中：

- 客户租户必须拥有Azure AD Premium许可证。 有关哪些许可证支持 SSPR 的信息，请参阅许可要求[Azure Active Directory自助服务密码重置。](/azure/active-directory/authentication/concept-sspr-licensing)

- 客户租户必须在 Lighthouse 内处于活动状态。 若要了解如何确定租户是否处于活动状态，请参阅租户Microsoft 365 Lighthouse[概述](m365-lighthouse-tenants-page-overview.md)。

## <a name="view-sspr-tenant-status"></a>查看 SSPR 租户状态

1. In the left navigation pane of Lighthouse， select **Users**.

2. 选择" **密码重置"** 选项卡。

"密码重置"选项卡概述通过推荐设置启用 SSPR 的租户、尚未注册 SSPR 的用户数，以及您管理的组织中 SSPR 部署进度的租户详细细分。

## <a name="enable-sspr-for-a-tenant"></a>为租户启用 SSPR

1. In the left navigation pane in Lighthouse， select **Users**.

2. 选择" **密码重置"** 选项卡。

3. 从租户列表中，选择一个租户以打开详细信息窗格。

4. 选择 **"编辑 SSPR 设置Azure Active Directory** 转到"Azure Active Directory (Azure AD) "。

5. 在Azure AD中，为所有用户或所选用户启用 SSPR。 若要了解更多信息，请参阅[教程：允许用户](/azure/active-directory/authentication/tutorial-enable-sspr)使用自助密码重置解锁Azure Active Directory重置密码。

## <a name="notify-users-to-register-for-sspr"></a>通知用户注册 SSPR

1. In the left navigation pane in Lighthouse， select **Users**.

2. 选择" **密码重置"** 选项卡。

3. 从租户列表中，选择一个租户以打开详细信息窗格。

4. 选择要通知的用户。

5. 选择 **"创建电子邮件"。**

Lighthouse 打开默认电子邮件客户端，并预填充电子邮件，并包含注册 SSPR 的说明。 所有选定用户都将包含在"BCC"行中。 如果你希望单独向用户发送电子邮件，可以选择用户名旁边的电子邮件图标。

如果要使用不同的电子邮件帐户，可以将用户列表导出到文件中。 您还可以下载可以使用公司品牌自定义的示例电子邮件模板。

## <a name="related-content"></a>相关内容

[Plan an Azure Active Directory self-service password reset deployment deployment (](/azure/active-directory/authentication/howto-sspr-deployment) article) \
[教程：允许用户使用自助服务](/azure/active-directory/authentication/tutorial-enable-sspr)密码重置Azure Active Directory解锁其帐户或重置密码 (文章) \
[如何启用和配置 SSPR Azure AD (](https://www.youtube.com/watch?v=rA8TvhNcCvQ)视频) \
[管理多重身份验证 (](m365-lighthouse-manage-mfa.md) 文章) 
