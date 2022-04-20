---
title: 脅威エクスプローラーとリアルタイム検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 Defender ポータルでエクスプローラーとリアルタイムの検出を使用して、脅威を効率的に調査して対応します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8a5029ad6de3de33eacdf814729ed2eafcd2cf89
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941679"
---
# <a name="threat-explorer-and-real-time-detections"></a>脅威エクスプローラーとリアルタイム検出

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織に [Microsoft Defender for Office 365](defender-for-office-365.md)があり、[必要なアクセス許可](#required-licenses-and-permissions)がある場合は、**エクスプローラー** または **リアルタイム検出** (以前 *のリアルタイム レポート* - [新着情報を参照](#new-features-in-threat-explorer-and-real-time-detections)) があります。 セキュリティ & コンプライアンス センターで **、脅威の管理** に移動し、**エクスプローラー**_または_**リアルタイム検出** を選択します。

|Microsoft Defender for Office 365 プラン 2 では、次の情報が表示されます。|Microsoft Defender for Office 365プラン 1 では、次の情報が表示されます。|
|---|---|
|![脅威エクスプローラー。](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|

エクスプローラーまたはリアルタイム検出は、セキュリティ運用チームが脅威を効率的に調査して対応するのに役立ちます。 レポートは次の図のようになります。

:::image type="content" source="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png" alt-text="セキュリティ & コンプライアンス ポータルの [エクスプローラー] メニュー項目" lightbox="../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png":::

このレポートを使用すると、次のことができます。

- [Microsoft 365セキュリティ機能によって検出されたマルウェアを確認する](#see-malware-detected-in-email-by-technology)
- [フィッシング URL を表示し、判定データをクリックする](#view-phishing-url-and-click-verdict-data)
- [エクスプローラーのビューから自動調査と応答プロセスを開始](#start-automated-investigation-and-response)する (プラン 2 のみDefender for Office 365)
- [悪意のあるメールなどを調査する](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a>脅威ハンティング エクスペリエンスの改善


### <a name="introduction-of-alert-id-for-defender-for-office-365-alerts-within-explorerreal-time-detections"></a>エクスプローラー/リアルタイム検出内でのDefender for Office 365アラートのアラート ID の概要

現在、アラートから脅威エクスプローラーに移動すると、エクスプローラー内でフィルター処理されたビューが開き、そのビューはアラート ポリシー ID でフィルター処理されます (ポリシー ID はアラート ポリシーの一意の識別子です)。
この統合の関連性を高めるには、Threat Explorer とリアルタイム検出でアラート ID (以下のアラート ID の例を参照) を導入し、特定のアラートに関連するメッセージとメールの数を確認します。 また、メッセージがアラートの一部であったかどうかを確認したり、そのメッセージから特定のアラートに移動したりすることもできます。

アラート ID は、個々のアラートを表示するときに URL 内で使用できます。の例を示します `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-Filter.png" alt-text="アラート ID のフィルター処理" lightbox="../../media/AlertID-Filter.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/AlertID-DetailsFlyout.png" alt-text="詳細ポップアップのアラート ID" lightbox="../../media/AlertID-DetailsFlyout.png":::

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days"></a>エクスプローラー (およびリアルタイム検出) のデータ保有期間と試用版テナントの検索制限を 7 日から 30 日に延長する

この変更の一環として、Defender for Office P1 および P2 試用版テナントの両方の脅威エクスプローラー/リアルタイム検出で、30 日間 (過去 7 日間の増加) にわたって電子メール データを検索およびフィルター処理できます。
これは、既に 30 日間のデータリテンションと検索機能を備えている P1 および P2/E5 の両方の顧客の運用テナントには影響しません。

### <a name="updated-limits-for-export-of-records-for-threat-explorer"></a>脅威エクスプローラーのレコードのエクスポートの制限を更新しました

この更新プログラムの一環として、脅威エクスプローラーからエクスポートできる電子メール レコードの行数が 9990 から 200,000 レコードに増加します。 現在エクスポートできる列のセットは変わりませんが、行数は現在の制限から増加します。

### <a name="tags-in-threat-explorer"></a>脅威エクスプローラーのタグ

> [!NOTE]
> ユーザー タグ機能は *プレビュー段階* にあり、すべてのユーザーが使用できず、変更される可能性があります。 リリース スケジュールの詳細については、Microsoft 365ロードマップを参照してください。

ユーザー タグは、Microsoft Defender for Office 365内のユーザーの特定のグループを識別します。 ライセンスや構成など、タグの詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

脅威エクスプローラーでは、次のエクスペリエンスでユーザー タグに関する情報を確認できます。

#### <a name="email-grid-view"></a>電子メール グリッド ビュー

電子メール グリッドの **[タグ** ] 列には、送信者または受信者のメールボックスに適用されたすべてのタグが含まれています。 既定では、優先度アカウントなどのシステム タグが最初に表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-grid.png" alt-text="電子メール グリッド ビューのフィルター タグ" lightbox="../../media/tags-grid.png":::

#### <a name="filtering"></a>フィルター処理

タグをフィルターとして使用できます。 優先度の高いアカウントまたは特定のユーザー タグのシナリオ間だけでハントします。 特定のタグを持つ結果を除外することもできます。 この機能を他のフィルターと組み合わせて、調査範囲を絞り込みます。

[![タグをフィルター処理します。](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-filter-not.png" alt-text="フィルター処理されていないタグ" lightbox="../../media/tags-filter-not.png":::

#### <a name="email-detail-flyout"></a>電子メールの詳細ポップアップ

送信者と受信者の個々のタグを表示するには、件名を選択してメッセージの詳細ポップアップを開きます。 [ **概要** ] タブでは、送信者タグと受信者タグがメールに存在する場合は、個別に表示されます。
送信者と受信者の個々のタグに関する情報は、エクスポートされた CSV データにも及び、これらの詳細は 2 つの個別の列で確認できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-flyout.png" alt-text="電子メールの詳細タグ" lightbox="../../media/tags-flyout.png":::

URL のクリックポップアップにもタグ情報が表示されます。 表示するには、[フィッシング] または [すべてのメール] ビューに移動し、[ **URL]** または [ **URL のクリック** ] タブに移動します。個々の URL ポップアップを選択すると、その URL のクリックに関する追加の詳細 (そのクリックに関連付けられたタグなど) が表示されます。

### <a name="updated-timeline-view"></a>更新されたタイムライン ビュー

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tags-urls.png" alt-text="URL タグ" lightbox="../../media/tags-urls.png":::
>
[このビデオ](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)を見て詳細をご確認ください。

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>脅威ハンティング エクスペリエンスの改善 (予定)

### <a name="updated-threat-information-for-emails"></a>メールの脅威情報を更新しました

メール レコードのデータの正確性と一貫性を高めるために、プラットフォームとデータ品質の向上に重点を置いています。 機能強化には、ZAP プロセスの一環として電子メールで実行されるアクションなど、配信前と配信後の情報を 1 つのレコードに統合する機能が含まれます。 スパム判定、エンティティ レベルの脅威 (悪意のある URL など)、最新の配信場所などの追加の詳細も含まれます。

これらの更新後、メッセージに影響を与える配信後のさまざまなイベントに関係なく、メッセージごとに 1 つのエントリが表示されます。 アクションには、ZAP、手動修復 (管理者アクションを意味する)、 [動的配信](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)などがあります。

マルウェアやフィッシングの脅威を表示するだけでなく、メールに関連付けられているスパムの判定も表示されます。 電子メール内で、電子メールに関連付けられているすべての脅威と、対応する検出テクノロジを確認します。 電子メールには、0、1、または複数の脅威を含めることができます。 メール ポップアップの **[詳細** ] セクションに現在の脅威が表示されます。 複数の脅威 (マルウェアやフィッシングなど) の場合、 **検出技術** フィールドには、脅威を特定した検出テクノロジである脅威検出マッピングが表示されます。

検出テクノロジのセットには、新しい検出方法とスパム検出テクノロジが含まれるようになりました。 同じ検出テクノロジのセットを使用して、さまざまなメール ビュー (マルウェア、フィッシング、すべての電子メール) で結果をフィルター処理できます。

> [!NOTE]
> 判定分析は、必ずしもエンティティに関連付けられているとは限りません。 たとえば、メールはフィッシングまたはスパムとして分類されますが、フィッシング/スパムの判定でスタンプされた URL はありません。 これは、フィルターによって、判定を割り当てる前にメールのコンテンツやその他の詳細も評価されるためです。

#### <a name="threats-in-urls"></a>URL 内の脅威

これで、[電子メール ポップアップの **詳細** ] タブで URL の特定の脅威を確認できるようになりました。脅威は *、マルウェア*、 *フィッシング*、 *スパム*、 *またはなし* である可能性があります)。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/URL_Threats.png" alt-text="URL の脅威" lightbox="../../media/URL_Threats.png":::

### <a name="updated-timeline-view-upcoming"></a>更新されたタイムライン ビュー (予定)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Email_Timeline.png" alt-text="更新されたタイムライン ビュー" lightbox="../../media/Email_Timeline.png":::

タイムライン ビューは、すべての配信イベントと配信後イベントを識別します。 これには、これらのイベントのサブセットについて、その時点で特定された脅威に関する情報が含まれます。 タイムライン ビューには、実行された追加のアクション (ZAP や手動修復など) とそのアクションの結果に関する情報も表示されます。 タイムライン ビューの情報には、次のものが含まれます。

- **ソース：** イベントのソース。 管理者/システム/ユーザーを指定できます。
- **イベント：** 元の配信、手動修復、ZAP、提出、動的配信などの最上位レベルのイベントが含まれます。
- **アクション：** ZAP または管理者アクションの一部として実行された特定のアクション (論理的な削除など)。
- **脅威：** その時点で特定された脅威 (マルウェア、フィッシング、スパム) について説明します。
- **結果/詳細:** ZAP/admin アクションの一部として実行されたかどうかなど、アクションの結果の詳細。

### <a name="original-and-latest-delivery-location"></a>元の配送先と最新の配送先

現在、メール グリッドと電子メール ポップアップに配信場所を表示しています。 **[配信場所]** フィールドの名前が **_元の配信場所_*_に変更されました。また、別のフィールドである _*_Latest 配信場所_ を紹介** します。

**元の配信場所** には、最初にメールが配信された場所に関する詳細情報が表示されます。 **最新の配信場所** には、 *ZAP* などのシステム アクションや削除済み *アイテムへの移動* などの管理者アクションの後に電子メールが届いた場所が示されます。 最新の配信場所は、メッセージの配信後の最後の既知の場所、またはシステム/管理者のアクションを管理者に伝えることを目的としています。 電子メールにはエンド ユーザーアクションは含まれません。 たとえば、ユーザーがメッセージを削除した場合、またはメッセージをアーカイブ/pst に移動した場合、メッセージ "配信" の場所は更新されません。 ただし、システム アクションによって場所が更新された場合 (たとえば、ZAP によって電子メールが検疫に移動した場合)、 **最新の配信場所** は "検疫" と表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Updated_Delivery_Location.png" alt-text="更新された配信場所" lightbox="../../media/Updated_Delivery_Location.png":::

> [!NOTE]
> **配信場所** と **配信アクション** が "不明" と表示される場合がいくつかあります。
>
> - メッセージが配信された場合は **配信場所** が "配信済み" で **、配信場所** が "不明" と表示される場合がありますが、受信トレイルールによって、受信トレイフォルダーや迷惑メール フォルダーではなく、既定のフォルダー (下書きまたはアーカイブなど) にメッセージが移動されました。
>
> - 管理者/システムアクション (ZAP など) が試行されたが、メッセージが見つからなかった場合、**最新の配信場所** は不明になる可能性があります。 通常、アクションは、ユーザーがメッセージを移動または削除した後に行われます。 このような場合は、タイムライン ビューで **[結果]/[詳細]** 列を確認します。 "ユーザーによって移動または削除されたメッセージ" ステートメントを探します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Updated_Timeline_Delivery_Location.png" alt-text="タイムラインの配信場所" lightbox="../../media/Updated_Timeline_Delivery_Location.png":::

### <a name="additional-actions"></a>その他のアクション

電子メールの配信後に *追加のアクション* が適用されました。 *ZAP*、*手動修復* (論理的な削除などの管理者が実行したアクション)、*動的配信*、*再処理* (遡及的に良好と検出された電子メールの場合) を含めることができます。

> [!NOTE]
> 保留中の変更の一環として、配信アクション フィルターに現在表示されている "ZAP によって削除済み" の値は削除されます。 **追加** アクションを使用して ZAP 試行ですべてのメールを検索する方法があります。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Additional_Actions.png" alt-text="エクスプローラーのその他のアクション" lightbox="../../media/Additional_Actions.png":::

### <a name="system-overrides"></a>システムオーバーライド

*システムオーバーライド* を使用すると、メッセージの意図した配信場所に対して例外を作成できます。 フィルター処理スタックによって識別された脅威やその他の検出に基づいて、システムによって提供される配信場所をオーバーライドします。 システムオーバーライドは、テナントポリシーまたはユーザー ポリシーを使用して設定して、ポリシーによって提案されたとおりにメッセージを配信できます。 オーバーライドは、ユーザーによって設定された過度に広範なセーフ送信者ポリシーなど、構成のギャップが原因で悪意のあるメッセージの意図しない配信を識別できます。 これらのオーバーライド値には、次の値を指定できます。

- ユーザー ポリシーで許可: ユーザーは、ドメインまたは送信者を許可するポリシーをメールボックス レベルで作成します。

- ユーザー ポリシーでブロック: ユーザーは、ドメインまたは送信者をブロックするポリシーをメール ボックス レベルで作成します。

- 組織ポリシーで許可: 組織のセキュリティ チームは、組織内のユーザーの送信者とドメインを許可するポリシーまたはExchangeメール フロー ルール (トランスポート ルールとも呼ばれます) を設定します。 これは、一連のユーザーまたは組織全体に対して行うことができます。

- 組織ポリシーによってブロックされる: 組織のセキュリティ チームは、組織内のユーザーの送信者、ドメイン、メッセージ言語、またはソース IP をブロックするポリシーまたはメール フロー ルールを設定します。 これは、一連のユーザーまたは組織全体に適用できます。

- 組織ポリシーによってブロックされるファイル拡張子: 組織のセキュリティ チームは、マルウェア対策ポリシー設定を使用してファイル名拡張子をブロックします。 これらの値が電子メールの詳細に表示され、調査に役立ちます。 Secops チームは、リッチ フィルター機能を使用して、ブロックされたファイル拡張子をフィルター処理することもできます。

[![エクスプローラーのシステム オーバーライド。](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/System_Overrides_Grid.png" alt-text="エクスプローラーでグリッドをオーバーライドするシステム" lightbox="../../media/System_Overrides_Grid.png":::

### <a name="improvements-for-the-url-and-clicks-experience"></a>URL とクリックエクスペリエンスの機能強化

機能強化には、次のものが含まれます。

- URL ポップアップの **[クリック** ] セクションに、完全にクリックされた URL (URL の一部であるクエリ パラメーターを含む) を表示します。 現在、URL ドメインとパスはタイトル バーに表示されます。 その情報を拡張して、完全な URL を表示します。

- URL フィルター間の修正 (*URL* と *URL ドメインと URL ドメイン**とパス*): 更新プログラムは、URL/クリックの判定を含むメッセージの検索に影響します。 プロトコルに依存しない検索のサポートを有効にしたので、URL を使用 `http`せずに検索できます。 既定では、別の値が明示的に指定されていない限り、URL 検索は http にマップされます。 例:
  - **URL**、**URL ドメイン**、URL **ドメイン、およびパス** フィルター フィールドでプレフィックスの有無にかかわらず`http://`検索します。 検索には同じ結果が表示されます。
  - URL でプレフィックスを `https://` 検索 **します**。 値が指定されていない場合、 `http://` プレフィックスが想定されます。
  - `/` は、 **URL パス**、 **URL ドメイン、URL ドメイン**、パス フィールドの先頭 **と** 末尾で無視されます。 `/`**URL** フィールドの末尾では無視されます。

### <a name="phish-confidence-level"></a>フィッシングの信頼度レベル

フィッシングの信頼レベルは、メールが "フィッシング" として分類された信頼度を特定するのに役立ちます。 指定できる 2 つの値は *High* と *Normal です*。 初期段階では、このフィルターは脅威エクスプローラーのフィッシング ビューでのみ使用できます。

[![エクスプローラーのフィッシング信頼度レベル。](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL シグナル

ZAP URL シグナルは、通常、電子メールがフィッシングとして識別され、配信後に削除された ZAP フィッシング アラート シナリオに使用されます。 このシグナルは、アラートと対応する結果をエクスプローラーで接続します。 アラートの IOC の 1 つです。

ハンティング プロセスを改善するために、脅威エクスプローラーとリアルタイム検出が更新され、ハンティング エクスペリエンスの一貫性が向上しました。 変更の概要を次に示します。

- [タイムゾーンの機能強化](#timezone-improvements)
- [更新プロセスでの更新](#update-in-the-refresh-process)
- [フィルターに追加するグラフのドリルダウン](#chart-drilldown-to-add-to-filters)
- [製品情報の更新プログラム内](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>ユーザー タグでフィルター処理する

システムまたはカスタム のユーザー タグを並べ替えてフィルター処理し、脅威の範囲をすばやく把握できるようになりました。 詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。

> [!IMPORTANT]
> 現在、ユーザー タグによるフィルター処理と並べ替えはパブリック プレビュー段階です。 この機能は、商用リリースされる前に大幅に変更される可能性があります。 Microsoft は、明示的または黙示的に、提供された情報に関して一切の保証を行いません。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/threat-explorer-tags.png" alt-text="エクスプローラーの [Tags] 列" lightbox="../../media/threat-explorer-tags.png":::

### <a name="timezone-improvements"></a>タイムゾーンの機能強化

ポータルとエクスポートされたデータの電子メール レコードのタイム ゾーンが表示されます。 メール グリッド、詳細ポップアップ、電子メール タイムライン、類似メールなどのエクスペリエンス間で表示されるため、結果セットのタイム ゾーンが明確になります。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/TimezoneImprovements.png" alt-text="エクスプローラーでタイム ゾーンを表示する" lightbox="../../media/TimezoneImprovements.png":::

### <a name="update-in-the-refresh-process"></a>更新プロセスでの更新

一部のユーザーは、自動更新の混乱についてコメントしています (たとえば、日付を変更するとすぐにページが更新されます)、手動更新 (他のフィルターの場合)。 同様に、フィルターを削除すると自動更新につながります。 クエリの変更中にフィルターを変更すると、一貫性のない検索エクスペリエンスが発生する可能性があります。 これらの問題を解決するために、手動フィルター処理メカニズムに移行します。

エクスペリエンスの観点から、ユーザーはフィルターセットと日付からさまざまな範囲のフィルターを適用および削除し、更新ボタンを選択してクエリを定義した後に結果をフィルター処理できます。 画面で [更新] ボタンも強調されるようになりました。 また、関連するツールヒントと製品内ドキュメントも更新しました。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/ManualRefresh.png" alt-text="結果をフィルター処理する [更新] ボタン" lightbox="../../media/ManualRefresh.png":::

### <a name="chart-drilldown-to-add-to-filters"></a>フィルターに追加するグラフのドリルダウン

凡例の値をグラフに表示して、それらをフィルターとして追加できるようになりました。 [ **更新** ] ボタンを選択して結果をフィルター処理します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/ChartDrilldown.png" alt-text="フィルター処理するグラフをドリルダウンする" lightbox="../../media/ChartDrilldown.png":::

### <a name="in-product-information-updates"></a>製品内情報の更新

グリッド内の検索結果の合計数など、製品内で追加の詳細を利用できるようになりました (以下を参照)。 フィルター、検索エクスペリエンス、結果セットに関する詳細情報を提供するために、ラベル、エラー メッセージ、ツールヒントが改善されました。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/ProductInfo.png" alt-text="表示する製品内情報" lightbox="../../media/ProductInfo.png":::

## <a name="extended-capabilities-in-threat-explorer"></a>脅威エクスプローラーの拡張機能

### <a name="top-targeted-users"></a>対象ユーザーの上位

現在、メールの [マルウェア] ビューの [上位マルウェア ファミリ] セクションで、対象の上位ユーザーの一覧 **を** 公開しています。 このビューは、[フィッシング] ビューと [すべてのメール] ビューでも拡張されます。 対象ユーザーの上位 5 人と、対応するビューに対する各ユーザーの試行回数を確認できます。 たとえば、フィッシング ビューの場合、フィッシングの試行回数が表示されます。

対象ユーザーの一覧 (最大 3,000 件) と、各メール ビューのオフライン分析の試行回数をエクスポートできます。 さらに、試行回数 (次の図では 13 回など) を選択すると、脅威エクスプローラーでフィルター処理されたビューが開き、そのユーザーのメールや脅威の詳細を確認できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Top_Targeted_Users.png" alt-text="ターゲットの上位のユーザー" lightbox="../../media/Top_Targeted_Users.png":::

### <a name="exchange-transport-rules"></a>Exchange トランスポート ルール

データ エンリッチメントの一環として、メッセージに適用されたすべてのさまざまなExchangeトランスポート ルール (ETR) を確認できます。 この情報は、[電子メール] グリッド ビューで確認できます。 表示するには、グリッドで **[列] オプション** を選択し、列オプションから **[トランスポート ルールExchange追加**] を選択します。 メールの **[詳細** ] ポップアップにも表示されます。

メッセージに適用されたトランスポート ルールの GUID と名前の両方を確認できます。 トランスポート ルールの名前を使用してメッセージを検索できます。 これは "Contains" 検索です。つまり、部分的な検索も行うことができます。

> [!IMPORTANT]
> ETR 検索と名前の可用性は、割り当てられている特定のロールによって異なります。 ETR 名を表示して検索するには、次のいずれかのロール/アクセス許可が必要です。 これらのロールが割り当てられていない場合は、トランスポート ルールの名前を表示したり、ETR 名を使用してメッセージを検索したりすることはできません。 ただし、電子メールの詳細には ETR ラベルと GUID 情報が表示されます。 電子メール グリッド、電子メール ポップアップ、フィルター、およびエクスポートのその他のレコード表示エクスペリエンスは影響を受けられません。
>
> - EXO のみ - データ損失防止: すべて
> - EXO のみ - O365SupportViewConfig: すべて
> - Microsoft Azure Active Directoryまたは EXO - セキュリティ管理者: すべて
> - AADまたは EXO - セキュリティ リーダー: すべて
> - EXO のみ - トランスポート ルール: すべて
> - EXO のみ - View-Only構成: すべて
>
> 電子メール グリッド、詳細ポップアップ、エクスポートされた CSV 内では、次に示すように ETR に Name/GUID が表示されます。
>
> > [!div class="mx-imgBorder"]
> > :::image type="content" source="../../media/ETR_Details.png" alt-text="Exchange トランスポート ルール" lightbox="../../media/ETR_Details.png":::

### <a name="inbound-connectors"></a>受信コネクタ

コネクタは、Microsoft 365またはOffice 365組織との間の電子メールのフローをカスタマイズする手順のコレクションです。 セキュリティ制限または制御を適用できます。 脅威エクスプローラー内で、電子メールに関連するコネクタを表示し、コネクタ名を使用して電子メールを検索できるようになりました。

コネクタの検索は本質的に "含まれている" ため、部分的なキーワード検索も機能する必要があります。 メイン グリッド ビュー、詳細ポップアップ、エクスポートされた CSV 内で、コネクタは次のように Name/GUID 形式で表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/Connector_Details.png" alt-text="コネクタの詳細" lightbox="../../media/Connector_Details.png":::

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>脅威エクスプローラーとリアルタイム検出の新機能

- [偽装されたユーザーとドメインに送信されたフィッシングメールを表示する](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [電子メール ヘッダーをプレビューし、電子メール本文をダウンロードする](#preview-email-header-and-download-email-body)
- [電子メール タイムライン](#email-timeline)
- [URL クリック データをエクスポートする](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a>偽装されたユーザーとドメインに送信されたフィッシングメールを表示する

偽装されたユーザーとドメインに対するフィッシング詐欺の試行を特定するには、保護するユーザーの一覧 *に追加する* 必要があります。 ドメインの場合、管理者は *組織のドメイン* を有効にするか、ドメイン名を *Domains に追加して保護する* 必要があります。 保護するドメインは、[*偽装*] セクションの [*フィッシング詐欺対策] ポリシー ページ* にあります。

フィッシング メッセージを確認し、偽装されたユーザーまたはドメインを検索するには、エクスプローラーの [[電子メール >フィッシング] ビュー](threat-explorer-views.md) を使用します。

この例では、脅威エクスプローラーを使用します。

1. [セキュリティ & コンプライアンス センター](https://protection.office.com)で (https://protection.office.com)脅威管理> エクスプローラー (またはリアルタイム検出) を選択します)。

2. [表示] メニューの [メール >フィッシング] を選択します。

   ここでは、 **偽装されたドメイン** または **偽装されたユーザーを** 選択できます。

3. **[****偽装されたドメイン**] を選択し、テキスト ボックスに保護されたドメインを入力します。

   たとえば、 *contoso*、 *contoso.com、contoso.com.au* などの保護されたドメイン名 *を検索します*。

4. [電子メール >] タブの [詳細] タブで [件名] を選択すると、偽装されたドメインや検出された場所などの追加の偽装情報が表示されます。

    **OR**

    [ **偽装されたユーザー** ] を選択し、テキスト ボックスに保護されたユーザーの電子メール アドレスを入力します。

    > [!TIP]
    > **最適な結果を得るには**、 *完全な電子メール アドレスを* 使用して、保護されたユーザーを検索します。 ユーザーの偽装を調査する場合など、 *firstname.lastname@contoso.com* を検索すると、保護されたユーザーが迅速かつ正常に見つかります。 保護されたドメインを検索する場合、検索はルート ドメイン (たとえば、contoso.com) とドメイン名 (contoso) を取得 *します*。 ルート ドメイン *contoso.com* を検索すると、 *contoso.com* の偽装と *ドメイン名 contoso* の両方が返されます。

5. [**電子メール] タブ****の [件名] タブ** > を選択すると、ユーザーまたはドメインに関するその他の偽装情報と *検出された場所が表示されます*。

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="検出場所と検出された脅威を示す保護されたユーザーの脅威エクスプローラーの詳細ウィンドウ (ここでは、ユーザーのフィッシング偽装)" lightbox="../../media/threat-ex-views-impersonated-user-image.png":::

> [!NOTE]
> 手順 3 または 5 では、 **検出テクノロジ** を選択し、[ **偽装ドメイン** ] または [ **偽装ユーザー** ] をそれぞれ選択した場合、ユーザーまたはドメインに関する [ **電子メール] タブ** > **の情報が [Details] タブ** に表示され、 *検出された場所* は *、[フィッシング対策] ポリシー* ページに表示されているユーザーまたはドメインに関連するメッセージにのみ表示されます。

### <a name="preview-email-header-and-download-email-body"></a>電子メール ヘッダーをプレビューし、電子メール本文をダウンロードする

これで、メール ヘッダーをプレビューし、脅威エクスプローラーで電子メール本文をダウンロードできるようになりました。 管理者は、ダウンロードしたヘッダーや電子メール メッセージを分析して脅威を分析できます。 電子メール メッセージをダウンロードすると情報が漏洩するリスクがあるため、このプロセスはロールベースのアクセス制御 (RBAC) によって制御されます。 すべてのメール メッセージ ビューでメールをダウンロードする機能を付与するには、新しいロール *であるプレビュー* が必要です。 ただし、電子メール ヘッダーを表示する場合、追加のロールは必要ありません (脅威エクスプローラーでメッセージを表示するために必要な役割以外)。 プレビュー ロールを使用して新しい役割グループを作成するには:

1. Data Investigator や電子情報開示マネージャーなど、プレビュー ロールのみを持つ組み込みの役割グループを選択します。
2. [ **役割グループのコピー**] を選択します。
3. 新しい役割グループの名前と説明を選択し、[ **次へ**] を選択します。
4. 必要に応じてロールを追加および削除し、プレビュー ロールを残してロールを変更します。
5. メンバーを追加し、[ **役割グループの作成**] を選択します。

エクスプローラーとリアルタイム検出では、電子メール メッセージが届く場所をより完全に把握できる新しいフィールドも取得されます。 これらの変更により、Security Ops の捜索が容易になります。 しかし、主な結果は、問題のある電子メール メッセージの場所を一目で把握できます。

これはどのように行われますか? 配信状態は次の 2 つの列に分けられます。

- **配信アクション** - 電子メールの状態。
- **配信場所** - 電子メールがルーティングされた場所。

*配信アクション* は、既存のポリシーまたは検出が原因で電子メールに対して実行されるアクションです。 電子メールの可能なアクションを次に示します。

|配信|ぽんこつ|Blocked|交換|
|---|---|---|---|
|電子メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーはそれにアクセスできます。|電子メールがユーザーの迷惑メールフォルダーまたは削除済みフォルダーに送信され、ユーザーはそれにアクセスできます。|検疫された、失敗した、または削除された電子メール。 これらのメールは、ユーザーがアクセスできません。|メールには、悪意のある添付ファイルが、悪意のある添付ファイルであることを示す.txt ファイルに置き換えられました。|

ユーザーが表示できる内容と表示できない内容を次に示します。

|エンド ユーザーがアクセス可能|エンド ユーザーがアクセスできない|
|---|---|
|配信|Blocked|
|ぽんこつ|交換|

**配信場所** には、配信後に実行されるポリシーと検出の結果が表示されます。 **_配信アクション_** にリンクされています。 次の値を指定できます。

- *受信トレイまたはフォルダー*: 電子メールは受信トレイまたはフォルダーにあります (メール ルールに従います)。
- *オンプレミスまたは外部*: メールボックスはクラウドには存在せず、オンプレミスです。
- *迷惑メール フォルダー*: 電子メールはユーザーの迷惑メール フォルダーにあります。
- *削除済みアイテム フォルダー*: ユーザーの削除済みアイテム フォルダー内の電子メール。
- *検疫*: 電子メールは検疫内にあり、ユーザーのメールボックスにはありません。
- *失敗:* 電子メールがメールボックスに届きに失敗しました。
- *削除済み*: メール フローのどこかでメールが失われました。

### <a name="email-timeline"></a>電子メール タイムライン

**電子メール タイムライン** は、管理者のハンティング エクスペリエンスを向上させる新しいエクスプローラー機能です。 イベントを理解しようとするために、さまざまな場所のチェックに費やされた時間が短縮されます。 電子メールが届くと同時に複数のイベントが発生するか、または近くで発生すると、それらのイベントはタイムライン ビューに表示されます。 メールの配信後に発生する一部のイベントは、[ **特別なアクション** ] 列にキャプチャされます。 管理者は、タイムラインからの情報と、配信後のメールに対して実行された特別なアクションとを組み合わせて、ポリシーの動作、メールが最終的にルーティングされた場所、および場合によっては最終的な評価の内容を把握できます。

詳細については、「[Office 365で配信された悪意のあるメールを調査して修復する」を](investigate-malicious-email-that-was-delivered.md)参照してください。

### <a name="export-url-click-data"></a>URL クリック データをエクスポートする

URL クリックのレポートをMicrosoft Excelにエクスポートして **、ネットワーク メッセージ ID** と **クリック判定** を表示できるようになりました。これにより、URL クリック トラフィックの発信元を説明できます。 動作方法は次のとおりです。Office 365クイック起動バーの脅威管理では、次のチェーンに従います。

**エクスプ ローラー** \>**フィッシングを表示する** \>**クリック** \>**[トップ URL]** または **[URL] トップ クリックで任意の**\>レコードを選択し、URL ポップアップを開きます。

一覧で URL を選択すると、ポップアップ パネルに新しい **[エクスポート]** ボタンが表示されます。 このボタンを使用すると、レポートを簡単にするためにExcelスプレッドシートにデータを移動できます。

リアルタイム検出レポートで同じ場所に移動するには、次のパスに従います。

**エクスプ ローラー** \>**リアルタイム検出** \>**フィッシングを表示する** \>**Url** \>**[トップ URL]** または **[トップ クリック] 任意の**\>レコードを選択して、[**クリック**] タブに移動して URL ポップアップ\>を開きます。

> [!TIP]
> ネットワーク メッセージ ID は、エクスプローラーまたは関連するサードパーティツールを使用して ID を検索するときに、クリックを特定のメールにマップします。 このような検索では、クリック結果に関連付けられている電子メールが識別されます。 関連付けられたネットワーク メッセージ ID を使用すると、より迅速かつ強力な分析が可能になります。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/tp_ExportClickResultAndNetworkID.png" alt-text="エクスプローラーの [クリック] タブ" lightbox="../../media/tp_ExportClickResultAndNetworkID.png":::

## <a name="see-malware-detected-in-email-by-technology"></a>電子メールで検出されたマルウェアをテクノロジ別に表示する

たとえば、Microsoft 365テクノロジで並べ替えられた電子メールでマルウェアが検出されたことを確認するとします。 これを行うには、エクスプローラーの [[Email > Malware](threat-explorer-views.md#email--malware) ] ビュー (またはリアルタイム検出) を使用します。

1. セキュリティ & コンプライアンス センター (<https://protection.office.com>) で、 **脅威管理** \> **エクスプローラー** (または **リアルタイム検出**) を選択します。 (この例ではエクスプローラーを使用します。

2. [ **表示** ] メニューの [ **電子メール** \> **マルウェア**] を選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerViewEmailMalwareMenu.png" alt-text="エクスプローラーの [表示] メニュー" lightbox="../../media/ExplorerViewEmailMalwareMenu.png":::

3. [ **送信者]** をクリックし、[ **基本** \> **検出テクノロジ**] を選択します。

   検出テクノロジは、レポートのフィルターとして使用できるようになりました。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerEmailMalwareDetectionTech.png" alt-text="マルウェア検出テクノロジ" lightbox="../../media/ExplorerEmailMalwareDetectionTech.png":::

4. オプションを選択します。 次に、[ **更新** ] ボタンを選択して、そのフィルターを適用します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerEmailMalwareDetectionTechATP.png" alt-text="選択された検出テクノロジ" lightbox="../../media/ExplorerEmailMalwareDetectionTechATP.png":::

レポートが更新され、選択したテクノロジ オプションを使用して、マルウェアが電子メールで検出した結果が表示されます。 ここから、さらに分析を行うことができます。

## <a name="view-phishing-url-and-click-verdict-data"></a>フィッシング URL を表示し、判定データをクリックする

許可、ブロック、およびオーバーライドされた URL の一覧を含む、メール内の URL を介したフィッシングの試行を確認するとします。 クリックされた URL を識別するには、[セーフ リンク](safe-links.md)を構成する必要があります。 クリック時の保護と[、セーフ リンク](set-up-safe-links-policies.md)によるクリックの判定のログ記録のために、セーフ リンク ポリシーを設定していることを確認します。

メッセージ内のフィッシング URL を確認し、フィッシング メッセージの URL をクリックするには、エクスプローラーまたはリアルタイム検出の [**EmailPhish** > ](threat-explorer-views.md#email--phish) ビューを使用します。

1. セキュリティ & コンプライアンス センター (<https://protection.office.com>) で、 **脅威管理** \> **エクスプローラー** (または **リアルタイム検出**) を選択します。 (この例ではエクスプローラーを使用します。

2. [ **表示** ] メニューの [ **電子メール** \> **フィッシング**] を選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerViewEmailPhishMenu.png" alt-text="フィッシング コンテキストでのエクスプローラーの [表示] メニュー" lightbox="../../media/ExplorerViewEmailPhishMenu.png":::

3. [**送信者]** をクリックし、[**URL**\>] **の [判定] をクリックします**。

4. **[ブロック]** や [**ブロック] のオーバーライド** など、1 つ以上のオプションを選択し、そのフィルターを適用するオプションと同じ行の **[更新**] ボタンを選択します。 (ブラウザー ウィンドウを更新しないでください)。)

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ThreatExplorerEmailPhishClickVerdictOptions.png" alt-text="URL とクリックの判定" lightbox="../../media/ThreatExplorerEmailPhishClickVerdictOptions.png":::

   レポートが更新され、レポートの下の [URL] タブに 2 つの異なる URL テーブルが表示されます。

   - **上位 URL は** 、フィルター処理したメッセージ内の URL であり、各 URL の電子メール配信アクション数です。 フィッシング メール ビューでは、通常、この一覧には正当な URL が含まれています。 攻撃者は、メッセージに適切な URL と悪い URL を組み合わせて配信しようとしますが、悪意のあるリンクをより興味深く見せようとします。 URL のテーブルは合計メール数で並べ替えられますが、ビューを簡略化するためにこの列は非表示です。

   - **トップ クリック** 数は、クリックされたリンクラップ URL のセーフであり、合計クリック数で並べ替えられます。 ビューを簡略化するために、この列も表示されません。 列ごとの合計数は、クリックされた URL ごとにセーフリンククリックの判定数を示します。 フィッシング メール ビューでは、通常、これらは疑わしい URL または悪意のある URL です。 ただし、ビューには、脅威ではなくフィッシング メッセージ内にある URL が含まれる可能性があります。 ラップされていないリンクの URL クリックはここには表示されません。

   2 つの URL テーブルには、配信アクションと場所によってフィッシングメール メッセージの上位 URL が表示されます。 テーブルには、警告にもかかわらずブロックまたはアクセスされた URL クリックが表示されるため、ユーザーに表示された潜在的な不適切なリンクと、ユーザーがクリックした可能性のあるリンクを確認できます。 ここから、さらに分析を行うことができます。 たとえば、グラフの下には、組織の環境でブロックされた電子メール メッセージの上位 URL が表示されます。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/ExplorerPhishClickVerdictURLs.png" alt-text="ブロックされたエクスプローラーの URL" lightbox="../../media/ExplorerPhishClickVerdictURLs.png":::

   URL を選択すると、詳細な情報が表示されます。

   > [!NOTE]
   > [URL ポップアップ] ダイアログ ボックスでは、電子メール メッセージのフィルター処理が削除され、環境内の URL の露出の完全なビューが表示されます。 これにより、エクスプローラーで関心のある電子メール メッセージをフィルター処理し、潜在的な脅威である特定の URL を検索し、エクスプローラー ビュー自体に URL フィルターを追加しなくても、環境内の URL 公開に関する理解を広めることができます。

### <a name="interpretation-of-click-verdicts"></a>クリック判定の解釈

電子メールまたは URL ポップアップ、トップ クリック数、およびフィルター処理エクスペリエンス内には、さまざまなクリック判定値が表示されます。

- **なし：** URL の判定をキャプチャできません。 ユーザーが URL をクリックした可能性があります。
- **許可：** ユーザーは URL に移動することができました。
- **ブロック：** ユーザーが URL への移動をブロックされました。
- **保留中の判定:** ユーザーに、起爆保留中のページが表示されました。
- **ブロックされたオーバーライド:** ユーザーが URL への直接移動をブロックされました。 ただし、ユーザーはブロックをオーバーロードして URL に移動します。
- **保留中の判定がバイパスされました。** ユーザーにデトネーション ページが表示されました。 ただし、ユーザーはメッセージをオーバーロードして URL にアクセスします。
- **エラー：** ユーザーにエラー ページが表示されたか、判定のキャプチャ中にエラーが発生しました。
- **失敗：** 判定のキャプチャ中に不明な例外が発生しました。 ユーザーが URL をクリックした可能性があります。

## <a name="review-email-messages-reported-by-users"></a>ユーザーによって報告された電子メール メッセージを確認する

レポート メッセージ [アドインまたはレポート](enable-the-report-message-add-in.md) フィッシング アドインを使用して、組織内のユーザーが *迷惑* メール、*迷惑メールではない*、または *フィッシングとして* 報告した電子メール メッセージ [を](enable-the-report-phish-add-in.md)表示するとします。 それらを表示するには、エクスプローラー (またはリアルタイム検出) の [**EmailSubmissions** > ](threat-explorer-views.md#email--submissions) ビューを使用します。

1. セキュリティ & コンプライアンス センター (<https://protection.office.com>) で、 **脅威管理** \> **エクスプローラー** (または **リアルタイム検出**) を選択します。 (この例ではエクスプローラーを使用します。

2. [ **表示** ] メニューの [ **電子メール** \> **送信]** を選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/explorer-view-menu-email-user-reported.png" alt-text="メールのエクスプローラーの [表示] メニュー" lightbox="../../media/explorer-view-menu-email-user-reported.png":::

3. [ **送信者**] をクリックし、[ **基本** \> **レポートの種類**] を選択します。

4. **[フィッシング**] などのオプションを選択し、[**更新**] ボタンを選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/EmailUserReportedReportType.png" alt-text="ユーザーから報告されたフィッシング" lightbox="../../media/EmailUserReportedReportType.png":::

レポートが更新され、組織内のユーザーがフィッシング詐欺の試みとして報告した電子メール メッセージに関するデータが表示されます。 この情報を使用してさらなる分析を行い、必要に応じて[Microsoft Defender for Office 365でフィッシング対策ポリシーを](configure-mdo-anti-phishing-policies.md)調整できます。

## <a name="start-automated-investigation-and-response"></a>自動調査と対応を開始する

> [!NOTE]
> 自動調査と対応機能は、*Microsoft Defender for Office 365プラン 2* および *Office 365 E5* で利用できます。

[自動調査と対応により、](automated-investigation-response-office.md) セキュリティ運用チームがサイバー攻撃の調査と軽減に費やした時間と労力を節約できます。 セキュリティ プレイブックをトリガーできるアラートの構成に加えて、エクスプローラーのビューから自動調査と応答プロセスを開始できます。 詳細については、「 [例: セキュリティ管理者がエクスプローラーから調査をトリガーする」を](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)参照してください。

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>エクスプローラーとリアルタイム検出を使用するその他の方法

この記事で説明するシナリオに加えて、エクスプローラー (またはリアルタイム検出) で使用できるレポート オプションも多数用意されています。 次の記事をご覧ください。

- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online、OneDrive、Microsoft Teamsで検出された悪意のあるファイルを表示する](./mdo-for-spo-odb-and-teams.md)
- [脅威エクスプローラー (およびリアルタイム検出) でビューの概要を取得する](threat-explorer-views.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 365 Defender での自動調査と応答](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

エクスプローラーまたはリアルタイム検出を使用する[Microsoft Defender for Office 365](defender-for-office-365.md)が必要です。

- エクスプローラーは、Defender for Office 365 プラン 2 に含まれています。
- リアルタイム検出レポートは、Defender for Office 365 プラン 1 に含まれています。
- Defender for Office 365で保護する必要があるすべてのユーザーにライセンスを割り当てる計画を立てます。 エクスプローラーとリアルタイム検出では、ライセンスを持つユーザーの検出データが表示されます。

エクスプローラーまたはリアルタイム検出を表示して使用するには、セキュリティ管理者やセキュリティ リーダーに付与されたアクセス許可など、適切なアクセス許可が必要です。

- セキュリティ & コンプライアンス センターでは、次のいずれかのロールが割り当てられている必要があります。

  - 組織の管理
  - セキュリティ管理者 (Azure Active Directory管理センターで割り当てることができます (<https://aad.portal.azure.com>)
  - セキュリティ閲覧者

- Exchange Onlineでは、Exchange管理センター (EAC) または [powerShell](/powershell/exchange/exchange-online-powershell) Exchange Onlineで、次のいずれかのロールが割り当てられている必要があります。

  - 組織の管理
  - 表示専用組織の管理
  - "View-Only Recipients/表示専用受信者"
  - コンプライアンス管理

ロールとアクセス許可の詳細については、次のリソースを参照してください。

- [Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)
- [Exchange Online の機能アクセス許可](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>脅威エクスプローラーとリアルタイム検出の違い

- *リアルタイム検出* レポートは、Defender for Office 365 プラン 1 で使用できます。 *脅威エクスプローラー* は、Defender for Office 365 プラン 2 で利用できます。
- リアルタイム検出レポートを使用すると、検出をリアルタイムで表示できます。 脅威エクスプローラーでも同様に行われますが、特定の攻撃に関する追加の詳細も提供されます。
- *[すべてのメール*] ビューは、脅威エクスプローラーでは使用できますが、リアルタイム検出レポートでは使用できません。
- その他のフィルター処理機能と使用可能なアクションは、脅威エクスプローラーに含まれています。 詳細については、「[Microsoft Defender for Office 365 サービスの説明: Defender for Office 365 プラン間の機能の可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

## <a name="other-articles"></a>その他の記事

[[電子メール エンティティ] ページを使用して電子メールを調査する](mdo-email-entity-page.md)
