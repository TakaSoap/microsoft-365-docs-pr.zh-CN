---
title: 将 Microsoft 365 for business 用户升级到最新的 Office 客户端
f1.keywords:
- NOCSH
ms.author: kwekuako
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 了解如何将用户升级到最新的 Office 客户端。
ms.openlocfilehash: 2140e246882d9d9b30481bc20b78142708408f88
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011264"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>将 Microsoft 365 for business 用户升级到最新的 Office 客户端

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 到达支持终止

Office 2010 将在2020年10月13日到达其支持的结束。 当 Office 2010 达到其支持的结束时间时，Microsoft 将不再提供以下内容：

- 问题的技术支持

- 针对发现的问题的 Bug 修补程序

- 发现的漏洞的安全修补程序

有关详细信息，请参阅[Office 2010 终止支持路线图](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。

 **这是正确的主题吗？**
  
 如果您是负责组织中的 Microsoft 365 for business 订阅的管理员，那么就是正确的位置。 管理员通常负责管理用户、重置密码、管理 Office 安装和添加或删除许可证等任务。

 如果你不是管理员，并且拥有[Microsoft 365 系列](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans)产品，请参阅[如何升级 office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx)以获取有关升级旧版 office 的信息。

## <a name="get-ready-to-upgrade"></a>准备升级

作为管理员，您可以控制组织中的 Office 用户可以安装的版本。 强烈建议您在组织中运行较早版本的 Office 的用户（如 Office 2010、Office 2013 或 Office 2016 升级到最新版本，以充分利用其安全性和生产率改进。

## <a name="upgrade-steps"></a>升级步骤

下面的步骤将指导您完成将用户升级到最新 Office 桌面客户端的过程。 我们建议您在开始升级过程之前先阅读这些步骤。
  
## <a name="step-1---check-system-requirements"></a>第1步-检查系统要求

[检查 office 的系统要求](https://products.office.com/office-system-requirements)，以确保您的设备与 office 的最新版本兼容。 例如，Office 的较新版本不能安装在运行 Windows XP 或 Windows Vista 的计算机上。
  
> [!TIP]
> 如果你的组织中有用户在其电脑或笔记本电脑上运行较旧版本的 Windows，我们建议升级到 Windows 10。 Windows 7 已到达支持终止。 有关详细信息，请参阅[Windows 7 2020 年1月结束](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)的阅读支持。

请查看[Windows 10 系统要求](https://www.microsoft.com/windows/windows-10-specifications)，了解是否可以升级其操作系统。

### <a name="check-application-compatibility"></a>检查应用程序兼容性

为了确保成功升级，我们建议您确定 Office 应用程序，包括 VBA 脚本、宏、第三方加载项和复杂文档和电子表格，并评估其与 Office 最新版本的兼容性。
  
例如，如果要将第三方加载项与当前 Office 安装一起使用，请与制造商联系，以确保它们与 Office 的最新版本兼容。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>步骤 2-检查现有订阅计划

一些 Microsoft 365 计划不包括 Office 的完整桌面版本，如果您的计划不包括 Office，升级步骤将有所不同。
  
不确定您拥有哪种订阅计划？ 查看[我拥有什么 Microsoft 365 for business 订阅？](../admin-overview/what-subscription-do-i-have.md)
  
如果现有计划包含 Office，请转到[步骤 3-卸载 office](#step-3---uninstall-office)。
  
如果现有计划不包含 Office，请从以下选项中进行选择：
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>不包括 Office 的计划的升级选项

 **选项1：切换 Office 订阅**

切换到包含 Office 的订阅。 请参阅[切换到其他 Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**选项2：购买 Office 的单个、一次性购买或通过批量许可证购买 Office**

 - 购买 Office 的单个一次性购买。 请参阅[Office &amp;家庭商业](https://products.office.com/home-and-business)[版或 office Professional](https://products.office.com/professional)

     OR

 - 通过批量许可证购买 Office 的多个副本。 请参阅[可通过批量许可进行比较的套件](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)。

## <a name="step-3---uninstall-office"></a>步骤 3-卸载 Office

在安装 Office 的最新版本之前，我们建议您卸载所有较早版本的 Office。 但是，如果你改变了你对 Office 升级的想法，请注意以下在卸载 Office 后无法重新安装 Office 的情况。
  
如果你有第三方加载项，建议与制造商联系以查看是否有更新可用于 Office 的最新版本。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>选择要卸载的 Office 版本

- [从电脑](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [从 Mac](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>卸载后尝试重新安装早期版本的 Office 的已知问题

 **通过批量许可证的 Office**如果您不再有权访问这些批量许可证版本的 Office，将无法重新安装。

 **Office 预安装在您的计算机上**如果您不再拥有光盘或产品密钥（如果 Office 随附一台），则无法重新安装它。

 **不支持的订阅**如果您的 Office 副本是通过停止订阅（如 Office 365 小型企业高级版或 Office 365 中型企业版）获取的，则您将无法安装较旧版本的 Office，除非您拥有订阅附带的产品密钥。

如果您希望使用最新版本的 Office 并行安装早期版本的 Office，您可以查看在[同一台电脑上安装和使用 office 的不同版本](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx)的版本列表。 并行安装对于您来说可能是最合适的选择，例如，您已安装了与较旧版本的 Office 结合使用的第三方加载项，并且您尚不确定它们是否与最新版本兼容。

## <a name="step-4---assign-office-licenses-to-users"></a>步骤 4-将 Office 许可证分配给用户

如果尚未执行此操作，请将许可证分配给组织中需要安装 Office 的任何用户，请参阅[在 Microsoft 365 for business 中向用户分配许可证](../manage/assign-licenses-to-users.md)。
  
## <a name="step-5---install-office"></a>第5步-安装 Office

确认要升级的用户都拥有许可证后，最后一步是让他们安装 Office，请参阅[在电脑或 Mac 上下载并安装或重新安装 office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)。
  
> [!TIP]
> 如果您不希望用户安装 Office 本身，请参阅[在 Office 365 中管理软件下载设置](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)。 您可以使用[Office 部署工具](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool)将 office 软件下载到本地网络，然后使用您通常使用的软件部署方法部署 office。
