---
title: 電子メール通信をセキュリティで保護するために SMTP DNS ベースの名前付きエンティティの認証 (DANE) のしくみ
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
description: SMTP DNS ベースの名前付きエンティティの認証 (DANE) が、メール サーバー間の電子メール通信をセキュリティで保護するためにどのように機能するかを説明します。
ms.openlocfilehash: b5f9337457556dda53b5b2f982480a4c2501fcc9
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782855"
---
# <a name="how-smtp-dns-based-authentication-of-named-entities-dane-works"></a>名前付きエンティティの SMTP DNS ベースの認証 (DANE) のしくみ

SMTP プロトコルは、メール サーバー間でメッセージを転送するために使用されるメイン プロトコルであり、既定ではセキュリティで保護されていません。 トランスポート層セキュリティ (TLS) プロトコルは、SMTP 経由でのメッセージの暗号化された送信をサポートするために数年前に導入されました。 これは一般的に要件としてではなく日和見的に使用され、多くの電子メール トラフィックをクリア テキストに残し、悪意のあるアクターによる傍受に対して脆弱です。 さらに、SMTP は、スプーフィングや中間者攻撃 (MITM) の影響を受けやすいパブリック DNS インフラストラクチャを介して宛先サーバーの IP アドレスを決定します。 これにより、電子メールの送受信のセキュリティを高めるために多くの新しい標準が作成されました。そのうちの 1 つは、DNS ベースの名前付きエンティティの認証 (DANE) です。

DANE for SMTP [RFC 7672](https://tools.ietf.org/html/rfc7672) では、ドメインの DNS レコード セットにトランスポート層セキュリティ認証 (TLSA) レコードが存在することを使用して、ドメインとそのメール サーバーが DANE をサポートすることを通知します。 TLSA レコードが存在しない場合、メール フローの DNS 解決は通常どおりに機能し、DANE チェックは試行されません。 TLSA レコードは、TLS のサポートを安全に通知し、ドメインの DANE ポリシーを発行します。 そのため、メール サーバーを送信すると、SMTP DANE を使用して正当な受信メール サーバーを正常に認証できます。 これにより、ダウングレードと MITM 攻撃に対する耐性が高くなります。 DANE は DNSSEC に直接依存しています。これは、公開キー暗号化を使用して DNS 参照のレコードにデジタル署名することで機能します。 DNSSEC チェックは、クライアントの DNS クエリを行う DNS サーバーである再帰 DNS リゾルバーで行われます。 DNSSEC を使用すると、DNS レコードが改ざんされず、信頼性が高いことが保証されます。

ドメインの MX、A/AAAA、DNSSEC 関連のリソース レコードが DNSSEC の信頼性として DNS 再帰リゾルバーに返されると、送信メール サーバーは、MX ホストエントリまたはエントリに対応する TLSA レコードを要求します。 TLSA レコードが存在し、別の DNSSEC チェックを使用して信頼性が証明されている場合、DNS 再帰リゾルバーは TLSA レコードを送信側のメール サーバーに返します。

本格的な TLSA レコードを受信すると、送信メール サーバーは、本物の TLSA レコードに関連付けられた MX ホストへの SMTP 接続を確立します。 送信側メール サーバーは TLS を設定し、サーバーの TLS 証明書を TLSA レコードのデータと比較して、送信者に接続されている宛先メール サーバーが正当な受信メール サーバーであることを検証します。 認証に成功すると、メッセージは (TLS を使用して) 送信されます。 認証が失敗した場合、または移行先サーバーで TLS がサポートされていない場合、Exchange Onlineは、15 分後、その後 15 分後、次の 24 時間ごとに、同じ宛先ドメインの DNS クエリで始まる検証プロセス全体を再試行します。 再試行の 24 時間後に認証が失敗し続けた場合、メッセージは期限切れになり、エラーの詳細を含む NDR が生成され、送信者に送信されます。

## <a name="what-are-the-components-of-dane"></a>DANE のコンポーネントは何ですか?

### <a name="tlsa-resource-record"></a>TLSA リソース レコード

TLS 認証 (TLSA) レコードは、サーバーの X.509 証明書または公開キー値をレコードを含むドメイン名に関連付けるために使用されます。 TLSA レコードは、ドメインで DNSSEC が有効になっている場合にのみ信頼できます。 DNS プロバイダーを使用してドメインをホストしている場合は、ドメインを構成するときに提供される設定である可能性があります。 DNSSEC ゾーン署名の詳細については、次のリンクを参照[してください:DNSSEC |の概要Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))。

