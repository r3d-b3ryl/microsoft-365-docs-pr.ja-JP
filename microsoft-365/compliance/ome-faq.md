---
title: Office 365 Message Encryption に関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Office 365 の新しいメッセージ保護機能がどのように機能するかについての質問がありますか。 ここで回答を確認してください。
ms.openlocfilehash: 95efde63ff9cf4c53522c0242a33001a35d2e334
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818849"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 Message Encryption に関する FAQ

Office 365 の新しいメッセージ保護機能がどのように機能するかについての質問がありますか。 ここで回答を確認してください。 また、azure information protection でのデータ保護サービスの Azure Rights Management に関する質問に対する回答については、「 [Azure Information protection でのデータ保護に関するよく寄せられる質問](https://docs.microsoft.com/information-protection/get-started/faqs-rms)」を参照してください。

## <a name="what-is-office-365-message-encryption-ome"></a>Office 365 メッセージの暗号化 (OME) とは

OME は、電子メールの暗号化と権限の管理機能を統合します。 権限管理機能は、Azure Information Protection によって処理されます。
  
## <a name="who-can-use-ome"></a>OME を使用できるユーザー

OME の新機能は、次の条件下で使用できます。
  
- Office 365 で OME または IRM を Exchange Online 用にセットアップしたことがない場合。

- OME と IRM をセットアップしている場合は、azure Information Protection から Azure Rights Management サービスを使用している場合は、次の手順を使用できます。

- Active Directory Rights Management サービス (AD RMS) を使用して Exchange Online を使用している場合、これらの新機能をすぐに有効にすることはできません。 代わりに、まず[AD RMS を Azure Information Protection に移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)する必要があります。 移行が完了したら、OME を正常にセットアップできます。

  Azure Information Protection に移行するのではなく、Exchange Online でオンプレミスの AD RMS を引き続き使用することを選択した場合、これらの新機能を使用することはできません。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>新しい OME 機能を使用するために必要なサブスクリプションは何ですか。

新しい OME 機能を使用するには、次のプランのいずれかが必要です。
  
- Office 365 メッセージの暗号化は、Office 365 Enterprise E3 および E5、Microsoft Enterprise E3 および E5、Microsoft 365 Business、Office 365 A1、A3、A5、および Office 365 Government G3 および G5 の一部として提供されます。 お客様は、Azure Information Protection によって提供される新しい保護機能を利用するために追加のライセンスを必要としません。

- また、次のプランに Azure Information Protection Plan 1 を追加して、新しい Office 365 メッセージの暗号化機能を受け取ることができます。 Exchange Online プラン1、Exchange Online プラン2、Office 365 F1、Office 365 Business Essentials、Office 365 Business Premium、またはOffice 365 Enterprise E1

- Office 365 の各ユーザー利点を活用するには、この機能の対象となるライセンスが必要です。

- 完全なリストについては、「 [Exchange Online サービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)」の「Office 365 Message Encryption」を参照してください。

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Exchange Online を Azure Information Protection に独自のキーを取り込むことができますか (BYOK)。

はい。 Microsoft では、OME を設定する前に、[ok] を設定する手順を完了することをお勧めします。
  
BYOK の詳細については、「 [Azure Information Protection のテナントキーを計画および実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)」を参照してください。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>「Azure Information Protection を使用して OME と BYOK を実行する」では、subpoenas などのサードパーティのデータ要求に対する Microsoft のアプローチを変更します。

いいえ。 OME と、Azure Information Protection からの独自の暗号化キーを提供および制御するオプションは、法的執行者 subpoenas に応答するようには設計されていませんでした。 Azure Information Protection の OME では、コンプライアンスを重視したお客様を対象として設計されています。 Microsoft は、お客様のデータに関するサードパーティの要求を非常に真剣に行います。 クラウドサービスプロバイダーとして、お客様のデータのプライバシーを常に支持しています。 召喚を受け取った場合は、常にお客様にサードパーティをリダイレクトして、情報を入手してください。 (官庁のブログ: 「[お客様のデータを政府から保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)する」を参照してください)。 受信する要求の詳細情報を定期的に公開しています。 サードパーティのデータ要求の詳細については、「Microsoft Trust Center で[顧客データにアクセスするための政府機関および司法執行機関への対応](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data)」を参照してください。 また、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx)の「顧客データの開示」を参照してください。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>この機能は、従来の Office 365 メッセージの暗号化 (OME) と Information Rights Management (IRM) の機能に関連しています。

