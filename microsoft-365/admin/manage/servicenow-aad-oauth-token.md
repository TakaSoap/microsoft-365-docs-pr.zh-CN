---
title: 配置Microsoft 365身份验证令牌Azure AD集成
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: 9f9985e07989f168f9b27dde1c1d574813c3f349
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320895"
---
# <a name="configure-microsoft-365-support-integration-with-azure-ad-auth-token"></a>配置Microsoft 365身份验证令牌Azure AD集成

## <a name="prerequisites-azure-ad-auth-token"></a>身份验证 (Azure AD的先决条件) 

这些必备组件是设置支持集成Microsoft 365所必需的。

1. \[AAD管理员\]在Azure AD租户下为出站Microsoft 365应用程序。

    1. 使用你的租户凭据Microsoft 365 Azure 门户，然后转到应用注册[页面](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)以创建新应用程序。

    2. Select **Accounts in this organizational directory only ({Microsoft-365-tenant-name} only – Single tenant)** and select **Register**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 转到" **身份验证"** ，然后选择 **"添加平台"**。 选择 **"Web** "选项并输入重定向 URL： `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[AAD管理员\]在 Azure AD 租户下创建一个 rest Microsoft 365 API。

    1. 使用你的[租户凭据Microsoft 365](https://portal.azure.com/) Azure 门户，然后转到应用注册页面以创建新应用程序。

    1. 仅 **选择此组织目录中的帐户 { (Microsoft-365-tenant-name} – 单租户)**。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[AAD管理员\]在 Azure AD 租户下创建一个 rest Microsoft 365 应用程序。

    1. 使用你的[租户凭据Microsoft 365](https://portal.azure.com/) Azure 门户，然后转到应用注册页面以创建新应用程序。

    1. 仅 **选择此组织目录中的帐户 { (Microsoft-365-tenant-name} – 单租户)**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[ServiceNow 管理员\] 在 ServiceNow 中设置出站 OAuth 提供程序。

    如果范围未设置为 **"** 全局"，则通过导航到"开发人员设置并切换到"**全局" &gt; &gt;** 来 **这样做**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"**。

1. 使用"向第三连接 **OAuth 提供程序"选项创建新的** 应用程序并输入以下值：

    - 客户端 ID：这是在步骤 1 的先决条件 (Azure AD中创建的应用程序) \#ID。

    - 客户端密码：这是在步骤 1 中的先决条件 (Azure AD创建\#的应用程序) 密码值。

    - 默认授予类型：客户端凭据

    - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 重定向 URL： `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员\] 若要在 ServiceNow 中配置 OIDC 提供程序，请参阅 [联机文档](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    如果作用域未设置为 **"****&gt;全局"，请转到"设置应用程序&gt;"并** 切换到"**全局"**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"**。

1. 选择 **"新建**"，然后选择"**新建开放 ID 连接提供程序"**。

1. 在 **"OAuth OIDC 提供程序** 配置"中，选择"搜索"，然后使用这些值在 **oidcproviderconfiguration.list\_\_ 下创建新的 OIDC** 提供程序配置：

    - OIDC 提供程序： **{TenantName\_} Azure** (示例：Contoso Azure) 

    - OIDC 元数据 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim： **appid**

    - UserField： **用户 ID**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. 通过选择"配置 **OIDC 提供程序以使用这些值验证 ID** 令牌"来创建新应用程序：

    - 名称：**{TenantName\_}\_applicationinboundapi\_\_** (示例：contosoapplicationinboundapi\_\_\_) 

    - 客户端 ID：在步骤 2 中的先决条件 (Azure AD创建\#的应用程序) ID。

    - 客户端密码：在步骤 2 中的先决条件 (Azure AD创建的应用程序) \#密码。

    - OAuth OIDC 提供程序配置：在上一步中创建的 OIDC 提供程序

    - 重定向 URL： `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员\] 创建集成用户。

    必须指定集成用户。 如果没有现有集成用户 **&gt;**，或者希望专门为此集成创建一个集成用户，请转到"组织用户"以创建新用户。 用户 ID 的 **值为** 在系统必备组件和身份验证令牌 (Azure AD [中创建的应用程序)](#prerequisites-azure-ad-auth-token)。

    如果要创建新的集成用户，请检查" **仅 Web 服务访问"** 选项。 还必须向此用户授予 **incidentmanager\_** 角色。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="图形用户界面，自动生成应用程序说明":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL\] 允许服务的 IP 地址支持Microsoft 365集成

如果贵公司使用自己的策略限制 Internet 访问，请通过允许下面的 IP 地址同时用于入站和出站 API 访问，为 Microsoft 365 服务启用网络访问以支持集成。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> 此终端命令列出服务的所有活动 IP，Microsoft 365集成：`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>配置Microsoft 365集成应用程序

可以在Microsoft 365下设置支持集成Microsoft 365应用程序。

若要设置 ServiceNow 实例与服务支持之间的集成，需要Microsoft 365这些步骤。

1. \[ServiceNow 管理员\] 将作用域切换 **为Microsoft 365集成。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

1. \[ServiceNow 管理员\]转到 **Microsoft 365支持&gt;安装程序以** 打开集成工作流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略而被拒绝从作用域'xmiomsm365assis\_\_\_'对'oauthentity\_'执行读取操作"，则由表访问策略导致。 必须确保 **已检查 &gt; 表** oauthentity 的所有应用程序作用域"可\_读取"。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员\] **选择同意** 同意提示以继续。

    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-1.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-1.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员\] 配置环境和设置类型。
    如果此安装位于测试环境中，请选择选项"这是测试环境"。 在设置完成后，你将能够快速禁用此选项，并且稍后完成所有测试。
    如果实例允许对入站连接使用基本身份验证，请选择"是"，并参考 [基本身份验证设置过程](servicenow-basic-authentication.md)。 否则，请选择 **"否"** ，然后单击" **启动设置"**。 
      :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-2.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-2.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员\] 输入你的Microsoft 365租户域。
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-3.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员\] 配置出站 OAuth 提供程序。
    1. 配置出站 OAuth 提供程序。
    1. 完成先决条件部分中的说明后，单击"完成"。 否则，请按照向导中的说明操作，在 AAD。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-4.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::
    1. 注册 ServiceNow OAuth 应用。
    1. 完成先决条件部分中的说明后，选择新创建的 OAuth 应用程序注册并单击"下一步"。 否则，请按照说明在 ServiceNow 中创建实体，然后选择新的应用程序注册。
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-5.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-5.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员\] 配置入站设置。
    1. 配置入站AAD应用。
    1. 完成先决条件部分中的说明后，单击"完成"转到下一步。 否则，请按照说明为入站连接AAD应用注册。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-6.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-6.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::
    1. 配置 ServiceNow 外部 OpenID 连接提供程序 (OIDC 提供程序) 。
    1. 完成先决条件部分中的说明后，选择新创建的实体并单击"完成"。 否则，请按照说明在 ServiceNow 中创建实体，然后选择新的外部 OIDC 提供程序应用注册。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-7.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-7.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::
    1. 为入站AAD用户配置应用注册。
    1. 完成先决条件部分中的说明后，单击"完成"转到下一步。 否则，请按照说明为入站 REST 用户AAD应用注册 (集成) 。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-8.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-8.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::
    1. 配置集成用户。
    1. 完成先决条件部分中的说明后，选择新创建的实体并单击"下一步"。 否则按照说明在 ServiceNow 中创建集成用户，然后选择实体。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-9.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-9.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[Microsoft 365租户管理员\]完成集成。

    验证以下信息是否正确。 此时不要 **选择"下** 一步"。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 转到"**Microsoft 365 管理门户&gt;设置&gt;组织设置"&gt;"组织配置文件"**。

    1. 配置支持集成设置：

    Select the **Basic information** tab > **Internal support** **toolServiceNow** > ， and enter the **Outbound App ID** value in the **Application ID to issue Auth Token** field. 此出站应用 ID 位于"步骤 6 – 完成集成"中，该集成是在"身份验证令牌 (Azure AD[中创建) ](#prerequisites-azure-ad-auth-token)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

    1. 在" **存储库"** 选项卡上，选择" **新建** 存储库"，然后使用下列设置更新它：

    - 存储库："步骤 6 – 完成集成"中的存储库 **ID** 值。

    - 终结点： **"步骤** 6 – 完成集成"中的 Endpoint 值。

    - 身份验证类型：选择 **"AAD身份验证"**。

    - 客户端 ID：步骤 6 – 完成集成中的客户端 **ID** 值。

    - 客户端密码：在步骤 2 中的先决条件 (Azure AD创建的\#入站 OAuth) 密码。

    - Rest username： **The User Name** value from Step 6 – Complete the Integration， which is the **Client ID** of the application created in Prerequisites (Azure AD Auth Token) step \#3.

    - Rest user password： The App Secret of the application that was created in Prerequisites (Azure AD Auth Token) step \#3.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="图形用户界面，自动生成应用程序说明":::

    1. 返回到 ServiceNow。

    1. 选择 **"下** 一步"完成集成。

   :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-10.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-10.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::
    支持Microsoft 365应用将执行测试以确保集成正常工作。 如果配置有问题，则会显示一条错误消息，说明需要修复的问题。 否则，应用程序已准备就绪。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-11.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员\] 为现有用户启用 Microsoft 支持集成。

    Microsoft 365角色之一的用户启用支持集成：

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

1. \[OPTIONAL\] \[角色为 xmiomsm365assis.administrator\_\_\_ 链接\]Microsoft 365管理员帐户的用户。

    如果任何用户具有 xmiomsm365assis.administrator\_\_\_ 角色，并且使用不同的 Microsoft 365 帐户来管理 Microsoft 365 支持案例，则必须转到 Microsoft 365 支持&gt;链接帐户以设置其 Microsoft 365 管理员电子邮件。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::
