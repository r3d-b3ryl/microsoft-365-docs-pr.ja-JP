---
title: グループ内のインシデントに優先順位をMicrosoft 365 Defender
description: インシデント キューからインシデントをフィルター処理する方法については、Microsoft 365 Defender
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、電子メール、インシデント、分析、応答、トリアージ
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
ms.openlocfilehash: 2d5477122a29c672a947a2022f49da3abeb7003b
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568546"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>グループ内のインシデントに優先順位をMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender関連するアラートと、さまざまな製品からの自動調査をインシデントに適用します。 Microsoft 365 Defenderは、Microsoft 365 Defender のエンド to エンドの可視性が製品のスイート全体にわたってある場合にのみ、悪意のあるアクティビティとして識別できるアクティビティに対する一意のアラートをトリガーします。 このビューにより、セキュリティ アナリストは広範な攻撃ストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。

インシデント **キューには、** デバイス、ユーザー、メールボックス間で作成されたインシデントのコレクションが表示されます。 インシデントを並べ替え、情報に基づいたサイバーセキュリティ対応の決定 (インシデント トリアージと呼ばれるプロセス) を作成するのに役立ちます。

インシデント ポータルのクイック起動時に、インシデント &**アラート**>インシデント キューに <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderきます</a>。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント ポータルのインシデント キューを表示する [インシデント] Microsoft 365 Defenderします。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

[ **最新のインシデントと** 通知] セクションには、過去 24 時間に受信したアラートとインシデントが作成された数のグラフが表示されます。

既定では、ポータル内のインシデント キュー Microsoft 365 Defender過去 6 か月間に発生したインシデントが表示されます。 最新のインシデントはリストの一番上にあるので、最初に確認できます。

インシデント キューには、インシデントの異なる特性や影響を受けたエンティティを表示できるカスタマイズ可能な列 ([列の **選択] を** 選択) があります。 これにより、分析のためのインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。

一目で見える表示を追加するために、インシデントの自動名前付けにより、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。 これにより、インシデントの範囲をすばやく把握できます。

たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

> [!NOTE]
> 自動インシデント名前付けのロールアウト前に存在していたインシデントは、その名前は変更されません。

また、インシデント キューには複数のフィルター オプションが用意されています。適用すると、環境内のすべての既存のインシデントの広範なスイープを実行したり、特定のシナリオや脅威に集中することができます。 インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。 

インシデント **の一** 覧の上にある [フィルター] リストには、現在適用されているフィルターが表示されます。

## <a name="available-filters"></a>利用可能なフィルター

既定のインシデント キューから[フィルター] を **選択すると、[** フィルター] ウィンドウが表示され、そこからフィルター処理されたインシデントのセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="ポータル内のインシデント キューの [フィルター] ウィンドウMicrosoft 365 Defenderします。" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

[フィルター] ウィンドウを **表示するには**、インシデントの一覧の上にある [フィルター] リストでフィルターを選択します。

次の表に、使用可能なフィルター名を示します。

| フィルター名 | 説明 |
|:-------|:-----|
| 状態 | [**新規]、****[進行中]、または** [**解決済み] を選択します**。 |
| 重要度 | インシデントの重大度は、資産に与える影響を示しています。 重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。 [**高、****中、低、****または** 情報] **を選択します**。 |
| インシデントの割り当て | 割り当てられたユーザーまたはユーザーを選択します。 |
| 複数のサービス ソース  | フィルターが複数のサービス ソース用であるかどうかを指定します。 |
| サービス ソース  | 通知を含むインシデントの指定: アプリ ガバナンス、Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps。 |
| タグ | リストから 1 つ以上のタグ名を選択します。 |
| 複数のカテゴリ  | フィルターが複数のカテゴリの場合に使用するかどうかを指定します。 |
| Categories | カテゴリを選択して、見られる特定の戦術、テクニック、または攻撃コンポーネントに焦点を当てる。 |
| Entities | ユーザー、デバイス、メールボックス、アプリケーション名などのアセットの名前を指定します。 |
| データの機密性 | 一部の攻撃では、機密データや貴重なデータを排除することを目的としています。 特定の機密ラベルにフィルターを適用することで、機密情報が侵害された可能性があるかどうかを迅速に判断し、それらのインシデントに対処する優先順位を付けできます。 <br><br> このフィルターは、有効になっているMicrosoft Information Protection使用できます。 |
| デバイス グループ | デバイス グループ [名を指定](/windows/security/threat-protection/microsoft-defender-atp/machine-groups) します。 |
| OS プラットフォーム | デバイス オペレーティング システムを指定します。 |
| 分類 | 関連するアラートの分類のセットを指定します。 |
| 自動調査の状態 | 自動調査の状態を指定します。  |
| 関連する脅威 | 名前付き脅威を指定します。  |
| Actors | 名前付き脅威アクターを指定します。  |
|||

既定のフィルターでは、状態が [新規] および [進行中] で、重大度が **"** 低"、"中"、または "高" のアラートと **インシデントすべてが表示****されます**。

フィルターの名前で [フィルター] ボックスの一覧で **[X** ] を選択すると、フィルターをすばやく **削除** できます。 

## <a name="save-custom-filters-as-urls"></a>カスタム フィルターを URL として保存する

インシデント キューで便利なフィルターを構成したら、ブラウザー タブの URL をブックマークするか、Web ページ、Word ドキュメント、または選択した場所にリンクとして保存できます。 これにより、次のようなインシデント キューの主要なビューにシングル クリックでアクセスできます。

- 新しいインシデント
- 重大度の高いインシデント
- 割り当てられていないインシデント
- 重大度が高く、割り当てられていないインシデント
- 割り当てられたインシデント
- ユーザーとユーザーに割り当てられたインシデントMicrosoft Defender for Endpoint
- 特定のタグまたはタグを持つインシデント
- 特定の脅威カテゴリを持つインシデント
- 特定の関連付けられた脅威を持つインシデント
- 特定のアクターを持つインシデント

有用なフィルター ビューのリストを URL としてコンパイルして保存したら、それを使用してキュー内のインシデントをすばやく処理および優先順位付けし、後続の割[](manage-incidents.md)り当てと分析のために管理できます。

## <a name="search-for-incidents"></a>インシデントの検索

インシデントの **一覧の上にある [名前または ID** の検索] ボックスから、インシデント ID またはインシデント名を入力できます。 検索結果の一覧からインシデントを選択すると、Microsoft 365 Defender ポータルがインシデントのプロパティを含む新しいタブを開き、そこから調査を開始[できます](investigate-incidents.md)。

## <a name="search-for-impacted-assets"></a>影響を受け取ったアセットを検索する

ユーザー、デバイス、メールボックス&mdash;、またはアプリケーション名&mdash;などのアセットに名前を付け、関連するインシデントを検索できます。 

## <a name="specify-a-time-range"></a>時間範囲の指定

インシデントの既定の一覧は、過去 6 か月間に発生したインシデントの一覧です。 カレンダー アイコンの横にあるドロップダウン ボックスから新しい時間範囲を指定するには、次の項目を選択します。

 - 1 日
 - 3 日間
 - 1 週間
 - 30 日間
 - 30 日間
 - 6 か月
 - 日付と時刻の両方を指定できるカスタム範囲

## <a name="next-steps"></a>次の手順

優先度が最も高いインシデントを決定した後、そのインシデントを選択し、次の操作を行います。

- [タグ](manage-incidents.md) 、割り当て、誤検知インシデントの即時解決、およびコメントのインシデントのプロパティを管理します。
- 調査を [開始します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
