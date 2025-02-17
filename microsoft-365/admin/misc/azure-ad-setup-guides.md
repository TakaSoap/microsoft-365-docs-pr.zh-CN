---
title: Azure Active Directory设置指南
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
description: 了解适用于 Azure Active Directory 的设置指南。
ms.openlocfilehash: 059890bd6a79ced1f7121e973b070790dffd8db9
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403602"
---
# <a name="azure-active-directory-setup-guides"></a>Azure Active Directory设置指南

Azure Active Directory (Azure AD) 功能可帮助您管理和保护组织。 这些设置指南将帮助您以一种简单方式集成这些功能。 在下列部分中，我们将简要介绍设置指南并共享指向这些指南的链接。

## <a name="who-are-these-setup-guides-for"></a>Who这些设置指南是什么？

这些设置指南专为通常可能没有专用标识团队的中小型组织设计。 你无需是标识专家来使用它们。

## <a name="what-to-expect-and-what-youll-need"></a>预期结果和需要哪些信息

设置指南可帮助你配置 Azure AD。 如果需要设置更高级的配置，则安装指南将指导你到 Azure AD 位置。

### <a name="required-permissions"></a>所需权限

您必须是以下管理角色的成员：

- 全局管理员：允许你使用安装指南中的集成工具在组织Microsoft 365更改。

- 全局读者：允许你查看设置指南，但不能在租户中进行更改。

## <a name="identity-security-for-teams"></a>用户的身份Teams

Azure Active Directory (Azure AD) 基于云的标识和访问管理服务，可帮助员工登录和访问应用和服务。
此目录包含一些基本安全功能，您可以使用这些功能来确保用户安全，并使用 Teams。

### <a name="licensing"></a>授权

需要Azure Active Directory P2 许可证才能利用此目录中的安全功能。

[打开目录的标识Teams安全](https://aka.ms/teamsidentity)

## <a name="azure-active-directory-deployment"></a>Azure Active Directory部署  

Azure Active Directory设置指南将帮助你按建议的顺序设置Azure AD最常用的功能。 设置指南分为三个部分：**初始、****核心和****高级**。 每个部分推荐应打开的一组功能。

设置指南包含需要完成的任务清单，可以在完成这些指南时跟踪进度。 如有必要，这些指南还将链接到其他设置指南。

[打开Azure Active Directory设置指南](https://go.microsoft.com/fwlink/p/?linkid=2183427)。

## <a name="add-or-sync-users-to-your-microsoft-account"></a>将用户添加或同步到 Microsoft 帐户  

本指南可帮助你设置 Azure 和 Microsoft 365 中的用户帐户设置。 根据您的环境和需求，你可以选择单独添加用户、使用 Azure AD 云同步或 Azure AD 连接 迁移本地目录，或解决现有同步问题。

### <a name="licensing"></a>授权

使用 Azure Active Directory 同步工具是免费的，并包含在所有Microsoft 365订阅中。

[打开添加或同步用户设置指南](https://go.microsoft.com/fwlink/?linkid=2183349)。

## <a name="add-a-cloud-app-to-microsoft-365"></a>将云应用添加到Microsoft 365 

本指南旨在帮助你将云应用添加到Microsoft 365。 在我们的指南中，你可以向租户添加应用程序、向应用添加用户、分配角色等。  如果应用支持单一Sign-On (SSO) ，我们还将演练该配置。

### <a name="licensing"></a>授权

每个付费订阅Microsoft 365都附带免费订阅到 Azure AD。 可以使用Azure AD管理应用，以及创建和管理用户和组帐户。

[打开添加云应用以Microsoft 365设置指南](https://aka.ms/AzureAppSetup)

## <a name="azure-self-service-password-reset-sspr-guide"></a>Azure Self-Service密码重置 (SSPR) 指南

此设置指南旨在帮助你启用和配置自助服务密码重置。 设置指南将指导你完成建议的选项，包括密码写回和管理通知。

### <a name="licensing"></a>授权

SSPR 需要以下许可证之一：

- Azure Active Directory P1 或 P2

- Microsoft 365 商业高级版

- Microsoft 365 企业版 E3 或 E5  

- Enterprise移动性和安全性 E3 或 E5

[打开自助服务密码重置设置指南](https://go.microsoft.com/fwlink/p/?linkid=2183284)。

## <a name="multi-factor-authentication-mfa"></a>多重身份验证 (MFA)

本指南提供当前的 MFA 状态，并帮助 IT 管理员选择满足其组织要求的最佳 MFA 选项。 然后，我们帮助为组织配置和强制执行所选的 MFA 方法。

### <a name="licensing"></a>授权

条件访问需要Azure Active Directory P1 或 P2 许可证，安全默认值和每用户 MFA 是免费的，并且包含在所有 Microsoft 365订阅中。

[打开 MFA 身份验证 (多重) 指南](https://go.microsoft.com/fwlink/?linkid=2183506)

## <a name="the-passwordless-setup-guide"></a>无密码设置指南

无密码设置指南旨在帮助您确定最适合您的环境的无密码方法。 这些方法包括安全密钥、Windows Hello For Business 和 Microsoft Authenticator 应用。 If the recommendation is Windows Hello for Business， there's a section to guide you through the different options. 本指南会询问问题，以帮助你制定分步计划。

### <a name="licensing"></a>授权

每个付费订阅Microsoft 365都附带免费订阅到 Azure AD。 可以使用Azure AD管理应用，以及创建和管理用户和组帐户。

[打开无密码设置指南](https://go.microsoft.com/fwlink/?linkid=2183427)。
