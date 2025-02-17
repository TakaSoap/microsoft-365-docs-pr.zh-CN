---
title: 设置连接器以存档 Twitter 数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解管理员如何设置和使用本机连接器将 Twitter 数据导入Microsoft 365。
ms.openlocfilehash: 959cdd49d229334f3129eb21505c4489d23ded4f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320629"
---
# <a name="set-up-a-microsoft-connector-to-archive-twitter-data-preview"></a>设置 Microsoft 连接器以存档 Twitter 数据 (预览) 

使用用户邮箱中的Microsoft 365 合规中心将数据从 Twitter 导入并存档Microsoft 365。 设置和配置连接器后，它将按计划连接到组织的 Twitter 帐户 () ，将项目内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的邮箱。

导入 Twitter 数据后，你可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核和 Microsoft 365 保留策略）应用到 Twitter 数据。 例如，当邮箱置于诉讼保留或分配给保留策略时，将保留 Twitter 数据。 您可以使用内容搜索搜索第三方数据，或将存储 Twitter 数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用连接器在企业邮箱中导入和存档 Twitter Microsoft 365可帮助你的组织遵守政府及法规策略。

导入 Twitter 数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于邮箱中存储的数据。 例如，您可以使用内容搜索搜索 Twitter 数据，或将数据存储的邮箱与案例的保管人Advanced eDiscovery关联。 使用连接器在企业邮箱中导入和存档 Twitter Microsoft 365可帮助你的组织遵守政府及法规策略。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

完成以下先决条件，然后才能在 Microsoft 365 合规中心中设置和配置连接器，以从组织的 Twitter 帐户导入和存档数据。

- 你需要一个 Twitter 帐户用于你的组织;设置连接器时，需要登录此帐户。

- 你的组织必须具有有效的 Azure 订阅。 如果你没有现有的 Azure 订阅，可以注册以下选项之一：

    - [注册一年免费的 Azure 订阅](https://azure.microsoft.com/free) 

    - [注册 Azure 付费订阅](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > [Azure Active Directory订阅](use-your-free-azure-ad-subscription-in-office-365.md)中包含的免费 Microsoft 365 订阅不支持 Microsoft 365 合规中心。

- Twitter 连接器在一天中总共可以导入 200，000 个项目。 如果一天中的 Twitter 项目超过 200，000 个，则这些项目不会导入Microsoft 365。

- 必须在步骤 5 Microsoft 365 合规中心 (中为在) 设置 Twitter 连接器的用户分配数据连接器管理员角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤 1：在 Azure Active Directory

第一步是在 Azure Active Directory (AAD) 中注册新Azure Active Directory (AAD) 。 此应用程序对应于你在 Twitter 连接器的步骤 2 中实现 Web 应用资源。

有关分步说明，请参阅在应用中[创建Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。

完成此步骤 (按照下面的分步说明) ，将以下信息保存到文本文件中。 这些值将在部署过程的稍后步骤中使用。

- AAD应用程序 ID

- AAD应用程序密码

- 租户 ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>步骤 2：将连接器 Web 服务GitHub存储库部署到 Azure 帐户

下一步是部署 Twitter 连接器应用的源代码，该应用将使用 Twitter API 连接到你的 Twitter 帐户并提取数据，以便你可以将其导入Microsoft 365。 为组织部署的 Twitter 连接器将项目从组织的 Twitter 帐户上传到Azure 存储创建的位置。 在步骤 5) 中的 Microsoft 365 合规中心 (创建 Twitter 连接器后，Microsoft 365 导入服务将 Twitter 数据从 Azure 存储 位置复制到 Microsoft 365 中的邮箱。 如之前设置连接器部分[](#before-you-set-up-a-connector)所述，你必须拥有有效的 Azure 订阅才能创建Azure 存储帐户。

若要部署 Twitter 连接器应用的源代码：

1. 转到[此GitHub网站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。

2. 单击 **"部署到 Azure"**。

有关分步说明，请参阅将连接器 Web 服务从 GitHub[部署到 Azure 帐户](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

在按照分步说明完成此步骤时，您将提供以下信息

- APISecretKey：在此步骤完成期间创建此密码。 它在步骤 5 中使用。

- tenantId：在步骤 1 Microsoft 365创建 Twitter 应用后复制的 Azure Active Directory 组织的租户 ID。

完成此步骤后，请确保复制应用服务 URL (例如， `https://twitterconnector.azurewebsites.net`) 。 您需要使用此 URL 完成步骤 3、步骤 4 和步骤 5) 。

## <a name="step-3-create-developer-app-on-twitter"></a>步骤 3：在 Twitter 上创建开发人员应用

下一步是在 Twitter 上创建和配置开发人员应用。 在步骤 7 中创建的自定义连接器使用 Twitter 应用与 Twitter API 进行交互，以从组织的 Twitter 帐户获取数据。

有关分步说明，请参阅 [创建 Twitter 应用](deploy-twitter-connector.md#step-3-create-the-twitter-app)。

完成此步骤 (按照下面的分步说明) ，将以下信息保存到文本文件中。 这些值将用于在步骤 4 中配置 Twitter 连接器应用。

- Twitter API 密钥

- Twitter API 密钥

- Twitter 访问令牌

- Twitter 访问令牌密码

## <a name="step-4-configure-the-twitter-connector-app"></a>步骤 4：配置 Twitter 连接器应用

下一步是将配置设置添加到你在步骤 2 中部署的 Twitter 连接器应用。 为此，请进入连接器应用的主页并配置它。

有关分步说明，请参阅 [配置连接器 Web 应用](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。

完成此步骤 (按照) 的分步说明 (完成上述步骤后复制到文本文件) ：

- 在步骤 3 (获取的 Twitter API 密钥) 

- 在步骤 3 (获取的 Twitter API 密钥) 

- 在步骤 3 (获取的 Twitter 访问) 

- 在步骤 3 (获取的 Twitter 访问令牌) 

- Azure Active Directory步骤 1 (AAD获取的应用程序 ID) 

- Azure Active Directory步骤 1 (AAD获取的应用程序密码) 

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>步骤 5：在 Microsoft 365 合规中心

最后一步是在 Microsoft 365 合规中心 中设置 Twitter 连接器，以将数据从组织的 Twitter 帐户导入 Microsoft 365。 完成此步骤后，Microsoft 365导入服务将开始从组织的 Twitter 帐户导入数据以Microsoft 365。

有关分步说明，请参阅在 Microsoft 365 合规中心 [中设置 Twitter 连接器](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)。 

在完成此步骤 (按照) 的分步说明 (您将提供在完成步骤) 后复制到文本文件的以下信息。

- 在步骤 2 中 (Azure 应用服务 URL;例如，) `https://twitterconnector.azurewebsites.net`

- 在步骤 2 (中创建的 APISecretKey) 