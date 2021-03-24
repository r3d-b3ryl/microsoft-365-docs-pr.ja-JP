---
title: メッセージの暗号化に関する FAQ
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
description: 新しいメッセージ保護機能がどのように機能するかについて質問がありますか? ここで答えを確認してください。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d4181482bf8ad7460480a70c762fe60fd28ad0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051749"
---
# <a name="message-encryption-faq"></a>メッセージの暗号化に関する FAQ

新しいメッセージ保護機能がどのように機能するかについて質問がありますか? ここで答えを確認してください。 また、Azure Information Protection のデータ保護サービス Azure Rights Management に関する質問に対する回答については [、Azure Information Protection](/information-protection/get-started/faqs-rms) のデータ保護に関してよく寄せられる質問を参照してください。

## <a name="what-is-office-365-message-encryption-ome"></a>365 Office暗号化 (OME) とは何ですか?

OME は、電子メールの暗号化と権限管理機能を組み合わせたもの。 権限管理機能は、Azure Information Protection によって提供されます。

## <a name="who-can-use-ome"></a>OME を使用できるユーザー

OME の新機能は、次の条件で使用できます。
  
- 365 で Exchange Online 用 OME または IRM を設定したことがないOffice。

- OME と IRM をセットアップしている場合は、Azure Information Protection の Azure Rights Management サービスを使用している場合は、次の手順を使用できます。

- Active Directory Rights Management サービス (AD RMS) で Exchange Online を使用している場合は、これらの新しい機能をすぐ有効にできます。 代わりに、最初に RMS AD [Azure Information Protection に移行する必要](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) があります。 移行が完了したら、OME を正常にセットアップできます。

  Azure Information Protection に移行する代わりに、Exchange Online でオンプレミス AD RMS を引き続き使用する場合は、これらの新機能を使用することはできません。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>新しい OME 機能を使用する必要があるサブスクリプション

新しい OME 機能を使用するには、次のいずれかの計画が必要です。
  
- Office 365 メッセージ暗号化は、Office 365 Enterprise E3 および E5、Microsoft Enterprise E3 および E5、Microsoft 365 Business Premium、Office 365 A1、A3、および A5、および Office 365 Government G3 および G5 の一部として提供されます。 お客様は、Azure Information Protection を利用した新しい保護機能を受け取る追加のライセンスを必要としません。

- Azure Information Protection Plan 1 を次のプランに追加して、新しい Office 365 メッセージ暗号化機能 (Exchange Online プラン 1、Exchange Online プラン 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 Business Standard、または Office 365 Enterprise E1) を受信できます。

- 365 Message Encryption Officeを利用する各ユーザーは、この機能の対象となるライセンスを取得する必要があります。

- 完全な一覧については [、「Exchange Online サービス](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) の説明」を参照Office 365 Message Encryption.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Azure Information Protection で独自のキー (BYOK) を持参して Exchange Online を使用できますか?

はい。 OME をセットアップする前に、BYOK をセットアップする手順を完了してください。
  
