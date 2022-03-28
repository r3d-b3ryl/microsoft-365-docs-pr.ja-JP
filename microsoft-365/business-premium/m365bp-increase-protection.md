---
title: ユーザーの脅威保護を強化Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- admindeeplinkMAC
- admindeeplinkEXCHANGE
- admindeeplinkSPO
search.appverid:
- BCS160
- MET150
description: ユーザーの保護のレベルを上Microsoft 365 Business Premium
ms.openlocfilehash: c6533b966587235b8f29c1ce53bd9d5579b23b9c
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403811"
---
# <a name="increase-threat-protection-for-microsoft-365-business-premium"></a>ユーザーの脅威保護を強化Microsoft 365 Business Premium

この目的では、脅威の保護を強化し、Microsoft 365 Business Premium。 組織をフィッシング、マルウェア、その他の脅威から保護する必要があります。 これらの推奨事項は、セキュリティの必要性が高い政治キャンペーン、法律事務所、医療クリニックに特に適しています。

## <a name="start-with-secure-score"></a>セキュリティで保護されたスコアから始める

Microsoft Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。 現在のスコアに注意し、この記事で推奨されるアクションを実行してスコアを上げろ。 目標は、常に注意してスコアを向上させる方法です。

詳細については、「 [Microsoft Secure Score」を参照してください](../security/defender/microsoft-secure-score.md)。

## <a name="review-and-apply-preset-security-policies"></a>事前設定されたセキュリティ ポリシーを確認して適用する

サブスクリプションには、 [スパム対策、](../security/office-365-security/preset-security-policies.md) マルウェア対策、フィッシング対策保護に推奨設定を使用する事前設定のセキュリティ ポリシーが含まれています。 既定では、組み込みの保護が有効になっています。セキュリティを強化する場合は、標準保護または厳密な保護の適用を検討してください。 

事前設定されたセキュリティ ポリシーは、次の要素で構成されます。

- 保護のレベルを決定するプロファイル
- ポリシー (スパム対策、マルウェア対策、フィッシング対策、セーフ添付ファイル、セーフ リンクなど)
- ポリシー設定 (グループ、ユーザー、ドメインなど、ポリシーと例外を受信する)

次の表に、保護のレベルと事前設定されたポリシーの種類を示します。

| 保護のレベル | 説明 |
|:---|:---|
| **標準保護** <br/>(*ほとんどの企業に推奨*) | 標準保護では、ほとんどのユーザーに適したベースライン プロファイルを使用します。 <br/><br/>これには、スパム対策、マルウェア対策、フィッシング対策、スプーフィング設定、偽装設定、セーフ リンク、セーフ添付ファイル ポリシーが含まれます。  |
| **厳密な保護**  | 厳密な保護には、標準保護と同じ種類のポリシーが含まれますが、より厳しい設定が含まれます。 ビジネスが追加のセキュリティ要件や規制を満たす必要がある場合は、優先度の高いユーザーまたは価値の高いターゲットに厳密な保護を適用してください。 |
| **組み込みの保護** | 電子メール内の悪意のあるリンクや添付ファイルから保護します。 既定では、すべてのユーザーに対して有効および適用されます。  |

ユーザー、グループ、およびドメインを指定して、事前設定されたポリシーを受け取り、特定の例外を定義できますが、事前設定されたポリシー自体を変更することはできません。

また、会社のニーズに合わせてカスタム設定用の独自のセキュリティ ポリシーを作成することもできます。




<!--https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide


## Raise the level of protection against malware in mail

Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware. To bump up malware protection in email:

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a> and sign in with your admin account credentials.

2. In the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.

3. Double-click the default policy to edit this company-wide policy.

4. Click **Settings**.

5. Under **Common Attachment Types Filter**, select **On**. The file types that are blocked are listed in the window directly below this control. Make sure you add these filetypes:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   You can add or delete file types later, if needed.

6. Click **Save.**

For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).

## Protect against ransomware

Ransomware restricts access to data by encrypting files or locking computer screens. It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.

You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.

In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros. Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.

To create a mail transport rule:

1. Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.

2. In the **mail flow** category, click **rules**.

3. Click **+**, and then click **Create a new rule**.

4. Click **More options** at the bottom of the dialog box to see the full set of options.

5. Apply the settings in the following table for the rule. Leave the rest of the settings at the default, unless you want to change them.

6. Click **Save**.

|Setting|Warn users before opening attachments of Office files|
|---|---|
|Name|Anti-ransomware rule: warn users|
|Apply this rule if . . .|Any attachment . . . file extension matches . . .|
|Specify words or phrases|Add these file types: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Do the following . . .|Notify the recipient with a message|
|Provide message text|Do not open these types of files from people you do not know because they might contain macros with malicious code.|

For more information, see:

