---
title: Office 365 セキュリティ、Microsoft Defender for Office 365、EOP、MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365 のセキュリティ、EOP から Office 365 プラン 1 および 2 の Defender、標準と厳密なセキュリティ構成など。 持っているもの、およびプロパティをセキュリティで保護する方法について理解します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f83eef6a19e26f4b8f47a049e2b2959b32a92550
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932552"
---
# <a name="office-365-security-overview"></a>Office 365 セキュリティの概要

この記事では、クラウドの新しいセキュリティ プロパティについて紹介します。 セキュリティ オペレーション センターに参加している場合でも、セキュリティ管理者が新しい場合でも、更新が必要な場合でも、作業を開始しましょう。

> [!CAUTION]
> if you're using **Outlook.com,** **Microsoft 365 Family,** or **Microsoft 365 Personal,** and need *Safe Links* or Safe *Attachments* info, * click **this link** _: Advanced Outlook.com security for [Microsoft 365 subscribers](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Office 365 セキュリティのスペル チェック

すべての Office 365 サブスクリプションには、セキュリティ機能が付属しています。 実行できる目標とアクションは、これらの異なるサブスクリプションの焦点によって異なります。 365 Officeでは、サブスクリプションの種類に関連付けられている 3 つの主要なセキュリティ サービス (製品) があります。

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 プラン 1 (Defender for Office P1)
1. Microsoft Defender for Office 365 プラン 2 (Defender for Office P2)

> [!NOTE]
> サブスクリプションを購入し、今すぐ*でセキュリティ機能を_rightする必要がある場合は、「脅威から保護する」の記事の手順 [にスキップ](protect-against-threats.md) してください。 サブスクリプションを使い始めてから始める前にライセンスを知りたい場合は [、Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage)管理センターで [請求>製品] を参照します。

Office 365 セキュリティは、EOP が提供するコア保護に基っています。 EOP は、Exchange Online メールボックスが見つかるすべてのサブスクリプションに存在します (ここで説明するセキュリティ製品はすべてクラウドベースです)。

この 3 つのコンポーネントについては、この方法で説明されているのが慣れている場合があります。

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|広範なボリューム ベースの既知の攻撃を防止します。|ゼロデイマルウェア、フィッシング、およびビジネス 電子メールの侵害から電子メールとコラボレーションを保護します。|侵害後の調査、捜ティング、対応、自動化、シミュレーション (トレーニング用) を追加します。|
|

ただし、アーキテクチャの観点から、各部分をセキュリティの累積的なレイヤーと考え、それぞれがセキュリティに重点を置いて考えてみなしましょう。 次のようにします。

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP と Microsoft Defender for Office 365 と、電子メール認証のメモなど、サービスに重点を置いてお客様との関係を示します。":::

これらの各サービスは、保護、検出、調査、応答の中から目標を強調しますが **、*** すべての _ サービス _**_ は、保護、検出、調査、および対応の任意の目標を実行できます。

Office 365 セキュリティの中核は EOP 保護です。 Microsoft Defender for Office 365 P1 には EOP が含まれている。 Defender for Office 365 P2 には P1 と EOP が含まれている。 構造体は累積的です。 このため、この製品を構成する場合は、EOP から始め、Office 365 の Defender に取り組む必要があります。

電子メール認証の構成はパブリック DNS で行いますが、スプーフィングから保護するためにこの機能を構成することが重要です。 _If you have EOP,* ***you should configure email [authentication](email-validation-and-authentication.md)**_.

Office 365 E3 以下の場合は EOP を使用できますが、アップグレードを通じて Office 365 P1 のスタンドアロン Defender を購入するオプションがあります。 365 E5 Officeしている場合は、365 P2 用の Defender Office既に存在します。

> [!TIP]
> サブスクリプションが Office 365 E3 または E5 のどちらでもない場合でも、Microsoft Defender for Office 365 P1 にアップグレードするオプションが存在しないか確認できます。 興味がある場合は、この [Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) ページに Office 365 P1 アップグレードの Microsoft Defender の対象となるサブスクリプションが一覧表示されます (ページの最後で細かい印刷を確認してください)。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Office 365 用の EOP から Microsoft Defender への Office 365 セキュリティ

