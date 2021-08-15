---
title: 使用连接器存档 Facebook 数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解如何设置&使用 Microsoft 365 合规中心 中的连接器将 & 存档数据从 Facebook 业务页面导入Microsoft 365。
ms.openlocfilehash: 9327da8f3e37d64300ff1bafeb375f65e77fda67cc2d13bf0d1a3227b9bca693
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53866651"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>设置连接器以存档 Facebook 数据 (预览) 

使用网站中的连接器Microsoft 365 合规中心数据从 Facebook 业务页面导入和存档Microsoft 365。 设置和配置连接器后，它将按计划连接到 facebook 业务页面 () ，将 Facebook 项目的内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的邮箱。

导入 Facebook 数据后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Facebook 数据。 例如，将邮箱置于诉讼保留或分配给保留策略时，将保留 Facebook 数据。 您可以使用内容搜索搜索第三方数据，或将存储 Facebook 数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用连接器在组织中导入和存档 Facebook Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>设置 Facebook 业务页面连接器的先决条件

完成以下先决条件，然后才能在 Microsoft 365 合规中心中设置和配置连接器，以从组织的 Facebook 业务页面导入和存档数据。 

- 你需要一个 Facebook 帐户作为组织业务页面 (设置连接器帐户时需要登录到此) 。 目前，只能存档 Facebook 业务页面的数据;无法存档单个 Facebook 配置文件的数据。

- 你的组织必须具有有效的 Azure 订阅。 如果你没有现有的 Azure 订阅，可以注册以下选项之一：

    - [注册一年免费的 Azure 订阅](https://azure.microsoft.com/free)

    - [注册 Azure 付费订阅](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > [Azure Active Directory订阅](use-your-free-azure-ad-subscription-in-office-365.md)中包含的免费 Microsoft 365 订阅不支持安全与合规&连接器。

- Facebook Business 页面的连接器一天中总共可以导入 200，000 个项目。 如果一天中 Facebook 业务项目超过 200，000 个，则这些项目不会导入Microsoft 365。

- 必须在步骤 5 Microsoft 365 合规中心 (中为在) 中设置自定义连接器的用户分配邮箱导入导出Exchange Online。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤 1：在 Azure Active Directory

第一步是在 AAD Azure Active Directory (注册) 。 此应用程序对应于你在 Facebook 连接器的步骤 4 和步骤 5 中实现 Web 应用资源。 

有关分步说明，请参阅在应用中[创建Azure Active Directory。](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

在完成此步骤过程中 (前面的分步说明) ，您将以下信息保存到文本文件中。 这些值在部署过程的稍后步骤中使用。

- AAD 应用程序 ID

- AAD 应用程序密码

- 租户 ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>步骤 2：将连接器 Web 服务从 GitHub部署到 Azure 帐户

下一步是部署 Facebook 业务页面连接器应用的源代码，该应用程序将使用 Facebook API 连接到 Facebook 帐户并提取数据，以便将其导入 Microsoft 365。 您为组织部署的 Facebook 连接器将项目从 Facebook 业务页面上载到Azure 存储创建的位置。 在步骤 5) 中的 Microsoft 365 合规中心 (创建 Facebook 业务页面连接器后，导入服务将 Facebook 业务页面数据从 Azure 存储 位置复制到 Microsoft 365 组织的邮箱。 如[先决条件部分所述](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)，你必须拥有有效的 Azure 订阅，以创建一个Azure 存储帐户。

有关分步说明，请参阅将连接器[Web](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)服务从 GitHub 部署到 Azure 帐户。

在完成此步骤的分步说明中，您将提供以下信息：

- APISecretKey：在此步骤完成期间创建此密码。 它在步骤 5 中使用。

- TenantId：在步骤 1 Microsoft 365创建 Facebook 连接器应用后复制的 Azure Active Directory 组织的租户 ID。

完成此步骤后，请确保将 Azure 应用服务 URL (例如 ， https://fbconnector.azurewebsites.net) 。 您需要使用此 URL 完成步骤 3、步骤 4 和步骤 5) 。

## <a name="step-3-register-the-web-app-on-facebook"></a>步骤 3：在 Facebook 上注册 Web 应用

下一步是在 Facebook 上创建和配置新应用程序。 在步骤 5 创建的 Facebook 业务页面连接器使用 Facebook Web 应用程序与 Facebook API 进行交互，以从组织的 Facebook 业务页面获取数据。

有关分步说明，请参阅注册 [Facebook 应用](deploy-facebook-connector.md#step-3-register-the-facebook-app)。

在此步骤完成 (按照本文中的分步) ，将以下信息保存到文本文件。 这些值用于配置步骤 4 中的 Facebook 连接器应用。

- Facebook 应用程序 ID

- Facebook 应用程序密码

- Facebook Webhook 验证令牌

## <a name="step-4-configure-the-facebook-connector-app"></a>步骤 4：配置 Facebook 连接器应用

下一步是将配置设置添加到你在步骤 1 中创建 Azure Web 应用资源时上载的 Facebook 连接器应用。 为此，请进入连接器应用的主页并配置它。

有关分步说明，请参阅配置 [Facebook 连接器应用](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。

在完成此步骤 (按照) 的分步说明 (完成上述步骤后复制到文本文件的以下信息) ：

- 在步骤 3 (获取的 Facebook 应用程序 ID) 

- Facebook 应用程序密码 (步骤 3 中) 

- Facebook Webhook 验证令牌 (步骤 3) 

- Azure Active Directory步骤 1 (获取的 AAD 应用程序 ID) 

- Azure Active Directory步骤 1 (中获取的 AAD 应用程序密码) 

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>步骤 5：在网站中设置 Facebook Microsoft 365 合规中心

最后一步是在 Microsoft 365 合规中心 中设置连接器，该连接器将数据从 Facebook 业务页面导入 Microsoft 365。 完成此步骤后，Microsoft 365导入服务将开始将数据从 Facebook 业务页面导入Microsoft 365。

有关分步说明，请参阅步骤[5：](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)在 Microsoft 365 合规中心 中设置 Facebook 连接器。 

在完成此步骤 (按照) 的分步说明 (在完成步骤) 后复制到文本文件的以下信息。

- 步骤 1 (获取的 AAD 应用程序 ID) 

- 在步骤 1 (获取的 Azure 应用服务 URL;例如， https://fbconnector.azurewebsites.net)

- 在步骤 2 (中创建的 APISecretKey) 