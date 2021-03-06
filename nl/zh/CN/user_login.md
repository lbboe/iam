---

copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}

# 管理用户的登录设置
{: #loginsettings}

帐户所有者或具有正确访问权的用户可以管理用户的登录设置，例如订购外部认证选项，支持在登录期间使用一次性密码，支持在登录时使用安全问题，以及设置密码到期时间段。
{:shortdesc}

要管理特定用户的登录设置，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户，然后单击**用户详细信息**。
3. 在**管理用户登录**部分中，可以对所选用户开启或关闭以下选项：

    * 基于时间的一次性密码 MFA：开启此选项可在登录时提示用户输入一次性密码。用户必须在“登录设置”页面中设置其 TOTP MFA。有关更多信息，请参阅[为用户启用一次性密码 MFA](/docs/iam/totp.html#totp)。

    * 订购外部认证：选择此选项可购买按月收费的 Symantec 或基于电话的认证。一次只能订购和使用一个选项。有关更多信息，请参阅[为用户订购外部认证 MFA](/docs/iam/external_mfa.html#external)。

        * 基于电话的认证：帐户所有者订购此选项后，用户可以通过在“用户详细信息”页面中设置的配置来使用此选项。
        * Symantec 认证：帐户所有者订购此选项后，用户即可以使用此选项。为了让管理员订购此选项，用户必须先提供自己的凭证标识。

    * 登录时使用 MFA 安全问题：开启此选项要求提示用户提供自己在“登录设置”页面中设置的安全问题和答案。除非用户已设置自己的安全问题，否则无法开启此选项。有关更多信息，请参阅[为用户启用 MFA 安全问题](/docs/iam/securityquestions.html#questions)。

    * 用户管理的登录：开启此选项以允许用户设置密码到期时间，开启安全问题用于登录，以及为 {{site.data.keyword.cloud_notm}} 登录和经典基础架构 API 指定允许的 IP 地址。

    * 密码到期时间：通过从列表中选择选项来设置到期时间。此选项仅可用于使用 SoftLayer 标识的用户。如果用户可以管理自己的登录设置，那么他们可以在其“登录设置”页面上设置此到期时间。只有具有以下许可权的用户才能为用户设置密码到期时间：

        * 分配有具有对用户管理服务的编辑者或更高角色的 IAM 策略的任何用户。
        * 其管理员在其“用户详细信息”页面上启用了用户管理的登录的任何用户。
        * 在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。

一次只应启用一个 MFA 选项。如果用户所属的任何帐户需要 IBM 标识 MFA，那么此 MFA 会覆盖其他任何已启用的 MFA，并且不会提示用户进行其他任何类型的 MFA。
{: important}
