---
title: 名前付きエンティティの SMTP DNS ベース認証 (DANE) が電子メール通信をセキュリティで保護する方法
f1.keywords:
- NOCSH
ms.author: v-mathavale
author: v-mathavale
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: メール サーバー間の電子メール通信をセキュリティで保護するために、SMTP DNS ベースの名前付きエンティティ認証 (DANE) がどのように機能しているかについて説明します。
ms.openlocfilehash: 596e1b04576edc025eda8b3486b42c5e7e0b29bc
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214296"
---
# <a name="how-smtp-dns-based-authentication-of-named-entities-dane-works"></a>名前付きエンティティの SMTP DNS ベース認証 (DANE) のしくみ

SMTP プロトコルは、メール サーバー間でメッセージを転送するために使用される主なプロトコルであり、既定ではセキュリティで保護されません。 トランスポート層セキュリティ (TLS) プロトコルは、SMTP を使用したメッセージの暗号化された送信をサポートするために数年前に導入されました。 通常、要件としてではなく日和見的に使用されます。多くの電子メール トラフィックはクリア テキストに残り、悪いアクターによる傍受に対して脆弱です。 さらに、SMTP は、パブリック DNS インフラストラクチャを介して宛先サーバーの IP アドレスを決定します。これはスプーフィングや MITM (Man-in-the-Middle) 攻撃の影響を受けやすいです。 これにより、電子メールの送受信のセキュリティを強化するために多くの新しい標準が作成されました。そのうちの 1 つは DNS ベースの名前付きエンティティ認証 (DANE) です。
  
DANE for [SMTP RFC 7672](https://tools.ietf.org/html/rfc7672) は、ドメインの DNS レコード セットにトランスポート層セキュリティ認証 (TLSA) レコードが存在してドメインを通知し、そのメール サーバーが DANE をサポートします。 TLSA レコードが存在しない場合、メール フローの DNS 解決は、DANE チェックが試行されることなく通常どおり機能します。 TLSA レコードは、TLS のサポートを安全に示し、ドメインの DANE ポリシーを発行します。 したがって、メール サーバーを送信すると、SMTP DANE を使用して正当な受信メール サーバーを正常に認証できます。 これにより、ダウングレードや MITM 攻撃に対する耐性が高い。 DANE は DNSSEC に直接依存します。これは、公開キー暗号化を使用して DNS 参照のレコードにデジタル署名することで機能します。 DNSSEC チェックは、クライアントの DNS クエリを行う DNS サーバーである再帰的 DNS リゾルバーで行われます。 DNSSEC を使用すると、DNS レコードが改ざんされ、本物である必要があります。  

ドメインの MX、A/AAAA、DNSSEC 関連のリソース レコードが DNSSEC の認証済みとして DNS 再帰的リゾルバーに返された後、送信側メール サーバーは MX ホスト エントリまたはエントリに対応する TLSA レコードを要求します。 別の DNSSEC チェックを使用して TLSA レコードが存在し、本物であることが証明された場合、DNS 再帰的リゾルバーは TLSA レコードを送信側メール サーバーに返します。 

本物の TLSA レコードを受信した後、送信側メール サーバーは、本物の TLSA レコードに関連付けられた MX ホストへの SMTP 接続を確立します。 送信側メール サーバーは、TLS をセットアップし、サーバーの TLS 証明書と TLSA レコード内のデータを比較して、送信者に接続されている宛先メール サーバーが正当な受信メール サーバーであると検証します。 認証が成功した場合、メッセージは (TLS を使用して) 送信されます。 認証が失敗した場合、または宛先サーバーで TLS がサポートされていない場合、Exchange Online は、同じ宛先ドメインの DNS クエリで始まる検証プロセス全体を 15 分後に再試行し、その後 15 分後に、次の 24 時間は 1 時間ごとに再試行します。 24 時間の再試行後も認証が失敗し続ける場合、メッセージは期限切れになります。エラーの詳細を含む NDR が生成され、送信者に送信されます。 

## <a name="what-are-the-components-of-dane"></a>DANE のコンポーネントは何ですか?

### <a name="tlsa-resource-record"></a>TLSA リソース レコード

TLS 認証 (TLSA) レコードは、サーバーの X.509 証明書または公開キー値を、レコードを含むドメイン名に関連付ける場合に使用します。 TLSA レコードは、ドメインで DNSSEC が有効になっている場合にのみ信頼できます。 DNS プロバイダーを使用してドメインをホストしている場合は、ドメインを構成するときに提供される設定である可能性があります。 DNSSEC ゾーン署名の詳細については、「DNSSEC ゾーン署名の概要」を [参照|Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11)). 
  
