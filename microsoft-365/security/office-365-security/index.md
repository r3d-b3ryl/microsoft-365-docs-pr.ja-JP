---
title: Office 365 セキュリティ、Microsoft Defender for Office 365、EOP、MSDO
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
description: Office 365 プラン 1 および 2、Standard vs. Strict セキュリティ構成など、EOP から Defender への Office 365 のセキュリティ。 持っているもの、およびプロパティをセキュリティで保護する方法を理解します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711942"
---
# <a name="office-365-security-overview"></a>Office 365 セキュリティの概要

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)


この記事では、クラウドの新しいセキュリティ プロパティについて紹介します。 セキュリティ 運用センターの一部である場合でも、セキュリティ管理者として新しいスペースを使用する場合も、更新プログラムが必要な場合でも、まず作業を開始します。

> [!CAUTION]
> **Outlook.com** **、Microsoft 365 ファミリ**、または Microsoft **365 Personal** を使用し、セーフ リンクまたは安全な添付ファイル情報が必要な場合は、この ***リンクをクリック*** します。 : [Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)サブスクライバーの高度な Outlook.com セキュリティ 。

## <a name="office-365-security-spelled-out"></a>Office 365 セキュリティのスペル アウト

すべての Office 365 サブスクリプションには、セキュリティ機能が付属しています。 実行できる目標とアクションは、これらの異なるサブスクリプションのフォーカスによって異なります。 365 Officeでは、サブスクリプションの種類に関連付けられている 3 つの主要なセキュリティ サービス (または製品) があります。

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 プラン 1 (Defender for Office P1)
1. Microsoft Defender for Office 365 Plan 2 (Defender for Office P2)

