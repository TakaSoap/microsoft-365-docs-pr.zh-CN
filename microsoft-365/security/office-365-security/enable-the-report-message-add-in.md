---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或整个组织启用 Outlook 和 Web 上的 Outlook 报告邮件外接程序。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08ad2f61cc5dcd2e59af89ca788319c81e2f6bdb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287361"
---
# <a name="enable-the-report-message-add-in"></a>启用报表消息加载项

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> 如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议您使用安全与合规中心&提交门户。 有关详细信息，请参阅使用管理员提交将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)

Outlook 和 Web 上的 Outlook 的"报告邮件"和"报告钓鱼"外接程序 (以前称为 Outlook Web App)  (，使用户能够轻松地将标记为错误) 或漏报 (的误报 () 错误电子邮件报告给 Microsoft 及其关联公司进行分析。

Microsoft 使用这些提交来提高电子邮件保护技术的有效性。 例如，如果用户报告大量使用报告邮件外接程序标记为"非垃圾邮件"的邮件，则组织的安全团队可能需要调整反垃圾邮件 [策略](configure-your-spam-filter-policies.md)。

可以安装"报告邮件"或"报告钓鱼"加载项。 如果希望用户仅报告网络钓鱼邮件，请在你的组织中部署报告网络钓鱼外接程序。 有关详细信息，请参阅"[启用报告网络钓鱼外接程序"。](enable-the-report-phish-add-in.md)

报告邮件外接程序提供了报告垃圾邮件和网络钓鱼邮件的选项。 管理员可以为组织启用"报告消息"加载项，并且单个用户可以自行安装它。

如果你是单个用户，您可以为自己启用报告 [消息外接程序](#get-the-report-message-add-in-for-yourself)。

如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，您可以为组织启用报告邮件 [外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。 报告消息Add-In现在通过 [集中部署提供](../../admin/manage/centralized-deployment-of-add-ins.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 报告消息外接程序适用于大多数 Microsoft 365 订阅和以下产品：

  - Outlook 网页版
  - Outlook 2013 SP1 或更高版本
  - Outlook 2016 for Mac
  - Microsoft 365 企业应用版中包含的 Outlook
  - 适用于 iOS 和 Android 的 Outlook 应用

- 报告邮件外接程序对内部部署 Exchange 组织的邮箱不可用。

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅 [用户提交策略](user-submission.md)。

- 现有的 Web 浏览器应该与"报告消息"加载项一起工作。 但是，如果发现加载项不可用或未正常工作，请尝试其他浏览器。

- 对于组织安装，组织需要配置为使用 OAuth 身份验证。 有关详细信息，请参阅"确定外接程序的集中部署[是否适用于你的组织"。](../../admin/manage/centralized-deployment-of-add-ins.md)

- 管理员需是全局管理员角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-the-report-message-add-in-for-yourself"></a>为自己获取报告消息外接程序

1. 转到 Microsoft AppSource， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告消息"加载项。 若要直接转到"报告邮件"加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。

2. 单击 **"立即获取"。**

   ![报告邮件 - 现在获取](../../media/ReportMessageGETITNOW.png)

3. 在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**

4. 使用工作或学校帐户登录 (商业) 或 Microsoft 帐户 (个人) 。

安装并启用加载项后，你将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![Outlook 的"报告邮件"加载项图标](../../media/OutlookReportMessageIcon.png)

- 在 Outlook 网页 Outlook 中，图标如下所示：

  ![Outlook 网页报表邮件外接程序图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

若要了解如何使用外接程序，请参阅"使用 [报告消息"加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>获取并启用组织的"报告邮件"加载项

> [!NOTE]
> 外接程序最多可能需要 12 小时才能显示在组织中。

1. 在 Microsoft 365 管理中心中，转到"设置加载项"页面，如果看不到外接程序页面，请转到"集成应用"页面顶部的"设置集成应用外接程序" \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  \>  \> 链接。

2. 选择 **页面顶部的"** 部署外接程序"，然后选择"下一 **步"。**

   ![Microsoft 365 管理中心中的"服务和外接程序"页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 在 **出现的"部署新的外接程序"** 飞出中，查看信息，然后单击"下一 **步"。**

4. 下一页上，单击 **"从应用商店中选择"。**

   ![部署新的外接程序页面](../../media/NewAddInScreen2.png)

5. 在 **出现的"选择外接程序"** 页中，在"搜索"框中单击，输入 **"报告** 消息"，然后单击 **"搜索搜索"** ![ 图标 ](../../media/search-icon.png) 。 在结果列表中，找到 **"报告消息**"，然后单击"**添加"。**

   ![选择外接程序搜索结果](../../media/NewAddInScreen3.png)

6. 在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**

7. 在 **出现的"配置外接程序"** 页中，配置以下设置：

   - **已分配用户**：选择下列值之一：

     - **每个** (默认) 
     - **特定用户/组**
     - **就我自己**

   - **部署方法**：选择下列值之一：

     - **修复 (默认) ：** 外接程序将自动部署到指定用户，并且无法删除它。
     - **可用**：用户可以在家庭获取管理员管理的外接程序 \>  \> **中安装外接程序**。
     - **可选**：加载项会自动部署到指定用户，但他们可以选择将其删除。

   ![配置外接程序页面](../../media/configure-add-in.png)

   完成后，单击"部署 **"。**

8. 在 **出现的"** 部署报告消息"页中，你将看到一个进度报告，然后确认加载项已部署。 阅读信息后，单击"下一 **步"。**

   !["部署报告消息"页](../../media/deploy-report-message-page.png)

9. 在出现的 **"宣布加载项"** 页上，查看信息，然后单击"关闭 **"。**

   !["宣布加载项"页](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用"报告邮件"加载项

分配了加载项的人将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![Outlook 的"报告邮件外接程序"图标](../../media/OutlookReportMessageIcon.png)

- 在 Outlook 网页 Outlook 中，图标如下所示：

  ![Outlook 网页报告邮件外接程序图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

在通知用户有关报告邮件外接程序时，请包含一个指向"使用报告邮件 ["加载项的链接](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>查看或编辑报告邮件外接程序的设置

1. 在 Microsoft 365 管理中心中，转到"设置加载项"页面，如果看不到外接程序页面，请转到"集成应用"页面顶部的"设置集成应用外接程序" \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  \>  \> 链接。

   ![新Add-Ins Microsoft 365 管理中心中的"服务和服务"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 查找并选择 **"报告邮件** "加载项。

3. 在 **出现的"编辑报告** 消息"飞出控件中，根据组织情况查看和编辑设置。 完成时，请单击“保存”。

   ![报告邮件加载项的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>查看和查看报告的邮件

若要查看用户向 Microsoft 报告的邮件，可以使用以下选项：

- 使用管理员提交门户。 有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。

- 创建邮件流规则 (也称为传输规则) 发送报告的邮件副本。 有关说明， [请参阅"使用邮件流规则"查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
