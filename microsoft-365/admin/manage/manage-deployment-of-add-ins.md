---
title: 在管理中心部署外接程序
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何通过在管理中心中使用集中部署将外接程序部署到组织中的用户和组。
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102856"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>在管理中心部署外接程序

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)）。 作为管理员，你可以使用 Microsoft 365 管理中心中的集中部署功能为组织中的用户部署 Office 外接程序。 集中部署是大多数管理员为将外接程序部署到组织内的用户和组的建议功能和功能最丰富的方式。 

若要详细了解如何确定组织是否可以支持集中部署，请参阅[确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。

若要详细了解如何在部署后管理外接程序，请参阅[在管理中心管理外接程序](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  对于 Word，Excel 和 PowerPoint 使用[Sharepoint 应用程序目录](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)将外接程序部署到本地环境中的用户，而无需连接到 Microsoft 365 和/或支持 SharePoint 外接程序。 对于 Outlook，在不连接到 Microsoft 365 的情况下，使用 Exchange 控制面板在本地环境中部署。
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 外接程序的推荐方法

若要使用分阶段方式推出外接程序，我们建议您执行以下操作：
  
1. 将加载项推出给一小部分业务利益干系人和 IT 部门的成员。 如果部署成功，请转到步骤2。
    
2. 将加载项部署到企业内的更多个人。 再次评估结果，如果成功，则继续完全部署。
    
3. 对所有用户执行完整的部署。
    
根据目标访问群体的大小，可以添加或删除向外外接步骤。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用管理中心部署 Office 外接程序

在开始之前，请参阅[确定加载项的集中部署是否适用于你的组织](centralized-deployment-of-add-ins.md)。
  
1. 在管理中心中，转到 "**设置** \> **外接程序**" 页。
    
2. 在页面顶部选择 "**部署加载项**"，然后选择 "**下一步**"。
    
3. 选择一个选项，然后按照说明进行操作。
  
4. 如果选择了从 Office 应用商店添加外接程序的选项，请将您的外接程序选择。 </br>

    您可以按类别查看可用的加载项：**建议为你**、**评级**或**名称**。 Office 应用商店仅提供免费的外接程序。 目前尚不支持付费加载项。 选择加载项后，请接受条款和条件以继续。 <br/> 

    > [!NOTE] 
    > 使用 Office 应用商店选项，更新和增强功能将自动应用于用户。

5. 在下一页上，选择 "**所有人**"、"**特定用户/组**" 或 "**仅我**" 以指定要向其部署加载项的用户。 使用搜索框查找特定用户或组。 <br/>

    > [!NOTE] 
    > 若要了解适用于外接程序的其他状态，请参阅[外接程序状态](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。
  
6. 选择“部署”****。
  
7. 部署加载项时，将显示绿色计时周期。 按照页面上的说明测试加载项。

    > [!NOTE]
    > 用户可能需要重新启动 Office 以查看应用程序功能区上的外接程序图标。 Outlook 加载项最长可能需要24小时才能显示在应用程序功能区上。
    
8. 完成后，选择 "**下一步**"。 如果只部署到自己的，则可以选择 "**更改谁有权访问外接程序**以将其部署到更多用户"。

    如果已将外接程序部署到组织中的其他成员，请按照说明宣布外接程序的部署。 <br/>
  
    最好通知用户和组已部署的外接程序可用。 请考虑发送描述何时以及如何使用外接程序的电子邮件。 包含或链接，以帮助用户在加载项中遇到问题时可能会帮助用户。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>为用户和组分配加载项时的注意事项

管理员可以为每个人或特定用户和组分配加载项。 每个选项都有含义：
  
- **所有人**此选项将加载项分配给组织中的每个用户。 请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。 
    
- **用户**如果向单个用户分配外接程序，然后将该外接程序部署到新用户，则必须先添加新用户。
    
- **组**如果将加载项分配给某个组，则会自动为添加到该组的用户分配该外接程序。 从组中删除用户时，用户将无法访问加载项。 在这两种情况下，管理员无需执行任何其他操作。 

- **仅我**如果只向自己分配加载项，则会将外接程序分配给您的帐户，这是测试外接程序的理想选择。
    
您的组织的正确选项取决于您的配置。 但是，建议使用组进行分配。 作为管理员，您可能会发现使用组管理外接程序并控制这些组的成员身份，而不是每次分配单个用户，这会更加轻松。 在某些情况下，您可能希望通过手动分配用户来限制对一小部分用户进行的访问。
  
## <a name="more-about-office-add-ins-security"></a>有关 Office 外接程序安全性的详细信息

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- 显示数据。
    
- 读取用户文档以提供上下文服务。
    
- 从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。
    
若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
加载项更新的情况如下：
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > 管理员无需删除 LOB 加载项即可进行更新。   在 "外接程序" 部分中，管理员只需单击 LOB 外接程序，然后选择右下角的 "**更新" 按钮**即可。 仅当新外接程序的版本大于现有加载项的版本时，更新才有效。   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
  
## <a name="learn-more"></a>了解详细信息

创建和生成[Office 外接程序](https://go.microsoft.com/fwlink/p/?linkid=846362)

[在管理中心中管理外接程序](manage-addins-in-the-admin-center.md)

[向应用商店中的未成年人和收购外接程序](minors-and-acquiring-addins-from-the-store.md)
  
[使用集中部署 PowerShell cmdlet 管理外接程序](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[疑难解答：用户看不到外接程序](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
