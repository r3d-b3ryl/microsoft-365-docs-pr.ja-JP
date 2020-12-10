---
title: Office 365 セキュリティ、Microsoft Defender for Office 365、EOP、MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365 のセキュリティ。 Office 365 プラン1および2では、EOP から Defender に、標準のセキュリティ構成と厳密に比較します。 現在の状況と、プロパティをセキュリティで保護する方法について理解します。
ms.openlocfilehash: 84d7dcfc68ce78bfde92f3d7096cd4104355ce94
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616250"
---
# <a name="office-365-security-overview"></a>Office 365 のセキュリティの概要

この記事では、クラウド内の新しいセキュリティプロパティについて説明します。 セキュリティ操作センターの一部であるかどうかにかかわらず、セキュリティ管理者はこのスペースを利用しているか、またはリフレッシャーを使用したいと考えています。

> [!CAUTION]
> **Outlook.com**、 **microsoft 365 ファミリ**、または **microsoft 365 Personal** を使用していて *、安全なリンク* または安全な *添付ファイル* の情報を必要とする場合は、**[このリンク** _: [Microsoft 365 サブスクライバーの高度な Outlook.com セキュリティ](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)] をクリックします。

## <a name="office-365-security-spelled-out"></a>Office 365 のセキュリティに関する綴り

すべての Office 365 サブスクリプションには、セキュリティ機能が付属しています。 実行できる目標と操作は、これらの異なるサブスクリプションの焦点に依存します。 Office 365 のセキュリティでは、サブスクリプションの種類に関連付けられている3つの主要なセキュリティサービス (製品) があります。

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 プラン 1 (Defender for Office P1)
1. Microsoft Defender for Office 365 プラン 2 (Defender for Office P2)

