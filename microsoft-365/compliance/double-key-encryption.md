---
title: 双密钥加密(DKE)
description: DKE 使你能够保护高度敏感的数据，同时保持对密钥的完全控制。
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
ms.openlocfilehash: 9607b095ba073229edae43c1d2f0e893db07c634
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663087"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Microsoft 365 的双密钥加密

> *适用于：Microsoft 365 的双密钥加密 [、Microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management)[、Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *说明： [适用于 Windows 的 Azure 信息保护统一标记客户端](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *服务说明 [：Microsoft 365 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

双密钥加密 (DKE) 使用两个密钥来访问受保护的内容。 Microsoft 在 Microsoft Azure 中存储一个密钥，你持有另一个密钥。 使用双密钥加密服务维护对其中一个密钥的完全控制。 使用 Azure 信息保护统一标记客户端对高度敏感的内容应用保护。

双密钥加密支持云和本地部署。 这些部署有助于确保加密数据在存储受保护数据的位置都保持不透明。

有关默认的基于云的租户根密钥详细信息，请参阅规划和 [实现 Azure 信息保护租户密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。

## <a name="when-your-organization-should-adopt-dke"></a>组织何时应采用 DKE

双密钥加密适用于符合最严格保护要求的最敏感数据。 DKE 并不用于所有数据。 通常，你将使用双密钥加密来保护整个数据的一小部分。 在部署之前，应谨慎确定此解决方案要涵盖的合适数据。 在某些情况下，可能需要缩小范围，并针对大部分数据使用其他解决方案，例如 Microsoft 信息保护与 Microsoft 托管密钥或 BYOK。 这些解决方案足以用于不受增强保护和法规要求限制的文档。 此外，这些解决方案还使您能够使用最强大的 Office 365 服务;不能与 DKE 加密内容一同使用的服务。 例如：

- 需要查看附件的传输规则，包括反恶意软件和垃圾邮件
- Microsoft Delve
- 电子数据展示
- 内容搜索和索引
- 包括共同创作功能的 Office Web Apps

任何未通过 MIP SDK 与 DKE 集成的外部应用程序或服务将无法对加密数据执行操作。

Microsoft 信息保护 SDK 1.7+ 支持双密钥加密;与 SDK 集成的应用程序将能够通过足够的权限和集成来了解此数据。

我们建议组织使用 Microsoft 信息保护 (分类和标签) 来保护其大部分敏感数据，并且仅将 DKE 用于其任务关键型数据。 双密钥加密对于高度管控行业（如金融服务和医疗保健）中的非常敏感的数据尤其相关。

如果您的组织有以下任一要求，可以使用 DKE 来帮助保护内容的安全：

- 您希望确保 *在任何情况下仅* 可以解密受保护的内容。
- 你不希望 Microsoft 自行访问受保护的数据。
- 您具有在地理边界内保留密钥的法规要求。 您保留用于数据加密和解密的所有密钥均在数据中心中维护。

## <a name="system-and-licensing-requirements-for-dke"></a>DKE 的系统和许可要求

**Microsoft 365** 的双密钥加密随 Microsoft 365 E5 一起提供。 如果你没有 Microsoft 365 E5 许可证，可以[注册试用版。](https://aka.ms/M365E5ComplianceTrial) 有关这些许可证详细信息，请参阅 [Microsoft 365 安全与合规&指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

**Azure 信息保护**。 DKE 适用于敏感度标签，并且需要 Azure 信息保护。

DKE 敏感度标签通过 Office 桌面应用程序中的敏感度功能区提供给最终用户。 在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。

**Microsoft Office应用程序企业** 版 *.12711 或更高版本 (Windows 上的 Word、PowerPoint 和 Excel) 桌面版。

**Azure 信息保护统一标签客户端** 版本 2.7.93.0 或更高版本。 从 Microsoft 下载中心下载并安装统一 [标签客户端](https://www.microsoft.com/download/details.aspx?id=53018)。

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>用于存储和查看受 DKE 保护的内容的支持环境

**支持的应用程序**。 [Windows 上的 Microsoft 365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) 企业应用版客户端，包括 Word、Excel 和 PowerPoint。

**联机内容支持**。 支持联机存储在 Microsoft SharePoint 和 OneDrive for Business 中的文档和文件。 可以通过电子邮件共享加密内容，但不能联机查看加密的文档和文件。 相反，你必须在本地计算机上使用桌面应用查看受保护的内容。

## <a name="overview-of-deploying-dke"></a>部署 DKE 概述

你将按照这些常规步骤设置 DKE。 完成这些步骤后，最终用户将能够使用双密钥加密来保护高度敏感数据。

1. 部署 DKE 服务，如本文所述。

2. 使用双密钥加密创建标签。 导航到 [Microsoft 365 合规](https://compliance.microsoft.com) 中心下的信息保护，然后使用双密钥加密创建新标签。 请参阅 [使用敏感度标签应用加密来限制对内容的访问](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。

3. 使用双密钥加密标签。 通过从"敏感度"功能区中选择"双密钥加密"标签来保护Microsoft Office。

有几种方法可以完成部署双密钥加密的一些步骤。 本文提供了详细说明，以便经验不足的管理员能够成功部署服务。 如果习惯这样做，可以选择使用自己的方法。

## <a name="deploy-dke"></a>部署 DKE

本文和部署视频使用 Azure 作为 DKE 服务的部署目标。 如果要部署到其他位置，则需要提供自己的值。

观看 [双密钥加密部署视频](https://youtu.be/vDWfHN_kygg) ，查看本文中概念的分步概述。 视频大约需要 18 分钟才能完成。

你将按照这些常规步骤为组织设置双密钥加密。

1. [安装 DKE 服务的必备软件](#install-software-prerequisites-for-the-dke-service)
1. [克隆双密钥加密 GitHub 存储库](#clone-the-dke-github-repository)
1. [修改应用程序设置](#modify-application-settings)
1. [生成测试密钥](#generate-test-keys)
1. [生成项目](#build-the-project)
1. [部署 DKE 服务并发布密钥存储](#deploy-the-dke-service-and-publish-the-key-store)
1. [验证部署](#validate-your-deployment)
1. [注册密钥存储](#register-your-key-store)
1. [使用 DKE 创建敏感度标签](#create-sensitivity-labels-using-dke)
1. [在客户端中启用 DKE](#enable-dke-in-your-client)
1. [将受保护的文件从 HYOK 标签迁移到 DKE 标签](#migrate-protected-files-from-hyok-labels-to-dke-labels)

完成后，可以使用 DKE 加密文档和文件。 有关信息，请参阅 [在 Office 中将敏感度标签应用于文件和电子邮件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。

### <a name="install-software-prerequisites-for-the-dke-service"></a>安装 DKE 服务的必备软件

在要安装 DKE 服务的计算机上安装这些必备组件。

**.NET Core 3.1 SDK**。 从下载[.NET Core 3.1 下载并安装 SDK。](https://dotnet.microsoft.com/download/dotnet-core/3.1)

**Visual Studio代码**。 从 Visual Studio 下载代码 [https://code.visualstudio.com/](https://code.visualstudio.com) 。 安装完成后，运行Visual Studio代码并选择 **"查看** \> **扩展"。** 安装这些扩展。

- C# Visual Studio代码

- NuGet 程序包管理器

**Git 资源**。 下载并安装以下项之一。

- [Git](https://git-scm.com/downloads)

- [GitHub 桌面](https://desktop.github.com/)

- [GitHub 企业版](https://github.com/enterprise)

**OpenSSL** 部署 DKE 后，必须安装 [](#generate-test-keys) [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)以生成测试密钥。 确保从环境变量路径正确调用它。 例如，有关详细信息，请参阅"将安装目录添加到 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH"。

### <a name="clone-the-dke-github-repository"></a>克隆 DKE GitHub 存储库

Microsoft 在 GitHub 存储库中提供 DKE 源文件。 克隆存储库以在本地生成项目供组织使用。 DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。

以下说明适用于没有经验的 git 或 Visual Studio 代码用户：

1. 在浏览器中， [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 转到：

2. 在屏幕右侧，选择"**代码"。** 你的 UI 版本可能会显示"克隆 **"或"下载"** 按钮。 然后，在出现的下拉列表中，选择复制图标以将 URL 复制到剪贴板。

    例如：

   ![从 GitHub 克隆双密钥加密服务存储库](../media/dke-clone.png)

3. 在Visual Studio，选择 **"查看** \> **命令调色板**"，然后选择 **"Git： 克隆"。** 若要跳转到列表中的选项，请开始键入以筛选条目，然后从下拉列表 `git: clone` 中选择它。 例如：

   ![Visual Studio代码 GIT：Clone 选项](../media/dke-vscode-clone.png)

4. 在文本框中，粘贴从 Git 复制的 URL，然后从 **GitHub 中选择"克隆"。**

5. 在 **出现的"** 选择文件夹"对话框中，浏览到存储库并选择要存储存储库的位置。 在提示符下，选择"打开 **"。**

    存储库在代码Visual Studio中打开，并且显示在左下角的当前 Git 分支。 分支应为 **主控点**。

    例如：

   ![Visual Studio代码母版分支](../media/dke-vscode-master.png)

6. 从分支 **列表中选择** 单词母版。

   > [!IMPORTANT]
   > 选择主分支可确保您具有用于生成项目的正确文件。 如果不选择正确的分支，部署将失败。

现在，你已在本地设置 DKE 源存储库。 接下来 [，修改组织](#modify-application-settings) 的应用程序设置。

### <a name="modify-application-settings"></a>修改应用程序设置

若要部署 DKE 服务，必须修改以下类型的应用程序设置：

- [密钥访问设置](#key-access-settings)
- [租户和密钥设置](#tenant-and-key-settings)

修改文件上的appsettings.js设置。 此文件位于在 DoubleKeyEncryptionService\src\customer-key-store 下本地克隆的 DoubleKeyEncryptionService 存储库。 例如，在Visual Studio代码中，您可以浏览到该文件，如下图所示。

![在文件上appsettings.jsDKE 的配置文件。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>密钥访问设置

选择是使用电子邮件还是角色授权。 DKE 一次仅支持其中一种身份验证方法。

- **电子邮件授权**。 允许组织仅根据电子邮件地址授权访问密钥。

- **角色授权**。 允许组织根据 Active Directory 组授权访问密钥，并需要 Web 服务可以查询 LDAP。

**使用电子邮件授权为 DKE 设置密钥访问设置**

1. 打开 **appsettings.js并** 找到 `AuthorizedEmailAddress` 该设置。

2. 添加要授权的电子邮件地址。 用双引号和逗号分隔多个电子邮件地址。 例如：

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 找到 `LDAPPath` 该设置并删除双引号 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 之间的文本。 保留双引号。 完成后，设置应如下所示。

   ```json
   "LDAPPath": ""
   ```

4. 找到 `AuthorizedRoles` 该设置并删除整行。

此 **图显示了appsettings.js** 正确设置格式的电子邮件授权文件上的名称。

   ![显示appsettings.js方法的文件的扩展名](../media/dke-email-accesssetting.png)

**使用角色授权为 DKE 设置密钥访问设置**

1. 打开 **appsettings.js并** 找到 `AuthorizedRoles` 该设置。

2. 添加要授权的 Active Directory 组名称。 使用双引号和逗号分隔多个组名称。 例如：

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. 找到 `LDAPPath` 该设置并添加 Active Directory 域。 例如：

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 找到 `AuthorizedEmailAddress` 该设置并删除整行。

此 **图显示了appsettings.js** 角色授权正确设置格式的文件上的名称。

   ![appsettings.js显示角色授权方法的文件](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>租户和密钥设置

DKE 租户和密钥设置位于文件appsettings.js **中** 。

**配置 DKE 的租户和密钥设置**

1. 打开 **appsettings.js上的** 文件。

2. 找到 `ValidIssuers` 该设置， `<tenantid>` 并替换为租户 ID。 可以通过访问 Azure 门户并查看租户属性找到[租户 ID。](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 例如：

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

找到 `JwtAudience` 。 替换为 `<yourhostname>` 运行 DKE 服务的主机名。 例如：

  > [!IMPORTANT]
  > 其值 `JwtAudience` 必须与主机的名称完全 *匹配*。 调试时可以使用 **localhost：5001。** 但是，完成调试后，请确保将此值更新为服务器的主机名。

- `TestKeys:Name`. 输入密钥的名称。 例如：`TestKey1`
- `TestKeys:Id`. 创建一个 GUID，并输入它作为 `TestKeys:ID` 值。 例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。 可以使用联机 [GUID 生成器](https://guidgenerator.com/) 等网站随机生成 GUID。

此图像显示租户和密钥设置的正确格式，appsettings.js **打开**。 `LDAPPath` 配置为进行角色授权。

![在文件上的策略中显示 DKE 的正确appsettings.js和密钥设置。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>生成测试密钥

定义应用程序设置后，即可生成公钥和私钥测试密钥。

生成密钥：

1. 从 Windows"开始"菜单运行 OpenSSL 命令提示符。

2. 更改为要保存测试密钥的文件夹。 通过完成此任务中的步骤创建的文件存储在同一文件夹中。

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

6. 在文本编辑器中，打开 **pubkeyonly.pem。** 将 **pubkeyonly.pem** 文件（第一行和最后一行 `PublicPem` 除外）中appsettings.js **文件** 。

7. 在文本编辑器中，**打开nopass.pem。** 将 **appsettings.js.pem** 文件（第一行和最后一行除外 `PrivatePem` **）中appsettings.js文件** 。

8. 删除和节中的所有空格和 `PublicPem` `PrivatePem` 新行。

    > [!IMPORTANT]
    > 复制此内容时，不要删除任何 PEM 数据。

9. 在Visual Studio中，浏览 **到Startup.cs文件** 。 此文件位于在 DoubleKeyEncryptionService\src\customer-key-store\下本地克隆的 DoubleKeyEncryptionService 存储库。

10. 找到以下行：

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. 将以下行替换为以下文本：

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   最终结果应如下所示。

   ![startup.cs预览的预览文件](../media/dke-startupcs-usetestkeys.png)

现在，你已准备好生成 [DKE 项目](#build-the-project)。

### <a name="build-the-project"></a>生成项目

使用以下说明在本地生成 DKE 项目：

1. 在Visual Studio代码的 DKE 服务存储库中，选择 **"查看** 命令调色板"， \> 然后在提示 **符** 处键入生成。

2. 从列表中选择"**任务： 运行生成任务"。**

   如果没有找到生成任务，请选择" **配置** 生成任务"，然后为 .NET 核心创建一个，如下所示。

   ![为 .NET 配置缺少的生成任务](../media/dke-configurebuildtask.png)

   1. Choose **Create tasks.json from template.**

      ![根据 DKE 的tasks.js创建对文件进行创建](../media/dke-createtasksjsonfromtemplate.png)

   2. 从模板类型列表中，选择 **.NET Core。**

      ![为 DKE 选择正确的模板](../media/dke-tasksjsontemplate.png)

   3. 在生成部分中，找到 **customerkeystore.csproj 文件** 的路径。 如果不存在，请添加以下行：

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. 再次运行生成。

3. 确认输出窗口中没有红色错误。

   如果存在红色错误，请检查控制台输出。 确保您正确完成了上述所有步骤，并且存在正确的内部版本。

4. 选择 \> **"运行开始调试**"以调试过程。 如果系统提示你选择环境，请选择 **.NET core。**

.NET 核心调试程序通常启动到 `https://localhost:5001` 。 若要查看测试密钥，请转到 / (/) 和你的密钥的名称并追加 `https://localhost:5001` 一个正斜杠。 例如：

```https
https://localhost:5001/TestKey1
```

该键应该以 JSON 格式显示。

现在，你的设置已完成。 在发布 JwtAudience 设置的密钥appsettings.js，请确保主机名的值与 App Service 主机名完全匹配。 您可能已更改为 localhost 以对生成进行疑难解答。

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>部署 DKE 服务并发布密钥存储

对于生产部署，请部署第三方云中的服务或 [发布到本地系统](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。

你可能需要其他方法来部署密钥。 选择最适合贵组织的方法。

对于试点部署，可以在 Azure 中部署并立即开始。

**创建 Azure Web App 实例以托管 DKE 部署**

若要发布密钥存储，需要创建 Azure 应用服务实例来托管 DKE 部署。 接下来，将生成的密钥发布到 Azure。

1. 在浏览器中，登录到 [Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到 **"应用服务**  >  **添加"。**

2. 选择订阅和资源组并定义实例详细信息。

    - 输入要安装 DKE 服务的计算机的主机名。 请确保其名称与在文件上设置 JwtAudience 设置appsettings.js [**同**](#tenant-and-key-settings) 名。 您为名称提供的值也是 WebAppInstanceName。

    - 对于 **"发布****"、选择代码** 和运行时 **堆栈**，选择 **.NET Core 3.1。**

    例如：

   ![添加应用服务](../media/dke-azure-add-app-service.png)

3. 在页面底部，选择"审阅 **+ 创建**"，然后选择"**添加"。**

4. 执行下列操作之一以发布生成的密钥：

    - [通过 ZipDeployUI 发布](#publish-via-zipdeployui)
    - [通过 FTP 发布](#publish-via-ftp)
    - [通过 Visual Studio 2019 或更高版本发布](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>通过 ZipDeployUI 发布

1. 转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。

    例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. 在密钥存储的代码库中，转到 **customer-key-store\src\customer-key-store** 文件夹，并验证此文件夹是否包含 **customerkeystore.csproj** 文件。

3. 运行 **：dotnet 发布**

     输出窗口显示部署发布的目录。

    例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. 将发布目录中的所有文件发送到 .zip 文件。 创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。

5. 将创建的 .zip 文件拖放到上面打开的 ZipDeployUI 网站。 例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE 已部署，你可以浏览到已创建的测试密钥。 继续 [验证以下部署](#validate-your-deployment) 。

#### <a name="publish-via-ftp"></a>通过 FTP 发布

1. 连接到上面创建的应用 [服务](#deploy-the-dke-service-and-publish-the-key-store)。

    在浏览器中，转到 **：Azure 门户**  >  **应用服务**  >  **部署中心**  >  **手动部署**  >  **FTP**  >  **仪表板**。

2. 将显示的连接字符串复制到本地文件。 你将使用这些字符串连接到 Web 应用服务，然后通过 FTP 上载文件。

    例如：

   ![从 FTP 仪表板复制连接字符串](../media/dke-ftp-dashboard.png)

3. 在密钥存储的代码库中，转到 **customer-key-store\src\customer-key-store 目录**。

4. 验证此目录是否包含 **customerkeystore.csproj** 文件。

5. 运行 **：dotnet 发布**

    输出包含部署发布的目录。

    例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. 将发布目录中的所有文件发送到 zip 文件。 创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。

7. 从 FTP 客户端，使用复制的连接信息连接到应用服务。 将上一步中创建的 .zip 文件上载到 Web 应用的根目录。

DKE 已部署，你可以浏览到已创建的测试密钥。 接下来， [验证部署](#validate-your-deployment)。

### <a name="validate-your-deployment"></a>验证部署

使用上述方法之一部署 DKE 后，验证部署和密钥存储设置。

运行：

src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey

例如：

key_store_tester.ps1 https://mydkeservice.com/mykey

确保输出中未出现任何错误。 准备就绪后，注册 [密钥存储](#register-your-key-store)。

## <a name="register-your-key-store"></a>注册密钥存储

通过以下步骤注册 DKE 服务。 注册 DKE 服务是部署 DKE 的最后一步，然后才能开始创建标签。

注册 DKE 服务：

1. 在浏览器中，打开 [Microsoft Azure 门户](https://ms.portal.azure.com/)，然后转到"**所有服务** \> **标识** \> **应用注册"。**

2. 选择 **"新建注册**"，然后输入有意义的名称。

3. 从显示的选项中选择帐户类型。

    如果你将 Microsoft Azure 与非自定义域（如 **onmicrosoft.com）** 一同使用，请选择仅 (Microsoft - 单个租户 **) 。**

    例如：

   ![新应用注册](../media/dke-app-registration.png)

4. 在页面底部，选择" **注册** "以创建新的应用注册。

5. 在新的应用注册中，在左窗格中 **的"管理**"下，选择 **"身份验证"。**

6. 选择 **"添加平台"。**

7. 在"**配置平台"** 弹出窗口中，选择 **"Web"。**

8. 在 **重定向 URI 下**，输入双密钥加密服务的 URI。 输入应用服务 URL，包括主机名和域。

    例如：https://mydkeservicetest.com

    - 输入的 URL 必须与部署 DKE 服务的主机名匹配。
    - 如果要在本地使用 Visual Studio 测试，请使用 **https://localhost:5001** 。
    - 在所有情况下，方案必须为 **https。**

    确保主机名与应用服务主机名完全匹配。 您可能已更改它以 `localhost` 对生成进行疑难解答。 在 **appsettings.js中**，此值是设置为的主机名 `JwtAudience` 。

9. 在 **"隐式授予**"下 **，选中"ID 令牌"** 复选框。

10. 选择“**保存**”以保存所做的更改。

11. 在左窗格中，**选择"公开 API"，** 然后在"应用程序 ID URI"旁边，选择"**设置"。**

12. 仍在"**公开 API"页上**，在此 **API** 区域定义的"范围"中，选择 **"添加范围"。** 在新作用域中：

    1. 将范围名称定义为 **user_impersonation。**

    2. 选择可同意的管理员和用户。

    3. 定义所需的任何剩余值。

    4. 选择“添加作用域”。

    5. 选择 **顶部的** "保存"保存更改。

13. 仍在"**公开 API"页上** 的"授权客户端 **应用程序**"区域中，选择 **"添加客户端应用程序"。**

    在新的客户端应用程序中：

    1. 将客户端 ID 定义为 **d3590ed6-52b3-4102-aeff-aad2292ab01c。** 此值是Microsoft Office ID，使 Office 能够获取密钥存储的访问令牌。

    2. 在 **"授权范围"** 下， **选择user_impersonation** 范围。

    3. 选择“添加应用程序”。

    4. 选择 **顶部的** "保存"保存更改。

现在，DKE 服务已注册。 通过使用 [DKE 继续创建标签](#create-sensitivity-labels-using-dke)。

## <a name="create-sensitivity-labels-using-dke"></a>使用 DKE 创建敏感度标签

在 Microsoft 365 合规中心中，创建新的敏感度标签，并采用其他方式应用加密。 选择 **"使用双密钥加密** "，然后输入密钥的终结点 URL。

例如：

![选择 Microsoft 365 合规中心中的"使用双密钥加密"](../media/dke-use-dke.png)

你添加的任何 DKE 标签都将开始向最新版本的 Microsoft 365 企业应用版中的用户显示。

> [!NOTE]
> 客户端可能需要 24 小时才能刷新新标签。

### <a name="enable-dke-in-your-client"></a>在客户端中启用 DKE

如果你是 Office 预览体验成员，则启用 DKE。 否则，请通过添加以下注册表项来为客户端启用 DKE：

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>将受保护的文件从 HYOK 标签迁移到 DKE 标签

如果需要，完成 DKE 设置后，可以将使用 HYOK 标签保护的内容迁移到 DKE 标签。 若要迁移，请使用 AIP 扫描程序。 若要开始使用扫描程序，请参阅什么是[Azure 信息保护统一标签扫描程序？。](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)

如果不迁移内容，则 HYOK 保护的内容将不受影响。