TLSA レコードの例:

:::image type="content" source="../media/compliance-trial/example-TLSA-record.png" alt-text="TLSA レコードの例" lightbox="../media/compliance-trial/example-TLSA-record.png":::

TLSA レコードの種類に固有の 4 つの構成可能なフィールドがあります。

**[証明書の使用状況] フィールド**: 送信先の電子メール サーバーが宛先の電子メール サーバーの証明書を確認する方法を指定します。

|値|略語|説明|
|---|---|---|
|01<sup></sup>|PKIX-TA|使用される証明書は、X.509 トラスト チェーンからの信頼アンカーパブリック CA です。|
|11<sup></sup>|PKIX-Enterprise Edition|確認された証明書は宛先サーバーです。DNSSEC チェックでは、その信頼性を確認する必要があります。|
|2|DANE-TA|信頼チェーンの信頼アンカーによって検証する必要がある X.509 ツリーのサーバーの秘密キーを使用します。 TLSA レコードは、ドメインの TLS 証明書の検証に使用する信頼アンカーを指定します。|
|3|DANE-Enterprise Edition|移行先サーバーの証明書に対してのみ一致します。|

<sup>1</sup> Exchange Onlineは、RFC 実装ガイダンスに従います。0 または 1 の証明書使用フィールド値は、DANE を SMTP で実装する場合は使用しないでください。 証明書使用法フィールドの値が 0 または 1 の TLSA レコードがExchange Onlineに返されると、Exchange Onlineはそれを使用できないものとして扱います。 すべての TLSA レコードが使用できないと見なされた場合、Exchange Online電子メールの送信時に 0 または 1 の DANE 検証手順は実行されません。 代わりに、TLSA レコードが存在するため、Exchange Onlineは、電子メールを送信するための TLS の使用を強制し、宛先電子メール サーバーが TLS をサポートしている場合は電子メールを送信するか、宛先電子メール サーバーが TLS をサポートしていない場合は NDR を生成します。

