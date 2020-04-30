---
title: 设置连接器以存档 Twitter 数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将 Twitter 数据导入 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据的管理。
ms.openlocfilehash: 5d4c1817fe9b3c47dc3cbabd0147f23057c7bc65
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943191"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a>设置连接器以存档 Twitter 数据

使用 Microsoft 365 合规性中心中的连接器将来自 Twitter 的数据导入和存档到 Microsoft 365。 设置和配置连接器后，它会连接到您的组织的 Twitter 帐户（定期），将项目的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱。

导入 Twitter 数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核和 Microsoft 365 保留策略）应用到 Twitter 数据。 例如，如果将邮箱置于诉讼保留状态或分配到保留策略，则会保留 Twitter 数据。 您可以使用内容搜索来搜索第三方数据，或关联在高级电子数据展示事例中与保管人存储 Twitter 数据的邮箱。 使用连接器在 Microsoft 365 中导入和存档 Twitter 数据可帮助您的组织遵守政府和法规策略。

在导入 Twitter 数据之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用到存储在邮箱中的数据。 例如，您可以使用内容搜索来搜索 Twitter 数据，或将与数据存储在一起的邮箱与高级电子数据展示事例中的保管人相关联。 使用连接器在 Microsoft 365 中导入和存档 Twitter 数据可帮助您的组织遵守政府和法规策略。

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>为 Twitter 设置连接器的先决条件

先完成以下先决条件，然后才能在 Microsoft 365 合规性中心中设置和配置连接器，以便从组织的 Twitter 帐户导入和存档数据。

- 您的组织需要 Twitter 帐户;设置连接器时，需要登录到此帐户。

- 您的组织必须具有有效的 Azure 订阅。 如果你没有现有的 Azure 订阅，你可以注册以下选项之一：

    - [注册免费的一年 Azure 订阅](https://azure.microsoft.com/free) 

    - [注册 "转到即点即用 Azure 订阅"](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全 & 合规中心中的连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用全局管理员的凭据登录，然后接受该请求。

- 在 Microsoft 365 合规性中心（步骤5）中设置 Twitter 连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤1：在 Azure Active Directory 中创建应用程序

第一步是在 Azure Active Directory （AAD）中注册新应用程序。 此应用程序对应于您在您在 Twitter 连接器的步骤2中实现的 web 应用资源。

有关分步说明，请参阅[在 Azure Active Directory 中创建应用](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。

在完成此步骤（按照分步说明操作）后，您将把以下信息保存到文本文件中。 这些值将在部署过程的后续步骤中使用。

- AAD 应用程序 ID

- AAD 应用程序密码

- 租户 Id

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>步骤2：将 GitHub 存储库中的连接器 web 服务部署到 Azure 帐户

下一步是部署将使用 Twitter API 连接到 Twitter 帐户并提取数据的 Twitter 连接器应用的源代码，以便您可以将数据导入到 Microsoft 365。 为组织部署的 Twitter 连接器会将组织的 Twitter 帐户中的项目上载到在此步骤中创建的 Azure 存储位置。 在 Microsoft 365 合规性中心（步骤5）中创建 Twitter 连接器后，Office 365 导入服务会将 Twitter 数据从 Azure 存储位置复制到 Microsoft 365 中的邮箱。 如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-twitter)" 部分中所述，您必须具有有效的 azure 订阅才能创建 azure 存储帐户。

若要部署 Twitter 连接器应用的源代码，请执行以下操作：

1. 转到[此 GitHub 网站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。

2. 单击 "**部署到 Azure**"。

有关分步说明，请参阅[将连接器 web 服务从 GitHub 部署到你的 Azure 帐户](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

按照分步说明完成此步骤，您将提供以下信息

- APISecretKey：在完成此步骤的过程中，您将创建此密码。 它在步骤5中使用。

- tenantId：在第1步中创建 Azure Active Directory 中的 Twitter 应用之后复制的 Microsoft 365 组织的租户 ID。

完成此步骤后，请务必复制 app Service URL （例如`https://twitterconnector.azurewebsites.net`）。 您需要使用此 URL 来完成步骤3、步骤4和步骤5。

## <a name="step-3-create-developer-app-on-twitter"></a>步骤3：在 Twitter 上创建开发人员应用

下一步是在 Twitter 上创建和配置开发人员应用程序。 您在步骤7中创建的自定义连接器使用 Twitter 应用与 Twitter API 进行交互，以从组织的 Twitter 帐户中获取数据。

有关分步说明，请参阅[创建 Twitter 应用](deploy-twitter-connector.md#step-3-create-the-twitter-app)。

在完成此步骤（按照分步说明操作）后，将以下信息保存到文本文件中。 这些值将用于在步骤4中配置 Twitter 连接器应用。

- Twitter API 密钥

- Twitter API 密钥

- Twitter 访问令牌

- Twitter 访问令牌机密

## <a name="step-4-configure-the-twitter-connector-app"></a>步骤4：配置 Twitter 连接器应用

下一步是将配置设置添加到您在步骤2中部署的 Twitter 连接器应用。 为此，请转到连接器应用的主页并配置该页面。

有关分步说明，请参阅[Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。

在完成此步骤（按照分步说明操作）后，您将提供以下信息（在完成上述步骤后，您已将其复制到文本文件中）：

- Twitter API 密钥（在步骤3中获取）

- Twitter API 密钥（在步骤3中获取）

- Twitter 访问令牌（在步骤3中获取）

- Twitter 访问令牌机密（在步骤3中获取）

- Azure Active Directory 应用程序 ID （在步骤1中获取的 AAD 应用程序 ID）

- Azure Active Directory 应用程序密码（在步骤1中获取的 AAD 应用程序密码）

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>步骤5：在 Microsoft 365 合规性中心中设置 Twitter 连接器

最后一步是在 Microsoft 365 合规性中心中设置 Twitter 连接器，以将组织的 Twitter 帐户中的数据导入到 Microsoft 365 中的指定邮箱。 完成此步骤后，Office 365 导入服务将开始从您的组织的 Twitter 帐户向 Microsoft 365 导入数据。

有关分步说明，请参阅[在 Microsoft 365 合规性中心中设置 Twitter 连接器](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)。 

在完成此步骤（按照分步说明操作）后，您将提供以下信息（在完成这些步骤后，您已将其复制到文本文件中）。

- Azure 应用服务 URL （在步骤2中获取; 例如， `https://twitterconnector.azurewebsites.net`）

- APISecretKey （您在步骤2中创建）