TLSA レコードの例:
  
:::image type="content" source="../media/compliance-trial/example-TLSA-record.png" alt-text="TLSA レコードの例" lightbox="../media/compliance-trial/example-TLSA-record.png":::

TLSA レコードの種類に固有の 4 つの構成可能なフィールドがあります。 

**[証明書の使用状況]** フィールド: 送信側の電子メール サーバーが送信先の電子メール サーバーの証明書を確認する方法を指定します。

|値  |略語  |説明 |
|---------|---------|---------|
|0<sup>1</sup>     |PKIX-TA          |使用される証明書は、X.509 信頼チェーンからの信頼アンカーパブリック CA です。          |
|1<sup>1</sup>     |PKIX-Enterprise Edition         |チェックされた証明書は宛先サーバーです。DNSSEC チェックでは、その信頼性を確認する必要があります。          |
|2     |DANE-TA         |信頼チェーン内の信頼アンカーによって検証する必要がある X.509 ツリーのサーバーのプライベート キーを使用します。 TLSA レコードは、ドメインの TLS 証明書の検証に使用する信頼アンカーを指定します。         |
|3     |DANE-Enterprise Edition         |コピー先サーバーの証明書と一致する場合のみ。           |

<sup>1</sup>Exchange Online RFC 実装ガイダンスに従って、DANE が SMTP で実装されている場合、証明書使用法フィールドの値 0 または 1 を使用してはならない。   証明書使用法フィールドの値が 0 または 1 の TLSA レコードが Exchange Online に返Exchange Online、使用できないと処理されます。 すべての TLSA レコードが使用できないとExchange Onlineは、電子メールの送信時に 0 または 1 の DANE 検証手順を実行しません。 代わりに、TLSA レコードが存在する場合、Exchange Online は TLS を使用して電子メールを送信し、宛先電子メール サーバーが TLS をサポートしている場合は電子メールを送信するか、メールをドロップし、宛先電子メール サーバーが TLS をサポートしない場合は NDR を生成します。     

TLSA レコードの例では、証明書使用法フィールドが '3' に設定されているので、証明書の関連付けデータ ('abc123...xyz789') は、宛先サーバーの証明書にのみ一致します。

**セレクター フィールド**: 宛先サーバーの証明書をチェックする必要がある部分を示します。 

|値  |略語  |説明  |
|---------|---------|---------|
|0     |Cert         |完全な証明書を使用します。         |
|1     |SPKI (サブジェクト公開キー情報)          |証明書の公開キーと、使用する公開キーを識別するアルゴリズムを使用します。          |

TLSA レコードの例では、セレクター フィールドが '1' に設定され、証明書関連付けデータは、宛先サーバー証明書の公開キーと、使用する公開キーが識別されるアルゴリズムを使用して一致します。

**一致する型** フィールド : 証明書が TLSA レコードで表される形式を示します。 

|値  |略語  |説明  |
|---------|---------|---------|
|0     |Full         |TSLA レコードのデータは、完全な証明書または SPKI です。          |
|1     |SHA-256         |TSLA レコードのデータは、証明書または SPKI の SHA-256 ハッシュです。          |
|2     |SHA-512         |TSLA レコードのデータは、証明書または SPKI の SHA-512 ハッシュです。         |

TLSA レコードの例では、照合の種類フィールドが '1' に設定されているので、証明書の関連付けデータは、宛先サーバー証明書のサブジェクト公開キー情報の SHA-256 ハッシュです。

**証明書の関連付** けデータ: 宛先サーバー証明書との照合に使用する証明書データを指定します。 このデータは、セレクター フィールドの値と一致する型の値によって異なります。