TLSA レコードの例では、証明書使用法フィールドが '3' に設定されているため、証明書の関連付けデータ ('abc123...xyz789'') は、宛先サーバーの証明書とのみ照合されます。

**セレクター フィールド**: 宛先サーバーの証明書のどの部分を確認する必要があるかどうかを示します。

|値|略語|説明|
|---|---|---|
|0|証明 書|完全な証明書を使用します。|
|1|SPKI (サブジェクト公開キー情報)|証明書の公開キーと、使用する公開キーが識別されるアルゴリズムを使用します。|

TLSA レコードの例では、セレクター フィールドが '1' に設定されているため、証明書の関連付けデータは、宛先サーバー証明書の公開キーと、使用する公開キーが識別されるアルゴリズムを使用して照合されます。

**照合型フィールド**: TLSA レコードで証明書が表される形式を示します。

|値|略語|説明|
|---|---|---|
|0|Full|TSLA レコードのデータは、完全な証明書または SPKI です。|
|1|SHA-256|TSLA レコードのデータは、証明書または SPKI の SHA-256 ハッシュです。|
|2|SHA-512|TSLA レコードのデータは、証明書または SPKI の SHA-512 ハッシュです。|

TLSA レコードの例では、照合の種類フィールドが '1' に設定されているため、証明書の関連付けデータは宛先サーバー証明書のサブジェクト公開キー情報の SHA-256 ハッシュです。

**証明書の関連付けデータ**: 変換先サーバー証明書との照合に使用する証明書データを指定します。 このデータは、セレクター フィールドの値と一致する型の値によって異なります。

TLSA レコードの例では、証明書アソシエーション データは 'abc123.xyz789'. この例のセレクター フィールドの値は '1' に設定されているため、宛先サーバー証明書の公開キーとそれに使用されるアルゴリズムが参照されます。 また、この例の [照合の種類] フィールドの値は "1" に設定されているため、ターゲット サーバー証明書からサブジェクト公開キー情報の SHA-256 ハッシュを参照します。

## <a name="how-can-exchange-online-customers-use-smtp-dane-outbound"></a>お客様Exchange Online SMTP DANE 送信を使用する方法

Exchange Online顧客として、送信メールに対してこの強化された電子メール セキュリティを構成するために必要な操作はありません。 これは、お客様のために構築したものです。既定では、すべてのExchange Online顧客に対してオンになっており、宛先ドメインが DANE のサポートをアドバタイズするときに使用されます。 DNSSEC と DANE チェックを使用して電子メールを送信する利点を享受するには、DNSSEC と DANE を実装する必要がある電子メールを交換するビジネス パートナーに連絡して、これらの標準を使用して電子メールを受信できるようにします。

## <a name="how-can-exchange-online-customers-use-smtp-dane-inbound"></a>お客様Exchange Online SMTP DANE 受信を使用する方法

現在、受信 SMTP DANE はExchange Onlineではサポートされていません。 サポートは 2022 年末にリリースされる予定です。

## <a name="what-is-the-recommended-tlsa-record-configuration"></a>推奨される TLSA レコード構成は何ですか?

SMTP DANE の RFC 実装ガイダンスに従って、証明書使用法フィールドで構成される TLSA レコードを 3 に設定し、セレクター フィールドを 1 に設定し、照合の種類フィールドを 1 に設定することをお勧めします。

## <a name="exchange-online-mail-flow-with-smtp-dane"></a>SMTP DANE を使用したメール FlowのExchange Online

SMTP DANE を使用したExchange Onlineのメール フロー プロセスは、次のフロー 図に示すように、DNSSEC、宛先メール サーバーでの TLS サポート、および宛先メール サーバーの証明書が、関連する TLSA レコードに基づいて想定されているものと一致するドメインとリソース レコードのセキュリティを検証します。

SMTP DANE エラーによって電子メールがブロックされるシナリオは 2 つだけです。

- 宛先ドメインは DNSSEC のサポートを通知しましたが、1 つ以上のレコードが認証されていないものとして返されました。

- 宛先ドメインのすべての MX レコードには TLSA レコードがあり、宛先サーバーの証明書のいずれも、TSLA レコード データに対して想定されていたものと一致しないか、TLS 接続が宛先サーバーでサポートされていません。

:::image type="content" source="../media/compliance-trial/mail-flow-smtp-dane.png" alt-text="SMTP DANE を使用したオンライン メール フローのExchange" lightbox="../media/compliance-trial/mail-flow-smtp-dane.png":::

## <a name="related-technologies"></a>関連技術

|テクノロジ|その他の情報|
|---|---|
|**メール転送エージェント - 厳格なトランスポート セキュリティ (MTA-STS)** は、転送先の電子メール サーバーが TLS をサポートするかどうか、TLS をネゴシエートできない場合に行う操作を指定するドメイン ポリシーを設定するメカニズムを提供することで、ダウングレードと中間者攻撃を阻止するのに役立ちます。たとえば、転送を停止します。|Exchange Onlineのインバウンドおよびアウトバウンドの MTA-STS の今後のサポートの詳細については、今年後半に公開される予定です。 <br/><br/> [Microsoft Ignite 2020 からのトランスポート ニュースのExchange Online - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699) <br/><br/> [rfc8461 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc8461)|
|**Sender Policy Framework (SPF)** では、IP 情報を使用して、宛先電子メール システムがカスタム ドメインから送信されたメッセージを信頼するようにします。|[Sender Policy Framework (SPF) がスプーフィングを防止する方法 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)|
|**DomainKeys 識別メール (DKIM)** では、X.509 証明書情報を使用して、宛先電子メール システムがカスタム ドメインから送信されたメッセージを信頼できるようにします。|[カスタム ドメインの電子メールに DKIM を使用する方法 - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)|
|**ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) は、** 送信者ポリシー フレームワークと DomainKeys 識別メールと連携して、メール送信者を認証し、宛先電子メール システムがドメインから送信されたメッセージを信頼することを確認します。|[DMARC を使用して電子メールを検証し、手順をセットアップする - Office 365 - Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)|

