---
title: 启用报告邮件或举报网络钓鱼加载项
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为用户、单个用户或整个组织启用 Outlook 和 Outlook 网页版 报告网络钓鱼外接程序。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 758ee81852d9037ce39cbfdc6f2c2d6ad795aff2
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466799"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>启用报告邮件或举报网络钓鱼加载项

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 如果你是拥有多个邮箱Microsoft 365组织的管理员Exchange Online，我们建议您使用 Microsoft 365 Defender 门户中的"提交"页面。 有关详细信息，请参阅使用管理员提交将可疑的垃圾邮件、网络钓鱼、 [URL 和文件提交到 Microsoft](admin-submission.md)。

Outlook 和 Outlook 网页版 (的"报告邮件"和"报告网络钓鱼"外接程序（以前称为 Outlook Web App) ）可轻松将误报 (错误电子邮件报告为错误) 或漏报 (允许) 向 Microsoft 及其关联公司报告错误电子邮件进行分析。

Microsoft 使用这些提交来提高电子邮件保护技术的有效性。 例如，假设用户正在使用报告网络钓鱼外接程序报告许多邮件。 此信息在安全仪表板和其他报告中显示。 组织的安全团队可以使用此信息指示可能需要更新反网络钓鱼策略。

可以安装"报告邮件"或"报告钓鱼邮件"加载项。 如果希望用户同时报告垃圾邮件和网络钓鱼邮件，请在你的组织中部署"报告邮件"加载项。

报告邮件外接程序提供报告垃圾邮件和网络钓鱼邮件的选项。 管理员可以为组织启用"报告邮件"外接程序，并且各个用户可以自行安装它。

报告网络钓鱼外接程序提供仅报告网络钓鱼邮件的选项。 管理员可以为组织启用报告网络钓鱼外接程序，单个用户可以自行安装它。

如果您是单个用户，您可以为自己启用这两个外接程序。

