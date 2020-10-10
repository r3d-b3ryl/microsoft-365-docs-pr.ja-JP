---
title: Office 365 Security、Office 365 ATP、EOP、ATP、MSDO
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
- m365-initiative-m365-defender
description: Office 365 のセキュリティ。 EOP から ATP プラン1および2、標準セキュリティ構成の比較など 現在の状況と、プロパティをセキュリティで保護する方法について理解します。
ms.openlocfilehash: d650a02faa21ac6ade39506d2c423dd319951bef
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413056"
---
# <a name="office-365-security-overview"></a>Office 365 のセキュリティの概要

この記事では、クラウド内の新しいセキュリティプロパティについて説明します。 セキュリティ操作センターの一部であるかどうかにかかわらず、セキュリティ管理者はこのスペースを利用しているか、またはリフレッシャーを使用したいと考えています。

> [!CAUTION]
> **Outlook.com**、 **microsoft 365 ファミリ**、または**microsoft 365 Personal**を使用していて *、安全なリンク*または安全な*添付ファイル*の情報を必要とする場合は、***このリンクをクリックし***てください。 [Microsoft 365 サブスクライバーの高度な Outlook.com セキュリティ](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="office-365-security-spelled-out"></a>Office 365 のセキュリティに関する綴り

すべての Office 365 サブスクリプションには、セキュリティ機能が付属しています。 実行できる目標と操作は、これらの異なるサブスクリプションの焦点に依存します。 Office 365 のセキュリティでは、サブスクリプションの種類に関連付けられている3つの主要なセキュリティサービス (製品) があります。

1. Exchange Online Protection (EOP)
1. Advanced Threat Protection、Plan 1 (ATP P1)
1. Advanced Threat Protection、Plan 2 (ATP P2)

> [!NOTE]
> サブスクリプションを購入し、セキュリティ機能を *今すぐ*展開する必要がある場合は、「 [脅威から保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) する」の手順に進んでください。 ご利用のお客様がご自身のサブスクリプションを初めてご利用になる場合は、 [Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/#/homepage)の製品 > 請求先を参照してください。

Office 365 は、EOP によって提供される中心的な保護に基づいて構築されています。 EOP は、Exchange Online メールボックスが存在する任意のサブスクリプションに存在します (ここで説明するすべてのセキュリティ製品はクラウドベースであることに注意してください)。

この方法で説明した3つのコンポーネントについては、よく見られます。

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|ボリュームベースの広範な既知の攻撃を防止します。    |  ゼロ日のマルウェア、フィッシング、およびビジネスメールの侵害から電子メールとコラボレーションを保護します。       | 事後違反の調査、探し、応答、自動化、シミュレーション (トレーニング用) を追加します。         |

しかし、アーキテクチャに関しては、各部分をセキュリティの累積的なレイヤーと考え、それぞれにセキュリティ上の重点を置いて始めましょう。 次のようになります。

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="Placeholder graphic":::

これらのサービスはそれぞれ、保護、検出、調査、応答の中から目標を強調していますが、 ***すべて*** のサービスが、保護、検出、調査、応答の ***いずれか*** の目標を達成できます。

Office 365 セキュリティの中核となるのは、EOP 保護です。 ATP P1 には EOP が含まれています。 ATP P2 には、P1 と EOP が含まれています。 この構造体は累積されています。 この製品を構成する際には、EOP から開始し、ATP に作業する必要があります。

電子メール認証の構成はパブリック DNS で行われますが、この機能を構成してスプーフィングを防止することが重要です。 *EOP を使用している場合は、* ***[電子メール認証を構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)する必要があり***ます。

Office 365 E3 以降がある場合は、EOP がありますが、アップグレードを通じてスタンドアロン ATP P1 を購入するオプションがあります。 Office 365 E5 がインストールされている場合は、既に ATP P2 があります。

> [!TIP]
> サブスクリプションが Office 365 E3 または E5 のどちらでもない場合でも、ATP P1 にアップグレードするオプションがあるかどうかを確認することができます。 関心がある場合は、 [この web ページ](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) に ATP P1 upgrade の対象となるサブスクリプションが一覧表示されます (詳細については、ページの最後をチェックしてください)。

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>EOP から ATP への Office 365 セキュリティのはしご

<br/>

![EOP と ATP、およびそれらのセキュリティ重視は、保護と検出から、調査と応答に進みます。メール認証の構成 (少なくとも DKIM および DMARC) は、EOP と up に対して設定する必要があります。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)


> [!IMPORTANT]
> これらのページの詳細については、「 [Exchange Online protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview)」および [「Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)」を参照してください。

ATP プランを追加することによって、純粋な EOP threat management の利点が一目でわかります。 アップグレードパスが組織に適しているかどうかを判断するには、各製品の機能を次のように確認してみましょう。

 - 脅威の防止と検出
 - うち
 - 応答

**Exchange Online Protection**以降:
<p>

|防止/検出  |調査  |返信  |
|---------|---------|---------|
| テクノロジは次のとおりです。<ul><li>スパム</li><li>フィッシング</li><li>ウェア</li><li>バルクメール</li><li>スプーフィングインテリジェンス</li><li>偽装の検出</li><li>管理者検疫</li><li>誤検知と誤検知の管理者およびユーザーの送信</li><li>Url とファイルの許可/ブロック</li><li>レポート</li></u1>|<li>監査ログ検索</li><li>メッセージの追跡</li>|<li>ゼロ時間自動削除 (ZAP)</li><li>許可リストと禁止リストの絞り込みとテスト</li>|

EOP に移動する場合は、 **[この記事に移動](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)** してください。

これらの製品は累積的なので、ATP P1 を評価してサブスクライブする場合は、これらの機能を追加します。

**Advanced Threat Protection**を使用した利点: プラン 1 (終了):
<p>

|防止/検出  |調査  |返信  |
|---------|---------|---------|
| EOP に含まれるテクノロジには、次のようなものがあります。<u1><li>安全な添付ファイル</li><li>安全なリンク<li>ワークロードの ATP 保護 (例 SharePoint Online、Teams、OneDrive for Business)</li><li>電子メール、Office クライアント、および Teams でのクリック時の保護</li><li>ATP のフィッシング対策</li><li>ユーザーおよびドメインの偽装保護</li><li>通知の SIEM 統合 API</li>|<li>検出のための SIEM 統合 API</li><li>**リアルタイム検出ツール**</li><li>URL トレース</li>|<li>同じ</li></u1>

そのため、ATP P1 は家の ***予防*** 側を拡張し、 ***検出***のための追加のフォームを追加します。

ATP P1 では **、調査のリアルタイム検出** も追加されています。 この脅威の探すツールの名前は、ATP P1 があることを *知る* ことが明確であるため、太字になっています。 ATP P2 では表示されません。

**Advanced Threat Protection**を使用した利点: プラン 2 (終了):
<p>

|防止/検出  |調査  |返信  |
|---------|---------|---------|
| EOP には、次のようなテクノロジが含まれています。<u1><li>同じ</li>|<li>**脅威エクスプローラー**</li><li>脅威トラッカー</li><li>キャンペーンビュー</li>|<li>自動化された調査と応答 (AIR)</li><li>脅威エクスプローラからの空気</li><li>侵害されたユーザーのための空気</li><li>自動調査用の SIEM 統合 API</li>

そのため、ATP P2 は、住宅の ***調査と応答*** 側を拡張し、新しい探しの強さを追加します。 自動化。

ATP P2 では、プライマリの探しているツールは、リアルタイムの検出ではなく、[ **脅威エクスプローラー** ] と呼ばれます。 セキュリティセンターに移動したときに脅威エクスプローラーが表示された場合は、ATP P2 にいます。

ATP P1 と P2 の詳細を確認するには、 **[この記事に移動](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** します。

> [!TIP]
> また、EOP と ATP は、エンドユーザーに関しても異なります。 EOP と ATP P1 では、フォーカスは *認識*されます。この2つのサービスには、ユーザーが疑わしいと思われる電子メールを報告して詳細な分析を行うことができるようにするための *レポートメッセージ Outlook アドイン* が含まれています。 <p> ATP P2 (EOP および P1 のすべての内容が含まれています) では、フォーカスがエンドユーザーのための *追加トレーニング* に移り、セキュリティ操作センターが強力な *脅威シミュレータ* ツールと、それが提供するエンドユーザー指標にアクセスできるようになります。

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP プラン1対計画2カンニングペーパー

このクイックリファレンスは、各 ATP サブスクリプションで提供される機能について理解するのに役立ちます。 EOP の機能についての知識と組み合わせることにより、ビジネス意思決定者がニーズに最も適した ATP を判断できるようになります。

|Office 365 ATP プラン 1|Office 365 ATP プラン 2|
|---|---|
|<br/>構成、保護、および検出機能: <ul><li>[添付ファイル保護](atp-safe-attachments.md)</li><li>[リンク保護](atp-safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)</li><li>[ATP のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[リアルタイムの検出](threat-explorer.md)</li></ul>|Office 365 ATP プラン 1 の機能<br/>--- プラスのもの ---<br/>自動化、調査、修復、教育の機能:</li><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[攻撃シミュレータ](attack-simulator.md)</li></ul>|
|

- Office 365 ATP プラン 2 は、Office 365 E5、Office 365 A5、および Microsoft 365 E5 に含まれています。

- Office 365 ATP プラン 1 は、Microsoft 365 Business Premium に含まれています。

- Office 365 ATP プラン 1 および Office 365 ATP プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして使用できます。 詳細については、次のリンク [機能が ATP プラン全体で利用可能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)です。

- [安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Office 365 ATP プランには含まれません) を持つユーザーのみが利用できます。

- 現在のサブスクリプションに Office 365 ATP が含まれておらず、これを使用する場合は、 [販売に連絡して試用版を開始](https://go.microsoft.com/fwlink/p/?LinkId=518644)し、atp が組織内でどのように動作するかを確認してください。

> [!TIP]
> ***Insider ヒント***。 EOP と ATP の詳細については、docs.microsoft.com の目次を参照してください。 このページに戻ると、 [Office 365 のセキュリティの概要](https://docs.microsoft.com/microsoft-365/security/office-365-security/?view=o365-worldwide)が表示されます。この目次は、サイドバーにあることがわかります。 展開 (移行を含む) が開始され、予防、検出、調査、応答が続きます。 <p> この構造体は、 **セキュリティ管理** のトピックの後に **セキュリティの運用** に関するトピックが表示されるように分割されています。 いずれかのジョブロールの新しいメンバーである場合は、スペースの理解に役立つように、このヒントのリンクと目次の情報を使用します。 *フィードバックリンク*を必ず使用し、*記事*を参照してください。 フィードバックは、弊社が提供するものを改善するのに役立つ情報です。

## <a name="where-to-go-next"></a>[次へ]

セキュリティ管理者の場合は、メールの DKIM または DMARC の構成が必要になることがあります。 優先度の高いユーザーに対しては、「厳しい」セキュリティプリセットをロールアウトするか、製品の新機能を検索することができます。 または、セキュリティ対策を使用している場合は、リアルタイム検出または脅威エクスプローラーを活用して、攻撃シミュレータを使用したエンドユーザー検出の調査と対応を行うこともできます。 いずれにしても、次に説明する必要がある追加の推奨事項があります。

[SPF、DKIM、DMARC を含む電子メール認証 (すべての3つのセットアップへのリンクが含まれています)](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)

[特定の推奨される「ゴールデン」](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 構成を参照し、 [推奨される事前設定を使用してセキュリティポリシーを迅速に構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies)

[Office 365 ATP の新機能 (EOP 開発を含む)](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)をキャッチアップ

[脅威エクスプローラーまたはリアルタイム検出を使用する](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)

[Office 365 ATP でのアタックシミュレータの](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)使用