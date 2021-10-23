---
title: 确定外接程序的集中部署是否适用于您的组织
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 确定租户和用户是否满足要求，以便可以使用集中部署来部署Office外接程序。
ms.openlocfilehash: 9f428dc011d98d446f32f009345d5df30337c4f2
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552748"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>确定外接程序的集中部署是否适用于您的组织

对于大多数客户来说，集中部署是推荐且功能最丰富的方法Office向组织内的用户和组部署外接程序。 如果你是管理员，请使用本指南确定组织和用户是否满足要求，以便可以使用集中部署。

集中部署有以下优点：

- 全局管理员可以将外接程序直接分配给用户、通过组分配给多个用户或分配给组织中的每个人。

- 当相关Office应用程序启动时，外接程序将自动下载。 如果外接程序支持外接程序命令，则外接程序会自动显示在应用程序内的功能Office中。

- 如果管理员关闭或删除外接程序，或者如果用户从 Azure Active Directory 或外接程序分配到的组中删除，则用户将不再显示外接程序。

集中部署支持三个桌面Windows、Mac 和 Online Office应用。 集中部署还支持 iOS 和 Android (Outlook仅移动外接程序) 。

外接程序最多可能需要 24 小时才能显示给所有用户的客户端。

## <a name="before-you-begin"></a>准备工作

