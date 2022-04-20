---
title: Microsoft 365 Defenderのインシデントに優先順位を付ける
description: Microsoft 365 Defenderのインシデント キューからインシデントをフィルター処理する方法について説明します
keywords: インシデント, キュー, 概要, デバイス, ID, ユーザー, メールボックス, 電子メール, インシデント, 分析, 応答, トリアージ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 285da473c8e8035a28ee6e64c4950e2b8fe373f5
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64944417"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defenderのインシデントに優先順位を付ける

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender関連付け分析を適用し、関連するアラートと、さまざまな製品からの自動調査をインシデントに集計します。 Microsoft 365 Defenderでは、製品スイート全体にわたるMicrosoft 365 Defenderのエンドツーエンドの可視性を考慮すると、悪意のあるアクティビティとしてのみ識別できるアクティビティに対する一意のアラートもトリガーされます。 このビューは、セキュリティ アナリストに広範な攻撃ストーリーを提供します。これにより、組織全体の複雑な脅威をより深く理解し、対処するのに役立ちます。

**インシデント キュー** には、デバイス、ユーザー、メールボックス間で作成されたインシデントのコレクションが表示されます。 インシデントを並べ替えて、インシデントトリアージと呼ばれるプロセスである情報に基づいたサイバーセキュリティ対応の決定を優先順位付けし、作成するのに役立ちます。

Microsoft 365 Defender ポータルのクイック起動時に **、インシデント&アラート>インシデントからインシデント** キューにアクセス <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">します</a>。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender ポータルでインシデント キューを示す [インシデント] セクション。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

[ **最新のインシデントとアラート]** セクションには、受信したアラートの数と過去 24 時間に作成されたインシデントのグラフが表示されます。

既定では、Microsoft 365 Defender ポータルのインシデント キューには、過去 6 か月間に発生したインシデントが表示されます。 最新のインシデントは一覧の一番上に表示されるため、最初に確認できます。

インシデント キューには、インシデントまたは影響を受けるエンティティのさまざまな特性を視覚化できるカスタマイズ可能な **列 ([列の選択]** を選択) があります。 これにより、分析のためにインシデントの優先順位付けに関する情報に基づいた意思決定を行うことができます。

一目でわかるように、自動インシデントの名前付けでは、影響を受けるエンドポイントの数、影響を受けたユーザー、検出ソース、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。 これにより、インシデントの範囲をすばやく把握できます。

たとえば、 *複数のソースによって報告された複数のエンドポイントに対する多段階インシデント。*

> [!NOTE]
> 自動インシデントの名前付けのロールアウト前に存在していたインシデントの名前は変更されません。

インシデント キューには、複数のフィルターオプションも用意されています。このオプションを適用すると、環境内のすべての既存のインシデントを広範にスイープしたり、特定のシナリオや脅威に焦点を当てたりすることができます。 インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。 

インシデントの一覧の上にある **フィルター** の一覧には、現在適用されているフィルターが表示されます。

## <a name="available-filters"></a>利用可能なフィルター

既定のインシデント キューから [ **フィルター** ] を選択すると、[ **フィルター** ] ウィンドウが表示され、そこからフィルター処理されたインシデントのセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Microsoft 365 Defender ポータルのインシデント キューの [フィルター] ウィンドウ。" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

インシデント **の一** 覧の上にあるフィルターの一覧でフィルターを選択すると、[ **フィルター** ] ウィンドウも表示されます。

次の表に、使用可能なフィルター名を示します。