> [!NOTE]
> サブスクリプションを購入し、セキュリティ機能を今すぐ展開する必要がある場合は、「脅威に対する保護」の記事[の手順にスキップ](protect-against-threats.md)してください。 サブスクリプションを使い始めてからライセンスを知りたい場合は [、Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage)管理センターで [製品の請求>を参照してください。

Office 365 セキュリティ ビルドは、EOP によって提供されるコア保護に基付けされています。 EOP は、Exchange Online メールボックスが見つかるサブスクリプションに存在します (ここで説明するセキュリティ製品はすべてクラウドベースです)。

この方法で説明されているこれら 3 つのコンポーネントを見慣れている可能性があります。

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|ボリューム ベースの広範な既知の攻撃を防止します。|ゼロデイマルウェア、フィッシング、ビジネスメールの侵害から電子メールとコラボレーションを保護します。|侵害後の調査、狩猟、対応、オートメーション、シミュレーション (トレーニング用) を追加します。|
|

しかし、アーキテクチャの観点から、各部分をセキュリティの累積的な層として考え、それぞれセキュリティを重視します。 次のような詳細:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP と Microsoft Defender for Office 365 と、電子メール認証のメモを含む、サービス重視の関係。":::

これらの各サービスは、保護、検出、調査、および応答の間で目標を強調しますが、***all** _ the services は、保護、検出、調査、および応答の目標の *___* any * を実行できます。

365 セキュリティのOfficeは EOP 保護です。 Microsoft Defender for Office 365 P1 には EOP が含まれている。 365 P2 Officeの Defender には、P1 と EOP が含まれる。 構造は累積的です。 このため、この製品を構成する場合は、EOP から始め、365 用の Defender にOfficeがあります。

電子メール認証の構成はパブリック DNS で行うが、スプーフィングから防御するためにこの機能を構成することが重要です。 *EOP がある場合は、電子****メール [認証を構成する必要があります](email-validation-and-authentication.md)***。

365 E3 以下の Officeがある場合は、EOP がありますが、アップグレードを通じて 365 P1 のスタンドアロン Defender を購入Officeオプションがあります。 365 E5 Office場合は、365 P2 の Defender Officeがあります。

> [!TIP]
> サブスクリプションが 365 E3 または E5 Officeでもない場合でも、Microsoft Defender にアップグレードして 365 P1 にアップグレードするオプションOfficeできます。 興味がある場合は、この[](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids)Web ページに、Office 365 P1 アップグレードの Microsoft Defender の対象となるサブスクリプションが一覧表示されます (ページの末尾で詳細な印刷を確認してください)。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>EOP Office 365 セキュリティ ラダーから Microsoft Defender の 365 セキュリティ ラダー Office 365

![EOP と Microsoft Defender for Office 365 とそのセキュリティ重点。 EOP およびアップ用に電子メール認証構成 (少なくとも DKIM および DMARC) をセットアップする必要があります。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> これらのページの詳細については [、「Exchange Online Protection」、および「Defender](exchange-online-protection-overview.md) [for Office 365」を参照してください](office-365-atp.md)。

Microsoft Defender for Office 365 プランを純粋な EOP 脅威管理に追加するメリットは、一見するとわかりにくい場合があります。 アップグレード パスが組織に適切な場合の並べ替えに役立つには、次の場合に各製品の機能を確認します。

- 脅威の防止と検出
- 調査
- 応答

Exchange Online Protection から始 **まる:**
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには、次のものが含まれます。<ul><li>スパム</li><li>フィッシング</li><li>マルウェア</li><li>バルク メール</li><li>スプーフィング インテリジェンス</li><li>偽装の検出</li><li>管理者検疫</li><li>False Positives と False Negatives の管理者とユーザーの提出</li><li>URL とファイルの許可/ブロック</li><li>レポート</li></u1>|<li>監査ログ検索</li><li>メッセージの追跡</li>|<li>ゼロ時間自動削除 (ZAP)</li><li>許可リストとブロック リストの絞り込みとテスト</li>|
|

EOP を掘り下げる場合は、 **[この記事に移動します](exchange-online-protection-overview.md)**。

これらの製品は累積的なので、Microsoft Defender for Office 365 P1 を評価し、サブスクライブを決定した場合は、これらの機能を追加します。

**365 プラン 365 Office 1 (現在まで**) の Defender を使用した場合の利益:
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには、EOP のすべてと次のものが含まれます。<u1><li>安全な添付ファイル</li><li>安全なリンク<li>Microsoft Defender for Office 365 保護 (例: SharePoint Online、Teams、OneDrive for Business)</li><li>メール、クライアント、Teams でのクリック時Office保護</li><li>Defender for Office 365 のフィッシング対策</li><li>ユーザーとドメインの偽装保護</li><li>アラート、およびアラートの SIEM 統合 API</li>|<li>SIEM 統合 API による検出</li><li>**リアルタイム検出ツール**</li><li>URL トレース</li>|<li>同じ</li></u1>

そのため、Microsoft Defender for Office 365 P1 は、家の ***prevention** _ 側で展開され、_* 検出 **の追加形式が _追加_ されます。

Microsoft Defender for Office 365 P1 は、調査のための **リアルタイム検出も** 追加します。 この脅威ハンティング ツールの名前は太字で示されています。これは、365 P1 の Defender を使用しているという明確なOfficeです。  これは、365 P2 の Defender Office表示されません。

**365 プラン 365** Office 2 (現在まで) の Defender を使用した場合の利益:
<p>

|防止/検出|調査|対応|
|---|---|---|
|テクノロジには、EOP のすべてが含まれます。Microsoft Defender for Office 365 P1 プラス:<u1><li>同じ</li>|<li>**脅威エクスプローラー**</li><li>脅威トラッカー</li><li>キャンペーン ビュー</li>|<li>自動調査と応答 (AIR)</li><li>脅威エクスプローラーからの AIR</li><li>侵害されたユーザー向け AIR</li><li>SIEM Integration API for Automated Investigations</li>

そのため、Microsoft Defender for Office 365 P2 は、家の調査と対応の側面を拡大し、新しい狩猟の強さを追加します。 自動化。

Microsoft Defender for Office 365 P2 では、プライマリ ハンティングツールはリアルタイム検出ではなく脅威エクスプローラーと呼ばれる。 セキュリティ センターに移動するときに脅威エクスプローラーが表示される場合は、Microsoft Defender で 365 P2 Officeします。

Microsoft Defender for Office 365 P1 と P2 については、 **[この記事を参照してください](office-365-atp.md)**。

> [!TIP]
> EOP と Microsoft Defender for Office 365 は、エンドユーザーの場合も異なります。 EOP と Defender for Office 365 P1では、フォーカスは認識であり、これらの 2 つのサービスにはレポート メッセージ *Outlook* アドインが含まれるので、ユーザーは疑わしいと思われる電子メールを報告して詳細を分析できます。 <p> Defender for Office 365 P2 (EOP と P1 に含まれるもの)では、エンド ユーザー向けトレーニングにフォーカスが移り、セキュリティ オペレーションセンターは強力な脅威シミュレーター ツールとエンド ユーザーの指標にアクセスできます。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 Plan 1 vs. Plan 2 チート シート

このクイック リファレンスは、365 サブスクリプションの各 Microsoft Defender にどのような機能がOffice役立ちます。 EOP 機能に関する知識と組み合わせると、ビジネス上の意思決定者が Microsoft Defender for Office 365 のニーズに最適かを判断するのに役立ちます。

|Microsoft Defender for Office 365 プラン 1|Defender for Office 365 プラン 2|
|---|---|
|構成、保護、および検出機能: <ul><li>[添付ファイル保護](atp-safe-attachments.md)</li><li>[リンク保護](atp-safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[リアルタイムの検出](threat-explorer.md)</li></ul>|Defender for Office 365 Plan 1 の機能 <p> --- プラスのもの --- <p> 自動化、調査、修復、教育の機能: <ul><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](office-365-air.md)</li><li>[攻撃シミュレータ](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 プラン 2 は、Office 365 E5、Office 365 A5、Microsoft 365 E5 に含まれています。

- Microsoft Defender for Office 365 プラン 1 は、Microsoft 365 Business Premium に含まれています。

- Microsoft Defender for Office 365 Plan 1 および Defender for Office 365 Plan 2 は、それぞれ特定のサブスクリプションのアドオンとして利用できます。 詳細については、365 プランに関する Microsoft Defender 全体の機能Office [リンクを参照してください](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- [安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Microsoft Defender for Office 365 プランには含まれません) を持つユーザーのみが利用できます。

- 現在のサブスクリプションに Office 365 の Microsoft Defender が含まれる場合は、[](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)販売に問い合わせ、試用版を開始し、Microsoft Defender for Office 365 が組織でどのように機能できるのか確認してください。

> [!TIP]
> ***Insider tip** _. [コンテンツ] ウィンドウdocs.microsoft.comを使用して、EOP と Microsoft Defender for Officeできます。 このページに戻り [、Office 365 セキュリティ](index.md)の概要を確認すると、サイド バーに目次組織が表示されます。 展開 (移行を含む) から始まり、予防、検出、調査、および対応に進む。 <p> この構造は、_Security *Administration** のトピックの後にセキュリティ操作のトピック **が続く構成に分割** されています。 いずれかのジョブ ロールの新しいメンバーである場合は、このヒントのリンクと目次に関する知識を使用して、スペースの学習に役立ちます。 フィードバックリンクを *使用し、* 記事 *を評価* してください。 フィードバックは、お客様に提供する情報を改善するのに役立ちます。

## <a name="where-to-go-next"></a>次に移動する場所

セキュリティ管理者の場合は、メールの DKIM または DMARC を構成する必要があります。 優先度の高いユーザーに対して 'Strict' セキュリティ プリセットを展開したり、製品の新機能を探したりすることもできます。 または、Security Ops を使用している場合は、リアルタイム検出または脅威エクスプローラーを活用して、攻撃シミュレーターを使用して調査と対応を行い、エンドユーザー検出をトレーニングすることができます。 いずれにしろ、次に見る情報に関する追加の推奨事項を次に示します。

[SPF、DKIM、DMARC などの電子メール認証 (3 つすべてのセットアップへのリンク付き)](email-validation-and-authentication.md)

[特定の推奨される 'ゴールデン' 構成を確認](recommended-settings-for-eop-and-office365-atp.md) し、推奨されるプリセットを使用してセキュリティ [ポリシーをすばやく構成する](preset-security-policies.md)

Microsoft Defender for Office [365 (EOP](whats-new-in-office-365-atp.md)の開発を含む)

[脅威エクスプローラーまたはリアルタイム検出を使用する](threat-explorer.md)

Microsoft [Defender で攻撃シミュレーターを使用する (Office 365)](attack-simulator.md)
