---
title: 配置 Microsoft 365 支持与 AAD OAuth 令牌集成
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
ms.openlocfilehash: da241452f989ba5f682fd3219e3f3baabf623138
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071446"
---
# <a name="configure-microsoft-365-support-integration-with-aad-oauth-token"></a>配置 Microsoft 365 支持与 AAD OAuth 令牌集成

## <a name="prerequisites-aad-oauth-token"></a>OAuth (AAD的先决条件) 

这些必备组件是设置支持集成Microsoft 365所必需的。

1. \[AAD管理员 \]在AAD租户下创建出站Microsoft 365应用程序。

    1. 使用你的租户凭据Microsoft 365 Azure 门户，然后转到应用注册[页面](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)以创建新应用程序。

    2. Select **Accounts in this organizational directory only ({Microsoft-365-tenant-name} only – Single tenant)** and select **Register**.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 转到"**身份验证"，** 然后选择 **"添加平台"。** 选择 **"Web"** 选项并输入重定向 URL： `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[AAD管理员 \]在 AAD 租户下创建 Rest API Microsoft 365应用程序。

    1. 使用你的[租户凭据Microsoft 365](https://portal.azure.com/) Azure 门户，然后转到应用注册页面以创建新应用程序。

    1. 仅 **选择此组织目录中的帐户 { (Microsoft-365-tenant-name} – 单租户) 。**

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[AAD管理员 \]在 AAD 租户下创建一个 Rest Microsoft 365 应用程序。

    1. 使用你的[租户凭据Microsoft 365](https://portal.azure.com/) Azure 门户，然后转到应用注册页面以创建新应用程序。

    1. 仅 **选择此组织目录中的帐户 { (Microsoft-365-tenant-name} – 单租户) 。**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[ServiceNow 管理员 在 ServiceNow 中设置出站 \] OAuth 提供程序。

    如果范围未设置为 **"** 全局"，则通过导航到"开发人员设置 **&gt; &gt; 并** 切换到"全局"来 **完成。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"。**

1. 使用"向第三连接 **OAuth 提供程序创建** 一个新应用程序"选项并输入以下值：

    - 客户端 ID：这是在步骤 1 中的先决条件 (AAD OAuth 令牌) \# ID。

    - 客户端密码：这是在步骤 1 的先决条件 (AAD OAuth 令牌) \# 客户端密码值。

    - 默认授予类型：客户端凭据

    - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 重定向 URL： `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员 \] 若要在 ServiceNow 中配置 OIDC 提供程序，请参阅 [联机文档](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    如果作用域未设置为"全局"，请转到 **"设置 &gt; &gt; 应用程序"并** 切换到"**全局"。** 

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"。**

1. 选择 **"新建**"，然后选择"新建开放 **ID 连接提供程序"。**

1. 在 **"OAuth OIDC 提供程序配置**"中，选择"搜索"，然后使用这些值在 **oidc \_ 提供程序 \_ configuration.list** 下创建新的 OIDC 提供程序配置： 

    - OIDC 提供程序 **：{租户 \_ 名称} Azure** (示例：Contoso Azure) 

    - OIDC 元数据 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim：appId 

    - UserField： **用户 ID**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. 通过选择"配置 **OIDC** 提供程序以使用这些值验证 ID 令牌"来创建新应用程序：

    - 名称 **：{Tenant \_ Name} \_ \_ 应用程序入站 \_ api** (示例：contoso \_ 应用程序 \_ 入站 api \_) 

    - 客户端 ID：在步骤 2 的"先决条件" (AAD创建的应用程序) \# ID。

    - 客户端密码：在步骤 2 中基于 OAuth 令牌的先决条件 (AAD应用程序) \# 密码。

    - OAuth OIDC 提供程序配置：在上一步中创建的 OIDC 提供程序

    - 重定向 URL： `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员 \] 创建集成用户。

    必须指定集成用户。 如果没有现有集成用户，或者希望专门为此集成创建一个集成用户，请转到"组织用户"以创建新用户 **。 &gt;** 用户 ID **的值是在步骤** 3 的先决条件 (AAD OAuth 令牌) 客户端 [ \# ID。](#prerequisites-aad-oauth-token)

    如果要创建新的集成用户，请检查"仅 Web **服务访问"** 选项。 还必须向此用户授予 **事件管理员 \_** 角色。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="图形用户界面，自动生成应用程序说明":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL \] 允许服务的 IP 地址支持Microsoft 365集成

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

1. \[ServiceNow 管理员 \] 将作用域切换 **为Microsoft 365集成。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

1. \[ServiceNow 管理员 \] 转到 **Microsoft 365 &gt; 支持安装程序以** 打开集成工作流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略，作用域 \_ 'x \_ mioms \_ m365 \_ assis'中的'oauth 实体的读取操作'被拒绝"，则由表访问策略导致。 必须确保已检查 **table &gt;** oauth 实体的所有应用程序作用域"可读取 \_ "。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] **选择同意** 同意提示以继续。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 设置出站 OAuth 提供程序。

    Select the OAuth profile for Outbound OAuth Provider created in [Prerequisites (AAD OAuth Token) step \# 4](#prerequisites-aad-oauth-token)， and then select **Next**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 设置入站 OAuth 提供程序。

    1. 取消 **选中"跳过当前步骤"。**

    1. 检查 **外部 OIDC 身份验证令牌**。

    1. Select the OAuth Client created in [Prerequisites (AAD OAuth Token) step \# 5](#prerequisites-aad-oauth-token)， and then select **Next**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image28.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image28.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[ServiceNow 管理员 \] 设置入站呼叫集成用户。

    1. 取消 **选中"跳过当前步骤"。**

    1. 在步骤 [ \# 3](#prerequisites-aad-oauth-token)中输入在先决条件 (AAD OAuth 令牌) 创建的应用程序的客户端 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image39.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image39.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow \] 管理员 设置存储库 ID。

    指定存储库 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[ServiceNow 管理员 \] 设置应用程序设置。

    选择以下设置，然后选择"下一 **步"。**

    - 具有 Microsoft 365 的 SSO：检查 ServiceNow 实例是否设置为具有租户Microsoft 365 SSO，否则取消选中它。

    - Microsoft 365管理员电子邮件：创建Microsoft 365案例时联系的管理员Microsoft 365电子邮件。

    - 测试环境：选中此框可指示测试阶段，以避免 Microsoft 支持代理联系你以解决问题。 如果你已准备好使用支持集成Microsoft 365，请取消选中此框。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[Microsoft 365租户管理员 \]完成集成。

    验证以下信息是否正确。 此时不要 **选择"下** 一步"。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 转到 **"Microsoft 365 管理门户 &gt; 设置 &gt; 组织设置 &gt; ""组织配置文件"。**

1. 配置支持集成设置：

    Select the **Basic information** tab > Internal **support tool**  >  **ServiceNow**， and enter the **Outbound App ID** value in the Application ID to issue **OAuth token** field. 此出站应用 ID 位于步骤 6 – 完成集成中，该集成是在步骤 1 中的先决条件[ (AAD OAuth 令牌) \# 中创建的](#prerequisites-aad-oauth-token)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 在" **存储库"** 选项卡上，选择" **新建** 存储库"，然后使用下列设置更新它：

    - 存储库："步骤 6 – 完成集成"中的存储库 **ID** 值。

    - 终结点 **："步骤** 6 – 完成集成"中的 Endpoint 值。

    - 身份验证类型：选择 **"AAD身份验证"。**

    - 客户端 ID： **步骤** 6 – 完成集成中的客户端 ID 值。

    - 客户端密码：在步骤 2 中的先决条件 (AAD OAuth 令牌) \# 密码。

    - Rest username： **The User Name** value from Step 6 – Complete the Integration， which is the Client **ID** of the application created in Prerequisites (AAD OAuth Token) step \# 3.

    - Rest user password： The App Secret of the application that was created in Prerequisites (AAD OAuth Token) step \# 3.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. 返回到 ServiceNow。

1. 选择 **"下** 一步"完成集成。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image32.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image32.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员 \] 为现有用户启用 Microsoft 支持集成。

    Microsoft 365角色之一的用户启用支持集成：

    - x \_ mioms \_ m365 \_ assis.insights \_ 用户

    - x \_ mioms \_ m365 \_ assis.administrator

1. \[OPTIONAL \] \[ 角色为 x \_ mioms \_ m365 \_ assis.administrator link \] Microsoft 365管理员帐户的用户。

    如果任何用户具有角色 x \_ mioms \_ m365 \_ assis.administrator，并且使用不同的 Microsoft 365 帐户来管理 Microsoft 365 支持案例，则必须转到 Microsoft 365 支持 &gt; 链接帐户以设置其 Microsoft 365 管理员电子邮件。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::