如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，您可以为组织启用"报告邮件"外接程序和"报告网络钓鱼"外接程序。 这两个加载项现在都可以通过集中 [部署使用](../../admin/manage/centralized-deployment-of-add-ins.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 报告邮件外接程序和报告网络钓鱼外接程序均与大多数 Microsoft 365订阅和以下产品一起工作：
  - Outlook 网页版
  - Outlook 2013 SP1 或更高版本
  - Outlook 2016 for Mac
  - Outlook应用程序Microsoft 365中包含的Enterprise
  - Outlook iOS 和 Android 版应用

- 这两个外接程序均不适用于共享邮箱。

- 这两个加载项均不适用于本地Exchange邮箱。 

- 现有的 Web 浏览器应同时使用报告邮件和报告钓鱼外接程序。但是，如果发现加载项不可用或无法正常使用，请尝试其他浏览器。

- 对于组织安装，组织需要配置为使用 OAuth 身份验证。 有关详细信息，请参阅确定外接程序的集中部署 [是否适用于您的组织](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理员需为全局管理员角色组的成员。 有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

- 有关如何使用"报告邮件"功能报告邮件的信息，请参阅报告邮件[中的](report-false-positives-and-false-negatives.md)误报和Outlook。

- 具有 URL 筛选或安全解决方案 (如代理和/或防火墙) 的组织必须允许在 HTTPS 协议上访问 ipagave.azurewebsites.net 和 outlook.office.com 终结点。

### <a name="turn-off-the-built-in-reporting-experience"></a>关闭内置报告体验

我们不建议使用内置报告Outlook，因为它不使用用户[提交策略](./user-submission.md)。 我们建议改为使用报告邮件外接程序或报告钓鱼外接程序。

您必须先获得权限，然后才能运行此 cmdlet。 若要查找在贵组织中运行任何 cmdlet 或参数所需的权限，请参阅 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/find-exchange-cmdlet-permissions)。

运行以下 PowerShell 命令以禁用内置报告体验：

```powershell
Set-OwaMailboxPolicy -Identity OwaMailboxPolicy-Default -ReportJunkEmailEnabled $false
```

## <a name="get-the-report-message-add-in"></a>获取报告邮件外接程序

### <a name="get-the-report-message-add-in-for-yourself"></a>为自己获取报告邮件外接程序

1. 转到 Microsoft AppSource ， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告消息"加载项。 若要直接转到"报告邮件"加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180>。

2. 单击 **"立即获取"**。

   :::image type="content" source="../../media/ReportMessageGETITNOW.png" alt-text="&quot;获取它&quot;报告消息" lightbox="../../media/ReportMessageGETITNOW.png":::

3. 在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"**。

4. 使用工作或学校帐户登录 (商业用途) Microsoft 帐户 (个人使用) 。

安装并启用加载项后，你将看到以下图标：

- 在Outlook中，图标如下所示：

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/OutlookReportMessageIcon.png" alt-text="&quot;报告邮件&quot;外接程序图标的Outlook" lightbox="../../media/OutlookReportMessageIcon.png":::

- 在Outlook 网页版中，图标如下所示：

    > [!div class="mx-imgBorder"]
    > ![Outlook 网页版报告邮件外接程序图标。](../../media/owa-report-message-icon.png)

### <a name="get-the-report-message-add-in-for-your-organization"></a>获取组织的"报告邮件"加载项

> [!NOTE]
> 外接程序可能需要 12 个小时才能显示在组织中。

1. 在 [Microsoft 365 管理中心中](https://admin.microsoft.com/AdminPortal/Home?#/homepage)，转到"**设置** \> **集成应用"**。 单击 **"获取应用"**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-integrated-apps.png" alt-text="集成Microsoft 365 管理中心应用程序" lightbox="../../media/microsoft-365-admin-center-integrated-apps.png":::


2. 在 **出现的Microsoft 365 应用版** 页中，单击"搜索"**框中，输入**"**报告** 邮件"，然后单击"**搜索搜索**!["图标。](../../media/search-icon.png) 在结果列表中，查找并选择"报告 **邮件"**。 

3. 应用程序详细信息页面将打开。 选择 **"现在获取"**。 

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-report-message.png" alt-text="报告邮件外接程序" lightbox="../../media/microsoft-365-admin-center-report-message.png":::

4. 完成基本配置文件信息，然后单击"继续 **"**。 

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-profile-info.png" alt-text="报告邮件外接程序配置文件设置" lightbox="../../media/microsoft-365-admin-center-profile-info.png":::

5. 将 **打开"部署新应用** "飞出。 配置以下设置。 单击 **"下** 一步"转到下一页以完成设置。 

   - **添加用户**：选择下列值之一：
     - **就我自己**
     - **整个组织**
     - **特定用户/组**

   - **部署**：
     - **接受权限请求**：在进入下一页之前，请仔细阅读应用程序权限和功能。

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="../../media/microsoft-365-admin-center-deploy-new-app.png" alt-text="&quot;接受权限请求&quot;页" lightbox="../../media/microsoft-365-admin-center-deploy-new-app.png":::

     - **完成部署**：查看并完成外接程序的部署。 
     - **部署已完成**：选择 **"完成** "以完成设置。 

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="../../media/microsoft-365-admin-center-deployment-complete.png" alt-text="部署已完成的通知消息" lightbox="../../media/microsoft-365-admin-center-deployment-complete.png":::

## <a name="edit-settings-for-the-report-message-add-in"></a>编辑报告邮件外接程序的设置

1. 在Microsoft 365 管理中心中，转到"**设置** \> **集成应用"** \. 然后查找并选择 **"报告邮件** "外接程序。

2. 在出现的飞出控件中，选择 **"编辑用户"** 以编辑用户设置。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-report-message-edit.png" alt-text="&quot;报告消息&quot;飞出" lightbox="../../media/microsoft-365-admin-center-report-message-edit.png":::

3. 若要删除外接程序，请选择同一个飞出内容 **中的"操作****"下的**"删除应用"。 

## <a name="get-the-report-phishing-add-in"></a>获取报告网络钓鱼外接程序

### <a name="get-the-report-phishing-add-in-for-yourself"></a>为自己获取报告网络钓鱼外接程序

1. 转到 Microsoft AppSource ， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告钓鱼"加载项。

2. 单击 **"立即获取"**。

3. 在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"**。

4. 使用工作或学校帐户登录 (商业用途) Microsoft 帐户 (个人使用) 。

安装并启用加载项后，你将看到以下图标：

- 在Outlook中，图标如下所示：

  ![报告电子邮件的网络钓鱼外接程序Outlook。](../../media/Outlook-ReportPhishing.png)

- 在Outlook 网页版中，图标如下所示：

    > [!div class="mx-imgBorder"]
    > ![Outlook 网页版报告网络钓鱼外接程序图标。](../../media/OWA-ReportPhishing.png)

### <a name="get-the-report-phishing-add-in-for-your-organization"></a>获取组织的"报告网络钓鱼"外接程序

> [!NOTE]
> 外接程序可能需要 12 个小时才能显示在组织中。

1. 在 [Microsoft 365 管理中心中](https://admin.microsoft.com/AdminPortal/Home?#/homepage)，转到"**设置** \> **集成应用"**。 单击 **"获取应用"**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-integrated-apps.png" alt-text="集成Microsoft 365 管理中心应用程序" lightbox="../../media/microsoft-365-admin-center-integrated-apps.png":::

2. 在出现的 **Microsoft 365 应用版** 页中，单击"搜索"**框中，输入**"**报告** 网络钓鱼"，然后单击"搜索 **搜索"**![图标](../../media/search-icon.png)。 在结果列表中，查找并选择"报告 **网络钓鱼"**。 
 
3. 应用程序详细信息页面将打开。 选择 **"现在获取"**。

4. 完成基本配置文件信息，然后单击"继续 **"**。

5. 将 **打开"部署新应用** "飞出。 按照上述 [步骤完成](enable-the-report-message-add-in.md#get-the-report-message-add-in-for-your-organization) 设置。 

## <a name="edit-settings-for-the-report-phishing-add-in"></a>编辑报告网络钓鱼外接程序的设置

1. 在Microsoft 365 管理中心中，转到"**设置** \> **集成应用"** \. 然后查找并选择 **"报告网络钓鱼** 外接程序"。

2. 在出现的飞出控件中，选择 **"编辑用户"** 以编辑用户设置。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-report-phishing-edit.png" alt-text="报告网络钓鱼飞出" lightbox="../../media/microsoft-365-admin-center-report-phishing-edit.png":::

3. 若要删除外接程序，请选择同一个飞出内容 **中的"操作****"下的**"删除应用"。 
