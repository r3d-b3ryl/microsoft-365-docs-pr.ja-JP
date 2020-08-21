---
title: スパム対策保護 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のスパム対策保護に関してよく寄せられる質問と回答を表示できます。
ms.openlocfilehash: ed871990cf5f8fc4e15995987312fc6814ab8296
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825175"
---
# <a name="anti-spam-protection-faq"></a>スパム対策保護に関するよく寄せられる質問

このトピックでは、Exchange Online メールボックスを使用している Microsoft 365 組織または Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織向けのマルウェア対策保護に関してよく寄せられる質問と回答について取り上示します。

検疫に関する質問と回答については、「[検疫に関する FAQ](quarantine-faq.md)」を参照してください。

マルウェア対策保護に関する質問と回答については、「マルウェア対策保護 [」に関する FAQ を参照してください](anti-malware-protection-faq-eop.md)。

スプーフィング対策保護に関する質問と回答については、「スプーフィング [対策保護に関する FAQ」を参照してください](anti-spoofing-protection-faq.md)。

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>既定では、スパム検出メッセージはどのように処理されますか?

**受信メッセージの場合:** スパムの大部分は、ソース 電子メール サーバーの IP アドレスに基づき、接続フィルタを介して削除されます。 スパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) は、メッセージをスパム、バルク、またはフィッシングとして検疫および分類します。 既定では、スパムまたはバルクとして分類されたメッセージは受信者の迷惑メール フォルダーに配信される一方で、フィッシングとして分類されたメッセージは検疫されます。 既定のスパム対策ポリシーを変更する (すべての受信者に適用) したり、特定のユーザー グループについて高い設定でカスタムのスパム対策ポリシーを作成したりすることができます (たとえば、経営幹部に送信されたスパムを検疫できます)。 詳細については、「スパム対策[ポリシーと推奨されるスパム対策](configure-your-spam-filter-policies.md)[ポリシーの設定を構成する」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

> [!IMPORTANT]
> EOP が社内メールボックスを保護するハイブリッド展開では、メッセージに追加された EOP スパム フィルター ヘッダーを検出するように、オンプレミス Exchange 組織に 2 つの Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

 **送信メッセージの場合** メッセージが危険度の高い配信プール [経由でルーティング](high-risk-delivery-pool-for-outbound-messages.md) されるか、配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) で送信者に返されるかのいずれかになります。 送信スパム保護の詳細については、「送信スパム [制御」を参照してください](outbound-spam-controls.md)。

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>ゼロデイ スパム バリアントとは何ですか。また、サービスはそれをどのように処理しますか。

ゼロデイ スパム バリアントは、以前は未知のスパムの種類がキャプチャまたは分析されない最初の世元で、スパムの検出や分析の日付がまだないため、スパム対策フィルターには、スパム対策フィルターではまだ利用可能な情報がありません。 スパム分析が成功すると、スパム分析情報が満たされた場合、スパム分析の条件を満たすと、スパム対策フィルターが更新され、「ゼロデイ」と見なされなくなりまいます。

**注:** ゼロデイ スパム バリエーションであるメッセージを受信した場合、サービスを改善するためにサービスを改善するために、レポート メッセージとファイルに関する説明のいずれかの方法を使用して Microsoft [にそのメッセージを送信してください](report-junk-email-messages-to-microsoft.md)。

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>スパム対策保護を提供するサービスを構成する必要はありますか?

サービスのサインアップを行い、ドメインを追加すると、スパム フィルタリングが自動的に有効になります。 既定では、スパム フィルタリングは、(ハイブリッド環境で以前に説明したスタンドアロンの EOP スタンドアロンのお客様の例外と並行していた) 不要な構成のないようにチンコードされています。 管理者は組織のニーズに最適な既定のスパム フィルター設定を編集できます。 よりきめ細かく計画する場合は、組織内の指定したユーザー、グループ、またはドメインに適用されるスパム対策ポリシーおよび送信スパム対策ポリシーも作成できます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (つまり、実行順序) を変更できます。

詳細については、次のトピックをご覧ください。

[EOP およびドメイン 365 ATP セキュリティに関Office推奨設定](recommended-settings-for-eop-and-office365-atp.md)

[EOP で接続フィルターを構成する](configure-the-connection-filter-policy.md)

[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)