## <a name="troubleshooting-sending-emails-with-smtp-dane"></a>SMTP DANE を使用した電子メールの送信のトラブルシューティング

現在、EXCHANGE ONLINEで電子メールを送信する場合、DANE には 4 つのエラー コードがあります。 Microsoft では、このエラー コードの一覧を積極的に更新しています。 次のエラーが表示されます。

1. メッセージ トレースの詳細ビューを使用して管理センターポータルをExchangeします。
2. DANE または DNSSEC エラーが原因でメッセージが送信されない場合に生成される NDR。
3. リモート接続アナライザー ツール [Microsoft リモート接続アナライザー](https://testconnectivity.microsoft.com/tests/o365)。

|NDR コード|説明|
|---|---|
|5.7.321|starttls-not-supported: 宛先メール サーバーは、メールを受信するために TLS をサポートする必要があります。|
|5.7.322|certificate-expired: 宛先メール サーバーの証明書の有効期限が切れています。|
|5.7.323|tlsa-invalid: ドメインが DANE 検証に失敗しました。|
|5.7.324|dnssec-invalid: 宛先ドメインが無効な DNSSEC レコードを返しました。|

### <a name="troubleshooting-57321-starttls-not-supported"></a>トラブルシューティング 5.7.321 starttls-not-supported

これは通常、宛先メール サーバーに関する問題を示します。 メッセージを受信した後:

1. 宛先の電子メール アドレスが正しく入力されたことを確認します。
2. 宛先サーバーが TLS を使用してメッセージを受信するように正しく構成されているかどうかを判断できるように、このエラー コードを受信したことを宛先メール管理者に通知します。
3. メールの送信を再試行し、Exchange管理センター ポータルでメッセージのメッセージ トレースの詳細を確認します。

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 証明書の有効期限が切れた場合のトラブルシューティング

有効期限が切れていない有効な X.509 証明書を、送信側の電子メール サーバーに提示する必要があります。 X.509 証明書は、有効期限が切れた場合は更新する必要があり、一般的には毎年更新する必要があります。 メッセージを受信した後:

1. このエラー コードを受信したことを宛先の電子メール管理者に通知し、エラー コード文字列を指定します。
2. 宛先サーバー証明書を更新し、TLSA レコードを更新して新しい証明書を参照する時間を確保します。 次に、メールの送信を再試行し、Exchange管理センター ポータルでメッセージのメッセージ トレースの詳細を確認します。

### <a name="troubleshooting-57323-tlsa-invalid"></a>トラブルシューティング 5.7.323 tlsa-invalid

このエラー コードは、TLSA レコードの構成ミスに関連しており、DNSSEC の信頼性の高い TLSA レコードが返された後にのみ生成できます。 レコードが返された後に発生する DANE 検証中には、コードが生成される可能性があるシナリオが多数あります。 Microsoft は、各シナリオに特定のコードが含まれるように、このエラー コードの対象となるシナリオに積極的に取り組んでいます。 現時点では、次の 1 つ以上のシナリオでエラー コードが生成される可能性があります。

1. 宛先メール サーバーの証明書が、本物の TLSA レコードごとに想定される証明書と一致しない。
2. 本物の TLSA レコードが正しく構成されていない。
3. 宛先ドメインが攻撃されています。
4. その他の DANE エラー。

メッセージを受信した後:

1. このエラー コードを受信したことを宛先の電子メール管理者に通知し、エラー コード文字列を指定します。
2. 宛先メール管理者が DANE 構成と電子メール サーバー証明書の有効性を確認する時間を確保します。 次に、メールの送信を再試行し、Exchange管理センター ポータルでメッセージのメッセージ トレースの詳細を確認します。

### <a name="troubleshooting-57324-dnssec-invalid"></a>トラブルシューティング 5.7.324 dnssec-invalid

このエラー コードは、宛先ドメインが DNSSEC の信頼性を示したが、EXCHANGE ONLINE DNSSEC 認証として検証できなかった場合に生成されます。

メッセージを受信した後:

1. このエラー コードを受信したことを宛先の電子メール管理者に通知し、エラー コード文字列を指定します。
2. 宛先メール管理者がドメインの DNSSEC 構成を確認する時間を確保します。 次に、メールの送信を再試行し、Exchange管理センター ポータルでメッセージのメッセージ トレースの詳細を確認します。

## <a name="troubleshooting-receiving-emails-with-smtp-dane"></a>SMTP DANE を使用した電子メールの受信のトラブルシューティング

現在、受信ドメインの管理者が DNSSEC と DANE の構成を検証してトラブルシューティングし、これらの標準を使用してExchange Onlineから電子メールを受信するために使用できる方法は 2 つあります。

1. [RFC8460](https://datatracker.ietf.org/doc/html/rfc8460) で導入された SMTP TLS-RPT (トランスポート層セキュリティ レポート) を採用する
2. リモート接続アナライザー ツール [Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365) を使用する

TLS-RPT [https://datatracker.ietf.org/doc/html/rfc8460](https://datatracker.ietf.org/doc/html/rfc8460) は、送信者が DANE と MTA-STS の成功とそれぞれの宛先ドメインでの失敗に関する詳細を宛先ドメイン管理者に提供するためのレポート メカニズムです。 TLS-RPT レポートを受信するには、レポートの送信先となるメール アドレスまたは URI を含む TXT レコードをドメインの DNS レコードに追加するだけで済みます。 Exchange Onlineは、TLS-RPT レポートを JSON 形式で送信します。

レコードの例:

:::image type="content" source="../media/compliance-trial/example-record.png" alt-text="レコードの例" lightbox="../media/compliance-trial/example-record.png":::

2 つ目の方法は、リモート接続アナライザー [Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365) を使用することです。これは、サービスの外部で電子メールを送信するときに実行する DNS 構成に対して同じ DNSSEC と DANE チェックを実行Exchange Online。 これは、これらの標準を使用してExchange Onlineから電子メールを受信するために、構成内のエラーをトラブルシューティングする最も直接的な方法です。

トラブルシューティング時に、次のエラー コードが生成される場合があります。

|NDR コード|説明|
|---|---|
|4/5.7.321|starttls-not-supported: 宛先メール サーバーは、メールを受信するために TLS をサポートする必要があります。|
|4/5.7.322|certificate-expired: 宛先メール サーバーの証明書の有効期限が切れています。|
|4/5.7.323|tlsa-invalid: ドメインが DANE 検証に失敗しました。|
|4/5.7.324|dnssec-invalid: 宛先ドメインが無効な DNSSEC レコードを返しました。|

### <a name="troubleshooting-57321-starttls-not-supported"></a>トラブルシューティング 5.7.321 starttls-not-supported

> [!NOTE]
> これらの手順は、SMTP DANE を使用してExchange Onlineから電子メールを受信するトラブルシューティングを行う電子メール管理者向けです。

これは通常、宛先メール サーバーに関する問題を示します。 リモート接続アナライザーが接続をテストしているメール サーバー。 一般に、このコードを生成するシナリオは 2 つあります。

1. 宛先メール サーバーはセキュリティで保護された通信をまったくサポートしていないため、暗号化されていないプレーンな通信を使用する必要があります。
2. 移行先サーバーが正しく構成されておらず、STARTTLS コマンドは無視されます。

メッセージを受信した後:

1. メール アドレスを確認します。
2. ステートメントが関連付けられているメール サーバーを識別できるように、エラー ステートメントに関連付けられている IP アドレスを見つけます。
3. メール サーバーの設定を確認して、SMTP トラフィック (通常はポート 25 と 587) をリッスンするように構成されていることを確認します。
4. 数分待ってから、リモート接続アナライザー ツールを使用してテストを再試行します。
5. それでも失敗した場合は、TLSA レコードを削除し、リモート接続アナライザー ツールを使用してテストをもう一度実行してください。
6. エラーがない場合は、メールの受信に使用しているメール サーバーが STARTTLS をサポートしていないため、DANE を使用するためにアップグレードする必要がある場合があります。

### <a name="troubleshooting-57322-certificate-expired"></a>5.7.322 証明書の有効期限が切れた場合のトラブルシューティング

> [!NOTE]
> これらの手順は、SMTP DANE を使用してExchange Onlineから電子メールを受信するトラブルシューティングを行う電子メール管理者向けです。

有効期限が切れていない有効な X.509 証明書を、送信側の電子メール サーバーに提示する必要があります。 X.509 証明書は、有効期限が切れた場合は更新する必要があり、一般的には毎年更新する必要があります。 メッセージを受信した後:

1. エラー ステートメントに関連付けられている IP を確認して、関連付けられているメール サーバーを識別できるようにします。 指定した電子メール サーバーで有効期限が切れた証明書を見つけます。
2. 証明書プロバイダーの Web サイトにログインします。
3. 有効期限が切れた証明書を選択し、手順に従って更新し、更新の料金を支払います。
4. プロバイダーが購入を確認したら、新しい証明書をダウンロードできます。
5. 更新された証明書を関連付けられたメール サーバーにインストールします。
6. メール サーバーに関連付けられている TLSA レコードを新しい証明書のデータで更新します。
7. 適切な時間を待機した後、リモート接続アナライザー ツールを使用してテストを再試行します。

### <a name="troubleshooting-57323-tlsa-invalid"></a>トラブルシューティング 5.7.323 tlsa-invalid

> [!NOTE]
> これらの手順は、SMTP DANE を使用してExchange Onlineから電子メールを受信するトラブルシューティングを行う電子メール管理者向けです。

このエラー コードは TLSA レコードの構成ミスに関連しており、DNSSEC の正規 TSLA レコードが返された後にのみ生成できます。 ただし、レコードが返された後に発生する DANE 検証中には、コードが生成される可能性があるシナリオが多数あります。 Microsoft は、各シナリオに特定のコードが含まれるように、このエラー コードの対象となるシナリオに積極的に取り組んでいます。 現時点では、次の 1 つ以上のシナリオでエラー コードが生成される可能性があります。

1. 本物の TLSA レコードが正しく構成されていない。
2. 証明書は、今後の時間枠に対してまだ有効または構成されていません。
3. 宛先ドメインが攻撃されている。
4. その他の DANE エラー。

メッセージを受信した後:

1. エラー ステートメントに関連付けられている IP を確認して、関連付けられているメール サーバーを特定します。
2. 識別されたメール サーバーに関連付けられている TLSA レコードを識別します。
3. TLSA レコードの構成を確認して、優先 DANE チェックを実行するように送信者に通知し、正しい証明書データが TLSA レコードに含まれていることを確認します。
    1. 不一致のためにレコードを更新する必要がある場合は、数分待ってから、リモート接続アナライザー ツールを使用してテストを再実行します。
4. 識別されたメール サーバーで証明書を見つけます。
5. 証明書が有効な時間枠を確認します。 有効期限を将来の日付で開始するように設定されている場合は、現在の日付に対して更新する必要があります。
    1. 証明書プロバイダーの Web サイトにログインします。
    2. 有効期限が切れた証明書を選択し、手順に従って更新し、更新の料金を支払います。
    3. プロバイダーが購入を確認したら、新しい証明書をダウンロードできます。
    4. 更新された証明書を関連付けられたメール サーバーにインストールします。

### <a name="troubleshooting-57324-dnssec-invalid"></a>トラブルシューティング 5.7.324 dnssec-invalid

> [!NOTE]
> これらの手順は、SMTP DANE を使用してExchange Onlineから電子メールを受信するトラブルシューティングを行う電子メール管理者向けです。

このエラー コードは、宛先ドメインが DNSSEC の信頼性を示したが、DNSSEC 認証として検証できないExchange Onlineに生成されます。 このセクションは、DNSSEC の問題をトラブルシューティングするための包括的なものではなく、ドメインが以前に DNSSEC 認証を渡したが、現在は渡されなかったシナリオに焦点を当てています。

メッセージを受信した後:

1. GoDaddy などの DNS プロバイダーを使用している場合は、トラブルシューティングと構成の変更に対応できるように、DNS プロバイダーにエラーを警告します。
2. 独自の DNSSEC インフラストラクチャを管理している場合は、このエラー メッセージを生成する可能性のある DNSSEC の構成ミスが多数存在します。 ゾーンが以前に DNSSEC 認証を渡していたかどうかを確認するための一般的な問題がいくつかあります。
    1. 破損した信頼チェーン。親ゾーンが子ゾーンに存在しない何かを指す一連の DS レコードを保持している場合。 これにより、子ゾーンはリゾルバーの検証によって偽物としてマークされます。
        - 子ドメイン RRSIG キー ID を確認し、親ゾーンで発行された DS レコードのキー ID と一致することを確認して解決します。
    2. ドメインの RRSIG リソース レコードは有効な時間ではありません。有効期限が切れているか、有効期間が開始されていません。
        - 有効なタイムスパンを使用してドメインの新しい署名を生成することで解決します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="as-an-exchange-online-customer-can-i-opt-out-of-using-dnssec-andor-dane"></a>Exchange Online顧客として、DNSSEC または DANE の使用をオプトアウトできますか?

DNSSEC と DANE は、サービスのセキュリティポジションを大幅に向上させ、すべてのお客様に利益をもたらすと強く考えています。 このデプロイが M365 のお客様に与える可能性のある影響のリスクと重大度を軽減するために、昨年は勤勉に取り組んできました。 展開を積極的に監視および追跡し、ロールアウト時に悪影響を最小限に抑えます。このため、テナント レベルの例外またはオプトアウトは使用できません。
DNSSEC や DANE の有効化に関連する問題が発生した場合は、このドキュメントに記載されているエラーを調査するためのさまざまな方法が、エラーの原因を特定するのに役立ちます。 ほとんどの場合、問題は外部の宛先パーティーで発生し、これらの標準を使用してExchange Onlineから電子メールを受信するために DNSSEC と DANE を正しく構成する必要があることをこれらのビジネス パートナーに伝える必要があります。

### <a name="how-does-dnssec-relate-to-dane"></a>DNSSEC と DANE の関係

DNSSEC は、DNS クエリに応答して返されるレコードが確実に確実に信頼できるように、公開キー インフラストラクチャを利用して DNS 解決に信頼層を追加します。 DANE では、受信メール サーバーが正規の MX レコードの正当で想定されるメール サーバーであることを確認します。

### <a name="what-is-the-difference-between-mta-sts-and-dane-for-smtp"></a>SMTP の MTA-STS と DANE の違いは何ですか?

DANE と MTA-STS は同じ目的で機能しますが、DNS 認証には DNSSEC が必要ですが、MTA-STS は証明機関に依存しています。

### <a name="why-isnt-opportunistic-tls-sufficient"></a>日和見 TLS で十分でないのはなぜですか?

両者がサポートすることに同意した場合、日和見 TLS は 2 つのエンドポイント間の通信を暗号化します。 ただし、TLS によって送信が暗号化された場合でも、ドメインの実際のエンドポイントではなく悪意のあるアクターのエンドポイントを指すように、DNS 解決中にドメインがスプーフィングされる可能性があります。 これは、DNSSEC を使用して MTA-STS や SMTP DANE を実装することによって対処される電子メール セキュリティのギャップです。

### <a name="why-isnt-dnssec-sufficient"></a>DNSSEC が十分でない理由

DNSSEC は、中間者攻撃に対して完全に耐性がなく、メール フロー シナリオに対して (TLS からクリア テキストへの) 攻撃をダウングレードします。 DNSSEC と共に MTA-STS と DANE を追加すると、MITM 攻撃とダウングレード攻撃の両方を阻止するための包括的なセキュリティ方法が提供されます。

## <a name="additional-links"></a>その他のリンク

[ドメインまたは DNS レコードを追加後に問題を特定して解決する](/microsoft-365/admin/get-help-with-domains/find-and-fix-issues)

[DNSSEC |の概要Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))

[DMARC を使用して電子メールを検証する、セットアップ手順 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

[カスタム ドメインの電子メールに DKIM を使用する方法 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)

[Sender Policy Framework (SPF) がスプーフィングを防止する方法 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)

[Microsoft Ignite 2020 からのトランスポート ニュースのExchange Online - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)

[rfc8461 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc8461)
