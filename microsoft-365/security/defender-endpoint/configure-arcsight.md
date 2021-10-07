---
title: 配置 Micro Focus ArcSight 以拉取 Microsoft Defender 进行终结点检测
description: 配置 Micro Focus ArcSight 以接收和拉取来自Microsoft Defender 安全中心
keywords: 配置 Micro Focus ArcSight， 安全信息和事件管理工具， arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ce8c28a76ffc3348d5500f25820f4632ee862782
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211276"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>配置 Micro Focus ArcSight 以拉取 Defender 进行终结点检测

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configurearcsight-abovefoldlink)。

你需要安装和配置一些文件和工具以使用 Micro Focus ArcSight，以便它可以拉取 Defender 进行终结点检测。

> [!NOTE]
>
> - [Defender for Endpoint Alert](alerts.md) 由一个或多个检测组成
> - [Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。

## <a name="before-you-begin"></a>准备工作

配置微型焦点 ArcSight 连接器工具需要多个配置文件，以拉取和分析来自 AAD Azure Active Directory (应用程序的) 检测。

本部分将指导你获取正确设置和使用所需配置文件的必要信息。

- 确保你已从"开始"菜单启用 SIEM **设置** 功能。 有关详细信息，请参阅在 Defender [for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)。

- 准备好启用 SIEM 集成功能时保存的文件。 你需要获取以下值：
  - OAuth 2.0 令牌刷新 URL
  - OAuth 2.0 客户端 ID
  - OAuth 2.0 客户端密码

- 准备好以下配置文件：
- 
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    当你选择 Micro Focus ArcSight 作为你在组织.zip SIEM 类型时，你将保存一个包含这两个文件的配置文件。

- 请确保生成以下令牌并准备好：
  - 访问令牌
  - 刷新令牌

  你可以从门户的 **SIEM 集成** 设置部分生成这些令牌。

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>安装和配置 Micro Focus ArcSight FlexConnector

以下步骤假定你已完成开始之前的所有 [必需步骤](#before-you-begin)。

1. 安装最新的 32 位 Windows FlexConnector 安装程序。 可在 HPE 软件中心找到它。 该工具通常安装在以下默认位置 `C:\Program Files\ArcSightFlexConnectors\current\bin` ：。</br></br>您可以选择保存工具的位置，例如 C：folder_location \\ \current\bin，folder_location表示安装位置。 

2. 按照安装向导完成以下任务：
   - 简介
   - 选择"安装文件夹"
   - 选择"安装集"
   - 选择快捷方式文件夹
   - 安装前摘要
   - 正在安装...

   您可以保留其中每个任务的默认值，或修改选择以满足您的要求。

3. 打开文件资源管理器并找到启用 SIEM 集成功能时保存的两个配置文件。 将两个文件放在 FlexConnector 安装位置，例如：

   - WDATP-connector.jsonparser.properties：C：folder_location \\ \current\user\agent\flexagent\
   - WDATP-connector.properties：C：folder_location \\ \current\user\agent\flexagent\

   > [!NOTE]
   > 必须将配置文件放在此位置，其中 *folder_location表示安装* 该工具的位置。

4. 核心连接器的安装完成后，将打开"连接器设置"窗口。 在"连接器设置"窗口中，选择"**添加连接器"。**

5. 选择类型 **：ArcSight FlexConnector REST，** 然后单击下 **一步**。

6. 在参数详细信息表单中键入以下信息。 表单中的所有其他值都是可选的，可以留空。

   <br>

   ****

   |字段|值|
   |---|---|
   |配置文件|键入客户端属性文件的名称。 该名称必须与下载的 .zip中提供的文件匹配。 <p> 例如，如果"flexagent"目录中的配置文件名为"WDATP-Connector.jsonparser.properties"，则必须键入"WDATP-Connector"作为客户端属性文件的名称。|
   |事件 URL|根据您的数据中心位置，选择欧盟、美国或英国 URL： <ul><li>**对于欧盟**：  `https://wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li><li>**对于美国**： `https://wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li><li>**对于英国**： `https://wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li></ul>|
   |身份验证类型|OAuth 2|
   |OAuth 2 客户端属性文件|浏览到 *wdatp-connector.properties 文件* 的位置。 该名称必须与下载的 .zip中提供的文件匹配。|
   |刷新令牌|可以通过两种方式获取刷新令牌：从 **SIEM** 设置页生成刷新令牌，或者使用 restutil 工具。 <p> 有关从首选项设置生成刷新令牌详细信息 **，** 请参阅在 Defender for Endpoint 中启用 [SIEM 集成](enable-siem-integration.md)。 <p> **使用 restutil 工具获取刷新令牌**： <ol><li>打开命令提示符。 导航到 C： \\ *文件夹 \_ 位置*\current\bin，其中 *文件夹 \_* 位置表示安装该工具的位置。</li><li>类型： `arcsight restutil token -config` 从 bin 目录。 例如 **：arcsight restutil boxtoken -proxy proxy.location.hp.com:8080**。 将打开 Web 浏览器窗口。</li><li>键入凭据，然后单击密码字段，让页面重定向。 在登录提示中，输入凭据。</li><li>刷新令牌显示在命令提示符中。</li><li>将其复制并粘贴到 **"刷新令牌"** 字段中。|
   |

7. 浏览器窗口由连接器打开。 使用应用程序凭据登录。 登录后，将要求您授予 OAuth2 客户端的权限。 您必须向 OAuth 2 客户端授予权限，以便连接器配置可以进行身份验证。

   如果 `redirect_uri` 为 https URL，将重定向到本地主机上的 URL。 你将看到一个页面，请求你信任在本地主机上运行的连接器提供的证书。 如果证书是 https，则需要redirect_uri证书。

   但是，如果为证书指定 http URL redirect_uri，则无需在信任证书时提供同意。

8. 返回到 Micro Focus ArcSight 连接器设置窗口，继续进行连接器设置。

9. 选择 **ArcSight 管理器 (加密)** 作为目标，然后单击下一 **步**。

10. 在管理器主机名中键入目标 IP/主机名，在参数表单中键入凭据。  表单中的所有其他值都应保留为默认值。 单击“下一步”。

11. 在连接器详细信息表单中键入连接器的名称。 表单中的所有其他值都是可选的，可以留空。 单击“下一步”。

12. 将显示 ESM 管理器导入证书窗口。 选择 **"将证书从目标导入连接器"，然后单击**"下一 **步"。** 将显示 **"添加连接器摘要** "窗口，并导入证书。

13. 验证"添加 **连接器摘要"** 窗口中的详细信息是否正确，然后单击"下一步 **"。**

14. 选择 **"安装为服务"，** 然后单击"下一 **步"。**

15. 在"服务内部名称" **字段中键入** 名称。 窗体中的所有其他值都可以使用默认值保留或留空。 单击“下一步”。

16. 键入服务参数，然后单击下一 **步**。 将显示一个 **包含"安装服务摘要"** 的窗口。 单击“下一步”。

17. 通过选择"退出"和"下一 **步"完成****安装**。

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>安装和配置 Micro Focus ArcSight 控制台

1. 按照安装向导完成以下任务：
   - 简介
   - 许可协议
   - 特别通知
   - 选择 ArcSight 安装目录
   - 选择快捷方式文件夹
   - 安装前摘要

2. 单击“**安装**”。 安装完成后，将打开 ArcSight 控制台配置向导。

3. 在"管理器主机名"**中键入 localhost，在**"管理器端口"中键入 8443，**然后单击**"下一步 **"。**

4. 选择 **"使用直接连接"，** 然后单击"下一 **步"。**

5. 选择 **"基于密码的身份验证"，** 然后单击"下一 **步"。**

6. 选择 **"这是单个用户安装"。 (推荐**) "，然后单击"下一步 **"。**

7. 单击 **"完成** "退出安装程序。

8. 登录到 Micro Focus ArcSight 控制台。

9. 导航到 **"活动通道设置** \> **新建条件** \> **设备** \> **设备产品"。**

10. 设置 **设备产品 = Microsoft Defender ATP**。 验证事件是否流向工具后，请再次停止此过程，然后转到 Windows Services 并启动 ArcSight FlexConnector REST。

现在可以在 Micro Focus ArcSight 控制台中运行查询。

Defender for Endpoint 检测将显示为离散事件，"Microsoft"作为供应商，"Windows Defender ATP"作为设备名称。

## <a name="troubleshooting-micro-focus-arcsight-connection"></a>微焦点 ArcSight 连接疑难解答

**问题：** 未能刷新令牌。 你可以找到位于 C： \\ *folder_location*\current\logs 中的日志，folder_location表示安装该工具的位置。 打开 _agent.log_ 并查找 `ERROR/FATAL/WARN` 。

**症状：** 收到以下错误消息：

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**解决方案：**

1. 通过单击"连接器"窗口上的 Ctrl + C 停止此过程。 当 **系统询问"** 终止批处理作业 Y/N？"时，单击"Y"。

2. 导航到存储 WDATP-connector.properties 文件的文件夹，然后对其进行编辑以添加以下值：

   `reauthenticate=true`.

3. 通过运行以下命令重新启动连接器：

   `arcsight.bat connectors`.

   将显示浏览器窗口。 允许它运行，它应消失，连接器现在应该正在运行。

> [!NOTE]
> 通过再次停止进程来验证连接器是否正在运行。 然后再次启动连接器，不应显示浏览器窗口。

## <a name="related-topics"></a>相关主题

- [在 Defender for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)
- [将检测拉取到 SIEM 工具](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [使用 REST API 拉取 Defender for Endpoint 检测](pull-alerts-using-rest-api.md)
- [SIEM 工具集成问题疑难解答](troubleshoot-siem.md)