Office 365 の新しいメッセージの暗号化機能は、既存の IRM および従来の OME ソリューションを進化させることができます。 以下の表に詳細を示します。
  
**従来の OME、IRM、および新しい OME 機能の比較**

|**機能**|**以前のバージョンの OME**|**IRM**|**OME の新機能**|
|:-----|:-----|:-----|:-----|
|**暗号化された電子メールの送信**|Exchange メールフロールールを使用した場合のみ|エンドユーザーが Outlook for PC、outlook for Mac、または Outlook on the web から開始しました。または Exchange メールフロールールを介して|エンドユーザーが Outlook for PC、outlook for Mac、または Outlook on the web から開始しました。またはメールフロールールによって|
|**権限管理**|-|オプションとカスタムテンプレートを転送しない|転送不可オプション、暗号化のみオプション、既定およびカスタムテンプレート|
|**サポートされている受信者の種類**|外部の受信者のみ|内部受信者のみ|内部および外部の受信者|
|**受信者の利便性**|外部の受信者がブラウザーまたはダウンロードしたモバイルアプリでダウンロードして開く HTML メッセージを受信しました。|内部の受信者は、Outlook for PC、outlook for Mac、および Outlook on the web で暗号化された電子メールのみを受信しました。|内部および外部の受信者は、Outlook for PC、Outlook for Mac、Outlook on the web、Outlook for Android、および iOS 用の outlook、または web ポータルで、同じ Office 365 組織または Office 365 のどちらにあるかに関係なく、電子メールを受信します。機関. OME ポータルには、個別にダウンロードする必要はありません。|
|**独自のキーサポートを提供する**|使用不可|使用不可| BYOK サポート|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>組織のために新しい OME 機能を有効にするにはどうすればよいですか?

「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>以前のバージョンの OME は廃止されますか。

OME の以前のバージョンを引き続き使用することはできますが、この時点では廃止されることはありません。 ただし、新しい改良された OME ソリューションを使用することを組織に強くお勧めします。 OME をまだ展開していないお客様は、OME の以前のバージョンの新しい展開をセットアップすることはできません。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>組織では Active Directory Rights Management を使用していますが、この機能を使用することはできますか?

いいえ。 Active Directory Rights Management サービス (AD RMS) を使用して Exchange Online を使用している場合、これらの新機能をすぐに有効にすることはできません。 代わりに、まず[AD RMS を Azure Information Protection に移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)する必要があります。 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>自分の組織では、Exchange ハイブリッド展開を行っています。 この機能を使用できますか。

オンプレミスのユーザーは、Exchange Online のメールフロールールを使用して、暗号化されたメールを送信できます。 そのためには、Exchange Online 経由で電子メールをルーティングする必要があります。 詳細については、「[パート 2: 電子メールサーバーから Office 365 にメールが流れるように構成する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)」を参照してください。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>OME 暗号化メッセージを作成するために、どのような電子メールクライアントを使用する必要がありますか。 保護されたメッセージの送信に対してサポートされているアプリケーション

保護されたメッセージは、Outlook 2016、outlook 2013 for PC および Mac、および Outlook on the web から作成できます。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>保護された電子メールの読み取りと応答をサポートする電子メールクライアント

Office 365 ユーザーの場合は、PC および Mac 用の Outlook (2013 と 2016)、Outlook on the web、および Outlook mobile (Android および iOS) の読み取りと応答が可能です。 組織で許可されている場合は、iOS ネイティブメールクライアントを使用することもできます。 Office 365 以外のユーザーの場合は、web ブラウザーを使用して、web 上で暗号化されたメッセージの読み取りと返信を行うことができます。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>保護された電子メールの添付ファイルとしてサポートされているファイルの種類は何ですか。 添付ファイルは、保護された電子メールに関連付けられている保護ポリシーを継承しますか?

保護されたメールには任意のファイルの種類を添付できますが、保護ポリシーは、[ここ](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)に記載されているファイル形式でのみ適用されます。
  
