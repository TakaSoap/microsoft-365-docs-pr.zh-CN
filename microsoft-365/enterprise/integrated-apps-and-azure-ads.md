---
title: 为管理员Azure AD集成Microsoft 365应用程序
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: landing-page
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: 了解如何在 Office 365 中注册和管理Azure AD集成应用，从而允许在 **Azure AD DC** 管理员或全局管理员级别 **进行应用授权**。
ms.openlocfilehash: ddb22c6e1be3d337fe7b54f27cae6a197f823c71
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681251"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>为管理员Azure AD集成Microsoft 365应用程序

管理集成应用不仅仅是管理用户 [对应用的同意](../admin/misc/user-consent.md)。 随着 rest API 的Microsoft 365，用户可以向应用授予对 Microsoft 365 数据（如邮件、日历、联系人、用户、组、文件和文件夹）的访问权限。 默认情况下，用户需要单独向每个应用授予权限。 

但是，如果你想要在 **Azure AD DC** 管理员或全局管理员级别授权一次应用，并通过应用启动器将应用推出到整个组织，这不会很好地扩展。 为此，你必须在应用商店中注册Azure Active Directory (Azure AD) 。 若要在 Azure AD 中注册应用，需要执行一些步骤，并且应了解一些有助于在 Microsoft 365 组织中管理应用的背景信息。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD管理员Microsoft 365资源

你必须执行这两个任务，然后才能在 Azure AD 中管理 Microsoft 365 应用。
  
|必备条件|备注|
|:-----|:-----|
|[使用免费Azure AD订阅](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |每个付费订阅Microsoft 365都附带免费订阅到 Azure AD。 可以使用Azure AD管理应用以及创建和管理用户和组帐户。 若要使用 Azure AD，只需转到 Azure 门户 ，[https://portal.azure.com](https://portal.azure.com)然后使用你的 Microsoft 365 帐户登录。  <br/> |
|[管理用户对应用的同意](../admin/misc/user-consent.md) <br/> |你必须管理用户对应用的同意，以允许第三方应用访问用户Microsoft 365信息，并允许你在 Azure AD 中注册应用。 例如，当某用户使用第三方应用时，该应用可能会请求权限来访问其日历和编辑 OneDrive 文件夹中的文件。  <br/> |
   
管理Microsoft 365需要你了解应用中Azure AD。 使用这些文章提供你所需的背景信息。
  
|文章|备注|
|:-----|:-----|
|[满足 Microsoft 365 应用启动器](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |如果你是应用启动器的新用户，你可能想知道它是什么以及如何使用它。 应用启动器旨在帮助你从任何位置访问Microsoft 365。  <br/> |
|[Office 365 API 概述](/office/office-365-management-api/office-365-management-apis-overview) <br/> |利用 Microsoft 365 管理 API，您可以访问 Microsoft 365 数据，包括他们最关心的内容—邮件、日历、联系人、用户和组、文件和文件夹。 <br/> |
|[在应用程序中集成Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | 了解与 Azure AD 集成的应用程序，以及如何注册应用程序、了解已注册应用程序背后的概念，以及了解多租户应用程序的品牌准则。  <br/> |
|[将自定义磁贴添加到应用启动器](/office365/admin/manage/customize-the-app-launcher)  <br/> |应用中的应用启动Microsoft 365使用户可以更轻松地查找和访问其应用。 本文介绍你作为开发人员，你可以让应用显示在用户的应用启动器中的方法，并为用户提供使用 Microsoft 365 凭据的单一登录 (SSO) 体验。  <br/> |
|[Azure AD集成教程](/azure/active-directory/saas-apps/tutorial-list) <br/> |这些教程的目的是展示如何为第三Azure AD SaaS 应用程序配置 SSO。  <br/> |
|[Azure AD 的身份验证场景](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD通过提供标识即服务来简化开发人员的身份验证，同时支持行业标准协议（如 OAuth 2.0 和 OpenID 连接）以及适用于不同平台的开放源代码库，以帮助您快速开始编码。 本文档将帮助您了解支持的各种Azure AD并演示如何开始使用。  <br/> |
|[应用程序访问](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD SaaS 应用程序支持轻松集成到许多当今受欢迎的软件即服务 (软件) 集成。 它提供标识和访问管理，并为用户提供访问面板，用户可以在访问面板中发现他们拥有哪些应用程序访问权限，以及在何处使用 SSO 访问其应用程序。 本文提供了指向相关资源的链接，通过这些资源，您可以了解有关 Azure AD 的应用程序访问增强功能以及如何为它们做贡献。  <br/> |
|[个性化设置Office 365体验](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |可以通过在应用启动器中添加或删除应用，快速访问Microsoft 365应用。  <br/> |