TLSA レコードの例では、証明書の関連付けデータは 'abc123... に設定されます。xyz789'。 この例のセレクター フィールドの値は '1' に設定されています。この値は、宛先サーバー証明書の公開キーと、使用するアルゴリズムを参照します。 また、例の [一致する種類] フィールドの値は '1' に設定されているので、宛先サーバー証明書からサブジェクト公開キー情報の SHA-256 ハッシュを参照します。

## <a name="how-can-exchange-online-customers-use-smtp-dane-outbound"></a>ユーザーがExchange Online SMTP DANE 送信を使用する方法

お客様Exchange Online、この拡張メール セキュリティを送信メール用に構成するために必要な操作はありません。 これは、すべてのユーザーに対して既定でオンExchange Online、宛先ドメインが DANE のサポートをアドバタイズするときに使用されます。 DNSSEC と DANE チェックを使用して電子メールを送信する利点を得るには、DNSSEC と DANE を実装するために必要な電子メールを交換するビジネス パートナーと通信して、これらの標準を使用して電子メールを受信できます。 

## <a name="how-can-exchange-online-customers-use-smtp-dane-inbound"></a>SMTP DANE Exchange Onlineを使用する方法

現在、受信 SMTP DANE は、受信 SMTP DANE がサポートExchange Online。 サポートは 2022 年末にリリースされる予定です。 

## <a name="what-is-the-recommended-tlsa-record-configuration"></a>推奨される TLSA レコード構成は何ですか?

SMTP DANE の RFC 実装ガイダンスでは、証明書の使用法フィールドが 3 に設定され、セレクター フィールドが 1 に設定され、照合の種類フィールドが 1 に設定された TLSA レコードが推奨されます。 

## <a name="exchange-online-mail-flow-with-smtp-dane"></a>Exchange Online SMTP DANE Flowメール アドレス 

以下のフローチャートに示す SMTP DANE を使用した Exchange Online のメール フロー プロセスでは、DNSSEC によるドメインとリソース レコードのセキュリティ、宛先メール サーバーでの TLS サポート、および宛先メール サーバーの証明書が、関連付けられた TLSA レコードに基づいて予想される値と一致します。 

SMTP DANE エラーによって電子メールがブロックされるシナリオは 2 つのみです。

- 宛先ドメインは DNSSEC のサポートを示しましたが、1 つ以上のレコードが認証されていないとして返されました。 

- 宛先ドメインのすべての MX レコードには TLSA レコードが含まれており、宛先サーバーの証明書のいずれも TSLA レコード データごとに予想された値と一致しないか、宛先サーバーで TLS 接続がサポートされていません。

:::image type="content" source="../media/compliance-trial/mail-flow-smtp-dane.png" alt-text="Exchange SMTP DANE を使用したオンライン メール フローの作成" lightbox="../media/compliance-trial/mail-flow-smtp-dane.png":::

## <a name="related-technologies"></a>関連技術 

|テクノロジ  |その他の情報  |
|---------|---------|
|メール転送エージェント – 厳密なトランスポート セキュリティ **(MTA-STS)** は、宛先メール サーバーが TLS をサポートするかどうかを指定するドメイン ポリシーを設定するメカニズムを提供し、TLS をネゴシエートできない場合の操作 (送信の停止など) を行う方法を提供することで、ダウングレードと中間者攻撃を阻止するのに役立ちます。     |受信および送信Exchange Online MTA-STS の今後のサポートの詳細については、今年後半に公開されます。     [Exchange Online Microsoft Ignite 2020 からのトランスポート ニュース - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)<br /><br />[rfc8461 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc8461) |
|**Sender Policy Framework (SPF) は** IP 情報を使用して、宛先メール システムがカスタム ドメインから送信されたメッセージを信頼します。    |   [送信者ポリシー フレームワーク (SPF) がスプーフィングを防止する方法 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)      |
|**DomainKeys Identified Mail (DKIM)** は、X.509 証明書情報を使用して、宛先メール システムがカスタム ドメインから送信されたメッセージを信頼します。      | [カスタム ドメインのメールに DKIM を使用する方法 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)        |
|ドメイン ベースのメッセージ認証、レポート、および準拠 **(DMARC)** は、Sender Policy Framework および DomainKeys Identified Mail と組み合わせ、メール送信者を認証し、宛先電子メール システムがドメインから送信されたメッセージを信頼します。      |  [DMARC を使用して電子メール、セットアップ手順を検証する - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)       |