| フィルター名 | 説明 |
|:-------|:-----|
| 状態 | [ **新規]**、[ **進行中]**、または **[解決済み**] を選択します。 |
| 重要度 | インシデントの重大度は、資産に与える影響を示します。 重大度が高いほど影響が大きくなり、通常は最も迅速な注意が必要です。 **[高**]、[**中]**、[**低]**、または **[情報**] を選択します。 |
| インシデントの割り当て | 割り当てられたユーザーまたはユーザーを選択します。 |
| 複数のサービス ソース  | フィルターが複数のサービス ソースに対して行われるかどうかを指定します。 |
| サービス ソース  | アプリ ガバナンス、Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps。 |
| タグ | 一覧から 1 つまたは複数のタグ名を選択します。 |
| 複数のカテゴリ  | フィルターが複数のカテゴリに適用されるかどうかを指定します。 |
| カテゴリ | カテゴリを選択して、特定の戦術、手法、または攻撃コンポーネントに焦点を当てます。 |
| Entities | ユーザー、デバイス、メールボックス、アプリケーション名などの資産の名前を指定します。 |
| データの機密性 | 一部の攻撃では、機密データや貴重なデータを排除することを目的としています。 特定の秘密度ラベルのフィルターを適用することで、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントに対処する優先順位を付けることができます。 <br><br> このフィルターは、[Microsoft Purview Information Protectionから秘密度ラベル](../../compliance/sensitivity-labels.md)を適用した場合にのみ情報を表示します。 |
| デバイス グループ | [デバイス グループ](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)名を指定します。 |
| OS プラットフォーム | デバイス オペレーティング システムを指定します。 |
| 分類 | 関連するアラートの分類のセットを指定します。 |
| 自動調査の状態 | 自動調査の状態を指定します。  |
| 関連する脅威 | 名前付き脅威を指定します。  |
| Actors | 名前付き脅威アクターを指定します。  |
|||

既定のフィルターでは、 **状態が [新規** ] と **[進行中** ] で重大度が **[低**]、[ **中**]、または **[高**] のすべてのアラートとインシデントが表示されます。

フィルターの名前の **X** を [フィルター **] ボックスの** 一覧で選択すると、フィルターをすばやく削除できます。 

## <a name="save-custom-filters-as-urls"></a>カスタム フィルターを URL として保存する

インシデント キューで便利なフィルターを構成したら、ブラウザー タブの URL をブックマークするか、Web ページ、Word 文書、または任意の場所にリンクとして保存できます。 これにより、次のようなインシデント キューのキー ビューにシングル クリックでアクセスできます。

- 新しいインシデント
- 重大度の高いインシデント
- 割り当てられていないインシデント
- 重大度が高く、割り当てられていないインシデント
- 自分に割り当てられたインシデント
- 自分とMicrosoft Defender for Endpointに割り当てられたインシデント
- 特定のタグまたはタグを持つインシデント
- 特定の脅威カテゴリを持つインシデント
- 特定の関連する脅威を含むインシデント
- 特定のアクターを含むインシデント

有用なフィルター ビューの一覧をコンパイルして URL として保存したら、それを使用して、キュー内のインシデントをすばやく処理して優先順位を付け、後続の割り当てと分析のために [管理](manage-incidents.md) できます。

## <a name="search-for-incidents"></a>インシデントを検索する

インシデントの一覧の上にある **[名前または ID の検索** ] ボックスから、インシデント ID またはインシデント名を入力できます。 検索結果の一覧からインシデントを選択すると、Microsoft 365 Defender ポータルにインシデントのプロパティを含む新しいタブが開き、[そこから調査](investigate-incidents.md)を開始できます。

## <a name="search-for-impacted-assets"></a>影響を受けた資産を検索する

assetsuch&mdash; をユーザー、デバイス、メールボックス、またはアプリケーション名として名前&mdash;付けし、関連するすべてのインシデントを検索できます。 

## <a name="specify-a-time-range"></a>時間範囲を指定する

インシデントの既定の一覧は、過去 6 か月間に発生したインシデントの一覧です。 予定表アイコンの横にあるドロップダウン ボックスから新しい時間範囲を指定するには、次を選択します。

 - 1 日
 - 3 日間
 - 1 週間
 - 30 日間
 - 30 日間
 - 6 か月
 - 日付と時刻の両方を指定できるカスタム範囲

## <a name="next-steps"></a>次の手順

優先度が最も高いインシデントが必要であると判断したら、それを選択し、次の操作を行います。

- タグ、割り当て、偽陽性インシデントの即時解決、コメントのインシデントのプロパティを[管理](manage-incidents.md)します。
- 調査を開始 [します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
