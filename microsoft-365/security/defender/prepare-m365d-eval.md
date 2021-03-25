---
title: 准备 Microsoft 365 Defender 试用实验室环境
description: 设置 Microsoft 365 Defender 试用实验室或试验环境时，准备利益干系人注销、日程表、环境注意事项和采用顺序
keywords: MTP 试用准备， MTP 试点准备， 准备运行 MTP 试点项目， 运行试点 MTP 项目， 部署， 准备， 利益干系人， 时间线， 环境， 终结点， 服务器， 管理， 采用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: dada110faca71c9e8fcf384eb5bb0a78faefaad9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199133"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>准备 Microsoft 365 Defender 试用实验室或试验环境

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

创建 Microsoft 365 Defender 试用实验室或试验环境并部署它的过程分三个阶段：

|![阶段 1：准备](../../media/phase-diagrams/prepare.png)<br/>阶段 1：准备 |[![阶段 2：设置](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[阶段 2：设置](setup-m365deval.md) |[![阶段 3：载入](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[阶段 3：载入](config-m365d-eval.md) | [![返回到试点](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[返回到试点手册](m365d-pilot.md) |
|--|--|--|--|
|*你在这里！* | || |

你当前处于准备阶段。


准备工作是任何成功部署的关键。 本部分将指导你完成准备为 Microsoft 365 Defender 部署创建试用实验室或试验环境时需要考虑的内容。

## <a name="prerequisites"></a>先决条件
了解预配和使用 Microsoft 365 Defender 的许可、硬件和软件要求以及其他配置设置。 请参阅 Microsoft [365 Defender、Microsoft](https://docs.microsoft.com/microsoft-365/security/defender/prerequisites) [Defender for Endpoint、Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [Defender for Office 365、Microsoft Defender](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)for [Identity、Microsoft](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites) [Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)的最低要求。

## <a name="stakeholders-and-sign-off"></a>利益干系人与签署
确定项目所涉及的所有利益干系人，以及可能需要签署、审阅或随时了解情况（无论是评估还是运行试验项目）的利益干系人。

>[!NOTE]
>并非所有组织都有拥有此类角色的安全组织。 在这种情况下，请咨询领导团队，以承担审阅和审批责任。

根据组织需要，将利益干系人添加到下表。

-   SO = 此项目的注销

-   R = 查看此项目并提供输入

-   I = 已通知此项目

| 名称                 | Role                                                                                                                                                                                                          | 操作 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 输入名称和电子邮件 | **CISO (** 首席) 一名执行代表，他作为新技术部署 *的组织内部发起人。*                                                  | SO     |
| 输入名称和电子邮件 | **网络防御运营中心 (CDOC)** CDOC 团队的代表，负责定义此更改如何与客户安全运营团队中的流程 *保持一致。*       | SO     |
| 输入名称和电子邮件 | **安全** 架构师 来自安全团队的代表，负责定义此更改如何与组织中 *的核心安全体系结构保持一致。*                         | R      |
| 输入名称和电子邮件 | **工作区** 架构师 来自 IT 团队的代表，负责定义此变更如何与组织中的核心 *工作场所体系结构保持一致。*                             | R      |
| 输入名称和电子邮件 | **安全分析师** CDOC 团队的代表，可以从安全操作角度提供有关此更改的检测功能、用户体验和 *整体有用性的反馈。* | I      |

## <a name="prepare-your-azure-active-directory"></a>准备 Azure Active Directory
如果已在本地 Active Directory 和 Azure Active Directory 之间启用同步，请跳过此步骤。 查看 Azure Active Directory 中的现有最佳做法文档。 以下步骤经过优化，可评估或运行 Microsoft 365 Defender 试点项目。

1. 转到 [Azure AD Connect](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > Azure Active **Directory 门户**。 
![Azure Active Directory 门户页面的图像](../../media/mtp-eval-1.png) <br> 

2. 单击 **"从** **Microsoft Azure Active Directory Connect** 下载"，将其传输至域控制器。
![Azure Active Directoru Connect 下载页的图像](../../media/mtp-eval-2.png) <br>

3. 在域控制器上，按照 Azure Active Directory Connect 向导操作。 阅读许可条款和隐私声明，并选中复选框（如果你同意）。 单击"继续"。
![Azure AD Connect 欢迎页面的图像](../../media/mtp-eval-3.png) <br>

4. 导航到 **快速设置**。
![快速设置页面的图像](../../media/mtp-eval-4.png) <br>

5. 输入全局管理员凭据。 单击"下一步"。
![连接到 Azure AD 页面的图像，应在其中输入全局管理员凭据](../../media/mtp-eval-5.png) <br>

6. 输入 Active Directory 域服务企业管理员凭据。 单击"下一步"。
![连接到 AD DS 页面的图像，应在其中输入凭据](../../media/mtp-eval-6.png) <br>

7. 单击 **"安装** "以确认配置。
![配置确认页的图像](../../media/mtp-eval-7.png) <br>

8. 恭喜！已成功配置 Azure Active Directory Connect。
![成功配置的 Azure Active Directory Connect 页面的图像](../../media/mtp-eval-8.png) <br>

现在可以将 [用户和组添加到 Active Directory](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) 并 [配置 SAM-R 策略](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。  


## <a name="configuration-order"></a>配置顺序
下表指示 Microsoft 建议为试用实验室或试验环境部署配置 Microsoft 365 Defender 组件的顺序。

| 组件                               | 说明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 配置顺序排名 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender for Office 365|Microsoft Defender for Office 365 可保护你的组织免受电子邮件、链接 (URL) 和协作工具带来的恶意威胁。 <br> [了解更多信息。](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity 使用 Active Directory 信号来识别、检测和调查针对你的组织的高级威胁、泄露的身份和恶意预览体验成员操作。 <br> [了解详细信息](/azure-advanced-threat-protection/)。| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security 是 CASB (在) 云中操作的云访问安全代理。 它提供了丰富的可见性、控制数据传输和复杂的分析，以识别和防御所有云服务中的网络威胁。 <br> [了解详细信息](/cloud-app-security/)。                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender for Endpoint | 用于终结点检测和响应的 Microsoft Defender 提供了几乎实时和可操作的高级攻击检测。 安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。 <br> [了解更多信息。](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>后续步骤
|![阶段 2：设置](../../media/setup.png) <br>[阶段 2：设置](setup-m365deval.md) | 设置 Microsoft 365 Defender 试用实验室或试验环境
|:-------|:-----|