## <a name="troubleshooting-sending-emails-with-smtp-dane"></a>SMTP DANE を使用した電子メールの送信のトラブルシューティング

現在、DANE でメールを送信するときにエラー コードが 4 つExchange Online。 Microsoft は、このエラー コード 一覧を積極的に更新しています。 エラーは次の場所に表示されます。
1.  [Exchangeトレースの詳細] ビューを通じて管理センター ポータルを開きます。
2.  DANE または DNSSEC の障害のためにメッセージが送信されていない場合に生成されるNDRs。
3.  リモート接続アナライザー ツール [Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365).

|NDR コード  |説明  |
|---------|---------|
|5.7.321     |starttls-not-supported: 宛先メール サーバーは、メールを受信するために TLS をサポートする必要があります。          |
|5.7.322     |certificate-expired: 宛先メール サーバーの証明書の有効期限が切れています。          |
|5.7.323     |tlsa-invalid: ドメインが DANE 検証に失敗しました。          |
|5.7.324     |dnssec-invalid: 宛先ドメインが無効な DNSSEC レコードを返しました。         |

### <a name="troubleshooting-57321-starttls-not-supported"></a>5.7.321 starttls-not-supported のトラブルシューティング

これは通常、宛先メール サーバーに関する問題を示します。 メッセージを受信した後:
1.  宛先の電子メール アドレスが正しく入力されていることを確認します。
2.  宛先サーバーが TLS を使用してメッセージを受信するように正しく構成されているかどうかを判断できるよう、このエラー コードを受信した電子メール管理者に通知します。 
3.  電子メールの送信を再試行し、管理センター ポータルでメッセージのメッセージ追跡Exchange確認します。

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 証明書の有効期限切れのトラブルシューティング

有効期限が切れていない有効な X.509 証明書を送信側の電子メール サーバーに提示する必要があります。 X.509 証明書は、有効期限が切れた場合は更新する必要があり、一般的には毎年更新する必要があります。 メッセージを受信した後:

1.  このエラー コードを受信した電子メール管理者に警告し、エラー コード文字列を指定します。
2.  宛先サーバー証明書を更新し、TLSA レコードを更新して新しい証明書を参照する時間を許可します。 次に、電子メールの送信を再試行し、管理者センター ポータルでメッセージのメッセージ追跡Exchange確認します。

### <a name="troubleshooting-57323-tlsa-invalid"></a>5.7.323 tlsa-invalid のトラブルシューティング

このエラー コードは TLSA レコードの構成ミスに関連し、DNSSEC-Authentic TLSA レコードが返された後にのみ生成できます。 DANE 検証中には、レコードが返された後に発生するシナリオが多く、コードが生成される可能性があります。 Microsoft は、このエラー コードでカバーされるシナリオに積極的に取り組み、各シナリオに特定のコードが含まれています。 現在、次の 1 つ以上のシナリオでエラー コードが生成される可能性があります。

1.  宛先メール サーバーの証明書は、本物の TLSA レコードごとに予想される証明書と一致しません。
2.  本物の TLSA レコードが正しく構成されていない。
3.  宛先ドメインが攻撃されている。
4.  その他の DANE エラー。

メッセージを受信した後:

1. このエラー コードを受信した電子メール管理者に通知し、エラー コード文字列を指定します。
2. 宛先メール管理者が DANE 構成と電子メール サーバー証明書の有効性を確認する時間を許可します。 次に、電子メールの送信を再試行し、管理者センター ポータルでメッセージのメッセージ追跡Exchange確認します。

### <a name="troubleshooting-57324-dnssec-invalid"></a>5.7.324 dnssec-invalid のトラブルシューティング

このエラー コードは、宛先ドメインが DNSSEC-authentic を示したが、DNSSEC-authentic としてExchange Online確認できない場合に生成されます。 

メッセージを受信した後:

