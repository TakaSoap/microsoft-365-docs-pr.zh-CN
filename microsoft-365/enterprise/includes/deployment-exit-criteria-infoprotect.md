<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必需：为你的组织定义安全和信息保护级别

已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。

至少，当前需要使用三种安全级别：

- 基线
- 敏感
- 高度管控

如果需要，可在[步骤 1](../infoprotect-define-sec-infoprotect-levels.md) 中进行设置以满足此要求。 

<a name="crit-infoprotect-step3"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>必需：已配置增强的 Microsoft 365 安全性

你已配置 [Office 365 增强安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)的以下设置：

- Microsoft 365 安全中心中的威胁管理策略
- 其他 Exchange Online 租户范围内设置
- SharePoint Online 管理中心中的租户范围内共享策略
- Azure Active Directory 中的设置 (Azure AD)

你还已[启用 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。

如果需要，请执行[第 3 步](../infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step2"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>可选：已在整个环境中配置分类

你已与法律和合规性团队合作，为组织数据管理和安全策略制定了适当的分类和标签方案。 

这些策略对应于以下项的配置和部署：

- 敏感数据类型
- 保留标签
- 敏感度标签
- Azure 信息保护标签

如果需要，请执行[第 2 步](../infoprotect-configure-classification.md)，这样做有助于满足此要求。 


<a name="crit-infoprotect-step4"></a>
### <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>可选：在整个环境中部署 Windows 信息保护

你已注册 Windows 10 企业版设备，它们部署且应用了定义下列内容的 Intune 策略：

- 要保护的应用。
- 保护级别。
- 保护涵盖的范围。

必要时请执行[第 4 步](../infoprotect-deploy-windows-information-protection.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>可选：部署 Office 365 数据丢失防护 (DLP)

你分析、测试并随后推广了 DLP 策略集；该集中注明了位置和条件及操作规则，而且你的组织需要它来保护客户和其他类型的专用数据，并借此满足行业和区域性的法规和要求。

数据合规性和安全性员工正在使用 Office 365 安全与合规仪表板来监视 DLP 事件。

必要时请执行[步骤 5](../infoprotect-data-loss-prevention.md)，这样做有助于满足此要求。 


<a name="crit-infoprotect-step6"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>可选：配置 Office 365 Privileged Access Management

你已使用[在 Office 365 中配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题中的信息来启用特权访问并在组织中创建一个或多个特权访问策略。 你已配置这些策略，且实时访问已启用，可访问敏感数据或关键配置设置。

必要时请执行[步骤 6](../infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。 
