---
title: 为试用版实验室或试点环境配置 Microsoft 365 Defender 支柱
description: 为你的试用实验室或试点环境配置 Microsoft 365 Defender 支柱，例如 Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft 云应用安全和 Microsoft Defender for Endpoint。
keywords: 配置 Microsoft 威胁防护试用版，Microsoft 威胁防护试用版配置，配置 Microsoft 威胁 Protection 试点项目，配置 Microsoft 威胁防护支柱，Microsoft 威胁防护支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131293"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>为试用版实验室或试点环境配置 Microsoft 365 Defender 支柱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


创建 Microsoft 365 Defender 试用版实验室或试点环境并对其进行部署的过程分为三个阶段：

|[![第1阶段：准备](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[第1阶段：准备](prepare-mtpeval.md) |[![阶段2：设置](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[阶段2：设置](setup-mtpeval.md) |![第3阶段：板载](../../media/phase-diagrams/onboard.png)<br/>第3阶段：板载 | [![返回试点](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[返回试点行动手册](mtp-pilot.md) |
|--|--|--|--|
|| |*你在这里！* | |

你当前正在配置阶段。

准备工作是任何成功部署的关键。 在本文中，你将指导你在准备部署 Microsoft Defender for Endpoint 时需要考虑的事项。


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender 支柱
Microsoft 365 Defender 由四个支柱组成。 尽管一个支柱可以为你的网络组织的安全性提供价值，但启用四个 Microsoft 365 Defender 个支柱将为你的组织提供最大价值。

![Image of_Microsoft 365 Defender 解决方案，适用于用户、Microsoft Defender for a Endpoint for Microsoft Defender for Endpoint、云应用、Microsoft 云应用安全性和数据、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

本部分将指导您配置：
-   Microsoft Defender for Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender for Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>配置 Microsoft Defender for Office 365

>[!NOTE]
>如果已经启用了适用于 Office 365 的 Defender，请跳过此步骤。 

有一个 PowerShell 模块称为 *Office 365 高级威胁防护建议的配置分析器 (ORCA)* ，可帮助确定其中一些设置。 在租户中以管理员身份运行时，ORCAReport 将帮助生成反垃圾邮件、反网络钓鱼和其他邮件清洁设置的评估。 您可以从下载此模块 https://www.powershellgallery.com/packages/ORCA/ 。 

1. 导航到 [Office 365 Security & 合规性中心](https://protection.office.com/homepage)  >  **威胁管理**  >  **策略**。

   ![Image of_Office 365 Security & 合规性中心威胁管理策略页](../../media/mtp-eval-32.png)
 
2. 单击 " **反网络钓鱼**"，选择 " **创建** 并填写策略名称和说明"。 单击“**下一步**”。

   ![Image of_Office 365 Security & 合规中心 "反网络钓鱼策略" 页，可在其中命名策略](../../media/mtp-eval-33.png)

   > [!NOTE]
   > 在 Microsoft Defender for Office 365 中编辑高级反网络钓鱼策略。 将 **高级网络钓鱼阈值** 更改为 **2-主动**。

3. 单击 " **添加条件** " 下拉菜单，并选择您的域 (s) 作为 "收件人域"。 单击“**下一步**”。

   ![Image of_Office 365 Security & 合规中心 "反网络钓鱼策略" 页，可在其中为其应用程序添加条件](../../media/mtp-eval-34.png)
 
4. 查看您的设置。 单击 " **创建此策略** " 以确认。 

   ![Image of_Office 365 Security & 合规性中心 "反网络钓鱼策略" 页，您可以在其中查看设置，然后单击 "创建此策略" 按钮](../../media/mtp-eval-35.png)
 
5. 选择 " **安全附件** "，然后选择 " **启用 SharePoint、OneDrive 和 MICROSOFT 团队的 ATP** " 选项。

   ![Image of_Office 365 Security & 合规中心页，可在其中为 SharePoint、OneDrive 和 Microsoft 团队打开 ATP](../../media/mtp-eval-36.png)

6. 单击 "+" 图标创建新的 "安全附件策略"，将其作为 "收件人域" 应用到域。 单击“**保存**”。

   ![Image of_Office 365 Security & 合规中心页，可在其中创建新的 "新建安全附件" 策略](../../media/mtp-eval-37.png)
 
7. 接下来，选择 " **安全链接** " 策略，然后单击铅笔图标以编辑默认策略。

8. 请确保未选中 " **如果用户单击安全链接时不进行跟踪** " 选项，而其余选项则处于选中状态。 有关详细信息，请参阅 [安全链接设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 。 单击“**保存**”。 

   ![Image of_Office 365 Security & 合规中心页面，该页面显示当用户单击 "安全" 未选中时选项不会进行跟踪](../../media/mtp-eval-38.png)

9. 接下来，选择 **反恶意软件** 策略，选择默认设置，然后选择 "铅笔" 图标。

10. 单击 " **设置** " 并选择 **"是"，并使用默认通知文本** 启用 **恶意软件检测响应**。 打开 **常用附件类型筛选器** 。 单击“**保存**”。

    ![Image of_Office 365 Security & 合规中心页面，该页面显示在启用恶意软件检测响应时启用默认通知并启用常用附件类型筛选器](../../media/mtp-eval-39.png)
  
11. 导航到 [Office 365 安全 & 合规性中心](https://protection.office.com/homepage)  >  **搜索**  >  **审核日志搜索**，然后启用审核。

    ![Image of_Office 365 Security & 合规中心页，可在其中打开审核日志搜索](../../media/mtp-eval-40.png)

12. 将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成。 导航到 [Office 365 Security & 合规性中心](https://protection.office.com/homepage)"  >  **威胁管理**  >  **资源管理器**，然后选择屏幕右上角的" **Microsoft Defender for Endpoint Settings 设置**"。 在 "用于终结点连接的 Defender" 对话框中，启用 " **连接到 Microsoft Defender For endpoint**"。

    ![Image of_Office 365 Security & 合规中心页面，可在此页面上打开 Microsoft Defender for Endpoint connection](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>配置 Microsoft Defender for Identity

>[!NOTE]
>如果已启用 Microsoft Defender for Identity，请跳过此步骤

1. 导航到 [microsoft 365 安全中心](https://security.microsoft.com/info)> 选择 **更多资源**  >  **microsoft Defender for Identity**。

   ![Image of_Microsoft 365 Security Center 页面，其中有一个用于打开 Microsoft Defender for Identity 的选项](../../media/mtp-eval-42.png)

2. 单击 " **创建** " 以启动 Microsoft Defender for Identity 向导。 

   !["Of_Microsoft 用于标识向导的 Defender" 页面（应在其中单击 "创建" 按钮）的图像](../../media/mtp-eval-43.png)

3. 选择 " **提供用户名和密码" 以连接到你的 Active Directory 林**。  

   ![适用于标识欢迎页面的 of_Microsoft Defender 的图像](../../media/mtp-eval-44.png)

4. 输入你的 Active Directory 本地凭据。 可以是具有 Active Directory 的读访问权限的任何用户帐户。

   ![Of_Microsoft 用于标识目录服务的 Defender 页面（应在其中放置凭据）的图像](../../media/mtp-eval-45.png)

5. 接下来，选择 " **下载传感器设置** 并将文件传输到域控制器"。

   ![可在其中选择 "下载传感器安装" 的 "用于标识的 of_Microsoft Defender" 页面的图像](../../media/mtp-eval-46.png)

6. 执行用于标识传感器设置的 Microsoft Defender，并开始遵循向导。

   ![Of_Microsoft 用于标识页面的 Defender 的图像，您应在此页面上单击 "下一步" 以遵循 Microsoft Defender for Identity 传感器向导](../../media/mtp-eval-47.png)
 
7. 在传感器部署类型中，单击 " **下一步** "。

   ![图像 of_Microsoft 用于标识页面的 Defender，您应在此页面上单击 "下一步" 转到 "下一页"](../../media/mtp-eval-48.png)
 
8. 复制访问键，因为在向导的下一步需要输入它。

   !["图像 of_the 传感器" 页，应在此页面上复制您需要在下一个 Microsoft Defender for Identity 传感器安装向导页中输入的访问密钥](../../media/mtp-eval-49.png)
 
9. 将访问键复制到向导中，然后单击 " **安装**"。 

   ![Image of_Microsoft 用于 Identity 传感器的 Defender 向导 "页面，您应在其中提供访问密钥，然后单击" 安装 "按钮](../../media/mtp-eval-50.png)

10. 恭喜，你已在你的域控制器上成功配置 Microsoft Defender for Identity。

    ![Image of_Microsoft Defender for Identity 传感器向导安装完成，您应在其中单击 "完成" 按钮](../../media/mtp-eval-51.png)
 
11. 在 " [Microsoft defender For Identity](https://go.microsoft.com/fwlink/?linkid=2040449) 设置" 部分中，选择 "* * microsoft Defender for Endpoint * *"，然后打开 "切换"。 单击“**保存**”。 

    !["Microsoft Defender for Identity settings" 页的图像 of_the 应在其中打开 Microsoft Defender for Endpoint 切换](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP 已 rebranded 为 Microsoft Defender for Endpoint。 所有门户的重塑更改都是为了实现一致性而推出的。


## <a name="configure-microsoft-cloud-app-security"></a>配置 Microsoft 云应用安全

>[!NOTE]
>如果已启用 Microsoft 云应用安全性，请跳过此步骤。 

1. 导航到 [microsoft](https://security.microsoft.com/info)  >  **More Resources**  >  **云应用安全性** 的 microsoft 365 安全中心更多资源。

   ![Image of_Microsoft 365 Security Center 页面，可在其中查看 Microsoft 云应用程序卡，并应单击 "打开" 按钮](../../media/mtp-eval-53.png)

2. 在信息提示符下，集成 Microsoft Defender for Identity 时，选择 " **启用 Microsoft defender 以实现标识数据集成**"。
  
   ![Image of_the 信息提示将 Microsoft Defender 集成到您应在其中选择 "启用 Microsoft Defender for Identity data integration" 链接的标识。](../../media/mtp-eval-54.png)

   > [!NOTE]
   > 如果看不到此提示，可能意味着已为 Microsoft Defender 提供了标识数据集成。 但是，如果你不确定，请联系你的 IT 管理员进行确认。 

3. 转到 " **设置**"，打开 **Microsoft Defender for Identity integration** 切换，然后单击 " **保存**"。 

   !["图像 of_the 设置" 页面，您应在此页面上打开 Microsoft Defender for Identity integration 切换，然后单击 "保存"](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > 对于新的 Microsoft Defender for Identity 实例，此集成切换将自动打开。 在继续下一步之前，请确认已启用 Microsoft Defender 身份集成。
 
4. 在 "云发现设置" 下，选择 " **Microsoft Defender For Endpoint integration**"，然后启用集成。 单击“**保存**”。

   !["Unsanctioned Microsoft defender for endpoint integration" 下的 "阻止应用程序" 复选框中的 "Microsoft Defender for Endpoint integration" 的 of_the 图像已选中。 单击"保存"。](../../media/mtp-eval-56.png)

5. 在 "云发现设置" 下，选择 " **用户扩充**"，然后启用与 Azure Active Directory 的集成。

   !["用户扩充的图像" 部分，其中的 "浓缩已发现用户标识符与 Azure Active Directory 用户名" 复选框处于选中状态](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>为终结点配置 Microsoft Defender

>[!NOTE]
>如果已启用 Microsoft Defender for Endpoint，请跳过此步骤。

1. 导航到 microsoft Defender 安全中心的 [microsoft 365 安全中心](https://security.microsoft.com/info)  >  **更多资源**  >  **Microsoft Defender Security Center**。 单击“打开”。

   ![Microsoft 365 安全中心页面中的 "of_Microsoft Defender 安全中心" 选项的图像](../../media/mtp-eval-58.png)
 
2. 遵循 Microsoft Defender for Endpoint 向导。 单击“**下一步**”。 

   ![Microsoft Defender 安全中心欢迎向导页面 of_the 的图像](../../media/mtp-eval-59.png)

3. 选择 "基于您的首选数据存储位置"、"数据保留策略"、"组织大小" 和 "选择性加入预览" 功能。

   !["图像 of_the" 页以选择数据存储国家/地区、保留策略和组织大小。 完成选择后，单击 "下一步"。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > 之后，您无法更改某些设置，如数据存储位置。 

   单击“**下一步**”。 

4. 单击 " **继续** "，它将预配你的 Microsoft Defender for Endpoint 租户。

   ![图像 of_the 页面提示您单击 "继续" 按钮以创建云实例](../../media/mtp-eval-61.png)

5. 通过组策略、Microsoft 终结点管理器或通过运行本地脚本到 Microsoft Defender for Endpoint 来集成你的终结点。 为简单起见，本指南使用本地脚本。

6. 单击 " **下载包** "，并将载入脚本复制到终结点 (s) 。

   ![图像 of_page 提示您单击 "下载包" 按钮以将载入脚本复制到终结点或终结点](../../media/mtp-eval-62.png)

7. 在终结点上，以管理员身份运行载入脚本，然后选择 "Y"。 

   ![在运行载入脚本的情况下，图像 of_the 命令行，并选择 "Y" 继续](../../media/mtp-eval-63.png)

8. 恭喜，你已载入你的第一个终结点。

   ![图像 of_the 命令行载入，您可以在其中获取您对第一个终结点所做的确认。 按任意键继续](../../media/mtp-eval-64.png)

9. 从 Microsoft Defender for Endpoint 向导复制并粘贴检测测试。

   ![Image of_the 运行检测测试步骤，在此步骤中，应单击 "复制" 以复制应在命令提示符处粘贴的检测测试脚本](../../media/mtp-eval-65.png)

10. 将 PowerShell 脚本复制到提升的命令提示符，然后运行它。 

    ![图像 of_command 提示，应将 PowerShell 脚本复制到提升的命令提示符并运行它](../../media/mtp-eval-66.png)

11. 从向导中选择 " **开始使用 Microsoft Defender For Endpoint** "。

    ![图像 of_the 来自向导的确认提示，应单击该向导中的 "开始使用 Microsoft Defender for Endpoint"](../../media/mtp-eval-67.png)
 
12. 访问 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。 转到 " **设置** "，然后选择 " **高级功能**"。 

    ![应在其中选择 "高级功能" of_Microsoft "Defender 安全中心设置" 菜单的图像](../../media/mtp-eval-68.png)

13. 启用与 **Microsoft Defender For Identity** 的集成。  

    ![Image of_Microsoft Defender Security Center 高级功能，需要打开的 Microsoft Defender 标识选项切换](../../media/mtp-eval-69.png)

14. 启用与 **Office 365 威胁智能** 的集成。

    ![Image of_Microsoft Defender Security Center 高级功能，需要打开的 Office 365 威胁智能选项切换](../../media/mtp-eval-70.png)

15. 启用与 **Microsoft 云应用安全性** 的集成。

    ![Image of_Microsoft Defender Security Center 高级功能，需要打开的 Microsoft 云应用安全选项切换](../../media/mtp-eval-71.png)

16. 向下滚动，然后单击 " **保存首选项** " 以确认新的集成。

    ![您需要单击的图像 of_Save 首选项按钮](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>启动 Microsoft 365 Defender 服务

>[!NOTE]
>从2020年6月1日开始，Microsoft 自动为所有符合条件的租户启用 Microsoft 365 Defender 功能。 有关详细信息，请参阅本 [Microsoft 技术社区文章关于许可证资格](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。 


转到 [Microsoft 365 安全中心](https://security.microsoft.com/homepage)。 导航到 " **设置** "，然后选择 " **Microsoft 365 Defender**"。

![来自 Microsoft 365 安全中心设置页面的图像 of_Microsoft 365 Defender 选项屏幕截图 ](../../media/mtp-eval-72b.png) <br>

有关更全面的指导，请参阅 [打开 Microsoft 365 Defender](mtp-enable.md)。 

恭喜！ 你刚刚创建了 Microsoft 365 Defender 试用版实验室或试点环境！ 现在，你可以熟悉 Microsoft 365 Defender 用户界面！ 查看您可以从以下 Microsoft 365 Defender 互动版指南中了解的内容，并了解如何使用每个仪表板执行日常安全操作任务。


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

接下来，您可以模拟攻击，并查看跨产品功能如何检测、创建警报以及自动响应对终结点的 fileless 攻击。

## <a name="next-step"></a>后续步骤
|[攻击模拟阶段](mtp-pilot-simulate.md) | 为您的 Microsoft 365 Defender 试点环境运行攻击模拟。
|:-------|:-----|
