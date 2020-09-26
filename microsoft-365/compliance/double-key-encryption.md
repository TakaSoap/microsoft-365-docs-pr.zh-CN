---
title: " (DKE) 的双重密钥加密"
description: DKE 使您能够保护高度敏感的数据，同时保持对密钥的完全控制。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 39d7933014f1dc71f8c94e467954d36ede4fb451
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277529"
---
# <a name="double-key-encryption-for-microsoft-365"></a>适用于 Microsoft 365 的双重密钥加密

> *适用于：针对 Microsoft 365 的双重密钥加密， [microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management)， [Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *说明： [Azure 信息保护统一标签客户端 For Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *服务说明： [Microsoft 365 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

双密钥加密 (DKE) 将两个键一起使用，以访问受保护的内容。 Microsoft 在 Microsoft Azure 中存储一个密钥，并保留另一个密钥。 您可以使用双重密钥加密服务来维护对某个密钥的完全控制。 您可以使用 Azure 信息保护统一标记客户端对高度敏感的内容应用保护。

双密钥加密支持云和本地部署。 这些部署有助于确保在任何位置存储受保护的数据时，加密的数据保持不透明。

有关默认的基于云的租户根密钥的详细信息，请参阅 [规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。

## <a name="when-your-organization-should-adopt-dke"></a>您的组织应采用 DKE

双密钥加密适用于受最严格的保护要求的敏感数据。 DKE 并非适用于所有数据。 通常情况下，将使用双密钥加密来保护您的总体数据的一部分。 在部署之前，应努力确定要与此解决方案一起涵盖的正确数据。 在某些情况下，您可能需要缩小范围，并对大部分数据（如 Microsoft 管理的密钥或 BYOK 的 Microsoft 信息保护）使用其他解决方案。 这些解决方案足以满足不受增强的保护和法规要求的文档。 此外，这些解决方案使您能够使用最强大的 Office 365 服务;您不能与 DKE 加密内容一起使用的服务。 例如：

- 传输规则，包括需要查看附件的反恶意软件和垃圾邮件
- Microsoft Delve
- 电子数据展示
- 内容搜索和索引
- Office Web Apps 包括共同创作功能

任何未与 DKE 集成在 MIP SDK 中的外部应用程序或服务将无法对加密数据执行操作。

Microsoft Information Protection SDK 1.7 + 支持双密钥加密;与我们的 SDK 集成的应用程序将能够通过适当的权限和集成来导致此数据的原因。

我们建议组织使用 Microsoft 信息保护功能 (分类和标签) 保护其大部分敏感数据，并仅将 DKE 用于其任务关键型数据。 双密钥加密尤其适用于高度管控行业（如金融服务业和医疗保健行业）中的极其敏感的数据。

如果您的组织有以下任一要求，您可以使用 DKE 帮助保护您的内容：

- 您希望确保 *只有* 在所有情况下都可以对受保护的内容进行解密。
- 您不希望 Microsoft 能够单独访问受保护的数据。
- 您有管理法规要求，可在地理边界内保留密钥。 您为数据加密和解密而保留的所有密钥都将保留在您的数据中心中。

## <a name="system-and-licensing-requirements-for-dke"></a>DKE 的系统和许可要求

Microsoft 365 E5 和 Office 365 E5 提供了**适用于 microsoft 365 的双重密钥加密**。 如果你没有 Microsoft 365 E5 许可证，你可以注册 [试用版](https://aka.ms/M365E5ComplianceTrial)。 有关这些许可证的详细信息，请参阅 [适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

**Azure 信息保护**。 DKE 使用灵敏度标签，需要 Azure 信息保护。

通过 Office 桌面应用程序中的灵敏度功能区，最终用户可以使用 DKE 敏感度标签。 在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。

**适用于企业版的 Microsoft Office 应用** 版本12711或更高版本 (Windows 上的 Word、PowerPoint 和 Excel) 的桌面版本。

**Azure 信息保护统一标签客户端** 版本2.7.93.0 或更高版本。 从 [Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载并安装统一的标签客户端。

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>用于存储和查看受 DKE 保护的内容的受支持的环境

**支持的应用程序**。 Windows 上[的适用于企业客户端的 Microsoft 365 应用程序](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)，包括 Word、Excel 和 PowerPoint。

**在线内容支持**。 支持在 Microsoft SharePoint 和 OneDrive for Business 中联机存储的文档和文件。 您可以通过电子邮件共享加密内容，但不能联机查看加密的文档和文件。 相反，您必须使用本地计算机上的桌面应用程序查看受保护的内容。

## <a name="overview-of-deploying-dke"></a>部署 DKE 概述

您将按照以下常规步骤设置 DKE。 完成这些步骤后，最终用户将能够使用双密钥加密来保护高度敏感的数据。

1. 部署 DKE 服务，如本文中所述。

2. 创建带双密钥加密的标签。 导航到 [Microsoft 365 合规性中心](https://compliance.microsoft.com) 下的信息保护，并创建带双密钥加密的新标签。 请参阅 [使用敏感度标签限制对内容的访问，以应用加密](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。

3. 使用双密钥加密标签。 通过在 Microsoft Office 中的 "敏感度" 功能区中选择 "双密钥加密" 标签来保护数据。

有几种方法可以完成一些部署双密钥加密的步骤。 本文提供了详细说明，以便让经验较少的管理员能够成功部署服务。 如果你愿意，可以选择使用自己的方法。

## <a name="deploy-dke"></a>部署 DKE

本文和部署视频使用 Azure 作为 DKE 服务的部署目标。 如果要部署到其他位置，则需要提供自己的值。

观看 " [双重密钥加密部署" 视频](https://youtu.be/vDWfHN_kygg) ，以查看本文中的概念的分步概述。 完成该视频需要18分钟左右。

您将按照这些常规步骤为您的组织设置双密钥加密。

1. [安装 DKE 服务的必备软件](#install-software-prerequisites-for-the-dke-service)
1. [克隆双密钥加密 GitHub 存储库](#clone-the-dke-github-repository)
1. [修改应用程序设置](#modify-application-settings)
1. [生成测试键](#generate-test-keys)
1. [生成项目](#build-the-project)
1. [部署 DKE 服务并发布密钥存储区](#deploy-the-dke-service-and-publish-the-key-store)
1. [验证部署](#validate-your-deployment)
1. [注册密钥存储](#register-your-key-store)
1. [使用 DKE 创建敏感度标签](#create-sensitivity-labels-using-dke)
1. [在客户端中启用 DKE](#enable-dke-in-your-client)
1. [将受保护的文件从 HYOK 标签迁移到 DKE 标签](#migrate-protected-files-from-hyok-labels-to-dke-labels)

完成后，您可以使用 DKE 对文档和文件进行加密。 有关信息，请参阅 [将敏感度标签应用于 Office 中的文件和电子邮件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。

### <a name="install-software-prerequisites-for-the-dke-service"></a>安装 DKE 服务的必备软件

在要安装 DKE 服务的计算机上安装这些必备组件。

**.Net Core 3.1 SDK**。 从 [下载 .Net Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)下载并安装 SDK。

**Visual Studio Code**。 从下载 Visual Studio Code [https://code.visualstudio.com/](https://code.visualstudio.com) 。 安装完成后，运行 Visual Studio Code 并选择 " **查看** \> **扩展**"。 安装这些扩展。

- Visual Studio Code 的 c #

- NuGet 包管理器

**Git 资源**。 下载并安装以下各项之一。

- [Git](https://git-scm.com/downloads)

- [GitHub 桌面](https://desktop.github.com/)

- [GitHub 企业](https://github.com/enterprise)

**OpenSSL** 您必须安装了 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) ，才能在部署 DKE 后 [生成测试密钥](#generate-test-keys) 。 请确保您从环境变量路径中正确调用了它。 例如，有关详细信息，请参阅 "将安装目录添加到路径" [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) 。

### <a name="clone-the-dke-github-repository"></a>克隆 DKE GitHub 存储库

Microsoft 提供 GitHub 存储库中的 DKE 源文件。 克隆存储库，以在本地为组织的使用生成项目。 DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。

以下说明适用于缺乏的 git 或 Visual Studio Code users：

1. 在浏览器中，转到： [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。

2. 在屏幕右侧，选择 " **代码**"。 您的 UI 版本可能会显示 " **克隆" 或 "下载** " 按钮。 然后，在出现的下拉列表中，选择 "复制" 图标将 URL 复制到剪贴板。

    例如：

   ![从 GitHub 克隆双密钥加密服务存储库](../media/dke-clone.png)

3. 在 Visual Studio Code 中，选择 " **查看** \> **命令选项板** "，然后选择 " **Git： Clone**"。 若要跳转到列表中的选项，请开始键入 `git: clone` 以筛选条目，然后从下拉列表中进行选择。 例如：

   ![Visual Studio Code GIT： Clone 选项](../media/dke-vscode-clone.png)

4. 在文本框中，粘贴从 Git 复制的 URL，然后 **从 GitHub 中**选择 "复制"。

5. 在出现的 " **选择文件夹** " 对话框中，浏览并选择存储库的位置。 在提示符下，选择 " **打开**"。

    存储库将在 Visual Studio Code 中打开，并在左下角显示当前 Git 分支。 分支应为 **master**。

    例如：

   ![Visual Studio Code master 分支](../media/dke-vscode-master.png)

6. 从分支列表中选择 "word **母版** "。

   > [!IMPORTANT]
   > 选择主分支可确保您具有用于生成项目的正确文件。 如果不选择正确的分支，部署将会失败。

现在，你已在本地设置了 DKE 源存储库。 接下来，修改您的组织的 [应用程序设置](#modify-application-settings) 。

### <a name="modify-application-settings"></a>修改应用程序设置

若要部署 DKE 服务，必须修改以下类型的应用程序设置：

- [密钥访问设置](#key-access-settings)
- [租户和密钥设置](#tenant-and-key-settings)

您可以在 appsettings.js的文件中修改应用程序设置。 此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store。 例如，在 Visual Studio Code 中，可以按下图所示浏览到文件。

![为 DKE 查找文件上的 appsettings.js。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>密钥访问设置

选择是否使用电子邮件或角色授权。 DKE 一次仅支持其中一种身份验证方法。

- **电子邮件授权**。 允许您的组织仅基于电子邮件地址授权访问密钥。

- **角色授权**。 允许您的组织根据 Active Directory 组授权对密钥的访问，并要求 web 服务可以查询 LDAP。

**使用电子邮件授权设置 DKE 的密钥访问设置**

1. 打开文件 ** 上** 的 "appsettings.js" 并找到相应的 `AuthorizedEmailAddress` 设置。

2. 添加要授权的电子邮件地址。 用双引号和逗号分隔多个电子邮件地址。 例如：

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 找到 `LDAPPath` 设置并删除 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 双引号之间的文本。 将双引号括起来。 完成后，设置应如下所示。

   ```json
   "LDAPPath": ""
   ```

4. 找到 `AuthorizedRoles` 设置并删除整行。

此图显示了为电子邮件授权正确设置格式的文件 ** 上的appsettings.js** 。

   ![对文件显示电子邮件授权方法的 appsettings.js](../media/dke-email-accesssetting.png)

**使用角色授权设置 DKE 的密钥访问设置**

1. 打开文件 ** 上** 的 "appsettings.js" 并找到相应的 `AuthorizedRoles` 设置。

2. 添加要授权的 Active Directory 组名称。 用双引号和逗号分隔多个组名称。 例如：

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. 找到 `LDAPPath` 设置并添加 Active Directory 域。 例如：

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 找到 `AuthorizedEmailAddress` 设置并删除整行。

此图显示了为角色授权正确设置文件格式的 **appsettings.js** 。

   ![对显示角色授权方法的文件 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>租户和密钥设置

DKE 租户和关键设置位于 " **appsettings.js"** 文件中。

**为 DKE 配置租户和密钥设置**

1. 打开文件 ** 上** 的 "appsettings.js"。

2. 找到 `ValidIssuers` 设置并 `<tenantid>` 将其替换为你的租户 ID。 你可以转到 Azure 门户并查看 [租户属性](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)，以找到你的租户 ID。 例如：

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

找到 `JwtAudience` 。 `<yourhostname>`将替换为将运行 DKE 服务的计算机的主机名。 例如：

  > [!IMPORTANT]
  > 的值 `JwtAudience` 必须与您的主机的名称 *完全*匹配。 在调试时，您可以使用 **localhost： 5001** 。 但是，在完成调试后，请务必将此值更新到服务器的主机名。

- `TestKeys:Name`. 输入密钥的名称。 例如：`TestKey1`
- `TestKeys:Id`. 创建一个 GUID 并输入它作为 `TestKeys:ID` 值。 例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。 您可以使用 [联机 Guid 生成器](https://guidgenerator.com/) 等网站随机生成 GUID。

此图像显示 **appsettings.js上**的租户和密钥设置的正确格式。 `LDAPPath` 配置了角色授权。

![在 appsettings.js的文件中显示 DKE 的正确租户和密钥设置。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>生成测试键

定义应用程序设置后，即可生成公用和专用测试密钥。

生成密钥：

1. 从 Windows "开始" 菜单中，运行 OpenSSL 命令提示符。

2. 转到要在其中保存测试密钥的文件夹。 您通过完成此任务中的步骤创建的文件存储在同一个文件夹中。

3. 生成新的测试密钥。

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. 生成私钥。

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. 生成公钥。

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. 在文本编辑器中，打开 " **pubkeyonly**"。 将 **pubkeyonly** 文件中除第一行和最后一行之外的所有内容复制到 `PublicPem` "文件中的 **appsettings.js** " 部分。

7. 在文本编辑器中，打开 " **privkeynopass**"。 将 **privkeynopass** 文件中除第一行和最后一行之外的所有内容复制到 `PrivatePem` "文件中的 **appsettings.js** " 部分。

8. 删除和部分中的所有空格和换行符 `PublicPem` `PrivatePem` 。

    > [!IMPORTANT]
    > 复制此内容时，请不要删除任何 PEM 数据。

9. 在 Visual Studio Code 中，浏览到 **Startup.cs** 文件。 此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store\。

10. 找到以下行：

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. 将这些行替换为以下文本：

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   最终结果应如下所示。

   ![用于公共预览的 startup.cs 文件](../media/dke-startupcs-usetestkeys.png)

现在，你已准备好 [生成 DKE 项目](#build-the-project)。

### <a name="build-the-project"></a>生成项目

使用以下说明在本地生成 DKE 项目：

1. 在 Visual Studio Code 中，在 DKE 服务存储库中，选择 " **查看** \> **命令组件面板** "，然后在提示符处键入 **build** 。

2. 从列表中选择 " **任务：运行生成任务**"。

   如果找不到任何生成任务，请选择 " **配置生成任务** 并为 .net core 创建一个"，如下所示。

   ![为 .NET 配置缺少的生成任务](../media/dke-configurebuildtask.png)

   1. **从模板中选择 "创建 tasks.js"**。

      ![从 DKE 的模板创建对文件的 tasks.js](../media/dke-createtasksjsonfromtemplate.png)

   2. 从模板类型列表中，选择 " **.Net Core**"。

      ![为 DKE 选择正确的模板](../media/dke-tasksjsontemplate.png)

   3. 在 "生成" 部分，找到 **customerkeystore** 文件的路径。 如果没有，则添加以下行：

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. 再次运行生成。

3. 确认输出窗口中没有红色错误。

   如果出现红色错误，请检查控制台输出。 确保您已正确完成上述所有步骤，并且存在正确的生成版本。

4. 选择 " **运行** \> **启动调试** " 以调试进程。 如果系统提示您选择环境，请选择 " **.net core**"。

.NET core 调试器通常会启动到 `https://localhost:5001` 。 若要查看测试项，请转到 `https://localhost:5001` 并追加一个正斜杠 (/) 和键的名称。 例如：

```https
https://localhost:5001/TestKey1
```

该项应以 JSON 格式显示。

你的设置现已完成。 在发布密钥库之前，在 appsettings.js的 JwtAudience 设置中，确保主机名的值与您的应用程序服务主机名称完全匹配。 您可能已将其更改为 localhost 以对生成进行故障排除。

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>部署 DKE 服务并发布密钥存储区

对于生产部署，请在第三方云中部署该服务或 [发布到本地系统](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。

您可能更喜欢部署密钥的其他方法。 选择最适合您的组织的方法。

对于试点部署，您可以在 Azure 中部署并立即开始。

**创建 Azure Web 应用程序实例以托管你的 DKE 部署**

若要发布密钥存储，您将创建一个 Azure 应用服务实例以托管您的 DKE 部署。 接下来，你将生成的密钥发布到 Azure。

1. 在浏览器中，登录到[Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到 "**应用程序服务**" "  >  **添加**"。

2. 选择订阅和资源组，并定义实例详细信息。

    - 输入要安装 DKE 服务的计算机的主机名。 请确保它与在 [**appsettings.json**](#tenant-and-key-settings) file 中为 JwtAudience 设置定义的名称相同。 您为名称提供的值也是 WebAppInstanceName。

    - 对于 " **发布**"、"选择 **代码**" 和 " **运行时堆栈**"，选择 " **.net Core 3.1**"。

    例如：

   ![添加应用服务](../media/dke-azure-add-app-service.png)

3. 在页面底部，选择 " **审阅 + 创建**"，然后选择 " **添加**"。

4. 执行下列操作之一以发布生成的密钥：

    - [通过 ZipDeployUI 发布](#publish-via-zipdeployui)
    - [通过 FTP 发布](#publish-via-ftp)
    - [通过 Visual Studio 2019 或更高版本发布](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>通过 ZipDeployUI 发布

1. 转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。

    例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. 在密钥存储的基本代码中，转到 " **customer-key-store\src\customer-key-store** " 文件夹，并验证此文件夹是否包含 **customerkeystore** 文件。

3. 运行： **dotnet 发布**

     "输出" 窗口显示部署发布的目录。

    例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. 将发布目录中的所有文件发送到 .zip 文件。 创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。

5. 将您创建的 .zip 文件拖放到您在上面打开的 ZipDeployUI 网站上。 例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE 已部署，您可以浏览到已创建的测试键。 继续验证下面的 [部署](#validate-your-deployment) 。

#### <a name="publish-via-ftp"></a>通过 FTP 发布

1. 连接到您在 [上面](#deploy-the-dke-service-and-publish-the-key-store)创建的应用程序服务。

    在浏览器中，转到： **Azure portal**  >  **App Service**  >  **部署中心**  >  的**手动部署**  >  **FTP**  >  **仪表板**。

2. 将显示的连接字符串复制到本地文件。 您将使用这些字符串连接到 Web 应用服务，并通过 FTP 上载文件。

    例如：

   ![从 FTP 仪表板复制连接字符串](../media/dke-ftp-dashboard.png)

3. 在密钥存储的基本代码中，转到 **customer-key-store\src\customer-key-store 目录**。

4. 验证此目录是否包含 **customerkeystore** 文件。

5. 运行： **dotnet 发布**

    输出包含部署发布的目录。

    例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. 将发布目录中的所有文件发送到 zip 文件。 创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。

7. 从你的 FTP 客户端，使用复制的连接信息连接到应用服务。 将您在上一步中创建的 .zip 文件上载到 Web 应用程序的根目录。

DKE 已部署，您可以浏览到已创建的测试键。 接下来， [验证您的部署](#validate-your-deployment)。

### <a name="validate-your-deployment"></a>验证部署

使用上述方法之一部署 DKE 后，请验证部署和密钥存储设置。

以

src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey

例如：

key_store_tester.ps1 https://mydkeservice.com/mykey

确保输出中不显示任何错误。 准备好后， [注册你的密钥存储](#register-your-key-store)。

## <a name="register-your-key-store"></a>注册密钥存储

以下步骤使您能够注册 DKE 服务。 注册 DKE 服务是部署 DKE 之前的最后一步，您可以开始创建标签。

注册 DKE 服务的步骤：

1. 在浏览器中，打开 [Microsoft Azure 门户](https://ms.portal.azure.com/)，并转到 " **所有服务** \> **标识** \> **应用注册**"。

2. 选择 " **新建注册**"，并输入有意义的名称。

3. 从显示的选项中选择一个帐户类型。

    如果您使用的是具有非自定义域的 Microsoft Azure （如 **onmicrosoft.com**），请选择 " **仅限 Microsoft-单个租户) 中的组织目录中的帐户" (。**

    例如：

   ![新应用注册](../media/dke-app-registration.png)

4. 在页面底部，选择 " **注册** " 以创建新的应用注册。

5. 在新的应用注册中，在左窗格中的 " **管理**" 下，选择 " **身份验证**"。

6. 选择 " **添加平台**"。

7. 在 " **配置平台** " 弹出菜单上，选择 " **Web**"。

8. 在 " **重定向 uri**" 下，输入您的双密钥加密服务的 URI。 输入应用服务 URL，包括主机名和域。

    例如：https://mydkeservicetest.com

    - 输入的 URL 必须与部署 DKE 服务的主机名相匹配。
    - 如果您正在使用 Visual Studio 进行本地测试，请使用 **https://localhost:5001** 。
    - 在所有情况下，方案都必须是 **https**。

    确保主机名与应用服务主机名完全匹配。 您可能已将其更改为 `localhost` ，以排除生成故障。 在 **appsettings.js上**，此值是您为设置的主机名 `JwtAudience` 。

9. 在 " **隐式授予**" 下，选中 " **ID 令牌** " 复选框。

10. 选择“**保存**”以保存所做的更改。

11. 在左窗格中，选择 " **公开 API**"，然后选择 "应用程序 ID URI" 旁边的 " **设置**"。

12. 在 " **公开一个 API** " 页上的 " **此 Api 定义的作用域** " 中，选择 " **添加范围**"。 在新作用域中：

    1. 将范围名称定义为 **user_impersonation**。

    2. 选择可以同意的管理员和用户。

    3. 定义所需的任何剩余值。

    4. 选择“添加作用域”****。

    5. 选择顶部的 " **保存** " 以保存所做的更改。

13. 仍在 " **公开 API** " 页上的 " **授权客户端应用程序** " 区域中，选择 " **添加客户端应用程序**"。

    在新的客户端应用程序中：

    1. 将客户端 ID 定义为 **d3590ed6-52b3-4102-aeff-aad2292ab01c**。 此值是 Microsoft Office 客户端 ID，它使 Office 能够获取密钥存储的访问令牌。

    2. 在 " **授权范围**" 下，选择 " **user_impersonation** " 范围。

    3. 选择“添加应用程序”****。

    4. 选择顶部的 " **保存** " 以保存所做的更改。

现已注册你的 DKE 服务。 继续操作，方法是 [使用 DKE 创建标签](#create-sensitivity-labels-using-dke)。

## <a name="create-sensitivity-labels-using-dke"></a>使用 DKE 创建敏感度标签

在 Microsoft 365 合规性中心中，创建一个新的敏感度标签，并按您自己的方式应用加密。 选择 " **使用双密钥加密** "，并输入密钥的终结点 URL。

例如：

![在 Microsoft 365 合规性中心中选择 "使用双重密钥加密"](../media/dke-use-dke.png)

您添加的任何 DKE 标签将为适用于企业的 Microsoft 365 应用程序的最新版本中的用户显示。

> [!NOTE]
> 客户端可能需要长达24小时才能使用新标签进行刷新。

### <a name="enable-dke-in-your-client"></a>在客户端中启用 DKE

如果你是 Office 预览体验成员，则会为你启用 DKE。 否则，请添加以下注册表项，为客户端启用 DKE：

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>将受保护的文件从 HYOK 标签迁移到 DKE 标签

如果需要，在完成 DKE 设置后，您可以使用 HYOK 标签将受保护的内容迁移到 DKE 标签。 若要迁移，您将使用 AIP 扫描程序。 若要开始使用扫描程序，请参阅 [什么是 Azure 信息保护统一标记扫描程序？](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)。

如果不迁移内容，HYOK 受保护的内容将保持不受影响。
