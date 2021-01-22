---
title: 为试用实验室或试验环境配置 Microsoft 365 Defender 支柱
description: 为试用实验室或试点环境配置 Microsoft 365 Defender 支柱，如 Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security 和 Microsoft Defender for Endpoint。
keywords: 配置 Microsoft 威胁防护试用版， Microsoft 威胁防护试用配置， 配置 Microsoft 威胁防护试点项目， 配置 Microsoft 威胁防护支柱， Microsoft 威胁防护支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932234"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>为试用实验室或试验环境配置 Microsoft 365 Defender 支柱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


创建 Microsoft 365 Defender 试用实验室或试验环境并部署它的过程分三个阶段：

|[![第 1 阶段：准备](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[阶段 1：准备](prepare-mtpeval.md) |[![阶段 2：设置](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[阶段 2：设置](setup-mtpeval.md) |![阶段 3：载入](../../media/phase-diagrams/onboard.png)<br/>阶段 3：载入 | [![返回到试点](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[返回到试点手册](mtp-pilot.md) |
|--|--|--|--|
|| |*你在这里！* | |

你当前处于配置阶段。

准备是任何成功部署的关键。 本文将指导你在准备部署 Microsoft Defender for Endpoint 时需要考虑的要点。


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender 支柱
Microsoft 365 Defender 由四个支柱组成。 尽管一个支柱已经可为网络组织的安全提供价值，但启用四个 Microsoft 365 Defender 支柱将赋予你的组织最大价值。

![适用于of_Microsoft、Microsoft Defender for Identity、终结点 Microsoft Defender for Endpoint、云应用、Microsoft Cloud App Security 和数据、Microsoft Defender for Office 365 的 365 Defender 解决方案的图像](../../media/mtp/m365pillars.png)

本部分将指导你配置：
-   Microsoft Defender for Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender for Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>配置 Microsoft Defender for Office 365

>[!NOTE]
>如果你已启用 Office 365 的 Defender，请跳过此步骤。 

有一个 PowerShell 模块，称为 *OFFICE 365* 高级威胁防护建议配置分析器 (ORCA) 可帮助确定其中一些设置。 当以租户中的管理员角色运行时，get-ORCAReport 将有助于生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。 可以从中下载此模块 https://www.powershellgallery.com/packages/ORCA/ 。 

1. 导航到 [Office 365 安全&合规中心](https://protection.office.com/homepage)  >  **威胁管理**  >  **策略**。

   ![图像of_Office 365 安全&合规中心威胁管理策略页](../../media/mtp-eval-32.png)
 
2. 单击 **"防钓鱼"，** 选择 **"** 创建"并填写策略名称和说明。 单击“**下一步**”。

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，可在其中命名策略](../../media/mtp-eval-33.png)

   > [!NOTE]
   > 在 Microsoft Defender for Office 365 中编辑高级防钓鱼策略。 将 **高级网络钓鱼阈值更改为** **2 - 主动。**

3. 单击 **"添加条件** "下拉菜单，然后选择您的 (域) 收件人域。 单击“**下一步**”。

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，您可以在其中添加其应用程序的条件](../../media/mtp-eval-34.png)
 
4. 查看设置。 单击 **"创建此策略** "以确认。 

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，可在其中查看设置并单击"创建此策略"按钮](../../media/mtp-eval-35.png)
 
5. 选择 **"安全** 附件"，然后选择"启用 **适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP"** 选项。

   !["of_Office 365 安全与合规&页面，可在其中打开适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../../media/mtp-eval-36.png)

6. 单击 + 图标以创建新的安全附件策略，以收件人域形式应用到域。 单击“**保存**”。

   !["of_Office 365 安全&合规中心"页面，可在其中创建新创建一个新的安全附件策略](../../media/mtp-eval-37.png)
 
7. 接下来，选择 **安全链接** 策略，然后单击铅笔图标以编辑默认策略。

8. 确保未选择 **"不** 跟踪用户单击安全链接时"选项，同时选择其余选项。 有关详细信息 [，请参阅安全](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 链接设置。 单击“**保存**”。 

   ![图像of_Office 365 安全&合规中心页面，其中显示未选择"当用户单击安全时不跟踪"选项](../../media/mtp-eval-38.png)

9. 接下来， **选择"反恶意软件策略"，** 选择默认值，然后选择铅笔图标。

10. 单击 **"** 设置 **"，然后选择"是** "，然后使用默认通知文本启用 **恶意软件检测响应**。 打开 **常见附件类型筛选器** 。 单击“**保存**”。

    ![显示of_Office 365 安全&合规中心页面的图像，该页面显示恶意软件检测响应已使用默认通知打开，并且常见附件类型筛选器已打开](../../media/mtp-eval-39.png)
  
11. 导航到 [Office 365 安全&合规中心](https://protection.office.com/homepage)  >  **搜索**  >  **审核日志搜索** 并打开审核。

    !["of_Office 365 安全&合规中心"页面，可在其中打开审核日志搜索](../../media/mtp-eval-40.png)

12. 将适用于 Office 365 的 Microsoft Defender 与 Microsoft Defender for Endpoint 集成。 导航到[Office 365 安全](https://protection.office.com/homepage)&合规中心威胁管理资源管理器，然后选择屏幕右上角的 Microsoft Defender 终结点  >    >  设置。  在 Defender for Endpoint 连接对话框中，打开 **"连接到适用于终结点的 Microsoft Defender"。**

    ![365 of_Office 365 安全&合规中心页面，可在其中打开 Microsoft Defender for Endpoint 连接](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>为标识配置 Microsoft Defender

>[!NOTE]
>如果已启用 Microsoft Defender 标识，请跳过此步骤

1. 导航到 [Microsoft 365 安全中心>](https://security.microsoft.com/info)选择  >  **更多 Microsoft Defender 标识资源**。

   ![图像of_Microsoft 365 安全中心页面，其中提供了打开 Microsoft Defender for Identity 的选项](../../media/mtp-eval-42.png)

2. 单击 **"** 创建"以启动 Microsoft Defender for Identity 向导。 

   ![应of_Microsoft创建按钮的 Defender for Identity 向导页面的图像](../../media/mtp-eval-43.png)

3. 选择 **"提供用户名和密码"以连接到 Active Directory 林**。  

   ![映像of_Microsoft Defender for Identity 欢迎页面](../../media/mtp-eval-44.png)

4. 输入 Active Directory 本地凭据。 这可以是对 Active Directory 具有读取权限的任何用户帐户。

   ![适用于of_Microsoft Defender 的 Identity Directory 服务页面的图像，你应该将凭据放在其中](../../media/mtp-eval-45.png)

5. 接下来，选择 **"下载传感器设置** "，将文件传输至域控制器。

   !["of_Microsoft Defender for Identity"页面，可在其中选择"下载传感器设置"](../../media/mtp-eval-46.png)

6. 执行 Microsoft Defender for Identity 传感器设置，然后开始执行向导。

   !["of_Microsoft Defender for Identity"页面，应单击旁边的"Microsoft Defender for Identity"传感器向导](../../media/mtp-eval-47.png)
 
7. 在 **传感器** 部署类型上单击"下一步"。

   ![适用于of_Microsoft Defender 的图像页面，应单击该页面旁边的页面转到下一页](../../media/mtp-eval-48.png)
 
8. 复制访问密钥，因为你需要在向导中下一步输入它。

   ![图像of_the传感器页面，应在其中复制需要在下一个 Microsoft Defender for Identity 传感器设置向导页中输入的访问密钥](../../media/mtp-eval-49.png)
 
9. 将访问键复制到向导中，然后单击"**安装"。** 

   ![应of_Microsoft访问密钥，然后单击安装按钮的 Defender for Identity 传感器向导页面的图像](../../media/mtp-eval-50.png)

10. 恭喜！你已成功在域控制器上配置 Microsoft Defender 的 Identity。

    ![映像of_Microsoft Defender for Identity 传感器向导安装完成，应单击"完成"按钮](../../media/mtp-eval-51.png)
 
11. 在 ["Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) 设置"部分下，选择"适用于终结点的 Microsoft Defender"**，然后打开切换。 单击“**保存**”。 

    ![适用于of_the Microsoft Defender 标识设置页面的图像，应在其中打开 Microsoft Defender for Endpoint 切换](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP 已重新品牌为 Microsoft Defender for Endpoint。 为了保持一致性，将推出跨所有门户的重新品牌更改。


## <a name="configure-microsoft-cloud-app-security"></a>配置 Microsoft Cloud App Security

>[!NOTE]
>如果已启用 Microsoft Cloud App Security，请跳过此步骤。 

1. 导航到 [Microsoft 365 安全中心](https://security.microsoft.com/info)  >  **更多**  >  **资源 Microsoft Cloud App Security。**

   ![图像of_Microsoft 365 安全中心页面，可在其中看到 Microsoft Cloud App 卡，并单击打开按钮](../../media/mtp-eval-53.png)

2. 在信息提示符下集成 Microsoft Defender for Identity，选择 **"启用 Microsoft Defender for Identity"数据集成**。
  
   ![图像of_the信息提示以集成 Microsoft Defender for Identity，应选择"启用 Microsoft Defender for Identity 数据集成"链接](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 如果看不到此提示，这可能意味着 Microsoft Defender for Identity 数据集成已启用。 但是，如果您不确定，请与 IT 管理员联系以确认。 

3. 转到"**设置"，** 打开 **Microsoft Defender 的标识集成** 切换，然后单击"**保存"。** 

   ![图像of_the设置页面，应打开 Microsoft Defender for Identity 集成切换，然后单击"保存"](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 对于新的 Microsoft Defender for Identity 实例，此集成切换将自动打开。 在继续执行下一步之前，请确认 Microsoft Defender for Identity 集成已启用。
 
4. 在云发现设置下，选择 **Microsoft Defender 进行终结点集成**，然后启用集成。 单击“**保存**”。

   ![图像of_the Microsoft Defender for Endpoint 页面，其中选中了 Microsoft Defender for Endpoint 集成下的未批准应用复选框。 单击"保存"。](../../media/mtp-eval-56.png)

5. 在"云发现设置"下 **，选择"** 用户扩充"，然后启用与 Azure Active Directory 的集成。

   ![用户扩充部分的图像，其中选中了"使用 Azure Active Directory 用户名扩充发现的用户标识符" 复选框](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>配置适用于终结点的 Microsoft Defender

>[!NOTE]
>如果你已启用适用于终结点的 Microsoft Defender，请跳过此步骤。

1. 导航到 [Microsoft 365 安全中心](https://security.microsoft.com/info)  >  **更多**  >  **资源 Microsoft Defender 安全中心**。 单击“打开”。

   ![Microsoft 365 安全中心页of_Microsoft Defender 安全中心选项的图像](../../media/mtp-eval-58.png)
 
2. 按照 Microsoft Defender for Endpoint 向导操作。 单击“**下一步**”。 

   ![映像of_the Microsoft Defender 安全中心欢迎向导页面](../../media/mtp-eval-59.png)

3. 根据首选数据存储位置、数据保留策略、组织规模和选择加入预览功能进行选择。

   ![图像of_the页面，用于选择数据存储国家/地区、保留策略和组织规模。 完成选择后单击"下一步"。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 之后无法更改某些设置，如数据存储位置。 

   单击“**下一步**”。 

4. 单击 **"** 继续"，它将预配适用于终结点租户的 Microsoft Defender。

   ![提示of_the继续按钮以创建云实例的页面图像](../../media/mtp-eval-61.png)

5. 通过组策略、Microsoft Endpoint Manager 或运行 Microsoft Defender for Endpoint 的本地脚本载入终结点。 为简单起见，本指南使用本地脚本。

6. 单击 **"下载** 程序包"，将载入脚本复制到终结点 () 。

   ![提示of_page下载程序包按钮以将载入脚本复制到终结点的图像](../../media/mtp-eval-62.png)

7. 在终结点上，以管理员角色运行载入脚本并选择 Y。 

   ![运行of_the脚本并选择 Y 继续运行的命令行中的图像](../../media/mtp-eval-63.png)

8. 恭喜，你已载入第一个终结点。

   ![图像of_the命令行，可获取已载入第一终结点的确认信息。 按任意键继续](../../media/mtp-eval-64.png)

9. 从 Microsoft Defender for Endpoint 向导复制粘贴检测测试。

   ![运行of_the测试步骤时，应单击"复制"复制应粘贴到命令提示符中的检测测试脚本的图像](../../media/mtp-eval-65.png)

10. 将 PowerShell 脚本复制到提升的命令提示符并运行它。 

    ![图像of_command提示符，应在其中将 PowerShell 脚本复制到提升的命令提示符并运行它](../../media/mtp-eval-66.png)

11. 从 **向导中选择"开始使用 Microsoft Defender for Endpoint"。**

    ![图像of_the来自向导的确认提示，你应单击"开始使用 Microsoft Defender for Endpoint"](../../media/mtp-eval-67.png)
 
12. 访问 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。 转到"**设置"，** 然后选择 **"高级功能"。** 

    ![应of_Microsoft高级功能的 Defender 安全中心设置菜单上的图像](../../media/mtp-eval-68.png)

13. 打开与 Microsoft **Defender for Identity 的集成**。  

    ![映像of_Microsoft Defender 安全中心高级功能，需要打开的 Microsoft Defender for Identity 选项切换](../../media/mtp-eval-69.png)

14. 打开与 Office **365 威胁智能的集成**。

    ![需要of_Microsoft Defender 安全中心高级功能、Office 365 威胁智能选项切换的图像](../../media/mtp-eval-70.png)

15. 打开与 **Microsoft Cloud App Security 的集成**。

    ![需要of_Microsoft Defender 安全中心高级功能、Microsoft Cloud App Security 选项切换功能的图像](../../media/mtp-eval-71.png)

16. 向下滚动并单击 **"保存首选项** "以确认新的集成。

    ![需要of_Save图像首选项按钮](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>启动 Microsoft 365 Defender 服务

>[!NOTE]
>从 2020 年 6 月 1 开始，Microsoft 会自动为所有符合条件的租户启用 Microsoft 365 Defender 功能。 有关详细信息， [请参阅此有关许可证资格](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 的 Microsoft 技术社区文章。 


转到 [Microsoft 365 安全中心](https://security.microsoft.com/homepage)。 导航到 **"** 设置"，然后选择 **Microsoft 365 Defender。**

![Microsoft 365 安全中心设置of_Microsoft中的"365 Defender"选项屏幕截图 ](../../media/mtp-eval-72b.png) <br>

有关更全面的指南，请参阅"[打开 Microsoft 365 Defender"。](mtp-enable.md) 

恭喜！ 你刚刚创建了 Microsoft 365 Defender 试用实验室或试验环境！ 现在，你可以熟悉 Microsoft 365 Defender 用户界面！ 查看可以从以下 Microsoft 365 Defender 交互式指南中了解哪些内容，并了解如何使用每个仪表板执行日常安全操作任务。


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

接下来，你可以模拟攻击，并查看跨产品功能如何检测、创建警报并自动响应终结点上的无文件攻击。

## <a name="next-step"></a>后续步骤
|[攻击模拟阶段](mtp-pilot-simulate.md) | 为 Microsoft 365 Defender 试点环境运行攻击模拟。
|:-------|:-----|
