---
title: Office 365セキュリティの概要、 Microsoft Defender for Office 365 EOP、MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365 におけるセキュリティについて、EOP、Defender for Office 365 プラン 1 およびプラン 2、セキュリティの標準構成と厳格な構成の違いなどを説明します。 持っている情報を理解し、プロパティをセキュリティで保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 471817772327a761e1903d0074c41ad3a4bd5fbac1ddb501b2d8887e35d51b34
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838501"
---
# <a name="office-365-security"></a>Office 365 セキュリティ


**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)


この記事では、クラウドで利用可能な新しいセキュリティ プロパティについて紹介します。 この記事は、セキュリティ運用センターのメンバーや初めてセキュリティ管理者となったユーザーに役立つ内容となっており、セキュリティ機能を復習する目的でも利用できます。

> [!CAUTION]
> **Outlook.com**、**Microsoft 365 Family**、または **Microsoft 365 Personal** を使用していて、*安全なリンク* または *安全な添付ファイル* に関する情報が必要な場合は、***このリンクをクリックして***[「Microsoft 365 サブスクライバー用の Outlook.com の高度なセキュリティ](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

## <a name="office-365-security-spelled-out"></a>Office 365 セキュリティの説明

すべての Office 365 サブスクリプションにはセキュリティ機能が備わっています。 目標と実行可能なアクションは、これらのさまざまなサブスクリプションの目的によって異なります。 Office 365 セキュリティには、サブスクリプションの種類に結び付けられている、3 つの主なセキュリティ サービス (または製品) があります。

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 プラン 1 (Defender for Office P1)
1. Microsoft Defender for Office 365 プラン 2 (Defender for Office P2)

> [!NOTE]
> サブスクリプションを購入済みで、セキュリティ機能を今すぐ *展開* する必要がある場合は、記事「[脅威に対する保護](protect-against-threats.md)」で説明する手順にスキップしてください。 サブスクリプションを初めてご購入され、お持ちのライセンスをよく理解してからこの記事を読む場合は、[Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/#/homepage)で [課金情報] > [お使いの製品] の順に進んで情報を確認してください。

Office 365 セキュリティ は、EOP で提供される中心的な保護機能の上に構築されています。 EOP は、Exchange Online のメールボックスを使用するすべてのサブスクリプションに含まれています。 (この記事で説明するセキュリティ製品はすべてクラウドベースである点にご留意ください)。

これら 3 つのコンポーネントに関しては、次のような説明をよく目にするかもしれません。

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|広範な、ボリュームベースの既知の攻撃の防止。|ゼロデイ マルウェア、フィッシング、ビジネス メールの侵害からメールと共同作業を保護。|侵害後の調査、追求、対応のほか、オートメーションおよびシミュレーション (トレーニング用) の追加。|
|

しかし、アーキテクチャの観点から見た場合、各コンポーネントをセキュリティの累積的な層と捉え、各層にはセキュリティに関する特定の強調点があると考えることが可能です。 以下のように理解できます。

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP と Microsoft Defender for Office 365 およびこれらの間の関係とともにサービスの強調点が示され、メール認証に関するメモが含まれています":::

これらのサービスのそれぞれでは保護、検出、調査、対応のいずれかを強調していますが、***すべて** のサービスは保護、検出、調査、および対応の *_いずれの_**目標も達成できます。

Office 365 セキュリティの中心は、EOP 保護です。 Microsoft Defender for Office 365 P1 には、EOP が含まれています。 Defender for Office 365 P2 には、P1 および EOP が含まれています。 累積的な構造となっています。 このため、この製品を構成する場合は、EOP から始め、その後に Defender for Office 365 へと進む必要があります。

メール認証の構成はパブリック DNS で実行されますが、スプーフィングから保護するために、この機能を構成することが重要です。 *EOP をお持ちの場合は、****[メール認証を構成](email-validation-and-authentication.md)するようにしてください***。

Office 365 E3 以下をお持ちの場合は、EOP が含まれいますが、アップグレードを通してスタンドアロンの Defender for Office 365 P1 を購入するオプションが提供されています。 Office 365 E5 をお持ちの場合は、Defender for Office 365 P2 が含まれています。

> [!TIP]
> お持ちのサブスクリプションが Office 365 E3 と E5 のどちらでもない場合でも、Microsoft Defender for Office 365 P1 にアップグレードするオプションが提供されているかどうかを確認できます。 アップグレードを検討する場合は、Microsoft Defender for Office 365 P1へのアップグレード対象のサブスクリプションの一覧を[この Web サイト](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids)で確認できます (ページの最下部にある細則をご確認ください)。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>EOP から Microsoft Defender for Office 365 への Office 365 セキュリティの段階的構造

![EOP と Microsoft Defender for Office 365 およびそれらの保護から検出、調査、対応に至るセキュリティの強調点。 EOP 以上に対しては、メール認証の構成 (少なくとも DKIM および DMARC) を設定するようにしてください。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> 詳細については、「[Exchange Online Protection](exchange-online-protection-overview.md)」および「[Defender for Office 365](defender-for-office-365.md)」を参照してください。

Microsoft Defender for Office 365 プランを追加した場合に、EOP の脅威の管理のみを使用する場合にくらべてどのようなメリットがあるかについては、一目見ただけでは簡単には理解できません。 アップグレードがお客様の組織にとって適切かどうかを判断するために、次の面における各製品の機能を考えてみましょう。

- 脅威の防止と検出
- 調査
- 対応

まずは **Exchange Online Protection** を見てみましょう。
<p>

|防止/検出|調査|対応|
|---|---|---|
|提供されるテクノロジ:<ul><li>スパム</li><li>フィッシング</li><li>マルウェア</li><li>バルク メール</li><li>スプーフィング インテリジェンス</li><li>偽装の検出</li><li>管理者検疫</li><li>管理者とユーザーによる誤検知と検出漏れの報告</li><li>URL およびファイルの許可/禁止</li><li>レポート</li></u1>|<li>監査ログ検索</li><li>メッセージ追跡</li>|<li>ゼロアワー自動消去 (ZAP)</li><li>許可リストと禁止リストの絞り込みとテスト</li>|
|

EOP の詳細については、**[こちらの記事をご覧ください](exchange-online-protection-overview.md)**。

これらの製品の間には、累積的な関係があります。Microsoft Defender for Office 365 P1の評価を行った上でサブスクリプションを購入する場合は、以下の機能が追加されます。

**Defender for Office 365 プラン 1** で追加される機能 (現時点のもの):
<p>

|防止/検出|調査|対応|
|---|---|---|
|EOP に含まれるすべてのテクノロジに加えて:<u1><li>安全な添付ファイル</li><li>安全なリンク<li>Microsoft Defender for Office 365 によるワークロードの保護 (例: SharePoint Online、Teams、OneDrive for Business)</li><li>メール、Office クライアント、Teams でのクリック時の保護</li><li>Microsoft Defender for Office 365 のフィッシング詐欺対策</li><li>ユーザーの偽装とドメインの偽装の保護</li><li>アラートおよびアラート用 SIEM 統合 API</li>|<li>検出用 SIEM 統合 API</li><li>**リアルタイム検出ツール**</li><li>URL 追跡</li>|<li>同上</li></u1>

このように、Microsoft Defender for Office 365 P1 では、***防止** 面の機能が強化され、新たに*_検出_**手段が追加されています。

Microsoft Defender for Office 365 P1 では、調査機能として **リアルタイム検出** も追加されています。 この脅威追及機能の名前を太字にしている理由は、この機能名が表示される場合、Defender for Office 365 P1 をお持ちであることを確実に *示している* ためです。 この機能は Defender for Office 365 P2 には表示されません。

**Defender for Office 365 プラン 2** で追加される機能 (現時点のもの):
<p>

|防止/検出|調査|対応|
|---|---|---|
|EOP および Microsoft Defender for Office 365 P1に含まれるすべてのテクノロジに加えて:<u1><li>同上</li>|<li>**脅威エクスプローラー**</li><li>脅威トラッカー</li><li>キャンペーン ビュー</li>|<li>自動調査と応答 (AIR) </li><li>脅威エクスプローラーからの AIR</li><li>侵害されたユーザーの AIR</li><li>自動調査用 SIEM 統合 API</li>

このように、Microsoft Defender for Office 365 P2 では、***検出/対応*** 面の機能が強化され、新たに 自動化された追及機能が追加されています。

Microsoft Defender for Office 365 P2 のメインの追及ツールは、リアルタイム検出ではなく **脅威エクスプローラー** と呼ばれるツールです。 セキュリティ センターに移動した際に脅威エクスプローラーが表示される場合、Microsoft Defender for Office 365 P2 を使用していることを意味します。

Microsoft Defender for Office 365 P1 および P2 の詳細については、**[こちらの記事をご覧ください](defender-for-office-365.md)**。

> [!TIP]
> EOP と Microsoft Defender for Office 365 は、エンド ユーザーに関する部分でも異なります。 EOP および Defender for Office 365 P1 では、*認識* に焦点を当てています。そのため、この 2 つのサービスには *メッセージ報告用 Outlook アドイン* が含まれており、ユーザーは不信なメールを報告して詳しい分析を受けられます。 <p> Defender for Office 365 P2 (EOP と P1 のすべての機能が含まれます) の場合、焦点はエンド ユーザーの *より一層のトレーニング* に切り替わります。そのため、セキュリティ運用センターでは、強力な *脅威シミュレーター* のほか、脅威シミュレーターで提供されるエンド ユーザー指標にアクセスできます。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 プラン 1 とプラン 2 の違いに関するクイック ガイド

このクイック リファレンスは、Microsoft Defender for Office 365 のそれぞれのサブスクリプションに含まれている機能を理解する上で役立ちます。 EOP の機能に関してすでに理解している内容と組み合わせることで、企業の意思決定者はそれぞれのニーズに最適な Microsoft Defender for Office 365 のプランを特定できます。

|Microsoft Defender for Office 365 プラン 1|Defender for Office 365 プラン 2|
|---|---|
|構成、保護、および検出機能: <ul><li>[添付ファイル保護](safe-attachments.md)</li><li>[リンク保護](safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[リアルタイム検出](threat-explorer.md)</li></ul>|Defender for Office 365 プラン 1 の機能 <p> --- プラスのもの --- <p> 自動化、調査、修復、教育の機能: <ul><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](office-365-air.md)</li><li>[攻撃シミュレータ](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 プラン 2 は、Office 365 E5、Office 365 A5、Microsoft 365 E5 に含まれています。

- Microsoft Defender for Office 365 プラン 1 は、Microsoft 365 Business Premium に含まれています。

- Microsoft Defender for Office 365 プラン 1 および Microsoft Defender for Office 365 プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして提供されています。 詳細については、「[Microsoft Defender for Office 365 プラン全体での機能の可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

- [安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Microsoft Defender for Office 365 プランには含まれません) を持つユーザーのみが利用できます。

- 現在のサブスクリプションに Microsoft Defender for Office 365 が含まれていない場合に購入を希望する場合は、[営業担当者に問い合わせて試用版の使用を開始](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)し、お客様の組織にとって Microsoft Defender for Office 365 がどのようなメリットになるかを確認してください。

> [!TIP]
> ***インサイダー ヒント**: docs.microsoft.com の目次を使って EOP と Microsoft Defender for Office 365.について学ぶことができます。 このページ (「[Office 365 Security の概要](index.yml)」) に戻ると、目次の構成がサイド バーに表示されます。 展開 (移行を含む) から始まり、防止、検出、調査、対応へと続きます。 <p> この構成は、*セキュリティ管理* のトピックの下に **セキュリティ運用** のトピックが来るように分割されています。 どちらかの役割の新しいメンバーは、このヒントにあるリンクと目次から得た知識を使って、セキュリティに関する理解を深めてください。 読み進める際は、*フィードバックのリンク* を使用して、*記事を評価* してください。 Microsoft では、皆さまからのフィードバックをもとに製品やサービスの改善を図っています。

## <a name="where-to-go-next"></a>次に読むべき記事

セキュリティ管理者は、メール用に DKIM または DMARC を構成する必要がある場合があります。 優先度の高いユーザーのために "厳格な" セキュリティ のプリセットを展開したり、製品の最新情報を確認したりできます。 一方、セキュリティ運用チームのメンバーは、調査や対応でリアルタイム検出や脅威エクスプローラーを活用したり、攻撃シミュレーターを使用してエンド ユーザーによる検出のトレーニングを実施したりできます。 いずれの場合も、次にお読みいただける記事をいくつかご紹介します。

[SPF、DKIM、DMARC を含むメール認証 (3 つの技術のすべてについて、設定用のリンクが含まれています)](email-validation-and-authentication.md)

[推奨される信頼性の高い具体的な構成を確認](recommended-settings-for-eop-and-office365.md)し、[推奨されるプリセットを使用してセキュリティ ポリシーをすばやく構成する](preset-security-policies.md)

[Microsoft Defender for Office 365 の最新情報 (EOP の最新情報も含む)](whats-new-in-defender-for-office-365.md) を確認する

[脅威エクスプローラーまたはリアルタイム検出を使用する](threat-explorer.md)

[Microsoft Defender for Office 365 の攻撃シミュレーター](attack-simulator.md)を使用する
