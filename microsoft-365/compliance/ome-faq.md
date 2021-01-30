---
title: Message Encryption FAQ
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 新しいメッセージ保護機能がどのように機能するかについて質問がありますか? ここで回答を確認してください。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4be3ff4be1d5bf8b81d06ea17a8345e4c843b150
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058540"
---
# <a name="message-encryption-faq"></a>Message Encryption FAQ

新しいメッセージ保護機能がどのように機能するかについて質問がありますか? ここで回答を確認してください。 また、Azure Information Protection のデータ保護に関してよく寄せられる質問を見て [、Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) のデータ保護サービス Azure Rights Management に関する質問に対する回答を確認してください。

## <a name="what-is-office-365-message-encryption-ome"></a>OME Office 365 Message Encryption とは

OME は、電子メールの暗号化と権利管理機能を組み合わせた機能です。 権利管理機能は、Azure Information Protection を利用しています。

## <a name="who-can-use-ome"></a>OME を使用できるユーザー

OME の新しい機能は、次の条件で使用できます。
  
- 365 で Exchange Online 用に OME または IRM Office場合。

- OME と IRM を設定している場合は、Azure Information Protection の Azure Rights Management サービスを使用している場合は、次の手順を使用できます。

- Active Directory Rights Management サービス (AD RMS) で Exchange Online を使用している場合は、これらの新機能を今すぐ有効にできます。 代わりに、最初に RMS AD [Azure Information Protection に移行する必要](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) があります。 移行が完了したら、OME を正常にセットアップできます。

  Azure Information Protection に移行する代わりに、Exchange Online でオンプレミスの AD RMS を引き続き使用する場合、これらの新機能を使用することはできません。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>新しい OME 機能を使用するには、どのようなサブスクリプションが必要ですか。

新しい OME 機能を使用するには、次のいずれかのプランが必要です。
  
- Office 365 Message Encryption は、Office 365 Enterprise E3 および E5、Microsoft Enterprise E3 および E5、Microsoft 365 Business Premium、Office 365 A1、A3、A5、および Office 365 Government G3 および G5 の一部として提供されます。 お客様は、Azure Information Protection が提供する新しい保護機能を受け取る追加のライセンスを必要としません。

- Azure Information Protection プラン 1 を次のプランに追加して、Exchange Online プラン 1、Exchange Online プラン 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 Business Standard、または Office 365 Enterprise E1 の新しい Office 365 Message Encryption 機能を利用できます。

- 365 Message Encryption Officeを利用する各ユーザーには、この機能の対象となるライセンスが必要です。