外接程序的集中部署要求用户使用 Microsoft 365 企业版 SKUS：E3/E5/F3、Office 365 企业版 SK：E3/E5/F3 或业务 SK：Business Basic、Business Standard、Business 高级版 (，并且使用其组织 ID) 登录 Office，并且具有 Exchange Online 和活动的 Exchange Online 邮箱。 订阅目录必须位于或联合到Azure Active Directory。
可以查看下面的特定要求Office Exchange，或使用集中部署[兼容性检查器](#centralized-deployment-compatibility-checker)。

集中部署不支持以下内容：

- 针对 Office 2013 中 Word、Excel 或 PowerPoint 的加载项
- 本地目录服务
- 部署到内部部署Exchange的外接程序部署
- 部署到 SharePoint 的加载项
- Teams应用
- 部署组件对象模型 (COM) 或Visual Studio Tools for Office (VSTO) 加载项。
- 不包含Microsoft 365的部署，Exchange Online SK：Microsoft 365 应用版 for Business 和 Microsoft 365 应用版 for Enterprise。

### <a name="office-requirements"></a>Office要求

- 对于 Word、Excel 和 PowerPoint 加载项，用户必须使用下列加载项之一：
  - 在 Windows 设备上，版本 1704 或更高版本的 Microsoft 365 企业版 SK：E3/E5/F3 或 Business SKUs：Business Basic、Business Standard、Business 高级版。
  - 在 Mac 版本 15.34 或更高版本上。

- 对于Outlook，用户必须使用下列方法之一：
  - SKUS 的版本 1701 或Microsoft 365 企业版：E3/E5/F3 或 Business SKUs：Business Basic、Business Standard、Business 高级版。
  - 2019 年 Office 专业增强版 2019 Office Standard 版本 1808 或更高版本。
  - MSI 版本 16.0.4494.1000 或更高版本 Office 专业增强版 2016 (MSI) Office 标准版 2016 (MSI) \*
  - MS) I 2013 (2013 或 Office Professional Plus Office Standard 2013 Office Standard 2013 版本 15.0.4937.1000 () \*
  - 版本 16.0.9318.1000 或更高版本Office 2016 for Mac
- 适用于 iOS 的 Outlook 2.75.0 版或更高版本
- Android 移动版 2.2.145 Outlook更高版本

    *MSI 版本的 Outlook在相应的 Outlook 功能区中显示管理员安装的外接程序，而不是"我的外接程序"部分。

### <a name="exchange-online-requirements"></a>Exchange Online要求

Microsoft Exchange 存储组织的租户中的加载项清单。 部署外接程序的管理员和接收这些外接程序的用户必须位于支持 OAuth 身份验证的 Exchange Online 版本上。

请与组织的 Exchange 管理员联系，了解正在使用哪个配置。可使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet 验证每个用户的 OAuth 连接。


### <a name="centralized-deployment-compatibility-checker"></a>集中部署兼容性检查器

使用集中部署兼容性检查器，可以验证租户上的用户是否设置为使用 Word、Excel 和 PowerPoint。 Outlook 支持不需要兼容性检查器。 下载 [兼容性检查器](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)。

#### <a name="run-the-compatibility-checker"></a>运行兼容性检查器

1. 启动提升的PowerShell.exe窗口。

2. 运行以下命令：

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. 运行 **Invoke-CompatabilityCheck** 命令：

   ```powershell
   Invoke-CompatibilityCheck
   ```
   此命令会提示您输入  *_TenantDomain_* (例如 *TailspinToysIncorporated.onmicrosoft。 </span>com*) 和  *_TenantAdmin_* (使用全局管理员凭据) ，然后请求同意。

   > [!NOTE]
   > 检查器可能需要数分钟或数小时时间来完成检查，具体取决于租户中的用户数。 
  
工具运行完毕后，会生成逗号分隔格式的输出文件 (.csv)。 默认情况下，该文件 **将保存到当前工作** 目录中。 输出文件包含以下信息：

- 用户名

- 用户 ID（用户的电子邮件地址）

- 集中部署准备就绪 - 如果剩余的项为 true

- Office计划 - Office许可的用户计划

- Office 已激活 - 如果已激活 Office

- 支持的邮箱 - 如果使用已启用 OAuth 的邮箱

> [!NOTE]
> 使用中央部署 PowerShell 模块时不支持多重身份验证。 该模块仅适用于基本身份验证。

## <a name="user-and-group-assignments"></a>用户和组分配

集中部署功能当前支持大多数受 Azure Active Directory 支持组，Microsoft 365组、通讯组列表和安全组。

> [!NOTE]
> 当前不支持未启用邮件的安全组。

集中部署支持向租户中的单个用户、组和每个人分配工作。 集中部署支持顶级组或没有父组的组中的用户，但不支持嵌套组或有父组的组中的用户。

请查看以下示例，在这里，柏隼、康霓以及销售部门组被分配了加载项。由于西海岸销售部门是嵌套组，赵强和熊飞未被分配加载项。

![销售部门的关系图。](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a>找出一个组是否包含嵌套组

若要找出一个组是否包含嵌套组，最简单的方法是查看 Outlook 内的组联系人卡片。 如果在电子邮件的"到"字段中输入组名称，然后在解析时选择组名称，它将显示该组是否包含用户或嵌套组。 在以下示例中，测试组 Outlook 联系人卡片的" **成员**"选项卡显示没有用户且只有两个子组。

![联系人卡片Outlook"选项卡。](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

可以解析某个组，查看该组是否是任何组的成员，从而进行反向查询。在以下示例中，可以在 Outlook 联系人卡片的" **成员身份**"选项卡下看到子组 1 是测试组的成员。

![联系人卡片Outlook选项卡。](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

或者，可以使用 Azure Active Directory 图形 API 运行查询，查找组内的组列表。有关详细信息，请参阅 [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations)（组操作 | 图形 API 参考）。

### <a name="contacting-microsoft-for-support"></a>联系 Microsoft 以获取支持

如果你或你的用户在使用已集中部署的 Office Web (Word、Excel 等 ) 应用时遇到加载加载项的问题，你可能需要联系 Microsoft 支持人员 (了解如何) 。 [](../../business-video/get-help-support.md) 在支持票证中提供有关Microsoft 365环境的信息。

| 平台 | 调式信息 |
|:-----|:-----|
|办公室 | Charles/Fiddler 日志  <br/>  租户 ID ([了解如何) ](/onedrive/find-your-office-365-tenant-id)  <br/>  CorrelationID。 查看其中一个 Office 页面的源并查找相关 ID 值并将其发送给支持人员：  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>` |
|丰富的客户端（Windows、Mac） | Charles/Fiddler 日志  <br/>  客户端应用内部版本号最好 ("文件/帐户"应用中 **的屏幕截图)** |

## <a name="related-content"></a>相关内容

[在管理中心部署外接程序 (](../manage/manage-deployment-of-add-ins.md) 文章) \
[管理中心中的外接程序 (](manage-addins-in-the-admin-center.md) 文章) \
[集中部署常见问题](../manage/centralized-deployment-faq.yml) (文章) \
[将业务Microsoft 365升级到](../setup/upgrade-users-to-latest-office-client.md)最新 Office 客户端 (文章) 
 
