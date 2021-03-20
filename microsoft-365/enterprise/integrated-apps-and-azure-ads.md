---
title: 适用于 Microsoft 365 管理员的集成应用和 Azure AD
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
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
description: 了解如何在 Azure AD 中注册和管理 Office 365 集成应用，从而允许在全局管理员级别进行应用授权。
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909770"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>适用于 Microsoft 365 管理员的集成应用和 Azure AD

管理集成应用不仅仅是管理用户 [对应用的同意](../admin/misc/user-consent.md)。 随着 Microsoft 365 REST API 的出现，用户可以向应用授予访问其 Microsoft 365 数据的权限，如邮件、日历、联系人、用户、组、文件和文件夹。 默认情况下，用户需要单独向每个应用授予权限。 

但是，如果你想要在全局管理员级别对应用授权一次，并通过应用启动器将应用推出到整个组织，这不会很好地扩展。 为此，必须在 Azure AD (Azure Active Directory) 。 在 Azure AD 中注册应用之前，需要执行一些步骤，并且应了解一些有助于在 Microsoft 365 组织中管理应用的后台信息。
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>适用于 Microsoft 365 管理员的 Azure AD 资源

你必须执行这两个任务，然后才能在 Azure AD 中管理 Microsoft 365 应用。
  
|先决条件|备注|
|:-----|:-----|
|[使用免费的 Azure AD 订阅](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |每个 Microsoft 365 付费订阅都附带 Azure AD 的免费订阅。 可以使用 Azure AD 管理应用以及创建和管理用户和组帐户。 若要使用 Azure AD，只需转到 Azure 门户 ，然后 [https://portal.azure.com](https://portal.azure.com) 使用 Microsoft 365 帐户登录。  <br/> |
|[管理用户对应用的同意](../admin/misc/user-consent.md) <br/> |必须管理用户对应用的同意，以允许第三方应用访问用户 Microsoft 365 信息，以及允许你在 Azure AD 中注册应用。 例如，当某用户使用第三方应用时，该应用可能会请求权限来访问其日历和编辑 OneDrive 文件夹中的文件。  <br/> |
   
管理 Microsoft 365 应用需要你了解 Azure AD 中的应用。 使用这些文章提供你所需的背景信息。
  
|文章|备注|
|:-----|:-----|
|[使用 Microsoft 365 应用启动器](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |如果你是应用启动器的新用户，你可能想知道它是什么以及如何使用它。 应用启动器旨在帮助你在 Microsoft 365 中的任何位置访问你的应用。  <br/> |
|[Office 365 管理 API 概述](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365 管理 API 让你能够访问 Microsoft 365 数据，包括他们最关心的内容，即邮件、日历、联系人、用户和组、文件和文件夹。 <br/> |
|[在 Azure AD 中集成应用程序](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | 了解与 Azure AD 集成的应用程序，以及如何注册应用程序，了解注册应用程序背后的概念，并了解多租户应用程序的品牌准则。  <br/> |
|[将自定义磁贴添加到应用启动器](/office365/admin/manage/customize-the-app-launcher)  <br/> |Microsoft 365 中的应用启动器使用户能够更轻松地查找和访问其应用。 本文介绍作为开发人员，你可以让应用显示在用户的应用启动器中的方法，并为用户提供使用 Microsoft 365 凭据的单一登录 (SSO) 体验。  <br/> |
|[Azure AD 集成教程](/azure/active-directory/saas-apps/tutorial-list) <br/> |这些教程的目的是展示如何为第三方 SaaS 应用程序配置 Azure AD SSO。  <br/> |
|[Azure AD 的身份验证场景](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD 通过提供标识即服务、支持行业标准协议（如 OAuth 2.0 和 OpenID Connect）以及适用于不同平台的开放源代码库来帮助你快速开始编码，从而简化了开发人员的身份验证。 本文档可帮助你了解 Azure AD 支持的各种方案，并展示如何开始使用。  <br/> |
|[应用程序访问](/azure/active-directory/manage-apps/what-is-access-management) <br/> |借助 Azure AD (，可以轻松集成到 SaaS) 应用程序的许多热门软件即服务。 它提供标识和访问管理，并为用户提供访问面板，用户可以在访问面板中发现他们拥有哪些应用程序访问权限，以及在何处使用 SSO 访问其应用程序。 本文提供了指向相关资源的链接，可让你了解有关 Azure AD 的应用程序访问增强功能以及如何为它们做贡献。  <br/> |
|[个性化 Office 365 体验](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |可以通过在 Microsoft 365 应用启动器中添加或删除应用来快速访问你每天使用的应用。  <br/> |