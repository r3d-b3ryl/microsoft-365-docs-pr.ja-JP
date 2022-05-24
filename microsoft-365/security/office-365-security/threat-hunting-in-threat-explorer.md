---
title: Microsoft Defender for Office 365用の脅威エクスプローラーでの脅威の検出
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 Defender ポータルで脅威エクスプローラーまたはリアルタイム検出を使用して、脅威を効率的に調査して対応します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2c99bc2ce004156320ec8f53f6b956f7989ee056
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648825"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365用の脅威エクスプローラーでの脅威の検出

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事の内容:

- [脅威エクスプローラーのウォークスルー](#threat-explorer-walk-through)
- [メールの調査](#email-investigation)
- [電子メール修復](#email-remediation)
- [脅威ハンティング エクスペリエンスの改善](#improvements-to-threat-hunting-experience)

> [!NOTE]
> これは、**脅威エクスプローラー (エクスプローラー)**、**電子メール セキュリティ**、**エクスプローラーとリアルタイム検出** (ツール間の違い、操作に必要なアクセス許可など) に関する **3 記事シリーズ** の一部です。 このシリーズの他の 2 つの記事は、[脅威エクスプローラーと脅威エクスプローラーを使用した電子メール セキュリティ](email-security-in-microsoft-defender.md)[とリアルタイム検出です](real-time-detections.md)。

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織に [Microsoft Defender for Office 365](defender-for-office-365.md)があり、[アクセス許可](#required-licenses-and-permissions)がある場合は、**エクスプローラー** または **リアルタイム検出** を使用して脅威を検出して修復できます。

Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション**] に移動し、[**エクスプローラー]** または [**リアルタイム検出**] を選択します。 ページに直接移動するには、 <https://security.microsoft.com/threatexplorer> または <https://security.microsoft.com/realtimereports>.

これらのツールで以下のことができます。

- Microsoft 365セキュリティ機能によって検出されたマルウェアを確認する
- フィッシング URL を表示し、判定データをクリックする
- エクスプローラーのビューから自動調査と応答プロセスを開始する
- 悪意のあるメールなどを調査する

詳細については、「 [脅威エクスプローラーを使用した電子メール セキュリティ](email-security-in-microsoft-defender.md)」を参照してください。

この短いビデオでは、Microsoft Defender for Office 365を使用して電子メールやコラボレーションベースの脅威を検出して調査する方法について説明します。 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWyPRU]

## <a name="threat-explorer-walk-through"></a>脅威エクスプローラーのウォークスルー

Microsoft Defender for Office 365には、プラン 1 とプラン 2 の 2 つのサブスクリプション プランがあります。 手動で操作された脅威ハンティング ツールは、両方のプランに、異なる名前と異なる機能で存在します。

Defender for Office 365プラン 1 ではリアルタイム *検出* が使用されます。これは、プラン 2 の *脅威エクスプローラー* (*エクスプローラー* とも呼ばれる) ハンティング ツールのサブセットです。 この一連の記事では、ほとんどの例は完全な脅威エクスプローラーを使用して作成されました。 管理者は、リアルタイム検出の手順をテストして、適用場所を確認する必要があります。

**エクスプローラー** に移動すると、既定では **[マルウェア**] ページに移動しますが、[**表示**] ドロップダウンを使用してオプションを理解します。 フィッシングを探したり、脅威キャンペーンを掘り下げたりする場合は、それらのビューを選択します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/view-drop-down.png" alt-text="脅威エクスプローラーの [ビュー] ドロップダウン" lightbox="../../media/view-drop-down.png":::

セキュリティ操作 (Sec Ops) 担当者が表示するデータを選択すると、スコープがユーザー **提出** などの狭いビューであるか、 **またはすべてのメール** のようなより広いビューであるかを選択すると、 **送信者** ボタンを使用してさらにフィルター処理できます。 必ず [更新] を選択して、フィルター処理を完了してください。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/sender-drop-down.png" alt-text="脅威エクスプローラーの [送信者] ボタン" lightbox="../../media/sender-drop-down.png":::

エクスプローラーでのフォーカスの絞り込み、またはリアルタイム検出はレイヤーで考えることができます。 1 つ目は **View です**。 2 つ目は、 *フィルター処理されたフォーカス* と考えることができます。 たとえば、次のような決定を記録することで、脅威を見つける際に実行した手順を追跡できます。エクスプローラーで問題を見つけるには、[ **受信者] フィルターフォーカスの [マルウェア ビュー] を選択しました**。 これにより、手順のトレースが簡単になります。

> [!TIP]
> Sec Ops が **タグ** を使用して、高い価値のあるターゲットと見なされるアカウントをマークする場合、*タグ フィルターフォーカスを持つフィッシング ビューなどの選択を行うことができます (使用する場合は日付範囲を含めます)。* これにより、特定のフィッシング攻撃が業界で多く発生している日付など、時間範囲の間に高価値のユーザー ターゲットに向けられたフィッシングの試行が表示されます。

日付範囲コントロールを使用して、日付範囲に絞り込みを行うことができます。 ここでは、**検出テクノロジ** フィルターフォーカスを含むエクスプローラーが **[マルウェア**] ビューに表示されます。 ただし、Sec Ops チームが詳細を掘り下げるのは **、[詳細] フィルター** ボタンです。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/advanced-filter.png" alt-text="脅威エクスプローラーの [詳細設定] フィルター" lightbox="../../media/advanced-filter.png":::

**詳細フィルター** をクリックするとパネルが表示され、Sec Ops の狩人は自分でクエリを作成し、必要な情報を含めたり除外したりすることができます。 エクスプローラー ページのグラフとテーブルの両方に結果が反映されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-chart-table.png" alt-text="クエリの結果" lightbox="../../media/threat-explorer-chart-table.png":::

**[列オプション]** ボタンを使用して、最も役に立つテーブルの情報の種類を取得します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-column-options.png" alt-text="[列オプション] ボタンが強調表示されている" lightbox="../../media/threat-explorer-column-options.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/column-options.png" alt-text="[列] で使用できるオプション" lightbox="../../media/column-options.png":::

同じ mien で、表示オプションを必ずテストしてください。 異なる対象ユーザーは、同じデータの異なるプレゼンテーションによく反応します。 一部の閲覧者の場合、 **電子メール配信元** マップは、脅威の横にある **キャンペーン表示** オプションよりも、脅威が広範囲に及ぶか目立たないように表示できます。 Sec Ops では、これらのディスプレイを使用して、セキュリティと保護の必要性を強調するポイントを最適に作成したり、後で比較したりして、アクションの有効性を示すことができます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-origin-map.png" alt-text="電子メール配信元マップ" lightbox="../../media/threat-explorer-email-origin-map.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-campaign-display.png" alt-text="キャンペーンの表示オプション" lightbox="../../media/threat-explorer-campaign-display.png":::

### <a name="email-investigation"></a>メールの調査

不審なメールが表示されたら、名前をクリックして右側のポップアップを展開します。 ここでは、Sec Ops に [電子メール エンティティ ページ](mdo-email-entity-page.md) を表示できるようにするバナーを使用できます。

電子メール エンティティ ページには、[ **詳細**]、[ **添付ファイル]**、[ **デバイス**] の下に表示される内容がまとめられますが、より整理されたデータが含まれています。 これには、DMARC の結果、コピー オプションを使用した電子メール ヘッダーのプレーンテキスト表示、安全に起爆された添付ファイルに関する判定情報、およびそれらの爆発が削除されたファイル (連絡された IP アドレスとページまたはファイルのスクリーンショットを含めることができます) などが含まれます。 URL とその評決も、同様の詳細が報告されて一覧表示されます。

この段階に達すると、最後の手順である *修復* に電子メール エンティティ ページが重要になります。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-entity-page.png" alt-text="電子メール エンティティ ページ" lightbox="../../media/threat-explorer-email-entity-page.png":::

> [!TIP]
> デトネーションされた添付ファイルの結果、含まれる URL の結果、安全な電子メール プレビューなど、リッチ メール エンティティ ページ ([ **分析** ] タブで後述) の詳細については、 [こちらを](mdo-email-entity-page.md)クリックしてください。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-analysis-tab.png" alt-text="電子メール エンティティ ページの [分析] タブ" lightbox="../../media/threat-explorer-analysis-tab.png":::

### <a name="email-remediation"></a>電子メール修復

Sec Ops 担当者が電子メールが脅威であると判断したら、次のエクスプローラーまたはリアルタイム検出手順で脅威に対処し、修復します。 これを行うには、脅威エクスプローラーに戻り、問題の電子メールのチェック ボックスをオンにし、[ **アクション]** ボタンを使用します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-actions-button.png" alt-text="脅威エクスプローラーの [アクション] ボタン" lightbox="../../media/threat-explorer-email-actions-button.png":::

ここでは、アナリストは、メールをスパム、フィッシング、マルウェアとして報告する、受信者に連絡する、または自動調査と応答 (または AIR) プレイブックのトリガーを含むさらなる調査 (プラン 2 がある場合) などのアクションを実行できます。 または、メールをクリーンとして報告することもできます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-email-actions-drop-down.png" alt-text="[アクション] ドロップダウン" lightbox="../../media/threat-explorer-email-actions-drop-down.png":::

## <a name="improvements-to-threat-hunting-experience"></a>脅威ハンティング エクスペリエンスの改善

### <a name="alert-id"></a>アラート ID

アラートから脅威エクスプローラーに移動すると、 **ビュー** は **アラート ID** によってフィルター処理されます。 これはリアルタイム検出にも適用されます。 特定のアラートに関連するメッセージと、電子メールの合計 (カウント) が表示されます。 メッセージがアラートの一部であったかどうかを確認したり、そのメッセージから関連するアラートに移動したりできます。

最後に、次のようなアラート ID が URL に含まれます。 `https://https://security.microsoft.com/viewalerts`

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-Filter.png" alt-text="アラート ID のフィルター" lightbox="../../media/AlertID-Filter.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-DetailsFlyout.png" alt-text="詳細ポップアップのアラート ID" lightbox="../../media/AlertID-DetailsFlyout.png":::

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a>エクスプローラー (およびリアルタイム検出) のデータリテンション期間と試用版テナントの検索制限を拡張する

この変更の一環として、アナリストは、脅威エクスプローラーと Defender for Office P1 と P2 の両方の試用版テナントのリアルタイム検出で、30 日間 (7 日間から増加) にわたって電子メール データを検索およびフィルター処理できます。 これは、P1 と P2 E5 の両方の顧客の運用テナントには影響しません。保持の既定値は既に 30 日です。

### <a name="updated-export-limit"></a>エクスポートの制限を更新しました

脅威エクスプローラーからエクスポートできる電子メール レコードの数が 200,000 (9990) になりました。 エクスポートできる列のセットは変更されません。

### <a name="tags-in-threat-explorer"></a>脅威エクスプローラーのタグ

> [!NOTE]
> ユーザー タグ機能はプレビュー段階にあり、すべてのユーザーが使用できるわけではありません。 また、プレビューは変更される可能性があります。 リリース スケジュールの詳細については、Microsoft 365ロードマップを参照してください。

ユーザー タグは、Microsoft Defender for Office 365内のユーザーの特定のグループを識別します。 ライセンスや構成など、タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

脅威エクスプローラーでは、次のエクスペリエンスでユーザー タグに関する情報を確認できます。

#### <a name="email-grid-view"></a>電子メール グリッド ビュー

アナリストが電子メール グリッドの **[タグ** ] 列を見ると、送信者または受信者のメールボックスに適用されたすべてのタグが表示されます。 既定では、 *優先度アカウント* などのシステム タグが最初に表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-grid.png" alt-text="電子メール グリッド ビューのフィルター タグ" lightbox="../../media/tags-grid.png":::

#### <a name="filtering"></a>フィルター処理

タグはフィルターとして使用できます。 優先度アカウント間でのみハントするか、この方法で特定のユーザー タグのシナリオを使用します。 特定のタグを持つ結果を除外することもできます。 タグと他のフィルターと日付範囲を組み合わせて、調査範囲を絞り込みます。

[![タグをフィルター処理します。](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-filter-not.png" alt-text="フィルター処理されていないタグ" lightbox="../../media/tags-filter-not.png":::

#### <a name="email-detail-flyout"></a>電子メールの詳細ポップアップ

送信者と受信者の個々のタグを表示するには、メールを選択してメッセージの詳細ポップアップを開きます。 [ **概要** ] タブには、送信者タグと受信者タグが個別に表示されます。 送信者と受信者の個々のタグに関する情報は、CSV データとしてエクスポートできます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-flyout.png" alt-text="電子メールの詳細タグ" lightbox="../../media/tags-flyout.png":::

URL のクリックポップアップにもタグ情報が表示されます。 これを表示するには、[フィッシング] または [すべてのメール] ビュー> **URL** または **[URL のクリック] タブに** 移動します。個々の URL ポップアップを選択すると、その URL のクリックに関するその他の詳細 (そのクリックに関連付けられているタグなど) が表示されます。

### <a name="updated-timeline-view"></a>更新されたタイムライン ビュー

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-urls.png" alt-text="URL タグ" lightbox="../../media/tags-urls.png":::
>
[このビデオ](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)を見て詳細をご確認ください。

## <a name="extended-capabilities"></a>拡張機能

### <a name="top-targeted-users"></a>対象ユーザーの上位

[上位マルウェア ファミリ] には、[マルウェア] セクションに **対象ユーザーの上位** が表示されます。 上位の対象ユーザーは、フィッシングとすべての電子メール ビューを通じて拡張されます。 アナリストは、対象ユーザーの上位 5 人と、各ビューの各ユーザーの試行回数を確認できます。

セキュリティ操作のユーザーは、各メール ビューのオフライン分析のために、最大 3,000 人のターゲット ユーザーの一覧と試行回数をエクスポートできます。 また、試行回数 (次の図では 13 回など) を選択すると、脅威エクスプローラーでフィルター処理されたビューが開き、メール全体の詳細とそのユーザーの脅威を確認できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Top_Targeted_Users.png" alt-text="ユーザーが最もターゲットを絞った" lightbox="../../media/Top_Targeted_Users.png":::

### <a name="exchange-transport-rules"></a>Exchange トランスポート ルール

セキュリティ運用チームは、メール グリッド ビューで、メッセージに適用されたすべてのExchangeトランスポート ルール (またはメール フロー ルール) を表示できます。 グリッドで **[列] オプション** を選択し、列オプションから **[トランスポート ルールExchange追加**] を選択します。 Exchangeトランスポート ルール オプションは、電子メールの **[詳細**] ポップアップにも表示されます。

メッセージに適用されるトランスポート ルールの名前と GUID が表示されます。 アナリストは、トランスポート ルールの名前を使用してメッセージを検索できます。 これは CONTAINS 検索です。つまり、部分的な検索も行うことができます。

> [!IMPORTANT]
> トランスポート ルールの検索と名前の可用性Exchangeは、割り当てられている特定のロールによって異なります。 トランスポート ルールの名前と検索を表示するには、次のいずれかのロールまたはアクセス許可が必要です。 ただし、以下のロールやアクセス許可がなくても、アナリストはトランスポート ルールのラベルと GUID 情報を電子メールの詳細に表示できます。 電子メール グリッド、電子メール ポップアップ、フィルター、およびエクスポートのその他のレコード表示エクスペリエンスは影響を受けられません。
>
> - Exchange Onlineのみ - データ損失防止: すべて
> - Exchange Onlineのみ - O365SupportViewConfig: すべて
> - Microsoft Azure Active DirectoryまたはExchange Online - セキュリティ 管理: すべて
> - Azure Active DirectoryまたはExchange Online - セキュリティ リーダー: すべて
> - Exchange Onlineのみ - トランスポート ルール: すべて
> - Exchange Onlineのみ - View-Only構成: すべて
>
> 電子メール グリッド、詳細ポップアップ、エクスポートされた CSV 内では、次に示すように ETR に Name/GUID が表示されます。
>
> > [!div class="mx-imgBorder"]
> > :::image type="content" source="../../media/ETR_Details.png" alt-text="Exchange トランスポートのルール" lightbox="../../media/ETR_Details.png":::

### <a name="inbound-connectors"></a>受信コネクタ

コネクタは、Microsoft 365またはOffice 365組織との間の電子メールのフローをカスタマイズする手順のコレクションです。 セキュリティ制限または制御を適用できます。 脅威エクスプローラーでは、電子メールに関連するコネクタを表示し、コネクタ名を使用して電子メールを検索できます。

コネクタの検索は CONTAINS クエリです。これは、部分的なキーワード検索が機能できることを意味します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Connector_Details.png" alt-text="コネクタの詳細" lightbox="../../media/Connector_Details.png":::

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

エクスプローラーまたはリアルタイム検出を使用する[Microsoft Defender for Office 365](defender-for-office-365.md)が必要です。

- エクスプローラーは、Defender for Office 365 プラン 2 に含まれています。
- リアルタイム検出レポートは、Defender for Office 365 プラン 1 に含まれています。
- Defender for Office 365で保護する必要があるすべてのユーザーにライセンスを割り当てる計画を立てます。 エクスプローラーとリアルタイム検出では、ライセンスを持つユーザーの検出データが表示されます。

エクスプローラーまたはリアルタイム検出を表示して使用するには、次のアクセス許可が必要です。

- Microsoft 365 Defender ポータルで次の手順を実行します。
  - 組織管理
  - セキュリティ管理者 (Azure Active Directory管理センターで割り当てることができます (<https://aad.portal.azure.com>)
  - セキュリティ閲覧者
- Exchange Online:
  - 組織の管理
  - 表示専用組織の管理
  - "View-Only Recipients/表示専用受信者"
  - コンプライアンス管理

ロールとアクセス許可の詳細については、次のリソースを参照してください。

- [Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)
- [Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)
- [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>詳細

- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online、OneDrive、Microsoft Teamsで検出された悪意のあるファイルを表示する](mdo-for-spo-odb-and-teams.md)
- [脅威エクスプローラー (およびリアルタイム検出) でビューの概要を取得する](threat-explorer-views.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection での自動調査および対応](automated-investigation-response-office.md)
- [[電子メール エンティティ] ページを使用して電子メールを調査する](mdo-email-entity-page.md)