BYOK の詳細については、「Azure Information Protection テナント キーの計画 [と実装」を参照してください](/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Azure Information Protection を使用した OME と BYOK は、サブポエナなどのサード パーティのデータ要求に対する Microsoft のアプローチを変更しますか?

いいえ。 OME と、Azure Information Protection から BYOK と呼ばれる独自の暗号化キーを提供および制御するオプションは、法執行機関のサブポエナに対応するようには設計されていない。 OME は、BYOK for Azure Information Protection を使用して、コンプライアンスに焦点を当てたお客様向けに設計されました。 Microsoft は、顧客データに対するサード パーティの要求を非常に真剣に受け止めています。 クラウド サービス プロバイダーとして、常に顧客データのプライバシーを主張しています。 Subpoena を取得した場合は、常に第三者を顧客にリダイレクトして情報を取得します。 (Brad Smith のブログ「 政府のスヌーピングから顧客データを保護する」 [をご覧ください](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 受信した要求の詳細な情報を定期的に公開します。 サード パーティのデータ要求の詳細については、「Microsoft Trust [](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) Center で顧客データにアクセスする政府機関および法執行機関の要求への対応」を参照してください。 また、オンライン サービス条項 (OST) の「顧客データの開示 [」を参照してください](https://www.microsoft.com/Licensing/product-licensing/products.aspx)。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>この機能は、従来の 365 メッセージ暗号化 (OME) Office情報権利管理 (IRM) 機能とどのように関連していますか?

365 Message Encryption Office機能は、既存の IRM ソリューションと従来の OME ソリューションの進化です。 以下の表に詳細を示します。
  
**従来の OME、IRM、および新しい OME 機能の比較**

| 機能 | OME の以前のバージョン | IRM | 新しい OME 機能 |
|:-----|:-----|:-----|:-----|
|**暗号化されたメールの送信**|Exchange メール フロー ルールを使用する場合のみ|Outlook for Windows、Outlook for Mac、または Outlook on the web から開始されたエンド ユーザー。または Exchange メール フロー ルールを使用する|Outlook for Windows、Outlook for Mac、または Outlook on the web から開始されたエンド ユーザー。またはメール フロー ルールを使用する|
|**権限の管理**|-|[転送しない] オプションとカスタム テンプレート|[転送しない] オプション、暗号化のみ可能なオプション、既定のテンプレートとカスタム テンプレート|
|**サポートされている受信者の種類**|外部受信者のみ|内部受信者のみ|内部および外部の受信者|
|**受信者のエクスペリエンス**|外部受信者は、ブラウザーまたはダウンロードしたモバイル アプリでダウンロードして開いた HTML メッセージを受信しました。|内部受信者は、Outlook for Windows、Outlook for Mac、および Outlook on the web でのみ暗号化されたメールを受信しました。|内部および外部の受信者は、Outlook for Windows、Outlook for Mac、Outlook on the web、Outlook for Android、および Outlook for iOS、または Web ポータルを通じて、同じ組織または組織内のかどうかに関係なく、電子メールを受信します。 OME ポータルでは、個別にダウンロードする必要はありません。|
|**独自のキーのサポートを提供する**|使用不可|使用不可| BYOK がサポートされています|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>組織の新しい OME 機能を有効にする方法

[「365 メッセージ暗号化Officeをセットアップする」を参照してください](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>以前のバージョンの OME は非推奨ですか?

以前のバージョンの OME は引き続き使用できます。現時点では廃止されません。 ただし、新しく改良された OME ソリューションを使用することを組織に強くお勧めしています。 OME を展開していないお客様は、以前のバージョンの OME の新しい展開を設定できません。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>組織で Active Directory Rights Management を使用している場合、この機能を使用できますか?

いいえ。 Active Directory Rights Management サービス (AD RMS) で Exchange Online を使用している場合は、これらの新しい機能をすぐ有効にできます。 代わりに、最初に RMS AD [Azure Information Protection に移行する必要](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) があります。
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>組織に Exchange ハイブリッド展開があります。 この機能を使用できますか?

オンプレミスのユーザーは、Exchange Online メール フロー ルールを使用して暗号化されたメールを送信できます。 これを行うには、Exchange Online 経由で電子メールをルーティングする必要があります。 詳細については、「パート [2: メール サーバーから Microsoft 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)に流れるメールを構成する」を参照してください。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>OME 暗号化されたメッセージを作成するために使用する必要がある電子メール クライアント 保護されたメッセージの送信でサポートされているアプリケーション

Outlook 2016、Outlook 2013 for Windows および Mac、および Outlook on the web から保護されたメッセージを作成できます。 暗号化されたメッセージの送信の詳細については、「Outlook for PC で暗号化されたメッセージを送信、表示、返信する [」を参照してください](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>保護された電子メールの読み取りおよび返信にサポートされている電子メール クライアント

Microsoft 365 ユーザーは、Outlook for Windows と Mac (2013 と 2016)、Outlook on the web、Outlook mobile (Android および iOS) から読み取り、応答できます。 組織で許可されている場合は、iOS ネイティブ メール クライアントを使用することもできます。 Microsoft 365 ユーザーではない場合は、Web ブラウザーを介して Web 上の暗号化されたメッセージを読んで返信できます。

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>暗号化専用の保護された電子メールをサポートする電子メール クライアントは何ですか?

Microsoft 365 ユーザーは、Outlook for PC バージョン 2019 および Microsoft 365 を使用して、暗号化専用ポリシーで保護されたメールを作成できます。  つまり、新しい暗号化専用ポリシーが適用されているメッセージは、Outlook on the web、Outlook for iOS および Android、および現在の Outlook for PC バージョン 2019 および Microsoft 365 で直接読み取り可能です。

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>OME で送信できるメッセージのサイズ制限はありますか?

はい。 添付ファイルを含む OME で送信できる最大メッセージ サイズは 25 MB です。 詳細については、「メッセージの制限 [」を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)。

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>保護されたメールで添付ファイルとしてサポートされているファイルの種類 添付ファイルは、保護されたメールに関連付けられている保護ポリシーを継承しますか?

保護されたメールには、任意の種類のファイルを添付できます。 1 つの例外を除き、保護ポリシーは、Azure Information Protection クライアントでサポートされているファイルの種類に記載されているファイル形式 [にのみ適用されます](/information-protection/rms-client/client-admin-guide-file-types)。 OME は、Word (.doc)、Excel (.xls)、PowerPoint (.ppt) の 97~2003 バージョンの Office プログラムをサポートしていない。

Word、Excel、PowerPoint ファイルなどのファイル形式がサポートされている場合、添付ファイルが受信者によってダウンロードされた後でも、ファイルは常に保護されます。 たとえば、添付ファイルが転送しないによって保護されている場合などです。 元の受信者はファイルをダウンロードし、新しい受信者にメッセージを作成し、ファイルを添付します。 新しい受信者がファイルを受信すると、受信者は保護されたファイルを開くことができません。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF ファイルの添付ファイルはサポートされていますか?

短い答えははい! PDF 暗号化を使用すると、セキュリティで保護された通信または安全な共同作業を通じて、機密性の高い PDF ドキュメントを保護できます。 電子メールを送信すると、Office 365 サービスは Outlook クライアントではなく PDF ファイルの添付ファイルを暗号化します。

Outlook on the web、Outlook for iOS、および Outlook for Android の場合は、追加の手順なしで送信する PDF を暗号化できます。 これらのクライアントは、PDF 暗号化をネイティブにサポートします。

Outlook デスクトップは、PDF ファイル添付ファイルの暗号化をネイティブにサポートしません。 代わりに、Exchange メール フロー ルールまたは DLP を設定して、最初に PDF 添付ファイルに暗号化を適用する必要があります。 Outlook Desktop から PDF 添付ファイルを使用してメールを送信すると、クライアントは最初に添付ファイルを含むメッセージをサービスに送信します。 サービスがファイルを受信すると、サービスは Exchange Online のデータ損失防止 (DLP) ポリシーまたはメール フロー ルールの OME 保護を適用します。 次に、Exchange Online は保護された PDF ファイル添付ファイルを使用してメッセージを送信します。

PDF 添付ファイルの暗号化を有効にするには、Exchange Online PowerShell で次の [コマンドを実行します](/powershell/exchange/connect-to-exchange-online-powershell)。

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

PDF 暗号化を使用すると、セキュリティで保護された通信または安全な共同作業を通じて、機密性の高い PDF ドキュメントを保護できます。 すべての Outlook クライアントで、メッセージと保護されていない PDF 添付ファイルは、Exchange Online のデータ損失防止 (DLP) ポリシーまたはメール フロー ルールの OME 保護を継承します。 また、Outlook on the Web ユーザーが保護されていない PDF ドキュメントを添付し、メッセージに保護を適用した場合、メッセージはメッセージの保護を継承します。 ユーザーは、保護された PDF (OME ポータルや Azure Information Protection Viewer など) をサポートするアプリケーションでのみ、暗号化された添付ファイルを開くことができます。

> [!IMPORTANT]
> Outlook デスクトップ クライアントは PDF 暗号化をサポートしません。

## <a name="are-onedrive-for-business-attachments-supported"></a>OneDrive for Business の添付ファイルはサポートされていますか?

Not yet. OneDrive for Business の添付ファイルはサポートされていません。また、エンドユーザーはクラウド OneDrive for Business 添付ファイルを含むメールを暗号化できません。
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>保護されたメールで暗号化された添付ファイルのプレビューをサポートするメール クライアント

添付ファイルが保護されたメールで保護されている場合、Outlook クライアントはドキュメントを直接プレビューできます。 Outlook は、Officeドキュメント (docx、xlsx、pptx、doc、xls、ppt) のプレビューをサポートしています。 Outlook on the web では、Officeドキュメント (docx、xlsx、pptx) および PDF のプレビューがサポートされています。  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>保護されたメールの失効をサポートする電子メール クライアント

Outlook on the web では、保護されたメールの失効がサポートされています。  詳細 [については、「送信した暗号化されたメッセージを取り消す方法」](revoke-ome-encrypted-mail.md#how-to-revoke-an-encrypted-message-that-you-sent) を参照してください。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>ポリシーを設定してメッセージを自動的に暗号化できますか?

はい。 Exchange Online のメール フロー ルールを使用して、特定の条件に基づいてメッセージを自動的に暗号化します。 たとえば、受信者 ID、受信者ドメイン、またはメッセージの本文または件名のコンテンツに基づくポリシーを作成できます。 [「365 で電子メール メッセージを暗号化するメール フロー ルールの定義Office」を参照してください](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>受信メールと送信メールの暗号化を自動的に削除できますか?

管理者は、送信メールの暗号化を削除するメール フロー ルールを設定できます。 受信メールの暗号化を削除するルールを設定できない。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>セキュリティ コンプライアンス センターを通じてデータ損失防止 (DLP) でポリシーを設定することで、メッセージを自動的に &amp; 暗号化できますか?

はい。 メール フロー ルールは、Exchange Online で設定するか、セキュリティ コンプライアンス センターで DLP を &amp; 使用して設定できます。
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>会社のブランド化で暗号化されたメッセージをカスタマイズできますか?

はい。 電子メール メッセージと OME ポータルのカスタマイズの詳細については、「暗号化されたメッセージに組織のブランドを追加する」を参照してください。 「 [暗号化されたメッセージに組織のブランドを追加する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>暗号化されたメールに関するレポート機能や分析情報はありますか?

セキュリティとコンプライアンス センターに暗号化レポートがあります。 「 [セキュリティ コンプライアンス センターで電子メール セキュリティ レポートを表示&する」を参照してください](../security/defender-365-security/view-email-security-reports.md)。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>電子情報開示などのコンプライアンス機能でメッセージ暗号化を使用できますか?

はい。 暗号化された電子メール メッセージはすべて、Microsoft 365 コンプライアンス機能で検出できます。

## <a name="can-i-remove-encryption-from-email"></a>電子メールから暗号化を削除できますか?

管理者は、暗号化を削除するメール フロー ルールを設定できます。 暗号化専用保護を使用してメールを受信しない限り、別の組織によって適用されるメールからメール フロー ルールを使用して暗号化を削除できない。

## <a name="is-delegated-access-supported"></a>委任アクセスはサポートされていますか?

現時点ではそうではありません。

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>共有メールボックスとして送信し、電子メールを暗号化できますか?

暗号化メール フロー ルールに一致するメール メッセージを誰かが送信すると、メッセージは送信される前に暗号化されます。

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>共有メールボックスに送信される暗号化されたメッセージを開く方法は?

はい。 暗号化されたメッセージは、共有メールボックスでサポートされます。

- ユーザーは、共有メールボックスで保護されたメールを開き、共有メールボックスが配布グループの一部として保護されたメールを受信しました。

- ユーザーは、Outlook for Windows、Outlook for Mac、および Outlook on the web を使用するときに、電子メールからの保護を継承する添付ファイルを表示できます。

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

- Outlook モバイルを使用して、モバイル デバイスで受信したメールへの添付ファイルを開くことができません。

- メールが有効なセキュリティ グループによる割り当てはサポートされていません。 ユーザーが共有メールボックスに直接割り当て、自動マップが Exchange Online で有効になっているアクセスのみをサポートします。 自動マッピングは Exchange Online で既定で有効になっています。

**共有メールボックスにユーザーを割り当てるには**

1. [リモート PowerShell .aspx を使用して Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell?v=exchg.150)に接続します。

2. Automapping パラメーターAdd-MailboxPermissionを使用して、このコマンドレットを実行します。 この例では、Ayla にサポート メールボックスへのフル アクセス許可を与えます。

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```

## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>Fullaccess を使用して、別のユーザーのメールボックスに送信される暗号化されたメッセージを開く方法はありますか?

ユーザーは、直接アクセス権が与え、自動マッピングがオンになっている限り、暗号化されたメッセージを開くできます。 電子メールが有効なセキュリティ グループを介してアクセスが許可されている場合、アクセスは許可されません。

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>要求した後に 1 回のパス コードを受け取らない場合は、どうしますか。

まず、メール クライアントの迷惑メール フォルダーまたは迷惑メール フォルダーを確認します。 組織の DKIM と DMARC の設定により、これらのメールがスパムとしてフィルター処理される可能性があります。

次に、セキュリティ コンプライアンス センターで&を確認します。 多くの場合、1 回きりパス コードを含むメッセージ(特に組織が最初に受け取ったメッセージ)は検疫に入ります。