ファイル形式がサポートされている場合 (Word、Excel、PowerPoint ファイルなど)、受信者によって添付ファイルがダウンロードされた後も、ファイルは常に保護されます。 たとえば、添付ファイルが [転送不可] で保護され、元の受信者がその添付ファイルを新しい受信者にダウンロードして転送する場合、新しい受信者は保護されたファイルを開くことができません。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF ファイル添付はサポートされていますか?

はい。 Office 365 組織の PDF 添付ファイルの暗号化を有効にすることができます。 PDF 添付ファイルの暗号化を有効にするには、 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)で次のコマンドを実行します。

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

PDF 暗号化を使用すると、セキュリティで保護された通信やセキュリティで保護されたコラボレーションを通じて、機密の PDF ドキュメントを保護でき メッセージは、Exchange Online のデータ損失防止 (DLP) ポリシーまたはメールフロールールの OME 保護を継承します。 Outlook または web 上の Outlook ユーザーが保護されたメッセージに保護されていない PDF 添付ファイルを添付している場合、メッセージはメッセージの保護を継承します。 ユーザーが暗号化された添付ファイルを開くことができるのは、保護された Pdf をサポートするアプリケーション (OME ポータルや Azure Information Protection ビューアーなど) だけです。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>OneDrive for Business の添付ファイルはサポートされていますか?

Not yet. OneDrive for Business の添付ファイルはサポートされておらず、エンドユーザーは、クラウド OneDrive for Business の添付ファイルを含むメールを暗号化することはできません。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>ポリシーをセットアップすることで、メッセージを自動的に暗号化できますか?

はい。 Exchange Online でメールフロールールを使用して、特定の条件に基づいてメッセージを自動的に暗号化します。 たとえば、受信者 ID、受信者ドメイン、またはメッセージの本文または件名の内容に基づいたポリシーを作成できます。 「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義」を](define-mail-flow-rules-to-encrypt-email.md)参照してください。
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>受信および送信メールの暗号化を自動的に削除できますか?

管理者は、メールフロールールを設定して、送信メールの暗号化を削除することができます。 受信メールの暗号化を解除するルールを設定することはできません。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターを使用して、データ損失防止 (DLP) でポリシーを設定することによって、メッセージを自動的に暗号化できますか?

はい。 Exchange Online またはセキュリティ&amp; /コンプライアンスセンターで DLP を使用して、メールフロールールを設定できます。
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>共有メールボックスに送信された暗号化されたメッセージを開くことはできますか。

はい。 共有メールボックスで暗号化されたメッセージがサポートされています。

- 共有メールボックスで保護されたメールを配布グループの一部として受信した場合、ユーザーは共有メールボックスで保護されたメールを開くことができます。

- ユーザーが Outlook for Windows、outlook for Mac、および Outlook on the web を使用している場合は、電子メールから保護を継承する添付ファイルを表示できます。

## <a name="is-delegated-access-supported"></a>委任されたアクセスがサポートされていますか?

現時点ではできません。

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>企業ブランド化で暗号化されたメッセージをカスタマイズできますか。

はい。 電子メールメッセージと OME ポータルのカスタマイズの詳細については、「組織のブランドを暗号化されたメッセージに追加する」を参照してください。 「[組織のブランドを暗号化されたメッセージに追加する」を](add-your-organization-brand-to-encrypted-messages.md)参照してください。
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>暗号化された電子メールについては、レポート機能や分析情報はありますか。

セキュリティ/コンプライアンスセンターには、暗号化レポートがあります。 [セキュリティ & コンプライアンスセンターで電子メールセキュリティレポートを表示する](view-email-security-reports.md)を参照してください。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>電子情報開示などのコンプライアンス機能を使用してメッセージの暗号化を使用できますか?

はい。 すべての暗号化された電子メールメッセージは、Office 365 コンプライアンス機能によって検出できます。

## <a name="can-i-remove-encryption-from-email"></a>暗号化を電子メールから削除することはできますか?

管理者は、メールフロールールを設定して、送信メールから暗号化を削除することができます。 受信メッセージからメールフロールールを使用して暗号化を削除することはできません。
