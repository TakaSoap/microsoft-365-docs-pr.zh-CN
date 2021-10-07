---
title: 部署连接器以存档 Twitter 数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置本机连接器，以将 Twitter 数据导入和存档到Microsoft 365。 在将数据导入Microsoft 365，您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的 Twitter 数据的管理。
ms.openlocfilehash: 478731bc2855b199888311377c21f09aac17fcf1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193443"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>部署连接器以存档 Twitter 数据

本文包含部署连接器的分步过程，该连接器使用 Office 365 导入服务将数据从组织的 Twitter 帐户导入到 Microsoft 365。 有关此过程的简要概述和部署 Twitter 连接器所需的先决条件列表，请参阅设置连接器以存档 Twitter [数据 ](archive-twitter-data-with-sample-connector.md)。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤 1：在 Azure Active Directory

1. 转到 <https://portal.azure.com> ，然后使用全局管理员帐户的凭据登录。

   ![登录到 Azure。](../media/TCimage01.png)

2. 在左侧导航窗格中，单击 **Azure Active Directory**。

   ![转到Azure Active Directory。](../media/TCimage02.png)

3. 在左侧导航窗格中，单击"应用注册 (**预览**) 然后单击"新建 **注册"。**

   ![创建新的应用注册。](../media/TCimage03.png)

