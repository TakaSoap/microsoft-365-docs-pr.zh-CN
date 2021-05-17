---
title: 为Microsoft 365实验室或试验环境配置 Defender 支柱
description: 为Microsoft 365实验室或试验环境配置 Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security 和 Microsoft Defender for Endpoint 等 Defender 支柱。
keywords: 配置 Microsoft 365 Defender 试用版， Microsoft 365 Defender 试用配置， 配置 Microsoft 365 Defender 试点项目， 配置 Microsoft 365 Defender 支柱， Microsoft 365 Defender 支柱
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 05bdc9cbb678a3d6c1cee726fc4d8c2e45d2d360
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933501"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>为Microsoft 365实验室或试验环境配置 Defender 支柱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


创建 Microsoft 365 Defender 试用实验室或试验环境并部署它的过程分三个阶段：

|[![阶段 1：准备](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[阶段 1：准备](prepare-m365d-eval.md) |[![阶段 2：设置](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[阶段 2：设置](setup-m365deval.md) |![阶段 3：开始使用](../../media/phase-diagrams/onboard.png)<br/>阶段 3：开始使用 | [![返回到试点](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[返回到试点手册](m365d-pilot.md) |
|--|--|--|--|
|| |*你在这里！* | |

你当前处于配置阶段。

准备工作是任何成功部署的关键。 本文将指导你在准备部署适用于终结点的 Microsoft Defender 时需要考虑的要点。


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365Defender 支柱
Microsoft 365Defender 由四个支柱组成。 尽管一个支柱已经可为网络组织的安全性提供价值，但启用这四个Microsoft 365 Defender 支柱将为你的组织提供最大价值。

![适用于of_Microsoft、Microsoft Defender for Identity、终结点 Microsoft Defender for Endpoint、云应用、Microsoft Cloud App Security 和数据、Microsoft Defender for Office 365 的 365 Defender 解决方案的图像](../../media/mtp/m365pillars.png)

本部分将指导你配置：
-   Microsoft Defender for Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender for Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>配置 Microsoft Defender for Office 365

>[!NOTE]
>如果你已启用 Defender for Office 365。 

有一个 PowerShell 模块，名为 Office 365 高级威胁防护建议配置分析器 *(ORCA) ，* 可帮助确定其中一些设置。 在租户中以管理员角色运行时，get-ORCAReport 将有助于生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。 可以从 下载此模块 https://www.powershellgallery.com/packages/ORCA/ 。 

1. 导航到 [Office 365安全&中心](https://protection.office.com/homepage)  >  **威胁管理**  >  **策略"**。

   ![图像of_Office 365 安全&中心威胁管理策略页面](../../media/mtp-eval-32.png)
 
2. 单击 **"防钓鱼"，** 选择" **创建** "并填写策略名称和说明。 点击 **“下一步”**。

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，可在其中命名策略](../../media/mtp-eval-33.png)

   > [!NOTE]
   > 在 Microsoft Defender 中编辑高级防钓鱼策略Office 365。 将 **高级网络钓鱼阈值更改为** **2 - 攻击性**。

3. 单击" **添加条件** &quot;下拉菜单，然后选择您的域 (") "收件人域"。 点击 **“下一步”**。

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，您可以在其中添加其应用程序的条件](../../media/mtp-eval-34.png)
 
4. 查看设置。 单击 **"创建此策略** "以确认。 

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，可在其中查看设置并单击"创建此策略"按钮](../../media/mtp-eval-35.png)
 
5. 选择 **保险箱附件**"，然后选择"打开 **ATP for SharePoint、OneDrive 和 Microsoft Teams"** 选项。

   ![图像of_Office 365 安全&合规中心页面，可在其中打开 ATP for SharePoint、OneDrive 和 Microsoft Teams](../../media/mtp-eval-36.png)

6. 单击 + 图标以创建新的安全附件策略，以作为收件人域应用到你的域。 单击“保存”。

   !["of_Office 365 安全&合规中心"页面，可在其中创建新的新建安全附件策略](../../media/mtp-eval-37.png)
 
7. 接下来，选择 **"保险箱"** 策略，然后单击铅笔图标以编辑默认策略。

8. 确保未选中" **不跟踪用户** 单击安全链接时"选项，同时选择其余选项。 有关详细信息[保险箱链接](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365)设置。 单击“保存”。 

   !["of_Office 365 安全&中心"页面，其中显示未选中"不跟踪用户单击时安全"选项](../../media/mtp-eval-38.png)

9. 接下来， **选择"反恶意软件"** 策略，选择默认值，然后选择铅笔图标。

10. 单击 **设置** 选择 **是，然后使用默认通知文本** 启用 **恶意软件检测响应**。 打开 **"常见附件类型筛选器** "。 单击“保存”。

    !["of_Office 365 安全&合规中心"页面，其中显示恶意软件检测响应已打开且默认通知和常用附件类型筛选器已打开](../../media/mtp-eval-39.png)
  
11. 导航到 [Office 365安全&](https://protection.office.com/homepage)  >  **中心搜索**  >  **审核日志搜索** 并启用审核。

    !["of_Office 365 安全与&中心"页面，可在其中打开审核日志搜索](../../media/mtp-eval-40.png)

12. 将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成。 导航到 [Office 365安全&中心](https://protection.office.com/homepage)威胁管理资源管理器"，然后选择屏幕右上角设置适用于终结点的  >    >  **Microsoft Defender。** 在 Defender for Endpoint 连接对话框中，连接 **Microsoft Defender for Endpoint。**

    !["of_Office 365 安全&合规中心"页面，可在其中打开 Microsoft Defender for Endpoint 连接](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>为标识配置 Microsoft Defender

>[!NOTE]
>如果已启用 Microsoft Defender 标识，则跳过此步骤

1. 导航到Microsoft 365 [安全>](https://security.microsoft.com/info)**选择更多** Microsoft  >  **Defender 标识资源**。

   ![图像of_Microsoft 365 安全中心页面，其中提供打开 Microsoft Defender for Identity 的选项](../../media/mtp-eval-42.png)

2. 单击 **创建** 以启动 Microsoft Defender 标识向导。 

   !["of_Microsoft Defender for Identity 向导"页面，应单击"创建"按钮](../../media/mtp-eval-43.png)

3. 选择 **"提供用户名和密码"以连接到 Active Directory 林**。  

   ![图像of_Microsoft Defender for Identity 欢迎页面](../../media/mtp-eval-44.png)

4. 输入 Active Directory 本地凭据。 这可以是对 Active Directory 具有读取权限的任何用户帐户。

   ![Image of_Microsoft Defender for Identity Directory services 页面，你应该将凭据放在其中](../../media/mtp-eval-45.png)

5. 接下来，选择 **"下载传感器设置** "，将文件传输至域控制器。

   ![Image of_Microsoft Defender for Identity 页面，可在其中选择下载传感器设置](../../media/mtp-eval-46.png)

6. 执行 Microsoft Defender for Identity 传感器设置并开始遵循向导。

   ![Image of_Microsoft Defender for Identity 页面，你应单击旁边的页面，按照 Microsoft Defender for Identity 传感器向导操作](../../media/mtp-eval-47.png)
 
7. 在 **传感器** 部署类型上单击"下一步"。

   ![Image of_Microsoft Defender for Identity 页面，你应单击下一步转到下一页](../../media/mtp-eval-48.png)
 
8. 复制访问键，因为你需要在向导中下一步输入它。

   ![映像of_the"传感器"页面，应在其中复制需要在下一个 Microsoft Defender for Identity 传感器设置向导页中输入的访问密钥](../../media/mtp-eval-49.png)
 
9. 将访问键复制到向导中，**然后单击安装。** 

   ![映像of_Microsoft Defender for Identity 传感器向导页面，你应该提供访问密钥，然后单击安装按钮](../../media/mtp-eval-50.png)

10. 恭喜！已成功在域控制器上配置 Microsoft Defender 的 Identity。

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. 在 ["Microsoft Defender 标识设置](https://go.microsoft.com/fwlink/?linkid=2040449) "部分下，选择**Microsoft Defender for Endpoint **，然后打开切换。 单击“保存”。 

    ![适用于of_the Microsoft Defender 的"设置"页面的图像，应在其中打开 Microsoft Defender for Endpoint 切换](../../media/mtp-eval-52.png)


## <a name="configure-microsoft-cloud-app-security"></a>配置Microsoft Cloud App Security

> [!NOTE]
> 如果已启用此功能，请跳过Microsoft Cloud App Security。 

1. 导航到 [Microsoft 365安全中心](https://security.microsoft.com/info)  >  **更多**  >  **资源Microsoft Cloud App Security。**

   ![图像of_Microsoft 365 安全中心页面，可在其中看到 Microsoft 云应用卡，并单击打开按钮](../../media/mtp-eval-53.png)

2. 在集成 Microsoft Defender 标识的信息提示符下，选择 **启用 Microsoft Defender 的标识数据集成**。
  
   ![图像of_the信息提示，用于集成 Microsoft Defender for Identity，其中应选择"启用 Microsoft Defender for Identity 数据集成"链接](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 如果看不到此提示，这可能意味着 Microsoft Defender for Identity 数据集成已启用。 但是，如果您不确定，请与 IT 管理员联系以确认。 

3. 转到 **"设置"，** 打开 Microsoft **Defender for Identity 集成** 切换，然后单击"保存 **"。** 

   ![图像of_the设置页面，其中你应打开 Microsoft Defender for Identity 集成切换，然后单击保存](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 对于新的 Microsoft Defender for Identity 实例，此集成切换将自动打开。 在继续执行下一步之前，请确认 Microsoft Defender for Identity 集成已启用。
 
4. 在云发现设置下，选择 **Microsoft Defender 进行终结点集成**，然后启用集成。 单击“保存”。

   ![图像of_the Microsoft Defender for Endpoint 页面，其中选中了 Microsoft Defender for Endpoint 集成下的阻止未批准应用复选框。 单击"保存"。](../../media/mtp-eval-56.png)

5. 在"云发现设置"**下，** 选择"用户扩充"，然后启用与Azure Active Directory。

   ![用户扩充部分的图像，其中选中了"使用Azure Active Directory扩充发现的用户标识符" 复选框](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>配置 Microsoft Defender for Endpoint

>[!NOTE]
>如果你已启用适用于终结点的 Microsoft Defender，请跳过此步骤。

1. 导航到 [Microsoft 365安全中心](https://security.microsoft.com/info)  >  **"更多**  >  **Microsoft Defender 安全中心"。** 单击“打开”。

   !["of_Microsoft安全中心"页面中的"Microsoft 365 Defender 安全中心"选项的图像](../../media/mtp-eval-58.png)
 
2. 按照 Microsoft Defender for Endpoint 向导操作。 点击 **“下一步”**。 

   ![图像of_the Microsoft Defender 安全中心欢迎向导页面](../../media/mtp-eval-59.png)

3. 根据首选数据存储位置、数据保留策略、组织规模和选择加入预览功能进行选择。

   ![图像of_the页面，用于选择数据存储国家/地区、保留策略和组织规模。 完成选择后，单击"下一步"。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 之后，你无法更改某些设置，如数据存储位置。 

   点击 **“下一步”**。 

4. 单击 **"继续** "，它将预配适用于终结点租户的 Microsoft Defender。

   ![图像of_the提示您单击"继续"按钮以创建云实例的页面](../../media/mtp-eval-61.png)

5. 通过组策略、Microsoft Endpoint Manager或运行 Microsoft Defender for Endpoint 的本地脚本载入终结点。 为简单起见，本指南使用本地脚本。

6. 单击 **下载程序包** ，将载入脚本复制到你的 (程序包) 。

   ![提示of_page下载程序包按钮以将载入脚本复制到终结点的图像](../../media/mtp-eval-62.png)

7. 在终结点上，以管理员角色运行载入脚本并选择"Y"。 

   ![图像of_the运行载入脚本并选择"Y"继续操作命令行](../../media/mtp-eval-63.png)

8. 恭喜，你已载入你的第一个终结点。

   ![图像of_the命令行，可获取已载入第一终结点的确认信息。 按任意键继续](../../media/mtp-eval-64.png)

9. 从 Microsoft Defender for Endpoint 向导复制粘贴检测测试。

   ![图像of_the运行检测测试步骤，其中应单击"复制"复制应粘贴到命令提示符中的检测测试脚本](../../media/mtp-eval-65.png)

10. 将 PowerShell 脚本复制到提升的命令提示符并运行它。 

    ![图像of_command提示符，应在其中将 PowerShell 脚本复制到提升的命令提示符并运行它](../../media/mtp-eval-66.png)

11. 从 **向导中选择开始使用 Microsoft Defender for Endpoint。**

    ![图像of_the显示来自向导的确认提示，你应单击"开始使用 Microsoft Defender for Endpoint"](../../media/mtp-eval-67.png)
 
12. 请访问[Microsoft Defender 安全中心](https://securitycenter.windows.com/)。 转到 **"设置"，** 然后选择"**高级功能"。** 

    !["of_Microsoft Defender 安全中心设置菜单，其中应选择"高级功能"](../../media/mtp-eval-68.png)

13. 打开与 Microsoft **Defender 的 Identity 集成**。  

    ![映像of_Microsoft Defender 安全中心高级功能，需要打开的 Microsoft Defender for Identity 选项切换](../../media/mtp-eval-69.png)

14. 打开与威胁Office 365 **集成**。

    ![图像of_Microsoft Defender 安全中心高级功能Office 365需要打开的"威胁智能"选项切换](../../media/mtp-eval-70.png)

15. 打开与 Microsoft Cloud App Security **集成**。

    ![需要of_Microsoft Defender 安全中心高级功能Microsoft Cloud App Security选项切换的图像](../../media/mtp-eval-71.png)

16. 向下滚动并单击 **"保存首选项** "以确认新的集成。

    ![需要of_Save图像首选项按钮](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>启动 Microsoft 365 Defender 服务

>[!NOTE]
>从 2020 年 6 月 1 开始，Microsoft 会自动Microsoft 365符合条件的租户启用 Defender 功能。 有关详细信息，[请参阅Community许可证资格的](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)Microsoft 技术文章。 


转到["Microsoft 365安全中心"。](https://security.microsoft.com/homepage) 导航到 **设置，** 然后选择 **"Microsoft 365 Defender"。**

!["of_Microsoft安全中心"页面上的图像Microsoft 365 365 defender 设置屏幕截图 ](../../media/mtp-eval-72b.png) <br>

有关更全面的指南，请参阅启用[Microsoft 365 Defender。](m365d-enable.md) 

恭喜！ 你刚刚创建了你的 Microsoft 365 Defender 试用实验室或试点环境！ 现在，你可以熟悉 Microsoft 365 Defender 用户界面了！ 查看你可以从以下 Microsoft 365 Defender 交互式指南中了解哪些内容，并了解如何使用每个仪表板执行日常安全操作任务。

[请查看交互指南](https://aka.ms/MTP-Interactive-Guide)

接下来，你可以模拟攻击，并查看跨产品功能如何检测、创建警报以及自动响应终结点上的无文件攻击。

## <a name="next-step"></a>后续步骤

- [生成测试警报](generate-test-alert.md)- 在 defender Microsoft 365实验室中运行攻击模拟。