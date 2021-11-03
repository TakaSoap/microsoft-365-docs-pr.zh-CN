---
title: 解决与 Microsoft Defender for Endpoint 的安全管理相关的载入问题
description: 解决在使用 Microsoft Defender for Endpoint 的安全管理载入设备期间可能出现的问题。
keywords: 载入疑难解答， 载入问题， 事件查看器， 数据收集和预览版本， 传感器数据和诊断
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 817eb57df116de18e8add5d18eac0ea32f08da7f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60676961"
---
# <a name="troubleshoot-onboarding-issues-related-to-security-management-for-microsoft-defender-for-endpoint"></a>解决与 Microsoft Defender for Endpoint 的安全管理相关的载入问题 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [在设备上使用 Microsoft Defender for Endpoint 管理Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender for Endpoint 的安全管理是一项功能，适用于不由 Microsoft Endpoint Manager（Microsoft Intune 或 Microsoft Endpoint Configuration Manager）管理的设备，用于接收 Microsoft Defender 的安全配置直接从Endpoint Manager。
有关 Microsoft Defender for Endpoint 的安全管理详细信息，请参阅使用安全管理管理 Microsoft [Defender for Endpoint Microsoft Endpoint Manager。](/mem/intune/protect/mde-security-integration)

有关适用于终结点的 Microsoft Defender 的安全管理载入说明，请参阅 [Microsoft Defender for Endpoint Security Configuration Management](security-config-management.md)

此端到端载入设计为无接触，不需要用户输入。 但是，如果你在载入期间遇到问题，可以在 Microsoft Defender for Endpoint 平台中查看错误并排查错误。


