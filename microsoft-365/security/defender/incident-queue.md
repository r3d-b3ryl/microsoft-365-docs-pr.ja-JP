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
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 0705424080f58d58f8c45b4a403fae01beb53373
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2021
ms.locfileid: "61128834"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>グループ内のインシデントに優先順位をMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender関連するアラートと、さまざまな製品からの自動調査をインシデントに適用します。 Microsoft 365 Defenderは、Microsoft 365 Defender が製品のスイート全体で持つエンドツーエンドの可視性を考えると、悪意のあるアクティビティとしてのみ識別できるアクティビティに対する一意のアラートをトリガーします。 このビューは、セキュリティ アナリストに広範な攻撃ストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。

インシデント **キューには、** デバイス、ユーザー、メールボックス間で作成されたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。 これはインシデント トリアージとも呼ばれる。

インシデント ポータルのクイック 起動でインシデント &**アラート**>インシデント キューに <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderします</a>。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

[ **最新のインシデントと** 通知] セクションには、過去 24 時間に受信したアラートとインシデントが作成された数のグラフが表示されます。

既定では、ポータル内のインシデント キュー Microsoft 365 Defender過去 6 か月間に発生したインシデントが表示されます。 最新のインシデントはリストの一番上にあるので、最初に確認できます。

インシデント キューには、インシデントの異なる特性や影響を受けたエンティティを表示できるカスタマイズ可能な列 ([列の選択] を選択) があります。 これにより、分析のためのインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。

一目で見える表示を追加するために、インシデントの自動名前付けにより、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。 これにより、インシデントの範囲をすばやく把握できます。

たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

> [!NOTE]
> 自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前は変更されません。

インシデント キューでは、複数のフィルター オプションも公開されます。適用すると、環境内のすべての既存のインシデントの広範なスイープを実行したり、特定のシナリオや脅威に集中することができます。 インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。 

## <a name="available-filters"></a>利用可能なフィルター

既定のインシデント キューから [フィルター] を **選択して** [フィルター] ウィンドウを表示し、そこからフィルター処理されたインシデントのセットを表示できます。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="インシデント キューのフィルター ウィンドウの例。" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

既定のフィルターは、[新規] および [進行中] 状態のすべてのアラートと **インシデント****を表示** します。

次の表に、使用可能なフィルター名を示します。

| フィルター名 | 説明 |
|:-------|:-----|
| 状態 | [**新規]、[****進行中]、または**[**解決済み] を選択します**。 |
| 重要度 | インシデントの重大度は、資産に与える影響を示しています。 重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。 [**高]、[****中]、[****低]、または** **[Informational] を選択します**。 |
| インシデントの割り当て | [すべてのユーザーに割り当て済み]、[自分に割り当て済み]、または [割り当て解除] を選択します。 |
| 複数のサービス ソース  | フィルターが複数のサービス ソース用であるかどうかを指定します。 |
| サービス ソース  | フィルターを適用して、アプリ ガバナンス、Microsoft 365 Defender、microsoft Defender for Office 365、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps のアラートを含むインシデントのみを表示します。 |
| タグ | リストから 1 つ以上のタグ名を選択します。 |
| 複数のカテゴリ  | フィルターが複数のカテゴリの場合に使用するかどうかを指定します。 |
| Categories | カテゴリを選択して、見られる特定の戦術、テクニック、または攻撃コンポーネントに焦点を当てる。 |
| OS プラットフォーム | オペレーティング システムによってインシデント キュー ビューを制限します。 |
| 分類 | 関連するアラートの一連の分類に基づいてインシデントをフィルター処理します。 [True **alert] 、False** **Alerts 、または** **[Not set] を選択します**。 |
| 調査の状態 | 自動調査の状態によってインシデントをフィルター処理します。  |
| 関連する脅威 | 名前付き脅威によってインシデントをフィルター処理します。  |
| Actors | 名前付き脅威アクターによってインシデントをフィルター処理します。  |
| データの機密性 | 一部の攻撃では、機密データや貴重なデータを排除することを目的としています。 機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。 <br><br>このフィルターは、有効になっているMicrosoft Information Protection使用できます。|
|||

## <a name="save-defined-filters-as-urls"></a>定義されたフィルターを URL として保存する

インシデント キューで便利なフィルターを構成したら、ブラウザー タブの URL をブックマークするか、Web ページ、Word ドキュメント、または選択した場所にリンクとして保存できます。 これにより、次のようなインシデント キューの主要なビューにシングル クリックでアクセスできます。

- 新しいインシデント
- 重大度の高いインシデント
- 割り当てられていないインシデント
- 重大度が高く、割り当てられていないインシデント
- 割り当てられたインシデント
- Microsoft Defender for Endpoint に割り当てられたインシデント
- 特定のタグまたはタグを持つインシデント
- 特定の脅威カテゴリを持つインシデント
- 特定の関連付けられた脅威を持つインシデント
- 特定のアクターを持つインシデント

有用なフィルター ビューのリストを URL としてコンパイルして保存したら、それを使用してキュー内のインシデントをすばやく処理および優先順位付けし、[](manage-incidents.md)後続の割り当てと分析のために管理できます。

## <a name="next-steps"></a>次の手順

優先度が最も高いインシデントを決定した後、そのインシデントを選択し、次の操作を行います。

- [タグ](manage-incidents.md) 、割り当て、誤検知インシデントの即時解決、およびコメントのインシデントのプロパティを管理します。
- 調査を [開始します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
