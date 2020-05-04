---
title: 在管理中心中管理外接程序的部署
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何通过在管理中心中使用集中部署将外接程序部署到组织中的用户和组。
ms.openlocfilehash: 30f2c08aa895f63ed529b4390d208e3daa9d6d7b
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011707"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中管理外接程序的部署

Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅[开始使用 Office 加载项](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)）。 作为管理员，您可以为组织中的用户部署 Office 外接程序。 您可以使用 Microsoft 365 管理中心中的集中部署功能来执行此操作。
  
集中部署是大多数管理员为将外接程序部署到组织内的用户和组的建议功能和功能最丰富的方式。 若要详细了解如何确定组织是否可以支持集中部署，请参阅[确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。
  
集中部署有以下优点：
  
- 全局管理员可以将外接程序直接分配给用户、通过一个组将加载项分配给多个用户，或分配给租户中的所有人。
    
- 相关 Office 应用程序启动时，将自动为用户下载加载项。如果加载项支持加载项命令，加载项会自动显示在 Office 应用程序的"功能区"中。
    
- 如果管理员关闭或删除加载项，或者从 Azure Active Directory 或将外接程序分配到的组中删除了用户，外接程序将不再显示给用户。
    
> [!NOTE]
>  对于 Word，Excel 和 PowerPoint 使用[Sharepoint 应用程序目录](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)将外接程序部署到本地环境中的用户，而无需连接到 Microsoft 365 和/或支持 SharePoint 外接程序。 > Outlook 使用 Exchange 控制面板在本地环境中部署，而无需连接到 Microsoft 365。 > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 外接程序的推荐方法

请考虑采用分阶段方法推出加载项，帮助确保加载项部署顺利进行。推荐以下计划：
  
1. 向小部分业务利益干系人和 IT 部门成员推出加载项。评估部署是否成功，如果成功，请转到步骤 2。
    
2. 向企业内将使用加载项的较多人员推出加载项。同样，评估结果，如果一切顺利，请转至完整部署的下一步。
    
3. 全面向目标受众用户推出加载项。
    
根据目标受众的规模，可能需要添加或移除推出步骤。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用管理中心部署 Office 外接程序

在开始之前，请参阅[确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。

  
1. 在管理中心中，转到 "**设置** \> **外接程序**" 页。
    
2. 在页面顶部选择 "**部署加载项**"。 在 "概述" 页上，选择 "**下一步**"。
    
3. 选择一个选项，然后按照说明进行操作。
  
4. 如果选择了从 Office 应用商店添加加载项的选项，现在可以将加载项选择。 请注意，可以按" **建议** "、" **评级** "或" **名称** "查看可用加载项。 仅可从 Office Store 添加免费加载项。 目前尚不支持付费加载项。 选择你的外接程序后，你将需要同意一些其他条款和条件才能继续。 <br/><br/> 注意：通过 Office 应用商店选项，无需你的干预，即可自动将对外接程序的更新和增强提供给用户。

5. 在下一页上，选择 "**所有人**"、"**特定用户/组**" 或 "**仅我**" 以指定要向其部署加载项的用户。 使用搜索框查找要向其部署加载项的用户或组。 <br/>注意：了解适用于外接程序的其他状态。 请参阅本主题后面的[加载项状态](#add-in-states)。
  
6. 选择“部署”****。
  
7. 部署外接程序后，将显示绿色计时周期。 您可以按照页面上的说明测试外接程序是否已成功部署。

> [!NOTE]
> 用户可能需要重新启动 Office 以查看应用程序功能区上显示的外接程序图标。 Outlook 外接程序最长可能需要12个小时才能显示在用户的功能区上。
    
8. 完成后，选择 "**下一步**"。 如果只部署到自己的，则可以选择 "**更改谁有权访问外接程序**"，以便将其部署到更多用户。



如果您已将外接程序部署到您的组织的成员之外，请按照显示的说明进行操作，以便有效地宣布加载项的部署。 <br/>现在，你可以在 Microsoft 365 中看到你的外接程序和其他应用程序。
  
最好通知向其部署了加载项的用户和组，以便他们知道加载项可用。 可以向他们发送电子邮件，说明何时以及如何使用加载项，并说明加载项可以如何帮助他们更好地完成工作。 包含或链接到相关帮助内容或 Faq，如果用户在外接程序中遇到任何问题，则可能会有帮助。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>为用户和组分配加载项时的注意事项

管理员可以为每个人或特定用户和组分配加载项。每个选项都有含义：
  
- **每个人**：顾名思义，此选项为租户中的每位用户分配加载项。请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。 
    
- **用户** ：如果向单个用户分配加载项，那么为新用户部署加载项时，需要先添加该用户。这同样适用于删除用户。 
    
- **组** ：如果为组分配加载项，添加到组的用户将自动被分配该加载项。并且，当从组中删除用户时，该用户无法再访问该加载项。在任一情况下，不需要管理员执行任何额外操作。 

- **仅限我**：如果只向自己分配加载项，则会将外接程序仅分配给您的帐户。 如果您希望先测试加载项，这是理想之选。
    
适合您的组织的选项取决于您的配置。 但是，建议通过组进行分配。 作为管理员，可能会发现通过组管理加载项以及控制组成员身份更为轻松，而不是每次都更改分配的用户。 另一方面，在某些情况下，可能需要限制少数用户的访问权限，从而针对特定用户进行分配。 因此，需要手动管理分配的用户。
  
### <a name="add-in-states"></a>加载项状态

外接程序可以处于 "**打开**" 或 "**关闭**" 状态。
  
|**状态**|**状态出现的原因**|**影响**|
|:-----|:-----|:-----|
|**Active**  <br/> |管理员上载了加载项，并将其分配给用户或组。  <br/> |分配了加载项的用户和组可在相关客户端中看到它。  <br/> |
|**已禁用**  <br/> |管理员已禁用加载项。  <br/> |分配了外接程序的用户和组无法再访问它。  <br/> 如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。  <br/> |
|**已删除**  <br/> |管理员已删除加载项。  <br/> |分配了加载项的用户和组无法再访问它。  <br/> |
   
如果没有人再使用加载项，请考虑删除外接程序。 如果仅在一年的特定时间段使用加载项，那么可以选择关闭加载项。
  
### <a name="security-of-office-add-ins"></a>Office 加载项的安全性

Office 加载项结合了一个包含加载项相关元数据的 XML 清单文件，但最重要的是它指向包含所有代码和逻辑的 Web 应用程序。加载项的功能范围很广。例如，加载项可以：
  
- 显示数据。
    
- 读取用户文档以提供上下文服务。
    
- 从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。
    
若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。
  
若要与用户文档进行交互，加载项需要在清单中声明需要哪些权限。五级 JavaScript API 访问权限模型为任务窗格加载项的用户提供隐私和安全性的基础。Office 应用商店 中的大多数加载项是 ReadWriteDocument 级别，几乎所有加载项均至少支持 ReadDocument 级别。有关权限级别的详细信息，请参阅 [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863)（请求在内容和任务窗格加载项中使用 API 的权限）。
  
更新清单时，通常更改加载项的图标和文本。有时会更改加载项命令。但是，不会更改加载项的权限。Web 应用程序（加载项的所有代码和逻辑在其中运行）可以随时更改，这是 Web 应用程序的特性。
  
加载项更新的情况如下：
  
- **业务线加载项：** 在这种情况下，管理员显式上传清单，加载项需要管理员上传新的清单文件以支持元数据的更改。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。 

    > [!NOTE]
    > 管理员无需删除 LOB 加载项即可进行更新。   在 "外接程序" 部分中，管理员只需单击 LOB 外接程序，然后选择右下角的 "**更新" 按钮**即可。 仅当新外接程序的版本大于现有加载项的版本时，更新才有效。   
    
- **Office 应用商店加载项：** 管理员从 Office 应用商店 中选择加载项后，如果 Office 应用商店 中更新了加载项，则该加载项会稍后以集中式部署方式更新。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。 

### <a name="edit-add-in-access"></a>编辑外接访问

部署后，管理员还可以修改用户对加载项的访问权限。

1. 在 "管理中心" 中，转到 "**设置** > **服务" & "加载项**" 页面。

2. 选择部署的加载项。

3. 单击 "**有权访问**" 下的 "**编辑**"。
4. 保存所做的更改。
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>通过在所有客户端（Outlook 除外）中关闭 Office 应用商店来阻止外接程序下载

> [!NOTE]
> Outlook 外接程序安装由[不同的进程](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)进行管理。

作为组织，您可能希望阻止从 Office 应用商店下载新的 Office 加载项。 这可与集中部署结合使用，以确保仅向组织中的用户部署组织批准的外接程序。
  
若要关闭加载项获取，请执行以下操作：
  
1. 在管理中心，转到“**设置**”\> [服务和加载项](https://go.microsoft.com/fwlink/p/?linkid=2053743)页面。
    
3. 选择 "**用户拥有的应用和服务**"。
    
4. 清除 "允许用户访问 Office 应用商店" 选项。

这将阻止所有用户从存储中获取以下外接程序。
  
- Word、Excel 和 PowerPoint 2016 的外接程序来自：
    
  - Windows
    
  - Mac
    
  - Office
    
    
- 从**AppSource**中开始的收购
    
- Microsoft 365 中的外接程序
    
尝试访问应用商店的用户将看到以下消息：**抱歉，Microsoft 365 已配置为阻止单独获取 Office 应用商店外接程序。**
  
以下版本提供了对 Office 应用商店关闭的支持：
  
- Windows： 16.0.9001-当前可用。
    
- Mac： 16.10.18011401-当前可用。
    
- iOS： 2.9.18010804-当前可用。
    
- Web 当前可用。
    
这不会阻止管理员使用集中部署从 Office 应用商店分配外接程序。
  
若要阻止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。 有关详细信息，请参阅[此处](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>向应用商店中的未成年人和收购外接程序

一般数据保护条例（GDPR）是一种欧洲联合法规，生效时间可能为25，2018。 它向用户提供对其数据的权限并加以保护。 GDPR 的其中一个方面是，未成年人的个人数据不能发送给其家长或监护人尚未批准的当事人。 定义为次要的特定年龄取决于个人所在的区域。
  
具有关于家长同意的法令法规的地区包括美国、韩国、英国和欧盟。 对于这些区域，将阻止（通过 Azure Active Directory）从存储中获取任何新的 Office 外接程序，并运行之前获取的外接程序。 对于没有法令法规的国家/地区，将不提供下载限制。
  
根据 Azure Active Directory 中指定的数据，将用户确定为次要用户。 租户管理员负责声明法律年龄组和该用户的家长同意。
  
如果父/监护人同意使用特定的外接程序，则租户管理员可以使用集中部署将该外接程序部署到所有已同意的未成年人。
  
若要符合 GDPR 的要求，您需要确保在学校/组织中部署以下 Office 内部版本之一。
  
 **对于 Word、Excel、PowerPoint 和 Project**： 
  
|||
|:-----|:-----|
|**平台** <br/> |**内部版本号** <br/> |
|适用于企业的 Microsoft 365 应用（月度频道）  <br/> |9001.2138   <br/> |
|适用于企业的 Microsoft 365 应用（半年频道）  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Office 网页版  <br/> |无  <br/> |
   
 **对于 Outlook**： 
  
|||
|:-----|:-----|
|**平台** <br/> |**内部版本号** <br/> |
|适用于 Windows 的 Outlook 2016 （MSI）  <br/> |生成不 TBD  <br/> |
|适用于 Windows 的 Outlook 2016 （C2R）  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|适用于 iOS 的 Outlook mobile  <br/> |2.75.0  <br/> |
|Outlook mobile for Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |无  <br/> |
   
 **Office 2013 要求**
  
Word、Excel 和 PowerPoint 2013 for Windows 将支持相同的次要检查（如果已启用 Active Directory 身份验证库（ADAL））。 有两种合规性选项，如下所述。
  
- **启用 ADAL**。 本文介绍如何为 Office 2013 启用 ADAL：使用适用[于 office 客户端的 Microsoft 365 新式验证](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)。<br/>您还需要将注册表项设置为启用 ADAL，如在[Windows 设备上为 Office 2013 启用新式验证](../security-and-compliance/enable-modern-authentication.md)中所述。<br/>此外，还需要为 Office 2013 安装以下四月份更新：
    
  - [Office 2013 安全更新说明：4月10日，2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018年4月3日，Office 2013 更新（KB4018333）](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **不启用 ADAL**。 如果无法在 Office 2013 中启用 ADAL，我们建议使用组策略关闭 office 客户端的存储。 有关如何关闭 "Office 相关应用程序" 设置的信息位于[此处](https://technet.microsoft.com/library/cc178992.aspx)。
    
## <a name="end-user-experience-with-add-ins"></a>加载项最终用户体验

部署加载项后，最终用户就可开始在 Office 应用程序中使用此加载项（请参阅[开始使用 Office 加载项](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)）。加载项会显示在所有加载项支持的平台上。
  
如果加载项支持加载项命令，则 Office 功能区上会显示命令。在以下示例中，显示" **引文** "加载项的" **搜索引文** "命令。 

![带有搜索引文的 Office 功能区](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果部署的外接程序不支持外接程序命令，或者如果您想要查看所有部署的加载项，可以通过**我的外接**程序查看它们。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 选择 **" \>插入我的外接程序"**。 
    
2. 选择 Office 加载项窗口中的" **由管理员管理** "选项卡。 
    
3. 双击先前部署的加载项（在本例中是" **引文** "）。 <br/>!["Office 外接程序" 页的 "管理托管" 选项卡](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. 在 "**主页**" 功能区上，选择 "**获取外接程序**"。<br/>![Outlook 中的'应用商店'按钮](../../media/getaddinsicon.png)
  
2. 在左侧导航中选择 "**管理员管理**"。

## <a name="delete-the-add-in"></a>删除加载项

您还可以删除已部署的外接程序。

1. 在 "管理中心" 中，转到 "**设置** > **服务" & "加载项**" 页面。

2. 选择部署的加载项。

3. 单击 "**删除加载项**"。 移除右下角的外接端按钮。
4. 验证您的选择，然后选择 "**删除外接程序**"。
  
## <a name="learn-more"></a>了解详细信息

深入了解如何创建和构建 [Office 加载项](https://go.microsoft.com/fwlink/p/?linkid=846362)。
  
[使用集中部署 PowerShell cmdlet 管理外接程序](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9)。
  
[疑难解答：用户看不到外接程序](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