> [!NOTE]
> サブスクリプションを購入し、セキュリティ機能 _right 今すぐ展開する必要がある場合は、「 [脅威からの保護](protect-against-threats.md) 」の手順に進んでください。 ご利用のお客様がご自身のサブスクリプションを初めてご利用になる場合は、 [Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/#/homepage)の製品 > 請求先を参照してください。

Office 365 は、EOP によって提供される中心的な保護に基づいて構築されています。 EOP は、Exchange Online メールボックスが存在する任意のサブスクリプションに存在します (ここで説明するすべてのセキュリティ製品はクラウドベースであることに注意してください)。

この方法で説明した3つのコンポーネントについては、よく見られます。

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|ボリュームベースの広範な既知の攻撃を防止します。|ゼロ日のマルウェア、フィッシング、およびビジネスメールの侵害から電子メールとコラボレーションを保護します。|事後違反の調査、探し、応答、自動化、シミュレーション (トレーニング用) を追加します。|
|

しかし、アーキテクチャに関しては、各部分をセキュリティの累積的なレイヤーと考え、それぞれにセキュリティ上の重点を置いて始めましょう。 次のようになります。

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP および Microsoft Defender for Office 365 と、サービス強調を使用した相互関係 (電子メール認証に関するメモを含む)。":::

これらのサービスはそれぞれ、保護、検出、調査、応答の中から目標を強調していますが、***all** _ サービスは、保護、検出、調査、応答の _*_いずれか_*_ の目標を達成できます。

Office 365 セキュリティの中核となるのは、EOP 保護です。 Microsoft Defender for Office 365 P1 に EOP が含まれています。 Office の Defender 365 P2 には、P1 と EOP が含まれています。 この構造体は累積されています。 この製品を構成する場合は、EOP から始めて、Office 365 の Defender に対して作業を開始する必要があります。

電子メール認証の構成はパブリック DNS で行われますが、この機能を構成してスプーフィングを防止することが重要です。 _EOP がある場合、* ***[電子メール認証を構成](email-validation-and-authentication.md)する必要があり**_ ます。

Office 365 E3 以降がある場合は、EOP がありますが、アップグレードのためにスタンドアロン Defender for Office 365 P1 を購入するというオプションがあります。 Office 365 E5 がインストールされている場合は、既に Office 365 P2 の Defender があります。

> [!TIP]
> サブスクリプションが Office 365 E3 または E5 のどちらでもない場合でも、Microsoft Defender for Office 365 P1 にアップグレードするオプションがあるかどうかを確認することができます。 関心がある場合、 [この web ページ](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) には、Microsoft Defender for Office 365 P1 upgrade の対象となるサブスクリプションが表示されます (詳細については、ページの最後をチェックしてください)。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Office 365 セキュリティは、EOP から Microsoft Defender for Office 365 にはしごされています。

![EOP および Microsoft Defender for Office 365 と、セキュリティ上の強調。保護と検出から、調査と応答に進みます。 メール認証の構成 (少なくとも DKIM および DMARC) は、EOP と up に対して設定する必要があります。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> これらのページの詳細については、「 [Exchange Online Protection](exchange-online-protection-overview.md)」および「 [Office 365 用の Defender](office-365-atp.md)」を参照してください。

Microsoft Defender for Office 365 を追加することによって、純粋な EOP 脅威管理の利点を最初にわかりやすくすることが困難になります。 アップグレードパスが組織に適しているかどうかを判断するには、各製品の機能を次のように確認してみましょう。

- 脅威の防止と検出
- うち
- 応答

_ * Exchange Online Protection * * で開始します。
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジは次のとおりです。<ul><li>スパム</li><li>フィッシング</li><li>ウェア</li><li>バルクメール</li><li>スプーフィングインテリジェンス</li><li>偽装の検出</li><li>管理者検疫</li><li>誤検知と誤検知の管理者およびユーザーの送信</li><li>Url とファイルの許可/ブロック</li><li>レポート</li></u1>|<li>監査ログ検索</li><li>メッセージの追跡</li>|<li>ゼロ時間自動削除 (ZAP)</li><li>許可リストと禁止リストの絞り込みとテスト</li>|
|

EOP に移動する場合は、 **[この記事に移動](exchange-online-protection-overview.md)** してください。

これらの製品は累積的なものであるため、Microsoft Defender for Office 365 P1 を評価してそれにサブスクライブすることを決定した場合、これらの機能を追加します。

**Office 365 の Defender** によるメリット: プラン 1 (終了):
<p>

|防止/検出|調査|対応|
|---|---|---|
|EOP に含まれるテクノロジには、次のようなものがあります。<u1><li>安全な添付ファイル</li><li>安全なリンク<li>Microsoft Defender for Office 365 のワークロードの保護 (例) SharePoint Online、Teams、OneDrive for Business)</li><li>電子メール、Office クライアント、および Teams でのクリック時の保護</li><li>Office 365 の Defender でのフィッシング対策</li><li>ユーザーおよびドメインの偽装保護</li><li>通知の SIEM 統合 API</li>|<li>検出のための SIEM 統合 API</li><li>**リアルタイム検出ツール**</li><li>URL トレース</li>|<li>同じ</li></u1>

そのため、Microsoft Defender for Office 365 P1 は、家の **_防止_* _ 側に展開され、さらにさまざまな形式の _*_検出_*_ が追加されています。

Microsoft Defender for Office 365 P1 でも、調査のために *リアルタイム検出 * が* 追加されています。 この脅威の探すツールの名前は、Office 365 P1 の Defender があることを *知ら* せる明確なものであるため、太字になっています。 Office 365 P2 の Defender には表示されません。

**Office 365 の Defender の利点: プラン 2** (終了):
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには、EOP のすべてが含まれており、Microsoft Defender for Office 365 P1 plus が含まれています。<u1><li>同じ</li>|<li>**脅威エクスプローラー**</li><li>脅威トラッカー</li><li>キャンペーンビュー</li>|<li>自動化された調査と応答 (AIR)</li><li>脅威エクスプローラからの空気</li><li>侵害されたユーザーのための空気</li><li>自動調査用の SIEM 統合 API</li>

そのため、Microsoft Defender for Office 365 P2 は、社内の **_調査と応答_* の _ 側で拡張され、新しいお探しの強度が追加されています。 自動化。

Microsoft Defender for Office 365 P2 では、プライマリの探しているツールは、リアルタイムの検出ではなく、_ *Threat Explorer** と呼ばれます。 セキュリティセンターに移動したときに脅威エクスプローラーが表示される場合は、Microsoft Defender for Office 365 P2 にお客ください。

Microsoft Defender for Office 365 P1 と P2 の詳細については、 **[この記事に移動](office-365-atp.md)** してください。

> [!TIP]
> エンドユーザーに関しては、EOP と Microsoft Defender for Office 365 も異なります。 EOP および Defender for Office 365 P1 では、フォーカスは *認識* されます。この2つのサービスには、ユーザーが疑わしいと思われるメールを報告して詳細な分析を行うことができるようにするための *レポートメッセージ Outlook アドイン* が含まれています。 <p> Office 365 P2 の Defender (EOP および P1 のすべての内容が含まれています) では、フォーカスがエンドユーザーのための *トレーニング* に移り、セキュリティ操作センターが強力な *脅威シミュレータ* ツールと、それが提供するエンドユーザー指標にアクセスできるようになります。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 プラン1およびプラン2のカンニングペーパー

このクイックリファレンスは、Office 365 サブスクリプションの各 Microsoft Defender に付属する機能について理解するのに役立ちます。 EOP の機能についての知識と組み合わせることにより、ビジネスの意思決定者が自分のニーズに最適な Microsoft Defender Office 365 を決定するのに役立ちます。

|Office 用 Defender 365 プラン1|Office 用 Defender 365 プラン2|
|---|---|
|構成、保護、および検出機能: <ul><li>[添付ファイル保護](atp-safe-attachments.md)</li><li>[リンク保護](atp-safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)</li><li>[Office 365 の Defender でのフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[リアルタイムの検出](threat-explorer.md)</li></ul>|Office 用 Defender (365 プラン 1) の機能 <p> --- プラスのもの --- <p> 自動化、調査、修復、教育の機能: <ul><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](office-365-air.md)</li><li>[攻撃シミュレータ](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 プラン2は、Office 365 E5、Office 365 A5、および Microsoft 365 E5 に含まれています。

- Microsoft Defender for Office 365 プラン1は、Microsoft 365 Business Premium に含まれています。

- Microsoft Defender for Office 365 プラン1および Defender for Office 365 プラン2は、それぞれ特定のサブスクリプションのアドオンとして利用できます。 詳細については、 [office 365 プランの Microsoft Defender で利用できる](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)もう1つのリンク機能を参照してください。

- [ [安全なドキュメント](safe-docs.md) ] 機能は、Microsoft 365 e5 または Microsoft 365 E5 セキュリティライセンスを持つユーザーのみが使用できます (microsoft Defender for Office 365 プランには含まれていません)。

- 現在のサブスクリプションに Microsoft Defender for Office 365 が含まれておらず、これを必要としている場合は、 [販売に連絡して試用版を開始](https://go.microsoft.com/fwlink/p/?LinkId=518644)し、microsoft Defender for office 365 が組織内でどのように動作するかを確認してください。

> [!TIP]
> ***Insider tip** _。 Docs.microsoft.com の目次を使用して、EOP と Microsoft Defender for Office 365 について学ぶことができます。 このページに戻ると、 [Office 365 のセキュリティの概要](https://docs.microsoft.com/microsoft-365/security/office-365-security)が表示されます。この目次は、サイドバーにあることがわかります。 展開 (移行を含む) が開始され、予防、検出、調査、応答が続きます。 <p> この構造体は、_ *Security Administration** トピックの後に **セキュリティ運用** に関するトピックが表示されるように分割されています。 いずれかのジョブロールの新しいメンバーである場合は、スペースの理解に役立つように、このヒントのリンクと目次の情報を使用します。 *フィードバックリンク* を必ず使用し、*記事* を参照してください。 フィードバックは、弊社が提供するものを改善するのに役立つ情報です。

## <a name="where-to-go-next"></a>[次へ]

セキュリティ管理者の場合は、メールの DKIM または DMARC の構成が必要になることがあります。 優先度の高いユーザーに対しては、「厳しい」セキュリティプリセットをロールアウトするか、製品の新機能を検索することができます。 または、セキュリティ対策を使用している場合は、リアルタイム検出または脅威エクスプローラーを活用して、攻撃シミュレータを使用したエンドユーザー検出の調査と対応を行うこともできます。 いずれにしても、次に説明する必要がある追加の推奨事項があります。

[SPF、DKIM、DMARC を含む電子メール認証 (すべての3つのセットアップへのリンクが含まれています)](email-validation-and-authentication.md)

[特定の推奨される「ゴールデン」](recommended-settings-for-eop-and-office365-atp.md) 構成を参照し、 [推奨される事前設定を使用してセキュリティポリシーを迅速に構成する](preset-security-policies.md)

[Microsoft Defender For Office 365 の新機能 (EOP 開発を含む)](whats-new-in-office-365-atp.md)をキャッチアップする

[脅威エクスプローラーまたはリアルタイム検出を使用する](threat-explorer.md)

[Microsoft Defender For Office 365 でのアタックシミュレータ](attack-simulator.md)の使用