- [Ransomware: how to reduce risk](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restore your OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## Stop auto-forwarding for email

Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email. This can happen even without the user's awareness. You can prevent this from happening by configuring a mail flow rule.

To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, click **Admin centers** \> **Exchange**.

2. In the **mail flow** category, click **rules**.

3. Click **+**, and then click **Create a new rule**.

4. Click **More options** at the bottom of the dialog box to see the full set of options.

5. Apply the settings in the following table. Leave the rest of the settings at the default, unless you want to change them.

6. Click **Save**.

|Setting|Warn users before opening attachments of Office files|
|---|---|
|Name|Prevent auto forwarding of email to external domains|
|Apply this rule if ...|The sender . . . is external/internal . . . Inside the organization|
|Add condition|The message properties . . . include the message type . . . Auto-forward|
|Do the following ...|Block the message . . . reject the message and include an explanation.|
|Provide message text|Auto-forwarding email outside this organization is prevented for security reasons.|

## Protect your email from phishing attacks

If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection. Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks. If you haven't configured a custom domain, you don't need to do this.

We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.

To create an anti-phishing policy in Defender for Office 365, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:

1. Go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a>.

2. In the left navigation pane, under **Threat management**, choose **Policy**.

3. On the **Policy** page, choose **Anti-phishing**.

4. On the **Anti-phishing** page, select **+ Create**. A wizard launches that steps you through defining your anti-phishing policy.

5. Specify the name, description, and settings for your policy as recommended in the chart below. For more information, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.

|Setting or option|Recommended setting|
|---|---|
|Name|Domain and most valuable staff|
|Description|Ensure most important staff and our domain are not being impersonated.|
|Add users to protect|Select **+ Add a condition, The recipient is**. Type user names or enter the email address of the business owners, partners, or candidate, managers, and other important staff members. You can add up to 20 internal and external addresses that you want to protect from impersonation.|
|Add domains to protect|Select **+ Add a condition, The recipient domain is**. Enter the custom domain associated with your Microsoft 365 subscription, if you defined one. You can enter more than one domain.|
|Choose actions|If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*. <br/> If email is sent by an impersonated domain: Choose **Quarantine message**.|
|Mailbox intelligence|By default, mailbox intelligence is selected when you create a new anti-phishing policy. Leave this setting **On** for best results.|
|Add trusted senders and domains|Here you can add your own domain, or any other trusted domains.|
|Applied to|Select **The recipient domain is**. Under **Any of these**, select **Choose**. Select **+ Add**. Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**. Select **Done**.|

For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## Protect against malicious attachments, files, and links with Defender for Office 365

![Banner that point to https://aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)

First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on. Turn on the toggle next to the text **The new admin center**.

   ![The new admin center preview on.](../media/previewon.png)

If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center. See [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and [Set up Safe Links in the Security & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).

1. In the left nav, choose **Setup**.
2. On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.

   ![Choose View on the Increase protection from advanced threats.](../media/startatp.png)

3. On the **Increase protection from advanced threats** page, choose **Get started**.
4. On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.
    
   Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.

   ![Select all check boxes in Increase protection from advanced threats.](../media/setatp.png)

5. Choose **Create policies** to turn on Safe Attachments and Safe Links.

### Set up Safe Attachments in the Security & Compliance Center

People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more. It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message. Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default. We recommend that you create a new rule to begin using this protection. This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.

To create a Safe Attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:

1. Go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a> and sign in with your admin account.

2. In the left navigation pane, under **Threat management**, choose **Policy**.

3. On the Policy page, choose **Safe Attachments**.

4. On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.

5. Select **+** to create a new policy.

6. Apply the settings in the following table.

7. After you review your settings, choose **Create this policy** or **Save**, as appropriate.

|Setting or option|Recommended setting|
|---|---|
|Name|Block current and future emails with detected malware.|
|Description|Block current and future emails and attachments with detected malware.|
|Save attachments unknown malware response|Select **Block - Block the current and future emails and attachments with detected malware**.|
|Redirect attachment on detection|Enable redirection (select this box) <br/> Enter the admin account or a mailbox setup for quarantine. <br/> Apply the above selection if malware scanning for attachments times out or error occurs (select this box).|
|Applied to|The recipient domain is . . . select your domain.|

For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

### Set up Safe Links in the Security & Compliance Center

Hackers sometimes hide malicious websites in links in email or other files. Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents. Protection is defined through Safe Links policies.

We recommend that you do the following:

- Modify the default policy to increase protection.

- Add a new policy targeted to all recipients in your domain.

To set up Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:

1. Go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a> and sign in with your admin account.

2. In the left navigation pane, under **Threat management**, choose **Policy**.

3. On the Policy page, choose **Safe Links**.

To modify the default policy:

1. On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.

2. Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.

3. Click **Save**.

To create a new policy targeted to all recipients in your domain:

1. On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.

2. Apply the settings listed in the following table.

3. Click **Save**.

|Setting or option|Recommended setting|
|---|---|
|Name|Safe links policy for all recipients in the domain|
|Select the action for unknown potentially malicious URLs in messages|Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Use Safe Attachments to scan downloadable content|Select this box.|
|Applied to|The recipient domain is . . . select your domain.|

For more information, see [Safe Links in Defender for Office 365](../security/office-365-security/safe-links.md).

-->

## <a name="turn-on-the-unified-audit-log"></a>統合監査ログを有効にする

セキュリティ & コンプライアンス センターで監査ログ検索を有効にした後、管理者と他のユーザー アクティビティをログに保持して検索できます。

監査ログの検索を有効またはExchange Onlineするには、監査ログの役割をMicrosoft 365があります。 既定では、この役割は、管理センターの [アクセス許可] ページの [コンプライアンス管理] および [組織の管理<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange割り当てられます</a>。 既定では、Microsoft 365のグローバル管理者は、このグループのメンバーです。

1. 監査ログ検索を有効にする場合は、<https://admin.microsoft.com>管理センターに移動し、左側のナビゲーションの [管理センター] で [セキュリティ **]** を選択します。
2. [セキュリティの **Microsoft 365]** ページで、[その他のリソース] を選択し、[コンプライアンス センター] Office 365 **[&]** カードで開きます。

    ![コンプライアンス 車のセキュリティ とセキュリティ &を選択します。](../media/gotosecandcomp.png)
3. [セキュリティとコンプライアンス] ページで、[検索] を選択 **し** 、[ログ検索 **の監査] を選択します**。
4. [監査ログ検索] ページ **の上部にある [** 監査 **を有効にする] を選択します**。

機能を有効にすると、ファイル、フォルダー、および多くのアクティビティを検索できます。 詳細については、「監査ログ [を検索する」を参照してください](../compliance/search-the-audit-log-in-security-and-compliance.md)。

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>ファイルとフォルダーの共有と管理SharePoint匿名OneDrive設定を調整する

(既定の匿名リンクの有効期限を 14 日間に変更し、既定の共有の種類を "特定のユーザー" に変更する)ユーザーとユーザーの共有設定をOneDriveするにはSharePoint。

1. [管理センター] に移動<https://admin.microsoft.com>し、左側のナビゲーション **SharePoint** **[管理センター**] で [管理センター] を選択します。
2. 管理センター SharePoint[ポリシーの共有 **] に移動** \> <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**します**</a>。
3. [共有] ページの [ファイルとフォルダーのリンク] で、[特定のユーザー] を選択し、[すべてのユーザー **]** リンクの [詳細設定] で、[これらのリンクは、この数日以内に期限切れになる必要があります] を選択し、14 (またはリンクの有効期間を制限する別の日数) を入力します。

   ![[特定のユーザー] を選択し、リンクの有効期限を 14 日間に設定します。](../media/anyonelinks.png)


## <a name="activity-alerts"></a>アクティビティ通知

アクティビティ通知を使用して、管理者とユーザーのアクティビティを追跡し、組織内のマルウェアやデータ損失防止インシデントを検出できます。 サブスクリプションには一連の既定のポリシーが含まれていますが、カスタム ポリシーを作成できます。 詳細については、「アラート ポリシー [」を参照してください](../compliance/alert-policies.md)。 たとえば、誰も外部で共有したくない重要なファイルを SharePoint に保存する場合は、他のユーザーが共有した場合に通知する通知を作成できます。

次の図は、このポリシーに含まれる既定のMicrosoft 365。

![既定のアラート ポリシーは、Microsoft 365。](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>予定表の共有を無効または管理する

組織内のユーザーが予定表を共有したり、共有できるコンテンツを管理したりすることもできます。 たとえば、共有を空き時間に制限できます。

1. 管理センターに移動し、[<https://admin.microsoft.com>組織] **設定** \> **サービス設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**します**</a>。

1. [**予定表]** を選択し、組織内のユーザーが自分の予定表を外部のユーザーと共有できるかどうかOffice 365、Exchangeを選択します。

   [すべてのユーザーと共有] オプションを選択した場合は、空き時間情報のみを共有することもできます。

3. ページの **下部にある** [変更の保存] を選択します。

   次の図は、予定表の共有が許可されていないを示しています。

   ![外部予定表の共有を許可しないとして表示するスクリーンショット。](../media/nocalendarsharing.png)

   次の図は、空き時間情報のみを含むメール リンクで予定表の共有が許可されている場合の設定を示しています。

   ![予定表の空き時間情報を誰とでも共有するスクリーンショット。](../media/sharefreebusy.png)

ユーザーが予定表の共有を許可されている場合は、[ユーザーが予定表](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5)から共有する方法については、次の手順をOutlook on the web。