4. 注册应用程序。 Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.

   ![键入 https://portal.azure.com 重定向 URI。](../media/TCimage04.png)

5. 复制 **应用程序 (客户端) ID (** Directory) **ID，并将其** 保存到文本文件或其他安全位置。 在稍后的步骤中使用这些 ID。

    ![复制并保存应用程序 ID 和目录 ID。](../media/TCimage05.png)

6. 转到"**证书&应用密码"，在**"客户端密码"下单击"**新建客户端密码"。**

   ![创建新的客户端密码。](../media/TCimage06.png)

7. 创建新密码。 在说明框中，键入密码，然后选择过期期限。

   ![键入密码并选择过期期限。](../media/TCimage08.png)

8. 复制密码的值并将其保存到文本文件或其他存储位置。 这是在稍后的步骤中使用的 AAD 应用程序密码。

   ![复制并保存密码。](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>步骤 2：将连接器 Web 服务从 GitHub部署到 Azure 帐户

1. 转到此 [GitHub站点，](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)然后单击 **"部署到 Azure"。**

    ![转到 Azure 主页。](../media/FBCimage11.png)

2. 单击" **部署到 Azure"** 后，你将重定向到具有自定义模板页面的 Azure 门户。 填写基本 **信息并****设置详细信息**，**然后单击购买。**

   ![单击"创建资源并键入存储帐户"。](../media/FBCimage12.png)

    - **订阅：** 选择要将 Twitter 连接器 Web 服务部署到的 Azure 订阅。

    - **资源组：** 选择或创建新的资源组。 资源组是存储 Azure 解决方案相关资源的容器。

    - **位置：** 选择一个位置。

    - **Web 应用名称：** 为连接器 Web 应用提供唯一的名称。 名称长度必须在 3 到 18 个字符之间。 此名称用于创建 Azure 应用服务 URL;例如，如果你提供 **twitterconnector** 的 Web 应用名称，则 Azure 应用服务 URL **将** twitterconnector.azurewebsites.net。

    - **tenantId：** 在步骤 1 Microsoft 365 Azure Active Directory 中创建 Facebook 连接器应用后复制的组织租户 ID。

   - **APISecretKey：** 你可以键入任何值作为密码。 这用于访问步骤 5 中的连接器 Web 应用。

3. 部署成功后，页面将类似于以下屏幕截图：

    ![单击存储"，然后单击"存储帐户"。](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>步骤 3：创建 Twitter 应用

1. 转到 https://developer.twitter.com ，使用组织的开发人员帐户凭据登录，然后单击应用 。 

   ![转到 https://developer.twitter.com 并登录。](../media/TCimage25-5.png)
2. 单击 **"创建应用"。**

   ![转到应用页面以创建应用。](../media/TCimage26.png)

3. 在 **"应用程序详细信息**"下，添加有关应用程序的信息。

   ![输入有关应用的信息。](../media/TCimage27.png)

4. 在 Twitter 开发人员仪表板上，选择你刚刚创建的应用， **然后单击详细信息**。

   ![复制并保存应用 ID。](../media/TCimage28.png)

5. 在" **密钥和令牌** "选项卡上的"使用者 **API** 密钥"下，复制 API 密钥和 API 密钥，并将其保存到文本文件或其他存储位置。 然后单击 **"创建** "以生成访问令牌和访问令牌密码，然后将这些密钥复制到文本文件或其他存储位置。

   ![复制并保存到 API 密钥。](../media/TCimage29.png)

   然后单击 **"创建** "以生成访问令牌和访问令牌密码，然后将这些密钥复制到文本文件或其他存储位置。

6. 单击 **"权限"** 选项卡并配置权限，如以下屏幕截图所示：

   ![配置权限。](../media/TCimage30.png)

7. 保存权限设置后，单击"应用详细信息 **"选项卡，** 然后单击"编辑>**编辑详细信息"。**

   ![编辑应用详细信息。](../media/TCimage31.png)

8. 执行以下任务：

   - 选中复选框以允许连接器应用登录到 Twitter。

   - 采用以下格式添加 OAuth 重定向 **Uri：/Views/TwitterOAuth， \<connectorserviceuri>** 其中 *connectorserviceuri* 的值为组织的 Azure 应用服务 URL;例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth 。

    ![允许连接器应用登录 Twitter 并添加 OAuth 重定向 Uri。](../media/TCimage32.png)

Twitter 开发人员应用现在可供使用。

## <a name="step-4-configure-the-connector-web-app"></a>步骤 4：配置连接器 Web 应用

1. 转到 https:// \<AzureAppResourceName> .azurewebsites.net (，其中 **AzureAppResourceName** 是你在步骤 4) 中命名的 Azure 应用资源的名称。 例如，如果名称为 **twitterconnector**，请转到 https://twitterconnector.azurewebsites.net 。 应用程序的主页类似于以下屏幕截图：

   ![转到 Azure 应用资源页面。](../media/FBCimage41.png)

2. 单击 **"** 配置"显示登录页。

   ![单击"配置"显示登录页。](../media/FBCimage42.png)

3. 在"租户 ID"框中，键入或粘贴 (步骤 2 中获取的租户 ID) 。 在密码框中，键入或粘贴在步骤 2) 获取的 APISecretKey (，然后单击"设置配置 **设置"** 以显示配置详细信息页。

   ![使用租户 ID 和 API 密钥登录。](../media/TCimage35.png)

4. 输入以下配置设置

   - **Twitter Api 密钥：** 你在步骤 3 中创建的 Twitter 应用程序的 API 密钥。

   - **Twitter Api 密钥：** 你在步骤 3 中创建的 Twitter 应用程序的 API 密钥。

   - **Twitter 访问令牌：** 在步骤 3 中创建的访问令牌。

   - **Twitter 访问令牌密码：** 在步骤 3 中创建的访问令牌密码。

   - **AAD 应用程序 ID：** 在步骤 1 中创建Azure Active Directory应用程序的应用程序 ID

   - **AAD 应用程序密码：** 在步骤 1 中创建的 APISecretKey 密码的值。

5. 单击 **"保存** "以保存连接器设置。

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>步骤 5：在 Microsoft 365 合规中心

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击左侧 **导航中的** "数据连接器"。

2. 在"**数据连接器"页面上** 的 **Twitter 下**，单击"查看 **"。**

3. 在 **Twitter 页面上**，单击"添加 **连接器"。**

4. 在"**服务条款"页上**，单击"接受 **"。**

5. 在"**为连接器应用程序添加** 凭据"页上，输入以下信息，然后单击"验证 **连接"。**

   ![输入连接器应用凭据。](../media/TCimage38.png)

    - 在 **"名称** &quot;框中，键入连接器的名称，例如 Twitter **帮助处理**。

    - 在&quot; **连接器 URL&quot;** 框中，键入或粘贴 Azure 应用服务 URL;例如 `https://twitterconnector.azurewebsites.net` 。

    - 在 **&quot;密码** &quot;框中，键入或粘贴在步骤 2 中创建的 APISecretKey 的值。

    - 在 **&quot;Azure 应用 ID&quot;** 框中，键入或粘贴 Azure 应用程序应用 ID (也称为&quot;客户端 *ID")* 在步骤 1 中获取的值。

6. 成功验证连接后，单击"下一 **步"。**

7. 在"**授权Microsoft 365数据"** 页上，再次键入或粘贴 APISecretKey，然后单击"登录 Web **应用"。**

8. 单击 **"使用 Twitter 登录"。**

9. 在 Twitter 登录页面上，使用组织的 Twitter 帐户的凭据登录。

   ![登录到 Twitter 帐户。](../media/TCimage42.png)

   登录后，Twitter 页面将显示以下消息"Twitter 连接器作业已成功设置"。

10. 单击 **"** 继续"完成 Twitter 连接器的设置。

11. 在 **"设置筛选器** "页上，可以应用筛选器以初始导入具有特定年龄的项目。 选择一个年龄，然后单击下一 **步**。

12. 在"**选择存储位置**"页上，Microsoft 365 Twitter 项目将导入到的邮箱的电子邮件地址，然后单击"下一步 **"。**

13. 单击 **"下** 一步"查看连接器设置，然后单击" **完成** "以完成连接器设置。

14. 在合规中心，转到 **"数据连接器**"页，然后单击"连接器"选项卡以查看导入过程的进度。