[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>スパム対策ポリシーを変更した場合、変更を保存してからその変更が反映されるまで、どれ位かかりますか?

変更が有効になるまで最大 1 時間かかります。

## <a name="is-bulk-email-filtering-automatically-enabled"></a>バルク メールのフィルタリングは自動的に有効になりますか?

はい。 バルク メールの詳細については、「 [迷惑メールとバルク メールの違い」を参照してください](what-s-the-difference-between-junk-email-and-bulk-email.md)。

## <a name="does-the-service-provide-url-filtering"></a>このサービスでは URL フィルター機能が提供されますか?

はい、メッセージ内の URL を確認する URL フィルターがサービスに含まれます。 既知のスパムまたは悪意のあるコンテンツに関連付けられている URL が検出されると、メッセージはスパムとしてマークされます。

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>サービス使用中の顧客が Microsoft へ偽陰性 (スパム) メッセージおよび偽陽性 (スパムでない) メッセージを送信するにはどうしますか。

スパムとスパムではないメッセージを分析のために Microsoft に送信するには、いくつかの方法があります。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="can-i-get-spam-reports"></a>スパム報告を取得できますか?

はい。たとえば、Microsoft 365 管理センターでスパム検出レポートを取得することができます。 このレポートでは、スパムの量が一意のメッセージの数として表示されます。 レポートの詳細については、以下のリンクを参照してください。

Exchange Online のお客様 [: Exchange Online での監視、レポート、メッセージ追跡](https://docs.microsoft.com/exchange/monitoring/monitoring)

スタンドアロン EOP のお客様: [Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>他のユーザーがメッセージを送り、そのメッセージを見つけない。 スパムとして検出された可能性があります。 調べるためのツールはありますか?

はい、メッセージ追跡ツールを使用すると、サービスを通る電子メール メッセージを追跡し、メール メッセージがどうなったかを確認できます。 メッセージ追跡ツールを使用してメッセージが迷惑メールとしてマークされた理由を特定する方法の詳細については、「 [メッセージはスパムとしてマークされましたか?」を参照してください。](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>ユーザーがスパムを送信した場合、サービスはメールを調整 (速度制限) しますか?

特定の時間枠 (たとえば、1 時間ごと) 内でサービスを使用してユーザーから送信されたメールの半数以上が EOP によって迷惑メールと判断された場合、ユーザーはメッセージを送信できません。 この結果、通常の送信 IP プールが禁止リストに追加される可能性は減少します。

送信者が送信スパムの送信をブロックされている場合、指定したメール アドレスに通知を送信できます。 この設定の詳細については、「[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)」を参照してください。

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>サードパーティのスパム対策およびマルウェア対策プロバイダーを Exchange Online と併用できますか。

はい。 MX レコードの指定を Microsoft に推奨しますが、電子メールを最初に Microsoft 以外の場所にルーティングする正当な業務上の理由があることは認識しています。

- **受信**: サードパーティ プロバイダーを指定するために MX レコードを変更し、メッセージを EOP にリダイレクトして追加処理します。 詳細については [、「Exchange Online のコネクタ用の拡張フィルター処理」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **送信:** Microsoft 365 から宛先のサード パーティ プロバイダーへのスマート ホスト ルーティングを構成します。

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>マイクロソフトには、フィッシング詐欺から自分を守る方法に関するドキュメントはありますか。

はい。 詳細については、「インターネット上の [プライバシーを保護する」を参照してください。](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>スパム メッセージおよびマルウェア メッセージの送信元に関する調査や、法執行機関への転送は行っていますか?

サービスの中心はスパムやマルウェアの検出と除去ですが、特に危険で破壊力が大きい一連のスパムまたは攻撃については、加害者を調査および追跡する場合があります。 たとえば、Microsoft の法律部門やデジタル犯罪対策部門と連携して悪意のあるボットネットを削除したり、加害者がサービスを使用できないようにしたり (そのサービスが外部への電子メール送信に使用されている場合)、刑事告発のために法執行機関に情報を提供したりします。

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>メールが確実に配信されるようにするための、送信メールに関するベスト プラクティスは?

以下に示すガイドラインは、送信メール メッセージを送信するためのベスト プラクティスです。

- **ソース メール ドメインが DNS に解決されるはじです。**

  たとえば、送信者がドメイン管理者であるuser@fabrikamfabrikam は IP アドレスの 192.0.43.10 に解決されます。
  
  DNS で送信者のドメインの A-record と MX レコードが存在しない場合、メッセージのコンテンツがスパムであるなしにかかわらず、サービスはより危険度の高い配信プール経由でメッセージをルーティングします。 より危険度の高い配信プールの詳細については、送信メッセージに [関する危険度の高い配信プールを参照してください](high-risk-delivery-pool-for-outbound-messages.md)。

- **送信メール電子メール サーバーには、逆引き DNS (PTR) エントリが必要です。**

  たとえば、電子メール ソースの IP アドレスが 192.0.43.10 の場合、逆引き DNS エントリは `43-10.any.icann.org` .' になります。

- **HELO/EHLO および MAIL FROM コマンドに整合性があり、IP アドレスではなくドメイン名の形式で表現される必要があります。**

  HELO/EHLO コマンドは送信 IP アドレスの逆引き DNS と一致するように構成する必要があります。このようにすることで、メッセージ ヘッダーのあらゆる部分でドメインが同一に保たれます。

- **適切な SPF レコードが DNS に設定されていることを確認します。**

  SPF レコードとは、ドメインから送信されたメールがそのドメインから実際に送信されていること、なりすましではないことを確認するためのメカニズムです。 SPF レコードの詳細については、以下のリンクを参照してください:

  [SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [ドメイン FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **DKIM で電子メールを署名する場合、relaxed 正規化で署名します。**

  送信者が Domain Keys Identified Mail (DKIM) を使用してメッセージに署名し、サービスを通じて送信メールを送信する場合、送信者は relaxed ヘッダー正規化アルゴリズムを使用して署名する必要があります。 strict ヘッダー正規化で署名することにより、メッセージがサービスを通過するときに署名が無効になる場合があります。

- **ドメイン所有者は、WHOIS データベースに正確な情報が必要です。**

  これにより、安定した親会社、連絡先、およびネーム サーバーを入力することで、ドメインの所有者と問い合わせ方法が特定されます。

- **バルク メール業者にとって、From: 名は メッセージの送信者を表し、メッセージの件名行はメッセージの内容の概要である必要があります。**

  メッセージの本文は、提供、サービス、製品の分かりやすい説明である必要があります。 たとえば、送信者が Contoso 会社のバルク メールを送信している場合、電子メールの差出人および件名は以下のようになります:

  > From: marketing@contoso.com <br/> 件名: クリスマス シーズンの最新カタログ!

  以下の例は説明的ではないため、バルク メールとしては不適切です。

  > From: user@hotmail.com <br/> 件名: カタログ

- **バルク メールが多数の受信者に送信されるもので、メッセージが広報形式である場合、メッセージの最下部に登録解除手段が存在する必要があります。**

  登録解除オプションは次のように表示されるはずです:

  > このメッセージは、sender@fabrikam.com から example@contoso.com に送信されました。 Update Profile/Email Address |SafeUnsubscribe を使用した**瞬時の削除** &trade; |プライバシー ポリシー

- **バルク メールを送信する場合、ダブル オプトインを使用してリスト取得を実行する必要があります。バルク メールの送信者にとって、ダブル オプトインは業界のベスト プラクティスです。**

  ダブル オプトインでは、ユーザーがマーケティング メールの会員になるには、2 つのアクションを実行する必要があります:

  1. 1 回目は、ユーザーが以前にオンではなかったチェックボックスをクリックすることにより、ユーザーが業者からの広告やメール メッセージを今後も受け取ることを選択します。

  2. 2 回目は、ユーザーが入力したメール アドレスに確認メールを業者が送信します。この確認メールにある時間制限付きリンクをユーザーがクリックすることにより、確認が完了します。

  ダブル オプトインを使用することで、バルク メール送信業者としての良好な評価を得ることができます。

- **バルク送信業者は、説明責任を負うことが可能な透過的コンテンツを作成する必要があります:**

  1. アドレス帳に送信者を追加するようメール受信者に何度もお願いしても、それがメールの配信を保証しないことは明らかです。

  2. メッセージ本文でリダイレクトを作成するときには、一貫したリンク スタイルを使用します。

  3. サイズの大きな画像や添付ファイル、画像だけのメッセージは送信しません。

  4. トラッキング ピクセル (Web バグ、ビーコン) を使用する場合には、プライバシー ポリシー、P3P 設定にトラッキング ピクセルが存在することを明記します。

- **送信バウンス メッセージの書式を設定します。**

  配信状態通知メッセージ (配信不能レポート、NDR、バウンス メッセージとも呼ばれる) を生成する場合、送信者は [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)で指定されているバウンスの形式に従う必要があります。

- **存在しないユーザーのバウンスされたメール アドレスを削除します。**

  メール アドレスが使用されていないことを示す NDR を受信したら、存在しないメール エイリアスを一覧から削除します。 メール アドレスは時間とともに変化し、ユーザーはメール アドレスを破棄することがあります。

- **Hotmail の Smart Network Data Services (SNDS) プログラムを使用します。**

  Hotmail は Smart Network Data Services というプログラムを使用します。このプログラムにより、送信業者はエンド ユーザーが送信したクレームをチェックできます。 SNDS は、Hotmail の配信の問題をトラブルシューティングするための第一のポータルです。