>[!NOTE]
> 如果你在新设备的载入流方面遇到问题，请查看 Microsoft Defender for [Endpoint](/mem/intune/protect/mde-security-integration#prerequisites) 先决条件并确保遵循载入说明。


有关客户端分析器详细信息，请参阅使用 [Microsoft Defender for Endpoint Client Analyzer 解决传感器运行状况问题](/microsoft-365/security/defender-endpoint/overview-client-analyzer)。

## <a name="registering-domain-joined-computers-with-azure-active-directory"></a>向用户注册加入域Azure Active Directory  
若要成功注册设备Azure Active Directory，你需要确保： 

- 计算机可以使用域控制器进行身份验证 
- 计算机可以访问组织网络内部的以下 Microsoft 资源：
  - https://enterpriseregistration.windows.net
  - https://login.microsoftonline.com
  - https://device.login.microsoftonline.com
- Azure AD连接配置为同步计算机对象。 默认情况下，计算机 US Azure AD连接同步作用域。 如果计算机对象属于特定组织单位 (组织单位) ，请配置要同步到Azure AD 连接。 若要了解有关如何使用计算机对象同步计算机对象Azure AD 连接，请参阅基于组织 [单位的筛选](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering#organizational-unitbased-filtering)。

>[!IMPORTANT]
>Azure AD连接不会同步Windows Server 2012 R2 计算机对象。 如果你需要在 Microsoft Defender for Endpoint Azure AD安全管理中注册它们，则需要自定义 Azure AD 连接同步规则，以在同步作用域中包括这些计算机对象。 请参阅[有关在计算机加入规则中应用计算机加入Azure Active Directory 连接。]()

>[!NOTE]
>要成功完成载入流，并且独立于设备的操作系统，Azure Active Directory设备的初始状态可能会更改：<br>
>
>|      启动设备状态     |      新设备状态     |
>|---|---|
>|     已使用 AADJ 或 HAADJ    |     保持为    |
>|     未加入 AADJ 或混合 Azure Active Directory (HAADJ) + 已加入域    |     设备为 HAADJ'd    |
>|     未加入 AADJ 或 HAADJ + 未加入域    |     设备为 AADJ'd    |
>
>其中 AADJ Azure Active Directory Joined，HAADJ 表示 Hybrid Azure Active Directory Joined。


## <a name="troubleshoot-errors-from-the-microsoft-defender-for-endpoint-portal"></a>排查 Microsoft Defender 终结点门户中的错误


通过 Microsoft Defender for Endpoint 门户，安全管理员可以对适用于终结点载入的 Microsoft Defender 安全管理进行故障排除。 


在 **终结点>设备清单** 中，"托管者"列已添加到按管理通道筛选 (例如 MEM) 。


:::image type="content" alt-text="设备清单页的图像" source="./images/device-inventory-mde-error.png":::

To see a list of all devices that have failed the Security Management for Microsoft Defender for Endpoint onboarding process， filter the table by **MDE-Error**.

在列表中，选择特定设备以查看侧面板中的疑难解答详细信息、指向错误的根本原因以及相应的文档。


:::image type="content" alt-text="已筛选设备清单页面的图像" source="./images/secconfig-mde-error.png":::


## <a name="run-microsoft-defender-for-endpoint-client-analyzer-on-windows"></a>在终结点客户端分析器上运行 Microsoft Defender Windows 

请考虑在无法完成 Microsoft Defender 终结点载入流程安全管理的终结点上运行客户端分析器。 有关客户端分析器详细信息，请参阅使用 [Microsoft Defender for Endpoint Client Analyzer 解决传感器运行状况问题](overview-client-analyzer.md)。

MDE 客户端分析器 (输出文件Results.htm) 可提供关键疑难解答信息：

- 在"常规设备详细信息"部分，验证设备操作系统是否位于适用于终结点的 Microsoft Defender 载入流 **的安全管理范围内**
- 验证设备已成功注册到Azure Active Directory **配置管理详细信息中**


    ![客户端分析器结果的图像](images/client-analyzer-results.png)


在 **报告的"详细** 结果"部分，客户端分析器还提供了可操作指导。

>[!TIP]
>确保报告的详细结果部分不包含任何"错误"，并确保查看所有"警告"消息。

例如，作为安全管理载入流程的一部分，Microsoft Defender for Endpoint Tenant 中的 Azure Active Directory 租户 ID 需要与报告的设备配置管理详细信息部分中出现的 SCP 租户ID 相匹配。 如果相关，报告输出将建议执行此验证。

![详细结果的图像](images/detailed-results.png)


## <a name="general-troubleshooting"></a>一般疑难解答 

如果你无法识别 AAD 或 MEM 中已载入的设备，并且注册期间未收到错误，检查注册表项可以提供其他 `Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SenseCM\\EnrollmentStatus` 疑难解答信息。  

:::image type="content" alt-text="注册状态的图像。" source="images/enrollment-status.png":::

下表列出了为了处理错误而尝试/检查的错误和说明。 请注意，错误列表不完整，并且基于客户过去遇到的典型/常见错误： 



| 错误代码  |管理员操作                                                                                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``10``          |错误指示操作系统无法执行混合联接。 使用[混合Azure Active Directory设备疑](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current)难解答作为解决操作系统级别混合联接故障的指南。                                                            |
| ``13-14``       |查看[通过 Microsoft Defender Microsoft Endpoint Manager](/microsoft-365/security/defender-endpoint/security-config-management#onboard-devices)终结点载入 Windows 设备的先决条件，以确保终结点完成且混合 Azure Active Directory 加入可用。                   |
| ``15``          |确保 MDE AAD租户的租户 ID 与域的 SCP 条目中的租户 ID 相匹配。                                                                                                                                                                                                                     |
| ``16``          |查看[Azure Active Directory文档](/azure/active-directory/devices/hybrid-azuread-join-manual#configure-a-service-connection-point)。 与组织的身份团队合作，以部署 HAADJ 所需的配置方法。                                                                     |
| ``17``          |查看 Active Directory 环境的设备注册配置，并确定它使用的是 Enterprise DRS 还是 Azure DRS。                                                                                                                                                                                 |
| ``18``          |查看Azure AD 连接配置"，并确保配置为管理的设备在同步范围内。                                                                                                                                                                                              |
| ``25``          |查看网络拓扑并确保域控制器可用于完成混合加入请求。                                                                                                                                                                                                                       |
| ``26-32``       |查看完成联合加入所需声明的文档。 手动验证你的环境的终结点是否可用。                                                                                                                                                                                |
| ``36``          |查看网络拓扑并确保 LDAP API 可用于完成混合加入请求。                                                                                                                                                                                                                                  |
| ``37``          |对于加入域的计算机，请验证计算机是否位于域中同步Azure AD 连接。                                                                                                                                                                                                                    |
| ``38``          |工作站一侧的 DNS 设置无效：Active directory 要求您使用域 DNS，以正常 (，而不是路由器的地址) 。                                                                                                                                                                                |
| ``40``          |确保在发生错误的设备上正确设置/同步时钟。                                                                                                                          |
| ``41``          |重试以确认此错误是一致的。 如果重试没有帮助，请使用已加入Azure Active Directory[](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current)混合设备疑难解答作为解决操作系统级别混合联接故障的指南。                                                    |
| ``42``          |错误指示操作系统无法执行混合联接。 使用[混合Azure Active Directory设备疑](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current)难解答作为解决操作系统级别混合联接故障的指南。                                                            |


## <a name="azure-active-directory-runtime-troubleshooting"></a>Azure Active Directory运行时疑难解答 

### <a name="azure-active-directory-runtime"></a>Azure Active Directory运行时  

AADRT Azure Active Directory运行时 (的主要) 是收集调试跟踪。 Azure Active DirectoryWindows上的运行时使用 ID 为 **bd67e65c-9cc2-51d8-7399-0bb9899e75c1** 的 ETW 提供程序。 需要捕获 ETW 跟踪，同时重现故障 (例如，如果发生联接失败，则需要在一段时间内启用跟踪，包括调用 AADRT API 以执行) 。  

有关 AADRT 日志中的典型错误以及如何读取错误，请参阅下文： 

![事件属性的图像](images/event-properties.png)

根据消息信息，在大多数情况下，可以了解遇到的错误、哪些 Win32 API 返回了错误 (（如果适用) ）、使用了哪些 URL (（如果适用) ）以及遇到哪些 AAD 运行时 API 错误。 
  
 

## <a name="instructions-for-applying-computer-join-rule-in-aad-connect"></a>有关在计算机加入规则中应用计算机加入AAD 连接 

对于加入 R2 域Windows Server 2012计算机上的 Microsoft Defender for Endpoint 的安全管理，需要更新 Azure AD 连接 sync rule "In from AD-Computer Join"。 这可以通过克隆和修改规则实现，这将禁用原始"从 AD - 计算机加入"规则。 Azure AD 连接默认提供此体验，用于更改内置规则。

>[!NOTE]
>需要将这些更改应用于运行AAD 连接服务器。 如果已部署多个 AAD 连接，则必须将这些更改应用于所有实例。 

1. 从"开始"菜单打开同步规则编辑器应用程序。 在规则列表中，从 AD - 计算机加入 **中查找** 名为 In 的规则。 **记下此规则的"优先级"列中的值。** 

    ![同步规则编辑器的图像](images/57ea94e2913562abaf93749d306dd6cf.png)

2. 突出显示"**从 AD 加入 - 计算机加入"** 规则后，选择"编辑 **"。** 在"**编辑保留的规则确认"对话框中**，选择"**是"。** 

   ![编辑保留规则确认的图像](images/8854440d6180a5580efda24110551c68.png)

3. 将显示 **"编辑入站同步规则** "窗口。 更新规则说明，注意Windows Server 2012R2 将使用此规则进行同步。 除"优先级"值外，保留所有其他选项不变。 为"优先级"输入一个值，该值高于规则列表中的 (规则列表中的值) 。  

   ![确认图像](images/ee0f29162bc3f2fbe666c22f14614c45.png)

4.  选择 **"下一步** "三次。 这将导航到规则的"转换"部分。 不要对规则的"范围筛选器"和"加入规则"部分进行任何更改。 现在应显示"转换"部分。 

    ![入站同步规则的图像](images/296f2c2a705e41233631c3784373bc23.png)

5. 滚动到转换列表的底部。 查找 **cloudFiltered 属性的** 转换。 在"源"列的文本框中，选择"Control-A" (所有文本) 并将其删除。 文本框现在应该为空。 

6. 将新规则的内容粘贴到文本框中。 


    ```command
    IIF(
      IsNullOrEmpty([userCertificate])
      || 
      (
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        && 
        (Left([operatingSystemVersion],2) = "6.")
        &&
        (Left([operatingSystemVersion],3) <> "6.3")
      )
      ||
      (
        (Left([operatingSystemVersion],3) = "6.3") 
        &&
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        &&
        With(
          $validCerts,
          Where(
            $c, 
            [userCertificate], 
            IsCert($c) && CertNotAfter($c) > Now() && RegexIsMatch(CertSubject($c), "CN=[{]*" & StringFromGuid([objectGUID]) & "[}]*", "IgnoreCase")),
          Count($validCerts) = 0)
      ),
      True,
      NULL
    )

    ```

7.  选择 **"保存** "以保存新规则。

## <a name="related-topic"></a>相关主题
- [在设备上使用 Microsoft Defender for Endpoint 管理Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
