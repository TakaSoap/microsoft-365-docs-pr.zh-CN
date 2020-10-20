---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或您的整个组织启用 Outlook 和 web 上的 outlook 和 Outlook 网页版报告消息外接程序。
ms.openlocfilehash: b061d9db44b08a65b59481035c055a1b75eb6e3c
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600365"
---
# <a name="enable-the-report-message-add-in"></a>启用报表消息加载项

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 如果您是使用 Exchange Online 邮箱的 Microsoft 365 组织中的管理员，我们建议您在安全 & 合规性中心中使用提交门户。 有关详细信息，请参阅 [使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。

Outlook 和 web 上的 outlook 的报告邮件外接程序 (以前称为 Outlook Web App) 使人们可以轻松地报告误报 (电子邮件被标记为错误的) 或漏报 (错误的电子邮件将) 到 Microsoft 及其子公司进行分析。 Microsoft 使用这些提交改进电子邮件保护技术的有效性。

例如，假设有人将大量邮件报告为网络钓鱼。 [安全仪表板](security-dashboard.md)和其他报告中的此信息图面。 组织的安全团队可以使用此信息指示可能需要更新的反网络钓鱼策略。 或者，如果用户使用报告邮件外接程序报告大量被标记为垃圾邮件的邮件，则组织的安全团队可能需要调整 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。

此外，如果您的组织使用的是 [Office 365 高级威胁防护计划 1](office-365-atp.md) 或 [计划 2](office-365-ti.md)，则报告消息外接程序会为您组织的安全团队提供可用于查看和更新安全策略的有用信息。

管理员可以为组织启用报告邮件外接程序，单个用户可以自行安装。

如果您是单个用户，则可以 [为自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。

如果您是全局管理员或 Exchange Online 管理员，并且将 Exchange 配置为使用 OAuth 身份验证，则可以 [为您的组织启用报告消息外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。 现在，可以通过 [集中部署](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)使用报告消息 Add-In。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 报告邮件加载项适用于大多数 Microsoft 365 订阅和以下产品：

  - Outlook 网页版
  - Outlook 2013 SP1 或更高版本
  - Outlook 2016 for Mac
  - Outlook 包含在适用于企业的 Microsoft 365 应用程序中

- 报告消息外接程序对本地 Exchange 组织中的邮箱不可用。

- 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [用户提交策略](user-submission.md)。

- 您的现有 web 浏览器应与报告邮件外接程序一起使用。 但是，如果您注意到加载项不可用或无法按预期工作，请尝试使用不同的浏览器。

- 对于组织安装，需要将组织配置为使用 OAuth 身份验证。 有关详细信息，请参阅 [确定加载项的集中部署是否适用于你的组织](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理员需要是全局管理员角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-the-report-message-add-in-for-yourself"></a>获取自己的报告邮件外接程序

1. 转到 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，并搜索报告邮件外接程序。 若要直接转到报告邮件加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。

2. 单击 " **立即获取**"。

   ![报告消息-立即获取](../../media/ReportMessageGETITNOW.png)

3. 在显示的对话框中，查看使用条款和隐私策略，然后单击 " **继续**"。

4. 使用您的工作或学校帐户登录 (商业用途) 或你的 Microsoft 帐户 (以供个人使用) 。

安装并启用加载项后，您将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![报告邮件外接程序图标（适用于 Outlook）](../../media/OutlookReportMessageIcon.png)

- 在 web 上的 Outlook 中，图标如下所示：

  ![Outlook 网页报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

若要了解如何使用加载项，请参阅 [使用报告消息加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>为您的组织获取并启用报告邮件外接程序

> [!NOTE]
> 最长可能需要12个小时，外接程序才会显示在您的组织中。

1. 在 Microsoft 365 管理中心，转到 " **设置"、"集成应用 & 外接** 程序" 页 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> ，然后单击 " **部署外接程序**"。

   ![Microsoft 365 管理中心中的 "服务和外接程序" 页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 在 " **部署新的外接程序** " 弹出对话框中，查看信息，然后单击 " **下一步**"。

3. 在下一页上，单击 **"从存储区中选择"**。

   ![部署新的加载项页面](../../media/NewAddInScreen2.png)

4. 在出现的 " **选择外接程序** " 页中，单击 **"搜索** " 框，输入 **报告消息**，然后单击 " **搜索** ![ 搜索" 图标 ](../../media/search-icon.png) 。 在结果列表中，找到 " **报告消息** "，然后单击 " **添加**"。

   ![选择加载项搜索结果](../../media/NewAddInScreen3.png)

5. 在出现的对话框中，查看许可和隐私信息，然后单击 " **继续**"。

6. 在出现的 " **配置外接程序** " 页中，配置以下设置：

   - **分配的用户**：选择下列值之一：

     - 默认)  (的**所有人**
     - **特定用户/组**
     - **就我自己**

   - **部署方法**：选择下列值之一：

     - **固定 (默认) **：加载项将自动部署到指定的用户，并且无法将其删除。
     - **可用**：用户可以在**家庭**版中安装外接程序 \> **Get add-ins** \> **管理员管理**。
     - **可选**：将加载项自动部署到指定的用户，但可以选择将其删除。

   ![配置加载项页面](../../media/configure-add-in.png)

   完成后，请单击 " **部署**"。

7. 在出现的 " **部署报告邮件** " 页中，您将看到一个进度报告，随后将会看到已部署加载项的确认信息。 阅读信息后，单击 " **下一步**"。

   !["部署报告邮件" 页](../../media/deploy-report-message-page.png)

8. 在出现的 " **通知外接程序** " 页上，查看信息，然后单击 " **关闭**"。

   ![通知加载项页面](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用报告邮件加载项

为其分配了加载项的人员将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![报告邮件外接程序图标（适用于 Outlook）](../../media/OutlookReportMessageIcon.png)

- 在 web 上的 Outlook 中，图标如下所示：

  ![Outlook 网页报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

当您通知用户有关报告邮件加载项时，请包含 [使用报告邮件加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>查看或编辑报告邮件外接程序的设置

1. 在 Microsoft 365 管理中心，转到上的 " **服务" & "外接程序** " 页 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 。

   ![新 Microsoft 365 管理中心中的 "服务和 Add-Ins" 页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 查找并选择 **报告邮件** 加载项。

3. 在显示的 " **编辑报告消息** " 浮出控件中，查看并编辑组织的相应设置。 完成时，请单击“保存”****。

   ![报告邮件外接程序的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>查看和查看报告的邮件

若要查看用户向 Microsoft 报告的邮件，您可以选择以下选项：

- 使用管理提交门户。 有关详细信息，请参阅 [View user 报送 To Microsoft](admin-submission.md#view-user-submissions-to-microsoft)。

- 创建邮件流规则 (也称为传输规则) 发送报告的邮件的副本。 有关说明，请参阅 [使用邮件流规则查看用户报告给 Microsoft 的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
