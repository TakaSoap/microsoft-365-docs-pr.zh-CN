---
title: 准备你的 Microsoft 威胁防护试用实验室环境
description: 在设置 Microsoft 威胁防护试用实验室或试点环境时，准备利益干系人签署、时间线、环境注意事项和采用顺序
keywords: MTP 试用准备、MTP 试点准备、准备运行 MTP 试点项目、运行试点 MTP 项目、部署、准备、利益干系人、日程表、环境、终结点、服务器、管理、采用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a684f49ab8c70a19a17ff43195197677bccbf95b
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816765"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>准备你的 Microsoft 威胁防护试用实验室或试点环境

**适用于：**
- Microsoft 威胁防护

创建 Microsoft 威胁防护试用实验室或试点环境并对其进行部署的过程分为三个阶段：

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="准备你的 Microsoft 威胁防护试用实验室或试点环境" />
      <br/>第1阶段：准备 </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="设置你的 Microsoft 威胁防护试用实验室或试点环境" />
      <br/>阶段2：安装程序 </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="配置每个 Microsoft 威胁防护支柱并将终结点集成在一起" />
      <br/>第3阶段： Configure & 板载</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

你当前正在准备阶段。


准备工作是任何成功部署的关键。 本部分将指导您在准备为 Microsoft 威胁防护部署创建试用实验室或试点环境时需要考虑的事项。

## <a name="prerequisites"></a>先决条件
了解有关设置和使用 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置。 请参阅 [Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide)、 [microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)、 [OFFICE 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)、 [Azure atp](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)、 [microsoft 云应用安全性](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)的最低要求。

## <a name="stakeholders-and-sign-off"></a>利益干系人和签署
以下部分用于确定项目中涉及的所有利益干系人以及可能需要签署、查看或随时通知的所有利益干系人，无论是评估还是运行试点。

>[!NOTE]
>并非所有组织都可能具有此类角色的安全组织成熟度。 在这种情况下，请与您的领导团队联系，了解审阅和批准责任。

根据您的组织的需要，向下表中添加利益干系人。

-   SO = 此项目上的注销

-   R = 查看此项目并提供输入

-   I = 此项目的通知

| 名称                 | Role                                                                                                                                                                                                          | 操作 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 输入名称和电子邮件 | **首席信息安全专员 (CISO) ** *作为新技术部署的组织中充当承办人的执行者。*                                                  | 就     |
| 输入名称和电子邮件 | "**网络防护运营中心" (CDOC) ** *来自 CDOC 团队的代表，负责定义如何将此更改与客户安全操作团队中的过程相一致。*       | 就     |
| 输入名称和电子邮件 | **安全***团队中的一名代表，负责定义如何将此更改与组织中的核心安全体系结构保持一致。*                         | R      |
| 输入名称和电子邮件 | **工作场所架构师***由 IT 团队负责定义此更改与组织中的核心工作区体系结构的对齐方式。*                             | R      |
| 输入名称和电子邮件 | **安全分析员***来自 CDOC 团队的代表，可以通过安全操作的角度提供对此更改的检测功能、用户体验和总体有用性的输入。* | I      |

## <a name="prepare-your-azure-active-directory"></a>准备 Azure Active Directory
如果已启用本地 Active directory 和 Azure Active Directory 之间的同步，请跳过此步骤。 查看 Azure Active Directory 中现有的最佳实践文档。 以下步骤经过优化，可评估或运行试点 Microsoft 威胁防护项目。

1. 请转到 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 门户 > **azure AD Connect**。 
![Azure Active Directory 门户页面的图像](../../media/mtp-eval-1.png) <br> 

2. 单击 **"** 从 **Microsoft Azure Active Directory 连接** "，并将其传输到域控制器。
![Azure Active Directoru Connect 下载页面的图像](../../media/mtp-eval-2.png) <br>

3. 在域控制器上，按照 Azure Active Directory 连接向导。 阅读许可条款和隐私声明，如果同意，请选中此复选框。 单击"继续"。
![Azure AD Connect "欢迎" 页面的图像](../../media/mtp-eval-3.png) <br>

4. 导航到 " **Express 设置**"。
![快速设置页面的图像](../../media/mtp-eval-4.png) <br>

5. 输入全局管理员凭据。 单击“**下一步**”。
![应在其中输入全局管理员凭据的 "连接到 Azure AD" 页面的图像](../../media/mtp-eval-5.png) <br>

6. 输入你的 Active Directory 域服务企业管理员凭据。 单击“**下一步**”。
![应在其中输入凭据的 "连接到 AD DS" 页的图像](../../media/mtp-eval-6.png) <br>

7. 单击 " **安装** " 以确认配置。
![配置确认页的图像](../../media/mtp-eval-7.png) <br>

8. 恭喜，你已成功配置 Azure Active Directory Connect。
![成功配置的 Azure Active Directory Connect 页面的图像](../../media/mtp-eval-8.png) <br>

您现在可以 [向 Active Directory 中添加用户和组](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) ，并 [配置 SAM-R 策略](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。  


## <a name="configuration-order"></a>配置顺序
下表指出 Microsoft 建议为试用版实验室或试点环境部署配置 Microsoft 威胁防护组件的顺序。

| 组件                               | 说明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 配置顺序排名 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 高级威胁防护| Office 365 ATP 将保护您的组织免受电子邮件、链接 (Url) 和协作工具带来的恶意威胁的侵扰。 <br> [了解更多信息。](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1                    |
|Azure 高级威胁防护|Azure ATP 使用 Active Directory 信号识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕活动。 <br> [了解详细信息](https://docs.microsoft.com/azure-advanced-threat-protection/)。| 2  |
|Microsoft Cloud App Security| Microsoft 云应用安全是一个云访问安全代理 (CASB) ，可在多个云上运行。 它提供丰富的可见性、控制数据旅行和完善的分析，以跨所有云服务识别和防御威胁。 <br> [了解详细信息](https://docs.microsoft.com/cloud-app-security/)。                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Microsoft Defender 高级威胁防护 | Microsoft Defender ATP 终结点检测和响应功能提供了准实时且可操作的高级攻击检测。 安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。 <br> [了解更多信息。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>后续步骤
![阶段2：安装程序](../../media/setup.png) <br>[阶段2：安装程序](setup-mtpeval.md)<br> 设置你的 Microsoft 威胁防护试用实验室或试点环境

