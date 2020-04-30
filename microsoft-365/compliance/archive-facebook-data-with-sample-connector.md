---
title: 使用连接器存档 Facebook 数据
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
description: 管理员可以将连接器设置为从数据源（如 Facebook 商业页面、Twitter、LinkedIn 公司页面和即时 Bloomberg）导入第三方数据。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据的管理。
ms.openlocfilehash: 21023e380e4065f40edd4c3dea3f4c461d743f04
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943231"
---
# <a name="set-up-a-connector-to-archive-facebook-data"></a>使用连接器存档 Facebook 数据

使用 Microsoft 365 合规性中心中的连接器将来自 Facebook 商业页面的数据导入并存档到 Microsoft 365。 在设置并配置连接器后，它会连接到 Facebook 商业页面（按计划），将 Facebook 项目的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱中。

在导入 Facebook 数据之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Facebook 数据。 例如，如果将邮箱置于诉讼保留或分配到保留策略，则会保留 Facebook 数据。 您可以使用内容搜索来搜索第三方数据，或关联在高级电子数据展示事例中与保管人存储 Facebook 数据的邮箱。 使用连接器在 Microsoft 365 中导入和存档 Facebook 数据可帮助您的组织遵守政府和法规策略。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>设置用于 Facebook 商业页面的连接器的先决条件

先完成以下先决条件，然后才能在 Microsoft 365 合规性中心中设置和配置连接器，以便从组织的 Facebook 商业页面导入和存档数据。 

- 您的组织的业务页面需要一个 Facebook 帐户（在设置连接器时，需要登录到此帐户）。 目前，您只能存档 Facebook 商业页面中的数据;您不能存档单个 Facebook 配置文件中的数据。

- 您的组织必须具有有效的 Azure 订阅。 如果你没有现有的 Azure 订阅，你可以注册以下选项之一：

    - [注册免费的一年 Azure 订阅](https://azure.microsoft.com/free) 

    - [注册 "转到即点即用 Azure 订阅"](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全 & 合规中心中的连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用全局管理员的凭据登录，然后接受该请求。

- 在 Microsoft 365 合规性中心（步骤5）中设置自定义连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤1：在 Azure Active Directory 中创建应用程序

第一步是在 Azure Active Directory （AAD）中注册新应用程序。 此应用程序对应于您在第4步和第5步中为 Facebook 连接器实现的 web 应用资源。 

有关分步说明，请参阅[在 Azure Active Directory 中创建应用](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。

在完成此步骤（通过使用前面的分步说明）时，您将把以下信息保存到文本文件中。 这些值将在部署过程的后续步骤中使用。

- AAD 应用程序 ID

- AAD 应用程序密码

- 租户 Id

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>步骤2：将来自 GitHub 的连接器 web 服务部署到你的 Azure 帐户

下一步是部署 Facebook 商业页面连接器应用程序的源代码，该应用程序将使用 Facebook API 连接到 Facebook 帐户并提取数据，以便您可以将数据导入到 Microsoft 365。 您为组织部署的 Facebook 连接器会将您的 Facebook 商业页面中的项目上载到在此步骤中创建的 Azure 存储位置。 在 Microsoft 365 合规性中心（第5步）中创建 Facebook 商业页面连接器后，导入服务会将 Facebook business pages 数据从 Azure 存储位置复制到 Microsoft 365 组织中的邮箱。 如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)" 部分中所述，您必须具有有效的 azure 订阅才能创建 azure 存储帐户。

有关分步说明，请参阅[将连接器 web 服务从 GitHub 部署到你的 Azure 帐户](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

在完成此步骤的分步说明中，您将提供以下信息：

- APISecretKey：在完成此步骤的过程中，您将创建此密码。 它在步骤5中使用。

- TenantId：在第1步中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Microsoft 365 组织的租户 ID。

完成此步骤后，请务必复制 Azure 应用服务 URL （例如， https://fbconnector.azurewebsites.net)。 您需要使用此 URL 来完成步骤3、步骤4和步骤5。

## <a name="step-3-register-the-web-app-on-facebook"></a>步骤3：在 Facebook 上注册 web 应用程序

下一步是在 Facebook 上创建和配置新的应用程序。 您在步骤5中创建的 Facebook 商业页面连接器使用 Facebook web 应用与 Facebook API 进行交互，以从组织的 Facebook 商业版页面中获取数据。

有关分步说明，请参阅[注册 Facebook 应用](deploy-facebook-connector.md#step-3-register-the-facebook-app)。

在完成此步骤（按照分步说明操作）后，将以下信息保存到文本文件中。 这些值用于在步骤4中配置 Facebook 连接器应用。

- Facebook 应用程序 ID

- Facebook 应用程序密码

- Facebook webhook verify token

## <a name="step-4-configure-the-facebook-connector-app"></a>步骤4：配置 Facebook 连接器应用程序

下一步是将配置设置添加到在步骤1中创建 Azure web 应用资源时上载的 Facebook 连接器应用。 为此，请转到连接器应用的主页并配置该页面。

有关分步说明，请参阅[Configure The Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。

在完成此步骤（按照分步说明执行）后，您将提供以下信息（在完成上述步骤后，您已将其复制到文本文件中）：

- Facebook 应用程序 ID （在步骤3中获取）

- Facebook 应用程序密码（在步骤3中获取）

- Facebook webhook verify token （在步骤3中获取）

- Azure Active Directory 应用程序 ID （在步骤1中获取的 AAD 应用程序 ID）

- Azure Active Directory 应用程序密码（在步骤1中获取的 AAD 应用程序密码）

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>第5步：设置 Microsoft 365 合规性中心中的 Facebook 商业页面连接器

最后一步是在 Microsoft 365 合规性中心中设置连接器，以将来自 Facebook 商业页面的数据导入到 Microsoft 365 中的指定邮箱。 完成此步骤后，Office 365 导入服务将开始将你的 Facebook 商业页面中的数据导入到 Microsoft 365。

有关分步说明，请参阅[第5步：在 Microsoft 365 合规性中心中设置 Facebook 连接器](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)。 

在完成此步骤（按照分步说明执行）后，您将提供以下信息（在完成这些步骤后，您已将其复制到文本文件中）。

- AAD 应用程序 ID （在步骤1中获取）

- Azure 应用服务 URL （在步骤1中获取; 例如，https://fbconnector.azurewebsites.net)

- APISecretKey （您在步骤2中创建）