![EOP と Microsoft Defender for Office 365 とそのセキュリティに重点を置いて、保護と検出から調査と対応に向かっている。 電子メール認証の構成 (少なくとも DKIM と DMARC) は、EOP 用にセットアップしてセットアップする必要があります。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> これらのページの詳細については [、「Exchange Online Protection」と「Defender](exchange-online-protection-overview.md) [for Office 365」を参照してください](office-365-atp.md)。

Office 365 プランに Microsoft Defender を追加すると、純粋な EOP 脅威管理に対する利点が一目でわかるのは困難な場合があります。 アップグレード パスが組織に適切な場合の並べ替えに役立つ、次に関する各製品の機能を見てみます。

- 脅威の防止と検出
- 調査中
- 応答中

_*Exchange Online Protection** で始まるもの:
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには以下が含まれます。<ul><li>スパム</li><li>phish</li><li>マルウェア</li><li>バルク メール</li><li>スプーフィング インテリジェンス</li><li>偽装検出</li><li>管理者検疫</li><li>誤検知と検出検出の管理者およびユーザーの送信</li><li>URL とファイルの許可/ブロック</li><li>レポート</li></u1>|<li>監査ログ検索</li><li>メッセージの追跡</li>|<li>ゼロアワー自動消去 (ZAP)</li><li>許可リストとブロック リストの絞り込みとテスト</li>|
|

EOP について掘り下げる場合は、この **[記事に移動してください](exchange-online-protection-overview.md)**。

これらの製品は累積的なので、Microsoft Defender を Office 365 P1 について評価し、サブスクライブを決定した場合は、これらの機能を追加します。

Office **365 プラン 1** (現在まで) で Defender を利用できます。
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには、EOP のすべての機能に加え、次のものが含まれます。<u1><li>安全な添付ファイル</li><li>安全なリンク<li>Microsoft Defender for Office 365 Protection for workloads (ex. SharePoint Online、Teams、OneDrive for Business)</li><li>メール、クライアント、Teams でのOffice保護</li><li>Defender for Office 365 でのフィッシング対策</li><li>ユーザーとドメインの偽装保護</li><li>アラートと、アラート用の SIEM 統合 API</li>|<li>SIEM 統合 API による検出</li><li>**リアルタイム検出ツール**</li><li>URL トレース</li>|<li>同じ</li></u1>

そのため、Microsoft Defender for Office 365 P1 は、家の **_prevention_* _ 側に展開され、追加の形式の検出が追加 _*_されます_*_。

Microsoft Defender for Office 365 P1 では、調査のために _ *リアルタイム* 検出 * も追加されます。 この脅威の検索ツールの名前は太字で示されています。これは、Defender for  Office 365 P1 を使用しているという明確な手段です。 Defender では、365 P2 Officeには表示されません。

Office **365 プラン 2** (現在まで) で Defender を利用できます。
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには、EOP と Microsoft Defender for Office 365 P1 のすべてが含まれます。<u1><li>同じ</li>|<li>**脅威エクスプローラー**</li><li>脅威トラッカー</li><li>キャンペーン ビュー</li>|<li>自動調査と対応 (AIR)</li><li>脅威エクスプローラーからの AIR</li><li>セキュリティが侵害されたユーザー向け AIR</li><li>SIEM 統合 API による自動調査</li>

そのため、Microsoft Defender for Office 365 P2 は、家の **_調査_* と対応 _ 側を拡張し、新しい捜ティングの強さを追加します。 自動化。

Microsoft Defender for Office 365 P2 では、プライマリ ハンティング ツールはリアルタイム検出ではなく *_Threat Explorer** と呼ばされています。 セキュリティ センターに移動すると脅威エクスプローラーが表示される場合は、Microsoft Defender Office 365 P2 を利用できます。

Microsoft Defender for Office 365 P1 および P2 について詳しくは、この記事 **[をご覧ください](office-365-atp.md)**。

> [!TIP]
> EOP と Office 365 用の Microsoft Defender も、エンドユーザーに関しては異なります。 EOP と Defender for Office 365 P1では、認識に重点が置かわれているので、これらの 2 つのサービスには *Outlook* アドインのレポート メッセージが含まれるので、ユーザーは疑わしいと思われるメールを報告して、さらに分析することができます。 <p> Defender for Office 365 P2 (EOP と P1 のすべての機能を含む)では、フォーカスはエンド ユーザー向けトレーニングに移り、セキュリティ オペレーションセンターは強力な脅威シミュレーター ツールとエンド ユーザーの指標にアクセスできます。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 プラン 1 とプラン 2 の詐欺シート

このクイック リファレンスは、各 Microsoft Defender for Office 365 サブスクリプションで利用できる機能を理解するのに役立ちます。 EOP 機能に関する知識を組み合わせると、ビジネスの意思決定者がニーズに最適な Office 365 用 Microsoft Defender を判断するのに役立ちます。

|Defender for Office 365 プラン 1|Defender for Office 365 プラン 2|
|---|---|
|構成、保護、および検出機能: <ul><li>[添付ファイル保護](atp-safe-attachments.md)</li><li>[リンク保護](atp-safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 でのフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[リアルタイムの検出](threat-explorer.md)</li></ul>|Defender for Office 365 プラン 1 の機能 <p> --- プラスのもの --- <p> 自動化、調査、修復、教育の機能: <ul><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](office-365-air.md)</li><li>[攻撃シミュレータ](attack-simulator.md)</li></ul>|
|

- Office 365 プラン 2 用の Microsoft Defender は、Office 365 E5、Office 365 A5、および Microsoft 365 E5 に含まれています。

- Microsoft Defender for Office 365 プラン 1 は、Microsoft 365 Business Premium に含まれています。

- Microsoft Defender for Office 365 プラン 1 と Defender for Office 365 プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして利用できます。 詳細については [、365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)プランの Microsoft Defender 全体で利用Officeリンクを示します。

- [安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Microsoft Defender for Office 365 プランには含まれません) を持つユーザーのみが利用できます。

- 現在のサブスクリプションに Office 365 用の Microsoft Defender が含まず、必要[](https://go.microsoft.com/fwlink/p/?LinkId=518644)な場合は、販売に連絡して試用版を開始し、Microsoft Defender for Office 365 が組織でどのように機能するのか確認してください。

> [!TIP]
> ***Insider tip** _. EOP と Microsoft Defender docs.microsoft.com 365 の詳細については、次の目次Officeしてください。 このページに戻り、Office [365](https://docs.microsoft.com/microsoft-365/security/office-365-security)セキュリティの概要を確認すると、目次の組織がサイド バーに表示されます。 展開 (移行を含む) から始まり、予防、検出、調査、対応に進む。 <p> この構造は、_Security *Administration** のトピックの後にセキュリティ操作のトピック **が続く構成に分** かれています。 いずれかのジョブ ロールの新しいメンバーである場合は、このヒントのリンクと目次に関する知識を使用して、スペースを学習してください。 フィードバックリンクを *使用し、記事**を評価* してください。 フィードバックは、お客様に提供する機能の改善に役立ちます。

## <a name="where-to-go-next"></a>次の移動先

セキュリティ管理者の場合は、メールの DKIM または DMARC の構成が必要な場合があります。 優先度の高いユーザーに対して "厳密" セキュリティ プリセットを展開したり、製品の新機能を探したりすることもできます。 または、セキュリティ対策を使用している場合は、リアルタイム検出または脅威エクスプローラーを利用して、攻撃シミュレータを使ってエンド ユーザーの検出を調査して対応したり、トレーニングしたりすることもできます。 どちらの場合も、次に確認する必要があるその他の推奨事項を示します。

[SPF、DKIM、DMARC などの電子メール認証 (3 つすべてのセットアップへのリンクを含む)](email-validation-and-authentication.md)

[特定の推奨される "ゴールデン" 構成](recommended-settings-for-eop-and-office365-atp.md) を確認し、推奨されるプリセットを使用してセキュリティ [ポリシーをすばやく構成する](preset-security-policies.md)

Microsoft Defender for [Office 365 (EOP](whats-new-in-office-365-atp.md)開発を含む) の新機能に関する説明

[脅威エクスプローラーまたはリアルタイムの検出を使用する](threat-explorer.md)

[Microsoft Defender で攻撃シミュレータを使用して Office 365 にアクセス](attack-simulator.md)する
