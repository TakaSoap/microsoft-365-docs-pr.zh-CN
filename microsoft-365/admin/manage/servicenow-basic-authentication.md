---
title: 配置支持与 ServiceNow 集成 - 基本身份验证
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
ms.openlocfilehash: bd19e5fd72e2b21c7ec08e00497444475701817c
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754249"
---
# <a name="configure-support-integration-with-servicenow---basic-authentication"></a>配置支持与 ServiceNow 集成 - 基本身份验证

## <a name="prerequisites-basic-authentication"></a>基本 (的先决条件) 

这些必备组件是设置支持集成Microsoft 365 **所必需的**。

1. \[AAD管理员 \] 在 AAD 租户下创建Microsoft 365应用程序。

    1. 使用你的租户凭据Microsoft 365 Azure 门户，然后转到应用注册[页面](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)以创建新应用程序。

    1. Select Accounts in this organizational directory only **({Microsoft-365-tenant-name} only – Single tenant)** and select **Register**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 转到"**身份验证"，** 然后选择 **"添加平台"。** 选择 **"Web"** 选项并输入重定向 URL： `https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[ServiceNow 管理员 在 ServiceNow 中设置出站 \] OAuth 提供程序。

    如果范围未设置为"全局"，请转到"设置 **&gt; &gt; 应用程序"并** 切换到"**全局"。** 

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"。**

1. 通过使用"向第三方 **OAuth** 连接"选项并输入这些值，创建新的应用程序：

    - 客户端 ID：这是在步骤 1 中创建的应用程序的客户端 \# ID。

    - 客户端密码：这是步骤 1 中创建的应用程序的客户端密码 \# 值。

    - 默认授予类型：客户端凭据

    - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 重定向 URL： `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员 \] 设置入站 OAuth 提供程序。

    如果范围未设置为 **"** 全局"，则通过访问"开发人员应用程序"设置 **&gt; &gt; 切换到**"全局"来 **这样做**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"。**

1. 使用"为外部客户端创建 **OAuth API** 终结点"选项创建新应用程序。 命名入站 OAuth 提供程序，并保留所有其他字段的默认值。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image7.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image7.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员 \] 创建集成用户。

    必须指定集成用户。 如果没有现有集成用户，或者希望专门为此集成创建一个集成用户，请转到"组织用户"以创建新用户 **。 &gt;**

    如果要创建新的集成用户，请检查" **仅 Web 服务访问"** 选项。 还必须向此用户授予 **事件管理员 \_** 角色。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image8.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image8.png" alt-text="图形用户界面，自动生成应用程序说明":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL \] 允许服务的 IP 地址支持Microsoft 365集成

如果贵公司使用自己的策略限制 Internet 访问，请通过允许下面的 IP 地址同时用于入站和出站 API 访问，为 Microsoft 365 服务启用网络访问以支持集成：

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

1. \[ServiceNow 管理员 \] 将作用域 **切换到支持Microsoft 365集成。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

1. \[ServiceNow 管理员 \] 转到 **Microsoft 365 &gt; 支持安装程序以** 打开集成工作流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略，作用域 \_ 'x \_ mioms \_ m365 \_ assis'中的'oauth 实体的读取操作'被拒绝"，则由表访问策略导致。 必须确保已检查 **table &gt;** oauth 实体的所有应用程序作用域"可读取 \_ "。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image10.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image10.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 选择 **"同意** "继续。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 设置出站 OAuth 提供程序。

    Select the OAuth profile for Outbound OAuth Provider created in [Prerequisites (Basic Authentication) step \# 2](#prerequisites-basic-authentication) and select **Next**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 设置入站 OAuth 提供程序。

    1. 取消 **选中"跳过当前步骤"。**

    1. 取消 **选中"外部 OIDC 身份验证令牌"。**

    1. 选择在先决条件和基本 (中创建的 OAuth [) \# 步骤 3，](#prerequisites-basic-authentication)然后选择下一 **步**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image13.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image13.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 设置入站呼叫集成用户。

    1. 取消 **选中"跳过当前步骤"。**

    1. Select the integration user created in [Prerequisites (Basic Authentication) step \# 4](#prerequisites-basic-authentication)， and then select **Next**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image14.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image14.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[ServiceNow \] 管理员 设置存储库 ID。

    指定存储库 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[ServiceNow 管理员 \] 设置应用程序设置。

    选择以下设置，然后选择"下一 **步"。**

    - SSO with Microsoft 365： Check whether the ServiceNow instance is set up as SSO with Microsoft 365 tenants， otherwise uncheck it.

    - Microsoft 365管理员电子邮件：创建Microsoft 365案例时联系的管理员Microsoft 365电子邮件。

    - 测试环境：选中此框可指示测试阶段，以避免 Microsoft 支持代理联系你以解决问题。 如果你已准备好使用支持集成Microsoft 365，请取消选中此框。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[Microsoft 365租户管理员 \] 完成集成。

    验证以下信息是否正确。 此时不要 **选择"下** 一步"。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image17.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image17.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. 转到 **"Microsoft 365 管理门户 &gt; 设置 &gt; 组织设置 &gt; ""组织配置文件"。**

1. 配置支持集成设置：

    Select the **Basic information** tab > Internal **support tool**  >  **ServiceNow**， and enter the **Outbound App ID** value in the Application ID to issue **OAuth token** field. 此出站应用 ID 位于步骤 6 – 完成集成中，该集成是在步骤 [1 (基本身份验证) \# 中创建的](#prerequisites-basic-authentication)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 在" **存储库"** 选项卡上 **，选择"添加** 存储库"以使用这些设置创建新存储库：

    - 存储库：步骤 6 – 完成集成中的存储库 **ID** 值。

    - 终结点： **步骤** 6 – 完成集成中的 Endpoint 值。

    - 身份验证类型：选择 **"基本身份验证"。**

    - 客户端 ID： **步骤** 6 – 完成集成中的客户端 ID 值。

    - 客户端密码：在步骤 3 中的先决条件 (创建的入站 OAuth) \# 密码。

    - 刷新令牌过期：864000

    - Rest username: The **User Name** value from Step 6 – Complete the Integration.

    - Rest user password： The password of the integration user that was created in [Prerequisites (Basic Authentication) step \# 4](#prerequisites-basic-authentication).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image19.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image19.png" alt-text="图形用户界面，应用程序说明自动生成":::

1. 返回到 ServiceNow。

1. 选择 **"下** 一步"完成集成。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image20.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image20.png" alt-text="自动生成的图形用户界面、应用程序、网站说明":::

1. \[ServiceNow 管理员 \] 为现有用户启用 Microsoft 支持集成。

    Microsoft 365角色之一的用户启用支持集成：

    - x \_ mioms \_ m365 \_ assis.insights \_ 用户

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 角色为 x \_ mioms \_ m365 \_ assis.insights 的用户 \_ 可以看到服务运行状况事件、推荐解决方案。 角色为 x \_ mioms \_ m365 assis.administrator 的用户也可以打开一个支持Microsoft 365 \_ 案例。

1. \[OPTIONAL \] \[ 角色为 x \_ mioms \_ m365 \_ assis.administrator link \] Microsoft 365 管理 帐户的用户。

    如果任何用户具有角色 x \_ mioms \_ m365 \_ assis.administrator，并且使用不同的 Microsoft 365 帐户来管理 Microsoft 365 支持案例，则必须转到 Microsoft 365 支持 &gt; 链接帐户以设置其 Microsoft 365 管理员电子邮件。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::