1. このエラー コードを受信した電子メール管理者に通知し、エラー コード文字列を指定します。
2. 宛先メール管理者がドメインの DNSSEC 構成を確認する時間を許可します。 次に、電子メールの送信を再試行し、管理者センター ポータルでメッセージのメッセージ追跡Exchange確認します。

## <a name="troubleshooting-receiving-emails-with-smtp-dane"></a>SMTP DANE を使用したメールの受信のトラブルシューティング

現在、受信ドメインの管理者は、DNSSEC および DANE 構成を検証およびトラブルシューティングして、これらの標準を使用してドメインから電子メールを受信Exchange Online 2 つの方法があります。 

1. [RFC8460](https://datatracker.ietf.org/doc/html/rfc8460)で導入された SMTP TLS-RPT (トランスポート層セキュリティ レポート) を採用する 
2. リモート接続アナライザー ツールを使用 [する Microsoft リモート接続アナライザー](https://testconnectivity.microsoft.com/tests/o365)

TLS-RPT は、送信者がそれぞれの宛先ドメインで DANE および MTA-STS の成功と失敗に関する詳細を宛先ドメイン管理者に提供するためのレポートメカニズム [https://datatracker.ietf.org/doc/html/rfc8460](https://datatracker.ietf.org/doc/html/rfc8460) です。 TLS-RPT レポートを受信するには、レポートの送信先の電子メール アドレスまたは URI を含む TXT レコードをドメインの DNS レコードに追加する必要があります。 Exchange Onlineは JSON 形式で TLS-RPT レポートを送信します。 

レコードの例:

:::image type="content" source="../media/compliance-trial/example-record.png" alt-text="レコードの例" lightbox="../media/compliance-trial/example-record.png":::

2 つ目の方法は、リモート接続アナライザー [Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365)を使用する方法です。これは、サービス外で電子メールを送信するときに Exchange Online が実行する DNS 構成と同じ DNSSEC と DANE チェックを実行できます。 これは、構成内のエラーをトラブルシューティングする最も直接的な方法で、これらの標準を使用Exchange Onlineメールを受信します。 

トラブルシューティングを行う場合、次のエラー コードが生成される場合があります。

|NDR コード  |説明 |
|---------|---------|
|4/5.7.321     |starttls-not-supported: 宛先メール サーバーは、メールを受信するために TLS をサポートする必要があります。          |
|4/5.7.322     |certificate-expired: 宛先メール サーバーの証明書の有効期限が切れています。          |
|4/5.7.323    |tlsa-invalid: ドメインが DANE 検証に失敗しました。         |
|4/5.7.324     |dnssec-invalid: 宛先ドメインが無効な DNSSEC レコードを返しました。         |

### <a name="troubleshooting-57321-starttls-not-supported"></a>5.7.321 starttls-not-supported のトラブルシューティング

> [!NOTE]
> 次の手順は、SMTP DANE を使用してメールを受信する電子メールをトラブルシューティングするExchange Online手順です。

これは通常、宛先メール サーバーに関する問題を示します。 リモート接続アナライザーが接続をテストしているメール サーバー。 通常、このコードを生成するシナリオは 2 つです。 

1.  宛先メール サーバーはセキュリティで保護された通信を全くサポートしません。暗号化されていないプレーンな通信を使用する必要があります。 
2.  宛先サーバーが不適切に構成され、STARTTLS コマンドは無視されます。
    
メッセージを受信した後:

1. メール アドレスを確認します。
2. エラー ステートメントに関連付けられている IP アドレスを見つけて、ステートメントが関連付けられているメール サーバーを識別できます。
3. メール サーバーの設定を確認して、SMTP トラフィック (一般にポート 25 と 587) をリッスンするように構成されていることを確認します。
4. 数分待って、リモート接続アナライザー ツールでテストを再試行します。
5. それでも失敗した場合は、TLSA レコードを削除し、もう一度リモート接続アナライザー ツールを使用してテストを実行します。
6. エラーがない場合は、メールの受信に使用しているメール サーバーが STARTTLS をサポートしていない場合、DANE を使用するためにアップグレードが必要な場合があります。 

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 証明書の有効期限切れのトラブルシューティング

> [!NOTE]
> 次の手順は、SMTP DANE を使用してメールを受信する電子メールをトラブルシューティングするExchange Online手順です。

有効期限が切れていない有効な X.509 証明書を送信側の電子メール サーバーに提示する必要があります。 X.509 証明書は、有効期限が切れた場合は更新する必要があり、一般的には毎年更新する必要があります。 メッセージを受信した後:

1. エラー ステートメントに関連付けられている IP を確認して、関連付けられているメール サーバーを識別できます。 指定した電子メール サーバーで有効期限が切れた証明書を見つける。
2. 証明書プロバイダーの Web サイトにログインします。
3. 有効期限が切れた証明書を選択し、指示に従って更新と更新の支払いを行います。
4. プロバイダーが購入を確認した後、新しい証明書をダウンロードできます。
5. 更新された証明書を関連付けられたメール サーバーにインストールします。
6. メール サーバーに関連付けられた TLSA レコードを新しい証明書のデータで更新します。 
7. 適切な時間を待った後、リモート接続アナライザー ツールを使用してテストを再試行します。

### <a name="troubleshooting-57323-tlsa-invalid"></a>5.7.323 tlsa-invalid のトラブルシューティング

> [!NOTE]
> 次の手順は、SMTP DANE を使用してメールを受信する電子メールをトラブルシューティングするExchange Online手順です。

このエラー コードは TLSA レコードの構成ミスに関連し、DNSSEC-Authentic TSLA レコードが返された後にのみ生成できます。 ただし、DANE 検証中には、レコードが返された後に発生するシナリオが多く、コードが生成される可能性があります。 Microsoft は、このエラー コードでカバーされるシナリオに積極的に取り組み、各シナリオに特定のコードが含まれています。 現在、次の 1 つ以上のシナリオでエラー コードが生成される可能性があります。

1. 本物の TLSA レコードが正しく構成されていない。
2. 証明書がまだ時間有効/将来のタイム ウィンドウ用に構成されていません。 
3. 宛先ドメインが攻撃されている。
4. その他の DANE エラー。

メッセージを受信した後:

1. エラー ステートメントに関連付けられている IP を確認して、関連付けられているメール サーバーを識別します。 
2. 識別されたメール サーバーに関連付けられている TLSA レコードを識別します。 
3. TLSA レコードの構成を確認して、送信者に優先 DANE チェックの実行を通知し、正しい証明書データが TLSA レコードに含まれているか確認します。 
    1. 不一致のためにレコードを更新する必要がある場合は、数分待ち、リモート接続アナライザー ツールを使用してテストを再実行します。 
4. 識別されたメール サーバー上の証明書を見つける。
5. 証明書が有効なタイム ウィンドウを確認します。 将来の日付で有効期間を開始する場合は、現在の日付に対して更新する必要があります。
    1. 証明書プロバイダーの Web サイトにログインします。
    2. 有効期限が切れた証明書を選択し、指示に従って更新と更新の支払いを行います。
    3. プロバイダーが購入を確認した後、新しい証明書をダウンロードできます。
    4. 更新された証明書を関連付けられたメール サーバーにインストールします。

### <a name="troubleshooting-57324-dnssec-invalid"></a>5.7.324 dnssec-invalid のトラブルシューティング

> [!NOTE]
> 次の手順は、SMTP DANE を使用してメールを受信する電子メールをトラブルシューティングするExchange Online手順です。

このエラー コードは、宛先ドメインが DNSSEC-authentic を示したが、DNSSEC-authentic としてExchange Online確認できない場合に生成されます。 このセクションでは、DNSSEC の問題のトラブルシューティングについては包括的ではなく、ドメインが以前に DNSSEC 認証に合格したが、現在は渡されていないシナリオに焦点を当てました。 

メッセージを受信した後:

1. GoDaddy など、DNS プロバイダーを使用している場合は、DNS プロバイダーにエラーを通知して、トラブルシューティングと構成の変更に取り組む必要があります。 
2. 独自の DNSSEC インフラストラクチャを管理している場合は、このエラー メッセージを生成する DNSSEC の構成ミスが多数ある可能性があります。 ゾーンが以前に DNSSEC 認証に合格した場合にチェックする一般的な問題を次に示します。
    1. 壊れた信頼チェーン(親ゾーンが子領域に存在しないものを指す一連の DS レコードを保持している場合)。 これにより、リゾルバーを検証することで、子領域が偽としてマークされます。 
        - 子ドメイン RRSIG キーの ID を確認し、親ゾーンで発行された DS レコード内のキーの ID と一致を確認して解決します。 
    2. ドメインの RRSIG リソース レコードが時間有効でないか、有効期限が切れているか、有効期間が開始されていません。 
        - 有効なタイムスパンを使用してドメインの新しい署名を生成して解決します。 

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="as-an-exchange-online-customer-can-i-opt-out-of-using-dnssec-andor-dane"></a>お客様Exchange Online DNSSEC または DANE の使用をオプトアウトできますか?

DNSSEC と DANE は、サービスのセキュリティの位置を大幅に高め、すべてのお客様に利益をもたらすと強く信じています。 M365 のお客様に対してこの展開が与える潜在的な影響のリスクと重大度を軽減するために、過去 1 年間、厳しく取り組み続け、 展開の展開を積極的に監視および追跡し、展開の展開に対する悪影響を最小限に抑えます。この理由から、テナント レベルの例外またはオプトアウトは使用できません。
DNSSEC および/または DANE の有効化に関連する問題が発生した場合、このドキュメントに記載されている障害を調査するためのさまざまな方法は、エラーの原因を特定するのに役立ちます。 ほとんどの場合、問題は外部の宛先当事者に対して発生します。これらのビジネス パートナーは、これらの標準を使用して Exchange Online から電子メールを受信するために DNSSEC と DANE を正しく構成する必要があるという通信を行う必要があります。

### <a name="how-does-dnssec-relate-to-dane"></a>DNSSEC と DANE の関係

DNSSEC は、パブリック キー インフラストラクチャを活用して DNS クエリに応答して返されるレコードが本物であるのを確認することで、DNS 解決に信頼の層を追加します。 DANE は、受信メール サーバーが正規の MX レコードの正当で予期されるメール サーバーである必要があります。 

### <a name="what-is-the-difference-between-mta-sts-and-dane-for-smtp"></a>MTA-STS と DANE for SMTP の違いは何ですか?

DANE と MTA-STS は同じ目的を果たしますが、DANE は DNS 認証に DNSSEC を必要としますが、MTA-STS は認証局に依存しています。 

### <a name="why-isnt-opportunistic-tls-sufficient"></a>Opportunistic TLS で十分ではない理由

両方がサポートすることに同意した場合、2 つのエンドポイント間の通信が暗号化されます。 ただし、TLS が送信を暗号化した場合でも、DNS 解決中にドメインがスプーフィングされ、ドメインの実際のエンドポイントではなく悪意のあるアクターのエンドポイントをポイントする可能性があります。 これは、MTA-STS および/または SMTP DANE を DNSSEC で実装することで対処される電子メール セキュリティのギャップです。  

### <a name="why-isnt-dnssec-sufficient"></a>DNSSEC が十分でない理由

DNSSEC は、メール フロー シナリオに対する Man-in-the-Middle 攻撃およびダウングレード (TLS からクリア テキスト) 攻撃に対して完全に耐性を持つではありません。 MTA-STS と DANE を DNSSEC と共に追加すると、MITM 攻撃とダウングレード攻撃の両方を阻止する包括的なセキュリティ方法が提供されます。

## <a name="additional-links"></a>その他のリンク 

[ドメインまたは DNS レコードを追加後に問題を特定して解決する](/microsoft-365/admin/get-help-with-domains/find-and-fix-issues)

[DNSSEC の概要|Microsoft Docs ](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))

[DMARC を使用して電子メール、セットアップ手順を検証する - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

[カスタム ドメインでメールに DKIM を使用する方法 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)

[送信者ポリシー フレームワーク (SPF) がスプーフィングを防止する方法 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)

[Exchange Online Microsoft Ignite 2020 からのトランスポート ニュース - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)

[rfc8461 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc8461)