- 完全な一覧については [、365](https://technet.microsoft.com/library/exchange-online-service-description.aspx) Message Encryption Office Exchange Online サービスの説明を参照してください。

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Azure Information Protection で独自のキー (BYOK) を持ち込むとともに Exchange Online を使用できますか。

可能です! OME をセットアップする前に BYOK をセットアップする手順を完了してください。
  
BYOK の詳細については、「Azure Information Protection テナント キーの計画と [実装」を参照してください](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Azure Information Protection を使用する OME と BYOK は、Microsoft のサード パーティのデータ要求 (小計など) に対するアプローチを変更しますか?

いいえ。 OME と、Azure Information Protection から BYOK と呼ばれる独自の暗号化キーを提供および制御するオプションは、法執行機関の副機関に対応するようには設計されていない。 OME は、Azure Information Protection 用 BYOK を使用して、コンプライアンスに重点を置くお客様向けに設計されました。 Microsoft は、顧客データに対するサード パーティからの要求を非常に重く受け止めています。 クラウド サービス プロバイダーは、常に顧客データのプライバシーを支持しています。 小計を受け取った場合、常に第三者を顧客にリダイレクトして情報を取得します。 (Brad Smith のブログ「 政府機関のスプーフィングから顧客データを保護する」 [を参照してください](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 受信した要求の詳細情報を定期的に公開します。 サードパーティのデータ要求の詳細については、「Microsoft Trust Center[](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data)の顧客データにアクセスする政府機関および法執行機関の要求への対応」を参照してください。 また、オンライン サービス使用条件 (OST) の「顧客データの開示 [」も参照してください](https://www.microsoft.com/Licensing/product-licensing/products.aspx)。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>この機能は、従来の Office 365 Message Encryption (OME) および Information Rights Management (IRM) 機能とどのように関係していますか。

Office 365 Message Encryption の新機能は、既存の IRM ソリューションと従来の OME ソリューションの進化です。 以下の表に詳細を示します。
  
**従来の OME、IRM、および新しい OME 機能の比較**

|**機能**|**以前のバージョンの OME**|**IRM**|**新しい OME 機能**|
|:-----|:-----|:-----|:-----|
|**暗号化された電子メールの送信**|Exchange メール フロー ルールを使用する場合のみ|Windows 用の Outlook、Outlook for Mac、または Outlook on the web から開始されたエンドユーザーまたは Exchange メール フロー ルールを使用する|Windows 用の Outlook、Outlook for Mac、または Outlook on the web から開始されたエンドユーザーまたはメール フロー ルールを使用する|
|**権限の管理**|-|[転送しない] オプションとカスタム テンプレート|[転送しない] オプション、暗号化専用オプション、既定のテンプレートとカスタム テンプレート|
|**サポートされる受信者の種類**|外部受信者のみ|内部受信者のみ|内部および外部の受信者|
|**受信者のエクスペリエンス**|外部の受信者は、ブラウザーまたはダウンロードしたモバイル アプリでダウンロードして開いた HTML メッセージを受信しました。|内部の受信者は、Outlook for Windows、Outlook for Mac、および Outlook on the web でのみ暗号化された電子メールを受信しました。|内部および外部の受信者は、Outlook for Windows、Outlook for Mac、Outlook on the web、Outlook for Android、Outlook for iOS、または Web ポータルを介して、同じ組織または組織内のかどうかに関係なく、電子メールを受信します。 OME ポータルでは、別途ダウンロードする必要はありません。|
|**Bring Your Own Key のサポート**|使用不可|使用不可| BYOK のサポート|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>組織で新しい OME 機能を有効にする方法

「Set [up new Office 365 Message Encryption capabilities 」を参照してください](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>OME の以前のバージョンは廃止されますか?

You can still use the previous version of OME, it will not be deprecated at this time. ただし、新しい強化された OME ソリューションを使用することを組織に強くお勧めしています。 OME を展開していないお客様は、以前のバージョンの OME の新しい展開を設定できません。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>組織で Active Directory Rights Management を使用している場合、この機能を使用できますか。

いいえ。 Active Directory Rights Management サービス (AD RMS) で Exchange Online を使用している場合は、これらの新機能を今すぐ有効にできます。 代わりに、最初に RMS AD [Azure Information Protection に移行する必要](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) があります。
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>自分の組織には Exchange ハイブリッド展開があります。 この機能を使用できますか?

オンプレミスのユーザーは、Exchange Online メール フロー ルールを使用して暗号化されたメールを送信できます。 これを行うには、電子メールを Exchange Online 経由でルーティングする必要があります。 詳細については、「パート [2: メール サーバーから Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)にメールを流す構成」を参照してください。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>OME 暗号化メッセージを作成するために使用する必要がある電子メール クライアント 保護されたメッセージを送信するためにサポートされているアプリケーションは何ですか?

Outlook 2016、Outlook 2013 for Windows および Mac、および Outlook on the web から保護されたメッセージを作成できます。 暗号化されたメッセージの送信について詳しくは、Outlook for PC での暗号化されたメッセージの送信、表示、返信に関 [するページをご覧ください](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>保護されたメールの読み取りおよび返信がサポートされている電子メール クライアントは何ですか?

Microsoft 365 ユーザーは、Windows および Mac 用の Outlook (2013 および 2016)、Outlook on the web、および Outlook モバイル (Android および iOS) の読み取りおよび応答を行います。 組織で許可されている場合は、iOS ネイティブ メール クライアントを使用することもできます。 Microsoft 365 ユーザーではない場合は、Web ブラウザーを使用して Web 上の暗号化されたメッセージを読んで返信できます。

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>暗号化専用の保護された電子メールをサポートする電子メール クライアントは何ですか?

Microsoft 365 ユーザーは、OUTLOOK for PC バージョン 2019 および Microsoft 365 を使用して、暗号化専用ポリシーで保護されたメールを作成できます。  つまり、新しい暗号化専用ポリシーが適用されたメッセージは、Outlook on the web、iOS および Android 用の Outlook、および現在は OUTLOOK for PC バージョン 2019 および Microsoft 365 で直接読み取りできます。

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>OME で送信できるメッセージのサイズ制限はありますか?

はい。 OME で送信できる最大メッセージ サイズ (添付ファイルを含む) は 25 MB です。 詳細については、「メッセージの [制限」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)。

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>保護された電子メールで添付ファイルとしてサポートされているファイルの種類は何ですか? 添付ファイルは、保護された電子メールに関連付けられている保護ポリシーを継承しますか?

保護されたメールには、任意の種類のファイルを添付できます。 1 つの例外を除き、保護ポリシーは、Azure Information Protection クライアントでサポートされているファイルの種類に記載されているファイル形式 [にのみ適用されます](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)。 OME では、Word (.doc)、Excel (.xls)、PowerPoint (.ppt) の Office プログラムの 97-2003 バージョンはサポートされていません。

Word、Excel、PowerPoint ファイルなどのファイル形式がサポートされている場合、受信者が添付ファイルをダウンロードした後でも、ファイルは常に保護されます。 たとえば、添付ファイルが [転送しない] で保護されている場合などです。 元の受信者がファイルをダウンロードし、新しい受信者にメッセージを作成してファイルを添付します。 新しい受信者がファイルを受信すると、その受信者は保護されたファイルを開くことができません。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF 添付ファイルはサポートされていますか?

短い答えは「はい」です。 PDF 暗号化を使用すると、セキュリティで保護された通信や安全な共同作業を通じて機密性の高い PDF ドキュメントを保護できます。 電子メールを送信すると、Office 365 サービスは Outlook クライアントではなく PDF 添付ファイルを暗号化します。

Outlook on the web、Outlook for iOS、および Outlook for Android の場合は、追加の手順なしで送信する PDF を暗号化できます。 これらのクライアントは、PDF 暗号化をネイティブにサポートします。

Outlook デスクトップは、PDF 添付ファイルの暗号化をネイティブにサポートしません。 代わりに、最初に EXCHANGE メール フロー ルールまたは DLP を設定して、PDF 添付ファイルに暗号化を適用する必要があります。 OUTLOOK デスクトップから PDF 添付ファイル付きメールを送信すると、クライアントは添付ファイルを含むメッセージを最初にサービスに送信します。 サービスがファイルを受信すると、サービスは Exchange Online のデータ損失防止 (DLP) ポリシーまたはメール フロー ルールの OME 保護を適用します。 次に、Exchange Online は、保護された PDF ファイルの添付ファイルを含むメッセージを送信します。

PDF 添付ファイルの暗号化を有効にするには、Exchange Online PowerShell で次の [コマンドを実行します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

PDF 暗号化を使用すると、セキュリティで保護された通信や安全な共同作業を通じて機密性の高い PDF ドキュメントを保護できます。 すべての Outlook クライアントで、メッセージと保護されていない PDF 添付ファイルは、Exchange Online のデータ損失防止 (DLP) ポリシーまたはメール フロー ルールの OME 保護を継承します。 また、Outlook on the web ユーザーが保護されていない PDF ドキュメントを添付し、メッセージに保護を適用する場合、メッセージはメッセージの保護を継承します。 ユーザーは、保護された PDF (OME ポータルや Azure Information Protection Viewer など) をサポートするアプリケーションでのみ、暗号化された添付ファイルを開くことができます。

> [!IMPORTANT]
> Outlook デスクトップ クライアントは PDF 暗号化をサポートしません。

## <a name="are-onedrive-for-business-attachments-supported"></a>OneDrive for Business の添付ファイルはサポートされていますか?

Not yet. OneDrive for Business の添付ファイルはサポートされていません。エンド ユーザーは、クラウド OneDrive for Business 添付ファイルを含むメールを暗号化できません。
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>保護されたメール内の暗号化された添付ファイルのプレビューをサポートする電子メール クライアントは何ですか?

添付ファイルが保護されたメールで保護されている場合、Outlook クライアントはドキュメントを直接プレビューする機能を提供します。 Outlook は、Officeドキュメント (docx、xlsx、pptx、doc、xls、ppt) のプレビューをサポートしています。 Outlook on the web は、Officeドキュメント (docx、xlsx、pptx) および PDF のプレビューをサポートしています。  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>保護された電子メールの取り消しをサポートする電子メール クライアントは何ですか?

Outlook on the web は、保護されたメールの失効をサポートしています。  詳細 [については、「送信した暗号化されたメッセージを取り消す方法」](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) を参照してください。


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>ポリシーを設定してメッセージを自動的に暗号化できますか。

はい。 Exchange Online のメール フロー ルールを使用して、特定の条件に基づいてメッセージを自動的に暗号化します。 たとえば、受信者 ID、受信者ドメイン、またはメッセージの本文または件名のコンテンツに基づくポリシーを作成できます。 Office [365](define-mail-flow-rules-to-encrypt-email.md)で電子メール メッセージを暗号化するメール フロー ルールの定義を参照してください。
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>受信メールと送信メールの暗号化を自動的に削除できますか。

管理者は、送信メールの暗号化を削除するメール フロー ルールを設定できます。 受信メールの暗号化を削除するルールを設定できない。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>セキュリティ コンプライアンス センターでデータ損失防止 (DLP) のポリシーを設定して、メッセージを自動的に &amp; 暗号化できますか。

可能です! Exchange Online またはセキュリティ コンプライアンス センターで DLP を使用して、メール フロー ルールを &amp; 設定できます。
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>会社のブランドを使用して暗号化されたメッセージをカスタマイズできますか?

可能です! 電子メール メッセージと OME ポータルのカスタマイズの詳細については、「暗号化されたメッセージに組織のブランドを追加する」を参照してください。 「 [暗号化されたメッセージに組織のブランドを追加する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>暗号化された電子メールのレポート機能や分析情報はありますか?

セキュリティ/コンプライアンス センターに暗号化レポートがあります。 「 [セキュリティ/コンプライアンス センターでのメール セキュリティ](../security/office-365-security/view-email-security-reports.md)レポート&参照してください。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>電子情報開示などのコンプライアンス機能でメッセージの暗号化を使用できますか。

はい。 暗号化された電子メール メッセージはすべて、Microsoft 365 コンプライアンス機能で検出できます。

## <a name="can-i-remove-encryption-from-email"></a>電子メールから暗号化を削除できますか?

管理者は、送信メールから暗号化を削除するメール フロー ルールを設定できます。 受信メッセージからメール フロー ルールを使用して暗号化を削除できない。

## <a name="is-delegated-access-supported"></a>委任アクセスはサポートされていますか?

現時点ではそうではありません。

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>共有メールボックスとして送信し、電子メールを暗号化できますか?

暗号化メール フロー ルールに一致するメール メッセージを誰かが送信すると、メッセージは送信される前に暗号化されます。

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>共有メールボックスに送信された暗号化されたメッセージを開く方法

可能です! 暗号化されたメッセージは、共有メールボックスでサポートされます。

- ユーザーは、共有メールボックスが配布グループの一部として保護されたメールを受信した共有メールボックスで保護されたメールを開くできます。

- ユーザーは、Outlook for Windows、Outlook for Mac、および Outlook on the web を使用するときに、電子メールから保護を継承する添付ファイルを表示できます。

次の表に、共有メールボックスでサポートされているクライアントの一覧を示します。

| プラットフォーム | メールの読み取り | メールの添付ファイルを表示する |
|----------|-----------|------------------------|
| Outlook on the web | はい | はい                |
| Outlook for Windows| はい | はい                |
| Outlook for Mac    | はい | はい                |
| Outlook for Android| はい | いいえ                 |
| Outlook for iOS    | はい | いいえ                 |
|

現在、2 つの既知の制限があります。

- Outlook モバイルを使用して、モバイル デバイスで受信した電子メールの添付ファイルを開く方法は使用できません。

- メールが有効なセキュリティ グループによる割り当てはサポートされていません。 ユーザーの共有メールボックスへの直接割り当てによって提供されるアクセスのみサポートされ、自動マッピングは Exchange Online に対して有効になっています。 Exchange Online では、自動マッピングは既定で有効になっています。

**共有メールボックスにユーザーを割り当てるには**

1. [リモート PowerShell を使用して Exchange Online に接続します](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)。

2. Automapping パラメーターAdd-MailboxPermissionコマンドレットを実行します。 この例では、サポート メールボックスへのフル アクセス許可を Ayla に付与します。

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>別のユーザーのメールボックスに送信された暗号化されたメッセージを Fullaccess で開くことができるか?

ユーザーは、直接アクセスが許可され、自動マッピングがオンになっている限り、暗号化されたメッセージを開くできます。 電子メールが有効なセキュリティ グループを介してアクセスが許可されている場合、アクセスは許可されません。

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>要求した後に 1 回のパス コードを受け取らない場合は、どうしますか。

まず、メール クライアントの迷惑メール フォルダーまたはスパム フォルダーを確認します。 組織の DKIM と DMARC の設定によって、これらのメールがスパムとしてフィルター処理される場合があります。

次に、セキュリティ/コンプライアンス センターで&確認します。 多くの場合、1 回パス コードを含むメッセージ (特に組織が最初に受信するコード) は検疫されます。
