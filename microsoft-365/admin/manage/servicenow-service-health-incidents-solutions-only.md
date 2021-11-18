---
title: Microsoft 365服务运行状况事件和推荐解决方案集成
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
ms.openlocfilehash: b2676c05a4ee7767b40356852d32398f2d2c04a3
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071422"
---
# <a name="microsoft-365-support-integration-for-service-health-incidents-and-recommended-solutions-only"></a>Microsoft 365服务运行状况事件和推荐解决方案集成

此配置不允许通过 ServiceNow 实例创建 Microsoft 支持案例。 此选项仅提供服务运行状况事件信息和通过 ServiceNow 实例提供的建议解决方案。

## <a name="prerequisites-service-health-incidents-and-recommended-solutions-only"></a>服务 (事件的先决条件和仅建议的解决方案) 

这些必备组件是设置支持集成Microsoft 365 **所必需的**。

1. \[AAD管理员 \]在AAD租户下创建出站Microsoft 365应用程序。

    1. 使用你的租户凭据Microsoft 365 Azure 门户，在应用注册[页面上创建新应用程序](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)。

    2. Select **Accounts in this organizational directory only ({Microsoft-365-tenant-name} only – Single tenant)**， and then select **Register**.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 转到"**身份验证"，** 然后选择 **"添加平台"。** 选择 **"Web"** 选项并输入重定向 URL： `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 获取应用程序客户端 ID 并创建客户端密码并获取该值。

1. \[ServiceNow 管理员 在 ServiceNow 中设置出站 \] OAuth 提供程序。

    如果作用域未设置为"全局"，请转到 **"设置 &gt; &gt; 应用程序"并** 切换到"**全局"。** 

    :::image type="content" source="../../media/ServiceNow-guide/Servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/Servicenow-guide-image5.png" alt-text="自动生成的图形用户界面、文本、应用程序、聊天或短信说明":::

1. 转到 **"系统""OAuth &gt; 应用程序注册表"。**

1. 通过使用"向第三方 **OAuth** 连接"选项并输入这些值，创建新的应用程序：

    - 客户端 ID：这是在步骤 1 的"先决条件" (Insights创建的) \# ID。

    - 客户端密码：这是在步骤 1 的"先决条件" (Insights中创建) \# 密码值。

    - 默认授予类型：客户端凭据

    - 令牌 URL： `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 重定向 URL： `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="图形用户界面，自动生成应用程序说明":::

## <a name="configure-the-microsoft-365-support-integration-application"></a>配置Microsoft 365集成应用程序

可以在Microsoft 365下设置支持集成Microsoft 365应用程序。

若要设置 ServiceNow 实例与服务支持之间的集成，需要Microsoft 365这些步骤。

1. \[ServiceNow 管理员 \] 将作用域切换 **为Microsoft 365集成。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="图形用户界面，自动生成表说明":::

1. \[ServiceNow 管理员 \] 转到 **Microsoft 365 &gt; 支持安装程序以** 打开集成工作流。

    > [!NOTE]
    > 如果看到错误"由于表的跨作用域访问策略，作用域 \_ 'x \_ mioms \_ m365 \_ assis'中的'oauth 实体的读取操作'被拒绝"，则由表访问策略导致。 必须确保已检查 **table &gt;** oauth 实体的所有应用程序作用域"可读取 \_ "。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 选择 **"同意** "继续。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 设置出站 OAuth 提供程序。

    选择"出站 OAuth 提供程序"的 OAuth 配置文件，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. \[ServiceNow 管理员 \] 跳过入站 OAuth 提供程序。

    选中 **"跳过当前步骤"，** 然后选择"下一 **步"。**

1. \[ServiceNow 管理员 \] 跳过入站呼叫集成用户。

    选中 **"跳过当前步骤"，** 然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image34.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image34.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[ServiceNow \] 管理员 设置存储库 ID。

    指定存储库 ID，然后选择"下一 **步"。**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[ServiceNow 管理员 \] 设置应用程序设置。

    选择这些设置，然后选择"下一 **步"：**

    - 具有 Microsoft 365 的 SSO：检查 ServiceNow 实例是否设置为具有租户Microsoft 365 SSO，否则取消选中它。

    - Microsoft 365管理员电子邮件：创建Microsoft 365案例时联系的管理员Microsoft 365电子邮件。

    - 测试环境：选中此框可指示测试阶段，以避免 Microsoft 支持代理联系你以解决问题。 如果你已准备好使用支持集成Microsoft 365，请取消选中此框。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="自动生成的图形用户界面、文本、应用程序说明":::

1. \[Microsoft 365租户管理员 \]完成集成。

    验证以下信息是否正确。 此时不要 **选择"下** 一步"。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image35.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image35.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 转到 **"Microsoft 365 管理门户 &gt; 设置 &gt; 组织设置 &gt; ""组织配置文件"。**

1. 配置支持集成设置：

    Select the **Basic information** tab > Internal **support tool**  >  **ServiceNow**， and enter the **Outbound App ID** value in the Application ID to issue **OAuth token** field. 此出站应用 ID 位于步骤 6 – 完成集成中，该集成是在步骤[1 (Insights先决条件) \# 中创建的](#prerequisites-service-health-incidents-and-recommended-solutions-only)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="自动生成的图形用户界面、文本、应用程序、电子邮件说明":::

1. 在" **存储库"** 选项卡上，选择" **新建** 存储库"，然后使用下列设置更新它：

    - 存储库：步骤 6 – 完成集成中的存储库 **ID** 值。

    - 终结点： **步骤** 6 – 完成集成中的 Endpoint 值。

    - 身份验证类型：选择 **"AAD身份验证"。**

    - 客户端 ID：随机值 (示例：忽略) 。

    - Rest username： A random value (example： ignored) .

    - Rest 用户密码：随机值 (示例：忽略) 。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image36.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image36.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. 返回到 ServiceNow。

1. 选择 **"下** 一步"完成集成。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image37.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image37.png" alt-text="图形用户界面，自动生成应用程序说明":::

1. \[ServiceNow 管理员 \] 为现有用户启用 Microsoft 支持集成。

    Microsoft 365角色之一的用户启用支持集成：

    - x \_ mioms \_ m365 \_ assis.insights \_ 用户

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 角色为 x \_ mioms \_ m365 \_ assis.insights 的用户可以看到服务运行状况事件、 \_ 推荐解决方案。 角色为 x \_ mioms \_ m365 assis.administrator 的用户也可以打开一个Microsoft 365 \_ 案例。 对于Insights，不应为任何人分配角色 x \_ mioms \_ m365 \_ assis.administrator。
