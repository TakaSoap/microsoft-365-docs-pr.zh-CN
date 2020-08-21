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
description: 了解如何为单个用户或整个组织启用 Outlook 和 Outlook 网页版的报告邮件加载项。
ms.openlocfilehash: 45f67e4c88d311254a0d922baed66178c3f672a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826633"
---
# <a name="enable-the-report-message-add-in"></a>启用报表消息加载项

> [!NOTE]
> 如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议你在安全与自动安全与合规中心内使用&门户。 有关详细信息，请参阅["使用管理员提交"将可取的垃圾邮件、网络钓鱼邮件、URL 和文件提交到 Microsoft。](admin-submission.md)

用于 Outlook 和 Web 上的 Outlook 网页版的报告消息加载项 (Outlook Web App) 用户可以轻松地报告误报邮件 (标记为错误的) 或漏报电子邮件 (允许) Microsoft 及其关联来进行分析。 Microsoft 使用这些提交来提高电子邮件保护技术的有效性。

例如，假定用户要将大量邮件报告为网络钓鱼。 此信息会出现在 [安全仪表板](security-dashboard.md) 和其他报告中。 组织的安全团队可以将此信息用作反网络钓鱼策略可能需要更新的指示。 或者，如果用户要报告大量使用"报告邮件"外接程序标记为"非垃圾邮件"的邮件，则您组织的安全团队可能需要调整 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。

此外，如果组织使用的是 [Office 365 高级威胁防护计划 1](office-365-atp.md) 或计划 [2，](office-365-ti.md)则报告邮件加载项还会为组织的安全团队提供有用的信息，可用于审查和更新安全策略。

管理员可以为组织启用报告消息加载项，且单个用户可以为自己安装报告消息加载项。

如果你是单个用户，可以 [自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。

如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 被配置为使用 OAuth 身份验证，则可 [为组织启用报告邮件加载项](#get-and-enable-the-report-message-add-in-for-your-organization)。 现在可以通过集中部署提供" [报告消息"加载项](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 报告消息加载项适用于大多数 Microsoft 365 订阅和以下产品：

  - Outlook 网页版
  - Outlook 2013 SP1 或更高版本
  - Outlook 2016 for Mac
  - Microsoft 365 企业版应用版中包含 Outlook

- 报告邮件外接程序不适用于本地 Exchange 组织的邮箱。

- 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [在 Exchange Online 中指定提交用户收集垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。

- 现有 Web 浏览器应与报告邮件加载项一起使用。 但是，如果你注意到外接程序不可用或无法按预期正常运行，请尝试使用其他浏览器。

- 对于组织安装，需要将组织配置为使用 OAuth 身份验证。 有关详细信息，请参阅"[确定加载项集中部署是否适用于贵组织。](../../admin/manage/centralized-deployment-of-add-ins.md)

- 管理员必须是全局管理员角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-the-report-message-add-in-for-yourself"></a>为自己获取报告消息加载项

1. 转到 Microsoft <https://appsource.microsoft.com/marketplace/apps> AppSource，并搜索报告邮件加载项。 若要直接转到报告消息加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。

2. 单击 **"立即获取"。**

   ![报告消息 - 立即获取](../../media/ReportMessageGETITNOW.png)

3. 在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**

4. 使用你的工作或学校帐户 (以使用) 或 Microsoft 帐户管理员 (个人使用数据) 。

安装并启用加载项后，将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![Outlook 的报告邮件外接程序图标](../../media/OutlookReportMessageIcon.png)

- 在 Outlook 网页版中，图标如下所示：

  ![Outlook 网页版报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

若要了解如何使用外接程序，请参阅 ["报告邮件"加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>为组织获取并启用报告邮件加载项

> [!NOTE]
> 最长可能需要 12 小时，外接程序才能显示在组织中。

1. 在 Microsoft 365 管理中心，转到**上"服务 &"** 加载项 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 页面，然后单击"**部署加载项"。**

   ![Microsoft 365 管理中心的"服务和加载项"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 在随**即显示的新外接程序浮**出控件中，查看信息，然后单击"下一步 **"。**

3. 在下一页上，单击 **"应用商店"中的"选择"。**

   ![部署新的外接程序页面](../../media/NewAddInScreen2.png)

4. 在出现 **的"选择外接程序** 页面中单击"框，在'搜索' **框中** 单击，输入 **'报告消息'，** 然后单击' **搜索搜索** ![ '图标 ](../../media/search-icon.png) 。 在结果列表中，找到"**报告邮件"，** 然后单击"添加 **"。**

   ![选择加载项搜索结果](../../media/NewAddInScreen3.png)

5. 在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**

6. 在 **显示的"配置** 加载项"页中，配置以下设置：

   - **已分配用户**：选择以下值之一：

     - **默认情况下， (") **
     - **特定用户/组**
     - **就我自己**

   - **部署方法**：选择以下值之一：

     - **修复 (默认) ： **加载项自动部署到指定用户，且不能将其删除。
     - **可用**：用户可以在"家庭获取" **外接程序** \> **上安装管理员** \> **管理的加载项**。
     - **可选**：外接程序将自动部署到指定的用户，但可以选择删除它。

   ![配置加载项页面](../../media/configure-add-in.png)

   完成后，请单击"部署 **"。**

7. 在 **随即显示的** "部署报告邮件"页中，您将看到进度报告，后跟一个确认已部署外接程序的确认。 阅读这些信息后，单击"下一**步"。**

   !["部署报告消息"页面](../../media/deploy-report-message-page.png)

8. 在**出现的"通知外接程序"页上**，查看信息，然后单击"关闭 **"。**

   ![通知外接程序页面](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用报告消息加载项

为其分配有加载项的用户将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![Outlook 的报告邮件外接程序图标](../../media/OutlookReportMessageIcon.png)

- 在 Outlook 网页版中，图标如下所示：

  ![Outlook 网页版报表邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

如果你向用户通知报告邮件加载项，请加入一个指向 [使用报告邮件加载项的链接](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>查看或编辑报告消息加载项的设置

1. 在 Microsoft 365 管理中心，转到 **"服务"&页面** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 。

   ![新版 Microsoft 365 管理中心的"服务和加载项"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 查找并选择 **"报告** 消息"加载项。

3. 在随 **后显示的** "编辑报告消息"浮出控件中，根据你的组织查看和编辑设置。 完成时，请单击“保存”****。

   ![报告消息加载项的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>查看和审阅报告的邮件

若要查看用户报告给 Microsoft 的邮件，你可以选择以下选项：

- 使用管理提交门户。 有关详细信息，请参阅"[查看用户提交至 Microsoft"。](admin-submission.md#view-user-submissions-to-microsoft)

- 创建邮件流规则类型 (也称为传输规则，) 发送已报告邮件的副本。 有关说明，请参阅 ["邮件流规则"来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
