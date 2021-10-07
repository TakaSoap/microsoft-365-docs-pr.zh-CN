---
title: Microsoft 365 支持与 ServiceNow 配置指南集成
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow 的作用域认证应用程序安装和配置指南。
ms.openlocfilehash: 58b955509fd998e7478ad32704c00bd89d692098
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171983"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-guide"></a>Microsoft 365 支持与 ServiceNow 配置指南集成

[概述](#overview) 

[ServiceNow 环境中的应用程序依赖项](#application-dependencies-in-servicenow-environments)

[配置说明](#configuration-instructions)

[Who可以设置支持Microsoft 365集成？](#who-can-set-up-microsoft-365-support-integration)

[哪些功能在支持集成Microsoft 365可用？](#what-features-are-available-in-microsoft-365-support-integration) 

[设置Microsoft 365 ServiceNow 基本身份验证集成](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)

[设置Microsoft 365支持与 AAD OAuth 令牌集成](#set-up-microsoft-365-support-integration-with-aad-oauth-token)

[设置Microsoft 365仅支持Insights集成](#set-up-microsoft-365-support-integration-for-insights-only) 

[测试配置](#testing-the-configuration) 

[疑难解答](#troubleshooting) 

## <a name="overview"></a>概述

Microsoft 365集成使您可以将Microsoft 365、支持和服务运行状况与 ServiceNow 集成。 可以使用 Microsoft 建议的解决方案研究 Microsoft 已知和已报告的问题，解决事件并完成任务，如有必要，还可以上报给 Microsoft 人员协助支持。

## <a name="application-dependencies-in-servicenow-environments"></a>ServiceNow 环境中的应用程序依赖项

所需的权限：

- oauth \_ 实体

- oauth \_ 实体 \_ 配置文件

安装Microsoft 365集成后，将创建两个应用程序跨作用域访问。 如果出于任何原因未成功创建它们，请手动创建它们。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image1.png" alt-text="图形用户界面，自动生成应用程序说明":::

## <a name="configuration-instructions"></a>配置说明

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image2.png" alt-text="自动生成的图表说明":::

若要设置Microsoft 365集成：

- 在 AAD Microsoft Azure Active Directory (中) 应用程序，以对出站和入站 API 调用进行身份验证。

- 使用 Microsoft AAD 应用程序为出站和入站数据流创建 ServiceNow 实体。

- 通过 Microsoft 门户将 ServiceNow 实例Microsoft 365 管理 Microsoft 支持。

## <a name="who-can-set-up-microsoft-365-support-integration"></a>Who可以设置支持Microsoft 365集成？

- 有权创建 AAD 应用程序的任何人。

- ServiceNow 管理员。

- 支持人员管理员或租户中的服务Microsoft 365管理员。

## <a name="what-features-are-available-in-microsoft-365-support-integration"></a>哪些功能在支持集成Microsoft 365可用？

在设置支持集成Microsoft 365配置之前，请查看对以下问题的回答：

**问题#1** ServiceNow 环境是否允许基本身份验证 (对入站 Web 服务调用使用 ServiceNow) 访问？

**问题#2** 如果你有多个租户，是否计划使用与 ServiceNow 环境集成的单个租户Microsoft 365集成？

根据对以上问题的答案，此表将告诉您哪些功能可用以及如何设置Microsoft 365集成。 有关每个功能的说明，请参阅Microsoft 365[集成。](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)

|问题#1答案|问题#2答案|哪些功能可用？|配置步骤|
|--- |--- |--- |--- |
|是|是|服务运行状况事件 <br/>建议的解决方案 </br>Microsoft 服务请求|[设置Microsoft 365 ServiceNow 基本身份验证集成](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)|
|是|否|服务运行状况事件 <br/>建议的解决方案 </br>Microsoft 服务请求||
|否|是|服务运行状况事件 <br/>建议的解决方案 </br>Microsoft 服务请求|[设置Microsoft 365支持与 AAD OAuth 令牌集成](#set-up-microsoft-365-support-integration-with-aad-oauth-token)|
|否|否|服务运行状况事件 <br/>建议的解决方案|[设置Microsoft 365仅支持Insights集成](#set-up-microsoft-365-support-integration-for-insights-only) |

## <a name="set-up-microsoft-365-support-integration-with-servicenow-basic-authentication"></a>设置支持Microsoft 365 ServiceNow 基本身份验证集成

### <a name="prerequisites-basic-authentication"></a>基本 (的先决条件) 

若要设置支持集成，需要满足Microsoft 365先决条件。

1. \[可以在你的租户下创建 AAD 应用程序Microsoft 365 \] 应用程序。

    1. 使用你的[租户](https://portal.azure.com/)凭据Microsoft 365 Azure 门户。

    1. 转到"应用注册"页并创建新应用程序。

        Select **Accounts in this organizational directory only ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 添加重定向 `https://{your-servicenow-instance}.service-now.com/oauth_redirect.do` URL：。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 获取应用程序客户端 ID 并创建应用密码。

2. \[ServiceNow 管理员人员 在 \] ServiceNow 中设置出站 OAuth 提供程序。

    1. 如果范围未设置为"全局"，请打开 **"设置**  >    >  **应用程序"以** 切换到"**全局"。**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

    1. 转到 **"系统""OAuth**  >  **应用程序注册表"。**

    1. 通过选择"向第三方 OAuth 提供程序连接 **值新建** 一个应用程序。

    - 客户端 ID：步骤 1 中创建的应用程序的客户端 \# ID

    - 客户端密码：步骤 1 中创建的应用程序的应用 \# 密码

    - 默认授予类型：客户端凭据

    - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 重定向 URL： `https://{service-now-instance-name}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

3. \[ServiceNow 管理员人员 \] 设置入站 OAuth 提供程序。

    1. 如果范围未设置为"全局"，请打开 **"设置**  >    >  **应用程序"以** 切换到"**全局"。**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="图形用户界面，自动生成应用程序说明":::

    1. 转到 **"系统""OAuth**  >  **应用程序注册表"。**

    1. 通过选择"为外部客户端 **创建 OAuth API 终结点"创建新的应用程序**。 命名入站 OAuth 提供程序，并保留其他字段的默认值。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image7.png" alt-text="图形用户界面，自动生成应用程序说明":::

4. \[ServiceNow 管理员创建 \] 集成用户。

    必须指定集成用户。 如果你没有现有集成用户或要为此集成创建一个特定用户，请转到组织  >  **用户** 创建新用户。

    如果要创建新的集成用户，请选中" **仅 Web 服务访问"框**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image8.png" alt-text="图形用户界面，自动生成应用程序说明":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[可选 \] 允许服务的 IP 支持Microsoft 365集成

如果贵公司使用自己的策略限制 Internet 访问，请通过允许下面的 IP 地址同时用于入站和出站 API 访问，为 Microsoft 365 服务启用网络访问以支持集成。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> 此终端命令列出服务的所有活动 IP，Microsoft 365集成：`nslookup connector.rave.microsoft.com`

### <a name="set-up-microsoft-365-support-integration-application"></a>设置Microsoft 365集成应用程序

可以在Microsoft 365下设置支持集成Microsoft 365应用程序。

若要设置 ServiceNow 实例与服务支持之间的集成，需要Microsoft 365这些步骤。

1. \[ServiceNow 管理员将作用域切换为支持 \] Microsoft 365集成。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

2. \[ServiceNow 管理员人员 转到Microsoft 365 \] 支持>**安装程序** 以打开集成流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略，作用域 \_ 'x \_ mioms \_ m365 \_ assis'中的'oauth 实体的读取操作'被拒绝"，则由表访问策略导致。 必须确保已检查 **table** oauth 实体的所有应用程序  >  作用域"可读取 \_ "。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image10.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

3. \[作为 ServiceNow 管理员的用户 \] 选择 **"** 同意同意"以同意同意

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

4. \[ServiceNow 管理员人员 \] 设置出站 OAuth 提供程序。

    Select the OAuth profile for Outbound OAuth Provider created in [Prerequisites (Basic Authentication)](#prerequisites-basic-authentication) step \# 2 and select **Next**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

5. \[ServiceNow 管理员人员 \] 设置入站 OAuth 提供程序。

    - 取消 **选中"跳过当前步骤"。**

    - 取消 **选中"外部 OIDC 身份验证令牌"。**

    - 选择在先决条件和基本身份验证 [ (中创建](#prerequisites-basic-authentication) 的 OAuth) \# 步骤 3，然后选择下一 **步**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image13.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

6. \[ServiceNow 管理员人员 \] 设置入站呼叫集成用户。

    - 取消 **选中"跳过当前步骤"。**

    - Select the integration user created in [Prerequisites (Basic Authentication)](#prerequisites-basic-authentication) step \# 4 and select **Next**.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image14.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

7. \[ServiceNow 管理员人员 \] 设置存储库 ID。

    指定存储库 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

8. \[ServiceNow 管理员人员 \] 设置应用程序设置。

    选择以下设置，然后选择"下一 **步"。**

    - 具有 Microsoft 365 的 SSO：检查 ServiceNow 实例是否设置为 SSO Microsoft 365租户，否则取消选中它。

    - Microsoft 365管理员电子邮件：创建Microsoft 365案例时联系的管理员Microsoft 365电子邮件。

    - 测试环境：选中此框可指示测试阶段，以避免 Microsoft 支持代理联系你以解决问题。 如果你已准备好使用支持集成Microsoft 365，请取消选中此框。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

9. \[在租户中作为支持管理员或服务请求管理员Microsoft 365完全 \] 集成。

    1. 检查以下信息以确保正确无误。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image17.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

    1. 转到"Microsoft 365 [门户](https://admin.microsoft.com/)  >  **"设置"**  >  **组织设置**  >  **""组织配置文件"。**

    1. 设置支持集成设置：

        1. 在"基本信息"选项卡上，选择"内部支持工具""现在服务"，在"步骤 - 6 完成"页上键入"出站应用程序 [ID"](#prerequisites-basic-authentication)作为应用程序 **ID** 的值，该页是在先决条件 (基本身份验证) 步骤 1 中创建的 \# 。

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

        1. 在选项卡 **"存储库"** 中， **选择** "添加存储库"以创建具有以下设置的新存储库：

            - Repository： The **Repository ID** value from page Step - 6 Complete the integration.

            - 终结点： **第 6** 步中的终结点值完成集成。

            - 身份验证类型：选择 **"基本身份验证"。**

            - 客户端 ID： **第** 6 步中的客户端 ID 值 完成集成。

            - 客户端密码：在步骤 3 中的先决条件 ([中创建 ](#prerequisites-basic-authentication) 的入站 OAuth) \# 密码。

            - 刷新令牌过期：864000

            - Rest username： The **User Name** value from page Step - 6 Complete the integration.

            - Rest 用户密码：步骤 4 中在先决条件 ([基本 ](#prerequisites-basic-authentication) 身份验证) \# 密码。

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image19.png" alt-text="图形用户界面，应用程序说明自动生成":::

        1. 返回并选择按钮以保存集成。

    1. 选择 **"下** 一步"完成集成。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image20.png" alt-text="自动生成的图形用户界面、应用程序、网站说明":::

10. \[ServiceNow 管理员启用Microsoft 365 \] 支持现有用户的集成。

    Microsoft 365仅对具有以下角色之一的用户启用支持集成：

    - x \_ mioms \_ m365 \_ assis.insights \_ 用户

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 角色为 x \_ mioms \_ m365 \_ assis.insights 的用户 \_ 可以看到服务运行状况事件、推荐解决方案。 角色为 x \_ mioms \_ m365 assis.administrator 的用户也可以打开一个支持Microsoft 365 \_ 案例。

11. \[可选 \] \[ 具有角色的用户x_mioms_m365_assis.administrator \] 链接Microsoft 365 管理帐户。

    如果任何用户具有角色 x \_ mioms \_ m365 assis.administrator，并且使用不同的 Microsoft 365 帐户来管理 Microsoft 365 支持案例，则必须转到 Microsoft 365 支持 > 链接帐户以设置其 \_ Microsoft 365 管理员电子邮件。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

## <a name="set-up-microsoft-365-support-integration-with-aad-oauth-token"></a>设置Microsoft 365支持与 AAD OAuth 令牌集成

### <a name="prerequisites-aad-oauth-token"></a>AAD OAuth (的先决条件) 

以下先决条件步骤是设置支持集成Microsoft 365所必需的：

1. \[可以创建 AAD 应用程序的人 在租户下为出站创建 \] AAD Microsoft 365应用程序。

    1. 使用租户[凭据](https://portal.azure.com/)Microsoft 365 Azure 门户。

    1. 转到" **应用注册"** 页并创建新的应用程序。

        Select **Accounts in this organizational directory only ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 添加重定向 `https://{your-servicenow-instance}.service-now.com/auth_redirect.do` URL：。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 获取应用程序的客户端 ID 并创建应用密码。

2. \[可以创建 AAD 应用程序的用户在租户租户下创建 AAD Microsoft 365 \] API。

    1. 使用你的[租户](https://portal.azure.com/)凭据Microsoft 365 Azure 门户。

    1. 转到 **应用注册并** 创建新应用程序。

        Select **Accounts in this organizational directory only ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image22.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 获取应用程序客户端 ID 并创建应用密码。

3. \[可以创建 AAD 应用程序的用户在租户租户下创建 \] AAD Microsoft 365用户。

    1. 使用你的[租户](https://portal.azure.com/)凭据Microsoft 365 Azure 门户。

    1. 转到" **应用注册"** 页并创建新的应用程序。
        
        Select **Accounts in this organizational directory only ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 获取应用程序客户端 ID 并创建应用密码。

4. \[ServiceNow 管理员人员 在 \] ServiceNow 中设置出站 OAuth 提供程序。

    1. 如果范围未设置为"全局"，请打开 **"设置**  >    >  **应用程序"以** 切换到"**全局"。**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

    1. 转到 **"系统""OAuth**  >  **应用程序注册表"。**

    1. 通过选择"向第三方 **OAuth** 提供程序连接值创建新的应用程序。

        - 客户端 ID：在步骤 1 的"先决条件 ([AAD OAuth 令牌 ](#prerequisites-aad-oauth-token)) \# 的客户端 ID。

        - 客户端密码：在 [AAD OAuth ](#prerequisites-aad-oauth-token) 令牌的先决条件 (步骤 1 中创建) \# 密码。

        - 默认授予类型：客户端凭据。

        - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

        - 重定向 URL： `https://{service-now-instance-name}.service-now.com/auth_redirect.do`

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

5. \[作为 ServiceNow 管理员 \] 的用户在 ServiceNow 中配置 OIDC 提供程序，请参阅 [联机文档](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    1. 如果范围未设置为"全局"，请打开 **"设置**  >    >  **应用程序"以** 切换到"**全局"。**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

    1. 转到 **"系统""OAuth**  >  **应用程序注册表"。**

    1. 选择 **"新建**  >  **新建开放 ID 连接提供程序"。**

    1. 在 **"OAuth OIDC 提供程序配置**"中，选择"搜索"，然后使用这些值在"oidc provider  \_ \_ configuration.list"下创建新的 OIDC 提供程序配置：

        - OIDC 提供程序：Contoso Azure

        - OIDC 元数据 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

        - UserClaim：appId 

        - 用户字段： **用户 ID**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image24.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

    1. 通过选择"配置 **OIDC** 提供程序以使用这些值验证 ID 令牌"来创建新应用程序：

        - 名称：contoso \_ 应用程序 \_ 入站 \_ api

        - 客户端 ID：在步骤 2 的"先决条件" ([AAD OAuth 令牌 ](#prerequisites-aad-oauth-token)) \# ID。

        - 客户端密码：在 [AAD OAuth ](#prerequisites-aad-oauth-token) 令牌的先决条件 (步骤 2 中创建) \# 密码。

        - OAuth OIDC 提供程序配置：在上一步中创建的 OIDC 提供程序。

        - 重定向 URL：  
            `https://{service-now-instance-name}.service-now.com/oauth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image25.png" alt-text="图形用户界面，自动生成应用程序说明":::

6. \[ServiceNow 管理员创建 \] 集成用户的用户。

    导航到  >  **"组织用户**"，以在没有集成用户时创建新用户。 用户 **ID** 的值是在步骤 [Prerequisites (AAD OAuth Token)](#prerequisites-aad-oauth-token) 3 中创建的应用程序客户端 \# ID

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image26.png" alt-text="图形用户界面，自动生成应用程序说明":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[可选 \] 允许服务的 IP 支持Microsoft 365集成

如果贵公司使用自己的策略限制 Internet 访问，请通过允许这些 IP 地址同时用于入站和出站 API 访问，为 Microsoft 365 服务启用网络访问以支持集成：

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> 此终端命令列出服务的所有活动 IP，Microsoft 365集成 *：nslookup* connector.rave.microsoft.com

### <a name="set-up-microsoft-365-support-integration"></a>设置Microsoft 365支持集成

可以在Microsoft 365下通过安装程序设置支持 **集成Microsoft 365应用程序**。

这些步骤是设置 ServiceNow 实例与服务支持之间的集成Microsoft 365所必需的。

1. \[ServiceNow 管理员将作用域切换为支持 \] Microsoft 365集成。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

2. \[ServiceNow 管理员人员 转到Microsoft 365 \] 支持>**安装程序** 以打开集成流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略，作用域 \_ 'x \_ mioms \_ m365 \_ assis'中的'oauth 实体的读取操作'被拒绝"，则由表访问策略导致。 必须确保已检查 **table** oauth 实体的所有应用程序  >  作用域"可读取 \_ "。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

3. \[ServiceNow 管理员选择" \] **同意** "以同意同意。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

4. \[ServiceNow 管理员人员 \] 设置出站 OAuth 提供程序。

    选择在先决条件 AAD OAuth 令牌 (步骤 4 中创建) [OAuth 提供程序的 OAuth](#prerequisites-aad-oauth-token) 配置文件 \# ，然后选择下一 **步**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

5. \[ServiceNow 管理员人员 \] 设置入站 OAuth 提供程序。

    1. 取消 **选中"跳过当前步骤"。**

    1. 检查 **外部 OIDC 身份验证令牌**。

    1. Select the OAuth Client created at [Prerequisites (AAD OAuth Token)](#prerequisites-aad-oauth-token) step 5， and then select **Next**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image28.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

6. \[ServiceNow 管理员人员 \] 设置入站呼叫集成用户。

    1. 取消 **选中"跳过当前步骤"。**

    1. 输入在先决条件 [AAD OAuth](#prerequisites-aad-oauth-token) 令牌 (步骤 3 中创建) \# 客户端 ID，然后选择下一 **步**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image39.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

7. \[ServiceNow 管理员人员 \] 设置存储库 ID。

    指定存储库 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

8. \[ServiceNow 管理员人员 \] 设置应用程序设置。

    选择以下设置，然后选择"下一 **步"。**

    - 具有 Microsoft 365 的 SSO：检查 ServiceNow 实例是否设置为 SSO Microsoft 365租户，否则取消选中它。

    - Microsoft 365管理员电子邮件：创建Microsoft 365案例时联系的管理员Microsoft 365电子邮件。

    - 测试环境：选中此框可指示测试阶段，以避免 Microsoft 支持代理联系你以解决问题。 如果你已准备好使用支持集成Microsoft 365，请取消选中此框。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

    1. 选择“**下一步**”。

9. \[作为租户中的支持管理员或服务请求管理员Microsoft 365完全 \] 集成。

    1. 检查以下信息以确保正确无误。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image40.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 转到"Microsoft 365 [门户](https://admin.microsoft.com)  >  **"设置"**  >  **组织设置**  >  **""组织配置文件"。**

    1. 设置支持集成设置。

        1. 在"基本信息"选项卡上，选择"现在服务"作为内部支持工具，在"步骤 - 6 完成集成"页上键入出站应用 ID 作为应用程序 **ID** 的值，该集成页是在先决条件 [ (AAD OAuth](#prerequisites-aad-oauth-token)令牌) 步骤 1 中创建的。 \#

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

        1. 在" **存储库"** 选项卡上， **选择"添加** 存储库"以创建包含以下信息的新存储库：

            - 存储库：使用"步骤 - 6 完成集成"页中的存储库 **ID** 值。

            - 终结点 **：Step** - 6 Complete the integration page中的 Endpoint 值。

            - 身份验证类型：选择 **AAD 身份验证**。

            - 客户端 ID："步骤 - 6 完成集成"页上的"客户端 **ID"** 值，它是在步骤 2 的"先决条件 ([AAD OAuth](#prerequisites-aad-oauth-token) 令牌) \# 客户端 ID。

            - Rest username： The **User Name** value on the Step - 6 Complete the integration page， which is the **Client ID** of the application created in [Prerequisites (AAD OAuth Token)](#prerequisites-aad-oauth-token) step \# 3.

            - Rest user password： The App Secret of the application created in [Prerequisites (AAD OAuth Token) ](#prerequisites-aad-oauth-token) step \# 3.

                :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image31.png" alt-text="图形用户界面，自动生成应用程序说明":::

        1. 返回并选择按钮以保存集成。

    1. 选择 **"下** 一步"完成集成。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image32.png" alt-text="图形用户界面，自动生成应用程序说明":::

10. \[ServiceNow 管理员启用Microsoft 365 \] 支持现有用户的集成。

    Microsoft 365仅对具有以下角色的用户启用支持集成：

    - x \_ mioms \_ m365 \_ assis.insights \_ 用户

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 角色为 x \_ mioms \_ m365 \_ assis.insights 的用户可以看到服务运行状况事件、 \_ 推荐解决方案。 角色为 x \_ mioms \_ m365 assis.administrator 的用户也可以打开一个支持Microsoft 365 \_ 案例。

11. **\[可选 \] \[ 具有角色的用户x_mioms_m365_assis.administrator Link \] Microsoft 365 管理 帐户**

    如果任何用户的角色为"x \_ mioms \_ m365 assis.administrator"，并且他们使用不同的 Microsoft 365 帐户来管理 Microsoft 支持案例，则必须转到 Microsoft 365 支持 > 链接帐户以设置其 \_ Microsoft 365 管理员电子邮件。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

## <a name="set-up-microsoft-365-support-integration-for-insights-only"></a>设置Microsoft 365仅支持Insights集成

### <a name="prerequisites-insights-only"></a>先决条件 (Insights仅) 

若要设置支持集成Microsoft 365先决条件步骤：

1. \[可以在你的租户下创建 AAD 应用程序Microsoft 365 \] 应用程序。

    1. 使用你的[租户](https://portal.azure.com/)凭据Microsoft 365 Azure 门户。

    1. 转到" **应用注册"** 页并创建新的应用程序。

        Select **Accounts in this organizational directory only ({microsoft-365-tenant-name} only – Single tenant**.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 添加重定向 URL： `https://{your-servicenow-instance}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 获取应用程序的客户端 ID 并创建应用密码。

1. \[ServiceNow 管理员人员 在 \] ServiceNow 中设置出站 OAuth 提供程序。

    1. 如果范围未设置为"全局"，请打开 **"设置**  >    >  **应用程序"以** 切换到"**全局"。**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

    1. 转到 **"系统""OAuth**  >  **应用程序注册表"。**

    1. 通过选择"向第三方 **OAuth** 提供程序连接值创建新的应用程序。

        - 客户端 ID：**仅在** 步骤 1 的"先决条件" (Insights [创建的)](#prerequisites-insights-only) \# ID

        - 客户端密码：在先决条件中创建的应用程序的应用密码 (Insights[步骤](#prerequisites-insights-only) \# 1) 密码

        - 默认授予类型：客户端凭据

        - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

        - 重定向 URL： `https://{servicenow-instance-name}.service-now.com/oauth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

### <a name="set-up-microsoft-365-support-integration"></a>设置Microsoft 365支持集成

可以在Microsoft 365下通过安装程序设置支持 **集成Microsoft 365应用程序**。

若要设置 ServiceNow 实例与 Microsoft 支持之间的集成，需要执行以下步骤。

1. \[ServiceNow 管理员将作用域切换为支持 \] Microsoft 365集成。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

2. \[ServiceNow 管理员人员 转到Microsoft 365 \] 支持>**安装程序** 以打开集成流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略，作用域 \_ 'x \_ mioms \_ m365 \_ assis'中的'oauth 实体的读取操作'被拒绝"，则由表访问策略导致。 必须确保已检查 **table** oauth 实体的所有应用程序  >  作用域"可读取 \_ "。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

3. \[ServiceNow 管理员选择" \] **同意** "以同意同意。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

4. \[ServiceNow 管理员人员 \] 设置出站 OAuth 提供程序。

    选择"出站 OAuth 提供程序的 OAuth 配置文件"，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

5. \[作为 ServiceNow 管理员的人跳过 \] 入站 OAuth 提供程序。

    选中 **"跳过当前步骤"，** 然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image33.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

6. \[作为 ServiceNow 管理员的人跳过 \] 集成用户。

    选中 **跳过当前步骤，** 然后选择下 **一步**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image34.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

7. \[ServiceNow 管理员人员 \] 设置存储库 ID。

    指定存储库 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

8. \[ServiceNow 管理员人员 \] 设置应用程序设置。

    选择正确的设置，然后选择下一 **步**。

    - 具有 Microsoft 365 的 SSO：检查 ServiceNow 实例是否设置为 SSO Microsoft 365租户;否则取消选中它。

    - Microsoft 365 管理电子邮件：创建Microsoft 365案例时要联系的管理员Microsoft 365电子邮件。

    - 测试环境：选中此框可指示测试阶段，以避免 Microsoft 支持代理联系你以解决问题。 如果你已准备好使用支持集成Microsoft 365，请取消选中此框。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

9. \[作为租户中的支持管理员或服务请求管理员Microsoft 365完全 \] 集成。

    1. 检查此处的信息以确保其正确无误。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image35.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 转到"Microsoft 365 [门户](https://admin.microsoft.com)  >  **"设置"**  >  **组织设置**  >  **""组织配置文件"。**

        1. 使用安装流中显示的信息设置支持集成设置。

        1. 在"**基本信息"** 选项卡上，选择"现在服务"作为内部支持工具，并键入 **出站应用 ID** 作为应用程序 ID 以颁发 OAuth 令牌。

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

        1. 在" **存储库"** 选项卡上， **选择"添加** 存储库"以创建包含以下信息的新存储库：

            - 存储库 **："步骤** - 6 完成集成"页中的存储库 ID 值。

            - 终结点 **：Step** - 6 Complete the integration page中的 Endpoint 值。

            - 身份验证类型：选择 **AAD 身份验证**。

            - 客户端 ID：随机值，例如 **忽略**。

            - Rest username： A random value， such as **ignored**.

            - Rest 用户密码：随机值，例如 **忽略**。

                :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image36.png" alt-text="图形用户界面，自动生成应用程序说明":::

        1. 返回并选择按钮以保存集成。

    1. 选择 **"下** 一步"完成集成。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image37.png" alt-text="图形用户界面，自动生成应用程序说明":::

10. \[ServiceNow 管理员启用Microsoft 365 \] 支持现有用户的集成。

    Microsoft 365仅为这些用户角色启用支持集成：

    - x \_ mioms \_ m365 \_ assis.insights \_ 用户

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE] 
    > 具有 x_mioms_m365_assis.insights_user 角色的用户可以看到服务运行状况事件、推荐解决方案。 具有 x_mioms_m365_assis.administrator 角色的用户也可以打开案例，Microsoft 365支持。 如果Insights，则不应为任何人分配x_mioms_m365_assis.administrator。

## <a name="testing-the-configuration"></a>测试配置

如果应用程序需要与外部系统成功通信，请概述如何测试连接以确保成功配置。

下面是测试支持集成Microsoft 365的步骤：

1. 以管理员状态登录到 ServiceNow 门户。

2. 打开任何事件。

3. 重点关注 **"Microsoft 365"** 选项卡，然后选择"Microsoft 365 Insights"确定建议的解决方案是否检索成功。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image38.png" alt-text="自动生成的图形用户界面、应用程序、网站说明":::

##  <a name="troubleshooting"></a>疑难解答

|#|问题|诊断操作|
|--- |--- |--- |
|1|看不到"支持 **Microsoft 365** 选项卡|使用筛选器验证 **当前视图和**  >  "全部系统日志x_mioms_m365_assit|
|2|选择 **Microsoft 推荐的解决方案** ，但收到错误"Please contact your ServiceNow admin and ask them to complete the setup steps for the app."|检查表单顶部的错误消息和"系统日志全部  >  "以及筛选器x_mioms_m365_assit|
|3|选择 **Microsoft 推荐的解决方案** ，但收到错误"Please contact your ServiceNow admin and ask them to complete the final set up step for the app."|检查表单顶部的错误消息和"系统日志全部  >  "以及筛选器x_mioms_m365_assit|
|4 |在搜索框中键入问题并选择 **Microsoft 建议** 的解决方案，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的设置步骤。"|检查表单顶部的错误消息和"系统日志全部  >  "以及筛选器x_mioms_m365_assit|
|5|在搜索框中键入问题并选择 **Microsoft 建议** 的解决方案，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的最终设置步骤。"|检查表单顶部的错误消息和"系统日志全部  >  "以及筛选器x_mioms_m365_assit|
|6 |选择 **"联系 Microsoft 支持** 人员"，但收到错误"Please contact your ServiceNow admin and ask them to complete the setup steps for the app."|检查表单顶部的错误消息和"系统日志全部"  >  以及筛选器x_mioms_m365_assit|
|7 |选择 **"联系 Microsoft 支持** 人员"，但收到错误"Please contact your ServiceNow admin and ask them to complete the final set up step for the app."|检查表单顶部的错误消息和"系统日志全部"  >  以及筛选器x_mioms_m365_assit|
|8 |选择 **"联系 Microsoft 支持** 人员"，但收到错误"{EmailAddress} 不是有效的Microsoft 365帐户。 您需要Microsoft 365管理员权限才能打开服务请求。 在应用中，链接管理员帐户。"|检查表单顶部的错误消息和"系统日志全部"  >  以及筛选器x_mioms_m365_assit|
|9 |选择 **Microsoft 建议的解决方案** ，但没有任何显示|检查 **系统日志 – 具有** 筛选器筛选器的出站 HTTP login.microsoftonline.com connector.rave.microsoft.com|
|10 |选择 **Microsoft 推荐的解决方案** ，但收到错误"请联系应用支持人员"。|检查表单顶部的错误消息和"系统日志全部"  >  以及筛选器x_mioms_m365_assit|
|11|在搜索框中键入问题，然后选择 **Microsoft 建议的解决方案** ，但不显示任何内容|检查 **系统日志 – 具有** 筛选器筛选器的出站 HTTP login.microsoftonline.com connector.rave.microsoft.com|
|12 |在搜索框中键入问题，然后选择 **Microsoft 建议的解决方案** ，但收到错误"请联系应用支持人员"。|检查表单顶部的错误消息和"系统日志全部"  >  以及筛选器x_mioms_m365_assit|
|13|用户选择" **联系 Microsoft 支持人员**"，但没有任何反应|检查 **系统日志 – 具有** 筛选器筛选器的出站 HTTP login.microsoftonline.com connector.rave.microsoft.com|
|14 |重新打开事件后看不到 Microsoft 建议的解决方案|使用 **筛选器检查**  >  **"系统** 日志全部x_mioms_m365_assit|
|15 |重新打开已转移到 Microsoft 支持人员的事件时看不到 Microsoft 案例|使用 **筛选器检查**  >  **"系统** 日志全部x_mioms_m365_assit|
|16|无法保存票证详细信息，收到错误"无法保存票证详细信息。 请联系应用支持人员。"|检查表单顶部的错误消息|
